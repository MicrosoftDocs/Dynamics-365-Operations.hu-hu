---
title: Váltás a szállítói arculatok között
description: Ez a cikk a szállítói adatok Finance and Operations-alkalmazások és Dataverse közötti integrációjának átváltási módjáról ad felvilágosítást.
author: RamaKrishnamoorthy
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-09-20
ms.openlocfilehash: 5a18fed2eac4c120dca20a1d7797d047639275b9
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750594"
---
# <a name="switch-between-vendor-designs"></a><span data-ttu-id="c3d1a-103">Váltás a szállítói arculatok között</span><span class="sxs-lookup"><span data-stu-id="c3d1a-103">Switch between vendor designs</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



## <a name="vendor-data-flow"></a><span data-ttu-id="c3d1a-104">Szállítói adatok áramlása</span><span class="sxs-lookup"><span data-stu-id="c3d1a-104">Vendor data flow</span></span> 

<span data-ttu-id="c3d1a-105">Ha úgy dönt, hogy a **Fiók** táblát használja a **Szervezeti** típus és a **Kapcsolattartó** tábla **Személy** típusú szállítóinak tárolásához, akkor a következő munkafolyamatokat konfigurálja.</span><span class="sxs-lookup"><span data-stu-id="c3d1a-105">If you choose to use the **Account** table to store vendors of the **Organization** type and the **Contact** table to store vendors of the **Person** type, configure the following workflows.</span></span> <span data-ttu-id="c3d1a-106">Máskülönben nem szükséges ez a konfiguráció.</span><span class="sxs-lookup"><span data-stu-id="c3d1a-106">Otherwise, this configuration isn't required.</span></span>

## <a name="use-the-extended-vendor-design-for-vendors-of-the-organization-type"></a><span data-ttu-id="c3d1a-107">A kibővített szállítói kialakítás használata a Szervezet típusú szállítókhoz</span><span class="sxs-lookup"><span data-stu-id="c3d1a-107">Use the extended vendor design for vendors of the Organization type</span></span>

<span data-ttu-id="c3d1a-108">A **Dynamics365FinanceExtended** megoldáscsomag a következő munkafolyamat-feldolgozási sablonokat tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="c3d1a-108">The **Dynamics365FinanceExtended** solution package contains the following workflow process templates.</span></span> <span data-ttu-id="c3d1a-109">Minden sablonhoz létrehoz egy munkafolyamatot.</span><span class="sxs-lookup"><span data-stu-id="c3d1a-109">You will create a workflow for each template.</span></span>

+ <span data-ttu-id="c3d1a-110">Szállítók létrehozása a Partnerek táblában</span><span class="sxs-lookup"><span data-stu-id="c3d1a-110">Create Vendors in Accounts Table</span></span>
+ <span data-ttu-id="c3d1a-111">Szállítók létrehozása a Szállítók táblában</span><span class="sxs-lookup"><span data-stu-id="c3d1a-111">Create Vendors in Vendors Table</span></span>
+ <span data-ttu-id="c3d1a-112">Szállítók frissítése a Fiókok táblában</span><span class="sxs-lookup"><span data-stu-id="c3d1a-112">Update Vendors in Accounts Table</span></span>
+ <span data-ttu-id="c3d1a-113">Szállítók frissítése a Szállítók táblában</span><span class="sxs-lookup"><span data-stu-id="c3d1a-113">Update Vendors in Vendors Table</span></span>

<span data-ttu-id="c3d1a-114">A munkafolyamat-feldolgozási sablonokkal új munkafolyamat-feldolgozások létrehozásához kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="c3d1a-114">To create new workflow processes by using the workflow process templates, follow these steps.</span></span>

1. <span data-ttu-id="c3d1a-115">Hozzon létre munkafolyamat-feldolgozást a **Szállító** táblához a **Szállítók létrehozása a partnerek táblában** munkafolyamat-feldolgozási sablonban, és kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="c3d1a-115">Create a workflow process for the **Vendor** table, and select the **Create Vendors in Accounts Table** workflow process template.</span></span> <span data-ttu-id="c3d1a-116">Majd kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c3d1a-116">Then select **OK**.</span></span> <span data-ttu-id="c3d1a-117">Ez a munkafolyamat kezeli a szállító létrehozásának menetét a **Számla** táblához.</span><span class="sxs-lookup"><span data-stu-id="c3d1a-117">This workflow handles the vendor creation scenario for the **Account** table.</span></span>

    ![Szállítók létrehozása a Fiókok tábla munkafolyamatban](media/create_process.png)

