---
title: Rapporto di coinvolgimento e-mail
description: Scopri il rapporto Coinvolgimento e-mail in Adobe Marketo Optimizer, che mostra il recapito messaggi e le metriche di coinvolgimento per e-mail e percorso.
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
source-git-commit: 8c47a9c69c32ba0a37ba2efadb6ad4c1b796c21d
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 0%
---

# Rapporto di coinvolgimento e-mail

<!-- SPHR-39569: content drafted, but hide: true and hide-from-toc stay until eng confirms this shipped to production. Filter by Program, Filter by Audience, and the program data point from SPHR-32511 are not documented here pending delivery-state confirmation. -->

Utilizza il rapporto [!UICONTROL Coinvolgimento e-mail] per rivedere il recapito messaggi e le prestazioni del coinvolgimento nell&#39;istanza, suddivisi per e-mail e percorso.

_Per visualizzare il report :_

1. Nel menu di navigazione a sinistra, seleziona **[!UICONTROL Rapporti]**.
1. Fai clic sull&#39;icona _Elenco_ ( ![Icona Elenco](../assets/do-not-localize/icon-table-of-contents.svg) ) e seleziona **[!UICONTROL Coinvolgimento e-mail]** nel pannello _[!UICONTROL Sommario]_.

![Report di coinvolgimento e-mail con filtri Nome Percorso e Persona, intervallo di date Ultimi 30 giorni e una tabella di metriche di attività e-mail.](./assets/reports-email-engagement.png){width="700" zoomable="yes"}

Puoi [modificare l&#39;intervallo di date](./reports-overview.md#change-the-date-range) utilizzando lo stesso selettore di intervalli di date disponibile in altre sezioni del rapporto.

Seleziona **[!UICONTROL Condividi]** nella parte superiore del report per scaricare o pianificare l&#39;esportazione di tutti i dati del report. Vedi [_Esportare un report_](./reports-overview.md#export-a-report) nella panoramica dei report.

## Tabella report {#report-table}

Il report [!UICONTROL Email Engagement] mostra una riga per ogni e-mail, con le seguenti dimensioni di riga.

* **[!UICONTROL Nome e-mail]** - Nome dell&#39;e-mail.
* **[!UICONTROL Nome Percorso]** - Nome del percorso che ha inviato l&#39;e-mail.

Le colonne delle metriche sono raggruppate in **[!UICONTROL Attività e-mail]**.

| Colonna | Descrizione |
| --- | --- |
| [!UICONTROL Inviato] | Numero di e-mail inviate. |
| [!UICONTROL Consegnato] | Numero di e-mail consegnate. |
| [!UICONTROL % recapitato] | Percentuale di e-mail inviate consegnate. |
| [!UICONTROL Notifica di mancato recapito] | Numero di e-mail che non sono state consegnate in modo permanente. |
| [!UICONTROL Rimbalzo morbido] | Numero di e-mail che al momento non sono state consegnate. |
| [!UICONTROL Aperto] | Numero di volte in cui i destinatari hanno aperto l’e-mail. |
| [!UICONTROL % aperto] | Percentuale di e-mail consegnate aperte. |
| [!UICONTROL Selezionato] | Numero di volte in cui i destinatari hanno fatto clic su un collegamento nell’e-mail. |
| [!UICONTROL % clic] | Percentuale di e-mail consegnate che hanno ricevuto un clic. |
| [!UICONTROL Fare clic per aprire la proporzione] | Percentuale di e-mail aperte che hanno ricevuto un clic. |
| [!UICONTROL Abbonamento annullato] | Numero di destinatari che hanno annullato l’abbonamento all’e-mail. |
| [!UICONTROL % ha annullato l&#39;abbonamento] | Percentuale di e-mail consegnate che hanno comportato l’annullamento dell’abbonamento. |

<!--

## Filters {#filters}

Use filters to narrow the report to a specific journey, persona, or date range. Select **[!UICONTROL Reset all]** to clear every filter and return to the default view.

* **[!UICONTROL Journey Name (Event)]** - Filter by the journey that sent the email. Default is [!UICONTROL No filter].
* **[!UICONTROL Persona (Event)]** - Filter by the persona associated with the email. Default is [!UICONTROL No filter].
* **[!UICONTROL Date range]** - Filter by a specific date span, shown as explicit start and end dates. Default is [!UICONTROL Last 30 days].
-->