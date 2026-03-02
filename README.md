## Orvosi betegnyilvántartás
Készítsünk relációs adatmodellt egy háziorvosi betegnyilvántartó rendszerhez. Az orvosok elvárásainak
megfelelően az adatbázisnak tartalmaznia kell a betegek személyi adatait, gyógyszerérzékenységüket, az egyes
vizsgálatok időpontjait és felírt gyógyszereket.
### Feltételezzük, hogy:
* egy vizsgálaton több betegség is diagnosztizálható,
* egy betegségre több gyógyszer is felírható,
* egy páciens több gyógyszerre is lehet érzékeny,
* egy vizsgálatot a dátum és a vizsgálat kódja határoz meg egyértelműen.
### Feladatok
* Azonosítsd az adatbázis egyedtípusait, az attribútumokat, kapcsolatokat!
* Készítsd el az adatbázis ER-modelljét!
* Készítsd el az adatbázis Relációs modelljét!
* Kódold le az adatbázis phpmyadmin segítségével!
* Töltsd fel az adatbázist adatokkal!
* Készíts lekérdezéseket az adatbázis tesztelése céljából!
* Dokumentáld a munkádat a weben!
### Adatok

#### PÁCIENS

| Pid         | név              | cím                          | telefon        |
|-------------|------------------|------------------------------|----------------|
| 17402213339 | Kovács Krisztián | Hajdúhadház, Szűk u. 1.      | (66) 329-896   |
| 17303313254 | Andrészki Dezső  | Téglás, Kossuth utca 125.    | (52) 421-643   |
| 25602143598 | Kajár Miklósné   | Téglás, Petőfi út 12.        | (52) 342-453   |
| 26511123265 | Kocsis Béláné    | Téglás, Március 15. utca 3.  | (52) 384-345   |
| 14404013214 | Rézbányai Ernő   | Hajdúhadház, Bocskai út 35.  | (66) 325-643   |

#### VIZSGÁLAT

| Vid | Pid         | Dátum      |
|-----|-------------|------------|
| 1   | 17402213339 | 1996.02.11 |
| 2   | 17303313254 | 1996.02.11 |
| 3   | 25602143598 | 1996.02.11 |
| 4   | 26511123265 | 1996.02.11 |
| 5   | 14404013214 | 1996.02.11 |

#### BETEGSÉG

| Bnév            |
|-----------------|
| grippe          |
| hepatitis       |
| encefaritis     |
| encephalomylitis|
| pneumonia       |
| bronchitis      |

#### GYÓGYSZER

| Gynév        |
|--------------|
| Semicilin    |
| Prednisolon  |
| Medrol       |
| Metyl-pred   |
| Ceclor       |
| Diflucan     |
| Calciphedrin |

#### MIT_KAP

| Bnév             | Gynév        |
|------------------|--------------|
| grippe           | Semicilin    |
| hepatitis        | Prednisolon  |
| encefaritis      | Medrol       |
| encephalomylitis | Metyl-pred   |
| pneumonia        | Ceclor       |
| bronchitis       | Calciphedrin |

#### MIRE_ÉRZÉKENY

| Pid         | Gynév     |
|-------------|-----------|
| 17402213339 | –         |
| 17303313254 | –         |
| 25602143598 | –         |
| 26511123265 | Diflucan  |
| 14404013214 | –         |
| 26511123265 | Calciphedrin |

#### DIAGNÓZIS

| Vid | Dátum      | Bnév             |
|-----|------------|------------------|
| 1   | 1996.02.11 | encefaritis      |
| 1   | 1996.02.11 | encephalomylitis |
| 2   | 1996.02.11 | grippe           |
| 3   | 1996.02.11 | hepatitis        |
| 4   | 1996.02.11 | pneumonia        |
| 5   | 1996.02.11 | grippe           |
