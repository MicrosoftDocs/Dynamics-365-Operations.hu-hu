---
title: Bevétel- és költség halasztások előfizetés számlázásakor
description: Ez a témakör bemutatja, hogyan lehet beállítani bevétel- és költség halasztásokat az előfizetéses számlázásban.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 9a12cf52d904db0396aa9914b8e324060289710f
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/04/2022
ms.locfileid: "8690948"
---
# <a name="revenue-and-expense-deferrals-in-subscription-billing"></a>Bevétel- és költség halasztások előfizetés számlázásakor

Ez a témakör bemutatja, hogy hogyan lehet beállítani és használni a bevétel- és költség halasztásokat az előfizetési számlázásban. A halasztások ütemezése mindig egy alapul szolgáló dokumentumon vagy számlázási ütemezésen alapul, és attól függ. Mivel ezek létrehozása alapértelmezett értékek alapján történik, nem lehet őket külön megadni vagy létrehozni.

A bevétel- és költség halasztások beállításának és használatának folyamata több oldalon történik:

- A Bevételi **és költség halasztások** paraméterei oldalon megadhatja a vállalat beállításait.
- A Halasztások **alapértelmezései** lapon lehet beállítani a halasztások ütemezéséhez használt alapértelmezett számlákat és sablonokat.
- A **Halasztássablonok** **és** az Esemény alapú halasztássablonok oldalon megadhatja a halasztás ütemezéséhez használt sablonokat.
- A Minden **halasztás ütemezése** lapon megtekinthetők és szerkeszthetők a halasztások ütemezései.

A bevételek és a költségek halasztásai az ismétlődő szerződésszámlázással együtt használhatók.

## <a name="revenue-and-expense-deferral-parameters"></a>Bevétel- és költséghalasztási paraméterek

A **Bevétel és költség halasztás paraméterei** lap a következő mezőket tartalmazza.

