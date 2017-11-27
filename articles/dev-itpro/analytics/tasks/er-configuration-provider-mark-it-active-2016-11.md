--- 
title: "Konfigurációszolgáltató létrehozása és megjelölése aktívként az elektronikus jelentéskészítéshez (ER)"
description: "A következő lépések leírják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörhöz rendelt felhasználó miként hozhat létre konfigurációszolgáltatót az Elektronikus jelentéshez (ER)."
author: NickSelin
manager: AnnBe
ms.date: 11/01/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 809a1466b0f4674f503bc654175d8f94b37a6508
ms.openlocfilehash: 2dfa04f280249884af2a237807fb283059444a6c
ms.contentlocale: hu-hu
ms.lasthandoff: 11/02/2017

---
# <a name="create-a-configuration-provider-and-mark-it-as-active-for-electronic-reporting-er"></a><span data-ttu-id="65e5d-103">Konfigurációszolgáltató létrehozása és megjelölése aktívként az elektronikus jelentéskészítéshez (ER)</span><span class="sxs-lookup"><span data-stu-id="65e5d-103">Create a configuration provider and mark it as active for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="65e5d-104">A következő lépések leírják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörhöz rendelt felhasználó miként hozhat létre konfigurációszolgáltatót az Elektronikus jelentéshez (ER).</span><span class="sxs-lookup"><span data-stu-id="65e5d-104">The following steps explain how a user assigned to the System Administrator or Electronic Reporting Developer role can create a configuration provider for Electronic reporting (ER).</span></span> <span data-ttu-id="65e5d-105">Minden egyes ER konfiguráció a konfiguráció szerzőjeként hivatkozik a szolgáltatóra.</span><span class="sxs-lookup"><span data-stu-id="65e5d-105">Each ER configuration will refer to the provider as the author of the configuration.</span></span> <span data-ttu-id="65e5d-106">Ebben a példában a mintavállalatra, Litware-ra, Inc.-ra vonatkozóan létrehoz egy konfigurációs szolgáltatót. Ezeket a lépéseket minden vállalat minden vállalat között megosztott ER konfigurációs szolgáltatókként hajthatók végre az egyes vállalatoknál.</span><span class="sxs-lookup"><span data-stu-id="65e5d-106">In this example, you will create a configuration provider for sample company, Litware, Inc. These steps can be performed in any company as ER configuration providers are shared among all companies.</span></span>


## <a name="create-a-provider"></a><span data-ttu-id="65e5d-107">Szolgáltató létrehozása</span><span class="sxs-lookup"><span data-stu-id="65e5d-107">Create a provider</span></span>
1. <span data-ttu-id="65e5d-108">Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.</span><span class="sxs-lookup"><span data-stu-id="65e5d-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="65e5d-109">Kattintson a konfigurációszolgáltatókra.</span><span class="sxs-lookup"><span data-stu-id="65e5d-109">Click Configuration providers.</span></span>
3. <span data-ttu-id="65e5d-110">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="65e5d-110">Click New.</span></span>
    * <span data-ttu-id="65e5d-111">Egy szolgáltató rekord egyedi névvel és URL-címmel rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="65e5d-111">A provider record has a unique name and URL.</span></span> <span data-ttu-id="65e5d-112">Tekintse át ezen oldal tartalmát és ugorja át ezt az eljárást, ha a rekord a Litware, Inc. (http://www.litware.com) számára már létezik.</span><span class="sxs-lookup"><span data-stu-id="65e5d-112">Review the content of this page and skip this procedure if a record for Litware, Inc. (http://www.litware.com) already exists.</span></span>  
4. <span data-ttu-id="65e5d-113">A Név mezőbe írja be a „Litware, Inc.” nevet.</span><span class="sxs-lookup"><span data-stu-id="65e5d-113">In the Name field, type 'Litware, Inc.'.</span></span>
    * <span data-ttu-id="65e5d-114">Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="65e5d-114">Litware, Inc.</span></span>  
5. <span data-ttu-id="65e5d-115">Az internetcím mezőbe ezt írja be: http://www.litware.com.</span><span class="sxs-lookup"><span data-stu-id="65e5d-115">In the Internet address field, type 'http://www.litware.com'.</span></span>
    * <span data-ttu-id="65e5d-116">http://www.litware.com</span><span class="sxs-lookup"><span data-stu-id="65e5d-116">http://www.litware.com</span></span>  
6. <span data-ttu-id="65e5d-117">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="65e5d-117">Click Save.</span></span>
7. <span data-ttu-id="65e5d-118">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="65e5d-118">Close the page.</span></span>

## <a name="select-as-an-active-provider"></a><span data-ttu-id="65e5d-119">Kiválasztás aktív szolgáltatónak</span><span class="sxs-lookup"><span data-stu-id="65e5d-119">Select as an active provider</span></span>
1. <span data-ttu-id="65e5d-120">Válassza ki a „Litware, Inc.” szolgáltatót.</span><span class="sxs-lookup"><span data-stu-id="65e5d-120">Select the Litware, Inc. provider.</span></span>
2. <span data-ttu-id="65e5d-121">Kattintson erre: Beállítás aktívként.</span><span class="sxs-lookup"><span data-stu-id="65e5d-121">Click Set active.</span></span>


