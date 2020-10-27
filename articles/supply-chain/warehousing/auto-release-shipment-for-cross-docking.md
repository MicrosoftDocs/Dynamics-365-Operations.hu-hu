---
title: Szállítmány automatikus kiadása áttároláshoz
description: Ez a témakör egy olyan áttárolási stratégiát mutat be, amely lehetővé teszi az igény szerinti rendelés automatikus kiadását a raktárban, ha az igény szerinti mennyiséget átadó termelési rendelés készre van jelentve, hogy a mennyiség közvetlenül a termelési kimenetből legyen kiszállítva a kimenő helyre.
author: omulvad
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSCrossDockingTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2019-10-1
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: b86fe2f3ea4321dbe598233018934187ba0d713a
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2020
ms.locfileid: "3983979"
---
# <a name="auto-release-shipment-for-cross-docking"></a>Szállítmány automatikus kiadása áttároláshoz

[!include [banner](../includes/banner.md)]

Ez a témakör egy olyan áttárolási stratégiát mutat be, amely lehetővé teszi az igény szerinti rendelés automatikus kiadását a raktárnak, ha az igény szerinti mennyiséget biztosító termelési rendelés készként van lejelentve. Ilyen módon az igény szerinti rendelés teljesítéséhez szükséges mennyiség közvetlenül a termelés kimeneti helyéről a kimenő helyre kerülhet.

Az áttárolás egy olyan raktárkezelési folyamat, amely a kimenő rendelés teljesítéséhez szükséges mennyiséget a rendelés kimenő vagy előkészítő területére irányítja arról a helyről, ahonnan a bejövő rendelés érkezett. (A bejövő rendelés lehet beszerzési rendelés, átmozgatási rendelés vagy termelési rendelés.) Mivel a speciális áttárolás funkció támogatja az összes beszerzési és igény szerinti rendelést, és megköveteli, hogy a kimenő igényt az áttárolás lehetőség azonosítása előtt felszabadítsák, az automatikus kiadású szállítmányok szolgáltatásai ezeket a jellemzőket tartalmazzák:

- Csak termelési rendeléseket támogat, és csak az értékesítési rendeléseket és az átmozgatási rendeléseket támogat igényként.
- Az áttárolási művelet akkor is elindítható, ha az igényi rendelést nem adták fel a raktárnak az ellátási elismervény rögzítése előtt (azaz a termelés készként jelentése előtt).

Ez az áttárolás funkció két előnnyel jár:

- A raktári műveletek kihagyhatják azt a lépést, amikor a késztermékek mennyiségét a szokásos raktári tárolóhelyre áthelyezik, ha ezeket a mennyiségeket a kimenő rendelés teljesítéséhez egyszerűen újra felveszik. Ehelyett ezek a mennyiségek egy alkalommal áthelyezhetők a kimenő helyről a csomagolási/szállítási helyre. Ilyen módon ez a funkció segít minimalizálni a készlet kezeléseinek számát és végső soron elősegíti az idő- és helymegtakarítás maximalizálást a raktár területén.
- A raktári műveletek elhalaszthatják az értékesítési rendelések és átmozgatási rendelések kiadását a raktárba mindaddig, amíg készre nem lettek jelentve a társított termelési rendeléshez tartozó késztermékek. Ez az előny különösen fontos lehet a rendelésre gyártó termelési környezetekben, ahol a gyártás átfutási ideje általában hosszabb, mint az átfutási idő a készletre gyártó környezetekben.

## <a name="prerequisites"></a>Előfeltételek

| Előfeltételek | Leírás |
|---|---|
| Tétel | A cikknek elérhetőnek kell lennie a raktárkezelő folyamathoz.<p>**Megjegyzés:** A tényleges súllyal rendelkező cikkek nem szerepelhetnek az áttárolási folyamatok között.</p> |
| Raktár | A raktárnak elérhetőnek kell lennie a raktárkezelő folyamathoz. |
| Áttárolási sablonok | Legalább egy olyan áttárolási sablont be kell állítani egy adott raktárhoz, amely az **Ellátási elismervény esetén** igénykiadási irányelvet használja az adott raktárhoz. |
| Munkaosztály | Egy áttárolási munkaosztály azonosítót létre kell hozni az **Áttárolási** munkarendelés típushoz. |
| Munkasablonok | Az **Áttárolási** munkarendeléstípusának munkasablonjai szükségesek áttárolási ki- és betárolási faladathoz. |
| Helyutasítások | Az **Áttárolási** munkarendelés-típus helyirányelvei szükségesek a betárolási munka irányításához olyan helyeken ahol az értékesítési-rendelés mennyiségek csomagolása és kiszállítása történik. |
| Jelölés igény szerinti rendelés és termelési rendelés között | A raktárrendszer a kimenő rendelési szállítmány automatikus kiadását csak akkor indíthatja el és hozhat létre áttárolási munkát a kimeneti helyről a bejelentés elkészüléskor művelet során, ha az értékesítési rendelések és átviteli rendelések le vannak foglalva és jelölve vannak a termelési rendeléssel szemben. |

