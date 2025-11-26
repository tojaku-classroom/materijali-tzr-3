### Grupa A: Sustav za upravljanje knjigama u knjižnici

**Opis:** Kreirajte sustav za upravljanje knjigama u knjižnici. Napravite klasu `Knjiga` koja sadrži osnovne informacije o knjizi, a zatim izvedene klase za različite žanrove.

**Zahtjevi:**

1. Klasa `Knjiga` treba imati atribute `naslov` (tipa `String`) i `autor` (tipa `String`).
2. Iz klase `Knjiga` izvedite podklase `Roman` i `Strip`, gdje:
    - `Roman` ima dodatni atribut `zanr` (tipa `String`).
    - `Strip` ima dodatni atribut `serija` (tipa `String`) koja predstavlja seriju stripova kojoj pripada.
3. Omogućite korisniku unos podataka za više knjiga različitih tipova.
4. Pohranite knjige u `ArrayList` i ispišite podatke o svim knjigama.

**Dodatni izazov za ocjenu:**

- Dodajte klasu `Osoba` koja sadrži podatke o korisnicima (ime i prezime) i proširite klasu `Knjiga` metodom `posudiKnjigu(Osoba korisnik)` koja povezuje knjigu s korisnikom. Ispišite podatke o knjigama, uključujući ime i prezime osobe koja ih je posudila.

---

### Grupa B: Sustav za praćenje ljubimaca u veterinarskoj ordinaciji

**Opis:** Kreirajte sustav za praćenje ljubimaca u veterinarskoj ordinaciji. Napravite klasu `Ljubimac` koja sadrži osnovne podatke o ljubimcu, a zatim izvedene klase za različite vrste ljubimaca.

**Zahtjevi:**

1. Klasa `Ljubimac` treba imati atribute `imeLjubimca` (tipa `String`) i `godine` (tipa `int`).
2. Izvedite podklase `Pas` i `Mačka` iz klase `Ljubimac`, gdje:
    - `Pas` ima dodatni atribut `pasmina` (tipa `String`).
    - `Mačka` ima dodatni atribut `omiljenaIgračka` (tipa `String`).
3. Omogućite unos podataka o više ljubimaca različitih tipova i pohranite ih u `ArrayList`.
4. Ispišite podatke o svim ljubimcima.

**Dodatni izazov za ocjenu:**

- Dodajte klasu `Osoba` koja sadrži podatke o vlasnicima (ime i prezime) i proširite klasu `Ljubimac` metodom `dodijeliVlasnika(Osoba vlasnik)` koja povezuje ljubimca s vlasnikom. Ispišite podatke o ljubimcima, uključujući ime i prezime vlasnika.