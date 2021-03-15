---
title: Rendelésmegerősítési modul
description: Ez a témakör a rendelésmegerősítési modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket használni a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 11/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 9d916d2687777403f2b0df7c35171948ad2fb7db
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4972743"
---
# <a name="order-confirmation-module"></a>Rendelésmegerősítési modul

[!include [banner](includes/banner.md)]

Ez a témakör a rendelésmegerősítési modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket használni a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A rendelési visszaigazolás modul a rendelés visszaigazolási részleteinek megjelenítésére szolgál a rendelés leadását követően. Megjeleníti a rendelés visszaigazolási azonosítóját, a rendelés kapcsolattartási adatait, valamint az egyéb rendelésre vonatkozó adatokat, például a beszerzett cikkeket, a fizetési adatokat, az átvételi beállításokat és a szállítási módot.

## <a name="order-confirmation-module-properties"></a>A Rendelés-megerősítési modul tulajdonságai

| Tulajdonság neve  | Értékek | Leírás |
|----------------|--------|-------------|
| Címsor        | Fejléc szövege és fejléc címkéje (**H1**, **H2**, **H3**, **H4**, **H5** vagy **H6**) | A rendelés-megerősítési modulnak lehet fejléce. Alapértelmezés szerint a program a címsorhoz a **H2** fejléccímkét használja. A címke azonban módosítható az akadálymentességi követelmények teljesítése érdekében. |
| Kapcsolattartási telefonszám | Text | A rendeléssel kapcsolatos kérdésekhez kapcsolattartói szám adható meg. |
| Felvételi időköz adatainak megjelenítése | Igaz vagy hamis | A tulajdonság a Dynamics 365 Commerce 10.0.15-ös vagy újabb verziókban áll rendelkezésre. Ha ez igaz, akkor megjeleníti a felvételi időközzel kapcsolatos információkat, ha egy felvételi cikkhez van megadva|

## <a name="modules-that-can-be-used-on-an-order-confirmation-page"></a>A rendelési visszaigazolás oldalon használható modulok

A rendelési visszaigazolás oldal létrehozásakor a rendelési visszaigazolás modul mellett további releváns modulok is hozzáadhatók. Íme néhány példa:

- **Javaslatok modul** – A javaslatok modul hozzáadható a rendelési visszaigazolás oldalhoz, hogy a vevőnek más termékeket ajánljon fel.
- **Marketingmodulok** – Bármely marketingmodul hozzáadható a rendelési visszaigazolás oldalhoz, hogy marketingtartalmakat jelenítsen meg.

## <a name="add-an-order-confirmation-module-to-a-page"></a>Rendelés visszaigazolás modul felvétele egy oldalra

A rendelés visszaigazolás modul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.

1. Lépjen a **Sablonok** pontra, majd új sablon készítéséhez válassza az **Új** elemet.
1. Az **Új sablon** párbeszédablakban a **Sablon neve** alatt adja meg a **Rendelés visszaigazolási sablon** nevet, majd válassza az **OK** gombot.
1. A **Törzs** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki az **Alapértelmezett oldal** modult, majd kattintson az **OK** gombra.
1. Az **Alapértelmezett lap** modul **Fő** helyén válassza ki a három pont (**…**) gombot, majd válassza a **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki a **Rendelés visszaigazolás** modult, majd kattintson az **OK** gombra.
1. Válassza a **Mentés** lehetőséget, majd a sablon előnézetének megtekintéséhez az **Előnézet** elemet. A rendelés-visszaigazolási modult nem szabad megjeleníteni, mert szükséges hozzá a rendelés megerősítési számának a környezete.
1. Válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.
1. Lépjen az **Oldalak** pontra, majd válassza az **Új** lehetőséget új oldal létrehozásához.
1. A **Sablon kiválasztása** párbeszédpanelen válassza ki a **Rendelési visszaigazolási sablont**. Az **Oldal neve** alatta adja meg a **Rendelés visszaigazolás oldalt**, majd kattintson az **OK** gombra.
1. Az **Alapértelmezett lap** modul **Fő** helyén válassza ki a három pont (**…**) gombot, majd válassza a **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki a **Rendelés visszaigazolás** modult, majd kattintson az **OK** gombra.
1. A rendelés visszaigazolása modul tulajdonságlapján válassza a ceruza szimbólum melletti **Címsor** elemet.
1. A **Címsor** párbeszédpanel **Címsor szövege** mezőjébe írja be a **Rendelés visszaigazolása** címsorszöveget, majd válassza az **OK** gombot.
1. Válassza a **Mentés** lehetőséget, majd az oldal előnézetének megtekintéséhez az **Előnézet** elemet.
1. Válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

## <a name="additional-resources"></a>További erőforrások

[Kosármodul](add-cart-module.md)

[Kosárikon modul](cart-icon-module.md)

[Fizetésmodul](add-checkout-module.md)

[Fizetési modul](payment-module.md)

[Szállítási cím modul](ship-address-module.md)

[Szállítási lehetőségek modul](delivery-options-module.md)

[Átvételi információ modul](pickup-info-module.md)

[Ajándékutalvány modul](add-giftcard.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]