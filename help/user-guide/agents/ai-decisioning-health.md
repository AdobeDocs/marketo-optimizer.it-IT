---
title: Integrità di AI-Decisioning
description: Scopri in che modo i controlli di integrità basati sull’intelligenza artificiale determinano la copertura, la classificazione dell’utente e la ricchezza dei segnali in Marketo Optimizer, e segnalano cosa manca.
source-git-commit: 75b481faf0d66210329f95c8afabdfa59e7bcb79
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 0%

---


# Integrità delle decisioni basate sull’intelligenza artificiale

L&#39;integrità delle decisioni basate su IA controlla i dati che determinano la personalizzazione in [!DNL Adobe Marketo Optimizer]. Riporta la copertura dei lead, la classificazione dei personaggi e la ricchezza delle storie nelle categorie demografiche, firmografiche, tecnologiche e psicografiche. Quindi contrassegna i dati mancanti per identificare da dove iniziare.

Utilizza l&#39;integrità delle decisioni basate sull&#39;intelligenza artificiale per visualizzare i flussi di dati in da [!DNL Marketo Engage] e dove esistono spazi vuoti. Colmare queste lacune migliora il modo in cui [AI decisioning](./ai-decisioning.md) assegna punteggi e indirizza ogni persona.

## Integrità Open AI-decisioning {#open}

Apri il rapporto dalla home page o dalla chat di Collaboratore.

