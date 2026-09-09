---
title: Creare modelli di punteggio personalizzati
description: Crea, visualizza in anteprima e pubblica modelli personalizzati di punteggio del lead in Marketo Optimizer utilizzando l’abilità Studio di punteggio nell’interfaccia della chat di Collaborator.
TQID: 'https://experienceleague.adobe.com/OAY0CzFPTyUi7NCPbRnxGkG6nnndPygbwGlbv9u2oeA'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2:
  - id: 1650dadf-b034-5ac9-a309-77ad1e2f5035
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 468
ht-degree: 1%

---

# Crea modelli di punteggio personalizzati

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_scoring_studio"
>title="Scoring Studio"
>abstract="Utilizza l’abilità di Scoring Studio per creare, configurare e pubblicare modelli personalizzati di punteggio del lead tramite l’interfaccia di chat di Collaborator."

L&#39;abilità [_Scoring Studio_](./skills.md#scoring-signals) in [!DNL Adobe Marketo Optimizer] fornisce una soluzione di valutazione dei lead nativa per l&#39;intelligenza artificiale che consente di creare, configurare e pubblicare modelli di valutazione dei lead. Lo studio combina un flusso di lavoro basato su agenti con un&#39;interfaccia utente visiva: è possibile creare modelli di punteggio tramite prompt del linguaggio naturale nell&#39;[interfaccia chat di Coworker](./chat-interface.md) o interagendo direttamente con i controlli dell&#39;interfaccia utente.

* **Abilità** - `scoring-studio`
* **Chiamata** - Utilizzare un comando barra per aprire Scoring Studio. Ad esempio: _&quot;open Scoring Studio.&quot;_
* **Legge/scrive in** - [!DNL Marketo Optimizer] servizio di punteggio; legge [!DNL Marketo Engage] campi lead e tipi di attività

Al momento del lancio, Collaboratore recupera automaticamente il contesto rilevante, inclusi i tipi di attività, i campi del lead, gli elenchi di persone e gli elenchi di punteggi esistenti, per motivare i suggerimenti nei dati.

![Studio punteggio avviato nell&#39;interfaccia chat di Coworker](./assets/scoring-studio.png){width="700" zoomable="yes"}

## Creare un modello di punteggio {#create-model}

Quando apri Scoring Studio, Collaboratore propone un modello di punteggio di esempio pertinente precompilato con un elenco statico e un set di attività con punteggio. Potete accettare questo punto iniziale suggerito o fornire un prompt personalizzato per definire un modello personalizzato.

### Anteprima del modello {#preview-model}

Dopo aver visualizzato un prompt, viene generata un&#39;anteprima del modello prima di apportare qualsiasi modifica. Le superfici di anteprima:

* Dimensioni punteggio in uso
* Attributi e attività con punteggio
* Elenchi statici o elenchi avanzati applicati come segmenti
* Riepilogo dell&#39;obiettivo del modello, del segmento di destinazione e dei segnali primari

Puoi rivedere l’anteprima e scegliere di creare il modello basato su di essa, oppure continuare a perfezionare attraverso la chat prima di finalizzare.

### Struttura del modello {#model-structure}

Il modello creato è organizzato in _dimensioni_ e _segnali_. Puoi configurare ogni segnale utilizzando il pannello delle proprietà nell’interfaccia utente:

* **Tipo di segnale**: basato su attività o su attributi
* **Attività o attributo**: l&#39;elemento specifico da valutare
* **Parametri segnale** — Impostazioni regolabili per il segnale

Puoi creare e configurare modelli interamente tramite Coworker utilizzando il linguaggio naturale, oppure interagire direttamente con i controlli dell’interfaccia utente.

## Pubblicare un modello di punteggio {#publish-model}

Quando il modello è finalizzato, indica a Collaboratore di pubblicarlo. Il processo di pubblicazione gestisce automaticamente quanto segue:

| Passaggio | Cosa succede |
|---|---|
| **Compilazione regola** | Tutte le regole di punteggio vengono compilate e convalidate |
| **Creazione attività punteggio** | Viene creata e configurata un’attività punteggio pianificata da eseguire ogni giorno |

Dopo la pubblicazione, puoi anche attivare un’esecuzione manuale per elaborare immediatamente i punteggi.

## Visualizzare i risultati del punteggio {#view-results}

Al termine dell&#39;esecuzione di un punteggio, i punteggi vengono scritti nuovamente in [!DNL Marketo Engage] tramite il processo di importazione del lead. Al termine dell&#39;importazione, i punteggi aggiornati possono essere verificati direttamente in [!DNL Marketo Engage].

Dopo ogni esecuzione, puoi visualizzare un riepilogo dei risultati che mostra:

* Quante persone hanno ottenuto un punteggio
* Le singole modifiche di punteggio per persona

È disponibile un registro di controllo per la revisione di ulteriori dettagli di esecuzione.
