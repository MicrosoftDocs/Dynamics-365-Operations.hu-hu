---
title: Pályázó integrációs eredménye
description: Ez a témakör a pályázói integráció eredményének beállítását írja le Dynamics 365 Human Resources.
author: jaredha
ms.date: 09/12/2022
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
ms.openlocfilehash: 86f3f75e538268644cea4f927f04c07aae115f00
ms.sourcegitcommit: 27ce4fc706100b626b81c3a1023238acd872e76c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/20/2022
ms.locfileid: "9702228"
---
# <a name="applicant-integration-result"></a>Pályázó integrációs eredménye


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör a pályázói integráció eredményének beállítását írja le Dynamics 365 Human Resources.

Fizikai név: mshr_hcmapplicantintegrationresult

Ez a felsorolás a jelöltrekord állapotát biztosítja.

| Érték | Címke | Leírás |
| --- | --- | --- |
| 200000000 | Nincs feldolgozva | A jelölt még mindig megfontolás alatt áll. |
| 200000001 | Felvéve | A jelöltet felvették. |
| 200000002 | Nincs felvéve | Úgy döntöttek, hogy nem veszik fel a jelöltet. |
| 200000003 | Elutasított | A jelöltet kivették a megfontolandók köréből. |

## <a name="see-also"></a>Lásd még

[Pályázó követésrendszer integrációs API bevezetése](hr-admin-integration-ats-api-introduction.md)<br>
[Példa lekérdezésre a Felvenni kívánt jelölt esetében](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
