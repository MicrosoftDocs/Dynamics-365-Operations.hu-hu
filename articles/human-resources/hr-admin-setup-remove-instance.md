---
title: Példány eltávolítása
description: Ez a cikk végigvezeti Önt a teszt- vagy éles környezet eltávolításán a Microsoft Dynamics 365 Human Resources esetében.
author: andreabichsel
manager: tfehr
ms.date: 08/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1490bd95c284b58497325e57979e63a8190cb386
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2021
ms.locfileid: "5112822"
---
# <a name="remove-an-instance"></a><span data-ttu-id="029ed-103">Példány eltávolítása</span><span class="sxs-lookup"><span data-stu-id="029ed-103">Remove an instance</span></span>

<span data-ttu-id="029ed-104">Ez a cikk végigvezeti Önt a teszt- vagy éles környezet eltávolításán a Microsoft Dynamics 365 Human Resources esetében.</span><span class="sxs-lookup"><span data-stu-id="029ed-104">This article walks you through the process of removing a test drive or production environment for Microsoft Dynamics 365 Human Resources.</span></span>

## <a name="remove-a-test-drive-environment"></a><span data-ttu-id="029ed-105">Tesztkörnyezet eltávolítása</span><span class="sxs-lookup"><span data-stu-id="029ed-105">Remove a test drive environment</span></span>

<span data-ttu-id="029ed-106">A Human Resources tesztverziói esetében 60 napos lejárati szabályt alkalmazunk.</span><span class="sxs-lookup"><span data-stu-id="029ed-106">Human Resources test drives are provisioned with a 60-day expiration policy.</span></span> <span data-ttu-id="029ed-107">A tesztkörnyezetek tulajdonosai azonban korábban is be tudják fejezni a próbaidőszakot a következő lépések végrehajtásával.</span><span class="sxs-lookup"><span data-stu-id="029ed-107">However, owners of test drive environments have the option to end their trial early by completing the following steps.</span></span> 

