---
title: Toborzási kérelem állapota
description: Ez a témakör a Toborzási kérelem állapota beállításkészletet írja le a Dynamics 365 Human Resources rendszerhez.
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
ms.openlocfilehash: 55ed9c391a1b5f86c3c443b9fceeee5c2301444d
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125954"
---
# <a name="recruiting-request-status"></a>Toborzási kérelem állapota

Ez a témakör a Toborzási kérelem állapota beállításkészletet írja le a Dynamics 365 Human Resources rendszerhez.

Fizikai név: mshr_hcmrecruitingrequeststatus

Ez a felsorolás a toborzási kérelem állapotértékeinek beállításkészletét adja meg.

| Érték | Címke | Leírás |
| --- | --- | --- |
| 200000000 | Piszkozat | A kérelem piszkozatban van, és nem áll készen az aktív toborzásra. |
| 200000001 | Ellenőrzés alatt | A kérelmet elküldték, most pedig a munkafolyamat jóváhagyására vár. Csak akkor érhető el, ha a munkafolyamat engedélyezve van. |
| 200000002 | Függőben | A kérelem munkafolyamat-műveletre vár. Csak akkor érhető el, ha a munkafolyamat engedélyezve van. |
| 200000003 | Érvénytelenítve | A kérés törlésre került. Csak akkor érhető el, ha a munkafolyamat engedélyezve van. |
| 200000004 | Megtagadva | A kérelmet megtagadták. Csak akkor érhető el, ha a munkafolyamat engedélyezve van. |
| 200000005 | Aktív | Minden munkafolyamatot befejeztek és jóváhagytak, és a kérelem készen áll az aktív toborzásra. |
| 200000006 | Lezárva | A toborzási kérelmet lezárták. |

## <a name="see-also"></a>Lásd még

[Pályázó követésrendszer integrációs API bevezetése](hr-admin-integration-ats-api-introduction.md)<br>
[Példa lekérdezésre Toborzási kérelemmel kapcsolatban](hr-admin-integration-ats-api-recruiting-request-example-query.md)
