--- 
title: "Vízszintesen bővíthető tartományokat használó formátum futtatása oszlopok Excel-kimutatásokba történő dinamikus hozzáadásához az elektronikus jelentéskészítéshez (ER)"
description: "Az alábbi útmutató azt ismerteti, hogy a rendszergazda vagy elektronikus jelentésfejlesztői szerepkörhöz hozzárendelt felhasználó hogyan konfigurálhat elektronikus jelentési (ER) formátumot jelentések létrehozásához OPENXML munkalap (Excel) fájlok formájában, amelyekben a szükséges oszlopok vízszintesen bővíthető tartományokként, dinamikusan hozhatók létre."
author: NickSelin
manager: AnnBe
ms.date: 10/28/2016
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
ms.openlocfilehash: 8e5c53905b903bc5242625283f3b093144243cf9
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="run-a-format-that-uses-horizontally-expandable-ranges-to-dynamically-add-columns-in-excel-reports-for-electronic-reporting-er"></a><span data-ttu-id="cd5a4-103">Vízszintesen bővíthető tartományokat használó formátum futtatása oszlopok Excel-kimutatásokba történő dinamikus hozzáadásához az elektronikus jelentéskészítéshez (ER)</span><span class="sxs-lookup"><span data-stu-id="cd5a4-103">Run a format that uses horizontally-expandable ranges to dynamically add columns in Excel reports for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="cd5a4-104">Az alábbi útmutató azt ismerteti, hogy a rendszergazda vagy elektronikus jelentésfejlesztői szerepkörhöz hozzárendelt felhasználó hogyan konfigurálhat elektronikus jelentési (ER) formátumot jelentések létrehozásához OPENXML munkalap (Excel) fájlok formájában, amelyekben a szükséges oszlopok vízszintesen bővíthető tartományokként, dinamikusan hozhatók létre.</span><span class="sxs-lookup"><span data-stu-id="cd5a4-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to generate reports as OPENXML worksheets (Excel) files in which the required columns can be created dynamically as horizontally expandable ranges.</span></span> <span data-ttu-id="cd5a4-105">Ezeket a lépéseket a DEMF vállalatban hajthatja végre.</span><span class="sxs-lookup"><span data-stu-id="cd5a4-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="cd5a4-106">Ezeknek a lépéseknek a végrehajtásához először hajtsa végre az „ER Vízszintesen bővíthető tartományok használata oszlopok Excel-kimutatásokba történő dinamikus hozzáadásához (1. rész: Formátum kialakítása)” eljárás lépéseit.</span><span class="sxs-lookup"><span data-stu-id="cd5a4-106">To complete these steps, you must first complete the steps in the “ER Use horizontally expandable ranges to dynamically add columns in Excel reports (Part 1: Design format)” procedure.</span></span>

<span data-ttu-id="cd5a4-107">Ez az eljárás egy olyan funkcióra vonatkozik, amely a Dynamics 365 for Operations 1611-es verziójába került be.</span><span class="sxs-lookup"><span data-stu-id="cd5a4-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="find-created-format"></a><span data-ttu-id="cd5a4-108">Létrehozott formátum keresése</span><span class="sxs-lookup"><span data-stu-id="cd5a4-108">Find created format</span></span>
1. <span data-ttu-id="cd5a4-109">Nyissa meg a következőt: Szervezeti adminisztráció > Elektronikus jelentés > Konfigurációk.</span><span class="sxs-lookup"><span data-stu-id="cd5a4-109">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="cd5a4-110">A fastruktúrában bontsa ki a következőt: „Pénzügyi dimenziók mintamodell”.</span><span class="sxs-lookup"><span data-stu-id="cd5a4-110">In the tree, expand 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="cd5a4-111">A fastruktúrában válassza ki a következőt: „Pénzügyi dimenziók mintamodell\Mintajelentés vízszintesen bővíthető tartományokkal”.</span><span class="sxs-lookup"><span data-stu-id="cd5a4-111">In the tree, select 'Financial dimensions sample model\Sample report with horizontally expandable ranges'.</span></span>

