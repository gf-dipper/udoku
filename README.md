# Udoku weboldal

Statikus oldal, szerver nélkül. Bármilyen ingyenes statikus tárhelyre feltehető (Cloudflare Pages, GitHub Pages).

## Felépítés
- `index.html` – a könyvtár (főoldal): kiemelt sorozat, új fejezetek, összes sorozat.
- `catalog.json` – a sorozatok listája. Új sorozat = új bejegyzés + új mappa.
- `<sorozat>/index.html` – a sorozat saját oldala.
- `<sorozat>/read.html` – az olvasó (`read.html#ch=chapter2.json`).
- `<sorozat>/chapters.json` – a fejezetek listája (szám, fájl, esőnap, bélyegkép, megjelenés).
- `<sorozat>/chapterN.json` + `img/` – a fejezetek adatai és képei.

## Új fejezet
1. A fejezet JSON-ja és képei a sorozat mappájába (`chapter3.json`, `img/f03_*.webp`).
2. Az előző fejezet JSON-jába `next`, az újba `prev` link.
3. `chapters.json`: új sor a `chapters` listába, a `next` mező a következőre.
4. Feltöltés (újra az egész mappát).

Az olvasási helyet a böngésző tárolja (`prog:<mappa>` kulcs), szerverre semmi nem megy.
