Programski jezici su prošli kroz nekoliko faza razvoja, koje su se prilagođavale sve složenijim zahtjevima računalnih sustava i aplikacija. Dvije ključne prekretnice u povijesti programiranja bile su strukturirano programiranje koje koristi funkcije, te kasniji razvoj objektno orijentiranog programiranja (OOP). Između njih, jezik C odigrao je ključnu ulogu u oblikovanju oba pristupa te postao jedan od najvažnijih jezika u povijesti programiranja.

## Počeci programskih jezika

U ranim fazama računalstva, programi su se pisali pomoću strojnih jezika i asemblera, što je bilo vrlo zahtjevno i sklonije pogreškama. Prvi korak prema apstrakciji od hardvera bio je razvoj jezika visokog nivoa. Ovi jezici omogućili su pisanje programa na način koji je bliži ljudskom razmišljanju, a ne strojnim instrukcijama.

### Fortran (1957.) i COBOL (1959.)

- Fortran (FORmula TRANslation) bio je prvi široko korišteni jezik visokog nivoa, prvenstveno dizajniran za znanstvene izračune.
- COBOL (COmmon Business-Oriented Language) bio je usmjeren prema poslovnim aplikacijama i olakšao je razvoj velikih poslovnih programa.

Ovi jezici bili su proceduralni, što znači da su programi organizirani kao niz naredbi koje se izvršavaju slijedno i s vrlo ograničenom strukturom.

## Strukturirano programiranje i uloga funkcija

Tijekom 1960-ih i 1970-ih, programiranje je doživjelo značajan napredak s uvođenjem strukturiranog programiranja, koje je naglašavalo modularnost i jasnu organizaciju koda. Ključan alat u ovom pristupu bile su funkcije.

### Uloga funkcija

Funkcije omogućavaju rastavljanje programa na manje, ponovo iskoristive dijelove. One izvršavaju specifične zadatke unutar programa i mogu se pozivati iz različitih dijelova koda, čime olakšavaju ponovnu upotrebu koda, održavanje i testiranje.

Primjer programskog jezika koji je promovirao strukturirano programiranje bio je Algol (1960.), koji je uveo funkcije i blokove koda kao osnovne jedinice organizacije.

Pascal (1970.), dizajniran od strane Niklausa Wirtha, također je promicao strukturirano programiranje. Pascal je bio popularan u edukaciji jer je omogućavao modularno programiranje s naglaskom na funkcije, petlje i grananje. No, pravi preokret u razvoju programskih jezika donio je jezik C.

### C jezik i njegov utjecaj

C jezik (1972.), razvijen od strane Dennisa Ritchieja u Bell Labsu, imao je dubok i dugotrajan utjecaj na razvoj softvera. Stvoren kao jezik za razvoj Unix operacijskog sustava, C je kombinirao efikasnost asemblera s fleksibilnošću jezika visokog nivoa.

Ključne karakteristike C jezika:

- Efikasnost: C omogućava direktan pristup memoriji i upravljanje hardverskim resursima, što ga čini izuzetno brzim.
- Modularnost: C potiče organizaciju koda u funkcije, što je u skladu sa strukturiranim programiranjem.
- Prenosivost: Programi napisani u C jeziku mogu se lako prenositi između različitih računalnih sustava, što je bilo ključno za razvoj Unixa i softverskih sustava općenito.

C jezik u potpunosti podržava strukturirano programiranje putem funkcija. Programi u C-u se sastoje od funkcija, a glavna funkcija (main) kontrolira izvršavanje programa. Ovaj pristup omogućuje modularnost i bolju organizaciju koda, što je bio jedan od glavnih razloga popularnosti C jezika.

C je postao osnova za mnoge kasnije jezike, uključujući C++, Java, C#, i JavaScript. Svi ovi jezici naslijedili su osnovne sintaktičke elemente C jezika, poput korištenja zagrada za kontrolu blokova koda, sintaksu operatora i funkcijske strukture.

## Ograničenja proceduralnog programiranja i prelazak na OOP

Iako je C bio izuzetno moćan jezik, proceduralni pristup se pokazao ograničenim za vrlo složene aplikacije. Kako su aplikacije postajale složenije, postalo je sve teže pratiti interakcije između različitih dijelova programa. To je dovelo do razvoja objektno orijentiranog programiranja (OOP).

## Razvoj objektno orijentiranog programiranja (OOP)

Objektno orijentirano programiranje uvelo je ideju da bi podaci i funkcije trebali biti objedinjeni u jednu cjelinu – objekt. Ovaj pristup omogućava bolje organiziranje koda, jer svaki objekt može predstavljati stvarni entitet s podacima (atributima) i funkcionalnostima (metodama).

Ključni koncepti OOP-a:

- Klase i objekti: Klasa je predložak za stvaranje objekata, a objekt je instanca klase.
- Nasljeđivanje: Mogućnost da nove klase naslijede karakteristike postojećih klasa.
- Polimorfizam: Omogućava da se ista funkcija može koristiti za različite objekte.
- Enkapsulacija: Osigurava da su podaci objekta skriveni i dostupni samo putem definirane funkcionalnosti.

### C++: Spoj C jezika i OOP-a

C++ je bio nadogradnja na C jezik, koju je razvio Bjarne Stroustrup 1985. godine. C++ je zadržao sve karakteristike C jezika, uključujući njegovu efikasnost i moćno upravljanje memorijom, ali je dodao podršku za objektno orijentirano programiranje. To je omogućilo programerima da koriste najbolje od oba svijeta – proceduralni pristup s funkcijama i modularnost OOP-a.

C++ je postao vrlo popularan jer je omogućavao postupni prelazak iz proceduralnog u objektno orijentirano programiranje, čime je omogućio programerima veću fleksibilnost i organizaciju koda u složenim aplikacijama.

### Java i širenje OOP-a

Java (1995.) je dodatno popularizirala OOP pristup, kombinirajući ga s platformskom neovisnošću. Java je u potpunosti objektno orijentirana i eliminirala je mnoge složenosti prisutne u C++-u, poput ručnog upravljanja memorijom, što ju je učinilo pristupačnijom i sigurnijom za razvoj složenih aplikacija.

## Moderni jezici i C kao temelj

Mnogi moderni jezici, poput Python, C#, JavaScript, i Swift, preuzeli su ključne koncepte iz C jezika, uključujući njegovu sintaksu, korištenje funkcija i upravljanje resursima. Iako su razvijeni s različitim ciljevima, svi ovi jezici zadržali su trag C-a u svojim osnovnim principima.