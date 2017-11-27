--- 
title: "Tárgyi eszköz értékcsökkenésének kiszámítása jogi személyek között"
description: "Ez a témakör bemutatja, hogy hogyan állíthat be és futtathat több jogi személynél értékcsökkenés folyamatot."
author: saraschi2
manager: AnnBe
ms.date: 11/02/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d804480167414cd038f8229db312dc9c52d131f8
ms.openlocfilehash: 4c45da124136b7fecb916d2ff9098c8ffeff6cb1
ms.contentlocale: hu-hu
ms.lasthandoff: 11/02/2017

---
# <a name="calculate-fixed-asset-depreciation-across-legal-entities"></a><span data-ttu-id="e293f-103">Tárgyi eszköz értékcsökkenésének kiszámítása jogi személyek között</span><span class="sxs-lookup"><span data-stu-id="e293f-103">Calculate fixed asset depreciation across legal entities</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e293f-104">Tárgyi eszköz értékcsökkenése egyetlen lépésben futtatható jogi személyek között.</span><span class="sxs-lookup"><span data-stu-id="e293f-104">Fixed asset depreciation can be run across legal entities in a single step.</span></span> <span data-ttu-id="e293f-105">Ez a témakör bemutatja, hogy hogyan állíthatja be és futtathatja több jogi személynél a folyamatot.</span><span class="sxs-lookup"><span data-stu-id="e293f-105">This procedure shows you to how set up and run the process for multiple legal entities.</span></span> <span data-ttu-id="e293f-106">A könyvelői szerepkört használja.</span><span class="sxs-lookup"><span data-stu-id="e293f-106">It uses the accountant role.</span></span>  

<span data-ttu-id="e293f-107">Ez a felvétel az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="e293f-107">This recording uses the USMF demo company.</span></span>


<span data-ttu-id="e293f-108">Lépések (16) alfeladat: Vállalatközi vállalati értékcsökkenés-futtatási naplók beállítása.</span><span class="sxs-lookup"><span data-stu-id="e293f-108">Steps (16) Sub-task: Set up cross company depreciation run journals.</span></span> 

1. <span data-ttu-id="e293f-109">Először be kell állítania a naplókat a több vállalatot érintő értékcsökkenés futtatásához valamennyi jogi személynél.</span><span class="sxs-lookup"><span data-stu-id="e293f-109">First, you must set up the journals to be used in the cross company depreciation run in each legal entity.</span></span> <span data-ttu-id="e293f-110">Ugorjon a Tárgyi eszközök > Beállítás > Tárgyi eszköz paraméterek pontra.</span><span class="sxs-lookup"><span data-stu-id="e293f-110">Go to Fixed assets > Setup > Fixed assets parameters.</span></span> 
2. <span data-ttu-id="e293f-111">Bontsa ki a tárgyieszköz-javaslatok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="e293f-111">Expand the Fixed asset proposals section.</span></span> 
3. <span data-ttu-id="e293f-112">Hozzon létre rekordot azzal a naplónévvel, amely a jogi személy egyes feladási rétegekeinél lesz használatban.</span><span class="sxs-lookup"><span data-stu-id="e293f-112">Create a record with the journal name to be used for each posting layer in the legal entity.</span></span> <span data-ttu-id="e293f-113">Ha a könyvek nem adják fel az adatokat a főkönyvbe, akkor a Nincs feladási réteget lehetőséget kell kiválasztania a társított naplóval.</span><span class="sxs-lookup"><span data-stu-id="e293f-113">If books do not post to the general ledger, then the None posting layer should be selected with the associated journal.</span></span> <span data-ttu-id="e293f-114">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="e293f-114">Click Add.</span></span> 
4. <span data-ttu-id="e293f-115">A Feladási réget mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="e293f-115">In the Posting layer field, enter or select a value.</span></span> 
5. <span data-ttu-id="e293f-116">A Napló neve mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="e293f-116">In the Journal name field, enter or select a value.</span></span> 
6. <span data-ttu-id="e293f-117">Ismételje meg a napló beállítását a tárgyi eszköz paraméterei lapon az egyes jogi személyekhez.</span><span class="sxs-lookup"><span data-stu-id="e293f-117">Repeat the journal setup on the Fixed asset parameters page in each legal entity.</span></span> 

<span data-ttu-id="e293f-118">Alfeladat: Értékcsökkenés kiszámítása</span><span class="sxs-lookup"><span data-stu-id="e293f-118">Sub-task: Calculate depreciation</span></span>

