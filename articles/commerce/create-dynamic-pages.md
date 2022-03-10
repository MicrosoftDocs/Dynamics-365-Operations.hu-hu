---
title: Dinamikus e-kereskedelmi oldalak létrehozása URL-paraméterek alapján
description: Ez a témakör azt mutatja be, hogyan lehet beállítani olyan Microsoft Dynamics 365 Commerce e-kereskedelmi oldalt, amely az URL-paraméterek alapján szolgáltat dinamikus tartalmat.
author: StuHarg
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ROBOTS: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 3de589e908b20a90ba32fc49f1b987066283aafacfb4b879124b4f0677b34301
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6747673"
---
# <a name="create-dynamic-e-commerce-pages-based-on-url-parameters"></a>Dinamikus e-kereskedelmi oldalak létrehozása URL-paraméterek alapján

[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet beállítani olyan Microsoft Dynamics 365 Commerce e-kereskedelmi oldalt, amely az URL-paraméterek alapján szolgáltat dinamikus tartalmat.

Az e-kereskedelmi oldalak különböző tartalmak nyújtására konfigurálhatók az URL elérési útjának egy szegmense alapján. Ennek megfelelően az oldal dinamikus oldalként ismert. A szegmenst a program paraméterként használja az oldal tartalmának beolvasására. Létrehoznak például egy **blog\_viewer** nevű lapot, amelyet a `https://fabrikam.com/blog` URL-címhez társítanak. Ezen a lapon különböző tartalmak láthatók az URL elérési útjának utolsó szegmense alapján. A `https://fabrikam.com/blog/article-1` URL utolsó szegmense például: **article-1**.

Az URL elérési útjában található szegmenseihez különálló, a dinamikus oldalt felülbíráló egyéni lapok is társíthatók. Létrehoznak például egy **blog\_summary** nevű lapot, amelyet a `https://fabrikam.com/blog/about-this-blog` URL-címhez társítanak. Az URL lekérése esetén a rendszer az **about-this-blog** paraméterrel társított **blog\_summary** oldalt jeleníti meg a **blog\_viewer** oldal helyett.

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

Az útvonal konfigurálása után a paraméterezett URL elérési úthoz tartozó összes kérés az adott URL-hez társított oldalt tölti be. Ha a kérések egy további szegmenst tartalmaznak, a társított lap megjelenik, és az oldal tartalmának beolvasása a szegmens használatával történik paraméterként. A `https://fabrikam.com/blog/article-1` például a **blog\_summary** oldalt jeleníti meg, az oldal tartalmának betöltése pedig az **/article-1** paraméterrel történik.

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
