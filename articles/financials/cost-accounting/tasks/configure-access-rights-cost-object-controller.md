---
title: Hozzáférési jogok konfigurálása egy költségobjektum-ellenőr számára
description: Ezzel az eljárásal konfigurálhatja a hozzáférési jogokat egy költségobjektum-ellenőr számára.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6b7018f9d4926321341af94efd13911e2c69f5f5
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1544002"
---
# <a name="configure-access-rights-for-a-cost-object-controller"></a><span data-ttu-id="3eac0-103">Hozzáférési jogok konfigurálása egy költségobjektum-ellenőr számára</span><span class="sxs-lookup"><span data-stu-id="3eac0-103">Configure access rights for a cost object controller</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3eac0-104">Ezzel az eljárásal konfigurálhatja a hozzáférési jogokat egy költségobjektum-ellenőr számára.</span><span class="sxs-lookup"><span data-stu-id="3eac0-104">Use this procedure to configure access rights for a cost object controller.</span></span> <span data-ttu-id="3eac0-105">Ez a felvétel az USP2 bemutató vállalati adatait használja.</span><span class="sxs-lookup"><span data-stu-id="3eac0-105">This recording uses the USP2 demo data company.</span></span>


## <a name="assign-the-cost-object-controller-role"></a><span data-ttu-id="3eac0-106">Költségobjektum-ellenőr szerepkör hozzárendelése</span><span class="sxs-lookup"><span data-stu-id="3eac0-106">Assign the cost object controller role</span></span>
1. <span data-ttu-id="3eac0-107">Ugrás a Rendszerfelügyelet > Felhasználók > Felhasználók elemre.</span><span class="sxs-lookup"><span data-stu-id="3eac0-107">Go to System administration > Users > Users.</span></span>
2. <span data-ttu-id="3eac0-108">Rekordok kereséséhez használja a gyorsszűrőt.</span><span class="sxs-lookup"><span data-stu-id="3eac0-108">Use the Quick Filter to find records.</span></span> <span data-ttu-id="3eac0-109">Például szűkítsen a Felhasználónév mezőben az „aliz” szót beírva.</span><span class="sxs-lookup"><span data-stu-id="3eac0-109">For example, filter on the User name field with a value of 'alicia'.</span></span>
3. <span data-ttu-id="3eac0-110">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="3eac0-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="3eac0-111">Kattintson a Szerepkörök hozzárendelése elemre.</span><span class="sxs-lookup"><span data-stu-id="3eac0-111">Click Assign roles.</span></span>
5. <span data-ttu-id="3eac0-112">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="3eac0-112">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="3eac0-113">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="3eac0-113">Click OK.</span></span>

## <a name="enable-access-list-security"></a><span data-ttu-id="3eac0-114">Hozzáférési lista biztonságának engedélyezése</span><span class="sxs-lookup"><span data-stu-id="3eac0-114">Enable access list security</span></span>
1. <span data-ttu-id="3eac0-115">Lépjen a Költségkönyvelés > Dimenziók > Dimenzióhierarchiák pontra.</span><span class="sxs-lookup"><span data-stu-id="3eac0-115">Go to Cost accounting > Dimensions > Dimension hierarchies.</span></span>
2. <span data-ttu-id="3eac0-116">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="3eac0-116">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="3eac0-117">Válassza ki a szervezetet.</span><span class="sxs-lookup"><span data-stu-id="3eac0-117">Select Organization.</span></span>  
3. <span data-ttu-id="3eac0-118">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3eac0-118">Click Edit.</span></span>
4. <span data-ttu-id="3eac0-119">A Hozzáférési lista hierarchia mezőben válassza az Igen lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3eac0-119">Select Yes in the Access list hierarchy field.</span></span>
5. <span data-ttu-id="3eac0-120">Kattintson a Hierarchia megtekintése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3eac0-120">Click View hierarchy.</span></span>

