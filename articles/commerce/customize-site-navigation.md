---
title: Webhely-navigáció testreszabása
description: Ez a témakör azt mutatja be, hogyan lehet testreszabott online navigációs hierarchiát létrehozni a böngészésre szánt termékek rendszerezéséhez a Microsoft Dynamics 365 Commerce webhelyén.
author: bicyclingfool
manager: annbe
ms.date: 12/12/2019
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
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 642cb5c145dec68631eb9ab27d926ba8ab75c59b
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914910"
---
# <a name="customize-site-navigation"></a>Webhely-navigáció testreszabása

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet testreszabott online navigációs hierarchiát létrehozni a böngészésre szánt termékek rendszerezéséhez a Microsoft Dynamics 365 Commerce webhelyén.

## <a name="overview"></a>Áttekintés

Az online kirakatok általában lehetővé teszik a vevők számára, hogy a termékkategóriák között navigálva felfedezzék és böngésszék a termékeket. Ezt a lehetőséget általában a lapok felső részén található fülek, illetve a bal oldali navigációs sáv biztosítja. A Dynamics 365 Commerce alkalmazásban létrehozhatja és kezelheti a kategórianavigáció hierarchikus szerkezetét, valamint a különböző kategóriákba tartozó termékeket.

## <a name="create-a-retail-channel-navigation-hierarchy"></a>Kiskereskedelmi csatorna navigációs hierarchiájának létrehozása

Kiskereskedelmi csatorna navigációs hierarchiájának létrehozásához kövesse az alábbi lépéseket.

1. Ugorjon a **Kiskereskedelem \> Termékek és kategóriák \> Kategória és termék kezelése** lehetőségre.
1. Válassza ki a **Kategóriahierarchiák**, majd az **Új** lehetőséget.
1. Nevezze le a hierarchiát.

    > [!NOTE]
    > A legfelső kategória, amelyet létrehoz, a gyökér kategória csomópontja. A webhelyen nem fog megjelenni. Ha olyan kategóriahierarchiát szeretne létrehozni, ahol egyetlen felső szintű csomópont jelenik meg a webhelyen, hozza létre és nevezze el a kategóriát a gyökér kategóriájának gyermekeként.

1. Válassza ki az **Új kategória-csomópont** lehetőséget, és nevezze el a kategóriát.
1. Szükség szerint folytassa testvér- és gyermekkategóriák létrehozásával.

Ezután a felső szintű kategória alatt létrehozott egyes kategóriákhoz rendelheti hozzá a termékeket.

## <a name="customize-the-order-of-categories"></a>Kategóriák sorrendjének testreszabása

Alapértelmezés szerint a megadott kategóriák ábécésorrendben jelennek meg a webhelyén. Azonban a kategóriák megjelenítési sorrendjét is testreszabhatja.

## <a name="assign-a-category-hierarchy-type"></a>Típus hozzárendelése kategóriahierarchiához 

1. Ugorjon a **Kiskereskedelem \> Termékek és kategóriák \> Kategória és termék kezelése** lehetőségre.
1. Válassza a **Kategóriahierarchiák** lehetőséget.
1. A műveleti ablaktáblán a **Kategóriahierarchia** lapon a **Beállítás** csoportban válassza a **Hierarchiatípus társítása** lehetőséget.
1. Válassza az **Új** lehetőséget.
1. A **Kategóriahierarchia-típus** mezőben válassza a **Kiskereskedelmi csatornák navigációs hierarchiája** lehetőséget.
1. A **Kategóriahierarchia** mezőben válassza ki a korábban létrehozott csatornanavigációs hierarchiát.

## <a name="publish-new-or-updated-navigation-hierarchies"></a>Új vagy frissített navigációs hierarchiák közzététele

Ha a navigációs hierarchiáját elérhetővé szeretné tenni az online kirakatában, kövesse az alábbi lépéseket.

1. Lépjen a **Kiskereskedelem \> Csatorna beállítása \> Csatornakategóriák és termékattribútumok** lehetőségre.
1. Válassza ki az online áruházát a bal oldali fában.
1. Válassza a **Csatornafrissítések közzététele** lehetőséget.
1. Lépjen a **Kiskereskedelem \> Kiskereskedelem IT \> Elosztási ütemezés** pontra.
1. Keresse meg és válassza ki a listáról a **1040-es feladat** elemet.
1. Válassza a **Futtatás most** parancsot.
1. Ismételje meg az 5. és 6. lépést az 1070-es és 1150-es feladatok esetében.

## <a name="show-categories-on-your-site"></a>Kategóriák megjelenítése a webhelyen

Ha meg szeretné jeleníteni a kategóriahierarchiát az online kirakatában, akkor egy sablon vagy töredék megfelelő helyén egy navigációs menü modult kell hozzáadnia. A navigációs menü modul ezt követően megmutatja a navigációs hierarchiát, feltéve, hogy a kiskereskedelmi navigációs hierarchiát közzétette a csatornán, amelyhez a webhelye hozzá van kötve.

> [!NOTE]
> Az áruház kezdőcsomagban található navigációs menü modul lehetővé teszi a felhasználók számára, hogy csak olyan kategóriákba navigáljanak, amelyeknél nincsenek alkategóriák. Ha a vevők olyan kategóriákhoz szeretnének navigálni, amelyek rendelkeznek alkategóriákkal, akkor testre kell szabnia a navigációs menü modulját.

## <a name="add-custom-navigation-options"></a>Egyéni navigációs beállítások hozzáadása

A navigációs menüben hozzáadhat olyan navigációs beállításokat, amelyek nem szerepelnek a termék kategóriahierarchiájában. A termékkategóriák listájának végén például hozzáadhat egy **Kapcsolat** elemet, amely egy kapcsolati információkat tartalmazó lapra mutat, amelyet a webhelyéhez állított össze.

A navigációs menü egyéni navigációs beállításainak hozzáadásához kövesse az alábbi lépéseket.

1. Válassza ki a módosítani kívánt sablont vagy töredéket a navigációs menü modulban.
1. A tulajdonságlapon az **Adatok** fülön válassza az **Elem hozzáadása** lehetőséget egy új tartalomkezelő rendszer (CMS) navigációs elem létrehozásához.
1. Adja meg a hivatkozás szövegét és URL-címét.
1. További egyéni navigációs lehetőségek hozzáadásához ismételje meg a 2. és 3. lépést.
1. Ha végzett, mentse a sablont vagy a töredéket, és ellenőrizze, hogy be van-e adva.

## <a name="additional-resources"></a>További erőforrások

[Sablonok és elrendezések áttekintése](templates-layouts-overview.md)

[Sablonok használata](work-with-templates.md)

[Előre beállított elrendezések használata](work-with-layouts.md)

[Töredékek használata](work-with-fragments.md)

[Modulok használata](work-with-modules.md)

[Weblap URL-címének létrehozása](create-page-url.md)

[A közzétételi csoportokkal végzett munka](publish-groups.md)
