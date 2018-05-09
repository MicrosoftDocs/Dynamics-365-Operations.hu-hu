--- 
title: "Számlálási és összegzési formátumának létrehozása"
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
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: c20f2190e6480b6586d8102c489633d748d85a95
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---
# <a name="create-format-for-counting-and-summing"></a><span data-ttu-id="462eb-103">Számlálási és összegzési formátumának létrehozása</span><span class="sxs-lookup"><span data-stu-id="462eb-103">Create format for counting and summing</span></span> 

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="462eb-104">Az alábbi útmutató azt ismerteti, hogy a rendszergazda vagy elektronikus jelentésfejlesztői szerepkörhöz hozzárendelt felhasználó hogyan konfigurálhat egy elektronikus jelentési (ER) formátumot számlálás és összegzés céljára a már létrehozott szöveges kimeneti adatok alapján.</span><span class="sxs-lookup"><span data-stu-id="462eb-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="462eb-105">Ezeket a lépéseket bármely vállalatban végrehajthatja.</span><span class="sxs-lookup"><span data-stu-id="462eb-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="462eb-106">Hajtsa végre az alábbi lépéseket: Először hajtsa végre a „Konfiguráció szolgáltatói létrehozása és aktívként történő megjelölése” eljárás lépéseit.</span><span class="sxs-lookup"><span data-stu-id="462eb-106">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>

<span data-ttu-id="462eb-107">Ez az eljárás egy olyan funkcióra vonatkozik, amely a Dynamics 365 for Operations 1611-es verziójába került be.</span><span class="sxs-lookup"><span data-stu-id="462eb-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a><span data-ttu-id="462eb-108">Hozzáférés a Microsoft által biztosított konfigurációk listájához</span><span class="sxs-lookup"><span data-stu-id="462eb-108">Get access to the list of configurations provided by Microsoft</span></span>
1. <span data-ttu-id="462eb-109">Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.</span><span class="sxs-lookup"><span data-stu-id="462eb-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="462eb-110">Győződjön meg róla, hogy a Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="462eb-110">Make sure that the “Litware, Inc.”</span></span> <span data-ttu-id="462eb-111">szolgáltató elérhető és aktívként megjelölt legyen.</span><span class="sxs-lookup"><span data-stu-id="462eb-111">provider is available and marked as active.</span></span>  
2. <span data-ttu-id="462eb-112">Válassza ki a Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="462eb-112">Select the “Litware, Inc.”</span></span> <span data-ttu-id="462eb-113">szolgáltatót.</span><span class="sxs-lookup"><span data-stu-id="462eb-113">provider.</span></span>
3. <span data-ttu-id="462eb-114">Kattintson a Tárházak gombra.</span><span class="sxs-lookup"><span data-stu-id="462eb-114">Click Repositories.</span></span>
    * <span data-ttu-id="462eb-115">Ha már létezik egy „Üzemi erőforrások” típusú tár, hagyja ki az aktuális altevékenység többi lépését.</span><span class="sxs-lookup"><span data-stu-id="462eb-115">If a repository of the "Operations resources" type already exists, skip the remaining steps of the current sub-task.</span></span>  
4. <span data-ttu-id="462eb-116">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="462eb-116">Click Add to open the drop dialog.</span></span>
5. <span data-ttu-id="462eb-117">A Konfiguráció tárházának típusa mezőbe írja be az „Üzemi erőforrások” szöveget.</span><span class="sxs-lookup"><span data-stu-id="462eb-117">In the Configuration repository type field, enter 'Operations resources'.</span></span>
6. <span data-ttu-id="462eb-118">Kattintson a Tárház létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="462eb-118">Click Create repository.</span></span>
7. <span data-ttu-id="462eb-119">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="462eb-119">Click OK.</span></span>

## <a name="get-the-intrastat-configurations-provided-by-microsoft"></a><span data-ttu-id="462eb-120">A Microsoft által biztosított Intrastat konfigurációk beszerzése</span><span class="sxs-lookup"><span data-stu-id="462eb-120">Get the Intrastat configurations provided by Microsoft</span></span>
1. <span data-ttu-id="462eb-121">Kattintson a Megnyitás gombra.</span><span class="sxs-lookup"><span data-stu-id="462eb-121">Click Open.</span></span>
2. <span data-ttu-id="462eb-122">A fastruktúrában jelölje ki a következőt: „Intrastat modell\Intrastat (DE)”.</span><span class="sxs-lookup"><span data-stu-id="462eb-122">In the tree, select 'Intrastat model\Intrastat (DE)'.</span></span>
3. <span data-ttu-id="462eb-123">Kattintson az Importálás gombra.</span><span class="sxs-lookup"><span data-stu-id="462eb-123">Click Import.</span></span>
    * <span data-ttu-id="462eb-124">Kattintson az Importálás gombra a kijelölt konfiguráció 1.1-es verziójának esetében.</span><span class="sxs-lookup"><span data-stu-id="462eb-124">Click Import for version 1.1 of the selected configuration.</span></span>  
4. <span data-ttu-id="462eb-125">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="462eb-125">Click Yes.</span></span>
5. <span data-ttu-id="462eb-126">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="462eb-126">Close the page.</span></span>
6. <span data-ttu-id="462eb-127">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="462eb-127">Close the page.</span></span>
7. <span data-ttu-id="462eb-128">Kattintson a Jelentéskészítés konfigurációi lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="462eb-128">Click Reporting configurations.</span></span>
8. <span data-ttu-id="462eb-129">A fastruktúrában bontsa ki az „Instrastat modell” elemet.</span><span class="sxs-lookup"><span data-stu-id="462eb-129">In the tree, expand 'Intrastat model'.</span></span>
9. <span data-ttu-id="462eb-130">A fastruktúrában jelölje ki a következőt: „Intrastat modell\Intrastat (DE)”.</span><span class="sxs-lookup"><span data-stu-id="462eb-130">In the tree, select 'Intrastat model\Intrastat (DE)'.</span></span>


