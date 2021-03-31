---
title: Raktári kiadási szabály
description: Ez a témakör a Raktári kiadási szabály funkcióval kapcsolatban tartalmaz tájékoztatást, amely rugalmasságot biztosít a raktárba történő kiadás során. Olyan konfigurációs beállítást ad hozzá, amely azt szabályozza, hogy a rendszer engedélyezi-e a részlegesen lefoglalt rendeléssorok kiadását.
author: mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: b23ef104b918f44eed6508319d9b58f2b8355ff1
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5228417"
---
# <a name="release-to-warehouse-rule"></a>Raktári kiadási szabály

[!include [banner](../includes/banner.md)]

A *Raktári kiadási szabály* funkció rugalmasságot biztosít a raktárba történő kiadás során. Minden raktárhoz felvesz egy konfigurációs beállítást. Ezzel a beállítással megadhatja, hogy az adott raktárhoz a részlegesen lefoglalt rendelési sorok kiadhatók-e. Ez a funkció a speciális áttárolási funkciókkal együtt működik olyan helyzetekben, amikor a rendelési sor mennyiségének egy része egy beszerzési forrással szemben van megjelölve, de a fennmaradó rész feldolgozható a raktárban is. Ennélfogva a sor kiadható, így a rendelkezésre álló készletmennyiség raktári feldolgozása folytatható.

## <a name="turn-on-and-initialize-the-release-to-warehouse-rule-feature"></a>A Raktári kiadási szabály funkció bekapcsolása és inicializálása

### <a name="turn-on-the-feature"></a>A funkció bekapcsolása

A *Raktári kiadási szabály* funkciót használata előtt be kell kapcsolni a rendszerben. A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához. A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:

- **Modul:** *Raktárkezelés*
- **Szolgáltatás neve:** *Raktári kiadási szabály*

### <a name="initialize-the-feature"></a>A funkció inicializálása

Miután a funkció be van kapcsolva a rendszerben, inicializálnia kell azt, hogy a szabályt az összes raktár esetében a helyes kezdeti állapotába állítsa.

- Olyan raktárak esetében, amelyeknél nem engedélyezett a raktárkezelés, a szabály kezdetben a **Nem alkalmazható** értékre van beállítva.
- Olyan raktárak esetében, amelyeknél engedélyezett a raktárkezelés, a szabály kezdetben a **Részleges foglalás engedélyezése** értékre van beállítva.

A funkció inicializálásához és az összes raktárra vonatkozó kiadási szabály beállításához hajtsa végre az alábbi lépéseket.

1. Lépjen a **Raktárkezelés \> Beállítás \> Raktárkezelési paraméterek** részre.
1. A **Raktárkezelési paraméterek** oldal **Általános** lapjának **Vállalat adatai** szakaszában válassza ki a **Raktárba történő kiadás inicializálása** szabály hivatkozását. (Ha a hivatkozás nem jelenik meg, akkor a funkció vagy nincs bekapcsolva, vagy már inicializálva van.)
1. Amikor a program megkérdezi, hogy megerősíti-e a műveletet, válassza az **Igen** lehetőséget a funkció inicializálásához.

## <a name="set-the-release-to-warehouse-rule-for-each-warehouse"></a><a name="set-option-warehouse"></a>Raktári kiadási szabály beállítása az egyes raktárakhoz

Miután a funkció be van kapcsolva, és a rendszer inicializálása megtörtént, a raktáraknak lesz kezdeti beállítása, ahogy azt az előző részben ismertették. Ezt a beállítást az egyes raktárak esetében a következő lépésekkel lehet módosítani.

