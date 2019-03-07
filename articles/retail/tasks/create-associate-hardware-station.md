---
title: Hardverállomás létrehozása és hozzárendelése
description: Ez az eljárás végigveszi, hogyan hozhat létre egy új hardverállomást.
author: jashanno
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailHardwareStation, RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 80df4fa663d208e28f5c9b031b6610d29286171c
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "330563"
---
# <a name="create-and-associate-a-hardware-station"></a><span data-ttu-id="be899-103">Hardverállomás létrehozása és hozzárendelése</span><span class="sxs-lookup"><span data-stu-id="be899-103">Create and associate a hardware station</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="be899-104">Ez az eljárás végigveszi, hogyan hozhat létre egy új hardverállomást.</span><span class="sxs-lookup"><span data-stu-id="be899-104">This procedure walks through how to create a new hardware station.</span></span> <span data-ttu-id="be899-105">Egy új hardverprofillal új hardverállomásokat adhat hozzá egy előre definiált üzlethez (vagy üzleti csatornához).</span><span class="sxs-lookup"><span data-stu-id="be899-105">A new hardware profile will be created and used to add new hardware stations to a pre-defined store (channel).</span></span> <span data-ttu-id="be899-106">Ez az eljárás az USRT cég adatait használja, mint bemutatóadatokat.</span><span class="sxs-lookup"><span data-stu-id="be899-106">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="be899-107">Lépjen a Kereskedelmi alapok > Csatornák > ..</span><span class="sxs-lookup"><span data-stu-id="be899-107">Go to Commerce essentials > Channels > ..</span></span> <span data-ttu-id="be899-108">> ..</span><span class="sxs-lookup"><span data-stu-id="be899-108">> ..</span></span> <span data-ttu-id="be899-109">> ..</span><span class="sxs-lookup"><span data-stu-id="be899-109">> ..</span></span> <span data-ttu-id="be899-110">> Hardverállomás profiljai lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="be899-110">> Hardware station profiles.</span></span>
2. <span data-ttu-id="be899-111">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="be899-111">Click New.</span></span>
3. <span data-ttu-id="be899-112">A Hardverállomás-azonosító mezőbe írja be a következőt: „TestHWProfile”.</span><span class="sxs-lookup"><span data-stu-id="be899-112">In the Hardware station ID field, type 'TestHWProfile'.</span></span>
4. <span data-ttu-id="be899-113">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="be899-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="be899-114">Írjon be egy számot a Portszám mezőbe.</span><span class="sxs-lookup"><span data-stu-id="be899-114">In the Port number field, enter a number.</span></span>
6. <span data-ttu-id="be899-115">A Hardverprofil mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="be899-115">In the Hardware profile field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="be899-116">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="be899-116">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="be899-117">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="be899-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="be899-118">A Csomag neve mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="be899-118">In the Package name field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="be899-119">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="be899-119">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="be899-120">Ez a standard csomag, amely új környezettel érkezik.</span><span class="sxs-lookup"><span data-stu-id="be899-120">This is the standard package that comes with a new environment.</span></span> <span data-ttu-id="be899-121">A verziószám változhat.</span><span class="sxs-lookup"><span data-stu-id="be899-121">The version number may vary.</span></span>  
11. <span data-ttu-id="be899-122">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="be899-122">Click Save.</span></span>
12. <span data-ttu-id="be899-123">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="be899-123">Close the page.</span></span>
13. <span data-ttu-id="be899-124">Ugorjon a következő oldalra: Kiskereskedelem és kereskedelem > Csatornák > Minden kiskereskedelmi üzlet.</span><span class="sxs-lookup"><span data-stu-id="be899-124">Go to Retail and commerce > Channels > All retail stores.</span></span>
14. <span data-ttu-id="be899-125">Jelölje ki a 17. sort a listában.</span><span class="sxs-lookup"><span data-stu-id="be899-125">In the list, select row 17.</span></span>
    * <span data-ttu-id="be899-126">Ha az USRT bemutatócéget használja, ekkor ez a Houston üzlet.</span><span class="sxs-lookup"><span data-stu-id="be899-126">If you are using the USRT demo data company, this is the Houston store.</span></span>  
15. <span data-ttu-id="be899-127">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="be899-127">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="be899-128">Váltson a Hardverállomások szakasz kibontására.</span><span class="sxs-lookup"><span data-stu-id="be899-128">Toggle the expansion of the Hardware stations section.</span></span>
17. <span data-ttu-id="be899-129">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="be899-129">Click Add.</span></span>
18. <span data-ttu-id="be899-130">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="be899-130">In the list, mark the selected row.</span></span>
19. <span data-ttu-id="be899-131">A Profilazonosító mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="be899-131">In the Profile ID field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="be899-132">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="be899-132">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="be899-133">Ez az új hardverállomás-profil, amit az előző lépésekben hozott létre.</span><span class="sxs-lookup"><span data-stu-id="be899-133">This must be the new hardware station profile that was created in the previous steps.</span></span>  
21. <span data-ttu-id="be899-134">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="be899-134">In the list, click the link in the selected row.</span></span>
22. <span data-ttu-id="be899-135">Írjon be egy értéket az Állomás neve mezőbe.</span><span class="sxs-lookup"><span data-stu-id="be899-135">In the Host name field, type a value.</span></span>
23. <span data-ttu-id="be899-136">Írjon be egy értéket az Elektronikus átutalási terminál azonosítója mezőbe.</span><span class="sxs-lookup"><span data-stu-id="be899-136">In the EFT terminal ID field, type a value.</span></span>
24. <span data-ttu-id="be899-137">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="be899-137">Click Save.</span></span>

