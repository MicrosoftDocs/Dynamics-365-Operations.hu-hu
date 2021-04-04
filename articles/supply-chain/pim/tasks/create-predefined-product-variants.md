---
title: Az előre meghatározott termékváltozatok létrehozása
description: Ez az eljárás bemutatja az alaptermék termékváltozatainak a termékdimenziók kombinációjának használatával történő létrehozását.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductMasterDimension, EcoResProductVariants, EcoResProductVariantSuggestions, EcoResProductVariantsPendingReleaseFormPart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c33bbc7fa0ef7c3ce9768dd3688f9d1d575a513e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5259866"
---
# <a name="create-predefined-product-variants"></a>Az előre meghatározott termékváltozatok létrehozása

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja az alaptermék termékváltozatainak a termékdimenziók kombinációjának használatával történő létrehozását. Ez az eljárás az USMF bemutatócéget használja.


## <a name="create-a-product-master"></a>Alaptermék létrehozása
1. Ugorjon a Termékinformációk kezelése > Termékek > Alaptermékek lehetőségre.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Termékszám mezőbe.
    * A termékszám manuálisan történő megadása csak akkor kötelező, ha nincs beállítva számsorozat a termék száma mezőre vonatkozóan. Másképpen fogalmazva, hagyja ki a lépést, ha a számsorozatot létrehozta a rendszer a mezőre vonatkozóan.  
4. Írjon be egy értéket a Terméknév mezőbe.
5. A Termékdimenzió csoport mezőben adjon meg, vagy válasszon ki egy értéket.
    * Válassza ki a SizeCol termékdimenzió-csoportot (Méret és Szín).  
6. Kattintson az OK gombra.

## <a name="add-product-dimensions"></a>Termékdimenziók hozzáadása
1. Kattintson a Termékdimenziók lehetőségre.
    * Ez a példa bemutatja, hogy hogyan lehet manuálisan megadni a termékdimenziókat. Arra is lehetősége van, hogy kiválassza a méretet, a színt és a stíluscsoportot, amely a használni kívánt termékdimenzió értékeket tartalmazza.  
2. Kattintson az Új lehetőségre.
3. A listában jelölje meg a kiválasztott sort.
4. A Méret mezőben adjon meg vagy válasszon ki egy értéket.
5. Írjon be egy értéket a Név mezőbe.
6. Kattintson az Új elemre.
7. A listában jelölje meg a kiválasztott sort.
8. A Méret mezőben adjon meg vagy válasszon ki egy értéket.
9. Írjon be egy értéket a Név mezőbe.
10. Kattintson a Színek fülre.
11. Kattintson az Új lehetőségre.
12. A listában jelölje meg a kiválasztott sort.
13. A Szín mezőben adjon meg vagy válasszon ki egy értéket.
14. Írjon be egy értéket a Név mezőbe.
15. Kattintson az Új elemre.
16. A listában jelölje meg a kiválasztott sort.
17. A Szín mezőben adjon meg vagy válasszon ki egy értéket.
18. Írjon be egy értéket a Név mezőbe.
19. Kattintson a Mentés gombra.
20. Zárja be a lapot.

## <a name="generate-product-variants"></a>Termékváltozatok létrehozása
1. Kattintson a Termékváltozatok lehetőségre.
2. Kattintson a Változatjavaslatok lehetőségre.
3. Kattintson a Minden kijelölése elemre.
    * Az alábbi példában az összes lehetséges változat ki van választva. Ha csak a lehetséges termék cikkdimenzió-kombinációk egy részét használja fel a rendszer a változatok létrehozásához, kiválaszthatja az egyes bejegyzéseket.  
4. Kattintson a Létrehozás lehetőségre.
    * A termékdimenzió-értékek kombinációin alapuló összes változatra vonatkozóan létrehozhat leírásokat. A Leírások nem kötelező jellegűek.  
5. Kattintson a Mentés gombra.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]