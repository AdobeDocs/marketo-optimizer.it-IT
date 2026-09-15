---
title: Abilità del collaboratore
description: 'Esaminare le competenze di CX Enterprise Coworker in Marketo Optimizer: flussi di lavoro combinati per programmi, percorsi, tipi di pubblico, valutazione, contenuto e ottimizzazione del tempo di invio.'
TQID: 'https://experienceleague.adobe.com/nNFB9UEghfqVvnBrNtTDnpnLUKKKMAU2nY1Pqt0KkUQ'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3cf5f37e-e87e-5179-812b-53ce05d7eebb
    internal-label: Setup
  - id: 46e599c6-e20f-5f67-9824-93415016f66b
    internal-label: Audiences
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
    internal-label: Journeys
  - id: a29661b8-f7a4-53d1-a9ac-fdec08c092e4
    internal-label: Programs
  - id: d4203578-d294-5145-b397-f26f4488a904
    internal-label: Channels
topic_v2:
  - id: b4dd41a7-ccf8-4e9d-918e-acaab534a307
    internal-label: Data quality
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 6e03e2dc6abb00d288f5684e9ea9b6489c6517e4
workflow-type: tm+mt
source-wordcount: '568'
ht-degree: 5%
---
# Competenze del collaboratore

Una _abilità_ è un flusso di lavoro integrato che Coworker è in grado di eseguire, ovvero i blocchi predefiniti sia del menu `/` che delle richieste in linguaggio naturale. Ogni abilità riunisce istruzioni dettagliate e gli strumenti specifici necessari per un lavoro (ad esempio, &quot;pubblicare un percorso&quot;, &quot;confrontare elenchi di due persone&quot;, &quot;creare un modello di punteggio&quot;).

>[!NOTE]
>
>Ogni abilità viene classificata a seconda che muti lo stato [!DNL Marketo Optimizer] o [!DNL Marketo Engage] (**Scrivi**), solo le query/analisi/genera (**Leggi**) o ha funzioni di query + mutazione (**Leggi+Scrivi**).

## Programmi e pianificazione {#programs-planning}

| Competenza | Funzionamento | Accesso | Superficie del prodotto | Impatto/flusso di dati |
|---|---|---|---|---|
| `adapt-program` | Genera storie di migrazione da [!DNL Marketo Engage] programmi per l&#39;adattamento [!DNL Marketo Optimizer]. | Lettura | [!DNL Marketo Optimizer] | Legge [!DNL Marketo Engage], scrive [!DNL Marketo Optimizer] |
| `folder-creation` | Crea cartelle organizzative nella struttura ad albero delle risorse. | Scrittura | [!DNL Marketo Optimizer] | Legge e scrive [!DNL Marketo Optimizer] |
| `program-creation` *(Programmi di compilazione)* | Crea programmi Marketo da una descrizione della campagna.  <p>Consulta _[Creare un programma da una descrizione](./program-from-brief.md)_. | Scrittura | [!DNL Marketo Engage] | Legge e scrive [!DNL Marketo Engage] |
| `program-planning` *(Pianificare Campagne)* | Trasforma i resoconti in documenti di configurazione/implementazione. | Lettura | [!DNL Marketo Engage] | Legge [!DNL Marketo Engage] |
| `program-qa` *(Convalida Programmi)* | Convalidare/controllare i programmi (solo regole, piano di test o descrizione). | Lettura | [!DNL Marketo Engage] | Legge [!DNL Marketo Engage] |

## Percorsi {#journeys}

| Competenza | Funzionamento | Accesso | Prodotto | Back-end (flusso di dati) |
|---|---|---|---|---|
| `journey-creation` | Creazione e modifica di percorsi di persone dal linguaggio naturale. | Scrittura | [!DNL Marketo Optimizer] | Legge e scrive [!DNL Marketo Optimizer] |
| `journey-edit-dates` | Modifica la data di inizio/fine di un percorso senza pubblicazione. | Scrittura | [!DNL Marketo Optimizer] | Legge e scrive [!DNL Marketo Optimizer] |
| `journey-publish` | Pubblicare/avviare/pianificare percorsi di persone. | Scrittura | [!DNL Marketo Optimizer] | Legge e scrive [!DNL Marketo Optimizer] |
| `journey-stop` | Interrompi, chiudi, interrompi, interrompi o uccidi percorsi. | Scrittura | [!DNL Marketo Optimizer] | Legge e scrive [!DNL Marketo Optimizer] |
| `journey-reentry` | Configura reinserimento: consenti/non consentiti, arresto del sistema, numero massimo di voci. | Scrittura | [!DNL Marketo Optimizer] | Legge e scrive [!DNL Marketo Optimizer] |
| `journey-trafficcontrol` | Esegui una simulazione di controllo del traffico che mostra l’instradamento del profilo. | Lettura | [!DNL Marketo Optimizer] | Legge [!DNL Marketo Optimizer] (simulazione) |
| `journey-observability` | Avanzamento debug/monitoraggio: percorsi, tempistica, divisioni, blocchi, permanenza. <p>Consulta _[Eseguire il debug e monitorare la progressione del percorso](./journey-observability.md)_. | Lettura | [!DNL Marketo Optimizer] | Legge [!DNL Marketo Optimizer] + [!DNL Marketo Engage] (controllo elenco statico) |

## Pubblico e persone {#audiences-people}

