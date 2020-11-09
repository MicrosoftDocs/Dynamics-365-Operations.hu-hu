---
title: Váltás a szállítói arculatok között
description: Ez a cikk a szállítói adatok Finance and Operations-alkalmazások és Common Data Service közötti integrációjának átváltási módjáról ad felvilágosítást.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-09-20
ms.openlocfilehash: 0ecc401706911f8b92146b95bb6415185df8b451
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997552"
---
# <a name="switch-between-vendor-designs"></a><span data-ttu-id="f3419-103">Váltás a szállítói arculatok között</span><span class="sxs-lookup"><span data-stu-id="f3419-103">Switch between vendor designs</span></span>

[!include [banner](../../includes/banner.md)]



## <a name="vendor-data-flow"></a><span data-ttu-id="f3419-104">Szállítói adatok áramlása</span><span class="sxs-lookup"><span data-stu-id="f3419-104">Vendor data flow</span></span> 

<span data-ttu-id="f3419-105">Ha úgy dönt, hogy a **Fiók** entitást használja a **Szervezeti** típus és a **Kapcsolattartó** entitás **Személy** típusú szállítóinak tárolásához, akkor a következő munkafolyamatokat konfigurálja.</span><span class="sxs-lookup"><span data-stu-id="f3419-105">If you choose to use the **Account** entity to store vendors of the **Organization** type and the **Contact** entity to store vendors of the **Person** type, configure the following workflows.</span></span> <span data-ttu-id="f3419-106">Máskülönben nem szükséges ez a konfiguráció.</span><span class="sxs-lookup"><span data-stu-id="f3419-106">Otherwise, this configuration isn't required.</span></span>

## <a name="use-the-extended-vendor-design-for-vendors-of-the-organization-type"></a><span data-ttu-id="f3419-107">A kibővített szállítói kialakítás használata a Szervezet típusú szállítókhoz</span><span class="sxs-lookup"><span data-stu-id="f3419-107">Use the extended vendor design for vendors of the Organization type</span></span>

<span data-ttu-id="f3419-108">A **Dynamics365FinanceExtended** megoldáscsomag a következő munkafolyamat-feldolgozási sablonokat tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="f3419-108">The **Dynamics365FinanceExtended** solution package contains the following workflow process templates.</span></span> <span data-ttu-id="f3419-109">Minden sablonhoz létrehoz egy munkafolyamatot.</span><span class="sxs-lookup"><span data-stu-id="f3419-109">You will create a workflow for each template.</span></span>

+ <span data-ttu-id="f3419-110">Szállítók létrehozása a Fiókok entitásban</span><span class="sxs-lookup"><span data-stu-id="f3419-110">Create Vendors in Accounts Entity</span></span>
+ <span data-ttu-id="f3419-111">Szállítók létrehozása a Szállítók entitásban</span><span class="sxs-lookup"><span data-stu-id="f3419-111">Create Vendors in Vendors Entity</span></span>
+ <span data-ttu-id="f3419-112">Szállítók frissítése a Fiókok entitásban</span><span class="sxs-lookup"><span data-stu-id="f3419-112">Update Vendors in Accounts Entity</span></span>
+ <span data-ttu-id="f3419-113">Szállítók frissítése a Szállítók entitásban</span><span class="sxs-lookup"><span data-stu-id="f3419-113">Update Vendors in Vendors Entity</span></span>

<span data-ttu-id="f3419-114">A munkafolyamat-feldolgozási sablonokkal új munkafolyamat-feldolgozások létrehozásához kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="f3419-114">To create new workflow processes by using the workflow process templates, follow these steps.</span></span>

1. <span data-ttu-id="f3419-115">Hozzon létre munkafolyamat-feldolgozást a **Szállító** entitáshoz a **Szállítók létrehozása a fiókentitásban** munkafolyamat-feldolgozási sablonban, és kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="f3419-115">Create a workflow process for the **Vendor** entity, and select the **Create Vendors in Accounts Entity** workflow process template.</span></span> <span data-ttu-id="f3419-116">Majd kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f3419-116">Then select **OK**.</span></span> <span data-ttu-id="f3419-117">Ez a munkafolyamat kezeli a szállító létrehozásának menetét a **Számla** entitáshoz.</span><span class="sxs-lookup"><span data-stu-id="f3419-117">This workflow handles the vendor creation scenario for the **Account** entity.</span></span>

    ![Szállítók létrehozása a Fiókok entitás munkafolyamatban](media/create_process.png)

