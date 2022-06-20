---
title: A Cikk felvétele beállítás nem jelenik meg a bevásárlókocsi vagy a termékadatok oldalakon
description: Ez a cikk olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt abban az esetben, ha az üzleten való felvétel lehetősége nem jelenik meg a bevásárlókocsi vagy a termék részletező lapjain.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 88367e13b4d079edb0816e301901828b65c437ae
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8900308"
---
# <a name="pick-this-up-option-doesnt-appear-on-cart-or-product-details-pages"></a>A Cikk felvétele beállítás nem jelenik meg a bevásárlókocsi vagy a termékadatok oldalakon

[!include [banner](../../includes/banner.md)]

Ez a cikk olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt abban az esetben, ha az üzleten való felvétel lehetősége nem jelenik meg a bevásárlókocsi vagy a termék részletező lapjain.

## <a name="description"></a>Leírás

A **Cikk felvétele** gomb nem jelenik meg a bevásárlókocsi vagy a termékadatok oldalakon.

A következő ábra egy olyan oldal példáját mutatja be, amely tartalmazza a **Cikk felvétele** gombot.

![Cikk felvétele gomb.](media/pickup-button-missing.jpg)

## <a name="resolution"></a>Megoldás

### <a name="enable-the-bopis-extension-in-commerce-site-builder"></a>A BOPIS-bővítmény engedélyezése a Commerce webhelyszerkesztőben

Az „online vásárlás, átvétel az áruházban” (BOPIS) bővítmény Commerce webhelyszerkesztőben történő engedélyezéséhez kövesse az alábbi lépéseket.

1. Válassza ki a webhelyét.
1. Válassza a **Webhelybeállítások** lehetőséget, majd válassza ki a **Bővítmények** pontot.
1. Győződjön meg arról, hogy a **BOPIS letiltása** lehetőség ne legyen bejelölve.

### <a name="configure-modes-of-delivery-in-commerce-headquarters"></a>Szállítási módok konfigurálása a Commerce központi felületén

A szállítási módok Commerce központi felületén történő konfigurálásához kövesse az alábbi lépéseket.

1. Ugrás ide: **Beszerzés és forrás \> Beállítás \> Szállítási módok**.
1. Győződjön meg arról, hogy létrejött egy **Vevői átvétel** mód, és termékek és címek vannak hozzárendelve.
1. Lépjen a **Retail és Commerce \> Központ beállítása \> Paraméterek** menüpontra.
1. A bal oldali navigációs ablakban válassza ki a **Vevői rendelések** lehetőséget.
1. Győződjön meg arról, hogy az **Átvételi szállítási mód** helyesen legyen konfigurálva.

### <a name="configure-customer-orders-payments"></a>Vevői rendelések kifizetésének konfigurálása

A vevői rendelések kifizetésének Commerce központi felületén történő konfigurálásához kövesse az alábbi lépéseket.

1. Lépjen a **Retail és Commerce \> Központ beállítása \> Paraméterek** menüpontra.
1. A bal oldali navigációs ablakban válassza ki a **Vevői rendelések** lehetőséget.
1. A **Kifizetések** gyorslapon ellenőrizze, hogy helyesen vannak-e beállítva a **Fizetési feltételek** és a **Fizetési mód** mezők.

## <a name="additional-resources"></a>További erőforrások

[BOPIS konfigurálása](../cpe-bopis.md)

[Több felvételi szállítási mód engedélyezése a vevői rendelésekhez](../multiple-pickup-modes.md)

[Omni-channel Commerce rendelési kifizetések](../dev-itpro/commerce-payments.md)

[Üzletválasztó modul](../store-selector.md)