## <a name="example-cross-docking-flow"></a>Példa az áttárolási folyamatra

A szokásos áttárolási folyamat a következő fő lépésből áll.

1. Egy értékesítési rendelés elfogadója egy értékesítési rendelést hoz létre egy rendelésre készülő termékhez. A kért mennyiség általában nem áll rendelkezésre, és először elő kell állítani.
2. Az értékesítési rendelés fogadója létrehoz egy termelési rendelést közvetlenül az értékesítési rendelés sorából. Ily módon az értékesítési rendelés fogadója fenntartja a megjelöli az értékesítési rendelés mennyiségét a termelési rendelés mennyiségével szemben. 

    Azt is megteheti, hogy a termelési tervező azt határozza meg, hogy a jelölést frissíteni kell, amikor a tervezett rendelések meg lettek erősítve.

3. A termelési rendelés a következő lépéseken halad végig:

    1. A termelési tervező becsléseket készít, és kiadja a termelési rendelést. (A becslés tartalmazza a nyersanyag-foglalást, és a kiadás tartalmazza a raktárba történő kiadást.)
    2. A raktári dolgozó elindítja és elvégzi a nyersanyag kitárolását a tárolóhelyről a termelés bemeneti helyére a termelési kitárolási feladat szerint.
    3. Az üzemi kezelő elindítja a termelési rendelést.
    4. Az utolsó műveletben a gépkezelő a mobileszköz segítségével készre jelenti a termelési rendelést.

4. A rendszer a beállítás segítségével azonosítja a két csatolt rendelés áttárolási eseményét, majd végrehajtja a következő feladatokat:

    1. Szállítmány létrehozásához automatikusan felszabadítja a társított értékesítési rendelést a raktárnak.
    2. Automatikusan olyan áttárolási munkát hoz létre, amelynek utasításai vannak a késztermékek kiválasztásához a kimeneti helyről, és azok átvitelére a kimeneti helye, amelyhez az értékesítési rendeléshez az áttárolási hely utasítások hozzá vannak rendelve.
    3. Jelzi egy gépkezelőnek, hogy a termelési rendelés készként jelentése azonnal végezze el az áttárolási munkát.

5. Miután befejeződött az áttárolási munka, és a mennyiségek a járműre be lettek rakodva, a kimenő raktári tervező megerősíti az értékesítési szállítmányt.

## <a name="example-scenario"></a>Példaforgatókönyv

Ennél a helyzetnél a demo adatokat kell telepíteni, és az **USMF** demó adatvállalatot kell használnia.

### <a name="set-up-cross-docking-that-uses-the-auto-release-shipment-feature"></a>Automatikus szállítmánykiadást használó áttárolás beállítása

#### <a name="cross-docking-template"></a>Áttárolási sablon

1. Ugorjon a **Raktárkezelés** \> **Beállítás** \> **Munka** \> **Munkasablonokra** helyre.
2. Válassza az **Új** lehetőséget.
3. A **Sorozat száma** mezőben írja be az **1** -es számot.
4. Az **Áttárolási sablon azonosítója** mezőben adjon meg egy nevet, például **XDock\_RAF** .
5. Válassza az **Igény szerinti kiadási irányelv** mezőben az **Ellátási elismervény esetén** lehetőséget.
6. A **Raktár** mezőbe írja be annak a raktárnak a számát, amelybe be szeretné állítani az áttárolási folyamatot. Ehhez a példához válassza ki a következőt: **51** .

    > [!NOTE]
    > Amint kiválasztja az **Ellátási elismervény esetén** lehetőséget az igény szerinti kiadás irányelvnek a sablonhoz, az oldal többi mezője nem érhető el. Hasonlóképpen nem lehet megadni beszerzési forrásokat sem. Ez a viselkedés azért fordul elő, mert automatikus kiadású szállítmányt használó áttárolási funkció csak termelési rendeléseket támogat ellátási forrásként, és azt igényli, hogy az értékesítési rendelések és a termelési rendelések között legyen jelölés. Ha azt választja, hogy a **Beszerzési nyugta** előtt legyen az igény szerinti kiadás házirendje, akkor elérhetők a **Tervezés** és az **Ellátási források** lap mezői elérhetők és szerkeszthetők.

#### <a name="work-classes"></a>Munkaosztályok

