---
title: Képlista modul
description: Ez a témakör ismerteti a képlista modulok működését és bemutatja, hogyan tudjuk hozzáadni azokat az egyes webhelyekhez a Microsoft Dynamics 365 Commerce segítségével.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 67da83410d819d01396d0b7d421076ee3b0f17ec
ms.sourcegitcommit: ccb39767bd3430c24f4653c26560bba2cd66553c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/19/2022
ms.locfileid: "8780843"
---
# <a name="image-list-module"></a>Képlista modul

[!include [banner](includes/banner.md)]

Ez a témakör ismerteti a képlista modulok működését és bemutatja, hogyan tudjuk hozzáadni azokat az egyes webhelyekhez a Microsoft Dynamics 365 Commerce segítségével.

A képlista modul segítségével egyszerűen hozzáadhatja a képek gyűjteményét (tömböt) a webhelyoldalakhoz. A tömb minden egyes képe konfigurálható bekezdésszöveggel és hivatkozásI URL-címekkel. A képlista modul leginkább a márka emblémájának megjelenítésére, illetve az emblémákat tartalmazó lista megjelenítésére alkalmas.

> [!IMPORTANT]
> - A képlista modul a Dynamics 365 Commerce 10.0.20-as verziótól elérhető a Commerce modultárban.
> - A képlista modult az Adventure Works téma mutatja be.

Az alábbi ábra egy olyan példát mutat be, ahol a képlista modul egy olyan szöveget jelenít meg, amely emblémákat is magában foglal egy Adventure Works B2C webhelyen.

![Példa képlista modulra, amely emblémákat tartalmazó szöveglistát jelenít meg](./media/Image_list.PNG)

Az alábbi ábra egy olyan példát mutat be, ahol a képlista modul egy márkaemblémákat jelenít meg egy Adventure Works B2B webhelyen.

![Példa a márkaemblémáit megjelenítő képlista modulra](./media/Image_list_B2B.PNG)

## <a name="image-list-module-properties"></a>Képlista modul tulajdonságai

| Tulajdonság neve | Értékek | Leírás |
|---------------|--------|-------------|
| Fejléc       | Fejléc szövege és fejléc címkéje (**H1**, **H2**, **H3**, **H4**, **H5** vagy **H6**) | A képlista modul szöveges fejléce. |
| Képlista    | Képek, szöveg és URL-címek | A tömb minden egyes eleme egy olyan kép, amelyet bekezdésszöveg és URL-cím kísér. |

## <a name="add-an-image-list-module-to-a-new-page"></a>Képlista modul hozzáadása új laphoz

Egy képlista modul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához a Commerce webhelyépítőben, hajtsa végre az alábbi lépéseket.

1. Nyissa meg a **Sablonok** lapot, és nyissa meg a webhely kezdőlapjának marketingsablonját (vagy hozzon létre új marketingsablont).
1. Az alapértelmezett **oldal** főbejáratában válassza ki a három pontból (**...**), **majd válassza a Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **a Képlista** modult, majd válassza az **OK gombra**.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.
1. Nyissa meg az **Oldalak** területet, majd a webhely kezdőlapját (vagy hozzon létre egy új kezdőlapot a marketingsablon használatával).
1. Az alapértelmezett **oldal** főbejáratában jelölje ki az három pont gombot (**...**), majd válassza **a Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki a **Kép listát**, majd válassza az **OK gombra.**
1. A képlista modul tulajdonságablakában adjon meg egy fejlécet (például **Márkáink**).
1. Képlistaelem hozzáadása, kép, valamilyen bekezdésszöveg és átirányítási URL megadásával.
1. Szükség szerint adja hozzá és konfigurálja a további képlistaelem modulokat.
1. Válassza a **Mentés** lehetőséget, majd az oldal előnézetének megtekintéséhez az **Előnézet** elemet.
1. Válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

## <a name="additional-resources"></a>További erőforrások

[Modultár áttekintése](starter-kit-overview.md)

[Adventure Works téma](adventure-works-theme.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
