---
title: Talent-környezetek eltávolítása
description: Ez a témakör végigvezeti Önt a teszt vagy termelési környezet eltávolításán a Microsoft Dynamics 365 Talent számára.
author: andreabichsel
manager: AnnBe
ms.date: 11/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: 17271
ms.assetid: ba1ad49d-8232-400e-b11f-525423506a3f
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2017-11-20
ms.dyn365.ops.version: Talent July 2017 update
ms.openlocfilehash: bbc65a77b7c3df6545dfd7aa2109aba5c4e1b57b
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/06/2019
ms.locfileid: "2773034"
---
# <a name="remove-talent-environments"></a><span data-ttu-id="29038-103">Talent-környezetek eltávolítása</span><span class="sxs-lookup"><span data-stu-id="29038-103">Remove Talent environments</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="29038-104">Ez a témakör végigvezeti Önt a teszt vagy termelési környezet eltávolításán a Microsoft Dynamics 365 Talent számára.</span><span class="sxs-lookup"><span data-stu-id="29038-104">This topic walks you through the process of removing a test drive or production environment for Microsoft Dynamics 365 Talent.</span></span>

## <a name="removing-a-test-drive-environment"></a><span data-ttu-id="29038-105">Tesztkörnyezet eltávolítása</span><span class="sxs-lookup"><span data-stu-id="29038-105">Removing a test drive environment</span></span>

<span data-ttu-id="29038-106">A Talent tesztverziók esetében 60 napos lejárati szabályt alkalmazunk.</span><span class="sxs-lookup"><span data-stu-id="29038-106">Talent test drives are provisioned with a 60-day expiration policy.</span></span> <span data-ttu-id="29038-107">A tesztkörnyezetek tulajdonosai azonban korábban is be tudják fejezni a próbaidőszakot a következő lépések végrehajtásával.</span><span class="sxs-lookup"><span data-stu-id="29038-107">However, owners of test drive environments have the option to end their trial early by completing the following steps.</span></span> 

