---
title: Távollét felfüggesztése
description: Az alkalmazott távollétét felfüggesztheti Dynamics 365 Human Resources.
author: twheeloc
ms.date: 11/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SuspendLeave, LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9c8262fb34175f6f9326d6be82c922b2170fc5a7
ms.sourcegitcommit: e88ecaccd82afa3a915e41df1d4287d99da6a48a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/29/2022
ms.locfileid: "9805260"
---
# <a name="suspend-leave"></a>Szabadság felfüggesztése

>[!Important]
>Az ebben a cikkben említett funkciók jelenleg csak a különálló Dynamics 365 Human Resources rendszerében lévő vevőknek érhetők el. A funkciók egy része vagy egésze a Finance infrastruktúra jövőbeni kiadásának részeként lesz elérhető a Finance 10.0.26-ös kiadása után.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Az alkalmazott távollétét felfüggesztheti, hogy a program ne tudja feldolgozni a szabadságtípusokat.

## <a name="suspend-leave-and-absence-for-an-employee"></a>Egy alkalmazott szabadságának és távollétének felfüggesztése

1. Az alkalmazott rekordján válassza a **Szabadság** elemet.

2. Válassza a **Szabadság felfüggesztése** lehetőséget.

3. Válassza az **Új** lehetőséget.

4. A **Szabadság-elhatárolás felfüggesztése** párbeszédpanelen válassza ki a **Szabadság típust** a felfüggesztés **Kezdő dátuma** és **Záró dátuma** értékekkel együtt.

5. Lehetőség van arra is, hogy **Megjegyzést** fűzzön a felfüggesztéshez. 

Ha az elhatárolások feldolgozása az alkalmazott szabadságának felfüggesztése során történik, akkor a felfüggesztett szabadság típusokra nem készül elhatárolás.

> [!NOTE]
> A távolléti kérelmek felfüggesztik az idő-távolléti kérelmeket, de a távolléti kérelmeket nem.

## <a name="see-also"></a>Lásd még

- [Szabadság és távollét áttekintése](hr-leave-and-absence-overview.md)
- [Szabadság- és távolléttípusok konfigurálása](hr-leave-and-absence-types.md)
- [Szabadság- és távolléti tervek elhatárolása](hr-leave-and-absence-accrue.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
