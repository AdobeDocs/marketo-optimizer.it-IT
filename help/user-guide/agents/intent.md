---
title: Configurare e analizzare le finalità
description: Scopri come configurare i pesi delle attività per il modello di punteggio intento e analizzare l’intento a livello di lead con rapporti di classificazione, profilo, tendenza e confronto.
TQID: 'https://experienceleague.adobe.com/BNzbM6v6ADSKyPR6jQMj1QdWMnLQQX-j3PNk8gF6PxY'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2:
  - id: 46e599c6-e20f-5f67-9824-93415016f66b
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
topic_v2:
  - id: f8667931-f646-4dd3-af2a-b9d0cb8098ad
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 978
ht-degree: 0%

---


# Configurare e analizzare le finalità

In [!DNL Adobe Marketo Optimizer], Collaboratore fornisce due abilità nella categoria _Intento_. Ogni cliente valuta le attività di marketing in modo diverso, in modo che queste abilità ti consentano di configurare ciò che conta per la tua azienda. Puoi quindi convalidare ciò che ha prodotto la pipeline intento.

| Competenza | Comando | Funzionamento |
| --- | --- | --- |
| **Configurazione intento** | `/intent-configuration` (alias `/intent-config`) | Configurare i pesi delle attività per il modello di punteggio intento della persona |
| **Analizza intento** | `/analyze-intent` | Eseguire query e convalidare report di classificazione intento a livello di lead, tendenze, tassonomia di prodotti e parole chiave e di confronto |

Selezionando un’abilità, la sua descrizione viene inserita come prompt iniziale nell’input della chat, che puoi modificare prima dell’invio.

## Configurare il modello di ponderazione {#configure-model}

Per configurare i pesi delle attività per il modello di punteggio intento, segui questi passaggi generali. Per ulteriori informazioni sulla configurazione e sulla ponderazione dei punteggi, vedere [_Configurazione intento_](../audiences/intent-configuration.md).

1. Richiama l&#39;abilità (`/intent-configuration`) e premi **Invio**.

   Collaboratore apre il pannello **[!UICONTROL Configurazione intento]** come scheda area di lavoro. Il pannello elenca tutte le attività di intento della pipeline, mostrando un punteggio **[!UICONTROL AI suggerito]** e un punteggio **[!UICONTROL ponderazione]** modificabile per ciascuno di essi. Inoltre, elenca i modelli già esistenti per il tenant. Solo un modello può essere _[!UICONTROL Attivo]_ alla volta: quello che attualmente determina il punteggio.

1. Per apportare modifiche, apri un modello _[!UICONTROL Bozza]_ esistente oppure seleziona **[!UICONTROL Duplica]** nel modello _[!UICONTROL Attivo]_ per iniziare dai pesi correnti.

1. Regolare i pesi riga per riga.

   Ad esempio, contrassegna un&#39;attività di valore ridotto come **[!UICONTROL Aggiungi all&#39;opportunità]** come **[!UICONTROL banale]** e aumenta il numero di **[!UICONTROL Invia e-mail con clic]** o di **[!UICONTROL Fai clic sul collegamento]** a **[!UICONTROL Importante]** se tali attività sono più importanti per la tua attività.

1. Seleziona **[!UICONTROL Salva]**.

   Quando salvate, viene richiesto di attivare il modello ora. La conferma sostituisce il modello _[!UICONTROL Attivo]_ corrente, che viene abbassato di livello automaticamente.

## Punteggio intento

Il punteggio intento per un lead considera tre elementi:

* **Il peso configurato qui** per ogni tipo di attività.
* **Rilevanza dei contenuti**: parole chiave estratte dalle risorse associate a ogni attività.
* **Frequenza**: quante volte il lead ha interagito con tale contenuto.

Per informazioni dettagliate su queste metriche, tra cui il peso suggerito da IA, la rilevanza dei contenuti e le limitazioni, vedere [Configurazione intento](../audiences/intent-configuration.md).

## Rapporti intento

Per introdurre i quattro tipi di report che può generare, richiamare `/analyze-intent` per richiedere a Collaboratore. Il collaboratore attende quindi una richiesta di follow-up per denominare un lead, un prodotto o un confronto. Ogni report viene aperto come scheda propria nel pannello dell&#39;area di lavoro e in Collaboratore viene aggiunta anche una scheda di riepilogo nella chat con un pulsante _[!UICONTROL Apri report]_.

### Rapporto Classificazione intento

**Prompt consigliato:** _&quot;Mostra i lead più intensi per &lt;product>&quot;_

