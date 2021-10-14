---
title: Juttatáskezelési munkaterület
description: Ez a témakör a Dynamics 365 Human Resources Juttatáskezelési munkaterületét részletezi.
author: twheeloc
ms.date: 09/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-24
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e6cc1432e108c74706dea124a62024272e65b6c1
ms.sourcegitcommit: 47a3ad71210c7ac84d0c25e913c440b5ba205282
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/23/2021
ms.locfileid: "7512474"
---
# <a name="benefits-management-workspace"></a>Juttatáskezelési munkaterület

[!include [applies to](../includes/applies-to-hr.md)]

[!include [preview feature](./includes/preview-feature.md)]

Ez a témakör a Dynamics 365 Human Resources **Juttatáskezelési munkaterületét** részletezi.

> [!NOTE]
> A **Juttatáskezelés** munkaterület megtekintéséhez először engedélyeznie kell a Funkciókezelés **(Előzetes verzió) Juttatáskezelési munkaterület** funkcióját. Az előzetes funkciók aktiválásával kapcsolatos további részletekért tekintse meg a [Szolgáltatások kezelése](hr-admin-manage-features.md) oldalt.<br><br>![Juttatáskezelési munkaterület engedélyezése.](./media/hr-benefits-management-workspace-enable.png)

A **Juttatáskezelés** munkaterület használatával gyorsan megtekinthetők azok a juttatások, amelyekre figyelni kell. Ezen az oldalon a következők láthatók:

- Műveletre váró cikkek összegei
- Nem megerősített kijelölésű dolgozók
- Juttatásokra nemrég regisztrált dolgozók
- Dolgozók jövőbeli életeseményekkel
- Nem regisztrált új felvételek
- Dolgozók aktív életeseményekkel
- Azok a dolgozók, akiknek nyitott regisztrációjuk van, és egyetlen konstrukciót sem választottak

![Juttatáskezelési munkaterület.](./media/hr-benefits-management-workspace.png)

## <a name="view-action-items"></a>Műveletelemek megtekintése

A művelet elemeit csempe vagy lap kiválasztásával lehet megtekinteni. Ha kiválaszt egy lapot, a munkaterületi oldalon megtekintheti és kiválaszthatja a dolgozókat.

![Műveletelemek.](./media/hr-benefits-management-workspace-action-items.png)

Ha egy csempét választ ki, akkor az arra a területre vonatkozó oldalra lép. Például ezen csempék valamelyikének kiválasztása a **Dolgozói juttatási konstrukció** oldalt jeleníti mega, azokra az alkalmazottakra szűrve, akik esetében műveletet kell végeznie:

- **Meg nem erősített kiválasztások**
- **Nyitott beléptetések kivett konstrukciók nélkül**
- **Juttatáshoz beléptetve**
- **Az újonnan felvett dolgozó nincs beléptetve**

![Dolgozói juttatási konstrukciók.](./media/hr-benefits-management-workspace-plans.png)

Az **Aktív életesemények** és a **Jövőbeli életesemények** kiválasztása az aktív vagy jövőbeli életesemények listájára viszi.

![Életesemények.](./media/hr-benefits-management-workspace-life-events.png)

## <a name="processing"></a>Feldolgozás

A felvételi jogosultságok, az életesemények és a díjváltozások frissítéseinek feldolgozásához jelölje ki a megfelelő elemet a navigációs sávon.

![Feldolgozás folyamatban.](./media/hr-benefits-management-workspace-processing.png)

A folyamat eredményeinek megtekintéséhez válassza a **Folyamateredmények** lehetőséget az oldalon.

![Folyamateredmények.](./media/hr-benefits-management-workspace-process-results.png)

A juttatások feldolgozásával kapcsolatos további információkért lásd:

- [Felvételi jogosultság feldolgozása](hr-benefits-process-enrollment-eligibility.md)
- [Életesemények változásainak feldolgozása](hr-benefits-process-life-event-changes.md)
- [Életesemény-jogosultság feldolgozása](hr-benefits-process-life-event-eligibility.md)
- [Életesemények feldolgozása](hr-benefits-process-life-events.md)
- [Módosítások arányának feldolgozása](hr-benefits-process-rate-changes.md)

## <a name="change-period"></a>Időszak módosítása

Ha egy másik juttatási időszakot is meg kell tekinteni, válassza ki az **Időszak** legördülő listából.

![Időszak módosítása.](./media/hr-benefits-management-workspace-period.png)


## <a name="open-enrollment-tab"></a>Beléptetés megnyitása lap

A művelet elemeit csempe vagy lap kiválasztásával lehet megtekinteni. Ha kiválaszt egy lapot, a munkaterületi oldalon megtekintheti és kiválaszthatja a dolgozókat.
A **Nyitott belépés** lap fontos mérőszámokat biztosít a nyitott beléptetési folyamathoz. 

A nyitott tagságra vonatkozó adatok a **Beléptetés kezdő dátuma** előtt 30 nappal lesznek látható. Ez az **Időszakok** beállításban van meghatározva a **Juttatáskezelés** > **Hivatkozások** > **Időszakok** menüben a **Beléptetés kezdődátuma** mezőben.  Ennek a beállításnak a módosításához ugorjon a **Human Resource megosztott paraméterei** > **Juttatások kezelése** > **Nyitott tagsági beállítások** helyre, és frissítse a **Száma** mezőt.  