| Mező | Leírás |
|---|---| 
| **Ütemezés** lap | |
| Időszakonként egyenlő | <p>Adja meg, hogy az időszak napjainak a számát használja-e a program, amikor a halasztás ütemezésének időszakonkénti összegét számítja:</p><ul><li>**Igen** – az egyes időszakokkal azonos összeg, függetlenül attól, hogy hány nap van az időszakban. A részidőszakok (például a halasztás ütemezésének kezdő vagy záró időszaka) időkorreknálnak.</li><li>**Nem** – az összeg számítása az egyes időszakok napjainak száma alapján történik.</li></ul><p>Ezt a beállítást tranzakciószinten felülbírálhatja.</p> |
| Értékesítési engedményhalasztás lehetősége | <p>Adja meg, hogy az engedményhez és az értékesítési rendelés összeghez külön halasztások ütemezése jön-e létre:</p><ul><li>**Az engedmény külön ütemezése** – az engedmény összege elkülönül a bevételi összegtől.<p>Ebben az esetben két halasztás ütemezés jön létre az értékesítési rendelés létrehozása és feladása esetén. Az engedmény és a bevétel összegei más halasztások számláira lesznek feladva.</p></li><li>**Engedmény egyesítése a bevétellel** – az engedmény összegét a rendszer a bevétel összeggel kombinálja. Létrejön egy halasztás ütemezése, és mind az engedmény, mind a bevétel összege ugyanannak a halasztásnak a számlájára lesz feladva.<p>Ebben az esetben egy halasztás ütemezése jön létre az értékesítési rendelés létrehozása és feladása esetén. Mind az engedmény, mind a bevétel összege ugyanannak a halasztásnak a számlájára lesz feladva.</p></li></ul><p>**Megjegyzés:** Ha engedményeket kell alkalmazni a nemszámlázatlan bevétel szolgáltatást igénybe vevő cikkekre, **válassza az Engedmény külön ütemezése** lehetőséget. Ezután minden cikkre alkalmazni lehet engedményeket, függetlenül attól, hogy a be nemszámlázatlan bevétel funkciót használja-e. Ha be van **jelölve** az Engedmény egyesítése a bevétellel beállítás, nem alkalmazhatók engedmények olyan cikkekre, amelyek a nemszámlázatlan bevétel funkciót használják.</p> |
| Beszerzési engedmény halasztásának lehetősége | <p>Válassza ki, hogy az engedményhez és a beszerzési rendeléshez külön halasztás-ütemezések vannak-e létrehozva:</p><ul><li>**Az engedmény külön ütemezése** – az engedmény összege nem kerül a kiadás összegére.<p>Ebben az esetben két halasztás ütemezés jön létre a beszerzési rendelés létrehozása és feladása esetén. Az engedmény és a kiadás összegei különböző halasztások számláira vannak feladva.</p></li><li>**Engedmény egyesítése a bevétellel** – az engedmény összegét a rendszer a költség összeggel kombinálja. Létrejön egy halasztás ütemezése, és mind az engedmény összege, mind a költség összege ugyanannak a halasztásnak a számlájára lesz feladva.<p>Ebben az esetben egy halasztás ütemezése jön létre a beszerzési rendelés létrehozása és feladása esetén. Mind az engedmény összege, mind a költség összege ugyanannak a halasztásnak a számlájára lesz feladva.</p></li></ul> |
| Megelőző időszakok összesítése | <p>Adja meg, hogy összevonja-e a korábbi időszakok halasztás-ütemezési sorait:</p><ul><li>**Igen** – ha a halasztás kezdő dátuma a tranzakció dátuma előtti időszakba esik, akkor a tranzakció dátumán keresztül minden összeg egyetlen halasztás-ütemezési sorba lesz egyesítve.</li><li>**Nem** – az összes időszak összegei külön halasztás-ütemezési sorokban vannak.<p>Ha a halasztás kezdő dátuma a tranzakció dátumának megfelelő vagy annál későbbi időszakra vonatkozik, ennek a lehetőségnek nincs hatása.</p></li></ul><p>Ez a beállítás tranzakciószinten frissíthető.</p> |
| Halasztás alapértelmezett kezdő dátuma | <p>Válassza ki azt a szabályt, amely meghatározza a halasztás ütemezésének kezdő dátumát:</p><ul><li>**Tranzakció dátuma** – a tranzakció dátuma legyen a kezdő dátum.</li><li>**A jelenlegi hónap kezdete** – a kezdő dátum az aktuális hónap első napja. Ha a tranzakció dátuma bármely hónap első napja, akkor az aktuális hónap első napja a kezdő dátum.</li><li>**A következő hónap kezdete** – a következő hónap első napját használja kezdő dátumként. Ha a tranzakció dátuma az első, akkor a tranzakció dátumát használja a tranzakció dátuma. Ellenkező esetben a következő hónap első napja lesz használva.</li><li>**15-ös** szabály – ha a tranzakció dátuma az első és a tizenötödik nap közé esik, akkor kezdő dátumként az aktuális hónap első napját használja. Ha a tranzakció dátuma a tizenhatod vagy későbbi, akkor a kezdő dátum a következő hónap első napja legyen.</li></ul><p>Ezt a beállítást tranzakciószinten lehet frissíteni.</p> |
| Rövid távú halasztási módszer | <p>Válassza ki a rövid távú halasztás módját: **Nincs**, Görgető **időszakok** vagy **Rögzített év**.</p><p>|
| Halasztás feladási módja | <p>Válassza ki a halasztásos tranzakciók létrehozásához használt módszert:</p><ul><li>**Mérleg** – a mérlegfeladási módszerrel halasztó tranzakciókat hozhat létre.</li><li>**Eredmény – az** eredmény feladási módszerrel halasztott tranzakciókat hozhat létre. A tranzakciók feladása során áttekintheti a számlabizonylatot, és láthatja az olyan további bejegyzéseket, amelyek kiegyenlítik a kezdeti könyvelési és könyvelési ellenösszegeket.</li></ul> |
| Nyereség és veszteség sztornírozása jóváíráson | <p>**Megjegyzés:** Ez a mező csak akkor érhető el, ha **a Halasztás** **feladási mód mezőjének beállítása Eredmény**.</p><p>Adja meg, hogy az eredmény összegei sztornírozva vannak-e, amikor a számlázási ütemezésre vagy értékesítési rendelésre sztorníroznak, felmondást vagy visszatérítést alkalmaznak:</p><ul><li>**Igen** – sztornírozhatja az eredményösszegeket, és jóváírási helyesbítési összeget alkalmazhat a halasztás ütemezésében.<p>Ha a visszaszétadás félúton történik egy számlázási időszakon keresztül, az összegek csak időkorreknálnak meg.</p></li><li>**Nem** – nem jön létre tranzakció az eredményhez, ha a számlázási ütemezésre vagy értékesítési rendelésre ad fel egy kompenzációs, felmondási vagy visszatérítési tranzakciót.</li></ul> |
| **Felismerés** lap | |
| Általános naplók automatikus feladása | <p>Adja meg, hogy a bevétel- és költség halasztások által létrehozott naplóbejegyzéseket automatikusan feladja-e a program:</p><ul><li>**Igen** – automatikusan feladja a bevétel- és kiadáshalasztások által létrehozott naplóbejegyzéseket.<p>**Tipp:** Az **Igen** választásával megakadályozhatja a bizonylatok manuális módosításaiból következő inkonzisztenciákat a könyvelésben.</p></li><li>**Nem** – a bevétel- és költség halasztások alapján létrehozott naplóbejegyzések feladása nem történik meg automatikusan. A naplókat manuálisan kell feladni.</li></ul> |
| Elszámolási napló összegzése | <p>Annak megadása, hogy az felismerési bizonylatok összesítése alapértelmezés szerint meg van-e jelölve:</p><ul><li>**Igen** – egyetlen bizonylat létrehozása minden olyan felismerési sorhoz, amelyek dátuma megegyezik. Egy bizonylat minden olyan sorát, amelyekhez azonos számla van konszolidálva, egyetlen sorba kell konszolidálni.</li><li>**Nem** – bizonylat létrehozása minden egyes felismerési sorhoz.</li></ul><p>Ezt a beállítást az Felismerés feldolgozása **lapon frissítheti**.</p> |
| Alapértelmezett naplónév | A bevétel- és költség halasztási folyamatokból ( például az elszámolás feldolgozásában) létrehozott naplók nevének kiválasztása. |
| Elszámolási naplósor leírása | <p>Válassza ki a naplóbizonylati sor leírásában megjelenő leírást:</p><ul><li>**Ütemezési sorok dátumai** – az ütemezési sorok dátumának megjelenítése a naplósor leírásában.</li><li>**Eredeti tranzakció részletei** – az eredeti tranzakció információinak megjelenítése a naplósor leírásában.<p>**Példa:** USMF-0001, CIV-00839, software Revenue</p></li></ul> |
| **Számsorozatok** lap | Ezen a lapon beállíthatja a bérlet számsorozatok alapértelmezett értékeit. A számsorozatot generáló varázsló segítségével automatikusan generálhatja és hozzárendelheti a számsorozatokat. Nem kell megváltoztatni a számsorozatot, hacsak nem szeretné manuálisan módosítani a létrehozott számsorozatokat. |
| Ütemezés száma | A halasztások ütemezésében használt számsorozat. |

