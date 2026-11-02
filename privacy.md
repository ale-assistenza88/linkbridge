---
layout: default
title: "LinkBridge 1.1.16 - Informativa privacy / Privacy Policy"
permalink: /privacy.html
---

# LinkBridge — Privacy

[Italiano](#it) · [English](#en) · [Guida / User guide](guide.html)

<a id="it"></a>

## Informativa privacy — versione 1.1.16

Testo aggiornato il 2 novembre 2026.

LinkBridge aiuta a trasferire container FileCrypt compatibili a JDownloader sul computer dell'utente. Non richiede un account LinkBridge e non usa un server LinkBridge per raccogliere o conservare dati. Contatto: [linkbridge@assistenza88.it](mailto:linkbridge@assistenza88.it).

### Dati utilizzati e trasferimento locale

Quando avvii Clean Mode, l'estensione legge gli elementi necessari della pagina FileCrypt: URL del container e mirror, controlli di verifica, dati Click'n'Load (CNL), eventuali password degli archivi fornite dal container e, nel fallback ammesso, URL finali già presenti nella lista. I CAPTCHA interattivi restano manuali. L'estensione controlla se il sito richiede ancora interazione, senza risolvere CAPTCHA, modificare token o aggirare protezioni. Controlla anche la presenza di una risposta nei campi di verifica; non conserva il valore dei token. Se la sessione è già verificata e il CNL è utilizzabile, prosegue senza clic aggiuntivi.

Se il CNL è utilizzabile, LinkBridge invia il payload cifrato, il parametro chiave CNL, il riferimento al container e le eventuali password a JDownloader attraverso l'interfaccia locale HTTP su 127.0.0.1, porta 9666. Se manca CNL, il fallback accetta soltanto formati finali MEGA/Pixeldrain riconosciuti e già presenti negli elementi della lista, senza contattare tali URL per scoprirne la destinazione. Non vengono trasferiti token CAPTCHA a JDownloader. Il clic nativo FileCrypt rimane un'alternativa manuale monouso quando il payload non è estraibile.

Il completamento della trasmissione locale può provocare la chiusura della finestra Clean Mode, se la preferenza è attiva. Non costituisce conferma dell'importazione dei file in LinkGrabber. La preferenza è attiva per default e disattivabile nel popup dell'estensione. La chiusura riguarda soltanto la finestra Clean Mode creata per il tentativo, dopo circa 2,5 secondi dal completamento osservato del POST CNL. Un timeout, un errore, un CAPTCHA pendente, JDownloader irraggiungibile o l'assenza di un metodo supportato non autorizzano la chiusura. Un riferimento DLC viene solo segnalato: non è importato automaticamente.

### Conservazione locale

- In `chrome.storage.local`: preferenza di chiusura, massimo 200 eventi diagnostici e risultato dell'ultimo tentativo. Sono memorizzati stati, motivi codificati, tipo di percorso, conteggi, orari, identificatore casuale della sessione e codice HTTP. Questi nuovi record non contengono URL completi, payload CNL, chiavi, password, corpo delle risposte o token CAPTCHA.

- In `chrome.storage.session`: URL del container e mirror, identificativi della scheda/finestra, stato del tentativo, blocco contro doppi invii e ricevuta/scadenza per la chiusura. L'URL serve a riconoscere il tentativo: è distinto dal log diagnostico. Chrome cancella questi dati al riavvio del browser o quando l'estensione viene disattivata, ricaricata o aggiornata.

- Payload, chiavi, password e URL finali vengono trattati temporaneamente in memoria e nei messaggi necessari all'invio. Il codice di questa versione non li aggiunge ai nuovi log o record persistenti.

- Un aggiornamento da versioni precedenti può conservare dati già presenti, come URL rilevati/risolti e risultati del vecchio flusso. La 1.1.16 non esegue una cancellazione integrale di tutti i dati storici; l'apertura di un nuovo tentativo azzera alcuni campi legacy. Il precedente flusso di risoluzione dei redirect e copia automatica negli appunti non è disponibile.

I dati locali persistono fino alla loro sostituzione o rimozione. Il log conserva gli ultimi 200 eventi; l'ultimo esito viene sostituito dai tentativi successivi. Non viene usato `chrome.storage.sync`. La disinstallazione elimina lo storage dell'estensione; eventuali dati del sito o di JDownloader seguono le impostazioni di quei prodotti.

### Accesso ai siti e servizi terzi

L'accesso ai domini FileCrypt supportati permette il rilevamento dei controlli del container. L'accesso opzionale ai siti HTTP/HTTPS è richiesto al momento dell'uso per la comunicazione locale e per deviare le navigazioni esterne della sola scheda Clean Mode verso una pagina interna di arresto. I domini delle destinazioni intermedie non sono prevedibili. Non vengono seguite catene pubblicitarie per risolvere i link e questo accesso non viene usato per raccogliere la navigazione generale.

La pagina FileCrypt originale, i suoi CAPTCHA e le sue risorse restano pagine di terzi e possono fare proprie richieste di rete secondo le loro informative. Clean Mode non promette di bloccare tutte le pubblicità o tutte le finestre generate dal sito. Dopo la consegna, JDownloader può contattare gli hoster secondo le proprie impostazioni. LinkBridge non usa l'API dei cookie e non legge gli appunti; l'incollaggio manuale degli URL finali in JDownloader è un'azione dell'utente.

### Nessuna telemetria o codice remoto

LinkBridge non integra analytics, tracker, profilazione, vendita di dati o servizi di solving CAPTCHA. Non trasmette i dati a server gestiti dallo sviluppatore e non scarica codice da eseguire nell'estensione: il codice è incluso nel pacchetto. L'uso dei dati è limitato alla funzionalità descritta e rispetta i requisiti di uso limitato della Chrome Web Store User Data Policy. Non vengono ceduti dati per pubblicità, profilazione, credito o altri scopi estranei.

LinkBridge è indipendente da FileCrypt, JDownloader e dagli hoster. Usa l'estensione soltanto con servizi e contenuti ai quali sei autorizzato ad accedere. L'informativa va aggiornata se cambiano funzionalità o trattamento dei dati.

---

<a id="en"></a>

## Privacy policy — version 1.1.16

Updated text: November 2, 2026.

LinkBridge helps transfer compatible FileCrypt containers to JDownloader on your computer. It requires no LinkBridge account and operates no LinkBridge server that collects or stores user data. Contact: [linkbridge@assistenza88.it](mailto:linkbridge@assistenza88.it).

### Data use and local delivery

When you start Clean Mode, the extension reads the necessary FileCrypt page elements: container URL and mirror, verification controls, Click'n'Load (CNL) data, any archive passwords supplied by the container and, for the permitted fallback, final URLs already present in the file list. Interactive CAPTCHAs remain manual. The extension checks whether the site still requires interaction; it does not solve CAPTCHAs, modify tokens or bypass protections. It also checks whether verification fields contain a response; it does not retain token values. If the session is already verified and CNL is usable, it continues without an extra click.

When CNL is usable, LinkBridge sends the encrypted payload, CNL key parameter, container reference and any archive passwords to JDownloader through its local HTTP interface at 127.0.0.1, port 9666. Without CNL, the fallback accepts only recognized final MEGA/Pixeldrain formats already present in file-list elements, without contacting these URLs to discover their destination. CAPTCHA tokens are not sent to JDownloader. FileCrypt's native button remains a one-use manual alternative when the payload cannot be extracted.

Completed local transmission may close the Clean Mode window when the preference is enabled. It does not confirm that files were imported into LinkGrabber. This preference defaults to enabled and can be disabled in the extension popup. Only the Clean Mode window created for the attempt may close, approximately 2.5 seconds after observed completion of the CNL POST. A timeout, error, pending CAPTCHA, unreachable JDownloader or absence of a supported method does not authorize closing. A DLC reference is reported only; it is not imported automatically.

### Local retention

- `chrome.storage.local` stores the close preference, up to 200 diagnostic events and the last attempt outcome. Records contain states, coded reasons, route type, counts, times, a random session identifier and HTTP status. These new records do not contain full URLs, CNL payloads, keys, passwords, response bodies or CAPTCHA tokens.

- `chrome.storage.session` stores the container URL and mirror, tab/window identifiers, attempt state, duplicate-send reservation and closing receipt/deadline. The URL identifies the attempt and is separate from the diagnostic log. Chrome clears this storage when the browser restarts or the extension is disabled, reloaded or updated.

- Payloads, keys, passwords and final URLs are processed temporarily in memory and messages needed for delivery. This version does not add them to new logs or persistent records.

- Updating from older versions may retain existing data, such as detected/resolved URLs and results from the previous workflow. Version 1.1.16 does not erase all historical data; starting a new attempt resets some legacy fields. The previous redirect-resolution and automatic clipboard-copy workflow is unavailable.

Local data remains until replaced or removed. The log retains its latest 200 events; later attempts replace the last outcome. `chrome.storage.sync` is not used. Uninstalling removes the extension's storage; website and JDownloader data follow those products' own settings.

### Website access and third parties

Access to supported FileCrypt domains allows the extension to detect container controls. Optional HTTP/HTTPS host access is requested when used, for local communication and redirecting external navigation in the specific Clean Mode tab to an internal stop page. Intermediate domains cannot be predicted. LinkBridge does not follow advertising chains to resolve links or use this access to collect general browsing activity.

The original FileCrypt page, its CAPTCHAs and resources remain third-party content and may make their own network requests under their own policies. Clean Mode does not promise to block all advertising or every site-generated window. After delivery, JDownloader may contact hosters according to its settings. LinkBridge does not use the cookies API or read the clipboard; manually pasting final URLs into JDownloader is a user action.

### No telemetry or remotely hosted extension code

LinkBridge includes no analytics, trackers, profiling, data sales or CAPTCHA-solving services. It sends no data to developer-operated servers and does not download code for execution in the extension: executable code is packaged locally. Data use is limited to the functionality described and follows the Limited Use requirements of the Chrome Web Store User Data Policy. Data is not transferred for advertising, profiling, creditworthiness or unrelated purposes.

LinkBridge is independent of FileCrypt, JDownloader and hosting providers. Use it only with services and content you are authorized to access. This policy must be updated if functionality or data handling changes.
