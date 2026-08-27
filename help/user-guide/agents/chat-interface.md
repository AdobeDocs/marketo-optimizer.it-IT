---
title: Interfaccia chat
description: Utilizza il pannello Chat di Coworker in Marketo Optimizer per creare programmi, percorsi ed elenchi utilizzando il linguaggio naturale o il menu con barra (/).
source-git-commit: 6264cadee61cb4a9366df655611803214110cccf
workflow-type: tm+mt
source-wordcount: '928'
ht-degree: 0%

---

# Interfaccia chat

Il pannello chat è incorporato in [!DNL Adobe Marketo Optimizer]. È qui che interagisci con gli agenti di intelligenza artificiale utilizzando un linguaggio semplice per creare programmi e percorsi, creare e confrontare elenchi di persone, indagare sui lead, configurare il punteggio e altro ancora.

Per aprire il pannello, seleziona l&#39;icona _Collaboratore_ nell&#39;area di navigazione a sinistra. L’intestazione del pannello presenta quattro controlli:

| Controllo | Descrizione |
|---------|-------------|
| **Nuova conversazione** | Avvia una nuova chat (cancella il thread corrente). |
| **Cronologia conversazioni** | Apri le conversazioni precedenti in modo da poterne riaprire una. |
| **Scambia pannelli** | Sposta il pannello chat sull&#39;altro lato dell&#39;area di lavoro. |
| **Comprimi** | Nascondi il pannello per dare più spazio all’area di lavoro. |

Nella parte inferiore del pannello si trova la finestra di messaggio in cui è possibile:

* Aggiungi un messaggio e premi **Invio** per inviare (**MAIUSC+INVIO** inserisce una nuova riga).
* Allega un file utilizzando l&#39;icona _Allega_ (formati supportati: `.txt`, `.md`, `.csv`, `.json`, `.xlsx`, `.docx`, `.pdf`). Utilizza i caricamenti CSV e fogli di calcolo per avviare un’importazione di lead.

>[!BEGINSHADEBOX]

## Qualificatore di vendita

[!DNL Adobe Sales Qualifier] è un&#39;applicazione basata su IA che è possibile utilizzare con [!DNL Marketo Optimizer]. Implementa Account Qualification Agent ed è progettato per semplificare i flussi di lavoro per i rappresentanti di sviluppo aziendale (BDR, Business Development Representative). [!DNL Sales Qualifier] automatizza i flussi di lavoro di qualificazione dei potenziali clienti, di estensione e di coinvolgimento degli acquirenti tra i canali. Riduce il carico BDR manuale e accelera la velocità della pipeline per le aziende B2B aziendali.

