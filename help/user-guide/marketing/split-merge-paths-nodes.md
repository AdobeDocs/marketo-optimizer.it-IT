---
title: Dividere e unire i nodi dei percorsi
description: Scopri come utilizzare suddividere e unire i nodi dei percorsi nei percorsi di persone per segmentare le persone in percorsi distinti in base a condizioni definite, quindi riunirle in un punto comune a valle.
TQID: 'https://experienceleague.adobe.com/XMN7lgb77bFlJkNXrmPf9ZSCV-GgIuybtr-O3AsqT2U'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
    internal-label: Journeys
source-git-commit: 9d9f2ae1aafc5ffdc2bcc6546c7eb2ddcbaa4ab2
workflow-type: tm+mt
source-wordcount: '1064'
ht-degree: 6%
---
# Dividere e unire i nodi dei percorsi

Utilizza i nodi di percorsi suddivisi e uniti nei percorsi di persone per segmentare le persone in percorsi distinti in base alle condizioni definite, quindi unisci tali percorsi in modo che il percorso possa continuare. I percorsi di suddivisione consentono di personalizzare azioni ed eventi per segmenti di pubblico specifici, mentre i percorsi di unione combinano tali segmenti in un punto comune.

## Dividere i nodi dei percorsi

Utilizza i nodi suddivisi per segmentare le persone in base alle condizioni definite. Crea percorsi per l’elenco dei tipi di pubblico in base alle condizioni, definisci ogni percorso con nodi di azione ed evento per il segmento, quindi combina i percorsi e continua il percorso.

Un nodo Percorsi suddivisi definisce uno o più percorsi segmentati in base ai filtri delle persone.

<!-- A split based on a people filter is automatically closed with a merge paths node so that all people can move forward to the next step. Split by people paths can include only people actions. These paths cannot be split again and automatically join back. _not currently true_ -->

_&#x200B;**Funzionamento di un nodo di percorso diviso**&#x200B;_

* La valutazione di ciascun percorso è dall&#39;alto verso il basso. Se una persona corrisponde al primo e al secondo percorso, procede solo lungo il primo percorso.
* Il nodo supporta la definizione di un percorso _Altre persone_, in cui è possibile aggiungere azioni o eventi per le persone che non corrispondono a uno dei segmenti o percorsi definiti.

### Filtri persona corrispondenti

Per ogni percorso definito per il nodo, utilizza i seguenti tipi di filtro per far corrispondere le persone in base a una o più condizioni.

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

**Sono supportate [!DNL Marketo Optimizer] attività per i filtri di condizione**

Per le condizioni del percorso, [!DNL Marketo Optimizer] supporta le attività dell&#39;istanza [!DNL Marketo Engage] connessa come origine dati.

>[!NOTE]
>
>Può esistere una sola istanza [!DNL Marketo Engage] come origine dati ed è preconfigurata al momento del provisioning dell&#39;istanza [!DNL Marketo Optimizer].

È possibile creare le condizioni per le seguenti [!DNL Marketo Engage] attività:

