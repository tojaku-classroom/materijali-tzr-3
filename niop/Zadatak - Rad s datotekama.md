## Zadatak 1 - Upravitelj bilješkama (tekstualna datoteka + parsiranje)

**Tema:** `java.io` (`BufferedWriter`, `BufferedReader`) i parsiranje reda teksta.

### Cilj
Napraviti konzolnu aplikaciju koja upravlja bilješkama i sprema ih u tekstualnu datoteku.

### Obavezne klase
- `hr.obskc.datoteke.biljeske.Aplikacija`
- `hr.obskc.datoteke.biljeske.Biljeska` (model, `Serializable`)
- `hr.obskc.datoteke.biljeske.TekstSpremanje`

### Funkcionalnosti
1. Konzolni izbornik:
- `1` Dodaj biljesku
- `2` Oznaci biljesku arhiviranom
- `3` Ispisi sve biljeske
- `4` Spremi u datoteku
- `5` Ucitaj iz datoteke
- `6` Napravi ZIP sigurnosnu kopiju
- `0` Izlaz

2. Bilješka ima polja:
- `id` (int)
- `naslov` (String)
- `sadrzaj` (String)
- `arhivirana` (boolean)

3. Spremanje i čitanje:
- Datoteka: `biljeske.txt`
- Format reda: `id|naslov|sadrzaj|arhivirana`
- Čitanje mora preskočiti prazne redove.

4. Postavke (`Properties`):
- Datoteka: `biljeske_postavke.properties`
- Ključevi: `apl.naziv`, `apl.verzija`, `apl.max_duzina_sadrzaja`
- Ako datoteka ne postoji, napraviti inicijalnu.
- Pri pokretanju ispisati naziv i verziju aplikacije.

5. Arhiviranje:
- Napraviti `biljeske_backup.zip`
- U ZIP staviti datoteku `biljeske.txt`.

### Napomena
Koristiti `try-with-resources` gdje god je moguće.

---

## Zadatak 2 - Upravitelj narudžbama (binarno spremanje objekata)

**Tema:** serijalizacija (`ObjectOutputStream`, `ObjectInputStream`).

### Cilj
Napraviti konzolnu aplikaciju za rad s narudžbama i spremanjem liste objekata u `.ser` datoteku.

### Obavezne klase
- `hr.obskc.datoteke.narudzbe.Aplikacija`
- `hr.obskc.datoteke.narudzbe.Narudzba` (model, `Serializable`)
- `hr.obskc.datoteke.narudzbe.ObjektSpremanje`

### Funkcionalnosti
1. Konzolni izbornik:
- `1` Dodaj narudzbu
- `2` Oznaci narudzbu isporucenom
- `3` Ispisi narudzbe
- `4` Spremi binarno
- `5` Ucitaj binarno
- `6` Napravi ZIP sigurnosnu kopiju
- `0` Izlaz

2. Narudžba ima polja:
- `id` (int)
- `kupac` (String)
- `iznos` (double)
- `isporuceno` (boolean)

3. Spremanje i čitanje:
- Datoteka: `narudzbe.ser`
- Spremiti/učitati cijelu `List<Narudzba>`.

4. Postavke (`Properties`):
- Datoteka: `narudzbe_postavke.properties`
- Ključevi: `apl.naziv`, `apl.verzija`, `valuta`, `max_narudzbi`
- Ako datoteka ne postoji, inicijalizirati je default vrijednostima.

5. Arhiviranje:
- Napraviti `narudzbe_backup.zip`
- U ZIP staviti `narudzbe.ser` i `narudzbe_postavke.properties`.

### Napomena
Kod učitavanja nakon uspjeha osvježiti `nextId` na `max(id)+1`.

---

## Zadatak 3 - Upravitelj termina (NIO API)

**Tema:** `java.nio.file` (`Path`, `Files.writeString`, `Files.readAllLines`, `Files.newInputStream`).

### Cilj
Napraviti konzolnu aplikaciju za evidenciju termina koristeći NIO pristup spremanju i čitanju.

### Obavezne klase
- `hr.obskc.datoteke.termini.Aplikacija`
- `hr.obskc.datoteke.termini.Termin` (model, `Serializable`)
- `hr.obskc.datoteke.termini.NioSpremanje`

### Funkcionalnosti
1. Konzolni izbornik:
- `1` Dodaj termin
- `2` Oznaci termin odradjenim
- `3` Ispisi termine
- `4` Spremi NIO
- `5` Ucitaj NIO
- `6` Napravi ZIP sigurnosnu kopiju
- `0` Izlaz

2. Termin ima polja:
- `id` (int)
- `naslov` (String)
- `datum` (String, npr. `2026-03-18`)
- `odradjen` (boolean)

3. Spremanje i čitanje:
- Datoteka: `termini_nio.txt`
- Format reda: `id;naslov;datum;odradjen`
- Koristiti `Files.writeString(...)` i `Files.readAllLines(...)`.

4. Postavke (`Properties`):
- Datoteka: `termini_postavke.properties`
- Ključevi: `apl.naziv`, `apl.verzija`, `timezone`, `datum.format`
- Učitavanje preko `Files.newInputStream(...)`.

5. Arhiviranje:
- Napraviti mapu `arhiva/` ako ne postoji.
- Napraviti `arhiva/termini_backup.zip`.
- U ZIP staviti `termini_nio.txt`.

### Napomena
Provjeriti postoji li datoteka prije čitanja (`Files.exists`).

---

## Jedinstveni kriteriji ocjenjivanja (za sva 3 zadatka)

1. Struktura i organizacija koda (model + aplikacija + spremanje/učitavanje).
2. Ispravan rad izbornika i osnovnih operacija.
3. Ispravno spremanje i učitavanje podataka traženim stilom.
4. Ispravno korištenje `Properties` (inicijalizacija i učitavanje).
5. Ispravna izrada ZIP sigurnosne kopije.
6. Obrada grešaka (`IOException`, loš unos korisnika).

## Predloženi raspored vremena (90 min)

1. 0-15 min: model klase + kostur izbornika.
2. 15-45 min: implementacija spremanja i učitavanja.
3. 45-65 min: `Properties` i inicijalne postavke.
4. 65-80 min: ZIP backup.
5. 80-90 min: testiranje i ispravci.
