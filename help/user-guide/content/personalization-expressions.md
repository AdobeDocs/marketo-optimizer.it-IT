---
title: Editor Personalization
description: Scopri come utilizzare l’editor di personalizzazione in Marketo Optimizer per selezionare, disporre, personalizzare e convalidare i token di attributi di profilo nelle e-mail, nei messaggi WhatsApp, nelle pagine di destinazione e nei campi URL.
feature: Content Design Tools
role: User
TQID: 'https://experienceleague.adobe.com/5aPDp4kMpQo7LtE6CEUQWf2IbyeSMoW6iN5ZR-f-kLI'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 1002
ht-degree: 12%

---

# Editor di personalizzazione

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_personalization_editor"
>title="Informazioni sull’editor di personalizzazione"
>abstract="L’editor di personalizzazione consente di selezionare, disporre, personalizzare e convalidare gli attributi del profilo per creare contenuti personalizzati."

L&#39;editor di personalizzazione è il fulcro della personalizzazione in [!DNL Marketo Optimizer]. Utilizzalo ovunque tu abbia bisogno di contenuti dinamici: nelle e-mail, nei messaggi WhatsApp, nelle pagine di destinazione e nei campi URL.

Nell’interfaccia dell’editor di personalizzazione puoi selezionare, disporre, personalizzare e convalidare gli attributi del profilo per creare contenuti personalizzati.

![Editor di espressioni di personalizzazione](./assets/personalization-editor.png){width="700" zoomable="yes"}

