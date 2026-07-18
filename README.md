# Cześć, Przyniosłem Tobie Kwiaty — Box (strona prezentacyjna)

Jednostronicowa strona w formie prowadzonej sekwencji "slajdów" (ekran ładowania →
logo → dedykacja → "otwórz box" → zawartość zestawu → okładka i tracklista),
nawigowana przyciskami Wstecz / Dalej, z finalnym przekierowaniem do odtwarzacza:
https://bvdvm.github.io/badamify/

## Struktura

```
.
├── index.html
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

Brak zależności, brak build stepu — czysty HTML/CSS/JS. Jedyne zasoby zewnętrzne to
fonty z Google Fonts (Inter, JetBrains Mono).

## Kolejność slajdów (w `index.html`, sekcje `.slide`)

1. Logo + slogan
2. Dedykacja (stylizowana jako list)
3. "TERAZ OTWÓRZ BOX"
4. Zawartość zestawu z opisami
5. Okładka + tracklista (bez czasów trwania) — tu przycisk zmienia się na „Słuchaj teraz"

Nawigacja Wstecz/Dalej to stały pasek na dole ekranu (`.controls`), widoczny na
każdym slajdzie. Kliknięcie w małe logo w lewym górnym rogu wraca na slajd 1.

## Wrzucenie na GitHub Pages

```bash
cd package
git init
git add .
git commit -m "Strona prezentacyjna — Cześć, Przyniosłem Tobie Kwiaty"
git branch -M main
git remote add origin https://github.com/bvdvm/kwiaty-box.git
git push -u origin main
```

Potem: **Settings → Pages → Branch: main / (root)**. Strona pojawi się pod
`https://bvdvm.github.io/kwiaty-box/` (lub jako podfolder w repo `badamify`, jeśli
wolisz trzymać ją razem z odtwarzaczem).

## Co ewentualnie podmienić

- Link do odtwarzacza (`https://bvdvm.github.io/badamify/`) — szukaj
  `href="https://bvdvm.github.io/badamify/"`.
- Treść każdego slajdu jest w osobnej sekcji `<section class="slide" data-slide="N">`
  w `index.html` — edytuj bezpośrednio w znacznikach.
- Kolejność/liczbę slajdów można zmienić dodając/usuwając sekcje `.slide` — reszta
  (licznik kroków, stan przycisku Wstecz, zamiana Dalej→Słuchaj teraz na ostatnim
  slajdzie) liczy się automatycznie w skrypcie na dole pliku.
