---
title: Toborzási kérelem – pozíció állapota
description: Ez a témakör a Toborzási kérelem – pozíció állapota beállításkészletet írja le a Dynamics 365 Human Resources rendszerhez.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e287ec4b9b78194b76ef3c993c6ce32f808e26f9
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6051881"
---
# <a name="recruiting-request-position-status"></a>Toborzási kérelem – pozíció állapota

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör a Toborzási kérelem – pozíció állapota beállításkészletet írja le a Dynamics 365 Human Resources rendszerhez.

Fizikai név: mshr_hcmrecruitingrequestpositionstatus

Ez a felsorolás biztosítja a beállításkészletet a RecruitingRequestPosition entitásnál toborzási kérelemként megadott beosztások állapotértékére.

| Érték | Címke | Leírás |
| --- | --- | --- |
| 200000000 | Megnyitva | A toborzási kérelemben lévő beosztás meg van nyitva toborzásra. Ez nem azt jelzi, hogy jelenleg nincs aktív beosztás-hozzárendelés a beosztásra vonatkozóan. Megtörténhet, hogy a toborzás ideje alatt a beosztásban egy alkalmazott dolgozik. Kizárólag azt jelzi, hogy a beosztás toborzásra elérhető a toborzási kérelem keretében. |
| 200000001 | Betöltve | Egy dolgozót kiválasztottak a beosztáshoz való hozzárendelésre. |
| 200000002 | Érvénytelenítve | A beosztás toborzási kérelmét visszavonták. |

## <a name="see-also"></a>Lásd még

[Pályázó követésrendszer integrációs API bevezetése](hr-admin-integration-ats-api-introduction.md)<br>
[Példa lekérdezésre Toborzási kérelemmel kapcsolatban](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]