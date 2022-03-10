---
title: Termékszám elnevezési rendszerének létrehozása előre definiált termékváltozatokhoz
description: Ez a témakör bemutatja, hogyan állítható be termékszámozási rendszer előre definiált termékváltozatok számára, és hogyan rendelhető hozzá a megfelelő termékdimenzió-csoporthoz.
author: t-benebo
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductDimensionGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5179dd54f22de11dc4c0f54113376f13b2f59c48
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7569577"
---
# <a name="create-a-product-number-nomenclature-for-predefined-product-variants"></a>Termékszám elnevezési rendszerének létrehozása előre definiált termékváltozatokhoz

[!include [banner](../../includes/banner.md)]

Ez a témakör bemutatja, hogyan állítható be termékszámozási rendszer előre definiált termékváltozatok számára, és hogyan rendelhető hozzá a megfelelő termékdimenzió-csoporthoz. Ez az eljárás az USMF bemutatócéget használja. Az új termékszámozási rendszer a szín és méret termékdimenzió-csoporthoz van rendelve. Ezt a feladatot általában egy terméktervező végzi.


## <a name="create-a-product-number-nomenclature"></a>Termékszámozási rendszer létrehozása

1. Ugorjon a **Termékinformációk kezelése \> Beállítás \> Termék elnevezési rendszere** lehetőségre.
1. Válassza az **Új** lehetőséget.
1. A **Név** mezőben adja meg az elnevezési rendszer nevét, amely segít azonosítani a cél termékdimenzió-csoportot, például `ColorSize`.
1. Írjon egy értéket a **Leírás** mezőbe.
1. Válassza a **Hozzáadás** lehetőséget.
1. Válassza az **Alaptermék** számát.
1. Válassza a **Hozzáadás** lehetőséget.
1. Válassza a **Szöveges állandó** elemet.
1. Írjon be egy értéket a **Szöveg** mezőbe.
1. Válassza a **Hozzáadás** lehetőséget.
1. Válassza ki a **Szín** elemet.
1. Válassza a **Hozzáadás** lehetőséget.
1. Válassza a **Szöveges állandó** elemet.
1. Írjon be egy értéket a **Szöveg** mezőbe.
1. Válassza a **Hozzáadás** lehetőséget.
1. Válassza a **Méret** elemet.
1. Zárja be a lapot.

## <a name="assign-the-nomenclature-to-a-product-master"></a>Rendelje hozzá az elnevezési rendszert az alaptermékhez

1. Válassza ki a **Termékdimenzió-csoportok** elemet.
2. Válassza ki a **SizeCol termékdimenzió-csoport** elemet.
3. Válassza ki a **Szerkesztés** opciót.
4. Válassza az **Igen** lehetőséget az **Elnevezési rendszer használata** mezőben.
5. A **Termékváltozat-számozási rendszer** mezőben adjon meg, vagy válasszon ki egy értéket.
6. Zárja be a lapot.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]