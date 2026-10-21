---
title: Autorizzazioni prodotto
description: Elenco di riferimento delle autorizzazioni di Experience Platform che controllano l’accesso alle funzioni di Marketo Optimizer, con descrizioni e autorizzazioni consigliate per gli utenti amministratori, con accesso completo e di sola lettura.
TQID: https://experienceleague.adobe.com/Q4HnGxPkiE0dsZUjIgPvVJHgs0dPwLJiOKVSL1edS4Y
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3cf5f37e-e87e-5179-812b-53ce05d7eebb
    internal-label: Setup
  - id: a659ad61-de21-559d-a901-02e2fb329ff5
    internal-label: Administration
subfeature_v2:
  - id: b6434e31-d7bb-5416-960c-1c77bb1a2e8d
    internal-label: User Access
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
autotag-review: '2026-10-20T17:03:48.312Z'
source-git-commit: a33f749c32631dcd77ecf2892bdc3b1a5e06cd66
workflow-type: tm+mt
source-wordcount: '1556'
ht-degree: 3%
---
# Autorizzazioni prodotto

Le seguenti autorizzazioni controllano l&#39;accesso alle funzionalità in [!DNL Adobe Marketo Optimizer]. Aggiungerli ai ruoli nell&#39;area _[!UICONTROL Autorizzazioni]_ di [!DNL Adobe Experience Platform]. Per informazioni dettagliate sulla creazione di ruoli e sull&#39;assegnazione di tali ruoli agli utenti, vedere [_Accesso utente e autorizzazioni_](./user-management.md).

