# Bikeapi Frontend Dokumentáció 

 # Felhasználói Dokumentáció

### Célok
A webalkalmazás célközönsége kerékpárok iránt érdeklődő felhasználók, akik szeretnék böngészni a kínálatot, részletes információkat szeretnének kapni a különböző modellekről, valamint vásárolni szeretnének a platformon keresztül.

### Program leírása:
Az ISABIKE Kerékpárüzlet alkalmazás egy webes platform, amely lehetővé teszi kerékpárok böngészését, részletes termékinformációk megtekintését és vásárlását. Az alkalmazás célja kényelmes és intuitív felhasználói élmény biztosítása a kerékpárok iránt érdeklődő vásárlók számára.

### Futási környezet:
Az ISABIKE Kerékpárüzlet alkalmazás webes környezetben fut, így elérhető bármilyen modern webböngészőn keresztül, például Google Chrome, Mozilla Firefox, vagy Safari.

### Használat:
Az alkalmazás használata egyszerű és intuitív. A felhasználók a böngészőben navigálva érik el az alábbi oldalakat:

- **Főoldal:** Az ISABIKE főoldalára érkeznek, ahol láthatják az elérhető márkákat és 6 ajánlott terméket.
  Az egyes biciklik kártyáiban található részletek gombra kattintva átvisz a termek oldalra.
- **Biciklik:** Megtekinthetik a termékkínálatot, információkat kaphatnak a az árol és elérhetőségről. Az előző és következő gombokal lehet a temékeket lapozni.
  Az egyes biciklik kártyáiban található részletek gombra kattintva átvisz a termek oldalra. A
- **Termék:** Ez a oldal felelős egy adott termék egyébb részleteinek megjelenítésért mint kategoria, mennyiség rakáron, súly, szín, elérhetőség.
  A hozzáadás a kosárhoz gombra kattintva felveszi a kosárba a terméket. Ha a másik termék megtekintése gombra kattintunk visza irányit a bicikli oldalra.
- **Szerviz:** A kinált szervizszolgáltatásokl kapcsolatban informálodhatnak.
- **Rólunk:** További információkat találnak a vállalkozásról és annak történetéről.
- **Bejelentkezés:** Felhasználói fiókóba lehet bejelenkezni e-mail cím és jelszó megadásával.
  Amikor rányomunk a bejelenkezés gombra akkor elküdi a bejelenkezés a backendre és átvizs a főoldlra .
- **Regisztráció:** Felhasználói fiókót lehet létrehozni e-mail cím, név(Felhasználónév), keresztnév, vezetéknév, és jelszó megadásával. Amikor rányomunk a regisztráció gombra akkor elküdi a 
  regisztrációt a backendre és átvizs a viszaigazolás oldara.
- **Viszaigazolás:** Felhasználói fiók aktiválása az e-mailben kapot  5 számjegyű kódal.
  Ha a megerősités gombra katintunk akkor átvizs a bejelenkezés oldara.
- **Kosár:** A kiválasztott termékeket itt tárolodnak vásárlás előtt, láthato termék neve:, menyisége, a kosárhoz adás ideje adatokat.
  Ha a megrendelés gombra katintunk akkor átvizs a rendelés oldara.
- **Rendelés:** Felhasználók megadják az adataikat és leadják a rendelés amiről e-mail értesitést kapnak. Ha a küldés gombra katintunk akkor felveszi a rendelést és átvizs a főoldalra oldara.  
- **Felhasználó-Rendelések:** Felhasználók visszatekinthetnek korábbi rendeléseikre és nyomon követhetik azok állapotát. Rendelés adatai gombra katintva megjeleniti rendelés ideje, megjegyzés, szálitó(nem mükődik) és fizetés opció(nem mükődik) adatokat.


# Fejlesztői Dokumentáció

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

### `onPageChange()`

- **Leírás**: Ez a metódus hívódik meg, amikor a felhasználó vált az oldalak között.
- **Feladat**: Beállítja az aktuális oldalszámot a kapott oldalszámra.

### `showProductDetails()`

- **Leírás**: Ez a metódus hívódik meg, amikor a felhasználó részleteket kér egy termékről.
- **Feladat**: Elmenti a termék azonosítóját a localStorage-ben, majd navigál a részletek oldalra.

# Register komponens

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

# Login komponens

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
  3. Ellenőrzi a beviteli mezők validitását.
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

