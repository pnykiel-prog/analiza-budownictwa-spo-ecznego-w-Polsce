# Baza wiedzy „Budownictwo społeczne w Polsce” — plan budowy i lista dokumentów

Stan: 16 września 2026 r. Dokument roboczy do umieszczenia w repozytorium jako `PLAN.md`.

Założenia przyjęte przy pisaniu (jeśli któreś jest błędne — zmień, plan się przeskaluje):
- Baza ma służyć pracy doradczej SLE/DivideYou (analizy SIM/TBS, montaż finansowy BGK, RTB, materiały dla gmin i inwestorów), a nie publikacji jako produkt otwarty. Repozytorium: **prywatne**.
- Baza ma być czytelna zarówno dla ludzi, jak i dla Claude'a w Projekcie — stąd każdy PDF ma mieć wersję tekstową (`.md`) i wpis w indeksie.
- Zakres geograficzny: Polska. Materiały DE/CZ (raport z 8.09.2026) trafiają do osobnego katalogu porównawczego.

---

## 1. Architektura repozytorium

```
budownictwo-spoleczne-pl/
├── README.md                  # co to jest, jak korzystać, konwencje
├── PLAN.md                    # ten dokument
├── INDEX.csv                  # jeden wiersz = jeden dokument (patrz §1.2)
├── CHANGELOG.md               # co dodano/zaktualizowano i kiedy
├── 01-ustawy-rdzeniowe/       # akty wprost o budownictwie społecznym
├── 02-ustawy-posrednie/       # akty wpływające pośrednio
├── 03-rozporzadzenia/         # akty wykonawcze
├── 04-bgk/                    # programy, regulaminy, wzory, komunikaty BGK
│   ├── sbc-finansowanie-zwrotne/
│   ├── fundusz-doplat/
│   ├── rfrm/
│   ├── termomodernizacja/
│   └── mieszkanie-na-start/
├── 05-instytucje/             # MRiT, KZN, NIK, GUS, UOKiK (pomoc publiczna)
├── 06-przyklady/              # case studies — jeden podkatalog na inwestycję/gminę
│   └── <gmina>-<sim-lub-tbs>-<rok>/
│       ├── uchwaly/
│       ├── zamowienia/        # SWZ, PFU, kosztorys inwestorski, otwarcie ofert
│       ├── finansowanie/      # umowy z BGK, uchwały o poręczeniu, montaż
│       ├── zasiedlenie/       # regulamin naboru, kryteria, umowy partycypacji/najmu
│       └── sprawozdania/      # e-sprawozdania KRS, raporty roczne
├── 07-wzory/                  # wyekstrahowane wzory: uchwał, umów, regulaminów
├── 08-porownawcze-DE-CZ/      # raport z 8.09.2026 + źródła
├── 09-analizy/                # własne opracowania SLE (syntezy, mapy przepisów)
├── raw/                       # oryginalne PDF-y (Git LFS)
└── tools/                     # skrypty pobierania i konwersji
```

### 1.1 Konwencja nazw plików

`<typ>_<identyfikator>_<slug>_<wersja-lub-data>.<ext>`

Przykłady:
- `ustawa_DU-1995-654_spoleczne-formy-rozwoju-mieszkalnictwa_tj-2025-XX.pdf`
- `uchwala_XLV-312-2023_rada-miasta-XXX_utworzenie-sim.pdf`
- `bgk_sbc_regulamin-naboru_2026-01.pdf`

Zasady: bez polskich znaków w nazwach, myślniki zamiast spacji, data w ISO. Do każdego PDF plik `.md` o tej samej nazwie (tekst wyciągnięty) — to on jest indeksowany przez Claude'a; PDF jest źródłem.

### 1.2 INDEX.csv — kolumny

`id; kategoria; tytul; organ; data_aktu; data_wersji; sygnatura_lub_DzU; url_zrodlo; data_pobrania; sciezka_pdf; sciezka_md; status (obowiazuje/uchylony/projekt); tagi; uwagi`

Bez indeksu baza po pół roku stanie się stertą PDF-ów. Indeks jest ważniejszy niż liczba plików.

### 1.3 Ustalenia techniczne

- **Git LFS** dla `raw/` (PDF-y ustaw z tekstem jednolitym miewają po kilkadziesiąt MB w sumie; limit pojedynczego pliku na GitHub to 100 MB, ostrzeżenie od 50 MB).
- Konwersja PDF → tekst: `pdftotext -layout` jako pierwszy przebieg; skany (stare uchwały gmin) przez OCR (tesseract, język `pol`).
- Wersjonowanie aktów: nie nadpisuj starego tekstu jednolitego — dodaj nowy z datą, stary zostaw z `status=archiwalny`. Analizy odwołują się do konkretnej wersji.

