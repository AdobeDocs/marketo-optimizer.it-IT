---
title: Abilità del collaboratore
description: Rivedi le abilità del collaboratore in Marketo Optimizer per percorsi, pubblico, programmi, contenuti, analisi e decisioni basate su AI. Scopri cosa può fare ogni abilità per te.
autotag-review: '2026-09-22T14:02:17.516Z'
TQID: 'https://experienceleague.adobe.com/nNFB9UEghfqVvnBrNtTDnpnLUKKKMAU2nY1Pqt0KkUQ'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 1650dadf-b034-5ac9-a309-77ad1e2f5035
    internal-label: Chat Interface
subfeature_v2:
  - id: b9e5c7f3-be30-563c-9e41-cc8ea76e2fee
    internal-label: Skills
topic_v2:
  - id: bbbea26f-9621-49eb-9ab8-e06fb3bbce8c
    internal-label: Artificial intelligence
source-git-commit: 5334f0f5d9d958ea47b055b067a7308950352e9c
workflow-type: tm+mt
source-wordcount: '988'
ht-degree: 4%
---

# Competenze del collaboratore

Una _abilità_ è un flusso di lavoro integrato che può essere eseguito da Collaborator. Le abilità sono i componenti del menu `/` e delle richieste in linguaggio naturale. Ogni abilità riunisce istruzioni dettagliate e gli strumenti specifici necessari per un’attività, ad esempio la pubblicazione di un percorso, il confronto di elenchi di due persone o la creazione di un modello di punteggio.

La classificazione per ogni abilità riflette il tipo di azione che esegue:

* _Cerca_ abilità cerca o elenca i record esistenti.
* _Analizza_ le abilità per rivedere, confrontare o creare rapporti sui dati senza modificarli.
* _Visualizza_ abilità visualizza un report o una metrica di sola lettura.
* _Modifica_ abilità modifica le impostazioni o il contenuto di un oggetto esistente.
* _Crea_ abilità crea un nuovo oggetto.

## Percorsi {#journeys}

Queste abilità creano, pubblicano, eseguono il debug e gestiscono percorsi di persone.

| Competenza | Funzionamento | Tipo |
| --- | --- | --- |
| **Osservabilità Percorso** | Debug e monitoraggio del movimento delle persone in un percorso, inclusi percorsi, tempi, suddivisioni, blocchi e tempo di permanenza. Consulta _[Eseguire il debug e monitorare la progressione del percorso](./journey-observability.md)_. | Analizza |
| **Controllo traffico Percorso** | Simula il modo in cui i profili si distribuiscono tra tutti i percorsi attivi. | Analizza |
| **Pubblicazione Percorso** | Pubblica, avvia o pianifica un percorso, incluse la modalità di avvio, le date e la conferma. | Modifica |
| **Interruzione Percorso** | Interrompere un percorso in esecuzione per arrestarlo immediatamente o chiuderlo per riavvolgerlo. | Modifica |
| **Percorso modifica date** | Modifica la data di inizio o di fine in una bozza, un percorso pianificato o live senza ripubblicarlo. | Modifica |
| **Rientro Percorso** | Configurare le impostazioni di reinserimento per un percorso, specificando se è consentito il reinserimento, il ritardo di raffreddamento e il numero massimo di voci. | Modifica |
| **Creazione Percorso** | Creazione e modifica di percorsi di persone utilizzando richieste in linguaggio naturale. | Creare |
| **Webinar al Percorso** | Imposta un percorso promozionale prima di un webinar e un percorso di follow-up dopo di esso. | Creare |

## Elenchi di pubblico e persone {#audience-people-lists}

Queste abilità creano e gestiscono elenchi di persone e definizioni di pubblico.

| Competenza | Funzionamento | Tipo |
| --- | --- | --- |
| **Sfoglia membri elenco dinamico** | Sfoglia e filtra i membri di un elenco di persone dinamico o statico. | Ricerca |
| **Confronto elenco persone** | Confrontare gli elenchi di due persone e visualizzare i membri sovrapposti. | Analizza |
| **Rimuovi da elenco statico** | Rimuovere da un elenco statico i membri che corrispondono ai criteri del linguaggio naturale. | Modifica |
| **Creazione pubblico** | Adattare un elenco avanzato [!DNL Marketo Engage], creare un elenco di persone o aggiungere o aggiornare le relative regole. Consulta _[Creare tipi di pubblico per i programmi](./audience-creation.md)_. | Creare |

## Programmi, cartelle e canali {#programs-folders-channels}

Queste competenze gestiscono la struttura del programma, i token e la configurazione dei canali.

| Competenza | Funzionamento | Tipo |
| --- | --- | --- |
| **Crea programma** | Crea programmi da una descrizione della campagna. Consulta _[Creare un programma da una descrizione](./program-from-brief.md)_. | Analizza |
| **Adapt Program** | Genera storie di migrazione da [!DNL Marketo Engage] programmi per l&#39;adattamento [!DNL Marketo Optimizer]. | Analizza |
| **Token risorse** | Creazione e gestione di valori `{{my.token}}` in programmi, cartelle e percorsi. | Modifica |
| **Canali FCS** | Crea, pubblica, arresta e clona canali nel servizio Canali, inclusi gli schemi XDM e il provisioning. | Modifica |
| **Creazione cartella** | Crea cartelle organizzative nella struttura ad albero delle risorse. | Creare |
| **Campagna in linea WhatsApp** | Crea e pubblica una campagna in linea [!DNL WhatsApp] su un nodo di percorso. | Creare |
| **Creazione di un programma di marketing** | Creazione di un programma completo, che include sottocartelle, token, elenchi di persone e percorsi. | Creare |
| **Creazione di batch di programmi e Percorsi** | Creare più coppie di programmi e percorsi in una singola richiesta batch. | Creare |

