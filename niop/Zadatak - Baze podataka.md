# 📋 Specifikacija zadataka — Rad s bazom podataka u Javi

> **Napomena:** Zadaci se rješavaju kombiniranjem i prilagodbom koda iz demo projekta `BazePodataka`.
> Svaki zadatak prati istu arhitekturu: **Model → Repository → Singleton → Glavni program**.

---

## 📦 Zajednički zahtjevi za oba zadatka

| Stavka                 | Opis                                                                                      |
| ---------------------- | ----------------------------------------------------------------------------------------- |
| **Build alat**         | Maven, Java 17                                                                            |
| **Baza podataka**      | SQLite (dependency: `org.xerial:sqlite-jdbc`)                                             |
| **Arhitektura**        | Model klase + Repository klase + Singleton za vezu + Glavni program                       |
| **Singleton**          | Klasa koja upravlja JDBC vezom (ista kao `BazaPodatakaSingleton`)                         |
| **PreparedStatement**  | Svi SQL upiti s parametrima moraju koristiti `PreparedStatement`                          |
| **Try-with-resources** | Svi `Statement`, `PreparedStatement` i `ResultSet` objekti u try-with-resources blokovima |
| **Paket**              | `hr.obskc.[tvoje_ime].[naziv_projekta]`                                                   |

---

# 🔷 ZADATAK 1 — Knjižnica (Library)

## Tema

Sustav za evidenciju članova knjižnice i posuđivanja knjiga.

## Model klasa — specifikacija

### 1. `Clan` (Član knjižnice)

| Atribut       | Tip      | Opis                                               |
| ------------- | -------- | -------------------------------------------------- |
| `id`          | `int`    | Jedinstveni identifikator (autoinkrement u bazi)   |
| `ime`         | `String` | Ime člana                                          |
| `prezime`     | `String` | Prezime člana                                      |
| `clanskiBroj` | `String` | Jedinstveni broj članske iskaznice (npr. "CL-001") |

- Privatni atributi, getteri za sve
- Konstruktor: `Clan(int id, String ime, String prezime, String clanskiBroj)`
- `toString()` — čitljiv ispis

### 2. `Knjiga` (Knjiga)

| Atribut              | Tip      | Opis                                             |
| -------------------- | -------- | ------------------------------------------------ |
| `id`                 | `int`    | Jedinstveni identifikator (autoinkrement u bazi) |
| `naslov`             | `String` | Naslov knjige                                    |
| `autor`              | `String` | Autor knjige                                     |
| `dostupnoPrimjeraka` | `int`    | Broj trenutno dostupnih primjeraka               |

- Privatni atributi, getteri za sve
- Konstruktor: `Knjiga(int id, String naslov, String autor, int dostupnoPrimjeraka)`
- `toString()` — čitljiv ispis

### 3. `Posudba` (Evidencija posudbe)

| Atribut        | Tip      | Opis                              |
| -------------- | -------- | --------------------------------- |
| `id`           | `int`    | Jedinstveni identifikator         |
| `imeClana`     | `String` | Ime člana (dohvaćeno JOIN-om)     |
| `prezimeClana` | `String` | Prezime člana (dohvaćeno JOIN-om) |
| `naslovKnjige` | `String` | Naslov knjige (dohvaćen JOIN-om)  |

- Konstruktor: `Posudba(int id, String imeClana, String prezimeClana, String naslovKnjige)`
- `toString()` — čitljiv ispis

---

## Shema baze podataka

### Tablica `clanovi`

| Atribut        | Tip       | Ograničenje                 |
| -------------- | --------- | --------------------------- |
| `id`           | `INTEGER` | `PRIMARY KEY AUTOINCREMENT` |
| `ime`          | `TEXT`    | `NOT NULL`                  |
| `prezime`      | `TEXT`    | `NOT NULL`                  |
| `clanski_broj` | `TEXT`    | `NOT NULL`                  |

### Tablica `knjige`

| Atribut               | Tip       | Ograničenje                 |
| --------------------- | --------- | --------------------------- |
| `id`                  | `INTEGER` | `PRIMARY KEY AUTOINCREMENT` |
| `naslov`              | `TEXT`    | `NOT NULL`                  |
| `autor`               | `TEXT`    | `NOT NULL`                  |
| `dostupno_primjeraka` | `INTEGER` | `NOT NULL`                  |

