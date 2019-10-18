---
title: Karbantartási előrejelzések
description: Ez a cikk a karbantartási előrejelzések az Eszközkezelésben való használatát ismerteti.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 383c910b40199f2da863144c6dc85a579d0091e9
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/24/2019
ms.locfileid: "2024499"
---
# <a name="maintenance-forecasts"></a>Karbantartási előrejelzések

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


A munkarendelések létrehozásakor munkarendelési feladatokat hoz létre kapcsolódó eszközökkel és karbantartási feladattípusokkal. Karbantartási előrejelzéseket tartalmazó karbantartási feladattípus kiválasztásakor a program automatikusan átmásolja a munkarendelésbe az előrejelzéseket.

Előfordulhat, hogy egy munkarendelésben lehetősége van hozzáadni vagy törölni előrejelzési sorokat. A munkarendelés életciklus-állapotának beállítása, a kapcsolódó projekttípus és a projekt típusára vonatkozó szakaszszabályok határozzák meg, hogy az előrejelzés-sorok hozzáadhatók-e a naplóhoz, vagy szerkeszthetők-e. 

1. Kattintson az **Eszközkezelés** > **Közös** > **Munkarendelések** > **Összes munkarendelés** vagy **Aktív munkarendelések** elemre.

2. Válassza ki a munkarendelést a listában, majd kattintson az **Előrejelzés** elemre. A **Munkarendelés karbantartási előrejelzésébe**a munkarendelésen a kiválasztott karbantartási feladattípusból származó előrejelzési sorok jelennek meg.


## <a name="add-hours-forecast-to-a-work-order"></a>Órák előrejelzésének hozzáadása egymunkarendeléshez

1. Válassza ki azt a munkarendelés-feladatot, amelyhez előrejelzést szeretne hozzáadni.

2. Az **Órák** gyorslapon kattintson a **Hozzáadás** lehetőségre egy új sor létrehozásához.

3. Válasszon kategóriát a **Kategória** mezőben.

4. Az előre jelzett órák számának beszúrása az **Órák** mezőbe.

5. A **Sor tulajdonsága** mezőben válassza ki a sorban használt költségtípust.


## <a name="add-items-forecast-to-a-work-order"></a>Cikkek előrejelzésének hozzáadása egymunkarendeléshez

A cikkek munkarendelés karbantartási előrejelzéshez történő hozzáadásának három módja van: Létrehozhat sorokat a cikkekhez (pótalkatrészek), amelyek nem szerepelnek a cserealkatrészek listáján az eszköz DBJ-n, kiválaszthat cserealkatrészeket a jóváhagyott cserealkatrész-listából, illetve kiválaszthat cikkeket az eszköz DBJ-ről.

1. Válassza ki azt a munkarendelés-feladatot, amelyhez előrejelzést szeretne hozzáadni.

2. Válassza a **Cikkek** gyorslapot.

3. A **Hozzáadás** gombra kattintva hozzon létre egy új sort egy olyan pótalkatrészhez, amely nem szerepel a pótalkatrészek vagy az eszköz DBJ listáján.

4. Válassza ki a cikket a **Cikkszám** mezőben.

5. Írja be a mennyiséget az **Értékesítési mennyiség** mezőbe, majd válassza ki a mennyiségi egységet az **Egység** mezőben.

6. Írja be az önköltségi árat és a pénznemet a megfelelő mezőkbe, majd válassza ki a **Sortulajdonság** értékét.

7. Ha módosítani szeretné a cikkek soraiban megjelenített dimenziókat, kattintson a **Készlet** > **Dimenziók megjelenítése**elemre, válassza ki a dimenziókat, és válassza az „igen” beállítást a **Beállítás mentése** gombra kattintva.

8. Ha a karbantartási előrejelzéshez jóváhagyott pótalkatrészt szeretne hozzáadni, kattintson a **Pótalkatrészek hozzáadása** elemre, válassza ki a pótalkatrészt, szerkessze a szükséges adatokat, ha szükséges, és kattintson az **OK** gombra.

9. Ha szeretné hozzáadni a eszköz DBJ tételeit az előrejelzéshez, kattintson a **DBJ-cikkek hozzáadása** hivatkozásra, válassza ki a cikket, szerkessze akapcsolódó információt, ha szükséges, majd kattintson az **OK** gombra.

10. Ha szeretne áttekintést kapni arról, hogy az Eszközkezelésben hol használják a kiválasztott sorban található cikk az eszközökkel, alapértelmezett karbantartási feladattípusokkal, pótalkatrészekkel és munkarendelésekkel kapcsolatban, válassza a **Cikket hol használják** elemet. 



## <a name="add-expense-forecast-to-a-work-order"></a>Költségek előrejelzésének hozzáadása egymunkarendeléshez

1. Ez a témakör azt mutatja be, hogyan lehet költség-előrejelzést hozzáadni egy munkarendeléshez. A képernyő bal oldali részén válassza ki azt a munkarendelés-feladatot, amelyhez előrejelzést szeretne hozzáadni.

2. Válassza a **Költség** gyorslapot.

3. Kattintson a **Hozzáadás** elemre új sor létrehozásához.

4. Válasszon kategóriát a **Kategória** mezőben.

5. A **Mennyiség** mezőben adja meg a mennyiséget.

6. Szúrja be az önköltségi ár, az értékesítési pénznem és az eladási ár értékeit a megfelelő mezőkbe.

7. A **Sor tulajdonsága** mezőben válassza ki a sorban használt költségtípust.

>[!NOTE]
>A **Karbantartási előrejelzés összesítése** gyorslapon egy áttekintés látható az egyes lapokon létrehozott sorok számáról a kiválasztott munkarendelési feladathoz és a munkarendeléshez. Ezenkívül a munkarendelés feladathoz és a munkarendeléshez tartozó előre jelzett munkaórák összege is látható.

![1. ábra](media/06-work-orders.png)


## <a name="automatic-update-of-work-order-forecasts"></a>Munkarendelés-előrejelzések automatikus frissítése

Az Eszközkezelésben automatikusan frissítheti a munkarendelések előrejelzéseinek módosításait az óraköltség, a cikköltségekhez és más kiadásokhoz, amelyek frissítve lettek más modulokban. Erre azért van szükség, hogy a legutóbbi önköltségi árak legyenek mindig használva a munkarendelés-előrejelzésekben. Hasonló frissítések lehetségesek a [karbantartási feladattípus előrejelzésekhez](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md) is.

1. Kattintson az **Eszközkezelés** > **Időszakos** > **Előrejelzés** > **Munkarendelés-előrejelzés frissítése** hivatkozásra.

2. Ha szükséges , adja meg a munkarendelésekre vagy munkarendelés-feladatokra vonatkozó beállításokat a **Munkarendelés frissítése-előrejelzés** legördülő párbeszédpanelen. Kattintson a **Szűrőt** elemre ezen kiválasztásokhoz.

3. Ha szükséges, a **Futtatás a háttérben** gyorslapon szükség szerint kötegelt feladatként is beállíthatja az automatikus frissítést.

4. Az előrejelzés frissítése az **OK** gombra kattintva indítható el.


![2. ábra](media/07-work-orders.png)

