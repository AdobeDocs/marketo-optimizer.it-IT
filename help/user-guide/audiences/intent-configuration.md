---
title: Configurazione intento
description: Scopri come configurare i pesi delle attività che guidano il modello di punteggio intento della persona, dai valori predefiniti suggeriti dall’intelligenza artificiale all’attivazione di un modello di ponderazione personalizzato.
TQID: 'https://experienceleague.adobe.com/ZL9RJqD-OZkIgFMpwJ4Cz-FW-463w6OJyEHAe5uJuec'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2: id: 1650dadf-b034-5ac9-a309-77ad1e2f5035
topic_v2: id: f8667931-f646-4dd3-af2a-b9d0cb8098ad
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 1322
ht-degree: 2%

---


# Configurazione intento

Un singolo set standardizzato di pesi per l’attività non funziona tra i clienti. Ciò che segnala un reale intento di acquisto varia a seconda del business. Configura e attiva un modello intento per specificare ciò che ti interessa, ad esempio se un modulo riempie i segnali più di un clic e-mail, invece di ereditare un valore predefinito globale.

Gli strumenti del pannello **[!UICONTROL Configurazione intento]** controllano il conteggio di ogni attività di intento del lead rispetto al punteggio di intento di una persona. È l’unico input configurabile nel punteggio intento. Altri fattori, come rilevanza dei contenuti, decadimento e soglie, sono gestiti dal sistema. È disponibile tramite l&#39;abilità di configurazione [Intent](../agents/intent.md#configure-model).

Apri il pannello utilizzando uno dei due metodi dell&#39;interfaccia [chat](../agents/chat-interface.md) di Coworker:

