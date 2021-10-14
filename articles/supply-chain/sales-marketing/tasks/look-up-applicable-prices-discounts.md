---
title: Alkalmazandó árak és engedmények keresése
description: Ez az eljárás bemutatja, hogyan lehet árat és/vagy az engedményt találni egy termékhez, amely jelenleg érvényes egy meghatározott vevőre, értékesítési rendelés létrehozása nélkül.
author: Henrikan
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c80ae00e1bcbc4498ec4705195c3208170cee1b1
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7578920"
---
# <a name="look-up-applicable-prices-and-discounts"></a>Alkalmazandó árak és engedmények keresése

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja, hogyan lehet árat és/vagy az engedményt találni egy termékhez, amely jelenleg érvényes egy meghatározott vevőre, értékesítési rendelés létrehozása nélkül. Az eljárás végigvezet egy adott példán, és a szükséges értékek kiválasztásához követnie kell a példában az USMF bemutatóvállalat használatát.


## <a name="find-the-applicable-price"></a>A vonatkozó ár keresése
1. Ugorjon az Értékesítés és marketing > Árak és engedmények > Árak keresése elemre.
2. A Vevői számla mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
3. Az US-001 vevő megkeresése és kijelölése a listán
4. A listában kattintson a kijelölt sorban lévő hivatkozásra.
5. A Cikkszám mezőbe írja be az „T0004” értéket.
    * Alapértelmezés szerint a Mennyiség mező értéke 1. Azonban ha ismeri a rendelés méretét, amelyet a vevő a szóban forgó termékre le kíván adni, akkor inkább adja meg ezt az értéket. Ez az információ akkor releváns, ha a vevővel való kereskedelmi megállapodások mennyiség szüneteket tartalmaznak, ha például a termék ára függ a minimális beszerzett mennyiségtől.  
6. A Dátum mezőben adjon meg egy dátumot, amikor a vevő várhatóan rendelést ad le. 
    * A dátum lehet az adott nap, vagy bármilyen jövőbeni dátum.  
    * A rendszer most visszaadja az árat, amely a kiválasztott termékre érvényes, ha a megadott mennyiséggel vásárolja meg a kiválasztott vevő a kiválasztott dátumon. Ebben a példában ha az US-001 vevő vásárol egy egységnyi T0004 terméket a mai napon, az egységenként 350 CAD-ba kerül. Ez az ár a vevővel között meglévő és aktív kereskedelmi megállapodásból származik.      Az oldalon az egyéb mezők további részleteket tartalmaznak a termék árakra és költségekre vonatkozóan (ha az alapterméknél van megadva), és a számított nyereségességet.  
    * Ha a Kapcsolódó termékváltozatok megjelenítése beállítás be van jelölve, az azt jelenti, hogy további kereskedelmi megállapodások léteznek a termékváltozatokra.  
7. Jelölje be a Kapcsolódó termékváltozatok megjelenítése jelölőnégyzetet.
    * Megjelenik a termékváltozatok listája, a dimenziókkal kapcsolatos információkkal együtt.  
8. A listában jelölje be a Fehér színt képviselő sort.
    * Ne feledje, hogy a termék ára most eltér a korábban megjelenítettől, amikor nem dimenzió szerint volt megadva.  
9. Kattintson az Eladási árak megtekintése gombra.
    * Az Ár (eladási) oldal megjeleníti a termékre vonatkozó kereskedelmi megállapodásokat, a változatokkal együtt.  
10. Zárja be a lapot.

## <a name="find-the-applicable-discount"></a>A vonatkozó engedmény keresése
Ellenőrizze, hogy a Vevői számla mező az US-001 vevőszámot tartalmazza-e.   
1. A Cikkszám mezőbe írja be az „T0012” értéket.
    * Győződjön meg arról, hogy a Mennyiség mező értéke 1.  
    * A T0012 termékre vonatkozó következő árképzési adatok egy vagy több kereskedelmi megállapodásból származnak: az egységár 1000 CAD, és a sorengedmény százalékos értéke 5.  
2. Állítsa a mennyiséget 20 értékre.
    * A nagyobb rendelési mennyiség hatására a sorengedmény, amelyet a rendszer a vevőnek ajánl, 5-ről 7 százalékra változik.  
    * A Nettó összeget az egységár, az engedmény és a teljes mennyiség alapján számítja ki.  
3. Kattintson a Sorengedmény megtekintése gombra.
    * A T0012 termékhez két sorkedvezmény-megállapodás tartozik, 5 százalék engedményt adva egy rendelési sor mennyiséghez 1-től 10-re, illetve 10 felett rendelési mennyiségre vonatkozóan 7 százalékos engedményt. Vegye figyelembe, hogy az engedmények egy termékcsoportra vonatkoznak, ebben a példában a 01 csoportkódra, amelynek a T0012 termék tagja.  
4. Zárja be a lapot.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]