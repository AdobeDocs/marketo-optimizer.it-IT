---
title: Nodo Percorso pubblico persona
description: Configura il nodo del pubblico della persona in Journey Optimizer B2B per specificare quali profili inserire in un percorso utilizzando elenchi di persone dinamici o tipi di pubblico basati su eventi.
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 0%

---

# Nodo di pubblico della persona

Il nodo _audience persona_ specifica i profili di persona che entrano nel percorso. Quando [crei un percorso di persone](./person-journeys.md), il percorso inizia sempre con un nodo di pubblico di persone che ne definisce l&#39;input. Il nodo del pubblico della persona può avere uno dei due tipi di input del pubblico: un elenco dinamico di persone o un trigger di evento.

Se l&#39;elenco di persone dinamiche necessario per il percorso di persone non esiste già, [creare l&#39;elenco di persone](../audiences/people-lists.md#create-a-people-list) e quindi configurare il nodo di pubblico Persona.

_Per configurare il pubblico di percorso :_

1. Fai clic sul nodo **[!UICONTROL Pubblico persona]**.

   Questa azione visualizza le proprietà del nodo a destra.

   ![Nodo percorso di pubblico della persona](./assets/person-audience-node-properties.png){width="600" zoomable="yes"}

1. Utilizza una delle seguenti opzioni di configurazione del pubblico per il pubblico della persona:

   * **[!UICONTROL Elenco dinamico]** - Utilizza un elenco di persone dinamico basato su regole. Le regole di elenco vengono valutate in fase di runtime del percorso per qualificare i membri del percorso. Le persone che in seguito vengono escluse dall’elenco dinamico non vengono rimosse dal percorso. Vedi _[Elenchi dinamici](../audiences/people-lists.md#dynamic-lists)_.

   * **[!UICONTROL Pubblico evento]** - Utilizza un pubblico evento per definire il pubblico percorso in base agli eventi qualificanti. Definisci i membri del pubblico utilizzando il filtro del profilo della persona e attiva l’immissione del percorso utilizzando i criteri degli eventi. Consulta _[Tipi di pubblico basati su eventi](../audiences/event-based-audiences.md)_.