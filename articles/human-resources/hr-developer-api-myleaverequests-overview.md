---
title: MyLeaveRequests áttekintése
description: A Microsoft Dynamics 365 Human Resources MyLeaveRequests entitása biztosítja a Szabadságkérelmek listáját a rendszerben, amely az entitást lekérdező felhasználó számára elérhető kérelmek körére korlátozódik.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f29d5cf1469b58b4ea1837dc82b9513f5c002609
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054956"
---
# <a name="myleaverequests-overview"></a>MyLeaveRequests áttekintése

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

A Microsoft Dynamics 365 Human Resources MyLeaveRequests entitása biztosítja a Szabadságkérelmek listáját a rendszerben, amely az entitást lekérdező felhasználó számára elérhető kérelmek körére korlátozódik.

## <a name="key"></a>Kulcs

  | Tulajdonság neve | Adattípus |
  |---------------|-----------|
  | dataAreaId    | Karakterlánc    |
  | RequestId     | Karakterlánc    |
  | LeaveType     | Karakterlánc    |
  | LeaveDate     | Dátum      |
  
## <a name="properties"></a>Tulajdonságok

  | Tulajdonság neve     | Adattípus | Kötelező |
  |-------------------|-----------|----------|
  | dataAreaId        | Karakterlánc    | X        |
  | RequestId         | Karakterlánc    | X        |
  | LeaveType         | Karakterlánc    | X        |
  | LeaveDate         | Dátum      | X        |
  | ReasonCodeId      | Karakterlánc    |          |
  | PersonnelNumber   | Karakterlánc    | X        |
  | RequestDate       | Dátum      | X        |
  | Megjegyzés           | Karakterlánc    |          |
  | Állapot            | Felsorolás      | X        |
  | Összeg            | Valós      |          |
  | HalfDayDefinition | Felsorolás      |          |

## <a name="actions"></a>Műveletek

 | Művelet neve                               | Leírás                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [küldés](hr-developer-api-myleaverequests-submit.md)   | A munkafolyamat által feldolgozandó kérelem elküldése. |

## <a name="see-also"></a>Lásd még

- [Szabadságkérelem elküldése munkafolyamathoz](hr-developer-api-myleaverequests-submit.md)
- [Hitelesítés](hr-developer-api-authentication.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]