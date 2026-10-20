---
title: Configurazione Forms
description: Placeholder
TQID: 'https://experienceleague.adobe.com/7X5-67hfrjRjWbGjq9duLu7mVjgfCs7tpAQLV8u6YKE'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: a659ad61-de21-559d-a901-02e2fb329ff5
    internal-label: Administration
  - id: d4203578-d294-5145-b397-f26f4488a904
    internal-label: Channels
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: f65df8d5e83eca29ffaaabf51e7c80ed223d175a
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 15%
---
# Configurazioni Forms

Prima che gli addetti al marketing possano creare e pubblicare moduli da utilizzare nelle pagine di destinazione, un amministratore di prodotto deve creare uno o più predefiniti dedicati. Ogni predefinito definisce l’endpoint di connessione utilizzato per inviare i dati di invio del modulo e il set di dati utilizzato per memorizzare i dati acquisiti.

Quando i dati arrivano sull’endpoint di streaming, sono collegati alle informazioni del set di dati. Utilizzando le connessioni di origine/destinazione generate e il flusso di origine, i dati vengono quindi inviati al set di dati.

>[!BEGINSHADEBOX]

## Prerequisiti

Per utilizzare i moduli Web, è necessario che in Adobe Experience Platform siano definite una o più _**connessioni di streaming API HTTP**_. Verificare che ogni connessione che si desidera utilizzare soddisfi i seguenti requisiti:

* Il tipo di dati deve essere impostato su XDM (non su dati non elaborati)
* L&#39;autenticazione deve essere disabilitata (connessione non autenticata)

Per informazioni dettagliate sulla creazione di connessioni a origini di streaming, consulta la [_documentazione di Experience Platform_](https://experienceleague.adobe.com/it/docs/experience-platform/sources/ui-tutorials/create/streaming/http).

La configurazione del canale Forms in [!DNL Marketo Optimizer] richiede le [autorizzazioni](../start/permissions-reference.md) seguenti:

* _[!UICONTROL Configurazioni canale B2B]_ > _[!UICONTROL Visualizza predefinito Forms B2B]_ - Necessario per visualizzare le configurazioni dei predefiniti modulo.
* _[!UICONTROL Configurazioni canale B2B]_ > _[!UICONTROL Gestisci predefinito Forms B2B]_ - Necessario per creare, modificare ed eliminare configurazioni predefinito modulo.
* _[!UICONTROL Configurazioni canale B2B]_ > _[!UICONTROL Pubblica predefinito Forms B2B]_ - Necessario per pubblicare le configurazioni dei predefiniti modulo.

>[!ENDSHADEBOX]

## Linee guida per la configurazione dei predefiniti per moduli

Durante la creazione di un predefinito:

* Puoi impostare più predefiniti utilizzando diverse combinazioni di set di dati e connessioni in streaming.

* Puoi riutilizzare lo stesso set di dati o la stessa connessione in streaming su più predefiniti.

* Ogni connessione in streaming genera automaticamente risorse quali:

  * _Connessione Source_ - origine dei dati.
  * _Connessione di destinazione_ - in cui i dati vengono archiviati o utilizzati.
  * _Flusso Source_: la pipeline che sposta i dati dalla connessione di origine in Experience Platform. Gestisce la mappatura, la trasformazione e la convalida.

## Creare un predefinito di modulo {#create-preset}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_lp_form_connection"
>title="Selezionare l’endpoint da utilizzare"
>abstract="Definisci l’endpoint di streaming a cui vengono inviati i dati al momento dell’invio del modulo."
>additional-url="https://experienceleague.adobe.com/it/docs/experience-platform/sources/ui-tutorials/create/streaming/http" text="Creare una connessione streaming API HTTP"

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_lp_form_dataset"
>title="Selezionare un set di dati"
>abstract="Definisci un set di dati in cui memorizzare e riflettere le risposte del modulo. Inserisci il testo per cercare un set di dati specifico o selezionarlo dall’elenco."

1. Nel menu di navigazione a sinistra, vai a **[!UICONTROL Amministrazione]** > **[!UICONTROL Canali]**.

1. In _[!UICONTROL Impostazioni modulo]_ nel pannello di navigazione, selezionare **[!UICONTROL Predefiniti modulo]**.

   <!-- ![Access the form configurations](./assets/config-channels-forms.png){width="800" zoomable="yes"} -->

1. Fare clic su **[!UICONTROL Crea predefinito modulo]**.

1. Immetti un **[!UICONTROL Nome]** univoco (obbligatorio) e una **[!UICONTROL Descrizione]** (facoltativo) per la configurazione.

   >[!NOTE]
   >
   >I nomi devono iniziare con una lettera (A-Z) e possono contenere solo caratteri alfanumerici. È inoltre possibile utilizzare il carattere di sottolineatura `_`, il punto `.` e il trattino `-`.

1. Selezionare la **[!UICONTROL connessione in streaming]**.

   Questa connessione è l’endpoint di streaming utilizzato per inviare i dati quando un visualizzatore web invia un modulo. Se la connessione in streaming necessaria non viene visualizzata nell’elenco, verifica che i requisiti siano soddisfatti.

1. Fai clic sull&#39;icona _Seleziona set di dati_ ( ![Icona Seleziona set di dati](../assets/do-not-localize/icon-select-data.svg) ) per collegare un set di dati al modulo.

   Il set di dati è il luogo in cui vengono memorizzate e riflesse le risposte del modulo. Puoi immettere una stringa di testo per cercare un set di dati specifico o selezionarlo dall’elenco.

   <!-- ![Select datasets dialog](./assets/config-channel-forms-select-datasets.png){width="500" zoomable="yes"} -->

   >[!NOTE]
   >
   >Al momento sono disponibili per la selezione solo [set di dati di Adobe Experience Platform](https://experienceleague.adobe.com/it/docs/experience-platform/catalog/datasets/overview) abilitati e non abilitati per il profilo. Puoi selezionare un set di dati alla volta. I set di dati di sistema non possono essere utilizzati per salvare i dati del modulo.

   Selezionare la casella di controllo per il set di dati e fare clic su **[!UICONTROL Seleziona]**.

1. Fai clic su **[!UICONTROL Salva come bozza]**.

## Pubblicare un predefinito per moduli

1. Fai clic sul nome del predefinito per moduli per aprire la pagina di configurazione.

   Se necessario, potete apportare qualsiasi modifica alla bozza.

1. Fai clic su **[!UICONTROL Pubblica]**.

   Quando il predefinito per moduli è elencato con lo stato _Pubblicato_, è disponibile per la creazione di moduli.
