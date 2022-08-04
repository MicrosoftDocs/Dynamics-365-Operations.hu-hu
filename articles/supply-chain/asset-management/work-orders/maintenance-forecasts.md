---
title: Karbantartási előrejelzések
description: Ez a témakör bemutatja az Eszközkezelésben eszközkezelési karbantartási előrejelzéseket.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderForecastToJournals, EntAssetWorkOrderForecast
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 4e3da8ab9a739c8455d2c1d2720f94f91a42927d
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/02/2022
ms.locfileid: "9111600"
---
# <a name="maintenance-forecasts"></a>Karbantartási előrejelzések

[!include [banner](../../includes/banner.md)]



A munkarendelések létrehozásakor munkarendelési feladatokat hoz létre, amelyek a kapcsolódó eszközökkel és karbantartási feladattípusokkal rendelkeznek. Karbantartási előrejelzéseket tartalmazó karbantartási feladattípus kiválasztásakor a program automatikusan átmásolja a munkarendelésbe az előrejelzéseket.

Előfordulhat, hogy előrejelzési sorokat szeretné egy munkarendeléshez hozzáadni, vagy egy munkarendelésből törölni azokat. A munkarendelés életciklus-állapotának beállítása, a kapcsolódó projekttípus és a projekt típusára vonatkozó szakaszszabályok határozzák meg, hogy az előrejelzési sorok hozzáadhatók-e a naplóhoz, vagy szerkeszthetők-e. A munkarendelés életciklus-állapotaival és kapcsolódó projektfázisaival kapcsolatos további információért lásd: [Előrejelzések, munkarendelések és projektek](../integration-to-project-management-and-accounting/forecasts-work-orders-and-projects.md).

1. Válassza ki **az Eszközkezelés** > **munkarendelések minden** > **munkarendelését vagy** az aktív **munkarendeléseket**.

2. Válassza ki a munkarendelést a listában, majd a Művelet panel > **Munkarendelés** lapján a **Projekt** csoportban válassz az **Előrejelzés** pontot. A **Munkarendelés karbantartási előrejelzése** oldalon a munkarendelésen a kiválasztott karbantartási feladattípusból származó előrejelzési sorok jelennek meg.


## <a name="add-an-hours-forecast-to-a-work-order"></a>Órák előrejelzésének hozzáadása egymunkarendeléshez

1. A **Munkarendelés karbantartási előrejelzése** lapon válassza ki azt a munkarendelési feladatot, amelyhez előrejelzést szeretne hozzáadni.

2. Az **Órák** gyorslapon válassza a **Hozzáadás** lehetőséget egy új sor létrehozásához.

3. Válasszon egy kategóriát a **Kategória** mezőben.

4. Az előre jelzett órák számát írja be az **Órák** mezőbe.

5. A **Sor tulajdonsága** mezőben válassza ki a sorhoz használandó költségtípust.


## <a name="add-an-items-forecast-to-a-work-order"></a>A Cikkek előrejelzésének hozzáadása egymunkarendeléshez

Háromféle módja van cikkek munkarendelés karbantartási előrejelzésekhez történő hozzáadására. Létrehozhat sorokat a cikkekhez (pótalkatrészek), amelyek nem szerepelnek az eszköz anyagjegyzékén (DBJ), kiválaszthat cserealkatrészeket a jóváhagyott cserealkatrész-listából, illetve kiválaszthat cikkeket az eszköz DBJ-ről.

- A **Munkarendelés karbantartási előrejelzése** lapon válassza ki azt a munkarendelési feladatot, amelyhez előrejelzést szeretne hozzáadni.

- A **Cikkek** gyorslapon a megfelelő módszer használatával vegyen fel cikkeket a karbantartási előrejelzésbe.

Új sor létrehozásához egy olyan pótalkatrészhez, amely nem szerepel a pótalkatrészek vagy az eszköz DBJ listáján kövesse az alábbi lépéseket:

1. Válassza a **Hozzáadás** lehetőséget.
2. Válasszon egy cikket a **Cikkszám** mezőben.
3. Az **Értékesítési Mennyiség** mezőben Írja be a mennyiséget.
4. Az **Egység** mezőben válassza ki a mennyiséghez tartozó mértékegységet.
5. Az **Önköltségi ár** és a **Pénznem** mezőkbe írja be a megfelelő értékeket.
6. A **Sortulajdonság** mezőben válasszon ki egy sortulajdonságot.
7. A cikkek soraiban megjelenített dimenziók módosításához, válassza a **Készlet** > **Dimenziók megjelenítése** elemre, válassza ki a dimenziókat, majd az a **Beállítás mentése** beállításnál az **Igen** lehetőséget.

