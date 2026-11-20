# Zabawy ruchowe (Jekyll + GitHub Pages)

## Struktura

- `_zabawy/` – jedna zabawa = jeden plik .md (nazwa, kategoria, wiek, rekwizyty, obrazek, krótki opis i pełna treść zasad)
- `_data/kategorie.yml` – lista kategorii (slug, nazwa wyświetlana, opis)
- `assets/img/` – obrazki do zabaw
- `_layouts/` – szablony stron
- `index.html` – losowanie, `lista.html` – lista zabaw według kategorii
- `_config.yml` – ustawienia (tu ustawiasz `baseurl`)

## Dodanie zabawy

Skopiuj dowolny plik z `_zabawy/`, zmień nazwę pliku i uzupełnij pola na górze (między liniami `---`). Pole `kategoria` musi być slugiem z `_data/kategorie.yml`. Pole `obrazek` jest opcjonalne.

## Dodanie kategorii

Dopisz blok w `_data/kategorie.yml`:

    - slug: pilka
      nazwa: Z piłką tenisową
      opis: Toczenie, celowanie i podawanie.

Potem w nowych zabawach wpisz `kategoria: pilka`. Kategoria bez zabaw nie pokazuje się w losowaniu.

## Zmiana kategorii

- zmiana nazwy: edytujesz `nazwa` w `kategorie.yml`, wszystkie zabawy zmienią się same
- przeniesienie zabawy: zmieniasz `kategoria` w jej pliku
- zmiana kolejności: przestawiasz bloki w `kategorie.yml`
- zmiana sluga: musisz poprawić pole `kategoria` we wszystkich zabawach tej kategorii

## Publikacja

1. Wgraj całą zawartość tego folderu do repozytorium na GitHubie.
2. Settings → Pages → Deploy from a branch → gałąź main, folder / (root).
3. Jeśli repozytorium nazywa się inaczej niż `uzytkownik.github.io`, wpisz w `_config.yml` np. `baseurl: "/zabawy"`.

## Uruchomienie lokalne (opcjonalnie)

Wymaga Rubiego: `bundle install`, potem `bundle exec jekyll serve` i adres http://localhost:4000
