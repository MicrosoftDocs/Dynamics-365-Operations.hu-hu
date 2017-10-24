--- 
title: "Pénzügyi dimenziókat adatforrásként használó jelentés futtatása elektronikus jelentéskészítéshez (ER)"
description: "A következő lépések leírják, hogy egy rendszergazda vagy az elektronikus jelentések fejlesztője szerepkörhöz hozzárendelt felhasználó miként konfigurálhat egy elektronikusjelentés-modellt (ER-modell) a pénzügyi dimenzió használatához az ER-jelentések adatforrásaként."
author: NickSelin
manager: AnnBe
ms.date: 10/14/2016
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
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: cdecf5fb3f3047a56353ee6d4a8f94957f508e4b
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="run-a-report-that-uses-financial-dimensions-as-a-data-source-for-electronic-reporting-er"></a><span data-ttu-id="62f1a-103">Pénzügyi dimenziókat adatforrásként használó jelentés futtatása elektronikus jelentéskészítéshez (ER)</span><span class="sxs-lookup"><span data-stu-id="62f1a-103">Run a report that uses financial dimensions as a data source for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="62f1a-104">A következő lépések leírják, hogy egy rendszergazda vagy az elektronikus jelentések fejlesztője szerepkörhöz hozzárendelt felhasználó miként konfigurálhat egy elektronikusjelentés-modellt (ER-modell) a pénzügyi dimenzió használatához az ER-jelentések adatforrásaként.</span><span class="sxs-lookup"><span data-stu-id="62f1a-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="62f1a-105">Ezeket a lépéseket a DEMF vállalatban hajthatja végre.</span><span class="sxs-lookup"><span data-stu-id="62f1a-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="62f1a-106">A lépések végrehajtásához először hajtsa végre az „ER Pénzügyi dimenziók használata adatforrásként (3. rész: A jelentés megtervezése)” eljárás lépéseit.</span><span class="sxs-lookup"><span data-stu-id="62f1a-106">To complete these steps, you must first complete the steps in the “ER Use financial dimensions as a data source (Part 3: Design the report)” procedure.</span></span> <span data-ttu-id="62f1a-107">Emellett az alapértelmezett dokumentumtípusokat is meg kell adni az Elektronikus jelentési paraméterek lapon.</span><span class="sxs-lookup"><span data-stu-id="62f1a-107">You must also configure default document types on the Electronic reporting parameters page.</span></span> <span data-ttu-id="62f1a-108">Az alapértelmezett dokumentumtípusok beállítása bármely ER-konfiguráció letöltésekor és importálásakor is megtörténik.</span><span class="sxs-lookup"><span data-stu-id="62f1a-108">Default document types are also set when you download and import any ER configuration.</span></span> 


## <a name="run-report"></a><span data-ttu-id="62f1a-109">Futtassa a jelentést</span><span class="sxs-lookup"><span data-stu-id="62f1a-109">Run report</span></span>
1. <span data-ttu-id="62f1a-110">Nyissa meg a következőt: Szervezeti adminisztráció > Elektronikus jelentés > Konfigurációk.</span><span class="sxs-lookup"><span data-stu-id="62f1a-110">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="62f1a-111">A fastruktúrában bontsa ki a következőt: „Pénzügyi dimenziók mintamodell”.</span><span class="sxs-lookup"><span data-stu-id="62f1a-111">In the tree, expand 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="62f1a-112">A fastruktúrában válassza ki a következőt: „Pénzügyi dimenziók mintamodell\Főkönyvi naplójelentés”.</span><span class="sxs-lookup"><span data-stu-id="62f1a-112">In the tree, select 'Financial dimensions sample model\Ledger journal report'.</span></span>
4. <span data-ttu-id="62f1a-113">Kattintson a Futtatásra.</span><span class="sxs-lookup"><span data-stu-id="62f1a-113">Click Run.</span></span>
5. <span data-ttu-id="62f1a-114">A Dimenzió neve mezőben adja meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="62f1a-114">In the Dimension name field, In the Dimension name field, enter or select a value..</span></span>
    * <span data-ttu-id="62f1a-115">Az aktuális vállalat összes dimenziójának kijelöléséhez írja be a következőt: BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span><span class="sxs-lookup"><span data-stu-id="62f1a-115">To select all dimensions in the current company, enter the following:  BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span></span>  
6. <span data-ttu-id="62f1a-116">Bontsa ki a Szerepeltetni kívánt rekordok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="62f1a-116">Expand the Records to include section.</span></span>
7. <span data-ttu-id="62f1a-117">Kattintson a Szűrő parancsra.</span><span class="sxs-lookup"><span data-stu-id="62f1a-117">Click Filter.</span></span>
8. <span data-ttu-id="62f1a-118">Jelölje ki a főkönyvi napló táblájának a sorát, és a Napló kötegszáma mezőt.</span><span class="sxs-lookup"><span data-stu-id="62f1a-118">Select the row for the Ledger journal table and the Journal batch number field.</span></span>
9. <span data-ttu-id="62f1a-119">A Feltétel mezőbe írja be a „00057” értéket.</span><span class="sxs-lookup"><span data-stu-id="62f1a-119">In the Criteria field, type '00057'.</span></span>
10. <span data-ttu-id="62f1a-120">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="62f1a-120">Click OK.</span></span>
11. <span data-ttu-id="62f1a-121">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="62f1a-121">Click OK.</span></span>
    * <span data-ttu-id="62f1a-122">Tekintse át a létrehozott kimenetet.</span><span class="sxs-lookup"><span data-stu-id="62f1a-122">Review the generated output.</span></span> <span data-ttu-id="62f1a-123">Fontos megjegyezni, hogy a kiválasztott köteg minden tranzakciójához a megfelelő dimenziók pénzügyi dimenziói jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="62f1a-123">Note that for each transaction of the selected batch, the financial dimensions from the corresponding dimensions set are presented.</span></span> <span data-ttu-id="62f1a-124">Futtassa a jelentést, és válasszon ki különböző dimenziókat annak a megtekintéséhez, hogy a jelentés nem függ a kiválasztott dimenziók, vagy a Dynamics 365 for Finance and Operations Enterprise kiadás példányhoz konfigurált dimenziók számától.</span><span class="sxs-lookup"><span data-stu-id="62f1a-124">Run this report and select different dimensions to see that the report is not dependent on the number of selected dimensions or the number of dimensions configured for this Dynamics 365 for Finance and Operations, Enterprise edition instance.</span></span>  