* [!UICONTROL Modulo Marketo Engage compilato] - Corrisponde ai lead che hanno completato un modulo [!DNL Marketo Engage] specifico in qualsiasi punto del registro attività non obsoleto.
* [!UICONTROL Pagina Web Marketo Engage visitata] - Corrisponde ai lead che hanno visualizzato un URL specifico sul sito Web o [!DNL Marketo Engage] pagine di destinazione. Funziona direttamente utilizzando il codice di tracciamento di Munchkin installato sul tuo sito.
* [!UICONTROL Collegamento selezionato nella pagina Web di Marketo Engage] - Corrisponde ai lead che hanno fatto clic su un collegamento o una risorsa specifica in una pagina tracciata.
* [!UICONTROL E-mail Marketo Engage inviata] - Corrisponde ai lead a cui [!DNL Marketo Engage] ha tentato di inviare un&#39;e-mail specifica, tenendo conto delle azioni di distribuzione precedenti agli hard bounce o alle accettazioni del server.
* [!UICONTROL E-mail Marketo Engage recapitata] - Corrisponde a un lead il cui server di posta (MX) ha restituito una risposta di esito positivo (un messaggio OK 250) al server di invio [!DNL Marketo Engage].
* [!UICONTROL E-mail Marketo Engage non recapitata] - Corrisponde ai lead che hanno riscontrato un errore irreversibile (consegna permanente non riuscita) in un invio e-mail specifico o in un intervallo di tempo.
* [!UICONTROL E-mail non recapitate in Marketo Engage] - Corrisponde a lead le cui e-mail hanno subito un errore di consegna temporaneo (ad esempio, una casella in entrata completa o un server offline) anziché un errore permanente irreversibile.
* [!UICONTROL Annullamento dell&#39;iscrizione all&#39;e-mail di Marketo Engage] - Corrisponde ai lead che hanno rinunciato alle e-mail di marketing non operative. In questo caso, [!DNL Marketo Engage] aggiorna automaticamente il valore del campo `Unsubscribed` del lead in `true`, eliminandoli dagli invii di e-mail standard futuri.
* [!UICONTROL E-mail Marketo Engage aperta] - Corrisponde ai lead che hanno aperto un&#39;e-mail [!DNL Marketo Engage] tracciata.
* [!UICONTROL Collegamento selezionato nell&#39;e-mail di Marketo Engage] - Corrisponde ai lead che hanno fatto clic su un collegamento (o un collegamento specifico) all&#39;interno di un&#39;e-mail di [!DNL Marketo Engage].

>[!ENDSHADEBOX]

### Aggiungere un nodo di percorsi suddivisi

1. Passa all’area di lavoro del percorso.

1. Fare clic sull&#39;icona più ( **+** ) in un percorso e scegliere **[!UICONTROL Dividi percorsi]**.

   ![Fai clic sull&#39;icona Aggiungi nel percorso del percorso](./assets/person-journey-canvas-add-node.png){width="200"}

1. Per definire una condizione applicabile a _[!UICONTROL Percorso 1]_, fare clic su **[!UICONTROL Applica condizione]**.

1. Per definire il percorso di divisione, aggiungi uno o più filtri nell’editor delle condizioni.

   * Trascina e rilascia uno dei filtri persone dalla navigazione a sinistra e completa la definizione della corrispondenza.

   * Fare clic su **[!UICONTROL Aggiungi vincolo]** per ogni vincolo che si desidera utilizzare per perfezionare la corrispondenza del filtro.

     ![Dividi nodo percorso - filtro persona corrispondente per condizione percorso](./assets/journey-node-split-conditions-people.png){width="700" zoomable="yes"}

   * Affina le condizioni applicando la **[!UICONTROL logica filtro]** nella parte superiore. Scegli di soddisfare tutte le condizioni o una condizione qualsiasi.

   * Fai clic su **[!UICONTROL Fine]**.

1. Per aggiungere altri percorsi, fare clic su **[!UICONTROL Aggiungi percorso]** e ripetere i passaggi precedenti per aggiungere le condizioni applicabili al percorso.

   È inoltre possibile etichettare ogni percorso in base a queste condizioni o utilizzare le etichette predefinite.

1. Se necessario, riordinare i percorsi in base alla priorità desiderata per la suddivisione.

   Il filtro dei percorsi viene valutato in ordine decrescente. Ogni persona procede lungo il primo percorso che corrisponde a.

   Fai clic sulle frecce su e giù in alto a destra di ciascuna scheda di percorsi per spostarla in alto o in basso nell’elenco dei percorsi.

   <!-- ![Split path node - reorder paths](./assets/node-split-reorder-paths-people.png){width="500" zoomable="yes"} -->

1. Abilita l&#39;opzione **[!UICONTROL Altre persone]** per aggiungere un percorso predefinito per le persone che non corrispondono ai percorsi definiti.

   Se questa opzione non è abilitata, le persone che non corrispondono a un segmento/percorso definito si spostano oltre la divisione e procedono al passaggio successivo nel percorso.

Dopo aver definito le condizioni per ogni percorso, puoi aggiungere nodi di evento o azione da applicare alle persone presenti in un percorso.

## Unisci percorsi nodi

1. Passa all’area di lavoro del percorso e individua il nodo dei percorsi suddivisi con due o più percorsi.

   Ogni percorso deve avere una combinazione di nodi azione ed evento.

1. Fai clic sull&#39;icona più ( **+** ) alla fine di uno di questi percorsi e scegli **[!UICONTROL Unisci percorsi]** dalle opzioni visualizzate.

1. Nelle proprietà del nodo a destra, seleziona i percorsi che desideri unire.

   <!-- ![Journey node - merge paths](./assets/node-merge-select-paths.png){width="600" zoomable="yes"} -->

   A questo punto, i percorsi vengono uniti in modo che le persone dei percorsi selezionati si combinino in un singolo percorso che può continuare a progredire attraverso il percorso.

1. Se necessario, puoi annullare l’unione dei percorsi tornando alle proprietà del nodo percorsi unione e deselezionando la casella di controllo per tutti i percorsi che desideri rimuovere.