# VivalArc

Przekształć przeglądarkę Vivaldi w elegancki interfejs w stylu Arc — idealna alternatywa dla Arc Browser.

**Aktualna wersja**: v2.0.0 | **Wspierane Vivaldi**: v8.0+ | **Platformy**: macOS, Windows, Linux

## 🚀 Szybki start

### 1. Sklonuj repozytorium
```bash
git clone https://github.com/tovifun/VivalArc.git
```

### 2. Wybierz wersję

#### ✨ Wersja główna (aktywnie utrzymywana)
W ustawieniach Vivaldi wskaż katalog: `VivalArc/`

To jedyna wersja, która otrzymuje poprawki i nowe funkcje.

**Wbudowane funkcje opcjonalne** — edytuj `vivalarc.css` i ustaw w bloku `:root`:
- `--enable-autohide-tabbar: 1` — pasek kart zwija się do szerokości ikon i rozwija po najechaniu

**Tokeny konfiguracyjne** (wszystkie w bloku `:root`): `--window-border`, `--window-button-opacity`, `--webview-shadow-light` / `--webview-shadow-dark`, `--transition-duration` / `--transition-easing`, `--urlbar-focus-ring`

#### 📦 Wersje archiwalne (wsparcie starszych Vivaldi)
- **Vivaldi 7.7**: `VivalArc/archive/v7.7/` (warianty autotab i compact)
- **Vivaldi 6.9**: `VivalArc/archive/v6.9/default/`
- **Vivaldi 7.0**: `VivalArc/archive/v7.0/default/`
- **Vivaldi 7.4**: `VivalArc/archive/v7.4/default/`

Szczegółowe kroki konfiguracji: [📝Przewodnik startowy](./docs/installation/getting-started-pl.md)

## ✅ Zalecana konfiguracja w Vivaldi 7.8+

Od Vivaldi 7.8 dostępny jest niestandardowy pasek kart (ang. *Custom Tab Bar*), więc moja obecna ulubiona konfiguracja to:

- pasek adresu u góry bocznego paska kart,
- przyciski wstecz/dalej poniżej,
- rozszerzenia przeniesione do prawego panelu,
- górny pasek adresu ukryty.

To rozwiązanie jest czystsze i wygodniejsze niż wymuszanie każdego elementu w starym układzie samym CSS-em.

![Zalecana konfiguracja](./screenshots/screenshot_v1.3.0.png)

## 📚 Dokumentacja

### Pierwsze kroki
- [📝Przewodnik konfiguracji](./docs/installation/getting-started-pl.md)
- [📁Notatki o starszych wariantach](./docs/guides/variants-guide-pl.md)
- [📄Historia projektu](./docs/about/behind-the-scene-pl.md)

### Przewodniki
- [🖼️Polecane motywy Vivaldi](./docs/reference/curated-themes-pl.md)
- [🎨Używanie lokalnych motywów Vivaldi](./docs/guides/using-local-vivaldi-theme-pl.md)

### Materiały
- [🧑‍💻FAQ](./docs/reference/faq-pl.md)
- [🎉Lista zmian](./docs/reference/changelog-pl.md)
- [🌐Strona VivalArc](https://arc.tovi.fun)
- [📝English README](./README.md)

## 📂 Struktura projektu

```
VivalArc/
├── vivalarc.css           # Arkusz v2.0 dla Vivaldi 8.0+ (aktywnie utrzymywany)
├── archive/              # Wersje archiwalne
│   ├── v7.7/             # warianty autotab i compact (Vivaldi 7.7)
│   ├── v6.9/
│   ├── v7.0/
│   └── v7.4/
├── themes/               # Paczki motywów Vivaldi
├── assets/               # Zasoby
│   ├── icons/
│   └── wallpapers/
├── docs/                 # Pełna dokumentacja
└── screenshots/          # Zrzuty ekranu projektu
```

---
## 🖥️ Zrzut ekranu VivalArc
 ![Zrzut ekranu](./screenshots/screenshot_v1.3.0.png)

---

## 💌 Podziękowania
- Github [@clementpoiret](https://github.com/clementpoiret) — dodał [motyw ArcDark](https://github.com/tovifun/VivalArc/pull/5)
- Github [@Zettry](https://github.com/Zettry) — rozwiązał wiele [zgłoszeń](https://github.com/tovifun/VivalArc/issues/21)

---

## 🧑‍💻 Piękne zrzuty ekranu od:
- Twitter [@altemo](https://x.com/atlemo/status/1765726601239491014)
- Twitter [@vivaldi_fr](https://twitter.com/vivaldi_fr/status/1684643796942815233)
- Github [@clementpoiret](https://github.com/tovifun/VivalArc/pull/5)
- Bilibili [@tovi(to ja 😉)](https://www.bilibili.com/opus/844070281819455558)
