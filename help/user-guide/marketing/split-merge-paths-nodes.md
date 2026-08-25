---
title: Dividere e unire i nodi dei percorsi
description: Scopri come utilizzare suddividere e unire i nodi dei percorsi nei percorsi di persone per segmentare le persone in percorsi distinti in base a condizioni definite, quindi riunirle in un punto comune a valle.
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '660'
ht-degree: 0%

---

# Dividere e unire i nodi dei percorsi

Utilizza nodi di percorsi suddivisi e uniti in percorsi di persone per segmentare le persone in percorsi distinti in base alle condizioni che definisci, quindi riunisci nuovamente tali percorsi in modo che il percorso possa continuare. I percorsi di suddivisione consentono di personalizzare azioni ed eventi per segmenti di pubblico specifici, mentre i percorsi di unione riuniscono tali segmenti in un punto comune a valle.

## Dividere i nodi dei percorsi

Utilizza i nodi suddivisi per segmentare le persone in base alle condizioni definite. Crea percorsi per l’elenco dei tipi di pubblico in base alle condizioni, definisci ogni percorso con nodi di azione ed evento per il segmento, quindi combina i percorsi e continua il percorso.

Un nodo Percorsi suddivisi definisce uno o più percorsi segmentati in base ai filtri delle persone.

<!-- A split based on a people filter is automatically closed with a merge paths node so that all people can move forward to the next step. Split by people paths can include only people actions. These paths cannot be split again and automatically join back. _not currently true_ -->

_&#x200B;**Funzionamento di un percorso suddiviso per nodo persone**&#x200B;_

* La valutazione di ciascun percorso è dall&#39;alto verso il basso. Se una persona corrisponde per il primo e il secondo percorso, procede solo lungo il primo percorso.
* Il nodo supporta la definizione di un percorso _Altre persone_, in cui è possibile aggiungere azioni o eventi per le persone che non corrispondono a uno dei segmenti o percorsi definiti.

### Filtri corrispondenti

Per ogni percorso definito per il nodo, utilizza i seguenti tipi di filtro per far corrispondere le persone in base a una o più condizioni:

* Cronologia attività: puoi definire un percorso in base all’attività della persona in relazione a:

  * Messaggi e-mail
  * Modifica del valore dei dati

* Attributi della persona: definisce una condizione in base agli attributi di una persona, ad esempio paese, qualifica professionale, persona dervived o iscrizione all’elenco.

### Aggiungere un nodo di percorsi suddivisi

1. Passa all’area di lavoro del percorso.

1. Fare clic sull&#39;icona più ( **+** ) in un percorso e scegliere **[!UICONTROL Dividi percorsi]**.

   ![Fai clic sull&#39;icona Aggiungi nel percorso del percorso](./assets/person-journey-canvas-add-node.png){width="200"}

1. Per definire una condizione applicabile a _[!UICONTROL Percorso 1]_, fare clic su **[!UICONTROL Applica condizione]**.

1. Nell’editor delle condizioni, aggiungi uno o più filtri per definire il percorso di divisione.

   * Trascina e rilascia uno dei filtri persone dalla navigazione a sinistra e completa la definizione della corrispondenza.

   * Ottimizza le condizioni applicando la **[!UICONTROL logica filtro]** nella parte superiore. Scegli di soddisfare tutte le condizioni o una condizione qualsiasi.

     <!-- ![Split path node - conditions person filter logic](./assets/node-split-conditions-people.png){width="700" zoomable="yes"} -->

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

   Ogni percorso deve avere una combinazione di azioni ed eventi su ogni percorso.

1. Fai clic sull&#39;icona più ( **+** ) alla fine di uno di questi percorsi e scegli **[!UICONTROL Unisci percorsi]** dalle opzioni visualizzate.

1. Nelle proprietà del nodo a destra, seleziona i percorsi che desideri unire.

   <!-- ![Journey node - merge paths](./assets/node-merge-select-paths.png){width="600" zoomable="yes"} -->

   A questo punto, i percorsi vengono uniti in modo che le persone dei percorsi selezionati si combinino in un singolo percorso che può continuare a progredire attraverso il percorso.

1. Se necessario, puoi annullare l’unione dei percorsi tornando alle proprietà del nodo percorsi unione e deselezionando la casella di controllo per tutti i percorsi che desideri rimuovere.