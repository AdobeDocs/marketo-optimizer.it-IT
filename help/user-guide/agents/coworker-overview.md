---
title: Panoramica di CX Enterprise Coworker in Adobe Marketo Optimizer
description: Scopri come CX Enterprise Coworker utilizza le competenze Marketo Optimizer per creare e adattare programmi, verificare la preparazione alle decisioni basate sull’intelligenza artificiale e chiamare gli strumenti MCP.
autotag-review: '2026-11-24T22:43:00.917Z'
TQID: https://experienceleague.adobe.com/V4Kww-NcdfbFxXqWrs7mPq7UYu8AREqDgyfvlMnlURM
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 1650dadf-b034-5ac9-a309-77ad1e2f5035
    internal-label: Chat Interface
  - id: 5229c72e-d79b-574f-a03e-5c4bf48172c3
    internal-label: AI Decisioning
  - id: a29661b8-f7a4-53d1-a9ac-fdec08c092e4
    internal-label: Programs
subfeature_v2:
  - id: b9e5c7f3-be30-563c-9e41-cc8ea76e2fee
    internal-label: Skills
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: bbbea26f-9621-49eb-9ab8-e06fb3bbce8c
    internal-label: Artificial intelligence
source-git-commit: 418b81a0a39eca0ca7b537c76da972df7eefd09f
workflow-type: tm+mt
source-wordcount: '1313'
ht-degree: 2%
---

# [!DNL CX Enterprise Coworker] in [!DNL Adobe Marketo Optimizer] {#coworker-overview}

La chat di [!DNL CX Enterprise Coworker] è un&#39;interfaccia di conversazione per il completamento delle attività in [!DNL Adobe Marketo Optimizer]. Descrivere un obiettivo in linguaggio semplice e [!DNL Coworker] pianifica le attività, le esegue in [!DNL Marketo Optimizer], convalida i risultati e fornisce il lavoro completato per l&#39;approvazione.

[!DNL Coworker] utilizza le abilità create per [!DNL Marketo Optimizer] per guidarti attraverso le attività comuni delle operazioni di marketing: creazione di un nuovo programma, adattamento di un programma [!DNL Marketo Engage] esistente e verifica se i tuoi dati sono pronti per le decisioni di IA.

[!DNL Coworker] rispetta le [[!DNL Marketo Optimizer] autorizzazioni](../start/permissions-reference.md) esistenti della tua organizzazione. È possibile eseguire solo le azioni che sono già consentite e gli amministratori controllano quando si dispone dell&#39;accesso in scrittura. [!DNL Coworker] fa parte dell&#39;ecosistema Adobe e non è limitato a [!DNL Marketo Optimizer].

Per ulteriori informazioni, consulta:

