---
title: Végrehajtás állapota
description: Ez a témakör bemutatja a Végrehajtás állapota beállításkészletet a Dynamics 365 Human Resources rendszerben.
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
ms.openlocfilehash: 54ad5cc8f5f18d57b6713304cceb985acfdc93d1
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6055364"
---
# <a name="completion-status"></a>Végrehajtás állapota

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör bemutatja a Végrehajtás állapota beállításkészletet a Dynamics 365 Human Resources rendszerben.

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