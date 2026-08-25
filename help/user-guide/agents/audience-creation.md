---
title: Creare tipi di pubblico per i programmi
description: Utilizza l’abilità Creazione di tipi di pubblico in Marketo Optimizer per creare elenchi di persone, adattare gli elenchi avanzati di Marketo Engage e modificare le regole degli elenchi in chat.
source-git-commit: c00dc1d3f3028ece56905f9f1018605147b0ac20
workflow-type: tm+mt
source-wordcount: '1464'
ht-degree: 0%

---

# Creare tipi di pubblico per i programmi

In [!DNL Adobe Marketo Optimizer], [_elenchi di persone_](../audiences/people-lists.md) definiscono il pubblico per i percorsi di persone, sia come elenchi basati su filtri dinamici che vengono aggiornati automaticamente, sia come elenchi statici con appartenenza fissa. Dall&#39;interfaccia di [chat](./chat-interface.md), l&#39;_creazione pubblico_ [abilità](./skills.md) crea, adatta e modifica gli elenchi di persone tramite una conversazione guidata.

* **Abilità** - `audience-creation` e `people-list-comparison`
* **Chiamata** - Descrive direttamente i criteri del pubblico, carica un elenco avanzato [!DNL Marketo Engage] o denomina un elenco esistente da modificare
* **Legge da/scrive in** - [!DNL Marketo Optimizer]; legge [!DNL Marketo Engage] durante l&#39;adattamento degli elenchi avanzati

## Flussi di lavoro supportati {#workflows}

Cooker supporta tre flussi di lavoro per la creazione di tipi di pubblico e determina quale applicare dalla richiesta. Se il tuo intento è ambiguo, lo richiede prima di procedere.

| Flusso di lavoro | Quando utilizzarlo | Esempio di prompt |
|---|---|---|
| **Crea da zero** | Si desidera creare un nuovo elenco di persone definito in base a criteri o appartenenza. | _&quot;Crea un elenco dinamico di VP del marketing presso aziende SaaS in Nord America.&quot;_ |
| **Adattare un elenco avanzato [!DNL Marketo Engage]** | Disponi di un elenco avanzato [!DNL Marketo Engage] o di una campagna avanzata e desideri un elenco di persone equivalente. | _&quot;Adattare l&#39;elenco smart di Marketo a un elenco di persone.&quot;_ (allega la risorsa) |
| **Modifica un elenco esistente** | Desideri aggiungere o sostituire le regole in un elenco già esistente. | _&quot;Aggiungere una regola all&#39;elenco &#39;Enterprise Trials&#39; per ottenere un punteggio di lead superiore a 50.&quot;_ |

## Creare un elenco di persone da zero {#create-from-scratch}

Prima di generare qualsiasi elemento, Collaborator conferma tutte e quattro le operazioni seguenti. Chiede tutte quelle che mancano — in un singolo messaggio.

1. **Regole/criteri**: descrizione in linguaggio semplice di chi appartiene all&#39;elenco.
1. **Nome** - Chiamata dell&#39;elenco.
1. **Posizione** — Quale programma deve risiedere l&#39;elenco. Specifica un nome per il programma e il collaboratore lo trova; in caso di più corrispondenze, richiede di scegliere.
1. **Tipo**: dinamico (basato su filtro, aggiornamento automatico) o statico (appartenenza fissa). Questo è obbligatorio — Collaboratore non indovinerà; se non specifichi, chiede.

### Elenchi dinamici {#dynamic-lists}

Per gli elenchi dinamici, Collaboratore suggerisce in modo proattivo di includere attributi di personalizzazione per arricchire il targeting. Questi attributi sono **_inclusi per impostazione predefinita. Si rinuncia, non in_**:

| Attributo | Perché aiuta |
|---|---|
| **Persona derivata** | Utente tipo buyer dedotto dall’intelligenza artificiale per il targeting di contenuti basato su utente tipo. |
| **Intento derivato** | Segnali dedotti di intento di acquisto che emergono dai conti di mercato. |
| **Livello di coinvolgimento** | Livello di coinvolgimento calcolato che dà priorità ai contatti coinvolti. |

Informare il collaboratore se si desidera rimuovere uno di questi elementi prima di procedere.

### Elenchi statici {#static-lists}

* **Statico, nessun criterio**. L&#39;elenco verrà creato vuoto e sarà possibile aggiungere membri manualmente.
* **Statico da criteri (istantanea)** — Collaboratore crea il set corrispondente e copia tali persone in. La popolazione è asincrona - Collaboratore conferma che l’elenco è stato creato, ma nota che la visualizzazione potrebbe richiedere alcuni minuti. Non dichiarerà che l&#39;elenco è pronto immediatamente.

## Scheda Revisione {#review-card}