2. <span data-ttu-id="f3419-119">Hozzon létre munkafolyamat-feldolgozást a **Szállító** entitáshoz a **Szállítók frissítése a fiókentitásban** munkafolyamat-feldolgozási sablonban, és kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="f3419-119">Create a workflow process for the **Vendor** entity, and select the **Update Vendors in Accounts Entity** workflow process template.</span></span> <span data-ttu-id="f3419-120">Majd kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f3419-120">Then select **OK**.</span></span> <span data-ttu-id="f3419-121">Ez a munkafolyamat kezeli a szállító frissítésének menetét a **Számla** entitáshoz.</span><span class="sxs-lookup"><span data-stu-id="f3419-121">This workflow handles the vendor update scenario for the **Account** entity.</span></span>
3. <span data-ttu-id="f3419-122">Hozzon létre munkafolyamat-feldolgozást a **Fiók** entitáshoz a **Szállítók létrehozása a Szállítók entitásban** munkafolyamat-feldolgozási sablonban, és kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="f3419-122">Create a workflow process for the **Account** entity, and select the **Create Vendors in Vendors Entity** workflow process template.</span></span>
4. <span data-ttu-id="f3419-123">Hozzon létre munkafolyamat-feldolgozást a **Fiók** entitáshoz a **Szállítók frissítése a Szállítók entitásban** munkafolyamat-feldolgozási sablonban.</span><span class="sxs-lookup"><span data-stu-id="f3419-123">Create a workflow process for the **Account** entity, and select the **Update Vendors in Vendors Entity** workflow process template.</span></span>
5. <span data-ttu-id="f3419-124">A munkafolyamatokat igény szerint valós idejű vagy háttérben futó munkafolyamatként állíthatja be.</span><span class="sxs-lookup"><span data-stu-id="f3419-124">You can configure the workflows as either real-time workflows or background workflows, depending on your requirements.</span></span> <span data-ttu-id="f3419-125">Ha egy munkafolyamatot háttér-munkafolyamatként szeretne beállítani, válassza az **Átalakítás háttérben futó munkafolyamattá** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f3419-125">To configure a workflow as a background workflow, select **Convert to a background workflow**.</span></span>

    ![Átalakítás háttérben futó munkafolyamattá gomb](media/background_workflow.png)

6. <span data-ttu-id="f3419-127">Aktiválja a **Fiók** és a **Szállító** entitáson létrehozott munkafolyamatokat, hogy a **Fiók** entitást használja a **Szervezet** típusú szállítókhoz.</span><span class="sxs-lookup"><span data-stu-id="f3419-127">Activate the workflows that you created for the **Account** and **Vendor** entities to start to use the **Account** entity to store information for vendors of the **Organization** type.</span></span>

## <a name="use-the-extended-vendor-design-for-vendors-of-the-person-type"></a><span data-ttu-id="f3419-128">A kibővített szállítói kialakítás használata a Személy típusú szállítókhoz</span><span class="sxs-lookup"><span data-stu-id="f3419-128">Use the extended vendor design for vendors of the Person type</span></span>

<span data-ttu-id="f3419-129">A **Dynamics365FinanceExtended** megoldáscsomag a következő munkafolyamat-feldolgozási sablonokat tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="f3419-129">The **Dynamics365FinanceExtended** solution package contains the following workflow process templates.</span></span> <span data-ttu-id="f3419-130">Minden sablonhoz létrehoz egy munkafolyamatot.</span><span class="sxs-lookup"><span data-stu-id="f3419-130">You will create a workflow for each template.</span></span>

+ <span data-ttu-id="f3419-131">Személy típusú szállítók létrehozása a Szállítók entitásban</span><span class="sxs-lookup"><span data-stu-id="f3419-131">Create Vendors of type Person in Vendors Entity</span></span>
+ <span data-ttu-id="f3419-132">Személy típusú szállítók létrehozása a Kontaktok entitásban</span><span class="sxs-lookup"><span data-stu-id="f3419-132">Create Vendors of type Person in Contacts Entity</span></span>
+ <span data-ttu-id="f3419-133">Személy típusú szállítók frissítése a Kontaktok entitásban</span><span class="sxs-lookup"><span data-stu-id="f3419-133">Update Vendors of type Person in Contacts Entity</span></span>
+ <span data-ttu-id="f3419-134">Személy típusú szállítók frissítése a Szállítók entitásban</span><span class="sxs-lookup"><span data-stu-id="f3419-134">Update Vendors of type Person in Vendors Entity</span></span>