## <a name="deferral-templates"></a>Halasztási sablonok

A Halasztássablonok **lapon** határozhat meg olyan sorsablonokat, amelyek halasztások ütemezéséhez használatosak.

Íme néhány a sablon használatának előnyei közül:

* A halasztás hosszát a program automatikusan kiszámítja.
* Engedélyezi az olyan halasztások ütemezését, amelyekben kimarad a felismerés időszaka.
* A halasztások automatizálása a sablon termékhez, termékcsoporthoz, termékkategóriához, vevőhöz vagy vevőcsoporthoz való hozzárendelése által automatizálható. A sablon-hozzárendelés a Halasztás **alapértelmezései lapon történik**.

A sablonokhoz több időszaki gyakoriság is használható: napi, havi vagy pénzügyi időszakok.

A sablonsorok egy típusból (**felismert** **vagy** kihagyott) és az időszak hosszából állnak. Az kihagyott sorokban 0 (nulla) összeg van a halasztás ütemezési sorában. Ez a viselkedés akkor lehet hasznos, ha nem szeretné elismerni a bevételt minden időszakban.

### <a name="create-a-deferral-template"></a>Halasztássablon létrehozása

Halasztássablon létrehozásához kövesse az alábbi lépéseket.

1. A Halasztássablonok **lapon** válassza az Új **lehetőséget**.
2. Adjon meg **egy** nevet a Sablon mezőben.
3. Adjon meg egy leírást a **Leírás** mezőben.
4. Az Időszak **gyakorisága mezőben** válassza ki az időszak gyakoriságát.
5. Ha **a** sorok listájának tetejéhez hozzá szeretne adni egy sort, válassza a Hozzáadás lehetőséget, **a** lista aljára pedig a Hozzáfűzés lehetőséget.
6. A Típus **mezőben** válassza ki az időszak típusát.
7. Az Időszak **hossza mezőben** adja meg az időszak hosszát.
8. Ismételje meg az 5–7. lépést minden további szükséges sorra.
9. Válassza a **Mentés** lehetőséget.

