---
title: Rendelési részletek modul
description: Ez a témakör a rendelési részletek modulokkal foglalkozik, és bemutatja, hogy hogyan használhatók a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar
manager: annbe
ms.date: 01/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar-ms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: cb09a0b6ce1e48707f96021e9fad0006d9c1c55c
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/05/2020
ms.locfileid: "3026017"
---
# <a name="order-details-module"></a>Rendelési részletek modul


[!include [banner](includes/banner.md)]

Ez a témakör a rendelési részletek modulokkal foglalkozik, és bemutatja, hogy hogyan használhatók a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A rendelési részletek modul a rendelés visszaigazolási részleteinek megjelenítésére szolgál a rendelés leadását követően. Megjeleníti a rendelés visszaigazolási azonosítóját, a rendelés kapcsolattartási adatait, valamint az egyéb rendelésre vonatkozó adatokat, például a beszerzett cikkeket, a fizetési adatokat és a szállítási módot.

## <a name="order-confirmation-module-properties"></a>A Rendelés-megerősítési modul tulajdonságai

| Tulajdonság neve  | Értékek | Leírás |
|----------------|--------|-------------|
| Címsor        | Fejléc szövege és fejléc címkéje (**H1**, **H2**, **H3**, **H4**, **H5** vagy **H6**) | A rendelés-megerősítési modulnak lehet fejléce. Alapértelmezés szerint a program a címsorhoz a **H2** fejléccímkét használja. A címke azonban módosítható az akadálymentességi követelmények teljesítése érdekében. |
| Kapcsolattartási telefonszám | Text | A rendeléssel kapcsolatos kérdésekhez kapcsolattartói szám adható meg. |

## <a name="modules-that-can-be-used-on-an-order-details-page"></a>A rendelési részletek oldalon használható modulok

A rendelési részletek oldal létrehozásakor a rendelési részletek modul mellett további releváns modulok is hozzáadhatók. Íme néhány példa:

- **Javaslatok modul** – A javaslatok modul hozzáadható a rendelési részletek oldalhoz, hogy a vevőnek más termékeket ajánljon fel.
- **Marketingmodulok** – Bármely marketingmodul hozzáadható a rendelési részletek oldalhoz, hogy marketingtartalmakat jelenítsen meg.

## <a name="create-an-order-details-page-module"></a>Rendelési részletek oldalmodul létrehozása

1. Hozzon létre egy **Rendelési részletek sablon** nevű oldalsablont.
1. Az alapértelmezett lap **Fő** helyén adjon hozzá egy rendelési részletek modult.
1. A rendelési részletek modulban vegyen fel egy ajánlási modult.
1. Mentse a sablont, és tekintse meg az előnézetét. A rendelési részletek modul nem kerül megjelenítésre, mert szükséges hozzá a rendelés megerősítési számának a környezete.
1. Fejezze be a sablon szerkesztését, és tegye közzé.
1. A most létrehozott rendelési részletek sablon használatával hozzon létre egy **rendelési részletek oldal** nevű oldalt.
1. Adja hozzá az alapértelmezett lapot a lap struktúrájához.
1. Adja meg a fejléc-töredéket a **Fejléc** bővítőhelyén.
1. Adja meg a lábléc-töredéket a **Lábléc** bővítőhelyén.
1. A **Fő** bővítőhelyen adjon hozzá egy rendelési rézletek modult.
1. A rendelési részletek modul tulajdonságlapjához adja hozzá a **Rendelési részletek** fejlécet.
1. A rendelési részletek modul alatt vegyen fel egy ajánlási modult, és konfigurálja úgy, hogy az **Új** és **Legkelendőbb** beállításokat használja.
1. Mentse a lapot, és tekintse meg az előnézetét.
1. Fejezze be a lap szerkesztését, és tegye közzé.

## <a name="additional-resources"></a>További erőforrások

[Kezdő csomag áttekintése](starter-kit-overview.md)

[Tárolómodul](add-container-module.md)

[Vásárlásmező-modul](add-buy-box.md)

[Kosármodul](add-cart-module.md)

[Fizetésmodul](add-checkout-module.md)

[Fejlécmodul](author-header-module.md)

[Láblécmodul](author-footer-module.md)
