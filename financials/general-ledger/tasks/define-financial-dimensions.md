--- 
title: "Pénzügyi dimenziók meghatározása"
description: "Ez a feladat-útmutató bemutatja az entitás által támogatott pénzügyi dimenzió és egyéni pénzügyi dimenzió hozzáadását."
author: aprilolson
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 7cc83b24503fa383d0e2d2acd70173edcb2dcb03
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# <a name="define-financial-dimensions"></a>Pénzügyi dimenziók meghatározása

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ez a feladat-útmutató bemutatja az entitás által támogatott pénzügyi dimenzió és egyéni pénzügyi dimenzió hozzáadását.  Az útmutató az USMF bemutatócéget használja.


## <a name="create-an-entity-backed-financial-dimension"></a>Entitás által biztosított pénzügyi dimenzió létrehozása
1. Ugrás a következő útvonalra: Főkönyv > Számlatükör > Dimenziók > Pénzügyi dimenziók.
2. Kattintson az Új lehetőségre.
3. A pénzügyi dimenzió alapjául a Felhasználói értékek forrása mezőben jelöljön ki egy rendszer által definiált entitást. 
4. A Dimenzió neve mezőbe írjon be egy értéket a pénzügyi dimenzió leírásához.
    * A név eltérhet a rendszer által meghatározott entitástól, de nem tartalmazhat szóközt vagy különleges karaktert.  
5. Kattintson az Aktiválás gombra.
    * A pénzügyi dimenzió aktiválásával frissítheti a pénzügyi dimenzió nevét tartalmazó táblázatot, és eltávolíthatja a törölt dimenziókat. A pénzügyi dimenziók aktiválása előtt megadhat dimenzióértékeket, de a pénzügyi dimenzió nem használható, amíg nincs aktiválva.  
6. Kattintson a Bezárás gombra az aktiváló üzeneten.
7. Kattintson az Aktiválás gombra.
    * Megadhatja, hogy a dimenzió aktiválását egy adott napon és időpontban szeretné futtatni, kötegelt módon.  
8. Kattintson a Dimenzióértékek elemre.
    * Néhány dimenzióérték vállalatspecifikus érték. Ellenőrizheti, hogy vállalatspecifikusak-e, ha a vállalat neve megjelenik a dimenzióértékek listájában.  

## <a name="create-a-custom-financial-dimension"></a>Egyéni pénzügyi dimenzió létrehozása
1. Zárja be a lapot.
2. Kattintson az Új lehetőségre.
3. Az Értékek forrása mezőben válassza a(z) <Custom dimension> lehetőséget.
4. A Dimenzió neve mezőbe írjon be egy értéket a pénzügyi dimenzió leírásához.
    * A név nem tartalmazhat szóközt vagy különleges karaktert.  
    * A formátummaszk megadásával továbbá korlátozhatja a dimenzióértékekhez megadható adatok mennyiségét és típusát.   
    * Megadhat olyan karaktereket, például betűket vagy kötőjelet, amelyek minden egyes dimenzióértéknél változatlanok maradnak. Emellett megadhat kettős kereszt (#) vagy és-jel (&) karaktereket számok és betűk helyőrzőjeként, amelyek változni fognak a dimenzióértékek minden létrehozásakor. A kettős kereszt (#) a számok, míg az és-jel (&) a betűk helyőrzője.  Példa: Ha például a dimenzióértéket két C betűre és három számra szeretné korlátozni, formátummaszkként a CC-### értéket adja meg.  
5. Kattintson az Aktiválás gombra.
    * A pénzügyi dimenzió aktiválásával frissítheti a pénzügyi dimenzió nevét tartalmazó táblázatot, és eltávolíthatja a törölt dimenziókat. A pénzügyi dimenziók aktiválása előtt megadhat dimenzióértékeket, de a pénzügyi dimenzió nem használható, amíg nincs aktiválva.  
6. Kattintson az Aktiválás gombra.
    * Megadhatja, hogy a dimenzió aktiválását egy adott napon és időpontban szeretné futtatni, kötegelt módon.  
7. Kattintson a Dimenzióértékek elemre.
8. Kattintson az Új lehetőségre.
9. A Dimenzió értéke mezőbe írjon be egy nevet a pénzügyi dimenzióérték leírásához.
10. A Leírás mezőben írja be egy leírást, amely leírja a pénzügyi dimenzió értékét.