1. Ugorjon a **Raktárkezelés \> Beállítás \> Raktár \> Raktárak** pontra.
1. Válassza ki a konfigurálni kívánt raktárt.
1. Válassza ki a **Szerkesztés** parancsot, hogy a lapot szerkesztési módba helyezze.
1. A **Raktár** gyorslap **Foglalások** szakaszának **Készletfoglalási követelmények** mezője határozza meg, hogy a rendelések részleges felszabadítása engedélyezett-e. Válasszon a következő értékek közül:

    - **Nem alkalmazható** – A funkció első bekapcsolása és inicializálása alkalmával a rendszer automatikusan hozzárendeli ezt az értéket a raktárkezelés számára nem engedélyezett raktárakhoz. Ezt nem lehet módosítani. Ez az érték nem használható olyan raktárak esetében, amelyeknél engedélyezve van a raktárkezelés.
    - **Részleges foglalás engedélyezése** – A rendelések csak akkor adhatók fel, ha a mennyiségek le vannak foglalva. A rendszer kiértékeli, hogy a le nem foglalt mennyiséget megjelölte-e a program a speciális áttárolásra, és szükség szerint megjelöli a mennyiséget. Ha nincs megadva jelölés, akkor a rendszer csak a lefoglalt mennyiséghez készít munkát. A funkció első bekapcsolása és inicializálása alkalmával a rendszer automatikusan hozzárendeli ezt az értéket a raktárkezelés számára engedélyezett raktárakhoz. Ez az érték nem használható olyan raktárak esetében, amelyeknél nincs engedélyezve a raktárkezelés.
    - **Teljes foglalás szükséges** – A rendelések csak akkor adhatók fel, ha a teljes mennyiség le van foglalva. Nem adhatók fel, ha a teljes mennyiség nincs fizikailag lefoglalva, vagy nincs áttárolásra tervezve. Ez az érték nem használható olyan raktárak esetében, amelyeknél nincs engedélyezve a raktárkezelés.

1. Válassza a **Mentés** lehetőséget.

## <a name="scenarios"></a>Forgatókönyvek

Ez a szakasz két olyan esetet mutat be, amelyekkel megtudhatja, hogy a funkció milyen módon működik, és hogyan kell használni.

### <a name="make-sample-data-available"></a>A mintaadatok elérhetővé tétele

Ha ezeket a forgatókönyveket az itt megadott mintaadatok és értékek alapján kívánja elvégezni, akkor egy olyan rendszert kell használnia amelynél a szokásos [demóadatok](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) telepítve vannak. Emellett az **USMF** jogi személyt is ki kell választani a kezdés előtt.

Ezeket a forgatókönyveket a gyártási rendszerben végzett munka során a funkció használatához útmutatásként is használhatja. Ebben az esetben azonban a saját értékeit kell helyettesítenie, és előfordulhat, hogy bizonyos típusú kötelező rekordok hiányoznak, amelyeket a szabvány demóadatok biztosítanak.

### <a name="scenario-1-require-full-release-no-planned-cross-docking"></a><a name="scenario1"></a>1. eset: Teljes foglalás szükséges (nincs tervezett áttárolás)

Ez a példa azt mutatja be, hogyan működik a funkció olyan raktárak esetében, amelyek **Teljes foglalás szükséges** értékre vannak beállítva.

