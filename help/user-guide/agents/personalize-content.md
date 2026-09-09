---
title: Personalizzazione del contenuto delle e-mail per persona
description: Utilizza l’abilità Personalization dei contenuti in Marketo Optimizer per trasformare un’e-mail in varianti basate su dati personali. Personalizzare o analizzare le e-mail.
TQID: 'https://experienceleague.adobe.com/9fa1wfsHH6h46jJ-slLxMpB6fud1VHgmiWxbao-bWvo'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2:
  - id: 1650dadf-b034-5ac9-a309-77ad1e2f5035
  - id: 46e599c6-e20f-5f67-9824-93415016f66b
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 1236
ht-degree: 0%

---


# Personalizzare il contenuto delle e-mail per persona

L&#39;abilità _Content Personalization_ trasforma un&#39;e-mail in varianti basate su dati personali, pertanto non è necessario creare un&#39;e-mail separata per ogni pubblico. Invece di inviare un messaggio dopo un evento, l&#39;abilità risolve il pubblico in [coorti tipo derivato](../audiences/personas.md), genera insights e genera varianti personalizzate. Ogni variante viene salvata come contenuto condizionale all’interno di una singola e-mail, in modo che ogni persona riceva automaticamente la versione che corrisponde al proprio utente tipo quando un percorso la invia.

* **Abilità** - `content-personalization`
* **Chiamata** - Dall&#39;[interfaccia chat](./chat-interface.md), descrivere un pubblico di destinazione per una nuova e-mail oppure selezionare **[!UICONTROL Personalizza questa e-mail]** o **[!UICONTROL Analizza questa e-mail]** in un&#39;e-mail esistente in un [Invia nodo e-mail](../marketing/action-nodes.md)
* **Lettura da/scrittura in** - [!DNL Marketo Optimizer]

## Concetti chiave {#key-concepts}

| Termine | Definizione |
|---|---|
| **Coorte personale** | Un gruppo di persone che condividono un [utente tipo derivato](../audiences/personas.md), ad esempio _CXO/EVP_ o _Collaboratore singolo_. |
| **Segmento** | Un gruppo di persone definito in base a qualsiasi criterio, ad esempio utente tipo, settore o livello di coinvolgimento. Una coorte tipo è un segmento definito in modo specifico dall’utente tipo derivato condiviso. |
| **Gruppo di destinazione** | Il pubblico che descrivi in linguaggio naturale. L’abilità lo risolve in coorti di utenti tipo corrispondenti. |
| **Insight** | Un risultato basato sui dati sulla messaggistica, il posizionamento o il tono che funziona meglio per una coorte di utenti tipo, tratto dai tuoi dati. |
| **Variante** | Versione personalizzata delle sezioni e-mail che hai scelto di personalizzare, generata per una coorte persona. |
| **E-mail personalizzata AI** | L&#39;unica e-mail salvata che racchiude ogni variante come [contenuto condizionale](../content/conditional-content.md) blocchi. |
| **Controllo e-mail** | Una rassegna di un’e-mail esistente rispetto a ciascuno dei segmenti del gruppo target, mostrando quali risonanze ha e cosa migliorare per ogni utente tipo prima di personalizzare. |

## Prerequisiti {#prerequisites}

* Accesso a [!DNL Marketo Optimizer] con Collaboratore abilitato.
* [Persone derivate](../audiences/personas.md) risolte nei tuoi dati. L’abilità si basa su queste classificazioni per creare coorti tipo. Il supporto personalizzato per l’utente è pianificato per una versione futura.
* Dati storici sufficienti per le informazioni. Se gli insights non sono disponibili per una coorte tipo, l’abilità indica che i dati sono insufficienti e si basa sulle best practice generali per tale persona.
* Un [modello e-mail](../content/templates.md) o un messaggio e-mail esistente a cui fa riferimento un nodo azione [_Invia e-mail_](../marketing/action-nodes.md).
* Un percorso di [persone](../marketing/person-journeys.md) contenente il nodo azione _Invia e-mail_ utilizzato per recapitare l&#39;e-mail personalizzata.

## Creare e personalizzare un’e-mail da un modello {#create-personalize-from-template}

Questo flusso crea una nuova e-mail e la personalizza nella stessa conversazione.

