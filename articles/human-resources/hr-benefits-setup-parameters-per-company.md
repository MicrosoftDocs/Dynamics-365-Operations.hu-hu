---
title: Juttatáskezelési paraméterek konfigurálása vállalatonként
description: Ez a témakör azt mutatja be, hogyan kell konfigurálni a Juttatások kezelése vállalatonkénti paramétereit a Microsoftnál Dynamics 365 Human Resources.
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
ms.openlocfilehash: e9516977002280e17ee82bf7581d8d7c5060de2a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8904217"
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
