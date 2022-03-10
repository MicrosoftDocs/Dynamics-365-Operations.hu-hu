---
title: Változatcsoport létrehozása
description: Ez a témakör azt mutatja be, hogyan hozhat létre szín-, stílus- vagy színváltozat csoportot egy termékhez a Microsoft Dynamics 365 Commerce alkalmazásban.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailSizeGroupTable, ConfigGroupIdLookup, RetailStyleGroupTable
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 49e6860fa22bbfba8b86a8243fa29b831e22b489d967a45310648e5debd7512b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6749931"
---
# <a name="create-a-variant-group"></a>Variánscsoport létrehozása


[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan hozhat létre szín-, stílus- vagy színváltozat csoportot egy termékhez a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A Dynamics 365 Commerce támogatja a termékek több változatát. Ideális megoldás változatcsoportok beállítása a különböző termékkategóriákhoz. Például méretcsoport hozható létre a az extrakicsi, kicsi, közepes, nagy, extranagy méretű pólókhoz, illetve színcsoportot is létre lehet hozni, amely tartalmazza a termék összes rendelkezésre álló színét. A termékek felvétele előtt kell hozzáadni a változatcsoportokat.

Ebben a témakörben egy méretcsoportot hozunk létre és konfigurálunk. Hasonló eljárások használhatók a stílus- és színcsoportok hozzáadására és beállítására is.

## <a name="create-a-size-group"></a>Méretcsoport létrehozása

Méretcsoport létrehozásához tegye a következőket:
 
1. A navigációs ablaktáblán lépjen ide: **Modulok \> Kiskereskedelmi és kereskedelem \> Termékek és kategóriák \> Változatcsoportok \> Méretcsoportok**.
1. A műveleti ablaktáblán kattintson az **Új** elemre.
1. A **Méretcsoport** mezőbe írjon be egy nevet a méretcsoportnak.
1. Ha szükséges, akkor adjon meg egy leírást a **Leírás** mezőben.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

## <a name="add-attributes-to-the-size-group"></a>Attribútumok hozzáadása a méretcsoporthoz

Attribútum hozzáadásához egy méretcsoporthoz kövesse az alábbi lépéseket.

1. A navigációs ablaktáblán lépjen ide: **Modulok \> Kiskereskedelmi és kereskedelem \> Termékek és kategóriák \> Változatcsoportok \> Méretcsoportok**
1. A navigációs ablaktáblán válasszon egy kategóriát.
1. A **Méret csoport sorai** területen válassza a **Hozzáadás** elemet.
1. A **Méret** mezőbe írjon be egy karakterláncot a mérethez (például „XL”).
1. A **Méret neve** mezőbe írja be a méret nevét (például „Extranagy”).
1. A **Feltöltési súly** mezőbe írjon be egy számot, amely a feltöltési súlyt jelenti.
1. A **Vonalkódban lévő szám** mezőbe írjon be egy számot a vonalkódnak megfelelően.
1. A **Megjelenítési sorrend** mezőbe a megjelenítési sorrendet jelölő számot.
1. Ha befejezte a méretek hozzáadását, válassza a művelet ablaktábla **Mentés** elemét .

A következő kép egy példát mutat be az „utcai pólóméretek” méretcsoportjára.

![Méretcsoport létrehozása.](media/create-variant-group.png)

## <a name="additional-resources"></a>További erőforrások

[Termékadatok áttekintése](../supply-chain/pim/product-information.md?toc=/dynamics365/commerce/toc.json)

[Retail termékek beállítása](set-up-retail-products.md)

[Termékdimenziók](../supply-chain/pim/product-dimensions.md?toc=/dynamics365/commerce/toc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]