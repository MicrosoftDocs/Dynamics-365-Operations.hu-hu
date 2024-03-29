---
title: Minősítések és értékelések kezelése
description: Ez a cikk bemutatja, hogyan lehet kezelni a értékeléseket és az értékeléseket a webhelyszerkesztőben Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2019-10-01
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.openlocfilehash: b42ebff9b68b01e195e9c6a9641add45b6c7e2a9
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286465"
---
# <a name="manage-ratings-and-reviews"></a>Minősítések és értékelések kezelése

[!include [banner](includes/banner.md)]

Ez a cikk bemutatja, hogyan lehet kezelni a értékeléseket és az értékeléseket a webhelyszerkesztőben Microsoft Dynamics 365 Commerce.

A Dynamics 365 Commerce a Microsoft Azure kognitív szolgáltatását használja a szöveg automatikus moderálására a profán szavak kivonásával. Ezenkívül a moderátorok a Dynamics 365 Commerce webhelykészítő segítségével a következő manuális feladatokat hajthatják végre:

- Értékelések moderálása válaszadással vagy eltávolításukkal.
- Vevői értékelések törlése a vevő kérésére.
- Minősítések és értékelése tömeges importálása egy Microsoft Power BI sablonba, hogy elemezhetők legyenek a minősítések és a vélemények trendjei.

## <a name="read-a-review"></a>Értékelés elolvasása 

Ha a Commerce webhelykészítőben egy értékelést szeretne elolvasni, akkor a következő lépéseket kövesse.

1. Nyissa meg a **Kezdőlap \> Értékelések \> Moderálás** elemet.
1. A lap jobb felső részén található keresési mező használatával szűrheti a megjelenített értékeléseket a termék azonosítója, a terméknév vagy az értékelés szövege szerint.

A további szűrők használatával időszak, minősítés, csatorna vagy probléma állapota szerint korlátozhatja (levett, megválaszolt vagy jelentett) az értékeléseket.

![Moderálás kezdőoldala.](media/rnr-moderation-home.png) 

## <a name="respond-to-a-review"></a>Értékelés megválaszolása 

Előfordulhat, hogy azok a vevőkk, akik egy terméket megvásároltak, kifejezik elégedettségüket vagy elégedetlenségüket, vagy jelzik, hogy nem értik, hogyan kell használni a terméket. Moderátorként válaszolhat értékelésekre.. Ez a válasz a az értékeléssel együtt jelenik meg a webhelyen. 

Ha a Commerce webhelykészítőben egy értékelésre szeretne válaszolni, akkor a következő lépéseket kövesse.

1. Nyissa meg a **Kezdőlap \> Értékelések \> Moderálás** elemet.
1. Keresse meg és válassza ki a megválaszolandó értékelést.
1. A jobb oldali tulajdonságok ablaktáblán válassza a **Válasz hozzáadása** lehetőséget.
1. Adja meg a válasz szövegét, valamint azt a nevet, amelyet meg kell jeleníteni a válaszadó számára. Az alapértelmezett válaszadó neve **Moderátor.**
1. Amikor elkészült, válassza a **Válasz feladása** elemet.

![Válaszolás értékelésre.](media/rnr-moderation-response.png) 

## <a name="take-down-a-review"></a>Egy értékelés levétele 

Előfordulhat, hogy üzleti érdek fűződik ahhoz, hogy a moderátorok eltávolítsanak bizonyos vevői értékeléseket. 

Ha a Commerce webhelykészítőben egy értékelést szeretne félretenni, akkor a következő lépéseket kövesse.

1. Nyissa meg a **Kezdőlap \> Értékelések \> Moderálás** elemet.
1. Keresse meg és válassza ki azt az értékelést, amelyet le kell venni.
1. A jobb oldali tulajdonságok ablaktáblán, a **Értékelés félretétele** elemnél válassza ki a félretétel okot, majd válassza **Félretétel** lehetőséget.
    
## <a name="delete-a-customers-reviews-at-the-customers-request"></a>Vevői értékelések törlése a vevő kérésére 

Előfordulhat, hogy a vevők az értékelést és az értékelés adatait véglegesen törölni szeretnék egy e-kereskedelmi webhelyről. A vevőtől érkező eltávolítási kérelmet fogadó moderátor eltávolíthatja a vevő adatait az értékelés törlése funkcióval. A vevő adatainak megkereséséhez és törléséhez a moderátornak be kell írnia azt az e-mail-címet, amelyet a vevő a bejelentkezéshez és az értékelés elkészítéséhez használt. 

A Commerce webhelykészítő vevői adatainak megkereséséhez és törléséhez az alábbi lépéseket hajtsa végre.