## <a name="deferral-defaults"></a>Halasztás alapértékei

A Halasztások **alapértelmezései** lapon beállíthatja a cikkek alapértelmezett halasztásszámláit, és alapértelmezett sablonokat rendelhet a halasztható cikkekhez. Halasztások számláit is be lehet állítani a költségekhez, és sablonokat lehet hozzárendelni a halasztható költségekhez.

**Halasztás cikk szerint**

Cikkekkel (például értékesítési rendelésekkel) rendelkező tranzakciókhoz számlákat és sablonokat rendelhet bizonyos cikkekhez és vevőkhöz. Ezeket a beállításokat használja a program alapértelmezett értékként egy tranzakció halasztása esetén. Ahhoz, hogy a tranzakció alapértelmezés szerint elalasztható legyen, **be kell állítania a cikkeket a Halasztható cikkek lapon**.

**Halasztás számla szerint**

Olyan tranzakciók esetén, amelyek nem tartalmaznak cikkeket (például általános naplókat), megadhatja a halasztások számláit. Ha ezeket a számlákat használja egy tranzakciósoron, akkor a tranzakció automatikusan halasztottként lesz megjelölve. A megfelelő sablont és felismerési számlát hozzárendeli a rendszer a tranzakciósorhoz.

**Minden tranzakciótípus (például az Értékesítési rendelés, a Beszerzés és a Főkönyvi napló lapon)**

A lapon található számlák azok a fő számlák, amelyek nem rendelkezik pénzügyi dimenziókkal. Az elismert számla pénzügyi dimenziói a vevőtől vagy a cikktől függnek, a szervezettől függően.

Minden sablonsornak vagy egy sorsablonnal, vagy esemény alapú sablonnal kell lennie. Nem lehet mindkettő.

### <a name="for-sales-orders"></a>Értékesítési rendelésekhez

A következő lépések szerint adja meg az értékesítési rendelések halasztás alapértelmezett értékeit.

1. Az Értékesítési **rendelés lapon** válassza ki a halasztás típusát.
2. Sor hozzáadásához válassza a **Hozzáadás** lehetőséget.
3. A Cikk-kód **mezőben** válassza ki a cikk-kódot. A cikk kódja meghatározza a halasztás alapértelmezett értékeinek alkalmazását.
4. A cikk-kód alkalmazásának meghatározása:

    * Ha a **Cikk-kód mező** tábla **·** **vagy csoport beállításra van** állítva, akkor a Cikk-kapcsolat mezőben válassza ki a cikk-kapcsolatot.**·**
    * Ha a Cikk-kód mező **beállítása Kategória** **, válassza ki a kategóriakapcsolatot a Kategóriakapcsolatban** **.**
    * Ha a **Cikk-kód mező** értéke **Mind**, az alapértelmezett értékek minden vonatkozó rekordra érvényesek.

5. A számlakód alkalmazásának meghatározása:

    * Ha a **Számlakód mező** beállítása **Tábla** **vagy** Csoport, válassza ki a számlakapcsolatot a Számlakapcsolat **mezőben.**
    * Ha a **Számlakód mező** beállítása **Mind**, a számla minden rekordra érvényes.

