---
title: Creare un programma da una descrizione
description: Utilizza l’abilità Creazione di programmi in Marketo Optimizer per creare programmi, token, elenchi di persone e percorsi da una descrizione della campagna.
TQID: 'https://experienceleague.adobe.com/Bi7ZemHiGpKwxsYZkrfCyT5IzFAJ8ZTyFr8KxwO4z6w'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2:
  - id: 1650dadf-b034-5ac9-a309-77ad1e2f5035
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
  - id: a29661b8-f7a4-53d1-a9ac-fdec08c092e4
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 1110
ht-degree: 4%

---

# Creare un programma da una descrizione

In [!DNL Adobe Marketo Optimizer], [_programma_](../marketing/programs.md) è il contenitore principale per percorsi, elenchi di persone, token e configurazione all&#39;interno di una campagna. Dall&#39;[interfaccia chat](./chat-interface.md), l&#39;abilità di creazione del programma crea l&#39;intera struttura in modo completo, partendo dalla tua descrizione, ovvero il programma stesso, le sottocartelle, i token, gli elenchi di persone e i percorsi di persone, in un&#39;unica conversazione guidata.

* **Abilità** - `program-creation`
* **Richiamo** - Carica una descrizione e immetti _Crea un programma da questa descrizione_ / _Crea un programma da questa descrizione_ o descrivi direttamente la campagna
* **Legge da/scrive in** - [!DNL Marketo Optimizer]; legge anche la configurazione del tipo di programma dal tenant

## Caricamento breve

Fai clic sull&#39;icona _Allega_ nell&#39;input della chat per caricare il file, quindi descrivi ciò che desideri. Il testo del resoconto viene estratto e consegnato a Coworker come contesto (nella chat viene visualizzato un indicatore &quot;Campaign Brief uploaded: filename (NkB)&quot;).

### Tipi di file supportati

| Formato | Comportamento |
|---|---|
| `.txt`, `.md` | Leggi direttamente nel browser |
| `.pdf`, `.docx`, `.xlsx`, `.json`, `.csv` | Inviato al servizio di estrazione del testo back-end |

Un file con un nome contenente *brief* viene automaticamente taggato come resoconto di una campagna; in caso contrario, viene dedotto dal contesto.

### Limite di dimensioni

Il testo breve viene troncato a circa 30.000 caratteri (circa 7,5 K token) prima di raggiungere Coworker. I slip molto lunghi vengono tagliati a quel punto (indicato da una nota `(truncated to 29KB)`). Inserisci subito i dettagli essenziali della campagna.

## Contenuto breve consigliato

L&#39;immissione del flusso legge le istruzioni per i seguenti input, includendo il maggior numero possibile di input:

* Nome del programma e breve descrizione/finalità
* Segnale del tipo di programma (ad esempio fiera, evento, webinar, roadshow, conferenza o cultura)
* Criteri di pubblico per gli elenchi di persone
* Progettazione del percorso: conteggio, criteri di immissione, punti di contatto/tempistica e data di pubblicazione
* Token (valori riutilizzabili come data evento, luogo, oggetto)

Il collaboratore richiede tutto ciò che manca prima di creare.

## Fasi build

L&#39;abilità viene eseguita in tre fasi: **INTAKE → APPROVARE → BUILD**. Non viene creato nulla finché non ricevi l’approvazione.

### Acquisizione

Coworker estrae quanto segue dalla descrizione e chiede se manca qualcosa:

* Nome del programma
* Cartella principale (se non specificata, viene utilizzata la directory principale del workspace)
* Descrizione
* Tipo di programma (se possibile dedotto da una breve formulazione)
* Token da creare (nome, tipo, valore)
* Criteri di pubblico dell’elenco Persone
* Percorsi: conteggio, criteri di ingresso, punti di contatto, data di pubblicazione

### Approvazione

Il collaboratore presenta un riepilogo di conferma prima di procedere:

`I'll create {program} in folder {id}, with {N} token(s), {N} dynamic people list(s), and {N} journey(s). Shall I proceed?`

Nessuno strumento di creazione viene chiamato finché non rispondi con un via libera (ad esempio _procedere_, _andare avanti_, _compilarlo_, _approvato_ e _sì_).

### Genera

I passaggi della build vengono eseguiti in ordine fisso; ciascuno di essi dipende dagli ID prodotti dal passaggio precedente.

| Passaggio | Descrizione | Strumenti | Output |
|---|---|---|---|
| **1. Cartella** | Risolve la cartella padre per nome o utilizza la directory principale del workspace; può creare una nuova sottocartella | `getRootTree`, `browseFolders`, `createFolder` | Nome cartella + ID |
| **1.5. Tipo di programma** | Cerca i tipi di programma tenant e seleziona la corrispondenza per la descrizione | `browseProgramTypes` | Nome tipo + `programTypeId` |
| **2. Programma** | Crea il programma nella cartella risolta, associato al tipo scelto | `createProgram` | Nome, ID e tipo del programma |
| **3. Token** | Crea ogni token `my.*` nel programma | `createProgramToken` | Nomi di token |
| **4. Elenchi persone** | Genera regole basate su attributi dai criteri di pubblico e crea l’elenco persone dinamico | `generate_ruleset`, `createSmartListWithRules` | Nome elenco + `smartListId` |
| **5. Percorsi** | Crea ogni percorso di persone con un nodo di ingresso del pubblico di persone collegato all&#39;elenco del passaggio 4 | `create_journey` | Nomi percorso, ID |
| **6. Pubblica** | Pubblica o pianifica il percorso se viene impostata e confermata una data di pubblicazione | `publish_journey_with_dates` | Percorso live/pianificato |
| **7. QA** | Anteprima di convalida e controllo qualità completo opzionali | `qa_program_preview`, `qa_program` | Rapporto di superamento/mancato superamento/avvisi |

