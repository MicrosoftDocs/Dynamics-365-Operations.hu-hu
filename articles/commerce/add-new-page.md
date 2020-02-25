---
title: Új webhelyoldal hozzáadása
description: Ez a témakör azt mutatja be, hogyan lehet egy új webhelyoldalt hozzáadni a Microsoft Dynamics 365 Commerce alkalmazásban.
author: psimolin
manager: annbe
ms.date: 10/01/2019
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
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 68461f1f0be46f979a67e1806e03c02200cf61db
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2020
ms.locfileid: "3001346"
---
# <a name="add-a-new-site-page"></a>Új webhelyoldal hozzáadása


[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet egy új webhelyoldalt hozzáadni a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

Miután létrehozott sablonokat és töredékeket a webhelyhez, a következő lépés az, hogy megkezdi az azokat használó oldalak létrehozását. A kezdéshez ki kell választania egy sablont vagy egy elrendezést, egy oldalnevet és egy oldal URL-t.

## <a name="template-or-layout"></a>Sablon vagy elrendezés

Az új oldalhoz egy sablon vagy egy elrendezés használható. A további tudnivalókat lásd: [Sablonok és elrendezések áttekintése](templates-layouts-overview.md).

## <a name="page-name"></a>Oldal neve

Az oldal nevének egyedinek kell lennie az oldalon. Leírónak kell lennie, hogy könnyen megtalálja azt, és mások tudják, hogy mire szánták a lapot. Gondosan válassza ki a lap nevét, mert a későbbiekben nem módosítható.

## <a name="page-url"></a>Oldal URL-címe

Lehetőség van az új oldal URL-címének megadására is. Az oldalak létrehozásakor megadhatja a teljes URL-cím alapjául szolgáló karakterláncot. Ez a karaktersorozat ismert relatív URL vagy URL alkategória néven is. A program ezt követően egy teljes URL-címet generál, és az új oldalt hozzárendeli a program az URL alkategória alapján. Később a lap közzététele előtt módosíthatja az URL alkategóriát. További tudnivalókkal kapcsolatban lásd: [Weblap URL-címének létrehozása](create-page-URL.md).

> [!NOTE]
> A Dynamics 365 Commerce leválasztja az URL-címeket és a tartalmat. Más szóval egy olyan oldalt is létre lehet hozni, amely nem URL-címhez van társítva, és létre lehet hozni egy URL-címet, amely nincs egy oldalhoz társítva. Ezért a tartalomcsere végrehajtható egy URL esetében, és nem igényel állásidőt, valamint az átirányítások könnyebben kezelhetők.

## <a name="add-a-new-page"></a>Új oldal hozzáadása

Ha új webhelyoldalt szeretne hozzáadni a webhelyhez, hajtsa végre az alábbi lépéseket.

1. A **Webhelyek** alatt válassza a **Fabrikam** (vagy a webhelye neve) lehetőséget.
1. Válassza az **Új oldal** lehetőséget.
1. Az **Új oldal** párbeszédpanelen válasszon ki egy sablont, majd kattintson az **OK** gombra.
1. Az **Oldal neve** mezőben adjon meg egy nevet (például **Az új oldalam**).
1. Az **URL** mezőbe írja be az URL kiegészítésére szolgáló karaktersorozatot (URL alkategória) (például **mynewpage**).
1. Válassza ki az **OK** lehetőséget. Megjelenik az oldalszerkesztő. Figyelje meg, hogy a kiválasztott sablon alapján a program automatikusan hozzáadja a fejlécet és a láblécet az oldalhoz.
1. Az oldalstruktúrában válassza ki a **Fő** helyet, válassza ki a három pontot (**…**), majd válassza a **Modul hozzáadása** elemet.
1. Válassza a **Tároló**, majd az **OK** elemet
1. Válassza ki a **Folyékony tároló** lehetőséget, válassza ki a három pont gombot, majd válassza a **Modul hozzáadása** elemet.
1. Válassza ki a **Tartalomgazdag blokk** elemet, majd kattintson az **OK** gombra.
1. Válassza ki a **Tartalomgazdag blokk** lehetőséget, válassza ki a három pont gombot, majd válassza a **Modul hozzáadása** elemet.
1. Válassza ki a **Tartalomgazdag blokk elem** lehetőséget, majd kattintson az **OK** gombra.
1. A jobb oldali tulajdonságok panelen válassza a **Bekezdés** elemet, majd a mezőbe írja be **Saját tesztszöveg** szöveget.
1. Válassza a **Mentés** parancsot, majd válassza a **Beadás** elemet.
1. A **Megjegyzések** mezőbe írja be az **Új oldal hozzáadva** szöveget, majd kattintson az **OK** gombra.
1. A oldal előnézetének megjelenítéséhez válassza az **Előnézet** lehetőséget. Ha befejezte, zárja be az előnézeti lapot, és térjen vissza a szerkesztési eszközhöz.
1. Válassza a **Közzététel** lehetőséget.
1. A navigációs útvonalon (navigációs eszközök) válassza ki a **Fabrikam** (vagy a webhelye neve) lehetőséget.
1. A bal oldali navigációs ablakban válassza ki az **URL-címek** lehetőséget.
1. Keresse meg és válassza ki az URL-címét (**mynewpage**) a listából.
1. Válassza a **Közzététel** lehetőséget.

## <a name="additional-resources"></a>További erőforrások

[Meglévő webhelyoldal módosítása](modify-existing-page.md)

[Oldalelrendezések kiválasztása](select-page-layouts.md)

[SEO-metaadatok kezelése](manage-seo-metadata.md)

[Oldal mentése, megtekintése és közzététele](save-preview-publish-page.md)

[A termékoldal bővítése](enrich-product-page.md)

[Kategória céloldalának bővítése](enrich-category-page.md)

[Oldaltartalom hozzáférhetőségének ellenőrzése](verify-accessibility.md)
