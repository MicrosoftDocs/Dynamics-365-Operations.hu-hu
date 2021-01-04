---
title: Váltás a szállítói arculatok között
description: Ez a cikk a szállítói adatok Finance and Operations-alkalmazások és Dataverse közötti integrációjának átváltási módjáról ad felvilágosítást.
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
ms.openlocfilehash: 731efd3ae841960f3a2c0b9be210c5c68ac835f5
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685509"
---
# <a name="switch-between-vendor-designs"></a><span data-ttu-id="87792-103">Váltás a szállítói arculatok között</span><span class="sxs-lookup"><span data-stu-id="87792-103">Switch between vendor designs</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



## <a name="vendor-data-flow"></a><span data-ttu-id="87792-104">Szállítói adatok áramlása</span><span class="sxs-lookup"><span data-stu-id="87792-104">Vendor data flow</span></span> 

<span data-ttu-id="87792-105">Ha úgy dönt, hogy a **Fiók** entitást használja a **Szervezeti** típus és a **Kapcsolattartó** entitás **Személy** típusú szállítóinak tárolásához, akkor a következő munkafolyamatokat konfigurálja.</span><span class="sxs-lookup"><span data-stu-id="87792-105">If you choose to use the **Account** entity to store vendors of the **Organization** type and the **Contact** entity to store vendors of the **Person** type, configure the following workflows.</span></span> <span data-ttu-id="87792-106">Máskülönben nem szükséges ez a konfiguráció.</span><span class="sxs-lookup"><span data-stu-id="87792-106">Otherwise, this configuration isn't required.</span></span>

## <a name="use-the-extended-vendor-design-for-vendors-of-the-organization-type"></a><span data-ttu-id="87792-107">A kibővített szállítói kialakítás használata a Szervezet típusú szállítókhoz</span><span class="sxs-lookup"><span data-stu-id="87792-107">Use the extended vendor design for vendors of the Organization type</span></span>

<span data-ttu-id="87792-108">A **Dynamics365FinanceExtended** megoldáscsomag a következő munkafolyamat-feldolgozási sablonokat tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="87792-108">The **Dynamics365FinanceExtended** solution package contains the following workflow process templates.</span></span> <span data-ttu-id="87792-109">Minden sablonhoz létrehoz egy munkafolyamatot.</span><span class="sxs-lookup"><span data-stu-id="87792-109">You will create a workflow for each template.</span></span>

+ <span data-ttu-id="87792-110">Szállítók létrehozása a Partnerek táblában</span><span class="sxs-lookup"><span data-stu-id="87792-110">Create Vendors in Accounts Table</span></span>
+ <span data-ttu-id="87792-111">Szállítók létrehozása a Szállítók táblában</span><span class="sxs-lookup"><span data-stu-id="87792-111">Create Vendors in Vendors Table</span></span>
+ <span data-ttu-id="87792-112">Szállítók frissítése a Fiókok táblában</span><span class="sxs-lookup"><span data-stu-id="87792-112">Update Vendors in Accounts Table</span></span>
+ <span data-ttu-id="87792-113">Szállítók frissítése a Szállítók táblában</span><span class="sxs-lookup"><span data-stu-id="87792-113">Update Vendors in Vendors Table</span></span>

<span data-ttu-id="87792-114">A munkafolyamat-feldolgozási sablonokkal új munkafolyamat-feldolgozások létrehozásához kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="87792-114">To create new workflow processes by using the workflow process templates, follow these steps.</span></span>

1. <span data-ttu-id="87792-115">Hozzon létre munkafolyamat-feldolgozást a **Szállító** entitáshoz a **Szállítók létrehozása a partnerek táblában** munkafolyamat-feldolgozási sablonban, és kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="87792-115">Create a workflow process for the **Vendor** entity, and select the **Create Vendors in Accounts Table** workflow process template.</span></span> <span data-ttu-id="87792-116">Majd kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="87792-116">Then select **OK**.</span></span> <span data-ttu-id="87792-117">Ez a munkafolyamat kezeli a szállító létrehozásának menetét a **Számla** entitáshoz.</span><span class="sxs-lookup"><span data-stu-id="87792-117">This workflow handles the vendor creation scenario for the **Account** entity.</span></span>

    ![Szállítók létrehozása a Fiókok tábla munkafolyamatban](media/create_process.png)

