## Zadatak

Potrebno je izraditi vlastitu web aplikaciju u Node.js okruženju koristeći iste ili vrlo slične obrasce kao u prikazanom oglednom projektu.

Od učenika se očekuje da naprave novi projekt s drugom tematikom, ali sa sličnom arhitekturom i osnovnim funkcionalnostima:

- Express aplikacija s odvojenim rutama
- Handlebars prikazi
- SQLite baza podataka
- autentifikacija korisnika
- rad sa sesijama
- CRUD operacije nad glavnim entitetom aplikacije
- validacija unosa na poslužiteljskoj strani

## Cilj zadatka

Cilj je pokazati da učenik razumije kako samostalno izraditi manju web aplikaciju s prijavom korisnika, bazom podataka, obrascima, prikazima i osnovnim pravilima pristupa podacima.

## Obavezni funkcionalni zahtjevi

Svaki projekt mora sadržavati sljedeće cjeline:

### 1. Korisnički računi

- registracija korisnika
- prijava korisnika
- odjava korisnika
- spremanje lozinke u hashiranom obliku

### 2. Rad sa sesijama

- nakon prijave korisnik ostaje prijavljen kroz sesiju
- neprijavljeni korisnik ne smije pristupiti zaštićenim stranicama
- prijavljeni korisnik treba imati pristup samo svojim podacima

### 3. Glavni entitet aplikacije

Projekt mora imati jedan glavni entitet nad kojim korisnik radi CRUD operacije.

Nad glavnim entitetom potrebno je omogućiti:

- prikaz popisa zapisa
- dodavanje novog zapisa
- uređivanje postojećeg zapisa
- brisanje zapisa

### 4. Prikazi i obrasci

- naslovnica
- stranica za prijavu
- stranica za registraciju
- stranica s popisom glavnih zapisa
- forma za unos novog zapisa
- forma za uređivanje zapisa

### 5. Validacija i zaštita pristupa

- obavezna polja moraju se provjeravati na poslužiteljskoj strani
- neispravan unos mora prikazati jasnu poruku korisniku
- korisnik ne smije moći uređivati ili brisati tuđe podatke

## Tehnički zahtjevi

- koristiti Express kao web platformu
- koristiti Handlebars za prikaze
- koristiti SQLite kao bazu podataka
- koristiti parametrizirane SQL upite
- organizirati kod u više datoteka, npr. rute, pomoćne funkcije i prikazi
- koristiti middleware gdje ima smisla, primjerice za autentifikaciju ili pristup bazi
- koristiti postojeći ili vrlo sličan način organizacije projekta kao u oglednom primjeru

## Ponuđene teme

## Tema 1: Knjige koje želim pročitati

### Opis

Izraditi aplikaciju u kojoj korisnik vodi vlastiti popis knjiga.

### Glavni entitet

Knjiga

### Obavezna polja

- naslov knjige
- autor
- kratki opis
- status, na primjer: planiram čitati, čitam, pročitano

### Obavezne funkcionalnosti

- korisnik može dodati novu knjigu
- korisnik može vidjeti svoj popis knjiga
- korisnik može urediti podatke o knjizi
- korisnik može obrisati knjigu
- korisnik vidi status svake knjige

### Primjeri dodatnih mogućnosti (za dodatnu ocjenu)

- filtriranje po statusu
- pretraga po naslovu ili autoru
- označavanje omiljenih knjiga

## Tema 2: Evidencija osobnih troškova

### Opis

Izraditi aplikaciju u kojoj korisnik vodi evidenciju svojih troškova.

### Glavni entitet

Trošak

### Obavezna polja

- naziv troška
- iznos
- datum
- kategorija, na primjer: hrana, prijevoz, režije, zabava

### Obavezne funkcionalnosti

- korisnik može dodati novi trošak
- korisnik može pregledati svoj popis troškova
- korisnik može urediti postojeći trošak
- korisnik može obrisati trošak
- korisnik vidi osnovne podatke o svakom trošku

### Primjeri dodatnih mogućnosti (za dodatnu ocjenu)

- filtriranje po kategoriji
- izračun ukupnog iznosa svih troškova
- prikaz troškova za odabrani mjesec

## Tema 3: Dnevnik treninga

### Opis

Izraditi aplikaciju u kojoj korisnik prati svoje treninge.

### Glavni entitet

Trening

### Obavezna polja

- naziv treninga
- datum
- trajanje
- bilješka ili opis

### Obavezne funkcionalnosti

- korisnik može dodati novi trening
- korisnik može pregledati svoj popis treninga
- korisnik može urediti postojeći trening
- korisnik može obrisati trening
- korisnik vidi osnovne podatke o svakom treningu

### Primjeri dodatnih mogućnosti (za dodatnu ocjenu)

- filtriranje po datumu
- označavanje vrste treninga
- prikaz ukupnog trajanja treninga

## Što se predaje

- izvorni kod projekta - GitHub repozitorij na vlastitom korisničkom računu
- kratka dokumentacija u Markdown formatu - dio projekta

Dokumentacija mora sadržavati:

- naziv projekta
- odabranu temu
- opis funkcionalnosti
- opis strukture baze podataka
- popis ruta
- upute za pokretanje

## Kriteriji vrednovanja

### Funkcionalnost

- aplikacija se može pokrenuti bez rušenja
- registracija i prijava rade ispravno
- CRUD nad glavnim entitetom radi ispravno
- podaci su odvojeni po korisnicima

### Organizacija koda

- kod je pregledan i logično raspoređen
- rute, prikazi i pomoćne funkcije nisu pomiješani u jednoj datoteci
- koriste se razumljivi nazivi varijabli i funkcija

### Baza podataka

- tablice i stupci imaju smisla u odnosu na temu
- upiti su ispravni i parametrizirani

### Korisničko sučelje

- stranice su pregledne i upotrebljive
- obrasci imaju jasne oznake i poruke o greškama

### Razumijevanje rješenja

- učenik zna objasniti kako rade rute, sesije i baza
- učenik zna objasniti kako je zaštitio pristup podacima

## Minimalni uvjeti za prolaznu ocjenu

- projekt koristi Express, Handlebars i SQLite
- postoji registracija, prijava i odjava korisnika
- postoji najmanje jedan glavni entitet s CRUD operacijama
- prijavljeni korisnik vidi i mijenja samo svoje podatke
- projekt ima osnovnu dokumentaciju i može se pokrenuti