---
title: Visszatérítések feldolgozása, felülvizsgálata és feladása
description: Ez a témakör bemutatja, hogyan lehet feldolgozni a Visszatérítés-kezelési ajánlatokat, kiszámítani a kedvezményeket, átnézni a létrehozott tranzakciókat, tranzakciókat feladni és átnézni a feladásokat.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TAMRebateDeal
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 53a24866786f209a1d0f6932bb4f782bf936bd21
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5819256"
---
# <a name="process-review-and-post-rebates"></a>Visszatérítések feldolgozása, felülvizsgálata és feladása

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

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

## <a name="process-rebate-management-deals"></a>Visszatérítés-kezelési ajánlatok feldolgozása

Az ajánlat feldolgozásakor a rendszer kiszámítja az összes beállított vonatkozó visszatérítést és jogdíjat. Csak azok a kiválasztott ajánlatok kerülnek feldolgozásra, amelyek számítási időszakai készen állnak a számításra, és *Aktív* állapotúak. A feldolgozás befejezése után a rendszer létrehoz egy tranzakciókészletet, amelyet áttekinthet, majd feladhat.

> [!NOTE]
> A visszatérítések feldolgozása minden esetben azon a szinten történik, amelyet az egyes ajánlatok **Egyeztetés a következő szerint:** beállítása (*Ajánlat* vagy *Sor*) meghatároz. Az egysoros számításokat csak olyan ajánlatokhoz végezheti el, ahol az **Egyeztetés a következő szerint:** mező *Sor* értékre van állítva.

### <a name="process-all-lines-for-one-or-more-deals"></a>Egy vagy több ajánlat összes sorának feldolgozása

1. Nyissa meg a megfelelő [visszatérítési ajánlatok listaoldalát](rebate-management-deals.md) a kezelni kívánt ajánlattípushoz.
1. Jelölje ki a feldolgozni kívánt ajánlat sorát (vagy nyissa meg a feldolgozni kívánt ajánlatot).
1. A Művelet panel **Visszatérítés-kezelési ajánlatok** lapján, a **Létrehozás** csoportban válassza ki az alábbi parancsok egyikét:

    - **Feldolgozás \> Létesítés** – Létesítsen egy elhatároláskészletet az egyes releváns visszatérítési ajánlatokhoz, de ne tegye közzé azokat.
    - **Feldolgozás \> Visszatérítés-kezelés** – Olyan tranzakciók sorozatának feldolgozása, amelyek az egyes ajánlatokra vonatkozó visszatérítés értékét adják meg.
    - **Feldolgozás \> Leírás** – A korábban könyvelt tranzakciók sztornírozása a leírásukhoz, hogy az új visszatérítési ajánlattranzakciók kiszámíthatók legyenek.

1. A megjelenő párbeszédpanelen állítsa be a **Kezdő dátum** és a **Záró dátum** mezőt a számítás dátumtartományának meghatározásához.
1. A számítás futtatásához válassza az **OK** lehetőséget.

### <a name="process-one-or-more-specific-deal-lines-for-a-selected-deal"></a>Egy vagy több konkrét ajánlatsor feldolgozása egy kiválasztott ajánlathoz

1. Nyissa meg a megfelelő [visszatérítési ajánlatok listaoldalát](rebate-management-deals.md) a kezelni kívánt ajánlattípushoz.
1. Nyissa meg azt az ajánlatot, amelyből egy sort fel szeretne feldolgozni.
1. Jelölje ki a jobb felső sarokban található **Sorok** lapot.
1. A **Visszatérítés-kezelés** gyorslapon jelölje ki a feldolgozni kívánt ajánlatsorok sorát.
1. A **Visszatérítés-kezelés** gyorslap eszköztárán válasszon az alábbi parancsok közül. (Ezek a parancsok csak olyan ajánlatokhoz érhetők el, ahol az **Egyeztetés a következő szerint:** mező *Sor* értékre van állítva.)

    - **Feldolgozás \> Létesítés** – Létesítsen egy elhatároláskészletet az egyes releváns visszatérítési ajánlatsorokhoz, de ne tegye közzé azokat.
    - **Feldolgozás \> Visszatérítés-kezelés** – Olyan tranzakciók sorozatának feldolgozása, amelyek az egyes ajánlatsorokra vonatkozó visszatérítés értékét adják meg.
    - **Feldolgozás \> Leírás** – A korábban könyvelt tranzakciók sztornírozása a leírásukhoz, hogy az új visszatérítési ajánlattranzakciók kiszámíthatók legyenek.

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

## <a name="view-and-edit-rebate-management-transactions"></a>Visszatérítés-kezelési tranzakciók megtekintése és szerkesztése

Egy vagy több ajánlat feldolgozásakor a rendszer olyan tranzakciókat hoz létre, amelyek megtekinthetők, és esetleg szerkeszthetőek a feladásuk előtt.

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

    - Egy vagy több sor igénylésének feladáshoz jelölje ki a megfelelő sorokat, majd a Művelet panelen válassza a **Feladás** lehetőséget. (A **Feladás** gomb csak visszatérítési tranzakciók esetén érhető el. Nem érhető el fedezeti és leírási tranzakciókhoz.) A **Feladás** párbeszédpanelen a **Kezdő dátum** és a **Záró dátum** mező automatikusan be van állítva. Állítsa be a **Feladás dátuma** mezőt, majd kattintson az **OK** lehetőségre.
    - A nyitott vagy fel nem adott tranzakciók összegének módosításához jelölje ki a tranzakciót, majd kövesse az alábbi lépések egyikét:

        - Módosítsa az értéket a **Korrigált összeg** mezőben.
        - Válassza a Művelet panelen a **Korrekció beállítása** lehetőséget. Ezután a **Javított összeg** mezőben megjelenő legördülő párbeszédpanelen adjon meg egy értéket.

