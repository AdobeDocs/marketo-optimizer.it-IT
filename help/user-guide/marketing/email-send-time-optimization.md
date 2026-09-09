---
title: Ottimizzazione dell’ora di invio delle e-mail
description: Configurare l’ottimizzazione del tempo di invio nei percorsi di persone di Marketo Optimizer. Imposta le finestre di invio, aggiungi nodi di attesa e visualizza i rapporti STO in Collaborator.
TQID: 'https://experienceleague.adobe.com/7g2aCAhlDO17TNy-VZSsWZ2JKGFgE5MZT20zp7eC1WQ'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2: id: 3c1de303-7a7c-59a6-abca-8c534730e19cid: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 759
ht-degree: 0%

---

# Ottimizzazione dell’ora di invio delle e-mail

Utilizza la funzione di ottimizzazione del tempo di invio per personalizzare la tempistica di consegna delle e-mail per [percorsi di persone](./person-journeys.md) prevedendo quando è più probabile che ogni profilo sia coinvolto. Invece di un tempo di invio fisso, STO utilizza segnali storici di coinvolgimento e-mail per pianificare la consegna al momento ottimale per ogni destinatario, migliorando il coinvolgimento complessivo.

STO analizza il coinvolgimento storico di ciascun profilo utilizzando un modello di linguaggio di grandi dimensioni. Prevede e classifica i potenziali tempi di invio, quindi pianifica la consegna al momento più alto nella finestra di ottimizzazione.

Informazioni approfondite sulle prestazioni, come l’utilizzo, l’incremento del coinvolgimento e i confronti STO rispetto a non-STO, sono disponibili tramite query in linguaggio naturale in Coworker.

>[!BEGINSHADEBOX]

Ci sono molti **_miglioramenti futuri_** pianificati per STO:

* Configurazione STO globale nell&#39;area _[!UICONTROL Amministratore]_
* Abilitazione STO a livello di percorso
* Divisioni di test/controllo configurabili

>[!ENDSHADEBOX]

## Configurazione {#configuration}

Puoi configurare l&#39;ottimizzazione dell&#39;ora di invio quando [aggiungi un _[!UICONTROL Esegui un&#39;azione]_ nodo](./action-nodes.md) a un percorso di persone e scegli l&#39;azione **[!UICONTROL Invia e-mail]**.

1. Selezionare il nodo _Invia e-mail_ azione di percorso.

1. Nelle proprietà del nodo a destra, abilita l&#39;opzione **[!UICONTROL Ottimizzazione dell&#39;ora di invio]**.

   ![Invia nodo del percorso di posta elettronica - Opzioni di ottimizzazione del tempo di invio](./assets/email-node-send-time-optimization.png){width="450" zoomable="no"}

1. Per specificare la distribuzione della finestra e del test, impostare le opzioni STO:

   * **[!UICONTROL Invia entro]** - Questo valore determina la finestra di ottimizzazione (in giorni), che è l&#39;intervallo di tempo in cui è possibile recapitare le e-mail. Ad esempio, per un webinar che si svolge in cinque giorni, puoi impostare una finestra di quattro o cinque giorni. STO seleziona il tempo di invio migliore previsto per ciascun profilo all’interno di questa finestra.

   * **STO / Distribuzione fissa** - STO crea automaticamente una _suddivisione test e controllo_ per suddividere i profili idonei tra i tempi di invio ottimizzati e quelli fissi. La suddivisione consente un confronto diretto delle prestazioni. (I miglioramenti futuri sono pianificati per consentire percentuali di suddivisione personalizzate).

   >[!NOTE]
   >
   >I profili con una solida cronologia di coinvolgimento vengono suddivisi in gruppi di controllo e di test in modo uniforme per misurare l’impatto dell’operazione STO. Per garantire risultati statisticamente affidabili, la suddivisione tra STO e non STO è limitata tra il 30% e il 70%. Questo aiuta a evitare che le coorti più piccole distorcano i risultati e garantisce confronti significativi.

