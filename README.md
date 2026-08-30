# Pagina di stato — hosting

Questo repository esiste per una cosa sola: servire su GitHub Pages, con un indirizzo stabile apribile
senza login, le **due pagine generate** del front-end.

| Pagina | Cos'è | Generatore |
|---|---|---|
| `index.html` | la **mappa del front-end** per lo staff: una riga per schermata, tutte e 85 | `tools/status/` |
| `requirements.html` | la **checklist dei requisiti**: il documento dei requisiti voce per voce, col wireframe accanto alla schermata di oggi (accesso e backoffice) | `tools/todo/` |

**Non si modifica niente qui a mano.** Le due pagine sono generate, e ogni modifica fatta a mano sparisce
alla rigenerazione successiva. I generatori, le fonti che leggono e il perché stanno nel progetto.

Aggiornare, dalla radice del progetto:

```bash
node tools/status/build-status.mjs      # rigenera index.html dalle fonti
node tools/todo/build-todo.mjs          # rigenera requirements.html
cd docs/status && git add -A && git commit -m "update" && git push
```

Entrambe dichiarano `noindex, nofollow` e il `robots.txt` qui accanto vieta la scansione di tutto il
sito: si aprono a chi ha il link, non si trovano cercando.
