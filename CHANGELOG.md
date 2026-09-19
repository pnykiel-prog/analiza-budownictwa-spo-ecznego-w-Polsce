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

## 2026-09-18 (partia 6 — otwarcie 04-bgk: SBC)
- Nowy katalog `04-bgk/sbc-finansowanie-zwrotne/`. Dodano 4 dokumenty BGK (md + raw): zrzut strony produktu Kredyt preferencyjny SBC (6 zakładek scalonych w jeden PDF, wiersz 047), Informator programu SBC aktualizacja 01/2025 (096), Poradnik kredytowy dla SIM z 6.02.2025 (097), Informator o gwarancji InvestEU (098).
- INDEX.csv: 047 → `pobrany`; 048–051 pozostają `do pobrania`, ale w uwagach wpisano dokładne nazwy dokumentów widoczne w zakładce Dokumenty na bgk.pl (18.09.2026), do pobrania w kolejnej turze.
- Ustalenie ze strony BGK: XXI (jesienna 2026) edycja SBC nie będzie prowadzona — środki wyczerpane. Oznacza to, że najbliższy nabór SBC zależy od decyzji ustawodawcy o limitach na 2027 r.
- Uwaga: Informator SBC (01/2025) opisuje stan sprzed rozp. 2026/575 — przy parametrach naboru pierwszeństwo ma rozporządzenie.
- INDEX.csv: 98 pozycji, 24 `pobrany`.

## 2026-09-18 (partia 6b — SBC: dokumenty z zakładki „Dokumenty”)
- Dodano 7 dokumentów BGK do `04-bgk/sbc-finansowanie-zwrotne/`: Proces udzielania finansowania (048), Warunki współfinansowania kosztów i zasady podziału (099), Wymagania dot. standardu lokali (100), Ramowy wzór umowy kredytu dla decyzji od 1.12.2025 (050), Wzór umowy z gminą (.docx, 101), Wniosek edycja XX 2026 (.xlsm, 049), Wytyczne dla rzeczoznawców (102).
- Formaty źródłowe inne niż PDF (.docx, .xlsm) zachowane w `raw/`; .md z .xlsm zawiera tylko arkusze WNIOSEK i oceny wiarygodności.
- Większość dokumentów BGK nie ma daty w treści — w INDEX jako `data_wersji` przyjęto datę pobrania; przy każdym użyciu sprawdzić, czy na bgk.pl nie ma nowszej wersji.
- Z listy na bgk.pl pozostają niepobrane: Załącznik do wniosku edycja XX, Formularz zmian do wniosku, Informacja o należnościach i przychodach, Biznes Plan, Formularz pomocy publicznej (od 1.05.2026), Wniosek o gwarancję InvestEU, wzór umowy dla decyzji do 30.11.2025.
- INDEX.csv: 102 pozycje, 31 `pobrany`.

## 2026-09-18 (partia 7 — otwarcie 04-bgk: Fundusz Dopłat, zrzut strony)
- Nowy katalog `04-bgk/fundusz-doplat/`. Dodano zrzut strony programu „Bezzwrotne wsparcie budownictwa z Funduszu Dopłat” (8 zakładek scalonych, 44 str., sekcje rozwijane rozwinięte; wiersz 053 → `pobrany`).
- Dodano matrycę wysokości wsparcia z Funduszu Dopłat obowiązującą od 22.08.2025 (osobny PDF ze strony, wiersz 054 → `pobrany`). Ponieważ pdftotext zniekształca tę tabelę, .md jest transkrypcją do tabeli markdown wykonaną z rasteryzacji stron i sprawdzoną wzrokowo; w raw/ obok PDF leży arkusz .xlsx z tą samą transkrypcją. PDF pozostaje źródłem rozstrzygającym.
- W uwagach 054, 055, 057 wpisano dokładne nazwy dokumentów i podstron z bgk.pl (18.09.2026) do pobrania w kolejnej turze.
- INDEX.csv: 102 pozycje, 33 `pobrany`.

## 2026-09-19 (partia 7b — Fundusz Dopłat: informatory, formularze, komunikaty BIP)
- Dodano 19 dokumentów do `04-bgk/fundusz-doplat/` (md + raw; formularze .xlsx i pełnomocnictwo .docx zachowane w oryginale):
  - informatory: Informator BSK (103), ulotka BSK (104), ulotka akademiki (105), aktualność o budżecie BSK 2025 (106);
  - formularze (zakładka Wnioski/Formularze): wniosek o finansowe wsparcie v2 od 11.06.2026 (055), wniosek dla uczelni v2 (107), wniosek o aneks (108), formularz rozliczenia środki krajowe v3 (109), formularz rozliczenia krajowe+KPO v5 (110), zestawienie wykonawców KPO (111), wzór pełnomocnictwa (112);
  - BIP: wykaz informacji o środkach (057) + informacje nr 4/2025, 1/2026, 4/2026 (113–115); wykaz list wniosków zakwalifikowanych (058) + listy nr 4/2025, 3/2026, 4/2026 (116–118).
- W .md z formularzy .xlsx pominięto arkusze słownikowe (TERYT, N_S_O, Infrastruktura) i techniczne; oryginały kompletne w raw/.
- 056 (wzór umowy o finansowe wsparcie) → `do weryfikacji`: BGK nie publikuje go na stronie.
- Ustalenia: środki na zasilenie Funduszu Dopłat — 2025: 1,92 mld zł (po podwyższeniu 22.08.2025); 2026: 4,13 mld zł (30.01.2026) → 4,15 mld zł (4.08.2026). W wykazie BIP na 2026 r. brak informacji nr 2 i 3.
- Zasada dla list BIP: pobierane są najnowsze 2–3 listy + jedna referencyjna; wykaz wszystkich dostępnych jest w zrzucie podstrony.
- INDEX.csv: 118 pozycji, 52 `pobrany`, 3 `do weryfikacji`.

## 2026-09-19 (partia 8 — RFRM: fundusz zlikwidowany)
- Nowy katalog `04-bgk/rfrm/`. Dodano zrzut strony funduszu (059) oraz plan finansowy na 2024 r. (119) i informację o realizacji planu za 2024 r. (120).
- USTALENIE KLUCZOWE: Rządowy Fundusz Rozwoju Mieszkalnictwa uległ likwidacji 20.12.2024 z powodu wyczerpania środków (art. 33s u.s.f.r.m.). Wsparcie gmin na objęcie udziałów w SIM (10% kosztów inwestycji / do 3 mln zł na utworzenie SIM) nie jest już dostępne. To wyjaśnia odesłania w rozp. Dz.U. 2025 poz. 1897 do art. 33l „w brzmieniu obowiązującym 21.08.2025” — dotyczą rozliczeń wsparcia udzielonego przed likwidacją.
- Korekta wcześniejszego przypuszczenia z CHANGELOG/uwag (że RFRM jest „wygaszany od 22.08.2025”): fundusz nie istnieje od grudnia 2024.
- Pozycje 060–064 (regulamin, wniosek, umowa, komunikaty, lista beneficjentów RFRM) → `archiwalny` — nie będą pobierane.
- Konsekwencja dla analiz montażu SIM: filar „udziały gminy z RFRM” należy z modeli usunąć lub zastąpić środkami własnymi gminy; do sprawdzenia w 077 (nowe programy 2025–2026), czy powstał instrument zastępczy.
- INDEX.csv: 120 pozycji, 55 `pobrany`, 6 `archiwalny`.