# Uer-rendeles komponens

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

# Rolunk komponens

Ez a komponens az ISABIKE kerékpárüzlet bemutatására szolgál. Az oldal három fő részre van osztva: az üdvözlő szakaszra, a történetre és az elérhetőségre.

## Tartalom

### Bevezető szakasz 
Ez a rész üdvözli a látogatókat az ISABIKE-ban. Tartalmazza az üzlet nevét, egy rövid üzenetet a minőségi kerékpárokról és kiegészítőkről, valamint egy képet a kerékpárüzletről.

### Történet 
Itt található a kerékpárüzlet bemutatása és az ISABIKE-hoz való csatlakozás értékrendje. Részletesen ismerteti, hogy az ISABIKE nem csupán egy kerékpárüzlet, hanem egy közösség, ahol a kerékpározás iránti szenvedély megosztható és átélhető.

### Elérhetőség 
Ebben a szakaszban megtalálhatók az ISABIKE elérhetőségi adatai, mint például a telefonszám, az email cím és a cím. Ezek segítségével a látogatók könnyen kapcsolatba léphetnek az üzlettel.

# Szerviz komponens

Ez az oldal a szerviz kínálatokat mutatja be az ISABIKE kerékpárüzletben. A felsorolt szolgáltatásokat és azok árait tartalmazza.

### Állapotfelmérés
Ez a szolgáltatás magában foglalja a fékrendszer vizsgálatát, szekunder áttétel vizsgálatát, gumiabroncsok állapotának ellenőrzése.A munkadíj: 8 000 Ft.
### Olaj- és szűrőcsere
Ez a szolgáltatás az olaj- és szűrőcserét jelenti a kezelési útmutatóban javasolt periódus alapján. A munkadíj: 8 000 Ft.
### Láncszett csere
Ez a szolgáltatás a jó állapotú szekunder áttétel cseréjét szettben tartalmazza. A munkadíj: 14 000 Ft-tól.
### Fékszerviz
Fontos a biztonságos közlekedés érdekében. Ez a szolgáltatás magában foglalja a fékalkatrészek ellenőrzését és szükség esetén cseréjét. A munkadíj: 12 000 Ft-tól.
### Teleszkópszerviz 
A kényelmes használat érdekében elengedhetetlen a tökéletes állapotú futómű. A munkadíj: 40 000 Ft-tól.
### Gumiabroncs csere
A motorkerékpár legfontosabb alkatrésze a gumiabroncs. Ez a szolgáltatás a gumiabroncs cseréjét jelenti. A munkadíj: 10 000 Ft-tól.

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

# Kosár komponens

Ez a komponens felelős a felhasználó bevásárlókosarában található termékek megjelenítéséért az ISABIKE Kerékpárüzlet webhelyén.

## Tartalom

A komponens egy listát jelenít meg a felhasználó bevásárlókosarában található termékekről. Minden termékhez tartozik a termék neve, mennyisége és hozzáadásának ideje. Minden termékhez egy gomb is tartozik, amely lehetővé teszi a termék törlését a kosárból.

## Metódusok

### `getItems()`

- **Leírás**: A felhasználó bevásárlókosarában található termékek lekérdezése.
- **Feladatok**: Lekéri a felhasználó bevásárlókosarában található termékeket a megfelelő szolgáltatástól, majd megjeleníti azokat a felületen. Ha a kosár üres, kiír egy figyelmeztetést és visszairányítja a felhasználót a biciklik oldalra.

### `deleteItem()`

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

## Metódusok

### `getItems()`

- **Leírás**: A felhasználó rendeléseinek lekérdezése.
- **Feladatok**: Lekéri a felhasználó rendeléseit a megfelelő szolgáltatástól, majd megjeleníti azokat a felületen. Ha a lekérdezés sikertelen, visszairányítja a felhasználót a biciklik oldalra, és kiír egy figyelmeztetést.

### `getRendelesTermekek()`

- **Leírás**: Egy rendeléshez tartozó termékek lekérdezése.
- **Feladatok**: Lekéri az adott rendeléshez tartozó termékeket a megfelelő szolgáltatástól, majd megjeleníti azokat egy felugró üzenetben. Az üzenet tartalmazza a termék nevét, darabszámát, egységárát és állapotát.

### `kezbesitve()`

- **Leírás**: Állapot visszaadása szöveges formában.
- **Feladatok**: Az adott szám alapján visszaadja a megfelelő állapot szöveges formában.