**_Dipendenze fase:_**

* Per poter allegare token, elenchi o percorsi è necessario specificare l’ID del programma (passaggio 2).
* `smartListId` dal passaggio 4 viene passato a `create_journey` nel passaggio 5. Se ometti, il nodo di ingresso del pubblico del percorso rimane vuoto.
* Il prompt del percorso inizia sempre con _Inizia con un nodo di pubblico Persona come punto di ingresso_ per garantire un nodo di ingresso popolato.

## Risorse di output

### Programma

Il contenitore principale. La vista Dettaglio presenta le seguenti schede:

| Scheda | Contenuti |
|---|---|
| **Panoramica** | Nome, descrizione, tipo di programma, stato, posizione della cartella, timestamp |
| **Attributi** | Campi personalizzati definiti dal tipo (solo se il tipo di programma li abilita) |
| **Token** | `my.*` token con ambito in questo programma |
| **Percorsi** | Percorsi contenuti nel programma |

### Token

Valori riutilizzabili `my.*` con ambito nel programma (ad esempio `my.eventDate`). Ciascuno ha un tipo, uno di `text`, `date`, `rich text`, `score` o `number`, e un valore. Si risolvono all’interno di e-mail e contenuti all’interno dell’ambito del programma.

### Elenco persone

Un elenco dinamico (intelligente) di persone creato in base ai criteri di pubblico tramite regole generate e basate su attributi, creato nel programma.

### Percorso

Un percorso di persone che inizia con un nodo di ingresso del pubblico Persona associato all&#39;elenco di persone del passaggio 4, seguito dai punti di contatto del breve (ad esempio, _invia e-mail di benvenuto dopo 1 giorno, follow-up dopo 3 giorni_). Se è impostata una data di pubblicazione, il percorso può essere pubblicato immediatamente o pianificato.

## Risoluzione del tipo di programma

I programmi sono **associati in modo permanente** a un tipo di programma definito dal tenant al momento della creazione. Non è possibile modificarlo in seguito. Il flusso risolve il tipo in modo esplicito tramite `browseProgramTypes` in ogni caso.

| Caso | Comportamento |
|---|---|
| **Più tipi disponibili** | Corrisponde a un tipo di testo breve (ad esempio fiera/stand/expo = *fiera*/*evento*; webinar = *webinar*/*evento*; crescita/espansione = *crescita*; nessun segnale chiaro = *predefinito*). Se non viene trovata alcuna corrispondenza, in Collaboratore vengono elencati i tipi e le richieste disponibili. |
| **Tenant di sola impostazione predefinita** | Utilizza *Default* e nota che un amministratore può aggiungere [tipi di programma](../admin/program-types.md) personalizzati. |
| **Nessun tipo configurato** | Fermate — la creazione non riuscirà. Chiede a un amministratore di eseguire il provisioning dei tipi di programma prima di riprovare. |

## Valori predefiniti

| Impostazione | Predefinito |
|---|---|
| **Cartella** | Directory principale Workspace (se non è specificata alcuna cartella) |
| **Tipo di programma** | *Predefinito* (se non viene visualizzato alcun breve segnale e non viene eseguita alcuna selezione manuale) |
| **Attributi Personalization** | Persona derivata, intento derivato, livello di coinvolgimento incluso per impostazione predefinita (rinuncia disponibile) |
| **Pubblicazione** | Non automatico per le date di pubblicazione future — indicato come passaggio `ACTIVATE journey by {date}` manuale; pubblicazione immediata solo quando viene avviato e confermato |
| **Gate di approvazione** | Nessuna risorsa creata prima dell&#39;approvazione esplicita |

## Limitazioni

| Limitazione | Dettaglio |
|---|---|
| **Limite breve** | ~30.000 caratteri; i documenti troncati perdono i contenuti finali e pongono al primo posto gli elementi essenziali |
| **Tipo di programma immutabile** | Non può essere modificato dopo la creazione; verifica il tipo corretto prima di approvare |
| **Campi interni richiesti** | `parent` e `programTypeId` sono sempre impostati. Se si omette `parent`, verrà negato l&#39;accesso. Se si omette il tipo, verrà automaticamente ripristinato il valore *Predefinito* |
| **Il Percorso richiede l&#39;elenco delle persone** | `smartListId` dal passaggio 4 è obbligatorio per il passaggio 5; il flusso lo applica |
| **Appartenenza a elenco asincrono** | Gli elenchi statici (da criteri) vengono compilati in diversi minuti, non istantaneamente |
| **Gestione errori** | Gli errori dello strumento vengono segnalati con l’errore esatto; Collaboratore richiede di confermare l’input e riprovare |
| **Conflitti di nomi** | Risoluzione non automatica: verrà richiesto un nome diverso |
| **Ambito** | Solo Marketo Optimizer; [!DNL Marketo Engage] utenti devono utilizzare le competenze separate di creazione/pianificazione del programma |


## Controllo di qualità

Al termine della build, Collaboratore offre:

> &quot;Desideri che esegua un controllo di qualità per convalidare tutto prima del lancio?&quot;

Confermare l&#39;esecuzione di `qa_program_preview` seguita da `qa_program`. Il processo restituisce un rapporto dei controlli superati, non riusciti ed eventuali avvisi, insieme ai passaggi successivi consigliati.
