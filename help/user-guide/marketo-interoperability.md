---
title: Interoperabilità con Marketo Engage
description: Scopri cosa Marketo Optimizer condivide con Marketo Engage, inclusi dati, attività e tipi di pubblico, e come inviare e-mail da entrambi i prodotti nei tuoi percorsi.
role: User, Admin
autotag-review: '2026-10-01T18:40:01.444Z'
TQID: 'https://experienceleague.adobe.com/7TB6JG9yiUT-l0VevNW4tvwieCyFjOypZwI0SlUzmmY'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
  - id: 46e599c6-e20f-5f67-9824-93415016f66b
    internal-label: Audiences
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
    internal-label: Journeys
  - id: a29661b8-f7a4-53d1-a9ac-fdec08c092e4
    internal-label: Programs
  - id: d4203578-d294-5145-b397-f26f4488a904
    internal-label: Channels
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: 518a807aeed2471772b4f0a4d6d8d525cd3e22fd
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 0%
---

# Interoperabilità con Marketo Engage

[!DNL Adobe Marketo Optimizer] e [!DNL Adobe Marketo Engage] condividono dati, alcune attività e tipi di pubblico. Mantengono le risorse separate. Scopri cosa condividono i singoli prodotti per decidere dove creare e inviare il tuo marketing.

## Condiviso tra i prodotti {#shared}

* [!DNL Marketo Engage] lead e attività vengono automaticamente inseriti in [!DNL Marketo Optimizer].
* I percorsi possono ascoltare [!DNL Marketo Engage] attività.
* I tipi di pubblico basati su eventi possono includere persone che eseguono [!DNL Marketo Engage] attività.
* Le azioni di percorso possono interagire con [!DNL Marketo Engage]. È possibile aggiungere o rimuovere persone da un elenco [!DNL Marketo Engage] e richiedere una campagna [!DNL Marketo Engage].
* [!UICONTROL Lo studio con punteggio] assegna un punteggio alle persone rispetto a [!DNL Marketo Engage] e [!DNL Marketo Optimizer] attività. È possibile utilizzare i punteggi in [!DNL Marketo Engage].
* Entrambi i prodotti condividono indirizzi IP e sottodomini.
* Il reporting conversazionale unificato riguarda entrambi i prodotti.

## Mantenuto separato {#separate}

* **Assets:** le e-mail, i modelli, i programmi e le immagini vengono salvati in archivi separati.
* **Attività:** [!DNL Marketo Optimizer] attività non sono condivise nuovamente in [!DNL Marketo Engage].
* **Campi e limiti:** I campi personali derivati da [!DNL Marketo Optimizer] non sono disponibili in [!DNL Marketo Engage]. I limiti di comunicazione sono stabiliti separatamente in ciascun prodotto.

Per informazioni dettagliate sulla sincronizzazione, vedere [Sincronizzazione entità](./data-architecture.md#entity-sync).

## Invia e-mail da Marketo Engage {#send-from-marketo}

Utilizza questo approccio per eseguire percorsi, passaggi di attesa e decisioni AI in [!DNL Marketo Optimizer], mentre [!DNL Marketo Engage] invia ogni e-mail.

1. In [!DNL Marketo Optimizer], crea un percorso che include passaggi di attesa e decisioni basate su IA.
1. Per ogni passaggio di invio, aggiungi l&#39;azione **[!UICONTROL Richiedi campagna Marketo Engage]** e seleziona una campagna [!DNL Marketo Engage] corrispondente.
1. Facoltativo: aggiungere un programma generale predefinito in [!DNL Marketo Engage] per aggregare i report di successo nel percorso.

Per informazioni dettagliate sull&#39;azione, vedere [Eseguire un&#39;azione &#x200B;](./marketing/action-nodes.md).

[!DNL Marketo Engage] invia l&#39;e-mail tramite le impostazioni del canale esistenti. Poiché [!DNL Marketo Engage] invia l&#39;e-mail, non è possibile configurare canali o e-mail in [!DNL Marketo Optimizer]. Inoltre:

* Invii, aperture e clic sono registrati in [!DNL Marketo Engage].
* Gestione degli annullamenti dell&#39;abbonamento e governance delle e-mail applicabili in [!DNL Marketo Engage].
* L&#39;attività di posta elettronica alimenta le [!DNL Marketo Engage] campagne di punteggio esistenti.
* Le campagne di sincronizzazione Salesforce attivate dall’attività vengono eseguite come previsto.
* Ogni invio è associato a una campagna [!DNL Marketo Engage], in modo da tenere traccia dell&#39;iscrizione al programma per ogni campagna e-mail e generare report in programmi familiari.

## Invia e-mail da Marketo Optimizer {#send-from-optimizer}

Utilizzare questo approccio per creare il percorso e inviare messaggi di posta elettronica interamente in [!DNL Marketo Optimizer]. [!DNL Marketo Engage] rimane il sistema di registrazione per il trasferimento al sistema di gestione delle relazioni con i clienti (CRM).

1. Configura il canale e-mail. Crea modelli e-mail e configura l’indirizzo IP e il sottodominio, i collegamenti per l’annullamento dell’abbonamento e le pagine di destinazione. Consulta [Recapito e-mail](./start/email-deliverability.md).
1. Impostare i limiti di comunicazione in [!DNL Marketo Optimizer]. I limiti di comunicazione condivisi non sono disponibili.
1. Crea il percorso con tipi di pubblico, decisioni basate sull’intelligenza artificiale e il percorso migliore successivo.
1. Invia e-mail da [!DNL Marketo Optimizer]. [!DNL Marketo Optimizer] registra le attività.
1. Punteggio delle persone in [!UICONTROL Scoring Studio] per creare un modello in [!DNL Marketo Engage] e [!DNL Marketo Optimizer] attività. Vedi [Studio punteggio](./labs/scoring-studio.md).

Annulla l&#39;iscrizione sincronizza automaticamente con [!DNL Marketo Engage] tramite campi condivisi. L&#39;attività e-mail [!DNL Marketo Optimizer] non viene rimandata a [!DNL Marketo Engage], ma [!UICONTROL Scoring Studio] la utilizza ancora.

### Consegna porta alle vendite {#hand-off}

[!DNL Marketo Optimizer] non dispone di integrazione CRM diretta. Indirizza i lead attraverso [!DNL Marketo Engage] con uno dei seguenti metodi:

* **Basato su punteggio:** Il campo del punteggio viene visualizzato in [!DNL Marketo Engage] e una campagna intelligente sincronizza il lead nel CRM.
* **Basato sulle attività:** Un percorso [!DNL Marketo Optimizer] ascolta l&#39;attività e aggiunge il lead a una [!DNL Marketo Engage] campagna avanzata.
* **Iscrizione al programma:** Il percorso si trova in un programma [!DNL Marketo Optimizer], quindi puoi tenere traccia dello stato dall&#39;inizio alla fine.
