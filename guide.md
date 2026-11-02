---
layout: default
title: "LinkBridge 1.1.16 - Guida / User Guide"
permalink: /guide.html
---

# LinkBridge — Guida / User Guide

[Italiano](#it) · [English](#en) · [Informativa privacy / Privacy policy](privacy.html)

<a id="it"></a>

## Italiano — versione 1.1.16

Aggiornata il 2 novembre 2026.

LinkBridge trasferisce i container FileCrypt compatibili a JDownloader sul tuo computer. Il percorso principale usa il **Click'n'Load nativo (CNL)** del container. La pagina originale e l'eventuale CAPTCHA rimangono visibili nella finestra dedicata **Clean Mode / Modalità pulita**.

### Avvio

1. Avvia JDownloader sullo stesso computer di Chrome.
2. Fai clic con il tasto destro su un link FileCrypt, sull'URL FileCrypt selezionato come testo oppure sulla pagina del container e scegli **Apri con LinkBridge**. In alternativa, apri il popup dell'estensione, incolla l'URL del container e premi **Apri con LinkBridge**.
3. Se Chrome richiede l'accesso opzionale HTTP/HTTPS, consenti l'accesso per continuare. Serve alla comunicazione con JDownloader locale e a fermare le navigazioni esterne della scheda Clean Mode su una pagina interna.
4. Completa manualmente il CAPTCHA **solo se FileCrypt richiede un'interazione**. Se la sessione è già verificata o il CNL valido diventa disponibile senza una challenge interattiva, LinkBridge prosegue automaticamente, senza clic aggiuntivi.
5. Se JDownloader richiede un'autorizzazione, confermala nella sua finestra. Attendi l'esito nel pannello LinkBridge e verifica i link in **LinkGrabber**.

Non premere il pulsante CNL di FileCrypt mentre LinkBridge sta già inviando. LinkBridge impedisce invii concorrenti dello stesso tentativo e non effettua reinvii automatici dopo un errore o un timeout.

### Metodi disponibili

Il CNL ha la priorità. LinkBridge attende il caricamento e la stabilizzazione della pagina prima di classificare l'assenza di un metodo; un CAPTCHA ancora in attesa mantiene distinta la richiesta di verifica. Continua a osservare la pagina anche per rilevare CNL generato in ritardo.

Se il CNL non è disponibile, possono essere inoltrati soltanto URL finali MEGA/Pixeldrain riconosciuti e già presenti negli elementi della lista del container. LinkBridge non effettua richieste a questi URL per scoprirne la destinazione. Le sole righe con il nome dell'hoster e un collegamento `/Link/` non sono URL finali utilizzabili.

Quando il CNL è riconoscibile ma i dati non sono estraibili, il pannello può offrire **Usa Click'n'Load FileCrypt una volta**. È un'alternativa manuale monouso, non un secondo invio automatico. Un riferimento DLC viene segnalato, ma **l'importazione DLC automatica non è implementata**.

LinkBridge non segue `/Link/`, `/Go/` o catene pubblicitarie per risolvere i link. Il precedente resolver generico, la modalità classica di risoluzione e il fallback automatico negli appunti non sono disponibili nella 1.1.16. Non aggira CAPTCHA, autenticazione o protezioni Cloudflare.

### Chiusura automatica

**Chiudi automaticamente dopo l'invio** è attiva per impostazione predefinita e può essere disattivata nel popup dell'estensione.

Dopo una trasmissione CNL locale completata con risposta compatibile e senza errori rilevati, la finestra Clean Mode del tentativo può chiudersi dopo circa **2,5 secondi**. Il pannello distingue **Trasmissione CNL completata** da **Importazione in LinkGrabber non verificata**. JDownloader può continuare a elaborare i link dopo la chiusura: controlla LinkGrabber per verificare il risultato effettivo.

Il solo trascorrere del tempo non provoca la chiusura. La finestra resta aperta durante CAPTCHA o autorizzazione JDownloader pendente, oppure in caso di JDownloader irraggiungibile, errore, timeout, risposta non riconosciuta o metodo non supportato. Anche il semplice clic nativo e il fallback degli URL diretti mantengono aperta la finestra, perché non forniscono la ricevuta CNL osservata richiesta dalla chiusura automatica. Non vengono chiuse altre finestre Chrome.

### Stati diagnostici

| Messaggio | Significato e azione |
|---|---|
| Caricamento FileCrypt... / Verifica in corso... | La pagina o la verifica non sono ancora pronte. Attendi; l'assenza di CNL non viene conclusa sulla prima scansione. |
| CAPTCHA richiesto | Completa il controllo originale del sito, se richiesto. Un semplice clic non prova che sia superato. |
| CNL rilevato / Invio a JDownloader... | È in corso il percorso CNL. Se JDownloader chiede autorizzazione, confermala nella sua finestra. |
| JDownloader raggiungibile | L'interfaccia locale ha risposto al controllo; questo stato da solo non conferma l'invio o l'importazione. |
| Trasmissione CNL completata | Il trasferimento locale si è concluso senza errori osservati. L'importazione rimane da verificare in LinkGrabber. |
| Link inviati a JDownloader - verifica LinkGrabber | Controlla LinkGrabber e leggi il dettaglio: l'esito potrebbe essere ambiguo. Nessun reinvio automatico. |
| JDownloader non raggiungibile | Verifica che JDownloader sia aperto, che l'interfaccia locale sulla porta 9666 sia disponibile e che Chrome disponga dei permessi richiesti. |
| DLC rilevato: importazione automatica non ancora implementata | Il DLC è riconoscibile, ma questa versione non lo importa. |
| Questo container non espone un metodo di importazione automatica supportato. | Dopo l'osservazione non è disponibile un percorso utilizzabile. La finestra resta aperta; se compare successivamente un CNL valido, LinkBridge può riprendere automaticamente. |
| Errore | Leggi il dettaglio diagnostico. Non vengono avviati metodi alternativi per inseguire pubblicità. |

Il **Log diagnostico locale** nel popup e il log del pannello Clean Mode mostrano stati, motivi codificati e conteggi. Sono conservati al massimo 200 eventi, senza URL completi, payload CNL, chiavi, password o token CAPTCHA nei nuovi record. Nel popup trovi anche l'esito dell'ultimo tentativo. La lingua dell'interfaccia segue Chrome: italiano o inglese, con inglese come lingua di riserva.

### Importazione manuale e nuovi tentativi

Se hai già ottenuto legittimamente URL finali nel browser:

1. Chiudi manualmente tutte le finestre LinkBridge di quel tentativo, per evitare un invio CNL tardivo mentre procedi a mano.
2. Incolla gli URL direttamente in **JDownloader → Aggiungi collegamenti**.
3. Verifica LinkGrabber.

Questa procedura non avvia risoluzioni o navigazioni pubblicitarie con LinkBridge e non richiede che l'estensione legga gli appunti. Non usare come URL finali i semplici riferimenti agli hoster o i collegamenti intermedi di FileCrypt.

Prima di un nuovo tentativo automatico, chiudi le finestre del tentativo precedente e verifica LinkGrabber: una richiesta terminata con timeout potrebbe comunque essere arrivata a JDownloader.

### Privacy e assistenza

Clean Mode ferma le navigazioni esterne della propria scheda su una pagina interna; non promette di bloccare ogni pubblicità o finestra generata dal sito. FileCrypt, i provider CAPTCHA e JDownloader mantengono il proprio comportamento e le proprie informative.

LinkBridge non usa server dello sviluppatore per ricevere i link. I dati necessari alla consegna vengono trasferiti a JDownloader locale. Preferenze e diagnostica sono locali; i dati di sessione includono l'URL del container. Un aggiornamento può conservare dati di versioni precedenti. Consulta l'[informativa completa](privacy.html#it).

Assistenza: [linkbridge@assistenza88.it](mailto:linkbridge@assistenza88.it). LinkBridge è indipendente da FileCrypt, JDownloader e dagli hoster. Usalo soltanto con servizi e contenuti ai quali sei autorizzato ad accedere.

---

<a id="en"></a>

## English — version 1.1.16

Updated November 2, 2026.

LinkBridge transfers compatible FileCrypt containers to JDownloader on your computer. Its primary route uses the container's **native Click'n'Load (CNL)**. The original page and any CAPTCHA remain visible in the dedicated **Clean Mode** window.

### Getting started

1. Run JDownloader on the same computer as Chrome.
2. Right-click a FileCrypt link, a FileCrypt URL selected as text, or the container page and choose **Open with LinkBridge**. Alternatively, open the extension popup, paste the container URL and select **Open with LinkBridge**.
3. If Chrome requests optional HTTP/HTTPS access, allow it to continue. It supports communication with local JDownloader and stopping external navigation in the Clean Mode tab at an internal page.
4. Complete the CAPTCHA manually **only if FileCrypt requires interaction**. If the session is already verified or valid CNL becomes available without an interactive challenge, LinkBridge continues automatically without an extra click.
5. If JDownloader requests authorization, approve it in its own window. Wait for the result in the LinkBridge panel and check **LinkGrabber**.

Do not click FileCrypt's CNL button while LinkBridge is already sending. LinkBridge prevents concurrent sends for the same attempt and does not automatically resend after an error or timeout.

### Available methods

CNL takes priority. LinkBridge waits for the page to load and stabilize before classifying the absence of a method; a pending CAPTCHA remains a separate verification state. It continues monitoring for CNL generated later by the page.

Without CNL, only recognized final MEGA/Pixeldrain URLs already present in the container's file-list elements may be forwarded. LinkBridge does not request these URLs to discover their destinations. Rows that contain only a hoster name and a `/Link/` reference do not expose usable final URLs.

When CNL is recognizable but its data cannot be extracted, the panel may offer **Use FileCrypt Click'n'Load once**. This is a one-use manual alternative, not a second automatic send. A DLC reference is reported, but **automatic DLC import is not implemented**.

LinkBridge does not follow `/Link/`, `/Go/` or advertising chains to resolve links. The previous generic resolver, classic resolution mode and automatic clipboard fallback are unavailable in 1.1.16. It does not bypass CAPTCHAs, authentication or Cloudflare protections.

### Automatic closing

**Automatically close after sending** is enabled by default and can be disabled in the extension popup.

After local CNL transmission completes with a compatible response and no detected errors, the attempt's Clean Mode window may close after approximately **2.5 seconds**. The panel distinguishes **CNL transmission complete** from **Import into LinkGrabber is not verified**. JDownloader may continue processing after the window closes: check LinkGrabber for the actual result.

Elapsed time alone does not trigger closing. The window stays open while a CAPTCHA or JDownloader authorization is pending, or when JDownloader is unreachable, an error or timeout occurs, a response is unrecognized, or the method is unsupported. A native-button click and the direct-URL fallback also keep the window open because they do not provide the observed CNL receipt required for automatic closing. Other Chrome windows are not closed.

### Diagnostic states

| Message | Meaning and action |
|---|---|
| Loading FileCrypt... / Verification in progress... | The page or verification is not ready. Wait; CNL is not classified as unavailable on the first scan. |
| CAPTCHA required | Complete the original website check if requested. A click alone does not prove completion. |
| CNL detected / Sending to JDownloader... | The CNL route is active. Approve any authorization request in JDownloader's own window. |
| JDownloader reachable | The local interface responded to the availability check; this alone does not confirm transmission or import. |
| CNL transmission complete | Local transfer completed without observed errors. Check LinkGrabber to verify import. |
| Links sent to JDownloader - check LinkGrabber | Check LinkGrabber and read the details: the outcome may be ambiguous. No automatic resend occurs. |
| JDownloader unreachable | Check that JDownloader is running, its local interface on port 9666 is available and Chrome has the requested permissions. |
| DLC detected: automatic import is not yet implemented | A DLC reference is recognizable, but this version does not import it. |
| This container does not expose a supported automatic import method. | No usable route was available after observation. The window stays open; if valid CNL appears later, LinkBridge may resume automatically. |
| Error | Read the diagnostic details. Alternative methods are not started to follow advertising redirects. |

The **Local diagnostic log** in the popup and the Clean Mode panel log display states, coded reasons and counts. Up to 200 events are retained, with no full URLs, CNL payloads, keys, passwords or CAPTCHA tokens in new records. The popup also shows the last attempt's outcome. The interface follows Chrome's language: Italian or English, with English as the fallback.

### Manual import and new attempts

If you have already obtained final URLs legitimately in your browser:

1. Manually close all LinkBridge windows for that attempt to avoid a late CNL send while you import manually.
2. Paste the URLs directly into **JDownloader → Add Links**.
3. Check LinkGrabber.

This procedure does not start resolution or advertising navigation through LinkBridge and does not require the extension to read your clipboard. Hoster references or intermediate FileCrypt links are not final URLs.

Before starting a new automatic attempt, close the previous attempt's windows and check LinkGrabber: a timed-out request may still have reached JDownloader.

### Privacy and support

Clean Mode stops external navigation in its own tab at an internal page; it does not promise to block every advertisement or site-generated window. FileCrypt, CAPTCHA providers and JDownloader retain their own behavior and privacy policies.

LinkBridge does not use developer-operated servers to receive links. Data needed for delivery is sent to local JDownloader. Preferences and diagnostics remain local; session data includes the container URL. Updating may retain data from older versions. Read the [full privacy policy](privacy.html#en).

Support: [linkbridge@assistenza88.it](mailto:linkbridge@assistenza88.it). LinkBridge is independent of FileCrypt, JDownloader and hosting providers. Use it only with services and content you are authorized to access.
