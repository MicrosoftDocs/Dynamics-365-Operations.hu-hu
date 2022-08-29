---
title: Termék kosárhoz adási beállításainak alkalmazása
description: Ez a cikk tartalmazza a "Termék hozzáadása a kosárhoz" beállítást, és bemutatja, hogyan lehet azokat alkalmazni a kosárban Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 07/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 16644e6746d182cd86a40861c4e30a85a9d3d478
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277027"
---
# <a name="apply-add-product-to-cart-settings"></a>Termék kosárhoz adási beállításainak alkalmazása

[!include [banner](includes/banner.md)]

Ez a témakör a Termék **hozzáadása** a kosárhoz beállítást ismerteti, és bemutatja, hogyan lehet azokat alkalmazni a kosárban Microsoft Dynamics 365 Commerce.

Különböző munkafolyamatok támogatottak, amikor egy terméket hozzáadnak a kosárhoz a Dynamics 365 Commerce egyik e-kereskedelmi webhelyén. Előfordulhat például, hogy a webhely egyik felhasználója a bevásárlókocsihoz kerül. Azt is be lehet állítani, hogy a felhasználó az aktuális oldalon maradjon, de értesítést kapjon arról, hogy a terméket a kosárba helyezte.

A különböző munkafolyamatok támogatásához rendelkezésre áll egy **Termék hozzáadása a kosárhoz** mező a Commerce webhelykészítő **Beállítások \> Bővítmények** területén. Válassza ki az alábbi beállítások egyikét a megfelelő munkafolyamat implementálásához:

- **Navigáció a kosár oldalához** – Amikor a felhasználók hozzáadnak egy tételt a kosárhoz, a kosár oldalára kerülnek.
- **Értesítés megjelenítése** – Amikor a felhasználók tételt adnak hozzá a kosárhoz, visszaigazoló értesítést kapnak, és tovább böngészhetnek a termék részleteinek oldalán (PDP).
- **Minikosár megjelenítése** – Amikor a felhasználók hozzáadnak egy tételt a kosárhoz, megjelenik a minikosár tartalma. A felhasználók ellenőrizhetik a kosárban lévő összes elemet, és ha készen állnak, folytathatják a fizetési műveletet.
- **Értesítés megjelenítése az Értesítési modul használatával** – Amikor a felhasználók hozzáadnak egy tételt a kosárhoz, a rendszer az értesítési modulban visszaigazolási értesítést jelenít meg. Ahhoz, hogy ez a beállítás működjön, az értesítési modult hozzá kell adni az oldal fejlécéhez.
- **Ne navigáljon a kosár oldalához** – Amikor a felhasználók hozzáadnak egy tételt a kosárhoz, az aktuális oldalon maradnak.

Az alábbi ábra a **Termék hozzáadása a kosárhoz** beállításra mutat példát a webhelykészítőben.

![Példa a Termék hozzáadása a kosárhoz beállítási lehetőségekre a webhelyszerkesztőben](./media/AW_sitesettings.PNG)

> [!IMPORTANT]
> - A **Termék hozzáadása a kosárhoz** webhelybeállítások a Dynamics 365 Commerce 10.0.11-es verziójától kezdve érhetők el. Ha a Dynamics 365 Commerce egy korábbi verziójáról frissít, akkor manuálisan kell frissítenie az appsettings.json fájlt. Az appsettings.json fájlok frissítésével kapcsolatos tudnivalókért lásd az [SDK- és modultár-frissítések](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file) témakört.
> - A **Minikosár megjelenítése** beállítási lehetőség a Dynamics 365 Commerce 10.0.20-as verziójától kezdve érhető el. Ha a Dynamics 365 Commerce egy korábbi verziójáról frissít, akkor manuálisan kell frissítenie az appsettings.json fájlt. Az appsettings.json fájlok frissítésével kapcsolatos tudnivalókért lásd az [SDK- és modultár-frissítések](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file) témakört.

A következő ábra példát mutat egy „kosárhoz adva” visszaigazolási értesítésre a Fabrikam oldalon.

![Példa egy „kosárhoz adva” visszaigazolási értesítésre a Fabrikam oldalon](./media/ecommerce-addtocart-notifications.PNG)

A következő ábra példát mutat egy „kosárhoz adva” visszaigazolási értesítésre az Adventure Works oldalon.

![Példa egy „kosárhoz adva” visszaigazolási értesítésre az Adventure Works oldalon](./media/AW_minicart.PNG)

## <a name="additional-resources"></a>További erőforrások

[Modultár áttekintése](starter-kit-overview.md)

[Vásárlásmező-modul](add-buy-box.md)

[Üzletválasztó modul](store-selector.md)
