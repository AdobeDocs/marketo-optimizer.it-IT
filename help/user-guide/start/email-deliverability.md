---
title: Configurazione recapito e-mail
description: Configura la delega dei sottodomini, DMARC, SPF, DKIM e i pool IP per Marketo Optimizer.
TQID: 'https://experienceleague.adobe.com/-7yEXTaOrGIfCFw-UzanMqA9VJ1Nk-BmdmE2JJJSoB4'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2: id: 3c1de303-7a7c-59a6-abca-8c534730e19cid: 3cf5f37e-e87e-5179-812b-53ce05d7eebbid: 64b90904-e4f0-5c1b-a871-8c6a40b204a1id: a659ad61-de21-559d-a901-02e2fb329ff5id: d4203578-d294-5145-b397-f26f4488a904
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: e0eb8757-182f-49f3-94a4-1587d16f5094id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 2502
ht-degree: 0%

---

# Recapitabilità delle e-mail

Le informazioni seguenti sono destinate agli amministratori che configurano l’infrastruttura di invio per supportare gli addetti al marketing e i creatori di contenuti e-mail. Descrive le funzioni di recapito messaggi e come configurare i sottodomini, l’autenticazione e i pool IP.

Il recapito messaggi e-mail in [!DNL Adobe Marketo Optimizer] è il set di configurazioni di infrastruttura e autenticazione che consentono ai messaggi e-mail di raggiungere la casella in entrata del destinatario, non la cartella di posta indesiderata e non bloccati dagli ISP (provider di servizi Internet).

Utilizza i seguenti blocchi predefiniti, configurati da un amministratore, in genere nell’ordine seguente:

