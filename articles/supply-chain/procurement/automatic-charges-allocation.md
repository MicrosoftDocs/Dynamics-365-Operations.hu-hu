---
title: A kiadások automatikus felosztása
description: A Microsoft Dynamics 365 Supply Chain Management költség funkciójával automatikusan lefoglalhatók a beszerzési rendelések vagy értékesítési rendelések költségei.
author: Henrikan
ms.date: 09/30/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-10-01
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 6032539e57961998e7130e9cb6578248aaa2843e
ms.sourcegitcommit: 49f29aaa553eb105ddd5d9b42529f15b8e64007e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/01/2021
ms.locfileid: "7592540"
---
# <a name="automatic-allocation-of-charges"></a>A kiadások automatikus felosztása

[!include [banner](../includes/banner.md)]

A kezelt ügyfél vagy az értékesített cikk alapján előfordulhat, hogy specifikus kiegészítő költségeket szeretne alkalmazni. A Microsoft Dynamics 365 Supply Chain Management *költség* funkciójával automatikusan lefoglalhatók a beszerzési rendelések vagy értékesítési rendelések költségei.

Az automatikus költségek, a továbbiakban automatikus költségek, automatikusan alkalmazásra kerülnek, ha létrehoz egy értékesítési rendelést vagy beszerzési rendelést. Az automatikus költségeket definiálhatja adott szállítókhoz, ügyfelekhez, szállítócsoportokhoz, vagy cikkcsoportokhoz. Megadhat automatikus költségeket, amelyek minden szállítóra, vevőre vagy cikkre vonatkoznak.

## <a name="set-up-parameters"></a>Paraméterek beállítása

A **Beszerzés és forrásparaméterek** oldalon néhány olyan beállítás is van, amelyek különösen fontosak, amikor automatikusan szeretné hozzárendelni a költségeket. Ennek a beállításnak a befejezéséhez kövesse az alábbi lépéseket.

1. Nyissa meg a **Beszerzés és forrás \> Beállítás \> Beszerzés és forrás paraméterei** pontot.
1. Nyissa meg az **Árak** lapot.
1. Az **Árak** gyorslapon tegye a következő beállításokat:
    - **Automatikus költségek megkeresése a fejléchez** – Megadja, hogy a költségeket automatikusan hozzá kell-e rendelni a beszerzési rendelési fejlécek között. Állítsa *Igen* beállításra a költségek automatikus elosztásának használatára.
    - **Automatikus költségek megkeresése a sorhoz** – Megadja, hogy a költségeket automatikusan hozzá kell-e rendelni a beszerzési rendelési sorok között. Állítsa *Igen* beállításra a költségek automatikus elosztásának használatára.

## <a name="set-up-charges-codes"></a>Állítsa be a költségkódokat

A kiadások felosztásához először meg kell határoznia a költségkódokat.

1. Tegye a következők egyikét:

    - Beszerzési rendeléseknél: Ugorjon a **Kötelezettségek \> Költségek beállítása \> Költségkódok**.
    - Értékesítési rendeléseknél: Ugorjon a **Kinnlevőségek \> Költségek beállítása \> Költségkódok**.

1. Jelölje be a műveleti ablakban az **Új** lehetőséget az új költségkód létrehozásához.
1. Az új rekord fejlécében állítsa be a következő mezőket:

    - **Költségkód** – adja meg a költség kódját.
    - **Leírás** – Adja meg a költségek leírását.
    - **Cikkáfacsoport** – Ha van ilyen, válasszon ki egy cikkáfacsoportot.
    - **Arány** – ezt a beállítást *Igen* értékre állítja, ha a költséget szeretné arányosítani. Ez az opció csak értékesítési rendelés érhető el.
    - **Maximális összeg** – Adja meg a maximálisan leírható összeget, amely engedélyezve van a költségkódhoz. Ez a mező a szállítói számlák költségének ellenőrzésére használható. Csak beszerzési rendelésekhez érhető el.

        > [!NOTE]
        > A beszerzési rendelések költségének ellenőrzésére szolgáló funkció bekapcsolásához nyissa meg a **Kötelezettségek \> Beállítás \> Kötelezettségek paraméterei** között. A **számla ellenőrzése** gyorslap **Számla érvényesítése** szakaszának beállításához adja meg a **Számlázási egyeztetés ellenőrzésének engedélyezése** beállítást *Igen* értékre.

