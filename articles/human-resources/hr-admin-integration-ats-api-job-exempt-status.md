---
title: Munka mentességi állapota
description: Ez a témakör bemutatja Munka mentességi állapota beállításkészletet a Dynamics 365 Human Resources rendszerben.
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
ms.openlocfilehash: 1f211002468384227acb2343ed6cbc6ae2a215d1
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/17/2021
ms.locfileid: "5464452"
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