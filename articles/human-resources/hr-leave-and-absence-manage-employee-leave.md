---
title: Alkalmazotti szabadság kezelése
description: Alkalmazotti szabadság kezelése a Dynamics 365 Human Resources alkalmazásban.
author: twheeloc
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-04-30
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e3c2ad8b25b337327823665dfbd551bbb5dbd959
ms.sourcegitcommit: 67c4ed957e43d4d60bb609d93921a0be9619e675
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2022
ms.locfileid: "8509528"
---
# <a name="manage-employee-leave"></a>Alkalmazotti szabadság kezelése

>[!Important]
>Az ebben a témakörben említett funkciók jelenleg csak a különálló Dynamics 365 Human Resources rendszerében lévő vevőknek érhetők el. A funkciók egy része vagy egésze a Finance infrastruktúra jövőbeni kiadásának részeként lesz elérhető a Finance 10.0.26-ös kiadása után.


[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Az alkalmazottak szabadságát szabadságtípusonként kezelheti. Ez magában foglalja a lejáró szabadság hozzárendelését és a szabadságtípus-egyenlegek helyesbítését. 

## <a name="adjust-leave-balances"></a>Szabadság-egyenlegek helyesbítése

1. Az alkalmazott rekordján válassza a **Szabadság** elemet.

2. Válassza a **Szabadság és távollét beállítása** lehetőséget.

3. Válassza az **Egyenleg helyesbítése** lehetőséget.

4. Válassza ki a **Szabadságtípust**.

5. Adjon meg egy **Kiigazítási összeget**. 

6. Opcionálisan kiválaszthat egy **Dátumot**. 

Az alkalmazott szabadságegyenlegének módosításakor az okkódok és a megjegyzések is megadhatók. 

Most, amikor bármely szabadságegyenleg fölé viszi az egérmutatót, a következő információk jelennek meg:

- **Elérhető** – az **Éves teljes érték** mínusz az **Ez évben kivett** érték.
- **Összesen ebben az évben** – Minden elhatárolás, kiigazítás és átvitel az évre.
- **Kivett ebben az évben** – Minden jóváhagyott távollét.

## <a name="see-also"></a>Lásd még

- [Szabadság és távollét áttekintése](hr-leave-and-absence-overview.md)
- [Szabadság- és távollétkérelmek kezelése](hr-employee-self-service-manage-requests.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
