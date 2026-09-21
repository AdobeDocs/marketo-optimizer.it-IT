---
title: Rapporto di coinvolgimento e-mail
description: Scopri il rapporto Coinvolgimento e-mail in Adobe Marketo Optimizer, che mostra il recapito messaggi e le metriche di coinvolgimento per e-mail e percorso.
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
source-git-commit: 6e919a66af259ea1f5facf7f5c3e811d76101e85
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 0%
---

# Rapporto di coinvolgimento e-mail

<!-- SPHR-32511: Filter by Program, Filter by Audience, and the program data point for the email performance table are not documented here pending delivery. -->

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

## Filtri {#filters}

Utilizza i filtri per restringere il rapporto a un percorso o a un utente tipo specifico. Seleziona **[!UICONTROL Reimposta tutto]** per cancellare ogni filtro e tornare alla visualizzazione predefinita.

* **[!UICONTROL Nome Percorso (Evento)]** - Filtra in base al percorso che ha inviato l&#39;e-mail. Il valore predefinito è [!UICONTROL Nessun filtro].
* **[!UICONTROL Persona (evento)]** - Filtra in base all&#39;utente tipo associato all&#39;e-mail. Il valore predefinito è [!UICONTROL Nessun filtro].