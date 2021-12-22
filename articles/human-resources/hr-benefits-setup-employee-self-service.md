---
title: Az alkalmazott önkiszolgáló szolgáltatásának konfigurálása
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
ms.openlocfilehash: 1e0c59eb8db5a97405e87922cc65f3eb74bee48e
ms.sourcegitcommit: b101c21f972fdad2667431f712222e040cd69d43
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/07/2021
ms.locfileid: "7898440"
---
# <a name="configure-employee-self-service"></a>Alkalmazotti önkiszolgálás konfigurálása

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

A Microsoft Dynamics 365 Human Resources rendszerben a felső szintű navigációhoz csempéket konfigurálhat a **Munkavállalói önkiszolgálásban**. A juttatási terv csempék a felhasználókat olyan juttatási konstrukciókhoz irányítják, amelyekre jogosultak.

## <a name="set-up-a-benefit-plans-tile"></a>Juttatásikonstrukció-csempe beállítása

1. A **Juttatások kezelése** munkaterület **Beállítás** részén válassza az **Alkalmazotti önkiszolgáló rendszer paraméterei** elemet.

2. Válassza ki a **Juttatásikonstrukció-csempe beállítása** lapot, majd válassza az **Új** lehetőséget.

3. Adjon meg értékeket a következő mezőkben.

   | Mező | Leírás |
   | --- | --- |
   | **Konstrukció típuskódja** | Az a tervtípus, amely akkor jelenik meg, amikor ez a csempe ki van jelölve az **Előnyök önkiszolgáló szolgáltatásban**. |
   | **Csempe azonosítója** | A mozaik egyedi azonosítója. |
   | **CSempecímke felirata** | A csempéhez a **Benefits önkiszolgáló szolgáltatásban megjelenő szöveg**. |
   | **Leírás** | A csempe leírása. |
   | **Csempeháttérkép** | A csempéhez használandó kép URL-címe (nem kötelező). |
   | **Nyílt beiratkozás nyomon követése** | Ezzel a beállítással nyomon követheti a csomagtípus nyitott regisztrációs előrehaladását. Előfordulhat például, hogy olyan terveket hoz létre, ahol **a Terv típusa = Egyéb**. Ezek a konstrukciók választható konstrukciók lehetnek, amelyekhez nem szeretné nyomon követni a beléptetés előrehaladását. Ha nem választja ki ezt a tervtípust, az ilyen típusú terv figyelmen kívül marad a regisztráció előrehaladásának vagy a regisztráció befejezésének nyomon követésekor a **Regisztráció megnyitása** lapon. Ez a beállítás az összes időszakra és jogi személyre kiválasztott tervtípusra vonatkozik. |

4. Válassza a **Mentés** lehetőséget.

## <a name="set-up-a-flex-credit-plan-tile"></a>Rugalmas hitelkonstrukció csempe beállítása

1. A **Juttatások kezelése** munkaterület **Beállítás** részén válassza az **Alkalmazotti önkiszolgáló rendszer paraméterei** elemet.

2. Válassza ki a **Rugalmas hitelkonstrukció csempe beállítása** lapot, majd válassza az **Új** lehetőséget.

3. Adjon meg értékeket a következő mezőkben.

   | Mező | Leírás |
   | --- | --- |
   | **Juttatás-jóváírás azonosítója** | A rugalmas hitelprogram-tervek, amelyek akkor jelennek meg, ha ez a csempe ki van jelölve a **Előnyök önkiszolgáló**. |
   | **Csempe azonosítója** | A mozaik egyedi azonosítója. |
   | **CSempecímke felirata** | A csempéhez a **Benefits önkiszolgáló szolgáltatásban megjelenő szöveg**. |
   | **Leírás** | A csempe leírása. |
   | **Csempeháttérkép** | A csempéhez használandó kép URL-címe (nem kötelező). |
   | **Nyílt beiratkozás nyomon követése** | Ezzel a beállítással nyomon követheti a csomagtípus nyitott regisztrációs előrehaladását. Előfordulhat például, hogy olyan terveket hoz létre, ahol **a Terv típusa = Egyéb**. Ezek a konstrukciók választható konstrukciók lehetnek, amelyekhez nem szeretné nyomon követni a beléptetés előrehaladását. Ha nem választja ki ezt a tervtípust, az ilyen típusú terv figyelmen kívül marad a regisztráció előrehaladásának vagy a regisztráció befejezésének nyomon követésekor a **Regisztráció megnyitása** lapon. Ez a beállítás az összes időszakra és jogi személyre kiválasztott tervtípusra vonatkozik. |

4. Válassza a **Mentés** lehetőséget.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