Non viene creato nulla finché non lo approvi. Dopo aver descritto i criteri, Coworker presenta una scheda interattiva _Revisione creazione elenco persone_ (per gli adattamenti da elenchi [!DNL Marketo Engage], la scheda si chiama _Revisione conversione elenco persone_).

Ogni riga nella scheda rappresenta una condizione:

| Colonna | Significato |
|---|---|
| **Requisiti** (o il nome dell&#39;elenco [!DNL Marketo Engage] per gli adattamenti) | La richiesta originale o il filtro Marketo di origine. |
| **(regola)** | Regola effettiva basata su attributi generata per la condizione. |
| **Includi** | Casella di controllo per mantenere o eliminare la regola. |

**Livelli di affidabilità:**

* **Affidabilità elevata** righe con corrispondenza pulita e verificate per impostazione predefinita.
* **Affidabilità bassa** righe (mappature approssimative o qualsiasi elemento contrassegnato) vengono visualizzate con un indicatore di avviso e sono deselezionate per impostazione predefinita.
* Le righe che il sistema non è riuscito a mappare mostrano **&quot;Nessun equivalente trovato&quot;**. Queste righe non contengono alcuna regola e rimangono deselezionate.

Un _riepilogo conversione_ conteggia _N affidabilità elevata_ e _N affidabilità bassa_, con un suggerimento: le regole di affidabilità bassa sono deselezionate per impostazione predefinita; controllarle per includere o descrivere la modifica desiderata nella chat.

**Azioni scheda:**

* **Continua** — crea l&#39;elenco utilizzando solo le regole selezionate.
* **Descrivi le modifiche desiderate nella chat** — Precompila l&#39;input con _&quot;Desidero modificare: &quot;_ in modo da poter perfezionare; Coworker rigenera e mostra una nuova scheda, mantenendo le regole già approvate.

Puoi anche digitare un follow-up in qualsiasi momento (ad esempio, _&quot;è limitato anche alle aziende con più di 500 dipendenti&quot;_) e Coworker rigenera la scheda.

## Mappatura attributi {#attribute-mapping}

Quando descrivi i criteri, in Collaborator ogni condizione viene tradotta in un attributo reale e noto a livello di persona. Nella scheda Review possono essere visualizzati tre risultati:

1. **Corrispondenza (affidabilità elevata)** — La condizione viene mappata direttamente su un attributo (ad esempio, _&quot;email is acme.com&quot;_ corrisponde all&#39;attributo `email`). Selezionato per impostazione predefinita.
1. **Approssimativo (attendibilità bassa)** — L&#39;attributo disponibile più vicino differisce per nome o modello dati (ad esempio, un filtro Marketo _Importo_ approssimato come _Punteggio lead_). Viene mostrata con una nota che spiega la differenza; deselezionata per impostazione predefinita.
1. **Non trovato**. Impossibile eseguire il mapping della condizione ad alcun attributo noto. Visualizzato come _&quot;Nessun equivalente trovato&quot;_. Nessuna regola generata.

Questo è il motivo per cui un elenco che descrivi potrebbe avere meno regole rispetto alle condizioni specificate: le condizioni senza corrispondenza vengono visualizzate in modo esplicito anziché essere eliminate in modo invisibile all&#39;utente. Se i criteri importanti arrivano come &quot;non trovato&quot;, riformulali utilizzando il nome reale dell’attributo e Coworker tenta nuovamente.

>[!NOTE]
>
>Se mappi le colonne del foglio di calcolo ai campi (una scheda di mappatura campi con _Colonna Source_, _Campo di destinazione_, una percentuale di affidabilità e un elenco _Colonne non mappate_), questo è il flusso di importazione principale, non la creazione di tipi di pubblico. Consulta l&#39;[abilità import-lead](./skills.md#audiences-people).

## Modificare le regole per un elenco esistente {#edit-rules}

Quando viene richiesto di modificare le regole di un elenco già esistente, Collaboratore stabilisce quale elenco e quale modalità di modifica:

* **Aggiungi/Aggiungi** (impostazione predefinita per _&quot;aggiungi regole&quot;_, _&quot;aggiungi altre regole&quot;_). Le nuove regole vengono unite a quelle esistenti.
* **Sostituisci** (impostazione predefinita per _&quot;sostituisci regole&quot;_, _&quot;cambia regole in&quot;_) — le nuove regole sostituiscono tutte le regole esistenti nell&#39;elenco.

Collaboratore riepiloga ciò che verrà applicato e indica chiaramente se si tratta di aggiunta o sostituzione, quindi ti chiede di confermare prima di confermare. Dopo l’applicazione, riporta il conteggio totale delle regole e quanti sono stati aggiunti o sostituiti.

>[!NOTE]
>
>Le modifiche utilizzano un percorso in grado di riconoscere l’unione, pertanto un’operazione di &quot;aggiunta&quot; non sovrascrive mai in modo invisibile all’utente le regole esistenti.

## Sovrapposizione del pubblico {#overlap}

Chiedi a Collaboratore di confrontare due elenchi di persone (ad esempio, _&quot;Mostra la sovrapposizione tra &quot;Webinar Q3&quot; e &quot;Account organizzazione&quot;&quot;_) ed esegue il rendering di una scheda _Sovrapposizione elenco persone_:

* Un badge di intestazione che mostra il conteggio: **&quot;{N} in comune.&quot;**
* Una riga di statistiche con il conteggio totale dei membri di ogni elenco e la sovrapposizione come **&quot;X% di A · Y% di B.&quot;**
* Tabella dei membri delle persone in entrambi gli elenchi, con una colonna **Name** e una seconda colonna che è possibile indirizzare: **Email** (impostazione predefinita), **Company** o **Job Title** a seconda delle richieste.
* Fai clic su un nome per aprire la persona nell’area di lavoro.
* In assenza di sovrapposizione, la scheda indica chiaramente: _&quot;Nessun membro in comune tra questi due elenchi.&quot;_

**Limitazioni:**

| Limite | Dettaglio |
|---|---|
| **Dimensione tabella** | Mostra fino a 200 membri; oltre a ciò nota _&quot;Visualizzazione di 200 di N — chiedimi di perfezionare la query per limitare i risultati.&quot;_ |
| **Calcolo sovrapposizione** | Calcolato in base all’indirizzo e-mail; le persone senza e-mail sono escluse dall’intersezione. |
| **Dimensione elenco** | Legge approssimativamente i primi ~1.000 membri di ciascun elenco. Per gli elenchi più grandi, Collaboratore indica che i risultati sono parziali. |
| **Elenchi dinamici bozza** | Non può essere confrontato — un elenco che non è stato pubblicato non ha un segmento live. In Coworker viene richiesto di pubblicarlo prima o di utilizzare un elenco statico. |

## Convalida QA {#qa-validation}

Dopo aver creato o aggiornato un elenco, Collaboratore offre: _&quot;Verificare che l&#39;elenco sia configurato correttamente?&quot;_ Se si accetta, l’elenco viene recuperato e vengono segnalati i seguenti controlli:

| Verifica | Risultato |
|---|---|
| Elenco trovato nel programma/cartella corretto | Superato/non superato |
| Il conteggio dei filtri corrisponde a quello applicato | _N_ filtri/mancata corrispondenza |
| Attributi Personalization presenti (se inclusi) | Presente/mancante |
| Il nome dell’elenco corrisponde a quello richiesto | Superato/non superato |
| Conteggio membri stimato | _count_ o N/D |

## Limitazioni {#limitations}

| Limitazione | Dettaglio |
|---|---|
| **Adattamento a elenco statico da[!DNL Marketo Engage]** | Non puoi adattare un elenco statico di [!DNL Marketo Engage] (o un messaggio e-mail o un&#39;altra risorsa non filtrabile) a un elenco di persone. Gli elenchi statici sono ID membri espliciti e non possono essere espressi come filtri. Viene richiesto invece un elenco avanzato o una campagna avanzata. |
| **Filtri basati su attività e appartenenza** | Durante l&#39;adattamento da [!DNL Marketo Engage], i filtri come _E-mail aperta_, _Pagina Web visitata_, _Modulo compilato_, _Membro dell&#39;elenco_ e _Membro di Smart Campaign_ non hanno un equivalente dell&#39;elenco persone e vengono restituiti come &quot;Nessun equivalente trovato&quot;. |
| **Condizioni a livello aziendale** | Tradotto all’attributo a livello di persona più vicino, ove possibile (gli elenchi di persone funzionano sugli attributi di persona) e contrassegnato come a bassa affidabilità quando l’adattamento è assente. |
| **Logica AND/OR profondamente nidificata** | Una logica nidificata complessa può comprimere in un AND/OR di livello superiore; se ciò si verifica, viene annotato in coorte. |
| **Conflitti di nomi** | Non risolto automaticamente: se il nome viene utilizzato, viene richiesto un nome diverso anziché aggiungere automaticamente un suffisso. |
| **Approvazione richiesta** | Coworker non creerà né modificherà un elenco finché non farai clic su **[!UICONTROL Procedi]**, confermerai o concederai un via libera (_&quot;approvato&quot;_, _&quot;sembra buono&quot;_, _&quot;compilalo&quot;_). |
| **Popolazione snapshot statico** | L’appartenenza a elenchi statici creati dai criteri viene riempita in pochi minuti, non all’istante. |