### Tablica `posudbe`

| Atribut     | Tip       | Ograničenje                             |
| ----------- | --------- | --------------------------------------- |
| `id`        | `INTEGER` | `PRIMARY KEY AUTOINCREMENT`             |
| `clan_id`   | `INTEGER` | `NOT NULL`, `FOREIGN KEY → clanovi(id)` |
| `knjiga_id` | `INTEGER` | `NOT NULL`, `FOREIGN KEY → knjige(id)`  |

---

## Repository klase — specifikacija

### `ClanRepository`

| Metoda                                     | Opis                            | SQL operacija |
| ------------------------------------------ | ------------------------------- | :-----------: |
| `stvoriTablicu()`                          | Stvara tablicu `clanovi`        |      DDL      |
| `spremi(ime, prezime, clanskiBroj)`        | Unosi novog člana               |    INSERT     |
| `promijeni(id, ime, prezime, clanskiBroj)` | Ažurira podatke člana           |    UPDATE     |
| `brisi(id)`                                | Briše člana po ID-u             |    DELETE     |
| `dohvatiSve()`                             | Vraća `List<Clan>` svih članova |    SELECT     |

### `KnjigaRepository`

| Metoda                                      | Opis                                | SQL operacija |
| ------------------------------------------- | ----------------------------------- | :-----------: |
| `stvoriTablicu()`                           | Stvara tablice `knjige` i `posudbe` |      DDL      |
| `spremi(naslov, autor, dostupnoPrimjeraka)` | Unosi novu knjigu                   |    INSERT     |
| `dohvatiSve()`                              | Vraća `List<Knjiga>` svih knjiga    |    SELECT     |

### `PosudbaRepository`

| Metoda                             | Opis                                                                               |  SQL operacija   |
| ---------------------------------- | ---------------------------------------------------------------------------------- | :--------------: |
| `posudiKnjigu(clanId, knjigaId)`   | ⭐ **Transakcija**: smanjuje `dostupno_primjeraka` za 1 + dodaje zapis u `posudbe` | UPDATE + INSERT  |
| `dohvatiPosudbeZaKnjigu(knjigaId)` | Vraća `List<Posudba>` — JOIN `posudbe` ⟕ `clanovi` ⟕ `knjige`                      |  SELECT + JOIN   |
| `dohvatiSvePosudbe()`              | Vraća `List<Posudba>` svih posudbi (JOIN, sortirano po naslovu knjige)             |  SELECT + JOIN   |
| `ispisiStatistiku()`               | Ispisuje: knjiga \| autor \| dostupno \| broj posuđenih (koristi podupit)          | SELECT + podupit |

---

## 🔒 Transakcija — detaljno

Metoda `posudiKnjigu(clanId, knjigaId)`:

1. **Provjera** — je li član već posudio tu knjigu? Ako da → iznimka
2. `setAutoCommit(false)`
3. **Korak 1** — smanjiti `dostupno_primjeraka` za 1 (samo ako ih ima > 0)
   - Ako je 0 redaka pogođeno → iznimka ("Nema dostupnih primjeraka")
4. **Korak 2** — dodati zapis u tablicu `posudbe`
5. `commit()` — potvrdi transakciju
6. Ako išta ne uspije → `rollback()` + ispis greške
7. `finally` → `setAutoCommit(true)`

---

## Glavni program — demonstracija

1. Stvoriti tablice
2. Dodati 3–5 članova (zakomentirano nakon prvog pokretanja)
3. Dodati 3–5 knjiga (zakomentirano nakon prvog pokretanja)
4. Izvršiti 3–4 posudbe kroz transakcije (zakomentirano nakon prvog pokretanja)
5. Ispisati sve članove
6. Ispisati sve knjige
7. Ispisati sve posudbe za pojedinu knjigu
8. Ispisati sve posudbe
9. Ispisati statistiku

---

---

# 🔶 ZADATAK 2 — Sportski klub (Sports Club)

