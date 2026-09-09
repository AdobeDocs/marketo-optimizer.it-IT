---
title: Creare modelli e-mail
description: 'Scopri come creare modelli e-mail in Marketo Optimizer: crea nuovi modelli, salva un’e-mail da un percorso come modello o converti un’immagine di progettazione in un modello e-mail.'
TQID: 'https://experienceleague.adobe.com/Hag-o6Hu-82rqnWHnDBgPD-dKApy5JGsPMD5cGFOCfA'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2: id: 8881ff95-1653-5fea-82af-ce1549c0d99d
topic_v2: id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: cc72dcf1-72e1-48cc-b434-e7c27d62d67cid: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 873
ht-degree: 1%

---


# Creare modelli e-mail

È possibile creare un modello di posta elettronica in [!DNL Adobe Marketo Optimizer] in tre modi:

* **Crea un nuovo modello** — Crea un modello nella libreria di modelli utilizzando lo spazio di progettazione e-mail visiva.
* **Salva da e-mail di percorso** — Salva un messaggio e-mail creato in un percorso come modello riutilizzabile.
* **Converti un&#39;immagine** - Carica un&#39;immagine di progettazione e utilizza l&#39;intelligenza artificiale generativa per convertirla in un modello di e-mail modificabile.

## Crea un nuovo modello {#build-new}

1. Nel menu di navigazione a sinistra, espandi **[!UICONTROL Gestione contenuto]** e seleziona **[!UICONTROL Modelli]**.
1. Fare clic su **[!UICONTROL Crea modello]**.
1. Immettere un **[!UICONTROL nome modello]** e una **[!UICONTROL descrizione]** facoltativa.
1. Imposta il **[!UICONTROL canale]** (tipo) per il modello.

   >[!NOTE]
   >
   >In questa versione di Beta, sono supportati solo i modelli e-mail.

   <!-- 1. Optionally add **[!UICONTROL Tags]** to categorize the template. -->

1. Fai clic su **[!UICONTROL Crea]** per aprire lo spazio di progettazione delle e-mail.

