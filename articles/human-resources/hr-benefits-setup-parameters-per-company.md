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
ms.openlocfilehash: 2f3f8625a8ebbe6812d2f051649ff2a608ed4b54
ms.sourcegitcommit: 66d129874635d34a8b29c57762ecf1564e4dc233
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/23/2022
ms.locfileid: "9323898"
---
# <a name="configure-benefits-management-parameters-per-company"></a>Juttatáskezelési paraméterek konfigurálása vállalatonként


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
