# Analiza budownictwa społecznego w Polsce — baza wiedzy

Repozytorium gromadzi akty prawne, dokumenty programowe BGK, materiały instytucji publicznych oraz przykłady zrealizowanych inwestycji (uchwały gmin, dokumenty przetargowe, regulaminy zasiedlenia, sprawozdania) dotyczące społecznego budownictwa mieszkaniowego w Polsce: SIM/TBS, mieszkania komunalne, spółdzielcze, senioralne, najem z dojściem do własności.

Repozytorium jest podpięte jako wiedza projektu w Claude („Analiza budownictwa społecznego”). Warstwą roboczą są pliki tekstowe `.md`; oryginalne PDF-y trafiają do `raw/` lub są linkowane w indeksie.

## Jak korzystać

1. Zacznij od `INDEX.csv` — każdy dokument w bazie ma tam jeden wiersz z metadanymi, ścieżką i statusem.
2. `PLAN.md` opisuje docelowy zakres bazy i etapy jej budowy.
3. `CLAUDE.md` zawiera konwencje (nazewnictwo, gdzie co leży, jak aktualizować) — obowiązują zarówno ludzi, jak i Claude'a pracującego na repo.
4. `CHANGELOG.md` — co i kiedy dodano.

## Struktura

| Katalog | Zawartość |
|---|---|
| `01-ustawy-rdzeniowe/` | ustawy wprost regulujące budownictwo społeczne |
| `02-ustawy-posrednie/` | ustawy wpływające pośrednio (proces inwestycyjny, samorząd, podatki, polityka społeczna) |
| `03-rozporzadzenia/` | akty wykonawcze, obwieszczenia o wskaźnikach |
| `04-bgk/` | programy BGK — regulaminy, wzory, komunikaty, listy beneficjentów |
| `05-instytucje/` | MRiT, KZN, NIK, GUS, UOKiK, RIO |
| `06-przyklady/` | case studies — jeden podkatalog na inwestycję; `_szablon-przypadku/` pokazuje wymagany komplet |
| `07-wzory/` | wyekstrahowane wzory uchwał, umów, regulaminów z komentarzem |
| `08-porownawcze-DE-CZ/` | materiały porównawcze: Niemcy, Czechy, UE |
| `09-analizy/` | opracowania własne: mapy przepisów, matryce instrumentów, syntezy |
| `raw/` | oryginalne pliki binarne (PDF, skany) — Git LFS |

## Status prawny materiałów

Akty prawne i dokumenty urzędowe nie są przedmiotem prawa autorskiego. Materiały instytucji (BGK, NIK, GUS) są publiczne; repozytorium jest prywatne i służy pracy analitycznej. Dokumenty z postępowań przetargowych mogą zawierać dane osobowe — przed konwersją do `.md` usuwać je lub zostawiać wyłącznie w `raw/`.

## Zastrzeżenie

Wersje `.md` są wyciągami tekstowymi wykonanymi automatycznie. Przed wykorzystaniem konkretnego przepisu w dokumencie zewnętrznym sprawdź brzmienie w tekście jednolitym w ISAP — datę wersji znajdziesz w `INDEX.csv`.