1. Ugorjon a **Raktárkezelés \> Beállítás \> Raktár \> Raktárak** pontra.
1. A _62._ raktárban adja meg a **Készletfoglalási követelmények** mezőben a **Teljes foglalás szükséges** értéket a témakör korábbi [Raktári kiadási szabály beállítása az egyes raktárakhoz](#set-option-warehouse) részében említett módon.
1. Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.
1. Új értékesítési rendelés létrehozásához kattintson az **Új** elemre.
1. Az **Értékesítési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:

    - A **Vevő** gyorslapon adja meg a **Vevőfiók** mezőt az _US-004_ számára.
    - Az **Általános** gyorslap **Raktár** mezőjében állítsa be az _62_ értéket.

1. Válassza az **OK** gombot az új beszerzési rendelés létrehozásához és a párbeszédpanel bezárásához.
1. A program megnyitja az új értékesítési rendelést. Egy üres sort tartalmaz a rács **Értékesítési rendelés sorai** szakaszában. Ezen a soron állítsa be a következő értékeket:

    - **Cikkszám:** *A0001*
    - **Mennyiség:** *2*

1. Válassza ki a **Sor hozzáadása** lehetőséget egy új sor hozzáadásához, és állítsa be a következő értékeket:

    - **Cikkszám:** *A0002*
    - **Mennyiség:** *2*

1. Válassza ki az első rendelési sort, majd a **Készlet** menüben, a rács felett válassza a **Foglalás** pontot.
1. A **Foglalás** oldalon válassza ki az **Adag foglalása** lehetőséget, hogy lefoglalja a kiválasztott sor teljes mennyiségét a raktárban.
1. Zárja be a **Foglalás** lapot, hogy visszatérjen az értékesítési rendeléshez.
1. Ne foglalja le a második rendelési sort.
1. Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Kiadás raktárba** lehetőséget.
1. Figyelje meg, hogy a következő hibaüzenet jelenik meg: „A teljes mennyiséget fizikailag le kell foglalni.” Ezért a rendszer nem hoz létre munkát, szállítmányt vagy terhelést a rendeléshez.

    > [!NOTE]
    > Ha részben lefoglalja a második sort, ugyanaz a hibaüzenet jelenik meg.

### <a name="scenario-2-allow-partial-release"></a>2. eset: Részleges foglalás engedélyezése

Ez a példa azt mutatja be, hogyan működik a funkció olyan raktárak esetében, amelyek **Részleges foglalás engedélyezése** értékre vannak beállítva.

1. Ugorjon a **Raktárkezelés \> Beállítás \> Raktár \> Raktárak** pontra.
1. A _62._ raktárban adja meg a **Készletfoglalási követelmények** mezőben a **Részleges foglalás engedélyezése** értéket a témakör korábbi [Raktári kiadási szabály beállítása az egyes raktárakhoz](#set-option-warehouse) részében említett módon.
1. Ahogy az [előző esetben](#scenario1) is tette, lépjen az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** lehetőségre, és hozzon létre egy értékesítési rendelést az _US-004_ vevőfiókhoz, a _62_. raktából. Adja hozzá a következő két rendelési sort:

    - **1. sor:** Állítsa be a **Cikkszám** mezőt _A0001_ értékre, a **Mennyiség** mezőt _2_ értékre és az **Egység** mezőt _Db_ értékre.
    - **2. sor:** Állítsa be a **Cikkszám** mezőt _A0002_ értékre, a **Mennyiség** mezőt _2_ értékre és az **Egység** mezőt _Db_ értékre.

1. Ahogy a [korábbi esetben](#scenario1) is tette, foglalja le az 1. rendelési sor teljes mennyiségét, de ne foglalja le a 2. rendelési sort.
1. Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Kiadás raktárba** lehetőséget.
1. Ne feledje, hogy ez alkalommal nem kap hibaüzenetet. Helyette a rendszer a szükséges munkát, szállítmányokat és terheléseket hozza létre, és megjeleníti az eredményeket.
1. A szállítmány, a terhelés és a munka adatainak megtekintéséhez használja a rács fölötti **Raktár** menü beállításait:

    - **1. sor:** Három lehetőség érhető el: **Szállítmány részletei**, **Terhelés részletei** és **Munka részletei**. Válassza ki az egyes beállításokat, ha a rendelést a raktárba történő kiadáskor létrehozott szállítmány, terhelés és munka adatait szeretné megtekinteni.
    - **2. sor:** Csak a **Munka részletei** beállítás érhető el. Jelölje ki, és figyelje meg, hogy nem jött létre munka, mert nincs lefoglalva készlet. Ennélfogva nem jött létre szállítmány vagy terhelés sem.

> [!NOTE]
> Ugyanez az eredmény várható, ha a második sor részben le van foglalva. Ebben az esetben a rendszer létrehozza a munkát a lefoglalt sormennyiséghez, de a nem lefoglalt mennyiséghez nem.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]