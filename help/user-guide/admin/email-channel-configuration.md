---
title: Configurazione canale e-mail
description: Crea e gestisci le configurazioni del canale e-mail che associano l’identità del mittente, il sottodominio, il pool IP, il tipo di e-mail e il tracciamento URL per Marketo Optimizer.
feature: Administration
role: Admin
TQID: 'https://experienceleague.adobe.com/VDqL3u2vPJ8YGJgZCx5lE0Xt1-WvAEBBwFiMZGj7w90'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2: id: 3cf5f37e-e87e-5179-812b-53ce05d7eebbid: 64b90904-e4f0-5c1b-a871-8c6a40b204a1id: a659ad61-de21-559d-a901-02e2fb329ff5id: d4203578-d294-5145-b397-f26f4488a904
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 624
ht-degree: 0%

---

# Configurazione del canale e-mail

Una configurazione del canale è l’oggetto centrale che unisce l’identità del mittente, il sottodominio, il pool IP e le impostazioni di tracciamento. Le azioni e-mail nei percorsi fanno riferimento a una configurazione di canale per sapere come inviare il messaggio. Prima di creare una configurazione, completa la [delega del sottodominio e la configurazione del pool IP](../start/email-deliverability.md).

* **Canale:** E-mail.
* **Tipo di e-mail:** di marketing o transazionale. Questa impostazione determina se le regole di soppressione sono applicabili (Marketing le applica; Transazionale ignora la soppressione dei reclami spam per impostazione predefinita per i messaggi transazionali legittimi).
* **Parametri intestazione:** Da nome, Da e-mail, Nome risposta, E-mail risposta, E-mail errore.
* **Sottodominio:** Il sottodominio delegato utilizzato per l&#39;invio. Il Da e-mail deve utilizzare questo sottodominio.
* **Pool IP:** Pool IP utilizzato per recapitare il messaggio.
* **Tracciamento URL:** Attiva o disattiva il tracciamento dei clic e dei messaggi aperti; configura il dominio di tracciamento.
* **Tag:** Tag per organizzazione e ricerca.

## Creare una configurazione del canale e-mail {#create-email-channel-configuration}

>[!PREREQUISITES]
>
>* Almeno un [sottodominio](../start/email-deliverability.md#subdomain-delegation) deve essere delegato e attivo.
>* È necessario assegnare almeno un [pool IP](../start/email-deliverability.md#ip-pools) all&#39;organizzazione.
>* È necessario il ruolo di amministratore.
>* Rivedi [limitazioni correnti](../start/email-deliverability.md#limitations) — I pool IP dedicati non sono disponibili in Beta.

1. Nella barra di navigazione a sinistra di [!DNL Adobe Marketo Optimizer], espandi **[!UICONTROL Amministrazione]** e seleziona **[!UICONTROL Canali]**.
1. Nel pannello, espandi **[!UICONTROL Impostazioni e-mail]** e seleziona **[!UICONTROL Configurazioni canale]**.
1. Fai clic su **[!UICONTROL Crea configurazione canale]**.
1. Immettere un nome (ad esempio, _Marketing B2B Contoso - Nord America_) e una descrizione facoltativa.
1. Seleziona il canale **[!UICONTROL E-mail]**.
1. (Facoltativo) Seleziona i tag per categorizzare la configurazione.
1. Nella sezione **[!UICONTROL Tipo di e-mail]**, scegli Marketing o Transazionale.
1. Nella sezione **[!UICONTROL Sottodominio]**, seleziona un sottodominio delegato in precedenza.
1. Nella sezione **[!UICONTROL Pool IP]** selezionare un pool IP attivo.

   In Beta è disponibile solo il pool IP condiviso. Puoi passare il cursore sugli IP per visualizzare i record PTR.

1. Configura i **[!UICONTROL parametri intestazione]**:
   * Dal nome (ad esempio, &quot;Contoso Marketing&quot;).
   * Da e-mail: deve utilizzare il sottodominio selezionato (ad esempio, `marketing@mail.contoso.com`).
   * Nome e indirizzo di risposta: il valore predefinito è _Da_ se vuoto.
   * E-mail di errore: indirizzo che riceve le notifiche di mancato recapito.
1. Abilita **[!UICONTROL Tracciamento URL]** e seleziona il dominio di tracciamento.
1. Fai clic su **[!UICONTROL Invia]**.

>[!NOTE]
>
>Dopo l’invio, il sistema esegue la convalida: stato del sottodominio, record MX, allineamento SPF/DKIM/DMARC, preparazione del pool IP, registrazione FBL. La configurazione si sposta attraverso l&#39;Elaborazione di bozze → → attiva.

>[!NOTE]
>
>Se la convalida non riesce, la configurazione passa allo stato **[!UICONTROL Non riuscito]**. Apri la configurazione per visualizzare il motivo dell’errore. Cause comuni sono errori di convalida dei record MX, IP nel pool che non corrispondono alla configurazione o disallineamento di DMARC. Risolvi e invia di nuovo.

## Modificare o eliminare una configurazione di canale {#edit-channel-configuration}

È possibile modificare le configurazioni di canale dopo la creazione, ma con un vincolo importante: **Il canale non può essere modificato.** Una configurazione è associata al relativo canale.

Quando modifichi una configurazione in uso:

* **Per i percorsi pubblicati:** la modifica viene applicata alla ricorrenza successiva o all&#39;esecuzione successiva. Le esecuzioni in volo continuano con le impostazioni precedenti.
* **Per i messaggi transazionali o in tempo reale:** le modifiche si propagano in circa cinque minuti.

>[!WARNING]
>
>L’eliminazione di una configurazione di canale è permanente. Non è possibile eliminare una configurazione a cui fa riferimento un percorso attivo. Rimuovi o riassegna prima tutte le azioni e-mail.

Per eliminare una configurazione, rimuovi o aggiorna innanzitutto ogni azione e-mail che vi fa riferimento in [Aggiungi e-mail ai percorsi](../marketing/email-channel.md#define-email-properties). [!DNL Marketo Optimizer] non elimina una configurazione attualmente utilizzata da un percorso attivo.

## Configurazioni multicanale {#multiple-channel-configurations}

La maggior parte delle organizzazioni B2B utilizza più configurazioni di canale per separare i marchi, le aree geografiche o i tipi di invio. Pattern comuni:

* Una configurazione marketing separata per unità aziendale (ad esempio, *BU-A Marketing*, *BU-B Marketing*).
* Una configurazione transazionale dedicata con Tipo e-mail = Transazionale per le notifiche di prodotti o contratti.
* Configurazioni specifiche per l&#39;area geografica che utilizzano sottodomini specifici dell&#39;area (ad esempio, `mail.eu.contoso.com`, `mail.us.contoso.com`) per l&#39;allineamento con gli ISP regionali e la conformità.

>[!TIP]
>
>Assegna alle configurazioni un nome chiaro e strutturato, ad esempio: *[Marchio] - [Regione] - [Tipo]*. Questo diventa critico una volta che hai una dozzina o più configurazioni.
