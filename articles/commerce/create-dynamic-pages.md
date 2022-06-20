---
title: Dinamikus e-kereskedelmi oldalak létrehozása URL-paraméterek alapján
description: Ez a témakör azt ismerteti, hogyan Microsoft Dynamics 365 Commerce lehet beállítani olyan e-commerce oldalt, amely az URL-paraméterek alapján dinamikus tartalmat szolgál.
author: StuHarg
ms.date: 05/27/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2019-09-30
ms.openlocfilehash: e2b13403ffb316059476a03857c849b4f9f8cb9c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8884663"
---
# <a name="create-dynamic-e-commerce-pages-based-on-url-parameters"></a>Dinamikus e-kereskedelmi oldalak létrehozása URL-paraméterek alapján

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Ez a témakör azt ismerteti, hogyan Microsoft Dynamics 365 Commerce lehet beállítani olyan e-commerce oldalt, amely az URL-paraméterek alapján dinamikus tartalmat szolgál.

Az e-kereskedelmi oldalak különböző tartalmak nyújtására konfigurálhatók az URL elérési útjának egy szegmense alapján. Ennek megfelelően az oldal dinamikus oldalként ismert. A szegmenst a program paraméterként használja az oldal tartalmának beolvasására. Például egy webhelyszerkesztőben **létrehozott lap, amely a Viewer Viewer\_** nevet tartalmazza, az URL-címhez lesz hozzárendelve `https://fabrikam.com/blog`. Ezen a lapon különböző tartalmak láthatók az URL elérési útjának utolsó szegmense alapján. A `https://fabrikam.com/blog/article-1` URL utolsó szegmense például: **article-1**.

A paraméterezett URL-szegmenst a webhelyszerkesztő oldalával is felülbírálhatja. Például az URL-címhez hozzárendelhet egy webhelyszerkesztőben létrehozott **lapot, és elnevezi az\_** összegzést `https://fabrikam.com/blog/about-this-blog`. Amikor az `https://fabrikam.com/blog` URL-címet a `/about-this-blog` végén található szegmenssel kérik, **\_**`/about-this-blog` akkor a rendszer visszaadja az összegzési lap tartalmát, és nem azt a szegmenst, amelyet paraméterként értelmez a lap.`https://fabrikam.com/blog` 

Amikor kiválasztja a dinamikus lapnak átadva kívánt paraméterek nevét, az URL-címben megjelenő dinamikus lap neve (`/blog` a fenti példában) nem használható paraméternévként vagy paraméternév alhálózataként. 

> [!NOTE]
> A dinamikus oldal tartalmának tárhelyre, beolvasásra és megjelenítésre vonatkozó funkcióit egy egyéni modul használatával valósítják meg. További információt az [Online csatorna bővíthetősége](e-commerce-extensibility/overview.md) című témakörben talál.

## <a name="set-up-a-dynamic-e-commerce-page"></a>Dinamikus e-kereskedelmi oldal beállítása

Dinamikus e-kereskedelmi oldal létrehozásához létre kell hoznia egy dinamikus lapot, létre kell hoznia az alap URL-címet, majd konfigurálnia kell a dinamikus oldal útvonalát.

### <a name="create-the-page-that-will-serve-dynamic-content"></a>A dinamikus tartalmat szolgáltató oldal létrehozása

Dinamikus tartalmat szolgáltató oldal létrehozásához kövesse az [Új webhelyoldal hozzáadása](add-new-page.md) pontban leírt lépéseket. A létrehozott oldalhoz egy olyan modul implementálására lesz szükség, amely az URL elérési útjának utolsó szegmensét használja a külső adatforrásból származó tartalom beolvasására. Az egyéni modul fejlesztésével kapcsolatos további tudnivalókat lásd az [Online csatorna bővíthetősége](e-commerce-extensibility/overview.md) pontban.

### <a name="create-the-base-url-for-the-dynamic-page"></a>A dinamikus oldal alap URL-címének létrehozása

