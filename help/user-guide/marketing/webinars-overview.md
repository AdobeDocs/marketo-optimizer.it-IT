---
title: Webinar interattivi
description: Scopri i concetti alla base dei webinar interattivi in Marketo Optimizer, tra cui il modello di risorse del webinar, gli stati membri, i token e le attività.
keywords: 
role: User
feature: Channels
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 75b481faf0d66210329f95c8afabdfa59e7bcb79
workflow-type: tm+mt
source-wordcount: 1085
ht-degree: 2%

---


# Webinar interattivi

I webinar interattivi ti consentono di pianificare, promuovere, distribuire e seguire un webinar live o simulato senza uscire da [!DNL Adobe Marketo Optimizer]. La consegna viene eseguita automaticamente su [!DNL Adobe Connect], pertanto non è mai necessario cambiare i prodotti per progettare una pagina di registrazione, ospitare la sessione in tempo reale o estrarre i dati di partecipazione.

>[!NOTE]
>
>Questa funzione richiede una licenza ed è soggetta a termini e condizioni aggiuntivi. Per informazioni sui termini e le condizioni aggiuntive, rivedi il contratto o contatta Adobe.

Puoi creare un webinar in due modi:

* **Esperienza di conversazione** - Chiedi al collega di pianificare, promuovere e creare report su un webinar in linguaggio naturale. Consulta [Creare webinar con Coworker](../agents/webinar-creation.md).

* **Scegli**. Utilizza l&#39;area di lavoro _[!UICONTROL Programmi]_ per aggiungere una risorsa del webinar, progettarla, aggiungere co-host e relatori, creare percorsi di promozione e follow-up e rivedere i rapporti. Consulta [Creare e progettare un webinar](create-webinar.md) e [percorsi di promozione e follow-up](webinar-journeys.md).

## Webinar come risorsa

