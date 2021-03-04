---
title: Felhasználás regisztrálása
description: Ez a témakör azt mutatja be, hogyan lehet felhasználást regisztrálni az Eszközkezelés modulban.
author: josaw1
manager: tfehr
ms.date: 08/21/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderJournal, EntAssetWorkOrderAddSparePart
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 2c9bbd51da23ea412bc124f932f73876a9506d47
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429632"
---
# <a name="register-consumption"></a>Felhasználás regisztrálása

[!include [banner](../../includes/banner.md)]

 

Ha egy munkarendelésen befejeződött egy karbantartási feladat, következő lépésként el kell végezni a felhasználási regisztrációkat és a naplók feladását. Regisztráció a következő felhasználási típusokon végezhető el: órák, cikkek és kiadások. A program a különböző felhasználási típusokat a **Munkarendelési naplók** lapon regisztrálja és adja fel. A program az **Eszközkezelés modulban** található naplóbeállítást használja a **Projektvezetés és könyvelés** modulban feltüntetett órák, cikkek és kiadások külön naplóinak a létrehozásához és feladásához.

Bizonyos esetekben előfordulhat, hogy egy munkarendelésben lehetősége van hozzáadni vagy törölni előrejelzési sorokat. A munkarendelés életciklus-állapotának beállítása, a kapcsolódó projekttípus és a projekt típusára vonatkozó szakaszszabályok határozzák meg, hogy a naplósorok hozzáadhatók-e a naplóhoz, vagy szerkeszthetők-e. A munkarendelés életciklus-állapotaival és kapcsolódó projektfázisaival kapcsolatos további információkat az [Előrejelzések, munkarendelések és projektek](../integration-to-project-management-and-accounting/forecasts-work-orders-and-projects.md) részben olvashat.

>[!NOTE]
>A munkarendelés életciklus-állapotára vonatkozó naplókhoz automatikus feladás is beállítható. További információt itt talál: [Munkarendelés életciklus-állapotai](../setup-for-work-orders/work-order-lifecycle-states.md).

1. Kattintson az **Eszközkezelés** > **Közös** > **Munkarendelések** > **Összes munkarendelés** vagy **Aktív munkarendelések** elemre.

2. Válassza ki a munkarendelést, és kattintson a **Naplók** elemre.

3. A **Másolás előrejelzésből** lehetőségre kattintva átviheti azokat az előrejelzési sorokat, amelyek a munkarendeléshez kapcsolódnak. Kiválaszthatja az átvinni kívánt felhasználási típusokat.

4. A **Sor hozzáadása** gombra kattintva és a sor adatainak kitöltésével több felhasználási sort is hozzáadhat a megfelelő gyorslaphoz, ha szükséges.

5. A **Naplók ellenőrzése** elemre kattintva ellenőrizheti a naplósorokat feladás előtt.

6. A **Naplók feladása** gombra kattintva feladhatja a naplósorokat.

7. A felhasználási naplók feladása után frissítheti a munkarendelés életciklus-állapotát. Például annak jelzésére, hogy a munkarendelést befejezték, az életciklus-állapotot a „Befejezett” lehetőségre frissítheti.

    - A **Munkarendelési naplók** lap tetején található **Megjelenítés** mezőben válassza ki a megjeleníteni kívánt naplósorokat a következők közül: **Összes**, **Nincs feladva** vagy **Feladva**. A feladott naplóknál ki van pipálva a **Feladva** jelölőnégyzet.  
    - Amikor a munkarendelési naplóban cikksorok jönnek létre, a program automatikusan átviszi a cikkhez tartozó termékdimenziókat és nyomon követési dimenziókat a napló sorába.  

Az alábbi képernyőkép azt szemlélteti, hogyan kell a **Munkarendelési naplók** elemben óra- és cikkregisztrációkat elvégezni egy munkarendelésnél.

![1. ábra](media/01-consumption.png)


## <a name="split-hours-on-work-orders-with-several-work-order-jobs"></a>A munkarendelések óráinak több munkarendelési feladattal történő megosztása

Ha a munkarendelés több munkarendelési feladatot is tartalmaz, akkor a munkaórák regisztrálhatók az **Órák megosztása** funkció segítségével, ami azt jelenti, hogy az egyes munkarendelési feladatokban egyenletesen lehet felosztani az egyórás regisztrációs sort.

1. Kattintson az **Eszközkezelés** > **Közös** > **Munkarendelések** > **Összes munkarendelés** vagy **Aktív munkarendelések** elemre.

2. Válassza ki a munkarendelést, majd kattintson a **Naplók** elemre.

3. Válassza ki a megosztani kívánt óraregisztrációs sort, majd kattintson az **Órák megosztása** elemre.

4. A **Munkarendelés karbantartási feladataihoz tartozó megosztott órák** párbeszédpanelen a bejelentkezett dolgozó neve automatikusan megjelenik a **Dolgozó** mezőben. Szükség esetén másik dolgozót is kiválaszthat.

5. Válasszon ki egy kategóriát az óraregisztrációhoz a **Kategória** mezőben.

6. Írja be a megosztandó munkaórák számát  az **Órák** mezőbe.

    ![2. ábra](media/02-consumption.png)

7. Kattintson az **OK** gombra.

*Példa:* az alábbi képernyőképen három munkarendelési feladatot tartalmazó munkarendeléshez tartozó naplósorok láthatók. A három munkaórát tartalmazó első sor már fel van osztva, és minden munkarendelésnél egy munkaóra van regisztrálva. Miután létrehozta a három órás regisztrációs sort, eldöntheti, mi legyen az eredeti óraregisztrációs sorral (a példa első sorával). Megtarthatja, de akár törölheti is. 

![3. ábra](media/03-consumption.png)

## <a name="financial-dimensions-on-consumption-registrations"></a>Felhasználási regisztrációk pénzügyi dimenziói

Felhasználási regisztrációk végrehajtásakor a rendszer egy megadott sorrendben hozzáadja a regisztrációkhoz a különböző regisztrációtípusokhoz kapcsolódó pénzügyi dimenziókat. 

- *Óra- és kiadásregisztrációk:* először a napló fejlécében szereplő pénzügyi dimenziókat adja hozzá a program, ha vannak ilyen dimenziók. Következő lépésként a kapcsolódó munkarendelés-projekt pénzügyi dimenzióinak felvételére kerül sor. Végezetül az erőforrás (dolgozó) pénzügyi dimenzióit adja hozzá a program.

- *Cikkregisztrációk:* először a napló fejlécében szereplő pénzügyi dimenziókat adja hozzá a program, ha vannak ilyen dimenziók. Majd a kapcsolódó munkarendelés-projekt pénzügyi dimenzióinak felvételére kerül sor. A következő lépés a hely pénzügyi dimenzióinak felvétele. Végezetül a cikk pénzügyi dimenzióit adja hozzá a program.

>[!NOTE]
>A program mindhárom regisztrációtípusnál ellenőrzi a pénzügyi dimenzió kombinációját, és az érvénytelen kombinációkat üresen hagyja. Ez a szokásos beállítás más Finance and Operations alkalmazások esetében.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]