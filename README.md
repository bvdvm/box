# Cześć, Przyniosłem Tobie Kwiaty — Box (strona prezentacyjna)

Statyczna strona prezentująca dedykację i tracklistę albumu na stronie głównej, z
osobną (nie eksponowaną od razu) podstroną z zawartością boxu (2× tee, brelok NFC,
puzzle, magnes), oraz przekierowaniem do odtwarzacza:
https://bvdvm.github.io/badamify/

## Struktura

```
.
├── index.html      ← strona główna: logo, dedykacja, okładka + tracklista
├── box.html        ← podstrona: zawartość zestawu (link w nawigacji "Zestaw")
└── assets/
    └── img/
        ├── logo-pink.webp
        ├── logo-black.webp
        ├── cover.webp
        ├── tee-gift.webp
        ├── tee-flowers.webp
        ├── keychain.webp
        ├── puzzle.webp
        └── magnet.webp
```

`box.html` nie jest linkowany na pierwszy rzut oka ze strony głównej — dostęp do niego
jest tylko przez link „Zestaw" w górnym menu, żeby zawartość zestawu nie była
pierwszą rzeczą, jaką widać po wejściu na stronę.

Brak zależności, brak build stepu — to czysty HTML/CSS/JS. Jedyne zasoby zewnętrzne to
fonty z Google Fonts (Inter, JetBrains Mono), wczytywane przez `<link>` w `<head>`.

## Wrzucenie na GitHub Pages

**Opcja A — nowe, osobne repo (np. `kwiaty-box`):**

```bash
cd package
git init
git add .
git commit -m "Strona prezentacyjna boxu — Cześć, Przyniosłem Tobie Kwiaty"
git branch -M main
git remote add origin https://github.com/bvdvm/kwiaty-box.git
git push -u origin main
```

Potem w ustawieniach repo: **Settings → Pages → Branch: main / (root)** i zapisz.
Strona pojawi się pod `https://bvdvm.github.io/kwiaty-box/`.

**Opcja B — jako podfolder w istniejącym repo `badamify`:**

Skopiuj zawartość tego folderu (`index.html` + `assets/`) do np. `badamify/box/`
w swoim repo i wypchnij zmiany — strona będzie dostępna pod
`https://bvdvm.github.io/badamify/box/`.

## Co ewentualnie podmienić

- Link do odtwarzacza (`https://bvdvm.github.io/badamify/`) występuje w obu plikach
  — szukaj `href="https://bvdvm.github.io/badamify/"`.
- Dedykacja i tracklista są w `index.html` (sekcje `.hero-dedication` i `#utwory`).
- Zawartość zestawu i opisy produktów są w `box.html` (sekcje `#zestaw` i `#szczegoly`)
  — edytuj tekst bezpośrednio w znacznikach.
- Obrazki w `assets/img/` to skompresowane .webp (autocrop + downscale z oryginałów)
  — jeśli chcesz podmienić którykolwiek produkt, zachowaj tę samą nazwę pliku albo
  zaktualizuj odpowiedni atrybut `src`.
