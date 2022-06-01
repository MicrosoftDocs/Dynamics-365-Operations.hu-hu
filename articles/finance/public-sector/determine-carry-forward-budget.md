---
title: Az áthozott költségvetés frissítése a beszerzési rendelések és számlák csökkentései után
description: Ez a témakör azt írja le, hogyan lehet szabályozni, hogy mi történjen az áthozott költségvetésben a beszerzési rendelések törlése vagy csökkentése, illetve a számlák csökkentése esetén.
author: TaylorVH
ms.date: 02/11/2022
ms.topic: article
ms.search.form: LedgerFund
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-savanh
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2022-02-01
ms.openlocfilehash: 3b0f06b8d5a38252fc8ff6662f3d454adffffe60
ms.sourcegitcommit: 5b55f2913e736d12e40c227bf3ce3a9abec815bd
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/24/2022
ms.locfileid: "8803042"
---
# <a name="update-the-carry-forward-budget-after-reductions-in-purchase-orders-and-invoices"></a>Az áthozott költségvetés frissítése a beszerzési rendelések és számlák csökkentései után

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Ez a témakör azt írja le, hogyan lehet szabályozni, hogy mi történjen az áthozott költségvetésben a beszerzési rendelések törlése vagy csökkentése, illetve a számlák csökkentése esetén.

A beszerzési rendelések év végi [feldolgozására vonatkozó tudnivalókat lásd: Beszerzési rendelések feldolgozása az év végén](/dynamicsax-2012/appuser-itpro/process-purchase-orders-at-year-end).

## <a name="turn-carry-forward-budget-reductions-for-invoice-variances-on-or-off"></a>Áthozott költségvetés-csökkentések be- és kikapcsolása a számlaeltérésekkel

