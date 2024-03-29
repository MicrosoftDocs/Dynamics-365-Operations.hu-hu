---
title: MyLeaveRequests áttekintése
description: A Microsoft SajátLeaveRequests entitása Dynamics 365 Human Resources tartalmazza a Szabadságigénylések listáját.
author: twheeloc
ms.date: 02/03/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 20cc53ec3bcf38444ccf75f81e28d5efd9fc4537
ms.sourcegitcommit: 1d2eeacad11c28889681504cdc509c90e3e8ea86
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/05/2022
ms.locfileid: "8717055"
---
# <a name="myleaverequests-overview"></a>MyLeaveRequests áttekintése


[!INCLUDE [PEAP](../includes/peap-1.md)]

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
