---
title: Architettura dei dati
description: Scopri come Marketo Optimizer e Marketo Engage condividono i dati, tra cui la direzione e la latenza della sincronizzazione delle entità, il flusso di dati delle attività e l’isolamento dei dati basato su sandbox.
role: User, Admin
autotag-review: '2026-10-01T18:40:38.362Z'
TQID: 'https://experienceleague.adobe.com/oelEtys81g6TzM8bi-qy1nuWw6scOBry7tbZkMkZ6u0'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
  - id: 3cf5f37e-e87e-5179-812b-53ce05d7eebb
    internal-label: Setup
  - id: 46e599c6-e20f-5f67-9824-93415016f66b
    internal-label: Audiences
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
    internal-label: Journeys
  - id: d4203578-d294-5145-b397-f26f4488a904
    internal-label: Channels
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
source-git-commit: 518a807aeed2471772b4f0a4d6d8d525cd3e22fd
workflow-type: tm+mt
source-wordcount: '771'
ht-degree: 1%
---

# Architettura dei dati

[!DNL Adobe Marketo Optimizer] si integra con [!DNL Adobe Marketo Engage] per fornire una visualizzazione completa dei lead B2B. Una sincronizzazione bidirezionale e affidabile mantiene entrambi i prodotti allineati, in modo che condividano una sola vista di persone, aziende, oggetti personalizzati e attività. [!DNL Marketo Engage] rimane l&#39;origine autorevole per i dati personali. Ogni istanza [!DNL Marketo Optimizer] è associata a un&#39;istanza [!DNL Marketo Engage].

## Data Foundation {#data-foundation}

[!DNL Marketo Optimizer] e [!DNL Marketo Engage] condividono una base dati comune che ne mantiene la sincronizzazione durante l&#39;alimentazione delle analisi a valle.

