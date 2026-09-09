---
title: Decisioning IA
description: Comprendi le decisioni basate sull’intelligenza artificiale in Marketo Optimizer, il livello di intelligence dietro il controllo del traffico del percorso, il percorso migliore successivo, l’ottimizzazione dell’ora di invio e altre funzionalità che sostituiscono le regole statiche con l’automazione basata sui risultati.
TQID: 'https://experienceleague.adobe.com/biPd2Zv3z75i7imGqRNuKXvgoD0sIcwrFrjWmSO7FpU'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2:
  - id: 3cf5f37e-e87e-5179-812b-53ce05d7eebb
  - id: 5229c72e-d79b-574f-a03e-5c4bf48172c3
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
topic_v2:
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 808
ht-degree: 2%

---


# Decisioning IA

Le decisioni basate sull’intelligenza artificiale sono il livello di intelligenza dietro Adobe Marketo Optimizer. Invece di pre-creare ogni ramo come regola statica, le decisioni basate sull’intelligenza artificiale valutano continuamente il contesto di un profilo, tra cui l’iscrizione al percorso, la cronologia del coinvolgimento, i punteggi di intento e il comportamento in tempo reale, per determinare l’azione o il percorso migliore successivo per quella persona.

Questa valutazione continua sposta l’orchestrazione da regole statiche verso un’automazione basata sui risultati: anziché definire in anticipo ogni condizione, descrivi il risultato desiderato e il sistema determina come raggiungerlo per ogni persona.

## Funzionalità {#capabilities}

Le decisioni di IA sono composte dalle seguenti funzionalità:

| Funzionalità | Cosa decide |
|---|---|
| [Controllo del traffico di Percorso](../marketing/journey-traffic-control.md) | In quale percorso una persona dovrebbe essere in questo momento. Quando una persona è idonea per più di un percorso, il controllo del traffico di percorso effettua un nuovo indirizzamento nel momento in cui il profilo o il comportamento cambia, anziché lasciarla su un percorso non più adatto. |
| [Percorso migliore successivo](../marketing/next-best-path.md) | Il percorso più adatto per una persona all’interno di un percorso. Invece delle condizioni di filtro hardcoding, descrivi l’intento nel linguaggio naturale, e il sistema indirizza ogni persona al percorso migliore al momento giusto. |
| [Ottimizzazione del tempo di invio](../marketing/email-send-time-optimization.md) | La finestra di invio migliore per ogni destinatario, in base al coinvolgimento storico, anziché una pianificazione fissa per tutti. |
| Contenuto contestuale | Varianti e-mail personalizzate generate automaticamente da una descrizione del contenuto, da utilizzare come singola risorsa e-mail personalizzata in pochi percorsi. _Disponibile a breve._ |
| [Brand Concierge](https://experienceleague.adobe.com/it/docs/brand-concierge/content/home){target="_blank"} | Indirizzamento e risposta conversazionali in tempo reale, ad esempio chat e assistenza in tempo reale. Brand Concierge richiede prodotti aggiuntivi. |

Alcune di queste funzionalità risolvono diversi problemi all’interno dello stesso percorso. Il controllo del traffico di percorso determina quale percorso ottiene la priorità quando più percorsi sono in competizione per coinvolgere la stessa persona contemporaneamente. Le altre funzionalità decidono cosa accade dopo che una persona è già in un percorso.

## Percorsi suddivisi e percorso migliore successivo {#split-paths-next-best-path}

[Percorsi suddivisi](../marketing/split-merge-paths-nodes.md) ti consentono di definire rami di percorso con condizioni di filtro esplicite: se un punteggio è superiore a una soglia, invia una persona in basso di un percorso, altrimenti invia un&#39;altra. Questa logica basata su regole è precisa e completamente controllabile, ma ogni nuova condizione richiede un nuovo ramo.

Il nodo [Percorso migliore successivo](../marketing/next-best-path.md) applica le decisioni di IA allo stesso problema. Invece di una soglia fissa, il modello valuta il coinvolgimento, l’utente tipo, l’interesse del prodotto e la fase di funnel insieme, prevede il risultato migliore per ogni persona e seleziona automaticamente il percorso ottimale.

## Input dati {#data-inputs}

Le decisioni basate sull’intelligenza artificiale si basano sulle seguenti categorie di dati:

| Categoria | Esempi |
|---|---|
| Demografico e firmografico | Qualifica, settore e dimensione società |
| Psicografica | Punteggio lead, urgenza e priorità |
| Coinvolgimento | Punteggio, livello, tendenza, ultima attività e canale |
| Intento | Intento di prodotto o parola chiave, raggruppato in contenitori alti, medi o bassi |
| Utente tipo | Ruolo nell’offerta, nella qualifica professionale e nella persona |

## Cadenza di valutazione {#evaluation-cadence}

Le decisioni basate su IA utilizzano due diversi programmi di valutazione. Il profilo sottostante di una persona viene ricalcolato in un batch notturno. La decisione stessa viene applicata in tempo reale a ogni interazione, utilizzando qualsiasi profilo notturno indichi. Quindi la parte continua del processo decisionale basato sull’intelligenza artificiale descrive il momento decisionale, non la frequenza di aggiornamento del profilo.

## Guardrail e regole {#guardrails-rules}

Le regole coprono solo le condizioni che qualcuno ha esplicitamente annotato. Quando la realtà cade al di fuori di quell&#39;albero, come un personaggio ibrido o una combinazione di segnali che nessuno aveva previsto, le regole non fanno nulla finché qualcuno non aggiunge un nuovo ramo. Il decisioning basato sull’intelligenza artificiale classifica ogni persona in modo continuo e restituisce un’azione migliore basata sull’affidabilità, in modo da gestire combinazioni per le quali non è stato esplicitamente programmato alcun risultato, e migliora man mano che si ottengono più risultati, cosa che una regola non fa mai.

Le regole sono spiegabili e immediate per l’auditing, mentre le decisioni basate sull’intelligenza artificiale sono basate su un punteggio di affidabilità anziché su un fattore deterministico. Per questo motivo, le regole rimangono lo strumento migliore quando:

* Non è mai necessario superare un limite di conformità rigido, ad esempio la soppressione dei contatti che hanno rinunciato.
* Volume o cronologia insufficienti per consentire a un modello di imparare da.
* Ogni decisione deve essere pienamente spiegabile su richiesta.

Le configurazioni più mature vengono eseguite insieme: regole come guardrail e decisioning di IA che gestiscono tutto nel mezzo.

## Vantaggi {#benefits}

* Meno complessità di percorso manuale, con meno rami di regole da mantenere.
* Esperienze più rilevanti senza la creazione di centinaia di regole.
* Maggiore efficienza delle qualifiche.
* Identificazione più rapida del miglior coinvolgimento successivo per ciascun profilo.

>[!BEGINSHADEBOX]

**Ambito futuro: contesto dell&#39;account e del gruppo di acquisto**

Non disponibile oggi in Marketo Optimizer. Le decisioni basate sull’intelligenza artificiale sono pianificate per estendersi oltre il profilo individuale a:

* Contesto dell’account: segnali a livello di società e di account come input decisionale.
* Segnali del gruppo di acquisto: ruolo nell’affare, status di decision-maker o professionista e coinvolgimento aggregato in tutti coloro che sono coinvolti in una decisione di acquisto.
* Orchestrazione del percorso a livello di account: le decisioni su indirizzamento e contenuti prese per l’account o il gruppo di acquisto come unità, con il controllo del traffico di percorso coordinato tra le diverse persone coinvolte.

>[!ENDSHADEBOX]
