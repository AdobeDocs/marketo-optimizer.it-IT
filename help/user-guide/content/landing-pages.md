---
title: Pagine di destinazione
description: 'Creazione, progettazione e pubblicazione di pagine di destinazione per percorsi di persone: puoi creare da zero, importare HTML, aggiungere moduli, personalizzare il contenuto e collegare le e-mail in Marketo Optimizer.'
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '1589'
ht-degree: 2%

---

# Pagine di destinazione

Una pagina di destinazione è una pagina web indipendente in cui puoi indirizzare contatti e clienti dopo che hanno fatto clic su un elemento collegato in un’e-mail, un messaggio SMS o qualsiasi posizione digitale. Puoi incorporare queste pagine nei tuoi percorsi per consentire ai potenziali clienti e ai clienti di visualizzare i messaggi sul web e i progressi compiuti nei tuoi percorsi.

Casi d’uso comuni per le pagine di destinazione:

* Fornisci il consenso o la rinuncia alle comunicazioni di marketing o a un servizio specifico. Utilizza un collegamento a un elenco di destinazione in un’e-mail o in un’altra comunicazione.
* Raccogli il consenso prima di inviare le comunicazioni e invia un’e-mail di conferma in caso di consenso o rinuncia.
* Acquisisci o aggiorna i dati del profilo (profilatura progressiva, preferenze, registrazioni e scenari simili) utilizzando i moduli nelle pagine di destinazione.
* Indirizza le persone a informazioni specifiche per la campagna progettate per l’orchestrazione del percorso.
* Reindirizza le persone a un modulo web dedicato senza creare una pagina esterna all&#39;esterno di [!DNL Marketo Optimizer].

## Flusso di lavoro per pagina di destinazione {#workflow}

Per indirizzare i membri di un pubblico di percorso a una pagina Web definita quando fanno clic su un collegamento specifico, creare una pagina di destinazione in [!DNL Marketo Optimizer]:

