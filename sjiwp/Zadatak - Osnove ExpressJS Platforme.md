# Osnove ExpressJS Platforme

Napraviti aplikaciju baziranu na ExpressJS platformi za stvaranje, pregled i brisanje entiteta ovisno o grupi. Aplikacija koristi PouchDB/LevelDB bazu podataka. Koristiti CSS za definiciju izleda aplikacije.

## Grupa A: Popis knjiga
- Entitet: Knjiga
- Polja:
    - id (timestamp)
    - naslov (tekst)
    - autor (tekst)
    - godinaIzdanja (broj)
    - zanr (tekst)


## Grupa B: Kolekcija filmova
- Entitet: Film
- Polja:
    - id (timestamp)
    - naslov (tekst)
    - redatelj (tekst)
    - godina (broj)
    - ocjena (broj)


## Grupa C: Recepti za kuhanje
- Entitet: Recept
- Polja:
    - id (timestamp)
    - naziv (tekst)
    - opis (tekst)
    - sastojci (duži tekst)
    - vrijemePripreme (broj)


## Grupa D: Školski događaji
- Entitet: Dogadaj
- Polja:
    - id (timestamp)
    - naziv (tekst)
    - lokacija (tekst)
    - brojSudionika (broj)
    - opis (tekst)