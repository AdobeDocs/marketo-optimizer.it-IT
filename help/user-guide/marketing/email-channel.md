---
title: Aggiungi e-mail a Percorsi
description: Aggiungi nodi di azione e-mail a percorsi di persone e crea nuove e-mail per comunicazioni mirate in Marketo Optimizer.
feature: Email Authoring, Person Journeys
role: User
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '1048'
ht-degree: 7%

---

# Aggiungi e-mail a percorsi

[!DNL Adobe Marketo Optimizer] offre agli esperti di marketing B2B un&#39;esperienza moderna di creazione e consegna di e-mail di livello enterprise.

>[!NOTE]
>
>Se invii un&#39;e-mail per la prima volta, assicurati che [recapito e-mail](../start/email-deliverability.md) e il [canale e-mail](../admin/email-channel-configuration.md) necessari siano configurati.

<!-- 
* **Email channel configurations** - Manage the sender identity, reply behavior, marketing vs. transactional message types, and tracking.
* **Email deliverability controls** - Set up your email deliverability channel, including subdomain delegation (Fully Delegated and CNAME methods), DMARC, SPF/DKIM auto-configuration, and shared IP pool support.
* **Send Email action** - From a journey, add a _Send email_ action node, including personalization using profile attributes (Handlebars syntax).
* **Visual drag-and-drop email design tools** -  Design your email content with structures, content components, themes, dark-mode support, and reusable visual fragments.
* **Marketo Design Studio assets** — Choose images and assets from a one-time copy of your Marketo Engage asset library directly inside the email canvas.
* **Reusable templates and fragments** — Save common headers, footers, CTAs, and full email layouts and reuse them across journeys.
* **Role-Based Access Control (RBAC)** — Apply granular permissions for creating, editing, approving, and sending email. 
-->

## Limitazioni attuali {#limitations}

* **I profili di test, Simula contenuto e Invia bozza** non sono disponibili in questa versione. Il rendering di Litmus e i rapporti di posta indesiderata basati su SpamAssassin sono nella roadmap di GA.
* **La personalizzazione a livello di account e i dati oggetto personalizzato** non sono disponibili in questa versione. Utilizza gli attributi del profilo.
* **Migrazione automatizzata Velocity-to-Handlebars** dei modelli Marketo Engage esistenti viene spedito in GA.
* **Commenti e collaborazione sulle e-mail** (commenti in linea, @mentions, flusso di lavoro di richiesta-revisione) inviati in una versione futura.
* Le integrazioni **AEM Assets, Frammenti di contenuto AEM e Adobe Express** sono incluse nella roadmap di _Fast Follow-up_.

## Concetti chiave {#key-concepts}

Prima di creare e-mail per percorsi di persone e contenuti e-mail, esamina i seguenti concetti:

| Concetto | In [!DNL Adobe Marketo Optimizer] |
| ------- | ---------------------- |
| **_Spazio di progettazione e-mail_** | L’area di lavoro visiva e gli strumenti di progettazione utilizzati per comporre il contenuto delle e-mail. Include componenti di layout drag-and-drop, modelli, frammenti, temi e un editor di personalizzazione. |
| **_Modello_** | Layout e-mail riutilizzabile disponibile per la creazione di un nuovo messaggio e-mail. Può essere un modello di esempio integrato fornito da Adobe o un modello personalizzato creato dal team. |
| **_Frammento visivo_** | Blocco di contenuto riutilizzabile (ad esempio intestazione, piè di pagina, CTA, dichiarazione di non responsabilità legale) che può essere inserito in più e-mail. L’aggiornamento di un frammento propaga la modifica a ogni e-mail che lo utilizza. |
| **_Tema_** | Predefinito di stile riutilizzabile (colori, composizione tipografica, spaziatura, stili di pulsante) applicato a un messaggio e-mail. |
| **_Token Personalization_** | Un&#39;espressione Handlebars, ad esempio `{{profile.firstName}}`, è stata risolta in fase di invio utilizzando i dati del profilo di ogni destinatario. |
| **_Invia azione e-mail_** | Nodo di azione del percorso che utilizza una configurazione di canale e contenuti e-mail per inviare un messaggio e-mail. |

## Aggiungere un messaggio e-mail da un percorso