Ha a pótalkatrészeket szeretne a jóváhagyott pótalkatrész listából hozzáadni, hajtsa végre az alábbi lépéseket:

1. Válassza a **Pótalkatrészek hozzáadása** lehetőséget.
2. Válassza ki a pótalkatrészt, és igény szerint szerkessze a szükséges adatokat.
3. Válassza ki az **OK** lehetőséget.

Cikk az eszköz DBJ-ből történő hozzáadásához kövesse az alábbi lépéseket:

1. Válassza a **DBJ-cikkek hozzáadása** lehetőséget.
2. Válassza ki a cikket, és igény szerint szerkessze a szükséges adatokat.
3. Válassza ki az **OK** lehetőséget.

Ha szeretne áttekintést kapni arról, hogy hol használják a kiválasztott sorban található cikket az eszközökkel, alapértelmezett feladattípusokkal, pótalkatrészekkel és munkarendelésekkel kapcsolatban, válassza a **Cikket hol használják** elemet. Az áttekintéssel kapcsolatos további tudnivalókat lásd a [Cikk használati helye](../controlling-and-reporting/item-where-used.md)részben.


## <a name="add-an-expense-forecast-to-a-work-order"></a>Költségek előrejelzésének hozzáadása egy munkarendeléshez

1. A **Munkarendelés karbantartási előrejelzése** lapon válassza ki azt a munkarendelési feladatot, amelyhez előrejelzést szeretne hozzáadni.

2. A **Költség** gyorslapon válassza a **Hozzáadás** lehetőséget egy új sor létrehozásához.

3. Válasszon egy kategóriát a **Kategória** mezőben.

4. A **Mennyiség** mezőben Írja be a mennyiséget.

5. A **Önköltségi ár**, **Értékesítési pénznem** és **Eladási ár** mezőkbe adja meg a megfelelő értékeket.

6. A **Sor tulajdonsága** mezőben válassza ki a sorhoz használandó költségtípust.

>[!NOTE]
>A **Karbantartási előrejelzés összesítése** gyorslapon egy áttekintés látható az egyes gyorslapokon létrehozott sorok számáról a kiválasztott munkarendelési feladathoz és a munkarendeléshez. Ezenkívül a munkarendelés feladathoz és a munkarendeléshez tartozó előre jelzett munkaórák összege is megjelenik.

Az alábbi ábra a **Munkarendelés beszerzés előrejelzés** egy példáját mutatja be.

![1. ábra](media/06-work-orders.png)


## <a name="automatic-update-of-work-order-forecasts"></a>Munkarendelés-előrejelzések automatikus frissítése

Ha más modulokban is frissítik az óraköltségeket, a cikk-költségeket és a költségeket, akkor az Eszközkezelés modul munkarendelés-előrejelzései automatikusan frissíthetők, hogy tükrözzék ezeket a módosításokat. Ez a képesség segít garantálni, hogy a legutóbbi önköltségi árak legyenek mindig használva a munkarendelés-előrejelzésekben. Hasonló frissítéseket végezhet a [karbantartási feladattípus előrejelzésekhez](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md) is.

1. Válassza az **Eszközkezelés** > **Időszakos** > **Előrejelzés** > **Munkarendelés-előrejelzés frissítése** lehetőséget.

2. Ha szükséges , adja meg a munkarendelésekre vagy munkarendelés-feladatokra vonatkozó beállításokat a **Munkarendelés frissítése-előrejelzés** legördülő párbeszédpanelen a **Befoglalandó rekordok** lapon. Kattintson a **Szűrő** elemre a kapcsolódó kiválasztásokhoz.

3. A **Futtatás a háttérben** gyorslapon szükség szerint kötegelt feladatként is beállíthatja az automatikus frissítést.

4. Az előrejelzés frissítése az **OK** gombot választva indítható el.


Az alábbi ábra a **Munkarendelés előrejelzés frissítése** párbeszédpanel egy példáját mutatja be.

![2. ábra](media/07-work-orders.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