![Diagramma dell&#39;architettura di Marketo Optimizer e Marketo Engage che mostra il modo in cui i servizi, i tempi di esecuzione e gli archivi dati dei due prodotti si connettono tra Microsoft Azure e AWS](./assets/marketo-optimizer-architecture.svg)

Ad alto livello:

* **[!DNL Marketo Engage]** è l&#39;origine definitiva dei dati oggetto personalizzati e lead, che garantisce l&#39;integrità dei dati nel punto di acquisizione.
* Un livello **Data Broker** coordina il modo in cui i dati si spostano tra i due prodotti. Aggrega i dati condivisi e replicati in un database operativo pronto per l&#39;uso. L&#39;intero scambio viene eseguito all&#39;interno di un singolo cluster Aurora MySQL.
* **[!DNL Marketo Optimizer]** è l&#39;origine autorevole per le attività di percorso eseguite.

## Sincronizzazione entità {#entity-sync}

Ogni tipo di entità viene sincronizzato nella direzione e alla velocità che meglio protegge l’integrità dei dati.

| Entità [!DNL Marketo Engage] | Direzione di sincronizzazione | Latenza |
| --- | --- | --- |
| Lead | Bidirezionale | Meno di 1 secondo |
| Azienda | Bidirezionale | Meno di 1 secondo |
| Oggetto personalizzato | Unidirezionale | Meno di 5 secondi |
| Attività | Unidirezionale | Meno di 5 secondi |
| iscrizione al programma | Non sincronizzato | Non applicabile |
| Risorse | Non sincronizzato | Non applicabile |

La sincronizzazione funziona in due modi:

* **Lead, società e oggetti standard:** [!DNL Marketo Engage] è il proprietario della tabella persona e la condivide tramite le visualizzazioni del database di lettura e scrittura. Gli aggiornamenti di un prodotto vengono visualizzati immediatamente nell’altro e non vengono create copie duplicate.
* **Oggetti personalizzati:** I dati vengono replicati da [!DNL Marketo Engage] in pochi secondi. Gli aggiornamenti dello schema in [!DNL Marketo Engage] sono immediatamente disponibili per i percorsi attivi.

[!DNL Marketo Engage] e [!DNL Marketo Optimizer] non sincronizzano l&#39;appartenenza al programma o le risorse. Questa esclusione consente di preservare la velocità e l&#39;integrità del sistema.

>[!NOTE]
>
>I dati sincronizzati con [!DNL Marketo Optimizer] e il data warehouse sono infine coerenti. La tempistica dipende dal meccanismo di acquisizione, batch o flusso dei dati di modifica sottostante.

Questa progettazione in tempo reale ti permette di ottenere i dati correnti in percorsi e rapporti. Puoi seguire rapidamente i lead con priorità alta. Puoi anche utilizzare i dati contestuali B2B, come l’utilizzo e l’intento del prodotto, nelle decisioni del percorso man mano che cambiano.

## Flusso di dati di attività {#activity-flow}

Le attività seguono un percorso separato dalle altre entità. Ogni attività si sposta in cinque fasi:

1. **Acquisizione primaria:** [!DNL Marketo Engage] scrive l&#39;attività nel relativo database condiviso e la indicizza in Apache SOLR per una ricerca rapida in [!DNL Marketo Engage].
1. **Riconoscimento tra prodotti:** [!DNL Marketo Engage] pubblica l&#39;attività nella pipeline dell&#39;attività, quindi [!DNL Marketo Optimizer] la riceve immediatamente.
1. **Trasformazione analitica:** Il runtime di percorso elabora l&#39;attività e la scrive in Snowflake, che trasforma i dati operativi in dati pronti per l&#39;analisi. Tutte le fasi finora vengono eseguite in Amazon Web Services (AWS).
1. **Destinazione a valle:** [!DNL Marketo Optimizer] replica l&#39;attività in [!DNL Adobe Experience Platform] set di dati.
1. **Generazione rapporti:** I set di dati feed incorporano [!DNL Adobe Customer Journey Analytics] rapporti. [!DNL Customer Journey Analytics] può essere ospitato su Microsoft Azure o AWS. È inoltre possibile eseguire query sui set di dati con [!DNL Query Service]. Consulta [Set di dati di Experience Platform](./reports/aep-datasets.md).

I percorsi e i tipi di pubblico di eventi possono utilizzare sia attività [!DNL Marketo Optimizer] che un sottoinsieme di attività [!DNL Marketo Engage]. Entrambi i set vengono utilizzati allo stesso modo. [!DNL Marketo Optimizer] attività non vengono rimandate a [!DNL Marketo Engage].

Utilizza attività come riempimenti di moduli, visite web e coinvolgimento via e-mail per attivare, filtrare e diramare percorsi di persone:

* [Trigger di eventi per il nodo Ascolta un evento](./marketing/listen-for-event-nodes.md#event-triggers)
* [Filtri di eventi per il nodo Ascolta un evento](./marketing/listen-for-event-nodes.md#event-filters)
* [Filtri di persona corrispondenti per i nodi dei percorsi suddivisi](./marketing/split-merge-paths-nodes.md#matched-person-filters)
* [Tipi di pubblico basati su eventi](./audiences/event-based-audiences.md)

## Isolamento dei dati e sandbox {#data-isolation}

[!DNL Marketo Engage], [!DNL Marketo Optimizer] e [!DNL Experience Platform] condividono i dati dei clienti come parte di questa architettura. Adobe isola in modo logico i dati da altri tenant utilizzando le sandbox [!DNL Experience Platform]. I dati vengono trasferiti su canali crittografati e protetti. Adobe lo archivia in Adobe Managed Services con crittografia e controlli degli accessi standard.

Ogni istanza di [!DNL Marketo Optimizer] dispone di una scheda prodotto dedicata in [!DNL Adobe Admin Console] e di una sandbox dedicata. Adobe esegue il provisioning di entrambi automaticamente, pertanto non crea una sandbox. Il nome della sandbox utilizza il pattern `mktoaep<prefix>`, in cui il prefisso è il prefisso [!DNL Marketo Engage]. Se utilizzi [!DNL Marketo Optimizer] con più istanze di [!DNL Marketo Engage], ogni istanza ha la propria scheda prodotto e la propria sandbox.

[!DNL Marketo Optimizer] è disponibile solo in questa sandbox, anche se la tua organizzazione ha altre sandbox.

Il provisioning non assegna l’accesso alla sandbox. In genere i ruoli hanno accesso alla sandbox predefinita `prod`, ma [!DNL Marketo Optimizer] non la utilizza. Assegnare in modo esplicito la sandbox dedicata a ogni ruolo [!DNL Experience Platform] oppure gli utenti non possono lavorare in [!DNL Marketo Optimizer]. Utilizzare i gruppi di utenti per aggiungere e rimuovere utenti senza ripetere l&#39;impostazione dei ruoli. Per la procedura completa, vedere [Accesso utente e autorizzazioni](./start/user-management.md).

[!DNL Marketo Optimizer] utilizza anche [!DNL Experience Platform] servizi in background. Tra questi il registro degli schemi, le destinazioni per l&#39;esportazione di file multimediali a pagamento, il controllo degli accessi e [!DNL Customer Journey Analytics]. Non impostare schemi o spazi dei nomi. [!DNL Marketo Optimizer] non richiede [!DNL Real-Time Customer Data Platform], Real-Time Customer Profile o segmentazione.

>[!WARNING]
>
>Non eliminare la sandbox [!DNL Marketo Optimizer] dedicata. L’eliminazione è permanente e non può essere annullata. Rieseguire il provisioning di [!DNL Marketo Optimizer] per il ripristino.
