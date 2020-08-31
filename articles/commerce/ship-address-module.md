---
title: Szállítási cím modul
description: Ez a témakör ismerteti szállítási cím modult, és bemutatja, hogyan konfigurálhatjuk a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 08/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 380d268ec0ba64367f090c31408eac1c54d0ff17
ms.sourcegitcommit: ae0843763a8b6b232bb71db326fab28605ac6c53
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2020
ms.locfileid: "3661441"
---
# <a name="shipping-address-module"></a>Szállítási cím modul

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Ez a témakor ismerteti a szállítási cím modult, és bemutatja, hogyan kell konfigurálni azt a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A szállítási cím modul segítségével a vásárlók hozzáadhatnak vagy kiválaszthatnak egy szállítási címet egy rendeléshez a fizetési folyamat során. Ha egy vásárló be van jelentkezve, minden addig mentett cím megjelenítésre kerül a vásárlónak, és a vásárló akár közülük is választhat. A vevő új címet is hozzáadhat. A szállítási cím modul minden cikkre használható, amely szállítást igényel.

A szállítási cím formátumok megadhatók a Commerce headquartersben minden országra vagy régióra, és a szállítási cím modul ezután ország/régió specifikus szabályokat érvényesít.

Amikor egy vevő megad egy szállítási címet a fizetési folyamatban, lehetőségük van elmenteni a címet elsődleges címként. Ez a lehetőség csak a bejelentkezett vevők számára jelenik meg.

Bár a szállítási cím modul nem biztosít címellenőrzést, ez a funkció implementálható a modul testreszabása által.

A következő illusztráció egy példát ábrázol egy új szállítási cím modulra egy fizetési oldalon.

![Példa egy szállítási cím modulra egy fizetési oldalon](./media/ecommerce-shippingaddress.PNG)

## <a name="module-properties"></a>Modul tulajdonságai

| Tulajdonság neve | Értékek | Leírás |
|---------------|--------|-------------|
| Fejléc | A fejléc szövege és a fejléc címkéje (**H1**, **H2**, **H3**, **H4**, **H5** vagy **H6**) | A szállítási cím modul választható címsora. |
| Címtípus megjelenítése | **Igaz** vagy **Hamis** | Ha ez a választható tulajdonság **Igaz** értékre van állítva, akkor egy címtípus vetődik fel, mint például az **Otthon** vagy az **Üzleti** lehetőség. Ha nincs megadva címtípus, a cím automatikusan mentésre kerül **Típus**=**Egyéb** címkével. |

## <a name="add-a-shipping-address-module-to-a-checkout-page-and-set-the-required-properties"></a>Adjon hozzá egy szállítási cím modult a fizetési oldalhoz és állítsa be a kötelező tulajdonságokat

A szállítási cím modul csak a pénztár modulhoz adható hozzá. A szállítási cím konfigurálásával és fizetési oldalhoz való hozzáadásával kapcsolatos bővebb információkért lásd: [Fizetési modul](add-checkout-module.md).

## <a name="additional-resources"></a>További erőforrások

[Kosármodul](add-cart-module.md)

[Kosárikon modul](cart-icon-module.md)

[Fizetésmodul](add-checkout-module.md)

[Fizetési modul](payment-module.md)

[Szállítási lehetőségek modul](delivery-options-module.md)

[Rendelési részletek modul](order-confirmation-module.md)

[Ajándékutalvány modul](add-giftcard.md)