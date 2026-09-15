---
title: Architettura di alto livello
description: Scopri l’architettura dei dati che collega Marketo Optimizer e Marketo Engage, inclusa la sincronizzazione bidirezionale, la latenza delle entità e l’isolamento dei dati del tenant.
role: User, Admin
TQID: 'https://experienceleague.adobe.com/oelEtys81g6TzM8bi-qy1nuWw6scOBry7tbZkMkZ6u0'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
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
source-git-commit: 1524f9f9e63044a11cd54d3299fa4d1e49172cb1
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 1%
---

# Architettura di alto livello

[!DNL Adobe Marketo Optimizer] si integra con [!DNL Adobe Marketo Engage] per fornire una visualizzazione completa dei lead B2B. Una sincronizzazione bidirezionale e affidabile mantiene allineati [!DNL Marketo Engage] e [!DNL Marketo Optimizer], offrendo a entrambe le piattaforme un&#39;unica visualizzazione condivisa di Persone, Aziende, Oggetti personalizzati e Attività. Il flusso di dati in tempo reale e ad alte prestazioni garantisce la disponibilità e l&#39;operatività dei record, in modo che le campagne e i percorsi possano rispondere ai lead nel momento in cui interagiscono.

## Data Foundation

[!DNL Marketo Optimizer] e [!DNL Marketo Engage] condividono una base dati comune che ne mantiene la sincronizzazione durante l&#39;alimentazione delle analisi a valle.

![Diagramma dell&#39;architettura di Marketo Optimizer e Marketo Engage che mostra il modo in cui i servizi, i runtime e gli archivi dati dei due prodotti si connettono tra Microsoft Azure e AWS](./assets/marketo-optimizer-architecture.svg)

Ad alto livello:

* **[!DNL Marketo Engage]Core** è l&#39;origine definitiva per i dati di lead e oggetto personalizzato, garantendo l&#39;integrità dei dati nel punto di acquisizione.
* Un livello **Data Broker** coordina lo spostamento dei dati tra [!DNL Marketo Engage] e [!DNL Marketo Optimizer], aggregando i dati condivisi e replicati in un ambiente operativo pronto all&#39;uso. L’intero scambio viene eseguito all’interno di una singola istanza AWS Aurora condivisa, formando la base a loop chiuso per l’orchestrazione B2B su larga scala.
* **Le attività** seguono un percorso definito: vengono inizialmente scritte nel database [!DNL Marketo Engage] e indicizzate in Apache SOLR per una ricerca rapida all&#39;interno del prodotto, quindi pubblicate nella pipeline delle attività in modo che [!DNL Marketo Optimizer] abbia consapevolezza immediata. Il runtime di percorso elabora tale attività e la scrive in Snowflake, trasformando i dati operativi in uno stato pronto per l’analisi. Da lì, l&#39;attività viene replicata in [!DNL Adobe Experience Platform] set di dati e [!DNL Adobe Customer Journey Analytics] in Power Reporting.
* Diversi tipi di entità si sincronizzano a velocità e direzioni diverse per bilanciare l&#39;aggiornamento rispetto all&#39;integrità del sistema:

| Entità [!DNL Marketo Engage] | Direzione di sincronizzazione | Latenza |
| --- | --- | --- |
| Lead | Bidirezionale | &lt; 1 sec |
| Azienda | Bidirezionale | &lt; 1 sec |
| Oggetto personalizzato | Unidirezionale | &lt; 5 sec |
| Attività | Unidirezionale | &lt; 5 sec |
| iscrizione al programma | Non sincronizzato | — |
| Risorse | Non sincronizzato | — |

Lead e aziende si aggiornano istantaneamente in entrambe le direzioni senza creare copie di dati duplicate. Gli oggetti personalizzati si replicano in pochi secondi, pertanto gli aggiornamenti dello schema in [!DNL Marketo Engage] possono essere immediatamente utilizzati in un percorso attivo. L&#39;appartenenza al programma e Assets sono intenzionalmente esclusi dalla sincronizzazione per preservare la velocità e l&#39;integrità del sistema.

Questo design con latenza pressoché nulla significa che le dashboard di analisi e i sistemi a valle vengono alimentati in tempo reale, consentendo l’ottimizzazione live delle campagne e un follow-up rapido sui lead ad alta priorità.

### Supporto dati attività [!DNL Marketo Engage] in percorsi

I dati di attività [!DNL Marketo Engage] sincronizzati alimentano la creazione di percorsi basati su eventi in [!DNL Marketo Optimizer]. Utilizza attività come riempimenti di moduli, visite web e coinvolgimento via e-mail per attivare, filtrare e diramare percorsi di persone.

* [Trigger di eventi per il nodo Ascolta un evento](./marketing/listen-for-event-nodes.md#event-triggers)
* [Filtri di eventi per il nodo Ascolta un evento](./marketing/listen-for-event-nodes.md#event-filters)
* [Filtri di persona corrispondenti per i nodi dei percorsi suddivisi](./marketing/split-merge-paths-nodes.md#matched-person-filters)

### Isolamento dei dati e tenancy

* I dati del cliente sono condivisi tra [!DNL Marketo Engage], [!DNL Marketo Optimizer] e [!DNL Experience Platform] come parte dell&#39;architettura di sincronizzazione e analisi dei dati del prodotto.
* I dati vengono isolati in modo logico per tenant e protetti dai controlli di sicurezza di Adobe.
* I dati vengono trasferiti su canali crittografati e protetti e memorizzati all&#39;interno di Adobe-Managed Services utilizzando la crittografia e i controlli di accesso standard.
* A seconda del tipo di dati, le informazioni possono essere sincronizzate tra [!DNL Marketo Engage] e [!DNL Marketo Optimizer] o replicate in [!DNL Experience Platform] per supportare le funzionalità di reporting e analisi, mantenendo la sicurezza e l&#39;isolamento del tenant.