> [!NOTE]
> A következő időszak feldolgozásakor a tranzakciólista tartalmazza az előző feladásból származó nem igényelt tranzakciókat, valamint a kiválasztott időszakra vonatkozó új tranzakciókat.

## <a name="post-rebates-transactions"></a>Visszatérítési tranzakciók feladása

A visszatérítések és levonások értékének feladásához futtatnia kell a feladási folyamatot, kivéve, ha beállította a rendszert az automatikus feladásukra.

### <a name="set-up-the-system-to-post-all-transactions-automatically"></a>A rendszer beállítása az összes tranzakció automatikus feladására

Annak beállításához, hogy a rendszer feladja az összes tranzakciót a létrehozásuk után, kapcsolja be a **Naplók automatikus feladása** és/vagy a **Szabadszöveges számlák automatikus feladása** lehetőséget a **Visszatérítés-kezelési paraméterek** lapon. További információkért lásd: [Visszatérítés-kezelési paraméterek](rebate-management-parameters.md).

### <a name="post-transactions-for-all-lines-for-one-or-more-deals"></a>Egy vagy több ajánlat összes sorához tartozó tranzakciók feladása

Ha nem használ automatikus feladást, a vonatkozó ajánlatok feldolgozása után kövesse az alábbi lépéseket egy vagy több ajánlat összes sorához létrehozott tranzakciók áttekintéséhez és feladásához.

1. Nyissa meg a megfelelő [visszatérítési ajánlatok listaoldalát](rebate-management-deals.md) a kezelni kívánt ajánlattípushoz.
1. Jelölje ki a feladni kívánt ajánlat sorát (vagy nyissa meg a feladni kívánt ajánlatot).
1. A Művelet panel **Visszatérítés-kezelési ajánlatok** lapján, a **Létrehozás** csoportban válassza ki az alábbi parancsok egyikét:

    - **Feladás \> Létesítés** – Az elérhető létrehozott elhatárolási tranzakciók feladása.
    - **Feladás \> Visszatérítés-kezelés** – Az elérhető létrehozott visszatérítési tranzakciók feladása.
    - **Feladás \> Leírás** – Az elérhető létrehozott leírási tranzakciók feladása.

1. A megjelenő párbeszédpanelen állítsa be a **Feladási dátum** mezőt: Ezután állítsa be a **Kezdő dátum** és a **Záró dátum** mezőt a feladni kívánt tranzakciók dátumtartományának meghatározásához.
1. Kattintson az **OK** gombra a tranzakciók feladásához.

### <a name="post-transactions-for-one-or-more-specific-deal-lines-for-a-selected-deal"></a>Egy vagy több konkrét ajánlatsor tranzakcióinak feladása egy kiválasztott ajánlathoz

Ha nem használ automatikus feladást, a vonatkozó ajánlatok feldolgozása után kövesse az alábbi lépéseket egy kiválasztott ajánlat egy vagy több adott ajánlatsorához létrehozott tranzakciók áttekintéséhez és feladásához.

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

## <a name="review-rebate-management-journals"></a>Visszatérítés-kezelési naplók áttekintése

A tranzakciók feladása után áttekintheti az eredményül kapott naplókat, dokumentumokat vagy cikkeket. A visszatérítések és jogdíjak céltranzakciói a feladási profilban beállított fizetési típuson és a visszatérítés kimeneti típusán alapulnak. Ha például a visszatérítés kimenete *Cikk* értékre van állítva, a program létrehoz egy értékesítési rendelést, amely a céltranzakciókon keresztül tekinthető meg. Másik lehetőségként, ha a kifizetés a Kötelezettségek használatára van beállítva, a vevőn beállított szállítóhoz szállítói számla jön létre a vevői visszatérítések esetében.

A visszatérítés-kezelési ajánlathoz társított naplóbejegyzések áttekintéshez kövesse az alábbi lépéseket.

1. Nyissa meg a megfelelő [visszatérítési ajánlatok listaoldalát](rebate-management-deals.md) a kezelni kívánt ajánlattípushoz.
1. Válassza ki azt az ügyletet, amelynek a naplóbejegyzéseit meg kívánja vizsgálni.
1. A Művelet panelen, a **Visszatérítés-kezelési ajánlatok** lap **Tranzakciók** csoportjában válassza a **Tranzakciók** vagy **Visszatérítési tranzakciók** lehetőséget a megtekinteni kívánt tranzakciók típusától függően.
1. Győződjön meg arról, hogy a **Megjelenítés** mező *Összes* vagy *Feladott* értékre van állítva.
1. Keresse meg és jelölje ki a ellenőrizni kívánt tranzakciógyűjteményt, majd a Művelet panelen válassza az alábbi gombok egyikét. (Ezek a gombok csak akkor érhetők el, ha a kiválasztott tranzakciógyűjteményhez megfelelő feladások léteznek.)

    - **Céltranzakciók** – A kijelölt ajánlat által létrehozott releváns naplók és egyéb típusú dokumentumok áttekintése.
    - **Cikkek** – A kijelölt ajánlat által létrehozott releváns cikkek áttekintése.

1. Megjelenik a megfelelő naplók, dokumentumok vagy cikkek listája. Ha további információt szeretne megtekinteni bármely naplóról, dokumentumról vagy cikkről, jelölje ki a sorát, majd a Művelet panelen válassza a **Részletek megtekintése** lehetőséget.
