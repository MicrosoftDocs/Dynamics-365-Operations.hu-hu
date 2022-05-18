---
title: Pénzügyi dimenziók meghatározása
description: Ez az eljárás bemutatja, hogyan adhat hozzá egy entitással támogatott pénzügyi dimenziót és egy egyéni pénzügyi dimenziót.
author: aprilolson
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DimensionDetails,  DimensionAttributeTableExtensionActivate, DimensionValueDetails
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 10a991938f68c0ade19999e48a02f032c92a6779
ms.sourcegitcommit: 1d2eeacad11c28889681504cdc509c90e3e8ea86
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/05/2022
ms.locfileid: "8716943"
---
# <a name="define-financial-dimensions"></a>Pénzügyi dimenziók meghatározása

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja, hogyan adhat hozzá egy entitással támogatott pénzügyi dimenziót és egy egyéni pénzügyi dimenziót. Az útmutató az USMF bemutatócéget használja.

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
1. Kattintson az **Új** elemre.
2. A **Használandó értékek forrása** mezőben válassza az **Egyéni dimenziók** értéket
3. A **Dimenzió neve** mezőbe írjon be egy értéket a pénzügyi dimenzió leírásához.
    - A név nem tartalmazhat szóközt vagy különleges karaktert.  
    - A formátummaszk megadásával továbbá korlátozhatja a dimenzióértékekhez megadható adatok mennyiségét és típusát.   
    - Megadhat olyan karaktereket, például betűket vagy kötőjelet, amelyek minden egyes dimenzióértéknél változatlanok maradnak. Emellett megadhat kettős kereszt (#) vagy és-jel (&) karaktereket számok és betűk helyőrzőjeként, amelyek változni fognak a dimenzióértékek minden létrehozásakor. A kettős kereszt (#) a számok, míg az és-jel (&) a betűk helyőrzője.  Példa: Ha például a dimenzióértéket két C betűre és három számra szeretné korlátozni, formátummaszkként a CC-### értéket adja meg.  
4. Kattintson az **Aktiválás** gombra. A pénzügyi dimenzió aktiválásával frissítheti a pénzügyi dimenzió nevét tartalmazó táblázatot, és eltávolíthatja a törölt dimenziókat. A pénzügyi dimenziók aktiválása előtt megadhat dimenzióértékeket, de a pénzügyi dimenzió nem használható, amíg nincs aktiválva.     
5. Kattintson az **Aktiválás** gombra. Megadhatja, hogy a dimenzió aktiválását egy adott napon és időpontban szeretné futtatni, kötegelt módon.      
6. A **Művelet panelen** kattintson a **Dimenzióértékek** elemre.
7. Kattintson az **Új** elemre.
8. A **Dimenzió értéke** mezőbe írjon be egy nevet a pénzügyi dimenzióérték leírásához.
9. A **Leírás** mezőben írja be egy leírást, amely leírja a pénzügyi dimenzió értékét.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