1. A **feladás** gyorslapon **Tartozik** és **követel** szakaszok találhatók. Adja meg a következő mezőket, attól függően, hogy milyen főkönyvbe szeretné feladni a költséget:

    - **Típus** – válassza ki annak a számlának a típusát, amelybe a feladás folyamatban van ( *Főkönyv*, *vevő* vagy *cikk*).
    - **Feladás** – válassza ki a létrehozni kívánt feladások típusát (például *ügynöki díj* vagy *Vevői elszámolás*).
    - **Számla** – válassza ki azt a számlát, amelyre feladja a költséget.

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

## <a name="create-charge-groups"></a>Költségcsoportok létrehozása

A Költségcsoportok automatikusan lefoglalják a megadott költségeket a vevők vagy szállítók egy csoportjához. Az alábbi szakaszok leírják, hogy hogyan lehet létrehozni és társítani ezeket a költségcsoportokat.

### <a name="charge-groups-for-purchase-orders"></a>Beszerzési rendelések költségcsoportjai

A beszerzési rendelésekhez tartozó költségcsoportok létrehozásához hajtsa végre az alábbi lépéseket.

1. Ugrás a **Kötelezettségek \> Költségek beállítása \>Szállítói költségcsoporthoz**.
1. A Művelet panelen válassza az **Új** lehetőséget egy sor rácshoz való hozzáadásához, majd állítsa be a következő mezőket:

    - **Költségcsoport** – adja meg a költségcsoport nevét.
    - **Leírás** – Adja meg a költségcsoportok leírását.

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
1. Ugrás a **Kötelezettségek \> Szállítói \> Összes szállító** pontra, illetve egy létező szállító megnyitása vagy új szállító létrehozása.
1. A **beszerzési rendelés alapértelmezett értékei** gyorslapján a **beszerzési rendelés** szakaszban adja meg a **költségcsoport** mezőt az imént létrehozott költség csoportnak.

### <a name="charge-groups-for-sales-orders"></a>Értékesítési rendelések költségcsoportjai

Az értékesítési rendelésekhez tartozó költségcsoportok létrehozásához hajtsa végre az alábbi lépéseket.

1. Ugorjon a **Kinnlevőségek \> Költségek beállítása \> Vevői költségcsoportok** pontra.
1. A Művelet panelen válassza az **Új** lehetőséget egy sor rácshoz való hozzáadásához, majd állítsa be a következő mezőket:

    - **Költségcsoport** – adja meg a költségcsoport nevét.
    - **Leírás** – Adja meg a költségcsoportok leírását.

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
1. Lépjen a **Kinnlevőségek \> Ügyfelek \> Összes ügyfél**, és vagy nyisson meg egy meglévő ügyfelet, vagy hozzon létre egy új ügyfelet.
1. A **beszerzési rendelés alapértelmezett értékei** gyorslapján a **értékesítési rendelés** szakaszban adja meg a **költségcsoport** mezőt az imént létrehozott költség csoportnak.

## <a name="define-auto-charges"></a>Automatikus költségek meghatározása

Miután beállította a költségkódokat, hajtsa végre az alábbi lépéseket az automatikus költség meghatározásához.

1. Tegye a következők egyikét:

    - Beszerzési rendelések esetében: ugrás a **Beszerzés \> Beállítás \> Költségek \> Automatikus költség**.
    - Értékesítési rendeléseknél: Ugorjon a **Kinnlevőségek \> Beállítás \> Költségek beállítása \> Automatikus költségek**.

1. A lista ablaktábla **szint** mezőjében válassza ki azt a szintet, amelyen az automatikus díj vonatkozik:

    - *Fő* – A költségek alkalmazása a rendelésfejlécre.
    - *Sor* – A költségek alkalmazása a rendeléssorokra.

1. Válassza ki a szerkeszteni kívánt meglévő automatikus költséget, vagy válassza az **új** lehetőséget az új automatikus költség meghatározásához.
1. A **Számlakód** listán válassza a következő értékek egyikét, hogy meghatározza az érintett számlák hatókörét:

    - *Tábla* – Költségek társítása egy megadott vevőhöz vagy szállítóhoz.
    - *Csoport* – Költségek társítása vegyesköltség-csoporthoz.
    - *Összes* – Költségek társítása az összes vevőhöz vagy szállítóhoz.