## <a name="execute-format-to-create-excel-output"></a><span data-ttu-id="cd5a4-112">Formátum végrehajtása Excel-kimenet létrehozásához</span><span class="sxs-lookup"><span data-stu-id="cd5a4-112">Execute format to create Excel output</span></span>
1. <span data-ttu-id="cd5a4-113">Kattintson a Futtatás elemre.</span><span class="sxs-lookup"><span data-stu-id="cd5a4-113">Click Run.</span></span>
2. <span data-ttu-id="cd5a4-114">A Dimenzió neve mezőbe írja be a következőt: „BusinessUnit;CostCenter;Osztály”.</span><span class="sxs-lookup"><span data-stu-id="cd5a4-114">In the Dimension name field, type 'BusinessUnit;CostCenter;Department'.</span></span>
    * <span data-ttu-id="cd5a4-115">A Dimenzió mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="cd5a4-115">In the Dimension name field, enter or select a value.</span></span>  <span data-ttu-id="cd5a4-116">Az aktuális vállalat összes dimenziójának kijelöléséhez írja be a következőt: BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span><span class="sxs-lookup"><span data-stu-id="cd5a4-116">To select all dimensions for the current company, enter the following:  BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span></span>  
3. <span data-ttu-id="cd5a4-117">Bontsa ki a Szerepeltetni kívánt rekordok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="cd5a4-117">Expand the Records to include section.</span></span>
4. <span data-ttu-id="cd5a4-118">Kattintson a Szűrő parancsra.</span><span class="sxs-lookup"><span data-stu-id="cd5a4-118">Click Filter.</span></span>
5. <span data-ttu-id="cd5a4-119">Jelölje ki a főkönyvi napló táblájának a sorát, és a Napló kötegszáma mezőt.</span><span class="sxs-lookup"><span data-stu-id="cd5a4-119">Select the row for the Ledger journal table and the Journal batch number field.</span></span>
6. <span data-ttu-id="cd5a4-120">A Feltétel mezőbe írja be a következőt: „00057..00058”.</span><span class="sxs-lookup"><span data-stu-id="cd5a4-120">In the Criteria field, type '00057..00058'.</span></span>
    * <span data-ttu-id="cd5a4-121">00057..00058</span><span class="sxs-lookup"><span data-stu-id="cd5a4-121">00057..00058</span></span>  
7. <span data-ttu-id="cd5a4-122">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="cd5a4-122">Click OK.</span></span>
8. <span data-ttu-id="cd5a4-123">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="cd5a4-123">Click OK.</span></span>
    * <span data-ttu-id="cd5a4-124">Tekintse át a létrehozott kimenetet.</span><span class="sxs-lookup"><span data-stu-id="cd5a4-124">Review the generated output.</span></span> <span data-ttu-id="cd5a4-125">Fontos megjegyezni, hogy az újonnan létrehozott Excel-fájl a pénzügyi dimenzióknál kijelölttel azonos számú oszlopot tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="cd5a4-125">Note that the newly created Excel file contains the same number of columns that were selected for financial dimensions.</span></span> <span data-ttu-id="cd5a4-126">A jelentés fejléce az oszlopokban a pénzügyi dimenziók nevét jelöli.</span><span class="sxs-lookup"><span data-stu-id="cd5a4-126">The report header in those columns represents financial dimensions’ names.</span></span> <span data-ttu-id="cd5a4-127">A tranzakciók sorai az oszlopokban a pénzügyi dimenziókat jelölik.</span><span class="sxs-lookup"><span data-stu-id="cd5a4-127">The transactions’ lines in those columns represent financial dimensions.</span></span> <span data-ttu-id="cd5a4-128">Futtassa a jelentést, és válasszon ki különböző dimenziókat annak a megtekintéséhez, hogy a jelentés nem függ a kiválasztott dimenziók, vagy a Dynamics 365 for Finance and Operations Enterprise kiadás példányhoz konfigurált dimenziók számától.</span><span class="sxs-lookup"><span data-stu-id="cd5a4-128">Run this report and select different dimensions to see that the report is not dependent on the number of selected dimensions or the number of dimensions configured for this Dynamics 365 for Finance and Operations, Enterprise edition instance.</span></span>  