1. [Crea la pagina](./landing-pages-create-publish.md#create-landing-page) - Seleziona un predefinito, imposta la pagina principale e aggiungi eventuali pagine secondarie richieste.
1. [Progettare il contenuto della pagina di destinazione](./landing-page-design.md) - Creare il contenuto della pagina utilizzando i componenti di progettazione visiva trascinati.
1. [Verifica la pagina di destinazione](./landing-pages-create-publish.md#test-landing-page) - Anteprima della pagina e verifica del comportamento del modulo.
1. [Pubblica la pagina di destinazione](./landing-pages-create-publish.md#publish-landing-page) - Pubblica per rendere la pagina live e disponibile per il collegamento.
1. [Collega alla pagina dal tuo percorso](#link-to-landing-page). Aggiungi l&#39;URL della pagina di destinazione a un&#39;azione e-mail, SMS o percorso in modo che i destinatari possano raggiungerla.

Ad esempio, puoi creare e progettare pagine di destinazione per indirizzare gli utenti a informazioni online. La pagina potrebbe includere un modulo in cui gli utenti possono dare il consenso o rinunciare alla ricezione delle comunicazioni. Oppure potrebbe essere l&#39;opportunità di abbonarsi a una comunicazione ricorrente, ad esempio a una newsletter.

## Accedere e gestire le pagine di destinazione {#access-manage-landing-pages}

Per accedere alle pagine di destinazione in [!DNL Marketo Optimizer], vai alla navigazione a sinistra ed espandi **[!UICONTROL Gestione contenuto]**. Quindi selezionare **[!UICONTROL Pagine di destinazione]**. Questa azione visualizza un elenco di tutte le pagine di destinazione create nell’istanza.

![Accedi alla libreria delle pagine di destinazione](./assets/landing-pages-list.png){width="800" zoomable="yes"}

L&#39;elenco è ordinato in base alla colonna _[!UICONTROL Modificato]_, con gli elementi aggiornati più di recente nella parte superiore. Fai clic sul titolo della colonna per passare da crescente a decrescente.

### Filtrare l’elenco delle pagine di destinazione {#filter-list}

Per cercare una pagina di destinazione per nome, immetti una stringa di testo nella barra di ricerca per trovare una corrispondenza. Fai clic sull&#39;icona _Filtro_ ( ![Mostra o nascondi icona filtri](../assets/do-not-localize/icon-filter.svg) ) per visualizzare le opzioni di filtro disponibili e modificare le impostazioni per filtrare gli elementi visualizzati in base ai criteri specificati.

![Filtra le pagine di destinazione visualizzate](./assets/landing-pages-list-filtered.png){width="800" zoomable="yes"}

<!-- 
This is going away? ### Customize the column display

Customize the columns that you want to display in the table by clicking the _Customize table_ icon ( ![Customize table icon](../assets/do-not-localize/icon-column-settings.svg) ) at the top right. 

In the dialog, select the columns to display and click **[!UICONTROL Apply]**.

![Select the columns that you want to display](./assets/landing-pages-customize-table-dialog.png){width="300"} 
-->

### Stato e ciclo di vita della pagina di destinazione {#landing-page-status}

Lo stato della pagina di destinazione determina la disponibilità del collegamento nei contenuti e-mail e SMS e le modifiche che puoi apportare.

| Stato | Descrizione |
| -------------------- | ----------- |
| Bozza | Quando crei una pagina di destinazione, questa si trova nello stato Bozza. Rimane in questo stato mentre definisci o modifichi il contenuto visivo e fino a quando non lo pubblichi come pagina in hosting. Azioni disponibili:<br/><ul><li>Modifica nome o descrizione</li><li>Modifica URL collegamento</li><li>Modifica nello spazio di progettazione visiva</li><li>Pubblica</li><li>Duplica</li><li>Elimina</li></ul> |
| Pubblicato | Quando pubblichi una pagina di destinazione, questa è ospitata nell&#39;istanza [!DNL Marketo Optimizer] e diventa disponibile per il collegamento in un contenuto di un messaggio e-mail o SMS. Azioni disponibili:<br/><ul><li>Modifica nome o descrizione</li><li>Modifica URL collegamento</li><li>Aggiungere un collegamento nel contenuto di un messaggio e-mail o SMS</li><li>Crea versione bozza</li><li>Duplica</li><li>Elimina</li></ul> |
| Pubblicato con bozza | Quando crei una bozza da una pagina di destinazione pubblicata, la versione pubblicata rimane e il contenuto della bozza può essere modificato nello spazio di progettazione visiva. Se pubblichi la bozza della versione, questa sostituisce la versione pubblicata corrente e il contenuto viene aggiornato nella pagina ospitata. Azioni disponibili:<br/><ul><li>Modifica nome o descrizione</li><li>Modifica URL collegamento</li><li>Aggiungere un collegamento nel contenuto di un messaggio e-mail o SMS</li><li>Modifica versione bozza in Visual Design Space</li><li>Pubblica versione bozza</li><li>Duplica</li><li>Elimina (elimina entrambe le versioni)</li><li>Elimina bozza (torna allo stato pubblicato)</li></ul> |

![Ciclo di vita stato pagina di destinazione](assets/status-lifecycle-diagram.png){zoomable="yes"}

## Modificare una pagina di destinazione {#edit-landing-page}

Le modifiche apportate a una pagina di destinazione dipendono dal suo stato corrente:

* Quando una pagina di destinazione è in stato **_Bozza_**, puoi modificarne i dettagli, l&#39;URL e il contenuto visivo.
* Quando una pagina di destinazione si trova nello stato **_Pubblicato_**, puoi modificare la descrizione, ma non il nome. Per modificare il contenuto visivo, è necessario creare una versione bozza della pagina.
* Quando una pagina di destinazione è in stato **_Pubblicato con bozza_**, la modifica dei dettagli è limitata alla descrizione. Puoi anche modificare il contenuto visivo della versione bozza.

>[!BEGINTABS]

>[!TAB Bozza]

1. Dalla pagina di elenco _[!UICONTROL Pagine di destinazione]_, fai clic sul nome della pagina di destinazione per aprirla.

   Viene visualizzata un’anteprima del contenuto visivo, con i dettagli della pagina di destinazione a destra.

1. Modifica uno dei dettagli, ad esempio nome e descrizione.

   ![Dettagli per la pagina di destinazione con stato Bozza](assets/landing-page-draft-details.png){width="700" zoomable="yes"}

1. Per apportare modifiche al contenuto nello spazio di progettazione visivo, fare clic su **[!UICONTROL Modifica pagina di destinazione]**.

   Utilizza gli strumenti di progettazione visiva secondo necessità:

   * [Aggiungere struttura e contenuto](./landing-page-design.md#structure-content-landing-page)
   * [Aggiungere risorse](./landing-page-design.md#add-assets)
   * [Spostarsi tra livelli, impostazioni e stili](./landing-page-design.md#navigate-layers-settings-styles)
   * [Personalizzazione dei contenuti](./landing-page-design.md#personalize-content)
   * [Modifica tracciamento URL collegato](./landing-page-design.md#linked-url-tracking)

1. Fai clic su **[!UICONTROL Salva]** o **[!UICONTROL Salva e chiudi]** per tornare ai dettagli della pagina di destinazione.

1. Quando la pagina soddisfa i criteri e desideri renderla disponibile per la visualizzazione, fai clic su **[!UICONTROL Pubblica]**.

>[!TAB Pubblicato]

1. Dalla pagina di elenco _[!UICONTROL Pagine di destinazione]_, fare clic sul nome della pagina per aprirla.

   Viene visualizzata un’anteprima del contenuto visivo, con i dettagli della pagina di destinazione a destra.

1. Se necessario, modifica la descrizione.

   Per una pagina di destinazione pubblicata, tutti gli altri dettagli non possono essere modificati.

1. Se desideri aggiornare il contenuto, fai clic su **[!UICONTROL Modifica pagina di destinazione]** a destra.

   Fare clic su **[!UICONTROL Crea bozza versione]** nella finestra di dialogo per aprire la bozza versione nello spazio di progettazione visivo.

   Utilizza gli strumenti di progettazione visiva secondo necessità:

   * [Aggiungere struttura e contenuto](./landing-page-design.md#structure-content-landing-page)
   * [Aggiungere risorse](./landing-page-design.md#add-assets)
   * [Spostarsi tra livelli, impostazioni e stili](./landing-page-design.md#navigate-layers-settings-styles)
   * [Personalizzazione dei contenuti](./landing-page-design.md#personalize-content)
   * [Modifica tracciamento URL collegato](./landing-page-design.md#linked-url-tracking)

1. Fai clic su **[!UICONTROL Salva]** o **[!UICONTROL Salva e chiudi]** per tornare ai dettagli della pagina di destinazione.

1. Quando la bozza della pagina di destinazione soddisfa i criteri e desideri rendere le modifiche disponibili nella pagina pubblicata, fai clic su **[!UICONTROL Pubblica]**.

   Quando pubblichi la versione bozza, questa sostituisce la versione pubblicata corrente e il contenuto viene aggiornato per l’URL della pagina.

>[!TAB Pubblicato con bozza]

Quando apri la pagina di destinazione, viene visualizzata la versione bozza. Le schede nella parte superiore dello spazio di anteprima consentono di alternare la visualizzazione tra la versione pubblicata e quella bozza. Le bozze delle azioni e dei dettagli sono visualizzate a destra.

![Anteprima e dettagli della versione bozza della pagina di destinazione](assets/landing-page-published-draft-details.png){width="700" zoomable="yes"}

_Per aggiornare il contenuto :_

1. Fai clic su **[!UICONTROL Modifica pagina di destinazione]** in alto a destra. Utilizza gli strumenti di progettazione visiva secondo necessità:

   * [Aggiungere struttura e contenuto](./landing-page-design.md#structure-content-landing-page)
   * [Aggiungere risorse](./landing-page-design.md#add-assets)
   * [Spostarsi tra livelli, impostazioni e stili](./landing-page-design.md#navigate-layers-settings-styles)
   * [Personalizzazione dei contenuti](./landing-page-design.md#personalize-content)
   * [Modifica tracciamento URL collegato](./landing-page-design.md#linked-url-tracking)

1. Fai clic su **[!UICONTROL Salva]** o **[!UICONTROL Salva e chiudi]** per tornare ai dettagli della pagina di destinazione.

1. Quando la pagina della bozza soddisfa i criteri e desideri rendere disponibili le modifiche, fai clic su **[!UICONTROL Pubblica]**.

   Quando pubblichi la versione bozza, questa sostituisce la versione pubblicata corrente e il contenuto viene aggiornato nella pagina ospitata.

>[!ENDTABS]

## Duplicare una pagina di destinazione {#duplicate-landing-page}

Puoi duplicare una pagina di destinazione utilizzando uno dei seguenti metodi:

* Dalla pagina dell&#39;elenco _[!UICONTROL Pagina di destinazione]_, fare clic sull&#39;icona _Altro_ (**...**) accanto al nome della pagina di destinazione e scegli **[!UICONTROL Duplica]**.
* Nella parte superiore destra della pagina dei dettagli della pagina di destinazione, fare clic su **[!UICONTROL ... Altro]** e scegli **[!UICONTROL Duplicato]**.

![Duplica la pagina di destinazione](assets/landing-page-details-duplicate-delete.png){width="600" zoomable="yes"}

Nella finestra di dialogo, inserisci un nome utile (univoco) e una descrizione (facoltativa). Fai clic su **[!UICONTROL Duplica]** per completare l&#39;azione.

![Immettere un nome e una descrizione per la pagina di destinazione duplicata](assets/landing-page-duplicate-dialog.png){width="350"}

La pagina duplicata (nuova) viene quindi visualizzata nell&#39;elenco _Pagine di destinazione_.

## Eliminare una pagina di destinazione {#delete-landing-page}

Puoi eliminare una pagina di destinazione utilizzando uno dei seguenti metodi:

* Dalla pagina dell&#39;elenco _[!UICONTROL Pagina di destinazione]_, fare clic sull&#39;icona _Altro_ (**...**) accanto al nome della pagina di destinazione e scegliere **[!UICONTROL Elimina]**.
* Nella parte superiore destra della pagina dei dettagli della pagina di destinazione, fare clic su **[!UICONTROL ... Altro]** e scegliere **[!UICONTROL Elimina]**.

Questa azione apre una finestra di dialogo di conferma. È possibile interrompere il processo facendo clic su **[!UICONTROL Annulla]** oppure su **[!UICONTROL Elimina]** per confermare l&#39;eliminazione.

![Finestra di dialogo Elimina pagina di destinazione](assets/landing-page-delete-dialog.png){width="400"}

## Collegamento a una pagina di destinazione {#link-to-landing-page}

In qualità di addetto al marketing o creativo che produce contenuti per e-mail, frammenti e pagine, puoi incorporare collegamenti alle pagine di destinazione pubblicate (live) create nell&#39;istanza [!DNL Marketo Optimizer].

1. Quando lavori nello spazio di progettazione visiva per un frammento, un’e-mail, una pagina di destinazione o un modello, seleziona una parte di testo, un componente pulsante o un componente immagine per il collegamento.

   Le opzioni **[!UICONTROL Collegamento]** sono visualizzate nel pannello di destra.

1. Per l&#39;opzione **[!UICONTROL Tipo]**, scegliere **[!UICONTROL Pagina di destinazione]**.

   ![Opzioni di collegamento per una pagina di destinazione](assets/content-design-link-settings.png){width="700" zoomable="yes"}

1. Per l&#39;opzione **[!UICONTROL Pagina di destinazione]**, fare clic sull&#39;icona _Seleziona pagina_ ( ![Mostra icona collegamenti](../assets/do-not-localize/icon-landing-page-select.svg) ).

1. Nella finestra di dialogo Seleziona pagina di destinazione, imposta **[!UICONTROL Origine pagina di destinazione]** come **[!UICONTROL Journey Optimizer B2B edition]**, seleziona la casella di controllo per la pagina di destinazione dall&#39;elenco delle pagine pubblicate e fai clic su **[!UICONTROL Seleziona]**.

   ![Opzioni di collegamento per una pagina di destinazione](assets/content-design-link-landing-page-select.png){width="600" zoomable="yes"}

1. Per l&#39;opzione **[!UICONTROL Target]**, scegliere il comportamento della destinazione di collegamento:

   * **[!UICONTROL Nessuno]** - Apre il collegamento utilizzando il comportamento predefinito del browser.
   * **[!UICONTROL Vuoto]** - Apre il collegamento in una nuova finestra o scheda.
   * **[!UICONTROL Autonomo]** - Apre il collegamento nello stesso frame.
   * **[!UICONTROL Elemento padre]** - Apre il collegamento nel frame padre.
   * **[!UICONTROL Top]** - Apre il collegamento nel corpo completo della finestra.

1. (Solo collegamento di testo) Per sottolineare il testo collegato, selezionare la casella di controllo **[!UICONTROL Sottolinea collegamento]**.

   Puoi impostare stili aggiuntivi per il testo del collegamento, incluso il colore del collegamento, selezionando la scheda **[!UICONTROL Stili]** nel pannello di destra.
