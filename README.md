# Bikeapi Dokumentáció

## Áttekintés
Ez a dokumentáció a Bikeapi nevű Angular alkalmazásról szól, amely egy kerékpárkereskedés webes felületét biztosítja. Az alkalmazás lehetővé teszi a felhasználók számára, hogy böngésszenek és vásároljanak kerékpárokat, valamint szervizidőpontot foglaljanak.

## Felhasználói Dokumentáció

### Főoldal
A főoldalon a felhasználók megtekinthetik a legújabb ajánlatokat és híreket.

### Kerékpárok
A "Kerékpárok" oldalon találhatóak a különböző kerékpármodellek listája. A felhasználók megtekinthetik a kerékpárok képeit, leírását, árát és gyártóját. Részletes információkért kattintsunk a "Részletek" gombra.

### Rólunk
Az "Rólunk" oldalon találhatóak információk a vállalatról és a szolgáltatásokról.

### Bejelentkezés és Regisztráció
A felhasználók bejelentkezhetnek vagy regisztrálhatnak az oldalon. Bejelentkezett felhasználók számára elérhetővé válik a "Rendelésem" menüpont.

### Kosár
A "Kosár" oldalon a felhasználók megtekinthetik a kosárba helyezett termékeket és véglegesíthetik a rendelésüket.

### Rendelésem
A "Rendelésem" oldalon a felhasználók megtekinthetik korábbi rendeléseiket.

## Fejlesztői Dokumentáció

### Komponensek
- `HomeComponent`: A főoldal komponense.
- `BiciklikComponent`: A kerékpárok listáját megjelenítő komponens.
- `TermekComponent`: Egy adott termék részletes nézetét megjelenítő komponens.
- `RolunkComponent`: Az "Rólunk" oldal komponense.
- `LoginComponent`: Bejelentkezésért és regisztrációért felelős komponens.

### Szolgáltatások
- `ProductService`: A termékekkel kapcsolatos adatokat kezeli.
- `PaginationService`: Az oldalak kezelését biztosító szolgáltatás.
- `UserAuthService`: Felhasználókhoz kapcsolódó autentikációs szolgáltatás.

### Routing
A routing a `AppRoutingModule` modulban van definiálva. A különböző útvonalak a megfelelő komponenseket rendelik hozzájuk.

### Könyvtárak és Modulok
- `NgxPaginationModule`: A lapozást megvalósító modul.
- `NgbModule`: A Bootstrap komponensek integrálására szolgáló modul.

## Telepítés és Indítás
1. Telepítsük a szükséges függőségeket a `npm install` paranccsal.
2. Indítsuk el az alkalmazást a `ng serve` paranccsal.
3. Navigáljunk a `http://localhost:4200/` címre a böngészőben.

# Home komponens

A Home komponens felelős a kezdőoldal tartalmának megjelenítéséért az ISABIKE Kerékpárüzlet webhelyén.

## Feladatok

- Betölti a termékek adatait a backend szolgáltatásból.
- Megjeleníti a kerékpár márkákat logók formájában.
- Megjeleníti a kezdőoldalon a legnépszerűbb termékeket kártyák formájában.
- Biztosítja a felhasználó számára, hogy a termékek részleteit megtekinthesse a "Részletek" gombra kattintva.

## Metódusok

### `ngOnInit()`

- **Leírás**: Ez a metódus az Angular életciklusának része, és a komponens inicializálásakor fut le.
- **Feladat**: Betölti a termékeket és a márkákat a backend szolgáltatásból.

### `getProducts()`

- **Leírás**: Ez a metódus lekéri a termékek adatait a backend szolgáltatásból.
- **Feladat**: Frissíti a `products` tömböt a lekért termékekkel.

### `showProductDetails(productId: number)`

- **Leírás**: Ez a metódus hívódik meg, amikor a felhasználó a termék részleteit kívánja megtekinteni.
- **Feladat**: Elmenti a kiválasztott termék azonosítóját a localStorage-be, majd navigál a termék részletek oldalra.


