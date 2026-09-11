---
title: Scoring Studio
description: Scopri Scoring Studio in Adobe Marketo Optimizer, compresi l’elenco di modelli, l’area di lavoro, le colonne delle dimensioni, le schede di segnale, i segmenti principali e la pubblicazione.
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2:
  - id: 1650dadf-b034-5ac9-a309-77ad1e2f5035
source-git-commit: 96a923c923a6290b9d90e4ffc8e161d78f029c47
workflow-type: tm+mt
source-wordcount: 897
ht-degree: 2%

---


# Scoring Studio

Scoring Studio include un elenco di modelli, un&#39;area di lavoro modificabile per ogni modello e l&#39;[interfaccia chat di Collaborator](../agents/chat-interface.md). Utilizza l’area di lavoro per rivedere o regolare direttamente dimensioni e segnali, mentre Collaboratore continua a proporre modifiche nel linguaggio naturale insieme a te. Per informazioni sulla creazione di un modello da un prompt, vedere [_Creare modelli di punteggio personalizzati_](../agents/lead-scoring-model.md).

## Elenco modelli {#model-list}

L’elenco dei modelli è la vista di destinazione di Scoring Studio. Ogni modello di punteggio nell&#39;istanza [!DNL Marketo Optimizer] viene visualizzato come righe in una tabella o come schede se si passa alla visualizzazione griglia.

| Colonna | Descrizione |
| --- | --- |
| Nome | Selezionare il nome di un modello per aprirlo nell&#39;area di lavoro. |
| Stato | _[!UICONTROL Attivo]_, _[!UICONTROL Bozza]_ o _[!UICONTROL Archiviato]_. |
| Dimensioni | Il numero di quote nel modello. |
| Segnali | Il numero di segnali nel modello. |
| Ultima modifica | Data dell’ultima modifica apportata al modello. |
| Ultima modifica eseguita da | Persona che ha modificato per ultima il modello. |
| Creato il | Data di creazione del modello. |
| Creato da | Persona che ha creato il modello. |

