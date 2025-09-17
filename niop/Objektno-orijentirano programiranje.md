Ideja objektno-orijentiranog programiranja nastala je analiziranjem načina na koji funkcionira stvarni svijet. Osnova ovog pristupa su objekti. Objekt sadrži podatake i operacije pomoću kojih će se manipulirati podaci. Uz navedeno, objekt skriva implementaciju (programski kod) od korisnika. Niz operacija koje objekt daje na raspolaganje nazivamo sučeljem (engl. interface). Sučelje predstavlja svojevrsni ugovor između objekta i korisnika tog objekta. Objekt koji poštuje ugovor jamči postojanje operacija i način njihova ponašanja. Objekt se "iznutra" može promijeniti bez utjecaja na korisnike tog objekta ukoliko se sučelje ne mijenja.

Objektno-orijentirani princip ne bi bio koristan kada bi se svaki pojedini objekt morao zasebno graditi. Mora postojati način da se taj proces automatizira na način da se stvori jedan nacrt i da se na temelju tog nacrta brzo i efikasno proizvode ili instanciraju objekti. Ovdje dolaze na scenu klase (engl. class). Slikovito možemo reći da je klasa tvornica za masovnu proizvodnju objekata određene vrste. Programer piše klasu koja sadrži nacrt željenog tipa objekta. U klasi definiramo njeno stanje kao niz podatkovnih članova odnosno jednostavnije rečeno varijabli, nakon čega definiramo niz operacija koje možemo provoditi nad objektima klase koje nazivamo funkcijskim članovima ili metodama (engl. methods). Prilikom pisanja klase moramo odrediti i prava pristupa nad pojedinim članovima što se vrši upotrebom specifikatora prava pristupa.

Svaki član može imati jedan od tri moguća načina pristupa:

- Javni (engl. public) - javnom članu mogu pristupiti svi.
- Privatni (engl. private) - privatnom članu mogu pristupiti samo članovi iste klase.
- Zaštićeni (engl. protected) - zaštićenom članu mogu pristupiti samo članovi iste klase i članovi naslijeđenih klasa.

U nekim je slučajevima potrebno dijeliti podatke između objekata iste klase. To se može ostvariti statičkim podatkovnim ili funkcijskim članovima ili drugim rječima članovima klase. Statički članovi su zajednički za sve objekte neke klase. Oni su slični globalnim varijablama s tom razlikom što su njihova imena vidljiva isključivo iz područja klase, te se podvrgavaju pravilima pristupa. Svi ostali članovi koji nisu statički nazivaju se članovima instance. Za stvaranje statičkih članova koristi se posebna naredba, a obično se radi o naredbi static.

Kada program treba novu instancu nekog objekta, tražit će od odgovarajuće klase da mu je ona napravi. Klasa će alocirati potreban memorijski prostor za varijable toga objekta i poslat će novonastali objekt. Svaki novonastali objekt zna od koje je klase nastao, tako da kad program pozove neku njegovu operaciju, može pogledati u klasu što treba napraviti da bi izvršio traženu operaciju. Kada je klasa jednom definirana, može se pomoću nje konstruirati neograničen broj objekata. Stvaranje i uništenje objekata je u praksi zadatak specijaliziranih metoda koje su dio klase. Kada se objekt stvori, potrebno mu je dati početni oblik što se definira konstruktorom klase. Kada objekt više nije potreban, posebna metoda klase pod imenom destruktor zadužena je za uništenje objekta.

U sljedećem odjeljku sažet ćemo ključne razlike i odnose između klase i objekta.

```
Klasa = nacrt, predložak za objekte
Klasa = tvornica objekata
Klasa = sadrži popis podatkovnih i funkcijskih članova (metoda)
```

```
Objekt = stvara se na temelju klase
Objekt = instanca klase
Objekt = ima svoje stanje koje se mijenja pod utjecajem poziva metoda (izvana ili iznutra)
Objekti su u međusobnoj interakciji i surađuju u postizanju cilja aplikacije
```

### Karakteristike OOPa

Objedinjavanje javnog sučelja klase i implementacije (programskog koda) naziva se učahurivanje ili enkapsulacija (engl. encapsulation). Drugim rječima, sve što je potrebno da bi klasa funkcionirala kao jedna logička cjelina učahureno je unutar klase.

Nasljeđivanje znači uzeti sučelje jednog objekta i nadograditi, proširiti ga s novim operacijama. Nasljeđivanje se postiže pisanjem nove klase koju deklariramo kao podklasu (engl. subclass) neke već postojeće klase. Klasa od koje nasljeđujemo, tj. polazna klasa zove se nadklasa (engl. superclass). Podklasa uvijek nasljeđuje kompletno sučelje nadklase, može prošriti sučelje novim operacijama, ali ne može izbrisati već postojeće operacije. Podklasa nasljeđuje, osim deklaracije operacija, i implementaciju navedenih operacija. No, ovdje podklasa ima otvorene ruke i može definirati novu implementaciju za postojeće operacije što nazivamo nadjačavanjem (engl. overriding). Programer može po izboru neke operacije nadjačati novom implementacijom, a one koje ne nadjača, ostat će iste kao kod nadklase.

Mogućnost promatranja objekta kroz različite klase u stablu nasljeđivanja se zove polimorfizam (engl. polymorphism).