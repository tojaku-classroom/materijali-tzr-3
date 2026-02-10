# 📋 Rad s Datotekama u Javi

## 1. Upravljanje Popisom Knjiga (Serijalizacija)

**Specifikacija:**

Napravite program koji omogućava rad s popisom knjiga. Svaka knjiga ima svojstva: ID (int), naslov (String), autor (String), godina izdanja (int) i broj dostupnih primjeraka (int).

**Zahtjevi:**

- Kreirajte klasu `Knjiga` koja implementira `Serializable`
- U programu `GlavnaKnjige.java` kreirajte listu od najmanje 5 knjiga
- Spremite listu u datoteku `knjige.ser` pomoću serijalizacije
- Učitajte listu iz datoteke i ispišite sve knjige

**Dodatne mogućnosti:**
- Dodajte metodu koja pretražuje knjige po autoru
- Dodajte metodu koja smanjuje broj dostupnih primjeraka kada se knjiga posudi

---

## 2. Izvoz Statistike Prodaje u CSV Format (Tekstne Datoteke)

**Specifikacija:**

Napravite sustav za bilježenje dnevne prodaje koja se može izvesti u CSV format. Svaka prodaja bilježi: redni broj (int), ime proizvoda (String), cijenu (double), količinu (int) i ukupan iznos (double).

**Zahtjevi:**

- Kreirajte klasu `Prodaja` s relevantnim svojstvima
- U klasi `ProdajeDatoteke` napravite metodu `spremi()` koja zapisuje prodaje u `prodaje.csv` s razdjelnikom `;`
- Napravite metodu `ucitaj()` koja čita CSV datoteku i vraća listu prodaja
- Dodajte metodu `ispisProdaje()` koja prikazuje učitane podatke u konzoli

**Dodatne mogućnosti:**
- Izračunajte ukupnu prodaju iz datoteke
- Nađite proizvod s najvećom prodajom

---

## 3. Upravljanje Popisom Gledatelja u Kinu (Tekstne Datoteke)

**Specifikacija:**

Napravite program za upravljanje popisom gledatelja koji su kupili kartu. Svaki gledatelj ima svojstva: ID (int), ime i prezime (String), film (String), redak (int) i sjedalo (int).

**Zahtjevi:**

- Kreirajte klasu `Gledatelj` s relevantnim svojstvima
- U klasi `GledateljDatoteke` napravite metodu `spremi()` koja zapisuje gledatelje u `gledatelji.txt` s razdjelnikom `|`
- Napravite metodu `ucitaj()` koja čita datoteku i vraća listu gledatelja
- Ispišite sve gledatelje sortirane po imenu

**Dodatne mogućnosti:**
- Pronađite sve gledatelje koji gledaju određeni film
- Provjerite je li sjedalo već zauzeto
