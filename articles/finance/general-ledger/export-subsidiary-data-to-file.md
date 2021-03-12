---
title: A leányvállalatok adatainak exportálása fájlokba
description: Ez a témakör bemutatja, hogy hogyan lehet előkészíteni az adatok Microsoft Dynamics 365 Finance rendszerből történő exportálását, majd egy konszolidált jogi személybe történő importálását.
author: jinniew
manager: AnnBe
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 179a401178935b8a76d6718a7fb1f63e08344f50
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4968679"
---
# <a name="export-subsidiary-data-to-files"></a><span data-ttu-id="19757-103">A leányvállalatok adatainak exportálása fájlokba</span><span class="sxs-lookup"><span data-stu-id="19757-103">Export subsidiary data to files</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="19757-104">Az **Exportálás** oldal (**Rendszerfelügyelet \> Munkaterületek \> Importálás/exportálás**) használatával előkészítheti a leányvállalatok adatainak egy olyan fájlba történő exportálását, amely később importálható egy konszolidált jogi személybe.</span><span class="sxs-lookup"><span data-stu-id="19757-104">You use the **Export** page (**System administration \> Workspaces \> Import/Export**) to prepare to export subsidiary data to files that can then be imported into a consolidated legal entity.</span></span> <span data-ttu-id="19757-105">Az importálási és exportálási folyamatokkal kapcsolatos további tudnivalókat lásd: [Adatimportálási és -exportálási feladatok áttekintése](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).</span><span class="sxs-lookup"><span data-stu-id="19757-105">For more information about the import and export processes, see [Data import and export jobs overview](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).</span></span>

1. <span data-ttu-id="19757-106">Hozzon létre egy jogi személyt a konszolidációs folyamathoz.</span><span class="sxs-lookup"><span data-stu-id="19757-106">Create a legal entity for the consolidation process.</span></span> <span data-ttu-id="19757-107">A jogi személyek létrehozásáról a [Jogi személy létrehozása](../../fin-ops-core/fin-ops/organization-administration/tasks/create-legal-entity.md) című témakörben talál információt.</span><span class="sxs-lookup"><span data-stu-id="19757-107">For information about how to create legal entities, see [Create a legal entity](../../fin-ops-core/fin-ops/organization-administration/tasks/create-legal-entity.md).</span></span> <span data-ttu-id="19757-108">A további tudnivalókat lásd: [Jogi személy előkészítése a konszolidációs folyamathoz](prepare-company-for-consolidation.md), valamint [Alárendelt jogi személy beállítása a konszolidációra](set-up-subsidiary-company-for-consolidation.md).</span><span class="sxs-lookup"><span data-stu-id="19757-108">For more information, see [Prepare a legal entity for use in the consolidation process](prepare-company-for-consolidation.md) and [Set up a subsidiary legal entity for consolidation](set-up-subsidiary-company-for-consolidation.md).</span></span> 

