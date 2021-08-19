---
title: Juttatáskezelési munkaterület
description: Ez a témakör a Dynamics 365 Human Resources Juttatáskezelési munkaterületét részletezi.
author: andreabichsel
ms.date: 02/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-24
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 49393ab65c2f0020af5b246f7c18a152d613725f5b31be89cb57f244b28003f3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6719092"
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

## <a name="processing"></a>Feldolgozás folyamatban

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

Ha egy másik juttatási időszakot is meg kell tekinteni, válassza ki az **Időszak** legördülő menüből.

![Időszak módosítása.](./media/hr-benefits-management-workspace-period.png)

## <a name="view-more-options"></a>További beállítások megtekintése

További adatok és műveletek megtekintéséhez válassza a **Hivatkozások** lehetőséget.

![Hivatkozások.](./media/hr-benefits-management-workspace-links.png)

## <a name="see-also"></a>Lásd még

[Juttatáskezelés áttekintése](hr-benefits-management-overview.md)