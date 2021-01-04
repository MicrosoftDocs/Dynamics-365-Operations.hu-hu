---
title: ER Pénzügyi dimenziók használata adatforrásként (4. rész – A jelentés futtatása)
description: A következő lépések leírják, hogy egy rendszergazda vagy az elektronikus jelentések fejlesztője szerepkörhöz hozzárendelt felhasználó miként konfigurálhat egy elektronikusjelentés-modellt (ER-modell) a pénzügyi dimenzió használatához az ER-jelentések adatforrásaként.
author: NickSelin
manager: AnnBe
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fb7f49310aa25ff7c17ab4bcd50e1842be84fe2d
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684739"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-4---run-the-report"></a><span data-ttu-id="6d252-103">ER Pénzügyi dimenziók használata adatforrásként (4. rész – A jelentés futtatása)</span><span class="sxs-lookup"><span data-stu-id="6d252-103">ER Use financial dimensions as a data source (Part 4 - Run the report)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6d252-104">A következő lépések leírják, hogy egy rendszergazda vagy az elektronikus jelentések fejlesztője szerepkörhöz hozzárendelt felhasználó miként konfigurálhat egy elektronikusjelentés-modellt (ER-modell) a pénzügyi dimenzió használatához az ER-jelentések adatforrásaként.</span><span class="sxs-lookup"><span data-stu-id="6d252-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="6d252-105">Ezeket a lépéseket a DEMF vállalatban hajthatja végre.</span><span class="sxs-lookup"><span data-stu-id="6d252-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="6d252-106">A lépések végrehajtásához először hajtsa végre az „ER Pénzügyi dimenziók használata adatforrásként (3. rész: A jelentés megtervezése)” eljárás lépéseit.</span><span class="sxs-lookup"><span data-stu-id="6d252-106">To complete these steps, you must first complete the steps in the "ER Use financial dimensions as a data source (Part 3: Design the report)" procedure.</span></span> <span data-ttu-id="6d252-107">Emellett az alapértelmezett dokumentumtípusokat is meg kell adni az Elektronikus jelentési paraméterek lapon.</span><span class="sxs-lookup"><span data-stu-id="6d252-107">You must also configure default document types on the Electronic reporting parameters page.</span></span> <span data-ttu-id="6d252-108">Az alapértelmezett dokumentumtípusok beállítása bármely ER-konfiguráció letöltésekor és importálásakor is megtörténik.</span><span class="sxs-lookup"><span data-stu-id="6d252-108">Default document types are also set when you download and import any ER configuration.</span></span> 


## <a name="run-report"></a><span data-ttu-id="6d252-109">Futtassa a jelentést</span><span class="sxs-lookup"><span data-stu-id="6d252-109">Run report</span></span>
1. <span data-ttu-id="6d252-110">Nyissa meg a következőt: Szervezeti adminisztráció > Elektronikus jelentés > Konfigurációk.</span><span class="sxs-lookup"><span data-stu-id="6d252-110">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="6d252-111">A fastruktúrában bontsa ki a következőt: „Pénzügyi dimenziók mintamodell”.</span><span class="sxs-lookup"><span data-stu-id="6d252-111">In the tree, expand 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="6d252-112">A fastruktúrában válassza ki a következőt: „Pénzügyi dimenziók mintamodell\Főkönyvi naplójelentés”.</span><span class="sxs-lookup"><span data-stu-id="6d252-112">In the tree, select 'Financial dimensions sample model\Ledger journal report'.</span></span>
4. <span data-ttu-id="6d252-113">Kattintson a Futtatásra.</span><span class="sxs-lookup"><span data-stu-id="6d252-113">Click Run.</span></span>
<span data-ttu-id="6d252-114">![ER-konfigurációk oldal](../media/er-financial-dimensions-guides-run1.png)</span><span class="sxs-lookup"><span data-stu-id="6d252-114">![ER configurations page](../media/er-financial-dimensions-guides-run1.png)</span></span>
5. <span data-ttu-id="6d252-115">A Dimenzió mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6d252-115">In the Dimension name field, enter or select a value.</span></span>
    * <span data-ttu-id="6d252-116">Az aktuális vállalat összes dimenziójának kijelöléséhez írja be a következőt: BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span><span class="sxs-lookup"><span data-stu-id="6d252-116">To select all dimensions in the current company, enter the following information:  BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span></span>  
![ER-konfigurációk oldal](../media/er-financial-dimensions-guides-run2.png)
6. <span data-ttu-id="6d252-118">Bontsa ki a Szerepeltetni kívánt rekordok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="6d252-118">Expand the Records to include section.</span></span>
7. <span data-ttu-id="6d252-119">Kattintson a Szűrő parancsra.</span><span class="sxs-lookup"><span data-stu-id="6d252-119">Click Filter.</span></span>
8. <span data-ttu-id="6d252-120">Jelölje ki a főkönyvi napló táblájának a sorát, és a Napló kötegszáma mezőt.</span><span class="sxs-lookup"><span data-stu-id="6d252-120">Select the row for the Ledger journal table and the Journal batch number field.</span></span>
9. <span data-ttu-id="6d252-121">A Feltétel mezőbe írja be a „00057” értéket.</span><span class="sxs-lookup"><span data-stu-id="6d252-121">In the Criteria field, type '00057'.</span></span>
10. <span data-ttu-id="6d252-122">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="6d252-122">Click OK.</span></span>
11. <span data-ttu-id="6d252-123">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="6d252-123">Click OK.</span></span>
<span data-ttu-id="6d252-124">![ER-konfigurációk oldal](../media/er-financial-dimensions-guides-run3.png)</span><span class="sxs-lookup"><span data-stu-id="6d252-124">![ER configurations page](../media/er-financial-dimensions-guides-run3.png)</span></span>
    * <span data-ttu-id="6d252-125">Tekintse át a létrehozott kimenetet.</span><span class="sxs-lookup"><span data-stu-id="6d252-125">Review the generated output.</span></span> <span data-ttu-id="6d252-126">A kiválasztott köteg minden tranzakciójához a megfelelő dimenziók pénzügyi dimenziói jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="6d252-126">For each transaction of the selected batch, the financial dimensions from the corresponding dimensions set are presented.</span></span> <span data-ttu-id="6d252-127">Futtassa a jelentést, és válasszon ki különböző dimenziókat annak a megtekintéséhez, hogy a jelentés nem függ a kiválasztott dimenziók, vagy a példányhoz konfigurált dimenziók számától.</span><span class="sxs-lookup"><span data-stu-id="6d252-127">Run this report and select different dimensions to see that the report is not dependent on the number of selected dimensions or the number of dimensions configured for this instance.</span></span>  
![ER-konfigurációk oldal](../media/er-financial-dimensions-guides-run4.png)
