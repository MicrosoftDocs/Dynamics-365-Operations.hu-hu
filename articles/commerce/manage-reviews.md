---
title: Minősítések és értékelések kezelése
description: Ez a témakör azt mutatja be, hogyan lehet kezelni a minősítéseket és értékeléseket a Microsoft Dynamics 365 Commerce minősítések és értékelések moderálása eszközével.
author: gvrmohanreddy
manager: annbe
ms.date: 01/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-01
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: a7fa2ae3124a0a68b3890987c5dce2730e5c2183
ms.sourcegitcommit: 1e6c8163da5818196769eb278afb3a2335d0cbe3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/05/2020
ms.locfileid: "3027242"
---
# <a name="manage-ratings-and-reviews"></a>Minősítések és értékelések kezelése

[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet kezelni a minősítéseket és értékeléseket a Microsoft Dynamics 365 Commerce minősítések és értékelések moderálása eszközével.

## <a name="overview"></a>Áttekintés

A Dynamics 365 Commerce a Microsoft Azure kognitív szolgáltatását használja a szöveg automatikus moderálására a profán szavak kivonásával. Ezenkívül a moderátorok a minősítések és a értékelések moderálása eszközt a következő manuális feladatokhoz használhatják:

- Értékelések moderálása válaszadással vagy eltávolításukkal.
- Vevői értékelések törlése a vevő kérésére.
- Minősítések és értékelése tömeges importálása egy Microsoft Power BI sablonba hogy elemezhetők legyenek a minősítések és a vélemények trendjei.

## <a name="access-ratings-and-reviews-moderation-features"></a>A minősítések és értékelések moderációs funkcióinak elérése

Az e-Commerce webhelykezelő eszköz minősítések és ellenőrzések moderálási szolgáltatásainak eléréséhez hajtsa végre az alábbi lépéseket.

1. Jelentkezzen be a [Microsoft Lifecycle Services (LCS)](https://lcs.dynamics.com) szolgáltatásba.
1. Nyissa meg azt a projektet, amely tartalmazza a projektet, ahol az e-kereskedelmet inicializálni kívánja.
1. A **Környezetek** szakaszban válassza ki a környezetet.
1. A **Környezeti funkciók** területen kattintson a**Kiskereskedelem kezelése** elemre.
1. Az **e-Commerce** lap **Hivatkozások** területén válassza az **e-Commerce webhelykezelő eszköz** elemet.

## <a name="read-a-review"></a>Értékelés elolvasása 

1. Nyissa meg a **Kezdőlap \> Értékelések \> Moderálás** elemet.
1. A lap jobb felső részén található keresési mező használatával szűrheti a megjelenített értékeléseket a termék azonosítója, a terméknév vagy az értékelés szövege szerint.

A további szűrők használatával időszak, minősítés, csatorna vagy probléma állapota szerint korlátozhatja (levett, megválaszolt vagy jelentett) az értékeléseket.

![Moderálás kezdőoldala](media/rnr-moderation-home.png) 

## <a name="respond-to-a-review"></a>Értékelés megválaszolása 

Előfordulhat, hogy azok a vevőkk, akik egy terméket megvásároltak, kifejezik elégedettségüket vagy elégedetlenségüket, vagy jelzik, hogy nem értik, hogyan kell használni a terméket. Moderátorként válaszolhat értékelésekre.. Ez a válasz a az értékeléssel együtt jelenik meg a webhelyen. 

Az értékelés megválaszolásához kövesse az alábbi lépéseket.

1. Nyissa meg a **Kezdőlap \> Értékelések \> Moderálás** elemet.
1. Keresse meg és válassza ki a megválaszolandó értékelést.
1. A jobb oldali tulajdonságok ablaktáblán válassza a **Válasz hozzáadása** lehetőséget.
1. Adja meg a válasz szövegét, valamint azt a nevet, amelyet meg kell jeleníteni a válaszadó számára. Az alapértelmezett válaszadó neve **Moderátor.**
1. Amikor elkészült, válassza a **Válasz feladása** elemet.

![Válaszolás értékelésre](media/rnr-moderation-response.png) 

## <a name="take-down-a-review"></a>Egy értékelés levétele 

Előfordulhat, hogy üzleti érdek fűződik ahhoz, hogy a moderátorok eltávolítsanak bizonyos vevői értékeléseket. 

Az értékelés levételéhez kövesse az alábbi lépéseket.

1. Nyissa meg a **Kezdőlap \> Értékelések \> Moderálás** elemet.
1. Keresse meg és válassza ki azt az értékelést, amelyet le kell venni.
1. A jobb oldali tulajdonságok ablaktáblán válasszon ki egy eltávolítási okot, majd válassza a **Levétel** parancsot.
    
## <a name="delete-a-customers-reviews-at-the-customers-request"></a>Vevői értékelések törlése a vevő kérésére 

Előfordulhat, hogy a vevők az értékelést és az értékelés adatait véglegesen törölni szeretnék egy e-kereskedelmi webhelyről. A vevőtől érkező eltávolítási kérelmet fogadó moderátor eltávolíthatja a vevő adatait az értékelés törlése funkcióval. A vevő adatainak megkereséséhez és törléséhez a moderátornak be kell írnia azt az e-mail-címet, amelyet a vevő a bejelentkezéshez és az értékelés elkészítéséhez használt. 

A vevői adatok megkereséséhez és törléséhez hajtsa végre az alábbi lépéseket.

1. Nyissa meg a **Kezdőlap \> Értékelések \> Törlés** elemet.
1. A **Vevő keresése e-mail-cím alapján** mezőben adja meg a felhasználó e-mail-címét, majd válassza a **Keresés** lehetőséget.
1. Ha a vevőnek van valamilyen értékelési tevékenysége (például a beküldött értékelések, szavazás más vásárlói értékelések hasznosságával kapcsolatosan vagy megjegyzések egy másik vásárló értékelésére), az eredmények megjelennek. Mindegyik tételhez tartozik egy **Törlés** gomb.
1. Minden egyes törlendő elemhez válassza ki a **Törlés** gombot. Amikor a program megerősítést kér, válassza az **Igen** lehetőséget. 
    
![Ügyféladatok törlése](media/rnr-moderation-delete-reviews.png) 

> [!NOTE]
> - Az adatok teljes eltávolítására rendszerből akár 7 napot is igénybe vehet. A moderátoroknak tájékoztatniuk kell a vevőket erről a késésről.
> - Ha a vevő a saját fiókbeállításaiban megváltoztatta a nevét, akkor a keresési eredmények között több elem is megjelenhet. Ebben az esetben a vevő adatainak teljes törléséhez a moderátornak ki kell választania a **Törlés** lehetőséget minden egyes elemhez. 

## <a name="download-ratings-and-reviews-data"></a>A minősítések és a értékelések adatainak letöltése

A minősítések és értékelések moderálása eszközzel a moderátorok importálhatják a minősítések és értékelések adatait, hogy elemezhessék a trendeket. Elérhető egy alapvető Power BI-metrikákat tartalmazó sablon. A moderátorok ezt a sablont használhatják a kötegben importált adatok összekapcsolására és egy irányítópult megjelenítésére is. Nem kell egyéni irányítópultot létrehozniuk. A moderátorok a Power BI-sablont is testreszabhatják, hogy az megfeleljen igényeiknek. 

A minősítések és a értékelések adatainak letöltéséhez hajtsa végre a következő lépéseket.

1. Nyissa meg a **Kezdőlap \> Értékelések \> Jelentéskészítés** elemet.
1. Válassza az **Étrékelések adatainak letöltése** lehetőséget a minősítések és értékelések adatainak tömeges letöltéséhez vesszővel tagolt (CSV) formátumban.

## <a name="view-ratings-and-reviews-trends"></a>Minősítések és értékelések trendjeinek áttekintése

A moderátorok letölthetik a Power BI-sablont, így megtekinthetik az trendeket az irányítópultokon.

A minősítések és a értékelések trendjeinek megtekintéséhez hajtsa végre a következő lépéseket.

1. Nyissa meg a **Kezdőlap \> Értékelések \> Jelentéskészítés** elemet.
1. A sablon letöltéséhez válassza ki a **PowerBI-sablont**.

    ![A Power BI-sablon letöltése](media/rnr-moderation-reports.png) 

1. Nyissa meg a letöltött sablont a Power BI alkalmazás segítségével. Zárja be a megjelenő **Webtartalomhoz való hozzáférés** párbeszédpanelt, majd zárja be a megjelenő „Frissítési” hibaüzenetet.
1. Menjen a **Kezdőlapra**, válassza a **Lekérdezések szerkesztése** lehetőséget, majd válassza az **Adatforrás-beállítások** elemet.
1. Az **Adatforrás beállításai** párbeszédpanelen jelölje be a **Forrás módosítása** lehetőséget.
1. Az **URL-cím** mezőbe írja be az előző eljárásban letöltött értékelés adatainak elérési útját (például **c:\\reviews\\ReviewsData.csv**).

    ![A Vesszővel tagolt értékek párbeszédpanel URL-mezője](media/rnr-powerbi-datasource-settings.png) 

1. Válassza a **OK** lehetőséget, majd kattintson az **Módosítások** alkalmazása gombra. Az adatforrásra módosításainak alkalmazása eltart egy-két percig.
1. Válassza ki a **Trendek lapot** a minősítések és a vélemények trendjeinek megtekintéséhez.

    ![Minősítések és értékelések trendjei](media/rnr-powerbi-dashboard-template.png) 
    
## <a name="additional-resources"></a>További erőforrások

[Minősítések és értékelések áttekintése](ratings-reviews-overview.md)

[A minősítések és ellenőrzések használatának kiválasztása](opt-in-ratings-reviews.md)

[Minősítések és értékelések konfigurálása](configure-ratings-reviews.md)

[A termék minősítések szinkronizálása a következőben: Dynamics 365 Retail](sync-product-ratings.md)
