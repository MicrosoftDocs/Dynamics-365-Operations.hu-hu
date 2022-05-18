---
title: Alkalmazotti önkiszolgáló rendszer konfigurálása
description: A Microsoft Dynamics 365 Human Resources alkalmazásban lehetősége van csempéket konfigurálni az Alkalmazotti önkiszolgáló rendszer felső szintű navigációjához.
author: twheeloc
ms.date: 12/06/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d7ddb1f1ea74a16265dac701151b2c25a4f9d4dc
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/04/2022
ms.locfileid: "8687163"
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
   | **Konstrukció típuskódja** | Az a tervtípus, amely akkor jelenik meg, ha ez a csempe be van jelölve a Juttatások **önkiszolgáló szolgáltatásban**. |
   | **Csempe azonosítója** | A mozaik egyedi azonosítója. |
   | **CSempecímke felirata** | A csempe szövege a **Juttatások önkiszolgáló szolgáltatásban** |
   | **Leírás** | A csempe leírása. |
   | **Csempeháttérkép** | A csempéhez használandó kép URL-címe (nem kötelező). |
   | **Nyitott beléptetés követése** | Válassza ezt a lehetőséget, ha nyomon követi ennek a tervtípusnak a nyitott beléptetési folyamatát. Létrehozhat például olyan terveket, amelyekben **a Terv típusa = Egyéb**. Ezek a konstrukciók választható konstrukciók lehetnek, amelyekhez nem szeretné nyomon követni a beléptetés előrehaladását. Ha nem ezt a tervtípust választja, **akkor a rendszer figyelmen kívül hagyja az ilyen típusú terveket, amikor nyomon követi a beléptetés előrehaladását vagy a beléptetés teljesítését a Nyitott beléptetés lapon** . Ez a beállítás az összes időszakra és jogi személyre vonatkozóan kiválasztott tervtípusra vonatkozik. |

4. Válassza a **Mentés** lehetőséget.

## <a name="set-up-a-flex-credit-plan-tile"></a>Rugalmas hitelkonstrukció csempe beállítása

1. A **Juttatások kezelése** munkaterület **Beállítás** részén válassza az **Alkalmazotti önkiszolgáló rendszer paraméterei** elemet.

2. Válassza ki a **Rugalmas hitelkonstrukció csempe beállítása** lapot, majd válassza az **Új** lehetőséget.

3. Adjon meg értékeket a következő mezőkben.

   | Mező | Leírás |
   | --- | --- |
   | **Juttatás-jóváírás azonosítója** | A Rugalmasidő-jóváírási program terve, amely akkor jelenik meg, ha ez a csempe be van jelölve a Juttatások **önkiszolgáló szolgáltatásban**. |
   | **Csempe azonosítója** | A mozaik egyedi azonosítója. |
   | **CSempecímke felirata** | A csempe szövege a **Juttatások önkiszolgáló szolgáltatásban** |
   | **Leírás** | A csempe leírása. |
   | **Csempeháttérkép** | A csempéhez használandó kép URL-címe (nem kötelező). |
   | **Nyitott beléptetés követése** | Válassza ezt a lehetőséget, ha nyomon követi ennek a tervtípusnak a nyitott beléptetési folyamatát. Létrehozhat például olyan terveket, amelyekben **a Terv típusa = Egyéb**. Ezek a konstrukciók választható konstrukciók lehetnek, amelyekhez nem szeretné nyomon követni a beléptetés előrehaladását. Ha nem ezt a tervtípust választja, **akkor a rendszer figyelmen kívül hagyja az ilyen típusú terveket, amikor nyomon követi a beléptetés előrehaladását vagy a beléptetés teljesítését a Nyitott beléptetés lapon** . Ez a beállítás az összes időszakra és jogi személyre vonatkozóan kiválasztott tervtípusra vonatkozik. |

4. Válassza a **Mentés** lehetőséget.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
