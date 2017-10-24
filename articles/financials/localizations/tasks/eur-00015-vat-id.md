--- 
title: "Áfaazonosító beállítása"
description: "Ez az eljárás végigvezeti az áfaazonosító regisztrációs előfeltételein, például egy regisztrációs típus beállításán és a hozzárendelésén egy nyilvántartási kategóriához."
author: v-oloski
manager: AnnBe
ms.date: 10/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 20f64385b988ff48d865d2d521a9e580dc04c4a2
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-vat-id"></a><span data-ttu-id="83ae9-103">Áfaazonosító beállítása</span><span class="sxs-lookup"><span data-stu-id="83ae9-103">Set up VAT ID</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="83ae9-104">Ez az eljárás végigvezeti az áfaazonosító regisztrációs előfeltételein, például egy regisztrációs típus beállításán és a hozzárendelésén egy nyilvántartási kategóriához.</span><span class="sxs-lookup"><span data-stu-id="83ae9-104">This procedure walks you through VAT ID registration prerequisites, such as setting up a registration type and assigning it to a registration category.</span></span> <span data-ttu-id="83ae9-105">További információ a regisztrációs azonosítókról és a regisztrációs azonosítók feldolgozásáról, a szükséges előfeltételeket is beleértve, a Regisztrációs azonosító súgótémakörben található.</span><span class="sxs-lookup"><span data-stu-id="83ae9-105">You can find additional information about registration IDs and registration ID processing, including required prerequisites, in the Registration IDs help topic.</span></span> 

<span data-ttu-id="83ae9-106">Ez az információ minden európai országra/régióra vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="83ae9-106">The information here applies to all European countries/regions.</span></span> <span data-ttu-id="83ae9-107">Ezt a feladatot elsődleges németországi címmel rendelkező DEMF bemutatócég mint jogi személy segítségével hozták létre.</span><span class="sxs-lookup"><span data-stu-id="83ae9-107">The task was created using the demo data company DEMF with Germany as the legal entity primary address.</span></span> <span data-ttu-id="83ae9-108">Ez a feladat rendszergazdáknak szól.</span><span class="sxs-lookup"><span data-stu-id="83ae9-108">This task is intended for system administrators.</span></span> <span data-ttu-id="83ae9-109">Ez az eljárás egy olyan funkcióra vonatkozik, amely a Dynamics 365 for Operations 1611-es verziójába került be.</span><span class="sxs-lookup"><span data-stu-id="83ae9-109">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="83ae9-110">Ugrás a Szervezeti adminisztráció > Globális címjegyzék > Regisztrációtípusok > Regisztrációtípusok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="83ae9-110">Go to Organization administration > Global address book > Registration types > Registration types.</span></span>
2. <span data-ttu-id="83ae9-111">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="83ae9-111">Click New to open the drop dialog.</span></span>
3. <span data-ttu-id="83ae9-112">A Név mezőbe írja be az „Áfaazonosító” szöveget.</span><span class="sxs-lookup"><span data-stu-id="83ae9-112">In the Name field, type 'VAT ID'.</span></span>
4. <span data-ttu-id="83ae9-113">A Leírás mezőbe írja be az áfaazonosítót.</span><span class="sxs-lookup"><span data-stu-id="83ae9-113">In the Description field, VAT number.</span></span>
5. <span data-ttu-id="83ae9-114">Az Ország/régió mezőben adja meg vagy válassza a DEU értéket</span><span class="sxs-lookup"><span data-stu-id="83ae9-114">In the Country/region field, enter or select a value DEU</span></span>
6. <span data-ttu-id="83ae9-115">Válassza ki az Igen lehetőséget az Egyedi mezőben.</span><span class="sxs-lookup"><span data-stu-id="83ae9-115">Select Yes in the Unique field.</span></span>
    * <span data-ttu-id="83ae9-116">Jelölje be ezt a jelölőnégyzetet annak ellenőrzéséhez, hogy az áfaazonosító egyedi-e.</span><span class="sxs-lookup"><span data-stu-id="83ae9-116">Select this check box to verify if the VAT ID is unique.</span></span>  
7. <span data-ttu-id="83ae9-117">Válassza az Igen lehetőséget az Ország elsődleges címe mezőben.</span><span class="sxs-lookup"><span data-stu-id="83ae9-117">Select Yes in the Primary for country field.</span></span>
    * <span data-ttu-id="83ae9-118">Jelölje be ezt a jelölőnégyzetet, ha az áfaazonosítónak a megadott országhoz/régióhoz tartozó összes címhez érvényesnek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="83ae9-118">Select this check box if the VAT ID should be effective for all addresses belonging to the specified country/region.</span></span>  
