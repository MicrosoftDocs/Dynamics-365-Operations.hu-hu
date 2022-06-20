---
title: Munka mentességi állapota
description: Ez a témakör a feladatmentességi állapot beállításának beállítását ismerteti Dynamics 365 Human Resources.
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
ms.openlocfilehash: e59a71264d50cecce4d31dfa26ad7f05ef3f34e4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8894672"
---
# <a name="job-exempt-status"></a>Munka mentességi állapota


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör a feladatmentességi állapot beállításának beállítását ismerteti Dynamics 365 Human Resources.

Fizikai név: cdm_jobexemptstatus

Ez a felsorolás bemutatja az FLSA munka mentességi állapotértékei beállításkészletet. Ez a meglévő cdm_jobexemptstatus beállításkészletben található.

| Érték | Címke | Leírás |
| --- | --- | --- |
| 200000000 | Mentes | A feladat mentességi állapottal rendelkezik az FLSA-irányelvek alapján. |
| 200000001 | NonExempt | A feladat nem rendelkezik mentességi állapottal rendelkezik az FLSA-irányelvek alapján. |
| 200000002 | Nem érvényes rá | Az FLSA állapot-irányelvek nem vonatkoznak a feladatra. |

## <a name="see-also"></a>Lásd még

[Pályázó követésrendszer integrációs API bevezetése](hr-admin-integration-ats-api-introduction.md)<br>
[Példa lekérdezésre Toborzási kérelemmel kapcsolatban](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