1. <span data-ttu-id="e293f-119">Az Értékcsökkenési javaslat létrehozása lap használatával indítsa el az értékcsökkenés futtatását a jogi személyek között.</span><span class="sxs-lookup"><span data-stu-id="e293f-119">Use the Create depreciation proposal page to start your depreciation run across legal entities.</span></span> <span data-ttu-id="e293f-120">Ugorjon a Tárgyi eszközök > Naplóbejegyzések > Értékcsökkenési javaslat létrehozása pontra.</span><span class="sxs-lookup"><span data-stu-id="e293f-120">Go to Fixed assets > Journal entries > Create depreciation proposal.</span></span> 
2. <span data-ttu-id="e293f-121">A Feladási réget mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="e293f-121">In the Posting layer field, enter or select a value.</span></span> 
3. <span data-ttu-id="e293f-122">A napló neve alapértelmezésben a tárgyi eszköz paramétereiből jön.</span><span class="sxs-lookup"><span data-stu-id="e293f-122">The journal name will default from the Fixed asset parameters.</span></span> <span data-ttu-id="e293f-123">Itt módosítható az aktuális jogi személyhez.</span><span class="sxs-lookup"><span data-stu-id="e293f-123">It can be changed here for the current legal entity.</span></span> 
4. <span data-ttu-id="e293f-124">Adja meg a dátumot a „Záró dátum” mezőben.</span><span class="sxs-lookup"><span data-stu-id="e293f-124">In the To date field, enter a date.</span></span> 
5. <span data-ttu-id="e293f-125">Válassza ki az értékcsökkenés futtatásába felvenni kívánt jogi személyeket.</span><span class="sxs-lookup"><span data-stu-id="e293f-125">Select the legal entities to be included in the depreciation run.</span></span> <span data-ttu-id="e293f-126">A listában csak a tárgyieszköz-javaslatokhoz a tárgyi eszköz paraméterei lapon beállított naplókkal rendelkező jogi személyek fognak megjelenni.</span><span class="sxs-lookup"><span data-stu-id="e293f-126">Only legal entities with journals set up for Fixed asset proposals on the Fixed asset parameters page will be shown in the list.</span></span> 
6. <span data-ttu-id="e293f-127">Ha engedélyezve van, a naplók feladása beállítás automatikusan feladja az értékcsökkenési naplókat a létrehozásukkor.</span><span class="sxs-lookup"><span data-stu-id="e293f-127">When enabled, the Post journals option will automatically post the depreciation journals when they are created.</span></span> <span data-ttu-id="e293f-128">Ha nincs bejelölve, a naplók létre lesznek hozva, de nem lesznek feladva, így a feladás előtt megtekintheti a részleteket.</span><span class="sxs-lookup"><span data-stu-id="e293f-128">When not selected, the journals will be created, but not posted, so you can review the details before posting.</span></span> <span data-ttu-id="e293f-129">Válassza ki az Igen lehetőséget a Naplók feladása mezőben.</span><span class="sxs-lookup"><span data-stu-id="e293f-129">Select Yes in the Post journals field.</span></span> 
7. <span data-ttu-id="e293f-130">A szűrőmezőkbe beletartozik az összes tárgyi eszköz, a csoportok és a könyvek az értékcsökkenési futtatáshoz kiválasztott a jogi személyekhez.</span><span class="sxs-lookup"><span data-stu-id="e293f-130">Filtering fields include all fixed assets, groups, and books for the legal entities selected for this depreciation run.</span></span> 
8. <span data-ttu-id="e293f-131">A kötegelt feldolgozási beállítás alapértelmezés szerint engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="e293f-131">The Batch processing option is enabled by default.</span></span> <span data-ttu-id="e293f-132">Ha ez a beállítás engedélyezve van, az értékcsökkenési napló létrehozása és feladása a háttérben fog futni.</span><span class="sxs-lookup"><span data-stu-id="e293f-132">When this option is enabled, the depreciation journal creation and posting will run in the background.</span></span> 
9. <span data-ttu-id="e293f-133">Kattintson a Napló létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e293f-133">Click Create journal.</span></span> 
10. <span data-ttu-id="e293f-134">Az egyes jogi személyeknél létrehozott értékcsökkenési naplókat meg kell tekinteni.</span><span class="sxs-lookup"><span data-stu-id="e293f-134">You must view the depreciation journals created in the respective legal entities.</span></span> <span data-ttu-id="e293f-135">Ugorjon a Tárgyi eszközök > Naplóbejegyzések > Tárgyi eszközök naplója pontra.</span><span class="sxs-lookup"><span data-stu-id="e293f-135">Go to Fixed assets > Journal entries > Fixed assets journal.</span></span>