Per ulteriori informazioni, consulta la [documentazione di Sales Qualifier](https://experienceleague.adobe.com/en/docs/sales-qualifier/using/home){target="_blank"}.

>[!ENDSHADEBOX]

## Chiedi al collega

Ci sono due modi ugualmente validi per ottenere lavoro fatto — non è mai necessario utilizzare il menu barra.

**Lingua naturale** — Digita la richiesta nel modo in cui l&#39;hai detta a un collega:

* _&quot;Crea un percorso di benvenuto per le nuove iscrizioni di prova.&quot;_
* _&quot;Perché john@acme.com non è entrato in questo percorso?&quot;_
* _&quot;Confrontare gli elenchi &#39;Partecipanti al webinar Q3&#39; e &#39;Account organizzazione&#39;.&quot;_

L&#39;agente associa il testo all&#39;abilità appropriata dietro le quinte ed esegue il flusso di lavoro appropriato.

**Menu barra (/)**. Digitare `/` per aprire un menu visualizzabile di tutte le operazioni consentite da Coworker. Questa funzione è utile quando desideri scoprire le funzionalità o passare direttamente a un flusso di lavoro noto.

## Menu barra (/)

Utilizzare `/` all&#39;inizio della finestra di messaggio o dopo uno spazio per aprire il menu. Mentre si continua a digitare, l&#39;elenco filtra per nome, descrizione o ID, ad esempio `/journey` si limita ai comandi relativi al percorso.

Utilizza **/** per spostarti tra le voci, **Invio** o **Scheda** da selezionare e **Esc** da ignorare. Puoi anche fare clic direttamente su una voce.

Le voci di menu sono raggruppate in sezioni etichettate:

| Sezione | Contiene |
|---------|----------|
| **Analizza** | Ricerche diagnostiche di sola lettura (ad esempio, indagini lead, query intento). |
| **Convalida** | Flussi di lavoro di controllo qualità e audit. |
| **Build** | Flussi di lavoro di creazione (programmi, percorsi, elenchi, punteggio). |
| **Importazione** | Importazione lead CSV. |
| **Altro** | Qualsiasi cosa che non rientri nelle categorie precedenti. |

Il menu elenca anche **connettori** (ad esempio, _Sfoglia Marketo_ apre una finestra di dialogo del selettore) e **collegamenti di navigazione** che ti portano a una schermata dell&#39;area di lavoro.

### Seleziona una voce di menu

Quando si seleziona un&#39;abilità o un agente dal menu, nella finestra di messaggio viene inserito un prompt iniziale da modificare. Il messaggio è **not** inviato automaticamente. Se ad esempio si seleziona _Pianifica campagne_, verrà visualizzato _&quot;Pianifica un nuovo programma Marketo per [nome campagna]. Caricherò la descrizione.&quot;_ Compila i segnaposto tra parentesi quadre e premi **Invio** per inviare.

I connettori aprono un modale invece di inserire testo. Le scelte rapide per la navigazione ti portano direttamente a quella schermata nell’area di lavoro.

>[!NOTE]
>
>Alcuni comandi sono visualizzati in grigio e contrassegnati come _In arrivo_. Questi sono gestiti da flag di funzione e non sono ancora attivi per il tuo account; selezionarne uno non fa nulla. Il set disponibile dipende dalle feature abilitate.

## Competenza

Un&#39;abilità è un flusso di lavoro in pacchetti che l&#39;agente è in grado di eseguire, ovvero i blocchi predefiniti del menu `/` e le richieste in linguaggio naturale. Ogni abilità riunisce istruzioni dettagliate e gli strumenti specifici necessari per un lavoro (ad esempio, &quot;pubblicare un percorso&quot;, &quot;confrontare elenchi di due persone&quot;, &quot;creare un modello di punteggio&quot;).

Per un elenco completo delle abilità attualmente supportate, consulta _[Competenze collaboratore](./skills.md)_.

Aspetti chiave da conoscere sulle competenze:

* **Le abilità hanno ambito di prodotto.** In [!DNL Marketo Optimizer] sono disponibili varie abilità specifiche del prodotto (percorsi, elenchi di persone, punteggi, canali, ottimizzazione dell&#39;ora di invio e così via). Alcune abilità sono solo [!DNL Marketo Engage] e una coppia lavora in entrambi i prodotti (importazione lead, conoscenza del prodotto). Le abilità sono visibili solo nel punto in cui ti trovi.
* **Non è necessario memorizzare i nomi delle abilità.** Descrivi il tuo obiettivo e l&#39;agente sceglie l&#39;abilità corrispondente. Il menu `/` è un collegamento più veloce e individuabile agli stessi flussi di lavoro.
* **Alcune abilità leggono solo, altre cambiano le cose.** Le abilità investigative e di reporting (ad esempio, analisi dei lead, query di intento, report sul tempo di invio) consentono di leggere solo i dati. Creare e configurare abilità (ad esempio, creazione di percorsi, punteggio) creare o modificare dati.

## Richieste di follow-up

Dopo le risposte di Coworker, viene spesso visualizzata una riga di richieste di follow-up selezionabili in base alle specifiche esigenze, ad esempio dopo la creazione di un percorso potrebbe offrire _&quot;Pubblica questo percorso&quot;_ o _&quot;Aggiungi un passaggio di attesa&quot;_. Fai clic su uno per continuare senza digitare. Questi sono solo suggerimenti; puoi sempre digitare il tuo messaggio successivo.

## Suggerimenti

* **Specificare con gli identificatori.** Durante le indagini o le modifiche, includi l’indirizzo e-mail, il nome della persona, il nome del percorso o il nome dell’elenco in modo che l’agente agisca sulla risorsa giusta.
* **Utilizza `/` per esplorare.** Se non si è certi di ciò che può fare Collaborator, aprire il menu `/` e scorrere le categorie.
* **Modifica il prompt iniziale.** La selezione di un&#39;abilità ti offre un modello — sostituisci i segnaposto `[bracketed]` prima dell&#39;invio.
* **Carica prima per le importazioni.** Per un’importazione di lead, allega prima il file CSV, quindi descrivi cosa desideri farne.
* **Avvia una nuova conversazione** quando si passa a un&#39;attività non correlata, in modo che il contesto precedente non influisca sulla nuova richiesta.