1. Az **Ügyfélkapcsolat** vagy **Szállítói kapcsolat** mezőben válasszon egy specifikus ügyfelet vagy szállítót, ha a **Számlakód** mezőt *Tábla* értékre. Ha a **Számlakód** mezőben a *Csoport* lehetőséget választotta, akkor válasszon ki egy vevői vagy szállítói költségcsoportot.
1. A **Cikk-kód** mezőben válassza a következő értékek egyikét, hogy meghatározza az érintett cikkek hatókörét. Csak akkor választhat cikkkódot, ha sor szintjén definiál automatikus költségeket.

    - *Tábla* – Költségek társítása egy meghatározott cikkhez.
    - *Csoport* – Költségek társítása egy cikk költségcsoportjához.
    - *Összes* – Költségek társítása az összes cikkhez.

1. A **Cikk-kapcsolat** mezőben válasszon egy specifikus cikket, ha a **Cikk-kód** mezőben a *Tábla* értéket választja. Ha a **Cikk-kód** mezőben a *Csoport* elemet választotta, válasszon ki egy cikk-költségcsoportot.
1. **Csak értékesítési rendelések esetében:** a **szállítási mód kódja** mezőben válassza a következő értékek egyikét, hogy meghatározza a szállítási módok azon körét, amelyekre hatással lesz:

    - *Tábla* – Költségek társítása egy megadott szállítási módhoz.
    - *Csoport* – Költségek társítása egy szállítási mód csoporthoz.
    - *Összes* – Költségek társítása az összes szállítási módhoz.

1. **Csak értékesítési rendelésekhez:** A **Szállítási mód kapcsolata** mezőben, választania kell egy adott szállítási módot, ha **Szállítási mód kódja** mező értéke *Tábla*. Ha a **Szállítási mód kódja** mező értékét *Csoport* értékre állítja, választania kell egy szállításimód-csoportot.
1. Bontsa ki a **Sorok** gyorslapot a költségek és a költségek árfolyamainak beállítására, amelyeket az aktuális automatikus költség alkalmazásakor használnak. A gyorslap eszköztárán a szükséges számú sor hozzáadására használható. Állítsa be a következő mezőket minden egyes sornál:

    - **Pénznem** – Itt kiválaszthatja a költség kiszámításához használt pénznemet.
    - **Költségkód** - Válassza ki a költség kódját.
    - **Kategória** - Válasszon a következő értékek közül:

        - *Rögzített* – A díj a sorhoz tartozó rögzített összegként kerül megadásra. A rögzített költségek a rendelés fejlécében és a rendeléssorokban szereplő költségek esetén használhatók.
        - *Darabszám* – A költség az egységen alapul. Ezek a költségek a rendelés soraiban használhatók. A rendelések összesítésének kiszámításakor fognak megjelenni.
        - *Százalék* – A díj a sorhoz tartozó százalékként kerül megadásra. A százalékos költségek a rendelés fejlécében és a rendeléssorokban szereplő költségek esetén használhatók.
        - *Vállalatközi százalék* – a költség a vállalatközi rendelések sorában százalékban szerepel. A vállalatközi költségek a rendelés soraiban használhatók.
        - *Külső* – A költség egy külső szolgáltatás által kerül kiszámításra, amely egy vagy több szállítmányozóhoz van hozzárendelve.

    - **Költség értéke** – adja meg a díj értékét a kiválasztott kategória alapján.
    - **Költségek pénznemkódja** – adja meg a költség pénznemét, ha a **pénznem** mezőben megadott pénznemtől eltérő pénznemet szeretne használni. Másik pénznemet csak akkor is használhat, ha a kiválasztott költségkód **Tartozás típusa** vagy **Követelés típusa** mező beállítása vagy *Főkönyv* vagy *Cikk*.
    - **Kezdő érték** - Adja meg az automatikus költség alkalmazásának kezdőösszegét. Az összeg ebben a környezetben a rendelési összegre vonatkozik.
    - **Célérték** - Adja meg az automatikus költség alkalmazásának végösszegét. Az összeg ebben a környezetben a rendelési összegre vonatkozik.
    - **Áfacsoport** – adja meg az áfacsoport.
    - **Telephely** és **raktár** – adja meg a helyet és a raktárat, ha a költséget csak meghatározott telephelyre és raktárra kell alkalmazni.
    - **Megtartás** - Válassza ki ezt a jelölőnégyzetet, a költségtranzakciók számlázás befejezése utáni megtartására úgy, hogy a költség minden alkalommal alkalmazásra kerüljön, ha új számlát hoz létre a kijelölt vevői számlára.

