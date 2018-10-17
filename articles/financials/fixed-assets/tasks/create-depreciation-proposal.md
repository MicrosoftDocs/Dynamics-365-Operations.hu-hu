---
title: "Értékcsökkenési javaslat létrehozása"
description: "Ez az eljárás bemutatja, hogy hogyan működnek az értékcsökkenési kötegjavaslatok, illetve elmagyarázza, hogy hogyan hozhat létre tárgyi eszközök értékcsökkenésére irányuló javaslatot."
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: d11554ee5f26ef5a85e799194d2f75757a31c254
ms.contentlocale: hu-hu
ms.lasthandoff: 09/14/2018

---

# <a name="create-depreciation-proposal"></a><span data-ttu-id="cdcc9-103">Értékcsökkenési javaslat létrehozása</span><span class="sxs-lookup"><span data-stu-id="cdcc9-103">Create depreciation proposal</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="cdcc9-104">Ez az eljárás bemutatja, hogy hogyan működnek az értékcsökkenési kötegjavaslatok, illetve elmagyarázza, hogy hogyan hozhat létre tárgyi eszközök értékcsökkenésére irányuló javaslatot.</span><span class="sxs-lookup"><span data-stu-id="cdcc9-104">This procedure describes how depreciation batch proposals work and explains how to propose depreciation for fixed assets.</span></span> <span data-ttu-id="cdcc9-105">Ez a feladat a USMF bemutató vállalatot, illetve a könyvelői szerepkört használja.</span><span class="sxs-lookup"><span data-stu-id="cdcc9-105">This task uses the USMF demo company and the accountant role.</span></span>


## <a name="create-depreciation-proposal"></a><span data-ttu-id="cdcc9-106">Értékcsökkenési javaslat létrehozása</span><span class="sxs-lookup"><span data-stu-id="cdcc9-106">Create depreciation proposal</span></span>
1. <span data-ttu-id="cdcc9-107">Ugorjon a Tárgyi eszközök > Naplóbejegyzések > Értékcsökkenési javaslat létrehozása pontra.</span><span class="sxs-lookup"><span data-stu-id="cdcc9-107">Go to Fixed assets > Journal entries > Create depreciation proposal.</span></span>
2. <span data-ttu-id="cdcc9-108">A Napló neve mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="cdcc9-108">In the Name of journal field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="cdcc9-109">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="cdcc9-109">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="cdcc9-110">Adja meg a dátumot a „Záró dátum” mezőben.</span><span class="sxs-lookup"><span data-stu-id="cdcc9-110">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="cdcc9-111">A z Értékcsökkenés összegzése opció kiválasztásával egyetlen naplósorba összegezheti a havi értékcsökkenéseket.</span><span class="sxs-lookup"><span data-stu-id="cdcc9-111">Select the Summarize depreciation option to summarize monthly depreciations into one journal line.</span></span>  
    * <span data-ttu-id="cdcc9-112">Például ha a záródátum értéke 2015. március 31., a program a következő leírást generálja: „Értékcsökkenés 2015. január 31-e óta”.</span><span class="sxs-lookup"><span data-stu-id="cdcc9-112">For example, if the To date value is March 31, 2015, the following description is generated: “Depreciation since January 31, 2015.”</span></span> <span data-ttu-id="cdcc9-113">A javasolt naplósorok Dátummezője ekkor 2015. március 31-re áll át.</span><span class="sxs-lookup"><span data-stu-id="cdcc9-113">The Date field on the proposed journal lines is then set to March 31, 2015.</span></span>  
    * <span data-ttu-id="cdcc9-114">A Szűrő opció segítségével eszköz, eszközcsoport vagy egyéb feltétel szerint szűrheti az értékcsökkenési javaslatokat.</span><span class="sxs-lookup"><span data-stu-id="cdcc9-114">The depreciation proposal can be filtered by asset, asset group, or other criteria using the Filter option.</span></span>  
    * <span data-ttu-id="cdcc9-115">A Beszerzési vagy értékcsökkenési javaslatok tárgyi eszközökhöz adatlap használata esetén tud kötegenkénti értékcsökkenésre vonatkozó javaslatot adni meg.</span><span class="sxs-lookup"><span data-stu-id="cdcc9-115">When you use the Create acquisition or depreciation proposals for fixed assets form, you can propose depreciation in batches.</span></span> <span data-ttu-id="cdcc9-116">Ezt a módszert ajánljuk olyan nagyobb javaslatoknál, amelyek komolyabb mértékben használják a rendszer erőforrásait.</span><span class="sxs-lookup"><span data-stu-id="cdcc9-116">This is recommended for larger proposals that will use more system resources.</span></span> <span data-ttu-id="cdcc9-117">Ha a köteg lehetőséget választja, akkor a rendszert közben más feladatokhoz is használhatja.</span><span class="sxs-lookup"><span data-stu-id="cdcc9-117">If you select the batch option, you can still complete other tasks during that time.</span></span> <span data-ttu-id="cdcc9-118">Ha ezzel a módszerrel hoz létre értékcsökkenési javaslatot, akkor az értékcsökkenés a tárgyieszköz-értékmodellekre jön létre.</span><span class="sxs-lookup"><span data-stu-id="cdcc9-118">When you propose depreciation in this way, depreciation is calculated for value models for fixed assets.</span></span>  
5. <span data-ttu-id="cdcc9-119">Kattintson a Napló létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cdcc9-119">Click Create journal.</span></span>

## <a name="review-depreciation-entries"></a><span data-ttu-id="cdcc9-120">Tekintse át az értékcsökkenés bejegyzéseket</span><span class="sxs-lookup"><span data-stu-id="cdcc9-120">Review depreciation entries</span></span>
1. <span data-ttu-id="cdcc9-121">Ugorjon a Tárgyi eszközök > Naplóbejegyzések > Tárgyi eszközök naplója pontra.</span><span class="sxs-lookup"><span data-stu-id="cdcc9-121">Go to Fixed assets > Journal entries > Fixed assets journal.</span></span>
2. <span data-ttu-id="cdcc9-122">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="cdcc9-122">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="cdcc9-123">Kattintson a Sorok pontra.</span><span class="sxs-lookup"><span data-stu-id="cdcc9-123">Click Lines.</span></span>
4. <span data-ttu-id="cdcc9-124">Kattintson a Feladás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cdcc9-124">Click Post.</span></span>


