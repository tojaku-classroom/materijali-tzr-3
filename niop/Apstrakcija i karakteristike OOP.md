**Apstrakcija** je jedna od temeljnih karakteristika **objektno-orijentiranog programiranja (OOP)**, koja omogućuje skrivanje složenosti i izlaganje samo onih dijelova sustava koji su ključni za korisnika. Apstrakcija omogućava fokusiranje na bitne karakteristike objekata, skrivajući nevažne detalje.

U kontekstu OOP-a, apstrakcija se koristi za definiranje **sučelja** (interface) ili **apstraktnih klasa** koje specificiraju što objekt može raditi, bez definiranja **kako** to radi. Ona omogućuje stvaranje složenih sustava s jednostavnijim interakcijama, gdje korisnik radi s apstraktnim modelom objekata, a detalji implementacije ostaju skriveni.

### Primjer apstrakcije:

Ako imate klasu **Automobil**, apstrakcija bi mogla definirati što automobil može raditi (npr. `vozi()`, `zaustavi()`), ali ne bi specificirala kako se te funkcije implementiraju. Korisnik klase ne mora znati detalje o motoru ili mehanici kočenja da bi koristio te funkcije.

```java
abstract class Automobil {
    abstract void vozi();
    abstract void zaustavi();
}
```

Konkretne klase (npr. **ElektričniAutomobil** ili **DizelskiAutomobil**) nasljeđuju ovu apstraktnu klasu i implementiraju specifične detalje.

Apstrakcija u OOP-u usko je povezana s ostalim ključnim principima objektno-orijentiranog programiranja: **nasljeđivanjem**, **enkapsulacijom** i **polimorfizmom**.

### **Nasljeđivanje**

Nasljeđivanje omogućava stvaranje novih klasa koje preuzimaju atribute i metode postojećih klasa. Klase često koriste nasljeđivanje jer definiraju opće funkcionalnosti koje specifične podklase mogu naslijediti i nadjačati ili proširiti prema svojim specifičnim potrebama.

Primjer:

```java
class ElektričniAutomobil extends Automobil {
    void vozi() {
        System.out.println("Električni automobil vozi tiho.");
    }
    void zaustavi() {
        System.out.println("Električni automobil se zaustavlja regenerativnim kočenjem.");
    }
}
```

### **Enkapsulacija**

Enkapsulacija je princip koji omogućava skrivanje unutarnjih detalja klase i izlaganje samo onih metoda i atributa koji su relevantni za vanjski svijet. Ona osigurava kontrolu pristupa podacima klase.

Primjer:

```java
class Automobil {
    private int brzina;  // Skriveni atribut
    public void vozi() {
        System.out.println("Automobil se kreće.");
    }
}
```

U ovom primjeru, `brzina` je enkapsulirana i dostupna je samo kroz javne metode klase.

### **Polimorfizam**

Polimorfizam omogućava korištenje istih metoda na različite načine, ovisno o specifičnoj implementaciji u naslijeđenim klasama. To znači da objekti različitih klasa mogu reagirati na iste metode na različite načine.

Primjer:

```java
Automobil auto = new ElektričniAutomobil();
auto.vozi();  // Ispisat će: Električni automobil vozi tiho.

```

U ovom primjeru, polimorfizam omogućuje da metoda `vozi()` bude pozvana na objektu tipa `Automobil`, ali da izvrši specifičnu implementaciju klase `ElektričniAutomobil`.

Svi ovi principi zajedno čine OOP sustave fleksibilnima, skalabilnima i lakšima za održavanje.