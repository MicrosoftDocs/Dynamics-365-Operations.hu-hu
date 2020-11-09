---
title: Rendelési részletek modul
description: Ez a témakör a rendelési részletek modulokkal foglalkozik, és bemutatja, hogy hogyan használhatók a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar
manager: annbe
ms.date: 06/18/2020
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
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6610d2abe0a1b03ddd763f9a65fc1dab42f1da1b
ms.sourcegitcommit: 49f3011b8a6d8cdd038e153d8cb3cf773be25ae4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/16/2020
ms.locfileid: "4015180"
---
# <a name="order-details-module"></a>Rendelési részletek modul

[!include [banner](includes/banner.md)]

Ez a témakör a rendelési részletek modulokkal foglalkozik, és bemutatja, hogy hogyan használhatók a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A rendelési részletek modul a rendelés visszaigazolási részleteinek megjelenítésére szolgál a rendelés leadását követően. Megjeleníti a rendelés visszaigazolási azonosítóját, a rendelés kapcsolattartási adatait, valamint az egyéb rendelésre vonatkozó adatokat, például a beszerzett cikkeket, a fizetési adatokat és a szállítási módot.

## <a name="order-details-module-properties"></a>A Rendelés részletei modul tulajdonságai

| Tulajdonság neve  | Értékek | Leírás |
|----------------|--------|-------------|
| Címsor        | Fejléc szövege és fejléc címkéje ( **H1** , **H2** , **H3** , **H4** , **H5** vagy **H6** ) | A rendelés részletei modulnak lehet fejléce. Alapértelmezés szerint a program a címsorhoz a **H2** fejléccímkét használja. A címke azonban módosítható az akadálymentességi követelmények teljesítése érdekében. |
| Kapcsolattartási telefonszám | Text | A rendeléssel kapcsolatos kérdésekhez kapcsolattartói szám adható meg. |

## <a name="modules-that-can-be-used-on-an-order-details-page"></a>A rendelési részletek oldalon használható modulok

A rendelési részletek oldal létrehozásakor a rendelési részletek modul mellett további releváns modulok is hozzáadhatók. Íme néhány példa:

- **Javaslatok modul** – A javaslatok modul hozzáadható a rendelési részletek oldalhoz, hogy a vevőnek más termékeket ajánljon fel.
- **Marketingmodulok** – Bármely marketingmodul hozzáadható a rendelési részletek oldalhoz, hogy marketingtartalmakat jelenítsen meg.

## <a name="add-an-order-details-module-to-a-page"></a>Rendelés részletei modul felvétele egy oldalra

A rendelés részletei modul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.

1. Lépjen a **Sablonok** pontra, majd új sablon készítéséhez válassza az **Új** elemet.
1. Az **Új sablon** párbeszédablakban a **Sablon neve** alatt adja meg a **Rendelés részletei** nevet, majd válassza az **OK** gombot.
1. A **Törzs** helyben válassza a három pont ( **…** ) gombot, majd válassza az **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki az **Alapértelmezett oldal** modult, majd kattintson az **OK** gombra.
1. Az **Alapértelmezett lap** modul **Fő** helyén válassza ki a három pont ( **…** ) gombot, majd válassza a **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki a **Rendelés részletei** modult, majd kattintson az **OK** gombra.
1. Válassza a **Mentés** lehetőséget, majd a sablon előnézetének megtekintéséhez az **Előnézet** elemet. A rendelési részletek modul nem kerül megjelenítésre, mert szükséges hozzá a rendelés megerősítési számának a környezete.
1. Válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.
1. Lépjen az **Oldalak** pontra, majd válassza az **Új** lehetőséget új oldal létrehozásához.
1. A **Sablon kiválasztása** párbeszédpanelen válassza ki a **Rendelés részletei sablont**. Az **Oldal neve** alatta adja meg a **Rendelés részletei oldalt** , majd kattintson az **OK** gombra.
1. Az **Alapértelmezett lap** modul **Fő** helyén válassza ki a három pont ( **…** ) gombot, majd válassza a **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki a **Rendelés részletei** modult, majd kattintson az **OK** gombra.
1. A rendelés részletei modul tulajdonságlapján válassza a ceruza szimbólum melletti **Címsor** elemet.
1. A **Címsor** párbeszédpanel **Címsor szövege** mezőjébe írja be a **Rendelés részletei** címsorszöveget, majd válassza az **OK** gombot.
1. Válassza a **Mentés** lehetőséget, majd az oldal előnézetének megtekintéséhez az **Előnézet** elemet.
1. Válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

## <a name="additional-resources"></a>További erőforrások

[Kosármodul](add-cart-module.md)

[Kosárikon modul](cart-icon-module.md)

[Fizetésmodul](add-checkout-module.md)

[Fizetési modul](payment-module.md)

[Szállítási cím modul](ship-address-module.md)

[Szállítási lehetőségek modul](delivery-options-module.md)

[Ajándékutalvány modul](add-giftcard.md)
