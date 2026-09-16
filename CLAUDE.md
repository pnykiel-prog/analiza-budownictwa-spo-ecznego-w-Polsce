# Konwencje repozytorium — instrukcja dla Claude'a i dla ludzi

## Czym jest to repozytorium
Baza wiedzy o budownictwie społecznym w Polsce, używana jako wiedza projektu w Claude oraz jako źródło do analiz doradczych SLE / Fundacji DivideYou. Priorytet: wiarygodność i śledzalność źródeł ponad liczbę plików.

## Zasady odpowiadania na podstawie tej bazy
- Cytując przepis, podawaj plik i datę wersji z `INDEX.csv`. Jeśli akt ma w indeksie status `do pobrania` lub `do weryfikacji`, powiedz to wprost zamiast odtwarzać treść z pamięci.
- Numery artykułów podawaj tylko wtedy, gdy są w pliku `.md` w repo. Bez pliku — opisz przepis, nie numeruj.
- Parametry programów BGK (limity, terminy naborów, oprocentowanie) bierz wyłącznie z plików w `04-bgk/` i podawaj datę dokumentu; jeśli dokument ma ponad kwartał, zaznacz, że mógł się zdezaktualizować.
- Rozróżniaj: fakt z pliku / wniosek / przypuszczenie / luka.

## Nazewnictwo plików
`<typ>_<identyfikator>_<slug>_<wersja-lub-data>.<ext>`
- typ: `ustawa`, `rozp`, `obwieszczenie`, `uchwala`, `bgk`, `nik`, `gus`, `kzn`, `swz`, `kosztorys`, `umowa`, `regulamin`, `sprawozdanie`, `analiza`
- identyfikator: numer Dz.U. (`DU-1995-654`), numer uchwały (`XLV-312-2023`), nazwa programu
- slug: bez polskich znaków, myślniki zamiast spacji
- wersja: `tj-2025-03` dla tekstu jednolitego, data ISO dla dokumentów
Przykład: `ustawa_DU-1995-654_spoleczne-formy-rozwoju-mieszkalnictwa_tj-2025-03.md`

Do każdego PDF w `raw/` istnieje plik `.md` o tej samej nazwie w katalogu tematycznym.

## Gdzie co leży
Patrz tabela w `README.md`. Zasada: dokument trafia do katalogu według swojej natury, nie według tego, gdzie akurat pracujesz. Uchwała gminy z case study → `06-przyklady/<przypadek>/uchwaly/`, jej uogólniony wzór → `07-wzory/`.

## INDEX.csv
Separator: średnik. Kodowanie: UTF-8. Kolumny:
`id;kategoria;typ;tytul;organ;data_aktu;dzu_lub_sygnatura;data_wersji;url_zrodlo;data_pobrania;sciezka_md;sciezka_raw;status;pewnosc_metadanych;tagi;uwagi`

Statusy: `do pobrania` · `pobrany` · `do weryfikacji` · `archiwalny` · `uchylony` · `projekt`
Pewność metadanych: `zweryfikowane` (sprawdzone w źródle) · `z pamieci` (wpisane bez sprawdzenia — do potwierdzenia przy pobieraniu)

Każde dodanie lub aktualizacja pliku = aktualizacja wiersza w indeksie + wpis w `CHANGELOG.md`. Nowa wersja tekstu jednolitego nie nadpisuje starej: stary plik dostaje status `archiwalny`.

## Case studies (`06-przyklady/`)
Podkatalog `<gmina>-<podmiot>-<rok>/` z pięcioma folderami jak w `_szablon-przypadku/`. W folderze przypadku plik `README.md` z: podmiotem, liczbą lokali, montażem finansowym (jeśli znany), datami, źródłami. Niekompletny komplet jest w porządku — brakujące elementy wpisz w README jako luki.

## Czego nie robić
- Nie wgrywać `raw/` do wiedzy projektu Claude — tylko `.md`, `INDEX.csv`, `07-wzory/`, `09-analizy/`.
- Nie tworzyć plików `.md` z treścią odtworzoną z pamięci modelu i nie oznaczać ich jako źródło.
- Nie usuwać archiwalnych wersji aktów.