1. <span data-ttu-id="29038-108">A [Power Apps Adminisztrációs központ](https://admin.businessplatform.microsoft.com/) megnyitása</span><span class="sxs-lookup"><span data-stu-id="29038-108">Navigate to the [Power Apps Admin center](https://admin.businessplatform.microsoft.com/).</span></span>
2. <span data-ttu-id="29038-109">Válassza a **Környezetek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="29038-109">Select **Environments**.</span></span>
3. <span data-ttu-id="29038-110">Válassza ki a tesztmeghajtó-környezetet, amelynek hasonló az elnevezési mintázata ehhez: TestDrive - alias@domain</span><span class="sxs-lookup"><span data-stu-id="29038-110">Select the test drive environment, which has a naming pattern similar to this: TestDrive - alias@domain</span></span>
4. <span data-ttu-id="29038-111">Válassza **Törlés** lehetőséget, és hagyja jóvá a döntést.</span><span class="sxs-lookup"><span data-stu-id="29038-111">Select **Delete** and confirm the decision.</span></span> 

<span data-ttu-id="29038-112">A meglévő tesztkörnyezetet el fogjuk távolítani.</span><span class="sxs-lookup"><span data-stu-id="29038-112">The existing test drive environment will be removed.</span></span> <span data-ttu-id="29038-113">Az eltávolítása után regisztráljon egy új tesztkörnyezetre.</span><span class="sxs-lookup"><span data-stu-id="29038-113">When it is removed, you can sign up for a new test drive environment.</span></span> 

## <a name="removing-a-production-environment"></a><span data-ttu-id="29038-114">Éles környezet eltávolítása</span><span class="sxs-lookup"><span data-stu-id="29038-114">Removing a production environment</span></span>

<span data-ttu-id="29038-115">Ez a témakör feltételezi, hogy a Talent rendszert felhőalapú szolgáltatón (CSP) keresztül vagy vállalati architektúra (EA) megállapodás részeként vásárolta.</span><span class="sxs-lookup"><span data-stu-id="29038-115">This topic assumes that you've purchased Talent through a Cloud Solution Provider (CSP) or an enterprise architecture (EA) agreement.</span></span> 

<span data-ttu-id="29038-116">Mivel egyetlen Talent környezet „van” egyetlen Power Apps környezeten belül, két beállítást kell figyelembe venni.</span><span class="sxs-lookup"><span data-stu-id="29038-116">Since a single Talent environment is “contained” within a single Power Apps environment, there are two options to consider.</span></span> <span data-ttu-id="29038-117">Az első lehetőség a teljes Power Apps környezet eltávolításával jár; a második lehetőség csak a Talent eltávolítását foglalja magában.</span><span class="sxs-lookup"><span data-stu-id="29038-117">The first option involves removing the entire Power Apps environment; the second option involves removing only Talent.</span></span> <span data-ttu-id="29038-118">Az első lehetőséget akkor érdemes használni, amikor a Power Apps környezetet kifejezetten a Talent létesítése céljából hozta létre, és csak most kezdi a végrehajtást, vagy nincs semmilyen megállapított integráció.</span><span class="sxs-lookup"><span data-stu-id="29038-118">The first option is preferred when you have created a Power Apps environment expressly for the purpose of provisioning Talent, and you've just begun implementation, or you don’t have any established integrations.</span></span> <span data-ttu-id="29038-119">A másik lehetőség csak akkor megfelelő, amikor jól beállított Power Apps környezete van multimédiás adatokkal, amelyeket a rendszer felhasznál a Power Apps és a Power Automate esetében.</span><span class="sxs-lookup"><span data-stu-id="29038-119">The second option is appropriate when you have an established Power Apps environment populated with rich data that's leveraged in Power Apps and Power Automate.</span></span>

> [!Important]
> <span data-ttu-id="29038-120">A Power Apps környezet eltávolítása előtt győződjön meg róla, nincs használatban gazdag adatintegrációkhoz a Talenten kívül.</span><span class="sxs-lookup"><span data-stu-id="29038-120">Before removing the Power Apps environment, ensure it is not being used for rich data integrations outside the scope of Talent.</span></span> <span data-ttu-id="29038-121">Vegye figyelembe azt is, hogy az alapértelmezett Power Apps környezeteket nem lehet eltávolítani.</span><span class="sxs-lookup"><span data-stu-id="29038-121">Also note that the default Power Apps environments cannot be removed.</span></span> 

<span data-ttu-id="29038-122">Ha el szeretné távolítani a teljes Power Apps környezetet, beleértve a Talent alkalmazást és a kapcsolódó alkalmazásokat és folyamatokat:</span><span class="sxs-lookup"><span data-stu-id="29038-122">To remove the entire Power Apps environment, including Talent and the associated apps and flows:</span></span>

1. <span data-ttu-id="29038-123">A [Power Apps Adminisztrációs központ](https://admin.businessplatform.microsoft.com/) megnyitása</span><span class="sxs-lookup"><span data-stu-id="29038-123">Navigate to the [Power Apps Admin center](https://admin.businessplatform.microsoft.com/).</span></span>
2. <span data-ttu-id="29038-124">Válassza a **Környezetek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="29038-124">Select **Environments**.</span></span>
3. <span data-ttu-id="29038-125">Jelölje ki az eltávolítani kívánt környezetet.</span><span class="sxs-lookup"><span data-stu-id="29038-125">Select the environment to be removed.</span></span>
4. <span data-ttu-id="29038-126">Válassza **Törlés** lehetőséget, és hagyja jóvá a döntést.</span><span class="sxs-lookup"><span data-stu-id="29038-126">Select **Delete** and confirm the decision.</span></span> 
5. <span data-ttu-id="29038-127">Várjon, amíg be nem fejeződik a törlés.</span><span class="sxs-lookup"><span data-stu-id="29038-127">Wait until the deletion is complete.</span></span>
6. <span data-ttu-id="29038-128">Jelentkezzen be az [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) portálra azzal a fiókkal, amelyet a Talentre való előfizetéshez használt.</span><span class="sxs-lookup"><span data-stu-id="29038-128">Sign in to [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) using the account that you used to subscribe to Talent.</span></span> 
7. <span data-ttu-id="29038-129">Válassza ki a Talent projektet, amely tartalmazza a környezetet.</span><span class="sxs-lookup"><span data-stu-id="29038-129">Select the Talent Project that contains the environment.</span></span> 
8. <span data-ttu-id="29038-130">Az LCS-projektben válassza a **Talent alkalmazás kezelése** csempét.</span><span class="sxs-lookup"><span data-stu-id="29038-130">In your LCS project, select the **Talent App Management** tile.</span></span> 
9. <span data-ttu-id="29038-131">Válassza ki azt a példányt, amelyet el szeretne távolítani.</span><span class="sxs-lookup"><span data-stu-id="29038-131">Select the instance to remove.</span></span> 
10. <span data-ttu-id="29038-132">Válassz a **Példány eltávolítása** lehetőséget, és hagyja jóvá a döntést.</span><span class="sxs-lookup"><span data-stu-id="29038-132">Select **Remove instance** and confirm your decision.</span></span>  

<span data-ttu-id="29038-133">A Talent környezet eltávolításához a meglévő Power Apps környezetből, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="29038-133">To remove a Talent environment from an existing Power Apps environment, complete the following steps.</span></span> <span data-ttu-id="29038-134">Ne feledje, hogy a támogatás szükséges bevonása és a Talent DevOps csapatával való kapcsolatfelvétel csak ideiglenes amíg ez a funkció nincs engedélyezve a közvetlenül az LCS-ben.</span><span class="sxs-lookup"><span data-stu-id="29038-134">Note that the need to involve support and contact the Talent DevOps team is temporary until this feature is enabled directly in LCS.</span></span>

1. <span data-ttu-id="29038-135">Forduljon a támogatáshoz eltávolítási igény kezdeményezésére.</span><span class="sxs-lookup"><span data-stu-id="29038-135">Contact Support to initiate a removal request.</span></span>
2. <span data-ttu-id="29038-136">A támogatási csapat eltávolítási kérelmet kezdeményez a Talent DevOps csoportnál.</span><span class="sxs-lookup"><span data-stu-id="29038-136">The Support team will initiate a removal request with the Talent DevOps team.</span></span> 
3. <span data-ttu-id="29038-137">Folytassa, miután értesült, hogy a környezet eltávolításra került.</span><span class="sxs-lookup"><span data-stu-id="29038-137">Continue after you receive word that the environment has been removed.</span></span>
4.  <span data-ttu-id="29038-138">Jelentkezzen be az LCS-be azzal a fiókkal, amelyet a Talentre való előfizetéshez használt.</span><span class="sxs-lookup"><span data-stu-id="29038-138">Sign in to LCS using the account that you used to subscribe to Talent.</span></span> 
5. <span data-ttu-id="29038-139">Válassza ki a Talent projektet, amely tartalmazza a környezetet.</span><span class="sxs-lookup"><span data-stu-id="29038-139">Select the Talent project that contains the environment.</span></span> 
6. <span data-ttu-id="29038-140">Az LCS-projektben válassza a **Talent alkalmazás kezelése** csempét.</span><span class="sxs-lookup"><span data-stu-id="29038-140">In your LCS project, select the **Talent App Management** tile.</span></span> 
7. <span data-ttu-id="29038-141">Válassza ki a példányt, amelyet el szeretné távolítani, amelynél fel kell tüntetni a telepítés állapotát **Nem sikerült** állapottal.</span><span class="sxs-lookup"><span data-stu-id="29038-141">Select the instance you would like to remove, which should be marked with a Deployment status of **Failed**.</span></span>
8. <span data-ttu-id="29038-142">Válassz a **Példány eltávolítása** lehetőséget, és hagyja jóvá a döntést.</span><span class="sxs-lookup"><span data-stu-id="29038-142">Select **Remove instance** and confirm your decision.</span></span> 