2. <span data-ttu-id="19757-109">Lépjen a **Konszolidációk \> Vállalati egyenlegek exportálása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="19757-109">Go to **Consolidations \> Export company balances**.</span></span> <span data-ttu-id="19757-110">Adja meg a konszolidáció részleteit a **Vállalati egyenlegek exportálása** oldal **Kritériumok** lapján a következő mezők beállításával.</span><span class="sxs-lookup"><span data-stu-id="19757-110">On the **Export company balances** page, on the **Criteria** tab, specify the details of the consolidation by setting the following fields.</span></span>

    | <span data-ttu-id="19757-111">Mező</span><span class="sxs-lookup"><span data-stu-id="19757-111">Field</span></span>                             | <span data-ttu-id="19757-112">Leírás</span><span class="sxs-lookup"><span data-stu-id="19757-112">Description</span></span> |
    |-----------------------------------|-------|
    | <span data-ttu-id="19757-113">Fő számla</span><span class="sxs-lookup"><span data-stu-id="19757-113">Main account</span></span>                      | <span data-ttu-id="19757-114">Adja meg a konszolidálni kívánt számlákat.</span><span class="sxs-lookup"><span data-stu-id="19757-114">Specify the accounts to consolidate.</span></span> <span data-ttu-id="19757-115">Ha minden számlát fel akar venni, hagyja üresen ezt a mezőt.</span><span class="sxs-lookup"><span data-stu-id="19757-115">To include all accounts, leave this field blank.</span></span> |
    | <span data-ttu-id="19757-116">Konszolidációs számla használata</span><span class="sxs-lookup"><span data-stu-id="19757-116">Use consolidation account</span></span>         | <span data-ttu-id="19757-117">Ha meghatározta a konszolidációs számlákat, állítsa ezt a beállítást **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="19757-117">If you've specified consolidation accounts, set this option to **Yes**.</span></span> |
    | <span data-ttu-id="19757-118">Konszolidációs számla kiválasztásának forrása</span><span class="sxs-lookup"><span data-stu-id="19757-118">Select consolidation account from</span></span> | <span data-ttu-id="19757-119">Válassza a **Fő számla** vagy a **Konszolidációs számlacsoport** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="19757-119">Select either **Main account** or **Consolidation account group**.</span></span> |
    | <span data-ttu-id="19757-120">Konszolidációsszámla-csoport</span><span class="sxs-lookup"><span data-stu-id="19757-120">Consolidation account group</span></span>       | <span data-ttu-id="19757-121">Válasszon ki egy konszolidációs számlacsoportot a kiválasztott konszolidációs számlához.</span><span class="sxs-lookup"><span data-stu-id="19757-121">Select a consolidation account group for the consolidation account that you selected.</span></span> |
    | <span data-ttu-id="19757-122">Konszolidációs időszak</span><span class="sxs-lookup"><span data-stu-id="19757-122">Consolidation period</span></span>              | <span data-ttu-id="19757-123">Adja meg a konszolidáció dátumtartományát.</span><span class="sxs-lookup"><span data-stu-id="19757-123">Specify "from" and "to" dates for the consolidation.</span></span> |
    | <span data-ttu-id="19757-124">Tényleges összegek belefoglalása</span><span class="sxs-lookup"><span data-stu-id="19757-124">Include actual amounts</span></span>            | <span data-ttu-id="19757-125">Tényleges összegek felvételéhez állítsa ezt a lehetőséget **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="19757-125">Set this option to **Yes** to include actual amounts.</span></span> |
    | <span data-ttu-id="19757-126">Költségvetési összegek belefoglalása</span><span class="sxs-lookup"><span data-stu-id="19757-126">Include budget amounts</span></span>            | <span data-ttu-id="19757-127">Ha költségvetési összegeket akar felvenni a konszolidációkba, állítsa ezt a lehetőséget **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="19757-127">Set this option to **Yes** to include budget amounts in consolidations.</span></span> |
    | <span data-ttu-id="19757-128">Költségvetési modellek</span><span class="sxs-lookup"><span data-stu-id="19757-128">Budget models</span></span>                     | <span data-ttu-id="19757-129">Adja meg a felvenni kívánt költségvetési modellt.</span><span class="sxs-lookup"><span data-stu-id="19757-129">Specify the budget model to include.</span></span> |

3. <span data-ttu-id="19757-130">Adja meg a konszolidáció részleteit a **Pénzügyi dimenziók** lapon:</span><span class="sxs-lookup"><span data-stu-id="19757-130">On the **Financial dimensions** tab, specify the details of the consolidation:</span></span>

    - <span data-ttu-id="19757-131">Adja meg, hogy milyen pénzügyi dimenziók adatai kerüljenek át a leányvállalati számlákról a konszolidált jogi személy tranzakcióiba.</span><span class="sxs-lookup"><span data-stu-id="19757-131">Specify the financial dimension information that should be transferred from the transactions in the subsidiary accounts to the transactions in the consolidated legal entity.</span></span>
    - <span data-ttu-id="19757-132">Válassza ki a pénzügyi dimenziókat a listából.</span><span class="sxs-lookup"><span data-stu-id="19757-132">Select financial dimensions in the list.</span></span>
    - <span data-ttu-id="19757-133">Azonosítsa a konszolidált pénzügyi dimenziók helyes meghatározását.</span><span class="sxs-lookup"><span data-stu-id="19757-133">Identify the correct specification for each financial dimension that is consolidated.</span></span> <span data-ttu-id="19757-134">A következő lehetőségek érhetők el: **Dimenzió**, **Csoportdimenzió**, **Vállalati számlák** és **Számla**.</span><span class="sxs-lookup"><span data-stu-id="19757-134">The available options include **Dimension**, **Group dimension**, **Company accounts**, and **Account**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="19757-135">A **Csoportdimenzió** beállítással definiálhatja a konszolidált vállalatcsoport által használt dimenzióértéket.</span><span class="sxs-lookup"><span data-stu-id="19757-135">The **Group dimension** option lets you define the dimension value that is used by the group of companies that is being consolidated.</span></span>

    - <span data-ttu-id="19757-136">Adja meg a konszolidálni kívánt szegmensrendelést.</span><span class="sxs-lookup"><span data-stu-id="19757-136">Specify the segment order to consolidate in.</span></span>

