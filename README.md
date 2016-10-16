#
# Dokumentáció

**Matracbolt raktár bevételezés**

Készítette: Tóth Andrea

***1. Követelményanalízis***

**1.1. Célkitűzés, projektindító dokumentum**

A program legfőbb célja jól átláthatóan, és érthetően megjeleníteni a bolt raktárában megtalálható különböző matracokat és tulajdonságaikat egy webes vastagkliens, azaz egyoldali alkalmazás felhasználásával Az adatok védelme érdekében legyen lehetőség regisztrációra, majd bejelentkezésre. A bejelentkezett felhasználó a matracok listáját megtekintheti, bővítheti, meglévő elemeket törölhet illetve módosíthat, kommentálhat.

*Funkcionális követelmények:*

- Regisztrációra
- Bejelentkezés
- Csak bejelentkezett felhasználók által elérhető funkciók
  - Új matrac felvételére a listába
  - A meglévő matracok szerkesztésére
  - A meglévő matracok törlésére
  - Komment írása

*Nem funkcionális követelmények:*

- Könnyű áttekinthetőség: Színekkel típus szerint csoportosítás
- Használhatóság: Könnyű áttekinthetőség, ésszerű elrendezés, könnyen kezelhetőség
- Megbízhatóság: jelszóval védett funkciók, és a jelszavak védelme a háttérben. Hibásan bevitt adatok esetén a program jól láthatóan jelezzen a felhasználónak, és emelje ki a hibás beviteli mezőket. A jól bevitt adatok maradjanak az űrlapban.
- Karbantarthatóság: könnyen lehessen bővíteni, a különböző típusú fájlok külön csoportosítva, ésszerűen legyenek felbontva, a könnyebb fejleszthetőség miatt

**1.2. Szakterületi fogalomjegyzék**

Fajták:

- Rugós matrac: Rugókkal rendelkező matrac.
- Habszivacs matrac: Habszivacsból készült matrac.
- Fedőmatrac: Normál matrac tetejére való vékonyabb matrac.

Keménység: A matrac keménységéről tájékoztató adat, lehet: kemény, félkemény, puha.

**1.3. Használatieset-modell, funkcionális követelmények**

Vendég: Csak a publikus oldalakat éri el

- Főoldal
- Bejelentkezés
- Regisztráció

Bejelentkezett felhasználó: A publikus oldalak elérésén felül egyéb funkciókhoz is hozzáfér.

- Új matrac felvétele
- Matrac megtekintése
  - Új komment írása
  - Matrac szerkesztése
- Matrac törlése

![](/docs/images/nomnoml (2).png?raw=true)

Vegyünk példának egy egyszerű folyamatot:

Meglévő matrac szerkesztése:

1. A felhasználó az oldalra érkezve, bejelentkezik vagy regisztrál
2. Regisztráció után megtekintheti a matracokat listázó oldalt, ahol kiválaszthatja a szerkeszteni kívánt matracot.
3. Megnyomja a „Megtekintés&quot; feliratú gombot
4. A megtekintés oldalon kiválaszthatja a „Szerkesztés&quot; gombot
5. Szerkesztés oldalon felviszi az új adatokat
6. Küdés gombra kattintva elmenti a változásokat

![](/docs/images/nomnoml (1).png?raw=true)

***2. Tervezés***

**2.1. Architektúra terv**

**2.1.1. Komponensdiagram**

![](/docs/images/nomnoml (3).png?raw=true)

**2.1.2. Oldaltérkép:**

Publikus:

- Főoldal
- Bejelentkezés
- Regisztráció

Bejelentkezett:

- Főoldal
- Új matrac felvétele
- Listaoldal
  - Matrac törlése
  - Matrac megtekintése
    - Matrac szerkesztése
    - Komment hozzáadása

**2.1.3. Végpontok**

- GET/: főoldal
- GET/login: bejelentkező oldal
- POST/login: bejelentkező adatok felküldése
- GET/login/signup: regisztrációs oldal
- POST/login/signup: regisztrációs adatok felküldése
- GET/logout: kijelentkező oldal
- GET/mattresses/list: matraclista oldal
- GET/mattresses/new: új matrac felvétele
- POST/mattresses/new: új matrac felvételéhez szükséges adatok felküldése
- GET/mattresses/id: matrac adatok
- POST/mattresses/id: új komment felvitele
- GET/mattresses/delete=id: matrac törlése
- GET/mattresses/edit=id: matrac módosítása
- POST/mattresses/edit=id: matrac módosítása, adatok felküldése

**2.2. Felhasználói-felület modell**

*2.2.1.Oldalvázlatok:*
![](/docs/images/foold.jpg?raw=true)
![](/docs/images/bej.jpg?raw=true)
![](/docs/images/reg.jpg?raw=true)
![](/docs/images/ujm.jpg?raw=true)
![](/docs/images/matrlist.jpg?raw=true)
![](/docs/images/matracmegt.jpg?raw=true)
