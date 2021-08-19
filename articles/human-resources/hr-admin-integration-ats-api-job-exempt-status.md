---
title: Munka mentességi állapota
description: Ez a témakör bemutatja Munka mentességi állapota beállításkészletet a Dynamics 365 Human Resources rendszerben.
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
ms.openlocfilehash: 1c3996d8f693b6df0bf6230b25c9339b2aad1ceaf49a790fda90bbfc1b68be41
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6720444"
---
# <a name="job-exempt-status"></a>Munka mentességi állapota

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör bemutatja Munka mentességi állapota beállításkészletet a Dynamics 365 Human Resources rendszerben.

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