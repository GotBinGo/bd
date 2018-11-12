# BigData HF
## Install
https://bkk.hu/apps/gtfs/  
Az itt letöltehtő zip-ben lévő .csv-ket kell a `data` mappába kicsomagolni.

## Adatok betöltése, értelmezése
 1. Első lépésként kigyűjtöttük a BKK weboldalának felhasználásával (https://bkk.hu/menetrendek/#ejszakai), hogy mely járatok éjszakaiak.
 2. Ezt követően betöltöttük a megfelelő csv fájlokat.
 3. Mintavételeztük az egyes fájlok tartalmát (head segítségével)
 4. Értelmeztük a táblák tartalmát, mit szeretne reprezentálni, felhasználva a https://developers.google.com/transit/gtfs/reference/ leírást. Érdekesség: az adatok szerint 1 nap 30 órából áll. Erre magyarázatot az említett honlapon találtunk.
 5. Megkerestük a kapcsolatokat az egyes fájlok között az idegen kulcsokat felhasználva: pl: routes - trips (route_id), stops - stop_times (stop_id) stb...
 6. Definiáltuk az éjszakai járatok fogalmát, amit későbbiekben használni fogunk: éjszakai járatnak számít a BKK szerint ÉS az érkezési ideje stop_times['arrival_time'] 24-nél nagyobb
 7. Diagramon ábrázoltuk az érkezési időket, melyről leolvasható, az éjszakai járatok mennyivel ritkábbak.