1. Nyissa meg a **Kezdőlap \> Értékelések \> Törlés** elemet.
1. A **Vevő keresése e-mail-cím alapján** négyzetben adja meg a felhasználó e-mail-címét, majd válassza a **Keresés** lehetőséget.
1. Ha a vevőnek van valamilyen értékelési tevékenysége (például a beküldött értékelések, szavazás más vásárlói értékelések hasznosságával kapcsolatosan vagy megjegyzések egy másik vásárló értékelésére), az eredmények megjelennek. Mindegyik tételhez tartozik egy **Törlés** gomb.
1. Minden egyes törlendő elemhez válassza ki a **Törlés** gombot. Amikor a program megerősítést kér, válassza az **Igen** lehetőséget. 
    
![Ügyféladatok törlése.](media/rnr-moderation-delete-reviews.png) 

> [!NOTE]
> - Az adatok teljes eltávolítására rendszerből akár 7 napot is igénybe vehet. A moderátoroknak tájékoztatniuk kell a vevőket erről a késésről.
> - Ha a vevő a saját fiókbeállításaiban megváltoztatta a nevét, akkor a keresési eredmények között több elem is megjelenhet. Ebben az esetben a vevő adatainak teljes törléséhez a moderátornak ki kell választania a **Törlés** lehetőséget minden egyes elemhez. 

## <a name="download-ratings-and-reviews-data"></a>A minősítések és a értékelések adatainak letöltése

A Commerce webhelykészítővel a moderátorok importálhatják a minősítések és értékelések adatait, hogy elemezhessék a trendeket. Elérhető egy alapvető Power BI-metrikákat tartalmazó sablon. A moderátorok ezt a sablont használhatják a kötegben importált adatok összekapcsolására és egy irányítópult megjelenítésére is. Nem kell egyéni irányítópultot létrehozniuk. A moderátorok a Power BI-sablont is testreszabhatják, hogy az megfeleljen igényeiknek. 

A Commerce webhelykészítőben az értékelések és vélemények letöltéséhez az alábbi lépéseket hajtsa végre.

1. Nyissa meg a **Kezdőlap \> Értékelések \> Jelentéskészítés** elemet.
1. Válassza az **Étrékelés adatainak letöltése** lehetőséget a minősítések és értékelések adatainak tömeges letöltéséhez vesszővel tagolt (CSV) formátumban.

## <a name="view-ratings-and-reviews-trends"></a>Minősítések és értékelések trendjeinek áttekintése

A moderátorok letölthetik a Power BI-sablont, így megtekinthetik az trendeket az irányítópultokon.

A Commerce webhelykészítőben az értékelések és vélemények trendjeinek megtekintéséhez az alábbi lépéseket hajtsa végre.

1. Nyissa meg a **Kezdőlap \> Értékelések \> Jelentéskészítés** elemet.
1. A sablon letöltéséhez válassza ki a **PowerBI-sablont**.

    ![Töltse le a Power BI sablont.](media/rnr-moderation-reports.png) 

1. Nyissa meg a letöltött sablont a Power BI alkalmazás segítségével. Zárja be a megjelenő **Webtartalomhoz való hozzáférés** párbeszédpanelt, majd zárja be a megjelenő „Frissítési” hibaüzenetet.
1. Menjen a **Kezdőlapra**, válassza a **Lekérdezések szerkesztése** lehetőséget, majd válassza az **Adatforrás-beállítások** elemet.
1. Az **Adatforrás beállításai** párbeszédpanelen jelölje be a **Forrás módosítása** lehetőséget.
1. Az **URL-cím** mezőbe írja be az előző eljárásban letöltött értékelés adatainak elérési útját (például **c:\\reviews\\ReviewsData.csv**).

    ![A Vesszővel tagolt értékek párbeszédpanel URL-mezője.](media/rnr-powerbi-datasource-settings.png) 

1. Válassza a **OK** lehetőséget, majd kattintson az **Módosítások** alkalmazása gombra. Az adatforrásra módosításainak alkalmazása eltart egy-két percig.
1. Válassza ki a **Trendek lapot** a minősítések és a vélemények trendjeinek megtekintéséhez.

    ![Minősítések és értékelések trendjei.](media/rnr-powerbi-dashboard-template.png) 
    
## <a name="additional-resources"></a>További erőforrások

[Minősítések és értékelések áttekintése](ratings-reviews-overview.md)

[A minősítések és értékelések használatának bekapcsolása](opt-in-ratings-reviews.md)

[Minősítések és értékelések konfigurálása](configure-ratings-reviews.md)

[A termék minősítések szinkronizálása a következőben: Dynamics 365 Retail](sync-product-ratings.md)

[A minősítések és az értékelések moderátor általi manuális közzétételének engedélyezése](manual-publish-rating-reviews.md)

[Értékelések és véleményezések importálása és exportálása](import-export-reviews.md)

[Szolgáltatás a szolgáltatáshoz típusú hitelesítés konfigurálása](service-to-service-auth.md)

[Értékelések és vélemények GYIK](ratings-reviews-faq.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