### `getSzalito()`

- **Leírás**: Szállító nevének visszaadása szöveges formában.
- **Feladatok**: Az adott szám alapján visszaadja a megfelelő szállító nevét szöveges formában.

### `getFizOp()`

- **Leírás**: Fizetési opció nevének visszaadása szöveges formában.
- **Feladatok**: Az adott szám alapján visszaadja a megfelelő fizetési opció nevét szöveges formában.

## Változók

### `rendelesData`

- **Típus**: any[]
- **Leírás**: A felhasználó rendeléseinek tömbje.

### `rendelesTermekek`

- **Típus**: any[]
- **Leírás**: A kiválasztott rendeléshez tartozó termékek tömbje.

# UserAuthService Szolgáltatás

Ez a szolgáltatás felelős a felhasználók autentikációjával és az azokhoz kapcsolódó műveletekkel.

## Metódusok

### `login(): Observable<any>`

- **Leírás**: Felhasználó bejelentkezésének kezelése.
- **Végpont**: `POST /api/login`
- **Paraméter**: loginObj - Bejelentkezési adatokat tartalmazó objektum.
- **Visszatérési érték típusa**: Observable<any>
- **Feladatok**: Ez a metódus küld egy HTTP POST kérést a bejelentkezési végpontra a megadott adatokkal. Visszatérési értékként egy Observable-t kapunk, amely tartalmazza a bejelentkezési választ.

### `getUserData(): Observable<any>`

- **Leírás**: Felhasználó adatainak lekérése a token alapján.
- **Végpont**: `POST /api/getonefelhasznalo`
- **Paraméter**: token - Felhasználóhoz tartozó token.
- **Visszatérési érték típusa**: Observable<any>
- **Feladatok**: Ez a metódus küld egy HTTP POST kérést a felhasználó adatainak lekérdezésére a token alapján. Visszatérési értékként egy Observable-t kapunk, amely tartalmazza a felhasználó adatait.

### `register(): void`

- **Leírás**: Felhasználó regisztrációjának kezelése.
- **Feladatok**: Ez a metódus küld egy regisztrációs kérést a megadott adatokkal a backend számára.

### `verifyAccount(): Promise<any>`

- **Leírás**: Felhasználó fiókjának ellenőrzése a megadott kóddal.
- **Végpont**: `PUT /api/verify`
- **Paraméter**: data - Ellenőrzési kódot tartalmazó objektum.
- **Visszatérési érték típusa**: Promise<any>
- **Feladatok**: Ez a metódus küld egy HTTP PUT kérést a felhasználó fiókjának ellenőrzésére a megadott kóddal. A visszatérési érték egy Promise, amely tartalmazza az ellenőrzés eredményét.

### `isLoggedIn(): boolean`

- **Leírás**: Ellenőrzi, hogy a felhasználó be van-e jelentkezve.
- **Visszatérési érték típusa**: boolean
- **Feladatok**: Ez a metódus ellenőrzi, hogy a felhasználó be van-e jelentkezve a helyi tárolt tokennel.

### `logout(): Observable<any>`

- **Leírás**: Felhasználó kijelentkezése.
- **Végpont**: `POST /api/logout`
- **Paraméter**: asd - Felhasználóhoz tartozó token.
- **Visszatérési érték típusa**: Observable<any>
- **Feladatok**: Ez a metódus küld egy HTTP POST kérést a kijelentkezési végpontra a felhasználóhoz tartozó tokennel. Visszatérési értékként egy Observable-t kapunk, amely tartalmazza a kijelentkezési választ.

# Cart Szolgáltatás

Ez a szolgáltatás felelős a felhasználó kosarával kapcsolatos műveletekkel.

## Metódusok

### `addToCart(): Observable<any>`

- **Leírás**: Termék hozzáadása a kosárhoz.
- **Végpont**: `POST /api/addkosar`
- **Paraméterek**: 
  - productId: A termék azonosítója, amelyet a kosárhoz szeretnénk adni.
  - quantity: A termék mennyisége.
- **Visszatérési érték típusa**: Observable<any>
- **Feladatok**: Ez a metódus küld egy HTTP POST kérést a kosárhoz adás végpontra a megadott adatokkal.

### `getCartItems(): Observable<any>`

