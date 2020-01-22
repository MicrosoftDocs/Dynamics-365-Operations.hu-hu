---
title: Váltás a szállítói arculatok között
description: Ez a cikk a szállítói adatok Finance and Operations alkalmazások és Common Data Service közötti integrációjának átváltási módjáról ad felvilágosítást.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-09-20
ms.openlocfilehash: 204d788e72e79e7acf744d24cbeacb0f9b47da7d
ms.sourcegitcommit: 3306e451f04df01c51d8d332306b135d8ae1e254
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/09/2019
ms.locfileid: "2902725"
---
# <a name="switch-between-vendor-designs"></a><span data-ttu-id="2681c-103">Váltás a szállítói arculatok között</span><span class="sxs-lookup"><span data-stu-id="2681c-103">Switch between vendor designs</span></span>

[!include [banner](../includes/banner.md)]

## <a name="vendor-data-flow"></a><span data-ttu-id="2681c-104">Szállítói adatok áramlása</span><span class="sxs-lookup"><span data-stu-id="2681c-104">Vendor data flow</span></span> 

<span data-ttu-id="2681c-105">Ha a szállítói alapadatokhoz más Dynamics 365-alkalmazásokat szeretne használni, és el szeretné különíteni a szállítók adatait a vevőktől, akkor használhatja a szállítói alapkialakítást.</span><span class="sxs-lookup"><span data-stu-id="2681c-105">If you use other Dynamics 365 apps for vendor mastering and you want to isolate vendor information from customers, use this basic vendor design.</span></span>  

![Alapszintű szállítói folyamat](media/dual-write-vendor-data-flow.png)
 
<span data-ttu-id="2681c-107">Ha a szállítói alapadatokhoz más Dynamics 365-alkalmazásokat szeretné használni, és továbbra is a **Számla** entitást szeretné használni a szállítók adatainak tárolásához; használhatja ezt a bővített szállítói kialakítást.</span><span class="sxs-lookup"><span data-stu-id="2681c-107">If you use other Dynamics 365 apps for vendor mastering and you want to continue to use the **Account** entity for storing vendor information, use this extended vendor design.</span></span> <span data-ttu-id="2681c-108">Ebben a kialakításban a bővített szállítói adatokat, például a szállító várakoztatott állapotát vagy a szállítói profilt a **szállítók** entitásban tárolja a Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="2681c-108">In this design, extended vendor information like vendor on-hold status and vendor profile is stored in the **vendors** entity in Common Data Service.</span></span> 

![Bővített szállítói folyamat](media/dual-write-vendor-detail.jpg)
 
<span data-ttu-id="2681c-110">A bővített szállítói kialakítás használatához hajtsa végre az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="2681c-110">Follow the below steps to use the extended vendor design:</span></span> 
 
1. <span data-ttu-id="2681c-111">A **SupplyChainCommon** megoldáscsomag a következő képen látható munkafolyamat-feldolgozási sablonokat tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="2681c-111">The **SupplyChainCommon** solution package contains the workflow process templates as shown in the following image.</span></span>
    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2681c-112">![Munkafolyamat-feldolgozási sablonok](media/dual-write-switch-3.png)</span><span class="sxs-lookup"><span data-stu-id="2681c-112">![Workflow process templates](media/dual-write-switch-3.png)</span></span>
2. <span data-ttu-id="2681c-113">A munkafolyamat-feldolgozási sablonokkal hozzon létre új munkafolyamat-feldolgozásokat:</span><span class="sxs-lookup"><span data-stu-id="2681c-113">Create new workflow processes using the workflow process templates:</span></span> 
    1. <span data-ttu-id="2681c-114">Hozzon létre új munkafolyamat-feldolgozást a **Szállító** entitáshoz a **Szállítók létrehozása a számlaentitásban** munkafolyamat-feldolgozási sablonban, és kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="2681c-114">Create a new workflow process for the **Vendor** entity using the **Create Vendors in Account Entity** workflow process template and click **OK**.</span></span> <span data-ttu-id="2681c-115">Ez a munkafolyamat kezeli a szállító létrehozásának menetét a **Számla** entitáshoz.</span><span class="sxs-lookup"><span data-stu-id="2681c-115">This workflow handles the vendor creation scenario for the **Account** entity.</span></span>
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="2681c-116">![Szállítók létrehozása a számlaentitásban](media/dual-write-switch-4.png)</span><span class="sxs-lookup"><span data-stu-id="2681c-116">![Create Vendors in Account Entity](media/dual-write-switch-4.png)</span></span>
    2. <span data-ttu-id="2681c-117">Hozzon létre új munkafolyamat-feldolgozást a **Szállító** entitáshoz a **Számlák entitás frissítése** munkafolyamat-feldolgozási sablonban, és kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="2681c-117">Create a new workflow process for the **Vendor** entity using the **Update Accounts Entity** workflow process template and click **OK**.</span></span> <span data-ttu-id="2681c-118">Ez a munkafolyamat kezeli a szállító frissítésének menetét a **Számla** entitáshoz.</span><span class="sxs-lookup"><span data-stu-id="2681c-118">This workflow handles the vendor update scenario for the **Account** entity.</span></span> 
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="2681c-119">![A Számlák entitás frissítése](media/dual-write-switch-5.png)</span><span class="sxs-lookup"><span data-stu-id="2681c-119">![Update Accounts Entity](media/dual-write-switch-5.png)</span></span>
    3. <span data-ttu-id="2681c-120">Hozzon létre új munkafolyamat-feldolgozásokat a **Számlák** entitáson létrehozott sablonokból.</span><span class="sxs-lookup"><span data-stu-id="2681c-120">Create new workflow processes from the templates created on the **Accounts** entity.</span></span> 
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="2681c-121">![Szállítók létrehozása a szállítóentitásban](media/dual-write-switch-6.png)
        > </span><span class="sxs-lookup"><span data-stu-id="2681c-121">![Create vendors in vendors entity](media/dual-write-switch-6.png)
        > </span></span>[!div class="mx-imgBorder"]
<span data-ttu-id="2681c-122">![Szállítók entitásának frissítése](media/dual-write-switch-7.png)</span><span class="sxs-lookup"><span data-stu-id="2681c-122">![Update vendors entity](media/dual-write-switch-7.png)</span></span>
    4. <span data-ttu-id="2681c-123">A munkafolyamatokat igény szerint valós idejű vagy háttérben futó munkafolyamatként állíthatja be.</span><span class="sxs-lookup"><span data-stu-id="2681c-123">You can configure the workflows as real-time or background workflows based on your requirements.</span></span> 
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="2681c-124">![Átalakítás háttérben futó munkafolyamattá](media/dual-write-switch-8.png)</span><span class="sxs-lookup"><span data-stu-id="2681c-124">![Convert to a background workflow](media/dual-write-switch-8.png)</span></span>
    5. <span data-ttu-id="2681c-125">Aktiválja a **Számla** és a **Szállító** entitáson létrehozott munkafolyamatokat, hogy a **Számla** entitását használja majd a szállítói adatok tárolásához.</span><span class="sxs-lookup"><span data-stu-id="2681c-125">Activate the workflows that you created on the **Account** and **Vendor** entities to start using the **Account** entity for storing vendor information.</span></span> 
 