>[!NOTE]
>
>In questa versione di Beta, nell’editor di personalizzazione sono disponibili solo gli attributi del profilo. La personalizzazione a livello di account e i dati oggetto personalizzato non sono disponibili. Vedi [Limitazioni correnti](../marketing/email-channel.md#limitations).

Puoi aggiungere la personalizzazione in qualsiasi campo con l&#39;icona _Personalizza_ ( ![Icona Personalizza](../assets/do-not-localize/icon-personalize.svg) ). Per ulteriori informazioni, espandi le sezioni seguenti.

+++E-mail e messaggi WhatsApp

In [messaggi e-mail](./email-authoring.md#personalize-content) e [messaggi WhatsApp](./whatsapp-authoring.md#personalize-message-content), è possibile aggiungere la personalizzazione in posizioni diverse, ad esempio il campo **[!UICONTROL Oggetto]** in un messaggio e-mail o parametri dinamici in un modello WhatsApp approvato.

Può essere aggiunto anche in altre sezioni del contenuto, tra cui il testo del corpo dell’e-mail, le preintestazioni e gli URL dei pulsanti.

+++

+++Spazio per la progettazione dei contenuti

Quando modifichi il contenuto visivo, puoi aggiungere la personalizzazione alla maggior parte degli elementi di testo utilizzando l’icona nella barra degli strumenti contestuale.

<!-- ![](assets/perso_insert.png) -->

+++

+++URL

[!DNL Marketo Optimizer] ti consente inoltre di personalizzare **URL** nei messaggi. Gli URL personalizzati indirizzano i destinatari verso pagine specifiche di un sito web o verso un microsito personalizzato, a seconda degli attributi del profilo.

<!-- ![](assets/perso-url.png){width="50%"} -->

>[!NOTE]
>
>La personalizzazione URL è disponibile per i seguenti tipi di collegamenti: **Collegamento esterno**, **Collegamento per l&#39;annullamento dell&#39;abbonamento** e **Rinuncia**.

+++

+++Configurazione e-mail

Durante la creazione di una [configurazione del canale e-mail](../admin/email-channel-configuration.md), puoi definire valori personalizzati per sottodomini, intestazioni e parametri di tracciamento URL.

+++

## Aggiungere personalizzazione {#add}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_perso_editor_autocomplete"
>title="Completamento automatico"
>abstract="L’attivazione di questa opzione consente al sistema di suggerire e completare automaticamente il codice durante la digitazione. Questa funzione è disponibile solo per i formati HTML e Testo e supporta gli attributi di profilo. Se viene disabilitata tramite il pulsante di attivazione, il completamento automatico del codice HTML nativo verrà eseguito dall’editor."

Nell’area di lavoro centrale puoi creare la sintassi di personalizzazione. Per utilizzare un attributo per personalizzare il messaggio, individuarlo nel riquadro di spostamento a sinistra e fare clic sul pulsante `+` per aggiungerlo all&#39;espressione.

<!-- ![](assets/personalization-add-attribute.png) -->

Il menu con i puntini di sospensione accanto all&#39;icona `+` consente di ottenere ulteriori dettagli per ciascun attributo e di aggiungere gli attributi utilizzati più di frequente ai preferiti. Gli attributi aggiunti ai preferiti sono accessibili dal menu **[!UICONTROL Preferiti]** nel riquadro di spostamento.

>[!NOTE]
>
>Per impostazione predefinita, nel riquadro degli attributi vengono visualizzati solo gli attributi compilati. Per visualizzare tutti gli attributi, selezionare il pulsante **[!UICONTROL Impostazioni]** nel riquadro degli attributi e disattivare l&#39;opzione **[!UICONTROL Mostra solo attributi popolati]**.

Inoltre, puoi definire il testo di fallback predefinito che verrà visualizzato se un attributo di profilo di tipo stringa è vuoto. A tale scopo, fare clic sul pulsante con i puntini di sospensione accanto all&#39;attributo e selezionare **[!UICONTROL Inserisci con testo di fallback]**. Scrivere il testo da visualizzare per impostazione predefinita se il valore dell&#39;attributo è vuoto per un profilo, quindi fare clic su **[!UICONTROL Aggiungi]**.

<!-- ![](assets/attribute-details.png) -->

Ad esempio, è possibile salutare ogni destinatario per nome utilizzando `{{profile.firstName}}` con un fallback quando manca il valore: `{{profile.firstName | default: "there"}}`.

## Opzioni per la modifica delle espressioni {#options}

L’area di lavoro centrale fornisce vari strumenti per aiutarti a scrivere la tua espressione di personalizzazione.

<!-- ![](assets/perso-workspace.png) -->

Le opzioni disponibili sono:

1. **[!UICONTROL Trova]** / **[!UICONTROL Trova e sostituisci]**: cerca nell&#39;espressione e sostituisci automaticamente parti di codice.
1. **[!UICONTROL Annulla]** / **[!UICONTROL Ripristina]**: annulla/ripristina l&#39;ultima operazione.
1. **[!UICONTROL Completamento automatico]**: suggerisce e completa automaticamente il codice durante la digitazione. Questa funzione è disponibile solo per i formati HTML e Testo e supporta gli attributi di profilo. Se viene disabilitata tramite il pulsante di attivazione, il completamento automatico del codice HTML nativo verrà eseguito dall’editor.

   <!-- ![](assets/perso-complete.png){width="70%" align="center" zoomable="yes"} -->

1. **[!UICONTROL HTML]** / **[!UICONTROL JSON]** / **[!UICONTROL Testo]**: identifica il formato del codice. Questo consente al sistema di adattare la convalida e la funzione di completamento automatico in base alla lingua selezionata.
1. **[!UICONTROL Convalida]**: verifica la sintassi dell&#39;espressione.
1. **[!UICONTROL Dimensione font]**: regola la dimensione font per i contenuti all&#39;interno dell&#39;editor per migliorarne la leggibilità.
1. **[!UICONTROL Parola a capo]**: attiva o disattiva il ritorno a capo automatico, consentendo la visualizzazione di espressioni lunghe su una singola riga o racchiuse nell&#39;editor. Le opzioni includono:
   * **Disattivato** (impostazione predefinita) - Nessun ritorno a capo automatico. Le linee lunghe si estendono oltre la vista dell’editor e richiedono uno scorrimento orizzontale.
   * **Il** - Dispone le righe alla larghezza dell&#39;editor.
   * **Colonna a capo automatico** - Dispone le righe quando una riga raggiunge gli 80 caratteri.
   * **Limitato** - Dispone le righe alla larghezza dell&#39;editor o a 80 caratteri, a seconda di quale dei due valori è più basso.
1. **[!UICONTROL Pillole]**: visualizza gli attributi come &quot;pillole&quot; compatte per migliorare la leggibilità nascondendo i percorsi degli attributi lunghi. Fare clic su un attributo per visualizzarne il percorso completo.

   >[!NOTE]
   >
   >Questa opzione è disponibile solo per gli attributi del profilo.

Nel riquadro di navigazione sono disponibili funzioni aggiuntive per aiutarti a creare la tua espressione di personalizzazione.

<!-- ![](assets/perso-features.png) -->

* **[!UICONTROL Funzioni helper]** - Le funzioni helper consentono di eseguire operazioni sui dati, ad esempio calcoli, formattazione o conversioni di dati, condizioni e di manipolarli nel contesto della personalizzazione.

* **[!UICONTROL Preferiti]** - Gli attributi aggiunti ai preferiti vengono visualizzati in questo elenco. Questo consente di accedere rapidamente agli elementi utilizzati più di frequente. Per aggiungere un attributo ai preferiti, fai clic sul menu con i puntini di sospensione e scegli **[!UICONTROL Aggiungi ai preferiti]**.

Il Collaboratore può generare espressioni Handlebars da descrizioni in linguaggio semplice, spiegare espressioni esistenti e identificare potenziali problemi.

Quando l&#39;espressione di personalizzazione è pronta, fare clic su **[!UICONTROL Conferma]** o **[!UICONTROL Inserisci]** per aggiungerla al contenuto.

## Meccanismi di convalida {#validation-mechanisms}

La convalida dell&#39;espressione viene eseguita automaticamente quando si fa clic su **[!UICONTROL Conferma]** o **[!UICONTROL Inserisci]** per chiudere l&#39;editor. Puoi anche fare clic su **[!UICONTROL Convalida]** per controllare la sintassi di personalizzazione prima di chiudere.

Per gli avvisi sul contenuto che bloccano l&#39;attivazione del percorso, vedere [Convalida del contenuto delle e-mail](./email-authoring.md#validation).

Espandi la sezione seguente per visualizzare gli errori più comuni che possono verificarsi durante la convalida della personalizzazione.

+++Errori comuni

* **Percorso &quot;XYZ&quot; non trovato**

Questo errore si verifica quando si fa riferimento a un campo non definito nello schema.

In questo caso **firstName1** non è definito come attributo nello schema del profilo:

```handlebars
{{profile.firstName1}}
```

* **Tipo non corrispondente per la variabile &quot;XYZ&quot;. Previsto array. Trovata stringa.**

Questo errore si verifica quando si tenta di eseguire l’iterazione su una stringa anziché su un array.

In questo caso **jobTitle** è una stringa e non un array:

```handlebars
{{#each profile.jobTitle as |item|}}
  {{item}}
{{/each}}
```

* **Sintassi Handlebars non valida. Trovato`'[XYZ}}'`**

Questo errore si verifica quando viene utilizzata una sintassi Handlebars non valida.

```handlebars
{{[profile.firstName}}
```

+++
