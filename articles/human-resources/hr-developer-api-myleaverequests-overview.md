---
title: MyLeaveRequests áttekintése
description: A Microsoft Dynamics 365 Human Resources MyLeaveRequests entitása biztosítja a Szabadságkérelmek listáját a rendszerben, amely az entitást lekérdező felhasználó számára elérhető kérelmek körére korlátozódik.
author: andreabichsel
manager: AnnBe
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
ms.openlocfilehash: 4bf3b298af9eb39e03514a4005afb43a42908e47
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/28/2020
ms.locfileid: "3092037"
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