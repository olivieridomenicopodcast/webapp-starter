# [Nome della webapp]: istruzioni permanenti

> Modello di partenza. Quando crei una webapp da questo repo, compila le sezioni tra parentesi quadre
> (1, 2, 7, 8) e lascia il resto. Il repo può essere pubblico: qui dentro non scrivere mai token, chiavi o dati di persone.

## 1. Cos'è
[Cosa fa la webapp, per chi, dove gira (es. telefono, PWA installata). Chi decide e chi rivede le modifiche.]

## 2. Utenti e dati
[Chi la usa. Dove stanno i dati: di norma `localStorage` sul dispositivo + sincronizzazione su un GitHub Gist privato con pull/push manuali.]

## 3. Come lavoriamo
- Chi scrive le richieste non è uno sviluppatore di mestiere: spiega le scelte tecniche in parole semplici e segnala i rischi prima di agire, non dopo.
- **Chiedi prima.** Se per fare una cosa devi scegliere tu, o non sei sicuro, chiedi prima di agire.
- **Non decidere di tua iniziativa.** Una modifica per richiesta. Non toccare, aggiungere, togliere o «migliorare» quello che non è stato chiesto. Se ti sembra che qualcosa vada lasciato fuori o cambiato, proponilo e aspetta la risposta: non farlo da solo.
- **Copiare significa copiare.** Se ti viene chiesto di clonare o portare qualcosa da un progetto a un altro, riporta tutto per filo e per segno, cambiando solo quello che è stato indicato (nomi, riferimenti). Se pensi che qualcosa non vada portato, chiedi prima.
- **Niente supposizioni spacciate per fatti.** Prima di affermare qualcosa, cerca una fonte o una conferma (il codice, i file, la documentazione, il sito). Se non la trovi, dillo chiaramente: «non l'ho verificato, è una mia supposizione».
- Se la richiesta è ambigua, chiedi. Se la cosa esiste già, dillo invece di rifarla.
- Prima di cambiare il formato dei dati salvati o la sincronizzazione: proponi un piano e aspetta l'ok. Niente codice prima.
- Spiegazioni di livello medio: cosa hai fatto e perché in poche righe, senza tutto il dettaglio tecnico, ma senza nascondere le scelte.
- A fine lavoro usa la skill `chiudere-una-modifica`.
- Non dichiarare risolto ciò che non hai verificato. Se non puoi verificare, dillo.
- **Commit e push li fai tu**, a fine di ogni modifica: un commit per modifica, con un messaggio chiaro in italiano, sul ramo di lavoro indicato dalla sessione. Mai riscrivere la cronologia (niente force push, rebase o amend su commit già inviati): ogni modifica deve potersi annullare con `git revert`.
- Non creare pull request e non pubblicare il sito se non è richiesto esplicitamente.

## 4. Stack di default
- HTML + CSS + JavaScript puro, senza build, senza framework, salvo diversa indicazione in questo file.
- **Sempre PWA**, installabile su telefono e PC: `manifest.json` + `sw.js` + icone. A ogni modifica ai file in cache, aumenta la versione della cache in `sw.js`.
- Si usa soprattutto da telefono, ma deve funzionare bene anche da PC: progetta per il telefono e controlla anche lo schermo largo.
- Pubblicazione: non è deciso dove. Non scegliere un servizio da solo: chiedi quando serve. Alcune app potrebbero essere fatte per altre persone.
- Un solo `index.html`, un `style.css`, un `app.js`. Se `app.js` supera ~600 righe, proponi di dividerlo.
- Sincronizzazione con Gist: segui la skill `sync-gist`.

## 5. Lingua, tono e design
- Interfaccia in italiano, dando del tu, maiuscola solo a inizio frase.
- Tono dei testi: **amichevole e ironico**, con qualche freddura quando ci sta, ma mai a scapito della chiarezza di un'etichetta o di un errore.
- **Niente emoji** nell'interfaccia: per le icone usa SVG.
- Codice, nomi di file e variabili in inglese.
- Mobile prima di tutto (controlla a 360px), poi anche schermo largo da PC. Una sola azione principale per schermata.
- **Tema scuro di default, tema chiaro disponibile**, con un interruttore visibile. La scelta si salva in `localStorage`. Alla prima apertura vale lo scuro, non la preferenza del sistema.
- Contrasto almeno AA in entrambi i temi (controllalo, soprattutto il viola scuro su sfondo scuro), bersagli tocco di almeno 44px.

### Font
- **Libre Baskerville** come font di default. Incluso nei file dell'app (self-hosted, con licenza OFL) e non caricato da CDN, così funziona anche offline come PWA.

### Colori del brand (variabili CSS in `:root`, mai valori scritti a mano sparsi nel codice)
| Ruolo | Colore |
|---|---|
| Principale | `#32187b` |
| Arancione | `#ff893a`, con sfumature `#ffad4e` e `#ffbd59` |
| Viola | `#b289fa` e `#724eb9` |

- I colori neutri (sfondi, testi, bordi) e lo stile generale (card, pulsanti, ombre) si prendono da **olivieridomenico.it**. Finché non sono stati verificati sul sito, non inventarli: chiedi.
- Se un colore del brand non passa il contrasto AA su un fondo, non cambiarlo di nascosto: proponi l'alternativa.

## 6. Sicurezza: regole non negoziabili
- Il repo può essere pubblico: mai token, chiavi o password nel codice, nei commit, negli esempi o nei log.
- Il token GitHub dell'utente vive solo in `localStorage` del suo dispositivo, inserito a mano dalle impostazioni dell'app.
- Il testo scritto dall'utente non entra mai in `innerHTML` senza escape: usa `textContent` o la funzione `esc()`.
- Nessuno script esterno caricato da CDN senza versione fissata.
- Mai cancellazioni di massa dei dati dell'utente senza conferma esplicita nell'interfaccia.

## Autore
Dev by Domenico "Niky" Olivieri in Vibe Coding.

## 7. Decisioni già prese: non rimetterle in discussione
[Le scelte fatte una volta per tutte, es. «Nessun login», «Un solo calendario».]

## 8. Fuori dal perimetro
[Cosa la webapp non fa e dove si fa.]