- **Leírás**: Kosár elemeinek lekérése.
- **Végpont**: `POST /api/getonekosar`
- **Visszatérési érték típusa**: Observable<any>
- **Feladatok**: Ez a metódus küld egy HTTP POST kérést a kosár elemeinek lekérdezésére.

### `updateCartItem(): Observable<any>`

- **Leírás**: Kosárban lévő elem mennyiségének frissítése.
- **Végpont**: `PUT /api/updatekosar`
- **Paraméterek**: 
  - cartItemId: A kosárban lévő elem azonosítója.
  - quantity: Az új mennyiség.
- **Visszatérési érték típusa**: Observable<any>
- **Feladatok**: Ez a metódus küld egy HTTP PUT kérést a kosárban lévő elem mennyiségének frissítésére.

### `removeCartItem(): Observable<any>`

- **Leírás**: Elem eltávolítása a kosárból.
- **Végpont**: `DELETE /api/deletekosar/:cartItemId`
- **Paraméter**: cartItemId: A kosárból eltávolítandó elem azonosítója.
- **Visszatérési érték típusa**: Observable<any>
- **Feladatok**: Ez a metódus küld egy HTTP DELETE kérést a megadott elem eltávolítására a kosárból.

### `submitOrder(): Observable<any>`

- **Leírás**: Rendelés leadása.
- **Végpont**: `POST /api/addrendeles`
- **Paraméter**: orderData: A rendelés adatait tartalmazó objektum.
- **Visszatérési érték típusa**: Observable<any>
- **Feladatok**: Ez a metódus küld egy HTTP POST kérést a rendelés leadás végpontra a megadott adatokkal.

### `getOrder(): Observable<any>`

- **Leírás**: Felhasználó rendeléseinek lekérése.
- **Végpont**: `POST /api/getonerendeles`
- **Visszatérési érték típusa**: Observable<any>
- **Feladatok**: Ez a metódus küld egy HTTP POST kérést a felhasználó rendeléseinek lekérdezésére.

### `getOrderData(): Observable<any>`

- **Leírás**: Egy rendelés részletes adatainak lekérése.
- **Végpont**: `GET /api/getonerendelestermekek/:id`
- **Paraméter**: id: A rendelés azonosítója.
- **Visszatérési érték típusa**: Observable<any>
- **Feladatok**: Ez a metódus küld egy HTTP GET kérést a megadott rendelés részletes adatainak lekérdezésére.

# Authentication-client Szolgáltatás

Ez a szolgáltatás felelős az autentikációs műveletekhez kapcsolódó ügyféloldali feladatok végrehajtásáért.

## Metódusok

### `register():`

- **Leírás**: Regisztrálja az új felhasználót az adott névvel, e-mail címmel és jelszóval.
- **Paraméterek**: 
  - felhasznalo_nev: string - A regisztrált felhasználó teljes neve.
  - kereszt_nev: string - A felhasználó keresztneve.
  - vezetek_nev: string - A felhasználó vezetékneve.
  - email: string - A felhasználó e-mail címe.
  - password: string - A felhasználó jelszava.
- **Visszatérési érték**: Egy Observable, amely tartalmazza a regisztrációval kapcsolatos válaszobjektumot.


# Pagination Szolgáltatás

Ez a szolgáltatás felelős az aktuális oldalszám tárolásáért és frissítéséért.

## Metódusok

### `setCurrentPage(): void`

- **Leírás**: Beállítja az aktuális oldalszámot.
- **Paraméter**: 
  - page: Az új aktuális oldalszám.
- **Feladatok**: Ez a metódus frissíti az aktuális oldalszám értékét a megadott értékre.


# Product szolgáltatás

Ez a szolgáltatás felelős a termékekkel kapcsolatos adatok lekérdezéséért.

## Főbb funkciók

### `getProducts(): `

- **Leírás**: Termékek lekérése.
- **Végpont**: `GET /api/termekek/100`
- **Visszatérési érték típusa**: Observable<any[]>
- **Feladatok**: Ez a metódus küld egy HTTP GET kérést a termékek lekérdezésére.

### `getProduct(): `

- **Leírás**: Egy termék lekérése az azonosítója alapján.
- **Végpont**: `GET /api/onetermekek/:id`
- **Paraméter**: id: A termék azonosítója.
- **Visszatérési érték típusa**: Observable<any>
- **Feladatok**: Ez a metódus küld egy HTTP GET kérést a megadott termék azonosítója alapján.

