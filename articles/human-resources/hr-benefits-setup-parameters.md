---
title: Juttatáskezelési és alkalmazotti önkiszolgáló paraméterek beállítása minden vállalatnál
description: Juttatáskezelési és alkalmazotti önkiszolgáló paraméterek konfigurálása a Microsoft Dynamics 365 Human Resources alkalmazásban.
author: andreabichsel
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d668238378e41287c7a9f845ae3e67078fc7776a
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6058968"
---
# <a name="set-benefits-management-and-employee-self-service-parameters-for-all-companies"></a>Juttatáskezelési és alkalmazotti önkiszolgáló paraméterek beállítása minden vállalatnál

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Mielőtt beállítaná a juttatásterveket a Microsoft Dynamics 365 Human Resources alkalmazásban, konfigurálnia kell a Juttatáskezelés paramétereit. Ezek a paraméterek az alapértelmezett értékeket, okkódokat és egyéb beállításokat határozzák meg. 

## <a name="configure-general-parameters"></a>Általános paraméterek konfigurálása

1. A **Juttatások kezelése** munkaterület **Beállítás** részén válassza az **Emberi erőforrások megosztott paraméterei** elemet.

2. A **Juttatások kezelése** lapon adja meg a megfelelő értékeket az alábbi mezőkben:

   | Mező | Leírás |
   | --- | --- |
   | **Ország/régió** | Az **Ország/régió** mező határozza meg az irányítószámok/államok megjelenítési sorrendjét. A kiválasztott ország/régió jelenik meg elsőként a legördülő listában. |
   | **Regisztráció okkódja** | Válasszon ki egy alapértelmezett okkódot, amely az alkalmazotti tervek létrehozásakor kerül felhasználásra a nyitott regisztrációs feldolgozás során. |
   | **Megszakítás okkódja** | Az alkalmazotti juttatási konstrukció érvénytelenítése során használandó okkód. Egy párbeszédablakban jelenik meg az érvénytelenítési folyamat során. Ha szükséges, a felhasználók módosthatják az **Érvénytelenítési okkód** részben. |
   | **Újranyitás okkódja** | Az alkalmazotti juttatási konstrukció újranyitása során használandó okkód. Egy párbeszédablakban jelenik meg az érvénytelenítési folyamat során. Ha szükséges, a felhasználók módosthatják az **Újranyitási okkód** részben. | 
   | **Életesemény okkódja** | A élettartam-esemény bekövetkezésekor használandó okkód. |
   | **Díjváltozás okkódja** | Az alkalmazotti juttatási konstrukciónak az árfolyam-módosítási frissítési folyamat során történő érvénytelenítése és újbóli megnyitása alkalmával használandó okkód. Azt jelzi, hogy az árfolyam-módosítási frissítési folyamat mely rekordokat módosította. |
   | **Juttatások éves fizetése** | Lehetővé teszi az alkalmazottakra vonatkozó **Juttatások évi fizetési** összegének beállítását. Az emberi erőforrások a fix kompenzációs éves összeg helyett a fedezeti összegek meghatározásakor a **Juttatások évi fizetésének** összegét fogják használni. |
   | **Új dolgozó jogosult** | Megadja, hogy az új dolgozók jogosultak-e. |
   | **Új dolgozó regisztrációs időszaka** | Az az időszak, amikor az új dolgozói regisztráció engedélyezve van.</br></br>**Megjegyzés**: Ez a beállítás felülbírál minden új dolgozói regisztrációs időszakot, amelyet a konstrukció jogosultsági szabályai között beállított. |
   | **Alapértelmezett fizetési gyakoriság** | Az új dolgozók hozzáadásakor használt alapértelmezett fizetési gyakoriság. |
   | **Életesemények engedélyezve** | Élettartam-események engedélyezése. |
   | **Korábbi juttatási űrlapok elrejtése** | Lehetővé teszi a korábbi juttatási űrlapok elrejtését. |
   | **Juttatás ellenőrzése** | Az önkiszolgáló juttatásfizetés során használandó ellenőrzési szöveg. |
   | **Kijelölt személyek automatikus kiválasztása** | Megadja, hogy a program automatikusan kiválassza-e a függő feleket és a kedvezményezetteket a konstrukció opcióira való jogosultságuk alapján. |

3. Válassza a **Mentés** lehetőséget.

## <a name="configure-employee-self-service-parameters"></a>Alkalmazotti önkiszolgáló rendszer paramétereinek konfigurálása

1. A **Juttatások kezelése** munkaterület **Beállítás** részén válassza az **Emberi erőforrások paraméterei** elemet.

2. A **Juttatások kezelése** lapon adja meg a megfelelő értékeket az alábbi mezőkben:

   | Mező | Leírás |
   | --- | --- |
   | **Juttatás ellenőrzése** | Az önkiszolgáló juttatásfizetés során használandó ellenőrzési szöveg. |
   | **Kijelölt személyek automatikus kiválasztása** | Megadja, hogy a program automatikusan kiválassza-e a függő feleket és a kedvezményezetteket a konstrukció opcióira való jogosultságuk alapján. |

3. Válassza a **Mentés** lehetőséget.




[!INCLUDE[footer-include](../includes/footer-banner.md)]