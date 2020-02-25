---
title: Példány eltávolítása
description: ''
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 5c5f875ad9361c31af4fbe863488b881cdd97a6e
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009231"
---
# <a name="remove-an-instance"></a><span data-ttu-id="24995-102">Példány eltávolítása</span><span class="sxs-lookup"><span data-stu-id="24995-102">Remove an instance</span></span>

<span data-ttu-id="24995-103">Ez a cikk végigvezeti Önt a teszt- vagy éles környezet eltávolításán a Microsoft Dynamics 365 Human Resources esetében.</span><span class="sxs-lookup"><span data-stu-id="24995-103">This article walks you through the process of removing a test drive or production environment for Microsoft Dynamics 365 Human Resources.</span></span>

## <a name="remove-a-test-drive-environment"></a><span data-ttu-id="24995-104">Tesztkörnyezet eltávolítása</span><span class="sxs-lookup"><span data-stu-id="24995-104">Remove a test drive environment</span></span>

<span data-ttu-id="24995-105">A Human Resources tesztverziói esetében 60 napos lejárati szabályt alkalmazunk.</span><span class="sxs-lookup"><span data-stu-id="24995-105">Human Resources test drives are provisioned with a 60-day expiration policy.</span></span> <span data-ttu-id="24995-106">A tesztkörnyezetek tulajdonosai azonban korábban is be tudják fejezni a próbaidőszakot a következő lépések végrehajtásával.</span><span class="sxs-lookup"><span data-stu-id="24995-106">However, owners of test drive environments have the option to end their trial early by completing the following steps.</span></span> 

