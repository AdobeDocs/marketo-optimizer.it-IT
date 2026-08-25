---
title: Architettura di alto livello
description: Scopri l’architettura dei dati che collega Marketo Optimizer e Marketo Engage, inclusa la sincronizzazione bidirezionale, la latenza delle entità e l’isolamento dei dati del tenant.
role: User, Admin
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 2%

---


# Architettura di alto livello

[!DNL Adobe Marketo Optimizer] si integra con [!DNL Adobe Marketo Engage] per fornire una visualizzazione a 360 gradi dei lead B2B. Una sincronizzazione bidirezionale e affidabile mantiene allineati Marketo Engage e Marketo Optimizer, fornendo a entrambe le piattaforme un&#39;unica vista condivisa di Persone, Aziende, Oggetti personalizzati e Attività. Il flusso di dati in tempo reale e ad alte prestazioni garantisce la disponibilità e l&#39;operatività dei record, in modo che le campagne e i percorsi possano rispondere ai lead nel momento in cui interagiscono.

## Data Foundation

[!DNL Marketo Optimizer] e [!DNL Marketo Engage] condividono una base dati comune che mantiene entrambe le piattaforme sincronizzate durante l&#39;alimentazione di analisi a valle.

![Diagramma dell&#39;architettura di Marketo Optimizer e Marketo Engage che mostra il modo in cui i servizi, i runtime e gli archivi dati dei due prodotti si connettono tra Microsoft Azure e AWS](./assets/marketo-optimizer-architecture.svg)

Ad alto livello:

* **Marketo Engage Core** è l&#39;origine definitiva per i dati di lead e oggetto personalizzato, garantendo l&#39;integrità dei dati nel punto di acquisizione.
* Un livello **Data Broker** coordina il modo in cui i dati vengono spostati tra Marketo Engage e Marketo Optimizer, aggregando dati condivisi e replicati in un ambiente operativo pronto all&#39;uso. L’intero scambio viene eseguito all’interno di una singola istanza AWS Aurora condivisa, formando la base a loop chiuso per l’orchestrazione B2B su larga scala.
* **Le attività** seguono un percorso definito: vengono inizialmente scritte nel database di Marketo Engage e indicizzate in Apache SOLR per una ricerca rapida all&#39;interno del prodotto, quindi pubblicate nella pipeline delle attività in modo che Marketo Optimizer possa riconoscerle immediatamente. Il runtime di Percorso elabora tale attività e la scrive in Snowflake, trasformando i dati operativi in uno stato pronto per l’analisi. Da lì, l’attività viene replicata nei set di dati di AEP e in CJA per potenziare i rapporti.
* Diversi tipi di entità si sincronizzano a velocità e direzioni diverse per bilanciare l&#39;aggiornamento rispetto all&#39;integrità del sistema:

| Entità Marketo Engage | Direzione di sincronizzazione | Latenza |
| --- | --- | --- |
| Lead | Bidirezionale | &lt; 1 sec |
| Azienda | Bidirezionale | &lt; 1 sec |
| Oggetto personalizzato | Unidirezionale | &lt; 5 sec |
| Attività | Unidirezionale | &lt; 5 sec |
| Iscrizione al programma | Non sincronizzato | — |
| Risorse | Non sincronizzato | — |

Lead e aziende si aggiornano istantaneamente in entrambe le direzioni senza creare copie di dati duplicate. Gli oggetti personalizzati si replicano in pochi secondi, pertanto gli aggiornamenti dello schema in Marketo Engage possono essere immediatamente utilizzati in un percorso attivo. L&#39;appartenenza al programma e Assets sono intenzionalmente esclusi dalla sincronizzazione per preservare la velocità e l&#39;integrità del sistema.

Questo design con latenza pressoché nulla significa che le dashboard di analisi e i sistemi a valle vengono alimentati in tempo reale, consentendo l’ottimizzazione live delle campagne e un follow-up rapido sui lead ad alta priorità.

### Isolamento dei dati e tenancy

* I dati dei clienti sono condivisi tra Marketo Engage, Marketo Optimizer e Experience Platform come parte dell’architettura di sincronizzazione e analisi dei dati dei prodotti.
* I dati vengono isolati in modo logico per tenant e protetti dai controlli di sicurezza di Adobe.
* I dati vengono trasferiti su canali protetti e crittografati e memorizzati all’interno dei servizi gestiti da Adobe utilizzando la crittografia e i controlli di accesso standard.
* A seconda del tipo di dati, le informazioni possono essere sincronizzate tra Marketo Engage e Marketo Optimizer o replicate in Experience Platform per supportare le funzionalità di reporting e analisi, mantenendo al contempo la sicurezza e l’isolamento dei tenant.
