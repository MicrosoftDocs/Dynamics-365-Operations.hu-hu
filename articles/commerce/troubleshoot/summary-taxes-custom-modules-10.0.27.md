---
title: A rendelésösszesítés részösszege nem tartalmazza a díjak adóját testreszabott rendelésösszesítő modulok használata esetén.
description: Ez a cikk olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt az egyedi rendelésösszegző modulok használata esetén, és a rendelés összegző részösszege nem tartalmazza a költségekre kivetett adókat az "ár tartalmazza az áfát" helyzetben.
author: gvrmohanreddy
ms.date: 05/17/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-04-22
ms.openlocfilehash: 260dcb6bc1585615195e32adfcd1da6bfbca294e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8848837"
---
# <a name="order-summary-subtotal-doesnt-include-taxes-on-charges-when-using-customized-order-summary-modules"></a>A rendelésösszesítés részösszege nem tartalmazza a díjak adóját testreszabott rendelésösszesítő modulok használata esetén.

Ez a cikk olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt az egyedi rendelésösszegző modulok használata esetén, és a rendelés összegző részösszege nem tartalmazza a költségekre kivetett adókat az "ár tartalmazza az áfát" helyzetben.

## <a name="description"></a>Leírás

Microsoft Dynamics 365 Commerce A 10.0.27-es verzióban az "ár tartalmazza az áfaösszegzést" változatban a következő módosítások segítségével egységes tapasztalatokat lehet adni az e-commerce webhely lapjainak rendelés-összefoglaló moduljaiban.

- Két új mező lett hozzáadva: **TaxOnShippingCharge** és **TaxOnNonShippingCharges**.
- A **GetSalesOrderBySalesId** **és a GetSalesOrderByTransactionId** alkalmazásprogramozási felületek (API-k) pontos értékkel rendelkezik az "Ár tartalmazza az forgalmi adót" eset következő mezőiben:

    - RészösszegSalesAmount
    - RészösszegAmountWithoutTax
    - Részösszegösszeg
    - ShippingChargeAmount
    - EgyébchargeAmount

Ha azonban testreszabott rendelésösszegző modulokat használ, ezek a változtatások hatással lehetnek a rendelés összegző részösszegzési értékeire, mivel a költségek adóját nem tartalmazzák.

## <a name="resolution"></a>Megoldás

Ha testreszabott rendelésösszegző modulokat használ, és nem szeretné örökölni a Commerce rendszer 10.0.27-es és újabb verziójú "Ár tartalmazza az áfaösszegzést" helyzeten végrehajtott módosításokat, kövesse az ebben a szakaszban található utasításokat.

A salesTransaction.SubtotalAmount és salesTransaction.SubtotalAmount.SubtotalAmountWithoutTax mezőkben visszaállítja a teljes költség adóösszegének (TaxOnShippingCharge **és** TaxOnNonShippingCharges **)** alkalmazását a részösszegekbe (**SubtotalAmount** **·** **és SubtotalAmountWithoutTax**). 10.0.27 **·**

A következő lépésekkel lehet visszaállni az előző rendelési összefoglaló viselkedésre.

1. A Commerce Headquartersben nyissa meg a Commerce paraméterek lapot (**Retail and Commerce \> Headquarters telepítő \> Commerce-paraméterek \>**).
1. A bal oldali navigációs ablakban válassza ki a Konfiguráció **paramétereit**.
1. Adja hozzá a következő konfigurációs paramétereket, és állítsa igaz értékre az értékek **értékét**:

    - IsLegacyTaxOnChargeInSubtotalAmountMaszkludedInTaxIncusiveEnabled
    - IsLegacyOrderSummary Egyenabled

> [!NOTE]
> Ha korábban már **használta az IsUpdatedPriceIncludesTaxSubtotalCalculationEnabled** **konfigurációs paramétert, és szeretné megtartani ugyanazt a viselkedést a rendelésben. A NetAmountWithoutTax tulajdonságot szintén** hozzá kell adni az IsLegacyPriceIncludesTaxNetAmountWithoutTaxCalculationEnabled **konfigurációs** paraméterhez, és az értékét true értékre kell állítani **.**

## <a name="additional-resources"></a>További erőforrások

[Adózásrészletezési információk elrejtése a rendelésösszesítésekben](../hide-taxes-breakup.md)