# Biciklik komponens

A Biciklik komponens felelős a kerékpártermékek megjelenítéséért az ISABIKE Kerékpárüzlet webhelyén.

## Feladatok

- Betölti a kerékpártermékeket a backend szolgáltatásból.
- Megjeleníti a kerékpártermékeket kártya formájában, amelyek tartalmazzák a termék nevét, gyártóját, leírását, árát és egy részletek gombot.
- Lehetővé teszi a felhasználó számára, hogy részleteket lásson a kiválasztott termékről.
- Biztosítja a lapozást, hogy a felhasználó könnyen navigálhasson az oldalak között.

## Metódusok

### `ngOnInit()`

- **Leírás**: Ez a metódus az Angular életciklusának része, és a komponens inicializálásakor fut le.
- **Feladat**: Betölti a kerékpártermékeket és beállítja az oldalak számát a lapozáshoz.

### `getProducts()`

- **Leírás**: Ez a metódus lekéri a kerékpártermékeket a backend szolgáltatásból.
- **Feladat**: Frissíti a `products` tömböt a lekért termékekkel, valamint beállítja az összes termék számát a lapozáshoz.

### `onPageChange(pageNumber: number)`

- **Leírás**: Ez a metódus hívódik meg, amikor a felhasználó vált az oldalak között.
- **Feladat**: Beállítja az aktuális oldalszámot a kapott oldalszámra.

### `showProductDetails(productId: number)`

- **Leírás**: Ez a metódus hívódik meg, amikor a felhasználó részleteket kér egy termékről.
- **Feladat**: Elmenti a termék azonosítóját a localStorage-ben, majd navigál a részletek oldalra.

# Regisztráció komponens

A regisztráció komponens lehetővé teszi a felhasználók számára, hogy regisztráljanak az ISABIKE Kerékpárüzlet webhelyére.

## Felhasználás

A komponens egy regisztrációs űrlapot tartalmaz, amely lehetővé teszi a felhasználók számára, hogy megadják a regisztrációhoz szükséges adatokat.

## Alkalmazás

1. **Felhasználónév**: A felhasználó teljes nevét kell megadnia.
2. **Keresztnév**: A felhasználó keresztnevét kell megadnia.
3. **Vezetéknév**: A felhasználó vezetéknevét kell megadnia.
4. **E-mail cím**: A felhasználó érvényes e-mail címét kell megadnia.
5. **Jelszó**: A felhasználó biztonságos jelszavát kell megadnia.

## Folyamat

1. A felhasználó kitölti az összes szükséges mezőt az űrlapon.
2. A felhasználó elküldi az űrlapot a "Regisztráció" gombra kattintva.
3. Az alkalmazás ellenőrzi az adatok helyességét és regisztrálja a felhasználót.

## Jellemzők

- A komponens használja a Reactive Forms modellt a form validációjához.
- Az űrlap ellenőrzi a megadott adatok formátumát és érvényességét.
- Ha sikeres a regisztráció, a felhasználó további tevékenységeket végezhet az alkalmazáson belül.


## Megjegyzések

- Ha bármely mezőt helytelenül töltik ki, hibaüzenet jelenik meg a felhasználónak.
- Az űrlap elküldése előtt győződj meg róla, hogy minden mezőt helyesen töltöttél ki.

## `ngOnInit()`

- **Leírás**: Ez a metódus az Angular életciklusának részeként fut le, amikor a komponens inicializálódik.
- **Feladat**: Létrehozza a regisztrációs űrlapot és beállítja a szükséges validátorokat a form mezőihez.

## `registerAction()`

- **Leírás**: Ez a metódus az űrlap elküldésekor fut le, amikor a felhasználó megpróbál regisztrálni.
- **Feladat**: Ellenőrzi az összes form mezőt, és ha minden mező megfelelően van kitöltve, elküldi a regisztrációs adatokat a backend szolgáltatásnak.