<span data-ttu-id="f3419-135">A munkafolyamat-feldolgozási sablonokkal új munkafolyamat-feldolgozások létrehozásához kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="f3419-135">To create new workflow processes by using the workflow process templates, follow these steps.</span></span>

1. <span data-ttu-id="f3419-136">Hozzon létre munkafolyamat-feldolgozást a **Szállító** entitáshoz a **Személy típusú szállítók létrehozása a Kontaktok entitásban** munkafolyamat-feldolgozási sablonban.</span><span class="sxs-lookup"><span data-stu-id="f3419-136">Create a workflow process for the **Vendor** entity, and select the **Create Vendors of type Person in Contacts Entity** workflow process template.</span></span> <span data-ttu-id="f3419-137">Majd kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f3419-137">Then select **OK**.</span></span> <span data-ttu-id="f3419-138">Ez a munkafolyamat kezeli a szállító létrehozásának menetét a **Kapcsolattartó** entitáshoz.</span><span class="sxs-lookup"><span data-stu-id="f3419-138">This workflow handles the vendor creation scenario for the **Contact** entity.</span></span>
2. <span data-ttu-id="f3419-139">Hozzon létre munkafolyamat-feldolgozást a **Szállító** entitáshoz a **Személy típusú szállítók frissítése a Kapcsolattartók entitásban** munkafolyamat-feldolgozási sablonban.</span><span class="sxs-lookup"><span data-stu-id="f3419-139">Create a workflow process for the **Vendor** entity, and select the **Update Vendors of type Person in Contacts Entity** workflow process template.</span></span> <span data-ttu-id="f3419-140">Majd kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f3419-140">Then select **OK**.</span></span> <span data-ttu-id="f3419-141">Ez a munkafolyamat kezeli a szállító frissítésének menetét a **Névjegy** entitáshoz.</span><span class="sxs-lookup"><span data-stu-id="f3419-141">This workflow handles the vendor update scenario for the **Contact** entity.</span></span>
3. <span data-ttu-id="f3419-142">Hozzon létre munkafolyamat-feldolgozást a **Névjegy** entitáshoz a **Személy típusú Szállítók létrehozása a Szállítók entitásban** munkafolyamat-feldolgozási sablonban, és kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="f3419-142">Create a workflow process for the **Contact** entity, and select the **Create Vendors of type Person in Vendors Entity** template.</span></span>
4. <span data-ttu-id="f3419-143">Hozzon létre munkafolyamat-feldolgozást a **Névjegy** entitáshoz a **Személy típusú Szállítók frissítése a Szállítók entitásban** munkafolyamat-feldolgozási sablonban, és kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="f3419-143">Create a workflow process for the **Contact** entity, and select the **Update Vendors of type Person in Vendors Entity** template.</span></span>
5. <span data-ttu-id="f3419-144">A munkafolyamatokat igény szerint valós idejű vagy háttérben futó munkafolyamatként állíthatja be.</span><span class="sxs-lookup"><span data-stu-id="f3419-144">You can configure the workflows as either real-time workflows or background workflows, depending on your requirements.</span></span> <span data-ttu-id="f3419-145">Ha egy munkafolyamatot háttér-munkafolyamatként szeretne beállítani, válassza az **Átalakítás háttérben futó munkafolyamattá** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f3419-145">To configure a workflow as a background workflow, select **Convert to a background workflow**.</span></span>
6. <span data-ttu-id="f3419-146">Aktiválja a **Névjegy** és a **Szállító** entitáson létrehozott munkafolyamatokat, hogy a **Névjegy** entitást használja a **Személy** típusú szállítókhoz.</span><span class="sxs-lookup"><span data-stu-id="f3419-146">Activate the workflows that you created on the **Contact** and **Vendor** entities to start to use the **Contact** entity to store information for vendors of the **Person** type.</span></span>
