# odcinkowy.eu

Strona aplikacji Odcinkowy: wizytówka z odznakami sklepów, polityka prywatności, warunki korzystania i wsparcie. Adresy dokumentów są w aplikacji (ekran „O aplikacji”) i w formularzach App Store i Google Play, więc ich nie zmieniamy:

- https://odcinkowy.eu/prywatnosc/
- https://odcinkowy.eu/warunki/
- https://odcinkowy.eu/wsparcie/

Zwykły HTML i CSS, bez builda, skryptów, ciasteczek i analityki. Wygląd według plansz „Strona www” na kanwie makiet: tokeny kolorów jak w apce, jasny albo ciemny motyw według ustawienia systemu. Kod aplikacji jest w repozytorium `odcinkowy` (zadanie #131).

## Pliki

| Plik | Co to |
| --- | --- |
| `index.html` | Wizytówka: hero z telefonami, „Co potrafi”, „Pobierz”, stopka |
| `prywatnosc/`, `warunki/`, `wsparcie/` | Dokumenty |
| `styles.css` | Tokeny (jasne w `:root`, ciemne w `prefers-color-scheme: dark`) i układ: od 1024 px dwie kolumny w hero |
| `fonts/` | Barlow i Barlow Condensed (OFL, `fonts/OFL.txt`), hostowane razem ze stroną, żeby nie łączyć się z Google Fonts |
| `favicon.svg`, `apple-touch-icon.png` | Ikona C apki |
| `og.png` | Podgląd linku (1200 × 630): hero w ciemnym motywie |

Ikony funkcji pochodzą z Lucide (licencja ISC).

## Po wydaniu aplikacji

1. W `index.html` zamień obie pary zaślepek `<span class="badge">` (w hero i w „Pobierz”) na oficjalne odznaki w wersji polskiej, czarne, tej samej wysokości, bez przerabiania, z linkami do kart apki:
   - App Store: odznaka „Pobierz w App Store” z Apple Marketing Tools, link `https://apps.apple.com/pl/app/…`;
   - Google Play: odznaka „Pobierz z Google Play” ze strony odznak Google Play, link `https://play.google.com/store/apps/details?id=…`.
2. Gdy telefony w hero zastąpią prawdziwe zrzuty z apki, wstaw je jako `<picture>` z wersją ciemną w `media="(prefers-color-scheme: dark)"` i odśwież `og.png` (zrzut hero 1440 × 756 w ciemnym motywie, zmniejszony do 1200 × 630).

## Jednorazowa konfiguracja

1. GitHub: Settings → Pages → Source: „Deploy from a branch”, gałąź `main`, katalog `/ (root)`. Custom domain: `odcinkowy.eu`.
2. Weryfikacja domeny (chroni przed przejęciem): ustawienia konta → Pages → „Add a domain”, a potem rekord TXT, który GitHub poda.
3. DNS w OVH dla `odcinkowy.eu`:
   - A: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - AAAA: `2606:50c0:8000::153`, `2606:50c0:8001::153`, `2606:50c0:8002::153`, `2606:50c0:8003::153`
   - CNAME `www` → `marcinobolewicz.github.io.`
4. Gdy GitHub sprawdzi DNS: Settings → Pages → „Enforce HTTPS”.
5. Poczta: w panelu OVH przekierowanie `kontakt@odcinkowy.eu` na swoją skrzynkę.
