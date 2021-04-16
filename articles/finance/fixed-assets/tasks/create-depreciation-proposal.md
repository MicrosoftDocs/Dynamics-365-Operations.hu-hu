---
title: Értékcsökkenési javaslat létrehozása
description: Ez a témakör leírja, hogyan működnek az értékcsökkenési kötegjavaslatok, és bemutatja, hogyan hozhat létre tárgyi eszközök értékcsökkenésére irányuló javaslatot.
author: abruer
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 013c768c8a016f399a27b1488ad0d5b339fdf7cb
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813579"
---
# <a name="create-a-depreciation-proposal"></a><span data-ttu-id="507ac-103">Értékcsökkenési javaslat létrehozása</span><span class="sxs-lookup"><span data-stu-id="507ac-103">Create a depreciation proposal</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="507ac-104">Ez a témakör leírja, hogyan működnek az értékcsökkenési kötegjavaslatok, és bemutatja, hogyan hozhat létre tárgyi eszközök értékcsökkenésére irányuló javaslatot.</span><span class="sxs-lookup"><span data-stu-id="507ac-104">This topic describes how depreciation batch proposals work and explains how to propose depreciation for fixed assets.</span></span> <span data-ttu-id="507ac-105">Ez a feladat a USMF bemutató vállalatot, illetve a könyvelői szerepkört használja.</span><span class="sxs-lookup"><span data-stu-id="507ac-105">This task uses the USMF demo company and the accountant role.</span></span>


## <a name="create-a-depreciation-proposal"></a><span data-ttu-id="507ac-106">Értékcsökkenési javaslat létrehozása</span><span class="sxs-lookup"><span data-stu-id="507ac-106">Create a depreciation proposal</span></span>
1. <span data-ttu-id="507ac-107">A navigációs ablaktáblán nyissa meg a **Modulok > Tárgyi eszközök > Naplóbejegyzések > Értékcsökkenési javaslat létrehozása** elemet.</span><span class="sxs-lookup"><span data-stu-id="507ac-107">In the navigation pane, go to **Modules > Fixed assets > Journal entries > Create depreciation proposal**.</span></span>
2. <span data-ttu-id="507ac-108">A **Napló neve** mezőben válasszon ki egy opciót a legördülő menüben.</span><span class="sxs-lookup"><span data-stu-id="507ac-108">In the **Name of journal** field, select an option from the drop-down menu.</span></span>
3. <span data-ttu-id="507ac-109">Adjon meg egy dátumot a **Záró dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="507ac-109">In the **To date** field, enter a date.</span></span>

    - <span data-ttu-id="507ac-110">Az **Értékcsökkenés összegzése** opció kiválasztásával egyetlen naplósorba összegezheti a havi értékcsökkenéseket.</span><span class="sxs-lookup"><span data-stu-id="507ac-110">Select the **Summarize depreciation** option to summarize monthly depreciations into one journal line.</span></span>  
    - <span data-ttu-id="507ac-111">Például ha a záródátum értéke 2015. március 31., a program a következő leírást generálja: „Értékcsökkenés 2015. január 31-e óta”.</span><span class="sxs-lookup"><span data-stu-id="507ac-111">For example, if the To date value is March 31, 2015, the following description is generated: "Depreciation since January 31, 2015."</span></span> <span data-ttu-id="507ac-112">A javasolt naplósorok **Dátum** mezője ekkor 2015. március 31-re áll át.</span><span class="sxs-lookup"><span data-stu-id="507ac-112">The **Date** field on the proposed journal lines is then set to March 31, 2015.</span></span>  
    - <span data-ttu-id="507ac-113">A **Szűrő** opció segítségével eszköz, eszközcsoport vagy egyéb feltétel szerint szűrheti az értékcsökkenési javaslatokat.</span><span class="sxs-lookup"><span data-stu-id="507ac-113">The depreciation proposal can be filtered by asset, asset group, or other criteria using the **Filter** option.</span></span>  
    - <span data-ttu-id="507ac-114">A **Beszerzési vagy értékcsökkenési javaslatok tárgyi eszközökhöz** adatlap használata esetén tud kötegenkénti értékcsökkenésre vonatkozó javaslatot adni meg.</span><span class="sxs-lookup"><span data-stu-id="507ac-114">When you use the **Create acquisition or depreciation proposals for fixed assets** form, you can propose depreciation in batches.</span></span> <span data-ttu-id="507ac-115">Ezt a módszert ajánljuk olyan nagyobb javaslatoknál, amelyek komolyabb mértékben használják a rendszer erőforrásait.</span><span class="sxs-lookup"><span data-stu-id="507ac-115">This is recommended for larger proposals that will use more system resources.</span></span> <span data-ttu-id="507ac-116">Ha a köteg lehetőséget választja, akkor a rendszert közben más feladatokhoz is használhatja.</span><span class="sxs-lookup"><span data-stu-id="507ac-116">If you select the batch option, you can still complete other tasks during that time.</span></span> <span data-ttu-id="507ac-117">Ha ezzel a módszerrel hoz létre értékcsökkenési javaslatot, akkor az értékcsökkenés a tárgyieszköz-értékmodellekre jön létre.</span><span class="sxs-lookup"><span data-stu-id="507ac-117">When you propose depreciation in this way, depreciation is calculated for value models for fixed assets.</span></span>  

4. <span data-ttu-id="507ac-118">Válassza a **Napló létrehozása** elemet.</span><span class="sxs-lookup"><span data-stu-id="507ac-118">Select **Create journal**.</span></span>

## <a name="review-depreciation-entries"></a><span data-ttu-id="507ac-119">Tekintse át az értékcsökkenés bejegyzéseket</span><span class="sxs-lookup"><span data-stu-id="507ac-119">Review depreciation entries</span></span>
1. <span data-ttu-id="507ac-120">A navigációs ablaktáblán nyissa meg a **Modulok > Tárgyi eszközök > Naplóbejegyzések > Tárgyi eszközök naplója** elemet.</span><span class="sxs-lookup"><span data-stu-id="507ac-120">In the navigation pane, go to **Modules > Fixed assets > Journal entries > Fixed assets journal**.</span></span>
2. <span data-ttu-id="507ac-121">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="507ac-121">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="507ac-122">**Sorok** kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="507ac-122">Select **Lines**.</span></span>
4. <span data-ttu-id="507ac-123">Válassza a **Feladás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="507ac-123">Select **Post**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]