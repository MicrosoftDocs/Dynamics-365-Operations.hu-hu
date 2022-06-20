---
title: Bevétel-felosztási sablonok előfizetési számlázásban
description: Ez a cikk bemutatja a kötegként értékesített cikkek bevétel felosztási sablonjainak beállítását.
author: JodiChristiansen
ms.date: 04/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 145ca6e6f0673a5a09fe9a23cf5e163421617fd9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8904759"
---
# <a name="revenue-split-templates-in-subscription-billing"></a>Bevétel-felosztási sablonok előfizetési számlázásban

A Bevétel felosztása **sablonlapon** beállíthatja a bevétel felosztására vonatkozó sablonokat. A bevétel felosztása egy szülőcikkből áll, amely gyermekcikkeket tartalmaz. Az ilyen típusú cikkeket gyakran egyetlen cikkként vagy kötegként adják el a vevőknek.

Például a következő módon lehet létrehozni egy számítógépes elemet:

- **Szülőcikk:** előfizetési ezüst
- **Sor (gyermek) tétel:**

    - Támogatás
    - Karbantartás
    - Licenc

Szülőcikk létrehozásakor tartsa szem előtt a következő korlátozásokat:

- Egy cikk csak egyszer lehet szülőcikkként megadni.
- A szülőcikk gyermekelemként is kiválasztható ugyanabban a sablonban.
- Az érvényes sablonhoz legalább egy gyermekelem szükséges.
- Egy cikk egy kötegcikknél több gyermekcikkként is meg lehet adni.
- Minden szülő-gyermek kapcsolatnak egyedinek kell lennie.

## <a name="create-a-parent-item-that-has-child-items"></a>Szülőcikk létrehozása gyermekcikkekkel

A következő lépések szerint szülőcikkeket hozhat létre, amelyekben gyermekcikkek is vannak.

1. Válassza az **Új lehetőséget a Bevétel felosztása sablonoldalon** **·**.
1. A Szülő **cikk mezőben** válasszon ki egy szülő cikket. A **Változatszám mező** automatikusan frissül. Az érték szükség szerint megváltoztatható.
1. A Felosztási **mód mezőben** válasszon ki egy felosztási módszert.
1. Az Összetevő cikkek **listájában** válassza a Hozzáadás **lehetőséget** a gyermekelemek hozzáadásához.
1. Ha a Felosztási mód **mezőben** **a Százalék beállítást választotta, adja meg a százalékot a Százalék** mezőben **.**

    - Ha a Felosztási mód **mezőben** **az** Egyenlő összeget választotta, **a** Százalék mező automatikusan frissül, így minden cikkhez azonos százalék kerül.
    - Ha a **Változó összeg, a** Nulla **·** **szülőösszeg** vagy a Nulla összeg beállítást választotta a Felosztási **mód mezőben, a Százalék mező értéke 0 (nulla**) marad, **·** **és nem módosítható.**

1. Válassza a **Mentés** lehetőséget.

## <a name="fields"></a>Mezők

A **Bevétel felosztása sablonlap** a következő mezőket tartalmazza.

| Mező | Leírás |
|-------|-------------|
| Szülő cikk | Válasszon egy cikkszámot. Ez a cikk lesz a létrehozott kötegcikk szülőcikke. |
| Termék neve | A termék neve. |
| Felosztási mód | <p>Válassza ki a felosztási módot:</p><ul><li>**Egyenlő összeg** – a felosztási százalékokat a program automatikusan kiszámítja, és egyenlően osztja fel a sablonban található cikkek között.</li><li>**Százalék** – a felosztáshoz százalékos összeget lehet megadni. A százalékok összegének 100-nak kell lennie.</li><li>**Változó összeg** – a hozzáadott gyermek cikkek nettó összege 0 (nulla). A gyermekelemek árát tranzakciószinten kell megadni.</li><li>**Nulla összeg** – a szülőcikk megtartja egységárát és nettó összegét. Minden gyermek cikk nettó összege 0 (nulla).</li><li>**Nulla szülőösszeg** – a szülőcikk fix nettó összege 0 (nulla). A gyermekelemek a normál cikkekként kezelendők. Nem történik ellenőrzés annak ellenőrzésére, hogy a gyermekcikkek összege megegyezik-e a szülő cikk összegével.</li></ul> |
| **Összetevő cikkek** | |
| Összetevő cikk | Válasszon egy cikkszámot. Ez a cikk egy gyermekelem. |
| Változat száma | A cikk változatszámának kiválasztása. |
| Termék neve | A termék neve. |
| Százalék | <p>A foglalási százalék a mérföldkőhöz:</p><ul><li>Ha a **Felosztási mód** mező értéke **Százalék**, megadhatja a százalékos értéket.</li><li>Ha a **Felosztási mód** mező értéke **Egyenlő** összeg, a program automatikusan kiszámítja a százalékot, hogy a sablon minden cikkének azonos százalékban megjelenik a értéke.</li><li>Ha a **Felosztási** **mód mező értéke Változó** összeg, Nulla **szülőösszeg** **vagy** Nulla összeg, a százalékos érték 0 (nulla), ezért nem szerkeszthető.</li></ul><p>A mező értéke bármilyen pozitív szám lehet 0 (nulla) és 100 között. Az összes százalék összegének 100-nak kell lennie.</p> |
| Százalékarány összesen | <p>A Százalék oszlopban lévő **értékek** összege.</p><ul><li>Ha a **Felosztási mód** mező **értéke** **Egyenlő** összeg vagy Százalék, az összes százalék összegének 100-nak kell lennie.</li><li>Ha a **Felosztási mód** **mező értéke Változó** összeg, Nulla **szülőösszeg** **vagy Nulla** összeg, a teljes százalékos érték 0 (nulla).</li></ul> |