![L&#39;elenco dei modelli di Scoring Studio mostra i modelli di punteggio attivi con le relative dimensioni, i segnali e i dettagli dell&#39;ultima modifica.](./assets/scoring-studio-ui.png){width="800" zoomable="yes"}

Utilizza il campo di ricerca per trovare un modello per nome o filtrare l’elenco per stato. Seleziona il **[!UICONTROL altro menu]** di una riga per **[!UICONTROL modificare]**, **[!UICONTROL duplicare]**, **[!UICONTROL archiviare]** o **[!UICONTROL eliminare]** un modello.

Un modello attivo è di sola lettura. Per modificarlo, duplicarlo e modificare il duplicato. Quindi, archivia l’originale e pubblica la copia modificata.

## Area di lavoro modello {#model-canvas}

Selezionando il nome di un modello, questo viene aperto nell&#39;area di lavoro. Ogni modello aperto viene visualizzato come una scheda propria, che consente di lavorare su più modelli. L&#39;area di lavoro è organizzata in schede, incluse **[!UICONTROL Regole]** e **[!UICONTROL Lead]**.

Nella scheda **[!UICONTROL Regole]**, ogni dimensione nel modello è una colonna nell&#39;area di lavoro. Ogni intestazione di colonna mostra il nome della dimensione e il totale del relativo punto rispetto al relativo limite, ad esempio `20 / 30 pts`, con una barra di avanzamento che si riempie man mano che i segnali contribuiscono ai punti.

![L&#39;area di lavoro della scheda Regole mostra tre colonne di dimensione, Coinvolgimento e-mail, Adattamento profilo e Attività recente, ciascuna con schede di segnale e punti.](./assets/scoring-studio-model-rules-tab.png){width="700" zoomable="yes"}

All&#39;interno di ogni dimensione, ogni segnale appare come una scheda che mostra il suo nome, il suo valore e la frequenza corrispondente (ad esempio, `1 time / day`) o `Static` per i segnali basati su attributi che non dipendono dall&#39;attività.

Quando viene rilevato un pattern tra più attività, è possibile combinarle in un&#39;unica scheda di segnale composito che riepiloga ogni condizione.

## Configurare un segnale {#configure-signal}

Per rivedere o modificare un segnale, eseguire la procedura seguente.

1. Seleziona **[!UICONTROL Modifica bozza]**.

1. Seleziona una scheda di segnale nell’area di lavoro.

   Il pannello delle proprietà si apre sul lato destro dell’area di lavoro.

   ![L&#39;area di lavoro della scheda Regole mostra una scheda di segnale selezionata e il relativo pannello delle proprietà con tipo di segnale, tipo di attività, condizioni e punti.](./assets/scoring-studio-model-selected-signal.png){width="700" zoomable="yes"}

1. Seleziona l&#39;icona **[!UICONTROL Modifica]** ( ![Modifica icona](../assets/do-not-localize/icon-react-edit.svg) ), quindi aggiorna le proprietà del segnale:

   * In **[!UICONTROL Segnale]**, conferma il tipo di segnale (un&#39;attività o un attributo) e l&#39;attività o l&#39;attributo specifico che ha ottenuto.

   * In **[!UICONTROL Attiva questo il]**, imposta le condizioni che devono corrispondere.

     Aggiungi gli elementi da utilizzare, ad esempio pagine specifiche, e se **[!UICONTROL Uno qualsiasi di]** o **[!UICONTROL Tutti]** le condizioni devono essere vere.

   * In **[!UICONTROL Punti]**, imposta il numero di punti in cui il segnale contribuisce.

     Facoltativamente, impostare un **[!UICONTROL Cap]** per limitare il numero di punti che può contribuire a persona. Collaboratore mostra un intervallo di punti suggerito in base agli altri segnali del modello.

   * Per i segnali basati sull&#39;attività, impostare la **[!UICONTROL Frequenza]** richiesta prima dei punti di aggiudicazione del segnale.

     Facoltativamente, impostare una percentuale di **[!UICONTROL Decadimento]** che riduca i punti del segnale dopo un numero di giorni impostato.

   * Abilita l&#39;opzione **[!UICONTROL Evita di assegnare gli stessi punteggi due volte]** per assegnare punti solo una volta a persona, indipendentemente dal numero di volte in cui si verifica l&#39;attività.

     Disattiva l’opzione per aggiudicare punti ogni volta che si verifica l’attività. Questa impostazione è attivata per impostazione predefinita.

1. Seleziona **[!UICONTROL Salva]** per applicare le modifiche e tornare all&#39;area di lavoro.

## Segmento lead {#lead-segment}

Ogni modello di punteggio assegna un punteggio a un segmento di lead, un riferimento a un elenco di persone esistente anziché alle regole definite in Scoring Studio. Quando viene creato un modello, viene selezionato un elenco corrispondente o ne viene creato uno nuovo.

Per modificare l&#39;elenco, selezionare la scheda **[!UICONTROL Lead]**, quindi selezionare **[!UICONTROL Change]** accanto al segmento di lead.

![Nella scheda Lead viene visualizzata la scheda del segmento di lead con un elenco di persone a cui si fa riferimento, un collegamento Visualizza elenco persone e un collegamento Modifica.](./assets/scoring-studio-model-lead-tab.png){width="700" zoomable="yes"}

Un segmento di lead utilizza uno dei due tipi di elenco seguenti:

* **Elenco statico**: gruppo fisso di persone acquisito al momento della creazione dell&#39;elenco.
* **Elenco avanzato**: un elenco che rivaluta le regole di appartenenza ogni volta che viene eseguito il modello, in modo che il segmento rifletta sempre i criteri dell&#39;elenco.

L&#39;anteprima del modello mostra il nome del segmento, il numero di membri e un collegamento **[!UICONTROL Visualizza elenco persone]** che apre direttamente l&#39;elenco. Per ulteriori informazioni sulla gestione degli elenchi, vedere [_Elenchi persone_](../audiences/people-lists.md).

Se l’elenco a cui si fa riferimento è vuoto o successivamente rimosso, il modello interrompe il punteggio invece di tornare all’intero pubblico. Nessun lead viene valutato finché non si assegna un elenco valido non vuoto.

Sotto il segmento del lead, la scheda **[!UICONTROL Nome campo punteggio]** mostra l&#39;attributo del lead in cui il modello scrive il punteggio. Per impostazione predefinita, il nome del campo corrisponde al nome del modello. Seleziona **[!UICONTROL Modifica]** per rinominarlo.

## Pubblicazione e pianificazione {#publish-schedule}

Quando il modello è pronto, seleziona **[!UICONTROL Pubblica]**. Scegli con quale frequenza il modello classifica il pubblico: giornaliero, settimanale o mensile.

Per informazioni sull&#39;intero processo di pubblicazione, incluso il modo in cui [!DNL Marketo Optimizer] esegue automaticamente il provisioning di un campo di punteggio, vedere [_Pubblicare un modello di punteggio_](../agents/lead-scoring-model.md#publish-model).
