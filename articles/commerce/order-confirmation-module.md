---
title: Rendelésmegerősítési modul
description: Ez a témakör a rendelésmegerősítési modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar
manager: annbe
ms.date: 10/31/2019
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
ms.openlocfilehash: e339ce02bb646d0d9a68c22b24fde9b72071de6f
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698326"
---
# <a name="order-confirmation-module"></a>Rendelésmegerősítési modul

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Ez a témakör a rendelésmegerősítési modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A rendelésmegerősítési modul egy rendelés megerősítő lapján megjelenő visszaigazoló üzenet megjelenítésére szolgál. A rendelésmegerősítési modul megjeleníti a rendelés visszaigazolási számát és a pénztárnál megadott vevői e-mail címet jeleníti meg.

Amikor egy rendelést leadják a pénztárnál, a rendelés visszaigazolásának számát és a vevő e-mail címét a program a lap URL-címében egy lekérdezési karakterláncként adja át a rendelés visszaigazolási lapjának. A rendelés megerősítési modulja megkapja ezeket az adatokat, és a rendelés visszaigazolási oldalán megjeleníti a rendelés állapotát. A rendelésmegerősítési modulnak szükséges ez az oldalkörnyezet rendelés állapotának megjelenítéséhez.

## <a name="order-confirmation-module-properties"></a>A Rendelés-megerősítési modul tulajdonságai

| Tulajdonság neve | Értékek | Leírás |
|---------------|--------|-------------|
| Címsor       | Fejléc szövege és fejléc címkéje (**H1**, **H2**, **H3**, **H4**, **H5** vagy **H6**) | A rendelés-megerősítési modulnak lehet fejléce. Alapértelmezés szerint a program a címsorhoz a **H2** fejléccímkét használja. A címke azonban módosítható az akadálymentességi követelmények teljesítése érdekében. |

## <a name="modules-that-can-be-used-in-an-order-confirmation-page-module"></a>A rendelés-visszaigazolási lapmodulban használható modulok 

- **Javaslatok** – A javaslatok modul elhelyezhető a rendelés megerősítő lapjára, hogy a vevőnek más termékeket ajánlhat fel.
- **Marketing** – a marketing modul marketing tartalmat adhat a rendelés megerősítésének lapjához.

## <a name="create-an-order-confirmation-page-module"></a>Rendelés-visszaigazolási oldal létrehozása

1. Hozzon létre egy **rendelés megerősítési sablon** nevű oldalsablont.
1. Az alapértelmezett lap **Fő** helyén adjon hozzá egy rendelés megerősítése modult.
1. A rendelés megerősítése modulban vegyen fel egy ajánlási modult.
1. Mentse a sablont, és tekintse meg az előnézetét. A rendelés-visszaigazolási modult nem szabad megjeleníteni, mert szükséges hozzá a rendelés megerősítési számának a környezete.
1. Adja be a sablont és tegye közzé.
1. A most létrehozott rendelés megerősítése sablon használatával hozzon létre egy **rendelés megerősítése** nevű lapot.
1. Adja hozzá az alapértelmezett lapot a lap struktúrájához.
1. Adja meg a fejléc-töredéket a **Fejléc** bővítőhelyén.
1. Adja meg a lábléc-töredéket a **Lábléc** bővítőhelyén.
1. A **Fő** bővítőhelyen adjon hozzá egy rendelés megerősítése modult.
1. A rendelés-visszaigazolási modul tulajdonságlapjához adja hozzá a **Rendelés megerősítése** fejlécet.
1. A rendelés-visszaigazolási modul alatt vegyen fel egy ajánlási modult, és konfigurálja úgy, hogy az **Új** és **Legkelendőbb** beállításokat használja.
1. Mentse az oldalt és tekintse meg előnézetét, adja be és tegye közzé.

## <a name="additional-resources"></a>További erőforrások

[Kezdő csomag áttekintése](starter-kit-overview.md)

[Tárolómodul](add-container-module.md)

[Vásárlásmező-modul](add-buy-box.md)

[Kosármodul](add-cart-module.md)

[Fizetésmodul](add-checkout-module.md)

[Fejlécmodul](author-header-module.md)

[Láblécmodul](author-footer-module.md)
