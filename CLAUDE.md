# [Nome della webapp]: istruzioni permanenti

> Modello di partenza. Quando crei una webapp da questo repo, compila le sezioni tra parentesi quadre
> (1, 2, 7, 8) e lascia il resto. Il repo può essere pubblico: qui dentro non scrivere mai token, chiavi o dati di persone.

## 1. Cos'è
[Cosa fa la webapp, per chi, dove gira (es. telefono, PWA installata). Chi decide e chi rivede le modifiche.]

## 2. Utenti e dati
[Chi la usa. Dove stanno i dati: di norma `localStorage` sul dispositivo + sincronizzazione su un GitHub Gist privato con pull/push manuali.]

## 3. Come lavoriamo
- Chi scrive le richieste non è uno sviluppatore di mestiere: spiega le scelte tecniche in parole semplici e segnala i rischi prima di agire, non dopo.
- Una modifica per richiesta. Non toccare quello che non è stato chiesto.
- Se la richiesta è ambigua, chiedi. Se la cosa esiste già, dillo invece di rifarla.
- Prima di cambiare il formato dei dati salvati o la sincronizzazione: proponi un piano e aspetta l'ok. Niente codice prima.
- A fine lavoro usa la skill `chiudere-una-modifica`.
- Non dichiarare risolto ciò che non hai verificato. Se non puoi verificare, dillo.
- Non creare pull request e non pubblicare se non è richiesto esplicitamente.

## 4. Stack di default
- HTML + CSS + JavaScript puro, senza build, senza framework, salvo diversa indicazione in questo file.
- PWA: `manifest.json` + `sw.js`. A ogni modifica ai file in cache, aumenta la versione della cache in `sw.js`.
- Un solo `index.html`, un `style.css`, un `app.js`. Se `app.js` supera ~600 righe, proponi di dividerlo.
- Sincronizzazione con Gist: segui la skill `sync-gist`.

## 5. Lingua e design
- Interfaccia in italiano, dando del tu, maiuscola solo a inizio frase.
- Codice, nomi di file e variabili in inglese.
- Mobile prima di tutto (controlla a 360px). Una sola azione principale per schermata.
- Colori e caratteri come variabili CSS (`:root`), mai valori scritti a mano sparsi nel codice. Tema chiaro e scuro (`prefers-color-scheme`).
- Contrasto almeno AA, bersagli tocco di almeno 44px.

## 6. Sicurezza: regole non negoziabili
- Il repo può essere pubblico: mai token, chiavi o password nel codice, nei commit, negli esempi o nei log.
- Il token GitHub dell'utente vive solo in `localStorage` del suo dispositivo, inserito a mano dalle impostazioni dell'app.
- Il testo scritto dall'utente non entra mai in `innerHTML` senza escape: usa `textContent` o la funzione `esc()`.
- Nessuno script esterno caricato da CDN senza versione fissata.
- Mai cancellazioni di massa dei dati dell'utente senza conferma esplicita nell'interfaccia.

## 7. Decisioni già prese: non rimetterle in discussione
[Le scelte fatte una volta per tutte, es. «Nessun login», «Un solo calendario».]

## 8. Fuori dal perimetro
[Cosa la webapp non fa e dove si fa.]
