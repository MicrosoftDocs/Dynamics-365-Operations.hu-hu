---
title: Anyagjegyzék-számítás elvégzése egyetlen szintű struktúra használatával (2016. február)
description: Ez az eljárás bemutatja, hogyan lehet kiszámítani egy késztermék költségét egyszintű alábontással, amelynek az alapja a költségszámítási táblázat.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventItemPrice, BOMCalcDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 013eddf1ba8e8cab3c87cb1f063d9bf886b0f833
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5821393"
---
# <a name="calculate-a-bom-by-using-a-single-level-structure-february-2016"></a>Anyagjegyzék-számítás elvégzése egyetlen szintű struktúra használatával (2016. február)

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja, hogyan lehet kiszámítani egy késztermék költségét egyszintű alábontással, amelynek az alapja a költségszámítási táblázat. Ez az anyagjegyzék-számítási sorozat hatodik feladata. A feladat létrehozásához az USMF bemutató vállalatot használtuk példaként.

1. Ugrás a Kiadott termékek elemre.
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Termék BOM_1 kiválasztása.  
3. A Művelet panelen kattintson a Költségkezelés elemre.
4. Kattintson a Cikk ára elemre.
5. Kattintson a Cikk-költség kiszámítása lehetőségre.
    * Előfordulhat, hogy a három pont (...) elemre kell kattintania a lehetőség megtekintéséhez a főmenüben.  
6. A Költségszámítási verzió mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
    * Ehhez a bemutatóhoz válassza ki a következőt: 10. Ez ugyanaz a költségszámítási verzió, amelyet az önköltségi ár hozzáadására használtunk az összetevőkhöz.  
7. Kattintson az OK gombra.
8. Kattintson a Számítás részleteinek megjelenítése elemre.
    * Előfordulhat, hogy a három pont (...) elemre kell kattintania a lehetőség megtekintéséhez a főmenüben.    Itt látható a költség összetétele:  *    10 az ITEM_A elemből származik, 10 az ITEM_B elemből, 10 a BOM_2 elemből. Ebben az esetben nincsenek részletek a BOM_2 esetében, mert a bevitele 10-es elszámolóárként történt, de nem a kalkuláció használatával.  *    7 forrása a beállítási idő, amely egy állandó költség, és további 7 forrása a futásidejű művelet (folyamat).  *    Vannak egyéb összegek is, amelyek megfelelnek a közvetett költségeknek.  
9. @SysTaskRecorder:_RequestClose



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]