# Notatki o starszych wariantach

`vivalarc.css` w katalogu głównym repozytorium to jedyna aktywnie utrzymywana wersja VivalArc.

## Automatycznie chowany pasek kart (dawny wariant `autotab`)

Automatyczne chowanie paska kart jest teraz wbudowane w główny arkusz stylów jako opcjonalny przełącznik — osobny plik nie jest potrzebny.

Aby je włączyć, otwórz `vivalarc.css` i zmień zmienną w bloku `:root`:

```css
--enable-autohide-tabbar: 1;   /* 0 = wyłączone (domyślnie), 1 = włączone */
```

Możesz też dostosować szerokość zwiniętego paska:

```css
--autohide-tabbar-size: 32px;
```

Po zapisaniu uruchom Vivaldi ponownie.

## Warianty archiwalne

Dawne foldery `variants/autotab/` i `variants/compact/` zostały przeniesione do `archive/v7.7/`. Są przeznaczone dla Vivaldi 7.7 i nie są już aktualizowane.

## Zalecenie

Przy nowej instalacji wskaż `VivalArc/` w Ustawienia > Wygląd > Niestandardowe modyfikacje UI.

Jeśli używasz starszego wariantu i po aktualizacji Vivaldi coś przestało działać, przejdź na wersję główną i skorzystaj z wbudowanych przełączników opisanych powyżej.
