---
title: ER Pénzügyi dimenziók használata adatforrásként (4. rész – A jelentés futtatása)
description: Ez a témakör azt ismerteti, hogyan kell konfigurálni egy Elektronikus jelentési (ER) modellt, amely a pénzügyi dimenziókat használja az ER-jelentések adatforrásaként. (4. rész)
author: NickSelin
manager: AnnBe
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ae7cc1a60234ef09b80950cbf0c7f18b0d65709d
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5565214"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-4---run-the-report"></a><span data-ttu-id="744e3-104">ER Pénzügyi dimenziók használata adatforrásként (4. rész – A jelentés futtatása)</span><span class="sxs-lookup"><span data-stu-id="744e3-104">ER Use financial dimensions as a data source (Part 4 - Run the report)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="744e3-105">A következő lépések leírják, hogy egy rendszergazda vagy az elektronikus jelentések fejlesztője szerepkörhöz hozzárendelt felhasználó miként konfigurálhat egy elektronikusjelentés-modellt (ER-modell) a pénzügyi dimenzió használatához az ER-jelentések adatforrásaként.</span><span class="sxs-lookup"><span data-stu-id="744e3-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="744e3-106">Ezeket a lépéseket a DEMF vállalatban hajthatja végre.</span><span class="sxs-lookup"><span data-stu-id="744e3-106">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="744e3-107">A lépések végrehajtásához először hajtsa végre az „ER Pénzügyi dimenziók használata adatforrásként (3. rész: A jelentés megtervezése)” eljárás lépéseit.</span><span class="sxs-lookup"><span data-stu-id="744e3-107">To complete these steps, you must first complete the steps in the "ER Use financial dimensions as a data source (Part 3: Design the report)" procedure.</span></span> <span data-ttu-id="744e3-108">Emellett az alapértelmezett dokumentumtípusokat is meg kell adni az Elektronikus jelentési paraméterek lapon.</span><span class="sxs-lookup"><span data-stu-id="744e3-108">You must also configure default document types on the Electronic reporting parameters page.</span></span> <span data-ttu-id="744e3-109">Az alapértelmezett dokumentumtípusok beállítása bármely ER-konfiguráció letöltésekor és importálásakor is megtörténik.</span><span class="sxs-lookup"><span data-stu-id="744e3-109">Default document types are also set when you download and import any ER configuration.</span></span> 


## <a name="run-report"></a><span data-ttu-id="744e3-110">Futtassa a jelentést</span><span class="sxs-lookup"><span data-stu-id="744e3-110">Run report</span></span>
1. <span data-ttu-id="744e3-111">Nyissa meg a következőt: Szervezeti adminisztráció > Elektronikus jelentés > Konfigurációk.</span><span class="sxs-lookup"><span data-stu-id="744e3-111">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="744e3-112">A fastruktúrában bontsa ki a következőt: „Pénzügyi dimenziók mintamodell”.</span><span class="sxs-lookup"><span data-stu-id="744e3-112">In the tree, expand 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="744e3-113">A fastruktúrában válassza ki a következőt: „Pénzügyi dimenziók mintamodell\Főkönyvi naplójelentés”.</span><span class="sxs-lookup"><span data-stu-id="744e3-113">In the tree, select 'Financial dimensions sample model\Ledger journal report'.</span></span>
4. <span data-ttu-id="744e3-114">Kattintson a Futtatásra.</span><span class="sxs-lookup"><span data-stu-id="744e3-114">Click Run.</span></span>
<span data-ttu-id="744e3-115">![ER-konfigurációk oldal](../media/er-financial-dimensions-guides-run1.png)</span><span class="sxs-lookup"><span data-stu-id="744e3-115">![ER configurations page](../media/er-financial-dimensions-guides-run1.png)</span></span>
5. <span data-ttu-id="744e3-116">A Dimenzió mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="744e3-116">In the Dimension name field, enter or select a value.</span></span>
    * <span data-ttu-id="744e3-117">Az aktuális vállalat összes dimenziójának kijelöléséhez írja be a következőt: BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span><span class="sxs-lookup"><span data-stu-id="744e3-117">To select all dimensions in the current company, enter the following information:  BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span></span>  
![ER-konfigurációk oldal](../media/er-financial-dimensions-guides-run2.png)
6. <span data-ttu-id="744e3-119">Bontsa ki a Szerepeltetni kívánt rekordok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="744e3-119">Expand the Records to include section.</span></span>
7. <span data-ttu-id="744e3-120">Kattintson a Szűrő parancsra.</span><span class="sxs-lookup"><span data-stu-id="744e3-120">Click Filter.</span></span>
8. <span data-ttu-id="744e3-121">Jelölje ki a főkönyvi napló táblájának a sorát, és a Napló kötegszáma mezőt.</span><span class="sxs-lookup"><span data-stu-id="744e3-121">Select the row for the Ledger journal table and the Journal batch number field.</span></span>
9. <span data-ttu-id="744e3-122">A Feltétel mezőbe írja be a „00057” értéket.</span><span class="sxs-lookup"><span data-stu-id="744e3-122">In the Criteria field, type '00057'.</span></span>
10. <span data-ttu-id="744e3-123">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="744e3-123">Click OK.</span></span>
11. <span data-ttu-id="744e3-124">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="744e3-124">Click OK.</span></span>
<span data-ttu-id="744e3-125">![ER-konfigurációk oldal](../media/er-financial-dimensions-guides-run3.png)</span><span class="sxs-lookup"><span data-stu-id="744e3-125">![ER configurations page](../media/er-financial-dimensions-guides-run3.png)</span></span>
    * <span data-ttu-id="744e3-126">Tekintse át a létrehozott kimenetet.</span><span class="sxs-lookup"><span data-stu-id="744e3-126">Review the generated output.</span></span> <span data-ttu-id="744e3-127">A kiválasztott köteg minden tranzakciójához a megfelelő dimenziók pénzügyi dimenziói jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="744e3-127">For each transaction of the selected batch, the financial dimensions from the corresponding dimensions set are presented.</span></span> <span data-ttu-id="744e3-128">Futtassa a jelentést, és válasszon ki különböző dimenziókat annak a megtekintéséhez, hogy a jelentés nem függ a kiválasztott dimenziók, vagy a példányhoz konfigurált dimenziók számától.</span><span class="sxs-lookup"><span data-stu-id="744e3-128">Run this report and select different dimensions to see that the report is not dependent on the number of selected dimensions or the number of dimensions configured for this instance.</span></span>  
![ER-konfigurációk oldal](../media/er-financial-dimensions-guides-run4.png)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]