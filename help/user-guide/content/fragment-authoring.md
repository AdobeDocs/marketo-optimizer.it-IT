---
title: Authoring di frammenti
description: 'Crea frammenti di contenuto riutilizzabili con strumenti di progettazione visiva: aggiungi struttura, risorse, personalizzazione, contenuto condizionale e tracciamento URL collegato per e-mail e modelli in Marketo Optimizer.'
TQID: 'https://experienceleague.adobe.com/KbnYkUMVfjBv5ST55WwAqYiMDkynwSw4BKIP0bsE-DI'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 203
ht-degree: 3%

---

# Authoring dei frammenti

Dopo aver [creato un frammento](./fragments.md#create-fragments), utilizza lo spazio di progettazione visiva per creare la struttura e i componenti di contenuto nel frammento.

## Aggiungere struttura e contenuto {#design-fragment}

{{$include /help/_includes/content-design-components-prime.md}}

## Aggiungere risorse {#add-assets}

Nello spazio di progettazione visiva, seleziona l&#39;icona _Assets_ ( ![icona Assets](../assets/do-not-localize/icon-assets-me.svg) ) nella barra di navigazione a sinistra per sfogliare e selezionare le risorse immagine dalla libreria di risorse [!DNL Marketo Optimizer].

Per i passaggi per selezionare, sostituire o caricare le risorse immagine, consulta [Utilizzare le risorse per l&#39;authoring dei contenuti](./digital-asset-management.md#assets-authoring).

## Spostarsi tra livelli, impostazioni e stili {#navigate-layers-settings-styles}

{{$include /help/_includes/content-design-navigation.md}}

## Personalizzazione dei contenuti {#personalize-content}

[!DNL Marketo Optimizer] utilizza la sintassi Handlebars per la personalizzazione. I token vengono sostituiti al momento dell’invio con i valori dei dati di profilo di ciascun destinatario.

_Per aggiungere la personalizzazione :_

1. Seleziona il componente testo e fai clic sull&#39;icona _Aggiungi personalizzazione_ ( ![icona Personalizza](../assets/do-not-localize/icon-personalize.svg) ) nella barra degli strumenti.
1. Nella finestra di dialogo di personalizzazione, sfoglia la struttura dello schema a sinistra e seleziona un attributo di profilo. L&#39;editor inserisce l&#39;espressione Handlebars corrispondente, ad esempio `{{profile.firstName}}`.
1. Aggiungere un valore di fallback per gestire i dati mancanti, se necessario, ad esempio `{{profile.firstName | default: "there"}}`.
1. Fai clic su **[!UICONTROL Conferma]** o **[!UICONTROL Inserisci]**. L’espressione viene visualizzata in linea nel campo.

Per informazioni dettagliate sugli strumenti e sulla sintassi dell&#39;editor espressioni, vedere [Editor Personalization](./personalization-expressions.md).

## Modifica tracciamento URL collegato {#edit-linked-url-tracking}

{{$include /help/_includes/content-design-links.md}}
