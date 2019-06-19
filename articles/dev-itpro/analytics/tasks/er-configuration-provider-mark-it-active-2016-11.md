---
title: Konfigurációszolgáltatók létrehozása, és megjelölésük aktívként
description: A következő lépések leírják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörhöz rendelt felhasználó miként hozhat létre konfigurációszolgáltatót az Elektronikus jelentéshez (ER).
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERVendorTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a4b1cd7a02cdf4c650af50199f4425eb53cef0a8
ms.sourcegitcommit: 574d4dda83dcab94728a3d35fc53ee7e2b90feb0
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/22/2019
ms.locfileid: "1595395"
---
# <a name="create-configuration-providers-and-mark-them-as-active"></a><span data-ttu-id="44585-103">Konfigurációszolgáltatók létrehozása, és megjelölésük aktívként</span><span class="sxs-lookup"><span data-stu-id="44585-103">Create configuration providers and mark them as active</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="44585-104">A következő lépések leírják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörhöz rendelt felhasználó miként hozhat létre konfigurációszolgáltatót az Elektronikus jelentéshez (ER).</span><span class="sxs-lookup"><span data-stu-id="44585-104">The following steps explain how a user assigned to the System Administrator or Electronic Reporting Developer role can create a configuration provider for Electronic reporting (ER).</span></span> <span data-ttu-id="44585-105">Minden egyes ER konfiguráció a konfiguráció szerzőjeként hivatkozik a szolgáltatóra.</span><span class="sxs-lookup"><span data-stu-id="44585-105">Each ER configuration will refer to the provider as the author of the configuration.</span></span> <span data-ttu-id="44585-106">Ebben a példában a mintavállalatra, Litware-ra, Inc.-ra vonatkozóan létrehoz egy konfigurációs szolgáltatót. Ezeket a lépéseket minden vállalat minden vállalat között megosztott ER konfigurációs szolgáltatókként hajthatók végre az egyes vállalatoknál.</span><span class="sxs-lookup"><span data-stu-id="44585-106">In this example, you will create a configuration provider for sample company, Litware, Inc. These steps can be performed in any company as ER configuration providers are shared among all companies.</span></span>


## <a name="create-a-provider"></a><span data-ttu-id="44585-107">Szolgáltató létrehozása</span><span class="sxs-lookup"><span data-stu-id="44585-107">Create a provider</span></span>
1. <span data-ttu-id="44585-108">Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.</span><span class="sxs-lookup"><span data-stu-id="44585-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="44585-109">Kattintson a konfigurációszolgáltatókra.</span><span class="sxs-lookup"><span data-stu-id="44585-109">Click Configuration providers.</span></span>
3. <span data-ttu-id="44585-110">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="44585-110">Click New.</span></span>
    * <span data-ttu-id="44585-111">Egy szolgáltató rekord egyedi névvel és URL-címmel rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="44585-111">A provider record has a unique name and URL.</span></span> <span data-ttu-id="44585-112">Tekintse át ezen oldal tartalmát és ugorja át ezt az eljárást, ha a rekord a Litware, Inc. (https://www.litware.com) számára már létezik.</span><span class="sxs-lookup"><span data-stu-id="44585-112">Review the content of this page and skip this procedure if a record for Litware, Inc. (https://www.litware.com) already exists.</span></span>  
4. <span data-ttu-id="44585-113">A Név mezőbe írja be a „Litware, Inc.” nevet.</span><span class="sxs-lookup"><span data-stu-id="44585-113">In the Name field, type 'Litware, Inc.'.</span></span>
    * <span data-ttu-id="44585-114">Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="44585-114">Litware, Inc.</span></span>  
5. <span data-ttu-id="44585-115">Írja be a(z) „https://www.litware.com” értéket az internetcím mezőbe.</span><span class="sxs-lookup"><span data-stu-id="44585-115">In the Internet address field, type 'https://www.litware.com'.</span></span>
    * https://www.litware.com  
6. <span data-ttu-id="44585-116">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="44585-116">Click Save.</span></span>
7. <span data-ttu-id="44585-117">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="44585-117">Close the page.</span></span>

## <a name="select-as-an-active-provider"></a><span data-ttu-id="44585-118">Kiválasztás aktív szolgáltatónak</span><span class="sxs-lookup"><span data-stu-id="44585-118">Select as an active provider</span></span>
1. <span data-ttu-id="44585-119">Válassza ki a „Litware, Inc.” szolgáltatót.</span><span class="sxs-lookup"><span data-stu-id="44585-119">Select the Litware, Inc. provider.</span></span>
2. <span data-ttu-id="44585-120">Kattintson erre: Beállítás aktívként.</span><span class="sxs-lookup"><span data-stu-id="44585-120">Click Set active.</span></span>

