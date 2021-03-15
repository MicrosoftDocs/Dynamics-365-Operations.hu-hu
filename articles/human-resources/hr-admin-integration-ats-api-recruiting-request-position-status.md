---
title: Toborzási kérelem – pozíció állapota
description: Ez a témakör a Toborzási kérelem – pozíció állapota beállításkészletet írja le a Dynamics 365 Human Resources rendszerhez.
author: jaredha
manager: tfehr
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3f7bae64f58f0bdc1603b3c1b5493f1ebcfa8de9
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/05/2021
ms.locfileid: "5126050"
---
# <a name="recruiting-request-position-status"></a>Toborzási kérelem – pozíció állapota

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