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

Ikony funkcji pochodzą z Lucide (licencja ISC).

## Po wydaniu aplikacji

1. W `index.html` zamień obie pary zaślepek `<span class="badge">` (w hero i w „Pobierz”) na oficjalne odznaki w wersji polskiej, czarne, tej samej wysokości, bez przerabiania, z linkami do kart apki:
   - App Store: odznaka „Pobierz w App Store” z Apple Marketing Tools, link `https://apps.apple.com/pl/app/…`;
   - Google Play: odznaka „Pobierz z Google Play” ze strony odznak Google Play, link `https://play.google.com/store/apps/details?id=…`.
2. Gdy telefony w hero zastąpią prawdziwe zrzuty z apki, wstaw je jako `<picture>` z wersją ciemną w `media="(prefers-color-scheme: dark)"` i odśwież `og.png` (zrzut hero 1440 × 756 w ciemnym motywie, zmniejszony do 1200 × 630).

## Publikacja

Strona stoi na hostingu OVH domeny (cluster129, HTTPS od OVH). Po zmianie w `main` wgraj przez FTP (`ftp.cluster129.hosting.ovh.net`) do katalogu `www` pliki strony: `index.html`, `styles.css`, `favicon.svg`, `apple-touch-icon.png`, `og.png` i katalogi `fonts/`, `prywatnosc/`, `warunki/`, `wsparcie/`. Plików repo (`README.md`, `.git`) nie wgrywaj.

Poczta: w panelu OVH przekierowanie `kontakt@odcinkowy.eu` na swoją skrzynkę.
