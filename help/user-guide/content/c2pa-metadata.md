---
title: Metadati C2PA
description: Scopri in che modo Adobe Marketo Optimizer applica automaticamente i metadati C2PA alle immagini generate con intelligenza artificiale generativa e cosa significa per il contenuto.
feature: Assets, Content
role: User
TQID: 'https://experienceleague.adobe.com/DI9vJhE4EsGI4g4X5wz5-kqTjHOZqs6cvqo6Fke-4HU'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2: id: d4203578-d294-5145-b397-f26f4488a904
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dcid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 586
ht-degree: 0%

---

# Metadati C2PA

Le organizzazioni di marketing si preoccupano più che mai della trasparenza dei contenuti, della divulgazione dell’intelligenza artificiale e della prevenzione della manomissione delle risorse. Content Authenticity Initiative (CAI) di Adobe crea strumenti conformi allo standard tecnico [Coalition for Content Provenance and Authenticity](https://c2pa.org/specifications/specifications/1.1/specs/C2PA_Specification.html#_trust_model) (C2PA). _I metadati C2PA_ sono informazioni crittografate e in grado di evidenziare eventuali manomissioni che possono aiutare gli utenti a comprendere la derivazione dei contenuti e garantire l&#39;integrità delle risorse del marchio. Queste informazioni includono:

* Emittente o firmatario: informazioni sull&#39;entità o sulla società che ha emesso la firma digitale per certificare o firmare la risorsa.
* Data problema: la data in cui i metadati C2PA sono stati applicati alla risorsa.
* Credito e utilizzo: informazioni sul produttore della risorsa, tra cui nome, handle di social media o altre informazioni relative all&#39;identità.
* Processo - Registra eventuali modifiche apportate alla risorsa.
* Dettagli dispositivo — informazioni sull&#39;app o sul dispositivo utilizzato per creare o modificare la risorsa.
* Strumento di intelligenza artificiale utilizzato: se per creare la risorsa è stata utilizzata l’intelligenza artificiale generativa, è possibile includere il nome del modello utilizzato.
* Altre informazioni pertinenti: sono inclusi anche dati aggiuntivi per offrire maggiore contesto sulla cronologia di una risorsa.

Per informazioni complete sulla cronologia delle risorse, puoi utilizzare lo strumento di [ispezione di Adobe Content Authenticity](https://contentauthenticity.adobe.com/inspect).

I metadati C2PA persistono con il file di immagine. Quando un&#39;immagine generata o modificata con IA generativa viene caricata o esportata da [!DNL Adobe Marketo Optimizer], i relativi metadati C2PA vengono conservati.

Per ulteriori dettagli sull&#39;allegato automatico dei metadati C2PA nelle applicazioni Adobe CX Enterprise, vedi [_Trasparenza dei contenuti di IA generativa_](https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/overview/content-transparency){target="_blank"} nella guida AI in CX Enterprise.

>[!NOTE]
>
>Alcuni metodi di importazione di immagini nel contenuto, ad esempio l&#39;estrazione di un&#39;immagine da un PDF o da un&#39;origine incorporata (base64), potrebbero non conservare i metadati C2PA originali. In questi casi, i metadati C2PA non possono essere letti dalla sorgente e non ne viene creato alcuno per il risultato.

>[!BEGINSHADEBOX]

## Persistenza dei metadati C2PA tramite canali {#channels}

Quando includi le immagini nelle e-mail o nei messaggi WhatsApp, vengono mantenuti anche i metadati C2PA per le immagini consegnate:

* **E-mail** - Quando utilizzi un&#39;azione di percorso _Invia e-mail_, aggiungi l&#39;immagine al contenuto dell&#39;e-mail dalla libreria _Assets_. Quando l’e-mail viene consegnata, il destinatario può scaricare l’immagine dal messaggio e i metadati C2PA sono intatti.
* **WhatsApp** - Aggiungi l&#39;immagine al modello di messaggio WhatsApp nel tuo account aziendale Meta. Puoi aggiungerlo direttamente dal sistema o scaricare un file immagine dalla libreria _Assets_. Utilizza il modello per un&#39;azione di percorso _Invia WhatsApp_. Quando il messaggio WhatsApp viene consegnato, il destinatario può scaricare l’immagine dal messaggio e i metadati C2PA sono intatti.

>[!ENDSHADEBOX]

## Generazione di immagini {#generate}

>[!INFO]
>
>Nuove leggi stanno emergendo sulla trasparenza generativa dell’intelligenza artificiale e Adobe sta lavorando per soddisfare i requisiti applicabili in tutte le giurisdizioni. I metadati C2PA sono lo strumento di provenienza utilizzato da Adobe per soddisfare i requisiti di queste normative.

Quando si utilizza l&#39;intelligenza artificiale generativa per creare un&#39;immagine per il contenuto dell&#39;e-mail in [!DNL Marketo Optimizer], i metadati C2PA vengono automaticamente allegati all&#39;immagine generata e non è richiesta alcuna azione da parte dell&#39;utente. Gli strumenti di intelligenza artificiale generativi producono un elemento di metadati C2PA combinato per varianti di immagini con metadati esistenti, inclusa la sorgente originale.

>[!NOTE]
>
>[!DNL Marketo Optimizer] non supporta attualmente le azioni di modifica manuale delle immagini. I flussi di lavoro dei metadati C2PA per queste azioni non sono al momento applicabili.
