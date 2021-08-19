---
title: A rakománysor nem frissíthető, mert a kiadott mennyiség negatív lenne
description: Ez a probléma akkor fordul elő, ha a rakománysor frissítése vagy törlése negatív kiadott mennyiséget okozna.
author: GalynaFedorova
ms.date: 6/30/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadPlanningListPage_WHSLoadLineUnShipQty,WHSLoadTable_WHSLoadLineUnShipQty,WHSLoadPlanningWorkbench_WHSLoadLineUnShipQty,WHSShipmentDetails_WHSLoadLineUnShipQty,WHSLoadPlanningListPage_DeleteButtonLoadLine,WHSLoadTable_DeleteButtonLoadLine,WHSLoadPlanningWorkbench_DeleteButtonLoadLine,WHSShipmentDetails_DeleteButtonShipment
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-06-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: a6325a632e1f68a0a3a9cb6b6091c48da014a405e8ce9ad69ea841f5cceb216f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6728459"
---
# <a name="cant-update-a-load-line-because-the-released-quantity-would-be-negative"></a>A rakománysor nem frissíthető, mert a kiadott mennyiség negatív lenne

Hibakód: @WAX:ReleasedQtyCannotBeNegative

## <a name="symptoms"></a>Tünetek

Ez a probléma akkor fordul elő, ha a rakománysor frissítése vagy törlése negatív kiadott mennyiséget okozna. Ebben az esetben a rakománysor frissítésének vagy törlésének megkísérlése esetén a rendszer a következő hibaüzenetet jeleníti meg:

> A kiadott mennyiség nem lehet negatív a(z) %1 cikk, %2 tétel esetében.

Ebből következően nem frissítheti vagy nem törölheti a rakománysort.

## <a name="cause"></a>Ok

A rakománysor frissítése vagy törlése után a rendszer frissíti a kapcsolódó értékesítési sor kiadott mennyiségét (*whsSalesLine.ReleaseQty*). A rendszer kiértékeli a kiadott mennyiséget, és ha azt észleli, hogy a sor kiadott mennyisége a frissítés után negatív lenne, akkor nem fogja lehetővé a sor frissítését vagy törlését. Erre az ellenőrzésre minden alkalommal kerül sor, amikor különböző műveletekkel próbálja meg frissíteni a rakománysor mennyiségét vagy a mértékegységet, például töröl egy rakománysort, töröl egy szállítmányt, módosítja a rakománysor mennyiségét, csökkenti a kitárolási mennyiséget és rövid kitárolást végez.

A probléma leggyakoribb kiváltó oka a nyitott rakománysorok mértékegységátváltásának módosítása. Például az értékesítési rendelés felszabadításakor az egység átváltása *50Eea = 1 PL* volt. A kapcsolódó rakományszállítmány véglegesítése előtt azonban az egység átváltása *100 Ea = 1 PL* lett.

## <a name="resolution"></a>Megoldás

A megoldás az mértékegység-átváltási módosítások visszaállítás,a a rakománysor frissítése vagy törlése, majd az átváltás ismételt alkalmazása. A probléma megoldásáig meg kell akadályozni az olyan egyéb rakományok feldolgozását, amelyek a problémát okozó cikket tartalmazzák. Ellenkező esetben az új átváltás esetleg más, már nyitott rakományok esetén is alkalmazva lesz.

A probléma javításához végezze el a következő feladatok egyikét:

1. A rakománysorhoz használt mértékegység-átváltás áttekintése.
2. A cikk aktuális mértékegység-átváltásának áttekintése, és a rakománysor frissítését vagy törléset engedélyező módosítások végrehajtása.
3. A rakománysor frissítése vagy törlése, valamint a mértékegység-átváltási módosítások visszaállítása.

### <a name="review-the-unit-conversion-that-was-used-for-the-load-line"></a>A rakománysorhoz használt mértékegység-átváltás áttekintése

A következő eljárás szerint tekintse át a rakománysorokat, és jegyezze fel a rakománysorhoz használt mértékegység-átváltást.

1. Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.
1. A nem törölhető vagy nem frissíthető rakománysort tartalmazó rakományt válassza ki.
1. A Művelet ablaktábla **Betöltések** lapjának **Kapcsolódó információk** csoportjában válassza a **Munka** elemet.
1. A felső rácson válassza ki a kívánt munkaazonosítót.
1. A lap alján található **Általános** lapon számítsa ki a **Készlet munkamennyisége** érték és a **Munka mennyiége** érték közötti átváltási arányt. Jegyezze fel az arányt.
1. Ismételje meg ezt az eljárást az összes kapcsolódó munkaazonosítóhoz, hogy meggyőződjön arról, hogy ugyanazt az átváltást használta-e.

### <a name="review-the-current-unit-conversion-for-the-item-and-make-adjustments"></a>A cikk aktuális mértékegység-átváltásának áttekintése és helyesbítések végrehajtása

Az alábbi módon tekintse át a termékei mértékegység-átváltását, és hajtsa végre a szükséges módosításokat, hogy a mértékegység-átváltás igazodjon a rakománysorhoz.

1. Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.
1. Nyissa meg a kapcsolódó terméket, hogy a **Kiadott termék részletei** oldalra jusson.
1. A Művelet panel **Termék** lapján, a **Beállítás** csoportban válassza a **Mértékegység-átváltások** lehetőséget.
1. Válassza ki a mértékegységek közötti átváltást, és a módosításokat hajtsa végre az előző szakaszban található átváltás segítségével.

### <a name="update-or-delete-the-load-line-and-revert-the-unit-conversion-adjustments"></a>A rakománysor frissítése vagy törlése, valamint a mértékegység-átváltási módosítások visszaállítása

A következő eljárás szerint feldolgozhatja a rakománysort a szükségesként, és visszaállítja a mértékegység-átváltásokat.

1. Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.
1. A nem törölhető vagy nem frissíthető rakománysort tartalmazó rakományt nyissa meg.
1. A **Rakománysorok** gyorslapon válassza ki a sor betöltése lehetőséget.
1. Igény szerint folytassa a szükséges műveletekkel. (Például a rakománysor törlése vagy a mennyiség módosítása.)
1. Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.
1. Nyissa meg a kapcsolódó terméket, hogy a **Kiadott termék részletei** oldalra jusson.
1. A Művelet panel **Termék** lapján, a **Beállítás** csoportban válassza a **Mértékegység-átváltások** lehetőséget.
1. Válassza ki a mértékegységek közötti átváltást, és állítsa vissza az előző szakaszban végzett módisításokat.
