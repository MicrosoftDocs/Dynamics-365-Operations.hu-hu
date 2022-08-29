---
title: Új webhelyoldal hozzáadása
description: Ez a témakör azt ismerteti, hogyan lehet új webhelyet felvenni a laphoz Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 02/03/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: f6714463c9d5dc844b03f78f0f6ff60c5f270da3
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9270318"
---
# <a name="add-a-new-site-page"></a>Új webhelyoldal hozzáadása

[!include [banner](includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet új webhelyet felvenni a laphoz Microsoft Dynamics 365 Commerce.

Miután létrehozott sablonokat és töredékeket a webhelyhez, a következő lépés az, hogy megkezdi az azokat használó oldalak létrehozását. A kezdéshez ki kell választania egy sablont vagy egy elrendezést, egy oldalnevet és egy oldal URL-t.

## <a name="template-or-layout"></a>Sablon vagy elrendezés

Az új oldalhoz egy sablon vagy egy elrendezés használható. A további tudnivalókat lásd: [Sablonok és elrendezések áttekintése](templates-layouts-overview.md).

## <a name="specify-the-page-name"></a>Az oldal nevének megadása

A lap nevének egyedinek kell lennie a webhelyen, és leíró jellegűnek kell lennie, hogy könnyen meg tudja találni, és mások is tudják, mi a lap célja. A lapot később átnevezheti úgy, hogy szerkeszti, majd kijelöli az oldal neve melletti toll szimbólumot a tulajdonságablakban.

## <a name="specify-the-page-url"></a>A lap URL-címének megadása

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
1. Válassza a **Mentés** parancsot, majd válassza a **Szerkesztés befejezése** elemet.
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

[Dinamikus e-kereskedelmi oldalak létrehozása URL-paraméterek alapján](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
