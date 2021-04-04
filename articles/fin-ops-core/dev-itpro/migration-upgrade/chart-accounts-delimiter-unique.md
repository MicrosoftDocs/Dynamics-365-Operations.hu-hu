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
# <a name="make-the-chart-of-accounts-delimiter-unique"></a><span data-ttu-id="0462c-104">A számlatükör-elválasztó egyedivé tétele</span><span class="sxs-lookup"><span data-stu-id="0462c-104">Make the chart of accounts delimiter unique</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0462c-105">A Microsoft Dynamics AX 2012-ben használható volt ugyanaz az elválasztó a számlatükörhöz és a dimenzióértékekhez.</span><span class="sxs-lookup"><span data-stu-id="0462c-105">In Microsoft Dynamics AX 2012, you could use the same delimiter for your chart of accounts and dimension values.</span></span> <span data-ttu-id="0462c-106">A Finance and Operations aktuális verzióiban nem használható ugyanaz az elválasztó a számlatükörhöz és a dimenzióértékekhez.</span><span class="sxs-lookup"><span data-stu-id="0462c-106">In current versions of Finance and Operations, you cannot have the same delimiter for the chart of accounts and dimension values.</span></span> <span data-ttu-id="0462c-107">Ha egy elválasztó ismétlődik, frissítés után módosíthatja.</span><span class="sxs-lookup"><span data-stu-id="0462c-107">If there is a duplicate delimiter, you can change it after upgrade.</span></span> 

<span data-ttu-id="0462c-108">Ez a funkció a következő verziókban érhető el:</span><span class="sxs-lookup"><span data-stu-id="0462c-108">This feature is available in the following versions:</span></span>
- <span data-ttu-id="0462c-109">Finance and Operations 8.0-s verzió</span><span class="sxs-lookup"><span data-stu-id="0462c-109">Finance and Operations version 8.0</span></span>
- <span data-ttu-id="0462c-110">Finance and Operations 7.1 verzió, KB 4094701 Nem lehet megadni a pénzügyi dimenziókat, ha a dimenzióértékek tartalmazzák a számlatükör elválasztóját</span><span class="sxs-lookup"><span data-stu-id="0462c-110">Finance and Operations version 7.1, KB 4094701 Cannot enter the financial dimensions when the dimension values contain the chart of accounts delimiter</span></span>
- <span data-ttu-id="0462c-111">Finance and Operations 7.2 verzió, KB 4092967 Részprojektet nem lehet dimenzióként kiválasztani, ha az alprojekt formátuma tartalmazza a dimenzió-elválasztót</span><span class="sxs-lookup"><span data-stu-id="0462c-111">Finance and Operations version 7.2, KB 4092967 Cannot choose sub-project as dimension when sub-project format contains the dimension delimiter</span></span>

## <a name="update-delimiter"></a><span data-ttu-id="0462c-112">Elválasztó frissítése</span><span class="sxs-lookup"><span data-stu-id="0462c-112">Update delimiter</span></span>
<span data-ttu-id="0462c-113">Ha van ütközés a számlatükörrel, akkor a számlatükör elhatárolója és a projekt/alprojekt azonosítóformátuma módosítható.</span><span class="sxs-lookup"><span data-stu-id="0462c-113">If there is a conflict with the chart of accounts, the chart of accounts delimiter and the project/subproject ID format can be changed.</span></span> <span data-ttu-id="0462c-114">Egyéb dimenzióhatárolók nem változtathatók meg.</span><span class="sxs-lookup"><span data-stu-id="0462c-114">No other dimension delimiters can be changed.</span></span> 
- <span data-ttu-id="0462c-115">A számlatükör elhatárolója frissítés után módosítható a **Főkönyvi paraméterek** > **Számlatükör és dimenziók** > **Elválasztó módosítása** menüpontjában.</span><span class="sxs-lookup"><span data-stu-id="0462c-115">You can change the chart of accounts delimiter after upgrade in **General ledger parameters** > **Chart of accounts and dimensions** > **Change delimiter**.</span></span> 
- <span data-ttu-id="0462c-116">Ha csak a projekt vagy alprojekt azonosítóformátuma ütközik, ezt az értéket módosíthatja a **Projektvezetési és könyvelési paraméterek** > **Általános** > **Alprojekt formátumának módosítása** pontban.</span><span class="sxs-lookup"><span data-stu-id="0462c-116">If the only conflict is with the project/subproject ID format, you can change that value in **Project management and accounting parameters** > **General** > **Modify subproject format**.</span></span> 

## <a name="how-to-determine-if-your-environment-requires-updated-delimiters"></a><span data-ttu-id="0462c-117">Annak megállapítása, ha környezet számára szükséges az elválasztók frissítése</span><span class="sxs-lookup"><span data-stu-id="0462c-117">How to determine if your environment requires updated delimiters</span></span> 
<span data-ttu-id="0462c-118">Ha a frissített környezetben lévő elhatárolók ütköznek egymással, instabilitást tapasztalhat abban az esetben, ha szegmentált bejegyzésvezérlőbe vagy a dimenzióbejegyzés-vezérlőbe visz be értékeket.</span><span class="sxs-lookup"><span data-stu-id="0462c-118">If delimiters in your upgraded environment are conflicting, you may experience instability when entering values in a segmented entry control or dimension entry control.</span></span> <span data-ttu-id="0462c-119">Ez azt jelenti, hogy mindig kereséssel vagy helyi menüvel kell megadnia a számla és a dimenzió kombinációját.</span><span class="sxs-lookup"><span data-stu-id="0462c-119">This means that you will need to always use lookups or a flyout menu when entering account and dimension combinations.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]