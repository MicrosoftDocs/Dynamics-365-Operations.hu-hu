---
title: Pályázó integrációs eredménye
description: Ez a témakör bemutatja a Pályázói integráció eredményének beállítását a Dynamics 365 Human Resources rendszerben.
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
ms.openlocfilehash: 3f173e15d5524dfd4d63113760760b2534cc8769456df621415a11e4053cc6fb
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6725914"
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