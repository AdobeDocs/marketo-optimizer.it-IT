---
title: Rapporto individuale Percorso di persone
description: Scopri il rapporto Individuale Percorso di persone in Adobe Marketo Optimizer, che mostra le metriche di completamento, coinvolgimento e e-mail per un percorso.
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
source-git-commit: 531dce4ffe6000efa0296f0e2393423f54124ea7
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 0%
---

# Rapporto individuale Percorso di persone

<!-- SPHR-39120: UX plans to move the Journey activity flow tile to the top of the report. Update the tile order in this page when that ships. -->

Fai clic su **[!UICONTROL Visualizza rapporto]** per un percorso di persone live o completate per visualizzarne le prestazioni, inclusi stato, coinvolgimento, metriche e-mail e flusso di attività.

_Per visualizzare il report :_

1. Apri un percorso di persone **[!UICONTROL Live]** o **[!UICONTROL Finished]** dall&#39;elenco _[!UICONTROL Person percorsi]_.
1. Nell&#39;intestazione del percorso selezionare **[!UICONTROL Visualizza report]**.

   ![Area di lavoro del percorso di persone con il pulsante Visualizza report evidenziato nell&#39;intestazione del percorso.](./assets/reports-person-journey-view-report.png){width="600" zoomable="yes"}

È possibile [modificare l&#39;intervallo di date](./reports-overview.md#change-the-date-range) per il report.

Seleziona **[!UICONTROL Condividi]** nella parte superiore del report per scaricare o pianificare un&#39;esportazione dei dati. Vedi [_Esportare un report_](./reports-overview.md#export-a-report) nella panoramica dei report.

![Rapporto individuale Percorso di persone che mostra lo stato del percorso, la tendenza di completamento e i riquadri di coinvolgimento.](./assets/reports-individual-journey.png){width="700" zoomable="yes"}

## Filtri {#filters}

L’ambito dei filtri del rapporto corrisponde al percorso corrente.

* **[!UICONTROL Nome Percorso (Evento)]** - Preimpostato per il percorso da cui hai aperto il report.
* **[!UICONTROL Persona (evento)]** - (_Non ancora supportato_) filtra il report per le persone che corrispondono a un [utente tipo derivato](../audiences/personas.md#filter-by-derived-persona) specifico. Il valore predefinito è [!UICONTROL Nessun filtro].

Selezionare **[!UICONTROL Reimposta tutto]** per cancellare il filtro _[!UICONTROL Persona (Evento)]_ e tornare alla visualizzazione predefinita.

## Stato e coinvolgimento della persona {#person-status-and-engagement}

Questa sezione presenta quattro sezioni:

* **[!UICONTROL Stato delle persone nel percorso]** - Suddivide le persone nel percorso in _[!UICONTROL Categorie completate]_ e _[!UICONTROL In corso]_, con percentuali corrispondenti.
* **[!UICONTROL Persone completate nel tempo]** - Grafico a linee che tiene traccia del numero di persone che hanno completato il percorso nell&#39;intervallo di date selezionato.
* **[!UICONTROL Persone coinvolte e non impegnate]** - Suddivide le persone nel percorso in _[!UICONTROL Categorie impegnate]_ e _[!UICONTROL Non impegnate]_, con percentuali corrispondenti.
* **[!UICONTROL Persone occupate]** - Numero totale di persone qualificate come occupate nel percorso.

## Prestazioni e-mail {#email-performance}

La tabella delle prestazioni [!UICONTROL E-mail] mostra le metriche di consegna e coinvolgimento per ogni e-mail inviata nel percorso. Per le stesse metriche e-mail per tutti i percorsi, consulta il [report sul coinvolgimento e-mail](./email-engagement-report.md).

![Tabella delle prestazioni delle e-mail che mostra le metriche inviate, recapitate, aperte e su cui è stato fatto clic per un&#39;e-mail.](./assets/reports-individual-journey-email-performance.png){width="700" zoomable="yes"}

[!UICONTROL Prestazioni e-mail] colonne tabella:

* [!UICONTROL Nome e-mail] - Nome dell&#39;e-mail.
* [!UICONTROL Inviato] - Numero di e-mail inviate.
* [!UICONTROL Recapitato] - Numero di e-mail consegnate.
* [!UICONTROL % recapitato] - Numero di e-mail consegnate diviso per il numero inviato.
* [!UICONTROL Aperto] - Numero di volte in cui i destinatari hanno aperto l&#39;e-mail.
* [!UICONTROL % aperti] - Numero di e-mail aperte diviso per il numero consegnato.
* [!UICONTROL Clic] - Numero di volte in cui i destinatari hanno fatto clic su un collegamento nell&#39;e-mail.
* [!UICONTROL % clic] - Numero di e-mail su cui è stato fatto clic diviso per il numero di messaggi consegnati.

## Flusso attività percorso {#journey-activity-flow}

La visualizzazione [!UICONTROL Flusso attività Percorso] mostra il percorso seguito dalle persone nel percorso, a partire dall&#39;attività _[!UICONTROL Aggiungi persona al Percorso]_. Ogni nodo mostra il numero di visualizzazioni del percorso per tale attività.

![Visualizzazione del flusso di attività del Percorso che mostra le visualizzazioni del percorso da Aggiungi persona al percorso tramite consegna e-mail.](./assets/reports-individual-journey-activity-flow.png){width="700" zoomable="yes"}
