---
title: "A számlatükör-elválasztónak egyedinek kell lennie."
description: "In Dynamics 365 for Finance and Operations rendszerben nem használható ugyanaz az elválasztó a számlatükörhöz és a dimenzióértékekhez. Frissítés után módosítania kell az elválasztóértékeket."
author: ryansandness
manager: AnnBe
ms.date: 03/30/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: 8
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: c9728714944b54f3bff1e2a8b43c7adcf5200f08
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---

# <a name="chart-of-accounts-delimiter-must-be-unique"></a>A számlatükör-elválasztónak egyedinek kell lennie.

[!include [banner](../includes/banner.md)]

A Microsoft Dynamics AX 2012-ben használható volt ugyanaz az elválasztó a számlatükörhöz és a dimenzióértékekhez. In Dynamics 365 for Finance and Operations rendszerben nem használható ugyanaz az elválasztó a számlatükörhöz és a dimenzióértékekhez. Ha egy elválasztó ismétlődik, frissítés után módosíthatja. 

Ez a funkció a következőkben érhető el:
- Dynamics 365 for Finance and Operations, 8.0 verzió
- Dynamics 365 for Finance and Operations 7.1 verzió, KB 4094701 Nem lehet megadni a pénzügyi dimenziókat, ha a dimenzióértékek tartalmazzák a számlatükör elhatárolóját
- Dynamics 365 for Finance and Operations 7.2 verzió, KB 4092967 Részprojektet nem lehet dimenzióként kiválasztani, ha az alprojekt formátuma tartalmazza a dimenzió-elhatárolót

## <a name="update-delimiter"></a>Elválasztó frissítése
Ha van ütközés a számlatükörrel, akkor a számlatükör elhatárolója és a projekt/alprojekt azonosítóformátuma módosítható. Egyéb dimenzióhatárolók nem változtathatók meg. 
- A számlatükör elhatárolója frissítés után módosítható a Finance and Operations in **Főkönyvi paraméterek** > **Számlatükör és dimenziók** > **Elválasztó módosítása** menüpontjában. 
- Ha csak a projekt vagy alprojekt azonosítóformátuma ütközik, ezt az értéket módosíthatja a **Projektvezetési és könyvelési paraméterek** > **Általános** > **Alprojekt formátumának módosítása** pontban. 

## <a name="how-to-determine-if-your-environment-requires-updated-delimiters"></a>Annak megállapítása, ha környezet számára szükséges az elválasztók frissítése 
Ha a frissített környezetben lévő elhatárolók ütköznek egymással, instabilitást tapasztalhat abban az esetben, ha szegmentált bejegyzésvezérlőbe vagy a dimenzióbejegyzés-vezérlőbe visz be értékeket. Ez azt jelenti, hogy mindig kereséssel vagy helyi menüvel kell megadnia a számla és a dimenzió kombinációját.
