1. W istocie jest to zmiana wyglądu za pomocą funkcji niestandardowych modyfikacji UI (ang. *custom UI mod*) przeglądarki Vivaldi
2. Ta konfiguracja działa również na Windowsie. Przy ustawianiu skrótów klawiszowych wystarczy zamienić `Command` na `Ctrl`
3. Aby wrócić do oryginalnego wyglądu, wystarczy usunąć lokalny CSS

---

## 🛠️ Kroki konfiguracji:

### 1. Zainstaluj przeglądarkę Vivaldi

- Najpierw zainstaluj przeglądarkę [Vivaldi](https://vivaldi.com) — to oczywiste.

### 2. Otwórz ustawienia Vivaldi

> Podczas konfiguracji możesz wyszukiwać słowa kluczowe w lewym górnym rogu strony „Ustawienia", aby szybko znaleźć właściwą opcję

**Niezbędne**
- **Karty** > Pozycja paska kart > `Po lewej`
- **Pasek adresu** > `Odznacz „Pokaż pasek adresu"`
- **Klawiatura** (ustaw niezbędne skróty klawiszowe)
    - Pasek adresu > `Command + B` (na Windowsie najpierw usuń skrót zakładek)
- **Dodatkowa konfiguracja paska przewijania dla użytkowników Windows**: domyślny pasek przewijania w Windowsie jest dość masywny i mało estetyczny, dlatego warto go poprawić. Jak to zrobić:
  - Wpisz w pasku adresu: `chrome://flags`
  - Wyszukaj `fluent` i włącz opcję w rodzaju `Fluent scrollbars` — pasek przewijania stanie się subtelniejszy.

**Warto mieć**
- **Wygląd** > Pasek stanu > `Nakładka informacji o stanie`
- **Panel** > Opcje panelu > `Zaznacz „Panel pływający"`
- **Szybkie polecenia** > `Zaznacz „Otwieraj linki w nowej karcie"`
- **Szybkie polecenia** > **Łańcuchy poleceń**
    - Dodaj łańcuch poleceń
    - Nazwa łańcucha > `Kopiuj URL do schowka`
    - Polecenie 1 > `Aktywuj pole adresu`
    - Polecenie 2 > `Opóźnienie` z parametrem `300`
    - Polecenie 3 > `Kopiuj`
- **Klawiatura** (ustaw niezbędne skróty klawiszowe)
    - Nowa karta > usuń skrót
    - Szybkie polecenia > `Command + T`
    - Zapisz stronę jako > usuń skrót
    - Pasek kart > `Command + S`
    - Utwórz zakładkę > usuń skrót
    - Przypnij / odepnij kartę > `Command + D`
    - Drukuj > usuń skrót
    - Panel > `Command + P`
    - Łańcuchy > Kopiuj URL do schowka > `Command + Shift + C`

### 3. Niestandardowa modyfikacja UI
- [Pobierz mod](https://github.com/tovifun/VivalArc/archive/refs/heads/main.zip) i wypakuj w bezpieczne miejsce na dysku
- **Motywy > Otwórz motyw** > theme-ArcLight.zip
  - Albo wybierz [motyw polecany przeze mnie ze społeczności Vivaldi](../reference/curated-themes-pl.md)
- Otwórz `vivaldi://experiments` i włącz `"Allow for using CSS modifications"`
- Otwórz Ustawienia > Wygląd > Niestandardowe modyfikacje UI
- Wskaż folder, do którego wypakowano pliki
- Uruchom Vivaldi ponownie

### Vivaldi 8.0 — gotowe układy

Vivaldi 8.0 dodał sześć wbudowanych presetów układu (Ustawienia > Wygląd > Układ). Dla najlepszego efektu VivalArc wybierz **Vertical Left** — odpowiada zalecanej konfiguracji z lewym paskiem kart. Możesz też skonfigurować układ ręcznie, jak opisano w kroku 2 powyżej.

> Jeśli po aktualizacji do Vivaldi 8.0 coś wygląda na zepsute, otwórz `vivaldi://inspect/#apps/`, kliknij **inspect** pod `browser.html` i użyj wybieraka elementów (`Ctrl+Shift+C`), aby sprawdzić, czy identyfikatory takie jak `#header`, `#tabs-tabbar-container` i `#panels-container` nadal odpowiadają selektorom w `vivalarc.css`.
