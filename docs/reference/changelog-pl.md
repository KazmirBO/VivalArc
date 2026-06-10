## 🗓️ 2026.06.10 | v2.0.0
Arkusz stylów przepisany od podstaw. Zachowanie selektorów jest celowo identyczne z v1.4.0 — zmieniły się struktura, cienie i animacje.

1. Przepisano z użyciem natywnego zagnieżdżania CSS: wspólne strażniki, takie jak `#browser:not(.tabs-top, .tabs-bottom)`, są teraz deklarowane raz na sekcję zamiast powtarzane przy niemal każdej regule — plik jest czytelniejszy, a silnik stylów dopasowuje selektory taniej.
2. Skonsolidowano zduplikowane reguły przez `:is()`, scalono po dwie sondy `:has()` wykrywające siatki kafelków/mozaiki w jedną oraz usunięto nadmiarową regułę cienia `theme-light` (fallback już ją pokrywał).
3. Nowe wielowarstwowe cienie webview dla jasnego i ciemnego motywu — przylegający cień kontaktowy, miękki cień otoczenia i włosowata krawędź.
4. Żwawsze animacje: krzywa wyhamowująca `cubic-bezier(0.2, 0, 0, 1)` zastępuje zwykłe `ease`, do tego delikatne przejścia hover na przyciskach paska narzędzi i polu adresu (wszystko objęte `prefers-reduced-motion: no-preference`).
5. Nowa obwódka fokusa w kolorze akcentu na polu adresu/wyszukiwania (`--urlbar-focus-ring`), wyprowadzana z aktywnego motywu przez `color-mix()`.
6. Celowo bez `@layer`: reguły w warstwie przegrywałyby w kaskadzie z niewarstwowymi stylami samego Vivaldi.

## 🗓️ 2026.05.21 | v1.4.0
Aktualizacja pod Vivaldi 8.0, który wprowadził przeprojektowany interfejs „Unified frame" i przepisany backend zarządzania kartami.

1. Zaktualizowano zgodność z Vivaldi 8.0.
2. Dodano w arkuszu znaczniki `[v8.0 check]` przy selektorach najbardziej narażonych na zmiany Unified frame — w razie problemów sprawdź DOM na żywo pod `vivaldi://inspect/#apps/`.
3. Scalono funkcję automatycznie chowanego paska kart (pierwotnie osobny wariant `autotab` autorstwa @Zettry) z głównym arkuszem jako opcjonalny przełącznik: ustaw `--enable-autohide-tabbar: 1` w bloku `:root`, aby ją włączyć.
4. Dodano płynne animacje przejścia dla paska kart (`--tabbar-transition`) i kontenera paneli.
5. Dodano zmienną `--window-button-hover-opacity` do konfiguracji nieprzezroczystości przycisków okna przy najechaniu.
6. Przeniesiono stare warianty (`autotab`, `compact`) do `archive/v7.7/` — nie są już utrzymywane jako osobne pliki.

## 🗓️ 2026.03.26 | v1.3.0
Ta aktualizacja celuje w najnowsze wydanie Vivaldi 7.9 i odświeża VivalArc po długiej przerwie.

1. Zaktualizowano zgodność z Vivaldi 7.9.
2. Ponownie uproszczono arkusz i usunięto kolejne niestandardowe nadpisania, dzięki czemu wersja główna jest mniej podatna na przyszłe zmiany UI Vivaldi.
3. Po ponad roku bez aktualizacji uporządkowano w tym wydaniu nagromadzone usterki wizualne.

Dziś większość popularnych przeglądarek, łącznie z Chrome, oferuje wbudowane pionowe karty. Dla mnie przewagą Vivaldi pozostaje poziom personalizacji. Dlatego zamierzam dalej utrzymywać VivalArc, ale przyszłe aktualizacje skupią się bardziej na naprawianiu regresji wizualnych i błędów interfejsu niż na dodawaniu kolejnych gałęzi stylistycznych.

## 🗓️ 2024.11.03 | v1.1.0
Vivaldi niedawno zaktualizował się do wersji 7.0, przynosząc zauważalne zmiany UI — bardziej dopracowane ikony, unowocześniony wygląd i subtelniejsze cienie wybranych kart w pasku bocznym. Bardzo polecam tę aktualizację, bo dzięki niej VivalArc wygląda jeszcze lepiej.

Na szczęście ta duża aktualizacja nie spowodowała żadnych problemów z VivalArc. Przy okazji rozwiązano jednak kilka nagromadzonych zgłoszeń z GitHuba:

