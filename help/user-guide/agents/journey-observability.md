---
title: Monitorare e debug l'avanzamento del Percorso
description: Scopri come utilizzare l’abilità di osservabilità del Percorso nella chat di Coworker per eseguire il debug e monitorare il modo in cui le persone e i lead passano attraverso i percorsi, le decisioni sui percorsi suddivisi e la tempistica.
TQID: 'https://experienceleague.adobe.com/Pnd1fVWUZ-g27UDE-y6Pc2Qwjsx-1pDSCaTGxjrBTRc'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2: id: 1650dadf-b034-5ac9-a309-77ad1e2f5035id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 634
ht-degree: 0%

---

# Monitorare ed eseguire il debug della progressione del percorso

L&#39;abilità [_Osservabilità Percorsi_](./skills.md#journeys) in [!DNL Adobe Marketo Optimizer] risponde a domande in linguaggio naturale sul modo in cui le persone e i lead si spostano nei percorsi. Utilizzalo nell&#39;interfaccia chat di [Collaborator](./chat-interface.md) per tracciare la progressione, comprendere le decisioni sui percorsi suddivisi, analizzare le persone all&#39;interno dei nodi di percorso e controllare le metriche di temporizzazione. Puoi anche chiedere informazioni sui pattern di comportamento tra percorsi.

* **Abilità** - `journey-observability`
* **Richiamo** - Poni una domanda in linguaggio naturale oppure utilizza un comando barra per eseguire l&#39;abilità Osservabilità Percorso. Ad esempio: _&quot;Come è avvenuto lo spostamento di demo_ lead_24@company.com attraverso LeadNurtureJourney?&quot;_
* **Legge da** - [!DNL Marketo Optimizer] dati di percorso; legge [!DNL Marketo Engage] elenchi statici per controllare l&#39;appartenenza all&#39;elenco

## Visualizza dettagli persona o lead {#person-details}

Chiedi dettagli di base e di sola lettura su una persona o un lead per stabilire il contesto prima di indagare sul loro percorso. Specifica l’indirizzo e-mail, l’ID lead o il nome del lead della persona.

* _&quot;Informazioni di base sul lead demo_ lead_24@company.com.&quot;_
* _&quot;Qual è il titolo del processo e il paese per il profilo john.doe@company.com?&quot;_
* _&quot;Visualizza l&#39;e-mail e il ruolo per lead_ 01.&quot;_

## Tracciare la progressione in un percorso {#journey-progression}

Chiedi in che modo una persona o un lead si è spostato all’interno di un percorso per visualizzare l’entrata a livello di nodo, l’uscita, la durata e il percorso seguito. Specifica l’indirizzo e-mail o l’ID del lead della persona e il nome del percorso.

* _&quot;Come è avvenuto lo spostamento di demo_ lead_24@company.com attraverso LeadNurtureJourney?&quot;_
* _&quot;Quali nodi sono stati passati da john.doe@company.com nel percorso Demo prodotto?&quot;_

## Comprendere le decisioni relative ai percorsi suddivisi {#split-path-analysis}

Chiedi perché una persona o un lead ha preso o non ha preso un percorso specifico in un nodo diviso. Osservabilità percorso spiega la decisione utilizzando i valori di attributo valutati in quel momento. Specifica l’indirizzo e-mail o l’ID del lead della persona, il nome del percorso e l’ID del nodo diviso.

* _&quot;Perché demo_ lead_24@company.com è passato al percorso &#39;Altamente coinvolto&#39; nel nodo diviso c764a9?&quot;_
* _&quot;Perché john.doe@company.com non ha scelto il percorso qualificato nel nodo ab123f in LeadNurtureJourney?&quot;_
* _&quot;Confrontare il motivo per cui lead_ 01 e lead_02 hanno preso percorsi diversi nel nodo diviso x99f3b.&quot;_

## Analizzare le persone nei nodi del percorso {#node-analysis}

Richiedere i conteggi e i dettagli relativi a persone o lead all&#39;interno di un nodo di percorso o di un percorso suddiviso. Filtra i risultati per persona, ruolo, posizione o livello di coinvolgimento. Immetti l’ID del nodo.

* _&quot;Assegnami tutte le persone attualmente nel percorso &#39;Coinvolgimento elevato&#39; del nodo node-459c7c.&quot;_
* _&quot;Quanti lead si trovano nel nodo di qualifica del percorso Demo Nurture?&quot;_
* _&quot;Mostra lead nel percorso di divisione &#39;Basso intento&#39; filtrato per ruolo: Marketing Manager.&quot;_

## Identificazione di pattern tra percorsi {#pattern-recognition}

Chiedi all’osservabilità del Percorso di identificare percorsi comuni, punti di riconsegna e comportamenti ripetuti in un percorso. Specifica il nome del percorso e, facoltativamente, un intervallo temporale, un utente, un prodotto o un account per limitare i risultati.

* _&quot;Quali sono i percorsi più comuni seguiti dai DSP nel percorso di dimostrazione del prodotto?&quot;_
* _&quot;Dove vengono solitamente rilasciati i lead in LeadNurtureJourney?&quot;_
* _&quot;Si verificano ritardi insoliti o percorsi imprevisti nel percorso di sviluppo Q1?&quot;_

## Controllare i tempi e le metriche operative {#operational-metrics}

Domande su tempi di ingresso, durate di attesa, latenza di transizione e progressione bloccata per un percorso. Specifica il nome del percorso e, facoltativamente, un ID nodo o un identificatore persona.

* _&quot;Quando john.doe@company.com è entrato nel percorso di follow-up demo?&quot;_
* _&quot;Quanto tempo normalmente attendono i lead sul nodo di qualifica in LeadNurtureJourney?&quot;_
* _&quot;Quali lead sono stati bloccati nel percorso di follow-up della demo per più di sette giorni?&quot;_

## Limitazioni {#limitations}

| Limitazione | Dettaglio |
|---|---|
| Modifica degli attributi di persona o lead | Non supportato. Aggiorna i record persona e lead direttamente in [!DNL Marketo Engage] o [!DNL Marketo Optimizer]. |
| Creazione, modifica, sospensione o ripresa di percorsi | Non supportato. Utilizza l&#39;[area di lavoro percorsi](../marketing/person-journeys.md) o un&#39;abilità di modifica percorsi in [Abilità collaboratori](./skills.md#journeys). |
| Modifica della logica di divisione o della configurazione del percorso | Non supportato. Modifica i percorsi suddivisi direttamente nell&#39;area di lavoro [percorso](../marketing/split-merge-paths-nodes.md). |
| Composizione del gruppo di acquisto o aggregazioni a livello di account | Fuori ambito. Rapporti percorsi di osservabilità a livello di persona e di lead. |
| Modifica delle pianificazioni o dei tempi di percorso | Non supportato. |
