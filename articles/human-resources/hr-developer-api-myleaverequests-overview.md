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
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: fefa436142fb99ed3bfb3d4454046a5d76619daecbf6f05100e8e405fca67d48
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6732105"
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