## `registerForm`

- **Leírás**: Ez egy FormGroup objektum, amely a regisztrációs űrlapot reprezentálja.
- **Feladat**: Ez a FormGroup objektum kezeli az összes form mezőt és validációt biztosít a megfelelő adatbevitelhez.

## `validationErrors`

- **Leírás**: Ez egy objektum, amely a validációs hibák tárolására szolgál.
- **Feladat**: Ha bármelyik mező hibásan van kitöltve, ez az objektum tárolja és megjeleníti a hibaüzeneteket a felhasználónak.

## `isSubmitting`

- **Leírás**: Ez a változó jelzi, hogy éppen folyamatban van-e az űrlap elküldése.
- **Feladat**: Amikor az űrlap elküldése folyamatban van, ez a változó igaz értéket kap, és letiltja az űrlap újbóli elküldését.

# Bejelentkezés

Ez a komponens felelős a felhasználó bejelentkezési felületének megjelenítéséért az ISABIKE Kerékpárüzlet webhelyén.

## Feladatok

- Megjeleníti az e-mail cím és jelszó beviteli mezőket.
- Biztosítja a bejelentkezés gomb funkcióját.
- Amennyiben a felhasználó még nem rendelkezik fiókkal, lehetőséget biztosít a regisztrációra.

## Metódusok

### `ngOnInit()`

- **Leírás**: Az Angular életciklusának része, a komponens inicializálásakor fut le.

### `loginAction()`

- **Leírás**: Ez a metódus hívódik meg, amikor a felhasználó be akar jelentkezni.
- **Feladatok**:
  1. Ellenőrzi a beviteli mezők validitását.
  2. Elküldi a bejelentkezési adatokat a backend szolgáltatásnak.
  3. Amennyiben a bejelentkezés sikeres, átirányítja a felhasználót a kezdőoldalra.
  4. Mentésre kerül a token a localStorage-be.
  5. Lekéri a felhasználó adatait a localStorage-ból és elmenti őket.


# Verify komponens

Ez a komponens felelős a felhasználói fiók megerősítéséért az ISABIKE Kerékpárüzlet webhelyén.

## Tartalom

### Sikeres Megerősítés

Ha a fiók megerősítése sikeres volt, megjelenik egy üzenet, amely megerősíti a sikert, és lehetővé teszi a továbblépést.

### Megerősítő Kód Bevitel

Ezen részben a felhasználó beírhatja az e-mailben kapott 5 számjegyű megerősítő kódot.

## Műveletek

### `verifyAccount()`

- **Leírás**: A fiók megerősítése.
- **Feladatok**: Elküldi a beírt megerősítő kódot a megfelelő szolgáltatásnak. Ha a megerősítés sikeres volt, átirányítja a felhasználót a bejelentkező oldalra.

## Változók

### `code`

- **Típus**: string
- **Leírás**: A felhasználó által beírt megerősítő kód.

### `isSubmitting`

- **Típus**: boolean
- **Leírás**: Megadja, hogy éppen folyamatban van-e a megerősítés folyamata.

### `validationErrors`

- **Típus**: any
- **Leírás**: Az esetleges validációs hibák tárolására szolgáló változó.

### `verificationSuccess`

- **Típus**: boolean
- **Leírás**: Megadja, hogy a fiók megerősítése sikeres volt-e vagy sem.

# Termék Részletek komponens

Ez a komponens felelős egy adott termék részleteinek megjelenítéséért az ISABIKE Kerékpárüzlet webhelyén.

## Tartalom

### Kép

Az adott termék képe megjelenítésre kerül, ha rendelkezésre áll.

### Termek Információk

A termék alábbi információi kerülnek megjelenítésre:

- **Termék neve**: Az adott termék neve.
- **Kategória**: Az adott termék kategóriája.
- **Gyártó**: Az adott termék gyártója.
- **Mennyiség rakáron**: Az adott termék raktáron lévő mennyisége.
- **Súly**: Az adott termék súlya és mértékegysége.
- **Szín**: Az adott termék színe.
- **Leírás**: Az adott termék leírása.
- **Ár**: Az adott termék egységára.
- **Elérhetőség**: Az adott termék elérhetősége, ami lehet "Elérhető" vagy "Nem Elérhető" attól függően, hogy van-e készleten.

### Műveletek

- **Másik termék megtekintése**: Visszatérés a terméklista oldalra.
- **Hozzáadás a kosárhoz**: Ha a felhasználó be van jelentkezve, lehetőség van a termék hozzáadására a kosárhoz.

## Metódusok

### `ngOnInit()`

- **Leírás**: Az Angular életciklusának része, a komponens inicializálásakor fut le.
- **Feladatok**: Betölti a termék részleteit az URL-ben megadott azonosító alapján.

### `goBack()`

- **Leírás**: Visszatérés a terméklista oldalra.
- **Feladatok**: Navigál a terméklista oldalra és törli az esetlegesen eltárolt termék azonosítót.

### `addCart()`

- **Leírás**: A termék hozzáadása a kosárhoz.
- **Feladatok**: Elküldi a kosárba helyezendő termék azonosítóját a kosár szolgáltatásnak, majd kezeli az esetleges válaszüzeneteket.

### `isLoggedIn()`

- **Leírás**: Ellenőrzi, hogy a felhasználó be van-e jelentkezve.
- **Feladatok**: Visszaadja a bejelentkezés állapotát.

# Rendeles komponens

Ez a komponens felelős a vásárlók rendeléseinek rögzítéséért az ISABIKE Kerékpárüzlet webhelyén.

## Űrlapmezők

1. **Vásárló telefonszáma**: A vásárló telefonszámának megadása kötelező. Az érvényes telefonszám formátumának meg kell felelnie.
2. **Szállítási cím**: A rendelés szállítási címének megadása kötelező.
3. **Megjegyzés**: Opcionális mező, ahol a vásárló megjegyzéseket fűzhet a rendeléshez.
4. **Szállító**: Az alapértelmezett szállító cég, amely a rendelést teljesíti. A felhasználó nem módosíthatja ezt a mezőt.
5. **Fizetési opció**: Az alapértelmezett fizetési mód, amelyet a vásárló választott. A felhasználó nem módosíthatja ezt a mezőt.
6. **Kedvezmény**: Az esetleges kedvezmények megjelenítése. A felhasználó nem módosíthatja ezt a mezőt.

## Metódusok

### `ngOnInit()`

- **Leírás**: Az Angular életciklusának része, a komponens inicializálásakor fut le.
- **Feladatok**: Létrehozza és validálja az űrlapot.

### `onSubmit()`

- **Leírás**: A rendelés űrlap elküldésekor hívódik meg.
- **Feladatok**:
  1. Ellenőrzi az űrlap validitását.
  2. Elküldi a rendelés adatait a szervernek.
  3. Megjelenít egy üzenetet a sikeres vagy sikertelen rendelésről.

## Fontos megjegyzés

- Ellenőrizd az összes kötelező mező kitöltését a rendelés elküldése előtt.
- Kezeld a szerver által visszaadott hibákat a rendelés küldésekor.
  
# Rolunk komponens

Ez a komponens az ISABIKE kerékpárüzlet bemutatására szolgál. Az oldal három fő részre van osztva: az üdvözlő szakaszra, a történetre és az elérhetőségre.

## Tartalom

### Bevezető szakasz 
Ez a rész üdvözli a látogatókat az ISABIKE-ban. Tartalmazza az üzlet nevét, egy rövid üzenetet a minőségi kerékpárokról és kiegészítőkről, valamint egy képet a kerékpárüzletről.