Un webinar è una risorsa di proprietà di un [programma](https://experienceleague.adobe.com/it/docs/journey-optimizer-b2b/prime/marketing-management/programs/programs), allo stesso modo di un&#39;e-mail o di una pagina di destinazione. L’aggiunta di un webinar a un programma ne effettua la registrazione e ne rende disponibili i token, gli attributi e le attività per ogni percorso e risorsa di tale programma.

>[!IMPORTANT]
>
>Un programma può attualmente possedere una risorsa del webinar. Per una versione futura è pianificato il supporto di più webinar per programma.

## Stati membri

Per ogni persona che è membro di un programma che contiene un webinar, si applicano contemporaneamente tre Stati indipendenti. È possibile fare riferimento a ciascuno di essi separatamente in audience e condizioni di percorso.

| Stato | Proprietario | Valori |
|---|---|---|
| Stato membro del programma | Programma | Configurabile per [tipo di programma](https://experienceleague.adobe.com/it/docs/journey-optimizer-b2b/prime/admin/program-types) |
| Stato del webinar | Risorsa webinar | Invitato, Registrato, Partecipato, No-Show, Partecipato su richiesta |
| Stato percorso | Percorso | Nodo corrente, in pausa, completato e altri stati di runtime del percorso |

### Stato del webinar

Lo stato del webinar ha cinque valori. [!DNL Adobe Connect] in genere imposta il valore automaticamente, ma è anche possibile impostare lo stato con un&#39;azione di percorso se è necessario sostituirlo. Per riflettere la frequenza registrata in un altro percorso, ad esempio, è possibile impostare lo stato nel proprio.

| Stato | Modalità di impostazione | Origine |
|---|---|---|
| Invitato | Un nodo di percorso _Esegui un&#39;azione_, in genere quando l&#39;e-mail di invito invia | Controllato dall&#39;autore |
| Registrato | Un nodo di percorso _Esegui un&#39;azione_ quando la persona si registra. Questo attiva anche [!DNL Adobe Connect] per generare l&#39;URL di unione della persona | Controllato dall&#39;autore |
| Partecipazione avvenuta | Un evento da [!DNL Adobe Connect] dopo l&#39;esecuzione del webinar live | Controllato dal sistema, con possibilità di sostituzione dell’autore tramite un percorso |
| No-Show | Un evento da [!DNL Adobe Connect] dopo l&#39;esecuzione del webinar live | Controllato dal sistema, con possibilità di sostituzione dell’autore tramite un percorso |
| Partecipazione su richiesta | Un evento di [!DNL Adobe Connect] quando una persona che non ha partecipato in diretta guarda la registrazione in un secondo momento | Controllato dal sistema, con possibilità di sostituzione dell’autore tramite un percorso |

>[!IMPORTANT]
>
>Sia che sia impostato automaticamente o da un percorso, lo stato del webinar si sposta solo in una direzione, esattamente come fa [lo stato del programma](./programs.md#statuses). Una persona può passare a uno stato successivo (ad esempio, _Registrato_ a _Partecipato_), ma non tornare a uno precedente. Pianifica qualsiasi sostituzione dell’autore tenendo presente questa progressione lineare.

Per spostare una persona da uno stato all&#39;altro da un percorso, utilizzare l&#39;azione **[!UICONTROL Modifica stato membro del webinar]**. Consulta [percorsi di promozione e follow-up](webinar-journeys.md).

## Token del webinar

I token del webinar sono disponibili ovunque tu personalizzi il contenuto dell’e-mail (oggetto, corpo, preintestazione e mittente). Trovali nell&#39;editor di personalizzazione in **_Contesto > Webinar_**.

I token a livello di risorsa si trovano direttamente nella cartella del webinar:

&#x200B;- Titolo
&#x200B;- Descrizione
&#x200B;- Data e ora inizio, data e ora fine
&#x200B;- Durata
&#x200B;- Fuso orario
&#x200B;- Presentatori
&#x200B;- URL di registrazione

>[!NOTE]
>
>I co-host vengono visualizzati nella sezione Team del webinar della pagina del webinar, ma non sono disponibili come token di personalizzazione.

I token per destinatario risiedono in una sottocartella **Membro**:

&#x200B;- **Stato** - Stato corrente del webinar del destinatario (Invitato, Registrato, Partecipato, No-Show o Partecipato su richiesta). Consulta [Stato webinar](#webinar-status).
&#x200B;- **URL di partecipazione** - Il collegamento [!DNL Adobe Connect] personale del destinatario. Questo problema viene risolto solo dopo la registrazione o la successiva dello stato del webinar del destinatario. Si risolve vuoto per chiunque in una fase precedente.
&#x200B;- **URL di registrazione** - Si risolve dopo la pubblicazione della registrazione dopo la sessione live e rimane vuoto fino ad allora. Utilizzalo in modo condizionale nelle e-mail dopo il webinar in modo che non venga visualizzato un collegamento prima che sia presente una registrazione da mostrare.

>[!NOTE]
>
>I token del webinar vengono attualmente visualizzati solo nel contenuto dell’e-mail (oggetto, corpo, preintestazione e mittente). Il supporto per i token del webinar nelle pagine di destinazione e nei moduli è pianificato per una versione futura.
>
>Poiché questi token si risolvono come vuoti anziché generare un errore, un’e-mail o una pagina che vi fa riferimento viene riprodotta in modo sicuro in qualsiasi momento del ciclo di vita del webinar. Visualizza l’anteprima del contenuto prima e dopo che i valori sono disponibili, per confermare che il layout funziona correttamente in entrambi i modi.

## Attività dei webinar

Ogni webinar segnala automaticamente le attività che puoi utilizzare come _Ascolta attivatori dell&#39;evento_, _Condizioni di suddivisione del percorso_, filtri del pubblico e metriche di reporting:

* Pone una domanda
* Risponde a un sondaggio
* Fai clic su un collegamento
* Scarica una risorsa
* Alza una mano

>[!NOTE]
>
>Le modifiche di stato del webinar (Invitato, Registrato, Partecipato, Non mostrato, Partecipato a richiesta) non sono attualmente disponibili come filtro di attivazione o attività _Ascolta evento_ personalizzato. Per diramare un percorso in base allo stato del webinar, utilizza direttamente una condizione _Dividi percorso_ nello stato del webinar (descritta in [_Crea un percorso post-webinar_](webinar-journeys.md#build-post-webinar-journey)) invece di ascoltare un&#39;attività di modifica dello stato.

Coinvolgimento da parte di persone che guardano la registrazione dopo che l’evento live viene acquisito come le stesse attività, contrassegnate con una modalità di On-Demand. A differenza delle attività, il coinvolgimento on-demand crea uno stato del webinar separato: una persona che non ha partecipato in diretta e successivamente guarda la registrazione spostarsi da **No-Show** a **Partecipazione su richiesta**.

## Prerequisiti

Prima di iniziare a creare un webinar, assicurati di aver soddisfatto le seguenti condizioni.

| Prerequisito | Dettagli |
|---|---|
| Un programma | Il webinar viene aggiunto all’interno di un programma esistente. In genere, un analista delle operazioni di marketing crea prima il programma. |
| Licenza webinar (capacità) | Prima di poter pianificare un webinar, è necessario disporre di una licenza per il webinar, detta anche licenza di capacità. È possibile scegliere una capacità al momento dell&#39;installazione e rendere disponibili componenti aggiuntivi con capacità più elevata. Per aumentare la capacità disponibile, contatta il team del tuo account Adobe. |
| [!DNL Adobe Connect] | La consegna viene eseguita in [!DNL Adobe Connect]. Il provisioning viene eseguito automaticamente in background. Non è necessario lasciare [!DNL Marketo Optimizer] per creare o ospitare un webinar. |

### Autorizzazioni

L’accesso alle funzioni dei webinar dipende dalle autorizzazioni assegnate ai webinar.

| Ruolo | Che cosa viene concesso |
|---|---|
| Visualizza webinar B2B | Visualizzare l&#39;elenco dei webinar, la configurazione del webinar, i dettagli e i report. I controlli Crea, Progetta, Modifica e Immetti non sono disponibili tramite questa autorizzazione e non puoi essere assegnato a un webinar come co-host o relatore. |

<!-- 
| Manage B2B webinars | Full lifecycle access: create, design, configure, schedule, edit, deliver, host, and delete a webinar. The Create, Design, Edit, and Manage controls are available only for users with this role. |
| Webinar co-host | After you are added as a co-host, this permission enables you to design and enter that webinar with co-host controls. |
| Webinar presenter | After you are added as a presenter, this permission enables you to view and enter that webinar with presenter capabilities. It grants no authoring or design access on its own. |

>[!NOTE]
>
>Co-hosts and presenters are currently defined by entering a name and email rather than selected from a picker of role-eligible users — see [Add co-hosts and presenters](create-webinar.md#add-co-hosts-and-presenters). The _Webinar co-host_ and _Webinar presenter_**_ roles still govern what that person can do when they are added as a co-host or presenter.

-->