6. A Fő **számla mezőben** válassza ki a halasztás fő számláját.
7. **Ha a Halasztás** **feladási** módja mező beállítása Eredmény, **·** **válassza** ki a kezdeti bevételszámlát a Kezdeti bevétel számla mezőjében, és a Bevétel ellenszámlája mezőben a bevétel ellenszámláját.
8. **Ha a Rövid** **·** **távú** halasztás módszer mezője Az időszakok vagy a Rögzített év beállítású, **a Rövid távú halasztásszámla mezőben válassza ki a rövid távú halasztás számláját.**
9. Sablonnál a Sor hozzáadásához **használhatja a Hozzáadás** lehetőséget.
10. A Cikk-kód **mezőben** válassza ki a cikk-kódot.
11. A cikk-kód alkalmazásának meghatározása:

    * Ha a **Cikk-kód mező** tábla **·** **vagy csoport beállításra van** állítva, akkor a Cikk-kapcsolat mezőben válassza ki a cikk-kapcsolatot.**·**
    * Ha a **Cikk-kód mező** beállítása **Kategória**, válassza ki a kategóriakapcsolatot a Kategóriakapcsolat **mezőben**.
    * Ha a **Cikk-kód mező** értéke **Mind**, az alapértelmezett értékek minden vonatkozó rekordra érvényesek.

12. A számlakód alkalmazásának meghatározása:

    * Ha a **Számlakód mező** beállítása **Tábla** **vagy** Csoport, válassza ki a számlakapcsolatot a Számlakapcsolat **mezőben.**
    * Ha a **Számlakód mező** beállítása **Mind**, a számla minden vonatkozó rekordra vonatkozik.
    * Válassza ki a straight line sablont **a Straight Line sablon** mezőben, vagy az **esemény alapú sablont az Esemény alapú sablon mezőben**.

13. Válassza a **Mentés** lehetőséget.

### <a name="for-purchase-orders"></a>Beszerzési rendelésekhez

A beszerzési rendelések alapértelmezett halasztásértékének megadásához kövesse ezeket a lépéseket.

1. A Beszerzés **lapon** válassza ki a halasztás típusát.
2. Sor hozzáadásához válassza a **Hozzáadás** lehetőséget.
3. A Cikk-kód **mezőben** válassza ki a cikk-kódot.
4. A cikk-kód alkalmazásának meghatározása:

    * Ha a **Cikk-kód mező** tábla **·** **vagy csoport beállításra van** állítva, akkor a Cikk-kapcsolat mezőben válassza ki a cikk-kapcsolatot.**·**
    * Ha a **Cikk-kód mező** beállítása **Kategória**, válassza ki a kategóriakapcsolatot a Kategóriakapcsolat **mezőben**.
    * Ha a **Cikk-kód mező** értéke **Mind**, az alapértelmezett értékek minden vonatkozó rekordra érvényesek.

5. A számlakód alkalmazásának meghatározása:

    * Ha a **Számlakód mező** beállítása **Tábla** **vagy** Csoport, válassza ki a számlakapcsolatot a Számlakapcsolat **mezőben.**
    * Ha a **Számlakód mező** beállítása **Mind**, a számla minden vonatkozó rekordra vonatkozik.

6. A Fő **számla mezőben** válassza ki a halasztás fő számláját.
7. **Ha a Halasztás** **feladási** módja mező beállítása Eredmény, **·** **válassza** ki a kezdeti bevételszámlát a Kezdeti bevétel számla mezőjében, és a Bevétel ellenszámlája mezőben a bevétel ellenszámláját.
8. **Ha a Rövid** **·** **távú** halasztás módszer mezője Az időszakok vagy a Rögzített év beállítású, **a Rövid távú halasztásszámla mezőben válassza ki a rövid távú halasztás számláját.**
9. A sablonok sor hozzáadásához **válassza a Hozzáadás** lehetőséget. 
10. A Cikk-kód **mezőben** válassza ki a cikk-kódot.
11. A cikk-kód alkalmazásának meghatározása:

    * Ha a **Cikk-kód mező** tábla **·** **vagy csoport beállításra van** állítva, akkor a Cikk-kapcsolat mezőben válassza ki a cikk-kapcsolatot.**·**
    * Ha a **Cikk-kód mező** beállítása **Kategória**, válassza ki a kategóriakapcsolatot a Kategóriakapcsolat **mezőben**.
    * Ha a **Cikk-kód mező** értéke **Mind**, az alapértelmezett értékek minden vonatkozó rekordra érvényesek.

