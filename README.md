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
