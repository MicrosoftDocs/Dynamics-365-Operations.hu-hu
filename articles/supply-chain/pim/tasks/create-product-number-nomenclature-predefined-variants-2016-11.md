---
title: Termékszám elnevezési rendszerének létrehozása előre definiált termékváltozatokhoz
description: Ez a témakör bemutatja, hogyan állítható be termékszámozási rendszer előre definiált termékváltozatok számára, és hogyan rendelhető hozzá a megfelelő termékdimenzió-csoporthoz.
author: ShylaThompson
manager: tfehr
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductDimensionGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3a15d1f4ecbf85e22bfadc1dd680d24bc56d807f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5007541"
---
# <a name="create-a-product-number-nomenclature-for-predefined-product-variants"></a>Termékszám elnevezési rendszerének létrehozása előre definiált termékváltozatokhoz

[!include [banner](../../includes/banner.md)]

Ez a témakör bemutatja, hogyan állítható be termékszámozási rendszer előre definiált termékváltozatok számára, és hogyan rendelhető hozzá a megfelelő termékdimenzió-csoporthoz. Ez az eljárás az USMF bemutatócéget használja. Az új termékszámozási rendszer a szín és méret termékdimenzió-csoporthoz van rendelve. Ezt a feladatot általában egy terméktervező végzi.


## <a name="create-a-product-number-nomenclature"></a>Termékszámozási rendszer létrehozása
1. Válassza a **Termékváltozat modelldefiníciója** elemet.
2. Válassza a **Termék elnevezési rendszere** elemet.
3. Válassza az **Új** lehetőséget.
4. A **Név** mezőben adja meg az elnevezési rendszer nevét, amely segít azonosítani a cél termékdimenzió-csoportot, például `ColorSize`.
5. Írjon egy értéket a **Leírás** mezőbe.
6. Válassza a **Hozzáadás** lehetőséget.
7. Válassza az **Alaptermék** számát.
8. Válassza a **Hozzáadás** lehetőséget.
9. Válassza a **Szöveges állandó** elemet.
10. Írjon be egy értéket a **Szöveg** mezőbe.
11. Válassza a **Hozzáadás** lehetőséget.
12. Válassza ki a **Szín** elemet.
13. Válassza a **Hozzáadás** lehetőséget.
14. Válassza a **Szöveges állandó** elemet.
15. Írjon be egy értéket a **Szöveg** mezőbe.
16. Válassza a **Hozzáadás** lehetőséget.
17. Válassza a **Méret** elemet.
18. Zárja be a lapot.

## <a name="assign-the-nomenclature-to-a-product-master"></a>Rendelje hozzá az elnevezési rendszert az alaptermékhez
1. Válassza ki a **Termékdimenzió-csoportok** elemet.
2. Válassza ki a **SizeCol termékdimenzió-csoport** elemet.
3. Válassza ki a **Szerkesztés** opciót.
4. Válassza az **Igen** lehetőséget az **Elnevezési rendszer használata** mezőben.
5. A **Termékváltozat-számozási rendszer** mezőben adjon meg, vagy válasszon ki egy értéket.
6. Zárja be a lapot.

