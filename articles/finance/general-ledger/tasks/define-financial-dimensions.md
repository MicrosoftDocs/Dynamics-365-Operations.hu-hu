---
title: Pénzügyi dimenziók meghatározása
description: Ez a feladat-útmutató bemutatja az entitás által támogatott pénzügyi dimenzió és egyéni pénzügyi dimenzió hozzáadását.
author: aprilolson
manager: AnnBe
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionDetails,  DimensionAttributeTableExtensionActivate, DimensionValueDetails
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fb2dc5df96198f3c9f68fcac70b2e5dcbe8c8832
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2175459"
---
# <a name="define-financial-dimensions"></a>Pénzügyi dimenziók meghatározása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez a feladat-útmutató bemutatja az entitás által támogatott pénzügyi dimenzió és egyéni pénzügyi dimenzió hozzáadását.  Az útmutató az USMF bemutatócéget használja.


## <a name="create-an-entity-backed-financial-dimension"></a>Entitás által biztosított pénzügyi dimenzió létrehozása
1. Menjen a **Navigációs panelen Modulok > Főkönyv> Számlatükör > Dimenziók > Pénzügyi dimenziók** lehetőséget.
2. Kattintson az **Új** elemre.
3. A pénzügyi dimenzió alapjául a **Felhasználói értékek** űrlapja mezőben jelöljön ki egy rendszer által definiált entitást. 
4. A **Dimenzió neve** mezőbe írjon be egy értéket a pénzügyi dimenzió leírásához. A név eltérhet a rendszer által meghatározott entitástól, de nem tartalmazhat szóközt vagy különleges karaktert.
5. Kattintson az **Aktiválás** gombra. A pénzügyi dimenzió aktiválásával frissítheti a pénzügyi dimenzió nevét tartalmazó táblázatot, és eltávolíthatja a törölt dimenziókat. A pénzügyi dimenziók aktiválása előtt megadhat dimenzióértékeket, de a pénzügyi dimenzió nem használható, amíg nincs aktiválva.  
6. Kattintson a **Bezárás** gombra az aktiváló üzeneten.
7. Kattintson az **Aktiválás** gombra. Megadhatja, hogy a dimenzió aktiválását egy adott napon és időpontban szeretné futtatni, kötegelt módon.  
8. A **Művelet panelen** kattintson a **Dimenzióértékek** elemre. Néhány dimenzióérték vállalatspecifikus érték. Ellenőrizheti, hogy vállalatspecifikusak-e, ha a vállalat neve megjelenik a dimenzióértékek listájában.  

## <a name="create-a-custom-financial-dimension"></a>Egyéni pénzügyi dimenzió létrehozása
1. Zárja be a lapot.
2. Kattintson az **Új** elemre.
3. A **Használandó értékek forrása** mezőben válassza az **Egyéni dimenziók** értéket
4. A **Dimenzió neve** mezőbe írjon be egy értéket a pénzügyi dimenzió leírásához.
    - A név nem tartalmazhat szóközt vagy különleges karaktert.  
    - A formátummaszk megadásával továbbá korlátozhatja a dimenzióértékekhez megadható adatok mennyiségét és típusát.   
    - Megadhat olyan karaktereket, például betűket vagy kötőjelet, amelyek minden egyes dimenzióértéknél változatlanok maradnak. Emellett megadhat kettős kereszt (#) vagy és-jel (&) karaktereket számok és betűk helyőrzőjeként, amelyek változni fognak a dimenzióértékek minden létrehozásakor. A kettős kereszt (#) a számok, míg az és-jel (&) a betűk helyőrzője.  Példa: Ha például a dimenzióértéket két C betűre és három számra szeretné korlátozni, formátummaszkként a CC-### értéket adja meg.  
5. Kattintson az **Aktiválás** gombra. A pénzügyi dimenzió aktiválásával frissítheti a pénzügyi dimenzió nevét tartalmazó táblázatot, és eltávolíthatja a törölt dimenziókat. A pénzügyi dimenziók aktiválása előtt megadhat dimenzióértékeket, de a pénzügyi dimenzió nem használható, amíg nincs aktiválva.     
6. Kattintson az **Aktiválás** gombra. Megadhatja, hogy a dimenzió aktiválását egy adott napon és időpontban szeretné futtatni, kötegelt módon.      
7. A **Művelet panelen** kattintson a **Dimenzióértékek** elemre.
8. Kattintson az **Új** elemre.
9. A **Dimenzió értéke** mezőbe írjon be egy nevet a pénzügyi dimenzióérték leírásához.
10. A **Leírás** mezőben írja be egy leírást, amely leírja a pénzügyi dimenzió értékét.

