---
title: Programmi
description: Scopri come utilizzare i programmi per organizzare le attività di marketing e gestire percorsi e materiali di marketing da un’unica posizione.
TQID: 'https://experienceleague.adobe.com/RljL2N9P22AbWB6jSSaQ-iKlpTSz8d3cGNrIKatMH4o'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2:
  - id: 46e599c6-e20f-5f67-9824-93415016f66b
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
  - id: a29661b8-f7a4-53d1-a9ac-fdec08c092e4
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: ff2b9b37-92e0-45fc-b853-379d44c08c89
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 804
ht-degree: 1%

---

# Programmi

I programmi sono progettati per fornire contesto condiviso ai percorsi e ai materiali di marketing, in modo da poter gestire tutti gli aspetti di un’attività di marketing da un’unica posizione. Utilizza gli attributi del programma per descrivere il programma e utilizza il filtro _Membro del programma_ per segmentare il pubblico in base all&#39;iscrizione al programma, allo stato del membro e al successo. Dalla scheda Token, puoi gestire sia i _token personali_ locali che i token ereditati dalla struttura delle cartelle.

## Accedere ai programmi {#access-programs}

Ogni programma si trova nella struttura di cartelle _[!UICONTROL Marketing]_ e può contenere percorsi, elenchi e altre risorse per organizzare le attività di marketing.

1. Nella barra di navigazione a sinistra, espandere **[!UICONTROL Gestione marketing]**.

1. Sulla destra dell&#39;elenco delle risorse **[!UICONTROL Marketing]**, selezionare **[!UICONTROL Programmi]**.

1. Utilizza gli strumenti _Cerca_ e _Filtra_ per trovare elementi all&#39;interno della struttura.

1. Selezionare un programma o una cartella nella struttura per aprirne i dettagli nell&#39;area di lavoro centrale.

   ![Programma selezionato nella struttura ad albero dei programmi](./assets/programs-tree-select.png){width="800" zoomable="yes"}

   Selezionare una delle schede per accedere ai dettagli o ai contenuti del programma o della cartella.

## Creare un programma {#create-program}

>[!IMPORTANT]
>
>Ogni programma è basato su un [tipo di programma](../admin/program-types.md), che definisce aspetti importanti del programma e dei relativi membri. Prima di creare un programma, accertarsi di disporre di un tipo di programma definito per supportarlo.

1. Fai clic su **[!UICONTROL Crea programma]** nella parte superiore della struttura ad albero del programma.

1. Nella finestra di dialogo, seleziona il percorso **[!UICONTROL Principale]** all&#39;interno della struttura Programmi.

   Può trattarsi della directory principale, di una cartella o di un programma esistente.

1. Immetti un **[!UICONTROL Nome]** univoco (obbligatorio).

   ![Finestra di dialogo Crea programma](./assets/program-create-dialog.png){width="400"}

1. Scegliere **[!UICONTROL Tipo di programma]**, che determina gli attributi e gli stati dei membri del programma.

1. (Facoltativo) Immetti una **[!UICONTROL Descrizione]** per il programma.

   >[!TIP]
   >
   >L’inclusione di una descrizione è una best practice e rende i programmi più accessibili e individuabili.

1. Fai clic su **[!UICONTROL Crea]**.

## Attributi {#attributes}

Ogni programma eredita un set di attributi dal relativo [tipo di programma](../admin/program-types.md). Utilizza gli attributi per descrivere gli aspetti importanti dei programmi di marketing, ad esempio le date degli eventi e gli attributi di posizione.

>[!NOTE]
>
>In arrivo dopo Beta: attributi del programma come token e vincoli di membro del programma

## Stati {#statuses}

Ogni programma eredita un set di stati membri dal relativo tipo di programma. Questi stati possono essere assegnati ai membri del programma per l’utilizzo nella segmentazione del pubblico con il filtro Membro del programma.

Ogni stato viene assegnato a un passaggio del tipo di programma, ad esempio 1, 2 o 3. I membri di un programma possono passare solo da uno stato con lo stesso numero di passaggio (ad esempio, da _Non mostrato_ a _Partecipato_) o a uno stato con un numero di passaggio superiore (ad esempio, da _Invitato_ a _Registrato_).

Nel tipo di programma, gli stati con _[!UICONTROL Contrassegna come completati]_ sono considerati completati.

### Modifica lo stato del programma {#change-program-status}

Per aggiungere una persona a un programma o per modificarne lo stato, deve passare attraverso un&#39;azione **_[!UICONTROL Modifica stato programma]_** [in un percorso](./action-nodes.md). Questo li rende membri del programma e assegna loro uno stato in quel programma.

### Correggere lo stato di un programma {#correct-program-status}

Se le persone sono state assegnate a uno stato per errore e non possono essere spostate in avanti o in un secondo momento allo stato corretto, è possibile correggerlo impostando prima la persona su _Not in Program_, quindi impostandola sullo stato corretto.

## Membri {#members}

La scheda **Membri** mostra un inventario delle persone che sono membri del programma.

<!-- How do they get there? I don't see this populated for any of the programs that I have reviewd -->

## Token {#tokens}

Utilizza _I miei token_ per gestire facilmente i dettagli del programma visualizzati in molte posizioni, ad esempio date e posizioni dell&#39;evento, piè di pagina e-mail, anni e trimestri fiscali e altro ancora. Questi token specifici per il programma sono stringhe speciali progettate per essere riutilizzate in più percorsi o risorse di marketing al fine di sostituire un valore predeterminato. Ad esempio:

_Sei invitato a partecipare alla nostra esposizione il `{{my.Event Date}}`._

Se invii questa e-mail tramite un percorso in un programma con _Data evento_ Il mio token impostato su `2026-01-01`, il destinatario visualizzerà:

_Sei invitato a partecipare alla nostra esposizione il 01/01/2026._

I miei token possono essere assegnati anche a livello di cartella. Le cartelle e i programmi ereditano entrambi i token definiti per un elemento padre nella struttura. Un token ereditato può essere sovrascritto se per lo stesso token è definito un valore diverso a un livello inferiore. Ad esempio, puoi definire un piè di pagina e-mail nella parte superiore della struttura delle cartelle, ma modificare il linguaggio del copyright per un evento di co-marketing con un partner o cambiare l’URL di un banner promozionale per un programma specifico per il prodotto.

Per ulteriori informazioni sulla definizione e l&#39;utilizzo dei token personali, vedere [Token personalizzati per la personalizzazione](./personalization-my-tokens.md).

## Membro del filtro Programma {#member-of-program}

_Membro del programma_ è un filtro che consente di segmentare gli elenchi dinamici in base al fatto che un utente sia membro di un programma, allo stato in cui si trova e all&#39;esito positivo del programma. Presta attenzione quando utilizzi insieme i vincoli **_Programma_** e **_Stato_**: utilizza tipi corrispondenti ai programmi utilizzati per i filtri, altrimenti potrebbe creare inavvertitamente un pubblico che non può avere membri.
