---
title: Pályázó integrációs eredménye
description: Ez a témakör bemutatja a Pályázói integráció eredményének beállítását a Dynamics 365 Human Resources rendszerben.
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
ms.openlocfilehash: dd25eca9cccf46ec4e4bb2a1d948ca98985e73e4
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/17/2021
ms.locfileid: "5467553"
---
# <a name="applicant-integration-result"></a>Pályázó integrációs eredménye

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör bemutatja a Pályázói integráció eredményének beállítását a Dynamics 365 Human Resources rendszerben.

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