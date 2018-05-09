--- 
title: "Jelentés futtatása pénzügyi dimenziók adatforrásként történő használatára"
description: "A következő lépések leírják, hogy egy rendszergazda vagy az elektronikus jelentések fejlesztője szerepkörhöz hozzárendelt felhasználó miként konfigurálhat egy elektronikusjelentés-modellt (ER-modell) a pénzügyi dimenzió használatához az ER-jelentések adatforrásaként."
author: NickSelin
manager: AnnBe
ms.date: 11/02/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: fefac4db9d6fec926068483bbe8ae91a6d5d6028
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---
# <a name="run-a-report-that-uses-financial-dimensions-as-a-data-source"></a><span data-ttu-id="327ea-103">Jelentés futtatása pénzügyi dimenziók adatforrásként történő használatára</span><span class="sxs-lookup"><span data-stu-id="327ea-103">Run a report that uses financial dimensions as a data source</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="327ea-104">A következő lépések leírják, hogy egy rendszergazda vagy az elektronikus jelentések fejlesztője szerepkörhöz hozzárendelt felhasználó miként konfigurálhat egy elektronikusjelentés-modellt (ER-modell) a pénzügyi dimenzió használatához az ER-jelentések adatforrásaként.</span><span class="sxs-lookup"><span data-stu-id="327ea-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="327ea-105">Ezeket a lépéseket a DEMF vállalatban hajthatja végre.</span><span class="sxs-lookup"><span data-stu-id="327ea-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="327ea-106">A lépések végrehajtásához először hajtsa végre az „ER Pénzügyi dimenziók használata adatforrásként (3. rész: A jelentés megtervezése)” eljárás lépéseit.</span><span class="sxs-lookup"><span data-stu-id="327ea-106">To complete these steps, you must first complete the steps in the “ER Use financial dimensions as a data source (Part 3: Design the report)” procedure.</span></span> <span data-ttu-id="327ea-107">Emellett az alapértelmezett dokumentumtípusokat is meg kell adni az Elektronikus jelentési paraméterek lapon.</span><span class="sxs-lookup"><span data-stu-id="327ea-107">You must also configure default document types on the Electronic reporting parameters page.</span></span> <span data-ttu-id="327ea-108">Az alapértelmezett dokumentumtípusok beállítása bármely ER-konfiguráció letöltésekor és importálásakor is megtörténik.</span><span class="sxs-lookup"><span data-stu-id="327ea-108">Default document types are also set when you download and import any ER configuration.</span></span> 


## <a name="run-report"></a><span data-ttu-id="327ea-109">Futtassa a jelentést</span><span class="sxs-lookup"><span data-stu-id="327ea-109">Run report</span></span>
1. <span data-ttu-id="327ea-110">Nyissa meg a következőt: Szervezeti adminisztráció > Elektronikus jelentés > Konfigurációk.</span><span class="sxs-lookup"><span data-stu-id="327ea-110">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="327ea-111">A fastruktúrában bontsa ki a következőt: „Pénzügyi dimenziók mintamodell”.</span><span class="sxs-lookup"><span data-stu-id="327ea-111">In the tree, expand 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="327ea-112">A fastruktúrában válassza ki a következőt: „Pénzügyi dimenziók mintamodell\Főkönyvi naplójelentés”.</span><span class="sxs-lookup"><span data-stu-id="327ea-112">In the tree, select 'Financial dimensions sample model\Ledger journal report'.</span></span>
4. <span data-ttu-id="327ea-113">Kattintson a Futtatásra.</span><span class="sxs-lookup"><span data-stu-id="327ea-113">Click Run.</span></span>
5. <span data-ttu-id="327ea-114">A Dimenzió neve mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="327ea-114">In the Dimension name field, In the Dimension name field, enter or select a value.</span></span>
    * <span data-ttu-id="327ea-115">Az aktuális vállalat összes dimenziójának kijelöléséhez írja be a következőt: BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span><span class="sxs-lookup"><span data-stu-id="327ea-115">To select all dimensions in the current company, enter the following:  BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span></span>  
6. <span data-ttu-id="327ea-116">Bontsa ki a Szerepeltetni kívánt rekordok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="327ea-116">Expand the Records to include section.</span></span>
7. <span data-ttu-id="327ea-117">Kattintson a Szűrő parancsra.</span><span class="sxs-lookup"><span data-stu-id="327ea-117">Click Filter.</span></span>
8. <span data-ttu-id="327ea-118">Jelölje ki a főkönyvi napló táblájának a sorát, és a Napló kötegszáma mezőt.</span><span class="sxs-lookup"><span data-stu-id="327ea-118">Select the row for the Ledger journal table and the Journal batch number field.</span></span>
9. <span data-ttu-id="327ea-119">A Feltétel mezőbe írja be a „00057” értéket.</span><span class="sxs-lookup"><span data-stu-id="327ea-119">In the Criteria field, type '00057'.</span></span>
10. <span data-ttu-id="327ea-120">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="327ea-120">Click OK.</span></span>
11. <span data-ttu-id="327ea-121">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="327ea-121">Click OK.</span></span>
    * <span data-ttu-id="327ea-122">Tekintse át a létrehozott kimenetet.</span><span class="sxs-lookup"><span data-stu-id="327ea-122">Review the generated output.</span></span> <span data-ttu-id="327ea-123">Fontos megjegyezni, hogy a kiválasztott köteg minden tranzakciójához a megfelelő dimenziók pénzügyi dimenziói jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="327ea-123">Note that for each transaction of the selected batch, the financial dimensions from the corresponding dimensions set are presented.</span></span> <span data-ttu-id="327ea-124">Futtassa a jelentést, és válasszon ki különböző dimenziókat annak a megtekintéséhez, hogy a jelentés nem függ a kiválasztott dimenziók, vagy a Dynamics 365 for Finance and Operations példányhoz konfigurált dimenziók számától.</span><span class="sxs-lookup"><span data-stu-id="327ea-124">Run this report and select different dimensions to see that the report is not dependent on the number of selected dimensions or the number of dimensions configured for this Dynamics 365 for Finance and Operations instance.</span></span>  