---

## 2. Dokumenty do pozyskania

Oznaczenia pewności dotyczą nazw i dat aktów podanych z pamięci. Same tytuły są stabilne; numery Dz.U. i aktualność wersji **trzeba sprawdzić w ISAP** przy pobieraniu — skrypt i tak wyszukuje po tytule, więc ewentualna pomyłka w numerze nie blokuje pracy.

### 2.1 Ustawy rdzeniowe (`01-ustawy-rdzeniowe/`)

| Akt | Dlaczego | Pewność co do nazwy/daty |
|---|---|---|
| Ustawa z 26.10.1995 o społecznych formach rozwoju mieszkalnictwa (dawniej: o niektórych formach popierania budownictwa mieszkaniowego) — SIM/TBS, partycypacja, czynsz, finansowanie zwrotne | fundament całej bazy | wysoka |
| Ustawa z 8.12.2006 o finansowym wsparciu niektórych przedsięwzięć mieszkaniowych — Fundusz Dopłat | bezzwrotne wsparcie gmin/SIM | wysoka co do przedmiotu, średnia co do dokładnego tytułu po nowelizacjach |
| Ustawa z 20.07.2018 o pomocy państwa w ponoszeniu wydatków mieszkaniowych w pierwszych latach najmu mieszkania („Mieszkanie na Start”) | dopłaty do czynszu najemców | średnia |
| Ustawa z 10.12.2020 o zmianie niektórych ustaw wspierających rozwój mieszkalnictwa — pakiet SIM, RFRM, „lokal za grunt” | zmiana TBS→SIM, RFRM | średnia |
| Ustawa z 16.12.2020 o rozliczaniu ceny lokali lub budynków w cenie nieruchomości zbywanych z gminnego zasobu („lokal za grunt”) | model wnoszenia gruntu | średnia |
| Ustawa z 20.07.2017 o Krajowym Zasobie Nieruchomości — KZN, SIM-y KZN, najem instytucjonalny | grunt Skarbu Państwa, SIM-y wojewódzkie | wysoka |
| Ustawa z 5.07.2018 o ułatwieniach w przygotowaniu i realizacji inwestycji mieszkaniowych (specustawa mieszkaniowa) | ścieżka lokalizacyjna poza MPZP | wysoka co do aktu; **sprawdzić, czy nadal obowiązuje / do kiedy** (akt miał charakter epizodyczny) |
| Ustawa z 21.06.2001 o ochronie praw lokatorów, mieszkaniowym zasobie gminy i o zmianie KC — zasady wynajmu z zasobu gminy, najem socjalny, najem instytucjonalny z dojściem do własności (baza dla RTB) | zasiedlenie, RTB | wysoka |
| Ustawa z 21.06.2001 o dodatkach mieszkaniowych | zdolność czynszowa najemców | wysoka |
| Ustawa z 21.11.2008 o wspieraniu termomodernizacji i remontów oraz CEEB — premie BGK | modernizacja zasobu | wysoka |
| Nowelizacje 2023–2026 ustawy o SIM i ustaw towarzyszących | stan prawny | **luka** — nie odtwarzam z pamięci; pobrać wszystkie akty zmieniające z ISAP i odnotować w INDEX |

### 2.2 Ustawy pośrednio wpływające (`02-ustawy-posrednie/`)

Proces inwestycyjny:
- Prawo budowlane (7.07.1994)
- Ustawa o planowaniu i zagospodarowaniu przestrzennym (27.03.2003) wraz z nowelizacją z 2023 r. wprowadzającą plan ogólny gminy — terminy wygaszania studiów są kluczowe dla lokalizacji [pewność: średnia co do terminów — sprawdzić]
- Ustawa o gospodarce nieruchomościami (21.08.1997) — bonifikaty, aport, użytkowanie wieczyste, wycena
- Ustawa o przekształceniu prawa użytkowania wieczystego gruntów zabudowanych na cele mieszkaniowe (20.07.2018)
- Ustawa o charakterystyce energetycznej budynków (29.08.2014)
- Ustawa o zapewnianiu dostępności osobom ze szczególnymi potrzebami (19.07.2019) — istotna dla mieszkań senioralnych
- Ustawa o księgach wieczystych i hipotece (6.07.1982) — zabezpieczenia BGK

Forma prawna i własność:
- Ustawa o własności lokali (24.06.1994)
- Ustawa o spółdzielniach mieszkaniowych (15.12.2000) i Prawo spółdzielcze (16.09.1982)
- Kodeks spółek handlowych (15.09.2000) — SIM jako sp. z o.o./S.A., PSA
- Kodeks cywilny — najem (tytuł XVII)

