# Stile Inventa

Lo stile della webapp **Inventa** (hub di strumenti: atlante, suoni, sprite, ecc.). Si usa **solo se l'utente lo conferma** per quella webapp (vedi `CLAUDE.md`, sezione 5).

Fonte: `shared.css` e `fonts/` del repo `Inventa`. I valori sono copiati da lì, non stimati. `shared.css` è condiviso da hub e strumenti: alcune pagine possono aggiungere regole proprie, che qui non sono state censite.

## L'idea
Scuro, notturno, con un accento **ciano luminoso**: vetro smerigliato, bordi sottili, bagliori. Bottoni a pillola, testi in maiuscolo con spaziatura larga.

## Colori (variabili in `:root`)
| Variabile | Valore | Uso |
|---|---|---|
| `--bg` | `#03040a` | sfondo |
| `--ink` | `#e9efff` | testo |
| `--dim` | `#8f9bbd` | testo secondario |
| `--ac` | `#35d0ff` | accento ciano |
| `--glass` | `rgba(14,18,36,.62)` | pannelli di vetro |
| `--line` | `rgba(255,255,255,.12)` | bordi |

## Font (inclusi nel repo, self-hosted)
- **Unbounded** (titoli, bottoni, marchio), pesi 300, 600, 900.
- **Space Grotesk** (testo), peso 300 + fallback di sistema.
- **Press Start 2P** (pixel, usato per sprite/giochi).
- Licenza in `fonts/LICENSE.txt`. I file `.woff2` si copiano dal repo `Inventa`, cartella `fonts/`.
- Nota: `index.html` di Inventa carica anche Google Fonts dal CDN; nelle nuove webapp usare solo i file locali.

## Componenti
- **Pillola** (`.pill`): fondo vetro con sfocatura, bordo sottile, angoli completamente tondi, testo 12px maiuscolo con spaziatura; al passaggio il bordo diventa ciano con bagliore e sale di 1px.
- **Bottone** (`.btn`): fondo ciano, testo scuro, Unbounded 12px maiuscolo con spaziatura larga, angoli tondi, ombra luminosa; alla pressione si rimpicciolisce (`scale(.97)`). Variante `.btn.ghost`: trasparente con bordo.
- **Marchio** (`.brand`): Unbounded 900, spaziatura molto larga, con un puntino ciano che pulsa.
- **Barra in alto** (`.top`): fissa, sfumata dal scuro al trasparente, rispetta le zone sicure del telefono (`env(safe-area-inset-top)`).
- **Notifica** (`#toast`): pillola scura con bordo ciano, scende dall'alto e svanisce.
- Interazioni lente e morbide (transizioni 0.25-0.45s).

## Tema chiaro
Inventa è solo scuro. Se la webapp deve avere l'interruttore chiaro/scuro (`CLAUDE.md`), il tema chiaro va proposto da zero e fatto approvare. Non decidere da soli.