## <a name="revenue-split-on-a-sales-order"></a>Bevétel felosztása értékesítési rendelésre

A következő lépések szerint hozhat létre olyan értékesítési rendelést, amelynél be van állítva a bevétel felosztása.

1. Hozzon **létre egy értékesítési** rendelést az Értékesítési rendelés lapon.
2. A bevétel felosztása érdekében beállított cikkek sorában jelölje be **a Bevétel felosztása** jelölőnégyzetet. Ez a cikk lesz a szülő cikk. Ha a sablon már be van állítva, a gyermekelemek automatikusan megjelennek a listában.
3. Ha további gyermekcikkeket szeretne hozzáadni, **válassza** a Bevétel felosztása gyermek hozzáadása lehetőséget, majd válassza ki a hozzáadni kívánt gyermek cikket.
4. Mentse a rendelést.

## <a name="revenue-split-with-billing-schedules"></a>Bevétel felosztása számlázási ütemezésekkel

A következő lépések szerint hozhat létre olyan számlázási ütemezést, amely tartalmazza a bevétel felosztásához beállított cikket.

1. Hozzon létre **egy számlázási ütemezést a Mind/Aktív** számlázási ütemezések lapon.
2. A bevétel felosztása érdekében beállított cikkek sorában jelölje be **a Bevétel felosztása** jelölőnégyzetet. Ez a cikk lesz a szülő cikk. Ha a sablon már be van állítva, a gyermekelemek automatikusan megjelennek a listában.
3. Ha további gyermekcikkeket szeretne hozzáadni, **válassza** a Bevétel felosztása gyermek hozzáadása lehetőséget, majd válassza ki a hozzáadni kívánt gyermek cikket.
4. A számlázási ütemezéssel kapcsolatos lépések folytatása.

> [!NOTE]
> Ha a Bevétel **felosztásának** **·** **automatikus** létrehozása beállítás Az Ismétlődő szerződés számlázási paraméterei lapon Igen beállítás van megállítva, a következő műveletek fordulhatnak elő:
>
> - Ha a sorcikk szülőcikkként van beállítva a bevétel felosztási sablonjában, **a** Bevétel felosztása jelölőnégyzet automatikusan be van jelölve.
> - A gyermekelemek automatikusan megjelennek az értékesítési rendelés vagy a számlázási ütemezés sorában.
>
> Ha a Bevétel felosztásának **automatikus** létrehozása beállítás Nem **beállításra** van állítva, a viselkedés magyarázata a korábbiak szerint történik.

## <a name="additional-revenue-split-information"></a>További bevétel-felosztási információk

Bevétel felosztása részeként hozzáad egy cikket, jegyezze fel a következő adatokat: 

- A szülő összege nem halasztható.
- A gyermekcikkek kezdő dátumán, záró dátumán, mennyiségén, egységén, telephelyén és raktári értékén a szülőcikk alapul. Ezek az értékek nem módosíthatók a gyermekelemeknél. A szülőcikken minden módosítást végre kell tenni. 
- Az árképzési mód **7000** 000, ezért nem módosítható.
- A gyermekelemek hozzáadhatók vagy eltávolíthatók.
- A szülő- és a gyermekelemeknek ugyanazt a cikkcsoportot kell használniuk. 
- A gyermekelemek a következő beállítások valamelyikét választhatják:

    - A **Számlázási gyakoriság és** **a Számlázási intervallum** mezők értéke megegyezik a szülő cikk értékével. 
    - A **Számlázási gyakoriság** mező beállítása **Egyszeres**. Ebben az esetben a Számlázási **intervallumok** mező automatikusan **1-et ad meg**. 