A rendszer beszerzési rendelés visszavonása vagy csökkentése esetén mindig frissítheti az áthozott költségvetést. Ha viszont számla csökkentése esetén frissíteni szeretné az áthozott költségvetést, *akkor az áthozott költségvetés csökkentése akkor kell bekapcsolni, amikor a* beszerzési rendeléshez kapcsolódó számla az eltérési funkcióval csökken. A rendszergazdák úgy kapcsolhatják be és kapcsolják ki ezt a funkciót, hogy a szolgáltatás a **[Szolgáltatáskezelés munkaterületén](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** keresi meg a funkciót.

## <a name="purchase-order-reductions-and-cancellations"></a>Beszerzési rendelések csökkentései és érvénytelenítései

Attól függetlenül *, hogy az áthozott költségvetés csökkentése, amikor egy beszerzési rendeléshez tartozó számla az eltérési funkcióval csökken, be* van-e kapcsolva az áthozott költségvetés, a minősítési beszerzési rendelés visszavonása vagy csökkentése esetén az áthozott költségvetés frissül. Az egyes főkönyvi alapokat a következőképpen állíthatja be:

- Az áthozott költségvetés megőrzése a létrehozás során.
- Az áthozott költségvetés automatikus kiigazítása az érvénytelen vagy csökkentett összeg eltávolításához.

Az automatikus költségvetés-korrekcióhoz csak az alapot is magában foglaló felosztású beszerzésirendelés-sorok érhetők el. Az automatikus költségvetés-korrekcióra akkor kerül sor, amikor a beszerzési rendelés véglegesített, vagy visszaigazolódik a beszerzési rendelés csökkentése.

## <a name="invoice-reductions"></a>Számlacsökkentések

*Ha az áthozott költségvetés csökkentése, amikor egy* beszerzési rendeléssel szembeni számla az eltérési funkcióval csökken, be lehet-e kapcsolva, megadhatja, hogy az egyes alapok csökkentik-e az áthozott költségvetést a számla csökkentése esetén, valamint a beszerzési rendelés csökkentése vagy érvénytelenné vétele esetén. A számlának áthozott költségvetéssel rendelkezik beszerzési rendeléshez kell lennie. A csökkentések magukban foglalják az áreltéréseket, a költségeltéréseket és az adóeltéréseket. Ha a számlázás során csökkentik az áthozott beszerzési rendeléseket, eltérés jön létre. A számla feladott részszámlája esetén a beszerzési rendelés kötelezettségvállalása az eltérés összeggel csökken. A funkció az eltérés összegére is létrehozza az automatikus költségvetés-korrekciót.

Ha az *áthozott költségvetés csökkentése, ha egy* beszerzési rendeléshez tartozó számla ellenében az eltérési funkció ki van kapcsolva, akkor az áthozott költségvetés ebben az esetben nem csökken. Ebből következően az eltérés összegének fennmaradó áthozott költségvetése marad.

## <a name="configure-the-carry-forward-budget-options-for-each-fund"></a>Adja meg az áthozott költségvetési beállításokat az egyes alapokhoz.

Hajtsa végre ezeket a lépéseket minden olyan főkönyvi alapnál, amelynél a beszerzési rendelés vagy számla csökkentése esetén csökkenteni tudja az áthozott költségvetést.

1. Ugrás a főkönyvi **\> számlatükre alapokhoz \>\>**.
1. Válassza ki a beállítani kívánt alapot.
1. A **Beszerzési rendelés év végi feldolgozás** részen győződjön meg arról, **hogy** a Kijelölt év végi felülbírálat beállítás Beállítása *Igen*.
1. Az **Áthozott költségvetési állapot területen állítsa** be a költségvetés visszaállítását olyankor, **amikor** egy áthozott beszerzési rendelést visszavon vagy csökkentett mező szükséges. A beállítások kismértékben eltérnek attól függően, *hogy a rendszer be van-e kapcsolva az áthozott költségvetés csökkentése, ha egy beszerzési rendeléssel szemben csökkentik a* számlát.

    - Ha a funkció ki van kapcsolva, a rendszer csak visszavont vagy csökkentett beszerzési rendelésekre vált. A beállítási beállítások a következő módon működnek:

        - *Nem* – a rendszer létrehoz egy költségvetési tételjegyzék-bejegyzést a visszavont vagy csökkentett beszerzési rendelések fennmaradó egyenlegéhez.
        - *Igen* – a rendszer engedélyezi a beszerzési rendelések érvénytelen tételét vagy csökkentését, de nem hoz létre költségvetési tételjegyzék-bejegyzést. Az áthozott költségvetés rendelkezésre marad más dokumentumokban való felhasználásra.

    - Ha a funkció be van kapcsolva, a rendszer a számlaeltérésekkel, illetve a visszavont vagy csökkentett beszerzési rendelésekkel együtt továbbküldi a rendszert. A beállítási beállítások a következő módon működnek:

        - *Nem* – a számlaeltérésekkel szemben a rendszer létrehoz egy költségvetési tételjegyzék-bejegyzést az eltérés-csökkentési összegre vonatkozó beszerzési rendeléshez. A visszavont vagy csökkentett beszerzési rendelések esetén ennek a beállításnak ugyanaz a hatása, mint a funkció kikapcsolása esetén.
        - *Igen* – a számlaeltérésekkel a rendszer lehetővé teszi a számlacsökkentést, de nem hoz létre költségvetési tételjegyzék-bejegyzést. Az áthozott költségvetés rendelkezésre marad más dokumentumokban való felhasználásra. A visszavont vagy csökkentett beszerzési rendelések esetén ennek a beállításnak ugyanaz a hatása, mint a funkció kikapcsolása esetén.

## <a name="additional-resources"></a>További erőforrások

- [Beszerzési rendelések év végi feldolgozása](/dynamicsax-2012/appuser-itpro/process-purchase-orders-at-year-end)
- [Általános költségvetési foglalások karbantartása](general-budget-reservation-tasks.md)
- [Alapok az állami szektorban](funds-public-sector.md)
- [Alaptípus beállítása az állami szektor részére](tasks/set-up-fund-public-sector.md)
