---
title: Moduli
description: 'Creazione e gestione di moduli riutilizzabili per la raccolta dati aziendali: progettare campi, impostare pagine di ringraziamento, pubblicare e tenere traccia dell’utilizzo in Marketo Optimizer.'
TQID: 'https://experienceleague.adobe.com/StexA1TJKaBYnAoIMcxnHIoUwzfMAnJrBO7FDLdLnMo'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2: id: 8881ff95-1653-5fea-82af-ce1549c0d99did: a29661b8-f7a4-53d1-a9ac-fdec08c092e4id: d4203578-d294-5145-b397-f26f4488a904
topic_v2: id: d3cdead0-685a-4489-9250-4bb709942f66id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 2434
ht-degree: 2%

---

# Moduli

Per acquisire informazioni dai visitatori delle pagine web, crea moduli e aggiungili alle pagine di destinazione. Un modulo è un insieme di campi che i visitatori della pagina completano e inviano per ottenere un qualche tipo di contenuto o offerta, ad esempio un white paper, un webinar on-demand o una versione di prova gratuita.

La quantità di informazioni che il modulo deve acquisire dipende dal valore del contenuto o dell’offerta. Se offri qualcosa di semplice, come un white paper, raccogli solo informazioni minime, come nome, e-mail e azienda. Se l’offerta presenta un valore superiore, ad esempio una demo o una versione di prova gratuita, puoi raccogliere ulteriori informazioni. La richiesta di un modulo inviato per consentire la visualizzazione del contenuto è denominata _contenuto gestito_. L&#39;organizzazione decide quale contenuto deve essere gestito e quale non è (_libero_). La best practice prevede l’autorizzazione gratuita di alcuni contenuti e l’accesso solo ai contenuti premium o ad alta richiesta.

>[!PREREQUISITES]
>
>Prima che i team di marketing possano creare e utilizzare i moduli per acquisire informazioni, un amministratore deve definire uno o più predefiniti per moduli. Per ulteriori informazioni, vedere [_Configurazioni Forms_](../admin/configuration-presets-forms.md).

