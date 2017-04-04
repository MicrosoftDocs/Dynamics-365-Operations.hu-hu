---
title: "Áfa mértékét a számítás alapja és számítási módszerek alapján"
description: "A cikk leírja, hogy a Számítás alapja mezőben található értékek és a Számítási módszer értékei, hogyan határozzák meg az értékesítési és beszerzési tranzakciók adó(it)."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: TaxTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 7171
ms.assetid: 381fc309-b32a-4927-b5b8-fa1c31b0bd72
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 114dee90b0fe525f0b3efabbf651d2804a22dd7d
ms.openlocfilehash: ad731401fe553cdc50665cc87aaac64dc48813f2
ms.lasthandoff: 03/31/2017


---

# <a name="sales-tax-rates-based-on-the-marginal-base-and-calculation-methods"></a>Áfa mértékét a számítás alapja és számítási módszerek alapján

A cikk leírja, hogy a Számítás alapja mezőben található értékek és a Számítási módszer értékei, hogyan határozzák meg az értékesítési és beszerzési tranzakciók adó(it).

A számítás gyorslapon és az áfa kód lapon lévő számítás alapot az határozza meg, hogy melyik összeg használatos a megfelelő adó értékek az áfa kód értékek oldalán lévő értékekből történő kivételéhez. A számítási mód mező módszerével kombinált számítás alapja mezőben lévő a összeg típusa határozza meg, hogy hogyan találja meg a tranzakcióhoz a megfelelő adó értéket. 

A mezőértékek különféle kombinációi igen különböző áfaszámítási módokra adnak lehetőséget, ahogy az a következő példákban is látható. A példák ugyanazokat az áfaintervallum értékek használják, amelyek az áfa kód értékek oldalán állíthatók be minden áfakód esetében. A lap megnyitásához kattintson a forgalmi adó kódja &gt;értékek kódok forgalmi adó lapján.

> [!Important]                                                                                                                  
> Ha az áfakódok bármelyikének számítási alapja a sor összegétől vagy egységtől függ, akkor aszámítási módszer mezőjének értékét a sorra kell beállítani a főkönyv paramétereinek oldalán. |

## <a name="net-amount-per-line"></a>Soronkénti nettó összeg
Válassza ezt az opciót a számlasorok nettó összegén alapuló áfa értékek meghatározására, minden egyéb adó kizárásával.

### <a name="example"></a>Példa

Az áfakulcsok a következő intervallumokra vannak beállítva.

| Összegintervallum    | Adómérték |
|--------------------|----------|
| 0 - 50             | 30%      |
| 50 - 100           | 20%      |
| 100 - 0 (&gt; 100) | 10%      |

> [!NOTE]                                                                                                             
> Az utolsó intervallumban szereplő nulla (0) felső határ azt jelenti, hogy minden olyan összeg, amely meghaladja a 100-at ebbe az intervallumba esik.

Számítás alapja: **soronkénti nettó összeg** 

Számítási módszer: **intervallum** 

8 darab lámpát vásárol, amelyek egyenként 25.00 kerülnek. 

A számlasor nettó értéke 200.00. 

Az áfa számítása a következő: 

Áfa összesen = 50 x 30 % + 50 x 20 % + 100 x 10 % = 15 + 10 + 10 = 35.00 

A számla végösszege 200,00 + 35.00 = 235.00 = 

**Variation** 

Ha a számla két sor négy tételből minden sorban, minden sorban a nettó összeg 100,00 és a forgalmi adó számítása a következőképpen: 

Forgalmi adó sor 1 = 50 x 30 % + 50 x 20 % = 15 + 10 = 25,00 

Forgalmi adó sor, 2 = 50 x 30 % + 50 x 20 % = 15 + 10 = 25,00 

Áfa összesen = 25,00 + 25,00 = 50,00 

Számla teljes összege = 200,00 + 50,00 = 250.00

## <a name="net-amount-per-unit"></a> Egységenkénti nettó összeg
Válassza ezt az opciót a az egyes egységek értékein alapuló áfa értékek meghatározására, minden egyéb adó kizárásával. Ha egy számítás alapon alapuló egység van bejelölve, akkor is egy egységet kell megadni az áfakódhoz.

### <a name="example"></a>Példa

Az áfakulcsok a következő intervallumokra vannak beállítva.

| Összeg             | Adómérték |
|--------------------|----------|
| 0 - 50             | 30%      |
| 50 - 100           | 20%      |
| 100 - 0 (&gt; 100) | 10%      |

Számítás alapja: **egységenkénti nettó összeg** 

Számítási módszer: **teljes összeg** 

8 darab lámpát vásárol, amelyek egyenként 25.00 kerülnek. 

A számlasor nettó értéke 200.00. 

Az áfa számítása a következőképpen történik: Egységenkénti áfa = 25,00 x 30 % = 7.50 Összes áfa = 7,50 x 8 egység = 60.00 Teljes számlaösszeg = 200,00 + 60,00 = 260.00

## <a name="net-amount-of-invoice-balance"></a> Számlaegyenleg nettó összege

Válassza ezt az opciót a számlasorok nettó összegén alapuló áfa értékek meghatározására, minden egyéb adó kizárásával.

### <a name="example"></a>Példa

Az áfakulcsok a következő intervallumokra vannak beállítva.

| Összeg            | Adómérték |
|-------------------|----------|
| 0 - 50            | 30%      |
| 50 - 100          | 20%      |
| 100 -0 (&gt; 100) | 10%      |

Számítás alapja: **Számlaegyenleg nettó összege** 

