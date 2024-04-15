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

## További Segítség
További segítségért és információkért tekintsük meg az [Angular CLI Overview and Command Reference](https://angular.io/cli) oldalt.

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

## Figyelmeztetések

- A jelszónak legalább 6 karakter hosszúnak kell lennie.
- A felhasználónak érvényes e-mail címet kell megadnia.
- A felhasználónak kitöltendő minden kötelező mezőt.

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
