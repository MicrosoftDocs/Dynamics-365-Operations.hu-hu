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
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 88d6208e867bd322ddfc4e599856b1905fa8e19b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969378"
---
# <a name="configure-access-rights-for-a-cost-object-controller"></a><span data-ttu-id="268a3-103">Hozzáférési jogok konfigurálása egy költségobjektum-ellenőr számára</span><span class="sxs-lookup"><span data-stu-id="268a3-103">Configure access rights for a cost object controller</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="268a3-104">Ezzel az eljárásal konfigurálhatja a hozzáférési jogokat egy költségobjektum-ellenőr számára.</span><span class="sxs-lookup"><span data-stu-id="268a3-104">Use this procedure to configure access rights for a cost object controller.</span></span> <span data-ttu-id="268a3-105">Ez a felvétel az USP2 bemutató vállalati adatait használja.</span><span class="sxs-lookup"><span data-stu-id="268a3-105">This recording uses the USP2 demo data company.</span></span>


## <a name="assign-the-cost-object-controller-role"></a><span data-ttu-id="268a3-106">Költségobjektum-ellenőr szerepkör hozzárendelése</span><span class="sxs-lookup"><span data-stu-id="268a3-106">Assign the cost object controller role</span></span>
1. <span data-ttu-id="268a3-107">Ugrás a Rendszerfelügyelet > Felhasználók > Felhasználók elemre.</span><span class="sxs-lookup"><span data-stu-id="268a3-107">Go to System administration > Users > Users.</span></span>
2. <span data-ttu-id="268a3-108">Rekordok kereséséhez használja a gyorsszűrőt.</span><span class="sxs-lookup"><span data-stu-id="268a3-108">Use the Quick Filter to find records.</span></span> <span data-ttu-id="268a3-109">Például szűkítsen a Felhasználónév mezőben az „aliz” szót beírva.</span><span class="sxs-lookup"><span data-stu-id="268a3-109">For example, filter on the User name field with a value of 'alicia'.</span></span>
3. <span data-ttu-id="268a3-110">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="268a3-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="268a3-111">Kattintson a Szerepkörök hozzárendelése elemre.</span><span class="sxs-lookup"><span data-stu-id="268a3-111">Click Assign roles.</span></span>
5. <span data-ttu-id="268a3-112">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="268a3-112">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="268a3-113">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="268a3-113">Click OK.</span></span>

## <a name="enable-access-list-security"></a><span data-ttu-id="268a3-114">Hozzáférési lista biztonságának engedélyezése</span><span class="sxs-lookup"><span data-stu-id="268a3-114">Enable access list security</span></span>
1. <span data-ttu-id="268a3-115">Lépjen a Költségkönyvelés > Dimenziók > Dimenzióhierarchiák pontra.</span><span class="sxs-lookup"><span data-stu-id="268a3-115">Go to Cost accounting > Dimensions > Dimension hierarchies.</span></span>
2. <span data-ttu-id="268a3-116">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="268a3-116">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="268a3-117">Válassza ki a szervezetet.</span><span class="sxs-lookup"><span data-stu-id="268a3-117">Select Organization.</span></span>  
3. <span data-ttu-id="268a3-118">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="268a3-118">Click Edit.</span></span>
4. <span data-ttu-id="268a3-119">A Hozzáférési lista hierarchia mezőben válassza az Igen lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="268a3-119">Select Yes in the Access list hierarchy field.</span></span>
5. <span data-ttu-id="268a3-120">Kattintson a Hierarchia megtekintése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="268a3-120">Click View hierarchy.</span></span>

## <a name="assign-access-rights-to-user"></a><span data-ttu-id="268a3-121">Hozzáférési jogok hozzárendelése a felhasználóhoz</span><span class="sxs-lookup"><span data-stu-id="268a3-121">Assign access rights to user</span></span>
1. <span data-ttu-id="268a3-122">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="268a3-122">Click New.</span></span>
2. <span data-ttu-id="268a3-123">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="268a3-123">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="268a3-124">A Felhasználói azonosító mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="268a3-124">In the User ID field, enter or select a value.</span></span>
    * <span data-ttu-id="268a3-125">Válassza a Rendszergazda lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="268a3-125">Select Admin.</span></span>  