Nelle ultime tre colonne vengono visualizzate le autorizzazioni consigliate per ciascuno dei [tipi di utente suggeriti](#suggested-user-types): Amministratore, Tutti gli utenti con accesso e Utente con accesso in sola lettura. Un segno di spunta (✔) indica che l&#39;autorizzazione è consigliata per quel tipo di utente e un trattino (-) indica che non lo è. Adatta i consigli in base alle esigenze della tua organizzazione.

>[!IMPORTANT]
>
>Per l&#39;accesso a [!DNL Marketo Optimizer] è necessario abilitare una sandbox specifica per la quale è stato eseguito il provisioning utilizzando la seguente convenzione per i nomi: `Mktoaep` + prefisso di sottoscrizione [!DNL Marketo Engage]. Ad esempio, se il prefisso della sottoscrizione [!DNL Marketo Engage] collegata è _AcmeAssoc_, la sandbox richiesta per l&#39;accesso [!DNL Marketo Optimizer] è _MktoaepAcmeAssoc_. Aggiungi questa sandbox a ogni ruolo.

>[!NOTE]
>
>Per visualizzare il riquadro _[!UICONTROL Autorizzazioni]_ in Experience Platform è necessario essere amministratore di sistema.

Alcune autorizzazioni si applicano alle funzioni non ancora disponibili nel prodotto. Gli amministratori possono aggiungere ora queste autorizzazioni in modo che gli utenti possano accedere quando le funzioni diventano disponibili.

## Tipi di utenti consigliati {#suggested-user-types}

Utilizza i consigli sulle autorizzazioni nelle tabelle di questa pagina come punto di partenza per i ruoli creati. Questi sono suggerimenti per ogni tipo di utente. Adattale alle esigenze della tua organizzazione.

| Attributo | Amministratore | Tutti gli utenti di accesso | Utente con accesso in sola lettura |
| --- | ----- | --------------- | --------------------- |
| **Per chi è** | Persone che hanno configurato e gestito [!DNL Marketo Optimizer] per il tuo team. | Esperti di marketing e operatori che lavorano ogni giorno in [!DNL Marketo Optimizer]. | Persone che devono visualizzare [!DNL Marketo Optimizer] ma non modificare nulla, ad esempio dirigenti, analisti e revisori. |
| **Come possono fare** | Tutto, comprese le impostazioni di configurazione e amministrazione. | Utilizza ogni funzione: percorsi, programmi, contenuti, elenchi, rapporti e l’assistente. | Visualizzare percorsi, programmi, contenuti, elenchi e rapporti e porre domande all&#39;assistente. |
| **Autorizzazioni da assegnare** | Ogni autorizzazione in questa pagina (seleziona **[!UICONTROL Aggiungi tutti]** nell&#39;editor ruoli). | Le autorizzazioni con un ✔ nella colonna _Accesso completo_ delle tabelle di questa pagina. | Le autorizzazioni con un ✔ nella colonna _Sola lettura_ delle tabelle di questa pagina. |
| **Non incluso** | – | <li>Configurazioni amministratore<li>Configurazioni del canale, comprese le impostazioni e-mail, i predefiniti per moduli, le impostazioni della pagina di destinazione e i predefiniti e le impostazioni WhatsApp<li>Tipi di programmi (visualizzazione e gestione) | <li>Creazione, modifica, eliminazione, pubblicazione o esportazione (tutte le autorizzazioni _Gestisci_ e _Pubblica_, ad eccezione dell&#39;accesso tramite chat)<li>Attivazione di tipi di pubblico nelle destinazioni<li>Configurazioni dell’amministratore e configurazioni del canale, inclusa la visualizzazione delle impostazioni e-mail e dei predefiniti per moduli<li>Visualizzazione dei tipi di programmi |
| **Gruppo utenti consigliato** | Gruppo Amministratori Marketo Optimizer | Marketo Optimizer Users Group | Gruppo utenti di sola lettura Marketo Optimizer |
| **Ruolo suggerito** | Amministratore Marketo Optimizer | Utente con accesso a tutti i Marketo Optimizer | Utente con accesso in sola lettura Marketo Optimizer |

Per la procedura per la creazione di questi gruppi e ruoli, vedere [Creare gruppi di utenti e ruoli per i tipi di utenti suggeriti](./user-management.md#create-suggested-roles).

## Contenuto e risorse {#content-assets}

| Categoria | Autorizzazione | Descrizione | Amministratore | Tutti gli accessi | Sola lettura |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| Assets B2B | Gestire Assets B2B | Crea, modifica ed elimina i file di risorse. | ✔ | ✔ | – |
| | Gestire le e-mail B2B | Crea, modifica ed elimina messaggi e-mail. | ✔ | ✔ | – |
| | Gestire il Forms B2B | Creare, modificare ed eliminare moduli. | ✔ | ✔ | – |
| | Gestire i frammenti B2B | Crea, modifica ed elimina frammenti di contenuto. | ✔ | ✔ | – |
| | Gestisci pagina di destinazione B2B | Crea, modifica ed elimina pagine di destinazione. | ✔ | ✔ | – |
| | Gestione esportazione messaggi B2B | Esporta i rapporti sui messaggi nella sezione _E-mail_. | ✔ | ✔ | – |
| | Gestire modelli B2B | Creare, modificare ed eliminare modelli di contenuto. | ✔ | ✔ | – |
| | Gestire i webinar B2B | Creare, modificare ed eliminare i webinar interattivi. | ✔ | ✔ | – |
| | Pubblicare Forms B2B | Pubblica i moduli da utilizzare nelle pagine di destinazione. | ✔ | ✔ | – |
| | Pubblicare frammenti B2B | Pubblica frammenti di contenuto da utilizzare in modelli, e-mail e pagine di destinazione. | ✔ | ✔ | – |
| | Pubblica pagina di destinazione B2B | Pubblicare le pagine di destinazione. | ✔ | ✔ | – |
| | Visualizza Assets B2B | Visualizza i dettagli della libreria Assets e del file di risorse. | ✔ | ✔ | ✔ |
| | Visualizza e-mail B2B | Visualizzare i messaggi e-mail. | ✔ | ✔ | ✔ |
| | Visualizza Forms B2B | Visualizza moduli. | ✔ | ✔ | ✔ |
| | Visualizzare frammenti B2B | Visualizzare l’elenco e i dettagli dei frammenti di contenuto. | ✔ | ✔ | ✔ |
| | Visualizza pagina di destinazione B2B | Visualizzare le pagine di destinazione. | ✔ | ✔ | ✔ |
| | Visualizza modelli B2B | Visualizzare l’elenco e i dettagli dei modelli di contenuto. | ✔ | ✔ | ✔ |
| | Visualizza webinar B2B | Visualizza i webinar interattivi. | ✔ | ✔ | ✔ |

## Configurazione e amministrazione dei canali {#channels-admin}

| Categoria | Autorizzazione | Descrizione | Amministratore | Tutti gli accessi | Sola lettura |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| Configurazioni amministratore B2B | Gestire le configurazioni dell’amministratore B2B | Configura le impostazioni di amministrazione, ad esempio le connessioni per la gestione delle risorse digitali, gli archivi delle risorse e gli eventi. | ✔ | – | – |
| Configurazioni del canale B2B | Gestione configurazioni canali B2B | Accedi alla voce di menu _Canali_ nell&#39;area di navigazione a sinistra e a tutte le operazioni di configurazione dei canali. | ✔ | – | – |
| | Gestione impostazioni e-mail B2B | Configurare le impostazioni e-mail. Queste impostazioni sono necessarie prima che gli utenti possano inviare e-mail. | ✔ | – | – |
| | Gestire il predefinito per Forms B2B | Creare, modificare ed eliminare predefiniti di modulo. | ✔ | – | – |
| | Gestione impostazioni pagina di destinazione B2B | Configura le impostazioni della pagina di destinazione, ad esempio i sottodomini. | ✔ | – | – |
| | Gestire i predefiniti WhatsApp B2B | Crea, visualizza ed elimina i predefiniti per messaggi WhatsApp e le impostazioni SMS associate. | ✔ | – | – |
| | Gestione impostazioni WhatsApp B2B | Configura le impostazioni del canale WhatsApp. | ✔ | – | – |
| | Pubblica predefinito Forms B2B | Pubblicare i predefiniti per moduli. | ✔ | – | – |
| | Visualizza impostazioni e-mail B2B | Visualizzare le impostazioni e-mail (sottodomini, record PTR, pool IP, elenchi di soppressione, elenchi di seed, piani di riscaldamento IP). | ✔ | – | – |
| | Visualizza predefinito Forms B2B | Visualizzare i predefiniti per moduli. | ✔ | – | – |

## Percorsi, programmi e cartelle {#journeys-programs}

| Categoria | Autorizzazione | Descrizione | Amministratore | Tutti gli accessi | Sola lettura |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| Token cartella B2B | Gestire i token delle cartelle B2B | Creare, modificare ed eliminare token nelle cartelle. Le modifiche vengono applicate a tutto ciò che si trova nella cartella, quindi assegnale separatamente da _Gestisci cartelle B2B_. | ✔ | ✔ | – |
| | Visualizza token cartelle B2B | Visualizza i token definiti nelle cartelle. | ✔ | ✔ | ✔ |
| Cartelle B2B | Gestire le cartelle B2B | Creare, modificare ed eliminare cartelle. | ✔ | ✔ | – |
| | Visualizzare le cartelle B2B | Visualizza cartelle. | ✔ | ✔ | ✔ |
| Percorsi B2B | Gestire il controllo del traffico di Percorso B2B | Configurare il controllo del traffico di percorso, inclusa la simulazione dell&#39;effetto. | ✔ | ✔ | – |
| | Gestire Percorsi di persone B2B | Accesso all&#39;elenco _Percorsi di persone_ e a tutte le operazioni del percorso di persone. | ✔ | ✔ | – |
| | Pubblicare Percorsi di persone B2B | Pubblicare percorsi di persone. | ✔ | ✔ | – |
| | Visualizza controllo del traffico di Percorso B2B | Visualizzare le impostazioni di controllo del traffico di percorso. | ✔ | ✔ | ✔ |
| | Visualizza rapporti Percorso di persone B2B | Visualizza i report percorso di persone, incluso il report _Individuale Percorso di persone_. | ✔ | ✔ | ✔ |
| | Visualizza Percorsi di persone B2B | Accesso in sola lettura all&#39;elenco _Percorsi di persone_ e ai dettagli del percorso. | ✔ | ✔ | ✔ |
| Token del programma B2B | Gestire i token del programma B2B | Crea, modifica ed elimina token su programmi e tipi di programmi. | ✔ | ✔ | – |
| | Visualizzare i token del programma B2B | Visualizza i token definiti per programmi e tipi di programmi. | ✔ | ✔ | ✔ |
| Tipi di programmi B2B | Gestire i tipi di programmi B2B | Crea, modifica ed elimina tipi di programmi di marketing. | ✔ | – | – |
| | Visualizza tipi di programmi B2B | Visualizzare i tipi di programmi di marketing. | ✔ | – | – |
| Programmi B2B | Gestire i programmi B2B | Crea, modifica ed elimina programmi di marketing. | ✔ | ✔ | – |
| | Visualizza programmi B2B | Visualizza programmi di marketing. | ✔ | ✔ | ✔ |

## Tipi di pubblico, finalità e destinazioni {#audiences-intent}

| Categoria | Autorizzazione | Descrizione | Amministratore | Tutti gli accessi | Sola lettura |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| Destinazioni B2B | Attivare le destinazioni B2B | Attiva i tipi di pubblico nelle destinazioni B2B. | ✔ | ✔ | – |
| | Gestire le destinazioni B2B | Creare, modificare ed eliminare destinazioni B2B. | ✔ | ✔ | – |
| | Visualizzare le destinazioni B2B | Accesso in sola visualizzazione alle destinazioni B2B. | ✔ | ✔ | ✔ |
| Configurazione intento B2B | Gestione configurazione intento B2B | Creare, modificare ed eliminare configurazioni intento. | ✔ | ✔ | – |
| | Visualizza configurazione intento B2B | Visualizzate le configurazioni intento (modelli di ponderazione intento). | ✔ | ✔ | ✔ |
| Regole organizzazione B2B | Gestire le regole dell’organizzazione B2B | Creare, modificare ed eliminare regole di organizzazione. | ✔ | ✔ | – |
| | Visualizza regole organizzazione B2B | Visualizzare le regole di organizzazione. | ✔ | ✔ | ✔ |
| Elenchi di persone B2B | Gestire gli elenchi di persone B2B | Crea, modifica ed elimina elenchi di persone e gestisci l’iscrizione a un elenco. | ✔ | ✔ | – |
| | Visualizzare gli elenchi di persone B2B | Visualizzare elenchi di persone statici e dinamici. | ✔ | ✔ | ✔ |

## Rapporti, laboratori e chat {#reports-labs-chat}

| Categoria | Autorizzazione | Descrizione | Amministratore | Tutti gli accessi | Sola lettura |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| Esperienza conversazionale B2B | Gestire l’esperienza conversazionale B2B | Accedi al pannello chat e all’assistente. Le azioni nel pannello richiedono anche l’autorizzazione per la funzione corrispondente. Ad esempio, la creazione di un percorso richiede _Gestione Percorsi di persone B2B_. Consulta [Autorizzazioni di chat](#chat-permissions). | ✔ | ✔ | ✔ |
| Labs B2B | Gestire i laboratori B2B | Abilita e configura le funzioni di Labs. | ✔ | ✔ | – |
| | Visualizza laboratori B2B | Visualizza le funzioni di Labs disponibili e abilitate. | ✔ | ✔ | ✔ |
| Reporting B2B | Visualizzare rapporti incorporati B2B | Visualizza i report nella scheda _Report_. | ✔ | ✔ | ✔ |
| | Visualizza rapporti intento B2B | Visualizzare i rapporti intento. | ✔ | ✔ | ✔ |

## Autorizzazioni di chat {#chat-permissions}

Le autorizzazioni di chat seguono le autorizzazioni a livello di funzione. [!DNL Coworker for Marketo Optimizer] controlla ogni abilità o azione in chat in base alla stessa autorizzazione necessaria per la funzione all&#39;esterno della chat: _Gestisci_ autorizzazioni per creare, modificare o pubblicare e _Visualizza_ autorizzazioni per le abilità di sola lettura. Se un utente non dispone dell&#39;autorizzazione per la funzionalità, [!DNL Coworker] non può eseguire l&#39;azione. Ad esempio, la creazione di un percorso richiede _Gestione Percorsi di persone B2B_, mentre l&#39;elenco dei moduli richiede _Visualizza Forms B2B_.

<!--
_Manage B2B Conversational Experience_ gives access to the [!DNL CX Coworker] chat panel, but it does not grant access to any feature functions.

Per wiki: 
Update 10/02: We are no longer mapping b2b-conversational-experience read or write to any tools. It was decided that chat will be available for all users without permissions, but what they can do within the chat (i.e. tools they can use) will be defined by other permissions.
-->

## Autorizzazioni delle destinazioni esterne {#external-destinations-permissions}

Per fornire l&#39;accesso alle destinazioni esterne agli utenti in [!DNL Marketo Optimizer], sono necessarie le seguenti autorizzazioni. Le colonne seguono le stesse raccomandazioni per ogni tipo utente descritto in [Tipi utente suggeriti](#suggested-user-types).

| Categoria | Autorizzazione | Descrizione | Amministratore | Tutti gli accessi | Sola lettura |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| Dashboard | Gestione dashboard standard | Aggiungi attributi personalizzati non ancora presenti nel data warehouse. | ✔ | ✔ | – |
| | Visualizza dashboard standard | Accesso in sola visualizzazione alle _dashboard dei profili_, _destinazioni_ e _segmenti_. Abilita inoltre l&#39;accesso a _Dashboard_ nel menu di navigazione a sinistra. | ✔ | ✔ | ✔ |
| Destinazioni | Attivare le destinazioni | Attiva i dati nelle destinazioni attive. _È necessario anche visualizzare le destinazioni_ o _gestire le destinazioni_. | ✔ | ✔ | – |
| | Attiva segmento senza mappatura | Attiva i tipi di pubblico nelle destinazioni esistenti senza il passaggio di mappatura. Gli utenti possono aggiungere e rimuovere tipi di pubblico nei flussi di lavoro di attivazione, ma non possono aggiungere o rimuovere attributi o identità mappati. _Visualizza destinazioni_ è obbligatorio. | ✔ | ✔ | – |
| | Authoring delle destinazioni | Creare destinazioni utilizzando Experience Platform Destination SDK. | ✔ | ✔ | – |
| | Gestire e attivare la destinazione del set di dati | Visualizza, crea, modifica e disabilita i flussi di esportazione dei set di dati e attiva i dati nei set di dati. _Visualizza destinazioni_ è obbligatorio. | ✔ | ✔ | – |
| | Gestire le destinazioni | Visualizzare, creare ed eliminare connessioni di destinazioni e account di destinazione. | ✔ | ✔ | – |
| | Visualizza destinazioni | Visualizza le destinazioni disponibili nella scheda _Catalogo_ e le destinazioni autenticate nella scheda _Sfoglia_. | ✔ | ✔ | ✔ |
| Governance dei dati | Gestire le etichette di utilizzo per l’eliminazione B2B | Visualizzare, creare ed eliminare le etichette di utilizzo dei dati (DULE) applicate ai set di dati e agli schemi. | ✔ | ✔ | – |
| | Gestire i criteri di utilizzo dei dati | Visualizza, crea, modifica ed elimina i criteri di utilizzo dei dati. | ✔ | ✔ | – |
| | Visualizza criteri di utilizzo dati | Accesso in sola visualizzazione per i criteri di utilizzo dei dati appartenenti alla tua organizzazione. | ✔ | ✔ | ✔ |
| Acquisizione dei dati | Gestisci origini | Visualizzare, creare, modificare e disattivare le origini. | ✔ | ✔ | – |
| | Visualizza origini | Visualizza le origini disponibili nella scheda _Catalogo_ e le origini autenticate nella scheda _Sfoglia_. | ✔ | ✔ | ✔ |
| Gestione profilo | Gestione impostazioni profilo | Visualizza e modifica tutte le impostazioni di profilo. | ✔ | ✔ | – |
| | Visualizza impostazioni profilo | Accesso in sola visualizzazione a tutte le impostazioni di profilo. | ✔ | ✔ | ✔ |

<!-- 

## Planned permissions {#planned-permissions}

The following permissions are for features that are not yet available in [!DNL Marketo Optimizer]. Adobe Marketo Qualifier permissions are not currently enforced. The estimated enforcement date is November 2026. Accounts and buying groups are targeted for delivery in Q1 2027.

| Category | Permission | Description | Admin | All Access | Read Only |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| Marketo Qualifier Configurations | Manage Marketo Qualifier Configurations | Create, edit, and delete Marketo Qualifier configurations. | ✔ | – | – |
| | View Marketo Qualifier Configurations | View Marketo Qualifier configurations. | ✔ | ✔ | ✔ |
| Marketo Qualifier Outbound | View Marketo Qualifier Outbound | View Marketo Qualifier outbound workflows and outbound reporting. | ✔ | ✔ | ✔ |
| Marketo Qualifier Research | Manage Marketo Qualifier Research | Use and manage research capabilities. | ✔ | ✔ | – |
| | View Marketo Qualifier Research | View research: conversational interface, prospect view, and account and lead research. | ✔ | ✔ | ✔ |
| B2B Account Lists | Manage B2B Account Lists | Create, edit, and delete account lists, including adding, removing, and importing accounts. | ✔ | ✔ | – |
| B2B Buying Groups | Manage B2B Buying Groups | Create, edit, and delete buying groups. | ✔ | ✔ | – |
| | Manage B2B Role Templates | Manage the role templates used in buying groups. | ✔ | ✔ | – |
| | Manage B2B Solution Interests | Manage the solution interests used in buying groups. | ✔ | ✔ | – |
| | Manage B2B Stages | Manage buying group stages. | ✔ | ✔ | – |
| | View B2B Buying Groups | View buying groups. | ✔ | ✔ | ✔ |

-->
