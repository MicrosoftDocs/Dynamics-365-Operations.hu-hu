---
title: MyLeaveRequests áttekintése
description: A Microsoft Dynamics 365 Human Resources MyLeaveRequests entitása biztosítja a Szabadságkérelmek listáját a rendszerben, amely az entitást lekérdező felhasználó számára elérhető kérelmek körére korlátozódik.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0ca5bc225400338e76faee41a279e91fc00ce570
ms.sourcegitcommit: 18e626c49ccfdb12c1484b985e3a275e51f61320
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2021
ms.locfileid: "5115536"
---
# <a name="myleaverequests-overview"></a>MyLeaveRequests áttekintése

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