---
title: Tárgyi eszköz felosztása
description: Ez a témakör azt ismerteti, hogyan kell egy eszközkönyv egy részét egy másik eszközkönyvhöz rendeli.
author: saraschi2
manager: AnnBe
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook, AssetSplit, AssetBookLookup, LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: db601be192b57fbec220193d3c9fde1a4f50c085
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5213508"
---
# <a name="split-a-fixed-asset"></a><span data-ttu-id="195ef-103">Tárgyi eszköz felosztása</span><span class="sxs-lookup"><span data-stu-id="195ef-103">Split a fixed asset</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="195ef-104">Ez a témakör azt ismerteti, hogyan kell egy eszközkönyv egy részét egy másik eszközkönyvhöz rendeli.</span><span class="sxs-lookup"><span data-stu-id="195ef-104">This topic explains how to split a percentage of one asset book to a new asset book.</span></span> <span data-ttu-id="195ef-105">A Könyvelői szerepkört és a USMF bemutató adatokat használja.</span><span class="sxs-lookup"><span data-stu-id="195ef-105">It uses the Accountant role and USMF demo data.</span></span>

## <a name="create-a-new-fixed-asset"></a><span data-ttu-id="195ef-106">Új tárgyi eszköz létrehozása</span><span class="sxs-lookup"><span data-stu-id="195ef-106">Create a new fixed asset</span></span>

1. <span data-ttu-id="195ef-107">A navigációs ablaktáblán ugorjon a **Modulok \> Tárgyi eszközök \> Tárgyi eszközök \> Tárgyi eszközök** elemre.</span><span class="sxs-lookup"><span data-stu-id="195ef-107">In the navigation pane, go to **Modules \> Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
2. <span data-ttu-id="195ef-108">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="195ef-108">Select **New**.</span></span>
3. <span data-ttu-id="195ef-109">A **Tárgyieszköz-csoport** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="195ef-109">In the **Fixed asset group** field, enter or select a value.</span></span> <span data-ttu-id="195ef-110">Jegyezze fel a tárgyi eszköz számát, a felosztás során későbbi felhasználás céljából.</span><span class="sxs-lookup"><span data-stu-id="195ef-110">Note the fixed asset number to use in the split process later.</span></span>
4. <span data-ttu-id="195ef-111">A **Név** mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="195ef-111">In the **Name** field, enter a value.</span></span>
5. <span data-ttu-id="195ef-112">Zárja be az űrlapot.</span><span class="sxs-lookup"><span data-stu-id="195ef-112">Close the form.</span></span>

## <a name="split-a-fixed-asset"></a><span data-ttu-id="195ef-113">Tárgyi eszköz felosztása</span><span class="sxs-lookup"><span data-stu-id="195ef-113">Split a fixed asset</span></span>

<span data-ttu-id="195ef-114">A teljes mértékben értékcsökkentett eszköz felosztása előtt a tárgyi eszköz állapotát manuálisan módosítani kell **Lezárt** értékről **Nyitott** értékre.</span><span class="sxs-lookup"><span data-stu-id="195ef-114">Before a fully depreciated asset is split, the asset book status should be manually changed from **Closed** to **Open**.</span></span> <span data-ttu-id="195ef-115">Ezt a lépést kötelező végrehajtani, mert a könyv állapotának **Nyitottnak** kell lennie, ha a tárgyi eszközhöz tranzakciókat kell feladnia (például egy értékesítéses kivezetés esetében).</span><span class="sxs-lookup"><span data-stu-id="195ef-115">This step is required because the book status has to be **Open** if you must post transactions for the asset (for example, for a disposal sale).</span></span> <span data-ttu-id="195ef-116">A **Főkönyvi paraméterek** lap **Általános** fülön be kell kapcsolnia a **Több tranzakció engedélyezése egy bizonylat** paramétert.</span><span class="sxs-lookup"><span data-stu-id="195ef-116">You must also turn on the **Allow multiple transactions within one voucher** parameter on the **General** tab of the **General ledger parameters** page.</span></span> <span data-ttu-id="195ef-117">Miután az eszközkönyv állapota megváltozott, és egy bizonylaton belül több tranzakció is engedélyezett, hajtsa végre a következő lépéseket az eszköz felosztásához.</span><span class="sxs-lookup"><span data-stu-id="195ef-117">After the asset book status is changed and multiple transactions within one voucher have been allowed, complete the following steps to split the asset.</span></span>