Samorząd, finanse publiczne, zamówienia:
- Ustawa o samorządzie gminnym (8.03.1990), o samorządzie powiatowym (5.06.1998)
- Ustawa o gospodarce komunalnej (20.12.1996) — spółki gminne
- Ustawa o finansach publicznych (27.08.2009) — limity zadłużenia, poręczenia dla SIM
- Prawo zamówień publicznych (11.09.2019)
- Ustawa o partnerstwie publiczno-prywatnym (19.12.2008) i o umowie koncesji na roboty budowlane lub usługi (21.10.2016)
- Ustawa o postępowaniu w sprawach dotyczących pomocy publicznej (30.04.2004) + unijna decyzja SGEI 2025/2630 (już w raporcie DE/CZ; obowiązuje też w Polsce)
- Ustawa o Banku Gospodarstwa Krajowego (14.03.2003)

Podatki:
- Ustawa o VAT (11.03.2004) — stawka obniżona dla budownictwa objętego społecznym programem mieszkaniowym; nie podaję numeru artykułu z pamięci
- Ustawa o CIT (15.02.1992) — zwolnienia dla TBS/SIM przeznaczających dochód na cele statutowe [pewność: średnia — sprawdzić aktualne brzmienie]
- Ustawa o podatkach i opłatach lokalnych (12.01.1991) — zwolnienia uchwałowe z podatku od nieruchomości dla SIM
- Ustawa o podatku od czynności cywilnoprawnych — aport gruntu

Polityka społeczna:
- Ustawa o pomocy społecznej (12.03.2004) — mieszkania treningowe i wspomagane
- Ustawa o rehabilitacji zawodowej i społecznej oraz zatrudnianiu osób niepełnosprawnych (27.08.1997) — PFRON jako źródło dla dostępności

### 2.3 Rozporządzenia (`03-rozporzadzenia/`)

- Warunki techniczne, jakim powinny odpowiadać budynki i ich usytuowanie (12.04.2002, wielokrotnie zmieniane)
- Rozporządzenie RM w sprawie warunków i trybu finansowania zwrotnego w ramach programu popierania budownictwa mieszkaniowego (SBC) [pewność: średnia co do organu i daty — 2015 r. z późniejszymi zmianami]
- Rozporządzenie MRiT w sprawie finansowego wsparcia (wniosek do Funduszu Dopłat, zakres dokumentów)
- Rozporządzenie w sprawie określenia metod i podstaw sporządzania kosztorysu inwestorskiego (MRiT, 2021)
- Rozporządzenie w sprawie szczegółowego zakresu i formy dokumentacji projektowej, STWiORB i PFU
- Rozporządzenie w sprawie mieszkań treningowych i wspomaganych (standardy)
- Obwieszczenia wojewodów o wskaźniku przeliczeniowym kosztu odtworzenia 1 m² — **wszystkie 16 województw, aktualne półrocze** (limit czynszu w SIM zależy od tego wskaźnika)

### 2.4 BGK (`04-bgk/`)

Dla każdego programu komplet: strona programu (zapis PDF z datą), regulamin/warunki naboru, wzór wniosku i lista załączników, wzór umowy (jeśli publikowany), komunikaty o naborach i harmonogramy, FAQ, prezentacje z webinarów, **zestawienia udzielonego wsparcia** (listy beneficjentów — najlepsze źródło do wyboru case studies).

Programy [nazwy: pewność średnia — BGK zmienia nazewnictwo; sprawdzić aktualne na bgk.pl]:
1. Społeczne Budownictwo Czynszowe — finansowanie zwrotne / preferencyjny kredyt dla SIM/TBS/spółdzielni
2. Fundusz Dopłat — bezzwrotne wsparcie dla gmin, związków, SIM (w tym mieszkania komunalne, chronione, noclegownie)
3. Rządowy Fundusz Rozwoju Mieszkalnictwa — wsparcie gmin na objęcie udziałów w SIM
4. Fundusz Termomodernizacji i Remontów — premie termomodernizacyjna, remontowa, MZG
5. Mieszkanie na Start — dopłaty do czynszu
6. Programy z lat 2025–2026 (w tym ewentualne nowe instrumenty MRiT/BGK) — **luka do sprawdzenia**; nie zakładam ich z pamięci
7. Raporty roczne BGK i sprawozdania z realizacji programów mieszkaniowych (dane o skali, średnie koszty, liczba lokali)

### 2.5 Instytucje (`05-instytucje/`)

