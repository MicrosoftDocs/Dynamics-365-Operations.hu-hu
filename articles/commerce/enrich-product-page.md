---
title: A termékoldal bővítése
description: Ez a témakör azt ismerteti, hogyan lehet a termékoldalak bővítődni a témakörben Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 04/14/2020
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
ms.openlocfilehash: f01dcc2518fe861339b4984522582ed3de7aa6ad
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282134"
---
# <a name="enrich-a-product-page"></a>A termékoldal bővítése

[!include [banner](includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet a termékoldalak bővítődni a témakörben Microsoft Dynamics 365 Commerce.

Alapértelmezés szerint a webhelye általános lapot használ a termék adatainak megjelenítéséhez. Ez a lap a termékkel kapcsolatos alapadatokat és az értékesítéshez szükséges vezérlőket tartalmazza. A Commerce Scale Unit rendszerből származó információkat azonban egy adott termékhez tartozó további képekkel vagy szöveggel lehet kiegészíteni. Ezt a folyamatot nevezzük a terméklap bővítésének.

Sok esetben előfordulhat, hogy a termékhez külön további tartalmat kíván használni. Amikor a **Kiskereskedelem és kereskedelem** lehetőségre lép a szerkesztési eszközben, akkor a webhelyhez rendelt csatornából származó termékek listáját fogja látni. Ebben a listában a **Bővített** oszlop jelzi, hogy az adott termékhez tartozó terméklap bővített-e. Ha ebben az oszlopban pipa látható, akkor a termékhez létezik egy bővített terméklap. Ha nem látható pipa, akkor a termékhez a program az alapértelmezett terméklapot és tartalmat használja. A listában a termék nevére kattintva megtekintheti a bővített és nem bővített terméklapokat.

## <a name="enrich-a-product-page"></a>A termékoldal bővítése

A termék oldalának bővítéséhez kövesse az alábbi lépéseket.

1. A **Webhelyek** alatt válassza a **Fabrikam** (vagy a webhelye neve) lehetőséget.
1. A bal oldali navigációs ablakban válassza ki a **Termékek** lehetőséget.
1. Válassza ki azokat a termékeket, amelyeknél nem szerepel bővített terméklap.
1. A Művelet ablaktáblán válassza ki a **Terméklap bővítése** elemet.
1. Válassza a **PDP-sablon**, majd az **OK** elemet.
1. A bal oldali oldalstruktúrán bontsa ki a **Fő** helyet.
1. Válassza ki a **Fő** helyhez tartozó három pont gombot (**...**), majd válassza a **Modul hozzáadása** elemet.
1. Válassza a **Tároló 2**, majd az **OK** elemet.
1. Válassza ki a **Tárolós 2** helyhez tartozó három pont gombot, majd válassza a **Modul hozzáadása** elemet.
1. Válassza a **Funkció** parancsot, majd válassza az **OK** elemet.
1. A jobb oldali tulajdonságok panel **Rich Text** mezőbe írja be a termék frissített leírását.
1. A **Fejléc** mezőbe írja be a fejléc szövegét, majd kattintson az **OK** gombra.
1. Válassza a **Mentés** parancsot, majd válassza a **Szerkesztés befejezése** elemet.
1. A **Megjegyzések** mezőbe írja be a **Termék bővítve** szöveget, majd kattintson az **OK** gombra.
1. A bővített terméklap előnézetéhez válassza az **Előnézet** lehetőséget. Ha befejezte, zárja be az előnézeti lapot, és térjen vissza a szerkesztési eszközhöz.
1. Válassza a **Közzététel** lehetőséget.

## <a name="additional-resources"></a>További erőforrások

[Meglévő webhelyoldal módosítása](modify-existing-page.md)

[Új webhelyoldal hozzáadása](add-new-page.md)

[Oldalelrendezések kiválasztása](select-page-layouts.md)

[SEO-metaadatok kezelése](manage-seo-metadata.md)

[Oldal mentése, megtekintése és közzététele](save-preview-publish-page.md)

[Kategória céloldalának bővítése](enrich-category-page.md)

[Oldaltartalom hozzáférhetőségének ellenőrzése](verify-accessibility.md)

[Dinamikus e-kereskedelmi oldalak létrehozása URL-paraméterek alapján](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
