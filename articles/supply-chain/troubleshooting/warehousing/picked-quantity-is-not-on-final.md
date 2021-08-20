---
title: Nem erősítheti meg a szállítmányt, mert a cikkeket nem tárolták ki
description: Nem erősítheti meg a szállítmányt, mert a cikkeket nem tárolták ki
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 7b57d3151852c9a2880185b7d9414e4246b7efb6429fcfce04c7cdae4ee00e37
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6760924"
---
# <a name="you-cant-confirm-a-shipment-because-items-havent-been-picked"></a>Nem erősítheti meg a szállítmányt, mert a cikkeket nem tárolták ki

Hibakód: LoadNotPickedAndMrmedToFinalShippingLocation

## <a name="symptoms"></a>Tünetek

Szállítmány megerősítésekor a rendszer a következő hibaüzenetet jeleníti meg:

> A(z) %1 rakományhoz szükséges egyes cikkek még nem lettek kitárolva és a végső szállítási helyre áthelyezve.

Ezért nem tudja megerősíteni a szállítmányt a betöltéshez.

## <a name="cause"></a>Ok

A rakomány vagy szállítmány jelenleg nem erősíthető meg, mert a következő feltételek valamelyike fennáll:

- A kapcsolódó munkát még nem választották ki és nem helyezték át a végső szállítási helyre.
- A kitárolt munkamennyiség nem egyezik meg a rakománysor létrehozott munkamennyiségével.
- A helyutasítás úgy lett beállítva, hogy a csomagolási hely legyen a végleges kiszállítási hely a hullámsablon tárolóra bontása során.

## <a name="resolution"></a>Megoldás

A rakomány vagy szállítmány jelenleg olyan állapotban van, amelyben a szállítmány megerősítése sikertelen. A probléma javításához végezze el a következő feladatok egyikét:

- Ellenőrizze a rakomány sorait, és győződjön meg róla, hogy minden kapcsolódó munkát befejeztek a végleges kiszállítási helyen, és hogy a mennyiségek megegyeznek.
- Érvénytelenítse azt a munkaazonosítót, amelynél a csomagolási hely a végső szállítási hely, konfigurálja újra a helyutasítást, és adja ki újra a rakományt.

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a>Ellenőrizze a rakomány sorait, és győződjön meg róla, hogy minden kapcsolódó munkát befejeztek a végleges kiszállítási helyen, és hogy a mennyiségek megegyeznek

Az alábbi módon ellenőrizze a rakomány sorait, és győződjön meg róla, hogy minden kapcsolódó munkát befejeztek a végleges kiszállítási helyen, és hogy a mennyiségek megegyeznek.

1. Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.
1. Válassza ki azt a rakományt, amelynél a szállítmányt nem lehet megerősíteni.
1. A **Rakománysorok** gyorslapon válassza ki a sor betöltése lehetőséget.
1. Jegyezze fel a **Munka létrehozott mennyisége** mező értékét.
1. A Művelet ablaktábla **Betöltések** lapjának **Kapcsolódó információk** csoportjában válassza a **Munka** elemet.
1. Ellenőrizze, hogy a munkát a végső kiszállítási helyen befejezték-e, és hogy a kitárolt munkamennyiség megegyezik-e a rakománysor létrehozott munkamennyiségével.
1. Ismételje meg ezt az eljárást minden rakománysorral annak érdekében, hogy minden feltétel teljesüljön.

### <a name="cancel-the-work-ids-that-have-been-created-with-the-packing-location-as-the-final-shipping-location-reconfigure-the-location-directive-and-rerelease-the-load"></a>Érvénytelenítse azt a munkaazonosítót, amelynél a csomagolási hely a végső szállítási hely, konfigurálja újra a helyutasítást, és adja ki újra a rakományt

A következő módon érvénytelenítse az automatizált tárolóra bontással azt a munkaazonosítót, amelynél a csomagolási hely a végső szállítási hely.

1. Menjen a **Raktárkezelés \> Időszakos feladatok \> Tisztítás \> Munka megszakítása** menühöz.
1. Megjelenik a **Munka érvénytelenítése** párbeszédpanel. A **Munkaazonosító** mezőben adja meg a megszakítani kívánt munka azonosítóját. A kijelölt munkaazonosító esetében a **Munka állapota** beállításnál a *Nyitott*, a *Folyamatban*, az *Érvénytelenítve*, a *Kombinálva* vagy a *Lezárva* értéknek kell szerepelnie.
1. Válassza ki az **OK** lehetőséget.
1. Válassza az **Igen** lehetőséget a munka megszakításához.
1. Ha szükséges, ismételje meg ezt az eljárást a többi munkaazonosítónál.

További információ: [A kivétel kezelésére vonatkozó raktári munka visszavonása](../../warehousing/cancel-warehouse-work.md).

Az alábbi módon konfigurálja újra úgy a helyutasítást, hogy ne a csomagolási hely legyen a végleges kiszállítási hely, amikor a hullámsablonhoz be van állítva az automatikus tárolóra bontás.

1. Ugrás a **Raktárkezelés \> Beállítás \> Helyutasítások** elemre.
1. A **Munkarendelés típusa** mezőben válassza ki az *Értékesítési rendelések* elemet.
1. Válassza ki az automatikus tárolóra bontáshoz használt helyutasítást.
1. A **Helyutasítási műveletek** gyorslap eszköztárán válassza a **Lekérdezés szerkesztése** lehetőséget.
1. A Lekérdezésszerkesztő párbeszédpanel **Tartomány** lapján keresse meg azt a sort, ahol a **Mező** értéke *Helyprofil*, és ellenőrizze, hogy a sornál a **Feltételek** mező értéke ne olyan helyprofil legyen, amelynél a **Hely típusa** *Csomagolás*. A **Feltételek** mezőben javítsa ki a végső szállítási helyet.

Az alábbi módon adja ki újra a rakományt, és hozza létre a munkaazonosítókat a végső szállítási hellyel.

1. Ugorjon a **Raktárkezelés \> Rakományok \> Rakománytervező munkaterület** elemre.
1. A **Rakományok** szakaszban keresse meg a kiadandó rakományt.
1. A **Rakományok** szakasz eszköztárán a **Kiadás \> Kiadás raktárba** beállítással adja ki a kiválasztott rakoményt a raktárba.
1. Ha szükséges, ismételje meg ezt az eljárást a többi rakománynál.
