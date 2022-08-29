---
title: Szállítási cím modul
description: Ez a témakör leírja a szállítási cím modult, és bemutatja, hogyan kell konfigurálni a modulban Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 02/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.13
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 48e6909b4dac9722830a83ec3a63a58876768d7e
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275005"
---
# <a name="shipping-address-module"></a>Szállítási cím modul

[!include [banner](includes/banner.md)]

Ez a témakör leírja a szállítási cím modult, és bemutatja, hogyan kell konfigurálni a modulban Microsoft Dynamics 365 Commerce.

A szállítási cím modul segítségével a vásárlók hozzáadhatnak vagy kiválaszthatnak egy szállítási címet egy rendeléshez a fizetési folyamat során. Ha egy vásárló be van jelentkezve, minden addig mentett cím megjelenítésre kerül a vásárlónak, és a vásárló akár közülük is választhat. A vevő új címet is hozzáadhat. A szállítási cím modul minden cikkre használható, amely szállítást igényel.

A szállítási cím formátumok megadhatók a Commerce headquartersben minden országra vagy régióra, és a szállítási cím modul ezután ország/régió specifikus szabályokat érvényesít.

Amikor egy vevő megad egy szállítási címet a fizetési folyamatban, lehetőségük van elmenteni a címet elsődleges címként. Ez a lehetőség csak a bejelentkezett vevők számára jelenik meg.

Bár a szállítási cím modul nem biztosít címellenőrzést, ez a funkció implementálható a modul testreszabása által.

A következő illusztráció egy példát ábrázol egy új szállítási cím modulra egy fizetési oldalon.

![Példa egy szállítási cím modulra egy fizetési oldalon.](./media/ecommerce-shippingaddress.PNG)

## <a name="module-properties"></a>Modul tulajdonságai

| Tulajdonság neve | Értékek | Leírás |
|---------------|--------|-------------|
| Fejléc | A fejléc szövege és a fejléc címkéje (**H1**, **H2**, **H3**, **H4**, **H5** vagy **H6**) | A szállítási cím modul választható címsora. |
| Címtípus megjelenítése | **Igaz** vagy **Hamis** | Ha ez a választható tulajdonság **Igaz** értékre van állítva, akkor egy címtípus vetődik fel, mint például az **Otthon** vagy az **Üzleti** lehetőség. Ha nincs megadva címtípus, a cím automatikusan mentésre kerül **Típus**=**Egyéb** címkével. |
| Automatikus javaslatok engedélyezése| **Igaz** vagy **Hamis** | Ha ez az opcionális tulajdonság **Igaz**, a rendszer automatikus címjavaslatokat ad. Ezeket a javaslatokat a Bing Térképek biztosítja. A webhely Bing Térképek-integrációjának beállítására vonatkozó tudnivalókat lásd: [Üzletválasztó modul](store-selector.md). Ez a funkció már elérhető a Commerce alkalmazás 10.0.15-ös kiadásában.|
|Automatikus javaslat beállításai| Egy szám| Ha engedélyezve vannak az automatikus címjavaslatok, megadhatja a további beállításokat is, például a nyújtható javaslatok maximális számát.|

## <a name="add-a-shipping-address-module-to-a-checkout-page-and-set-the-required-properties"></a>Adjon hozzá egy szállítási cím modult a fizetési oldalhoz és állítsa be a kötelező tulajdonságokat

A szállítási cím modul csak a pénztár modulhoz adható hozzá. A szállítási cím konfigurálásával és fizetési oldalhoz való hozzáadásával kapcsolatos bővebb információkért lásd: [Fizetési modul](add-checkout-module.md).

## <a name="additional-resources"></a>További erőforrások

[Kosármodul](add-cart-module.md)

[Kosárikon modul](cart-icon-module.md)

[Pénztármodul](add-checkout-module.md)

[Fizetési modul](payment-module.md)

[Szállítási lehetőségek modul](delivery-options-module.md)

[Átvételi információ modul](pickup-info-module.md)

[Rendelési részletek modul](order-confirmation-module.md)

[Ajándékutalvány modul](add-giftcard.md)

[Üzletválasztó modul](store-selector.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
