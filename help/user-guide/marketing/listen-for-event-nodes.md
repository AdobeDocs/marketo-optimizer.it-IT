---
title: Ascolta un nodo evento
description: 'Configurare Ascolta per i nodi di un evento in Marketo Optimizer: imposta i trigger di evento, applica filtri facoltativi e avanza le persone quando si verificano attività o modifiche di dati.'
TQID: 'https://experienceleague.adobe.com/6v3i6M-Hhr2RAWrS68WaEVb8VJEzJZbD7vXOJOsjgc8'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 354
ht-degree: 5%

---

# Ascolta un nodo evento

Aggiungi il nodo _Ascolta un evento_ per spostare il pubblico al passaggio successivo nel percorso in cui si verifica un evento.

## Trigger evento {#event-triggers}

Puoi generare trigger intorno a [!DNL Marketo Engage] attività, ad esempio:

* Modulo compilato: si attiva quando una persona invia un modulo [!DNL Marketo Engage] nella pagina di destinazione.
* Pagina Web Visite: viene attivata quando un lead visualizza una pagina Web tracciata (è possibile specificare URL esatti o utilizzare caratteri jolly).
* Clic sul collegamento: viene attivato quando si fa clic su un collegamento tracciato in un’e-mail di marketing.
* Modifiche al valore dei dati: viene attivato quando un campo specifico (come Stato lead, Punteggio o Settore) viene aggiornato sui record di una persona.
* Campaign is Requested (Campagna è richiesta): spesso utilizzato per integrazioni API o webhook, questo attivatore avvia una campagna quando viene chiamato da un altro programma o servizio web.
* Punteggio modificato: viene attivato quando il punteggio di lead di un individuo aumenta o diminuisce oltre una determinata soglia.
* Push mobile attivato: viene attivato nelle campagne intelligenti di mobile marketing quando una notifica push viene interagita con su un dispositivo.

## Filtri degli eventi {#event-filters}

| Filtri | Descrizione |
| ------- | ----------- |
| Cronologia attività > E-mail | Attività e-mail in base a condizioni valutate utilizzando uno o più messaggi e-mail selezionati: <li>Collegamento cliccato nell’e-mail <li>E-mail aperta |
| Cronologia attività > Valore dati modificato | Per un attributo persona selezionato, si è verificata una modifica del valore. Questi tipi di modifica includono: <li>Nuovo valore <li>Valore precedente <li>Motivo <li>Origine <li>Data dell’attività <li> Min numero di volte |

## Aggiungere un nodo evento {#add-event-node}

1. Passa all’area di lavoro del percorso.

1. Fai clic sull&#39;icona più ( **+** ) in un percorso e scegli **[!UICONTROL Ascolta un evento]**.

   ![Fai clic sull&#39;icona Aggiungi nel percorso del percorso](./assets/person-journey-canvas-add-node.png){width="200"}

1. Nelle proprietà del nodo a destra, fai clic su **[!UICONTROL Aggiungi criterio evento]**.

1. Nella finestra di dialogo _[!UICONTROL Modifica evento]_, aggiungi gli eventi da attivare.

   ![Modifica evento - trigger evento](./assets/edit-event-triggers.png){width="600" zoomable="yes"}

1. (Facoltativo) Seleziona la scheda **[!UICONTROL Filtri]** nella finestra di dialogo e aggiungi i criteri di filtro per i trigger.

1. Fai clic su **[!UICONTROL Modifica evento]** e definisci i dettagli dell&#39;evento.

   ![Modifica evento - filtro eventi](./assets/edit-event-filters.png){width="600" zoomable="yes"}

1. Fai clic su **[!UICONTROL Salva]**.

<!--
1. If needed, set the **[!UICONTROL Timeout]** option to limit the time period to listen for the event.

   >[!NOTE]
   >
   >The journey ends after a timeout unless you define a timeout path, where you can add other nodes.

   Enable the **[!UICONTROL Timeout]** option and select the duration for which the journey waits for an event to occur before it times out.

   You can choose to end the path here or take a different course of action by setting another path. To create a new path in the journey where you can add actions and events applicable to accounts when the event does not occur, select the **[!UICONTROL Set timeout path]** check box.

   ![Journey event node - set timeout path](assets/node-event-timeout-set-path.png){width="700" zoomable="yes"}
-->

>[!NOTE]
>
>La funzionalità di timeout per Ascolta per un nodo evento non funziona al momento. È pianificata per una versione successiva.