1. Ugorjon a **Raktárkezelés** \> **Beállítás** \> **Munka** \> **Munkaosztályok** pontra.
2. Válassza az **Új** lehetőséget.
3. A **Munkaosztály azonosítója** mezőbe írjon be egy nevet, például **CrossDock.**
4. A **Munka rendeléstípusa** mezőben válassza ki az **Áttárolás** elemet.

Ha korlátozni szeretné, hogy milyen típusú raktárakban állíthatók be az áttárolt késztermékek, egy vagy több érvényes helytípust is megadhat.

#### <a name="work-templates"></a>Munkasablonok

1. Ugrás a **Raktárkezelés** \> **Beállítás** \> **Munka** \> **Munkasablonokra** .
2. A **Munka rendeléstípusa** mezőben válassza ki az **Áttárolás** elemet.
3. Válassza az **Új** lehetőséget.
4. A **Sorozat száma** mezőben írja be az **1** -es számot.
5. A **Munkasablon** azonosítója mezőbe írjon be egy nevet, például **CrossDock\_51** .
6. Válassza a **Mentés** lehetőséget.
7. A **Munkasablon részletei** szakaszban válassza az **Új** elemet.
8. Az új sorhoz a **Munkatípus** mezőben válassza ki a **Kitárolás** elemet. A **Munkaosztály-azonosító** mezőben válassza a **CrossDock** lehetőséget.
9. Válassza az **Új** lehetőséget.
10. Az új sorhoz a **Munkatípus** mezőben válassza ki a **Kirakás** elemet. A **Munkaosztály-azonosító** mezőben válassza a **CrossDock** lehetőséget.

#### <a name="location-directives"></a>Helyutasítások

A késztermékek szokásos elraktározási folyamata egy **Betárolási** helyre vonatkozó irányelvet igényel, amely a kitárolt termelési mennyiségek szabályos tárolóhelyre történő mozgatását vezérli. Hasonlóképpen be kell állítani egy továbbszállítási **Betárolási** helyirányelvnél is, amely arra utasítja a munkát, hogy a kész mennyiséget egy olyan kijelölt kimenő helyen tárolja be, amely a kapcsolódó értékesítési rendelés szállítását végzi.

A áttárolás esetében a késztermékek szokásos elraktározásához hasonlóan nem kell létrehoznia a kitárolási munkaművelethez tartozó hely direktívát, mivel a kimeneti hely meg van adva. Ezenkívül a kimenő helyet a program az erőforráshoz kapcsolódó rekordok (azaz az erőforrás, az erőforráscsoport-kapcsolat vagy az erőforráscsoport) vagy a termelési kész áruk alapértelmezett helyekének a raktárban.

1. Ugrás a **Raktárkezelés** \> **Beállítás** \> **Helyutasítások** elemre.
2. A **Munka rendeléstípusa** mezőben válassza ki az **Áttárolás** elemet.
3. Válassza az **Új** lehetőséget.
4. A **Sorozat száma** mezőben írja be az **1** -es számot.
5. A **Név** mezőbe írjon be egy nevet, például **Baydoor.**
6. A **Munkatípus** mezőben válassza a **Betárolás** lehetőséget.
7. A **Site** mezőben válasszon ki a **5** értéket.
8. A **Raktár** mezőben válassza ki az **51** értéket.
9. A **Sorok** gyorslapon válassza az **Új** értéket.
10. A **Záró mennyiség** mezőbe írja be a tartomány maximális mennyiségét (például **1000000** ).
11. Válassza a **Mentés** lehetőséget.
12. A **Helyutasítások műveletei** gyorslapon válassza az **Új** lehetőséget.
13. A **Név** mezőbe írjon be egy nevet, például **Baydoor.**
14. Válassza a **Mentés** lehetőséget.
15. A szokásos lekérdezési konstrukcióval korlátozhatja a betárolási helyeket egy vagy több konkrét helyre. Válassza ki a **Lekérdezés szerkesztése** elemet , majd válassza ki az **51** értéketa **Raktárak** mező feltételeként a **Helyek** táblájában.

### <a name="cross-dock-finished-goods-to-the-outbound-location"></a>Készáruk áttárolása a kimenő helyre

Ha a késztermékek mennyiségét át szeretné tárolni a társított értékesítési rendelés kimenő helyére, hajtsa végre az alábbi lépéseket.

