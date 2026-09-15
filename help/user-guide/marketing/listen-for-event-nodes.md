---
title: Ascolta un nodo evento
description: 'Configurare Ascolta per i nodi di un evento in Marketo Optimizer: imposta i trigger di evento, applica filtri facoltativi e avanza le persone quando si verificano attività o modifiche di dati.'
TQID: 'https://experienceleague.adobe.com/6v3i6M-Hhr2RAWrS68WaEVb8VJEzJZbD7vXOJOsjgc8'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
source-git-commit: cc98b02f4273c5df2e27b52acd1239f0f0bf8aa0
workflow-type: tm+mt
source-wordcount: '1139'
ht-degree: 6%
---
# Ascolta un nodo evento

Per far avanzare il pubblico al passaggio successivo nel percorso quando si verifica un evento, aggiungi il nodo _Ascolta un evento_.

## Trigger evento {#event-triggers}

Definisci i criteri dell’evento che attivano il nodo del percorso e sposta in avanti il membro del pubblico.

| Trigger | Descrizione |
| -------- | ----------- |
| Brand Concierge | Attività per lead che interagiscono con [!DNL Brand Concierge]. |
| E-mail | Attività e-mail per i lead, inclusi invii, consegna e coinvolgimento. |
| Evento | Attività di webinar interattivi per i lead, inclusa la registrazione, la partecipazione e le interazioni. |
| Opportunità | Attività relative ai record opportunità associati a lead o account. |
| App di vendita | Attività lead relative a [!DNL Sales Qualifier] o [!DNL Marketo Sales Insights]. |
| Altro | Attività che non rientrano nelle categorie predefinite, fornendo flessibilità per attivatori di eventi personalizzati o vari. |

>[!BEGINSHADEBOX]

**Attività Marketo Engage supportate per i trigger**

Quando si attiva su eventi, [!DNL Marketo Optimizer] supporta le attività dell&#39;istanza [!DNL Marketo Engage] connessa come origine dati.

>[!NOTE]
>
>Può esistere una sola istanza [!DNL Marketo Engage] come origine dati ed è preconfigurata al momento del provisioning dell&#39;istanza [!DNL Marketo Optimizer].

È possibile generare trigger di evento in base alle seguenti [!DNL Marketo Engage] attività:

