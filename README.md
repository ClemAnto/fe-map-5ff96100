# Pagina di stato — hosting

Questo repository esiste per una cosa sola: servire `index.html` su GitHub Pages, così che il documento
abbia un indirizzo stabile apribile senza login.

**Non si modifica niente qui a mano.** `index.html` è generato, e ogni modifica fatta a mano sparisce
alla rigenerazione successiva. Il generatore, le fonti che legge e il perché stanno nel progetto, in
`tools/status/`.

Aggiornare, dalla radice del progetto:

```bash
node tools/status/build-status.mjs      # rigenera index.html dalle fonti
cd docs/status && git add -A && git commit -m "update" && git push
```

La pagina dichiara `noindex, nofollow` e il `robots.txt` qui accanto vieta la scansione: si apre a chi
ha il link, non si trova cercando.