2. <span data-ttu-id="c3d1a-119">Hozzon létre munkafolyamat-feldolgozást a **Szállító** táblához a **Szállítók frissítése a partnerek táblában** munkafolyamat-feldolgozási sablonban, és kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="c3d1a-119">Create a workflow process for the **Vendor** table, and select the **Update Vendors in Accounts Table** workflow process template.</span></span> <span data-ttu-id="c3d1a-120">Majd kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c3d1a-120">Then select **OK**.</span></span> <span data-ttu-id="c3d1a-121">Ez a munkafolyamat kezeli a szállító frissítésének menetét a **Számla** táblában.</span><span class="sxs-lookup"><span data-stu-id="c3d1a-121">This workflow handles the vendor update scenario for the **Account** table.</span></span>
3. <span data-ttu-id="c3d1a-122">Hozzon létre munkafolyamat-feldolgozást a **Számla** táblához a **Szállítók létrehozása a szállítók táblában** munkafolyamat-feldolgozási sablonban, és kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="c3d1a-122">Create a workflow process for the **Account** table, and select the **Create Vendors in Vendors Table** workflow process template.</span></span>
4. <span data-ttu-id="c3d1a-123">Hozzon létre munkafolyamat-feldolgozást a **Számla** táblához a **Szállítók frissítése a szállítók táblában** munkafolyamat-feldolgozási sablonban, és kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="c3d1a-123">Create a workflow process for the **Account** table, and select the **Update Vendors in Vendors Table** workflow process template.</span></span>
5. <span data-ttu-id="c3d1a-124">A munkafolyamatokat igény szerint valós idejű vagy háttérben futó munkafolyamatként állíthatja be.</span><span class="sxs-lookup"><span data-stu-id="c3d1a-124">You can configure the workflows as either real-time workflows or background workflows, depending on your requirements.</span></span> <span data-ttu-id="c3d1a-125">Ha egy munkafolyamatot háttér-munkafolyamatként szeretne beállítani, válassza az **Átalakítás háttérben futó munkafolyamattá** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c3d1a-125">To configure a workflow as a background workflow, select **Convert to a background workflow**.</span></span>

    ![Átalakítás háttérben futó munkafolyamattá gomb](media/background_workflow.png)

6. <span data-ttu-id="c3d1a-127">Aktiválja a **Fiók** és a **Szállító** táblákban létrehozott munkafolyamatokat, hogy a **Fiók** táblát használja a **Szervezet** típusú szállítókhoz.</span><span class="sxs-lookup"><span data-stu-id="c3d1a-127">Activate the workflows that you created for the **Account** and **Vendor** tables to start to use the **Account** table to store information for vendors of the **Organization** type.</span></span>

## <a name="use-the-extended-vendor-design-for-vendors-of-the-person-type"></a><span data-ttu-id="c3d1a-128">A kibővített szállítói kialakítás használata a Személy típusú szállítókhoz</span><span class="sxs-lookup"><span data-stu-id="c3d1a-128">Use the extended vendor design for vendors of the Person type</span></span>

<span data-ttu-id="c3d1a-129">A **Dynamics365FinanceExtended** megoldáscsomag a következő munkafolyamat-feldolgozási sablonokat tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="c3d1a-129">The **Dynamics365FinanceExtended** solution package contains the following workflow process templates.</span></span> <span data-ttu-id="c3d1a-130">Minden sablonhoz létrehoz egy munkafolyamatot.</span><span class="sxs-lookup"><span data-stu-id="c3d1a-130">You will create a workflow for each template.</span></span>

+ <span data-ttu-id="c3d1a-131">Személy típusú szállítók létrehozása a Szállítók táblában</span><span class="sxs-lookup"><span data-stu-id="c3d1a-131">Create Vendors of type Person in Vendors Table</span></span>
+ <span data-ttu-id="c3d1a-132">Személy típusú szállítók létrehozása a Kapcsolattartók táblában</span><span class="sxs-lookup"><span data-stu-id="c3d1a-132">Create Vendors of type Person in Contacts Table</span></span>
+ <span data-ttu-id="c3d1a-133">Személy típusú szállítók frissítése a Kapcsolattartók táblában</span><span class="sxs-lookup"><span data-stu-id="c3d1a-133">Update Vendors of type Person in Contacts Table</span></span>
+ <span data-ttu-id="c3d1a-134">Személy típusú szállítók frissítése a Szállítók táblában</span><span class="sxs-lookup"><span data-stu-id="c3d1a-134">Update Vendors of type Person in Vendors Table</span></span>

