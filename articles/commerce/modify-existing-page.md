---
title: Meglévő webhelyoldal módosítása
description: Ez a témakör azt mutatja be, hogyan lehet módosítani egy létező webhelyoldalt a Microsoft Dynamics 365 Commerce megoldásban.
author: psimolin
manager: annbe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 47a7d17b97631ba469a9b68f5f6cf492ebccde6f
ms.sourcegitcommit: 872600103d2a444d78963867e5e0cdc62e68c3ec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2021
ms.locfileid: "5097306"
---
# <a name="modify-an-existing-site-page"></a>Meglévő webhelyoldal módosítása


[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet módosítani egy létező webhelyoldalt a Microsoft Dynamics 365 Commerce megoldásban.

## <a name="overview"></a>Áttekintés

Amikor módosítania kell egy lapot, az első lépés az, hogy megnyitja az oldalszerkesztőben. Nyissa meg azt a webhelyet, amely az oldalt tartalmazza majd az oldalak listáján keresse meg a kívánt oldalt. Ha nem találja az oldalt, akkor használhatja a szerkesztőeszköz bővített keresés funkcióját. Írja be az oldal pontos nevét, vagy írja be az első néhány betűjét, majd egy csillagot (\*). Megjelenik a lapok szűrt listája. Ez a lista a kívánt lap megtalálására használhatja. Miután megtalálta a megfelelő lapot, válassza ki a lap nevét, hogy megnyissa azt a lapszerkesztőben.

> [!TIP]
> Ha a lap látható a lapvizsgálóban akkor választhatja a **Szerkesztés** lehetőséget, és kiveheti az oldalt, mielőtt megnyitná azt a lapszerkesztőben. Ily módon egyszerre több lapot is kivehet.

Miután a lap a szerkesztőben meg van nyitva, győződjön meg arról, hogy az ki van-e véve az Ön számára. A szerkesztési eszközben a parancssáv dinamikus, környezetfüggő és állapotérzékeny. Éppen ezért csak azokat a tevékenységeket jeleníti meg, amelyeket a lapon jelenleg végrehajthat. Ha például a lap nincs Önhöz kivéve akkor a **Mentés** és **Szerkesztés befejezése** gomb nem jelenik meg a parancssávon. Az ablak jobb oldalán is látható a lap állapota.

Ha a lap még nincs kivéve akkor a parancssávon válassza a **Szerkesztés** lehetőséget. A parancssáv a lap új állapotának megfelelően változik. Egy értesítést is kap arról, hogy a lap ki lett véve az Ön számára.

A következő lépés a tényleges módosítások elvégzése. Gyakran a lap bal oldalon látható faszerkezetét kell használni a módosítani kívánt modul megtalálásához és kiválasztásához, majd a jobb oldali Tulajdonságok ablaktáblán végezheti el a szükséges módosításokat. 

Előfordulhat azonban, hogy a változás néha modellek vagy töredékek hozzáadásával vagy eltávolításával jár. Egy töredék vagy egy modul hozzáadásához használja a lap faszerkezettét és keresse meg azt a bővítőhelyet, amelyhez hozzá szeretné adni a modult vagy a töredéket, majd válassza a három pont gombot (**...**) ahhoz a bővítőhelyhez. Megjelenik egy menü, amely modul vagy töredék hozzáadására szolgáló parancsokat tartalmazza. Egy modul vagy töredék eltávolításához keresse meg és válassza ki azt a lap fastruktúrájában, válassza ki a három pont gombot, majd válassza ki a modul vagy a töredék törlésére szolgáló parancsot.

> [!TIP]
> Azon modulok tulajdonságait is megtekintheti és szerkesztheti, amelyek láthatók a vizuális oldalkészítő előnézetben, ha közvetlenül kiválasztja.

Miután elkészült a módosítások elvégzésével és a hatásuk előnézetének megtekintésével, akkor adja be a lapot a **Szerkesztés befejezése** elem kiválasztásával a parancssávon. 

Ha azonnal közzé szeretné tenni a változtatásokat, válassza a **Közzététel** elemet a parancssávon. A program közzéteszi a módosított lap legutóbbi bejelentkezett változatát, és az elérhetővé válik a webhelyet megtekintő külső felhasználók számára. 

## <a name="example-change-the-video-on-the-home-page"></a>Példa: Videó módosítása a kezdőlapon

A következő példa bemutatja, hogyan lehet módosítani a kezdőlap videolejátszó moduljában megjelenő videót.

1. A **Webhelyek** alatt válassza a **Fabrikam** (vagy a webhelye neve) lehetőséget.
1. A bal oldali navigációs ablakban válassza ki a **Oldalak** lehetőséget.
1. Keresse meg és válassza ki a kezdőlapot a megnyitáshoz a lapszerkesztőben.
1. Válassza a parancssáv **Szerkesztés** elemét.
1. Válassza ki a **Fő** bővítőhelyet a az oldalstruktúrában.
1. A **Fő** bővítőhely alatt bontsa ki az összes folyékony tárolómodult.
1. Keresse meg és jelölje ki a videolejátszó modulját.
1. A jobb oldali tulajdonságok ablaktáblán válassza ki a **videó** tulajdonságot. Megjelenik az eszközválasztó.
1. Az eszközválasztóban válassza ki a rendelkezésre álló videoeszközt, vagy válassza az **Új eszköz feltöltése** lehetőséget új videoeszköz feltöltéséhez.
1. Válassza ki az **OK** lehetőséget.
1. Válassza a **Mentés** parancsot, majd válassza a **Szerkesztés befejezése** elemet.
1. A **Megjegyzések** mezőbe írja be a **Videó módosítva** szöveget, majd kattintson az **OK** gombra.
1. A frissített oldal előnézetének megjelenítéséhez válassza az **Előnézet** lehetőséget. Ha befejezte, zárja be az előnézeti lapot, és térjen vissza a szerkesztési eszközhöz.
1. Válassza a **Közzététel** lehetőséget.

## <a name="additional-resources"></a>További erőforrások

[Új webhelyoldal hozzáadása](add-new-page.md)

[Oldalelrendezések kiválasztása](select-page-layouts.md)

[SEO-metaadatok kezelése](manage-seo-metadata.md)

[Oldal mentése, megtekintése és közzététele](save-preview-publish-page.md)

[A termékoldal bővítése](enrich-product-page.md)

[Kategória céloldalának bővítése](enrich-category-page.md)

[Oldaltartalom hozzáférhetőségének ellenőrzése](verify-accessibility.md)

[Dinamikus e-kereskedelmi oldalak létrehozása URL-paraméterek alapján](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]