# CHANGELOG

## 2026-09-16
- Utworzono szkielet repozytorium: struktura katalogów, README, PLAN, CLAUDE.md, INDEX.csv.
- INDEX.csv: wpisano akty i grupy dokumentów z planu ze statusem `do pobrania`; metadane oznaczone jako `z pamieci` do potwierdzenia przy pobieraniu.

## 2026-09-16 (partia 1)
- Dodano 4 akty (md + raw): ustawa o SIM t.j. Dz.U. 2025 poz. 1273; nowelizacja Dz.U. 2025 poz. 1077; ustawa o finansowym wsparciu t.j. Dz.U. 2024 poz. 304; ustawa o ochronie praw lokatorów t.j. Dz.U. 2023 poz. 725.
- INDEX.csv: wiersze 001, 002, 008 → `pobrany`, metadane `zweryfikowane`; dodano wiersz 088 (nowelizacja 2025).
- Ustalono działające źródło: `https://api.sejm.gov.pl/eli/acts/DU/{rok}/{poz}/text.pdf` (ISAP i dziennikustaw.gov.pl blokują pobieranie automatyczne).

## 2026-09-16 (partia 2)
- Dodano 7 aktów (md + raw): KZN t.j. 2025/834; Mieszkanie na Start t.j. 2024/506; dodatki mieszkaniowe t.j. 2023/1335; termomodernizacja t.j. 2024/1446; specustawa mieszkaniowa t.j. 2024/195; ustawa 2025/413 (limity); ustawa 2026/39 (spółdzielnie/SIM/KZN).
- INDEX.csv: wiersze 003, 006, 009, 010 → `pobrany`; 007 (specustawa) → `do weryfikacji` (status obowiązywania); 011 → `do weryfikacji`; dodano 089, 090.

## 2026-09-16 (partia 3a — domknięcie 01-ustawy-rdzeniowe)
- Dodano: „lokal za grunt” t.j. 2023/1525; pakiet mieszkaniowy 2021/11 (ustawa z 10.12.2020).
- INDEX.csv: wiersze 004, 005 → `pobrany`. W katalogu 01 pozostają tylko 007 (specustawa — status obowiązywania) i 011 (akty zmieniające 2023–2024) ze statusem `do weryfikacji`.

## 2026-09-18 (partia 4 — otwarcie katalogów 02 i 03, aktualizacja t.j. Funduszu Dopłat)
- Dodano 7 aktów (md + raw), źródło: ELI/API Sejmu, PDF-y pobrane ręcznie i wgrane do rozmowy:
  - `01-ustawy-rdzeniowe/`: ustawa o finansowym wsparciu — nowy t.j. Dz.U. 2026 poz. 511 (stan prawny 25.03.2026). Stary t.j. 2024/304 (wiersz 002) → `archiwalny`, plik zachowany; nowy wiersz 091.
  - `02-ustawy-posrednie/` (nowy katalog): ustawa o spółdzielniach mieszkaniowych t.j. Dz.U. 2026 poz. 889 (wiersz 020); ustawa o BGK t.j. Dz.U. 2026 poz. 195 (wiersz 033).
  - `03-rozporzadzenia/` (nowy katalog): rozp. RM z 20.10.2015 o finansowaniu zwrotnym SBC — t.j. Dz.U. 2021 poz. 766 (wiersz 041; organ i data potwierdzone); zmiany Dz.U. 2024 poz. 1732 (nowy wiersz 092) i Dz.U. 2026 poz. 575 (nowy wiersz 093); rozp. MFiG z 29.12.2025 o finansowym wsparciu Dz.U. 2025 poz. 1897 (wiersz 042; tytuł, organ i data ustalone).
- INDEX.csv: 020, 033, 041, 042 → `pobrany`, metadane `zweryfikowane`; 002 → `archiwalny`; dodano 091–093. Stan: 93 pozycje, 18 `pobrany`, 72 `do pobrania`, 2 `do weryfikacji`, 1 `archiwalny`.
- Uwaga metodyczna: t.j. rozp. 766 z 2021 r. nie zawiera zmian z 2024 i 2026 — przy cytowaniu § 4, § 5, § 7, § 8 i załącznika sprawdzić brzmienie w plikach 1732 i 575.
- Z wykazu podstaw prawnych kalkulatora `simprywatny` (sierpień 2026) pozostają do potwierdzenia/pobrania: Dz.U. 2026 poz. 986 (nowelizacja u.s.f.r.m.? — niepotwierdzona w ELI), rozp. RM z 11.08.2004 o obliczaniu wartości pomocy publicznej (t.j. Dz.U. 2018 poz. 461), rozp. MIiR z 4.03.2019 o standardach dla FD (Dz.U. 2019 poz. 457) — to ostatnie jest przywołane wprost w zał. 1 pkt VI.S rozp. 1897.

## 2026-09-18 (partia 5 — domknięcie podstaw rekompensaty UOIG)
- Dodano 2 akty (md + raw) do `03-rozporzadzenia/`: rozp. MIiR z 4.03.2019 o standardach dla Funduszu Dopłat (Dz.U. 2019 poz. 457, nowy wiersz 094); rozp. RM z 11.08.2004 o obliczaniu wartości pomocy publicznej — t.j. Dz.U. 2018 poz. 461 (nowy wiersz 095).
- Oba akty sprawdzone przez użytkownika w ELI 18.09.2026: obowiązujące, bez aktów zmieniających po dacie t.j./ogłoszenia.
- Tym samym komplet podstaw prawnych z wykazu kalkulatora `simprywatny` jest w bazie, z wyjątkiem Dz.U. 2026 poz. 986 (niepotwierdzone — pozycja 011).
- INDEX.csv: 95 pozycji, 20 `pobrany`, 72 `do pobrania`, 2 `do weryfikacji`, 1 `archiwalny`.
