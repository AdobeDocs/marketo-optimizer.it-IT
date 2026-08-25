---
title: Percorsi di promozione e follow-up dei webinar
description: Crea percorsi di promozione, consegna e post-webinar intorno a un webinar in Marketo Optimizer e personalizza il contenuto con token del webinar.
keywords: null
role: User
feature: Person Journeys
source-git-commit: 75b481faf0d66210329f95c8afabdfa59e7bcb79
workflow-type: tm+mt
source-wordcount: '823'
ht-degree: 0%

---


# Percorsi di promozione e follow-up dei webinar

Dopo aver aggiunto un webinar a un programma, crea uno o più [percorsi](./person-journeys.md) all&#39;interno dello stesso programma per invitare le persone, inviare loro un promemoria, distribuire la sessione e proseguire in seguito.

>[!NOTE]
>
>Questa pagina descrive come creare questi percorsi a mano. Affinché Coworker crei gli stessi percorsi da un modello, consulta [Creare webinar con Coworker](../agents/webinar-creation.md).

## Creare un percorso di promozione {#build-promotion-journey}

Un tipico percorso di promozione invita le persone, tiene traccia della loro registrazione e ricorda loro l’avvicinarsi del webinar.

1. [Crea il percorso di persone](./person-journeys.md#create-a-person-journey).

1. [Selezionare un pubblico per il percorso](./person-audience-node.md).

1. Aggiungi un nodo **[!UICONTROL Invia e-mail]** con un invito e-mail.

   Utilizza i token del webinar come _Titolo_ e _Data/ora inizio_ nel contenuto e collega alla pagina di registrazione del webinar.

1. Aggiungi un nodo **[!UICONTROL Esegui un&#39;azione]**, seleziona l&#39;azione **[!UICONTROL Cambia stato membro del webinar]**, seleziona il webinar e imposta lo stato su _Invitato_.

   Inseriscilo subito dopo il nodo **[!UICONTROL Invia e-mail]** dell&#39;invito.

   >[!NOTE]
   >
   >In genere si impostano solo _Invitato_ e _Registrato_ da un percorso di promozione. [!DNL Adobe Connect] imposta automaticamente _Partecipazione avvenuta_, _Nessuna partecipazione_ e _Partecipazione avvenuta_. La stessa azione può ignorare questi stati successivi da un percorso se necessario, ma solo in avanti, in base alla progressione lineare descritta in [_Stato webinar_](webinars-overview.md#webinar-status).

1. Ospita il modulo di registrazione in una [pagina di destinazione](../content/landing-pages.md).

1. Aggiungi un nodo **[!UICONTROL Esegui un&#39;azione]**, seleziona l&#39;azione **[!UICONTROL Cambia stato membro del webinar]**, seleziona il webinar e imposta lo stato su _Registrato_ (attivato dall&#39;invio del modulo).

   Lo spostamento di un utente a _Registrato_ comporta due operazioni automatiche:

   * [!DNL Adobe Connect] genera l&#39;URL di join individuale di tale persona.
   * Invia l&#39;e-mail di conferma, se ne hai configurato uno, contenente il token _URL di unione_.

1. Genera una cadenza di promemoria utilizzando i nodi **[!UICONTROL Wait]** temporizzati rispetto al token _Start Datetime_ del webinar.

   Ad esempio, impostalo su una settimana prima, un giorno prima e un’ora prima.

1. Aggiungi un nodo **[!UICONTROL Wait]** temporizzato al webinar _End Datetime_ token, pertanto il percorso si interrompe fino al termine della sessione live.

   Continua a [Creare un percorso post-webinar](#build-post-webinar-journey) da qui.

   >[!NOTE]
   >
   >Le modifiche allo stato del webinar non sono attualmente disponibili come **[!UICONTROL Ascolta un evento]** trigger. Utilizza invece un nodo **[!UICONTROL Wait]** temporizzato seguito da un nodo **[!UICONTROL Split paths]** sullo stato del webinar, come mostrato di seguito, invece di ascoltare la modifica di stato stessa.

## Personalizzare le e-mail

I token del webinar vengono riprodotti nel contenuto dell’e-mail: oggetto, corpo, preintestazione e mittente. Consulta [Token del webinar](webinars-overview.md#webinar-tokens) per l&#39;elenco completo.

>[!NOTE]
>
>I token del webinar non sono attualmente disponibili nella pagina di destinazione della registrazione o nei moduli. Personalizza quelli con token di programma standard e riservi la personalizzazione specifica per il webinar (come URL di unione e URL di registrazione) per l’e-mail.

>[!IMPORTANT]
>
>Il token **_URL di unione_** viene risolto solo per le persone il cui stato del webinar è _Registrato_ o successivo. Il token **_URL di registrazione_** viene risolto solo dopo la pubblicazione della registrazione. Entrambi si risolvono in precedenza in un valore vuoto anziché in un errore, pertanto verifica attentamente che le e-mail vengano visualizzate in modo accettabile in qualsiasi modo prima di pubblicarle.

## Consegna il webinar {#deliver-webinar}

All&#39;ora pianificata, il webinar verrà eseguito in [!DNL Adobe Connect]:

* I relatori e i co-host partecipano utilizzando il collegamento individuale nella sezione **Team del webinar**.
* Partecipanti che partecipano utilizzando il token **URL di partecipazione** personale.
* [!DNL Adobe Connect] acquisisce le attività in-session (domande, risposte ai sondaggi, clic sui collegamenti, download di risorse e aumenti di mano) e le invia nuovamente a [!DNL Marketo Optimizer] come [attività webinar](webinars-overview.md#webinar-activities), disponibili per qualsiasi percorso in ascolto.

Se il webinar è impostato su **Live simulato**, il contenuto preregistrato viene riprodotto automaticamente all&#39;ora pianificata mentre i relatori interagiscono in diretta tramite chat, sondaggi e domande e risposte.

## Creare un percorso di post-webinar {#build-post-webinar-journey}

Al termine della sessione live, [!DNL Adobe Connect] imposta lo stato del webinar di ogni persona su _Partecipazione avvenuta_ o _No-Show_. Quando il nodo **[!UICONTROL Wait]** del percorso viene rilasciato, eseguire il ramo utilizzando tale stato con un nodo **[!UICONTROL Split paths]**.

1. Aggiungi un nodo **[!UICONTROL Percorsi suddivisi]** con una condizione sullo stato del webinar, ad esempio _Ha partecipato al webinar_.

1. Nel percorso _Partecipato_, invia un&#39;e-mail di ringraziamento.

   Ad esempio, invia una ripetizione e il follow-up delle risorse. Quindi utilizza un nodo **[!UICONTROL Attendi]** e un&#39;e-mail call-to-action del passaggio successivo.

1. Nel percorso _No-Show_, invia un&#39;e-mail di _ci sei mancato_.

   Nel contenuto dell’e-mail, invitali a guardare la registrazione. Quindi utilizza un nodo **[!UICONTROL Attendi]** e un messaggio e-mail di follow-up che riepiloga le principali attività da intraprendere.

1. Personalizza ulteriormente uno dei percorsi utilizzando altre attività del webinar.

   Ad esempio, diramare o personalizzare in base a _risponde a un sondaggio_ con una risposta specifica.

1. Utilizza il token **_URL di registrazione_** in entrambi i percorsi dopo che è risolvibile, in modo che gli utenti possano guardarlo su richiesta.

   **_Il coinvolgimento on-demand_** (durata del controllo, clic sul collegamento di riproduzione e download) viene acquisito come le stesse attività del webinar, con tag della modalità _On-Demand_. A differenza di queste attività, la visualizzazione on-demand sposta anche una persona _No-Show_ nello stato del webinar _Partecipazione avvenuta_. Di conseguenza, un percorso di percorso _No-Show_ può raggiungere le persone che guardano la registrazione in un secondo momento. Dividi ulteriormente lo stato del webinar, o ricontrollane dopo un ritardo, se desideri un trattamento diverso per le persone che guardano on-demand.