## Tema

Sustav za evidenciju igrača i njihovog učlanjenja u sportske timove.

## Model klasa — specifikacija

### 1. `Igrac` (Igrač)

| Atribut     | Tip      | Opis                                             |
| ----------- | -------- | ------------------------------------------------ |
| `id`        | `int`    | Jedinstveni identifikator (autoinkrement u bazi) |
| `ime`       | `String` | Ime igrača                                       |
| `prezime`   | `String` | Prezime igrača                                   |
| `brojDresa` | `int`    | Broj na dresu (1–99)                             |

- Privatni atributi, getteri za sve
- Konstruktor: `Igrac(int id, String ime, String prezime, int brojDresa)`
- `toString()` — čitljiv ispis

### 2. `Tim` (Sportski tim)

| Atribut            | Tip      | Opis                                             |
| ------------------ | -------- | ------------------------------------------------ |
| `id`               | `int`    | Jedinstveni identifikator (autoinkrement u bazi) |
| `naziv`            | `String` | Naziv tima (npr. "Nogometni klub X")             |
| `sport`            | `String` | Vrsta sporta (npr. "Nogomet", "Košarka")         |
| `maksimalnoIgraca` | `int`    | Maksimalan broj igrača u timu                    |

- Privatni atributi, getteri za sve
- Konstruktor: `Tim(int id, String naziv, String sport, int maksimalnoIgraca)`
- `toString()` — čitljiv ispis

### 3. `Clanstvo` (Evidencija članstva)

| Atribut         | Tip      | Opis                               |
| --------------- | -------- | ---------------------------------- |
| `id`            | `int`    | Jedinstveni identifikator          |
| `imeIgraca`     | `String` | Ime igrača (dohvaćeno JOIN-om)     |
| `prezimeIgraca` | `String` | Prezime igrača (dohvaćeno JOIN-om) |
| `nazivTima`     | `String` | Naziv tima (dohvaćen JOIN-om)      |

- Konstruktor: `Clanstvo(int id, String imeIgraca, String prezimeIgraca, String nazivTima)`
- `toString()` — čitljiv ispis

---

## Shema baze podataka

### Tablica `igraci`

| Atribut      | Tip       | Ograničenje                 |
| ------------ | --------- | --------------------------- |
| `id`         | `INTEGER` | `PRIMARY KEY AUTOINCREMENT` |
| `ime`        | `TEXT`    | `NOT NULL`                  |
| `prezime`    | `TEXT`    | `NOT NULL`                  |
| `broj_dresa` | `INTEGER` | `NOT NULL`                  |

### Tablica `timovi`

| Atribut             | Tip       | Ograničenje                 |
| ------------------- | --------- | --------------------------- |
| `id`                | `INTEGER` | `PRIMARY KEY AUTOINCREMENT` |
| `naziv`             | `TEXT`    | `NOT NULL`                  |
| `sport`             | `TEXT`    | `NOT NULL`                  |
| `maksimalno_igraca` | `INTEGER` | `NOT NULL`                  |

### Tablica `clanstva`

| Atribut    | Tip       | Ograničenje                            |
| ---------- | --------- | -------------------------------------- |
| `id`       | `INTEGER` | `PRIMARY KEY AUTOINCREMENT`            |
| `igrac_id` | `INTEGER` | `NOT NULL`, `FOREIGN KEY → igraci(id)` |
| `tim_id`   | `INTEGER` | `NOT NULL`, `FOREIGN KEY → timovi(id)` |

---

## Repository klase — specifikacija

### `IgracRepository`

| Metoda                                   | Opis                            | SQL operacija |
| ---------------------------------------- | ------------------------------- | :-----------: |
| `stvoriTablicu()`                        | Stvara tablicu `igraci`         |      DDL      |
| `spremi(ime, prezime, brojDresa)`        | Unosi novog igrača              |    INSERT     |
| `promijeni(id, ime, prezime, brojDresa)` | Ažurira podatke igrača          |    UPDATE     |
| `brisi(id)`                              | Briše igrača po ID-u            |    DELETE     |
| `dohvatiSve()`                           | Vraća `List<Igrac>` svih igrača |    SELECT     |

