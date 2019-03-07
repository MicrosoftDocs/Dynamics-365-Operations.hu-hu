---
title: Elektronikus jelentés (ER) modell-leképezési konfigurációk kezelése elektronikus jelentéskészítéshez
description: A folyamat segítségével új, elektronikus jelentésen (ER) alapuló modell-leképezési konfigurációt tervezhet meg, és a beépített ER-funkciók segítségével hatékony összesített számításokat végezhet.
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 614ef06fcf5761f1cf2afb6e7655558d2858d763
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "357174"
---
# <a name="create-electronic-reporting-er-model-mapping-configurations"></a><span data-ttu-id="a966d-103">Elektronikus jelentés (ER) modell-leképezési konfigurációk kezelése elektronikus jelentéskészítéshez</span><span class="sxs-lookup"><span data-stu-id="a966d-103">Create Electronic reporting (ER) model mapping configurations</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a966d-104">A folyamat segítségével új, elektronikus jelentésen (ER) alapuló modell-leképezési konfigurációt tervezhet meg, és a beépített ER-funkciók segítségével hatékony összesített számításokat végezhet.</span><span class="sxs-lookup"><span data-stu-id="a966d-104">Use this procedure to design a new Electronic reporting (ER) model mapping configuration and use built-in ER functions for efficient aggregate calculations.</span></span> <span data-ttu-id="a966d-105">Ebben a folyamatban egy konfigurációt hoz létre a Litware, Inc. minta vállalatra vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="a966d-105">In this procedure, you will create a configuration for sample company, Litware, Inc.</span></span> 

<span data-ttu-id="a966d-106">Ez az eljárás a rendszergazda vagy az elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználók számára készült.</span><span class="sxs-lookup"><span data-stu-id="a966d-106">This procedure is created for uses with the assigned role of System administrator or Electronic reporting developer.</span></span>

<span data-ttu-id="a966d-107">Ezek a lépések bármely adathalmazzal végrehajthatók.</span><span class="sxs-lookup"><span data-stu-id="a966d-107">These steps can be completed using any dataset.</span></span> <span data-ttu-id="a966d-108">Hajtsa végre az alábbi lépéseket: először hajtsa végre a „Konfigurációszolgáltató létrehozása és aktívként történő megjelölése” eljárás lépéseit.</span><span class="sxs-lookup"><span data-stu-id="a966d-108">To complete these steps, you must first complete the steps in the procedure, “Create a configuration provider and mark it as active.”</span></span>

1. <span data-ttu-id="a966d-109">Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.</span><span class="sxs-lookup"><span data-stu-id="a966d-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="a966d-110">Ellenőrizze, hogy a Litware, Inc. mintavállalat esetében rendelkezésre áll és aktívként van megjelölve a konfigurációszolgáltató.</span><span class="sxs-lookup"><span data-stu-id="a966d-110">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as Active.</span></span> <span data-ttu-id="a966d-111">Ha nem látja a konfigurációszolgáltatót, végezze el a „Konfigurációszolgáltató létrehozása, és megjelölés aktívként” eljárásban szereplő lépéseket.</span><span class="sxs-lookup"><span data-stu-id="a966d-111">If you don’t see this configuration provider, complete the steps in the procedure, “Create a configuration provider and mark it as active”.</span></span>  
2. <span data-ttu-id="a966d-112">Kattintson a Jelentéskészítés konfigurációi lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a966d-112">Click Reporting configurations.</span></span>
3. <span data-ttu-id="a966d-113">Kattintson a Szűrők megjelenítése pontra.</span><span class="sxs-lookup"><span data-stu-id="a966d-113">Click Show filters.</span></span>
4. <span data-ttu-id="a966d-114">Írja be az „Intrastat” szűrőértéket a Név mezőbe az „ezzel kezdődik” szűrési operátor használatával.</span><span class="sxs-lookup"><span data-stu-id="a966d-114">In the "Name" field, enter the filter value, "Intrastat" and use the filter operator "begins with".</span></span>
    * <span data-ttu-id="a966d-115">Alkalmazza ezt a szűrőt az Intrastat adatmodell-konfiguráció keresésekor.</span><span class="sxs-lookup"><span data-stu-id="a966d-115">Apply this filter to find the ‘Intrastat’ data model configuration.</span></span> <span data-ttu-id="a966d-116">Megtörténhet, hogy a modell már létezik a konfigurációs fán.</span><span class="sxs-lookup"><span data-stu-id="a966d-116">This model may already exist in the configurations tree.</span></span> <span data-ttu-id="a966d-117">Ha igen, ugorjon a következő alfeladatra.</span><span class="sxs-lookup"><span data-stu-id="a966d-117">If it does, skip the next sub-task.</span></span>   