A Következő információk érhetők el a **Beléptetés megnyitása** lapon:
 - Azok az alkalmazottak, akik még nem indították el a beléptetés megnyitása folyamatot
 - Azok az alkalmazottak, akik kiválasztása folyamatban van
 - Azok az alkalmazottak, akik elvégezték a kiválasztási folyamatot
 - Meg nem erősített kiválasztások

**Összesítő csempék**

- **El nem kezdett** – Az **El nem kezdett** csempe mutatja azon alkalmazottak számát, akik még nem kezdték el a beléptetési folyamatot. Az **El nem kezdett** csempe egy szűrt lista, amely csak azokat az alkalmazottakat jeleníti meg, akiknek nincs kijelölt, lemondott vagy kivett tervük a nyitott beléptetési terv időszakához. A kötelező tervek figyelmen kívül vannak hagyva, és nem szerepelnek ebben, mert alapértelmezés szerint ki vannak választva az alkalmazotthoz.  Ezen a csempén leásva, láthatja azon alkalmazottak listáját, akik még nem kezdték el a nyitott beléptetési folyamatot a **Dolgozói juttatási konstrukció** oldalon.

  > [!NOTE]
  > Ha nem szeretné nyomon követni egy **Tervtípus** nyitott beléptetésének előrehaladását, akkor kizárhatja azt a következő helyen: **Juttatáskezelés** > **Hivatkozások** > **Munkavállalói önkiszolgáló rendszer paraméterei** > **Juttatási konstrukciók csempéjének beállítása**, itt frissítheti a **Nyitott beléptetések nyomon követése** mezőt.  Létrehozhat például olyan konstrukciókat, amelyeknél a **Konstrukció típusa** = **Egyéb**. Ezek a konstrukciók választható konstrukciók lehetnek, amelyekhez nem szeretné nyomon követni a beléptetés előrehaladását. Ha nem ezt a konstrukciótípust választja, akkor a rendszer figyelmen kívül hagyja az ilyen típusú konstrukciókat, amikor nyomon követi a beléptetés előrehaladását vagy a befejezését a **Nyitott beléptetés** lapon. Ez a beállítás az összes időszakra és jogi személyre vonatkozóan kiválasztott tervtípusra vonatkozik.

- **Folyamatban** – a **Folyamatban** csempe a folyamatban lévő kiválasztással rendelkező alkalmazottak számát adja meg. A **Folyamatban** csempe egy szűrt lista, amely csak azokat az alkalmazottakat jeleníti meg, akiknél legalább egy terv le van mondva, vagy ki van választva. A kötelező tervek figyelmen kívül vannak hagyva, és nem szerepelnek ebben, mert alapértelmezés szerint ki vannak választva az alkalmazotthoz. Ebben a csempében lehet visszaásni a kiválasztott és a lemondott tervekhez a **Dolgozói juttatási konstrukciók tömeges frissítése** lapon.

- **Juttatásokra regisztrált** – A **Juttatásokra regisztrált** csempe segítségével meg lehet számolni az olyan alkalmazottakat, akik teljesen regisztráltak juttatásra. A **Juttatásra regisztrált** csempe egy szűrt lista, amely azokat az alkalmazottakat jeleníti meg, akik vagy az összes konstrukciót kiválasztották vagy lemondták. A lekérdezés kizárja azokat a konstrukciókat, amelyekhez nincs nyomon követve a nyitott beléptetés az **Alkalmazott önkiszolgálás** paraméterei oldalon. Erről a csempéről visszaáshat, hogy láthassa az alkalmazottak listáját a **Dolgozói juttatási konstrukciók** oldalon.

- **Nem megerősített kiválasztások** – a **Nem megerősített kiválasztások** csempe mutatja azon alkalmazottak számát, akikhez kiválasztott vagy lemondott tervek vannak amelyek megerősítése szükséges. Erről a csempéről visszaáshat, hogy láthassa az alkalmazottak listáját a **Dolgozói juttatási konstrukciók tömeges frissítése** oldalon.

**Tevékenység**

- **El nem kezdett** – Az **El nem kezdett** lap mutatja azon alkalmazottak listáját, akik még nem kezdték el a beléptetési folyamatot. Az **El nem kezdett** csempe egy szűrt lista, amely azokat az alkalmazottakat jeleníti meg, akiknek nincs kijelölt, lemondott vagy kivett tervük a nyitott beléptetési terv időszakához. A kötelező tervek figyelmen kívül vannak hagyva, és nem szerepelnek ebben, mert alapértelmezés szerint ki vannak választva az alkalmazotthoz. A dolgozón leáshat, és a **Dolgozói juttatási konstrukciók részletei** lap jelenik meg.

- **Kiválasztások folyamatban** – a **Kiválasztások folyamatban** lap a folyamatban lévő kiválasztással rendelkező alkalmazottak számát adja meg. A **Folyamatban lévő kiválasztások** egy szűrt lista, amely csak azokat az alkalmazottakat jeleníti meg, akiknél legalább egy terv le van mondva, vagy ki van választva. A kötelező tervek figyelmen kívül vannak hagyva, és nem szerepelnek ebben, mert alapértelmezés szerint ki vannak választva az alkalmazotthoz. A dolgozón leáshat, és a **Dolgozói juttatási konstrukciók részletei** lap jelenik meg.

## <a name="view-more-options"></a>További beállítások megtekintése

További információk és további műveletek megtekintéséhez válassza a **Hivatkozások** lehetőséget.

![Hivatkozások.](./media/hr-benefits-management-workspace-links.png)

## <a name="see-also"></a>Lásd még

[Juttatáskezelés áttekintése](hr-benefits-management-overview.md)
