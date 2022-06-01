---
title: Feliratkozási modul
description: Ez a témakör a feliratkozási modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
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
ms.openlocfilehash: efc9150ea5ddeb7051f82fb07c4d566ac8a48dfa
ms.sourcegitcommit: ccb39767bd3430c24f4653c26560bba2cd66553c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/19/2022
ms.locfileid: "8780589"
---
# <a name="subscribe-module"></a>Feliratkozási modul

[!include [banner](includes/banner.md)]

Ez a témakör a feliratkozási modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.

A feliratkozási modulokat a webhelyoldalakon fel lehet használni a vevők információinak rögzítésére hírlevélre vagy promóciókra.

Az alábbi ábra egy feliratkozási modul példáját mutatja be egy Adventure Works webhely oldalának láblécében.

![Feliratkozási modul példája egy Adventure Works webhely oldalának láblécében](./media/Subscribe.PNG)

> [!IMPORTANT]
> - Az előfizetési modul a Dynamics 365 Commerce 10.0.20-as verziótól elérhető a Commerce modultárban.
> - A feliratkozási modult az Adventure Works téma mutatja be.
> - A feliratkozási modulhoz adatművelet-kiterjesztés szükséges ahhoz, hogy egyes marketing-e-mail-szolgáltatókkal együttműködjön, hogy hírlevél- vagy promóciós e-maileket tudjanak küldeni a vevői adatok rögzítését követően.

## <a name="subscribe-module-properties"></a>Feliratkozási modul tulajdonságai

| Tulajdonság neve | Értékek | Leírás |
|---------------|--------|-------------|
| Fejléc       | Fejléc szövege és fejléc címkéje (**H1**, **H2**, **H3**, **H4**, **H5** vagy **H6**) | Szöveges fejléc a feliratkozási modulhoz, például **Iratkozzon fel a hírlevélre** vagy **Regisztráljon, és 10% kedvezményt kap**. |
| Bekezdés     | Bekezdés szövege | A feliratkozási modul támogatja a bekezdés szöveget és a rich text formátumot, így további részleteket lehet adni a fejlécben található cselekvésre felhíváshoz. |

## <a name="add-a-subscribe-module-to-a-new-page"></a>Feliratkozási modul hozzáadása egy új oldalhoz

Egy feliratkozási modul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához a Commerce webhelyépítőben, hajtsa végre az alábbi lépéseket.

1. Nyissa meg a **Sablonok** lapot, és nyissa meg a webhely kezdőlapjának marketingsablonját (vagy hozzon létre új marketingsablont).
1. Az alapértelmezett **oldal** főbejáratában válassza ki a három pontból (**...**), **majd válassza a Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza a **Előfizetés** modult, majd kattintson az **OK gombra**.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.
1. Nyissa meg az **Oldalak** területet, majd a webhely kezdőlapját (vagy hozzon létre egy új kezdőlapot a marketingsablon használatával).
1. Az alapértelmezett **oldal** főbejáratában jelölje ki az három pont gombot (**...**), majd válassza **a Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza a **Előfizetés** modult, majd kattintson az **OK gombra**.
1. Adjon hozzá egy fejlécet a feliratkozási modul tulajdonságablakában, például: **Feliratkozás**.
1. Adja hozzá a bekezdés szövegét, például: **Legújabb trendek, stílusok és promóciók. Szerepel a listán? Iratkozzon fel, és fantasztikus akciók várják!**
1. Válassza a **Mentés** lehetőséget, majd az oldal előnézetének megtekintéséhez az **Előnézet** elemet.
1. Válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

## <a name="additional-resources"></a>További erőforrások

[Modultár áttekintése](starter-kit-overview.md)

[Adventure Works téma](adventure-works-theme.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
