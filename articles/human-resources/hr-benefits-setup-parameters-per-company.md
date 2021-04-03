---
title: Juttatáskezelési paraméterek konfigurálása vállalatonként
description: A Juttatáskezelés paramétereinek konfigurálása vállalatonként a Microsoft Dynamics 365 Human Resources alkalmazásban.
author: andreabichsel
manager: tfehr
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 31f30c3d268132327074e931b714b5b2ee3ec5ac
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/17/2021
ms.locfileid: "5466640"
---
# <a name="configure-benefits-management-parameters-per-company"></a>Juttatáskezelési paraméterek konfigurálása vállalatonként

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Minden olyan szervezetnek, amely juttatásokat kínál, konfigurálnia kell a beállításokat az juttatásokat visszaigazoló e-mailekhez.

## <a name="configure-confirmation-email-settings"></a>Megerősítő e-mail-beállítások megadása

1. A **Juttatások kezelése** munkaterület **Beállítás** részén válassza az **Emberi erőforrások paraméterei** elemet.

2. A **Juttatások kezelése** lapon adja meg a megfelelő értékeket az alábbi mezőkben: 

   | Mező | Leírás |
   | --- | --- |
   | **Visszaigazoló e-mail küldése** | Ha ez a funkció be van kapcsolva, a rendszer visszaigazoló e-mailt küld az alkalmazottaknak, amikor kijelentkeznek a juttatások regisztrációs szolgáltatásából a Munkavállalói önkiszolgáló rendszerben. |
   | **Visszaigazoló e-mail-sablon** | Válassza ki a regisztrációs visszaigazolás elküldésekor használandó szervezeti e-mail-sablont. Ha nem választ sablont, a rendszer a következő általános e-mailt küldi el:<br><br>%EmployeeFirstName%,<br><br>Gratulálunk! Sikeresen végrehajtotta a juttatási regisztrációt.<br><br>Köszönettel:<br><Company/Org name> juttatások. |
   | **Alapértelmezett feladói e-mail-cím** | A visszaigazoló e-mail küldésekor használandó e-mail cím. |

3. Válassza a **Mentés** lehetőséget.

[!INCLUDE[footer-include](../includes/footer-banner.md)]