| Competenza | Funzionamento | Accesso | Prodotto | Back-end (flusso di dati) |
|---|---|---|---|---|
| `audience-creation` | Adattare uno smartlist [!DNL Marketo Engage], creare un elenco di persone o aggiungere/aggiornare regole. <p>Consulta _[Creare tipi di pubblico per i programmi](./audience-creation.md)_. | Scrittura | [!DNL Marketo Optimizer] | Legge [!DNL Marketo Engage] + legge/scrive [!DNL Marketo Optimizer]. |
| `people-list-comparison` | Confrontare gli elenchi di due persone e visualizzare i membri sovrapposti. | Lettura | [!DNL Marketo Optimizer] | Legge [!DNL Marketo Optimizer] |
| `import-leads` | Controllare la qualità dei dati CSV e confermare le importazioni in [!DNL Marketo Engage]. | Lettura e scrittura | Entrambi | Legge e scrive [!DNL Marketo Engage] |
| `lead-investigation` *(Indagare sui lead)* | Analizzare l’attività, il punteggio, la qualifica e il ciclo di vita di un lead. | Lettura | [!DNL Marketo Engage] | Legge [!DNL Marketo Engage] |

## Contenuto e canali {#content-channels}

| Competenza | Funzionamento | Accesso | Prodotto | Back-end (flusso di dati) |
|---|---|---|---|---|
| `content-personalization` | Sfoglia/visualizza in anteprima i modelli e modifica il contenuto/genera varianti. | Lettura e scrittura | [!DNL Marketo Optimizer] | Legge e scrive [!DNL Marketo Optimizer]. Vedi _[Personalizzare il contenuto delle e-mail per persona](./personalize-content.md)_. |
| `asset-tokens` | CRUD del token completo su programmi/cartelle/percorsi. | Lettura e scrittura | [!DNL Marketo Optimizer] | Legge e scrive [!DNL Marketo Optimizer] |
| `fcs-channels` | Ricerche per canale e CRUD + pubblicazione/interruzione/eliminazione. | Lettura e scrittura | [!DNL Marketo Optimizer] | Legge e scrive [!DNL Marketo Optimizer] |

## Punteggio e segnali {#scoring-signals}

| Competenza | Funzionamento | Accesso | Prodotto | Back-end (flusso di dati) |
|---|---|---|---|---|
| `scoring-studio` | Elencare/ottenere modelli di punteggio e generarli/pubblicarli. <p>Consulta _[Creare modelli di punteggio personalizzati](./lead-scoring-model.md)_. | Lettura e scrittura | [!DNL Marketo Optimizer] | Legge e scrive [!DNL Marketo Optimizer] (servizio di assegnazione punteggio); legge [!DNL Marketo Engage] campi/tipi di attività lead. |
| `engagementconfiguration` | Mostra la configurazione del coinvolgimento e modifica/aggiorna i pesi. | Lettura e scrittura | [!DNL Marketo Optimizer] | Legge e scrive [!DNL Marketo Optimizer] |
| `intentconfiguration` | Mostra la configurazione intento e imposta/aggiorna i pesi. | Lettura e scrittura | [!DNL Marketo Optimizer] | Legge e scrive [!DNL Marketo Optimizer] |
| `intent-query` | Eseguire query e spiegare i punteggi di intento per persona/segmento/elenco. | Lettura | [!DNL Marketo Optimizer] | Legge [!DNL Marketo Optimizer] |

## Ottimizzazione dell’ora di invio {#sto}

| Competenza | Funzionamento | Accesso | Prodotto | Back-end (flusso di dati) |
|---|---|---|---|---|
| `send-time-optimization` | Controlla lo stato STO e abilita/disabilita su un nodo e-mail. | Lettura e scrittura | [!DNL Marketo Optimizer] | Legge e scrive [!DNL Marketo Optimizer] |
| `send-time-report` | Recupera/visualizza il rapporto sulle prestazioni STO. | Lettura | [!DNL Marketo Optimizer] | Legge [!DNL Marketo Optimizer] |

## Conoscenza {#knowledge}

| Competenza | Funzionamento | Accesso | Prodotto | Back-end (flusso di dati) |
|---|---|---|---|---|
| `product-knowledge` | Rispondi alle domande pratiche/concettuali dalla documentazione di [!DNL Marketo Optimizer] su Experience League. | Lettura | Entrambi | Legge i documenti esterni — nessun dato di prodotto |

## Back-end incrociato {#cross-backend}

Queste abilità si estendono su più back-end:

- **`adapt-program`** — `gather_program_assets` legge [!DNL Marketo Engage] (`get_program`, `get_smart_campaign`, `list_emails`), quindi scrive tramite `falcomcp_create_journey` — cross-backend classico.
- **`audience-creation`** - legge [!DNL Marketo Engage] elenchi smart (`get_smart_list` / `get_smart_campaign`), quindi scrive [!DNL Marketo Optimizer] elenchi di persone.
- **`journey-observability`** - [!DNL Marketo Optimizer] letture più `check_lead_in_marketo_static_list` [!DNL Marketo Engage] lette.
- **`scoring-studio`** - legge [!DNL Marketo Engage] tipi di campi/attività lead insieme al servizio di punteggio [!DNL Marketo Optimizer].

Tutti gli strumenti `falco-mcp_*` e percorsi/token/scoring/STO/FCS hanno raggiunto [!DNL Marketo Optimizer] servizi; gli strumenti CSV/program/lead hanno raggiunto [!DNL Marketo Engage].
