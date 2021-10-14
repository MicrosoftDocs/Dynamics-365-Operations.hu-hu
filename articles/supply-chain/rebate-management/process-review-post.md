---
title: Visszatérítések feldolgozása, felülvizsgálata és feladása
description: Ez a témakör bemutatja, hogyan lehet feldolgozni a Visszatérítés-kezelési ajánlatokat, kiszámítani a kedvezményeket, átnézni a létrehozott tranzakciókat, tranzakciókat feladni és átnézni a feladásokat.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TAMRebateDeal
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 803b4d8b287f2b0dc523654e3e1852209f4ea039
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7573537"
---
# <a name="process-review-and-post-rebates"></a>Visszatérítések feldolgozása, felülvizsgálata és feladása

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja, hogyan lehet feldolgozni a Visszatérítés-kezelési ajánlatokat, kiszámítani a kedvezményeket, átnézni a létrehozott tranzakciókat, tranzakciókat feladni és átnézni a feladásokat.

## <a name="change-the-status-of-a-deal"></a>Ajánlat állapotának módosítása

Minden ajánlathoz hozzárendelhet egy állapotot, hogy segítsen nyomon követni. Ez az állapot csak tájékoztatásra szolgál.

1. Válasszon ki egy ajánlatot (például az [**Összes visszatérítés-kezelési ajánlat** oldalt](rebate-management-deals.md)).
1. A Művelet ablaktábla **Visszatérítés-kezelési ajánlatok** lapjának **Karbantartás** csoportjában válassza az **Állapot módosítása** elemet.
1. A **Módosítás állapota** párbeszédpanelen állítsa a **Visszatérítés állapota** mezőt új állapotra.
1. Válassza ki az **OK** lehetőséget.

## <a name="calculate-fifo-purchase-prices"></a>FIFO beszerzési árak kiszámítása

A **FIFO beszerzési ár kiszámítása** ismétlődő feladat futtatásával ki kell számítani az olyan [ajánlatok](rebate-management-deals.md) visszatérítéseit, ahol az **Ár alapja** mező *FIFO* értékre van állítva. A rendszer az először be, először ki (FIFO) szabályt fogja használni az eladott készlet értékének kiszámításához. Ezt az értéket fogja használni a szállítói visszatérítések kiszámításához.

Lépjen a **Visszatérítés-kezelés \> Ismétlődő feladatok \> FIFO beszerzési ár kiszámítása** lehetőségre. A megjelenő párbeszédpanelen válassza az **OK** lehetőséget a számítás futtatásához.

## <a name="create-source-transactions"></a>Forrástranzakciók létrehozása

Létrehozhat értékesítési és beszerzési rendeléseket, amelyekhez forrástranzakciókat tartalmaznak egy megfelelő visszatérítési ügylet létrehozása előtt vagy után is.