A dinamikus oldal alap URL-címének Commerce webhelykészítőben történő létrehozásához kövesse az alábbi lépéseket.

1. Lépjen az **URL-ek** pontra, és válassza az **Új \> Új URL** lehetőséget.
1. Az **Új URL-cím létrehozása** párbeszédpanelen válassza a **Belső oldal** lehetőséget. Az **URL elérési útja** pontban adja meg a dinamikus lap gyökereként szolgáló elérési utat (ebben a példában: **/blog**). Majd válassza a **Következő** lehetőséget.
1. Az **Oldal kiválasztása** párbeszédpanelen válassza ki a létrehozott, dinamikus oldalként működtetni kívánt oldalt, majd kattintson a **Mentés** gombra.
1. Válassza a **Közzététel** lehetőséget.

### <a name="configure-the-route-to-the-dynamic-page"></a>Dinamikus oldal útvonalának konfigurálása

A dinamikus oldalra mutató útvonal Commerce webhelykészítőben történő konfigurálásához kövesse az alábbi lépéseket.

1. Lépjen a **Webhelybeállítások \> Bővítmények** pontra.
1. A **Paraméterezett URL elérési utak** mezőben válassza a **Hozzáadás** lehetőséget, majd adja meg az URL létrehozásakor megadott URL elérési utat (ebben a példában: **/blog**).
1. Válassza a **Mentés és közzététel** lehetőséget.

Az útvonal konfigurálása után a paraméterezett URL elérési úthoz tartozó összes kérés az adott URL-hez társított oldalt tölti be. Ha a kérések egy további szegmenst tartalmaznak, a társított lap megjelenik, és az oldal tartalmának beolvasása a szegmens használatával történik paraméterként. Visszaadja például azt a `https://fabrikam.com/blog/article-1``https://fabrikam.com/blog` lapot, **amely a /article-1 paraméterrel beolvasott tartalmat jeleníti** meg.

## <a name="override-a-parameterized-url-with-a-custom-page"></a>Paraméterezett URL elérési út felülbírálása egyéni oldal használatával

Ha felül szeretne bírálni egy paraméterezett URL elérési utat egy egyéni oldallal a Commerce webhelykészítőben, kövesse az alábbi lépéseket.

1. Lépjen az **URL-ek** pontra, és válassza az **Új \> Új URL** lehetőséget.
1. Az **Új URL-cím létrehozása** párbeszédpanelen válassza a **Belső oldal** lehetőséget. Az **URL elérési útja** pontba írja be a felülbírálni kívánt szegmenst tartalmazó elérési utat (ebben a példában: **/blog/about-this-blog**). Majd válassza a **Következő** lehetőséget.
1. Az **Oldal kiválasztása** párbeszédpanelen válassza ki az egyéni oldalt, majd válassza a **Mentés** lehetőséget.
1. Válassza a **Közzététel** lehetőséget.
1. Ha még nem tette közzé az egyéni oldalt, lépjen az **Oldalak** lehetőségre, válassza ki az egyéni oldalt, majd válassza a **Közzététel** lehetőséget.

Az egyéni oldal közzététele után a rendszer az egyéni oldalt jeleníti meg a paraméterezett tartalommal rendelkező dinamikus oldal helyett.

## <a name="additional-resources"></a>További erőforrások

[Meglévő webhelyoldal módosítása](modify-existing-page.md)

[Új webhelyoldal hozzáadása](add-new-page.md)

[Oldalelrendezések kiválasztása](select-page-layouts.md)

[SEO-metaadatok kezelése](manage-seo-metadata.md)

[Oldal mentése, megtekintése és közzététele](save-preview-publish-page.md)

[A termékoldal bővítése](enrich-product-page.md)

[Kategória céloldalának bővítése](enrich-category-page.md)

[Oldaltartalom hozzáférhetőségének ellenőrzése](verify-accessibility.md)

[Online csatorna bővíthetősége](e-commerce-extensibility/overview.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