* [!UICONTROL Compila il modulo di Marketo Engage] - Generato quando un lead invia un modulo [!DNL Marketo Engage] specificato.
* [!UICONTROL Visita la pagina Web di Marketo Engage] - Viene attivato quando un lead con un cookie di tracciamento di Munchkin visita una pagina Web specificata.
* [!UICONTROL Collegamento clic sulla pagina Web di Marketo Engage] - Viene attivato quando un lead fa clic su un collegamento ipertestuale tracciato in una pagina Web in cui è installato il codice di tracciamento di Munchkin [!DNL Marketo Engage].
* [!UICONTROL L&#39;e-mail Marketo Engage è stata recapitata]. Viene attivato quando il server di posta del lead (MX) restituisce una risposta di completamento (un messaggio OK 250) al server di invio [!DNL Marketo Engage].
* [!UICONTROL Mancati recapiti e-mail di Marketo Engage] - Viene attivato quando un server di posta di destinazione rifiuta un messaggio e-mail di [!DNL Marketo Engage] inviato come errore permanente, ad esempio un utente non valido o un dominio sconosciuto.
* [!UICONTROL Marketo Engage email bounces soft] - Viene attivato quando un server di posta di destinazione rifiuta un messaggio di posta elettronica [!DNL Marketo Engage] inviato come problema temporaneo (ad esempio, server occupato o cassetta postale piena). [!DNL Marketo Engage] ritenta automaticamente i mancati recapiti non permanenti fino a tre volte attraverso i server MX prima di segnalare i problemi.
* [!UICONTROL Annulla iscrizione all&#39;e-mail di Marketo Engage] - Viene attivato quando un lead rinuncia alle e-mail di marketing non operative. Quando viene attivato, [!DNL Marketo Engage] aggiorna automaticamente il valore del campo `Unsubscribed` del lead in `true`, eliminandoli dagli invii di e-mail standard futuri.
* [!UICONTROL Apre l&#39;e-mail di Marketo Engage] - Viene attivato quando un lead apre un&#39;e-mail di [!DNL Marketo Engage] tracciata.
* [!UICONTROL Collegamento clic nell&#39;e-mail di Marketo Engage] - Viene attivato quando un lead fa clic su un collegamento (o un collegamento vincolato specifico) all&#39;interno di un&#39;e-mail di [!DNL Marketo Engage].

>[!ENDSHADEBOX]

## Filtri degli eventi {#event-filters}

Puoi includere il filtro per limitare i trigger di evento corrispondenti in base a vari criteri:

| Filtri | Descrizione |
| ------- | ----------- |
| Cronologia delle attività | Attività basate su condizioni valutate utilizzando uno o più elementi selezionati |
| Brand Concierge | Attività per lead che interagiscono con [!DNL Brand Concierge]. |
| Attributi azienda | Attributi dal profilo società/account, tra cui: <li>Ricavi annuali <li>Nome dell’azienda <li>Paese di fatturazione <li>Settore <li>N. dipendenti <li>Codice SIC <li>Stato |
| Dati di intento | Attributi basati sui dati di intento associati al profilo della persona. |
| Opportunità | Attributi in base alle opportunità associate al profilo persona. |
| Attributi della persona | Attributi dal profilo persona B2B, tra cui: <li>Città <li>Paese <li>Data di nascita <li>Indirizzo e-mail <li>E-mail non valida <li>E-mail sospesa <li>Nome <li>Area geografica dello stato dedotta<li>Posizione lavorativa <li>Cognome <li>Numero di cellulare <li>Punteggio di coinvolgimento della persona <li>Numero di telefono <li>Codice postale <li>Stato <li>Annulla l&#39;iscrizione <li>Motivo dell’annullamento dell’iscrizione |
| App di vendita | Attività lead relative a [!DNL Sales Qualifier] o [!DNL Marketo Sales Insights]. |
| Filtri speciali | Filtrare gli attributi che non rientrano nelle categorie predefinite, fornendo flessibilità per criteri di filtro personalizzati o vari. |

>[!BEGINSHADEBOX]

**Attività Marketo Engage supportate per filtri**

Quando si filtrano eventi attivati, [!DNL Marketo Optimizer] supporta le attività dell&#39;istanza [!DNL Marketo Engage] connessa come origine dati.

>[!NOTE]
>
>Può esistere una sola istanza [!DNL Marketo Engage] come origine dati ed è preconfigurata al momento del provisioning dell&#39;istanza [!DNL Marketo Optimizer].

È possibile creare filtri evento per le seguenti [!DNL Marketo Engage] attività:

* [!UICONTROL Modulo Marketo Engage compilato] - Corrisponde ai lead che hanno completato un modulo [!DNL Marketo Engage] specifico in qualsiasi punto del registro attività non obsoleto.
* [!UICONTROL Pagina Web Marketo Engage visitata] - Corrisponde ai lead che hanno visualizzato un URL specifico sul sito Web o [!DNL Marketo Engage] pagine di destinazione. Si basa direttamente sul codice di tracciamento di Munchkin installato sul sito.
* [!UICONTROL Collegamento selezionato nella pagina Web di Marketo Engage] - Corrisponde ai lead che hanno fatto clic su un collegamento o una risorsa specifica in una pagina tracciata.
* [!UICONTROL E-mail Marketo Engage inviata] - Corrisponde ai lead a cui [!DNL Marketo Engage] ha tentato di inviare un&#39;e-mail specifica, tenendo conto delle azioni di distribuzione precedenti agli hard bounce o alle accettazioni del server.
* [!UICONTROL E-mail Marketo Engage recapitata] - Corrisponde ai lead il cui server di posta (MX) ha restituito una risposta di esito positivo (un messaggio OK 250) al server di invio [!DNL Marketo Engage].
* [!UICONTROL E-mail Marketo Engage non recapitata] - Corrisponde ai lead che hanno riscontrato un errore di recapito permanente in un invio e-mail specifico o in un arco temporale.
* [!UICONTROL E-mail non recapitate in Marketo Engage] - Corrisponde a lead le cui e-mail hanno subito un errore di consegna temporaneo (ad esempio, una casella in entrata completa o un server offline) anziché un errore permanente irreversibile.
* [!UICONTROL Annullamento dell&#39;iscrizione all&#39;e-mail di Marketo Engage] - Corrisponde ai lead che hanno rinunciato alle e-mail di marketing non operative. In questo caso, [!DNL Marketo Engage] aggiorna automaticamente il valore del campo `Unsubscribed` del lead in `true`, eliminandoli dagli invii di e-mail standard futuri.
* [!UICONTROL E-mail Marketo Engage aperta] - Corrisponde ai lead che hanno aperto un&#39;e-mail [!DNL Marketo Engage] tracciata.
* [!UICONTROL Collegamento selezionato nell&#39;e-mail di Marketo Engage] - Corrisponde ai lead che hanno fatto clic su un collegamento (o un collegamento specifico) all&#39;interno di un&#39;e-mail di [!DNL Marketo Engage].

>[!ENDSHADEBOX]

## Aggiungere un nodo evento {#add-event-node}

1. Passa all’area di lavoro del percorso.

1. Fai clic sull&#39;icona più ( **+** ) in un percorso e scegli **[!UICONTROL Ascolta un evento]**.

   ![Fai clic sull&#39;icona Aggiungi nel percorso del percorso](./assets/person-journey-canvas-add-node.png){width="200"}

1. Nelle proprietà del nodo a destra, fai clic su **[!UICONTROL Aggiungi criterio evento]**.

1. Nella finestra di dialogo _[!UICONTROL Modifica evento]_, aggiungi un evento e imposta i vincoli a cui desideri far corrispondere il trigger.

   Trascina e rilascia il trigger di evento nello spazio del generatore e imposta la definizione. Fare clic su **[!UICONTROL Aggiungi vincolo]** per ogni vincolo che si desidera utilizzare per perfezionare la corrispondenza dell&#39;evento.

   ![Modifica evento - trigger evento](./assets/edit-event-triggers.png){width="700" zoomable="yes"}

   Puoi aggiungere più eventi da associare. Il primo evento qualificante fa avanzare il profilo della persona nel percorso.

1. (Facoltativo) Seleziona la scheda **[!UICONTROL Filtri]** e aggiungi i criteri di filtro per i trigger.

   Trascina e rilascia il filtro nello spazio del generatore e imposta la definizione. Fare clic su **[!UICONTROL Aggiungi vincolo]** per ogni vincolo che si desidera utilizzare per perfezionare la corrispondenza del filtro.

   ![Modifica evento - filtro eventi](./assets/edit-event-filters.png){width="700" zoomable="yes"}

1. Fai clic su **[!UICONTROL Salva]**.

   In qualsiasi momento, puoi fare clic su **[!UICONTROL Modifica evento]** per modificare i criteri dell&#39;evento per il nodo.

1. Se necessario, impostare l&#39;opzione **[!UICONTROL Timeout]** per limitare il periodo di tempo per l&#39;ascolto dell&#39;evento.

   >[!NOTE]
   >
   >Il percorso termina dopo un timeout a meno che non si definisca un percorso di timeout in cui è possibile aggiungere altri nodi.

   Abilita l&#39;opzione **[!UICONTROL Timeout]** e seleziona la durata per la quale il percorso attende che si verifichi un evento prima del timeout.

   ![Opzioni di timeout abilitate per il nodo Ascolta percorso eventi](./assets/person-journey-event-node-timeout.png){width="550" zoomable="yes"}

   È possibile scegliere di terminare il percorso qui o eseguire un&#39;azione diversa impostando un altro percorso. Per creare un nuovo percorso nel percorso in cui è possibile aggiungere azioni ed eventi applicabili ai profili quando l&#39;evento non si verifica, selezionare la casella di controllo **[!UICONTROL Imposta percorso di timeout]**.