## E-mail e pagine di destinazione {#email-landing-pages}

Queste abilità creano e gestiscono e-mail, moduli e pagine di destinazione.

| Competenza | Funzionamento | Tipo |
| --- | --- | --- |
| **Elenca Forms** | Elencare i moduli e visualizzarne i dettagli e i campi. | Ricerca |
| **Elenca pagine di destinazione** | Elencare le pagine di destinazione, visualizzarne i dettagli e gestirne lo stato bozza o pubblicato. | Ricerca |
| **Controllo e-mail** | Controlla un’e-mail rispetto al relativo gruppo target, inclusa l’inferenza dell’utente tipo e una breve revisione sezione per sezione più. | Analizza |
| **Authoring di e-mail** | Crea o aggiorna un nodo e-mail di percorso, inclusa la composizione da un breve o PDF, il collegamento a un nodo e la scrittura di contenuto. | Modifica |
| **Authoring modulo** | Crea o aggiorna un modulo di acquisizione lead autonomo, pubblicalo e, facoltativamente, incorporalo in una pagina di destinazione. | Creare |
| **Authoring della pagina di destinazione** | Crea o aggiorna una pagina di destinazione da una breve descrizione, inclusa la pianificazione del contenuto, la selezione dei modelli, la compilazione degli slot e l’aggiunta di un modulo, quindi pubblicalo. Allegare una pagina di destinazione pubblicata come collegamento call-to-action in un messaggio e-mail. | Creare |
| **Verifica rendering e-mail** | Controlla se in un&#39;e-mail sono presenti [!DNL Microsoft Outlook] problemi di rendering e correggi automaticamente ciò che è in grado di fare. | Modifica |

## Personalizzazione dei contenuti {#content-personalization}

Questa abilità sfoglia i modelli e personalizza i contenuti delle e-mail per diversi utenti tipo.

| Competenza | Funzionamento | Tipo |
| --- | --- | --- |
| **Contenuto Personalization** | Sfoglia e visualizza in anteprima i modelli, quindi modifica il contenuto o genera varianti. Vedi _[Personalizzare il contenuto delle e-mail per persona](./personalize-content.md)_. | Creare |

## Analisi e ottimizzazione {#analytics-optimization}

Queste abilità generano rapporti sulle prestazioni e configurano modelli di ottimizzazione e punteggio del tempo di invio.

| Competenza | Funzionamento | Tipo |
| --- | --- | --- |
| **Analisi superficie** | Genera report di analisi da richieste in linguaggio naturale, che includono tendenze delle attività, prestazioni delle e-mail, dati di lead e account, appartenenza a segmenti e elenchi e metriche di percorso. I dati dei rapporti vengono aggiornati ogni due ore. Consulta _[Generare rapporti di analisi](./surface-analytics.md)_. | Analizza |
| **Rapporto sull&#39;ora di invio** | Visualizza il rapporto sulle prestazioni dell’ottimizzazione del tempo di invio (STO) a livello di percorso o per un singolo nodo e-mail. | Analizza |
| **Simulazione STO e-mail** | Visualizza in anteprima il tempo di invio previsto, la qualità del pubblico e la mappa di calore del coinvolgimento per un nodo e-mail prima di abilitare l’opzione STO. | Analizza |
| **Ottimizzazione dell&#39;ora di invio** | Attiva o disattiva l&#39;opzione STO in un nodo e-mail di percorso. | Modifica |
| **Configurazione del coinvolgimento** | Mostra e modifica i pesi delle attività per il modello di punteggio di coinvolgimento della persona. | Modifica |
| **Studio punteggio** | Elenca e visualizza i modelli di punteggio, quindi generane e pubblicane di nuovi. Consulta _[Creare modelli di punteggio personalizzati](./lead-scoring-model.md)_. | Creare |

## Decisioning e intento di IA {#ai-decisioning-intent}

Queste competenze valutano la preparazione dei dati per le decisioni di IA e configurano il punteggio intento.

| Competenza | Funzionamento | Tipo |
| --- | --- | --- |
| **Integrità Decisioning IA** | Segnala se i dati di un’organizzazione sono pronti per le decisioni di IA, tra cui la disponibilità di lead, la distribuzione dell’utente tipo, la ricchezza delle storie e le intenzioni. | Analizza |
| **Analizza intento** | Esegui query e convalida la classificazione dell’intento a livello di lead, le tendenze e la tassonomia del prodotto e delle parole chiave. | Analizza |
| **Configurazione intento** | Mostra e modifica i pesi delle attività per il modello di punteggio intento della persona. | Modifica |

## Gestione delle conoscenze e delle competenze {#knowledge-skill-management}

Queste abilità rispondono alle domande del prodotto e ti consentono di creare nuove abilità personalizzate.

| Competenza | Funzionamento | Tipo |
| --- | --- | --- |
| **Conoscenza del prodotto** | Rispondi alle domande pratiche e concettuali utilizzando la documentazione di [!DNL Marketo Optimizer] pubblicata su Experience League. | Ricerca |
| **Creazione abilità** | Crea, verifica e perfeziona nuove competenze personalizzate. | Creare |