<span data-ttu-id="c3d1a-135">A munkafolyamat-feldolgozási sablonokkal új munkafolyamat-feldolgozások létrehozásához kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="c3d1a-135">To create new workflow processes by using the workflow process templates, follow these steps.</span></span>

1. <span data-ttu-id="c3d1a-136">Hozzon létre munkafolyamat-feldolgozást a **Szállító** táblához a **Személy típusú szállítók létrehozása a Kontaktok táblában** munkafolyamat-feldolgozási sablonban.</span><span class="sxs-lookup"><span data-stu-id="c3d1a-136">Create a workflow process for the **Vendor** table, and select the **Create Vendors of type Person in Contacts Table** workflow process template.</span></span> <span data-ttu-id="c3d1a-137">Majd kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c3d1a-137">Then select **OK**.</span></span> <span data-ttu-id="c3d1a-138">Ez a munkafolyamat kezeli a szállító létrehozásának menetét a **Kapcsolattartó** táblához.</span><span class="sxs-lookup"><span data-stu-id="c3d1a-138">This workflow handles the vendor creation scenario for the **Contact** table.</span></span>
2. <span data-ttu-id="c3d1a-139">Hozzon létre munkafolyamat-feldolgozást a **Szállító** táblához a **Személy típusú szállítók frissítése a Kontaktok táblában** munkafolyamat-feldolgozási sablonban.</span><span class="sxs-lookup"><span data-stu-id="c3d1a-139">Create a workflow process for the **Vendor** table, and select the **Update Vendors of type Person in Contacts Table** workflow process template.</span></span> <span data-ttu-id="c3d1a-140">Majd kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c3d1a-140">Then select **OK**.</span></span> <span data-ttu-id="c3d1a-141">Ez a munkafolyamat kezeli a szállító frissítésének menetét a **Névjegy** táblához.</span><span class="sxs-lookup"><span data-stu-id="c3d1a-141">This workflow handles the vendor update scenario for the **Contact** table.</span></span>
3. <span data-ttu-id="c3d1a-142">Hozzon létre munkafolyamat-feldolgozást a **Névjegy** táblához a **Személy típusú Szállítók létrehozása a Szállítók táblában** munkafolyamat-feldolgozási sablonban, és kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="c3d1a-142">Create a workflow process for the **Contact** table, and select the **Create Vendors of type Person in Vendors Table** template.</span></span>
4. <span data-ttu-id="c3d1a-143">Hozzon létre munkafolyamat-feldolgozást a **Névjegy** táblához a **Személy típusú Szállítók frissítése a Szállítók táblában** munkafolyamat-feldolgozási sablonban, és kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="c3d1a-143">Create a workflow process for the **Contact** table, and select the **Update Vendors of type Person in Vendors Table** template.</span></span>
5. <span data-ttu-id="c3d1a-144">A munkafolyamatokat igény szerint valós idejű vagy háttérben futó munkafolyamatként állíthatja be.</span><span class="sxs-lookup"><span data-stu-id="c3d1a-144">You can configure the workflows as either real-time workflows or background workflows, depending on your requirements.</span></span> <span data-ttu-id="c3d1a-145">Ha egy munkafolyamatot háttér-munkafolyamatként szeretne beállítani, válassza az **Átalakítás háttérben futó munkafolyamattá** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c3d1a-145">To configure a workflow as a background workflow, select **Convert to a background workflow**.</span></span>
6. <span data-ttu-id="c3d1a-146">Aktiválja a **Névjegy** és a **Szállító** táblákban létrehozott munkafolyamatokat, hogy a **Névjegy** táblát használja a **Személy** típusú szállítókhoz.</span><span class="sxs-lookup"><span data-stu-id="c3d1a-146">Activate the workflows that you created on the **Contact** and **Vendor** tables to start to use the **Contact** table to store information for vendors of the **Person** type.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]