---
title: A számlatükör-elválasztó egyedivé tétele
description: Ez a témakör elmagyarázza, hogy a rendszerben hogyan nem lehet ugyanaz az elválasztó a számlatükörhöz és a dimenzióértékekhez. Frissítés után módosítania kell az elválasztóértékeket.
author: panolte
manager: AnnBe
ms.date: 03/30/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: 183980651a811ef30a49461ff5a5f649d94b079c
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5565262"
---
# <a name="make-the-chart-of-accounts-delimiter-unique"></a>A számlatükör-elválasztó egyedivé tétele

[!include [banner](../includes/banner.md)]

A Microsoft Dynamics AX 2012-ben használható volt ugyanaz az elválasztó a számlatükörhöz és a dimenzióértékekhez. A Finance and Operations aktuális verzióiban nem használható ugyanaz az elválasztó a számlatükörhöz és a dimenzióértékekhez. Ha egy elválasztó ismétlődik, frissítés után módosíthatja. 

Ez a funkció a következő verziókban érhető el:
- Finance and Operations 8.0-s verzió
- Finance and Operations 7.1 verzió, KB 4094701 Nem lehet megadni a pénzügyi dimenziókat, ha a dimenzióértékek tartalmazzák a számlatükör elválasztóját
- Finance and Operations 7.2 verzió, KB 4092967 Részprojektet nem lehet dimenzióként kiválasztani, ha az alprojekt formátuma tartalmazza a dimenzió-elválasztót

## <a name="update-delimiter"></a>Elválasztó frissítése
Ha van ütközés a számlatükörrel, akkor a számlatükör elhatárolója és a projekt/alprojekt azonosítóformátuma módosítható. Egyéb dimenzióhatárolók nem változtathatók meg. 
- A számlatükör elhatárolója frissítés után módosítható a **Főkönyvi paraméterek** > **Számlatükör és dimenziók** > **Elválasztó módosítása** menüpontjában. 
- Ha csak a projekt vagy alprojekt azonosítóformátuma ütközik, ezt az értéket módosíthatja a **Projektvezetési és könyvelési paraméterek** > **Általános** > **Alprojekt formátumának módosítása** pontban. 

## <a name="how-to-determine-if-your-environment-requires-updated-delimiters"></a>Annak megállapítása, ha környezet számára szükséges az elválasztók frissítése 
Ha a frissített környezetben lévő elhatárolók ütköznek egymással, instabilitást tapasztalhat abban az esetben, ha szegmentált bejegyzésvezérlőbe vagy a dimenzióbejegyzés-vezérlőbe visz be értékeket. Ez azt jelenti, hogy mindig kereséssel vagy helyi menüvel kell megadnia a számla és a dimenzió kombinációját.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]