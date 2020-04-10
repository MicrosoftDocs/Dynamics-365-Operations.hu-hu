---
title: Meglévő tevékenység hozzáadása termelési folyamat verziójához
description: A termelési folyamatok új verzióinak létrehozásakor lehetőség van a régebbi verziókhoz létrehozott tevékenységek hozzáadására az új verzióhoz.
author: cvocph
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityAddExisting, PlanActivityAddExistingLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c01d988469ead4ab09d69b1cb6e2f9b417080c69
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3149412"
---
# <a name="add-an-existing-activity-to-a-production-flow-version"></a><span data-ttu-id="8172d-103">Meglévő tevékenység hozzáadása termelési folyamat verziójához</span><span class="sxs-lookup"><span data-stu-id="8172d-103">Add an existing activity to a production flow version</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8172d-104">A termelési folyamatok új verzióinak létrehozásakor lehetőség van a régebbi verziókhoz létrehozott tevékenységek hozzáadására az új verzióhoz.</span><span class="sxs-lookup"><span data-stu-id="8172d-104">When creating new versions of production flows, you can choose to add activities created for the older versions, to the new version.</span></span> <span data-ttu-id="8172d-105">Ez az eljárás azt mutatja be, hogyan lehet új verziót létrehozni egy meglévő termelési folyamathoz a tevékenységek másolása nélkül.</span><span class="sxs-lookup"><span data-stu-id="8172d-105">This procedure shows how a new version is created for an existing production flow, without copying the activities.</span></span> <span data-ttu-id="8172d-106">A következő lépésben egy meglévő tevékenységet adunk az új verzióhoz.</span><span class="sxs-lookup"><span data-stu-id="8172d-106">In the next step, an existing activity is added to the new version.</span></span> 

<span data-ttu-id="8172d-107">A feladathoz már létrehozott verzióval és tevékenységekkel rendelkező termelési folyamatra van szükség.</span><span class="sxs-lookup"><span data-stu-id="8172d-107">This task requires production flow with version and activities already created.</span></span>


## <a name="create-a-new-production-flow-version"></a><span data-ttu-id="8172d-108">Termelési folyamat új verziójának létrehozása</span><span class="sxs-lookup"><span data-stu-id="8172d-108">Create a new production flow version</span></span>
1. <span data-ttu-id="8172d-109">Ugrás a Gyártásvezérléshez > Beállítás > Lean típusú termelési folyamat > Termelési folyamatok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8172d-109">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="8172d-110">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="8172d-110">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="8172d-111">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="8172d-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="8172d-112">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8172d-112">Click Edit.</span></span>
5. <span data-ttu-id="8172d-113">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="8172d-113">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="8172d-114">Az Lejárati dátum mezőben adjon meg egy dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="8172d-114">In the Expiration date field, enter a date and time.</span></span>
    * <span data-ttu-id="8172d-115">Megjegyzés: egy új termelésifolyamat-verzió létrehozása előtt ellenőrizze az aktív verzió lejárati dátumát és időpontját.</span><span class="sxs-lookup"><span data-stu-id="8172d-115">Note that before you create a new production flow version, make sure to check the expiration date and time of the active version.</span></span> <span data-ttu-id="8172d-116">Az új verzió az érvényesség kezdő dátumával jön létre, amely a kijelölt verzió lejárati dátumához kapcsolódik.</span><span class="sxs-lookup"><span data-stu-id="8172d-116">The new version will be created with an effective start date, which connects to the expiry date of the selected version.</span></span>  
7. <span data-ttu-id="8172d-117">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="8172d-117">Click Add.</span></span>
8. <span data-ttu-id="8172d-118">Válassza a Nem lehetőséget a Másolás verzióból mezőben.</span><span class="sxs-lookup"><span data-stu-id="8172d-118">Select No in the Copy from version field.</span></span>
    * <span data-ttu-id="8172d-119">Válassza a Nem lehetőséget, ha üres verzióval szeretne kezdeni, abban az esetben, ha a másolt verzió tevékenységeinek legtöbbje új tevékenységekre lesz cserélve.</span><span class="sxs-lookup"><span data-stu-id="8172d-119">Select No to start with an empty version if most of the activities of the copied version will be replaced by new activities.</span></span> <span data-ttu-id="8172d-120">A változatlan tevékenységeket manuálisan adja hozzá a tevékenység űrlap Meglévő hozzáadása funkciójával.</span><span class="sxs-lookup"><span data-stu-id="8172d-120">Add the unchanged activities to the Add existing function in the activity form manually.</span></span>  
9. <span data-ttu-id="8172d-121">Válassza a Nem lehetőséget az Ismétlődő kanbanszabályok mezőben.</span><span class="sxs-lookup"><span data-stu-id="8172d-121">Select No in the Duplicate kanban rules field.</span></span>
    * <span data-ttu-id="8172d-122">Ha a tevékenységeket nem másolja át az új verzióba, nincs lehetőség a kanbanszabályok átmásolására az új verzió létrehozásakor.</span><span class="sxs-lookup"><span data-stu-id="8172d-122">When the activities are not copied to the new version, it is not possible to copy the kanban rules at the time of creation of the new version.</span></span>   <span data-ttu-id="8172d-123">Ehelyett a helyettesítő kanban létrehozása funkciót használjuk a későbbiekben a kanbanszabály képernyőn a régi termelésifolyamat-verziójának kanbanszabályainak lecserélésére az új verzió a tevékenységeit használó kanbanszabályokra.</span><span class="sxs-lookup"><span data-stu-id="8172d-123">Instead you will use the create replacement kanban function later in the kanban rule form, to replace kanban rules of the old production flow version with kanban rules using the activities of the new version.</span></span>  
10. <span data-ttu-id="8172d-124">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="8172d-124">Click OK.</span></span>
11. <span data-ttu-id="8172d-125">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="8172d-125">In the list, find and select the desired record.</span></span>

## <a name="add-an-existing-activity"></a><span data-ttu-id="8172d-126">Meglévő tevékenység hozzáadása</span><span class="sxs-lookup"><span data-stu-id="8172d-126">Add an existing activity</span></span>
1. <span data-ttu-id="8172d-127">Kattintson a Tevékenységek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8172d-127">Click Activities.</span></span>
2. <span data-ttu-id="8172d-128">Kattintson a Meglévő hozzáadása lehetőségre a legördülő párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="8172d-128">Click Add existing to open the drop dialog.</span></span>
    * <span data-ttu-id="8172d-129">Keressen meg és jelöljön ki egy meglévő tevékenységet az új termelésifolyamat-verzióhoz való hozzáadáshoz.</span><span class="sxs-lookup"><span data-stu-id="8172d-129">Find and select an existing activity to be added to the new production flow version.</span></span>  <span data-ttu-id="8172d-130">Ne feledje, hogy a lista minden olyan tevékenységet megjelenít, amelyet a termelési folyamathoz hoztak létre, a folyamat összes korábbi verziójában.</span><span class="sxs-lookup"><span data-stu-id="8172d-130">Note that the list shows all activities that have been created for this production flow for all previous versions of the flow.</span></span>  
3. <span data-ttu-id="8172d-131">A Tevékenység mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="8172d-131">In the Activity field, enter or select a value.</span></span>
4. <span data-ttu-id="8172d-132">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="8172d-132">Click OK.</span></span>