1. <span data-ttu-id="029ed-108">A [Power Apps Adminisztrációs központ](https://admin.businessplatform.microsoft.com/) megnyitása</span><span class="sxs-lookup"><span data-stu-id="029ed-108">Navigate to the [Power Apps Admin center](https://admin.businessplatform.microsoft.com/).</span></span>
2. <span data-ttu-id="029ed-109">Válassza a **Környezetek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="029ed-109">Select **Environments**.</span></span>
3. <span data-ttu-id="029ed-110">Válassza ki a tesztmeghajtó-környezetet, amelynek hasonló az elnevezési mintázata ehhez: TestDrive - alias@domain</span><span class="sxs-lookup"><span data-stu-id="029ed-110">Select the test drive environment, which has a naming pattern similar to this: TestDrive - alias@domain</span></span>
4. <span data-ttu-id="029ed-111">Válassza **Törlés** lehetőséget, és hagyja jóvá a döntést.</span><span class="sxs-lookup"><span data-stu-id="029ed-111">Select **Delete** and confirm the decision.</span></span> 

<span data-ttu-id="029ed-112">A meglévő tesztkörnyezetet el fogjuk távolítani.</span><span class="sxs-lookup"><span data-stu-id="029ed-112">The existing test drive environment will be removed.</span></span> <span data-ttu-id="029ed-113">Az eltávolítása után regisztráljon egy új tesztkörnyezetre.</span><span class="sxs-lookup"><span data-stu-id="029ed-113">When it is removed, you can sign up for a new test drive environment.</span></span> 

## <a name="remove-a-production-environment"></a><span data-ttu-id="029ed-114">Éles környezet eltávolítása</span><span class="sxs-lookup"><span data-stu-id="029ed-114">Remove a production environment</span></span>

<span data-ttu-id="029ed-115">Ez a cikk feltételezi, hogy a Human Resources rendszert felhőalapú szolgáltatón (CSP) keresztül vagy vállalati architektúra (EA) megállapodás részeként vásárolta.</span><span class="sxs-lookup"><span data-stu-id="029ed-115">This article assumes that you've purchased Human Resources through a Cloud Solution Provider (CSP) or an enterprise architecture (EA) agreement.</span></span> 

<span data-ttu-id="029ed-116">Mivel egyetlen Human Resources-környezet van egyetlen Power Apps környezeten belül, két lehetőséget kell figyelembe venni.</span><span class="sxs-lookup"><span data-stu-id="029ed-116">Since a single Human Resources environment is contained within a single Power Apps environment, there are two options to consider.</span></span> <span data-ttu-id="029ed-117">Az első lehetőség a teljes Power Apps környezet eltávolításával jár; a második lehetőség csak a Human Resources eltávolítását foglalja magában.</span><span class="sxs-lookup"><span data-stu-id="029ed-117">The first option involves removing the entire Power Apps environment; the second option involves removing only Human Resources.</span></span> <span data-ttu-id="029ed-118">Az első lehetőséget akkor érdemes használni, amikor a Power Apps környezetet kifejezetten a Human Resources létesítése céljából hozta létre, és csak most kezdi a végrehajtást, vagy nincs semmilyen megállapított integráció.</span><span class="sxs-lookup"><span data-stu-id="029ed-118">The first option is preferred when you have created a Power Apps environment expressly for the purpose of provisioning Human Resources, and you've just begun implementation, or you don’t have any established integrations.</span></span> <span data-ttu-id="029ed-119">A másik lehetőség csak akkor megfelelő, amikor jól beállított Power Apps környezete van multimédiás adatokkal, amelyeket a rendszer felhasznál a Power Apps és a Power Automate esetében.</span><span class="sxs-lookup"><span data-stu-id="029ed-119">The second option is appropriate when you have an established Power Apps environment populated with rich data that's leveraged in Power Apps and Power Automate.</span></span>

> [!Important]
> <span data-ttu-id="029ed-120">A Power Apps környezet eltávolítása előtt győződjön meg róla, nincs használatban gazdag adatintegrációkhoz a Human Resources alkalmazáson kívül.</span><span class="sxs-lookup"><span data-stu-id="029ed-120">Before removing the Power Apps environment, ensure it is not being used for rich data integrations outside the scope of Human Resources.</span></span> <span data-ttu-id="029ed-121">Vegye figyelembe azt is, hogy az alapértelmezett Power Apps környezeteket nem lehet eltávolítani.</span><span class="sxs-lookup"><span data-stu-id="029ed-121">Also note that the default Power Apps environments cannot be removed.</span></span> 

<span data-ttu-id="029ed-122">Ha el szeretné távolítani a teljes Power Apps környezetet, beleértve a Human Resources alkalmazást és a társított alkalmazásokat és folyamatokat:</span><span class="sxs-lookup"><span data-stu-id="029ed-122">To remove the entire Power Apps environment, including Human Resources and the associated apps and flows:</span></span>

1. <span data-ttu-id="029ed-123">A [Power Apps Adminisztrációs központ](https://admin.businessplatform.microsoft.com/) megnyitása</span><span class="sxs-lookup"><span data-stu-id="029ed-123">Navigate to the [Power Apps Admin center](https://admin.businessplatform.microsoft.com/).</span></span>
2. <span data-ttu-id="029ed-124">Válassza a **Környezetek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="029ed-124">Select **Environments**.</span></span>
3. <span data-ttu-id="029ed-125">Jelölje ki az eltávolítani kívánt környezetet.</span><span class="sxs-lookup"><span data-stu-id="029ed-125">Select the environment to be removed.</span></span>
4. <span data-ttu-id="029ed-126">Válassza **Törlés** lehetőséget, és hagyja jóvá a döntést.</span><span class="sxs-lookup"><span data-stu-id="029ed-126">Select **Delete** and confirm the decision.</span></span> 
5. <span data-ttu-id="029ed-127">Várjon, amíg be nem fejeződik a törlés.</span><span class="sxs-lookup"><span data-stu-id="029ed-127">Wait until the deletion is complete.</span></span>
6. <span data-ttu-id="029ed-128">Jelentkezzen be a [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) portálra azzal a fiókkal, amelyet a Human Resources alkalmazásra való feliratkozáshoz használt.</span><span class="sxs-lookup"><span data-stu-id="029ed-128">Sign in to [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) using the account that you used to subscribe to Human Resources.</span></span> 
7. <span data-ttu-id="029ed-129">Válassza ki a Human Resources projektet, amely tartalmazza a környezetet.</span><span class="sxs-lookup"><span data-stu-id="029ed-129">Select the Human Resources Project that contains the environment.</span></span> 
8. <span data-ttu-id="029ed-130">Az LCS-projektben válassza a **Human Resources alkalmazás kezelése** csempét.</span><span class="sxs-lookup"><span data-stu-id="029ed-130">In your LCS project, select the **Human Resources App Management** tile.</span></span> 
9. <span data-ttu-id="029ed-131">Válassza ki azt a példányt, amelyet el szeretne távolítani.</span><span class="sxs-lookup"><span data-stu-id="029ed-131">Select the instance to remove.</span></span> 
10. <span data-ttu-id="029ed-132">Válassz a **Példány eltávolítása** lehetőséget, és hagyja jóvá a döntést.</span><span class="sxs-lookup"><span data-stu-id="029ed-132">Select **Remove instance** and confirm your decision.</span></span>  

<span data-ttu-id="029ed-133">A Human Resources-környezet meglévő Power Apps környezetből való eltávolításához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="029ed-133">To remove a Human Resources environment from an existing Power Apps environment, complete the following steps.</span></span> <span data-ttu-id="029ed-134">Ne feledje, hogy a támogatás szükséges bevonása és a Human Resources DevOps csapatával való kapcsolatfelvétel csak addig ideiglenes, amíg ez a funkció nincs engedélyezve a közvetlenül az LCS-ben.</span><span class="sxs-lookup"><span data-stu-id="029ed-134">Note that the need to involve support and contact the Human Resources DevOps team is temporary until this feature is enabled directly in LCS.</span></span>

1. <span data-ttu-id="029ed-135">Forduljon a támogatáshoz eltávolítási igény kezdeményezésére.</span><span class="sxs-lookup"><span data-stu-id="029ed-135">Contact Support to initiate a removal request.</span></span>
2. <span data-ttu-id="029ed-136">A támogatási csapat eltávolítási kérelmet kezdeményez a Human Resources DevOps csapatnál.</span><span class="sxs-lookup"><span data-stu-id="029ed-136">The Support team will initiate a removal request with the Human Resources DevOps team.</span></span> 
3. <span data-ttu-id="029ed-137">Folytassa, miután értesült, hogy a környezet eltávolításra került.</span><span class="sxs-lookup"><span data-stu-id="029ed-137">Continue after you receive word that the environment has been removed.</span></span>
4. <span data-ttu-id="029ed-138">Jelentkezzen be az LCS-be azzal a fiókkal, amelyet a Human Resources alkalmazásba való feliratkozáshoz használt.</span><span class="sxs-lookup"><span data-stu-id="029ed-138">Sign in to LCS using the account that you used to subscribe to Human Resources.</span></span> 
5. <span data-ttu-id="029ed-139">Válassza ki azt a Human Resources-projektet, amely tartalmazza a környezetet.</span><span class="sxs-lookup"><span data-stu-id="029ed-139">Select the Human Resources project that contains the environment.</span></span> 
6. <span data-ttu-id="029ed-140">Az LCS-projektben válassza a **Human Resources alkalmazás kezelése** csempét.</span><span class="sxs-lookup"><span data-stu-id="029ed-140">In your LCS project, select the **Human Resources App Management** tile.</span></span> 
7. <span data-ttu-id="029ed-141">Válassza ki az eltávolítani kívánt példányt, amelynél fel kell tüntetni a telepítés állapotát **Törölt** állapottal.</span><span class="sxs-lookup"><span data-stu-id="029ed-141">Select the instance you would like to remove, which should be marked with a Deployment status of **Deleted**.</span></span>
8. <span data-ttu-id="029ed-142">Válassz a **Példány eltávolítása** lehetőséget, és hagyja jóvá a döntést.</span><span class="sxs-lookup"><span data-stu-id="029ed-142">Select **Remove instance** and confirm your decision.</span></span> 

## <a name="recover-a-soft-deleted-environment"></a><span data-ttu-id="029ed-143">A részben törölt környezet helyreállítása</span><span class="sxs-lookup"><span data-stu-id="029ed-143">Recover a soft-deleted environment</span></span>

<span data-ttu-id="029ed-144">Ha törli azt a Power Apps környezetet, amelyhez a Emberi erőforrások környezete csatlakozik, akkor a Lifecycle Services Emberi erőforrások környezetének állapota **részben törlődik**.</span><span class="sxs-lookup"><span data-stu-id="029ed-144">If you delete the Power Apps environment that your Human Resources environment is connected to, the status of the Human Resources environment in Lifecycle Services will be **Soft deleted**.</span></span> <span data-ttu-id="029ed-145">Ebben az esetben a felhasználók nem tudnak az Emberi erőforrásokhoz csatlakozni.</span><span class="sxs-lookup"><span data-stu-id="029ed-145">In this case, users can't connect to Human Resources.</span></span>

<span data-ttu-id="029ed-146">A környezet helyreállítása:</span><span class="sxs-lookup"><span data-stu-id="029ed-146">To restore the environment:</span></span>

1. <span data-ttu-id="029ed-147">Kövesse a [Power Apps környzete visszaállítása](/power-platform/admin/recover-environment.md) részben található utasításokat.</span><span class="sxs-lookup"><span data-stu-id="029ed-147">Follow the instructions in [Recover the Power Apps environment](/power-platform/admin/recover-environment.md).</span></span>

2. <span data-ttu-id="029ed-148">Az Emberi erőforrások környezet helyreállításához forduljon a támogatáshoz.</span><span class="sxs-lookup"><span data-stu-id="029ed-148">Contact Support to restore the Human Resources environment.</span></span> <span data-ttu-id="029ed-149">További információért lásd a [Támogatás kérése](hr-admin-troubleshooting-support.md) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="029ed-149">For more information, see [Get support](hr-admin-troubleshooting-support.md).</span></span>

> [!Warning]
> <span data-ttu-id="029ed-150">A Power Apps környezeteket a törlést követően csak hét napig mentik.</span><span class="sxs-lookup"><span data-stu-id="029ed-150">Power Apps environments are only saved for seven days after deletion.</span></span> <span data-ttu-id="029ed-151">A környezetet a 7 napos időszakon belül kell helyreállítania.</span><span class="sxs-lookup"><span data-stu-id="029ed-151">You must recover the environment within the seven day period.</span></span>