1. Subito dopo il nodo _[!UICONTROL Invia e-mail]_, [aggiungi un nodo _Attendi_](./wait-nodes.md).

   Un nodo di attesa deve seguire immediatamente un’azione e-mail abilitata per STO. L’aggiunta di questo nodo assicura che i profili rimangano nel percorso fino a quando la finestra di ottimizzazione completa non viene cancellata e tutti gli invii dell’STO non vengono completati. Se si omette questo nodo, il sistema contrassegna la configurazione come non valida.

1. Dopo aver completato il resto del percorso di persone, procedi alla [pubblicazione](./person-journeys.md#publish).

## Generazione dei rapporti {#reporting}

I dati sulle prestazioni STO sono disponibili tramite [Collaboratore](../agents/chat-interface.md) utilizzando l&#39;abilità `send-time-report`. Puoi visualizzare un rapporto a livello di percorso che riepiloga tutti i nodi e-mail, oppure approfondire un rapporto a livello di nodo per una specifica azione e-mail.

Il report visualizza ogni nodo e-mail nel percorso e indica se STO è abilitato per esso. Mostra inoltre un confronto tabulare tra e-mail abilitate all’STO e non all’STO per valutare l’incremento del coinvolgimento.

### Generare il rapporto STO {#generate-sto-report}

Esistono tre modi per generare un rapporto STO utilizzando Collaboratore:

**Usa il comando barra**

1. Nel pannello Collaboratore, digita `/` per visualizzare l&#39;elenco delle abilità disponibili.
1. Selezionare **[!UICONTROL send-time-report]** dall&#39;elenco e fare clic sulla freccia su per inviare la query.

   ![Query abilità rapporto ora di invio collaboratore](./assets/email-sto-reporting-coworker.png){width="700" zoomable="yes"}

   Se un percorso è aperto nell’editor, viene utilizzato automaticamente come contesto. In caso contrario, viene richiesto di specificare il percorso.

   Collaboratore carica il rapporto e visualizza una scheda di riepilogo.

1. Fai clic su **[!UICONTROL Apri report]** per visualizzare il report completo con i dettagli a livello di nodo.

**Fare clic su un nodo e-mail**

1. Nell&#39;area di lavoro del percorso fare clic sul nodo **[!UICONTROL Invia e-mail]**.

1. Nel pannello Collaboratore, chiedi il rapporto STO.

   Poiché il nodo è selezionato, viene utilizzato come contesto e restituisce un report con ambito solo a tale nodo.

   Carica il rapporto e visualizza una scheda di riepilogo.

1. Fai clic su **[!UICONTROL Apri report]** per visualizzare il report completo.

**Query in linguaggio naturale**

1. Nel pannello Collaboratore, immetti una richiesta come _Assegnami il rapporto STO per [Nome percorso]_.

   Il collaboratore interpreta la richiesta, carica l&#39;abilità `send-time-report`, genera il rapporto e visualizza una scheda di riepilogo.

1. Fai clic su **[!UICONTROL Apri report]** per visualizzare il report completo.

### Visualizzare i dati del rapporto e-mail {#sto-report-data}

Puoi ridurre il pannello Collaboratore per aumentare le dimensioni del rapporto visualizzato, oppure scorrere per visualizzarne l’intera larghezza.

![Rapporto ottimizzazione ora di invio - riepilogo prestazioni e-mail](./assets/email-sto-reporting-summary-report.png){width="700" zoomable="yes"}

Nella colonna _[!UICONTROL Dettagli]_ fare clic su **[!UICONTROL Visualizza risultati STO]** per aprire una finestra popup. La finestra fornisce visualizzazioni dei dati e-mail per _Confronto prestazioni_, _Distribuzione al momento dell&#39;invio_ e _Integrità dati_.

![Rapporto di ottimizzazione del tempo di invio - dati sulle prestazioni delle e-mail](./assets/email-sto-reporting-data.png){width="500" zoomable="yes"}