1. **Fornisci il contenuto.** Carica una descrizione del contenuto o descrivi il contenuto desiderato in un linguaggio naturale.

1. **Seleziona un [modello](../content/templates.md)** dalla libreria di modelli.

1. **Rivedi la bozza.**

   Il collaboratore mappa il contenuto sul modello e genera una bozza di e-mail. È possibile apportare modifiche di base al testo in linea.

   >[!WARNING]
   >
   >Durante l’authoring sono disponibili in linea solo le modifiche di testo di base. Per modifiche avanzate, salvare l&#39;e-mail e aprirla nello [spazio di progettazione visivo](../content/email-authoring.md).

1. **Descrivere il gruppo di destinazione** in linguaggio naturale.

1. **Rivedi le coorti persona risolte**.

   Collabora esamina i tuoi dati e restituisce le coorti tipo che corrispondono alla tua descrizione, con un conteggio per ciascuna. Rivedi la descrizione del gruppo target e riprova, se necessario.

1. **Conferma il gruppo di destinazione**.

   Quindi Collaboratore recupera informazioni approfondite per ogni coorte persona risolta.

1. **Selezionare le sezioni da personalizzare**, ad esempio la sezione dell&#39;oggetto o del corpo, ed esaminare le varianti generate.

   Rigenera una variante se non rientra nel testo. Il numero di coorti tipo non è fisso. Dipende dal gruppo di destinazione e dai dati.

1. **Salva l&#39;e-mail**.

   Tutte le varianti vengono memorizzate in un’e-mail personalizzata IA, non come e-mail separate.

<!-- screenshot: Coworker chat panel showing the resolved persona cohorts with counts, and the "Personalized variants" review grid -->

## Analizzare un’e-mail esistente {#analyze-existing-email}