1. Ugorjon az **Értékesítés és marketing** \> **Értékesítési rendelések** \> **Minden értékesítési** rendelés pontra.
2. Válassza az **Új** lehetőséget.
3. Az értékesítési rendelés fejlécében válassza ki a vevő számláját, **US-001** és egy olyan raktárat, amely be van állítva áttároláshoz és a szállítmány automatikus kiadása funkciót használja.
4. Adjon hozzá egy sort egy késztermékhez, és adja meg a **10** mennyiséget.
5. Az **Értékesítésirendelés-sorok** szakaszban a válassza a **Termék-és beszerzési** \> **Termelési rendelést** lehetőséget.
6. Ellenőrizze az alapértelmezett értékeket a termelési **Rendelés létrehozása** párbeszédpanelen, majd válassza a **Létrehozás** parancsot. Létrejön egy új termelési rendelés, és kapcsolva van az értékesítési rendeléshez (azaz le van foglalva és meg van jelölve).
7. Opcionális: Módosítsa a **Mennyiség** mező értékét úgy, hogy az több legyen, mint az értékesítési rendelés teljesítéséhez szükséges érték. Amikor a termelési mennyiséget készként jelentik, a rendszer áttárolási munkát hoz létre a jelzett mennyiséghez és a betárolási munkát a fennmaradó mennyiségre vonatkozóan, a késztermékek elraktározásának szokásos eljárása alapján.

    A korábban említettek szerint az értékesítési rendelés és a termelési rendelés között jelölés szükséges. Ellenkező esetben az áttárolás folyamat nem fog működni. A jelölés több módon is létrehozható:

    - A rendszer automatikusan létrehozhatja a jelölést a következő helyzetekben:

        - A termelési rendelés manuálisan jön létre közvetlenül az értékesítési rendelés sorából (lásd a 6. lépést).
        - A tervezett termelési rendeléseket megerősítik, és a **Jelölés frissítése** mezője **Standard** értékre lesz beállítva.

    - A felhasználó manuálisan is létrehozhatja a jelölést, ha az igény szerinti rendelés sorából megnyitja a **Jelölés** lapot.

    > [!NOTE]
    > Nem lehet manuálisan létrehozni olyan cikkekhez, amelyek normál és súlyozott átlagú Készletmodellek használatára vannak beállítva.

8. A **Termelési rendelés** lap műveleti ablakának **Termelési rendelés** lapján a **Feldolgozás** csoportban válassza a **Becslés** elemet, majd válassza az **OK** lehetőséget. A rendelés becslése megtörténik, és a nyersanyag mennyisége a termeléshez le lesz foglalva.
9. A **Termelési rendelés lap** műveleti ablakában a **Feldolgozás** csoportban válassza ki a **Felszabadítás** elemet, majd válassza az **OK** lehetőséget. A raktári kitárolási munka létrejön a nyersanyagokhoz.
10. A munka megnyitása és áttekintése. A Művelet ablaktábla **Raktár** lapjának **Általános** csoportjában válassza a **Munka részletei** elemet. Jegyezze fel a munkaazonosítót
11. Jelentkezzen be raktáralkalmazásba, hogy munkát futtasson az 51-es raktárban.
12. Válassza a **Termelés** \> **Termelési kitárolás** lehetőséget.
13. Adja meg, hogy melyik munkaazonosító induljon el, és végezze el a nyersanyag kitárolását. 

    Miután a munkát készként jelentik, a nyersanyagok mennyisége a termelési bemenet helyen elérhető el ( **005** az USMF demóadatokban), és a termelési rendelés végrehajtása elindulhat.

14. A **Termelési rendelés** lap műveleti ablakának **Termelési rendelés** lapján a **Feldolgozás** csoportban válassza a **Kezdés** elemet, majd válassza az **OK** lehetőséget.
15. Az alkalmazásban nyissa meg a **Termelés** \> **Befejezés és betárolás** lehetőséget.
16. A **Gyártási azonosító** mezőbe írja be a termelési rendelés számát és az egyéb kötelező részleteket, majd kattintson az **OK** gombra.

Felhívjuk figyelmét, hogy ebben a szakaszban a következő események zajlanak le:

- A raktárba történő kiadás a csatolt értékesítési rendeléshez elindítja.
- A kiadás alapján egy szállítás és egy áttárolási munka jön létre. Ez a munka arra utasítja a raktári kezelőt, hogy kitárolja az értékesítésirendelés-sor teljesítéséhez szükséges mennyiségeket, és azokat az áttárolási hely irányelvében meghatározott kimeneti helyre helyezze.
- Ha a termelési rendelés mennyisége meghaladja az értékesítési rendeléshez szükséges mennyiséget, létrejön a szokásos betárolási munka. Ez a munka arra utasítja a raktári kezelőt, hogy kiválassza azt a mennyiséget a készárukból, ami az áttárolás után marad, és áthelyezze azt a szokásos tárolóhelyre a helyirányelvek alapján.