### `TimRepository`

| Metoda                                   | Opis                                 | SQL operacija |
| ---------------------------------------- | ------------------------------------ | :-----------: |
| `stvoriTablicu()`                        | Stvara tablice `timovi` i `clanstva` |      DDL      |
| `spremi(naziv, sport, maksimalnoIgraca)` | Unosi novi tim                       |    INSERT     |
| `dohvatiSve()`                           | Vraća `List<Tim>` svih timova        |    SELECT     |

### `ClanstvoRepository`

| Metoda                            | Opis                                                                      |  SQL operacija   |
| --------------------------------- | ------------------------------------------------------------------------- | :--------------: |
| `dodajIgracaUTim(igracId, timId)` | ⭐ **Transakcija**: provjerava limit + dodaje igrača u tim                | SELECT + INSERT  |
| `dohvatiIgraceUTimu(timId)`       | Vraća `List<Clanstvo>` — JOIN `clanstva` ⟕ `igraci` ⟕ `timovi`            |  SELECT + JOIN   |
| `dohvatiSvaClanstva()`            | Vraća `List<Clanstvo>` svih članstava (JOIN, sortirano po timu)           |  SELECT + JOIN   |
| `ispisiStatistiku()`              | Ispisuje: tim \| sport \| trenutno igrača \| maksimalno (koristi podupit) | SELECT + podupit |

---

## 🔒 Transakcija — detaljno

Metoda `dodajIgracaUTim(igracId, timId)`:

1. **Provjera 1** — je li igrač već u tom timu? Ako da → iznimka
2. **Provjera 2** — prebrojiti koliko igrača je trenutno u timu
3. **Provjera 3** — dohvati `maksimalno_igraca` za taj tim
   - Ako je trenutni broj ≥ maksimalno → iznimka ("Tim je popunjen")
4. `setAutoCommit(false)`
5. **Operacija** — dodati zapis u tablicu `clanstva`
6. `commit()` — potvrdi transakciju
7. Ako išta ne uspije → `rollback()` + ispis greške
8. `finally` → `setAutoCommit(true)`

---

## Glavni program — demonstracija

1. Stvoriti tablice
2. Dodati 3–5 igrača (zakomentirano nakon prvog pokretanja)
3. Dodati 3–5 timova (zakomentirano nakon prvog pokretanja)
4. Dodati igrače u timove kroz transakcije (zakomentirano nakon prvog pokretanja)
5. Ispisati sve igrače
6. Ispisati sve timove
7. Ispisati sve igrače u pojedinom timu
8. Ispisati sva članstva
9. Ispisati statistiku

---

# 📁 Struktura projekta (za oba zadatka)

```
📦 [ImeProjekta]/
├── 📄 pom.xml
└── 📁 src/main/java/hr/obskc/[tvoje_ime]/[projekt]/
    ├── 📄 [GlavnaKlasa].java          ← main metoda
    ├── 📄 [Naziv]Singleton.java       ← Singleton za vezu
    ├── 📄 [Entitet1].java             ← Model 1
    ├── 📄 [Entitet2].java             ← Model 2
    ├── 📄 [Entitet3].java             ← Model 3 (JOIN)
    ├── 📄 [Entitet1]Repository.java   ← CRUD za entitet 1
    ├── 📄 [Entitet2]Repository.java   ← CRUD + transakcija za entitet 2
    └── 📄 [Entitet3]Repository.java   ← JOIN upiti + statistika
```

---

# 💡 Savjeti za učenike

1. **Kreni od demo koda** — preslikaj `BazePodataka` strukturu, samo promijeni nazive i SQL upite
2. **Prvo Singleton** — klasa za vezu je identična, samo promijeni naziv
3. **Model klase** — prilagodi atribute i `toString()`
4. **Repository** — metoda po metoda, koristi iste SQL obrasce
5. **Transakcija** — najsloženiji dio, pažljivo prati redoslijed koraka
6. **Testiraj korak po korak** — prvo stvori tablice, pa dodaj podatke, pa testiraj dohvat
7. **Komentiraj INSERT naredbe** nakon prvog pokretanja da ne bi dobio duplikate