1. <span data-ttu-id="24995-107">A [Power Apps Adminisztrációs központ](https://admin.businessplatform.microsoft.com/) megnyitása</span><span class="sxs-lookup"><span data-stu-id="24995-107">Navigate to the [Power Apps Admin center](https://admin.businessplatform.microsoft.com/).</span></span>
2. <span data-ttu-id="24995-108">Válassza a **Környezetek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="24995-108">Select **Environments**.</span></span>
3. <span data-ttu-id="24995-109">Válassza ki a tesztmeghajtó-környezetet, amelynek hasonló az elnevezési mintázata ehhez: TestDrive - alias@domain</span><span class="sxs-lookup"><span data-stu-id="24995-109">Select the test drive environment, which has a naming pattern similar to this: TestDrive - alias@domain</span></span>
4. <span data-ttu-id="24995-110">Válassza **Törlés** lehetőséget, és hagyja jóvá a döntést.</span><span class="sxs-lookup"><span data-stu-id="24995-110">Select **Delete** and confirm the decision.</span></span> 

<span data-ttu-id="24995-111">A meglévő tesztkörnyezetet el fogjuk távolítani.</span><span class="sxs-lookup"><span data-stu-id="24995-111">The existing test drive environment will be removed.</span></span> <span data-ttu-id="24995-112">Az eltávolítása után regisztráljon egy új tesztkörnyezetre.</span><span class="sxs-lookup"><span data-stu-id="24995-112">When it is removed, you can sign up for a new test drive environment.</span></span> 

## <a name="remove-a-production-environment"></a><span data-ttu-id="24995-113">Éles környezet eltávolítása</span><span class="sxs-lookup"><span data-stu-id="24995-113">Remove a production environment</span></span>

<span data-ttu-id="24995-114">Ez a cikk feltételezi, hogy a Human Resources rendszert felhőalapú szolgáltatón (CSP) keresztül vagy vállalati architektúra (EA) megállapodás részeként vásárolta.</span><span class="sxs-lookup"><span data-stu-id="24995-114">This article assumes that you've purchased Human Resources through a Cloud Solution Provider (CSP) or an enterprise architecture (EA) agreement.</span></span> 

<span data-ttu-id="24995-115">Mivel egyetlen Human Resources-környezet van egyetlen Power Apps környezeten belül, két lehetőséget kell figyelembe venni.</span><span class="sxs-lookup"><span data-stu-id="24995-115">Since a single Human Resources environment is contained within a single Power Apps environment, there are two options to consider.</span></span> <span data-ttu-id="24995-116">Az első lehetőség a teljes Power Apps környezet eltávolításával jár; a második lehetőség csak a Human Resources eltávolítását foglalja magában.</span><span class="sxs-lookup"><span data-stu-id="24995-116">The first option involves removing the entire Power Apps environment; the second option involves removing only Human Resources.</span></span> <span data-ttu-id="24995-117">Az első lehetőséget akkor érdemes használni, amikor a Power Apps környezetet kifejezetten a Human Resources létesítése céljából hozta létre, és csak most kezdi a végrehajtást, vagy nincs semmilyen megállapított integráció.</span><span class="sxs-lookup"><span data-stu-id="24995-117">The first option is preferred when you have created a Power Apps environment expressly for the purpose of provisioning Human Resources, and you've just begun implementation, or you don’t have any established integrations.</span></span> <span data-ttu-id="24995-118">A másik lehetőség csak akkor megfelelő, amikor jól beállított Power Apps környezete van multimédiás adatokkal, amelyeket a rendszer felhasznál a Power Apps és a Power Automate esetében.</span><span class="sxs-lookup"><span data-stu-id="24995-118">The second option is appropriate when you have an established Power Apps environment populated with rich data that's leveraged in Power Apps and Power Automate.</span></span>

> [!Important]
> <span data-ttu-id="24995-119">A Power Apps környezet eltávolítása előtt győződjön meg róla, nincs használatban gazdag adatintegrációkhoz a Human Resources alkalmazáson kívül.</span><span class="sxs-lookup"><span data-stu-id="24995-119">Before removing the Power Apps environment, ensure it is not being used for rich data integrations outside the scope of Human Resources.</span></span> <span data-ttu-id="24995-120">Vegye figyelembe azt is, hogy az alapértelmezett Power Apps környezeteket nem lehet eltávolítani.</span><span class="sxs-lookup"><span data-stu-id="24995-120">Also note that the default Power Apps environments cannot be removed.</span></span> 

<span data-ttu-id="24995-121">Ha el szeretné távolítani a teljes Power Apps környezetet, beleértve a Human Resources alkalmazást és a társított alkalmazásokat és folyamatokat:</span><span class="sxs-lookup"><span data-stu-id="24995-121">To remove the entire Power Apps environment, including Human Resources and the associated apps and flows:</span></span>

1. <span data-ttu-id="24995-122">A [Power Apps Adminisztrációs központ](https://admin.businessplatform.microsoft.com/) megnyitása</span><span class="sxs-lookup"><span data-stu-id="24995-122">Navigate to the [Power Apps Admin center](https://admin.businessplatform.microsoft.com/).</span></span>
2. <span data-ttu-id="24995-123">Válassza a **Környezetek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="24995-123">Select **Environments**.</span></span>
3. <span data-ttu-id="24995-124">Jelölje ki az eltávolítani kívánt környezetet.</span><span class="sxs-lookup"><span data-stu-id="24995-124">Select the environment to be removed.</span></span>
4. <span data-ttu-id="24995-125">Válassza **Törlés** lehetőséget, és hagyja jóvá a döntést.</span><span class="sxs-lookup"><span data-stu-id="24995-125">Select **Delete** and confirm the decision.</span></span> 
5. <span data-ttu-id="24995-126">Várjon, amíg be nem fejeződik a törlés.</span><span class="sxs-lookup"><span data-stu-id="24995-126">Wait until the deletion is complete.</span></span>
6. <span data-ttu-id="24995-127">Jelentkezzen be a [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) portálra azzal a fiókkal, amelyet a Human Resources alkalmazásra való feliratkozáshoz használt.</span><span class="sxs-lookup"><span data-stu-id="24995-127">Sign in to [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) using the account that you used to subscribe to Human Resources.</span></span> 
7. <span data-ttu-id="24995-128">Válassza ki a Human Resources projektet, amely tartalmazza a környezetet.</span><span class="sxs-lookup"><span data-stu-id="24995-128">Select the Human Resources Project that contains the environment.</span></span> 
8. <span data-ttu-id="24995-129">Az LCS-projektben válassza a **Human Resources alkalmazás kezelése** csempét.</span><span class="sxs-lookup"><span data-stu-id="24995-129">In your LCS project, select the **Human Resources App Management** tile.</span></span> 
9. <span data-ttu-id="24995-130">Válassza ki azt a példányt, amelyet el szeretne távolítani.</span><span class="sxs-lookup"><span data-stu-id="24995-130">Select the instance to remove.</span></span> 
10. <span data-ttu-id="24995-131">Válassz a **Példány eltávolítása** lehetőséget, és hagyja jóvá a döntést.</span><span class="sxs-lookup"><span data-stu-id="24995-131">Select **Remove instance** and confirm your decision.</span></span>  

<span data-ttu-id="24995-132">A Human Resources-környezet meglévő Power Apps környezetből való eltávolításához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="24995-132">To remove a Human Resources environment from an existing Power Apps environment, complete the following steps.</span></span> <span data-ttu-id="24995-133">Ne feledje, hogy a támogatás szükséges bevonása és a Human Resources DevOps csapatával való kapcsolatfelvétel csak addig ideiglenes, amíg ez a funkció nincs engedélyezve a közvetlenül az LCS-ben.</span><span class="sxs-lookup"><span data-stu-id="24995-133">Note that the need to involve support and contact the Human Resources DevOps team is temporary until this feature is enabled directly in LCS.</span></span>

1. <span data-ttu-id="24995-134">Forduljon a támogatáshoz eltávolítási igény kezdeményezésére.</span><span class="sxs-lookup"><span data-stu-id="24995-134">Contact Support to initiate a removal request.</span></span>
2. <span data-ttu-id="24995-135">A támogatási csapat eltávolítási kérelmet kezdeményez a Human Resources DevOps csapatnál.</span><span class="sxs-lookup"><span data-stu-id="24995-135">The Support team will initiate a removal request with the Human Resources DevOps team.</span></span> 
3. <span data-ttu-id="24995-136">Folytassa, miután értesült, hogy a környezet eltávolításra került.</span><span class="sxs-lookup"><span data-stu-id="24995-136">Continue after you receive word that the environment has been removed.</span></span>
4.  <span data-ttu-id="24995-137">Jelentkezzen be az LCS-be azzal a fiókkal, amelyet a Human Resources alkalmazásba való feliratkozáshoz használt.</span><span class="sxs-lookup"><span data-stu-id="24995-137">Sign in to LCS using the account that you used to subscribe to Human Resources.</span></span> 
5. <span data-ttu-id="24995-138">Válassza ki azt a Human Resources-projektet, amely tartalmazza a környezetet.</span><span class="sxs-lookup"><span data-stu-id="24995-138">Select the Human Resources project that contains the environment.</span></span> 
6. <span data-ttu-id="24995-139">Az LCS-projektben válassza a **Human Resources alkalmazás kezelése** csempét.</span><span class="sxs-lookup"><span data-stu-id="24995-139">In your LCS project, select the **Human Resources App Management** tile.</span></span> 
7. <span data-ttu-id="24995-140">Válassza ki a példányt, amelyet el szeretné távolítani, amelynél fel kell tüntetni a telepítés állapotát **Nem sikerült** állapottal.</span><span class="sxs-lookup"><span data-stu-id="24995-140">Select the instance you would like to remove, which should be marked with a Deployment status of **Failed**.</span></span>
8. <span data-ttu-id="24995-141">Válassz a **Példány eltávolítása** lehetőséget, és hagyja jóvá a döntést.</span><span class="sxs-lookup"><span data-stu-id="24995-141">Select **Remove instance** and confirm your decision.</span></span> 
