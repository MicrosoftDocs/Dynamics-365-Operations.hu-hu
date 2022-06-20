---
title: Termékszám elnevezési rendszerének létrehozása előre definiált termékváltozatokhoz
description: Ez a cikk bemutatja az előre definiált termékváltozatok termékszám-névnómenklajának beállítását, valamint azt, hogy hogyan rendelhető hozzá a megfelelő termékdimenzió-csoporthoz.
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
ms.openlocfilehash: e77c8eabe1657f7fbfef71747627207dccff3b60
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8887312"
---
# <a name="create-a-product-number-nomenclature-for-predefined-product-variants"></a>Termékszám elnevezési rendszerének létrehozása előre definiált termékváltozatokhoz

[!include [banner](../../includes/banner.md)]

Ez a cikk bemutatja az előre definiált termékváltozatok termékszám-névnómenklajának beállítását, valamint azt, hogy hogyan rendelhető hozzá a megfelelő termékdimenzió-csoporthoz. Ez az eljárás az USMF bemutatócéget használja. Az új termékszámozási rendszer a szín és méret termékdimenzió-csoporthoz van rendelve. Ezt a feladatot általában egy terméktervező végzi.


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