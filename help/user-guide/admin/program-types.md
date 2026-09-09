---
title: Tipi di programmi
description: Creazione e gestione di tipi di programmi che definiscono attributi e flussi di stato dei membri per i programmi in Marketo Optimizer.
TQID: 'https://experienceleague.adobe.com/Eepcnc51p-P-yoyylXBr47SF0xR-3pvZab2aHf9jdew'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2: id: a29661b8-f7a4-53d1-a9ac-fdec08c092e4id: a659ad61-de21-559d-a901-02e2fb329ff5
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 389
ht-degree: 0%

---

# Tipi di programmi

I tipi di programmi definiscono aspetti importanti dei [programmi](../marketing/programs.md) e dei relativi membri e distinguono tra diversi tipi di programmi di marketing. Ogni tipo di programma definisce le seguenti proprietà, che vengono ereditate per i programmi che utilizzano il tipo di programma:

* **Attributi** - Gli attributi descrivono gli aspetti importanti del tipo di programma, ad esempio le date degli eventi e gli attributi di posizione.

* **Flusso di stato del programma** - Ogni stato viene assegnato a un passaggio nel tipo di programma (ad esempio 1, 2 o 3). I membri di un programma possono passare solo da uno stato con lo stesso numero di passaggio (ad esempio, da _Non mostrato_ a _Partecipato_) o a uno stato con un numero di passaggio superiore (ad esempio, da _Invitato_ a _Registrato_).

  Gli stati del programma si escludono a vicenda e sono lineari, pertanto una persona può avere un solo valore di stato per programma. Durante la progettazione degli stati, pensa a quali stati desideri consentire il movimento tra. Ad esempio, se un utente non viene visualizzato per un webinar ma dispone di un&#39;opzione per partecipare in un secondo momento a un evento on demand, può avere lo stesso numero di stato o deve impostarlo su un numero di stato superiore in modo che un membro del programma possa avanzare.

>[!NOTE]
>
>Se un tipo di programma è utilizzato da almeno un programma, non può essere modificato.

_Per definire un tipo di programma personalizzato :_

1. Nella barra di navigazione a sinistra di [!DNL Adobe Marketo Optimizer], espandi **[!UICONTROL Amministrazione]** e seleziona **[!UICONTROL Tipi di programma]**.

   ![Accedere all&#39;elenco dei tipi di programma](./assets/program-types-list.png){width="800" zoomable="yes"}

1. Fai clic su **[!UICONTROL Crea tipo]** in alto a destra.

1. Immetti un **[!UICONTROL Nome]** univoco (obbligatorio) e **[!UICONTROL Descrizione]** (facoltativo).

   ![Crea tipo di programma](./assets/program-type-create.png){width="600" zoomable="yes"}

   >[!TIP]
   >
   >L’inclusione di una descrizione è una best practice e rende la libreria dei tipi di programma più gestibile.

1. Fare clic su **[!UICONTROL Crea tipo]**.

1. Aggiungi **[!UICONTROL Attributi]** per il tipo di programma.

   Per ogni attributo che si desidera aggiungere:

   * Fare clic su **[!UICONTROL Aggiungi attributo]**.
   * Scegli il **[!UICONTROL nome API]** e immetti il **[!UICONTROL nome visualizzato]**.
   * Fai clic su **[!UICONTROL Salva]**.

   ![Attributi del tipo di programma](./assets/program-type-attributes.png){width="600" zoomable="yes"}

1. Definisci i passaggi per **[!UICONTROL Stati programma]**.

   Definisci ogni passaggio da includere nel flusso:

   * Fai clic su **[!UICONTROL Aggiungi passaggio]**.
   * Immettere un nome di stato.
   * (Facoltativo) Fai clic su **[!UICONTROL Aggiungi stato]** e immetti un nome di stato aggiuntivo da includere per il passaggio.

   Selezionare la casella di controllo **[!UICONTROL Contrassegna come completata]** per ogni passaggio che si desidera monitorare come esecuzione di un programma completata.

   ![Stati del tipo di programma](./assets/program-type-statuses.png){width="600" zoomable="yes"}

1. Fai clic su **[!UICONTROL Fine]** per salvare le modifiche e tornare all&#39;elenco dei tipi di programma.