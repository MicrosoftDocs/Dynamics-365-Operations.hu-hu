--- 
title: "Formátum létrehozása számláláshoz és összegzéshez az elektronikus jelentéskészítéshez (ER)"
description: "Az alábbi útmutató azt ismerteti, hogy a rendszergazda vagy elektronikus jelentésfejlesztői szerepkörhöz hozzárendelt felhasználó hogyan konfigurálhat egy elektronikus jelentési (ER) formátumot számlálás és összegzés céljára a már létrehozott szöveges kimeneti adatok alapján."
author: NickSelin
manager: AnnBe
ms.date: 11/02/2017
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
ms.sourcegitcommit: 5d4f57ae2a309d9e15c1afe60c3e91d7d7eb3870
ms.openlocfilehash: 3c4ae958a03d4681a85f5b83d81fe64b9ac99cf5
ms.contentlocale: hu-hu
ms.lasthandoff: 11/02/2017

---
# <a name="create-format-for-counting-and-summing-for-electronic-reporting-er"></a><span data-ttu-id="63eea-103">Formátum létrehozása számláláshoz és összegzéshez az elektronikus jelentéskészítéshez (ER)</span><span class="sxs-lookup"><span data-stu-id="63eea-103">Create format for counting and summing for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="63eea-104">Az alábbi útmutató azt ismerteti, hogy a rendszergazda vagy elektronikus jelentésfejlesztői szerepkörhöz hozzárendelt felhasználó hogyan konfigurálhat egy elektronikus jelentési (ER) formátumot számlálás és összegzés céljára a már létrehozott szöveges kimeneti adatok alapján.</span><span class="sxs-lookup"><span data-stu-id="63eea-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="63eea-105">Ezeket a lépéseket bármely vállalatban végrehajthatja.</span><span class="sxs-lookup"><span data-stu-id="63eea-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="63eea-106">Hajtsa végre az alábbi lépéseket: Először hajtsa végre a „Konfiguráció szolgáltatói létrehozása és aktívként történő megjelölése” eljárás lépéseit.</span><span class="sxs-lookup"><span data-stu-id="63eea-106">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>

<span data-ttu-id="63eea-107">Ez az eljárás egy olyan funkcióra vonatkozik, amely a Dynamics 365 for Operations 1611-es verziójába került be.</span><span class="sxs-lookup"><span data-stu-id="63eea-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a><span data-ttu-id="63eea-108">Hozzáférés a Microsoft által biztosított konfigurációk listájához</span><span class="sxs-lookup"><span data-stu-id="63eea-108">Get access to the list of configurations provided by Microsoft</span></span>
1. <span data-ttu-id="63eea-109">Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.</span><span class="sxs-lookup"><span data-stu-id="63eea-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="63eea-110">Győződjön meg róla, hogy a Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="63eea-110">Make sure that the “Litware, Inc.”</span></span> <span data-ttu-id="63eea-111">szolgáltató elérhető és aktívként megjelölt legyen.</span><span class="sxs-lookup"><span data-stu-id="63eea-111">provider is available and marked as active.</span></span>  
2. <span data-ttu-id="63eea-112">Válassza ki a Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="63eea-112">Select the “Litware, Inc.”</span></span> <span data-ttu-id="63eea-113">szolgáltatót.</span><span class="sxs-lookup"><span data-stu-id="63eea-113">provider.</span></span>
3. <span data-ttu-id="63eea-114">Kattintson a Tárházak gombra.</span><span class="sxs-lookup"><span data-stu-id="63eea-114">Click Repositories.</span></span>
    * <span data-ttu-id="63eea-115">Ha már létezik egy „Üzemi erőforrások” típusú tár, hagyja ki az aktuális altevékenység többi lépését.</span><span class="sxs-lookup"><span data-stu-id="63eea-115">If a repository of the "Operations resources" type already exists, skip the remaining steps of the current sub-task.</span></span>  
4. <span data-ttu-id="63eea-116">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="63eea-116">Click Add to open the drop dialog.</span></span>
5. <span data-ttu-id="63eea-117">A Konfiguráció tárházának típusa mezőbe írja be az „Üzemi erőforrások” szöveget.</span><span class="sxs-lookup"><span data-stu-id="63eea-117">In the Configuration repository type field, enter 'Operations resources'.</span></span>
6. <span data-ttu-id="63eea-118">Kattintson a Tárház létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="63eea-118">Click Create repository.</span></span>
7. <span data-ttu-id="63eea-119">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="63eea-119">Click OK.</span></span>

## <a name="get-the-intrastat-configurations-provided-by-microsoft"></a><span data-ttu-id="63eea-120">A Microsoft által biztosított Intrastat konfigurációk beszerzése</span><span class="sxs-lookup"><span data-stu-id="63eea-120">Get the Intrastat configurations provided by Microsoft</span></span>
1. <span data-ttu-id="63eea-121">Kattintson a Megnyitás gombra.</span><span class="sxs-lookup"><span data-stu-id="63eea-121">Click Open.</span></span>
2. <span data-ttu-id="63eea-122">A fastruktúrában jelölje ki a következőt: „Intrastat modell\Intrastat (DE)”.</span><span class="sxs-lookup"><span data-stu-id="63eea-122">In the tree, select 'Intrastat model\Intrastat (DE)'.</span></span>
3. <span data-ttu-id="63eea-123">Kattintson az Importálás gombra.</span><span class="sxs-lookup"><span data-stu-id="63eea-123">Click Import.</span></span>
    * <span data-ttu-id="63eea-124">Kattintson az Importálás gombra a kijelölt konfiguráció 1.1-es verziójának esetében.</span><span class="sxs-lookup"><span data-stu-id="63eea-124">Click Import for version 1.1 of the selected configuration.</span></span>  
4. <span data-ttu-id="63eea-125">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="63eea-125">Click Yes.</span></span>
5. <span data-ttu-id="63eea-126">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="63eea-126">Close the page.</span></span>
6. <span data-ttu-id="63eea-127">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="63eea-127">Close the page.</span></span>
7. <span data-ttu-id="63eea-128">Kattintson a Jelentéskészítés konfigurációi lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="63eea-128">Click Reporting configurations.</span></span>
8. <span data-ttu-id="63eea-129">A fastruktúrában bontsa ki az „Instrastat modell” elemet.</span><span class="sxs-lookup"><span data-stu-id="63eea-129">In the tree, expand 'Intrastat model'.</span></span>
9. <span data-ttu-id="63eea-130">A fastruktúrában jelölje ki a következőt: „Intrastat modell\Intrastat (DE)”.</span><span class="sxs-lookup"><span data-stu-id="63eea-130">In the tree, select 'Intrastat model\Intrastat (DE)'.</span></span>