4. <span data-ttu-id="268a3-126">A fán válassza a Szervezet>Vezérigazgató>Pénzügyi igazgató>FIM lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="268a3-126">In the tree, select 'Organization\CEO\CFO\FIM'.</span></span>
5. <span data-ttu-id="268a3-127">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="268a3-127">Click New.</span></span>
6. <span data-ttu-id="268a3-128">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="268a3-128">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="268a3-129">A Felhasználói azonosító mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="268a3-129">In the User ID field, enter or select a value.</span></span>
    * <span data-ttu-id="268a3-130">Válassza ki az Aliz lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="268a3-130">Select Alicia.</span></span>  
8. <span data-ttu-id="268a3-131">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="268a3-131">Click Save.</span></span>

## <a name="enable-access-rights-in-cost-accounting"></a><span data-ttu-id="268a3-132">Hozzáférési jogok engedélyezése a Költségkönyvelésben</span><span class="sxs-lookup"><span data-stu-id="268a3-132">Enable access rights in Cost accounting</span></span>
1. <span data-ttu-id="268a3-133">Lépjen a Költségkönyvelés > Beállítás > Paraméterek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="268a3-133">Go to Cost accounting > Setup > Parameters.</span></span>
2. <span data-ttu-id="268a3-134">Kattintson az Általános fülre.</span><span class="sxs-lookup"><span data-stu-id="268a3-134">Click the General tab.</span></span>
3. <span data-ttu-id="268a3-135">Válassza az Igen lehetőséget ki a Költségobjektumdimenzió-tagok megtekintési hozzáférésének engedélyezése mezőben.</span><span class="sxs-lookup"><span data-stu-id="268a3-135">Select Yes in the Enable view access for cost object dimension members field.</span></span>
4. <span data-ttu-id="268a3-136">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="268a3-136">Click Save.</span></span>
5. <span data-ttu-id="268a3-137">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="268a3-137">Close the page.</span></span>
6. <span data-ttu-id="268a3-138">Lépjen a Költségkönyvelés > Beállítás > Költségellenőrzési munkaterület konfigurációja lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="268a3-138">Go to Cost accounting > Setup > Cost control workspace configuration.</span></span>
7. <span data-ttu-id="268a3-139">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="268a3-139">Click Edit.</span></span>
8. <span data-ttu-id="268a3-140">Válassza az Igen lehetőséget a Közzétéve mezőben.</span><span class="sxs-lookup"><span data-stu-id="268a3-140">Select Yes in the Published field.</span></span>
    * <span data-ttu-id="268a3-141">Ha Igen értékre állítja ezt a beállítást, a következő négy szerepkör valamelyikéhez hozzárendelt felhasználó láthatja a Költség-ellenőrzési munkaterület jelentéseit: költségkönyvelés-kezelő, költségkönyvelő, költségkönyvelő adminisztrátor vagy költségobjektum-ellenőr.</span><span class="sxs-lookup"><span data-stu-id="268a3-141">If you select Yes, a user who is assigned one of the following four roles can see the reports in the Cost control workspace: cost accounting manager, cost accountant, cost accountant clerk, and cost object controller.</span></span> <span data-ttu-id="268a3-142">Ha Nem értékre állítja ezt a beállítást, a következő szerepkörök valamelyikéhez hozzárendelt felhasználó láthatja a jelentéseket: költségkönyvelés-kezelő, költségkönyvelő és költségkönyvelő adminisztrátor.</span><span class="sxs-lookup"><span data-stu-id="268a3-142">If you select No, only a user who is assigned one of the following roles can see the reports: cost accounting manager, cost accountant, and cost accountant clerk.</span></span>    
9. <span data-ttu-id="268a3-143">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="268a3-143">Click Save.</span></span>

