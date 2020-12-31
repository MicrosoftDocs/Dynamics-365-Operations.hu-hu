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
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a4b50782c7a1b69b6953c65d6df155f003028333
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444127"
---
# <a name="configure-access-rights-for-a-cost-object-controller"></a><span data-ttu-id="9354c-103">Hozzáférési jogok konfigurálása egy költségobjektum-ellenőr számára</span><span class="sxs-lookup"><span data-stu-id="9354c-103">Configure access rights for a cost object controller</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9354c-104">Ezzel az eljárásal konfigurálhatja a hozzáférési jogokat egy költségobjektum-ellenőr számára.</span><span class="sxs-lookup"><span data-stu-id="9354c-104">Use this procedure to configure access rights for a cost object controller.</span></span> <span data-ttu-id="9354c-105">Ez a felvétel az USP2 bemutató vállalati adatait használja.</span><span class="sxs-lookup"><span data-stu-id="9354c-105">This recording uses the USP2 demo data company.</span></span>


## <a name="assign-the-cost-object-controller-role"></a><span data-ttu-id="9354c-106">Költségobjektum-ellenőr szerepkör hozzárendelése</span><span class="sxs-lookup"><span data-stu-id="9354c-106">Assign the cost object controller role</span></span>
1. <span data-ttu-id="9354c-107">Ugrás a Rendszerfelügyelet > Felhasználók > Felhasználók elemre.</span><span class="sxs-lookup"><span data-stu-id="9354c-107">Go to System administration > Users > Users.</span></span>
2. <span data-ttu-id="9354c-108">Rekordok kereséséhez használja a gyorsszűrőt.</span><span class="sxs-lookup"><span data-stu-id="9354c-108">Use the Quick Filter to find records.</span></span> <span data-ttu-id="9354c-109">Például szűkítsen a Felhasználónév mezőben az „aliz” szót beírva.</span><span class="sxs-lookup"><span data-stu-id="9354c-109">For example, filter on the User name field with a value of 'alicia'.</span></span>
3. <span data-ttu-id="9354c-110">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="9354c-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="9354c-111">Kattintson a Szerepkörök hozzárendelése elemre.</span><span class="sxs-lookup"><span data-stu-id="9354c-111">Click Assign roles.</span></span>
5. <span data-ttu-id="9354c-112">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="9354c-112">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="9354c-113">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="9354c-113">Click OK.</span></span>

## <a name="enable-access-list-security"></a><span data-ttu-id="9354c-114">Hozzáférési lista biztonságának engedélyezése</span><span class="sxs-lookup"><span data-stu-id="9354c-114">Enable access list security</span></span>
1. <span data-ttu-id="9354c-115">Lépjen a Költségkönyvelés > Dimenziók > Dimenzióhierarchiák pontra.</span><span class="sxs-lookup"><span data-stu-id="9354c-115">Go to Cost accounting > Dimensions > Dimension hierarchies.</span></span>
2. <span data-ttu-id="9354c-116">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="9354c-116">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="9354c-117">Válassza ki a szervezetet.</span><span class="sxs-lookup"><span data-stu-id="9354c-117">Select Organization.</span></span>  
3. <span data-ttu-id="9354c-118">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9354c-118">Click Edit.</span></span>
4. <span data-ttu-id="9354c-119">A Hozzáférési lista hierarchia mezőben válassza az Igen lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9354c-119">Select Yes in the Access list hierarchy field.</span></span>
5. <span data-ttu-id="9354c-120">Kattintson a Hierarchia megtekintése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9354c-120">Click View hierarchy.</span></span>

## <a name="assign-access-rights-to-user"></a><span data-ttu-id="9354c-121">Hozzáférési jogok hozzárendelése a felhasználóhoz</span><span class="sxs-lookup"><span data-stu-id="9354c-121">Assign access rights to user</span></span>
1. <span data-ttu-id="9354c-122">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9354c-122">Click New.</span></span>
2. <span data-ttu-id="9354c-123">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="9354c-123">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="9354c-124">A Felhasználói azonosító mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="9354c-124">In the User ID field, enter or select a value.</span></span>
    * <span data-ttu-id="9354c-125">Válassza a Rendszergazda lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9354c-125">Select Admin.</span></span>  
