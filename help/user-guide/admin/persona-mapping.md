---
title: Mappatura personale
description: Scopri come impostare la mappatura persona in Marketo Optimizer. Mappa gli attributi della persona per definire gli utenti tipo e utilizza il filtro Persona derivata negli elenchi di persone e nei percorsi di persone.
TQID: 'https://experienceleague.adobe.com/JCBtJN4DgQZROVDamM4eKuCiGTwJQPQY3wMxmBPFj74'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2: id: 46e599c6-e20f-5f67-9824-93415016f66bid: 64b90904-e4f0-5c1b-a871-8c6a40b204a1id: a659ad61-de21-559d-a901-02e2fb329ff5id: d4203578-d294-5145-b397-f26f4488a904
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 1216
ht-degree: 1%

---

# Mappatura utente tipo

<!-- not available until GA -->

Gli utenti tipo sono un aspetto chiave in un approccio di marketing basato sull’account (ABM) perché aiutano gli esperti di marketing ad adeguare le loro strategie alle esigenze, alle preferenze e ai punti critici specifici degli utenti all’interno degli account target. Gli addetti al marketing possono creare profili dettagliati per ogni persona, indicandone background, responsabilità, punti critici e canali di comunicazione preferiti. Con queste definizioni, gli amministratori possono configurare gli utenti tipo in base agli attributi delle persone in Marketo Optimizer, in modo che gli elenchi di persone e i percorsi di persone possano utilizzare un filtro semplice e coerente per acquisire tali utenti tipo.

In Marketo Optimizer, la mappatura persona offre una funzionalità aggiuntiva oltre le condizioni del modello di ruolo: è possibile filtrare [elenchi di persone](../audiences/people-lists.md) e [percorsi di persone](../marketing/person-journeys.md) utilizzando **[!UICONTROL Persona derivata]** come criterio di filtro. Un utente tipo _derivato_ è l&#39;utente tipo dedotto dal sistema per un record persona valutandone gli attributi rispetto a tutte le definizioni utente tipo configurate.

Limitazioni di definizione e utilizzo dell’utente:

* Nell&#39;elenco _[!UICONTROL Mapping persona]_ è possibile definire fino a 20 utenti tipo.
* Ogni utente tipo può includere fino a cinque attributi nella propria definizione.
* In tutti gli utenti tipo definiti, puoi utilizzare fino a dieci attributi persona diversi.

>[!BEGINSHADEBOX]

**Caso d&#39;uso: varianti titolo processo**

Molti team di marketing e vendite utilizzano le qualifiche professionali per identificare utenti tipo diversi all’interno di un account. Tuttavia, i titoli dei contatti possono essere incoerenti e utilizzare numerose varianti per ruoli simili. Quando si creano filtri per l’elenco delle persone o condizioni di pubblico per il percorso di persone, può essere necessario definire ogni possibile posizione correlata per un determinato ruolo. Puoi semplificare queste definizioni e portare persone con titoli di lavoro simili sotto un utente tipo dedotto, che puoi quindi indirizzare filtrando _Persona derivata è Gestione prodotto_ invece di corrispondere ai valori dei singoli titoli di lavoro.

>[!ENDSHADEBOX]

## Accedere agli utenti tipo configurati {#access}

1. Nel menu di navigazione a sinistra, scegli **[!UICONTROL Amministrazione]** > **[!UICONTROL Configurazioni]**.

