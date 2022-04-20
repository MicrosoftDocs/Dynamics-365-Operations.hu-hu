---
title: A számlatükör-elválasztó egyedivé tétele
description: Ez a témakör elmagyarázza, hogy a rendszerben hogyan nem lehet ugyanaz az elválasztó a számlatükörhöz és a dimenzióértékekhez. Frissítés után módosítania kell az elválasztóértékeket.
author: panolte
ms.date: 04/13/2022
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
ms.openlocfilehash: 6081a62077f1fc6b6920991ed6faae667c25a47c
ms.sourcegitcommit: e8a2a1e34fa48a42afac9724828f4ec72b6d7085
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2022
ms.locfileid: "8573618"
---
# <a name="make-the-chart-of-accounts-delimiter-unique"></a>A számlatükör-elválasztó egyedivé tétele

[!include [banner](../includes/banner.md)]

A Microsoft Dynamics AX 2012-ben használható volt ugyanaz az elválasztó a számlatükörhöz és a dimenzióértékekhez. A Pénzügy és műveletek jelenlegi verzióiban nem lehet ugyanaz az elválasztó a számlatükrhez, a dimenziónevekhez és -értékekhez. Ha egy elválasztó ismétlődik, frissítés után módosíthatja. 

## <a name="update-delimiter"></a>Elválasztó frissítése
Ha van ütközés a számlatükörrel, akkor a számlatükör elhatárolója és a projekt/alprojekt azonosítóformátuma módosítható. Egyéb dimenzióhatárolók nem változtathatók meg. 
- A számlatükör elhatárolója frissítés után módosítható a **Főkönyvi paraméterek** > **Számlatükör és dimenziók** > **Elválasztó módosítása** menüpontjában. 
- Ha csak a projekt vagy alprojekt azonosítóformátuma ütközik, ezt az értéket módosíthatja a **Projektvezetési és könyvelési paraméterek** > **Általános** > **Alprojekt formátumának módosítása** pontban. 

### <a name="other-considerations"></a>További szempontok
A projekt-/alprojekt azonosítójához hasonlóan a pénzügyi dimenzióként használt minden más alapadatrekordnak, például a szállítóknak vagy a vevőknek nem lehet olyan számlaazonosító-értékük, amely a számlatükr-elválasztóval azonos karaktert használ. 

## <a name="how-to-determine-if-your-environment-requires-updated-delimiters"></a>Annak megállapítása, ha környezet számára szükséges az elválasztók frissítése 
Ha a frissített környezetben lévő elhatárolók ütköznek egymással, instabilitást tapasztalhat abban az esetben, ha szegmentált bejegyzésvezérlőbe vagy a dimenzióbejegyzés-vezérlőbe visz be értékeket. Ez azt jelenti, hogy mindig kereséssel vagy helyi menüvel kell megadnia a számla és a dimenzió kombinációját.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