1. **Csak értékesítési rendelések esetében:** Ha a többszintű költséget szeretné kiszámítani, akkor lásd: [az értékesítési rendelések többszintű költsége](/dynamicsax-2012/appuser-itpro/about-tiered-charges-on-sales-orders).

## <a name="allocate-charges-from-the-header-to-a-line"></a>Költség felosztása a fejlécből egy sorba

A következő eljárás bemutatja, hogy hogyan lehet a fejléc-szintű költséget egy sorhoz hozzárendelni. Az eljárás elkezdése előtt a *rögzített összeg* típusának fejléc-szintű költségét és a költség alkalmazásának a rendelését kell megadnia. Ezenkívül a rendelésnek már tartalmaznia kell legalább egy sorelemet.

1. Nyissa meg a beszerzési rendelést vagy a költségrendelést.
1. A műveleti panelen kövesse az alábbi lépések egyikét:

    - Beszerzési rendelések esetében: a **Beszerzés** lap **költségek** csoportjában válassza a **költség felosztása** lehetőséget.
    - Értékesítési rendelések esetében: a **Értékesítés** lap **költségek** csoportjában válassza a **költség felosztása** lehetőséget.

1. A **költségek felosztása a rendelési sorokhoz** párbeszédpanelen adja meg a következő mezőket:

    - **Költségfelosztás** – válassza ki a következő értékek egyikét, hogy meghatározza a díjak felosztásának módját:

        - *Nettó összeg* – a költség felosztása a teljes nettó összeghez viszonyított minden sor összege alapján.
        - *Mennyiség* – a költségek felosztása az egyes sorokhoz tartozó egységek számának megfelelően az egységek számához viszonyítva.
        - *Soronként* – a költségek felosztása egyenlő mértékben az összes sorban.

    - **Költség felosztása sorokhoz** – válassza ki azt az értéket, amely meghatározza, hogy az összes sorra, csak a pozitív sorokra vagy a negatív sorokra legyenek felosztva a költség.
    - **Összes felosztása** - Jelölje be ezt a jelölőnégyzetet, ha a költségeket rendelési sorokra szeretné felosztani, még olyan esetekben is, amikor a költségkód tartozási típusa *Cikk*.
    - **Bevételezett** - Jelölje be ezt a jelölőnégyzetet, ha a bevételezett rendeléssorokra szeretné feloszlatni a költségeket.
    - **Raktározott** - Jelölje be ezt a jelölőnégyzetet, ha a csak raktározott rendeléssorokra szeretné feloszlatni a költségeket.
    - **Választások megjelenítése és meghatározott sorok törlése** – jelölje be ezt a jelölőnégyzetet, ha ki szeretné hagyni a felosztásból a kívánt sorokat. Ha bejelöli ezt a jelölőnégyzetet, megnyílik a **Felosztásból kizárandó sorok kiválasztása** rács. A rácsban csak azok a sorok jelennek meg, amelyeket a **Költségek foglalása sorokhoz** és a **Raktározott** beállítások határozzák meg. Ha például a *Pozitív sorok* opciót választja a **Költségek foglalása sorokhoz** mezőben, és bejelöli a **Raktározott** jelölőnégyzetet, akkor csak azok a sorok jelennek meg a rácsban, amelyek pozitívak és raktározva is vannak. Ezenkívül a rács automatikusan kiszűri azokat a sorokat, amelyeknél a teljes mennyiség már bevételezett. Ha meg van nyitva a rács, törölje a jelet a **Tartalmazza** jelölőnégyzetből minden olyan sorhoz, amelyet ki szeretne zárni a felosztásból. 

        > [!IMPORTANT]
        > A **felosztásból kizárandó sorok kiválasztása** rács használata esetén ügyeljen arra, hogy a rács nyitva maradjon a **felosztás** kiválasztásáig. Ha bezárja a rácsot, mielőtt kiválasztja a **felosztást**, akkor a rácsban megadott beállítások elvesznek. Ezért a rendszer a korábban meghatározott feltételek alapján osztja fel a költséget.

1. Az **Felosztás** gombra kattintva alkalmazza a beállításokat, és zárja be a párbeszédpanelt.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
