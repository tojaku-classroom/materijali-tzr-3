## Povijesni razvoj

**HTML (HyperText Markup Language)** ima ključnu ulogu u razvoju weba. Njegova povijest započinje krajem 1980-ih, a evoluirala je kroz nekoliko značajnih verzija, prilagođavajući se novim tehnologijama i potrebama interneta.

### **Početak - HTML 1.0 (1991-1995)**

HTML je razvijen od strane **Tima Berners-Leeja** 1991. godine u CERN-u kako bi omogućio razmjenu informacija putem interneta. Prva verzija HTML-a bila je vrlo jednostavna, sadržavala je osnovne elemente za formatiranje teksta (naslove, odlomke, popise, linkove) te slike i hiperveze.

### **HTML 2.0 (1995)**

HTML 2.0 standardiziran je 1995. godine od strane IETF-a (Internet Engineering Task Force). Ova verzija uključivala je sve funkcije iz prvog HTML-a, uz dodatne značajke poput obrazaca za unos podataka (tekstualna polja, gumbe).

### **HTML 3.2 (1997)**

Razvoj weba ubrzao se, a HTML 3.2, koji je standardizirala **W3C** (World Wide Web Consortium), uveo je tablice, složenije obrasce, podršku za stilove (CSS) i osnovne elemente za multimediju poput ugrađenih objekata.

### **HTML 4.01 (1999)**

HTML 4.01 bila je ključna verzija jer je uvela podršku za **CSS** i **JavaScript**, čime je omogućeno odvajanje strukture, stila i ponašanja web stranica. Uvedeni su i atributi poput `id` i `class` koji su omogućili preciznije stiliziranje i interakcije.

### **XHTML (2000)**

XHTML je pokušaj standardizacije HTML-a na temelju **XML-a**. Cilj je bio uvesti strožu sintaksu, ali široka primjena HTML 4.01 nastavila se jer je bio jednostavniji za korištenje.

### **HTML5 (2014)**

HTML5 je najveća modernizacija jezika i postao je službeni standard 2014. godine. Uvedene su značajke za multimediju (video, audio), napredne grafičke elemente (Canvas, SVG), kao i API-je za interaktivne web aplikacije (geolokacija, pohrana podataka). HTML5 također pojednostavljuje sintaksu i uklanja zastarjele elemente poput `<font>`.

## HTTP i HTTPS protokoli

### **HTTP (HyperText Transfer Protocol)**

**HTTP** je protokol koji se koristi za prijenos podataka na webu. Njegova glavna svrha je omogućiti **komunikaciju između klijenta** (najčešće web preglednika) i **servera**. Klijent šalje zahtjev za određenim resursom (npr. web stranica, slika), a server vraća odgovor s traženim podacima. Model komunikacije je, prema tome, klijent-poslužitelj.

### Osnovne značajke HTTP-a

1. ***Stateless***: HTTP ne pamti stanje između različitih zahtjeva i odgovora. Svaki zahtjev neovisno dolazi i vraća podatke bez pamćenja prethodnih interakcija.
2. HTTP koristi različite **metode** za rad s podacima:
    - **GET**: Dohvaća podatke (npr. prikaz web stranice).
    - **POST**: Šalje podatke (npr. unos podataka u obrazac i slanje na server).
    - **PUT**: Ažurira podatke.
    - **DELETE**: Briše podatke.
3. **Port**: HTTP koristi **port 80** za komunikaciju.

### Način funkcioniranja

1. **Zahtjev klijenta**: Kada korisnik unese URL u preglednik, preglednik šalje HTTP zahtjev serveru.
2. **Odgovor servera**: Server obrađuje zahtjev i vraća odgovarajući odgovor, koji može uključivati HTML stranicu, sliku, video ili druge podatke.
3. **Prijenos podataka u otvorenom tekstu**: Podaci se prenose u **otvorenom tekstu**, što znači da su ranjivi na prisluškivanje ili napade treće strane.

### **HTTPS (HyperText Transfer Protocol Secure)**