Minden egyes ajánlatsor beállítható úgy, hogy automatikusan létrehoz visszatérítési rendelkezést azáltal, hogy feladja a szállítást vagy számlát az értékesítési rendeléshez vagy beszerzési rendeléshez. Az ajánlatsor **Tranzakciótípus** mezőjét állítsa *Szállítás* vagy *Számla* értékre, és a **Feldolgozás feladáskor** beállítás legyen *Igen*. Ha a **Tranzakciótípus** mező beállítása *Rendelés*, akkor a feladáskor történő feldolgozás le van tiltva. Az ügylet aktiválása után létrehozott forrástranzakciók esetében továbbra is lehetséges a feldolgozás, ezzel a jelen témakör későbbi, [Visszatérítés-kezelési ajánlatok feldolgozása](#process-deals) szakasz a foglalkozik.

### <a name="enable-price-details"></a>Áradatok engedélyezése

A forrástranzakciók létrehozása előtt engedélyeznie kell a Kinnlevőségek **Áradatok engedélyezése** beállítását.

1. Lépjen a **Kinnlevőségek \> Beállítások \> Kinnlevőségek paraméterei** pontra.
1. Az **Árak** lapon, az **Áradatok** gyorslapon állítsa az **Áradatok engedélyezése** beállítást *Igen* értékre.

### <a name="create-a-source-transaction"></a>Egy forrástranzakciók létrehozása

Egy forrástranzakciólétrehozásához kövesse az alábbi lépéseket.

1. Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.
1. Válassza az **Új** lehetőséget.

    A visszatérítési igénylések módjának utánzása érdekében most létre kell hoznia egy értékesítési rendelést, ahol a termék és a mennyiség fogja az adott vevőt feljogosítani az árengedményre.

1. A **Vevői számla** mezőben adja meg vagy válassza ki azt a vevőt, aki visszatérítési kedvezményre jogosult.
1. Az értékesítési rendelés létrehozásához kattintson az **OK** lehetőségre.
1. Az **Értékesítésirendelés-sorok** gyorslapon adjon hozzá egy sort, és állítsa be hozzá a következő mezőket:

    - **Cikkszám** – Olyan cikket adjon meg, amely visszatérítésre jogosult.
    - **Mennyiség** – olyan mennyiséget adjon meg, amely megfelel a visszatérítési megállapodásnak, és amely tartalmaz egy sort, ahol az **Alap** mező beállítása *Mennyiség*.
    - **Egységár** Egy árat adjon meg, amely megfelel a visszatérítési megállapodásnak, és amely tartalmaz egy sort, ahol az **Alap** mező beállítása *Érték*.
    - **Hely** – válassza ki azt a helyet, ahol a termék elérhető, és amely visszatérítési kedvezményre jogosít.
    - **Raktár** – Válasszon ki egy raktárat, ahol a termék elérhető, és amely visszatérítési kedvezményre jogosít.

1. Az **Ertékesítésirendelés-sorok** gyorslapon válassza az **Értékesítésirendelés-sor \> Áradatok** lehetőséget. Ez a parancs csak akkor érhető el, ha engedélyezte az áradatokat az előző szakaszban leírtak szerint.
1. Az **Áradatok** oldalon válassza a **Visszatérítések kezelése** gyorslapot. Ez a gyorslap lap felsorolja az aktuális rendelési sorra vonatkozó összes visszatérítéskezelési megállapodást, illetve megjeleníti a becsült visszatérítési összeget is a rendelés pénznemében. Ne feledje, hogy az összegek csak a jövőbeli visszatérítési igények becslései. A tényleges visszatérítési összegek eltérőek lehetnek. Íme néhány olyan tényező, amely a tényleges összegeket befolyásolhatja:

    - A vevő által egy időszaki visszatérítési megállapodás alapján elért teljes értékesítési mennyiség.
    - A vevő a teljes mennyiséget vagy csak részleges mennyiséget küldött vissza.
    - Hogy a vonatkozó értékesítési rendelés a visszatérítés-kezelési ügylethez meghatározott tranzakciótípust elérte-e (*Rendelés, Szállítás* vagy *Számla*).
    - Az üzlet **Kimenet** értéke. Üres visszatérítési összeg jelenik meg az ügyleteknél, ahol a **Kimenet** mező beállítása *Cikk*.

1. A **Részletek** gyorslapon figyelje meg, hogy a **Becsült haszonkulcs** szakasz a következő mezőket tartalmazza. Ezeket a mezőket a Visszatérítés-kezelés adta hozzá. Mindegyik egységenkénti értékeket mutat (míg a **Visszatérítések kezelése** gyorslap mezői a sor összesített értékeit mutatják).

    - **Visszatérítés-kezelés visszatérítési összege** (csak értékesítési rendelések)
    - **Visszatérítés-kezelés jogdíjösszege** (csak értékesítési rendelések)
    - **Visszatérítéskezelés – szállítói visszatérítés összege** (értékesítési rendelések és beszerzési rendelések)

1. Zárja be az **Áradatok** oldalt.
1. Ha az értékesítési rendelés nem kellene, hogy jogosult legyen az előbb megtekintett visszatérítésekre, a következő lépések szerint zárhatja ki a visszatérítéseket. (Általában azonban nem zár ki visszatérítéseket.)

    1. Az **Értékesítési rendelés sorai** gyorslapon válassza a kapcsolódó sort.
    1. Az **Ár és engedmény** lap **Sor részletei** gyorslapján állítsa a **Kizárás a visszatérítés-kezelésből** beállítás *Igen* értékre. Ez a beállítás nem vonatkozik a beszerzési rendelésekre. Ezenkívül csak a vevői visszatérítések kerülnek kizárásra, ha ez a beállítás *Igen*. A vevői jogdíj-visszatérítések és a szállítói visszatérítések továbbra is érvényesek.

1. Válassza a **Csomagjegyzék feladása** lehetőséget a Művelet ablaktábla **Kitárolás és csomagolás** lapjának **Generálás** csoportjában.
1. A **Paraméterek** gyorslapon a **Mennyiség** mezőben válassza az *Összes* lehetőséget.
1. Válassza ki az **OK** lehetőséget.
1. Kattintson az **OK** gombra, ha a rendszer a művelet megerősítését kéri.
1. A Műveleti ablaktábla **Számla** lapján a **Létrehozás** csoportban válassza a **Számla** lehetőséget.
1. A **Paraméterek** gyorslapon a **Mennyiség** mezőben válassza az *Összes* vagy a *Szállítólevél* lehetőséget.
1. Válassza ki az **OK** lehetőséget.
1. Kattintson az **OK** gombra, ha a rendszer a művelet megerősítését kéri.

## <a name="process-rebate-management-deals"></a><a name="process-deals"></a>Visszatérítés-kezelési ajánlatok feldolgozása

Az ajánlat feldolgozásakor a rendszer kiszámítja az összes beállított vonatkozó visszatérítést és jogdíjat. Csak azok a kiválasztott ajánlatok kerülnek feldolgozásra, amelyek számítási időszakai készen állnak a számításra, és *Aktív* állapotúak. A feldolgozás befejezése után a rendszer létrehoz egy tranzakciókészletet, amelyet áttekinthet, majd feladhat.

> [!NOTE]
> A visszatérítések feldolgozása minden esetben azon a szinten történik, amelyet az egyes ajánlatok **Egyeztetés a következő szerint:** beállítása (*Ajánlat* vagy *Sor*) meghatároz. Az egysoros számításokat csak olyan ajánlatokhoz végezheti el, ahol az **Egyeztetés a következő szerint:** mező *Sor* értékre van állítva.

### <a name="process-all-lines-for-one-or-more-deals"></a>Egy vagy több ajánlat összes sorának feldolgozása

1. Nyissa meg a megfelelő [visszatérítési ajánlatok listaoldalát](rebate-management-deals.md) a kezelni kívánt ajánlattípushoz.
1. Jelölje ki a feldolgozni kívánt ajánlat sorát (vagy nyissa meg a feldolgozni kívánt ajánlatot).
1. A Művelet panel **Visszatérítés-kezelési ajánlatok** lapján, a **Létrehozás** csoportban válassza ki az alábbi parancsok egyikét:

    - **Feldolgozás \> Létesítés** – Létesítsen egy elhatároláskészletet az egyes releváns visszatérítési ajánlatokhoz, de ne tegye közzé azokat. Ez a menüpont nem érhető el olyan ajánlatoknál, ahol a **Visszatérítési kimenet** mező értéke *Cikk*.
    - **Feldolgozás \> Visszatérítés-kezelés** – Olyan tranzakciók sorozatának feldolgozása, amelyek az egyes ajánlatokra vonatkozó visszatérítés értékét adják meg.
    - **Folyamat \> Leírás** – A visszatérítési ügylethez és a meghatározott időszakhoz tartozó minden forrásügylet esetében feldolgozza az ellátshoz és a visszatérítés-kezeléshez feladott összegek közötti eltérést. Ez a menüpont nem érhető el olyan ajánlatoknál, ahol a **Visszatérítési kimenet** mező értéke *Cikk*.

1. A megjelenő párbeszédpanelen állítsa be a **Kezdő dátum** és a **Záró dátum** mezőt a számítás dátumtartományának meghatározásához.
1. A számítás futtatásához válassza az **OK** lehetőséget.

### <a name="process-one-or-more-specific-deal-lines-for-a-selected-deal"></a>Egy vagy több konkrét ajánlatsor feldolgozása egy kiválasztott ajánlathoz

1. Nyissa meg a megfelelő [visszatérítési ajánlatok listaoldalát](rebate-management-deals.md) a kezelni kívánt ajánlattípushoz.
1. Nyissa meg azt az ajánlatot, amelyből egy sort fel szeretne feldolgozni.
1. Jelölje ki a jobb felső sarokban található **Sorok** lapot.
1. A **Visszatérítés-kezelés** gyorslapon jelölje ki a feldolgozni kívánt ajánlatsorok sorát.
1. A **Visszatérítés-kezelés** gyorslap eszköztárán válasszon az alábbi parancsok közül. (Ezek a parancsok csak olyan ajánlatokhoz érhetők el, ahol az **Egyeztetés a következő szerint:** mező *Sor* értékre van állítva.)

    - **Feldolgozás \> Létesítés** – Létesítsen egy elhatároláskészletet az egyes releváns visszatérítési ajánlatsorokhoz, de ne tegye közzé azokat. Ez a menüpont nem érhető el olyan ajánlatoknál, ahol a **Visszatérítési kimenet** mező értéke *Cikk*.
    - **Feldolgozás \> Visszatérítés-kezelés** – Olyan tranzakciók sorozatának feldolgozása, amelyek az egyes ajánlatsorokra vonatkozó visszatérítés értékét adják meg.
    - **Folyamat \> Leírás** – A visszatérítési ügylethez és a meghatározott időszakhoz tartozó minden forrásügylet esetében feldolgozza az ellátshoz és a visszatérítés-kezeléshez feladott összegek közötti eltérést. Ez a menüpont nem érhető el olyan ajánlatoknál, ahol a **Visszatérítési kimenet** mező értéke *Cikk*. 

1. A megjelenő párbeszédpanelen állítsa be a **Kezdő dátum** és a **Záró dátum** mezőt a számítás dátumtartományának meghatározásához.
1. A számítás futtatásához válassza az **OK** lehetőséget.

### <a name="process-deals-using-a-batch-job"></a>Ajánlatok feldolgozása kötegelt feldolgozással

Adott ajánlatok vagy ajánlatsorok feldolgozása helyett kötegelt feldolgozást futtathat több ajánlat egyszerre történő feldolgozásához. Opcionálisan alkalmazhat rekordszűrőket és/vagy beállíthat ismétlődő ütemezést. Az ajánlatok kötegelt feladattal történő feldolgozásához kövesse az alábbi lépéseket.

1. Tegye a következők egyikét:

    - Lépjen a **Visszatérítés-kezelés \> Ismétlődő feladatok \> Feldolgozás \> Létesítés** lehetőségre az egyes vonatkozó ügyletek esetében elhatárolások készletének létesítéséhez azok közzététele nélkül.
    - Lépjen a **Visszatérítés-kezelés \> Ismétlődő feladatok \> Feldolgozás \> Visszatérítés-kezelés** lehetőségre olyan tranzakciók sorozatának feldolgozása, amelyek az egyes ajánlatokra vonatkozó visszatérítés értékét adják meg.
    - Lépjen a **Visszatérítés-kezelés \> Ismétlődő feladatok \> Folyamat \> Leírás** lehetőségre a korábban könyvelt tranzakciók sztornírozása a leírásukhoz, hogy az új visszatérítési ajánlattranzakciók kiszámíthatók legyenek.

1. A **Paraméterek** gyorslap **Időszak** szakaszában megjelenő párbeszédpanelen állítsa be a **Kezdő dátum** és a **Záró dátum** mezőket a számítás tranzakcióira vonatkozó dátumtartomány meghatározásához.
1. A **Garancia időszaka** szakaszban állítsa be a **Kezdő dátum** és a **Záró dátum** mezőt a számítás garanciákra vonatkozó dátumtartományának meghatározásához.
1. A **Szerepeltetni kívánt rekordok** gyorslapon beállíthat szűrőket a kötegelt feladat által feldolgozott ajánlatok halmazának korlátozásához. Ezek a beállítások ugyanúgy működnek, mint más típusú kötegelt feladatok esetében.
1. A **Futtatás a háttérben** gyorslapon szükség szerint kötegelt feldolgozást és ütemezési lehetőségeket is megadhat. Ezek a beállítások ugyanúgy működnek, mint más típusú kötegelt feladatok esetében.
1. A számítás futtatásához és/vagy ütemezéséhez kattintson az **OK** gombra.

### <a name="process-deals-by-using-the-rebate-workbench"></a>Ügyletek feldolgozása a visszatérítési munkaterület használatával

Adott ajánlatok vagy ajánlatsorok feldolgozása helyett használj a *visszatérítés munkaterületet* több ügylet egyszerre történő feldolgozásához. Opcionálisan alkalmazhat rekordszűrőket és/vagy beállíthat ismétlődő ütemezést. Nem kell sorokat kijelölni. A rendszer feldolgoz minden sort, amely megfelel a beállított dátumnak és szűrési követelményeknek.

Az ügyeletek kötegelta visszatérítési munkaterülettel történő feldolgozásához kövesse az alábbi lépéseket.

1. Lépjen a **Visszatérítés-kezelés \> Visszatérítés-kezelési ajánlatok \> Visszatérítési munkaterület** részre.
1. A Művelet panel **Visszatérítési munkaterület** lapján, a **Feldolgozás** csoportban válassza ki az alábbi parancsok egyikét:

    - **Feldolgozás \> Létesítés** – Létesítsen egy elhatároláskészletet az egyes releváns visszatérítési ajánlatsorokhoz, de ne tegye közzé az elhatárolásokat.
    - **Feldolgozás \> Visszatérítés-kezelés** – Olyan tranzakciók sorozatának feldolgozása, amelyek az egyes ajánlatsorokra vonatkozó visszatérítés értékét adják meg.
    - **Folyamat \> Leírás** – A visszatérítési ügylethez és a meghatározott időszakhoz tartozó minden forrásügylet esetében feldolgozza az eltérést a tartalék és a visszatérítés feldolgozása között.

1. A **Visszatérítés kezelése** párbeszédpanel **Időszak** szakaszában megjelenő párbeszédpanelen állítsa be a **Kezdő dátum** és a **Záró dátum** mezőket a számítás tranzakcióira vonatkozó dátumtartomány meghatározásához.
1. A **Garancia időszaka** szakaszban állítsa be a **Kezdő dátum** és a **Záró dátum** mezőt a számítás garanciákra vonatkozó dátumtartományának meghatározásához.
1. A **Szerepeltetni kívánt rekordok** gyorslapon beállíthat szűrőket a kötegelt feladat által feldolgozott ajánlatok halmazának korlátozásához. Ezek a beállítások ugyanúgy működnek, mint más típusú kötegelt feladatok esetében.
1. A **Futtatás a háttérben** gyorslapon szükség szerint kötegelt feldolgozást és ütemezési lehetőségeket is megadhat. Ezek a beállítások ugyanúgy működnek, mint más típusú kötegelt feladatok esetében.
1. A számítás futtatásához és/vagy ütemezéséhez kattintson az **OK** gombra.

## <a name="view-and-edit-rebate-management-transactions"></a>Visszatérítés-kezelési tranzakciók megtekintése és szerkesztése

Egy vagy több ajánlat feldolgozásakor a rendszer olyan tranzakciókat hoz létre, amelyek megtekinthetők, és esetleg szerkeszthetőek a feladásuk előtt.

### <a name="view-and-edit-rebate-management-transactions-by-using-the-rebate-deals-list-page"></a>Visszatérítéskezelési tranzakciók megtekintése és szerkesztése a visszatérítési ügyletek listaoldal használatával

Visszatérítéskezelési tranzakciók megtekintéséhez és szerkesztéséhez a visszatérítési ügyletek listaoldal használatával kövesse az alábbi lépéseket.

1. Tegye a következők egyikét:

    - Válassza ki azt az ajánlatot, amelynek a tranzakciói meg szeretné tekinteni (például az [**Összes visszatérítés-kezelési ajánlat** oldalon](rebate-management-deals.md)). A Művelet panelen, a **Visszatérítés-kezelési ajánlatok** lap **Tranzakciók** csoportjában válassza a **Tranzakciók** vagy **Garanciatranzakciók** lehetőséget a megtekinteni kívánt tranzakció típusától függően.
    - Nyisson meg egy ajánlatot, amelynek a részleteit meg szeretné tekinteni (például az [**Összes visszatérítés-kezelési ajánlat** oldalon](rebate-management-deals.md)). Válassza ki azt az ajánlatsort a **Visszatérítés-kezelés** gyorslapon, amelynek a tranzakcióit meg kívánja tekinteni. Ezután az eszköztáron válassza a **Tranzakciók** vagy **Garanciatranzakciók** lehetőséget a megtekinteni kívánt tranzakció típusától függően. (Ezek a gombok csak olyan ajánlatokhoz érhetők el, ahol az **Egyeztetés a következő szerint:** mező *Sor* értékre van állítva.)

1. Megjelenik a **Visszatérítés-kezelési dátumtranzakciók** vagy a **Visszatérítés-kezelési garanciatranzakciók** oldal. Olyan rácsot tartalmaz, amelyben minden sor egyetlen visszatérítési vagy garanciaidőszakból származó tranzakciók gyűjteményét jelöli. Jelöljön ki egy sort a rácsban, majd a Művelet panelen válassza a **Forrástranzakciók** lehetőséget az adott sorhoz tartozó tranzakciók megtekintéséhez.
1. A megjelenő oldal a kijelölt sorhoz tartozó, kijelölt típusú tranzakciók listáját mutatja. A tranzakció típusától függően minden tranzakció releváns részleteket tartalmaz. A garanciatranzakciók esetében csak a listát tekintheti meg. Más típusú tranzakciók esetén a következő műveleteket hajthatja végre ezen az oldalon:

    - Az oldalon található összes igényelt tranzakció teljes értékének ellenőrzéséhez tekintse meg az **Igényelt összeg** mezőt.
    - Bármely tranzakcióval kapcsolatos további információk megtekintéséhez jelölje ki, majd válassza az **Általános**, **Pénzügyi dimenzió** vagy **Dimenzió** lapot.
    - Az vonatkozó csökkentések megtekintéséhez válassza a **Csökkentési tranzakciók** lehetőséget a Művelet panelen. További információért tekintse meg a következőt: [Visszatérítés-csökkentési elvek](rebate-reduction-principle.md).
    - Ha a tranzakciókat igénylési folyamat használata esetén igényeltként vagy nem igényeltként szeretné megjelölni, jelölje ki a megfelelő sorokat, majd a Művelet panelen válassza ki az alábbi parancsok egyikét. (Az igénylési folyamatot a [**Visszatérítéskezelési paraméterek** oldalon](rebate-management-parameters.md) engedélyezheti.)

        - **Igényelt beállítása \> Összes** – Az összes tranzakciót igényeltként jelöli meg.
        - **Igényelt beállítása \> Kiválasztott** – A kijelölt tranzakciókat igényeltként jelöli meg.
        - **Nem igényelt beállítása \> Összes** – Az összes tranzakciót nem igényeltként jelöli meg.
        - **Nem gényelt beállítása \> Kiválasztott** – A kijelölt tranzakciókat nem igényeltként jelöli meg.

    - Az összes vonatkozó sorra vonatkozó jogcím feladásához válassza **Feladás** lehetőséget a Művelet panelen. Ha igénylési folyamatot használ (ha az **Igénylési folyamat használata** beállítás engedélyezve van a **Visszatérítés-kezelés paraméterei** lapon), csak az **Igényelt** sorok kerülnek feladásra. Ellenkező esetben a kiválasztott visszatérítési tranzakció összes forrástranzakciója fel lesz adva. A **Feladás** gomb csak visszatérítési tranzakciók esetén érhető el. Ellátási és leírási tranzakciókhoz nem használható. A **Feladás** párbeszédpanel **Kezdő dátum** és **Záró dátum** mezője automatikusan be van állítva. Állítsa be a **Feladás dátuma** mezőt, majd kattintson az **OK** lehetőségre.
    - A nyitott vagy fel nem adott tranzakciók összegének módosításához jelölje ki a tranzakciót, majd kövesse az alábbi lépések egyikét:

        - Módosítsa az értéket a **Korrigált összeg** mezőben.
        - Válassza a Művelet panelen a **Korrekció beállítása** lehetőséget. Ezután a **Javított összeg** mezőben megjelenő legördülő párbeszédpanelen adjon meg egy értéket.

> [!NOTE]
> Ha igénylési folyamatot használ, a következő időszak feldolgozásakor a tranzakciólista tartalmazza az előző feladásból származó nem igényelt tranzakciókat, valamint a kiválasztott időszakra vonatkozó új tranzakciókat.

### <a name="view-and-edit-rebate-management-transactions-by-using-the-rebate-workbench"></a>Visszatérítéskezelési tranzakciók megtekintése és szerkesztése a visszatérítési munkaterület használatával

Visszatérítéskezelési tranzakciók megtekintéséhez és szerkesztéséhez a visszatérítés munkaterület használatával kövesse az alábbi lépéseket.

1. Lépjen a **Visszatérítés-kezelés \> Visszatérítés-kezelési ajánlatok \> Visszatérítési munkaterület** részre.
1. A **Megjelenítés** mezőt állítsa *Nincs feladva* beállításra.
1. A **Visszatérítés munkaterület** oldalon látható a tranzakciók listája. Minden tranzakció részletes adatokat tartalmaz. Ezek az adatok a tranzakció típusától függően eltérőek. Ezen az oldalon az alábbi műveleteket végezheti el:

    - Bármely tranzakcióval kapcsolatos további információk megtekintéséhez jelölje ki, majd válassza az **Általános**, **Pénzügyi dimenzió** vagy **Dimenzió** lapot.
    - Ha igénylési folyamatot használ, a tranzakciókat megjelölheti igényeltként vagy nem igényeltként. Jelölje ki a kapcsolódó sorokat, majd , a műveletpanelen a **Visszatérítési munkaterület** lapon válassza ki az alábbi parancsok egyikét. (Az igénylési folyamatot a [**Visszatérítéskezelési paraméterek**](rebate-management-parameters.md) oldalon engedélyezheti.)

        - **Igényelt beállítása** – A kijelölt tranzakciókat igényeltként jelöli meg.
        - **Nem igényelt beállítása** – A kijelölt tranzakciókat nem igényeltként jelöli meg.

    - Ha egy vagy több sor igényét szeretné feladni, válassza ki a megfelelő sorokat. Majd a Művelet panel **Visszatérítési munkaterület** lapján válassza a **Feladás** lehetőséget. A **Feladás** gomb elérhető a fedezeti, visszatérítési és leíró tranzakciókhoz. A **Feladás** párbeszédpanel **Kezdő dátum** és **Záró dátum** mezője automatikusan be van állítva. Állítsa be a **Feladás dátuma** mezőt, majd kattintson az **OK** lehetőségre.
    - A nyitott vagy fel nem adott tranzakciók összegének módosításához jelölje ki a tranzakciót, majd kövesse az alábbi lépések egyikét:

        - Módosítsa az értéket a **Korrigált összeg** mezőben.
        - A Művelet panel **Visszatérítési munkaterület** lapján válassza a **Korrekció beállítása** lehetőséget. Ezután a **Javított összeg** mezőben megjelenő legördülő párbeszédpanelen adjon meg egy értéket.

> [!NOTE]
> Ha igénylési folyamatot használ, a következő időszak feldolgozásakor a tranzakciólista tartalmazza az előző feladásból származó nem igényelt tranzakciókat, valamint a kiválasztott időszakra vonatkozó új tranzakciókat.

## <a name="post-rebates-transactions"></a>Visszatérítési tranzakciók feladása

A feldolgozott fedezet értékéhez, a visszatérítés-kezelés összegéhez és a leíráshoz tartozó érték feladásához a feladási folyamatot kell futtatni. A feladási folyamat úgy jelöli meg a fedezetet, a visszatérítés-kezelést vagy a leírási tranzakciókat, ahogy fel lettek adva, és létrehozza a céltranzakciót. Ha nem kell ellenőrizni a céltranzakciót, ezeket a tranzakciókat úgy állíthatja be, hogy automatikusan megtörténjen a feladásuk.

### <a name="set-up-the-system-to-post-all-target-transactions-automatically"></a>A rendszer beállítása az összes céltranzakció automatikus feladására

Annak beállításához, hogy a rendszer egyből feladja az összes céltranzakciót, amikor egy feladási fedezet, visszatérítés-kezelési összeg és leírás létrehozza őket, kapcsolja be a **Naplók automatikus feladása** és/vagy a **Szabadszöveges számlák automatikus feladása** lehetőséget a **Visszatérítés-kezelési paraméterek** lapon. További információkért lásd: [Visszatérítés-kezelési paraméterek](rebate-management-parameters.md).

### <a name="post-transactions-for-all-lines-for-one-or-more-deals"></a>Egy vagy több ajánlat összes sorához tartozó tranzakciók feladása

A vonatkozó ajánlatok feldolgozása után kövesse az alábbi lépéseket egy vagy több ajánlat összes sorához létrehozott tranzakciók áttekintéséhez és feladásához.

1. Nyissa meg a megfelelő [visszatérítési ajánlatok listaoldalát](rebate-management-deals.md) a kezelni kívánt ajánlattípushoz.
1. Jelölje ki a feladni kívánt ajánlat sorát (vagy nyissa meg a feladni kívánt ajánlatot).
1. A Művelet panel **Visszatérítés-kezelési ajánlatok** lapján, a **Létrehozás** csoportban válassza ki az alábbi parancsok egyikét:

    - **Feladás \> Létesítés** – Az elérhető létrehozott elhatárolási tranzakciók feladása.
    - **Feladás \> Visszatérítés-kezelés** – Az elérhető létrehozott visszatérítési tranzakciók feladása.
    - **Feladás \> Leírás** – Az elérhető létrehozott leírási tranzakciók feladása.

1. A megjelenő párbeszédpanelen állítsa be a **Feladási dátum** mezőt: Ezután állítsa be a **Kezdő dátum** és a **Záró dátum** mezőt a feladni kívánt tranzakciók dátumtartományának meghatározásához.
1. Kattintson az **OK** gombra a tranzakciók feladásához.

### <a name="post-transactions-for-one-or-more-specific-deal-lines-for-a-selected-deal"></a>Egy vagy több konkrét ajánlatsor tranzakcióinak feladása egy kiválasztott ajánlathoz

A vonatkozó ajánlatok feldolgozása után kövesse az alábbi lépéseket a kiválasztott ajánlat egy vagy több sorához létrehozott tranzakciók áttekintéséhez és feladásához. Ezek az eljárás csak olyan ajánlatokhoz használható, ahol az **Egyeztetés a következő szerint:** mező *Sor* értékre van állítva.

1. Nyissa meg a megfelelő [visszatérítési ajánlatok listaoldalát](rebate-management-deals.md) a kezelni kívánt ajánlattípushoz.
1. Nyissa meg az ajánlatot, amelynek a sorához tranzakciókat szeretne feladni.
1. Jelölje ki a jobb felső sarokban található **Sorok** lapot.
1. A **Visszatérítés-kezelés** gyorslapon jelölje ki a feladni kívánt ajánlatsorok sorát.
1. A **Visszatérítés-kezelés** gyorslap eszköztárán válasszon az alábbi parancsok közül. (Ezek a parancsok csak olyan ajánlatokhoz érhetők el, ahol az **Egyeztetés a következő szerint:** mező *Sor* értékre van állítva.)

    - **Feladás \> Létesítés** – Az elérhető létrehozott elhatárolási tranzakciók feladása.
    - **Feladás \> Visszatérítés-kezelés** – Az elérhető létrehozott visszatérítési tranzakciók feladása.
    - **Feladás \> Leírás** – Az elérhető létrehozott leírási tranzakciók feladása.

1. A megjelenő párbeszédpanelen állítsa be a **Feladási dátum** mezőt: Ezután állítsa be a **Kezdő dátum** és a **Záró dátum** mezőt a feladni kívánt tranzakciók dátumtartományának meghatározásához.
1. Kattintson az **OK** gombra a tranzakciók feladásához.

### <a name="post-transactions-using-a-batch-job"></a>Tranzakciók feladása kötegelt feladat használatával

Adott ajánlatok vagy ajánlatsorok tranzakcióinak feladása helyett kötegelt feladatot futtathat több ajánlat tranzakcióinak egyszerre történő feladásához. Opcionálisan alkalmazhat rekordszűrőket és/vagy beállíthat ismétlődő ütemezést. A tranzakciók kötegelt feladattal történő feladásához kövesse az alábbi lépéseket.

1. Tegye a következők egyikét:

    - Lépjen a **Visszatérítés-kezelés \> Ismétlődő feladatok \> Feladás \> Fedezet** lehetőségre a rendelkezésre álló, létrehozott elhatárolási tranzakciók feladásához.
    - Lépjen a **Visszatérítés-kezelés \> Ismétlődő feladatok \> Feladás \> Visszatérítés-kezelés** lehetőségre a rendelkezésre álló, létrehozott visszatérítési tranzakciók feladásához.
    - Lépjen a **Visszatérítés-kezelés \> Ismétlődő feladatok \> Feladás \> Leírás** lehetőségre a rendelkezésre álló, létrehozott leírási tranzakciók feladásához.

1. A **Paraméterek** gyorslap **Időszak** szakaszában megjelenő párbeszédpanelen állítsa be a **Feladási dátum** mezőt. Ezután állítsa be a **Kezdő dátum** és a **Záró dátum** mezőt a feladni kívánt tranzakciók dátumtartományának meghatározásához.
1. A **Garancia időszaka** szakaszban állítsa be a **Kezdő dátum** és a **Záró dátum** mezőt a feladni kívánt garanciák dátumtartományának meghatározásához.
1. A **Szerepeltetni kívánt rekordok** gyorslapon beállíthat szűrőket a kötegelt feladat által feldolgozott ajánlatok halmazának korlátozásához. Ezek a beállítások ugyanúgy működnek, mint más típusú kötegelt feladatok esetében.
1. A **Futtatás a háttérben** gyorslapon szükség szerint kötegelt feldolgozást és ütemezési lehetőségeket is megadhat. Ezek a beállítások ugyanúgy működnek, mint más típusú kötegelt feladatok esetében.
1. A számítás futtatásához és/vagy ütemezéséhez kattintson az **OK** gombra.

### <a name="post-transactions-by-using-the-rebate-workbench"></a>Tranzakciók feladása a visszatérítési munkaterület használatával

A létesítő, visszatérítési vagy leírási tranzakciók feldolgozása után a következő lépésekkel lehet a visszatérítés munkaterületet használni az összes ügylet egy vagy több konkrét tranzakciósorához létrehozott tranzakciók áttekintésére és feladására.

1. Lépjen a **Visszatérítés-kezelés \> Visszatérítés-kezelési ajánlatok \> Visszatérítési munkaterület** részre.
1. A rácsban jelölje be az egyes feladni kívánt tranzakciósorok oszlopát. Választhat fel nem adott létesítő, visszatérítési és/vagy leíró tranzakciókat. Az alábbi szabályokat kell betartani:

    - A rendszer az összes olyan sort is feladja, amelyeknél a **Visszatérítési tranzakció száma** megegyezik a kiválasztott sorokkal.
    - A rendszer nem ad fel olyan *Visszatérítési* tranzakciótípusú sorokat, amelyek nincsenek igényeltként megjelölve.
    - Ha olyan sorokat jelöl ki, amelyek már fel vannak adva, a rendszer kihagyja a feladott sorokat.
    - A **Feladás** gomb csak akkor érhető el, ha legalább egy nem feladott sort kiválaszt.

1. A Művelet panel **Visszatérítési munkaterület** lapján, a **Feldolgozás** csoportban válassza a **Feladás** lehetőséget.
1. A **Feladás** párbeszédpanelen állítsa be a **Feladási dátum** mezőt: A program automatikusan beállítja a **Kezdő dátum** és a **Befejező dátum** mezőket a kijelölt sorok **Kezdő dátum** és legkésőbbi **Befejező dátum** értéke alapján.
1. Kattintson az **OK** gombra a tranzakciók feladásához.

## <a name="review-rebate-management-journals"></a><a name="review-journals"></a>Visszatérítés-kezelési naplók áttekintése

A tranzakciók feladása után áttekintheti az eredményül kapott naplókat, dokumentumokat vagy cikkeket. A visszatérítések és jogdíjak céltranzakciói a feladási profilban beállított fizetési típuson és a visszatérítés kimeneti típusán alapulnak. Ha például a visszatérítés kimenete *Cikk*, akkor a rendszer a vevői visszatérítésekhez létrehoz egy-egy értékesítési rendelést, és a szállítói visszatérítésekhez létrehoz egy-egy beszerzési rendelést. Ezek a rendelések a céltranzakciókon keresztül tekinthetők meg. Másik lehetőségként, ha a kifizetés a Kötelezettségek használatára van beállítva, a vevőn beállított szállítóhoz szállítói számla jön létre a vevői visszatérítések esetében.

### <a name="review-journals-by-using-the-rebate-deals-list-page"></a>Naplók áttekintése a visszatérítési ügyletek listaoldalán

A visszatérítés-kezelési ajánlathoz társított naplóbejegyzések áttekintéshez kövesse az alábbi lépéseket.

1. Nyissa meg a megfelelő [visszatérítési ajánlatok listaoldalát](rebate-management-deals.md) a kezelni kívánt ajánlattípushoz.
1. Válassza ki azt az ügyletet, amelynek a naplóbejegyzéseit meg kívánja vizsgálni.
1. A Művelet panelen, a **Visszatérítés-kezelési ajánlatok** lap **Tranzakciók** csoportjában válassza a **Tranzakciók** vagy **Garanciatranzakciók** lehetőséget a megtekinteni kívánt tranzakciók típusától függően.
1. A **Megjelenítés** mezőt állítsa be *Mind* vagy *Feladva* beállításra.
1. Keresse meg és jelölje ki a ellenőrizni kívánt tranzakciógyűjteményt, majd a Művelet panelen válassza az alábbi gombok egyikét. (Ezek a gombok csak akkor érhetők el, ha a kiválasztott tranzakciógyűjteményhez megfelelő feladások léteznek.)

    - **Céltranzakciók** – A kijelölt ajánlat által létrehozott releváns naplók és egyéb típusú dokumentumok áttekintése.
    - **Cikkek** – A kiválasztott ügylet által generált releváns értékesítési megrendelések vagy beszerzési megbízások áttekintése.

1. Megjelenik a megfelelő naplók, dokumentumok vagy cikkek listája. Ha további információt szeretne megtekinteni bármely naplóról, dokumentumról vagy cikkről, jelölje ki a sorát, majd a Művelet panelen válassza a **Részletek megtekintése** lehetőséget.

### <a name="review-journals-by-using-the-rebate-workbench"></a>Naplók áttekintése a visszatérítési munkaterület használatával

A naplóók áttekintéséhez a visszatérítési munkaterülettel kövesse az alábbi lépéseket.

1. Lépjen a **Visszatérítés-kezelés \> Visszatérítés-kezelési ajánlatok \> Visszatérítési munkaterület** részre.
1. A **Megjelenítés** mezőt állítsa be _Mind_ vagy _Feladva_ beállításra.
1. Keresse meg és válassza ki a vizsgálni kívánt sort. Ezután a műveleti ablaktáblán a **Visszatérítési munkaterület** lapon a **Nézet** csoportban válassza a **Céltranzakciók** lehetőséget. Ez a gomb csak akkor érhető el, ha a kiválasztott sorhoz kapcsolódó feladások léteznek.
1. Megjelenik a megfelelő naplók, dokumentumok vagy cikkek listája. Ha további információt szeretne megtekinteni bármely naplóról, dokumentumról vagy cikkről, jelölje ki a sorát, majd a Művelet panelen válassza a **Részletek megtekintése** lehetőséget.

## <a name="rebate-management-transactions-on-the-deduction-workbench"></a>A Visszatérítés munkaterület tranzakciói a levonások munkaterületen

Amikor felad egy olyan Visszatérítés-kezelési tranzakciót, amely a következő **Fizetéstípus** értékek valamelyikét tartalmazza, a rendszer létrehoz egy vevői levonási naplót vagy egy szabadszöveges számlát a megfelelő vevői számlához:

- Vevői levonások
- Adószámla vevői levonásai
- Kereskedelmi kiadások
- Jelentés

A céltranzakció létrehozása és feladása után nyitott tranzakcióként elérhető lesz a **Levonás munkaterület** oldalon (**Értékesítés és marketing \> Kereskedelmi promóciók \> Levonások \> Levonások munkaterülete**). A nyitott tranzakciók **Igény típusa** értéke *Visszatérítés kezelése*, és a nyomon követhetőséghez rendelkezésre áll egy **Visszatérítésitranzakció-szám**. A dátum a visszatérítés-kezelési céltranzakció feladási dátumára van beállítva. Ha a levonási munkaterületen nyitott tranzakciókat egyenlít ki ugyanannak a vevői számlának a meglévő levonásaival, válassza a Műveleti panelen a **Karbantartás \> Egyeztetés** lehetőséget.

További tájékoztatás: [Levonások kezelése a levonás munkaterület használatával](deduction-workbench.md).

## <a name="purge-unposted-transactions"></a>Fel nem adott tranzakciók kiürítése

A létesítő, visszatérítési vagy leírási tranzakciók feldolgozása után kövesse ezeket a lépéseket a kijelölt, fel nem adott tranzakciók kiürítése érdekében.

1. Lépjen a **Visszatérítés-kezelés \> Visszatérítés-kezelési ajánlatok \> Visszatérítési munkaterület** részre.
2. A **Megjelenítés** mezőt állítsa *Nincs feladva* beállításra.
3. Válassza ki és keresse meg a törölni kívánt tranzakciókat. Majd a Művelet panel **Visszatérítési munkaterület** lapján, a **Feldolgozás** csoportban válassza a **Végleges törlés** lehetőséget.
4. Kattintson az **OK** gombra a nem feladott tranzakciók törléséhez.

## <a name="cancel-a-posted-provision"></a>Feladott létesítés törlése

Egy létesítés feldolgozása és feladása után kövesse az alábbi lépéseket a feladott létesítő tranzakciók törléséhez.

1. Lépjen a **Visszatérítés-kezelés \> Visszatérítés-kezelési ajánlatok \> Visszatérítési munkaterület** részre.
2. A **Megjelenítés** mezőt állítsa *Feladva* beállításra.
3. Válassza ki és keresse meg a visszavonni kívánt létesítési tranzakciókat. Majd a Művelet panel **Visszatérítési munkaterület** lapján, a **Feldolgozás** csoportban válassza a **Létesítés törlése** lehetőséget.
4. Kattintson az **OK** gombra a tranzakciók sztornózásához.

Ezek a létesítési sztornózások a megfelelő [Visszatérítés-kezelési naplókban](#review-journals) is láthatók lesznek.