8. <span data-ttu-id="83ae9-119">Kattintson a Létrehozás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="83ae9-119">Click Create.</span></span>
9. <span data-ttu-id="83ae9-120">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="83ae9-120">Click Add.</span></span>
10. <span data-ttu-id="83ae9-121">Az Ország/régió mezőben adja meg vagy válassza az ITA értéket</span><span class="sxs-lookup"><span data-stu-id="83ae9-121">In the Country/region field, enter or select a value ITA</span></span>
11. <span data-ttu-id="83ae9-122">A Formátum mezőbe írja be a következő értéket „###########”.</span><span class="sxs-lookup"><span data-stu-id="83ae9-122">In the Format field, type '###########'.</span></span>
    * <span data-ttu-id="83ae9-123">Amikor ilyen típusú kijelölt országhoz/régióhoz ad meg regisztrációs azonosítót, a regisztrációs azonosítót ennek a formátumnak megfelelően ellenőrizzük.</span><span class="sxs-lookup"><span data-stu-id="83ae9-123">When you enter a registration ID of this type for the selected country/region, the registration ID will be verified against this format.</span></span>  
12. <span data-ttu-id="83ae9-124">Jelölje be az Egyedi jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="83ae9-124">Select the Unique check box.</span></span>
    * <span data-ttu-id="83ae9-125">Jelölje be ezt a jelölőnégyzetet annak ellenőrzéséhez, hogy az áfaazonosító egyedi-e.</span><span class="sxs-lookup"><span data-stu-id="83ae9-125">Select this check box to verify if the VAT ID is unique.</span></span>  
13. <span data-ttu-id="83ae9-126">Jelölje be az Ország elsődleges címe jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="83ae9-126">Select the Primary for country check box.</span></span>
    * <span data-ttu-id="83ae9-127">Jelölje be ezt a jelölőnégyzetet, ha az áfaazonosítónak a megadott országhoz/régióhoz tartozó összes címhez érvényesnek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="83ae9-127">Select this check box if the VAT ID should be effective for all addresses belonging to the specified country/region.</span></span>  
14. <span data-ttu-id="83ae9-128">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="83ae9-128">Click Save.</span></span>
15. <span data-ttu-id="83ae9-129">Ugrás a Szervezeti adminisztráció > Globális címjegyzék > Regisztrációtípusok > Nyilvántartási kategóriák lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="83ae9-129">Go to Organization administration > Global address book > Registration types > Registration categories.</span></span>
16. <span data-ttu-id="83ae9-130">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="83ae9-130">Click New.</span></span>
17. <span data-ttu-id="83ae9-131">Az Ország/régió mezőben adja meg vagy válassza az Áfaazonosító, DEU értéket</span><span class="sxs-lookup"><span data-stu-id="83ae9-131">In the Country/region field, enter or select a value VAT ID, DEU</span></span>
18. <span data-ttu-id="83ae9-132">A Nyilvántartási kategória mezőben válassza az „Áfaazonosító” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83ae9-132">In the Registration category field, select 'VAT ID'.</span></span>
    * <span data-ttu-id="83ae9-133">Rendelje hozzá a korábban létrehozott regisztrációs típust egy előre megadott nyilvántartási kategóriához.</span><span class="sxs-lookup"><span data-stu-id="83ae9-133">Assign the registration type that you created earlier to a predefined Registration category.</span></span>  
19. <span data-ttu-id="83ae9-134">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="83ae9-134">Click New.</span></span>
20. <span data-ttu-id="83ae9-135">Az Ország/régió mezőben adja meg vagy válassza az Áfaazonosító, ITA értéket</span><span class="sxs-lookup"><span data-stu-id="83ae9-135">In the Country/region field, enter or select a value VAT ID, ITA</span></span>
21. <span data-ttu-id="83ae9-136">A Nyilvántartási kategória mezőben válassza az „Áfaazonosító” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83ae9-136">In the Registration category field, select 'VAT ID'.</span></span>
    * <span data-ttu-id="83ae9-137">Rendelje hozzá a létrehozott regisztrációs típust egy előre megadott nyilvántartási kategóriához.</span><span class="sxs-lookup"><span data-stu-id="83ae9-137">Assign the registration type that you created to a predefined registration category.</span></span>  
22. <span data-ttu-id="83ae9-138">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="83ae9-138">Click Save.</span></span>