Per inviare e-mail da un percorso, [aggiungi un _Esegui un&#39;azione_ nodo](action-nodes.md#add-an-action-node) e configuralo per inviare e-mail.

1. Nell&#39;area di lavoro del percorso fare clic sull&#39;icona **+** e selezionare **[!UICONTROL Esegui un&#39;azione]**.

1. Nelle proprietà del nodo a destra, imposta l&#39;azione su **[!UICONTROL Invia e-mail]**.

   ![Azione - Invia e-mail](./assets/person-action-node-send-email.png){width="500"}

1. Scegli l’origine dell’e-mail:

   * **Crea/modifica e-mail** - Scegliere questa opzione per definire il contenuto dell&#39;e-mail, inclusi l&#39;oggetto, le informazioni sul mittente e il corpo dell&#39;e-mail nell&#39;area di progettazione e-mail.

   * **[!UICONTROL Utilizza un&#39;e-mail personalizzata con IA]** - (_Non disponibile per Beta_) Scegli questa opzione per perfezionare un&#39;e-mail generata con IA nell&#39;area di progettazione delle e-mail. Queste e-mail sono ottimizzate in modo che i client di posta in arrivo assistiti da AI inseriscano nelle offerte e nelle chiamate all’azione i riepiloghi e le risposte.

1. Fai clic su **[!UICONTROL Crea e-mail]**.

1. Nella finestra di dialogo _[!UICONTROL Crea e-mail]_, immetti un **[!UICONTROL Nome]** univoco (obbligatorio) e una **[!UICONTROL Descrizione]** (facoltativo).

   ![Crea finestra di dialogo e-mail](./assets/email-channel-create-email-dialog.png){width="400"}

1. Fai clic su **[!UICONTROL Crea]**.

Per l&#39;[ottimizzazione del tempo di invio](email-send-time-optimization.md) opzionale, configura il nodo dell&#39;azione di percorso dopo la creazione dell&#39;e-mail.

## Definire le proprietà e le azioni dell’e-mail {#define-email-properties}

La pagina e-mail viene visualizzata quando crei un messaggio e-mail per un nodo _[!UICONTROL Invia e-mail]_. Puoi accedere a questa pagina anche dopo aver creato l&#39;e-mail facendo clic su **[!UICONTROL Modifica e-mail]** nelle proprietà del nodo a destra.

1. (Facoltativo) Nella scheda **[!UICONTROL Proprietà]**, inserisci le informazioni descrittive che desideri acquisire per l&#39;e-mail.

1. Seleziona la scheda **[!UICONTROL Azioni]** e completa le impostazioni funzionali per l&#39;e-mail:

   * **[!UICONTROL E-mail]** - Seleziona o crea una **[!UICONTROL Configurazione del canale e-mail]** da utilizzare.

     Si tratta del set riutilizzabile di impostazioni di consegna e-mail che definisce l’identità del mittente, l’indirizzo di risposta, il sottodominio, il pool IP, il tipo di e-mail (marketing o transazionale) e il tracciamento. Fai clic sull&#39;icona _Visualizza_ per esaminare le impostazioni per la configurazione selezionata.

     Gli amministratori creano configurazioni in [Configurazione del canale e-mail](../admin/email-channel-configuration.md).

   * **[!UICONTROL Regole aziendali]** - (Facoltativo) Applica regole di limitazione o di inattività all&#39;azione e-mail selezionando un set di regole.

     Per ulteriori informazioni sulle regole business e su come definire e attivare set di regole per le comunicazioni di canale, vedere [_Regole business_](../admin/business-rules.md).

   * **[!UICONTROL Tracciamento azioni]** - Selezionare le caselle di controllo per le azioni di cui si desidera tenere traccia per l&#39;e-mail.

   ![Canale e-mail - Scheda Azioni](./assets/email-channel-actions-tab.png){width="600" zoomable="yes"}

1. Fare clic su **[!UICONTROL Modifica contenuto]** oppure selezionare la scheda **[!UICONTROL Contenuto]**.

1. Immettere il testo **[!UICONTROL Oggetto]** che si desidera visualizzare nel campo oggetto dell&#39;e-mail.

   Fai clic sull&#39;icona _Personalizza_ ( ![Icona Personalizza](../assets/do-not-localize/icon-personalize.svg) ) per utilizzare un token di personalizzazione nel campo.

1. (Facoltativo) Selezionare la casella di controllo **[!UICONTROL Ottimizza dimensioni HTML]** per ridurre le dimensioni del HTML di posta elettronica durante il processo di pubblicazione.

   Questo è utile per evitare che l’e-mail risulti tagliata in client come Gmail, in cui i messaggi di oltre 100 KB vengono troncati. Per ulteriori informazioni, vedere [_Ottimizzare le dimensioni del HTML e-mail_](#optimize-html-size).

1. Fai clic su **[!UICONTROL Modifica corpo dell&#39;e-mail]** per accedere agli strumenti di progettazione visiva e avviare [la creazione del contenuto](../content/email-authoring.md).

   In alternativa, puoi fare clic su **[!UICONTROL Editor di codice]** per scrivere il codice del tuo contenuto in HTML normale. Se disponi di HTML da riutilizzare per la progettazione delle e-mail, puoi copiarlo e incollarlo nell’editor.

### Controllare gli avvisi {#alerts}

[!DNL Adobe Marketo Optimizer] rileva problemi nell&#39;angolo in alto a destra della pagina e-mail. Risolvi tutti gli errori prima di attivare il percorso. Le avvertenze sono solo consigli.

**Errori** (impedisce l&#39;attivazione del percorso):

* Il nome del mittente è vuoto
* Riga oggetto mancante
* Il contenuto dell’e-mail è vuoto

**Avvisi** (consigli):

* Il collegamento di rinuncia non è presente nel corpo dell’e-mail
* La versione testo di HTML è vuota
* Sono stati rilevati collegamenti vuoti
* L&#39;e-mail supera i 100 K

## Ottimizzare la dimensione dell’HTML dell’e-mail {#optimize-html-size}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_email_minification"
>title="Riduci la dimensionie dell’HTML"
>abstract="Abilita questa opzione per comprimere l’HTML dell’e-mail durante la pubblicazione rimuovendo spazi vuoti, rientri e commenti non essenziali non necessari. Questo è utile per evitare che l’e-mail risulti tagliata in client come Gmail, in cui i messaggi di oltre 100 KB vengono troncati."

[!DNL Marketo Optimizer] consente di comprimere la versione di e-mail HTML durante il processo di pubblicazione rimuovendo spazi vuoti, rientri e commenti non essenziali. Le dimensioni ridotte di HTML consentono di:

* Evita **il ritaglio e-mail**. Alcuni client, ad esempio Gmail, troncano i messaggi di dimensioni superiori a ~100 KB, impedendo ai destinatari di visualizzare l&#39;intero contenuto.
* Migliora il **tempo di caricamento e-mail** nella casella in entrata del destinatario.
* Migliora il recapito messaggi **1} e riduci l&#39;utilizzo della larghezza di banda.**

Questa ottimizzazione non viene applicata automaticamente. Abilitarla nella scheda _[!UICONTROL Contenuto]_.

<!-- ![](assets/email-optimize-html-size.png) -->

>[!IMPORTANT]
>
> La riduzione della dimensione del HTML viene applicata solo al momento della pubblicazione.

L’ottimizzazione è sicura per il client e-mail:

* Mantiene i commenti condizionali di MSO/Outlook.
* Non altera il contenuto effettivo, le immagini o i video.

>[!NOTE]
>
>La riduzione delle dimensioni dell’e-mail dipende dalla struttura HTML originale dell’e-mail. Se il contenuto è già compatto o il payload dell’e-mail è molto grande, la riduzione può essere minima e non impedire completamente il clipping in tutti i casi.

<!-- 
Proof and simulate workflows are not available in this release. See [Current limitations](#limitations).

### Test HTML size optimization {#optimize-html-proof}

If you have enabled the [HTML size optimization](#optimize-html-size) option, you can evaluate its impact before publishing when sending proofs. Follow the following steps.

1. In the email design space, click the _Issues_ icon on the top right. If the rendered email size exceeds 100 KB, a message is displayed to warn you that this may cause truncation in some email clients.

1. Click **[!UICONTROL Simulate content]**.

1. To test the optimized version, click the **[!UICONTROL Send proof]** button and select the **[!UICONTROL Optimize HTML size]** option. This will send a proof with the reduced HTML size to your test recipients.

    >[!NOTE]
    >
    >This setting is independent from the email editor — the proof reflects what you select in the proof, regardless of whether the option is enabled or disabled in the email itself.

1. Select the test recipients and click **[!UICONTROL Send proof]**.

1. Back in the **[!UICONTROL Simulate]** screen, click the **[!UICONTROL View Proof]** button.

1. Click the _Information_ icon next to the status of the proof.

   The optimization details are displayed in a pop-up window, including the original HTML size, the optimized HTML size, and the size reduction percentage.
    
    Use this information to validate the optimized output and confirm the email stays within the recommended 100 KB threshold before publishing.

-->