12. A számlakód alkalmazásának meghatározása:

    * Ha a **Számlakód mező** beállítása **Tábla** **vagy** Csoport, válassza ki a számlakapcsolatot a Számlakapcsolat **mezőben.**
    * Ha a **Számlakód mező** beállítása **Mind**, a számla minden vonatkozó rekordra vonatkozik.
    * Válassza ki a straight line sablont **a Straight Line sablon** mezőben, vagy az **esemény alapú sablont az Esemény alapú sablon mezőben**.

13. Válassza a **Mentés** lehetőséget.

### <a name="for-general-journals"></a>Általános naplókhoz

A következő lépések szerint adja meg a halasztás alapértelmezett értékeit az általános naplóbejegyzések számára.

1. Válassza a Főkönyvi **napló lapot**.
2. Halasztásnál válassza a Hozzáadás lehetőséget **sor** hozzáadásához.
3. **Ha a Rövid** **·** **távú** halasztás módszer mezője Az időszakok vagy a Rögzített év beállítású, **a Rövid távú halasztásszámla mezőben válassza ki a rövid távú halasztás számláját.**
4. A Halasztás **számla** mezőben válassza ki a halasztás számláját.
5. Az Felismerési **számla** mezőben válassza ki az elismert számlát.
6. **Ha a Halasztás** **feladási** módja mező beállítása Eredmény, **·** **válassza** ki a kezdeti bevételszámlát a Kezdeti bevétel számla mezőjében, és a Bevétel ellenszámlája mezőben a bevétel ellenszámláját.
7. Válassza ki a straight line sablont **a Straight Line sablon** mezőben, vagy az **esemény alapú sablont az Esemény alapú sablon mezőben**.
8. Válassza a **Mentés** lehetőséget.

### <a name="for-free-text-invoices"></a>Szabadszöveges számlákhoz

A szabadszöveges számlák alapértelmezett halasztásértékének megadásához kövesse ezeket a lépéseket.

1. Válassza a Szabadszöveges **számla fület**.
2. Halasztásnál válassza a Hozzáadás lehetőséget **sor** hozzáadásához.
3. A számlakód alkalmazásának meghatározása:

    * Ha a **Számlakód mező** beállítása **Tábla** **vagy** Csoport, válassza ki a számlakapcsolatot a Számlakapcsolat **mezőben.**
    * Ha a **Számlakód mező** beállítása **Mind**, a számlakód minden vonatkozó rekordra vonatkozik.

4. A Halasztás **számla** mezőben válassza ki a halasztás számláját.
5. **Ha a Rövid** **·** **távú** halasztás módszer mezője Az időszakok vagy a Rögzített év beállítású, **a Rövid távú halasztásszámla mezőben válassza ki a rövid távú halasztás számláját.**
6. Az Felismerési **számla** mezőben válassza ki az elismert számlát.
7. **Ha a Halasztás** **feladási** módja mező beállítása Eredmény, **·** **válassza** ki a kezdeti bevételszámlát a Kezdeti bevétel számla mezőjében, és a Bevétel ellenszámlája mezőben a bevétel ellenszámláját.
8. Válassza ki a straight line sablont **a Straight Line sablon** mezőben, vagy az **esemény alapú sablont az Esemény alapú sablon mezőben**.
9. Válassza a **Mentés** lehetőséget.

### <a name="for-invoice-journals"></a>Számlanaplókhoz

A számlanapló bejegyzéseinek alapértelmezett halasztásértékeit a következő lépések szerint adhatja meg.