Classifica i lead per intensità del segnale di intento per un prodotto o una parola chiave. Le colonne includono Lead, E-mail, Account, Settore, Prodotti, Punteggio, Livello intento e origine attività principale. La colonna delta _di_ 7 giorni mostra come il punteggio intento è stato spostato nell&#39;ultima settimana. La colonna _[!UICONTROL Ultimo aggiornamento]_ mostra quando il lead ha interagito per l&#39;ultima volta, ovvero quando è stato modificato il punteggio. I filtri per il livello di prodotto e intento sono elenchi a discesa live, quindi non sei limitato a ciò che hai digitato nel prompt. Le colonne sono ordinabili.

Altri prompt che aprono lo stesso report:

* &quot;Classifica i primi 10 lead per punteggio intento per Photoshop&quot;
* &quot;Elenca lead con intento elevato per Photoshop&quot;
* &quot;Mostrami i lead con il punteggio intento più alto per Photoshop questa settimana&quot;
* &quot;I leader del settore Retail dimostrano l&#39;interesse di Creative Cloud per il segmento medio-alto&quot;
* &quot;Trovare lead con punteggi intento conferiti dai download di risorse in un webinar&quot;
* &quot;Elencare i lead ad alte intenzioni la cui origine attività principale è il clic e-mail&quot;
* &quot;Mostra i lead con intento contribuito solo dalle visite web, esclusi download o webinar&quot;

### Rapporto Profilo intento

**Prompt consigliato:** _&quot;Visualizza il profilo intento di &lt;lead>&quot;_

Un’istantanea rapida di un lead: quali prodotti e parole chiave mostrano interesse e il punteggio per ciascuno. Utilizzare questo rapporto una volta che un rapporto di classificazione è emerso come un lead degno di essere esaminato. Consente di modellare percorsi, utenti tipo e gruppi di acquisto in base all’effettivo intento di prodotto del lead.

Altre richieste:

* &quot;A quali prodotti &lt;lead> è più interessato?&quot;
* &quot;A cosa è interessato &lt;lead> in questo momento?&quot;
* &quot;Fornisci un riepilogo di tutti i prodotti e delle parole chiave per cui il lead X ha mostrato l’intento&quot;

### Rapporto Tendenza intento

**Suggerimento:** _&quot;Mostra cronologia punteggio intento &lt;lead> per &lt;product> negli ultimi 30 giorni&quot;_

Traccia il punteggio intento di un lead per un prodotto nel tempo. Utilizzatela per identificare i punti di flesso. Ad esempio, un punteggio che rimane costante per settimane e poi cala bruscamente segnala un cambiamento di interesse, non dati irrilevanti. È possibile regolare l’intervallo temporale a 7, 30 o 100 giorni.

Altre richieste:

* &quot;Qual è l’impennata dell’intento per Acrobat questa settimana per il lead X?&quot;
* &quot;Mostrami la tendenza di intento per un lead questo mese&quot;
* &quot;L’intento del lead X per Acrobat è salito o sceso questo mese?&quot;

### Rapporto Intent Comparison

**Prompt consigliato:** _&quot;Confronto delle tendenze di intento per Photoshop e Illustrator in tutti i lead negli ultimi 30 giorni&quot;_

Confronta l’intento nel tempo per due lead o due prodotti, come grafico affiancato a una tabella di riepilogo (punteggio corrente, punteggio N giorni fa, delta). L’intervallo di tempo è regolabile allo stesso modo del rapporto sulle tendenze. L&#39;intenzione può essere cambiata ogni giorno, minuto per minuto o ogni ora, quindi una breve finestra piatta non significa necessariamente che non stia accadendo nulla.

Altre richieste:

* &quot;Confronta le finalità di Acrobat e Photoshop nell’ultimo trimestre&quot;
* &quot;Confrontare l&#39;intento del lead X e del lead Y per Creative Cloud&quot;
* &quot;Quale ha un intento medio più elevato: Photoshop o Illustrator?&quot;
* &quot;Confronta utenti tipo per Acrobat: chi ha il tasso di vincita più alto?&quot;
* &quot;Mostrare l’intento a vicenda per Photoshop nei segmenti Retail e Finanza&quot;

## Follow-up del rapporto {#report-follow-up}

I report intento sono di sola lettura e non dispongono di opzioni di esportazione autonome. Per agire in base a ciò che viene visualizzato in un rapporto, utilizza altre abilità.

* Prompt con _&quot;Elenca i lead di intenti principali per Creative Cloud.&quot;_ Collaboratore utilizza l&#39;abilità `/analyze-intent` per produrre l&#39;elenco specificato.

* Richiedi con _&quot;Crea un elenco di persone utilizzando questo elenco.&quot;_ Collaboratore consegna il set di lead all&#39;[abilità di creazione del pubblico](./audience-creation.md), che crea direttamente l&#39;elenco di persone. Non è necessario alcun passaggio di esportazione o importazione manuale.
