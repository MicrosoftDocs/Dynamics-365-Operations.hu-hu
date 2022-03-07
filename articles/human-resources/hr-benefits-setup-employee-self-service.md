---
title: Alkalmazotti önkiszolgáló konfigurálása
description: A Microsoft Dynamics 365 Human Resources alkalmazásban lehetősége van csempéket konfigurálni az Alkalmazotti önkiszolgáló rendszer felső szintű navigációjához.
author: twheeloc
ms.date: 12/06/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 83718856a864123d7941b21c078bcdb96a62cca8
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8067579"
---
# <a name="configure-employee-self-service"></a>Alkalmazotti önkiszolgálás konfigurálása


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

A Microsoft Dynamics 365 Human Resources rendszerben a felső szintű navigációhoz csempéket konfigurálhat a **Munkavállalói önkiszolgálásban**. A juttatási terv csempék a felhasználókat olyan juttatási konstrukciókhoz irányítják, amelyekre jogosultak.

## <a name="set-up-a-benefit-plans-tile"></a>Juttatásikonstrukció-csempe beállítása

1. A **Juttatások kezelése** munkaterület **Beállítás** részén válassza az **Alkalmazotti önkiszolgáló rendszer paraméterei** elemet.

2. Válassza ki a **Juttatásikonstrukció-csempe beállítása** lapot, majd válassza az **Új** lehetőséget.

3. Adjon meg értékeket a következő mezőkben.

   | Mező | Leírás |
   | --- | --- |
   | **Konstrukció típuskódja** | A csempe kiválasztásakor megjelenő tervtípus **Önkiszolgálás előnyei**. |
   | **Csempe azonosítója** | A mozaik egyedi azonosítója. |
   | **CSempecímke felirata** | A szöveg, amely a csempéhez fog megjelenni **Önkiszolgálás előnyei**. |
   | **Leírás** | A csempe leírása. |
   | **Csempeháttérkép** | A csempéhez használandó kép URL-címe (nem kötelező). |
   | **Nyitott jelentkezés nyomon követése** | Válassza ezt a lehetőséget, ha nyomon szeretné követni az ehhez a tervtípushoz tartozó nyitott regisztráció előrehaladását. Előfordulhat például, hogy hol készített terveket **Terv típusa = Egyéb**. Ezek a konstrukciók választható konstrukciók lehetnek, amelyekhez nem szeretné nyomon követni a beléptetés előrehaladását. Ha nem választja ki ezt a tervtípust, a rendszer figyelmen kívül hagyja ezt a típusú csomagot a beiratkozás előrehaladásának vagy a regisztráció befejezésének nyomon követésekor.**Nyitott jelentkezés** lapon. Ez a beállítás az összes időszakra és jogi személyre kiválasztott tervtípusra vonatkozik. |

4. Válassza a **Mentés** lehetőséget.

## <a name="set-up-a-flex-credit-plan-tile"></a>Rugalmas hitelkonstrukció csempe beállítása

1. A **Juttatások kezelése** munkaterület **Beállítás** részén válassza az **Alkalmazotti önkiszolgáló rendszer paraméterei** elemet.

2. Válassza ki a **Rugalmas hitelkonstrukció csempe beállítása** lapot, majd válassza az **Új** lehetőséget.

3. Adjon meg értékeket a következő mezőkben.

   | Mező | Leírás |
   | --- | --- |
   | **Juttatás-jóváírás azonosítója** | A rugalmas beszámítási programtervek, amelyek akkor jelennek meg, ha ez a csempe ki van választva **Önkiszolgálás előnyei**. |
   | **Csempe azonosítója** | A mozaik egyedi azonosítója. |
   | **CSempecímke felirata** | A szöveg, amely a csempéhez fog megjelenni **Önkiszolgálás előnyei**. |
   | **Leírás** | A csempe leírása. |
   | **Csempeháttérkép** | A csempéhez használandó kép URL-címe (nem kötelező). |
   | **Nyitott jelentkezés nyomon követése** | Válassza ezt a lehetőséget, ha nyomon szeretné követni az ehhez a tervtípushoz tartozó nyitott regisztráció előrehaladását. Előfordulhat például, hogy hol készített terveket **Terv típusa = Egyéb**. Ezek a konstrukciók választható konstrukciók lehetnek, amelyekhez nem szeretné nyomon követni a beléptetés előrehaladását. Ha nem választja ki ezt a tervtípust, a rendszer figyelmen kívül hagyja ezt a típusú csomagot a beiratkozás előrehaladásának vagy a regisztráció befejezésének nyomon követésekor.**Nyitott jelentkezés** lapon. Ez a beállítás az összes időszakra és jogi személyre kiválasztott tervtípusra vonatkozik. |

4. Válassza a **Mentés** lehetőséget.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
