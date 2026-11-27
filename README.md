# odcinkowy.eu

Strona aplikacji Odcinkowy: wizytówka z odznakami sklepów, polityka prywatności, warunki korzystania i wsparcie. Adresy dokumentów są w aplikacji (ekran „O aplikacji”) i w formularzach App Store i Google Play, więc ich nie zmieniamy:

- https://odcinkowy.eu/prywatnosc/
- https://odcinkowy.eu/warunki/
- https://odcinkowy.eu/wsparcie/

Zwykły HTML i CSS, bez builda, skryptów, ciasteczek i analityki, na hostingu OVH. Wygląd według plansz „Strona www” na kanwie makiet: tokeny kolorów jak w apce, jasny albo ciemny motyw według ustawienia systemu. Kod aplikacji jest w repozytorium `odcinkowy` (zadanie #131).

## Pliki

| Plik | Co to |
| --- | --- |
| `index.html` | Wizytówka: hero z telefonami, „Co potrafi”, „Pobierz”, stopka |
| `prywatnosc/`, `warunki/`, `wsparcie/` | Dokumenty |
| `styles.css` | Tokeny (jasne w `:root`, ciemne w `prefers-color-scheme: dark`) i układ: od 1024 px dwie kolumny w hero |
| `fonts/` | Barlow i Barlow Condensed (OFL, `fonts/OFL.txt`), hostowane razem ze stroną, żeby nie łączyć się z Google Fonts |
| `favicon.svg`, `apple-touch-icon.png` | Ikona apki (wariant E, `docs/icon/odcinkowy-ikona.svg` w repozytorium `odcinkowy`) |
| `og.png` | Podgląd linku (1200 × 630): hero w ciemnym motywie |
| `badges/` | Oficjalne odznaki sklepów po polsku, bez przerabiania: `app-store.svg` z Apple Marketing Tools i `google-play.png` ze strony odznak Google Play. PNG Google ma przezroczysty margines, który `styles.css` zjada ujemnym marginesem, żeby obie odznaki miały tę samą widoczną wysokość (`--badge-height`: 48 px, od 1024 px 56 px) |

Ikony funkcji pochodzą z Lucide (licencja ISC).

## Sklepy

Odznaki w hero i w „Pobierz” prowadzą do kart apki:

- App Store: https://apps.apple.com/pl/app/odcinkowy/id6826824938 (apka jest tylko w polskim sklepie, więc link ma `/pl/`);
- Google Play: https://play.google.com/store/apps/details?id=pl.shredmate.odcinkowy.

Gdy telefony w hero zastąpią prawdziwe zrzuty z apki, wstaw je jako `<picture>` z wersją ciemną w `media="(prefers-color-scheme: dark)"` i odśwież `og.png` (zrzut hero 1440 × 756 w ciemnym motywie, zmniejszony do 1200 × 630).

## Publikacja

Strona stoi na hostingu OVH domeny (cluster129, HTTPS od OVH). Po zmianie w `main` wgraj przez FTP (`ftp.cluster129.hosting.ovh.net`) do katalogu `www` pliki strony: `index.html`, `styles.css`, `favicon.svg`, `apple-touch-icon.png`, `og.png` i katalogi `badges/`, `fonts/`, `prywatnosc/`, `warunki/`, `wsparcie/`. Plików repo (`README.md`, `.git`) nie wgrywaj.

Poczta: w panelu OVH przekierowanie `kontakt@odcinkowy.eu` na swoją skrzynkę.