**HTTPS** je sigurnija verzija HTTP-a koja koristi **SSL/TLS** enkripciju za zaštitu podataka tijekom prijenosa. HTTPS štiti povjerljive podatke poput lozinki, osobnih podataka i informacija o plaćanju, osiguravajući privatnost i integritet podataka.

### Osnovne značajke HTTPS-a

1. HTTPS koristi **SSL (Secure Sockets Layer)** ili **TLS (Transport Layer Security)** protokol za enkripciju podataka.
2. HTTPS koristi **digitalne certifikate** kako bi osigurao da se klijent povezuje s pravim serverom, sprječavajući "man-in-the-middle" napade.
3. Enkripcija osigurava da podaci nisu promijenjeni ili ugroženi tijekom prijenosa.
4. HTTPS koristi **port 443** za sigurnu komunikaciju.

## Primjeri HTTP zahtjeva i odgovora

### **HTTP Zahtjev (Request)**

Ovo je primjer jednostavnog **GET** zahtjeva kojim klijent traži resurs (npr. HTML stranicu) s poslužitelja:

```
GET /index.html HTTP/1.1
Host: www.example.com
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64)
Accept: text/html
Connection: keep-alive
```

- **GET**: Metoda koja traži resurs (u ovom slučaju `index.html`).
- **Host**: Domen koji klijent pokušava kontaktirati.
- **User-Agent**: Informacija o pregledniku klijenta.
- **Accept**: Tip sadržaja koji klijent želi primiti (u ovom slučaju `text/html`).
- **Connection**: Način upravljanja vezom (ovdje je "keep-alive" što znači da klijent želi zadržati vezu otvorenom).

### **HTTP Odgovor (Response)**

Primjer odgovora servera na gore navedeni zahtjev:

```
HTTP/1.1 200 OK
Date: Mon, 20 Sep 2023 12:00:00 GMT
Server: Apache/2.4.1 (Unix)
Content-Type: text/html
Content-Length: 1234

<html>
<head><title>Naslov</title></head>
<body>
    <h1>Dobrodošli na našu stranicu!</h1>
    <p>Ovo je primjer HTML sadržaja.</p>
</body>
</html>
```

- **200 OK**: Statusni kod koji označava da je zahtjev uspješno obrađen.
- **Date**: Vrijeme odgovora servera.
- **Server**: Informacije o softveru servera (u ovom slučaju Apache).
- **Content-Type**: Tip sadržaja u odgovoru (`text/html`).
- **Content-Length**: Duljina tijela odgovora (ovdje 1234 bajta).

### Najčešći HTTP statusni kodovi i fraze

Statusni kodovi su dio odgovora servera i opisuju rezultat obrade zahtjeva. Podijeljeni su u 5 glavnih kategorija:

### **1xx - Informativni odgovori**

- **100 Continue**: Klijent može nastaviti s slanjem zahtjeva.
- **101 Switching Protocols**: Server prihvaća promjenu protokola.

### **2xx - Uspješni odgovori**

- **200 OK**: Zahtjev je uspješno obrađen.
- **201 Created**: Zahtjev je uspješno obrađen, a novi resurs je kreiran.
- **204 No Content**: Uspješan zahtjev, ali bez tijela odgovora.

### **3xx - Preusmjeravanje**

- **301 Moved Permanently**: Traženi resurs je trajno premješten na novu adresu.
- **302 Found**: Resurs je privremeno premješten.
- **304 Not Modified**: Resurs nije promijenjen (koristi se za keširanje).

### **4xx - Pogreške na strani klijenta**

- **400 Bad Request**: Server nije mogao obraditi zahtjev zbog pogreške u sintaksi.
- **401 Unauthorized**: Autentifikacija je potrebna, ali nije osigurana.
- **403 Forbidden**: Server razumije zahtjev, ali ga odbija obraditi.
- **404 Not Found**: Traženi resurs nije pronađen na serveru.

### **5xx - Pogreške na strani servera**

- **500 Internal Server Error**: Došlo je do greške na serveru.
- **502 Bad Gateway**: Server, koji djeluje kao gateway, primio je nevaljan odgovor od uzlaznog servera.
- **503 Service Unavailable**: Server je trenutno nedostupan (npr. zbog preopterećenja ili održavanja).