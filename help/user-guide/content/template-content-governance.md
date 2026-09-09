---
title: Governance dei contenuti per i modelli
description: Utilizza le impostazioni di governance in Marketo Optimizer per bloccare il contenuto dei modelli e-mail a livello di struttura o di componente, controllando cosa possono modificare gli autori di e-mail.
TQID: 'https://experienceleague.adobe.com/0QZuUrqbF97W7c9yZzBYY39EC7DmbadKxXOJxjxDDy8'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
topic_v2: id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 608
ht-degree: 0%

---


# Governance dei contenuti per i modelli

Il blocco del contenuto consente agli autori dei modelli di definire regole di governance che limitano le parti di un modello e-mail che possono essere modificate quando il modello viene utilizzato in un messaggio e-mail. In questo modo i team del marchio e di conformità possono proteggere gli elementi chiave del design, ad esempio intestazioni, loghi e contenuti legali, e al contempo consentire ai team di marketing di personalizzare il messaggio all’interno della struttura approvata.

>[!NOTE]
>
>Il blocco dei contenuti è una funzione di governance a livello di editor. Controlla gli elementi che gli autori possono modificare nello spazio di progettazione delle e-mail, ma non impedisce le modifiche effettuate tramite l’API.

Solo gli utenti con l&#39;autorizzazione **[!UICONTROL Gestisci modelli di contenuto]** possono configurare le impostazioni di governance.

## Abilita governance {#enable}

>[!NOTE]
>
>In questa versione di Beta, sono supportati solo i modelli e-mail.

1. Aprire il modello nello spazio di progettazione.
1. Nell&#39;area di lavoro fare clic sul componente **[!UICONTROL Body]** per selezionarlo.
1. Seleziona l&#39;icona _Impostazioni_ per il pannello di destra,
1. Attiva/Disattiva **[!UICONTROL Governance]**.
1. Per **[!UICONTROL Modalità]**, selezionare il tipo di governance che si desidera applicare:

   | Modalità | Descrizione |
   | ---- | ----------- |
   | **[!UICONTROL Blocco dei contenuti]** | Bloccare selettivamente strutture o componenti specifici. Le aree sbloccate rimangono modificabili dagli autori. |
   | **[!UICONTROL Sola lettura]** | Blocca l&#39;intero modello. Gli autori possono applicarlo a un’e-mail ma non possono modificarne alcuna parte del contenuto. |

1. Se hai selezionato la modalità di blocco del contenuto, puoi definire ulteriormente il modo in cui gli utenti possono interagire con il modello.

   Attiva l&#39;opzione Abilita aggiunta contenuto e scegli una delle opzioni seguenti:

   * **[!UICONTROL Consenti aggiunta struttura e contenuto]** - Gli utenti possono aggiungere strutture tra quelle esistenti e aggiungere componenti di contenuto o frammenti all&#39;interno di strutture modificabili.

   * **[!UICONTROL Consenti solo l&#39;aggiunta di contenuto]** - Gli utenti possono aggiungere componenti di contenuto o frammenti all&#39;interno di strutture modificabili, ma non possono aggiungere o duplicare strutture.

### Bloccare una struttura {#lock-structure}

1. Nell’area di lavoro, seleziona la struttura (layout colonne) da proteggere.
1. Nella barra a destra, abilita l&#39;interruttore **[!UICONTROL Blocca struttura]**.

Tutto il contenuto nidificato all’interno di una struttura bloccata viene bloccato automaticamente. Per consentire a un componente specifico all&#39;interno di una struttura bloccata di rimanere modificabile, seleziona il componente e abilita **[!UICONTROL Modificabile]** nella barra a destra.

Per impostazione predefinita, gli autori non possono eliminare una struttura bloccata. Per consentire l&#39;eliminazione, abilita l&#39;opzione **[!UICONTROL Consenti eliminazione]** nella barra a destra.

### Bloccare un componente {#lock-component}

All’interno di una struttura modificabile, puoi bloccare singoli componenti di contenuto.

1. Seleziona il componente nell’area di lavoro.
1. Nella barra a destra, abilita l&#39;interruttore **[!UICONTROL Blocca contenuto]** e scegli il tipo di blocco:

   | Tipo di blocco | Descrizione |
   | --------- | ----------- |
   | **[!UICONTROL Bloccato]** | Impedisce sia le modifiche di contenuto che di stile. Gli autori non possono modificare il testo o l’aspetto del componente. |
   | **[!UICONTROL Solo contenuto modificabile]** | Consente agli autori di modificare il testo e il contenuto, ma impedisce le modifiche allo stile, quali colori, font e spaziatura. |
   | **[!UICONTROL Modificabile]** | Consente modifiche complete anche all&#39;interno di una struttura bloccata. |

Per impostazione predefinita, gli autori non possono eliminare un componente bloccato. Per consentire l&#39;eliminazione, abilita l&#39;opzione **[!UICONTROL Consenti eliminazione]** nella barra a destra.

### Consenti aggiunte di contenuto {#allow-additions}

Quando si utilizza la modalità **[!UICONTROL Blocco contenuto]**, è possibile consentire agli autori di aggiungere nuovi contenuti al modello mantenendo gli elementi bloccati protetti:

1. Abilita **[!UICONTROL Consenti aggiunta contenuto]**.
1. Scegli se gli autori possono aggiungere sia strutture che componenti di contenuto oppure solo componenti di contenuto.

## Identificare gli elementi bloccati {#identify}

La **[!UICONTROL struttura di navigazione]** nella barra a sinistra mostra icone di lucchetto e matita per consentire agli autori di identificare rapidamente ciò che possono e non possono modificare:

* Un&#39;icona **lucchetto** indica un elemento bloccato.
* Un&#39;icona di **matita** indica un elemento modificabile.

Per migliorare ulteriormente la visibilità, abilita l&#39;interruttore **[!UICONTROL Evidenzia aree modificabili]** per distinguere visivamente le aree modificabili da quelle bloccate nell&#39;area di lavoro.

## Considerazioni

Le impostazioni di governance vengono salvate con il modello. Qualsiasi e-mail creata da un modello gestito eredita la relativa configurazione di blocco al momento dell’applicazione. L’aggiornamento delle impostazioni di governance su un modello non influisce sulle e-mail create in precedenza da esso.
