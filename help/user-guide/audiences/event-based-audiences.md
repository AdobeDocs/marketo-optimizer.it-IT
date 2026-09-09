---
title: Tipi di pubblico basati su eventi
description: Utilizza i tipi di pubblico basati su eventi in Marketo Optimizer per attivare l’ingresso di un percorso di persone in tempo reale in base alle attività di Marketo Engage.
TQID: 'https://experienceleague.adobe.com/pnXkfVhy4qJ4nsQJLjAXJR6cZA-1edr9LFpyvBo27Xo'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2: id: 46e599c6-e20f-5f67-9824-93415016f66bid: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 320
ht-degree: 0%

---

# Pubblico basato su eventi

In [!DNL Adobe Marketo Optimizer], _i tipi di pubblico basati su eventi_ ti consentono di aggiungere membri del pubblico a un [percorso di persone](../marketing/person-journeys.md) in tempo reale quando si verifica un&#39;attività [!DNL Marketo Engage]. Puoi configurare i tipi di pubblico basati su eventi sul nodo Pubblico dell’area di lavoro del percorso:

* Seleziona una o più attività [!DNL Marketo Engage] (standard o personalizzate) come eventi qualificanti.
* Facoltativamente, aggiungi i filtri del profilo della persona (ad esempio settore, regione o fase del ciclo di vita) per limitare le persone che possono entrare.
* Facoltativamente, definisci i vincoli dell’attributo dell’attività (ad esempio un modulo, un URL o un programma specifico) per limitare le occorrenze di ciascuna attività idonee.

Quando un&#39;attività idonea viene registrata in [!DNL Marketo Engage] per un lead e replicata in [!DNL Adobe Marketo Optimizer], il sistema valuta il record persona corrispondente in base ai filtri e ai vincoli configurati. Se le condizioni sono soddisfatte, la persona entra nel percorso immediatamente tramite il nodo Pubblico.

_Per definire un pubblico basato su eventi per un percorso di persone :_

1. Selezionare il nodo [_Pubblico persona_](../marketing/person-audience-node.md).

1. Nelle proprietà del nodo a destra, scegli **[!UICONTROL Pubblico evento]** come tipo di voce.

   ![Nodo percorso di pubblico persona impostato su pubblico basato su eventi](./assets/event-based-audience-node.png){width="400"}

1. Fare clic su **[!UICONTROL Aggiungi criteri evento]**.

1. Nella finestra di dialogo _[!UICONTROL Modifica criteri evento]_, aggiungi una o più attività [!DNL Marketo Engage] come eventi qualificati, ad esempio:

   * _Partecipa al webinar_
   * _E-mail consegnata_
   * _Clic sul collegamento nell&#39;e-mail_

   >[!NOTE]
   >
   >È inoltre possibile selezionare le attività personalizzate definite nell&#39;istanza [!DNL Marketo Engage] associata.

   Imposta l&#39;operatore e i valori corrispondenti per ogni attività.

   ![Trigger di attività per un pubblico basato su eventi](./assets/event-based-audience-triggers.png){width="700" zoomable="yes"}

   Una persona è idonea per il percorso quando una qualsiasi di queste attività configurate viene registrata per quel lead.

1. (Facoltativo) Per utilizzare una combinazione di evento e filtro per la qualifica del pubblico, aggiungi filtri a livello di persona.

   * Selezionare la scheda **[!UICONTROL Filtri]**.
   * Trascina ciascun filtro e imposta i criteri di corrispondenza.

   ![Filtri persona per un pubblico basato su eventi](./assets/event-based-audience-filters.png){width="700" zoomable="yes"}

   Se aggiungi dei filtri, la persona deve soddisfare almeno una condizione di attività configurata e i filtri configurati.

1. Fai clic su **[!UICONTROL Salva]**.