2. <span data-ttu-id="87792-119">Hozzon létre munkafolyamat-feldolgozást a **Szállító** entitáshoz a **Szállítók frissítése a partnerek táblában** munkafolyamat-feldolgozási sablonban, és kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="87792-119">Create a workflow process for the **Vendor** entity, and select the **Update Vendors in Accounts Table** workflow process template.</span></span> <span data-ttu-id="87792-120">Majd kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="87792-120">Then select **OK**.</span></span> <span data-ttu-id="87792-121">Ez a munkafolyamat kezeli a szállító frissítésének menetét a **Számla** entitáshoz.</span><span class="sxs-lookup"><span data-stu-id="87792-121">This workflow handles the vendor update scenario for the **Account** entity.</span></span>
3. <span data-ttu-id="87792-122">Hozzon létre munkafolyamat-feldolgozást a **Partner** entitáshoz a **Szállítók létrehozása a szállítók táblában** munkafolyamat-feldolgozási sablonban, és kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="87792-122">Create a workflow process for the **Account** entity, and select the **Create Vendors in Vendors Table** workflow process template.</span></span>
4. <span data-ttu-id="87792-123">Hozzon létre munkafolyamat-feldolgozást a **Partner** entitáshoz a **Szállítók frissítése a szállítók táblában** munkafolyamat-feldolgozási sablonban, és kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="87792-123">Create a workflow process for the **Account** entity, and select the **Update Vendors in Vendors Table** workflow process template.</span></span>
5. <span data-ttu-id="87792-124">A munkafolyamatokat igény szerint valós idejű vagy háttérben futó munkafolyamatként állíthatja be.</span><span class="sxs-lookup"><span data-stu-id="87792-124">You can configure the workflows as either real-time workflows or background workflows, depending on your requirements.</span></span> <span data-ttu-id="87792-125">Ha egy munkafolyamatot háttér-munkafolyamatként szeretne beállítani, válassza az **Átalakítás háttérben futó munkafolyamattá** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87792-125">To configure a workflow as a background workflow, select **Convert to a background workflow**.</span></span>

    ![Átalakítás háttérben futó munkafolyamattá gomb](media/background_workflow.png)

6. <span data-ttu-id="87792-127">Aktiválja a **Fiók** és a **Szállító** táblákban létrehozott munkafolyamatokat, hogy a **Fiók** entitást használja a **Szervezet** típusú szállítókhoz.</span><span class="sxs-lookup"><span data-stu-id="87792-127">Activate the workflows that you created for the **Account** and **Vendor** tables to start to use the **Account** entity to store information for vendors of the **Organization** type.</span></span>

## <a name="use-the-extended-vendor-design-for-vendors-of-the-person-type"></a><span data-ttu-id="87792-128">A kibővített szállítói kialakítás használata a Személy típusú szállítókhoz</span><span class="sxs-lookup"><span data-stu-id="87792-128">Use the extended vendor design for vendors of the Person type</span></span>

<span data-ttu-id="87792-129">A **Dynamics365FinanceExtended** megoldáscsomag a következő munkafolyamat-feldolgozási sablonokat tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="87792-129">The **Dynamics365FinanceExtended** solution package contains the following workflow process templates.</span></span> <span data-ttu-id="87792-130">Minden sablonhoz létrehoz egy munkafolyamatot.</span><span class="sxs-lookup"><span data-stu-id="87792-130">You will create a workflow for each template.</span></span>

+ <span data-ttu-id="87792-131">Személy típusú szállítók létrehozása a Szállítók táblában</span><span class="sxs-lookup"><span data-stu-id="87792-131">Create Vendors of type Person in Vendors Table</span></span>
+ <span data-ttu-id="87792-132">Személy típusú szállítók létrehozása a Kapcsolattartók táblában</span><span class="sxs-lookup"><span data-stu-id="87792-132">Create Vendors of type Person in Contacts Table</span></span>
+ <span data-ttu-id="87792-133">Személy típusú szállítók frissítése a Kapcsolattartók táblában</span><span class="sxs-lookup"><span data-stu-id="87792-133">Update Vendors of type Person in Contacts Table</span></span>
+ <span data-ttu-id="87792-134">Személy típusú szállítók frissítése a Szállítók táblában</span><span class="sxs-lookup"><span data-stu-id="87792-134">Update Vendors of type Person in Vendors Table</span></span>