1. Fai clic su **[!UICONTROL Mappatura persona]** nel pannello intermedio per visualizzare l&#39;elenco degli utenti tipo.

   ![Accedi agli utenti tipo configurati](assets/configuration-persona-mapping.png){width="800" zoomable="yes"}

   Da questa pagina è possibile [creare](#create-a-persona), [modificare](#edit-a-persona) o [eliminare](#delete-a-persona) utenti tipo.

   L&#39;elenco di mappatura Persona è organizzato in una tabella e visualizza in alto gli utenti tipo aggiornati più di recente (ordinati per _[!UICONTROL Ultimo aggiornamento]_). Puoi personalizzare la tabella visualizzata facendo clic sull&#39;icona _Impostazioni colonna_ ( ![Impostazioni colonna](../assets/do-not-localize/icon-column-settings.svg) ) nell&#39;angolo in alto a destra e selezionando o deselezionando le caselle di controllo della colonna.

   ![Colonne da visualizzare nell&#39;elenco di mappatura utenti tipo](assets/configuration-persona-mapping-list-columns.png){width="300"}

1. Per accedere ai dettagli di un utente tipo, fai clic sul nome.

### Utenti tipo predefiniti

L&#39;elenco _Mapping persona_ include cinque utenti tipo predefiniti definiti in base all&#39;attributo del titolo del processo. Puoi modificare uno di questi utenti tipo predefiniti in base alle esigenze della tua organizzazione:

| Utente tipo | Qualifiche |
| ------- | ---------- |
| CXO / EVP - CXO / vicepresidente esecutivo | CEO, CIO, CTO, CMO, CFO, Executive Vice President of Strategy |
| SVP / VP - Vicepresidente senior / Vicepresidente | SVP marketing, VP vendite, SVP operazioni, VP prodotto, VP IT |
| Direttore principale / Direttore - Direttore principale / Direttore | Direttore tecnico, Direttore senior del prodotto, Direttore delle finanze, Direttore del Customer Success |
| Senior Manager/Manager - Senior Manager/Manager | Senior Marketing Manager, IT Manager, Operations Manager, Sales Manager, HR Manager |
| Collaboratore individuale - Collaboratore individuale | Responsabile dell’account, ingegnere software, specialista di marketing, rappresentante del successo dei clienti |
| Analista - Analista | Analista aziendale, analista dati, analista ricerche di mercato, analista finanziario, analista operazioni |
| Sviluppatore - Sviluppatore | Sviluppatore front-end, sviluppatore back-end, sviluppatore full-stack, sviluppatore app mobile, ingegnere DevOps |
| Personale professionale - Personale professionale | Specialista delle risorse umane, Consulente legale, Responsabile per la conformità, Project Manager, Specialista di approvvigionamento |
| Consulente - Consulente | Consulente di gestione, consulente IT, consulente di processo aziendale, consulente di marketing |
| Altro - Altro | Specialista di settore, consulente indipendente, consulente freelance, esperto in materia |

### Filtraggio elenco

Per individuare l’utente tipo desiderato, immetti una stringa di testo nella barra di ricerca in modo che corrisponda agli utenti tipo per nome.

![Filtra i mapping utente tipo visualizzati](assets/configuration-persona-mapping-search.png){width="700" zoomable="yes"}

## Creare un utente tipo {#create-a-persona}

1. Nel menu di navigazione a sinistra, scegli **[!UICONTROL Amministrazione]** > **[!UICONTROL Configurazione]**.

1. Fai clic su **[!UICONTROL Mappatura personale]** nel pannello intermedio.

1. Fai clic su **[!UICONTROL Crea utente tipo]**.

1. Immetti un **[!UICONTROL Nome]** e una **[!UICONTROL Descrizione]** univoci (facoltativo) per l&#39;utente tipo.

   ![Creare un mapping utente tipo](assets/configuration-persona-mapping-new.png){width="700" zoomable="yes"}

1. Seleziona gli attributi da utilizzare per la corrispondenza con l’utente tipo.

   * Fare clic su **[!UICONTROL Seleziona attributi persona]**.

   * Nella finestra di dialogo, seleziona la casella di controllo per ogni attributo che desideri mappare (un massimo di cinque).

     Puoi personalizzare la tabella visualizzata facendo clic sull&#39;icona _Impostazioni colonna_ ( ![Impostazioni colonna](../assets/do-not-localize/icon-column-settings.svg) ) nell&#39;angolo in alto a destra.

     Per filtrare l&#39;elenco di attributi in base al nome, immettere una stringa di testo nella barra di ricerca. Puoi anche fare clic sull&#39;icona _Filtro_ ( ![Icona Filtro](../assets/do-not-localize/icon-filter.svg) ) in alto a sinistra per filtrare l&#39;elenco visualizzato per tipo, _Standard_ o _Personalizzato_.

     ![Finestra di dialogo Seleziona attributi persona](assets/configuration-persona-mapping-select-attributes.png){width="700" zoomable="yes"}

   * Fai clic su **[!UICONTROL Salva]**.

     Gli attributi selezionati sono inseriti nella sezione _[!UICONTROL Attributi personali]_.

1. Per ogni attributo, immettere i valori separati da virgola che si desidera associare per l&#39;attributo.

1. Fai clic su **[!UICONTROL Invia]**.

## Modificare un tipo di utente {#edit-a-persona}

Fai clic sul nome dell’utente tipo per accedere e modificare i relativi dettagli.

È possibile modificare il nome o la descrizione, aggiungere attributi o aggiornare i valori degli attributi. Al termine delle modifiche, fai clic su **[!UICONTROL Invia]**.

## Eliminare un utente tipo {#delete-a-persona}

Se si elimina un utente tipo, questo viene rimosso dall&#39;elenco _Mapping persona_ e non è più disponibile come filtro utente tipo derivato negli elenchi persone o nei percorsi di persone.

1. Nella pagina _[!UICONTROL Mapping persona]_ individuare l&#39;utente tipo che si desidera eliminare.

1. Accanto al nome fare clic sui puntini di sospensione (**...**) e scegliere **[!UICONTROL Elimina]**.

1. Nella finestra di dialogo di conferma, fai clic su **[!UICONTROL Elimina]**.

## Filtra per persona derivata {#derived-persona-filter}

Dopo aver configurato gli utenti tipo, Marketo Optimizer deriva un utente tipo per ogni record persona valutandone gli attributi in base alle mappature utente definite. È possibile utilizzare il risultato dedotto, ovvero _Persona derivata_, come filtro durante la definizione del pubblico per un elenco di persone o un percorso di persone.

Il filtro Persona derivata viene visualizzato nel pannello dei filtri nella categoria **[!UICONTROL Filtri speciali]** insieme ad altri attributi dedotti, ad esempio l&#39;appartenenza al percorso.

### Elenchi di persone

Quando si aggiungono o rimuovono membri da un elenco di persone statiche o quando si definiscono le regole di appartenenza per un elenco di persone dinamiche, è possibile filtrare per Persona derivata per eseguire il targeting di tutte le persone i cui attributi corrispondono a un utente specifico configurato.

**Elenco statico — Aggiungi membri**

1. Apri l&#39;elenco statico e fai clic su **[!UICONTROL Aggiungi persone]** in alto a destra.

1. Nella finestra di dialogo del filtro, espandi **[!UICONTROL Filtri speciali]** e trascina **[!UICONTROL Persona derivata]** nell&#39;area di lavoro.

1. Nella condizione del filtro, scegli **[!UICONTROL is]** e seleziona uno o più utenti tipo dall&#39;elenco.

1. Fai clic su **[!UICONTROL Fine]** per applicare il filtro e qualificare le persone corrispondenti nell&#39;elenco.

**Elenco dinamico - Imposta regole di appartenenza**

1. Apri l&#39;elenco dinamico e seleziona la scheda **[!UICONTROL Regole]**.

1. Fai clic su **[!UICONTROL Modifica regole]**.

1. Nella finestra di dialogo del filtro, espandi **[!UICONTROL Filtri speciali]** e trascina **[!UICONTROL Persona derivata]** nell&#39;area di lavoro.

1. Nella condizione del filtro, scegli **[!UICONTROL is]** e seleziona uno o più utenti tipo dall&#39;elenco.

1. Fai clic su **[!UICONTROL Fine]** per salvare la regola.

   L’iscrizione viene aggiornata automaticamente quando i record delle persone vengono valutati in base alla regola.

### Percorsi di persone

Quando configuri il pubblico per un percorso di persone utilizzando un pubblico di eventi, puoi utilizzare Persona derivata come filtro del profilo di persona per controllare quali persone entrano nel percorso.

1. Fai clic sul nodo **[!UICONTROL Pubblico persona]** nell&#39;area di lavoro del percorso.

1. Nel pannello delle proprietà del nodo, seleziona **[!UICONTROL Pubblico evento]** come tipo di pubblico.

1. In **[!UICONTROL Filtri profilo persona]**, fare clic su **[!UICONTROL Aggiungi filtro]**.

1. Espandi **[!UICONTROL Filtri speciali]** e trascina **[!UICONTROL Persona derivata]** nell&#39;area di lavoro del filtro.

1. Nella condizione del filtro, scegli **[!UICONTROL is]** e seleziona uno o più utenti tipo dall&#39;elenco.

   Solo le persone la cui persona derivata corrisponde ai valori selezionati possono entrare nel percorso.
