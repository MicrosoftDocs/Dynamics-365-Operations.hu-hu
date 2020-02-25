---
title: A juttatáskezelés paramétereinek beállítása
description: A Juttatáskezelés paramétereinek konfigurálása a Microsoft Dynamics 365 Human Resources alkalmazásban.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ab9b1fc78ce42479d9265b80337adf899cec3866
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009287"
---
# <a name="set-benefits-management-parameters"></a>A juttatáskezelés paramétereinek beállítása

[!include [banner](includes/preview-feature.md)]

Mielőtt beállítaná a szabadságterveket a Microsoft Dynamics 365 Human Resources alkalmazásban, konfigurálnia kell a Juttatáskezelés paramétereit. Ezek a paraméterek az alapértelmezett értékeket, okkódokat és egyéb beállításokat határozzák meg.

## <a name="configure-general-parameters"></a>Általános paraméterek konfigurálása

1. A **Juttatások kezelése** munkaterület **Beállítás** részén válassza a **Paraméterek** elemet.

2. Az **Általános** lapon adja meg a megfelelő értékeket a következő mezőkben:

   | Mező | Leírás |
   | --- | --- |
   | **Ország/régió** | Az **Ország/régió** mező határozza meg az irányítószámok/államok megjelenítési sorrendjét. A kiválasztott ország jelenik meg elsőként a legördülő listában. |
   | **Regisztráció okkódja** | Válasszon ki egy alapértelmezett okkódot, amely az alkalmazotti tervek létrehozásakor kerül felhasználásra a nyitott regisztrációs feldolgozás során. |
   | **Megszakítás okkódja** | Az alkalmazotti juttatási konstrukció érvénytelenítése során használandó okkód. Egy párbeszédablakban jelenik meg az érvénytelenítési folyamat során. Ha szükséges, a felhasználók módosthatják az **Érvénytelenítési okkód** részben. |
   | **Újranyitás okkódja** | Az alkalmazotti juttatási konstrukció újranyitása során használandó okkód. Egy párbeszédablakban jelenik meg az érvénytelenítési folyamat során. Ha szükséges, a felhasználók módosthatják az **Újranyitási okkód** részben. | 
   | **Életesemény okkódja** | A élettartam-esemény bekövetkezésekor használandó okkód. |
   | **Díjváltozás okkódja** | Az alkalmazotti juttatási konstrukciónak az árfolyam-módosítási frissítési folyamat során történő érvénytelenítése és újbóli megnyitása alkalmával használandó okkód. Azt jelzi, hogy az árfolyam-módosítási frissítési folyamat mely rekordokat módosította. |
   | **Új dolgozó jogosult** | Megadja, hogy az új dolgozók jogosultak-e. |
   | **Új dolgozó regisztrációs időszaka** | Az az időszak, amikor az új dolgozói regisztráció engedélyezve van.</br></br>**Megjegyzés**: Ez a beállítás felülbírál minden új dolgozói regisztrációs időszakot, amelyet a konstrukció jogosultsági szabályai között beállított. | 
   | **Éves fizetésbővítmény** | Megadja, hogy az **Évi juttatásfizetés** összege automatikusan kiszámításra kerüljön-e a **Dolgozói juttatás részletei** részben. Az alapja az alkalmazott **Fix kompenzációs díjalapja**, az **Átlagos munkaórák** és a **Fizetés gyakorisága**.</br></br>**Átlagos munkaórák** x **Fix fizetési díjalap** x **Fizetés gyakorisága** (a fizetési időszakok száma) = **Évi juttatásfizetés** </br></br>Ha az **Átlagos munkaórák**, a **Fix fizetési díjalap** vagy a **Fizetés gyakorisága** mező értéke megváltozik, a rendszer automatikusan újraszámítja az alkalmazott **Évi juttatásfizetés** összegét a módosított értékek alapján. A rendszer létrehoz egy **Érvényességi dátum** rekordot, amely a módosítás bekövetkezésének pontos dátumát és időpontját azonosítja. Szükség esetén az **Évi juttatásfizetés** összegét manuálisan is szerkesztheti. |
   | **Életesemények engedélyezve** | Élettartam-események engedélyezése. |
   | **Korábbi juttatási űrlapok elrejtése** | Lehetővé teszi a korábbi juttatási űrlapok elrejtését. |

3. Válassza a **Mentés** lehetőséget.

## <a name="configure-employee-self-service-parameters"></a>Alkalmazotti önkiszolgáló rendszer paramétereinek konfigurálása

1. A **Juttatások kezelése** munkaterület **Beállítás** részén válassza a **Paraméterek** elemet.

2. Az **Alkalmazotti önkiszolgáló rendszer** lapon adja meg a megfelelő értékeket a következő mezőkben:

   | Mező | Leírás |
   | --- | --- |
   | **Juttatás ellenőrzése** | Az önkiszolgáló juttatásfizetés során használandó ellenőrzési szöveg. |
   | **Kijelölt személyek automatikus kiválasztása** | Megadja, hogy a program automatikusan kiválassza-e a függő feleket és a kedvezményezetteket a konstrukció opcióira való jogosultságuk alapján. |

3. Válassza a **Mentés** lehetőséget.
