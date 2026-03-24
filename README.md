# Portfolio Akademickie — GitHub Pages

## Struktura plików

```
portfolio/
│
├── index.html          ← główna strona
├── styles.css          ← wszystkie style (motywy, layout)
├── script.js           ← przełącznik motywu, język, formularz
│
├── images/             ← ← ← TU WRZUCAJ ZDJĘCIA
│   ├── photo.jpg           (zdjęcie profilowe w headerze)
│   ├── gallery-1.jpg       (galeria — pozycja 1)
│   ├── gallery-2.jpg       (galeria — pozycja 2)
│   ├── gallery-3.jpg       (galeria — pozycja 3)
│   └── ...                 (kolejne dodajesz samodzielnie)
│
└── publications.html   ← (opcjonalnie) pełna lista publikacji
```

---

## Jak dodać zdjęcie do galerii

1. Skopiuj plik zdjęcia do folderu `images/`
2. W `index.html` odszukaj sekcję `<!-- ↓ Dodaj kolejne zdjęcia tutaj ↓ -->`
3. Wklej poniższy blok i zmień `gallery-4.jpg` oraz podpis:

```html
<figure class="gallery-item">
  <img src="images/gallery-4.jpg" alt="Opis zdjęcia" loading="lazy"
       onerror="this.parentElement.classList.add('img-missing')" />
  <figcaption data-pl="Podpis po polsku" data-en="Caption in English">
    Podpis po polsku
  </figcaption>
</figure>
```

---

## Jak zmienić dane osobowe

Edytuj `index.html` i zamień:
- `Jan Kowalski` — Twoje imię i nazwisko
- `Doktor habilitowany · Językoznawstwo` — stopień i dziedzina
- `Instytut Filologii Polskiej · Uniwersytet Jagielloński` — afiliacja
- `jan.kowalski@uj.edu.pl` — Twój adres e-mail (2 miejsca: w headerze i w `script.js`)
- Linki do ORCID, Google Scholar, GitHub

---

## Opcje kolorystyczne

Strona oferuje dwa motywy przełączane przyciskiem `◐` w prawym górnym rogu:

| Motyw | Tło | Akcent |
|-------|-----|--------|
| Jasny | Krem `#f5f0e8` | Granat `#1a1a6e` |
| Ciemny | Grafit `#1c1c1f` | Złoto `#c9a84c` |

Wybór jest zapamiętywany w `localStorage`.

---

## Wersje językowe

Strona obsługuje **PL** i **EN**. Każdy tłumaczony element ma atrybuty:
```html
data-pl="tekst po polsku" data-en="text in English"
```

Aby dodać/zmienić tłumaczenie — edytuj oba atrybuty naraz.

---

## Publikowanie na GitHub Pages

1. Utwórz repozytorium `username.github.io` (lub `portfolio`)
2. Wgraj wszystkie pliki
3. W ustawieniach repozytorium → **Pages** → Source: `main` branch, folder `/root`
4. Strona będzie dostępna pod `https://username.github.io`

---

## Formularz kontaktowy

Formularz generuje `mailto:` link — otwiera klienta pocztowego użytkownika.  
Zmień adres odbiorcy w `script.js` (linia z `const recipient = ...`).

Jeśli chcesz obsługę serwerową (np. Formspree), zamień w `script.js`
fragment z `window.location.href = mailto` na `fetch('https://formspree.io/f/TWOJE_ID', ...)`.
