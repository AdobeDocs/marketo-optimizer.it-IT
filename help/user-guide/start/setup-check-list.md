---
title: Elenco di controllo per l'installazione
description: Completa le attività di configurazione iniziali per l’istanza di Marketo Optimizer, inclusa la configurazione dell’accesso utente e l’infrastruttura di recapito messaggi e-mail.
TQID: 'https://experienceleague.adobe.com/XEPKIa88-L7mdPz1opKegY1pdEF4Qyls0nLVJBQSaJk'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2: id: 3cf5f37e-e87e-5179-812b-53ce05d7eebbid: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 249
ht-degree: 10%

---

# Elenco di controllo per l’installazione

Completa queste attività per abilitare la funzionalità nell&#39;istanza [!DNL Marketo Optimizer] con provisioning.

## Abilita accesso utente {#enable-user-access}

Una volta completato il provisioning e quando le sandbox sono associate, configura l&#39;accesso [!DNL Journey Optimizer B2B Edition] per il team e gli utenti.

<table>
<thead>
<tr>
<th colspan="2">Attività</th>
<th>Dettagli e istruzioni</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><strong>Fornisci l'accesso al prodotto e le autorizzazioni</strong> per gli utenti</td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Casella di controllo per l'attività"/></td>
<td>Creazione di un profilo di prodotto Journey Optimizer B2B edition in Admin Console (solo configurazione una tantum/iniziale)</td>
<td><a href="./user-management.md#create-profile">Crea profilo</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Casella di controllo per l'attività"/></td>
<td>Aggiungere un gruppo di utenti in Admin Console</td>
<td><a href="./user-management.md#add-user-group">Aggiungi gruppo utenti</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Casella di controllo per l'attività"/></td>
<td>Assegnare il profilo di prodotto al gruppo di utenti in Admin Console</td>
<td><a href="./user-management.md#assign-profile">Assegna profilo prodotto</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Casella di controllo per l'attività"/></td>
<td>Aggiungere utenti al gruppo di utenti in Admin Console</td>
<td><a href="./user-management.md#add-users">Aggiungere utenti</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Casella di controllo per l'attività"/></td>
<td>Modificare i ruoli incorporati o creare un ruolo personalizzato con le autorizzazioni del prodotto</td>
<td><a href="./user-management.md#edit-role-permissions">Modifica ruoli</a> <br/> <a href="./user-management.md#create-a-custom-role">Crea un ruolo personalizzato</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Casella di controllo per l'attività"/></td>
<td>Aggiungere utenti o gruppi ai ruoli in Adobe Experience Platform</td>
<td><a href="./user-management.md#add-users-to-a-role">Aggiungi utenti</a> <br/><a href="./user-management.md#add-user-groups-to-a-role">Aggiungi gruppi</a></td>
</tr>
</tbody>
</table>

## Recapitabilità delle e-mail {#email-deliverability}

Prima che gli esperti di marketing possano inviare e-mail dai percorsi, configura l’infrastruttura di invio per la tua organizzazione, inclusi la delega dei sottodomini, l’autenticazione e-mail e le impostazioni dei canali.

<table>
<thead>
<tr>
<th colspan="2">Attività</th>
<th>Dettagli e istruzioni</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><strong>Configurare il recapito messaggi e-mail e le impostazioni del canale</strong></td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Casella di controllo per l'attività"/></td>
<td>Delegare un sottodominio ad Adobe (completamente delegato o CNAME)</td>
<td><a href="./email-deliverability.md#delegate-fully-delegated">Delega completa</a> <br/> <a href="./email-deliverability.md#delegate-cname">CNAME</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Casella di controllo per l'attività"/></td>
<td>Configurare DMARC per il sottodominio</td>
<td><a href="./email-deliverability.md#configure-dmarc">Configurare DMARC</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Casella di controllo per l'attività"/></td>
<td>Revisione e assegnazione di un pool IP</td>
<td><a href="./email-deliverability.md#review-ip-pool">Verifica pool IP</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Casella di controllo per l'attività"/></td>
<td>Creare una configurazione del canale e-mail</td>
<td><a href="../admin/email-channel-configuration.md#create-email-channel-configuration">Configurare il canale e-mail</a></td>
</tr>
</tbody>
