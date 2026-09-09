---
title: Percorsi persona
description: 'Creazione, pubblicazione e gestione di percorsi di persone in Marketo Optimizer: consente di sfogliare l''elenco dei percorsi, progettare flussi a più passaggi e duplicare o eliminare percorsi.'
TQID: 'https://experienceleague.adobe.com/RYzV8B9QTuGm1gGb2ZX6i3rc4TlACsM3LRwcnULgwV8'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2: id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1id: a29661b8-f7a4-53d1-a9ac-fdec08c092e4id: d4203578-d294-5145-b397-f26f4488a904
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 1418
ht-degree: 19%

---

# Percorsi persona

In [!DNL Adobe Marketo Optimizer], i percorsi di persone sono piani di marketing basati su lead automatizzati e a più passaggi, che orchestrano esperienze personalizzate su più canali. Questi percorsi utilizzano i dati di Marketo Engage per eseguire questi piani di marketing in risposta a coinvolgimento, eventi di business o campagne pianificate.

>[!NOTE]
>
>Ogni percorso risiede in un [programma](./programs.md) definito. Prima di creare un percorso è necessario disporre di almeno un programma da utilizzare come padre.

_Per creare un nuovo percorso di persone :_

1. Crea il percorso di persone.
1. Aggiungi i nodi e definisci il flusso di percorso nell’area di lavoro del percorso.
1. [Pubblica il percorso](#publish-a-journey).

## Accedere e sfogliare percorsi di persone {#access-and-browse-person-journeys}

1. Nella barra di navigazione a sinistra, espandere **[!UICONTROL Gestione marketing]**.

1. Sulla destra nell&#39;elenco delle risorse **[!UICONTROL Marketing]**, seleziona **[!UICONTROL percorsi di persone]**.

   L&#39;elenco _percorsi di persone_ viene visualizzato come una scheda nell&#39;area di lavoro principale.

   È possibile immettere testo nello strumento _Ricerca_ nella parte superiore dell&#39;elenco per filtrare l&#39;elenco visualizzato in base al nome.

   ![Elenco percorsi di persone](./assets/person-journeys-list-search.png){width="800" zoomable="yes"}

1. Utilizzare gli strumenti elenco per personalizzare l&#39;elenco visualizzato:

   * Fai clic sull&#39;icona _Filtro_ ( ![Icona Filtro](../assets/do-not-localize/icon-react-filter.svg) ) per filtrare l&#39;elenco in base allo stato.
   * Fai clic sull&#39;icona _Personalizza tabella_ ( ![Personalizza icona tabella](../assets/do-not-localize/icon-falco-customize-table.svg) ) per controllare le colonne visualizzate.
   * Fai clic sull&#39;icona _Ripristina colonne_ ( ![Icona Ripristina larghezza colonne](../assets/do-not-localize/icon-falco-reset-columns.svg) ) per reimpostare la larghezza delle colonne.

### Colonne elenco percorso {#journey-list-columns}

La pagina dell&#39;elenco percorsi include le colonne riportate di seguito.

* [!UICONTROL Nome] (fare clic sul nome per aprire l&#39;area di lavoro del percorso per la modifica)
* [!UICONTROL Stato]
* [!UICONTROL Data di creazione]
* [!UICONTROL Creato da]
* [!UICONTROL Ultimo aggiornamento]
* [!UICONTROL Ultimo aggiornamento effettuato da]
* [!UICONTROL Pubblicato il]
* [!UICONTROL Pubblicato da]
* [!UICONTROL Data di inizio]
* [!UICONTROL Data di fine]

Puoi ordinare l&#39;elenco in base a _[!UICONTROL Stato]_, _[!UICONTROL Data di creazione]_ o _[!UICONTROL Ultimo aggiornamento]_ facendo clic sull&#39;intestazione della colonna. Per modificare la larghezza delle colonne visualizzate, puoi trascinare i bordi delle intestazioni. Nella finestra di dialogo _Personalizza tabella_, seleziona o deseleziona le caselle di controllo e fai clic su **[!UICONTROL Applica]**.

### Stato del percorso {#journey-status}

Lo stato di un percorso può cambiare in base alle azioni applicate. In base allo stato di un percorso, alcune azioni sono disponibili dal lato destro dell’intestazione.

| Stato | Descrizione | Azioni disponibili |
| ------ | ----------- | ----------------- |
| _**Bozza**_ | Un percorso non pubblicato che può essere modificato. | [Pubblicazione](#publish-a-journey), [Duplicata](#duplicate-a-journey), [Elimina](#delete-a-journey) |
| _**Live**_ | Lo stato del percorso cambia da _Bozza_ a _Live_ quando pubblichi un percorso. Se il percorso si trova in questo stato, non può più essere modificato. | [Duplicato](#duplicate-a-journey), [Vicino alle nuove voci](#close-to-new-entries), [Interrompi](#abort-a-journey) |
| _**Chiuso alle nuove voci**_ | Lo stato del percorso cambia da _Live_ a _Chiuso alle nuove voci_ quando si fa clic su **[!UICONTROL Chiudi alle nuove voci]** nell&#39;intestazione del percorso. | [Duplicato](#duplicate-a-journey), [Interrompi](#abort-a-journey) |
| _**Annullato**_ | Lo stato del percorso cambia da _Live_ o _Chiuso alle nuove voci_ quando interrompi un percorso. Un percorso interrotto non può essere riavviato. | [Duplicato](#duplicate-a-journey), [Elimina](#delete-a-journey) |
| _**Completato**_ | Quando tutti i membri del pubblico in un percorso completano il percorso, lo stato cambia da _Live_ o _Closed to new entries_ a _Finished_. | [Duplicato](#duplicate-a-journey), [Elimina](#delete-a-journey) |

## Creazione di un percorso di persone {#create-a-person-journey}

1. Fai clic su **[!UICONTROL Crea Percorso]** in alto a destra nell&#39;elenco dei percorsi.

1. Nella finestra di dialogo, seleziona il programma **[!UICONTROL Principale]** per il percorso di persone.

1. Immetti un **[!UICONTROL Nome]** univoco (obbligatorio) e **[!UICONTROL Descrizione]** (facoltativo).

   ![Finestra di dialogo Crea percorso di persone](./assets/person-journey-create-dialog.png){width="400"}

1. Fai clic su **[!UICONTROL Crea]**.

   L’area di lavoro del percorso si apre con il nodo di pubblico Persona iniziale.

   ![area di lavoro Percorso per nuovo percorso di persone](./assets/person-journey-new.png){width="600" zoomable="yes"}

### Intestazione percorso {#journey-header}

L’intestazione di ogni area di lavoro del percorso include il nome, lo stato e la pianificazione del percorso.

![Intestazione percorso di persone](./assets/person-journey-header.png){width="600" zoomable="yes"}

* Fai clic sull&#39;icona _Modifica_ ( ![Modifica icona](../assets/do-not-localize/icon-react-edit.svg) ) per modificare il nome o le informazioni di descrizione del percorso.
* Fai clic su **[!UICONTROL Impostazioni Percorso]** per modificare l&#39;inizio del percorso e la ricorrenza.
* Fare clic su **[!UICONTROL ... Altro]** per applicare un&#39;azione di percorso o per abilitare/disabilitare [il controllo del traffico di percorso](./journey-traffic-control.md) e reinserire.
* Se tutti gli errori sono stati risolti e si desidera attivare il percorso, fare clic su **[!UICONTROL Pubblica]**.

### Progettazione percorso {#journey-design}

L&#39;area di lavoro _percorso_ è la zona centrale nell&#39;area di lavoro percorso. È dove puoi aggiungere nodi di percorso e configurarli. Fai clic su un nodo per aprirne le proprietà nel pannello a destra del layout e impostarle in base al design. Un percorso di persone inizia sempre con un nodo [_[!UICONTROL Pubblico persona ]_](./person-audience-node.md), in cui puoi definire l&#39;input per il percorso.

Dopo aver creato un percorso di persone e aver definito il pubblico di tale persona, crea il percorso utilizzando i nodi. L’area di lavoro del percorso fornisce uno spazio di progettazione visiva in cui puoi creare i casi di utilizzo del marketing B2B a più passaggi utilizzando i seguenti tipi di nodo per creare il percorso:

* [Intraprendere un’azione](./action-nodes.md)
* [Ascoltare un evento](./listen-for-event-nodes.md)
* [Attendere](./wait-nodes.md)
* [Suddividi percorsi](./split-merge-paths-nodes.md)
* [Prossimo percorso migliore](./next-best-path.md)
* [Unisci percorsi](./split-merge-paths-nodes.md)

## Gestione dei percorsi {#journey-management}

Aprire l&#39;elenco percorsi per esaminare lo stato del percorso, apportare modifiche ed eseguire azioni.

### Azioni percorso {#journey-actions}

La pagina dell’elenco percorsi include tutti i percorsi di persone nell’istanza di Marketo Optimizer. Dalla pagina dell’elenco, puoi applicare una serie di azioni a un percorso.

#### Pubblicare un percorso {#publish}

È possibile pubblicare un percorso se non sono presenti errori di blocco. Quando viene pubblicato, lo stato del percorso cambia in _Live_. In caso di errori del percorso, il pulsante **[!UICONTROL Pubblica]** viene visualizzato in grigio con il messaggio `Resolve errors before publishing`.

1. Aprire il percorso bozza dall&#39;elenco _[!UICONTROL percorsi di persone]_.

1. In alto a destra nell&#39;area di lavoro del percorso, fai clic su **[!UICONTROL Pubblica]**.

1. Nella finestra di dialogo _[!UICONTROL Rivedi impostazioni percorso]_, imposta le opzioni di avvio del percorso.

   Se hai già definito una pianificazione in **[!UICONTROL Impostazioni Percorso]**, controlla le impostazioni.

   Se è necessario impostare l&#39;attivazione del percorso, scegliere un tipo di pianificazione:

   * Per attivare il percorso in fase di pubblicazione, scegliere **[!UICONTROL Immediatamente]**.
   * Per attivare il percorso in una data futura, scegli **[!UICONTROL In una data specifica]** e fai clic sull&#39;icona _Calendario_ per selezionare la data.

1. Se necessario, specifica la **[!UICONTROL data di fine]** per il percorso.

   ![Finestra di dialogo Rivedi impostazioni percorso](./assets/journey-publish-review-settings.png){width="400" zoomable="no"}

   Può essere un massimo di tre anni dalla data di inizio. Questo campo è obbligatorio per la pubblicazione.

1. Fai clic su **[!UICONTROL Avanti]**.

1. Nella finestra di dialogo di conferma, fai clic su **[!UICONTROL Pubblica]**.

#### Interrompi un percorso {#abort-a-journey}

Se si interrompe un percorso in tempo reale o un percorso pianificato per una data di inizio futura, le persone nel percorso interrompono immediatamente i loro progressi e non può accadere alcun ulteriore ingresso al percorso. Un percorso interrotto non può essere riavviato.

1. Apri il percorso dall&#39;elenco _[!UICONTROL percorsi di persone]_.

1. Fare clic su **[!UICONTROL ... Altro]** in alto a destra e scegli **[!UICONTROL Interrompi]**.

   ![Intestazione percorso persona in tempo reale](./assets/person-journey-live-header.png){width="600" zoomable="yes"}

1. Nella finestra di dialogo di conferma, fai clic su **[!UICONTROL Interrompi]**.

#### Chiudi ai nuovi ingressi {#close-to-new-entries}

Se chiudi un percorso in tempo reale ai nuovi ingressi, le persone attualmente nel percorso continuano il loro percorso in quel percorso e non può accadere alcun ulteriore ingresso al percorso. Un percorso chiuso non può essere riavviato, ma può essere duplicato.

1. Apri il percorso dall&#39;elenco _[!UICONTROL percorsi di persone]_.

1. Fare clic su **[!UICONTROL ... Altro]** in alto a destra e scegli **[!UICONTROL Chiudi alle nuove voci]**.

1. Nella finestra di dialogo di conferma, fai clic su **[!UICONTROL Chiudi a nuovi ingressi]**.

#### Duplicare un percorso {#duplicate-a-journey}

Un’azione di duplicazione è simile a una funzione di clonazione, ma un percorso duplicato non include le risorse dei contenuti del percorso create. Potete duplicare i dettagli del percorso o semplicemente una semplice ossatura della struttura del flusso e del percorso.

1. Nell&#39;elenco _[!UICONTROL percorsi di persone]_ fare clic sull&#39;icona _Altro_ ( **...** ) accanto al nome del percorso e scegliere **[!UICONTROL Duplica]**.

   ![Menu Altro percorso bozza persona](./assets/person-journey-draft-more-menu.png){width="400"}

   A seconda dello stato del percorso, puoi anche accedere all’azione duplicata dai dettagli del percorso o dall’area di lavoro del percorso:

   * Per un percorso bozza, fare clic su **[!UICONTROL ... Altro]** in alto a destra e scegli **[!UICONTROL Duplica]**.
   * Per tutti gli altri stati del percorso, fai clic su **[!UICONTROL Duplica]** in alto a destra.

1. Nella finestra di dialogo, seleziona il programma **[!UICONTROL Principale]** per il percorso duplicato.

1. Immetti un **[!UICONTROL Nome]** univoco (obbligatorio) e **[!UICONTROL Descrizione]** (facoltativo).

   Per impostazione predefinita, nella finestra di dialogo viene utilizzato il nome del percorso di origine aggiunto con `_copy`. Immettere un nome univoco diverso per il percorso in base alle esigenze.

   ![Finestra di dialogo Duplica percorso](./assets/journey-duplicate-dialog.png){width="370"}

1. Scegli il **[!UICONTROL Tipo]** di duplicazione:

   * **[!UICONTROL Duplicazione parziale del contenuto]**: utilizza questo tipo per copiare tutto ciò che si trova nel percorso, esclusi i messaggi e-mail o SMS creati. I nodi che fanno riferimento a un messaggio e-mail o SMS di Marketo Engage rimangono completamente intatti.

   * **[!UICONTROL Duplica senza dettagli]** - Utilizzare questo tipo per copiare solo la struttura e i percorsi dei nodi. Tutte le impostazioni del nodo e le condizioni del percorso non sono definite (impostazione predefinita), pertanto puoi riutilizzare il flusso di base con diverse impostazioni di pubblico, azioni e segmentazione del percorso. Tutti i nodi Wait (Attesa) utilizzano il valore predefinito di cinque giorni.

1. Fai clic su **[!UICONTROL Duplica]**.

   Il percorso duplicato viene aperto nell’area di lavoro del percorso, dove puoi impostare i dettagli e creare il contenuto del percorso in base alle esigenze.

#### Eliminare un percorso {#delete-a-journey}

Utilizza un’azione di eliminazione per eliminare definitivamente un percorso. Non puoi eliminare un percorso attivo o un percorso pianificato per una data di inizio futura.

>[!WARNING]
>
>L’eliminazione di un percorso è permanente e non può essere annullata.

1. Nell&#39;elenco _[!UICONTROL percorsi di persone]_ fare clic sull&#39;icona _Altro_ ( **...** ) accanto al nome del percorso e scegliere **[!UICONTROL Elimina]**.

   A seconda dello stato del percorso, puoi anche accedere all’azione di eliminazione dall’intestazione del percorso:

   * Per un percorso bozza, fare clic su **[!UICONTROL ... Altro]** in alto a destra e scegli **[!UICONTROL Elimina]**.
   * Per altri stati del percorso, ad esempio _Completato_ o _Interrotto_, fai clic su **[!UICONTROL Elimina]** in alto a destra.

1. Nella finestra di dialogo di conferma, fai clic su **[!UICONTROL Elimina]**.
