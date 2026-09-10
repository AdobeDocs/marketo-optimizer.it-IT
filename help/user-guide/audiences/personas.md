---
title: Utenti tipo derivati
description: Utilizza utenti tipo derivati in Marketo Optimizer per eseguire il targeting di elenchi di persone e percorsi di percorso. Scopri le mappature persona predefinite e il filtro Persona derivata.
TQID: 'https://experienceleague.adobe.com/5HAnnC6dbU-sE9dzBWs479z1H4LlNSkhhoNSrQxSfqI'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2:
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
  - id: a29661b8-f7a4-53d1-a9ac-fdec08c092e4
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 625
ht-degree: 0%

---

# Utenti tipo derivati

La classificazione Persona trasforma i dati grezzi dei clienti in acquirenti semantici, comprendendo che l’intelligenza artificiale può utilizzare per generare contesto e favorire decisioni personalizzate su ogni canale e percorso. Questo profilo unificato consente di:

* _Diramazione di Percorso_ - Dividi percorsi route lead per persona, profondità di coinvolgimento e ruolo
* _Arbitrato Percorso_ - Determina il percorso di sviluppo a cui appartiene un lead in questo momento, evitando conflitti di messaggi tra programmi concorrenti
* _Personalizzazione dei contenuti_ - Contenuti con narrazioni specifiche per il ruolo (&quot;per un dirigente&quot; o &quot;per un professionista&quot;)
* _Contesto Sales Qualifier_ - I rappresentanti dello sviluppo aziendale (BDR) ricevono un riepilogo a schermo singolo che mostra l&#39;identità dell&#39;individuo, i suoi interessi e la sua fase attuale nel percorso di acquirenti

## Utenti tipo predefiniti {#default-ersonas}

Per la versione Beta di Marketo Optimizer, i seguenti utenti tipo predefiniti sono definiti in base all’attributo titolo del processo:

| Utente tipo | Qualifiche |
| ------- | ---------- |
| [!UICONTROL CXO / EVP] | CEO, CIO, CTO, CMO, CFO, Executive Vice President of Strategy |
| [!UICONTROL SVP / VP] | SVP marketing, VP vendite, SVP operazioni, VP prodotto, VP IT |
| [!UICONTROL Responsabile / Manager senior] | Senior Marketing Manager, IT Manager, Operations Manager, Sales Manager, HR Manager |
| [!UICONTROL Collaboratore individuale] | Responsabile dell’account, ingegnere software, specialista di marketing, rappresentante del successo dei clienti |
| [!UICONTROL Analista] | Analista aziendale, analista dati, analista ricerche di mercato, analista finanziario, analista operazioni |
| [!UICONTROL Sviluppatore] | Sviluppatore front-end, sviluppatore back-end, sviluppatore full-stack, sviluppatore app mobile, ingegnere DevOps |
| [!UICONTROL Personale professionale] | Specialista delle risorse umane, Consulente legale, Responsabile per la conformità, Project Manager, Specialista di approvvigionamento |
| [!UICONTROL Consulente] | Consulente di gestione, consulente IT, consulente di processo aziendale, consulente di marketing |
| [!UICONTROL Altro] | Specialista di settore, consulente indipendente, consulente freelance, esperto in materia |

>[!NOTE]
>
>Nella prossima versione di Disponibilità generale, puoi modificare uno qualsiasi di questi utenti tipo predefiniti in base alle esigenze della tua organizzazione. Supporterà anche le definizioni e la mappatura personalizzate dei tipi di pubblico.

## Filtra per persona derivata {#derived-persona-filter}

[!DNL Marketo Optimizer] deriva un utente tipo per ogni record persona valutando gli attributi del record rispetto agli utenti tipo definiti. È possibile utilizzare il risultato dedotto, ovvero _Persona derivata_, come filtro durante la definizione del pubblico per un elenco di persone o per la segmentazione in un percorso di persone.

Il filtro _[!UICONTROL Persona derivata]_ viene visualizzato nel pannello dei filtri nella categoria **[!UICONTROL Attributi persona]**.

### Elenchi di persone {#people-lists}

Quando gestisci i membri in un [elenco di persone statiche](./people-lists.md#static-lists) o definisci le regole per un [elenco di persone dinamiche](./people-lists.md#dynamic-lists), puoi filtrare per _Persona derivata_ per eseguire il targeting di tutte le persone i cui attributi corrispondono a un utente tipo specifico configurato.

![Filtro utente tipo derivato per un elenco di persone](./assets/derived-persona-filter-people-list.png){width="750" zoomable="yes"}

**Elenco statico — Aggiungi membri**

1. Apri l&#39;elenco statico e fai clic su **[!UICONTROL Aggiungi persone]** in alto a destra.

1. Nella finestra di dialogo del filtro, espandi **[!UICONTROL Attributi persone]** e trascina **[!UICONTROL Persona derivata]** nell&#39;area di lavoro.

1. Nella condizione del filtro, scegli **[!UICONTROL is]** e seleziona uno o più utenti tipo dall&#39;elenco.

1. Fai clic su **[!UICONTROL Fine]** per applicare il filtro e qualificare le persone corrispondenti nell&#39;elenco.

**Elenco dinamico - Imposta regole di appartenenza**

1. Apri l&#39;elenco dinamico e seleziona la scheda **[!UICONTROL Regole]**.

1. Fai clic su **[!UICONTROL Modifica regole]**.

1. Nella finestra di dialogo del filtro, espandi **[!UICONTROL Attributi persone]** e trascina **[!UICONTROL Persona derivata]** nell&#39;area di lavoro.

1. Nella condizione del filtro, scegli **[!UICONTROL is]** e seleziona uno o più utenti tipo dall&#39;elenco.

1. Fai clic su **[!UICONTROL Fine]** per salvare la regola.

   L’iscrizione viene aggiornata automaticamente quando i record delle persone vengono valutati in base alla regola.

### Percorsi di persone {#person-journeys}

Quando configuri la segmentazione per un percorso di persone in un nodo [_Percorsi suddivisi_](../marketing/split-merge-paths-nodes.md), puoi utilizzare un utente tipo derivato come filtro del profilo persona per controllare quali persone entrano nel percorso del percorso.

![Filtro utente tipo derivato per una condizione di percorso diviso](./assets/derived-persona-filter-split-path.png){width="750" zoomable="yes"}

1. Fare clic sul nodo **[!UICONTROL Percorsi suddivisi]** nell&#39;area di lavoro del percorso.

1. Nel pannello delle proprietà del nodo a destra, fai clic su **[!UICONTROL Applica condizione]** o **[!UICONTROL Modifica condizione]** per un percorso.

1. Nella finestra di dialogo del filtro, espandi **[!UICONTROL Attributi persone]** e trascina **[!UICONTROL Persona derivata]** nell&#39;area di lavoro.

1. Nella condizione del filtro, scegli **[!UICONTROL is]** e seleziona uno o più utenti tipo dall&#39;elenco.

1. Fai clic su **[!UICONTROL Fine]** per salvare il filtro per il percorso.