## <a name="get-the-intrastat-model-configuration-provided-by-microsoft"></a><span data-ttu-id="a966d-118">A Microsoft által biztosított Intrastat modellkonfiguráció beszerzése</span><span class="sxs-lookup"><span data-stu-id="a966d-118">Get the Intrastat model configuration provided by Microsoft</span></span>
1. <span data-ttu-id="a966d-119">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="a966d-119">Close the page.</span></span>
2. <span data-ttu-id="a966d-120">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="a966d-120">Close the page.</span></span>
3. <span data-ttu-id="a966d-121">Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.</span><span class="sxs-lookup"><span data-stu-id="a966d-121">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
4. <span data-ttu-id="a966d-122">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="a966d-122">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="a966d-123">Válassza ki a Microsoft lapot.</span><span class="sxs-lookup"><span data-stu-id="a966d-123">Select the Microsoft provider tile.</span></span>  
5. <span data-ttu-id="a966d-124">Kattintson a Tárházak gombra.</span><span class="sxs-lookup"><span data-stu-id="a966d-124">Click Repositories.</span></span>
    * <span data-ttu-id="a966d-125">Kattintson a Tárházak lehetőségre a Microsoft lapon.</span><span class="sxs-lookup"><span data-stu-id="a966d-125">Click Repositories in the Microsoft provider tile.</span></span>  
6. <span data-ttu-id="a966d-126">Kattintson a Szűrők megjelenítése pontra.</span><span class="sxs-lookup"><span data-stu-id="a966d-126">Click Show filters.</span></span>
7. <span data-ttu-id="a966d-127">Írja be az „erőforrások” szűrőértéket a Típusnév mezőbe a „tartalmazza” szűrési operátor használatával.</span><span class="sxs-lookup"><span data-stu-id="a966d-127">In the "Type name" field, enter the filter value, “resources” and use the filter operator "contains".</span></span> 
8. <span data-ttu-id="a966d-128">Kattintson a Megnyitás gombra.</span><span class="sxs-lookup"><span data-stu-id="a966d-128">Click Open.</span></span>
9. <span data-ttu-id="a966d-129">A fastruktúrában válassza ki az „Instrastat modell” elemet.</span><span class="sxs-lookup"><span data-stu-id="a966d-129">In the tree, select 'Intrastat model'.</span></span>
10. <span data-ttu-id="a966d-130">Kattintson az Importálás gombra.</span><span class="sxs-lookup"><span data-stu-id="a966d-130">Click Import.</span></span>
11. <span data-ttu-id="a966d-131">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="a966d-131">Click Yes.</span></span>
    * <span data-ttu-id="a966d-132">Importálta azt az ER modellkonfigurációt, amely tartalmazza azt az adatmodellt, amelyet használni fog az új ER-funkciók használatának megismerése során.</span><span class="sxs-lookup"><span data-stu-id="a966d-132">You imported the ER model configuration that contains the data model that you will use to explore how the new ER functionality can be used.</span></span>  
12. <span data-ttu-id="a966d-133">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="a966d-133">Close the page.</span></span>
13. <span data-ttu-id="a966d-134">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="a966d-134">Close the page.</span></span>
14. <span data-ttu-id="a966d-135">Kattintson a Jelentéskészítés konfigurációi lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a966d-135">Click Reporting configurations.</span></span>

## <a name="add-a-new-model-mapping-configuration"></a><span data-ttu-id="a966d-136">Új modell-leképezési konfiguráció hozzáadása</span><span class="sxs-lookup"><span data-stu-id="a966d-136">Add a new model mapping configuration</span></span>
1. <span data-ttu-id="a966d-137">A fastruktúrában válassza ki az „Instrastat modell” elemet.</span><span class="sxs-lookup"><span data-stu-id="a966d-137">In the tree, select 'Intrastat model'.</span></span>
2. <span data-ttu-id="a966d-138">A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="a966d-138">Click Create configuration to open the drop dialog.</span></span>
3. <span data-ttu-id="a966d-139">Az Új mezőbe írja be az „Intrastat adatmodellen alapuló modell-leképezés” kifejezést.</span><span class="sxs-lookup"><span data-stu-id="a966d-139">In the New field, enter 'Model Mapping based on data model Intrastat'.</span></span>
4. <span data-ttu-id="a966d-140">A Név mezőbe írja be az „Intrastat mintaleképezés” szöveget.</span><span class="sxs-lookup"><span data-stu-id="a966d-140">In the Name field, type 'Intrastat sample mapping'.</span></span>
    * <span data-ttu-id="a966d-141">Intrastat mintaleképezés</span><span class="sxs-lookup"><span data-stu-id="a966d-141">Intrastat sample mapping</span></span>  
5. <span data-ttu-id="a966d-142">Kattintson a Konfiguráció létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a966d-142">Click Create configuration.</span></span>

