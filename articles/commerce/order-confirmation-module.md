---
title: Rendelésmegerősítési modul
description: Ez a témakör a rendelés-visszaigazolási modulokat tartalmazza, és bemutatja, hogyan használhatók a modulban Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 6011c7e4713813a02fa8f812ea8981fd6fa0253f
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269135"
---
# <a name="order-confirmation-module"></a>Rendelésmegerősítési modul

[!include [banner](includes/banner.md)]

Ez a témakör a rendelés-visszaigazolási modulokat tartalmazza, és bemutatja, hogyan használhatók a modulban Microsoft Dynamics 365 Commerce.

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
1. Adja meg **a Rendelés megerősítése** sablon nevét az Új **sablon párbeszédpanel Sablon neve párbeszédpanelen** **·**, **majd válassza az OK gombra való lehetőséget**.
1. Válassza ki a **három** pontból (**...**), **majd válassza a Modul hozzáadása lehetőséget** a Törzsnél.
1. A Modulok kiválasztása párbeszédpanelen **válassza ki az Alapértelmezett** **lap modult, majd kattintson az** OK gombra **.**
1. Az Alapértelmezett **lap** modul főbejáratában **válassza** ki a három pontból (**...**), **majd válassza a Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **a** Rendelés megerősítése modult, majd válassza az **OK gombra.**
1. Válassza a **Mentés** lehetőséget, majd a sablon előnézetének megtekintéséhez az **Előnézet** elemet. A rendelés-visszaigazolási modult nem szabad megjeleníteni, mert szükséges hozzá a rendelés megerősítési számának a környezete.
1. Válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.
1. Lépjen az **Oldalak** pontra, majd válassza az **Új** lehetőséget új oldal létrehozásához.
1. Adja meg **a Rendelés megerősítése lapot az Új** oldal létrehozása párbeszédpanel Oldal neve **csoportban,** **majd válassza a** Tovább **lehetőséget**.
1. A Sablon **kiválasztása mezőben válassza** ki a Rendelés **visszaigazolása** sablont, majd válassza a Tovább **lehetőséget**.
1. Az **Elrendezés kiválasztása oldalon válasszon** egy lapelrendezést (például **rugalmas** elrendezés), majd válassza **a Tovább lehetőséget**.
1. Az Ellenőrzés **és befejezés lapon** ellenőrizze a lap konfigurációját. Ha szerkesztenie kell a lap adatait, válassza a Vissza **lehetőséget**. Ha a lap adatai helyesek, válassza a Létrehozás **lapot**. 
1. Az Alapértelmezett **lap** modul főbejáratában **válassza** ki a három pontból (**...**), **majd válassza a Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **a** Rendelés megerősítése modult, majd válassza az **OK gombra.**
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
