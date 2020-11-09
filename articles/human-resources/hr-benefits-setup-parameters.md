---
title: A juttatáskezelés paramétereinek beállítása
description: A Juttatáskezelés paramétereinek konfigurálása a Microsoft Dynamics 365 Human Resources alkalmazásban.
author: andreabichsel
manager: tfehr
ms.date: 07/16/2020
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
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: cb9dd6eb8ef840dab54eabab8526200a3a8e21f0
ms.sourcegitcommit: e100c1c7c8dcdacf066defc206dd2f44b8ce6100
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/20/2020
ms.locfileid: "4057028"
---
# <a name="set-benefits-management-parameters"></a>Juttatáskezelés paramétereinek beállítása

Mielőtt beállítaná a szabadságterveket a Microsoft Dynamics 365 Human Resources alkalmazásban, konfigurálnia kell a Juttatáskezelés paramétereit. Ezek a paraméterek az alapértelmezett értékeket, okkódokat és egyéb beállításokat határozzák meg.

## <a name="configure-general-parameters"></a>Általános paraméterek konfigurálása

1. A **Juttatások kezelése** munkaterület **Beállítás** részén válassza az **Emberi erőforrások megosztott paraméterei** elemet.

2. Az **Általános** lapon adja meg a megfelelő értékeket a következő mezőkben:

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
   | **Új dolgozó regisztrációs időszaka** | Az az időszak, amikor az új dolgozói regisztráció engedélyezve van.</br></br>**Megjegyzés** : Ez a beállítás felülbírál minden új dolgozói regisztrációs időszakot, amelyet a konstrukció jogosultsági szabályai között beállított. |
   | **Alapértelmezett fizetési gyakoriság** | Az új dolgozók hozzáadásakor használt alapértelmezett fizetési gyakoriság. |
   | **Életesemények engedélyezve** | Élettartam-események engedélyezése. |
   | **Korábbi juttatási űrlapok elrejtése** | Lehetővé teszi a korábbi juttatási űrlapok elrejtését. |

3. Válassza a **Mentés** lehetőséget.

## <a name="configure-employee-self-service-parameters"></a>Alkalmazotti önkiszolgáló rendszer paramétereinek konfigurálása

1. A **Juttatások kezelése** munkaterület **Beállítás** részén válassza az **Emberi erőforrások paraméterei** elemet.

2. A **Juttatások kezelése** lapon adja meg a megfelelő értékeket az alábbi mezőkben:

   | Mező | Leírás |
   | --- | --- |
   | **Juttatás ellenőrzése** | Az önkiszolgáló juttatásfizetés során használandó ellenőrzési szöveg. |
   | **Kijelölt személyek automatikus kiválasztása** | Megadja, hogy a program automatikusan kiválassza-e a függő feleket és a kedvezményezetteket a konstrukció opcióira való jogosultságuk alapján. |

3. Válassza a **Mentés** lehetőséget.