<!-- 
>Form creation in [!DNL Marketo Optimizer] requires the following [permissions](../start/user-management.md#b2b-product-permissions):
>
>* _[!UICONTROL Journey Optimizer Library]_ > _[!UICONTROL Read B2C Forms]_ - Required to access and view forms.
>* _[!UICONTROL Journey Optimizer Library]_ > _[!UICONTROL Manage B2C Forms]_ - Required to create, update, and delete forms.
>* _[!UICONTROL Journey Optimizer Library]_ > _[!UICONTROL Publish B2C Forms]_ - Required to publish forms.
-->

## Accedere e gestire i moduli {#view-forms}

Per accedere ai moduli in [!DNL Marketo Optimizer], passa alla navigazione a sinistra e fai clic su **[!UICONTROL Gestione contenuto]** > **[!UICONTROL Forms]**. Questa azione consente di aprire una pagina di elenco in cui vengono visualizzati tutti i moduli creati nell’istanza.

![Accedere alla raccolta moduli](./assets/forms-list.png){width="800" zoomable="yes"}

Il sistema ordina la tabella in base alla colonna _[!UICONTROL Modificato]_, che mostra i moduli aggiornati più di recente nella parte superiore per impostazione predefinita. Fai clic sul titolo della colonna per passare da crescente a decrescente.

### Stato e ciclo di vita del modulo {#form-status}

Lo stato del modulo determina la disponibilità del modulo per l’utilizzo in una pagina di destinazione o in un modello di pagina di destinazione e le modifiche che è possibile apportare.

| Stato | Descrizione |
| -------------------- | ----------- |
| Bozza | Quando si crea un modulo, il modulo si trova nello stato Bozza. Rimane in questo stato mentre definisci o modifichi i campi fino a quando non li pubblichi per l’utilizzo in una pagina di destinazione o in un modello di pagina di destinazione. Azioni disponibili:<br/><ul><li>Modifica tutti i dettagli<li>Modifica nello spazio di progettazione visiva<li>Pubblica<li>Duplica<li>Elimina |
| Pubblicato | Quando pubblichi un modulo, questo diventa disponibile per l’utilizzo in una pagina di destinazione o in un modello di pagina di destinazione. Il contenuto del modulo pubblicato non può essere modificato nello spazio di progettazione visiva. Azioni disponibili:<br/><ul><li>Modifica nome, descrizione o pagina di ringraziamento<li>Aggiungi a una pagina di destinazione o a un modello di pagina di destinazione<li>Crea versione bozza<li>Duplica<li>Elimina (se non in uso)<li>Codice da incorporare |
| Pubblicato con bozza | Quando crei una bozza da un modulo pubblicato, la versione pubblicata rimane disponibile per l’utilizzo in una pagina di destinazione o in un modello. Il contenuto della bozza può essere modificato nello spazio di progettazione visiva. Se pubblichi la versione bozza, questa sostituisce la versione pubblicata corrente e il contenuto viene aggiornato nelle pagine di destinazione o nei modelli di pagina di destinazione in cui è in uso. Azioni disponibili:<br/><ul><li>Modificare le pagine di nome, descrizione o ringraziamento<li>Aggiungi a una pagina di destinazione o a un modello di pagina di destinazione<li>Modifica versione bozza in Visual Design Space<li>Pubblica versione bozza<li>Duplica<li>Elimina (se non in uso)<li>Codice da incorporare |

![Ciclo di vita stato modulo](assets/status-lifecycle-diagram.png){zoomable="yes"}

### Filtrare l’elenco dei moduli {#filter-list}

Per cercare un modulo per nome, immettere una stringa di testo nella barra di ricerca per trovare una corrispondenza. Fai clic sull&#39;icona _Filtro_ ( ![Mostra o nascondi icona filtri](../assets/do-not-localize/icon-filter.svg) ) per visualizzare le opzioni di filtro disponibili e modificare le impostazioni per filtrare gli elementi visualizzati in base ai criteri specificati.

![Filtra i moduli visualizzati](assets/forms-list-filtered.png){width="700" zoomable="yes"}

### Personalizzare la visualizzazione delle colonne {#column-display}

Personalizza le colonne da visualizzare nella tabella facendo clic sull&#39;icona _Personalizza tabella_ ( ![Personalizza icona tabella](../assets/do-not-localize/icon-column-settings.svg) ) in alto a destra.

Nella finestra di dialogo, seleziona le colonne da visualizzare e fai clic su **[!UICONTROL Applica]**.

![Colonne da visualizzare nell&#39;elenco di Forms](assets/forms-customize-table-dialog.png){width="300"}

## Creare moduli {#create-forms}

Prima di iniziare a creare moduli riutilizzabili in [!DNL Marketo Optimizer], è necessario prendere in considerazione diversi aspetti:

* Determinare i moduli necessari.

  Può essere possibile utilizzare solo quattro moduli standard. Uno per accedere ai contenuti scaricabili, uno per accedere alle pagine web premium, uno per visualizzare i video e uno per registrarsi per elementi come i webinar. Se hai bisogno di modificare un campo in un modulo, è più semplice aggiornare quattro moduli standard utilizzati a livello globale invece di modificare più moduli distribuiti in tutti i programmi di marketing.

  <!-- Global forms also make progressive profiling much easier to implement. -->

* Per ogni modulo standard, determina quali campi utilizzare e come presentarli.

  Considera l’utilizzo di forme più brevi, in quanto si è dimostrato che sono migliori per le conversioni. Quando si analizza ogni modulo, stabilire quali campi sono ragionevoli e necessari per il relativo scopo.

  Valuta se precompilare i campi del modulo in modo che le informazioni di base, come nome e e-mail, siano precompilate. Ma altre informazioni, come la qualifica e le dimensioni dell&#39;organizzazione, non lo sono. In questo modo, il visitatore deve compilare solo due campi e inviare il modulo. Puoi anche utilizzare un modulo social compilato con dati provenienti da Facebook o Twitter.

* Pianifica la pagina di follow-up visualizzata dopo l&#39;invio di un modulo da parte di un visitatore (_grazie_).

  Tutti ottengono la stessa pagina o è dinamica e basata sui loro dati? Ad esempio, un utente del settore sanitario potrebbe visualizzare una pagina con un contenuto diverso rispetto a un utente del settore tecnologico.

* Valutare se ignorare completamente un modulo se si dispone già delle informazioni necessarie.

  Quando consenti il bypass di un modulo a una persona nota che visita la pagina di destinazione, può semplicemente accedere al contenuto direttamente. Ignorando il modulo si ottiene un’esperienza del visitatore più semplice.

### Aggiungere un nuovo modulo {#new-form}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_lp_form_preset"
>title="Selezionare un predefinito"
>abstract="Scegli un predefinito preimpostato contenente la connessione da utilizzare e un set di dati preimpostato per il modulo."
>additional-url="https://experienceleague.adobe.com/it/docs/journey-optimizer-b2b/prime/admin/channels/configuration-presets-forms#create-preset" text="Creare un predefinito di modulo"

Puoi creare un modulo in [!DNL Marketo Optimizer] facendo clic su **[!UICONTROL Crea modulo]** in alto a destra nella pagina dell&#39;elenco _[!UICONTROL Forms]_.

1. Nella finestra di dialogo _[!UICONTROL Crea modulo]_, immetti un **[!UICONTROL Nome]** (obbligatorio) e una **[!UICONTROL Descrizione]** (facoltativo) utili.

   Requisiti del modulo:

   * Nome: massimo 100 caratteri, deve essere univoco, senza distinzione tra maiuscole e minuscole
   * Descrizione: massimo 300 caratteri
   * Alpha, caratteri numerici e speciali sono consentiti
   * I caratteri riservati sono **_non consentiti_**: `\ / : * ? " < > |`

   ![Finestra di dialogo Crea modulo](assets/forms-create-dialog.png){width="400"}

1. Per **[!UICONTROL Predefinito]**, fai clic sull&#39;icona _Seleziona dati_ ( ![Seleziona icona dati](../assets/do-not-localize/icon-select-data.svg) ) per collegare al modulo un predefinito di modulo configurato.

   Il predefinito determina dove vengono memorizzate e riflesse le risposte del modulo. Potete immettere una stringa di testo per cercare un predefinito specifico o selezionarlo dall&#39;elenco.

1. Fai clic su **[!UICONTROL Crea]**.

   Viene visualizzata la pagina dei dettagli del modulo con una definizione di base predefinita.

   ![Contenuto modulo predefinito](assets/form-new-default-content.png){width="700" zoomable="yes"}

### Modificare la struttura predefinita del modulo {#design}

Utilizza gli strumenti di progettazione visiva per modificare il contenuto del modulo in base alle esigenze:

* [Aggiungi campi](./form-design.md#add-field)
* [Modificare lo stile dei campi](./form-design.md#field-styling)
* [Riordina campi](./form-design.md#field-reorder)
* [Modificare il testo e lo stile del pulsante di invio](./form-design.md#submit-button)
* [Modificare lo stile del modulo](./form-design.md#form-styling)

Fai clic su **[!UICONTROL Salva e chiudi]** per salvare le modifiche alla struttura del contenuto del modulo e passare ai dettagli del modulo.

### Impostare la pagina di ringraziamento {#thank-you-page}

Nel pannello _[!UICONTROL Riepilogo]_ a destra, scorri fino alla sezione **[!UICONTROL Pagina di ringraziamento]** e utilizza l&#39;impostazione **[!UICONTROL Completa con]** per definire cosa accade quando un visitatore invia il modulo:

* **[!UICONTROL Resta a pagina]** - Scegli questa opzione per mantenere il visitatore sulla stessa pagina al momento dell&#39;invio del modulo.
* **[!UICONTROL Pagina di destinazione]** - Scegli questa opzione per selezionare una pagina di destinazione [!DNL Marketo Optimizer] come follow-up.
* **[!UICONTROL URL esterno]** - Scegliere questa opzione per specificare qualsiasi URL come pagina di follow-up. Dopo che il visitatore ha inviato il modulo, il browser carica l’URL designato.

  >[!TIP]
  >
  >Se desideri utilizzare il modulo per scaricare un file, puoi specificare un URL per il file ospitato. Con questa configurazione, il pulsante Invia funziona come un pulsante di download.

### Pubblicare la bozza del modulo {#publish}

Quando sei pronto a rendere il modulo disponibile per l&#39;utilizzo in una pagina di destinazione o in un modello di pagina di destinazione, fai clic su **[!UICONTROL Pubblica]**.

![Finestra di dialogo Pubblica modulo](assets/form-publish-dialog.png){width="400"}

Questa azione apre una finestra di dialogo di conferma. È possibile interrompere il processo di pubblicazione facendo clic su **[!UICONTROL Annulla]** oppure su **[!UICONTROL Pubblica]** per confermare.

## Visualizza dettagli modulo {#view-details}

Fare clic sul nome di un modulo nella pagina elenco per aprire la pagina dettagli modulo. È possibile modificare il modulo, rinominarlo o aggiornarne la descrizione. Per salvare automaticamente le modifiche, apporta gli aggiornamenti e fai clic all’esterno del campo nome o descrizione.

>[!NOTE]
>
>Se un modulo pubblicato è utilizzato da una pagina di destinazione o da un modello di pagina di destinazione, non è possibile modificare il contenuto o la pagina di ringraziamento. È possibile creare una bozza di versione se si desidera apportare modifiche al modulo.

![Visualizza dettagli per un modulo pubblicato](assets/form-details-published.png){width="600" zoomable="yes"}

Fare clic su **[!UICONTROL Modifica modulo]** per aprire il modulo nello spazio di progettazione visiva.

Uscire dalla visualizzazione in qualsiasi momento facendo clic sulla freccia _Indietro_ in alto a sinistra, per tornare alla pagina dell&#39;elenco _[!UICONTROL Forms]_.

## Visualizza riferimenti modulo utilizzato da {#used-by}

Nel pannello _[!UICONTROL Riepilogo]_ a destra, fai clic sulla scheda **[!UICONTROL Usato da]** per visualizzare i dettagli della posizione in cui il modulo è attualmente utilizzato in [!DNL Marketo Optimizer], tra le pagine di destinazione e i modelli di pagina di destinazione.

>[!IMPORTANT]
>
>Non è possibile eliminare i moduli attualmente utilizzati da pagine di destinazione o modelli di pagine di destinazione.

![Utilizzato dai riferimenti per il modulo](assets/form-used-by-published.png){width="600" zoomable="yes"}

I riferimenti vengono visualizzati in base alla categoria: _Pagina di destinazione_ o _Modello pagina di destinazione_. Fare clic sul collegamento per aprire la pagina o il modello corrispondente in cui viene utilizzato il modulo.

## Elimina moduli {#delete-forms}

Non è possibile eliminare i moduli attualmente utilizzati da una pagina di destinazione o da un modello di pagina di destinazione. Prima di avviare la rimozione di un modulo, è possibile controllare i riferimenti _used-by_. Inoltre, una rimozione non può essere annullata, pertanto controlla prima di avviare un’azione di eliminazione.

È possibile eliminare un modulo utilizzando uno dei metodi seguenti:

* In alto a destra, fai clic su **[!UICONTROL ... Altro]** e scegliere **[!UICONTROL Elimina]**.
* Dalla pagina dell&#39;elenco _[!UICONTROL Forms]_, fare clic su _Altro_ (**...**) accanto al nome del modulo e scegliere **[!UICONTROL Elimina]**.

Questa azione apre una finestra di dialogo di conferma. È possibile interrompere il processo facendo clic su **[!UICONTROL Annulla]** oppure su **[!UICONTROL Elimina]** per confermare l&#39;eliminazione.

![Finestra di dialogo Elimina modulo](assets/form-delete-dialog.png){width="400"}

Se il modulo è attualmente in uso, l&#39;azione apre una finestra di dialogo informativa che avvisa che non è possibile eliminarlo. Fare clic su **[!UICONTROL OK]** per interrompere l&#39;azione di eliminazione.

![Finestra di dialogo Elimina modulo - impossibile eliminare il modulo in uso](assets/form-delete-dialog-in-use.png){width="400"}

## Duplicare i moduli {#duplicate-forms}

Duplicare un modulo come metodo rapido e semplice per creare un nuovo modulo utilizzando un modulo esistente come punto di partenza per la progettazione del modulo.

È possibile duplicare un modulo utilizzando uno dei metodi seguenti:

* Nella parte superiore destra della pagina dei dettagli del modulo fare clic su **[!UICONTROL ... Altro]** e scegli **[!UICONTROL Duplicato]**.
* Dalla pagina dell&#39;elenco _[!UICONTROL Forms]_, fare clic su _Altro_ (**...**) accanto al nome del modulo e scegliere **[!UICONTROL Duplica]**.

![Duplica il modulo](assets/form-list-page-duplicate.png){width="450"}

Nella finestra di dialogo, inserisci un nome utile (univoco) e una descrizione. Fai clic su **[!UICONTROL Duplica]** per completare l&#39;azione.

![Nome e descrizione del modulo duplicato](assets/form-duplicate-dialog.png){width="400"}

Modificate il modulo duplicato per modificare il nome in base alle esigenze e modificare il modulo per l&#39;uso previsto.

## Modifica moduli {#edit-forms}

Le modifiche apportate a un modulo dipendono dallo stato corrente:

* Quando un modulo è nello stato _Bozza_, è possibile modificarne i dettagli e il contenuto (campi, pulsante e stile).
* Quando un modulo è nello stato _Pubblicato_, è possibile modificarne il nome o la descrizione. Non è possibile modificare il contenuto.
* Quando un modulo è in stato _Pubblicato con bozza_, è possibile modificarne il nome o la descrizione. Nella versione bozza, è inoltre possibile modificare il contenuto e la pagina di ringraziamento.

>[!BEGINTABS]

>[!TAB Bozza]

1. Nella pagina dell&#39;elenco _[!UICONTROL Forms]_ fare clic sul nome del modulo per aprirlo.

   Viene visualizzata un’anteprima del contenuto del modulo, con i dettagli del modulo a destra.

1. Modifica uno dei dettagli, ad esempio nome e descrizione.

   ![Dettagli modulo con stato Bozza](assets/form-details-draft.png){width="600" zoomable="yes"}

1. Per apportare modifiche al modulo nello spazio di progettazione visivo, fare clic su **[!UICONTROL Modifica modulo]**.

   Utilizza gli strumenti di progettazione visiva secondo necessità:

   * [Aggiungi campi](./form-design.md#add-field)
   * [Modificare lo stile dei campi](./form-design.md#field-styling)
   * [Riordina campi](./form-design.md#field-reorder)
   * [Modificare il testo e lo stile del pulsante di invio](./form-design.md#submit-button)
   * [Modificare lo stile del modulo](./form-design.md#form-styling)

   Fai clic su **[!UICONTROL Salva e chiudi]** per tornare ai dettagli del modulo.

1. Quando il modulo soddisfa i criteri e desideri renderlo disponibile per l&#39;utilizzo in una pagina di destinazione o in un modello di pagina di destinazione, fai clic su **[!UICONTROL Pubblica]**.

>[!TAB Pubblicato]

1. Nella pagina dell&#39;elenco _[!UICONTROL Forms]_ fare clic sul nome del modulo per aprirlo.

   Viene visualizzata un’anteprima del contenuto del modulo, con i dettagli del modulo a destra.

1. Per creare una bozza della versione per la modifica del modulo, fai clic su **[!UICONTROL Modifica modulo]** nel pannello _[!UICONTROL Riepilogo]_ a destra.

1. Fare clic su **[!UICONTROL Crea bozza versione]** nella finestra di dialogo per aprire la bozza versione nello spazio di progettazione visivo.

   ![Finestra di dialogo Crea bozza versione](assets/form-published-edit-create-draft-dialog.png){width="400"}

1. Utilizza gli strumenti di progettazione visiva necessari per aggiornare il contenuto del modulo:

   * [Aggiungi campi](./form-design.md#add-field)
   * [Modificare lo stile dei campi](./form-design.md#field-styling)
   * [Riordina campi](./form-design.md#field-reorder)
   * [Modificare il testo e lo stile del pulsante di invio](./form-design.md#submit-button)
   * [Modificare lo stile del modulo](./form-design.md#form-styling)

   Fai clic su **[!UICONTROL Salva e chiudi]** per tornare ai dettagli del modulo.

1. Quando la bozza del modulo soddisfa i criteri e desideri rendere le modifiche disponibili per l&#39;utilizzo in una pagina di destinazione o in un modello di pagina di destinazione, fai clic su **[!UICONTROL Pubblica]**.

   Quando pubblichi la versione bozza, questa sostituisce la versione pubblicata corrente e il contenuto del modulo viene aggiornato nelle pagine di destinazione o nei modelli di pagina di destinazione in cui è già in uso.

>[!TAB Pubblicato con bozza]

1. Fare clic sul nome del modulo per aprirlo.
1. Selezionare la scheda **[!UICONTROL Bozza]**.

   Viene visualizzata un’anteprima del contenuto del modulo della versione bozza, con i dettagli del modulo a destra.

   ![Modifica versione bozza modulo](assets/form-published-with-draft-edit.png){width="700" zoomable="yes"}

1. Fai clic su **[!UICONTROL Modifica modulo]** nel riquadro _[!UICONTROL Riepilogo]_ a destra e utilizza gli strumenti di progettazione visiva in base alle esigenze:

   * [Aggiungi campi](./form-design.md#add-field)
   * [Modificare lo stile dei campi](./form-design.md#field-styling)
   * [Riordina campi](./form-design.md#field-reorder)
   * [Modificare il testo e lo stile del pulsante di invio](./form-design.md#submit-button)
   * [Modificare lo stile del modulo](./form-design.md#form-styling)

   Fai clic su **[!UICONTROL Salva e chiudi]** per tornare ai dettagli del modulo.

1. Quando la bozza del modulo soddisfa i criteri e desideri rendere le modifiche disponibili per l&#39;utilizzo in pagine di destinazione e modelli di pagina di destinazione, fai clic su **[!UICONTROL Pubblica]**.

   Quando pubblichi la versione bozza, questa sostituisce la versione pubblicata corrente e il modulo viene aggiornato nelle pagine di destinazione e nei modelli in cui è già in uso.

>[!ENDTABS]

## Aggiungere moduli a una pagina di destinazione o a un modello {#insert-forms}

Forms è progettato per essere riutilizzato e può essere inserito durante la progettazione di una [pagina di destinazione](./landing-pages.md).

<!-- or [landing page template](./landing-page-templates.md). -->

{{$include /help/_includes/content-design-add-forms.md}}

## Azioni modulo per la creazione di pagine e modelli {#form-actions}

Quando un modulo viene incluso in una pagina di destinazione o in un modello di pagina di destinazione, il contenuto del modulo non può essere modificato all’interno della pagina o del modello. Tuttavia, puoi applicare le seguenti azioni:

* **[!UICONTROL Elimina]** - Questa azione rimuove il modulo dalla pagina corrente o dal contenuto del modello (l&#39;origine del modulo non è interessata).
* **[!UICONTROL Duplica]** - Questa azione duplica il modulo nell&#39;editor, mantenendo le stesse dimensioni.
* **[!UICONTROL Visualizza HTML]** - Questa azione apre un popup con HTML per il modulo. Puoi modificare il HTML o copiarlo per utilizzarlo in altri contenuti web.
* **[!UICONTROL Modifica modulo]** - Questa azione apre una nuova scheda del browser con la pagina e i dettagli dell&#39;editor moduli.

Quando selezioni il modulo nello spazio di progettazione della pagina di destinazione, queste azioni sono disponibili nella barra degli strumenti contestuale e nel pannello delle proprietà a destra.

![Applica azioni al modulo selezionato](assets/form-actions-page-authoring.png){width="600" zoomable="yes"}