4. <span data-ttu-id="9354c-126">A fán válassza a Szervezet>Vezérigazgató>Pénzügyi igazgató>FIM lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9354c-126">In the tree, select 'Organization\CEO\CFO\FIM'.</span></span>
5. <span data-ttu-id="9354c-127">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9354c-127">Click New.</span></span>
6. <span data-ttu-id="9354c-128">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="9354c-128">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="9354c-129">A Felhasználói azonosító mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="9354c-129">In the User ID field, enter or select a value.</span></span>
    * <span data-ttu-id="9354c-130">Válassza ki az Aliz lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9354c-130">Select Alicia.</span></span>  
8. <span data-ttu-id="9354c-131">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="9354c-131">Click Save.</span></span>

## <a name="enable-access-rights-in-cost-accounting"></a><span data-ttu-id="9354c-132">Hozzáférési jogok engedélyezése a Költségkönyvelésben</span><span class="sxs-lookup"><span data-stu-id="9354c-132">Enable access rights in Cost accounting</span></span>
1. <span data-ttu-id="9354c-133">Lépjen a Költségkönyvelés > Beállítás > Paraméterek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9354c-133">Go to Cost accounting > Setup > Parameters.</span></span>
2. <span data-ttu-id="9354c-134">Kattintson az Általános fülre.</span><span class="sxs-lookup"><span data-stu-id="9354c-134">Click the General tab.</span></span>
3. <span data-ttu-id="9354c-135">Válassza az Igen lehetőséget ki a Költségobjektumdimenzió-tagok megtekintési hozzáférésének engedélyezése mezőben.</span><span class="sxs-lookup"><span data-stu-id="9354c-135">Select Yes in the Enable view access for cost object dimension members field.</span></span>
4. <span data-ttu-id="9354c-136">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="9354c-136">Click Save.</span></span>
5. <span data-ttu-id="9354c-137">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="9354c-137">Close the page.</span></span>
6. <span data-ttu-id="9354c-138">Lépjen a Költségkönyvelés > Beállítás > Költségellenőrzési munkaterület konfigurációja lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9354c-138">Go to Cost accounting > Setup > Cost control workspace configuration.</span></span>
7. <span data-ttu-id="9354c-139">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9354c-139">Click Edit.</span></span>
8. <span data-ttu-id="9354c-140">Válassza az Igen lehetőséget a Közzétéve mezőben.</span><span class="sxs-lookup"><span data-stu-id="9354c-140">Select Yes in the Published field.</span></span>
    * <span data-ttu-id="9354c-141">Ha Igen értékre állítja ezt a beállítást, a következő négy szerepkör valamelyikéhez hozzárendelt felhasználó láthatja a Költség-ellenőrzési munkaterület jelentéseit: költségkönyvelés-kezelő, költségkönyvelő, költségkönyvelő adminisztrátor vagy költségobjektum-ellenőr.</span><span class="sxs-lookup"><span data-stu-id="9354c-141">If you select Yes, a user who is assigned one of the following four roles can see the reports in the Cost control workspace: cost accounting manager, cost accountant, cost accountant clerk, and cost object controller.</span></span> <span data-ttu-id="9354c-142">Ha Nem értékre állítja ezt a beállítást, a következő szerepkörök valamelyikéhez hozzárendelt felhasználó láthatja a jelentéseket: költségkönyvelés-kezelő, költségkönyvelő és költségkönyvelő adminisztrátor.</span><span class="sxs-lookup"><span data-stu-id="9354c-142">If you select No, only a user who is assigned one of the following roles can see the reports: cost accounting manager, cost accountant, and cost accountant clerk.</span></span>    
9. <span data-ttu-id="9354c-143">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="9354c-143">Click Save.</span></span>