- A gyermekelemek nettó összegének összege megegyezik a szülő összegével. Ha a felosztási mód Nulla **összeg**, a gyermekcikkösszegek és a szülőösszegek összege egyaránt 0 (nulla). 

    > [!NOTE]
    > Ha a felosztási **mód** Nulla szülőösszeg, a gyermekelemek (nem nulla) összege nem egyenlő a szülő összegével, amely 0 (nulla). Ez a felosztási mód belső célokat szolgál, hogy az alkalmazottak látják a gyermek cikkeket. A vevők azonban csak a szülőcikket láthatják.

- Ha az értékesítési rendelés többelemes elrendezése (MEA) **egy**, akkor a szülő és gyermek cikkek hozzáadásakor létrejön a megfelelő többelemes bevételfelosztási tranzakciósor. 
- Ha egy bevétel felosztási módja Egyenlő összeg, és módosul a **szülőösszeg**, a rendszer minden gyermeksor esetén újraszámítja az összegeket. 
- Olyan bevételfelosztás esetén, ahol **a felosztási mód változó összeg**, a következő viselkedés történik:

    - A szülőcikk nettó összege megjelenik a Szülő **összege oszlopban**. Az érték szerkeszthető. Az egységár, a nettó összeg és az engedmény azonban 0 (nulla) és nem szerkeszthető.
    - A gyermekelemek egységára 0 (nulla). Az egységár és a nettó összeg szerkeszthető. Az egyik érték szerkesztésekor a másik automatikusan frissül.

- Olyan bevételfelosztás esetén, ahol **a felosztási mód Százalék**, a következő viselkedés történik:

    - A szülőcikk nettó összege megjelenik a Szülő **összege oszlopban**. Az érték szerkeszthető. Az egységár, a nettó összeg és az engedmény azonban 0 (nulla) és nem szerkeszthető. 
    - A gyermekelemek nettó összegét a *szülő százalékos összegeként*&times;*számítja ki a program*.

- Olyan bevételfelosztás esetén, ahol **a** felosztási mód egyenlő összeg, a következő viselkedés történik:

    - A szülőcikk nettó összege megjelenik a Szülő **összege oszlopban**. Az érték szerkeszthető. Az egységár, a nettó összeg és az engedmény azonban 0 (nulla) és nem szerkeszthető. 
    - A gyermekelemek nettó összegét úgy számítja ki a program, hogy a szülőösszeget egyenlően elosztja a gyermekelemek között. 
    - Ha gyermek cikkeket távolít el vagy ad hozzá, akkor a nettó összeget és az egységárakat újraszámja a program, hogy az összes gyermeksor összege egyenlő legyen. 
    - Ha a szülő összege nem osztható fel egyenlően, akkor az utolsó gyermekcikk nettó összege és egységára lehet egy kissé több vagy kevesebb, mint a többi gyermekcikk nettó összege és egységára. 

- Olyan bevételfelosztás esetén, ahol **a felosztási mód Nulla** összeg, a következő viselkedés történik:

    - Az egységár, a nettó összeg és az engedmény szerkeszthető. A szülő összege 0 (nulla), ezért nem szerkeszthető. 
    - A gyermekcikkek mennyisége, egysége, telephelye és raktári értékei a szülő cikken alapulnak. A gyermekelemeknek nem lehet módosítani ezeket az értékeket. A szülőcikken minden módosítást végre kell tenni. 
    - A gyermekelemek egységára és nettó ára 0 (nulla), ezért nem szerkeszthető. 

- Olyan bevételfelosztás esetén, ahol **a felosztási mód Nulla szülőösszeg**, a következő viselkedés történik:

    - A szülőcikk egységára, szülőösszege és nettó összege 0 (nulla).
    - A számlázási ütemezésben a gyermeksorok úgy jelennek meg, mintha manuálisan hozzáadták volna őket, és minden érték frissítése a kiválasztott számlázási ütemezési csoport alapján történik. Ezek az értékek szerkeszthetők. Gyermek cikkek esetén elérhető **az Eszkaláció** **·** **és** engedmény, valamint a Speciális árképzés lehetőség a Megadott mennyiség, **Egységár**, **·** **·** **Engedmény és Nettó összeg mező használatával a Számlázási adatok megtekintése területen.** 
    - Értékesítési rendelésnél a gyermeksorok 0 (nulla) engedmény- és engedményszázalékot kapnak. 
    - Módosítani lehet a szülő és a gyermekelemek számlázási gyakoriságát, és az egyes sorok gyakorisága eltérő lehet. A szülőcikk azonban automatikusan frissül, hogy a gyermeksorok közül a legrövidebb gyakoriságot használja. Például a bevétel felosztása két gyermekelemet tartalmaz, **·** **amelyek** egyike a havi számlázási gyakoriságot, a másik pedig az éves számlázási gyakoriságot használja. Ebben az esetben a szülőcikk számlázási gyakorisága havira **módosul**.
