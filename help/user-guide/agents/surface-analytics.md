---
title: Generare rapporti di Analytics
description: Scopri come utilizzare l’abilità Surface Analytics nella chat di Coworker per generare rapporti di attività, e-mail, lead, segmenti e percorso da prompt in linguaggio naturale.
autotag-review: '2026-09-21T14:58:26.479Z'
TQID: 'https://experienceleague.adobe.com/BSDEihjdpz-YZjMWrYTmIuyjqtcjRHRrJdz4xPFZbHU'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 1650dadf-b034-5ac9-a309-77ad1e2f5035
    internal-label: Chat Interface
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
subfeature_v2:
  - id: b9e5c7f3-be30-563c-9e41-cc8ea76e2fee
    internal-label: Skills
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
source-git-commit: 1dcc3bcdc59114c7fc1e16178db8921ae173b955
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 0%
---
# Generare rapporti di analisi

L&#39;abilità [_Surface Analytics_](./skills.md#analytics-reporting) in [!DNL Adobe Marketo Optimizer] risponde a domande in linguaggio naturale sui dati. Utilizzalo nell&#39;interfaccia chat di [Collaboratore](./chat-interface.md) per esplorare tendenze attività, prestazioni e-mail, dati di lead e account, appartenenza a segmenti e elenchi e metriche di percorso. I risultati vengono restituiti come grafici e tabelle, pertanto non è necessario creare manualmente una query o un dashboard.

* **Abilità** - `surface-analytics`
* **Richiamo** - Poni una domanda in linguaggio naturale oppure utilizza un comando barra per eseguire l&#39;abilità Surface Analytics. Ad esempio: _&quot;Mostra i conteggi delle attività giornaliere per gli ultimi 30 giorni.&quot;_
* **Legge da** - [!DNL Marketo Optimizer] dati di analisi; legge [!DNL Marketo Engage] dati di analisi per domande che si estendono su entrambi i prodotti

>[!NOTE]
>
>I dati dei rapporti vengono aggiornati ogni due ore. I risultati potrebbero non riflettere l&#39;attività delle ultime due ore.

## Visualizza tendenze attività {#activity-trends}

Chiedi informazioni sui conteggi delle attività giornaliere o settimanali e suddividi i risultati per tipo di attività o area di prodotto.

* _&quot;Mostra conteggi attività giornalieri per gli ultimi 30 giorni.&quot;_
* _&quot;Quali sono i principali tipi di attività questa settimana?&quot;_
* _&quot;Suddividi l&#39;attività del mese scorso per area dell&#39;app.&quot;_

## Verifica prestazioni e-mail {#email-performance}

Chiedi informazioni su volumi di invio, tariffe di apertura e clic, mancati recapiti e annullamenti dell’abbonamento ai programmi e-mail.

* _&quot;Qual è il tasso di apertura delle e-mail per percorso?&quot;_
* _&quot;Mostra le percentuali di clic per gli ultimi 90 giorni.&quot;_
* _&quot;Quanti annullamenti di abbonamenti abbiamo ricevuto la settimana scorsa?&quot;_

## Analizzare i dati del lead e dell’account {#lead-account-data}

Chiedi informazioni sulla distribuzione del punteggio di lead, sulle suddivisioni utente e sulle aggregazioni geografiche o firmografiche.

* _&quot;Mostra la distribuzione del punteggio tra lead.&quot;_
* _&quot;Quante persone ci sono in ogni account?&quot;_
* _&quot;Suddividere i lead per persona.&quot;_

## Rivedi l’iscrizione a segmenti ed elenchi {#segment-list-membership}

Chiedi a chi appartiene un elenco o un segmento specifico.

* _&quot;Quante persone ci sono nell&#39;elenco Q1 Nurture?&quot;_
* _&quot;Quale segmento ha il maggior numero di membri?&quot;_

## Esplorare le metriche del percorso {#journey-metrics}

Domande sull’iscrizione al percorso, sui tassi di completamento, sulla navigazione dei nodi e sull’analisi funnel.

* _&quot;Qual è il tasso di completamento per il percorso di follow-up demo?&quot;_
* _&quot;Quante persone ci sono in ogni nodo di LeadNurtureJourney?&quot;_

## Poni le tue domande tra i prodotti {#cross-product}

Surface Analytics può rispondere a domande che si estendono su [!DNL Marketo Engage] e [!DNL Marketo Optimizer] dati in un unico prompt.

* _&quot;Qual è la mia e-mail con le prestazioni migliori in LumaSecure e in LumaStorage?&quot;_

## Limitazioni {#limitations}

| Limitazione | Dettaglio |
|---|---|
| Modifica o creazione di record | Non supportato. Surface Analytics legge e genera rapporti solo sui dati esistenti. |
| Nomi leggibili nei risultati | Non sempre disponibile. Alcuni rapporti mostrano un ID interno, ad esempio un ID percorso o un ID e-mail, invece di un nome. |
| Duplicare le schede dei rapporti | Una singola domanda può occasionalmente restituire più schede per lo stesso risultato. |