1. Válassza a Számlanapló **lapot**.
2. Halasztásnál válassza a Hozzáadás lehetőséget **sor** hozzáadásához.
3. A számlakód alkalmazásának meghatározása:

    * Ha a **Számlakód mező** beállítása **Tábla** **vagy** Csoport, válassza ki a számlakapcsolatot a Számlakapcsolat **mezőben.**
    * Ha a **Számlakód mező** beállítása **Mind**, a számlakód minden vonatkozó rekordra vonatkozik.

4. A Halasztás **számla** mezőben válassza ki a halasztás számláját.
5. **Ha a Rövid** **·** **távú** halasztás módszer mezője Az időszakok vagy a Rögzített év beállítású, **a Rövid távú halasztásszámla mezőben válassza ki a rövid távú halasztás számláját.**
6. Az Felismerési **számla** mezőben válassza ki az elismert számlát.
7. **Ha a Halasztás** **feladási** módja mező beállítása Eredmény, **·** **válassza** ki a kezdeti bevételszámlát a Kezdeti bevétel számla mezőjében, és a Bevétel ellenszámlája mezőben a bevétel ellenszámláját.
8. Válassza ki a straight line sablont **a Straight Line sablon** mezőben, vagy az **esemény alapú sablont az Esemény alapú sablon mezőben**.
9. Válassza a **Mentés** lehetőséget.

### <a name="items-that-are-deferred-by-default"></a>Alapértelmezés szerint halasztott cikkek

A Halasztott **cikkek** lapon meghatározhatja, hogy alapértelmezés szerint mely cikkekre van halasztva. Beállíthatja, hogy milyen típusú tranzakciókra kell halasztani a cikkeket. Megadhatja, hogy egyetlen cikk legyen halasztva, vagy egy teljes cikkcsoport vagy kategória.

Halasztottként adja meg a cikkeket, válassza ki az alapértelmezett számlákat és sablonokat a Halasztás **alapértelmezései lapon**. Ha nincsenek kiválasztva a számlák és a sablonok, akkor azok a tranzakciósorok, amelyekbe ezeket a cikkeket beírták, nem lesznek elhalasztva.

Halasztott cikkek esetén a halasztás a hozzájuk társított értékesítési vagy beszerzési kategória alapján történik, a halasztás beállításai a kategórián alapulnak. Ha viszont a kategória nincs **kiválasztva** a Kategóriakapcsolat mezőben, a rendszer a rangsorban magasabb szintű kategória halasztásbeállítását használja. Felvehet például egy **Otthoni videoértékesítési** kategóriát, de nem egy Televízió értékesítési **kategóriát**. Halasztott cikket ad hozzá, **amely** a televízió kategóriához van társítva, **akkor** a cikkhez a kezdőlap halasztásbeállítását használja a rendszer.

### <a name="set-up-deferred-items"></a>Halasztott cikkek beállítása

A halasztott cikkek beállítását a következő lépésekkel lehet beállítani.

1. A Cikkek alapértelmezés **szerint halasztott** lapján válassza ki a kívánt lapot: **Értékesítési rendelés vagy** **Beszerzés**.
2. Sor hozzáadásához válassza a **Hozzáadás** lehetőséget.
3. A Cikk-kód **mezőben** válassza ki a cikk-kódot.
4. A cikk-kód alkalmazásának meghatározása:

    * Ha a **Cikk-kód mező** beállítása **Csoport** **vagy** Tábla, akkor a Cikk-kapcsolat mezőben válassza ki a cikk-kapcsolatot.**·**
    * Ha a **Cikk-kód mező** beállítása **Kategória**, válassza ki a kategóriakapcsolatot a Kategóriakapcsolat **mezőben**.

5. Ismételje meg a 2–4. lépést minden további szükséges sorra.
6. Válassza a **Mentés** lehetőséget.

## <a name="deferred-charges"></a>Halasztott költségek

A Halasztások **költségei lapon** meghatározhatja, hogy alapértelmezés szerint mely költségeket halasztja a program.

