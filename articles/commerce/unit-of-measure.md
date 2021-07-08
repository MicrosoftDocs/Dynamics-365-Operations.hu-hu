---
title: Mértékegység-beállítások alkalmazása
description: Ez a témakör a mértékegységek beállításaival foglalkozik, és leírja, hogy hogyan kell alkalmazni azokat a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 7d338ba207c9a101f5e224ca66555b16a457bcbc
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271401"
---
# <a name="apply-unit-of-measure-settings"></a>Mértékegység-beállítások alkalmazása

[!include [banner](includes/banner.md)]

Ez a témakör a mértékegységek beállításaival foglalkozik, és leírja, hogy hogyan kell alkalmazni azokat a Microsoft Dynamics 365 Commerce alkalmazásban.

A termék különböző egységekben értékesíthető, például "darab", "pár" és "tucat". A Commerce központban meg lehet adni egy termékhez az értékesítési egységét, és meg lehet jeleníteni egy e-kereskedelmi webhelyen. Ha például egy kiskereskedő külön-külön és tucatonként is értékesít egy terméket, a rendelkezésre álló mértékegységek más termékinformációkkal együtt megjeleníthetők.

A következő példában a Commerce központban egy termékhez be van állítva egy **db** (darab) értékesítési egység.

![Példa olyan termékre, amely a Commerce központban mértékegységgel van konfigurálva](./media/Productunit-headquarters.PNG)

> [!NOTE]
> A mértékegység alkalmazásának és megjelenítésének támogatása a Commerce rendszer 10.0.19-es verziójának kiadásától áll rendelkezésre.

## <a name="unit-of-measure-settings"></a>Mértékegység-beállítások

A mértékegység-megjelenítési beállításokat a Commerce webhelyszerkesztőben, a **Webhelybeállítások \> Kiterjesztések \> Mértékegység-megjelenítés termékekhez** helyen lehet meghatározni. Három támogatott beállítás van:

- **Ne jelenítse meg** – Ha ez a beállítás ki van választva, akkor az e-commerce webhely nem mutatja meg a termék mértékegységét. Ez a viselkedés az alapértelmezett viselkedés.
- **Megjelenítés a termék vásárlási élményben** – Ha ez a beállítás be van jelölve, akkor a mértékegység megjelenik a termék részletei, a kosár, a pénztár, a rendelési előzmények és a rendelés részleteit tartalmazó lapokon.
- **Megjelenítés a termék böngészési és a vásárlási élményben** – Ha ez a beállítás van kiválasztva a mértékegység megjelenik a termékvásárlási élmény lapjain és a termékböngészési élményben is. A viselkedés részeként a mértékegységek megjelennek a keresési eredményekben és a termékgyűjtemény modulokban is.

> [!IMPORTANT]
> A mértékegység-megjelenítési beállítások a Commerce rendszer 10.0.19-es verziójú kiadásában érhetők el. Ha a Commerce egy korábbi verziójáról frissít, akkor manuálisan kell frissítenie az appsettings.json fájlt. Az utasításokat lásd itt: [SDK- és modultár-frissítések](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="modules-that-use-unit-of-measure-settings"></a>A mértékegység-beállításokat használó modulok

A mértékegység-beállításokat használó modulok közé tartozik a vásárlásmező, a kívánságlista, a kosár, a kosár ikon, a keresési eredmények tárolója, a termékgyűjtemény, a pénztár és a rendelés részletei modul.

A következő példában a termék részletező lapja (PDP) megjeleníti a termékhez tartozó mértékegységet (**db**).

![Példa a mértékegységet megjelenítő PDP-re](./media/Productunit-PDP.png)

A következő példában a termékgyűjtemény modul megjeleníti a termékhez tartozó mértékegységet (**db**).

![Példa a mértékegységet megjelenítő gyűjteménymodulra](./media/Productunit-productcollection.png)

## <a name="additional-resources"></a>További erőforrások

[Modultár áttekintése](starter-kit-overview.md)

[Kosármodul](add-cart-module.md)

[Vásárlásmező-modul](add-buy-box.md)

[Számlakezelési oldalak és modulok](account-management.md)

[SDK- és modultár-frissítések](e-commerce-extensibility/sdk-updates.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