- MRiT: Narodowy Program Mieszkaniowy i jego aktualizacje, interpretacje, wzory dokumentów dla gmin, statystyki
- KZN: sprawozdania, lista SIM-ów KZN, zasady przekazywania gruntów, wzory umów
- NIK: kontrole SIM/TBS, Mieszkanie Plus, gospodarki zasobem gminnym — gotowe diagnozy błędów
- GUS: „Budownictwo mieszkaniowe” (roczne), ceny 1 m², zasoby mieszkaniowe
- UOKiK: pomoc publiczna w mieszkalnictwie, rekompensata SGEI
- RIO: rozstrzygnięcia nadzorcze dot. uchwał o SIM (cenne — pokazują, jak gminy błądzą)

### 2.6 Przykłady (`06-przyklady/`) — co zebrać dla jednej inwestycji

Cel: 8–12 kompletnych case studies, dobranych tak, by pokryć: SIM KZN, SIM gminne, TBS „stare”, spółdzielnia z SBC, mieszkania komunalne z Funduszu Dopłat, projekt z komponentem senioralnym, projekt z najmem z dojściem do własności.

Dla każdego przypadku:

**Uchwały rady gminy (BIP):**
- o utworzeniu SIM / przystąpieniu do SIM / objęciu udziałów
- o wniesieniu aportu (grunt) lub sprzedaży z bonifikatą
- o zaciągnięciu zobowiązania / poręczeniu kredytu SBC
- o zasadach wynajmowania lokali (art. 21 ustawy o ochronie praw lokatorów — ten numer podaję z pamięci, pewność wysoka, ale zweryfikuj)
- o wieloletnim programie gospodarowania mieszkaniowym zasobem gminy
- o zwolnieniu z podatku od nieruchomości
- o kryteriach pierwszeństwa i zasadach partycypacji

**Zamówienia (platformy zakupowe, BIP):**
- SWZ, PFU, dokumentacja projektowa
- kosztorys inwestorski (jeśli publikowany) i **informacja z otwarcia ofert** — realny koszt 1 m²
- umowa z generalnym wykonawcą (często publikowana w rejestrze umów)

**Finansowanie:**
- decyzje/umowy z BGK (rzadko publiczne; czasem w uchwałach lub sprawozdaniach)
- montaż finansowy z uzasadnienia uchwały budżetowej / WPF

**Zasiedlenie:**
- regulamin naboru najemców, punktacja
- wzór umowy partycypacyjnej, umowy najmu, umowy najmu z dojściem do własności
- stawki czynszu i ich uchwałowe/zarządcze podstawy

**Sprawozdania:**
- e-sprawozdania finansowe SIM/TBS z KRS (bezpłatne, publiczne) — 3 lata wstecz
- raporty z działalności zarządu

Dobór przypadków: zacząć od listy beneficjentów BGK (§2.4) i listy SIM-ów KZN, wybrać te z najbogatszym BIP.

### 2.7 Kwestie prawne pozyskiwania

- Akty prawne, uchwały, dokumenty urzędowe — nie podlegają prawu autorskiemu (art. 4 ustawy o prawie autorskim) [pewność: wysoka].
- Materiały BGK, NIK, GUS — publiczne, ale sprawdzić noty o ponownym wykorzystywaniu; w repo prywatnym problem praktycznie nie istnieje.
- Kosztorysy i oferty z przetargów — informacja publiczna; oferty mogą zawierać dane osobowe (imiona w wykazach personelu) — usuwać przed wgraniem lub trzymać tylko w `raw/` bez konwersji do `.md`.

---

## 3. Plan działania

| Etap | Czas | Efekt |
|---|---|---|
| 0. Szkielet repo | 1 dzień | struktura katalogów, README, INDEX.csv, LFS, skrypty |
| 1. Ustawy i rozporządzenia | 3–4 dni | skrypt pobiera teksty jednolite z ISAP wg listy §2.1–2.3, konwersja do `.md`, wpisy w indeksie |
| 2. BGK i instytucje | 2–3 dni | ręczne pobranie (strony BGK nie mają API), zapis z datą, indeks |
| 3. Wybór i zebranie 3 pierwszych case studies | 1 tydzień | pełne komplety wg §2.6; ustalenie, co realnie da się pozyskać |
| 4. Wzory | 2 dni | wyciągnięcie z case studies wzorów uchwał/umów/regulaminów do `07-wzory/` z komentarzem |
| 5. Pozostałe case studies | 2–3 tygodnie | docelowo 8–12 |
| 6. Warstwa analityczna | ciągły | `09-analizy/`: mapa przepisów, matryca „co gmina musi uchwalić”, matryca instrumentów BGK, słownik |
| 7. Utrzymanie | kwartalnie | ponowne pobranie tekstów jednolitych, kontrola naborów BGK, CHANGELOG |

