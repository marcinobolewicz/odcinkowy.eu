# odcinkowy.eu

Strona aplikacji Odcinkowy: krótki opis, polityka prywatności, warunki korzystania i wsparcie. Adresy tych stron są w aplikacji (ekran „O aplikacji”) i w formularzach App Store i Google Play, więc ich nie zmieniamy:

- https://odcinkowy.eu/prywatnosc/
- https://odcinkowy.eu/warunki/
- https://odcinkowy.eu/wsparcie/

Zwykły HTML i jeden plik CSS, bez builda, ciasteczek i analityki. Hostuje GitHub Pages z gałęzi `main` (`.nojekyll` wyłącza Jekylla, `CNAME` ustawia domenę). Kod aplikacji jest w repozytorium `odcinkowy` (zadanie #131).

## Po wydaniu aplikacji

W `index.html`, w sekcji „Pobierz”, zamień „wkrótce” na linki do stron aplikacji w App Store i Google Play, np. `<li><a href="https://apps.apple.com/pl/app/…">App Store</a> (iPhone)</li>`.

## Jednorazowa konfiguracja

1. GitHub: Settings → Pages → Source: „Deploy from a branch”, gałąź `main`, katalog `/ (root)`. Custom domain: `odcinkowy.eu`.
2. Weryfikacja domeny (chroni przed przejęciem): ustawienia konta → Pages → „Add a domain”, a potem rekord TXT, który GitHub poda.
3. DNS w OVH dla `odcinkowy.eu`:
   - A: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - AAAA: `2606:50c0:8000::153`, `2606:50c0:8001::153`, `2606:50c0:8002::153`, `2606:50c0:8003::153`
   - CNAME `www` → `marcinobolewicz.github.io.`
4. Gdy GitHub sprawdzi DNS: Settings → Pages → „Enforce HTTPS”.
5. Poczta: w panelu OVH przekierowanie `kontakt@odcinkowy.eu` na swoją skrzynkę.