1. Fai clic su **[!UICONTROL Modifica corpo dell&#39;e-mail]** per accedere allo spazio di progettazione del contenuto.

   Per informazioni dettagliate sulla progettazione del contenuto, consulta [Authoring di e-mail](email-authoring.md).

1. Facoltativamente, abilita **[!UICONTROL Governance]** e configura [il blocco del contenuto](template-content-governance.md) per limitare le parti che gli autori dei modelli possono modificare quando applicano il modello.

1. Fai clic su **[!UICONTROL Salva]**.

## Salvare un’e-mail come modello {#save-as-template}

Quando apri il contenuto dell’e-mail che desideri riutilizzare, salvalo direttamente nella libreria dei modelli dalla pagina del contenuto dell’e-mail.

1. Fai clic su **[!UICONTROL Modello di contenuto]** nella parte superiore della pagina.
1. Selezionare **[!UICONTROL Salva come modello di contenuto]**.
1. Immettere un **[!UICONTROL Nome]** e una **[!UICONTROL Descrizione]** facoltativa.
1. È possibile aggiungere **[!UICONTROL Tag]**.
1. Fai clic su **[!UICONTROL Crea]**.

L’e-mail originale del percorso non subisce modifiche. Il modello salvato è disponibile nella libreria di modelli per tutti gli utenti nella sandbox. Puoi aggiornare il modello creato per ottimizzare il riutilizzo:

* Modifica il testo e aggiungi [token di personalizzazione](email-authoring.md#personalize-content).
* Aggiornare o sostituire immagini e aggiungere collegamenti.
* Configura [blocco contenuto](template-content-governance.md).

## Convertire un’immagine in un modello {#image-to-template}

[!DNL Adobe Marketo Optimizer] può convertire un&#39;immagine statica, ad esempio un modello di Figma o Photoshop, in un modello di e-mail modificabile utilizzando l&#39;intelligenza artificiale generativa. Questo elimina la necessità di ricreare manualmente i layout dai file di progettazione ed è ideale per la migrazione delle progettazioni di e-mail esistenti da altre piattaforme. Questa funzione è disponibile solo per i modelli di contenuto e-mail.

>[!BEGINSHADEBOX]

### Prerequisiti

Prima di iniziare:

* La tua organizzazione deve aver firmato l’addendum all’intelligenza artificiale generativa con Adobe.
* È necessario disporre dell&#39;autorizzazione **[!UICONTROL Genera contenuto]** oltre a **[!UICONTROL Gestisci modelli di contenuto]**.
* Il file di immagine deve soddisfare le seguenti specifiche:
  * Formato: JPEG (.jpg, .jpeg) o PNG (.png)
  * Dimensione massima file: 10 MB
  * Larghezza consigliata: 600-800 pixel
  * Immagine chiara e di alta qualità con testo leggibile ed elementi visivi distinti

>[!IMPORTANT]
>
>L’immagine non deve contenere dati personali (PII, personally identifiable information) né dati sensibili.

>[!ENDSHADEBOX]

### Creare il modello

1. Nel menu di navigazione a sinistra, espandi **[!UICONTROL Gestione contenuto]** e seleziona **[!UICONTROL Modelli]**.
1. Fare clic su **[!UICONTROL Crea modello]**.
1. Immettere un **[!UICONTROL nome modello]** e una **[!UICONTROL descrizione]** facoltativa.
1. Imposta **[!UICONTROL Canale]** su E-mail.

   <!--  Optionally add **[!UICONTROL Tags]** to categorize the template. -->

1. Fai clic su **[!UICONTROL Crea]**.

### Generare il contenuto del modello

1. Nella sezione **[!UICONTROL Converti immagine in modello]**:

   * Se necessario, seleziona un **[!UICONTROL tema marchio]** per applicare i colori, i font e la spaziatura del tuo marchio all&#39;output generato.
   * Selezionare la casella di controllo Conferma per confermare che l&#39;immagine non contiene dati personali o altri dati sensibili.
   * Fai clic su **[!UICONTROL Carica immagine]** e seleziona il file di immagine.

   >[!CAUTION]
   >
   >Il caricamento di un’immagine elimina qualsiasi contenuto presente nell’e-mail e lo sostituisce con il modello generato.

1. Se richiesto, rivedi e accetta le linee guida per l’utente di Adobe Generative AI.

1. Fai clic su **[!UICONTROL Apri]** per avviare il processo di conversione.

   Generalmente la conversione viene completata entro circa cinque minuti. Immagini complesse o di grandi dimensioni possono richiedere fino a dieci minuti. La conversione viene eseguita in background: potete spostarvi e la bozza del modello viene salvata automaticamente al termine della conversione.

1. Aggiorna la pagina per visualizzare il modello completato.

   >[!NOTE]
   >
   >Il risultato non viene visualizzato automaticamente. Aggiorna la pagina o torna alla libreria dei modelli per visualizzare il modello completato.

1. Facoltativamente, utilizza la sezione **[!UICONTROL Immagine per modellare il feedback del convertitore]** per condividere i suggerimenti con Adobe.

1. Fai clic su **[!UICONTROL Modifica corpo dell&#39;e-mail]** per aprire il modello convertito nello spazio di progettazione e-mail per la modifica.

1. Fai clic su **[!UICONTROL Salva]**.

### Modificare il contenuto convertito

Il contenuto del modello convertito viene aperto nello spazio di progettazione come modello e-mail completamente modificabile. Utilizza gli strumenti di progettazione dei contenuti standard per:

* Modifica il testo e aggiungi [token di personalizzazione](email-authoring.md#personalize-content).
* Aggiornare o sostituire immagini e aggiungere collegamenti.
* Regola colori, tipi di carattere e spaziatura.
* Aggiungere, rimuovere o ridisporre i componenti di contenuto.
* Abilita la governance e configura [il blocco del contenuto](template-content-governance.md).

>[!IMPORTANT]
>
>L’intelligenza artificiale generativa produce un HTML statico basato sull’immagine visiva. Controlla tutto il testo per verificarne la precisione e aggiungi manualmente personalizzazione, contenuto dinamico e tracciamento dopo la conversione.

Al termine della conversione, il modello convertito viene salvato automaticamente nella libreria di modelli.

### Suggerimenti per ottenere risultati ottimali

Utilizza le seguenti linee guida per ottenere risultati migliori dalla conversione da immagine a modello:

**Prima della conversione:**

* Utilizza la versione con la massima risoluzione del file di progettazione.
* Progetta con larghezze e-mail standard (600-800 pixel) e includi il layout completo, dall’intestazione al piè di pagina, in una singola immagine.
* Assicuratevi di ottenere un contrasto sufficiente tra testo e sfondi e di utilizzare dimensioni dei caratteri leggibili.

**Progettazione per una conversione accurata:**

* Utilizzare layout semplici e ben strutturati con una netta separazione tra le sezioni.
* Segui i pattern e-mail standard: intestazione, corpo, inviti all’azione, piè di pagina, anziché progetti complessi a più livelli.
* Mantieni distinti gli elementi visivi in modo che l’intelligenza artificiale possa identificare correttamente i limiti strutturali.

**Dopo la conversione:**

* Prima di utilizzare il modello in un percorso, verifica il rendering tra client e dispositivi e-mail.
* Verifica l’allineamento con i colori del marchio, i font e le linee guida di stile.
* Rivedi e migliora l’accessibilità, incluso il testo alternativo dell’immagine.