* Nella pagina _Home_, seleziona la scheda **[!UICONTROL Integrità delle decisioni AI]** nella riga Accesso rapido. La scheda guida la fila e mostra il volume della storia e l’avanzamento della classificazione personale, ad esempio 929 storie, 32% persone classificate.
* Nella chat box di Coworker, chiedi informazioni dirette sui tuoi dati di personalizzazione oppure digita `/` e seleziona **[!UICONTROL Integrità delle decisioni basate sull&#39;intelligenza artificiale]**.

![Riga di accesso rapido nella home page, che mostra prima la scheda di integrità di AI-decisioning, seguita da Marketing, Assets e Report.](./assets/ai-decisioning-health-quick-access.png){width="600"}

Entrambi i percorsi aprono il rapporto all’interno dell’area di lavoro di Collaborator.

## Chat delle richieste di benvenuto e follow-up {#chat-welcome}

L&#39;apertura dell&#39;integrità delle decisioni basate sull&#39;intelligenza artificiale dalla chat visualizza un messaggio di benvenuto, _[!UICONTROL *Benvenuti nell&#39;integrità delle decisioni basate sull&#39;intelligenza artificiale]_, un riepilogo dei controlli del report e una scheda per aprire il report completo.

Sotto la scheda, in _[!UICONTROL Come procedere?]_, AI-decisioning health suggerisce prompt di follow-up in base alle lacune specifiche dei tuoi dati. Ad esempio, se il 67,7% dei lead non è classificato come utente tipo, un prompt suggerito recita _Perché il 67,7% dei lead non è classificato per utente tipo?_ Seleziona un prompt suggerito o fai una domanda per ottenere una risposta diretta senza uscire dalla chat.

![Pannello chat del collaboratore che mostra il messaggio di benvenuto per l&#39;integrità delle decisioni basate sull&#39;intelligenza artificiale, una scheda che apre il report e quattro prompt di follow-up consigliati.](./assets/ai-decisioning-health-highlights.png){width="800" zoomable="yes"}

## Panoramica dei rapporti {#report-overview}

Il report dell&#39;area di lavoro si apre con un callout **[!UICONTROL Elementi di rilievo]** che elenca le aree più forti e deboli dei dati in un linguaggio semplice, ad esempio _I dati demografici raggiungono il 100% dei lead con una profondità di campo elevata_ oppure _67,7% dei lead non viene classificato in alcun tipo_. Un segno di spunta indica un risultato valido e un cerchio con una barra indica un vuoto.

Accanto agli elementi di rilievo, un grafico radar traccia la **[!UICONTROL copertura]** complessiva in sei dimensioni: demografica, firmografica, tecnografica, psicografica, persona e intento. Un&#39;area ombreggiata più ampia garantisce una copertura più ampia.

## Classificazione personale {#persona-classification}

La sezione **[!UICONTROL Classificazione Persona]** mostra quante delle tue storie sono classificate in una persona, ad esempio: _300 di 929 storie classificate · 32,3% classificate · 67,7% non classificate_. Una barra impilata interrompe le storie classificate per persona, con una legenda che mostra il conteggio e la percentuale delle storie per ogni persona.

Seleziona un segmento della persona per aprire una scheda di dettagli con titoli di lavoro di esempio per tale persona. Ad esempio, il segmento **[!UICONTROL Altro]** potrebbe mostrare: _272 storie/29,3%_, con esempi come specialista di settore, consulente indipendente, consulente freelance ed esperto in materia.

## Copertura {#coverage}

Nella sezione **[!UICONTROL Copertura]** sono elencate cinque categorie di dati: demografico, firmografico, tecnografico, psicografico, intento e attività. Ogni categoria mostra la percentuale di storie con almeno un attributo disponibile nella categoria.

Seleziona una categoria per espanderla, quindi scegli una delle due schede seguenti:

* **[!UICONTROL Attributi]** - Attributi raggruppati per tipo, ad esempio Dati personali o Posizione sotto demografico. Ogni attributo mostra quanti brani hanno un valore, ad esempio: `firstName (906 stories)`.
* **[!UICONTROL Flag]** - Intervalli specifici per la categoria o _Nessun flag aperto in questa categoria_ quando la copertura è integra.

Utilizzare il campo di ricerca sopra l&#39;elenco delle categorie per passare direttamente a una categoria o a un attributo in base al nome.

![Sezione di copertura con la categoria Demografica espansa, con gruppi di attributi quali Dettagli personali, Punteggio di coinvolgimento e Posizione.](./assets/ai-decisioning-health-coverage.png){width="800" zoomable="yes"}

## Contrassegni {#flags}

La sezione **[!UICONTROL Contrassegni]** nella parte inferiore del report elenca ogni lacuna riscontrata in tutte le categorie, ordinata in base alla gravità:

* **[!UICONTROL Critico]** - Le lacune che bloccano completamente una funzionalità, ad esempio _La copertura tecnografica è pari allo 0% per tutti i lead_.
* **[!UICONTROL Guarda]** - Le lacune che riducono l&#39;efficacia ma non bloccano una funzionalità, ad esempio _La copertura psicografica raggiunge solo il 7,2% dei lead_.

Filtra l&#39;elenco in base alla gravità, quindi seleziona un flag per espanderlo e leggerne una spiegazione dell&#39;impatto aziendale in una sola frase, ad esempio: _I lead non classificati non possono entrare in percorsi specifici dell&#39;utente o ricevere messaggi personalizzati in base al ruolo, riducendo la rilevanza della campagna e i tassi di conversione._

![La sezione dei flag è filtrata in base alla gravità dell&#39;osservazione e mostra tre flag, uno espanso per rivelarne la spiegazione dell&#39;impatto aziendale.](./assets/ai-decisioning-health-flags.png){width="800" zoomable="yes"}

## Accesso recente {#recently-accessed}

Se apri l&#39;integrità di AI-decisioning e poi esci, questo viene nuovamente visualizzato in **[!UICONTROL Accesso recente]** nell&#39;area di lavoro vuota, in modo da poter tornare al report senza tornare alla home page.

![Elenco degli ultimi accessi che mostra l&#39;integrità delle decisioni basate sull&#39;intelligenza artificiale come elemento più recente, prima di Scoring Studio.](./assets/ai-decisioning-health-recently-accessed.png){width="500"}

>[!BEGINSHADEBOX]

I miglioramenti pianificati per l’integrità delle decisioni basate sull’intelligenza artificiale includono:

* Voce dedicata nel catalogo delle competenze dei collaboratori.
* Azioni guidate di tipo &quot;chiedi come&quot; che ti guidano attraverso la correzione di un flag.
* Una scheda Passaggi successivi dedicata.

>[!ENDSHADEBOX]