Etap 1 jest w większości automatyzowalny. ISAP udostępnia API ELI (`api.sejm.gov.pl/eli/...`) zwracające metadane i PDF-y tekstów jednolitych [pewność: średnia — pamiętam istnienie API, nie sprawdzałem teraz jego aktualnej struktury; skrypt trzeba przetestować na jednym akcie].

---

## 4. GitHub i podpięcie do Projektu Claude

### 4.1 Repozytorium

1. Utwórz prywatne repo `budownictwo-spoleczne-pl` na GitHub (konto organizacji DivideYou lub prywatne).
2. Lokalnie: `git init`, `git lfs install`, `git lfs track "raw/**/*.pdf"`, `.gitattributes` do commita.
3. Pierwszy commit: szkielet + README + PLAN + skrypty. PDF-y dopiero po ustaleniu, że LFS działa.
4. Branch `main` chroniony; zmiany przez PR tylko jeśli będzie więcej niż jedna osoba.

Ważne: z tej sesji nie mogę wypchnąć repo na GitHub (brak Twoich poświadczeń). Mogę natomiast przygotować cały szkielet, skrypty i pierwsze `.md` jako paczkę do rozpakowania i `git push` u Ciebie — lub zrobić to przez Claude Code, jeśli tam jest skonfigurowany dostęp do GitHub.

### 4.2 Podpięcie repo do Projektu „Budownictwo społeczne”

Sprawdzone w dokumentacji Anthropic (claude.com/docs/connectors/github, wersja z lipca 2026):
- W projekcie, w sekcji „Project knowledge”, przycisk „+” → dodanie z GitHub; przy pierwszym użyciu przekierowanie do autoryzacji GitHub. Dla repo prywatnego trzeba nadać aplikacji GitHub dostęp do konkretnego repozytorium (lub poprosić administratora organizacji).
- Wybiera się konkretne pliki/foldery, nie całe repo hurtem; obowiązuje limit pojemności wiedzy projektu.
- Synchronizacja **nie jest automatyczna** — po każdej zmianie w repo klikasz „Sync now”.

Konsekwencje dla projektu bazy:
- Do Projektu Claude synchronizuj wyłącznie `.md`, `INDEX.csv` i `09-analizy/` — nie `raw/`. Kilkadziesiąt ustaw w PDF przekroczy limit pojemności; teksty jednolite dużych ustaw (Prawo budowlane, PZP, ustawa o VAT) nawet w `.md` są duże — te lepiej trzymać w repo i wgrywać do projektu tylko wyciągi lub konkretne rozdziały.
- Czy konektor GitHub indeksuje PDF-y, nie potwierdziłem — kolejny powód, by warstwą roboczą były pliki tekstowe [pewność: niska].
- W repo trzymaj `CLAUDE.md` z instrukcją korzystania z bazy (konwencje, gdzie co leży) — przyda się w Claude Code niezależnie od Projektu.

---

## 5. Co proponuję jako następny krok

1. Potwierdź założenia z nagłówka (repo prywatne; zakres PL; docelowi odbiorcy).
2. Zbuduję szkielet repo: strukturę, README, INDEX.csv z wpisanymi wszystkimi aktami z §2.1–2.3 (status „do pobrania”), skrypt `tools/fetch_isap.py` i `tools/pdf_to_md.sh`, `CLAUDE.md`.
3. Przetestuję skrypt na 2–3 ustawach, żeby potwierdzić działanie API ISAP, zanim zaufasz automatyzacji.

---

## Do zweryfikowania przed użyciem

- Numery Dz.U. i aktualne wersje tekstów jednolitych wszystkich aktów z §2.1–2.3 — sprawdzić w: ISAP (isap.sejm.gov.pl)
- Czy specustawa mieszkaniowa (2018) nadal obowiązuje i do kiedy — ISAP, akt zmieniający
- Nowelizacje ustawy o SIM z lat 2023–2026 — ISAP, lista aktów zmieniających
- Aktualne nazwy i status naborów programów BGK (§2.4), zwłaszcza pozycja 6 — bgk.pl
- Organ i data rozporządzenia o finansowaniu zwrotnym SBC — ISAP
- Struktura API ELI ISAP — test na jednym akcie przed uruchomieniem masowego pobierania
- Czy konektor GitHub w Projektach Claude indeksuje PDF-y — test na jednym pliku po podpięciu repo