4. <span data-ttu-id="19757-137">A **Jogi személyek** lapon a következő lépéseket követve adja meg az exportálni kívánt jogi személyt:</span><span class="sxs-lookup"><span data-stu-id="19757-137">On the **Legal entities** tab, follow these steps to specify the legal entity that you're exporting:</span></span>

    1. <span data-ttu-id="19757-138">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="19757-138">Select **New**.</span></span>
    2. <span data-ttu-id="19757-139">A **Forrás jogi személy** mezőbe írja be a jogi személyt.</span><span class="sxs-lookup"><span data-stu-id="19757-139">In the **Source legal entity** field, enter the legal entity.</span></span>

        <span data-ttu-id="19757-140">Ha azonos adatbázisban tárolt több leányvállalatra is érvényesek ugyanazok a feltételek, akkor az ilyen leányvállalatok adatai egyetlen exportálási műveletben átvihetők külön exportfájlokba.</span><span class="sxs-lookup"><span data-stu-id="19757-140">If the same criteria apply to several subsidiaries that are in the same database, you can transfer data from those subsidiaries to separate export files in a single operation:</span></span>

        1. <span data-ttu-id="19757-141">Hozzon létre egy sort minden olyan leányvállalati jogi személynek, amelynek a számláit fájlokba fogja exportálni.</span><span class="sxs-lookup"><span data-stu-id="19757-141">Create a line for each subsidiary legal entity for which accounts should be exported to files.</span></span> <span data-ttu-id="19757-142">Ezeket a fájlokat kell majd importálni a konszolidált jogi személybe.</span><span class="sxs-lookup"><span data-stu-id="19757-142">These files will be imported into the consolidated legal entity later.</span></span>
        2. <span data-ttu-id="19757-143">Adja meg minden leányvállalat esetében a leányvállalat nevét és az exportálás során létrejövő exportfájl nevét.</span><span class="sxs-lookup"><span data-stu-id="19757-143">For each subsidiary, enter the subsidiary name and the name of the export file that will be created during the export job.</span></span>

    3. <span data-ttu-id="19757-144">Az **Átváltási különbözetek számlatípusa** mezőben válassza a **Nyereség és veszteség** vagy a **Mérleg** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="19757-144">In **Account type of conversion differences** field, Select **Profit and loss** or **Balance sheet**.</span></span>
    4. <span data-ttu-id="19757-145">Írja be a létrehozandó exportfájl nevét.</span><span class="sxs-lookup"><span data-stu-id="19757-145">Enter a file name for the export file that will be created.</span></span>

5. <span data-ttu-id="19757-146">Az exportálás futtatásához válassza az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="19757-146">Select **OK** to run the export.</span></span>

<span data-ttu-id="19757-147">Az exportálás befejeződése után a program egy üzenetben jeleníti meg, hogy hány rekordot mentett az egyes fájlokba.</span><span class="sxs-lookup"><span data-stu-id="19757-147">When the export is completed, you receive a message that shows the number of records that were saved in each file.</span></span> <span data-ttu-id="19757-148">Ezt követően importálhatja a fájlokat a konszolidált jogi személybe.</span><span class="sxs-lookup"><span data-stu-id="19757-148">You can then import the files into the consolidated legal entity.</span></span>
