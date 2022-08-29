---
title: Értékesítési rendelés szállítási dátumának számítása az "CTP" módszer használatával
description: A ígérő (CTP) funkciók segítségével való valószerű dátumokat lehet adni a vevőknek arra az időpontra, amikor adott árukat ígérni lehet. Ez a témakör azt ismerteti, hogyan lehet beállítani és használni az egyes tervezőmotorok (Tervezési optimalizálás és a beépített motor) CTP készletét.
author: t-benebo
ms.date: 07/20/2022
ms.topic: article
ms.search.form: SalesAvailableDlvDates, SalesTable, CustParameters, InventItemOrderSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-07-20
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 9a2d8a66fe7e68ebd5729a401af3f0efe04051b1
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/06/2022
ms.locfileid: "9229997"
---
# <a name="calculate-sales-order-delivery-dates-using-ctp"></a>Értékesítési rendelés szállítási dátumának számítása az "CTP" módszer használatával

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]

A ígérő (CTP) funkciók segítségével való valószerű dátumokat lehet adni a vevőknek arra az időpontra, amikor adott árukat ígérni lehet. Minden értékesítési sorhoz meg lehet adni egy dátumot, amely figyelembe veszi a meglévő aktuális készletet, termelési kapacitást és szállítási időket.

A ígérhető ([CTP](../../sales-marketing/delivery-dates-available-promise-calculations.md)) szolgáltatás a kapacitási adatok figyelembevével bővíti az ígérethez rendelkezésre álló funkciókat. Míg az "ATP" figyelembe veszi, hogy csak az anyagok rendelkezésre állása áll rendelkezésre, és végtelen kapacitású erőforrásokat feltételez, a CTP figyelembe veszi mind az anyagok, mind a kapacitás elérhetőségét. Így pontosabb képet ad arról, hogy az igényt egy adott időkereten belül kielégítheti-e.

Az ön által használt alaptervezési motortól (tervezési optimalizálás vagy beépített motor) függően a CTP (CTP) egy kissé másképp működik. Ez a témakör azt ismerteti, hogyan lehet beállítani az egyes motorokat. A tervezési optimalizáláshoz rendelkezésre álló mennyiség jelenleg csak a beépített motor által támogatott CTP esetek egy részkészletét támogatja.

## <a name="turn-on-ctp-for-planning-optimization"></a>Az "Egyen rendelkezésre álló mennyiség" bekapcsolása tervezési optimalizáláshoz

