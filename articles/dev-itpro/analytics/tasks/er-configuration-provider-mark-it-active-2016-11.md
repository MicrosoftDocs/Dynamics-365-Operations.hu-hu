--- 
title: "Konfigurációszolgáltató létrehozása és megjelölése aktívként az elektronikus jelentéskészítéshez (ER)"
description: "A következő lépések leírják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörhöz rendelt felhasználó miként hozhat létre konfigurációszolgáltatót az Elektronikus jelentéshez (ER)."
author: NickSelin
manager: AnnBe
ms.date: 10/18/2016
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
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: bdb3a3857a7293828a7766b6988c123a43e0673c
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-configuration-providand-mark-it-as-active-for-electronic-reporting-er"></a><span data-ttu-id="c7f6a-103">Konfigurációszolgáltató létrehozása és megjelölése aktívként az elektronikus jelentéskészítéshez (ER)</span><span class="sxs-lookup"><span data-stu-id="c7f6a-103">Create a configuration providand mark it as active for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c7f6a-104">A következő lépések leírják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörhöz rendelt felhasználó miként hozhat létre konfigurációszolgáltatót az Elektronikus jelentéshez (ER).</span><span class="sxs-lookup"><span data-stu-id="c7f6a-104">The following steps explain how a user assigned to the System Administrator or Electronic Reporting Developer role can create a configuration provider for Electronic reporting (ER).</span></span> <span data-ttu-id="c7f6a-105">Minden egyes ER konfiguráció a konfiguráció szerzőjeként hivatkozik a szolgáltatóra.</span><span class="sxs-lookup"><span data-stu-id="c7f6a-105">Each ER configuration will refer to the provider as the author of the configuration.</span></span> <span data-ttu-id="c7f6a-106">Ebben a példában a mintavállalatra, Litware-ra, Inc.-ra vonatkozóan létrehoz egy konfigurációs szolgáltatót. Ezeket a lépéseket minden vállalat minden vállalat között megosztott ER konfigurációs szolgáltatókként hajthatók végre az egyes vállalatoknál.</span><span class="sxs-lookup"><span data-stu-id="c7f6a-106">In this example, you will create a configuration provider for sample company, Litware, Inc. These steps can be performed in any company as ER configuration providers are shared among all companies.</span></span>


## <a name="create-a-provider"></a><span data-ttu-id="c7f6a-107">Szolgáltató létrehozása</span><span class="sxs-lookup"><span data-stu-id="c7f6a-107">Create a provider</span></span>
1. <span data-ttu-id="c7f6a-108">Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.</span><span class="sxs-lookup"><span data-stu-id="c7f6a-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="c7f6a-109">Kattintson a konfigurációszolgáltatókra.</span><span class="sxs-lookup"><span data-stu-id="c7f6a-109">Click Configuration providers.</span></span>
3. <span data-ttu-id="c7f6a-110">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c7f6a-110">Click New.</span></span>
    * <span data-ttu-id="c7f6a-111">Egy szolgáltató rekord egyedi névvel és URL-címmel rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="c7f6a-111">A provider record has a unique name and URL.</span></span> <span data-ttu-id="c7f6a-112">Tekintse át ezen oldal tartalmát és ugorja át ezt az eljárást, ha a rekord a Litware, Inc. (http://www.litware.com) számára már létezik.</span><span class="sxs-lookup"><span data-stu-id="c7f6a-112">Review the content of this page and skip this procedure if a record for Litware, Inc. (http://www.litware.com) already exists.</span></span>  
4. <span data-ttu-id="c7f6a-113">A Név mezőbe írja be a „Litware, Inc.” nevet.</span><span class="sxs-lookup"><span data-stu-id="c7f6a-113">In the Name field, type 'Litware, Inc.'.</span></span>
    * <span data-ttu-id="c7f6a-114">Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="c7f6a-114">Litware, Inc.</span></span>  
5. <span data-ttu-id="c7f6a-115">Az internetcím mezőbe ezt írja be: http://www.litware.com.</span><span class="sxs-lookup"><span data-stu-id="c7f6a-115">In the Internet address field, type 'http://www.litware.com'.</span></span>
    * <span data-ttu-id="c7f6a-116">http://www.litware.com</span><span class="sxs-lookup"><span data-stu-id="c7f6a-116">http://www.litware.com</span></span>  
6. <span data-ttu-id="c7f6a-117">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="c7f6a-117">Click Save.</span></span>
7. <span data-ttu-id="c7f6a-118">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c7f6a-118">Close the page.</span></span>

## <a name="select-as-an-active-provider"></a><span data-ttu-id="c7f6a-119">Kiválasztás aktív szolgáltatónak</span><span class="sxs-lookup"><span data-stu-id="c7f6a-119">Select as an active provider</span></span>
1. <span data-ttu-id="c7f6a-120">Válassza ki a „Litware, Inc.” szolgáltatót.</span><span class="sxs-lookup"><span data-stu-id="c7f6a-120">Select the Litware, Inc. provider.</span></span>
2. <span data-ttu-id="c7f6a-121">Kattintson erre: Beállítás aktívként.</span><span class="sxs-lookup"><span data-stu-id="c7f6a-121">Click Set active.</span></span>