1. <span data-ttu-id="195ef-118">A listában keresse meg és válassza ki a felosztani kívánt tárgyi eszköz hivatkozását.</span><span class="sxs-lookup"><span data-stu-id="195ef-118">In the list, find and select the link of the fixed asset to split.</span></span>
2. <span data-ttu-id="195ef-119">Válassza ki a **Könyvek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="195ef-119">Select **Books**.</span></span> <span data-ttu-id="195ef-120">Válassza ki az új tárgyi eszközhöz hozzárendelni kívánt könyvet.</span><span class="sxs-lookup"><span data-stu-id="195ef-120">Select the book to split to the new asset.</span></span>
3. <span data-ttu-id="195ef-121">Válassza a **Funkciók** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="195ef-121">Select **Functions**.</span></span>
4. <span data-ttu-id="195ef-122">Válassza ki a **Tárgyi eszköz felosztása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="195ef-122">Select **Split fixed asset**.</span></span>
5. <span data-ttu-id="195ef-123">A **Záró tárgyi eszköz** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="195ef-123">In the **To fixed asset** field, enter or select a value.</span></span>
6. <span data-ttu-id="195ef-124">A **Könyvhöz** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="195ef-124">In the **To book** field, select the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="195ef-125">A **Tranzakció dátuma** mezőben adjon meg egy dátumot.</span><span class="sxs-lookup"><span data-stu-id="195ef-125">In the **Transaction date** field, enter a date.</span></span>
8. <span data-ttu-id="195ef-126">Adjon meg egy számot a  **Százalék** mezőben.</span><span class="sxs-lookup"><span data-stu-id="195ef-126">In the **Percent** field, enter a number.</span></span>
9. <span data-ttu-id="195ef-127">A **Napló neve** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="195ef-127">In the **Journal name** field, enter or select a value.</span></span>
10. <span data-ttu-id="195ef-128">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="195ef-128">Select **OK**.</span></span>

## <a name="post-the-journal-transaction"></a><span data-ttu-id="195ef-129">Naplótranzakciók feladása</span><span class="sxs-lookup"><span data-stu-id="195ef-129">Post the journal transaction</span></span>

1. <span data-ttu-id="195ef-130">A navigációs ablaktáblán nyissa meg a **Modulok \> Tárgyi eszközök \> Naplóbejegyzések \> Tárgyi eszközök naplója** elemet.</span><span class="sxs-lookup"><span data-stu-id="195ef-130">In the navigation pane, go to **Modules \> Fixed assets \> Journal entries \> Fixed assets journal**.</span></span>
2. <span data-ttu-id="195ef-131">A listában válassza ki a felosztással létrehozott naplót.</span><span class="sxs-lookup"><span data-stu-id="195ef-131">In the list, select the journal created with the split process.</span></span>
3. <span data-ttu-id="195ef-132">**Sorok** kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="195ef-132">Select **Lines**.</span></span>

    - <span data-ttu-id="195ef-133">Erősítse meg a létrehozott naplósorokat.</span><span class="sxs-lookup"><span data-stu-id="195ef-133">Verify the journal lines created.</span></span>
    - <span data-ttu-id="195ef-134">Egy beszerzés-helyesbítési tranzakció jön létre az eredeti tárgyi eszközhöz az értéknek a felosztás során generált százalékkal történő csökkentéséhez.</span><span class="sxs-lookup"><span data-stu-id="195ef-134">An Acquisition adjustment transaction is created for the original asset to decrease the value by the percentage specified during the split process.</span></span>
    - <span data-ttu-id="195ef-135">Egy Beszerzési tranzakció jön létre az új eszközhöz ugyanazzal az összeggel.</span><span class="sxs-lookup"><span data-stu-id="195ef-135">An Acquisition transaction is created for the new asset for the same amount.</span></span>

4. <span data-ttu-id="195ef-136">Válassza a **Feladás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="195ef-136">Select **Post**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]