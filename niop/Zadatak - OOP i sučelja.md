## Opis zadatka

Napravite sustav za upravljanje prodavaonicom automobila koji omogućuje dodavanje, brisanje i pretraživanje automobila. Automobili mogu biti različitih vrsta (npr. osobni automobili, kamioni, motocikli). Sustav treba omogućiti i prodaju automobila kupcima.

## Zahtjevi

- **Nasljeđivanje**: Stvorite apstraktnu klasu Automobil s osnovnim atributima (marka, model, godina proizvodnje, cijena, registracija) i izvedene klase OsobniAutomobil, Kamion i Motocikl koje nasljeđuju Automobil.
- **Sučelja**: Stvorite sučelje Prodaja s metodom prodaj() koje će implementirati klase OsobniAutomobil, Kamion i Motocikl.
- **Polimorfizam**: Koristite polimorfizam za dodavanje različitih vrsta automobila u ArrayList.
- **Učahurivanje**: Koristite učahurivanje za skrivanje detalja implementacije prodaje automobila.
- **ArrayList**: Koristite ArrayList za pohranu automobila.
- **Obrada iznimaka**: Implementirajte obradu iznimaka za slučajeve kada se pokuša prodati automobil koji ne postoji u prodavaonici ili kada se pokuša dodati automobil s istom registracijskom oznakom.