1. Widoczność stopki: stopka jest teraz domyślnie widoczna, ale nadal można ją ukryć w ustawieniach. [#28](https://github.com/tovifun/VivalArc/issues/28) @IamMiao
2. Dodano możliwość przeciągania paska adresu w oknach wyskakujących — zasugerował @Zettry. [#30](https://github.com/tovifun/VivalArc/issues/30)
3. Przywrócono pasek przewijania w pasku kart, aby umożliwić zmianę szerokości, choć nieco psuje to estetykę. [#31](https://github.com/tovifun/VivalArc/issues/31)
4. Dodano funkcję automatycznie chowanego paska kart (sugestia @Zettry), wprowadzoną wtedy jako osobny wariant. [#21](https://github.com/tovifun/VivalArc/issues/21) [#29](https://github.com/tovifun/VivalArc/issues/29)

## 🗓️ 2024.08.17 | v1.0.4
### 1. Optymalizacja pod Vivaldi 6.9
Vivaldi Snapshot 6.9 (wersja beta Vivaldi) otrzymał niedawno aktualizację, która wprowadziła drobny problem z VivalArc — na tle paska bocznego pojawiła się dodatkowa półprzezroczysta warstwa #24. Ta aktualizacja przede wszystkim rozwiązuje ten problem.

### 2. Jak używać różnych wersji VivalArc
Niektórzy użytkownicy pytali, jak używać stylu z paskiem tytułu #26. Stworzyłem wtedy kilka wariantów VivalArc dla różnych preferencji. Notatki historyczne: [Notatki o starszych wariantach](../guides/variants-guide-pl.md).

### 3. Motyw Reflect New Tab
Niedawno odkryłem wtyczkę [Reflect New Tab](https://chromewebstore.google.com/detail/reflect-new-tab/jnhdkfampckckkmbanadkkjlcaemdkob) z pięknym gradientowym tłem. Postanowiłem stworzyć [motyw Vivaldi](./curated-themes-pl.md) z tym tłem — efekt okazał się świetny i nadał VivalArc zupełnie nowy wygląd. Mój ulubiony jest różowy; gorąco polecam go wypróbować.

## 🗓️ 2024.06.29 | v1.0.3
1. Ta wersja rozwiązuje głównie drobny problem z aktualizacją Vivaldi 6.8 — [Issue#20](https://github.com/tovifun/VivalArc/issues/20). (Podziękowania dla @NextEcho za rozwiązania CSS, choć ostatecznie nie przyjąłem ich metody w całości).
2. W poprzednich wersjach stworzyłem kilka gradientowych motywów Vivaldi naśladujących styl Arc i dołączyłem je do plików projektu. Kilka dni temu przejrzałem sekcję motywów społeczności Vivaldi i odkryłem wiele pasujących propozycji. Uznałem, że nie ma potrzeby tworzyć własnych, więc wypróbowałem popularne motywy ze społeczności i wybrałem kilka trafnych. Jak ich użyć:
	1.	Otwórz [link z polecanymi motywami](./curated-themes-pl.md).
	2.	Kliknij nazwę motywu, aby przejść na jego stronę.
	3.	Kliknij przycisk instalacji pod motywem.

## 🗓️ 2024.05.12 | v1.0.2
- Najnowsza wersja VivalArc skupia się na optymalizacji dwóch elementów Vivaldi 6.7:
  - przycisków okna w lewym górnym rogu macOS, których nie można już dostosowywać, przez co nachodziły na elementy paska kart,
  - przycisku dodawania nowych kart, przeniesionego na dół okna.

## 🗓️ 2024.03.30
- Zoptymalizowano wysokość paska tytułu.

## 🗓️ 2023.11.09
- Zwiększono odstępy po obu stronach paska kart.
- Pasek kart można teraz domyślnie przeciągać (jeśli nie chcesz, zmień `.tabbar-wrapper` na `no-drag` w pliku `main_arc.css`).
- Wyskakująca strona ustawień ma teraz porządny pasek tytułu (we wcześniejszych wersjach przycisk zamykania był bardzo mały).
- Dodano dwa nowe motywy: `theme-gradientGreenLight` i `theme-gradientPinkLight`.
- Wciąż chcę poprawić pasek kart — na razie jest nieco surowy i powinien zostać dopracowany w przyszłych wersjach.

## 🗓️ 2023.09.17
- Ta aktualizacja zawiera wiele zmian. Przejrzałem każdą linię kodu, aby style były bardziej dopracowane.
- Główne zmiany:
  - Cienie na obszarach webview stały się subtelniejsze.
  - Optymalizacja paneli dla spójniejszych stylów w różnych konfiguracjach.
  - Ujednolicone kolory paska kart i paska menu.
- Dla chcących dostosować więcej: planowałem nagrać wideo demonstracyjne, ale jeszcze nie jest gotowe. Możesz śledzić mój [Youtube](https://www.youtube.com/channel/UCbmcO7HxXDYqEZFb-QgmRsw) — gdy demo będzie gotowe, opublikuję je tam. Na razie możesz otworzyć `css/main.css` i wprowadzić dodatkowe ustawienia. Krótkie wskazówki:
  - `--window-border` ustawia grubość ramki wokół okna. Polecam wartości między 4px a 16px. (0 oznacza brak ramki.)
  - `--window-button-opacity` reguluje nieprzezroczystość trzech przycisków w prawym górnym rogu dla użytkowników Windows. Domyślnie 0.3. Możesz ustawić dowolną wartość od 0 do 1 — wyższe wartości czynią przyciski bardziej widocznymi. Przy ok. 0.1 stają się prawie niewidoczne, ale wciąż pojawiają się po najechaniu. Jeśli chcesz czystszy nagłówek, ustaw poniżej 0.1.
  - Jeśli obszar przeciągania u góry jest za mały, możesz zwiększyć wartość `--window-header` albo użyć następującej metody:
  - Zmień `webkit-app-region` elementu `tabbar-wrapper` z `nodrag` na `drag`, aby cały pasek kart był przeciągalny. Część użytkowników zgłaszała jednak, że przeciąganie w tym obszarze może wpływać na lewy panel (prawy panel sprawia mniej problemów — sam ustawiłem go po prawej). Jeśli podczas testów napotkasz problemy, daj znać.
  - Uwaga: jeśli obszar paska kart stanie się przeciągalny, podwójne kliknięcie tworzące nową kartę przestanie działać. Możesz odkomentować „display new tab button" powyżej, aby dodać przycisk nowej karty do paska.
- **Uwaga: po modyfikacjach CSS trzeba ponownie uruchomić przeglądarkę, aby zmiany zaczęły działać.**

 ![Adnotacje](../installation/images/annotate-config.png)


## 🗓️ 2023.07.23
- Kilku użytkowników Windowsa zgłaszało, że nie widzi trzech przycisków okna, co było bardzo niewygodne — w tej wersji je przywróciłem.
- Trzy przyciski w lewym górnym rogu na Macu też wróciły, ale dla estetyki są wyszarzone i nabierają koloru dopiero po najechaniu.

## 🗓️ 2023.03.12
- Optymalizacje
    - Ukrycie ramki wokół okna w trybie pełnoekranowym;
    - Pokazanie paska tytułu i utrzymanie widocznych trzech przycisków w lewym górnym rogu (wielu użytkowników miało problem z ich znalezieniem);
    - Usunięcie przeciągania paska kart (powodowało wiele nieoczekiwanych błędów);
    - Uproszczenie arkusza stylów
        - Wcześniej, by jak najwierniej odwzorować Arc, używałem zbyt wielu niestandardowych stylów, przez co część z nich psuła się przy aktualizacjach Vivaldi. Przyjąłem więc zasadę: nie gonić ślepo za idealnym wyglądem, lecz używać jak najmniej CSS.

## 🗓️ 2022.08.28 Tło: dlaczego to powstało
Tytułem wstępu: od około roku używam Vivaldi jako głównej przeglądarki. Niedawno miałem okazję przez dwa tygodnie testować przeglądarkę Arc, wtedy jeszcze w becie. To doświadczenie było naprawdę dobre — interakcje intuicyjne, a UI bardzo estetyczne.

Ostatecznie wróciłem jednak do Vivaldi, głównie dlatego, że Arc kilka razy się zawiesił.

Później dowiedziałem się, że Vivaldi pozwala dostosowywać UI za pomocą CSS, więc postanowiłem spróbować. Efektem jest konfiguracja opisana na tej stronie.

Choć końcowy rezultat nie dorównuje UI Arc i jego dbałości o szczegóły, uważam, że ta konfiguracja zapewnia podobne doświadczenie. Chciałem się nią podzielić ze wszystkimi, którzy wciąż czekają na możliwość przetestowania Arc albo szukają alternatywy ze względu na jego zużycie pamięci.
