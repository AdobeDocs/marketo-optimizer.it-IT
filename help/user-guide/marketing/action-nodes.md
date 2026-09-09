---
title: Crea un nodo azione
description: Configurare un nodo Azioni in Marketo Optimizer per aggiungere, rimuovere o aggiornare persone, elenchi, programmi e destinazioni o per inviare messaggi quando raggiungono il nodo in un percorso di persone.
TQID: 'https://experienceleague.adobe.com/KmYvfJm9d5YZdC7ZWQiybjNsFmnt0GLReJIL8nDQF-k'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2:
  - id: 46e599c6-e20f-5f67-9824-93415016f66b
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
  - id: a29661b8-f7a4-53d1-a9ac-fdec08c092e4
topic_v2:
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 1145
ht-degree: 0%

---

# Crea un nodo di azione

In un percorso di persone, utilizza un’azione sulle persone quando desideri applicare una modifica a tutte le persone nel percorso del nodo.

## Azioni e vincoli {#actions}

| Azione | Vincoli |
| ------ | ----------- |
| **[!UICONTROL Attiva nella destinazione]** | <li>Seleziona o crea un elenco statico <li>Se l’elenco non ha una destinazione attivata, attivalo per una o più destinazioni |
| **[!UICONTROL Aggiungi persona al percorso]** | <li>Seleziona un percorso pianificato o live <li>I criteri di pubblico del percorso target non vengono applicati |
| **[!UICONTROL Aggiungi all&#39;elenco]** | <li>Crea un nuovo elenco statico o selezionane uno esistente |
| **[!UICONTROL Aggiungi a elenco Marketo Engage]** | <li>Seleziona un elenco statico in Marketo Engage |
| **[!UICONTROL Modifica valore dati]** | <li>Seleziona attributo persona <li>Imposta nuovo valore |
| **[!UICONTROL Modifica stato nel programma]** | <li>Seleziona programma<li>Seleziona nuovo stato |
| **[!UICONTROL Modifica stato membro webinar]** | <li>Seleziona programma<li>Seleziona nuovo stato |
| **[!UICONTROL Rimuovi dall&#39;elenco]** | <li>Seleziona elenco statico <li>Ignora la persona se non ne è attualmente membro |
| **[!UICONTROL Rimuovi dall&#39;elenco di Marketo Engage]** | <li>Seleziona un elenco statico in Marketo Engage <li>Ignora la persona se non ne è attualmente membro |
| **[!UICONTROL Rimuovi persona dal percorso]** | <li>Seleziona un percorso live <li>Ignora la persona se non è attualmente membro del percorso target |
| **[!UICONTROL Richiedi campagna Marketo Engage]** | <li>Seleziona una campagna Marketo Engage |
| **[!UICONTROL Invia e-mail]** | <li>Creare, modificare o utilizzare un’e-mail personalizzata con IA <li>Ottimizzazione del tempo di invio (facoltativo) |
| **[!UICONTROL Invia WhatsApp]** | <li>Seleziona un messaggio WhatsApp |

<!-- 
removed? | **[!UICONTROL Change Program Data]** | <li>Select program attribute <li>Set new value | 
-->

## Aggiungi un nodo azione {#add-an-action-node}

1. Passa all’area di lavoro del percorso.

1. Fai clic sull&#39;icona più ( **+** ) in un percorso e scegli **[!UICONTROL Esegui un&#39;azione]**.

   ![Fai clic sull&#39;icona Aggiungi nel percorso del percorso](./assets/person-journey-canvas-add-node.png){width="200"}

1. Nelle proprietà del nodo a destra, seleziona un’azione dall’elenco e imposta i valori per l’azione.

+++Attiva nella destinazione

Utilizza questa azione per aggiungere persone a un elenco statico e attivare tale elenco in una destinazione direttamente dal percorso. È possibile utilizzare un elenco statico esistente o crearne uno specifico per il percorso.

>[!PREREQUISITES]
>
>Prima di impostare un nodo di percorso _Attiva nella destinazione_, è necessario disporre di una o più [destinazioni configurate](../audiences/destinations.md) per la sandbox [!DNL Marketo Optimizer].

![Esegui un&#39;azione - Attiva nella destinazione](./assets/person-action-node-activate-to-destination.png){width="450"}

In **[!UICONTROL Aggiungi all&#39;elenco]** scegliere una delle opzioni seguenti:

* **[!UICONTROL Crea]** — crea un nuovo elenco statico e aggiungi persone. L&#39;elenco è immediatamente disponibile in **[!UICONTROL Elenchi persone]**.

  Selezionare un programma padre per l&#39;elenco e immettere un **[!UICONTROL Nome]** (obbligatorio) e una **[!UICONTROL Descrizione]** (facoltativo). Fai clic su **[!UICONTROL Crea]** per aggiungere il nuovo elenco per il nodo.

  ![Creare un elenco statico da utilizzare per il nodo di percorso](./assets/person-action-node-destination-create-list.png){width="375"}

* **[!UICONTROL Seleziona]** — seleziona un elenco statico esistente in cui aggiungere le persone che raggiungono il nodo.

  Selezionare la casella di controllo per l&#39;elenco statico esistente e fare clic su **[!UICONTROL Salva]**.

  ![Selezionare un elenco statico da utilizzare per il nodo di percorso](./assets/person-action-node-destination-select-list.png){width="700" zoomable="yes"}

Chiunque raggiunga il nodo viene aggiunto all’elenco statico selezionato, ma l’azione non viene completata finché l’elenco non viene attivato su una destinazione:

* Se l&#39;elenco selezionato è già attivato, le relative destinazioni vengono visualizzate in **[!UICONTROL Destinazioni]** e l&#39;azione è pronta.
* In caso contrario, viene visualizzato un messaggio _È richiesta almeno una destinazione_. Fai clic su **[!UICONTROL Attiva elenco nella destinazione]**, seleziona la destinazione e fai clic su **[!UICONTROL Salva]**. Fai clic su **[!UICONTROL Attiva]** nella finestra di dialogo di conferma.

![Destinazioni configurate disponibili per l&#39;attivazione](../audiences/assets/static-list-activate-destination-select.png){width="600" zoomable="yes"}

Al termine dell&#39;attivazione, la destinazione viene visualizzata in **[!UICONTROL Destinazioni]** e l&#39;azione è pronta. Se necessario, puoi attivare l’elenco in altre destinazioni.

Chiunque raggiunga il nodo viene aggiunto all’elenco statico selezionato, che viene attivato nella destinazione scelta, in modo che vengano aggiunti al pubblico di destinazione e, a sua volta, a qualsiasi campagna feed dal pubblico.

+++

+++[!UICONTROL Aggiungi persona al percorso]

Utilizza questa azione per aggiungere persone ad altri percorsi pianificati o live. Le persone aggiunte tramite questa azione vengono immediatamente aggiunte al pubblico del percorso target; i criteri di pubblico del percorso target non vengono applicati.

![Esegui un&#39;azione - Aggiungi persona al percorso](./assets/person-action-node-add-to-journey.png){width="450"}

+++

+++[!UICONTROL Aggiungi all&#39;elenco]

Utilizzare questa azione per aggiungere persone a un elenco statico in Marketo Optimizer.

![Esegui un&#39;azione - Aggiungi all&#39;elenco](./assets/person-action-node-add-to-list.png){width="450"}

Scegliere una delle opzioni seguenti:

* **[!UICONTROL Crea]** — crea una nuova risorsa elenco statica e aggiungi persone. L’elenco è immediatamente disponibile per l’utilizzo da parte di altre risorse in Marketo Optimizer.
* **[!UICONTROL Seleziona]** — seleziona una risorsa elenco statico esistente in cui desideri aggiungere persone che raggiungono il nodo.

+++

+++[!UICONTROL Aggiungi a elenco Marketo Engage]

Utilizzare questa azione per aggiungere persone a un elenco statico in Marketo Engage.

![Esegui un&#39;azione - Aggiungi a elenco Marketo](./assets/person-action-node-add-to-marketo-list.png){width="450"}

+++

+++[!UICONTROL Modifica valore dati]

Utilizzare questa azione per aggiornare il valore di un attributo in un record persona. Selezionare l&#39;attributo e impostare il nuovo valore.

>[!TIP]
>
>Per cancellare il valore di un attributo, impostare il valore su `NULL`.

![Azione - Modifica valore dati](./assets/person-action-node-change-data-value.png){width="450"}

+++

+++[!UICONTROL Modifica stato nel programma]

Utilizzare questa azione per modificare lo stato di una persona in un programma Marketo Engage. Selezionare il programma e quindi il nuovo stato.

![Azione - Modifica stato programma](./assets/person-action-node-change-status-program.png){width="450"}

+++

+++[!UICONTROL Modifica stato membro webinar]

Utilizza questa azione per modificare lo stato di una persona in relazione a un webinar interattivo. Seleziona il webinar e quindi il nuovo stato.

![Azione - Modifica stato programma](./assets/person-action-node-change-webinar-status.png){width="450"}

+++

+++[!UICONTROL Rimuovi dall&#39;elenco]

Utilizzare questa azione per rimuovere persone da un elenco statico in Marketo Optimizer. Se una persona non è attualmente membro dell’elenco, l’azione viene ignorata per tale persona.

![Esegui un&#39;azione - Rimuovi dall&#39;elenco](./assets/person-action-node-remove-from-list.png){width="450"}

+++

+++[!UICONTROL Rimuovi dall&#39;elenco di Marketo Engage]

Utilizzare questa azione per rimuovere persone da un elenco statico in Marketo Engage. Se una persona non è attualmente membro dell’elenco, l’azione viene ignorata per tale persona.

![Esegui un&#39;azione - Rimuovi dall&#39;elenco di Marketo](./assets/person-action-node-remove-from-marketo-list.png){width="450"}

+++

+++[!UICONTROL Rimuovi persona dal percorso]

Utilizza questa azione per rimuovere persone da altri percorsi di persone live. La persona viene immediatamente rimossa dal percorso target e non vengono intraprese ulteriori azioni nei suoi confronti. Se una persona non è attualmente membro del percorso target, l’azione viene ignorata per tale persona.

![Azione - Rimuovi persona dal percorso](./assets/person-action-node-remove-from-journey.png){width="450"}

+++

+++[!UICONTROL Richiedi campagna Marketo Engage]

Utilizza questa azione per aggiungere persone a una campagna di richieste in un’istanza di Marketo Engage connessa. Seleziona la campagna Marketo Engage da richiedere.

![Azione - Richiedi campagna Marketo](./assets/person-action-node-request-marketo-campaign.png){width="450"}

+++

+++[!UICONTROL Invia e-mail]

Utilizza questa azione per inviare un’e-mail alle persone che hanno prestato il consenso. Le persone che hanno annullato l’abbonamento, sono state inserite nell’elenco Bloccati, hanno sospeso l’e-mail o il marketing saltano questa azione.

![Azione - Invia e-mail](./assets/person-action-node-send-email.png){width="450"}

Puoi creare un’e-mail, modificare un’e-mail esistente o utilizzare un’e-mail personalizzata con IA. Per informazioni sulla creazione e la modifica delle e-mail, consulta [Canale e-mail](./email-channel.md). Per generare varianti basate su persona per un indirizzo e-mail esistente, vedi [Personalizzare il contenuto delle e-mail per persona](../agents/personalize-content.md).

Puoi utilizzare [Ottimizzazione del tempo di invio](./email-send-time-optimization.md) per personalizzare la tempistica di consegna delle e-mail prevedendo quando è più probabile che ogni profilo sia coinvolto.

+++

+++[!UICONTROL Invia WhatsApp]

Utilizza questa azione per inviare un messaggio WhatsApp. Puoi creare, personalizzare e visualizzare in anteprima i messaggi WhatsApp nello spazio di progettazione visivo (vedi [Authoring WhatsApp](../content/whatsapp-authoring.md)).

![Esegui un&#39;azione - Invia WhatsApp](./assets/person-action-node-send-whatsapp.png){width="450"}

+++