## <a name="assign-access-rights-to-user"></a><span data-ttu-id="3eac0-121">Hozzáférési jogok hozzárendelése a felhasználóhoz</span><span class="sxs-lookup"><span data-stu-id="3eac0-121">Assign access rights to user</span></span>
1. <span data-ttu-id="3eac0-122">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3eac0-122">Click New.</span></span>
2. <span data-ttu-id="3eac0-123">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="3eac0-123">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="3eac0-124">A Felhasználói azonosító mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="3eac0-124">In the User ID field, enter or select a value.</span></span>
    * <span data-ttu-id="3eac0-125">Válassza a Rendszergazda lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3eac0-125">Select Admin.</span></span>  
4. <span data-ttu-id="3eac0-126">A fán válassza a Szervezet>Vezérigazgató>Pénzügyi igazgató>FIM lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3eac0-126">In the tree, select 'Organization\CEO\CFO\FIM'.</span></span>
5. <span data-ttu-id="3eac0-127">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3eac0-127">Click New.</span></span>
6. <span data-ttu-id="3eac0-128">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="3eac0-128">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="3eac0-129">A Felhasználói azonosító mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="3eac0-129">In the User ID field, enter or select a value.</span></span>
    * <span data-ttu-id="3eac0-130">Válassza ki az Aliz lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3eac0-130">Select Alicia.</span></span>  
8. <span data-ttu-id="3eac0-131">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="3eac0-131">Click Save.</span></span>

## <a name="enable-access-rights-in-cost-accounting"></a><span data-ttu-id="3eac0-132">Hozzáférési jogok engedélyezése a Költségkönyvelésben</span><span class="sxs-lookup"><span data-stu-id="3eac0-132">Enable access rights in Cost accounting</span></span>
1. <span data-ttu-id="3eac0-133">Lépjen a Költségkönyvelés > Beállítás > Paraméterek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3eac0-133">Go to Cost accounting > Setup > Parameters.</span></span>
2. <span data-ttu-id="3eac0-134">Kattintson az Általános fülre.</span><span class="sxs-lookup"><span data-stu-id="3eac0-134">Click the General tab.</span></span>
3. <span data-ttu-id="3eac0-135">Válassza az Igen lehetőséget ki a Költségobjektumdimenzió-tagok megtekintési hozzáférésének engedélyezése mezőben.</span><span class="sxs-lookup"><span data-stu-id="3eac0-135">Select Yes in the Enable view access for cost object dimension members field.</span></span>
4. <span data-ttu-id="3eac0-136">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="3eac0-136">Click Save.</span></span>
5. <span data-ttu-id="3eac0-137">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="3eac0-137">Close the page.</span></span>
6. <span data-ttu-id="3eac0-138">Lépjen a Költségkönyvelés > Beállítás > Költségellenőrzési munkaterület konfigurációja lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3eac0-138">Go to Cost accounting > Setup > Cost control workspace configuration.</span></span>
7. <span data-ttu-id="3eac0-139">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3eac0-139">Click Edit.</span></span>
8. <span data-ttu-id="3eac0-140">Válassza az Igen lehetőséget a Közzétéve mezőben.</span><span class="sxs-lookup"><span data-stu-id="3eac0-140">Select Yes in the Published field.</span></span>
    * <span data-ttu-id="3eac0-141">Ha Igen értékre állítja ezt a beállítást, a következő négy szerepkör valamelyikéhez hozzárendelt felhasználó láthatja a Költség-ellenőrzési munkaterület jelentéseit: költségkönyvelés-kezelő, költségkönyvelő, költségkönyvelő adminisztrátor vagy költségobjektum-ellenőr.</span><span class="sxs-lookup"><span data-stu-id="3eac0-141">If you select Yes, a user who is assigned one of the following four roles can see the reports in the Cost control workspace: cost accounting manager, cost accountant, cost accountant clerk, and cost object controller.</span></span> <span data-ttu-id="3eac0-142">Ha Nem értékre állítja ezt a beállítást, a következő szerepkörök valamelyikéhez hozzárendelt felhasználó láthatja a jelentéseket: költségkönyvelés-kezelő, költségkönyvelő és költségkönyvelő adminisztrátor.</span><span class="sxs-lookup"><span data-stu-id="3eac0-142">If you select No, only a user who is assigned one of the following roles can see the reports: cost accounting manager, cost accountant, and cost accountant clerk.</span></span>    
9. <span data-ttu-id="3eac0-143">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="3eac0-143">Click Save.</span></span>

