---
title: ER Számláláshoz és összegzéshez használt formátum konfigurálása (1. rész – Formátum létrehozása)
description: Ez a témakör azt ismerteti, hogyan kell konfigurálni az Elektronikus jelentéskészítési formátumokat a már létrehozott szövegkimenet adatai alapján. (1. rész)
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport,  ERSolutionTable
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3f1db144b2bfafa72abeaa92c6b21de717e4acbf
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5749045"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-1---create-format"></a><span data-ttu-id="c83eb-104">ER Számláláshoz és összegzéshez használt formátum konfigurálása (1. rész – Formátum létrehozása)</span><span class="sxs-lookup"><span data-stu-id="c83eb-104">ER Configure format to do counting and summing (Part 1 - Create format)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c83eb-105">Az alábbi útmutató azt ismerteti, hogy a rendszergazda vagy elektronikus jelentésfejlesztői szerepkörhöz hozzárendelt felhasználó hogyan konfigurálhat egy elektronikus jelentési (ER) formátumot számlálás és összegzés céljára a már létrehozott szöveges kimeneti adatok alapján.</span><span class="sxs-lookup"><span data-stu-id="c83eb-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="c83eb-106">Ezeket a lépéseket bármely vállalatban végrehajthatja.</span><span class="sxs-lookup"><span data-stu-id="c83eb-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="c83eb-107">Hajtsa végre az alábbi lépéseket: először hajtsa végre a „Konfigurációszolgáltató létrehozása és aktívként történő megjelölése” eljárás lépéseit.</span><span class="sxs-lookup"><span data-stu-id="c83eb-107">To complete these steps, you must first complete the steps in the "Create a configuration provider and mark it as active" procedure.</span></span>

<span data-ttu-id="c83eb-108">Az eljárás egy olyan szolgáltatáshoz tartozik, amely a Dynamics 365 for Operations 1611-es verziójában jelent meg.</span><span class="sxs-lookup"><span data-stu-id="c83eb-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a><span data-ttu-id="c83eb-109">Hozzáférés a Microsoft által biztosított konfigurációk listájához</span><span class="sxs-lookup"><span data-stu-id="c83eb-109">Get access to the list of configurations provided by Microsoft</span></span>
1. <span data-ttu-id="c83eb-110">Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.</span><span class="sxs-lookup"><span data-stu-id="c83eb-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="c83eb-111">Győződjön meg róla, hogy a „Litware, Inc.”</span><span class="sxs-lookup"><span data-stu-id="c83eb-111">Make sure that the "Litware, Inc."</span></span> <span data-ttu-id="c83eb-112">szolgáltató elérhető és aktívként megjelölt legyen.</span><span class="sxs-lookup"><span data-stu-id="c83eb-112">provider is available and marked as active.</span></span>  
2. <span data-ttu-id="c83eb-113">Válassza ki a Litware, Inc. lehetőséget</span><span class="sxs-lookup"><span data-stu-id="c83eb-113">Select the "Litware, Inc."</span></span> <span data-ttu-id="c83eb-114">szolgáltatót.</span><span class="sxs-lookup"><span data-stu-id="c83eb-114">provider.</span></span>
3. <span data-ttu-id="c83eb-115">Kattintson a Tárházak gombra.</span><span class="sxs-lookup"><span data-stu-id="c83eb-115">Click Repositories.</span></span>
    * <span data-ttu-id="c83eb-116">Ha már létezik egy „Üzemi erőforrások” típusú tár, hagyja ki az aktuális altevékenység többi lépését.</span><span class="sxs-lookup"><span data-stu-id="c83eb-116">If a repository of the "Operations resources" type already exists, skip the remaining steps of the current sub-task.</span></span>  
4. <span data-ttu-id="c83eb-117">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="c83eb-117">Click Add to open the drop dialog.</span></span>
5. <span data-ttu-id="c83eb-118">A Konfiguráció tárházának típusa mezőbe írja be az „Üzemi erőforrások” szöveget.</span><span class="sxs-lookup"><span data-stu-id="c83eb-118">In the Configuration repository type field, enter 'Operations resources'.</span></span>
6. <span data-ttu-id="c83eb-119">Kattintson a Tárház létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c83eb-119">Click Create repository.</span></span>
7. <span data-ttu-id="c83eb-120">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="c83eb-120">Click OK.</span></span>

## <a name="get-the-intrastat-configurations-provided-by-microsoft"></a><span data-ttu-id="c83eb-121">A Microsoft által biztosított Intrastat konfigurációk beszerzése</span><span class="sxs-lookup"><span data-stu-id="c83eb-121">Get the Intrastat configurations provided by Microsoft</span></span>
1. <span data-ttu-id="c83eb-122">Kattintson a Megnyitás gombra.</span><span class="sxs-lookup"><span data-stu-id="c83eb-122">Click Open.</span></span>
2. <span data-ttu-id="c83eb-123">A fastruktúrában jelölje ki a következőt: „Intrastat modell\Intrastat (DE)”.</span><span class="sxs-lookup"><span data-stu-id="c83eb-123">In the tree, select 'Intrastat model\Intrastat (DE)'.</span></span>
3. <span data-ttu-id="c83eb-124">Kattintson az Importálás gombra.</span><span class="sxs-lookup"><span data-stu-id="c83eb-124">Click Import.</span></span>
    * <span data-ttu-id="c83eb-125">Kattintson az Importálás gombra a kijelölt konfiguráció 1.1-es verziójának esetében.</span><span class="sxs-lookup"><span data-stu-id="c83eb-125">Click Import for version 1.1 of the selected configuration.</span></span>  
4. <span data-ttu-id="c83eb-126">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="c83eb-126">Click Yes.</span></span>
5. <span data-ttu-id="c83eb-127">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c83eb-127">Close the page.</span></span>
6. <span data-ttu-id="c83eb-128">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c83eb-128">Close the page.</span></span>
7. <span data-ttu-id="c83eb-129">Kattintson a Jelentéskészítés konfigurációi lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c83eb-129">Click Reporting configurations.</span></span>
8. <span data-ttu-id="c83eb-130">A fastruktúrában bontsa ki az „Instrastat modell” elemet.</span><span class="sxs-lookup"><span data-stu-id="c83eb-130">In the tree, expand 'Intrastat model'.</span></span>
9. <span data-ttu-id="c83eb-131">A fastruktúrában jelölje ki a következőt: „Intrastat modell\Intrastat (DE)”.</span><span class="sxs-lookup"><span data-stu-id="c83eb-131">In the tree, select 'Intrastat model\Intrastat (DE)'.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]