> [!NOTE]
> * Jelenleg csak az értékesítési rendeléseken érhetőek el a halasztható költségek.
> * A költségeket csak a sor szintjén lehet halasztani. Ha az értékesítési rendelés fejlécének szintjén el kell halasztani egy díjat, a költség beállítható halasztott cikkként az értékesítési rendelés egy külön sorában.
> * Szabadszöveges számla díjának halasztása esetén a díjat külön halasztott számlasorként kell megadni.
> * Ez a funkció nem áll rendelkezésre a támogatási költségekhez és a bevétel-felosztási funkciókhoz.

### <a name="set-up-deferred-charges"></a>Halasztott költségek beállítása

A halasztott költségek beállítását a következő lépések szerint hajtsa végre.

1. A Halasztások **költségei lapon** kattintson a Hozzáadás **gombra** sor hozzáadásához.
2. A Költségkód **mezőben** válassza ki a költségkódot.
3. A Költségkapcsolat **mezőben** válassza ki a költségkapcsolatot.
4. Ismételje meg az 1–3. lépést minden további szükséges sorra.
5. Válassza a **Mentés** lehetőséget.

## <a name="event-based-deferral-templates"></a>Eseményalapú halasztási sablonok

Az Esemény **alapú** **halasztássablonok lapon meghatározhatja azokat az esemény alapú halasztássablonokat, amelyek a halasztások tranzakcióiban használhatók, és amelyek társítva vannak a Halasztások alapértelmezései lapon**.

### <a name="create-an-event-based-template"></a>Esemény alapú sablon létrehozása

A következő lépésekkel lehet esemény alapú halasztássablont létrehozni.

1. Az Esemény alapú **halasztássablonok** lapon válassza az Új **lehetőséget**.
2. A Sablon **mezőbe** írja be a sablon egyedi nevét.
3. Adjon meg egy leírást a **Leírás** mezőben.
4. A Felosztás **típusa mezőben** válassza ki a felosztás típusát:

    * **Változó összeg** – adott összeg felosztása minden egyes beírt sorhoz.
    * **Egyenlő összeg** – minden beírt sorhoz ugyanazt az összeget osztja fel. 
    * **Százalék** – az egyes sorokhoz megadott százalékértéken alapuló összeg felosztása.
    * **Százalékos teljesítési** érték – halmozott teljesítési érték felosztása minden beírt sorhoz.
    * **Változó mennyiség** – adott mennyiség felosztása minden egyes megadott sorhoz.

5. Állítsa Az Egységenkénti **külön** események létrehozása lehetőséget Igen **beállításra**, ha az eseménysorokat egyenletesen szeretné felosztani a számlatranzakcióban szereplő egységek számán. Állítsa Nem **beállításra**, ha nem szeretné felosztani az eseménysorokat.
6. A Lejárati **számla** mezőben válassza ki a lejárati fiókot.
7. Ha **a** sorok listájának tetejéhez hozzá szeretne adni egy sort, válassza a Hozzáadás lehetőséget, **a** lista aljára pedig a Hozzáfűzés lehetőséget.
8. A Leírás **mezőbe** írja be az esemény leírását.
9. Ha a **Felosztás típusa mező** értéke **Százalék**, adja meg a felosztási százalékot a Felosztási százalék **mezőben**. A százalékos értéknek 0 (nulla) és 100 között kell lennie. Ha üresen hagyja **a Felosztási** százalék mezőt, a százalék 0-nak számít. A százalékértékek összege **a** lap alján található Összes százalék mezőben jelenik meg, és az összegnek 100-nak kell lennie.
10. Adja meg **a** Hónapok a lejáratig mezőben, hogy hány hónapra legyen érvényes az esemény. A tranzakció halasztásának lejárati dátumát a program automatikusan beírta ezen érték alapján.
11. Jelölje be **a Feladáskor jelölőnégyzetet**, ha a tranzakció feladása során automatikusan fel kell ismernie a bevételt. Ha a jelölőnégyzetet törölve hagyja, a bevételt manuálisan kell elismerni.
12. Az Eseti **számla** mezőben válassza ki az esemény esetfelismerési számláját, ha az esemény a teljes halasztás-ütemezéstől eltérő számlát használ. Ez a mező a feladáskor való felismeréssel **együtt** használatos.
13. Ismételje meg a 7–12. lépést minden további szükséges sorra.
14. Válassza a **Mentés** lehetőséget.