In un percorso [_Invia e-mail_ nodo](../marketing/action-nodes.md) che fa riferimento a un indirizzo e-mail esistente, il pannello **[!UICONTROL Esegui un&#39;azione]** mostra il nome dell&#39;indirizzo e-mail con due opzioni: **[!UICONTROL Personalizza questo indirizzo e-mail]** e **[!UICONTROL Analizza questo indirizzo e-mail]**.

<!-- screenshot: Send Email node "Take an action" panel showing the email name and the Personalize this email / Analyze this Email options -->

Seleziona **[!UICONTROL Analizza questa e-mail]** per eseguire un controllo e-mail:

1. **Descrivi il gruppo target** per il quale desideri effettuare la personalizzazione, in termini di tipo di utente.

   Ad esempio _Persone con ruoli di marketing_ o _Persone con funzioni di leadership_.

1. **Verifica il controllo delle e-mail.**

   Coworker risolve la descrizione in segmenti personali e mostra una scheda di **Verifica e-mail** in cui sono elencati tutti i segmenti, quindi rivede l&#39;e-mail rispetto a ciascuno per evidenziare le ripercussioni e cosa migliorare.

1. Il collaboratore chiede cosa fare dopo, incluso **[!UICONTROL Vedere controllo sezione per sezione]** e **[!UICONTROL Personalizzare questa e-mail]**.

1. Seleziona **[!UICONTROL Consulta controllo sezione per sezione]** per aprire una visualizzazione **_Analisi e-mail_** con un selettore persona e raccomandazioni specifiche per ogni sezione.

   Ogni sezione mostra il numero di modifiche consigliate e ogni utente tipo mostra un conteggio di consigli, ad esempio `4 recommendations for SVP/VP`. Puoi anche applicare direttamente i consigli immettendo _personalizza_ nella chat.

1. Dal controllo di audit, seleziona **[!UICONTROL Personalizza questa e-mail]** per applicare gli approfondimenti e generare varianti.

   Consulta la sezione seguente, [_Personalizzare un&#39;e-mail esistente_](#personalize-existing-email).

<!-- screenshot: Email analysis view with persona selector, per-section "N changes" badges, and "what needs work" recommendations -->

## Personalizzare un’e-mail esistente {#personalize-existing-email}

Seleziona **[!UICONTROL Personalizza questa e-mail]** in un nodo di azione _Invia e-mail_ o continua da un [controllo e-mail](#analyze-existing-email), per personalizzare un e-mail già creato.

1. **Rivedi le coorti persona risolte.**

   Collabora esamina i tuoi dati e restituisce le coorti tipo che corrispondono alla tua descrizione, con un conteggio per ciascuna. Rivedi la descrizione del gruppo target e riprova, se necessario.

   Se sei arrivato a questo passaggio da un controllo e-mail, Collaborator continua direttamente dagli approfondimenti del controllo.

1. **Selezionare le sezioni da personalizzare** nell&#39;anteprima del messaggio di posta elettronica, ad esempio l&#39;oggetto e le sezioni di contenuto specifico, e confermare.

1. **Rivedi le varianti generate.**

   Oltre alla persona, le varianti possono anche variare in base al settore, ad esempio un CXO nel settore sanitario rispetto a un CXO nei servizi finanziari. Collaboratore presenta una griglia di **[!UICONTROL varianti personalizzate]**, una scheda per coorte tipo, ciascuna con oggetto, titolo, corpo e un&#39;opzione **[!UICONTROL Anteprima]**.

   Seleziona l&#39;icona _Informazioni_ su una scheda per visualizzare l&#39;insight dietro quella variante (l&#39;utente tipo su cui si basa e l&#39;insight di coinvolgimento che l&#39;ha modellata) e se necessario rigenera una variante.

   Puoi filtrare la griglia per persona.

1. **Salva il set.**

   Fai clic su **[!UICONTROL Salva]** e conferma. Il collaboratore conferma che l’e-mail è ora disponibile nella Libreria di intelligenza artificiale, quindi chiede se applicare le modifiche anche all’e-mail originale, che la aggiorna automaticamente.

<!-- screenshot: "Personalized variants" grid showing persona cards with subject, headline, body, Preview, and the info-icon insight tooltip -->

## Output salvato e utilizzo in un percorso {#saved-output}

Indipendentemente dal flusso da cui inizi, la personalizzazione produce un singolo messaggio e-mail **AI personalizzato** archiviato nella libreria di intelligenza artificiale. L&#39;e-mail contiene [contenuti condizionali](../content/conditional-content.md) blocchi impostati dall&#39;utente tipo. Per modificare le sezioni, aprirle nello [spazio di progettazione visivo](../content/email-authoring.md) e per visualizzare in anteprima la risoluzione di ogni blocco con chiave utente tipo, utilizzare **[!UICONTROL Simula contenuto]**.

Per utilizzare l&#39;e-mail in un percorso, aggiungi un [Invia nodo e-mail](../marketing/action-nodes.md) e seleziona **[!UICONTROL E-mail personalizzate AI]** invece di **[!UICONTROL Crea un&#39;e-mail]**, quindi scegli l&#39;e-mail salvata. Applica normalmente la configurazione e le regole aziendali al nodo.

<!-- screenshot: Send Email node configuration with "AI Personalized Emails" selected and the saved email applied -->

## Comportamento in fase di esecuzione {#run-time-behavior}

Seleziona l’e-mail personalizzata con IA singola nel percorso, non una variante per pubblico. Quando il percorso viene eseguito, l’e-mail viene risolta automaticamente nella variante che corrisponde all’utente tipo di ogni destinatario. Non scegli una variante per destinatario.

## Limitazioni {#limitations}

| Limitazione | Dettaglio |
|---|---|
| **Utenti tipo personalizzati** | Non ancora supportato. L&#39;abilità classifica le coorti tipo solo da [persone derivate](../audiences/personas.md) pronte all&#39;uso. |
| **Dati insufficienti per approfondimenti** | Se i dati non supportano una coorte insight per utente tipo, l’abilità lo indica e si basa sulle best practice generali per tale utente tipo. |
| **Modifica in linea durante la creazione** | Quando [crei e personalizzi un&#39;e-mail da un modello](#create-personalize-from-template), sono disponibili solo le modifiche di testo di base in linea. Le modifiche avanzate richiedono [spazio di progettazione visivo](../content/email-authoring.md). |
| **Punto iniziale richiesto** | La personalizzazione di un’e-mail richiede un modello o un’e-mail esistente a cui fa riferimento un nodo Invia e-mail. |
