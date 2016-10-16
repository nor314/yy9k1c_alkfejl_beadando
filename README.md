**Tanganyika sügéres akvárium**

Készítette: Bereczki Norbert

### **1. Követelményanalízis**

##### **1.1. Célkitűzés, projektindító dokumentum**

A program célja, átfogóbb ismereteket adni a Tanganyika-tó sügéri, mint díszállatok tartásáról egyoldali alkalmazás felhasználásával.  Lehetőség legyen böngészni, ill. ismerkedni az egyes típusokkal, fajtákkal, továbbá akváriumi tartásukról minimális információkat szerezni. Vendégként böngészni, regisztrálni, felhasználóként pedig bejelentkezni, hirdetést feladni, akváriumot összeállítani és vezetni az ismert halfajtákból.

###### **Funkcionális követelmények:**

- Regisztráció
- Bejelentkezés
- Csak vendégként elérhető funkciók
  - az ismert, listában szereplő halakkal való ismerkedés
  - keresés a listából
  - hirdetések böngészése
- Csak bejelentkezett felhasználók által elérhető (plusz) funkciók
  - saját akvárium létrehozása (benne az ismert sügérek összeválogatásával)
  - meglévő akvárium szerkesztése
  - meglévő akvárium törlésére
  - hirdetés kiírása/szerkesztése

###### **Nem funkcionális követelmények:**

- Hibás adat esetén jelzés, jól bevitt adatok maradjanak az űrlapban. A funkciók jelszóval védettek, és a jelszavak védelme a háttérben.
- Gyors működés
- Könnyű kezelhetőség/áttekintés, követhető elrendezés
- Bővíthetőség, fájlcsoportosítás

##### **1.2. Szakterületi fogalomjegyzék**

**Fajták: (táplálkozás ill. viselkedés –esetleg forma- alapján)**

- Algázók: Kis- és nagytestű, főleg algával, növényekkel, ill. növényi származékokkal táplálkoznak
- Csigasügérek: leginkább mindenevő halfajok csoportja, jellegzetességük, hogy üres csigaházakban élnek és szaporodnak
- Homoki sügérek: főleg mindenevők, jellemzően talajlakó sügérfajták
- Kis testű ikrázók: formailag és táplálkozásban változatok, általában 10 cm alatti egyéb sügérfélék
- Lazacsügérek: könnyen elkülöníthető, vegyes táplálkozású, formailag inkább egységes halfajok
- Ragadozók: formában, színekben, méretben változatos, húsevő tanganyikai sügérfajok

##### **1.3. Használatieset-modell, funkcionális követelmények**

**Vendég**  : Csak a publikus oldalakat éri el

- Főoldal
- Bejelentkezés
- Regisztráció
- Keresés
- Globális lista, ill. halak böngészése

**Bejelentkezett felhasználó**  : plusz funkciókhoz is hozzáférhet

- Új akvárium felvétele (halak hozzáadása lista formájában)
- Meglévő akvárium törlése
- Meglévő akvárium szerkesztése
- Új (esetleg nem ismert, ill. kimaradt) sügérfaj felvétele a központi listába: jó admin esetén nem jellemző
- Hirdetés feladása

Vegyünk példának egy egyszerű folyamatot:

![](docs/images/folyamatabra.jpg)

**Meglévő akvárium szerkesztése:**

1. A felhasználó az oldalra érkezve, bejelentkezik vagy regisztrál
2. Regisztráció után megtekintheti a halait listázó oldalt, tehát a saját akváriumát ahol kiválaszthatja a szerkeszteni kívánt halat.
3. Megtekint, majd szerkeszt.
4. Szerkesztés oldalon felviszi az új adatokat
5. Beküldés gombra kattintva elmenti a változásokat

### **2. Tervezés**

##### **2.1. Architektúra terv**

###### **2.1.1. Adatmodell:**

![](docs/images/dbmodel.png.jpg)

###### **2.1.2. Oldaltérkép:**

**Publikus:**

- Főoldal
- Bejelentkezés
- Regisztráció
- Keresés

**Bejelentkezett:**

- Főoldal
- Új hal felvétele a saját akváriumba
- Listaoldal (vezetett akvárium és a benne lévő halakról)
  -
    - Törlés
    - Halak hozzáadása/törlése
    - Hozzászólás vagy hirdetés létrehozása/szerkesztése

###### **2.1.3. Végpontok**

- GET/: főoldal
- GET/advert: hirdetések oldal
- GET/login: bejelentkezés
- POST/login: bejelentkező adatok felküldése
- GET/login/signup: regisztráció
- POST/login/signup: regisztrációs adatok felküldése
- GET/logout: kijelentkezés
- GET/profile: profiladatok
- GET/aquarium/list: saját akváriumi halak listája oldal
- GET/aquarium/create: új akvárium létrehozása
- GET/chiclid/id: sügér adatok
- POST/chiclid/create: új sügér felvitele
- POST/advert/create: új hirdetés feladása

##### **2.2. Felhasználói-felület modell**

###### **2.2.1.Oldalvázlatok:**

**Főoldal**

![](docs/images/Home_page.jpg)

**Regisztrációs oldal**

![](docs/images/Registration_page.jpg)

**Profil oldal**

![](docs/images/Profile_page.jpg)

**User oldal**

![](docs/images/User_page.jpg)

**Sügér adatok**

![](docs/images/Chiclid_page.jpg)
