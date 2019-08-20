---
title: Konfigurációszolgáltatók létrehozása és megjelölése aktívként
description: A témakör leírja, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörhöz rendelt felhasználó miként hozhat létre konfigurációszolgáltatót az Elektronikus jelentéshez (ER) a Dynamics 365 for Finance and Operations alkalmazásban.
author: NickSelin
manager: AnnBe
ms.date: 07/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERVendorTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0dfbcf70493a43320e17d4d2734fe6343d43eaf3
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/02/2019
ms.locfileid: "1850327"
---
# <a name="create-configuration-providers-and-mark-them-as-active"></a><span data-ttu-id="c1961-103">Konfigurációszolgáltatók létrehozása és megjelölése aktívként</span><span class="sxs-lookup"><span data-stu-id="c1961-103">Create configuration providers and mark them as active</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c1961-104">A témakör leírja, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörhöz rendelt felhasználó miként hozhat létre konfigurációszolgáltatót az Elektronikus jelentéshez (ER) a Dynamics 365 for Finance and Operations alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="c1961-104">This topic explains how a user assigned to the System Administrator or Electronic Reporting Developer role can create a configuration provider for Electronic reporting (ER) in Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="c1961-105">Minden egyes ER konfiguráció a konfiguráció szerzőjeként hivatkozik a szolgáltatóra.</span><span class="sxs-lookup"><span data-stu-id="c1961-105">Each ER configuration will refer to the provider as the author of the configuration.</span></span> <span data-ttu-id="c1961-106">Ebben a példában a mintavállalatra, Litware-ra, Inc.-ra vonatkozóan létrehoz egy konfigurációs szolgáltatót. Ezeket a lépéseket minden vállalat minden vállalat között megosztott ER konfigurációs szolgáltatókként hajthatók végre az egyes vállalatoknál.</span><span class="sxs-lookup"><span data-stu-id="c1961-106">In this example, you will create a configuration provider for sample company, Litware, Inc. These steps can be performed in any company as ER configuration providers are shared among all companies.</span></span>

## <a name="create-a-provider"></a><span data-ttu-id="c1961-107">Szolgáltató létrehozása</span><span class="sxs-lookup"><span data-stu-id="c1961-107">Create a provider</span></span>
1. <span data-ttu-id="c1961-108">Nyissa meg a bal felső sarokban látható **navigációs ablaktáblát**, és válassza ki a **Szervezet adminisztrációját**.</span><span class="sxs-lookup"><span data-stu-id="c1961-108">Go to the **navigation pane** in the upper left corner and select **Organization administration**.</span></span>
2. <span data-ttu-id="c1961-109">Ugorjon a **Munkaterületek > Elektronikus jelentés** pontra.</span><span class="sxs-lookup"><span data-stu-id="c1961-109">Go to **Workspaces > Electronic reporting**.</span></span>
3. <span data-ttu-id="c1961-110">Ugrás a **Kapcsolódó linkek > Konfigurációs szolgáltatók** pontra.</span><span class="sxs-lookup"><span data-stu-id="c1961-110">Go to **Related links > Configuration providers**.</span></span>
4. <span data-ttu-id="c1961-111">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c1961-111">Select **New**.</span></span>
    - <span data-ttu-id="c1961-112">Egy szolgáltató rekord egyedi névvel és URL-címmel rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="c1961-112">A provider record has a unique name and URL.</span></span> <span data-ttu-id="c1961-113">Tekintse át ezen oldal tartalmát és ugorja át ezt az eljárást, ha a rekord a Litware, Inc. (https://www.litware.com) számára már létezik.</span><span class="sxs-lookup"><span data-stu-id="c1961-113">Review the content of this page and skip this procedure if a record for Litware, Inc. (https://www.litware.com) already exists.</span></span>  
5. <span data-ttu-id="c1961-114">A Név mezőbe írja be a „`Litware, Inc.`” szöveget.</span><span class="sxs-lookup"><span data-stu-id="c1961-114">In the Name field, type `Litware, Inc.`.</span></span>
6. <span data-ttu-id="c1961-115">Írja be a `https://www.litware.com` értéket az internetcím mezőbe.</span><span class="sxs-lookup"><span data-stu-id="c1961-115">In the Internet address field, type `https://www.litware.com`.</span></span>
7. <span data-ttu-id="c1961-116">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c1961-116">Select **Save**.</span></span>
8. <span data-ttu-id="c1961-117">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c1961-117">Close the page.</span></span>

## <a name="select-as-an-active-provider"></a><span data-ttu-id="c1961-118">Kiválasztás aktív szolgáltatónak</span><span class="sxs-lookup"><span data-stu-id="c1961-118">Select as an active provider</span></span>
1. <span data-ttu-id="c1961-119">Válassza ki a „Litware, Inc.” szolgáltatót.</span><span class="sxs-lookup"><span data-stu-id="c1961-119">Select the Litware, Inc. provider.</span></span>
2. <span data-ttu-id="c1961-120">Válassza ki az **Aktív beállítása** elemet.</span><span class="sxs-lookup"><span data-stu-id="c1961-120">Select **Set active**.</span></span>