1. [Delega uno o più sottodomini](#subdomain-delegation) ad Adobe.
1. [Configura i record DMARC, SPF e DKIM](#dmarc-spf-dkim) in ciascun sottodominio.
1. [Conferma il pool IP](#ip-pools) utilizzato per inviare e-mail per il tuo sottodominio.
1. [Crea una o più configurazioni del canale e-mail](../admin/email-channel-configuration.md#create-email-channel-configuration) che associano un sottodominio, un pool IP e un&#39;identità mittente.

![Configurazione del recapito messaggi e-mail per Marketo Optimizer](./assets/email-deliverability-diagram.svg){width="600"}

>[!TIP]
>
>Considera il recapito messaggi e la configurazione dei canali come un’attività amministratore una tantum. Una volta configurata, gli addetti al marketing e gli autori di e-mail non dovranno più visitarla.
>
> Per ulteriori informazioni sui canali e-mail, consulta i seguenti argomenti:
>
>* Configurazione dei canali e-mail - [Configurazione del canale e-mail](../admin/email-channel-configuration.md)
>* Creazione di e-mail - [Aggiungi e-mail ai percorsi](../marketing/email-channel.md)
>* Progettazione di contenuti e-mail - [Authoring di contenuti e-mail](../content/email-authoring.md)

## Limitazioni attuali {#limitations}

* **Il metodo di delega personalizzato** per la delega del sottodominio non è ancora disponibile. Utilizza Fully Delegated o CNAME. Per la versione GA è prevista la delega personalizzata.
* **Pool IP dedicati** non disponibili in Beta. L&#39;unica opzione è il pool IP condiviso. Gli IP dedicati vengono forniti in GA, inclusa la pianificazione del riscaldamento IP e la gestione dei record PTR.

## Concetti chiave {#key-concepts}

Prima di configurare l’e-mail, esamina i concetti seguenti che si applicano alle funzioni di consegna del canale e-mail:

| Concetto | Cosa significa in [!DNL Marketo Optimizer] |
| ------- | ---------------------- |
| **_Sottodominio_** | Parte delegata del dominio di invio (ad esempio, `mail.contoso.com`) utilizzata per inviare messaggi di posta elettronica tramite [!DNL Marketo Optimizer]. I sottodomini isolano la reputazione di marketing B2B dalla posta aziendale o transazionale. |
| **_Pool IP_** | Un gruppo di indirizzi IP associati a uno o più sottodomini. [!DNL Marketo Optimizer] supporta un pool IP condiviso gestito da Adobe in questa versione; i pool IP dedicati sono nella roadmap di GA. |
| **_Configurazione canale_** | Un set riutilizzabile di impostazioni di invio e-mail (identità del mittente, indirizzo di risposta, sottodominio, pool IP, tipo e-mail e tracciamento) da allegare alle azioni e-mail nei percorsi. Puoi avere più configurazioni di canale denominate per diversi marchi, business unit o tipi di invio. |

<!--

## Roles and permissions {#roles-permissions}

[!DNL Marketo Optimizer] uses role-based access control (RBAC) for email features. Permissions are managed in the Adobe Admin Console (IMS) and synced at login. Product administrators assign granular permissions to product profiles, and then attach those product profiles to users.

Access to email functionality in [!DNL Marketo Optimizer] is gated by two layers:

1. **Feature flag (LD).** A LaunchDarkly flag controls whether the entire feature is turned on for your organization. Email authoring and deliverability are gated by `dx_ajo_btob_channel_foundation`. Without this flag, the feature is hidden regardless of permissions.
2. **Functional permission.** A user-level permission that controls whether a specific user can read or write within a feature.

Most email features follow a `view-*` (read) and `manage-*` (write) pattern. A user needs the read permission to see a feature in the navigation, and the write permission to create, edit, or delete within it.

### Email authoring permissions {#email-authoring-permissions}

| Capability | Permission | What it allows |
| ---------- | ---------- | -------------- |
| **View emails** | `view-b2b-emails` | View the email list, open emails, view content (read-only). |
| **Create / edit / delete emails** | `manage-b2b-emails` | All read access plus create, edit, duplicate, and delete emails. Required to author email content within a journey. |
| **View templates** | `view-b2b-templates` | Browse and preview templates in the Templates gallery (read-only). |
| **Create / edit / delete templates** | `manage-b2b-templates` | All read access plus create, edit, and delete saved templates. |
| **View fragments** | `view-b2b-fragments` | Browse and preview visual fragments (read-only). |
| **Create / edit fragments** | `manage-b2b-fragments` | All read access plus create and edit visual fragments. |
| **Publish fragments** | `publish-b2b-fragments` | Publish a fragment so it becomes available to email authors across the organization. |
| **Manage shared assets and library items** | `manage-b2b-library-items` | Manage the underlying shared library used by templates, fragments, and emails. Often granted alongside the template/fragment manage permissions. |
| **Manage usage labels** | `manage-b2b-delete-usage-labels` | Manage data usage labels (DULE) attached to library items for governance. |
| **Manage packages** | `manage-b2b-packages` | Bundle and move templates, fragments, and emails between sandboxes. |
| **View assets (Marketo Design Studio assets in [!DNL Marketo Optimizer])** | `view-b2b-assets` | Browse the asset picker and preview images. Read-only. |
| **Manage assets** | `manage-b2b-assets` | All read access plus future asset-management actions (Beta scope). |
| **Export message data** | `manage-b2b-message-export` | Export email-level message data and reports. |

Within a person journey, the **Send email** action requires `manage-b2b-person-journeys` (to add the action and activate the journey). A user with only email permissions can author content but cannot add an email to a journey.

### Email deliverability permissions {#email-deliverability-permissions}

Deliverability features (subdomains, DMARC, IP pools, suppression lists, allowed lists, IP warmup plans, and seed lists) are administrator-level configuration. They are governed by two permissions covering the entire **[!UICONTROL Channels]** > **[!UICONTROL Email settings]** area:

| Capability | Permission | What it allows |
| ---------- | ---------- | -------------- |
| **View email settings** | `view-b2b-email-settings` | View subdomains, PTR records, IP pools, suppression list, allowed list, IP warmup plans, and seed lists (read-only). |
| **Manage email settings** | `manage-b2b-email-settings` | All read access plus delegate subdomains, configure DMARC, manage suppression and allowed lists, manage IP warmup plans and seed lists. |

Some sub-features within Email settings are gated by additional LaunchDarkly flags — Suppression list (`enable-suppression`), Allowed list (`enable-allow-list`), Seed lists (`enable-seedlist-ui`). If a sub-feature is not visible in your organization, check with your Adobe representative on flag enablement.

### Channel configuration permissions {#channel-configuration-permissions}

Channel configurations sit under **[!UICONTROL Channels]** → **[!UICONTROL General settings]**. They tie deliverability primitives (subdomain, IP pool, sender identity) to a reusable object that journey authors reference. They are governed by a single permission:

| Capability | Permission | What it allows |
| ---------- | ---------- | -------------- |
| **Manage channel configurations** | `manage-b2b-channels-configurations` | View, create, edit, and delete email channel configurations. |

-->

## Delega dei sottodomini {#subdomain-delegation}

La delega dei sottodomini comunica a Internet che Adobe è autorizzato a inviare e-mail per conto di un sottodominio specifico (ad esempio, `mail.contoso.com`) del tuo dominio. La delega di un sottodominio dedicato, anziché del dominio principale, protegge la posta aziendale e offre i seguenti vantaggi:

* **Isolamento reputazione.** Gli invii di marketing sono tenuti separati dalla posta aziendale. Se la reputazione di marketing diminuisce, i messaggi aziendali e transazionali non subiranno modifiche.
* **Riscaldamento IP più veloce.** I sottodomini dedicati aiutano a stabilire più rapidamente una reputazione positiva del mittente con gli ISP.
* **Autenticazione moderna.** SPF, DKIM e DMARC possono essere configurati in modo pulito per sottodominio senza influire sugli altri flussi di posta.
* **Conformità.** Consente di soddisfare i requisiti di invio in blocco da Gmail, Yahoo e altri importanti ISP.

>[!NOTE]
>
>Ogni sottodominio in [!DNL Marketo Optimizer] può essere utilizzato solo da un prodotto Adobe. Impossibile condividere lo stesso sottodominio di invio tra [!DNL Marketo Optimizer] e un altro prodotto come Adobe Marketo Engage o Adobe Campaign. È necessario utilizzare sottodomini distinti.

### Metodi supportati {#supported-methods}

[!DNL Marketo Optimizer] supporta due dei tre metodi di delega dei sottodomini in questa versione di Beta. Il terzo metodo (Delega personalizzata) si trova nella roadmap.

| Metodo | Quando utilizzare | Che cosa implica |
| ------ | ----------- | ---------------- |
| **Delega completa** | Consigliato | Delega l’autorità DNS completa per il sottodominio ad Adobe. Adobe crea e gestisce record MX, SPF, DKIM, DMARC, A e CNAME. Sovraccarico operativo minimo. Adobe gestisce le modifiche DNS per te. |
| **CNAME** | Per criteri con restrizioni | Mantieni l’autorità DNS al tuo fianco e crea record CNAME che puntano ai record gestiti da Adobe. Utilizzalo quando i criteri DNS della tua organizzazione non consentono la delega completa. Sei responsabile della gestione dei record DNS. |
| **Delega personalizzata** | Roadmap (GA) | Mantenere la piena proprietà dei certificati DNS e SSL. Offre il massimo controllo, inclusa la possibilità di utilizzare certificati personalizzati. Questa è la destinazione per la versione GA. |

### Delegare un sottodominio (metodo Fully Delegated) {#delegate-fully-delegated}

>[!PREREQUISITES]
>
>* Decidi su una convenzione di denominazione del sottodominio (ad esempio, `mail.contoso.com` per il marketing, `alerts.contoso.com` per le transazioni).
>* Conferma con il tuo team IT/DNS di poter delegare il sottodominio (record NS) ad Adobe.
>* Crea il nuovo sottodominio nel provider DNS, quindi attendi 24-48 ore per la propagazione DNS prima di delegare ad Adobe.
>* Conferma di disporre del ruolo di amministratore in [!DNL Marketo Optimizer].

1. Nella barra di navigazione a sinistra di [!DNL Marketo Optimizer], espandi **[!UICONTROL Amministrazione]** e seleziona **[!UICONTROL Canali]**.
1. Nel pannello, espandi **[!UICONTROL Impostazioni e-mail]** e seleziona **[!UICONTROL Sottodomini]**.
1. Fare clic su **[!UICONTROL Configura sottodominio]**.
1. Immettere il nome completo del sottodominio, ad esempio `mail.contoso.com`.
1. Scegliere **[!UICONTROL Delega completa]** come metodo di delega.
1. Configurare DMARC per il sottodominio (vedere [DMARC, SPF e DKIM](#dmarc-spf-dkim)).

   Imposta almeno un record DMARC con un criterio di avvio di `none` per monitorare i report senza influire sulla consegna.

1. Esamina l’elenco dei record DNS da gestire in Adobe.

   In genere includono i record MX, SPF, DKIM, DMARC, A e CNAME (per il tracciamento e gli URL delle pagine mirror).

1. Scarica i record DNS come file CSV utilizzando il pulsante **[!UICONTROL Scarica record]**. Condividi questo file con il tuo team DNS.

1. Il team DNS aggiunge i record NS nella soluzione di hosting del dominio che delegano il sottodominio ad Adobe.

1. Dopo che il team DNS ha confermato la disponibilità dei record, tornare a [!DNL Marketo Optimizer] e selezionare la casella di controllo che conferma la creazione dei record richiesti nel sito di hosting.

1. Fai clic su **[!UICONTROL Invia]** per avviare una serie di controlli di convalida (pre-convalida, MX, SPF, DKIM, DMARC, registrazione FBL).

1. Attendere che lo stato del sottodominio passi a **[!UICONTROL Operazione completata]**.

   Questa operazione richiede in genere alcuni minuti dopo il completamento della propagazione DNS.

>[!NOTE]
>
>Se la convalida non riesce, lo stato diventa **[!UICONTROL Non riuscito]** e [!DNL Marketo Optimizer] viene visualizzato il motivo (ad esempio, record NS non trovato, record MX mancante o configurazione errata di DMARC). Correggi il problema DNS sottostante, quindi riprova l’invio.

### Delega un sottodominio (metodo CNAME) {#delegate-cname}

Utilizzare questo metodo solo se il criterio DNS dell&#39;organizzazione non consente la delega completa. Con CNAME puoi mantenere i record DNS al tuo fianco.

1. Nella barra di navigazione a sinistra di [!DNL Marketo Optimizer], espandi **[!UICONTROL Amministrazione]** e seleziona **[!UICONTROL Canali]**.
1. Nel pannello, espandi **[!UICONTROL Impostazioni e-mail]** e seleziona **[!UICONTROL Sottodomini]**.
1. Fare clic su **[!UICONTROL Configura sottodominio]**.
1. Immetti il nome completo del sottodominio.
1. Scegliere **[!UICONTROL CNAME]** come metodo di delega.
1. Configurare DMARC per il sottodominio ([DMARC, SPF e DKIM](#dmarc-spf-dkim)).
1. Esamina l’elenco dei record CNAME da generare. Questi puntano i componenti del sottodominio ai record gestiti da Adobe.
1. Scarica i record come CSV e condividili con il tuo team DNS.
1. Il team DNS aggiunge ogni record CNAME alla soluzione di hosting DNS.
1. Quando i record sono presenti e propagati, tornare a [!DNL Marketo Optimizer] e confermare.
1. Fai clic su **[!UICONTROL Invia]**.
1. Attendere che lo stato raggiunga il **[!UICONTROL successo]**.

>[!IMPORTANT]
>
>Con CNAME, Adobe non può aiutarti a modificare, gestire o risolvere i problemi DNS per il sottodominio. Eventuali modifiche future, ad esempio l’aggiunta di un nuovo CNAME per un aggiornamento della funzione, devono essere apportate dal team DNS.

Per istruzioni dettagliate sui provider DNS comuni, consulta le sezioni seguenti:

### Aggiungi record CNAME per provider DNS {#add-cname-records-dns-provider}

[!DNL Marketo Optimizer] genera i record CNAME e TXT esatti per il tuo sottodominio e ti consente di scaricarli come file CSV. Utilizza i seguenti passaggi specifici per il provider per aiutare il team DNS a individuare la schermata delle impostazioni corretta e aggiungere ogni record.

>[!NOTE]
>
>I valori di host, tipo e destinazione nel file CSV scaricato sono specifici per il tuo sottodominio e organizzazione. Copiali esattamente anziché riutilizzare i valori di un altro sottodominio.

#### AWS Route 53 {#aws-route-53}

1. Accedere ad AWS Management Console e aprire **[!UICONTROL Route 53]**.
1. Seleziona **[!UICONTROL Zone ospitate]**, quindi scegli la zona ospitata per il tuo dominio.
1. Fare clic su **[!UICONTROL Crea record]** e mantenere i criteri di routing impostati su **[!UICONTROL Routing semplice]**.
1. Per ogni riga nel file CSV:

   * **Nome record** - Immettere solo la parte che precede il nome della zona. Ad esempio, per `data.mail.contoso.com` nella zona `contoso.com`, immettere `data.mail`.
   * **Tipo di record** - Scegliere `CNAME` o `TXT` per ottenere la corrispondenza con il file CSV.
   * **Valore** - Incolla la destinazione dal file CSV. Per i record TXT, racchiudere il valore tra virgolette doppie.
   * **TTL** — 300 secondi sono sufficienti.

1. Fai clic su **[!UICONTROL Aggiungi un altro record]** alle voci batch, quindi su **[!UICONTROL Crea record]** dopo l&#39;immissione di tutte le righe.

>[!NOTE]
>
>I valori TXT devono essere racchiusi tra virgolette doppie, altrimenti il record non supera la convalida. Un record CNAME non può trovarsi all’apice della zona, ma questo non influisce su un sottodominio delegato.

#### Nuvola {#cloudflare}

1. Accedi al dashboard di Cloudflare e seleziona il tuo dominio.
1. Vai a **[!UICONTROL Record DNS]** e fai clic su **[!UICONTROL Aggiungi record]**.
1. Per ogni riga nel file CSV:

   * **Tipo** — Scegliere `CNAME` o `TXT`.
   * **Nome** — Immettere la porzione dell&#39;host, ad esempio `data.mail`. Cloudflare aggiunge automaticamente il dominio.
   * **Destinazione** (per CNAME) o **Contenuto** (per TXT) - Incolla il valore dal file CSV.
   * **Stato proxy** — Imposta su **[!UICONTROL Solo DNS]** (icona cloud grigio).
   * **TTL** — Lascia come **[!UICONTROL Auto]**.

1. Fai clic su **[!UICONTROL Salva]** per ogni riga.

>[!IMPORTANT]
>
>Ogni record aggiunto per [!DNL Marketo Optimizer] deve mostrare una nuvola grigia (solo DNS) e non una nuvola arancione (proxy). Un record proxy indirizza il traffico attraverso i server di Cloudflare invece di Adobe, interrompendo la firma di DKIM, il tracciamento dei clic e la gestione dei messaggi non recapitati. Se un record è di colore arancione, fare clic sull&#39;icona del cloud per impostarla su grigio.

#### DNS AZURE {#azure-dns}

1. Accedi al portale Azure e apri **[!UICONTROL zone DNS]**.
1. Selezionare la zona DNS per il dominio.
1. Fare clic su **[!UICONTROL + Set di record]**.
1. Per ogni riga nel file CSV:

   * **Nome** — Immettere la porzione dell&#39;host, ad esempio `data.mail`. Azure aggiunge il nome della zona.
   * **Tipo** — Scegliere `CNAME` o `TXT`.
   * Per un record CNAME, immetti la destinazione dal file CSV nel campo **[!UICONTROL Alias]**.
   * Per un record TXT, incolla il valore nel campo **[!UICONTROL Value]**. Azure gestisce le offerte per te.
   * **TTL** — immettere un numero e un&#39;unità, ad esempio 300 secondi.

1. Fare clic su **[!UICONTROL OK]** per salvare il set di record per ogni riga.

>[!NOTE]
>
>Utilizza un set di record CNAME standard, non l’opzione Set di record Alias, che punta solo alle risorse Azure anziché ai nomi host esterni. Ogni set di record CNAME contiene esattamente una destinazione, che corrisponde al modo in cui [!DNL Marketo Optimizer] genera record: un CNAME per host.

#### DNS di Google Cloud {#google-cloud-dns}

1. Apri la console Google Cloud e vai a **[!UICONTROL Servizi di rete]** > **[!UICONTROL DNS cloud]**.
1. Seleziona la zona per il dominio.
1. Fai clic su **[!UICONTROL Aggiungi standard]** per aggiungere un set di record.
1. Per ogni riga nel file CSV:

   * **Nome DNS** - Immettere la porzione host, ad esempio `data.mail`. Il DNS cloud mostra il suffisso della zona e l’host viene anteposto.
   * **Tipo di record di risorsa** — Scegliere `CNAME` o `TXT`.
   * **TTL** — 300 secondi sono sufficienti.
   * Per un record CNAME, immettere la destinazione in **[!UICONTROL Canonical name]** e terminarla con un punto finale.
   * Per un record TXT, incolla il valore nel campo dati.

1. Fai clic su **[!UICONTROL Crea]** per ogni riga.

>[!NOTE]
>
>Il nome canonico deve essere completo e terminare con un punto finale, altrimenti la risoluzione non riesce. Il tuo team DNS può anche aggiungere ogni record con il comando `gcloud dns record-sets create`.

### Guardrail del sottodominio {#subdomain-guardrails}

* **Limite predefinito:** 10 sottodomini per organizzazione. Contatta il tuo rappresentante Adobe se ne hai bisogno di più (fino a 100 a seconda del contratto).
* **Propagazione DNS:** Consenti la propagazione globale delle modifiche per 24-48 ore. La convalida può non riuscire semplicemente perché il DNS non è ancora stato propagato.
* **Riutilizzo sottodominio:** Un sottodominio già utilizzato da un altro prodotto Adobe (Marketo Engage, Adobe Campaign) non può essere riutilizzato in [!DNL Marketo Optimizer].

## DMARC, SPF e DKIM {#dmarc-spf-dkim}

DMARC, SPF e DKIM sono standard di autenticazione e-mail. Assieme, dimostrano ai server di posta che il messaggio è stato effettivamente inviato per conto del dominio e non è stato oggetto di spoofing. Gli ISP moderni - Gmail, Yahoo, Microsoft - richiedono questi standard per i mittenti in blocco.

| Record | Sta per | Finalità |
| ------ | ---------- | ------- |
| **SPF** | Framework criteri mittente | Elenca gli IP del server di posta autorizzati a inviare messaggi dal dominio. I server di ricezione rifiutano la posta da indirizzi IP non inclusi nell&#39;elenco. Adobe crea e mantiene automaticamente il record SPF quando deleghi un sottodominio (completamente delegato). |
| **DKIM** | Posta identificata DomainKeys | Una firma crittografica aggiunta a ogni e-mail in uscita. Il server ricevente verifica la firma in base a una chiave pubblica pubblicata nel DNS. Adobe genera automaticamente le chiavi DKIM e i record DNS durante la delega del sottodominio. |
| **DMARC** | Autenticazione, reporting e conformità dei messaggi basati su dominio | Indica ai server riceventi cosa fare in caso di errore di SPF o DKIM e fornisce report sui risultati dell&#39;autenticazione. DMARC dispone di tre modalità di criteri: nessuno, quarantena e rifiuto. |

### Modalità criteri di DMARC {#dmarc-policy-modes}

| Policy | Azione | Quando utilizzare |
| ------ | ------ | ----------- |
| `none` | Monitoraggio | Il server ricevente non esegue alcuna operazione in caso di errore di DMARC, ma invia comunque un report. Utilizza questa opzione quando deleghi un sottodominio per la prima volta a confermare il funzionamento dell’autenticazione senza rischiare la perdita dei messaggi. |
| `quarantine` | Quarantena | Il server ricevente inserisce i messaggi di errore nella cartella di posta indesiderata. |
| `reject` | Rifiuta | Il server ricevente rifiuta i messaggi (non recapitati) che non superano l’autenticazione. Modalità più rigida. Consigliato quando si è sicuri della configurazione dell’autenticazione. |

### Configurare DMARC {#configure-dmarc}

DMARC è configurato al momento della delega del sottodominio, ma puoi anche aggiungere o aggiornare DMARC per un sottodominio già delegato.

1. Nella barra di navigazione a sinistra di [!DNL Marketo Optimizer], espandi **[!UICONTROL Amministrazione]** e seleziona **[!UICONTROL Canali]**.

1. Nel pannello, espandi **[!UICONTROL Impostazioni e-mail]** e seleziona **[!UICONTROL Sottodomini]**.

1. Nell’elenco Sottodomini, individua il sottodominio e controlla la colonna Record di DMARC.

   Se manca un record, viene visualizzato un avviso.

1. Apri il sottodominio e scorri fino alla sezione del record DMARC.

   * Se nel dominio padre esiste già un record DMARC, [!DNL Marketo Optimizer] recupera automaticamente i valori. Puoi tenerli o ignorarli.
   * Se non esiste alcun record, scegli **[!UICONTROL Gestisci con Adobe]** e Adobe crea e ospita il record DMARC.

1. Impostare i criteri: `none`, `quarantine` o `reject`. Iniziare con `none` a meno che non si disponga già di una postura DMARC matura nel dominio padre.

1. (Facoltativo) Configurare altri tag di DMARC (`sp` per il criterio del sottodominio, `pct` per la percentuale, `rua` e `ruf` per gli indirizzi di report).

1. Se si utilizza Completamente delegato, fare clic su **[!UICONTROL Salva]**.

   Adobe applica il record automaticamente. Se utilizzi CNAME, copia il record DNS e chiedi al tuo team DNS di aggiungerlo, quindi confermarlo in [!DNL Marketo Optimizer].

1. Consenti fino a 48 ore per la propagazione DNS, quindi verifica che l’indicatore di stato DMARC nella pagina del sottodominio sia verde/integro.

>[!TIP]
>
>Inizia con `policy=none` per monitorare i rapporti di autenticazione, quindi passa a `quarantine` e infine a `reject` dopo che i rapporti hanno mostrato un allineamento di SPF e DKIM integro. Se si passa direttamente a `reject` senza monitoraggio, i messaggi legittimi potrebbero essere rifiutati.

## Pool IP {#ip-pools}

Un pool IP è un gruppo denominato di indirizzi IP utilizzati per inviare l’e-mail. I pool IP sono fondamentali per la reputazione del mittente: ogni pool ha la propria reputazione rispetto agli ISP, pertanto un problema relativo a un pool (ad esempio, un burst di marketing che attiva reclami di spam) non ne infligge un altro (ad esempio, conferme transazionali).

### Tipi di pool {#pool-types}

| Tipo di pool | Disponibilità | Descrizione |
| --------- | ------------ | ----------- |
| **Pool IP condiviso** | Disponibile in Beta | Un pool di indirizzi IP gestiti da Adobe e condivisi tra molti clienti. La reputazione viene mantenuta da Adobe in tutto il pool. Consigliato per volumi di e-mail da basso a medio e clienti che non desiderano gestire il riscaldamento dell’IP. |
| **Pool IP dedicato** | Roadmap (GA) | Uno o più indirizzi IP allocati esclusivamente alla tua organizzazione. Tu possiedi la reputazione. Consigliato per mittenti con volumi elevati. Include la pianificazione del riscaldamento IP e la gestione dei record PTR. |

### Revisione e assegnazione di un pool IP {#review-ip-pool}

In questa versione, viene eseguito il preprovisioning dei pool IP per la tua organizzazione. Assegna un pool IP durante la creazione di una configurazione del canale e-mail.

1. Nella barra di navigazione a sinistra di [!DNL Marketo Optimizer], espandi **[!UICONTROL Amministrazione]** e seleziona **[!UICONTROL Canali]**.
1. Nel pannello, espandi **[!UICONTROL Impostazioni e-mail]** e seleziona **[!UICONTROL Pool IP]**.
1. Verificare che un pool IP con stato **[!UICONTROL Attivo]** sia disponibile per l&#39;organizzazione.
1. Passa il puntatore del mouse sul pool per visualizzare gli indirizzi IP e i relativi record PTR (DNS inverso).
1. Se la tua organizzazione dispone di più business unit o marchi, pianifica come utilizzare i pool IP (ad esempio, pool di marketing rispetto a pool di webinar) prima di creare configurazioni di canale.

>[!IMPORTANT]
>
>Non combinare il traffico di marketing e quello transazionale sullo stesso pool IP, anche quando il pool condiviso è disponibile. L’impostazione del tipo di e-mail nella configurazione del canale (Marketing anziché Transazionale) governa il comportamento di eliminazione, ma le configurazioni del canale devono comunque utilizzare pool distinti, ove possibile.

<!--

### Frequently asked questions {#faq}

| Question | Answer |
| -------- | ------ |
| **Can I reuse the subdomain I already use in Marketo Engage?** | No. A subdomain can only be associated with one Adobe product at a time. Create a new subdomain (for example, mail2.contoso.com) for [!DNL Marketo Optimizer]. |
| **Why does my channel configuration show Failed?** | The most common reasons are: MX record validation failed (your subdomain DNS isn't fully configured); DMARC misalignment; or an IP pool that is in Processing and has never been associated with the selected subdomain. Open the configuration to see the specific reason. |
| **What happens if a personalization token has no value at send time?** | If you defined a fallback with the Handlebars `default` helper, the fallback is used. If not, the token resolves to an empty string. [!DNL Marketo Optimizer] warns you when a token has no fallback and the underlying attribute is not guaranteed by the audience definition. |
| **Can I personalize using account-level attributes?** | Not in this release. Personalization in [!DNL Marketo Optimizer] today supports profile attributes only. |
| **What's the maximum email size?** | 100 KB is the recommended best-practice cap for inbox rendering. [!DNL Marketo Optimizer] warns you in the editor if you exceed it. |
| **Can I migrate existing Marketo email templates into [!DNL Marketo Optimizer]?** | A guided self-serve migration tool — including Velocity-to-Handlebars conversion — is delivered at GA. In this release, you can manually rebuild templates or paste raw HTML. |
| **Will my updates to Marketo assets show up in [!DNL Marketo Optimizer]?** | No. Asset availability in [!DNL Marketo Optimizer] is based on a one-time copy from Marketo Design Studio. Re-uploaded or modified Marketo assets are not reflected in [!DNL Marketo Optimizer] today. Native asset upload and management within [!DNL Marketo Optimizer] is on the Beta roadmap. |

## Glossary {#glossary}

| Term | Definition |
| ---- | ---------- |
| **DKIM** | DomainKeys Identified Mail — cryptographic email signature. |
| **DMARC** | Domain-based Message Authentication, Reporting & Conformance. |
| **FBL** | Feedback Loop — a service ISPs offer to receive spam-complaint reports back to senders. |
| **Handlebars** | JavaScript templating language used in [!DNL Marketo Optimizer] for personalization expressions. |
| **IP pool** | Group of IP addresses used to send email. |
| **MX record** | Mail Exchange DNS record — directs incoming mail to the correct mail servers. |
| **NS record** | Name Server DNS record — used to delegate a subdomain. |
| **PTR record** | Pointer record — reverse DNS that maps an IP address back to a hostname. |
| **RBAC** | Role-Based Access Control. |
| **SPF** | Sender Policy Framework — DNS record listing authorized sending IPs. |
| **Subdomain delegation** | Granting Adobe authority over a portion of your domain (a subdomain) for sending email. |

-->