Számítási módszer: **intervallum** egy eladási számlát 2 sor 4 lámpával van 25,00 minden egyes sorában. Számlaegyenleg nettó összege 4 x 25,00 + 4 x 25,00 = 200,00. Az áfa számítása a következőképpen történik: Összes áfa = 50 x 0,30 + 50 x 0,20 + 100 x 0,10 = 15 + 10 + 10 = 35,00 Teljes számlaösszeg = 200,00 + 35,00 = 235.00

## <a name="gross-amount-per-line"></a> Soronkénti bruttó összeg

Válassza ezt az opciót a számlasorok értékein alapuló áfa értékek meghatározására, minden erre a sorra vonatkozó egyéb adóval együtt.

> [!NOTE]
> Egy áfacsoportban csak egy áfakód lehetséges ezzel a kiválasztással a számítási alap mezőben.

### <a name="example"></a>Példa

Az áfakulcsok a következő intervallumokra vannak beállítva.

| Összeg             | Adómérték |
|--------------------|----------|
| 0 - 50             | 30%      |
| 50 - 100           | 20%      |
| 100 - 0 (&gt; 100) | 10%      |

Számítás alapja: **Soronkénti bruttó összeg** Számítási módszer: **Intervallum** Ezen kívül van egy másik áfakód minden lámpán 5,00 speciális vám kiszámításához. A vámot a nettó összeghez kell hozzáadni, még az áfa számítása előtt. 8 darab lámpát vásárol, amelyek egyenként 25.00 kerülnek. A számlasor nettó értéke 200.00. A számlasor bruttó összege 8 x 25.00 + 8 x 5,00 = 240,00. Az adó az alábbiak szerint számítandó: áfa összesen 50 x 0,30 + 50 x 0,20 + 140 x 0,10 = 15 + 20 + 14 = 39.00 = teljes vám = 5,00 x 8 = 40,00 számla teljes összege 200,00 + 39.00 + 40,00 = 279.00 =

**Variation** 

Ha a számla minden sorban 4 elem 2 számlasorok segítségével készült, a nettó összege számlasoronként 100,00. A számlasoronkénti bruttó összeg (4 x 5.00 vámmal együtt) 120.00 lenne, és az áfa létrehozása a következőképpen történik: Számla sor 1 áfája = 50 x 0,30 + 50 x 0,20 + 20 x 0,10 = 15 + 10 + 2 = 27,00 Számla sor 2 áfája = 50 x 0,30 + 50 x 0,20 + 20 x 0,10 = 15 + 10 + 2 = 27,00 Összes áfa = 27,00 + 27,00 = 54,00 Összes vám = 5,00 x 8 = 40,00 Teljes számlaösszeg = 200,00 + 54,00 + 40,00 = 294.00

## <a name="gross-amount-per-unit"></a> Egységenkénti bruttó összeg

Válassza ezt az opciót az egység értékein alapuló áfa értékek meghatározására, minden egyéb adóval együtt.

> [!NOTE]
> Egy áfacsoportban csak egy áfakód lehetséges ezzel a kiválasztással a számítási alap mezőben.

### <a name="example"></a>Példa

Az áfakulcsok a következő intervallumokra vannak beállítva.

| Összeg             | Adómérték |
|--------------------|----------|
| 0 - 50             | 30%      |
| 50 - 100           | 20%      |
| 100 - 0 (&gt; 100) | 10%      |

Számítás alapja: **Egységenkénti bruttó összeg** Minden lámpán 5,00 speciális vám van. A vámot a nettó összeghez kell hozzáadni, még az áfa számítása előtt. 8 darab lámpát vásárol, amelyek egyenként 25.00 kerülnek. Az egységenkénti bruttó érték 30,00. Az áfa számítása a következőképpen történik: Összes áfa = 30 x 30% = 9.00 Összes áfa = 9,00 x 8 = 72,00 Teljes vám= 5.00 x 8 = 40.00 Teljes számlaösszeg =200.00 + 72,00 + 40,00 = 312.00

## <a name="invoice-total-incl-other-sales-tax-amounts"></a> Egyéb áfaösszegeket tartalmazó számlaösszeg

Válassza ezt az opciót a számla összes értékén alapuló áfa értékek meghatározására, minden egyéb adóval együtt.
> [!NOTE]
> Az áfacsoportot csak akkor egy forgalmi adó kódja a kijelölt beállításokkal marginális viszonyítási mező és a

### <a name="example"></a>Példa

Az áfakulcsok a következő intervallumokra vannak beállítva.

| Összeg             | Adómérték |
|--------------------|----------|
| 0 - 50             | 30%      |
| 50 - 100           | 20%      |
| 100 - 0 (&gt; 100) | 10%      |

Számítás alapja: **számla Összesen ÁFÁ egyéb áfaösszegeket** számítási módszer: **intervallum**   
A speciális vámot minden egyes lámpa a 5.00 van. A vámot a nettó összeghez kell hozzáadni, még az áfa számítása előtt. 8 darab lámpát vásárol, amelyek egyenként 25.00 kerülnek. A számlasor nettó értéke 200.00. A számla bruttó összege 200.00 + (8 x 5,00) = 240,00. Az áfa számítása a következőképpen történik: Összes áfa = 50 x 0,30 + 50 x 0,20 + 140 x 0,10 = 15 + 10 + 14 = 39,00 Összes vám = 5,00 x 8 = 40,00 Teljes számlaösszeg = 200,00 + 39,00 + 40,00 = 279,00

További tudnivalókért lásd: [teljes összeg és a számítási beállítások időköz Áfakódok](whole-amount-interval-options-sales-tax-codes.md) és [áfa számítási módszerek az Eredet mezőben](sales-tax-calculation-methods-origin-field.md).


