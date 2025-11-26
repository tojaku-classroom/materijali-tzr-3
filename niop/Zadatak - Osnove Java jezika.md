# Osnove Java jezika – zadaci za vrednovanje

## Slučajni niz – min, max i granice
Napiši program koji:
- Napravi cjelobrojni niz dužine `10`.
- Popuni ga slučajnim brojevima (1 – 100) pomoću `Math.random()`.
- Ispiši najmanji i najveći element.
- Uhvati iznimku ako pokušaš ispisati 11. element.

**Zahtjevi koje mora pokriti**: `Math.random()`, pristup elementu, `try-catch`, `ArrayIndexOutOfBoundsException`.

---

## Višestruko hvatanje iznimki
Proširi prethodni zadatak tako da uhvatiš:
- `ArrayIndexOutOfBoundsException` (pogrešan indeks) i  
- `ArithmeticException` (dijeljenje s nulom).
- U `finally` ispiši „Završena obrada niza.“

---

## Riječi dok ne stigne „kraj“
Koristeći `Scanner` i `ArrayList<String>`:
- Učitavaj riječi dok korisnik **ne upiše** „kraj“ (case-insensitive).
- Ispiši koliko je ukupno riječi i duljinu najduže riječi.

*Pomoć:* `equalsIgnoreCase("kraj")`.

---

## Ispis unazad pomoću `ListIterator`
**Bonus zadatak, potrebno istraživanje.**
Proširi prethodni zadatak tako da:  
- Kada korisnik završi unos, ispiši sve riječi **od zadnje prema prvoj** koristeći `ListIterator`.

*Pomoć:* `list.listIterator(list.size())` i `hasPrevious()`.

---

## Zamjena „dan“ → „večer“ i usporedba stringova
- Učitaj cijeli redak teksta.
- Zamijeni svaki podstring „dan“ riječi „večer“.
- Ispiši:
   - novi string
   - rezultat usporedbe `==` original vs. novi
   - rezultat `equals`

---

## Loto 6 od 50
- Generiraj 6 **različitih** slučajnih cijelih brojeva između 1 i 50.
- Spremi ih u `ArrayList<Integer>` (provjeri `contains` prije `add`).
- Ispiši sortiranu listu.

---

## Parsiranje i zbroj brojeva iz stringa
- Učitaj redak npr. „a 3 b 4 c 5“.
- „Isparsiraj“ sve što je cijeli broj (`Scanner` ili `Character.isDigit`) i zbroji.
- Ispiši sumu ili „Nema brojeva“.

---

## 3×3 matrica – dijagonala
- Kreiraj i popuni matricu 3×3 slučajnim 0/1.
- Ispiši ju redak-po-redak `for` petljom.
- Izračunaj i ispiši sumu **glavne dijagonale**.

---

## Statistika riječi
- Učitaj redak, podijeli na riječi (`split` ili `Scanner`).

Ispiši:
- koliko riječi duljine ≥ 5  
- broj jedinstvenih riječi (koristi `HashSet`)  
- najdulju riječ.

---

## Mini-kviz s iznimkama
- U dva `ArrayList`-a spremi 4 pitanja i 4 točna (cijela) odgovora.
- Postavi pitanja, učitaj `int` odgovor.
- Uhvati `InputMismatchException` ako korisnik unese slovo i ponovi upit.
- Ispiši rezultat npr. „Osvojio si 3/4“.

---

### Dodatne upute za učenike 
- Za iznimke **obavezno** ispisati vlastitu poruku (ne samo `toString` ili `getMessage`).