* Immettere il comando `/intent-configuration`.
* Fai clic su **[!UICONTROL +]**, seleziona **[!UICONTROL Usa un&#39;abilità agente]**, seleziona la scheda **[!UICONTROL Intento]**, quindi fai clic su **[!UICONTROL Configurazione intento]**.

![Il pannello di configurazione intento è stato aperto dall&#39;interfaccia chat](./assets/intent-configuration-panel.png){width="700" zoomable="yes"}

## Vista a elenco modelli

La pagina di destinazione nel pannello mostra **[!UICONTROL la ponderazione del punteggio intento]**, con il conteggio totale dei modelli sotto il titolo, un campo di ricerca da filtrare per nome e una tabella ordinabile:

| Colonna | Note |
| --- | --- |
| [!UICONTROL Nome] | Ordinabile, ordinamento predefinito |
| [!UICONTROL Stato] | _[!UICONTROL Attivo]_ (punto verde), _[!UICONTROL Bozza]_ (punto arancione), _[!UICONTROL Archiviato]_ (punto grigio) |
| [!UICONTROL Data di creazione] | Abbreviato, data completa al passaggio del mouse |
| [!UICONTROL Ultimo aggiornamento] | Abbreviato, data completa al passaggio del mouse |
| [!UICONTROL Ultimo aggiornamento effettuato da] | Nome utente troncato, nome completo al passaggio del mouse |

Solo un modello può essere _[!UICONTROL Attivo]_ alla volta ed è il punteggio guida del modello. Ogni altro modello si trova in uno stato _[!UICONTROL Bozza]_ (in corso di modifica, non ancora attivo) o _[!UICONTROL Archiviato]_ (un precedente modello _[!UICONTROL Attivo]_, retrocesso automaticamente quando ne viene attivato uno nuovo).

Fate clic su una riga per aprire la vista dei dettagli del modello.

## Vista dettagli modello

La vista dei dettagli mostra il nome del modello, il badge di stato, la marca temporale dell&#39;ultimo salvataggio e una breadcrumb che mostra **[!UICONTROL la ponderazione del punteggio intento]** e il nome del modello, su cui puoi fare clic per tornare all&#39;elenco.

Nella vista Dettaglio sono elencate le attività di intento del buyer e il livello di importanza che ogni attività contribuisce al punteggio di intento della persona. Il catalogo attività è fisso e solo i livelli possono cambiare. Questi livelli sono indipendenti: non è necessario sommare fino a un totale. È possibile attivare una sola versione del modello di ponderazione alla volta. Per apportare modifiche, duplica la versione corrente e modifica la copia.

![Visualizzazione dettagli per un modello intento attivo](./assets/intent-configuration-model-detail.png){width="550" zoomable="yes"}

Un campo di ricerca filtra le righe dell’attività per nome. La tabella stessa:

| [!UICONTROL Attività intento] | [!UICONTROL IA suggerita] | [!UICONTROL Ponderazione] | [!UICONTROL Reimposta] |
| --- | --- | --- | --- |
| Ad esempio, Aggiungi a opportunità, Compila modulo, Fai clic su E-mail, Fai clic su collegamento, Apri e-mail, Annulla iscrizione e-mail, Visita pagina web, Pone domande nel webinar, Download di risorse nel webinar, Momento di interesse, Risposta al sondaggio nel webinar, Aggiorna opportunità | Sola lettura | Menu a discesa, modificabile nei modelli bozza | Icona **↺**: reimposta la riga al valore suggerito da IA |

**Ponderazione dei livelli** (stessa scala sia per le colonne Suggested di IA che per le colonne Ponderazione):

| Livello | Valore |
| ---| --- |
| [!UICONTROL Nessun peso] | 0 |
| [!UICONTROL Bassa] | 30 |
| [!UICONTROL Non grave] | 40 |
| [!UICONTROL Normale] | 60 |
| [!UICONTROL Importante] | 90 |
| [!UICONTROL Vitale] | 100 |

![Modifica del valore per l&#39;attività Aggiungi all&#39;opportunità in un modello intento bozza](./assets/intent-configuration-model-edit.png){width="550" zoomable="yes"}

Se si imposta un&#39;attività su **[!UICONTROL Nessun peso]** (0), il punteggio non viene assegnato completamente. Il sistema esclude attualmente **[!UICONTROL Annulla sottoscrizione e-mail]** per impostazione predefinita utilizzando questo metodo.

Fai clic su **[!UICONTROL Reimposta tutto su suggerito]** sopra la tabella per ripristinare ogni riga al relativo valore suggerito da IA.

### Creare e attivare un modello

Per creare e attivare un nuovo modello di ponderazione, effettuate le seguenti operazioni.

1. Inizia da un modello _[!UICONTROL Bozza]_ esistente.

   Puoi anche fare clic su **[!UICONTROL Duplica]** per il modello _[!UICONTROL Attivo]_ corrente per clonarne i pesi in una nuova bozza.

1. Regola i pesi riga per riga per riflettere ciò che conta per la tua azienda.

   Ad esempio, puoi effettuare il downgrade di un&#39;attività a segnale basso a **[!UICONTROL Banale]** o l&#39;aggiornamento di un&#39;attività a segnale alto a **[!UICONTROL Importante]** o **[!UICONTROL Vitale]**.

1. Fai clic su **[!UICONTROL Salva]**.

   Il salvataggio richiede di attivare immediatamente il modello.

1. Conferma l’attivazione.

La conferma lo rende il nuovo modello _[!UICONTROL Attivo]_ e lo abbassa automaticamente a _[!UICONTROL Archiviato]_. Può essere attivo un solo modello alla volta.

### Colonna suggerita da IA

La colonna Suggested di IA è un punto di partenza, non un consiglio addestrato.

* Una chiamata di completamento LLM gestisce tutte le attività contemporaneamente per un tenant, non una chiamata per attività.

* Per ogni attività, il modello legge solo il nome e la descrizione, quindi seleziona un livello di peso in base alla conoscenza generale del comportamento dell’acquirente B2B. Ad esempio, considera cosa **[!UICONTROL Compila modulo]** o **[!UICONTROL Fai clic su E-mail]** in genere segnala per un acquirente B2B. Non ha accesso ai dati cliente del tenant, ai record CRM o ai pattern di coinvolgimento storici e non è attualmente specifico del tenant o dell’abbonamento.

* L&#39;output compila `SUGGESTED_WEIGHT_VALUE` in `IBG_INTENT_ACTIVITY_WEIGHT` al momento della creazione del modello e successivamente rimane statico. Non viene aggiornato durante la modifica della colonna Ponderazione.

* Ogni riga di attività ha sempre un valore suggerito popolato. Nessuno viene lasciato vuoto.

Rivedi e regola ogni riga per riflettere il tuo contesto aziendale. I valori suggeriti sono un valore di default ragionevole, non un modello ottimizzato.

## Azioni su un modello

Puoi gestire un modello in base al suo stato.

| Azione | Disponibile per | Cosa succede |
| --- | --- | --- |
| **[!UICONTROL Duplica]** | Attivo, Bozza | Apre un modale con titolo **[!UICONTROL Duplicato]**, con un campo Nome precompilato e i pulsanti **[!UICONTROL Annulla]** e **[!UICONTROL Duplica]**. La conferma crea un nuovo modello _[!UICONTROL Bozza]_ con gli stessi pesi, che si apre direttamente nella vista dei dettagli. |
| **[!UICONTROL Attiva]** | Solo bozza (disponibile anche come prompt subito dopo il salvataggio) | Promuove la bozza a _[!UICONTROL Attivo]_ e abbassa automaticamente di livello il modello precedentemente Attivo a _[!UICONTROL Archiviato]_. |
| **[!UICONTROL Elimina]** | Solo bozza | Richiede una finestra di dialogo di conferma prima dell&#39;eliminazione definitiva. Questa azione è irreversibile. I modelli attivi non possono essere eliminati. |

Poiché solo i modelli bozza sono modificabili, il flusso di lavoro normale consiste nel fare clic su **[!UICONTROL Duplica]** per il modello _[!UICONTROL Attivo]_ corrente, modificare il peso della bozza, quindi fare clic su **[!UICONTROL Salva]**. Puoi attivarlo immediatamente o in un secondo momento utilizzando il pulsante **[!UICONTROL Attiva]**.

## Ponderazione dei calcoli nei punteggi intento

La colonna **[!UICONTROL Ponderazione]** visualizza il numero utilizzato nel punteggio giornaliero, letto dalla riga per il modello _[!UICONTROL Attivo]_. Tre fattori determinano il punteggio intento di un lead:

1. **Il peso configurato qui** (`WEIGHT_VALUE`) per ogni attività. Inizia dal suggerimento di IA, ma può essere ignorato per tenant. Viene utilizzata solo la riga associata al modello _[!UICONTROL Active]_, pertanto non è necessario rilasciare il codice per cambiare lo spessore.

1. **Rilevanza del contenuto**: non configurabile qui. Il sistema estrae parole chiave da contenuto o risorse correlate all’attività e valuta la corrispondenza tra il contenuto e una parola chiave, un prodotto o una categoria da 0 a 1.

1. **Frequenza**: quante volte un lead ha interagito con quel contenuto, considerato nella media tra le interazioni di una persona.

Formalmente, per coinvolgimento: `activity weight × content relevance`, viene calcolata la media in un **punteggio giornaliero** con un decadimento esponenziale di **7 giorni** applicato in modo che l&#39;attività recente domini, quindi min-max viene normalizzato a 0 a 1 nella popolazione corrente e inserito nel bucket:

| Punteggio finale | Livello intento |
| --- | --- |
| > 0.6 | Alta |
| > 0.2 | Canale |
| Altrimenti | Bassa |

### Rilevanza dei contenuti

Per le attività basate sul web, il sistema controlla l’URL della risorsa e l’azienda associata, quindi deriva le parole chiave pertinenti dalla tassonomia di tale azienda. Ad esempio, un URL associato a [!DNL Intuit] presenta parole chiave come _tax_ o _payroll_. L&#39;effettivo coinvolgimento di un lead con tale contenuto, ad esempio la visualizzazione di una pagina [!DNL TurboTax] o [!DNL QuickBooks], viene confrontato con tali parole chiave per determinare a quale prodotto specifico è associato l&#39;interesse. Per le attività non Web come _[!UICONTROL Momento di interesse]_ (inclusi gli eventi non in linea), il modello valuta la descrizione o il contenuto del momento, ad esempio un argomento del webinar non in linea, anziché il tipo di attività. La rilevanza viene determinata dal contenuto e non dalla categoria dell’evento.

## Limitazioni note

Le seguenti limitazioni si applicano oggi alla configurazione dell’intento.

* **Nessuna attività personalizzata o definita dal tenant al momento.** Il catalogo attività è fisso e [!DNL Marketo Engage] è l&#39;unica origine di verità. Per ottenere il punteggio, è necessario che un&#39;attività sia registrata in [!DNL Marketo Engage]. È in corso l&#39;ambito di una colonna futura per le attività definite dal tenant.
* **Nessuna acquisizione con intento di terze parti oggi**, ad esempio da [!DNL Demandbase], [!DNL ZoomInfo] o [!DNL 6sense]. Questo aggiornamento è pianificato per le versioni successive. Fino ad allora, la soluzione consiste nel generare il pubblico nello strumento di terze parti e inviarlo direttamente in [!DNL Marketo Engage] o [!DNL Marketo Optimizer], ignorando il punteggio intento per quel segnale.
* **Nessuna esportazione nativa** dal pannello di ponderazione o dai report intento. Consulta [Seguito del report](../agents/intent.md#report-follow-up) per i prompt che trasformano i risultati del report in un elenco di persone.