### Történet 
Itt található a kerékpárüzlet bemutatása és az ISABIKE-hoz való csatlakozás értékrendje. Részletesen ismerteti, hogy az ISABIKE nem csupán egy kerékpárüzlet, hanem egy közösség, ahol a kerékpározás iránti szenvedély megosztható és átélhető.

### Elérhetőség 
Ebben a szakaszban megtalálhatók az ISABIKE elérhetőségi adatai, mint például a telefonszám, az email cím és a cím. Ezek segítségével a látogatók könnyen kapcsolatba léphetnek az üzlettel.

# Kosár komponens

Ez a komponens felelős a felhasználó bevásárlókosarában található termékek megjelenítéséért az ISABIKE Kerékpárüzlet webhelyén.

## Tartalom

A komponens egy listát jelenít meg a felhasználó bevásárlókosarában található termékekről. Minden termékhez tartozik a termék neve, mennyisége és hozzáadásának ideje. Minden termékhez egy gomb is tartozik, amely lehetővé teszi a termék törlését a kosárból.

## Műveletek

### `getItems()`

- **Leírás**: A felhasználó bevásárlókosarában található termékek lekérdezése.
- **Feladatok**: Lekéri a felhasználó bevásárlókosarában található termékeket a megfelelő szolgáltatástól, majd megjeleníti azokat a felületen. Ha a kosár üres, kiír egy figyelmeztetést és visszairányítja a felhasználót a biciklik oldalra.

### `deleteItem(id: any)`

- **Leírás**: Termék törlése a kosárból.
- **Feladatok**: Törli az adott terméket a kosárból a megfelelő szolgáltatás segítségével. A törlés után frissíti a kosár tartalmát.

## Változók

### `shoppingCartData`

- **Típus**: any[]
- **Leírás**: A felhasználó bevásárlókosarában található termékek tömbje.

# Felhasznalo-Rendeles komponens

Ez a komponens felelős a felhasználó rendeléseinek megjelenítéséért az ISABIKE Kerékpárüzlet webhelyén.

## Tartalom

A komponens egy listát jelenít meg a felhasználó rendeléseiről, minden rendeléshez tartozik a rendelés ideje, megjegyzés, szállító és fizetési opció. Minden rendeléshez tartozik egy gomb is, amely lehetővé teszi a rendelés részletes adatainak megtekintését.

## Műveletek

### `getItems()`

- **Leírás**: A felhasználó rendeléseinek lekérdezése.
- **Feladatok**: Lekéri a felhasználó rendeléseit a megfelelő szolgáltatástól, majd megjeleníti azokat a felületen. Ha a lekérdezés sikertelen, visszairányítja a felhasználót a biciklik oldalra, és kiír egy figyelmeztetést.

### `getRendelesTermekek(id: any)`

- **Leírás**: Egy rendeléshez tartozó termékek lekérdezése.
- **Feladatok**: Lekéri az adott rendeléshez tartozó termékeket a megfelelő szolgáltatástól, majd megjeleníti azokat egy felugró üzenetben. Az üzenet tartalmazza a termék nevét, darabszámát, egységárát és állapotát.

### `kezbesitve(num:any)`

- **Leírás**: Állapot visszaadása szöveges formában.
- **Feladatok**: Az adott szám alapján visszaadja a megfelelő állapot szöveges formában.

### `getSzalito(num:any)`

- **Leírás**: Szállító nevének visszaadása szöveges formában.
- **Feladatok**: Az adott szám alapján visszaadja a megfelelő szállító nevét szöveges formában.

### `getFizOp(num:any)`

- **Leírás**: Fizetési opció nevének visszaadása szöveges formában.
- **Feladatok**: Az adott szám alapján visszaadja a megfelelő fizetési opció nevét szöveges formában.

## Változók

### `rendelesData`

- **Típus**: any[]
- **Leírás**: A felhasználó rendeléseinek tömbje.

### `rendelesTermekek`

- **Típus**: any[]
- **Leírás**: A kiválasztott rendeléshez tartozó termékek tömbje.

