---
title: Set di dati di Experience Platform
description: Scopri i set di dati che Marketo Optimizer scrive in Adobe Experience Platform per potenziare la generazione di rapporti e query ad hoc in Customer Journey Analytics.
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
source-git-commit: 1ebb0036699252c50f33ba6c0f4a56e8e670aacd
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 4%
---

# Set di dati di Experience Platform

[!DNL Adobe Marketo Optimizer] replica i dati di lead, percorso e attività in [!DNL Adobe Experience Platform] set di dati. Questi set di dati alimentano la pagina [!UICONTROL Report] e l&#39;esperienza di report [!DNL Adobe Customer Journey Analytics] incorporata. Puoi anche eseguire query direttamente con [!DNL Query Service] per l&#39;analisi ad hoc.

I set di dati sono gestiti dal sistema. Una connessione in [!DNL Customer Journey Analytics] li collega alla visualizzazione dati utilizzata dai report di [!DNL Marketo Optimizer], pertanto non è necessario creare personalmente la connessione. Questa connessione è la stessa che si raggiunge selezionando **[!UICONTROL Analizza in CJA]** in una sezione del report. Vedi [Analizzare un report in Customer Journey Analytics](./reports-overview.md#analyze-a-report-in-cja).

## Set di dati disponibili {#available-datasets}

I seguenti set di dati vengono compilati per ogni istanza [!DNL Marketo Optimizer].

>[!NOTE]
>
>Ogni nome di set di dati utilizza il prefisso `AJOB2B`, che indica il nome di sistema per i dati [!DNL Marketo Optimizer]. Questo comportamento è previsto ed è possibile utilizzare questi nomi per individuare i set di dati nella sandbox [!DNL Experience Platform].

| Set di dati | Schema | Descrizione |
| --- | --- | --- |
| `AJOB2B - Person` | Persona | Attributi lead standard. |
| `AJOB2B - PersonActivity` | Attività della persona | Eventi di attività associati a una persona. |
| `AJOB2B - PersonActivityType` | Tipo di attività della persona | Tipi di attività associati a una persona. |
| `AJOB2B - PersonActivityTypeEngagementMapping` | Mappatura del coinvolgimento del tipo di attività della persona | Mappa i tipi di attività in base alla classificazione del coinvolgimento, all’evento di canale e alla direzionalità. |
| `AJOB2B - Journey` | Percorso | Elenco dei percorsi e dei relativi metadati del ciclo di vita. |
| `AJOB2B - JourneyNode` | Nodo percorso | Elenco di nodi all’interno di un percorso e dei metadati associati. |
| `AJOB2B - EngagementAsset` | Risorsa di coinvolgimento | Ricerca unificata degli ID e dei nomi visualizzati delle risorse di coinvolgimento per diversi tipi di risorse di coinvolgimento. |

## Eseguire query sui set di dati con Query Service {#query-service}

Utilizzare [!DNL Query Service] per eseguire query SQL ad hoc su questi set di dati quando è necessaria l&#39;analisi al di fuori dei report [!DNL Customer Journey Analytics]. L&#39;accesso tramite query richiede le autorizzazioni [!DNL Experience Platform] appropriate per la sandbox. Per informazioni generali sulla sintassi e la configurazione delle query, vedere [Query Service](https://experienceleague.adobe.com/it/docs/experience-platform/query/home){target="_blank"}.

![L&#39;editor del servizio query visualizza una query SELECT per il set di dati ajob2b_percorsi e una tabella di record di percorso risultanti.](./assets/aep-query-service.png){width="800" zoomable="yes"}

>[!NOTE]
>
>Questi set di dati sono di sola lettura. Per modificare i dati acquisiti da [!DNL Marketo Optimizer], aggiornare i dati di origine in [!DNL Marketo Optimizer] o [!DNL Marketo Engage] anziché modificare direttamente un set di dati.