A beépített alaptervezési motorhoz mindig rendelkezésre áll a CTP (CTP) mennyiség. Ha azonban tervezési optimalizáláshoz CTP (CTP) javaslatokat szeretne használni, akkor azt a rendszernek kell bekapcsolni. A rendszergazdák használhatják a [funkciókezelési](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és bekapcsolásához. A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:

- **Modul:** *Alaptervezés modul*
- **Funkciónév:** *(előnézet) - CTP tervezési optimalizáláshoz*

## <a name="how-ctp-compares-to-atp"></a>A CTP és az "ATP" viszony viszonya

A CTP és az ATP hasonló, de a CTP gyakran pontosabb eredményt is nyújthat, mint azt az alábbi példa mutatja.

Az A cikk olyan cikk, amely B és C cikkből áll, és az A cikk tényleges készlete 0 (nulla). Ha olyan" ellenőrzést elvégez, amely csak az anyagokat veszi figyelembe, az "ATP" mennyiség szintén 0 (nulla) lesz. Ha azonban egy CTP-ellenőrzést is ellenőriz, a rendszer ellenőrzi a B és C cikkek rendelkezésre állását, ellenőrzi az A cikkből szükséges erőforrásokat, és kiszámítja, hogy az A cikkből hány elemet lehet készletre tenni. Ezen kívül a CTP-számítás ellenőrizheti azokat az erőforrásokat és anyagokat, amelyekre szükség van a B és C cikkből, és azokat felhasználhatja az A cikkből való további mennyiségre.

Az anyagokat és erőforrásokat egyaránt figyelembeó" "CTP" számítás nagyobb mennyiséget is mutathat, mint az anyagokat kizárólag ellenőrző számítás, különösen akkor, ha az ellenőrzés alatt álló cikk rendelésre összeállítandó cikk. Más szóval a CTP funkció az alászámítási funkción alapul, és a kiválasztott értékesítésirendelés-sorra futtatható a várható szállítási dátum kiszámításához.

## <a name="how-ctp-differs-depending-on-the-master-planning-engine-that-you-use"></a>A CTP-mennyiség eltérése a használt alaptervezési motortól függően

Az alábbi táblázat összefoglalja a beépített alaptervezési motor CTP (tervezési optimalizálási) és CTP (CTP) szerinti különbségeit.

| Elem | Tervezési optimalizálás | Beépített alaptervezési motor |
|---|---|---|
| **A szállítási dátum ellenőrzése** a rendelések, rendeléssorok és termékek esetében | *Ígérhető a tervezési optimalizáláshoz* | *Ctp* |
| Számítás ideje | A számítást egy dinamikus terv ütemezett feladatként való futtatása indítja el. | A számítást azonnal elindítja a rendszer minden alkalommal, amikor beír vagy frissít egy értékesítésirendelés-sort. |
| **CTP a Tervezés optimalizálása állapotmező** értékének tervezéshez | <p>A nem *kész érték olyan* rendeléseknél és rendeléssoroknél jelenik meg, amelyek dinamikus terve nem fut le a rendelések és sorok létrehozása vagy legutóbbi frissítése óta.</p><p>A Dinamikus terv futtatásával *azok* a rendelések és sorok mellett megjelenik a Kész érték, amelyeknél a CTP (CTP) mennyiség a visszaigazolt szállítási dátumok kiszámítására használható.</p> | Mindig megjelenik *a Kész* érték. |

## <a name="set-default-delivery-date-control-methods"></a><a name="default-methods"></a> Alapértelmezett szállításidátum-ellenőrzési módszerek beállítása

A rendszer többféle módszerrel számíthatja ki az egyes rendelési sorok és rendeléssorok szállítási dátumának becslését. A leggyakrabban globális alapértelmezett módszerként használni kívánt szállításidátum-ellenőrzési módszert kell beállítania. Az egyes termékekhez egyéni felülbírálásokat is be lehet állítani. Később szükség esetén felülbírálhatja az egyes rendeléssorok és/vagy rendeléssorok alapértelmezett metódusát.

### <a name="set-the-global-default-delivery-date-control"></a><a name="global-default"></a> A globális alapértelmezett szállításidátum-ellenőrzés beállítása

A program minden olyan új rendelési sorra alkalmazza az alapértelmezett szállításidátum-ellenőrzési módszert, ahol nem alkalmazható felülbírálás. A következő lépések szerint választhat egyet.

1. Lépjen a **Kinnlevőségek \> Beállítások \> Kinnlevőségek paraméterei** pontra.
1. A Szállítások **lap** **Szállításvezérlés** gyorslapJán **·**, a Szállítási dátum ellenőrzése mezőben válassza ki a vállalat alapértelmezett módszereként használni kívánt módszert:

    - *Nincs* – ne számítsa ki a szállítási dátumokat.
    - *Értékesítés átfutási ideje* – Az értékesítés átfutási ideje az értékesítés rendelés létrehozása és a szállítás közti idő. A szállítási dátum számítása az alapértelmezett számú napon alapul, és nem veszi figyelembe a készlet rendelkezésre állását, az ismert igényt vagy a tervezett készletet.
    - *Ígérethez* rendelkezésre áll – az ígérethez rendelkezésre álló cikk mennyisége, amely egy meghatározott időpontban ígérhető a vevőnek. Az Ígérethez rendelkezésre álló mennyiség kiszámítása tartalmazza a nem véglegesített készletet, az átfutási időket a tervezett bevételezéseket és kiadásokat.
    - *ATP + kiadási időrés* – a szállítási dátum megegyezik az "Tp" dátum és a cikk kiadási időrtéke alapján. A kiadási időtartalék a szállítandó cikkek előkészítéséhez szükséges idő.
    - *CTP* – a beépített alaptervezési motor által biztosított CTP-számítás használata. Ha tervezés szerinti optimalizálást használ, *a "CTP* " szállításidátum-ellenőrzési módszer nem engedélyezett, és ha be van jelölve, hibát okoz a számítás futtatásakor.
    - *CTP tervezési optimalizáláshoz* – a tervezési optimalizálás által biztosított CTP-számítás használható. Ennek a beállításnak nincs hatása, ha a beépített alaptervezési motort használja.

### <a name="set-delivery-date-control-overrides-for-individual-products"></a>Az egyes termékek szállításidátum-ellenőrzési felülbírálásának beállítása

Felülbírálásokat olyan meghatározott termékekhez rendelhet hozzá, amelyeknél a globális alapértelmezett módszerként megadotttól különböző szállításidátum-ellenőrzési módszert kíván használni.

1. Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.
1. Válassza ki a beállítani kívánt terméket.
1. A Művelet ablaktáblán a **Készlet kezelése** lapon a **Rendelés beállításai** csoportban válassza az **Alapértelmezett rendelési beállítások** lehetőséget.
1. Az Alapértelmezett rendelés **beállításai lapon, az** **Értékesítési rendelés gyorslapon állítsa** **a Szállításvezérlő felülbírálása beállítást Igen beállításra** *.*
1. A Szállítási **dátum ellenőrzése** mezőben válassza ki a kiválasztott termékhez használni kívánt módszert. Elérhetők a Globális alapértelmezett [szállításidátum](#global-default)-ellenőrzés szakaszban leírt beállítások.

## <a name="schedule-ctp-for-planning-optimization-calculations"></a><a name="batch-job"></a> CTP ütemezése tervezési optimalizálási számításokhoz

Ha A tervezéshez CTP (CTP) optimalizálást használ, dinamikus tervet kell futtatnia, hogy a rendszer elindítsa az "CTP" számítások elvégzését, majd állítsa be a visszaigazolt szállítási és kézhezvételi dátumokat az összes kapcsolódó rendeléshez. A tervnek tartalmaznia kell minden olyan tételt, amelynél visszaigazolt szállítási és kézhezvételi dátumok szükségesek. (Ha a beépített tervezőmotorhoz CTP-t használ, akkor a rendszer azonnal helyben számolja ki az egyes mennyiségeket. Emiatt nem kell dinamikus tervet futtatnia ahhoz, hogy látsa a CTP-eredményeket.)

Annak érdekében, hogy a dátumok minden felhasználó számára megfelelő időben rendelkezésre érhetők el, javasoljuk, hogy a megfelelő tervek ismétlődő futtatásához kötegelt feladatokat állítson be. Például egy olyan kötegelt feladat, amely dinamikus terv 30 percenkénti futtatására van beállítva, 30 percenként beállítja a visszaigazolt szállítási és fogadási dátumokat. Ezért a rendeléseket be- és importáló felhasználóknak legfeljebb 30 percet kell várnia a visszaigazolt szállítási és fogadási dátumok fogadására.

A következő lépések szerint állíthat be kötegelt feladatot dinamikus terv rendszeres futtatásához.

1. Ugrás az Alaptervezés **futtatása alaptervezéshez \>\>\>.**
1. Az Alaptervezés **párbeszédpanel** **·** **Paraméterek** gyorsablakában állítsa az Alapterv mezőt a futtatni kívánt dinamikus tervre.
1. A háttérben **futó gyorslapon** állítsa **a Kötegelt feldolgozás** beállítást Igen *beállításra*.
1. Válassza az **Ismétlődés** lehetőséget, és állítsa be a kívánt ütemezést.
1. Az **ütemezés mentéshez kattintson az OK** gombra.
1. A **kötegelt feladat létrehozásához és a párbeszédpanel bezárásához kattintson az OK** gombra.

## <a name="use-ctp-for-built-in-master-planning"></a>CTP használata beépített alaptervezéshez

### <a name="create-a-new-order-by-using-ctp-for-built-in-master-planning"></a>Új rendelés létrehozása beépített alaptervezésre vonatkozó CTP használatával

A rendszer minden alkalommal, amikor új értékesítési rendelést vagy rendeléssort ad hozzá, hozzárendel egy alapértelmezett szállításidátum-ellenőrzési módszert. A rendelési fejléc mindig a globális alapértelmezett módszerrel kezdődik. Ha egy megrendelt cikkhez felülbírálás van hozzárendelve, az új rendelési sor ezt a felülbírálatot használja. Ellenkező esetben az új rendeléssor a globális alapértelmezett módszert fogja használni. Ezért úgy kell beállítani az alapértelmezett metódusokat, hogy azok megegyeznek a leggyakrabban használt szállításidátum-ellenőrzési módszerrel. A rendelés létrehozása után a rendelés fejlécének és/vagy sorának szintjén felülbírálhatja az alapértelmezett módszert. A további tudnivalókat lásd az [Alapértelmezett](#default-methods)[szállításidátum-ellenőrzési módszerek beállítása és a meglévő értékesítési rendelések módosítása az "Alapértelmezett szállítási dátum ellenőrzése" beállítással.](#change-orders)

### <a name="view-confirmed-delivery-dates-when-you-use-ctp-for-built-in-master-planning"></a>Visszaigazolt szállítási dátumok megtekintése a beépített alaptervezésben a CTP (CTP) használata esetén

Ha a beépített alaptervezési motort használja, akkor a rendszer az "CTP" számításokat alkalmazza az olyan rendelésekre és/**·** *vagy rendeléssorokra, amelyekben a Szállítási dátum vezérlő mezője a CTP (CTP) beállítású*.

A beépített alaptervezésben A **CTP** **készletet** használó értékesítési soroknál a rendszer minden értékesítési sor mentésekor automatikusan beállítja a Visszaigazolt szállítási dátum és a Visszaigazolt kézhezvételi dátum mezőket. Ha később módosít egy értékesítési sort (például a mennyiség vagy a telephely módosításával), akkor a program azonnal újraszámja a dátumokat.

- Értékesítésirendelés-sor visszaigazolt szállítási dátumának megtekintéséhez nyissa meg az értékesítési rendelést, és válassza ki az értékesítési sort. Ezután a Szállítás lap **Sor részletei gyorslapján** **·** **ellenőrizze** a Visszaigazolt szállítási dátum és a Visszaigazolt kézhezvételi dátum értékeit.**·**
- Egy teljes rendelés visszaigazolt szállítási dátumának megtekintéséhez nyissa meg az értékesítési rendelést, és válassza a Fejléc **nézetet**. Ezután a Szállítás gyorsététában **ellenőrizze** a **Visszaigazolt szállítási dátum és** a Visszaigazolt **kézhezvételi dátum értékeit**.

## <a name="use-ctp-for-planning-optimization"></a>A CTP használata a tervezés optimalizálása során

### <a name="create-a-new-order-by-using-ctp-for-planning-optimization"></a>Új rendelés létrehozása a CTP használatával tervezési optimalizáláshoz

A rendszer minden alkalommal, amikor új értékesítési rendelést vagy rendeléssort ad hozzá, hozzárendel egy alapértelmezett szállításidátum-ellenőrzési módszert. A rendelési fejléc mindig a globális alapértelmezett módszerrel kezdődik. Ha egy megrendelt cikkhez felülbírálás van hozzárendelve, az új rendelési sor ezt a felülbírálatot használja. Ellenkező esetben az új rendeléssor a globális alapértelmezett módszert fogja használni. Ezért úgy kell beállítani az alapértelmezett metódusokat, hogy azok megegyeznek a leggyakrabban használt szállításidátum-ellenőrzési módszerrel. A rendelés létrehozása után a rendelés fejlécének és/vagy sorának szintjén felülbírálhatja az alapértelmezett módszert. A további tudnivalókat lásd az [Alapértelmezett](#default-methods)[szállításidátum-ellenőrzési módszerek beállítása és a meglévő értékesítési rendelések módosítása az "Alapértelmezett szállítási dátum ellenőrzése" beállítással.](#change-orders)

### <a name="view-confirmed-delivery-dates-when-using-ctp-for-planning-optimization"></a>Visszaigazolt szállítási dátumok megtekintése a CTP (tervezési optimalizálási) mennyiség használata esetén

Ha tervezés szerinti optimalizálást használ, akkor a program az olyan rendelésekre és/**·** *vagy rendeléssorokra alkalmazza a CTP-számításokat, amelyekben a Szállítási dátum vezérlő mező a tervezési optimalizálásnál "CTP" (CTP) beállításra van állítva.*

A **CTP** **tervezéshez** használható értékesítési soroknál a Visszaigazolt szállítási dátum és a Visszaigazolt kézhezvételi dátum mező addig üres marad, amíg nem futtatja a megfelelő dinamikus tervet (általában ismétlődő kötegelt feladat alkalmazásával). A program ezután automatikusan beállítja őket. A további tudnivalókat lásd [: Tervezésoptimalizálási számítások CTP ütemezése](#batch-job).

A **Tervezés szerinti optimalizálás** állapotmezője jelzi, hogy ki vannak-e már számítva a visszaigazolt dátumok minden olyan sorhoz, amely tervezési optimalizálási CTP-t használ. A mező értéke Nem áll készen olyan sorokhoz és rendelésekhez, amelyeknél a *visszaigazolt* szállítási dátumok vagy még nincsenek kiszámítva, vagy más módosítások miatt már nem érvényesek. Megjeleníti a Sorokra kész *érték* és a kiszámított rendelések értékét. Megtekintheti az egyes sorok és a teljes rendelés állapotát.

- Értékesítésirendelés-sor állapotának megtekintéséhez nyissa meg az értékesítési rendelést, és válassza ki az értékesítési sort. Ezután a Szállítás **lap** **Sor** részletei gyorslapján ellenőrizze a **Tervezési** optimalizálás állapotértékhez rendelkezésre álló mennyiség értékét. A **sorHoz a Visszaigazolt** **szállítási dátum** és a Visszaigazolt kézhezvételi dátum mező is megjelenik ezen a lapon, azok számítását követően.
- Egy teljes rendelés állapotának megtekintéséhez nyissa meg az értékesítési rendelést, és válassza a Fejléc **nézetet**. Ezután a Szállítás gyorsjelentésben **ellenőrizze** a **Tervezési** optimalizálás állapotértékhez rendelkezésre álló mennyiség értékét. A **rendeléshez kiszámított** Visszaigazolt **szállítási** dátum és Visszaigazolt kézhezvételi dátum is megjelenik ezen a lapon.

<!-- KFM: The following text may be untrue and needs to be reviewed with the PM for next revision:

The sales orders that are *Ready* or *Not ready* are shown in the **All sales orders** list page. You can check the sales order that are *Ready* or *Not ready* from the sales order list page by filtering on this new status field.

-->

> [!NOTE]
> - Ha azt követően frissíti az értékesítésirendelés-sort, hogy a tervezési optimalizálásban a CTP (CTP) által kiszámított visszaigazolt dátumok vannak hozzá, a rendszer a megfelelő dinamikus terv következő futásáig törli ezeket a dátumokat.
> - Ha olyan kapcsolódó beállítást szerkeszt, amely hatással lehet a meglévő visszaigazolt dátumokra (például az átfutási idők, a foglalások vagy a jelölések módosításával), törölje a megfelelő meglévő rendelések visszaigazolt dátumait. A művelet hatására az egyes érintett sorok állapota Nem készre *változik*. A módosítás hatására a rendszer a dinamikus terv következő futtatásakor újraszámolhatja a visszaigazolt dátumokat.

## <a name="change-existing-sales-orders-so-that-they-use-ctp"></a><a name="change-orders"></a> Meglévő értékesítési rendelések módosítása ctp (CTP) használatára

A szállítási dátum ellenőrzése **bármikor** megváltoztatható bármely nyitott rendelésre. A fejléc szintjén és/vagy mindegyik sorban szükség esetén módosíthatja az értéket.

### <a name="change-to-ctp-at-the-order-header-level"></a>Váltás az "Egyen rendelkezésre álló mennyiség" szintre a rendelés fejlécének szintjén

<!-- KFM: Would be nice to mention how changing this setting on the header affects the individual lines. -->

A rendelés rendelésfejlécben való felhasználása érdekében módosítsa a rendelést, kövesse ezeket a lépéseket.

1. Ugrás a **Kinnlevőségek \> Rendelések \> Minden értékesítési rendelésre**.
1. Nyissa meg a beállítani kívánt értékesítési rendelést, vagy hozzon létre egy újat.
1. Válassza ki **a Fejléc** lehetőséget a fejlécadatok megnyitásához az Értékesítési **rendelés adatai lapon**.
1. A Szállítás **gyorsblokkon** **állítsa** a Szállítás dátuma vezérlőmezőt a használt tervezőmotortól függően a következő értékek egyikére:

    - *CTP* – a beépített alaptervezési motor által biztosított CTP-számítás használata. Ha tervezés szerinti optimalizálást használ, *a "CTP* " szállításidátum-ellenőrzési módszer nem engedélyezett. Ezért ha ezt az értéket választja, hiba történik a számítás futtatásakor.
    - *CTP tervezési optimalizáláshoz* – a tervezési optimalizálás által biztosított CTP-számítás használható. Ennek a beállításnak nincs hatása, ha a beépített alaptervezési motort használja.

<!-- KFM: Additional dialogs are shown here. Review these with the PM and expand this procedure at next revision. -->
1. A módosítások alkalmazásához kattintson az **OK** gombra.

### <a name="change-to-ctp-at-the-order-line-level"></a>Váltás az "CTP" mennyiségre a rendelési sor szintjén

Ha másik szállításidátum-ellenőrzési módszerrel hozott létre rendeléssort, bármikor át lehet válthat "CTP" típusúra. A sor szintjén végrehajtott módosítások nem befolyásolják a többi sort. Előfordulhat azonban, hogy a rendelés szállítási dátumai az egyes frissített sorok számításának változásától függően előre vagy hátrafelé haladnak. <!-- KFM: Confirm this intro at next revision -->

Ha módosítani kell egy rendelést úgy, hogy a sor szintjén a beépített alaptervezésben CTP-t használ, kövesse ezeket a lépéseket.

1. Ugrás a **Kinnlevőségek \> Rendelések \> Minden értékesítési rendelésre**.
1. Nyissa meg a beállítani kívánt értékesítési rendelést, vagy hozzon létre egy újat.
1. Az Értékesítési **rendelés részletei** lap Értékesítésirendelés-sor **gyorslapján** válassza ki a beállítani kívánt értékesítésirendelés-sort.
1. A **Szállítás** **·** **lap** Sor részletei gyorslapján állítsa a Szállítási dátum vezérlőmezőt az alábbi értékek egyikére a használt tervezőmotortól függően:

    - *CTP* – a beépített alaptervezési motor által biztosított CTP-számítás használata. Ha tervezés szerinti optimalizálást használ, *a "CTP* " szállításidátum-ellenőrzési módszer nem engedélyezett. Ezért ha ezt az értéket választja, hiba történik a számítás futtatásakor.
    - *CTP tervezési optimalizáláshoz* – a tervezési optimalizálás által biztosított CTP-számítás használható. Ennek a beállításnak nincs hatása, ha a beépített alaptervezési motort használja.

    **Megjelenik az Elérhető szállítási** és kézhezvételi dátumok párbeszédpanel, amely megjeleníti a rendelkezésre álló szállítási és kézhezvételi dátumokat. Ez a párbeszédpanel ugyanúgy működik a rendeléssorok és a rendelésfejlécek során, mint az előző szakaszban leírtak.

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
