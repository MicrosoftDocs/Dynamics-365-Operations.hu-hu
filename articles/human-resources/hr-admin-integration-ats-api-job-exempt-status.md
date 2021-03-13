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
ms.openlocfilehash: 0cd6ffc01793c8ff12e36175c7c9feaf8a4b3cdf
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125569"
---
# <a name="job-exempt-status"></a>Munka mentességi állapota

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
