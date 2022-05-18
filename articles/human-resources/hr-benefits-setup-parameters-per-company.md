---
title: Juttatáskezelési paraméterek konfigurálása vállalatonként
description: Ez a témakör a Microsoft Dynamics 365 Human Resources rendszerben a Juttatások kezelése paramétereinek vállalatonkénti konfigurálását ismerteti.
author: twheeloc
ms.date: 8/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3c5e53d3dec4c6fc8be573b8a1ad3ba8fb01b490
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/04/2022
ms.locfileid: "8689944"
---
# <a name="configure-benefits-management-parameters-per-company"></a>Juttatáskezelési paraméterek konfigurálása vállalatonként


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Minden olyan szervezetnek, amely juttatásokat kínál, konfigurálnia kell a beállításokat az juttatásokat visszaigazoló e-mailekhez.

## <a name="configure-confirmation-email-settings"></a>Megerősítő e-mail-beállítások megadása

1. A **Juttatások kezelése** munkaterület **Beállítás** részén válassza az **Emberi erőforrások paraméterei** elemet.

2. A **Juttatások kezelése** lapon adja meg a megfelelő értékeket az alábbi mezőkben: 

   | Mező | Leírás |
   | --- | --- |
   | **Visszaigazoló e-mail küldése** | Ha ez a funkció be van kapcsolva, a munkavállalóknak visszaigazoló e-mailt küldünk, amikor kijelentkeznek az **alkalmazottak önkiszolgáló szolgáltatásában** a juttatások igénybevételével kapcsolatos tapasztalatokról. |
   | **Visszaigazoló e-mail-sablon** | Válassza ki a regisztrációs visszaigazolás elküldésekor használandó szervezeti e-mail-sablont. Ha nem választ sablont, a rendszer a következő általános e-mailt küldi el:<br><br>%EmployeeFirstName%,<br><br>Gratulálunk! Sikeresen végrehajtotta a juttatási regisztrációt.<br><br>Köszönettel:<br><Company/Org name> juttatások. |
   | **Alapértelmezett feladói e-mail-cím** | A visszaigazoló e-mail küldésekor használandó e-mail cím. |

3. Válassza a **Mentés** lehetőséget.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