* [Panoramica chat di [!DNL Adobe CX Enterprise Coworker]](https://experienceleague.adobe.com/en/docs/coworker/content/chat/overview)
* [Interfaccia chat in [!DNL Marketo Optimizer]](./chat-interface.md)
* [[!DNL Coworker] abilità in [!DNL Marketo Optimizer]](./skills.md)

## [!DNL Marketo Optimizer] abilità in [!DNL CX Enterprise Coworker] {#skills}

Utilizza le seguenti competenze specifiche per il prodotto per creare e adattare programmi o valutare la preparazione ai dati.

| Competenza | Cosa ti aiuta a fare | Richiesta di esempio |
| --- | --- | --- |
| `program-creation-marketo-optimizer` | Creare un programma di marketing [!DNL Marketo Optimizer] end-to-end. [!DNL Coworker] ti guida dall&#39;obiettivo a un programma generato. | Carica una descrizione della campagna, quindi chiedi: _Crea un programma utilizzando la descrizione allegata._ |
| `adapt-program-marketo-optimizer` | Adattare, migrare o convertire un programma [!DNL Marketo Engage] esistente in un programma [!DNL Marketo Optimizer]. | _Adattare il programma Q3 Enterprise Webinar Nurture da [!DNL Marketo Engage] a [!DNL Marketo Optimizer]._ |
| `ai-decisioning-health-marketo-optimizer` | Segnala se i dati del tenant sono pronti per le decisioni di intelligenza artificiale, coprendo la copertura delle storie, la ricchezza delle caratteristiche e la copertura della persona. | _Quali dati vengono utilizzati per le decisioni basate sull&#39;intelligenza artificiale?_ |

### Esempio di prompt di creazione del programma {#program-creation-prompt}

Carica una descrizione o descrivi direttamente il programma. Includi il pubblico, il percorso, il contenuto e le impostazioni che desideri che [!DNL Coworker] utilizzi.

Il diagramma riepiloga le sezioni dei prompt nell’esempio seguente. Mostra come organizzare la richiesta, non l’ordine in cui le persone si spostano all’interno del percorso.

![Otto sezioni della richiesta di creazione del programma: obiettivo del programma, pubblico, percorso con inviti basati su intento, contenuto e-mail, attivazione di LinkedIn, gestione della registrazione, follow-up post-evento e impostazioni.](./assets/coworker-program-creation-prompts.svg){width="800" zoomable="yes"}

Espandi ogni sezione per visualizzare il prompt di esempio.

+++Obiettivo del programma

_Crea un programma di marketing B2B denominato Experience Cloud Leadership Forum - AI-Powered Experience Summit, in esecuzione dal 3 agosto al 3 dicembre, utilizzando e-mail e LinkedIn. L&#39;evento si terrà al Bay Area Innovation Center alle 9 del mattino. Avvia il percorso immediatamente._

+++

+++Pubblico

_Esegui il targeting di persone con un intento di prodotto per Experience Cloud e un punteggio di coinvolgimento maggiore di 1. Escludi profili non sottoscritti e sospesi dal marketing._

+++

+++Percorso

_Utilizza il percorso migliore successivo per dividere il pubblico in base alle finalità di Medium, e Experience Cloud. Invia inviti e-mail personalizzati personalizzati e personalizzati a ogni livello di intento. Unisci i percorsi e attendi due giorni. Controlla le aperture delle e-mail, i clic, il coinvolgimento con i contenuti e le registrazioni. Invia un&#39;anteprima dell&#39;agenda ai membri coinvolti; attiva i membri non coinvolti in LinkedIn e attendi due giorni. Unisci i percorsi interessati e invia un promemoria di registrazione finale 10 giorni prima dell’evento. Abilita ottimizzazione ora di invio per tutte le e-mail._

+++

+++Contenuto e-mail

_Creazione di tre e-mail: invito esecutivo (6 settimane prima dell&#39;evento), anteprima agenda (sei settimane prima dell&#39;evento) e promemoria di registrazione finale (10 giorni prima dell&#39;evento). Includi argomenti pertinenti, intestazioni preliminari, inviti all’azione (Prenota il mio posto, Visualizza agenda, Registrazione completa) e contenuti personalizzati basati sull’intelligenza artificiale utilizzando la storia della persona, la classificazione personale, il settore, l’interesse per la soluzione, il coinvolgimento recente e le intenzioni di Experience Cloud. Includere un&#39;immagine del luogo nell&#39;invito ma nessun banner nell&#39;anteprima dell&#39;agenda._

+++

+++LinkedIn

_Indirizza i membri non coinvolti con contenuti sponsorizzati che promuovono la trasformazione della customer experience e la personalizzazione AI._

+++

+++Registrazione

_Uscire immediatamente i membri registrati dal percorso di inviti e inviare un&#39;e-mail di preparazione esecutiva con argomenti di discussione generati dall&#39;intelligenza artificiale, un&#39;agenda personalizzata, dettagli sul luogo, sessioni consigliate e un collegamento al calendario._

+++

+++Post-evento

_Indirizza i partecipanti al programma di follow-up per la leadership di Experience Cloud con un riepilogo, registrazioni, risorse e una revisione delle qualifiche di vendita. Inviare eventi di rilievo, contenuti on-demand e inviti di eventi futuri._

+++

+++Impostazioni

_Imposta my.replyToEmail su `events@example.com` e my.senderName su Experience Cloud Events. Utilizza un modello riutilizzabile in cui cambiano solo città, luogo, argomenti delle note chiave e focus sul settore._

+++

Per ulteriori informazioni sulla preparazione di una descrizione, vedere [Creare un programma da una descrizione](./program-from-brief.md).

## Casi d’uso di esempio {#use-cases}

### Crea un programma dopo aver verificato la fattibilità dei dati {#check-readiness-create-program}

Un lead di operazioni di marketing vuole sapere che il tenant è pronto per le decisioni di IA prima di creare un nuovo programma basato sull’account.

1. Per rivedere la copertura delle storie, la ricchezza delle caratteristiche e la copertura dell&#39;utente tipo, esegui il controllo di integrità [AI-decisioning](./ai-decisioning-health.md). Ad esempio, chiedi: _Mostra i dati Marketo utilizzati per le decisioni AI._
1. Risolvi eventuali lacune identificate dal rapporto.
1. Carica una descrizione della campagna e chiedi: _Crea un programma con la descrizione allegata._
1. Rivedi e approva il programma quando [!DNL Coworker] presenta il risultato.

Il risultato è una relazione di preparazione che identifica le carenze, seguita da un programma basato su dati che possono supportare le decisioni di IA.

### Sposta un programma [!DNL Marketo Engage] esistente in [!DNL Marketo Optimizer] {#adapt-program}

Un team di demand generation desidera un programma collaudato in esecuzione in [!DNL Marketo Optimizer] senza ricrearlo manualmente.

1. Denomina il programma [!DNL Marketo Engage] da adattare. Ad esempio: _Adattare il programma Q3 Enterprise Webinar Nurture da [!DNL Marketo Engage] a [!DNL Marketo Optimizer]._
1. [!DNL Coworker] mappa il programma su [!DNL Marketo Optimizer] costrutti e contrassegna tutto ciò che non viene convertito.
1. Rivedi il risultato e approvalo.

Il risultato è un programma convertito per la revisione, più un elenco di elementi che richiedono una decisione manuale.

## [!DNL Marketo Optimizer] strumenti MCP {#mcp-tools}

Le abilità [!DNL Coworker] chiamano i seguenti 37 strumenti sul server MCP (Model Context Protocol) [!DNL Marketo Optimizer]. Ogni nome di strumento contiene il prefisso `marketo-optimizer__`.

Questo riferimento riguarda gli strumenti documentati da abilità registrate, incluse le competenze di supporto utilizzate durante un flusso di lavoro. Non indica lo stato di distribuzione o la frequenza di utilizzo. I nomi delle abilità in questa tabella seguono il riferimento dello strumento e possono differire dai nomi delle abilità specifici del prodotto elencati sopra.

| Strumento | Competenze | Finalità |
| --- | --- | --- |
| `marketo-optimizer__get_workspace_root_tree` | `program-creation-marketo-optimizer` | Trova l’area di lavoro o la sottocartella denominata per un nuovo programma. |
| `marketo-optimizer__create_program` | `program-creation-marketo-optimizer` | Crea un programma nella zona o cartella confermata. |
| `marketo-optimizer__list_programs` | `program-creation-marketo-optimizer`, `landing-page-authoring` | Sfoglia i programmi o individua la posizione in cui archiviare una pagina di destinazione. |
| `marketo-optimizer__get_program` | `program-creation-marketo-optimizer` | Leggi un programma per ID. |
| `marketo-optimizer__update_program` | `program-creation-marketo-optimizer` | Aggiornare i metadati del programma, ad esempio il nome. |
| `marketo-optimizer__create_program_token` | `program-creation-marketo-optimizer` | Crea o correggi un token di programma approvato. |
| `marketo-optimizer__list_program_tokens` | `program-creation-marketo-optimizer` | Leggi i token risolti di un programma. |
| `marketo-optimizer__create_dynamic_people_list_with_rules` | `program-creation-marketo-optimizer` | Crea un elenco di persone collegate a un programma e genera regole per il pubblico da una descrizione. |
| `marketo-optimizer__list_people_journeys` | `adapt-program`; riferimento condiviso plug-in canale | Verifica la presenza di un conflitto nel nome del percorso di destinazione, individua un percorso esistente dopo un risultato non chiaro oppure sfoglia i percorsi per individuare il lavoro del canale. |
| `marketo-optimizer__create_person_journey` | `program-creation-marketo-optimizer`, `adapt-program`, `channel-content-authoring` | Crea un percorso collegato a un programma, avvia un percorso adattato o crea un percorso mancante per un canale e-mail. |
| `marketo-optimizer__get_person_journey` | `program-creation-marketo-optimizer`, `adapt-program`; riferimento condiviso plug-in canale | Leggi un percorso o la relativa area di lavoro, verifica le modifiche in staging o cerca un percorso per il lavoro del canale. |
| `marketo-optimizer__update_person_journey` | `adapt-program` | Aggiungi un passaggio di build approvato alla volta al percorso di destinazione. |
| `marketo-optimizer__run_person_journey_simulation` | `program-creation-marketo-optimizer` | Convalidare un flusso di percorso senza pubblicare. |
| `marketo-optimizer__run_program_qa` | `program-creation-marketo-optimizer` | Eseguire un controllo di sola lettura del programma e dei relativi percorsi. |
| `marketo-optimizer__create_channel` | `channel-content-authoring`; `program-creation-marketo-optimizer` e `image-to-html` tramite handoff | Crea e collega un canale. Per l’e-mail, la prima chiamata elenca i modelli; la seconda utilizza il modello selezionato per creare e collegare l’e-mail. |
| `marketo-optimizer__get_channel` | `channel-content-authoring` | Leggi un canale, includendo facoltativamente l’oggetto e-mail e il HTML. |
| `marketo-optimizer__list_channels` | `channel-content-authoring` | Sfoglia i canali per tipo, facoltativamente filtrati per nome. |
| `marketo-optimizer__update_channel_content` | `channel-content-authoring`; `image-to-html` tramite handoff | Aggiornare l’oggetto di un’e-mail o il HTML di un’e-mail, inclusa l’applicazione di HTML convertito. |
| `marketo-optimizer__image_to_html` | `image-to-html` | Avvia una conversione asincrona della progettazione dell’e-mail e recupera il HTML modificabile. |
| `marketo-optimizer__list_asset_library_images` | `landing-page-authoring` | Cerca le immagini sostitutive per gli slot della pagina di destinazione. |
| `marketo-optimizer__add_asset_to_program_or_folder` | `landing-page-authoring` | Registra una nuova pagina di destinazione nel programma o nella cartella Optimizer selezionata. |
| `marketo-optimizer__get_person_story` | `personalization-engine-health` | Leggi la storia di personalizzazione di una persona per ID numerico. |
| `marketo-optimizer__get_persona_story` | `personalization-engine-health` | Leggi la storia per un nome utente tipo esatto. |
| `marketo-optimizer__run_arbitration` | `personalization-engine-health` | Dopo un’esplicita conferma, ricalcola i punteggi e riseleziona i percorsi per le persone qualificate. |
| `marketo-optimizer__get_arbitration_summary` | `personalization-engine-health` | Leggi le statistiche di riepilogo per l’ultima esecuzione dell’arbitrato. |
| `marketo-optimizer__get_arbitration_decisions` | `personalization-engine-health` | Leggi le decisioni per persona dall’ultima esecuzione dell’arbitrato. |
| `marketo-optimizer__get_ai_decisioning_health_summary` | `ai-decisioning-health` | Recupera il rapporto complessivo di preparazione del tenant. |
| `marketo-optimizer__get_persona_distribution` | `ai-decisioning-health` | Segnala i conteggi e le percentuali degli utenti tipo. |
| `marketo-optimizer__get_people_without_personas` | `ai-decisioning-health` | Segnala il numero e la condivisione di persone senza un utente tipo. |
| `marketo-optimizer__get_person_story_attribute_coverage` | `ai-decisioning-health` | Misura la copertura delle caratteristiche e delle categorie e identifica i campi compilati. |
| `marketo-optimizer__get_person_story_data_completeness` | `ai-decisioning-health` | Riporta la ricchezza, la completezza e la variazione della storia in base alla persona. |
| `marketo-optimizer__get_person_story_coverage` | `ai-decisioning-health` | Segnala la copertura della storia, le tendenze e la generazione in sospeso. |
| `marketo-optimizer__get_personalization_story_pipeline_status` | `ai-decisioning-health` | Leggi lo stato della pipeline, la cronologia di esecuzione e la durata riportata. |
| `marketo-optimizer__get_person_story_refresh_backlog` | `ai-decisioning-health` | Conta storie in attesa di aggiornamento perché i dati di origine sono cambiati. |
| `marketo-optimizer__get_person_intent_signal_coverage` | `ai-decisioning-health` | Misura le finalità del prodotto, le finalità delle parole chiave e la copertura delle attività. |
| `marketo-optimizer__get_person_story_activity_coverage` | `ai-decisioning-health` | Report dei campi di coinvolgimento acquisiti e delle tendenze di attività aggregate. |
| `marketo-optimizer__get_person_audience_membership_distribution` | `ai-decisioning-health` | Segnala la media e la distribuzione delle appartenenze al pubblico per persona. |
