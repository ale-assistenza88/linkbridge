---
layout: default
title: LinkBridge - User Guide
---

# LinkBridge – Guida rapida

LinkBridge semplifica la gestione dei container FileCrypt supportati e l'invio dei link risolti al download manager.

## Modalità rapida

1. Seleziona l'URL di un container FileCrypt in una pagina web.
2. Fai clic con il tasto destro sulla selezione.
3. Scegli **Apri con LinkBridge**.
4. LinkBridge apre il container in **Modalità pulita**.
5. Completa manualmente l'eventuale CAPTCHA.
6. LinkBridge rileva e risolve automaticamente i link.
7. Se JDownloader è disponibile, i link vengono inviati direttamente al LinkGrabber tramite l'interfaccia locale Click'n'Load.

Al primo utilizzo JDownloader può chiedere di autorizzare LinkBridge. Seleziona **Permetti**. Normalmente l'autorizzazione viene ricordata per gli utilizzi successivi.

## Modalità dal popup

Puoi anche:

1. Aprire LinkBridge dalla barra delle estensioni.
2. Incollare l'URL di un container FileCrypt.
3. Avviare la Modalità pulita.
4. Completare manualmente il CAPTCHA.

Il resto del processo è automatico.

## Modalità classica

Rimane disponibile anche il funzionamento originale:

1. Apri normalmente il container FileCrypt.
2. Completa manualmente il CAPTCHA.
3. Apri LinkBridge.
4. Risolvi i link rilevati.

## Modalità pulita

La Modalità pulita cerca di ridurre le navigazioni non necessarie durante il processo.

Se il container tenta di spostare la finestra temporanea verso una pagina pubblicitaria non correlata, LinkBridge può intercettare il passaggio e riportare la finestra al container.

Il CAPTCHA resta sempre manuale e non viene aggirato o risolto automaticamente.

## JDownloader

Quando JDownloader è in esecuzione, LinkBridge prova a inviare direttamente i link risolti alla sua interfaccia locale Click'n'Load.

Se l'invio diretto non è disponibile, LinkBridge può utilizzare gli appunti come metodo alternativo.

## Problemi comuni

### JDownloader non riceve i link

Verifica che:

- JDownloader sia aperto;
- il LinkGrabber sia attivo;
- alla prima richiesta Click'n'Load sia stato selezionato **Permetti**.

### Compare brevemente una finestra vuota

Alcuni container possono aprire finestre temporanee durante il CAPTCHA o il flusso pubblicitario. LinkBridge tenta di chiuderle immediatamente e di mantenere in primo piano la finestra del CAPTCHA.

### I link non vengono rilevati

Prova nuovamente il container oppure utilizza la Modalità classica come fallback.

## Privacy

LinkBridge elabora i link localmente nel browser e non invia i link risolti a un server LinkBridge.

[Privacy Policy](privacy.html)

## Contatti

Per assistenza:

**linkbridge@assistenza88.it**

---

# LinkBridge – Quick Guide

LinkBridge simplifies the handling of supported FileCrypt containers and the delivery of resolved links to your download manager.

## Quick Mode

1. Select a FileCrypt container URL on a web page.
2. Right-click the selected URL.
3. Choose **Open with LinkBridge**.
4. LinkBridge opens the container in **Clean Mode**.
5. Complete any required CAPTCHA manually.
6. LinkBridge automatically detects and resolves the links.
7. When JDownloader is available, the resolved URLs are sent directly to its local Click'n'Load interface.

The first time this is used, JDownloader may ask you to authorize LinkBridge. Choose **Allow**. This permission is normally remembered for subsequent uses.

## Popup Mode

You can also open LinkBridge from the browser toolbar, paste a supported container URL and start Clean Mode from the popup.

## Classic Mode

The original workflow is still available: open the container normally, complete the CAPTCHA manually and use LinkBridge to resolve the detected links.

## Clean Mode

Clean Mode reduces unnecessary navigation around the container page.

If the temporary container window is redirected to an unrelated advertising page, LinkBridge may intercept the navigation and return the window to the container flow.

CAPTCHAs are always completed manually and are never bypassed or solved automatically.

## JDownloader

When JDownloader is running, LinkBridge attempts to send resolved links directly to its local Click'n'Load interface.

If direct delivery is unavailable, clipboard copy can be used as a fallback.

## Privacy

LinkBridge processes links locally in the browser and does not send resolved links to a LinkBridge-operated server.

[Privacy Policy](privacy.html)

## Support

**linkbridge@assistenza88.it**