<span data-ttu-id="87792-135">A munkafolyamat-feldolgozási sablonokkal új munkafolyamat-feldolgozások létrehozásához kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="87792-135">To create new workflow processes by using the workflow process templates, follow these steps.</span></span>

1. <span data-ttu-id="87792-136">Hozzon létre munkafolyamat-feldolgozást a **Szállító** entitáshoz a **Személy típusú szállítók létrehozása a Kontaktok táblában** munkafolyamat-feldolgozási sablonban.</span><span class="sxs-lookup"><span data-stu-id="87792-136">Create a workflow process for the **Vendor** entity, and select the **Create Vendors of type Person in Contacts Table** workflow process template.</span></span> <span data-ttu-id="87792-137">Majd kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="87792-137">Then select **OK**.</span></span> <span data-ttu-id="87792-138">Ez a munkafolyamat kezeli a szállító létrehozásának menetét a **Kapcsolattartó** entitáshoz.</span><span class="sxs-lookup"><span data-stu-id="87792-138">This workflow handles the vendor creation scenario for the **Contact** entity.</span></span>
2. <span data-ttu-id="87792-139">Hozzon létre munkafolyamat-feldolgozást a **Szállító** entitáshoz a **Személy típusú szállítók frissítése a Kontaktok táblában** munkafolyamat-feldolgozási sablonban.</span><span class="sxs-lookup"><span data-stu-id="87792-139">Create a workflow process for the **Vendor** entity, and select the **Update Vendors of type Person in Contacts Table** workflow process template.</span></span> <span data-ttu-id="87792-140">Majd kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="87792-140">Then select **OK**.</span></span> <span data-ttu-id="87792-141">Ez a munkafolyamat kezeli a szállító frissítésének menetét a **Névjegy** entitáshoz.</span><span class="sxs-lookup"><span data-stu-id="87792-141">This workflow handles the vendor update scenario for the **Contact** entity.</span></span>
3. <span data-ttu-id="87792-142">Hozzon létre munkafolyamat-feldolgozást a **Névjegy** entitáshoz a **Személy típusú Szállítók létrehozása a Szállítók táblában** munkafolyamat-feldolgozási sablonban, és kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="87792-142">Create a workflow process for the **Contact** entity, and select the **Create Vendors of type Person in Vendors Table** template.</span></span>
4. <span data-ttu-id="87792-143">Hozzon létre munkafolyamat-feldolgozást a **Névjegy** entitáshoz a **Személy típusú Szállítók frissítése a Szállítók táblában** munkafolyamat-feldolgozási sablonban, és kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="87792-143">Create a workflow process for the **Contact** entity, and select the **Update Vendors of type Person in Vendors Table** template.</span></span>
5. <span data-ttu-id="87792-144">A munkafolyamatokat igény szerint valós idejű vagy háttérben futó munkafolyamatként állíthatja be.</span><span class="sxs-lookup"><span data-stu-id="87792-144">You can configure the workflows as either real-time workflows or background workflows, depending on your requirements.</span></span> <span data-ttu-id="87792-145">Ha egy munkafolyamatot háttér-munkafolyamatként szeretne beállítani, válassza az **Átalakítás háttérben futó munkafolyamattá** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87792-145">To configure a workflow as a background workflow, select **Convert to a background workflow**.</span></span>
6. <span data-ttu-id="87792-146">Aktiválja a **Névjegy** és a **Szállító** táblákban létrehozott munkafolyamatokat, hogy a **Névjegy** entitást használja a **Személy** típusú szállítókhoz.</span><span class="sxs-lookup"><span data-stu-id="87792-146">Activate the workflows that you created on the **Contact** and **Vendor** tables to start to use the **Contact** entity to store information for vendors of the **Person** type.</span></span>
