## Zadatak 1: Planer učenja

### Ideja
Korisnik unese predmet i trajanje učenja, odabere vrstu učenja i spremi zapis.

### Što aplikacija mora imati

1. Početni ekran:
- unos "Naziv predmeta" (tekst)
- unos "Trajanje u minutama" (broj)
- provjera unosa:
  - predmet ne smije biti prazan
  - trajanje mora biti broj od 15 do 180
- gumb "Nastavi" vodi na drugi ekran

2. Ekran rezultata:
- prikaz unesenog predmeta i trajanja
- `Dropdown` s opcijama:
  - Čitanje
  - Rješavanje zadataka
  - Ponavljanje
  - Projektni rad
- izračun "opterećenja":
  - Čitanje: `trajanje * 1.0`
  - Rješavanje zadataka: `trajanje * 1.3`
  - Ponavljanje: `trajanje * 0.8`
  - Projektni rad: `trajanje * 1.5`
- gumb "Spremi u povijest"
- gumb "Spremi kao predložak"

3. Ekran povijesti:
- lista spremljenih zapisa (najnoviji na vrhu)
- brisanje jedne stavke uz potvrdu (`AlertDialog`)
- brisanje cijele povijesti

4. Ekran predložaka:
- lista predložaka
- klik na predložak vrati podatke na početni ekran i otvori ekran rezultata
- brisanje jednog predloška i svih predložaka

### Tehnički dio

1. Napravi model `StudyTemplate` (`toJson`, `fromJson`).
2. Napravi provider `StudyProvider`.
3. Povijest i predloške spremi u `SharedPreferences`.
4. UI osvježavaj preko `Consumer`.

### Što se ovdje uči
- forme i validacija
- rad s više ekrana
- upravljanje stanjem (`Provider`)
- lokalno spremanje podataka

---

## Zadatak 2: Planer obroka

### Ideja
Korisnik unese obrok i broj sastojaka, odabere tip obroka i dobije procjenu kalorija.

### Što aplikacija mora imati

1. Početni ekran:
- unos "Naziv obroka" (tekst)
- unos "Broj sastojaka" (broj)
- provjera unosa:
  - naziv ne smije biti prazan
  - broj sastojaka mora biti broj od 1 do 20
- gumb "Nastavi" vodi na drugi ekran

2. Ekran procjene:
- prikaz unesenih podataka
- `Dropdown` s opcijama:
  - Doručak
  - Ručak
  - Večera
  - Užina
- procjena kalorija:
  - Doručak: `sastojci * 90`
  - Ručak: `sastojci * 130`
  - Večera: `sastojci * 110`
  - Užina: `sastojci * 70`
- gumb "Spremi procjenu"
- gumb "Spremi kao predložak"

3. Ekran povijesti:
- lista procjena (najnoviji na vrhu)
- brisanje jedne stavke uz potvrdu
- brisanje cijele povijesti

4. Ekran predložaka:
- odabir predloška vraća podatke i otvara ekran procjene
- brisanje jednog i svih predložaka

### Tehnički dio

1. Napravi model `MealTemplate` (`toJson`, `fromJson`).
2. Napravi provider `MealProvider`.
3. Koristi `SharedPreferences` za spremanje.
4. Prikaži barem 2 različita `SnackBar`-a:
- uspješno spremanje
- uspješno brisanje

### Što se ovdje uči
- povezivanje UI-a i logike
- spremanje i učitavanje podataka
- rad s listama i predlošcima
- potvrde kod brisanja

---

## Kako se ocjenjuje (za svaki zadatak)

1. Funkcionalnost (40%)
- radi li sve što piše u zadatku

2. Organizacija koda (25%)
- jesu li UI i provider odvojeni

3. Stanje i pohrana (20%)
- pravilno korištenje `Provider` i `SharedPreferences`

4. Korisničko iskustvo (15%)
- jasne poruke greške
- potvrda prije brisanja
- hrvatski jezik u sučelju