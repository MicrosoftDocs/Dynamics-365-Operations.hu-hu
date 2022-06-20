---
title: Végrehajtás állapota
description: Ez a témakör a befejezési állapot beállításának beállítását írja le Dynamics 365 Human Resources.
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
ms.openlocfilehash: 32575dfdd9bcd61b8a16bb544a9e7906ec96eaa1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8880567"
---
# <a name="completion-status"></a>Végrehajtás állapota


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör a befejezési állapot beállításának beállítását írja le Dynamics 365 Human Resources.

Fizikai név: mshr_hcmcompletionstatus

Ez a felsorolás a jelöltek szűréséhez kapcsolódó állapotértékek beállításkészletét adja meg. 

| Érték | Címke | Leírás |
| --- | --- | --- |
| 200000000 | Nincs kész | A jelölt esetében még nem fejeződött be a szűrés. |
| 200000001 | Megfelelt | A jelölt átment a szűrésen. |
| 200000002 | Sikertelen | A jelölt nem ment át a szűrésen. |

## <a name="see-also"></a>Lásd még

[Pályázó követésrendszer integrációs API bevezetése](hr-admin-integration-ats-api-introduction.md)<br>
[Példa lekérdezésre a Felvenni kívánt jelölt esetében](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
