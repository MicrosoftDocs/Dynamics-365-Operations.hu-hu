---
title: Hozzáadás saját teljesítménynaplóhoz és pozitív visszajelzés elküldése másnak
description: A teljesítménynapló a célok teljesítésének módjával, valamint adott időszak során nyújtott teljesítménnyel kapcsolatos információkat tartalmaz.
author: ShielaSogge
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EssWorkspace, HcmPerfJournal, HcmPerfJournalAddLink, HcmPerfPraise, HcmWorkerLookUpByPerson, HcmPerfJournalAdd
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 07f5a16ccb349fbef4c0d2be14c1ef02ed8831dd
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "364557"
---
# <a name="add-to-your-performance-journal-and-send-praise-to-someone"></a><span data-ttu-id="71e8c-103">Hozzáadás saját teljesítménynaplóhoz és pozitív visszajelzés elküldése másnak</span><span class="sxs-lookup"><span data-stu-id="71e8c-103">Add to your performance journal and send praise to someone</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="71e8c-104">A teljesítménynapló a célok teljesítésének módjával, valamint adott időszak során nyújtott teljesítménnyel kapcsolatos információkat tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="71e8c-104">The performance journal holds information that relates to how you met your goals or how you performed during a period.</span></span> <span data-ttu-id="71e8c-105">A naplóból kollégák tevékenységéhez is küldhető dicséret.</span><span class="sxs-lookup"><span data-stu-id="71e8c-105">You can also praise the actions of a co-worker from the journal.</span></span> <span data-ttu-id="71e8c-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="71e8c-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="71e8c-107">Az eljárás egy olyan szolgáltatáshoz tartozik, amely a Dynamics 365 for Operations 1611-es verziójában jelent meg.</span><span class="sxs-lookup"><span data-stu-id="71e8c-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="71e8c-108">Lépjen a Minden munkaterület > Alkalmazotti önkiszolgáló rendszer pontra.</span><span class="sxs-lookup"><span data-stu-id="71e8c-108">Go to All workspaces > Employee self service.</span></span>
2. <span data-ttu-id="71e8c-109">Kattintson a Teljesítménynapló elemre.</span><span class="sxs-lookup"><span data-stu-id="71e8c-109">Click Performance journal.</span></span>
3. <span data-ttu-id="71e8c-110">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="71e8c-110">Click New.</span></span>
4. <span data-ttu-id="71e8c-111">Érték beírása a Címmezőbe.</span><span class="sxs-lookup"><span data-stu-id="71e8c-111">In the Title field, type a value.</span></span>
5. <span data-ttu-id="71e8c-112">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="71e8c-112">In the Description field, type a value.</span></span>
    * <span data-ttu-id="71e8c-113">A teljesítménynapló dátuma az a dátum, amikor a naplót létrehozták.</span><span class="sxs-lookup"><span data-stu-id="71e8c-113">The performance journal date is the date that the journal was created.</span></span>  
    * <span data-ttu-id="71e8c-114">A forrás azt mutatja, honnan származik a teljesítménynapló.</span><span class="sxs-lookup"><span data-stu-id="71e8c-114">The source represents where the performance journal came from.</span></span> <span data-ttu-id="71e8c-115">Amikor létrehoz egyet, az a Saját naplóból származik.</span><span class="sxs-lookup"><span data-stu-id="71e8c-115">When you create one, it comes from My journal.</span></span> <span data-ttu-id="71e8c-116">Ha a vezető hoz létre egyet, az a Vezető naplóból származik.</span><span class="sxs-lookup"><span data-stu-id="71e8c-116">If your manager creates one, it comes from the Manager journal.</span></span>  
    * <span data-ttu-id="71e8c-117">A napló megosztható a vezetővel, illetve beállítható, hogy csak Ön lássa.</span><span class="sxs-lookup"><span data-stu-id="71e8c-117">You can share this journal with your manager or make it only visible to you.</span></span>  
6. <span data-ttu-id="71e8c-118">Adja meg a dátumot a Kezdő dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="71e8c-118">In the Start date field, enter a date.</span></span>
7. <span data-ttu-id="71e8c-119">Adja meg a dátumot a Befejezés dátuma mezőben.</span><span class="sxs-lookup"><span data-stu-id="71e8c-119">In the Date completed field, enter a date.</span></span>
8. <span data-ttu-id="71e8c-120">A Fejlesztési terv mezőben válassza az Igen lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="71e8c-120">Select Yes in the Development plan field.</span></span>
9. <span data-ttu-id="71e8c-121">A Kulcsszavak mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="71e8c-121">In the Keywords field, type a value.</span></span>
10. <span data-ttu-id="71e8c-122">Kattintson a Külső hivatkozás hozzáadása elemre.</span><span class="sxs-lookup"><span data-stu-id="71e8c-122">Click Add external link.</span></span>
11. <span data-ttu-id="71e8c-123">A Leírás mezőbe írja be az „Envision” értéket.</span><span class="sxs-lookup"><span data-stu-id="71e8c-123">In the Description field, type 'Envision'.</span></span>
12. <span data-ttu-id="71e8c-124">Írja be a(z) „https://www.microsoft.com/en/envision/default” értéket az internetcím mezőbe.</span><span class="sxs-lookup"><span data-stu-id="71e8c-124">In the Internet address field, type 'https://www.microsoft.com/en/envision/default'.</span></span>
13. <span data-ttu-id="71e8c-125">Kattintson a Mentés gomb alatti "Teljesítménynapló" feliratra a rácshoz való visszatéréshez.</span><span class="sxs-lookup"><span data-stu-id="71e8c-125">Click on the caption below the Save button called "Performance journal" to return to the grid.</span></span>
    * <span data-ttu-id="71e8c-126">A kijelölt napló vagy naplók hozzáadhatók egy célhoz, és ezt követően megjelennek a cél megnyitásakor.</span><span class="sxs-lookup"><span data-stu-id="71e8c-126">You can add the selected journal or journals to a goal so that it appears when you open the goal.</span></span> <span data-ttu-id="71e8c-127">Bekerül egy hivatkozás a Hivatkozások gyorslapra. Ha egy naplót hozzáad egy célhoz, majd a célt hozzáadja egy ellenőrzéshez, úgy a napló automatikusan megjelenik az ellenőrzésben.</span><span class="sxs-lookup"><span data-stu-id="71e8c-127">A link will be added in the Links fast tab.    If you add a journal to a goal and then add the goal to a review, the journal will appear on the review automatically.</span></span>  
    * <span data-ttu-id="71e8c-128">A kijelölt napló vagy naplók hozzáadhatók egy ellenőrzéshez, és ezt követően megjelennek az ellenőrzés megnyitásakor.</span><span class="sxs-lookup"><span data-stu-id="71e8c-128">You can add the selected journal or journals to a review so that it appears when you open the review.</span></span>    <span data-ttu-id="71e8c-129">Bekerül egy hivatkozás a Hivatkozások gyorslapra.</span><span class="sxs-lookup"><span data-stu-id="71e8c-129">A link will be added in the Links fast tab.</span></span>  
14. <span data-ttu-id="71e8c-130">Kattintson a Gyors hozzáadás elemre.</span><span class="sxs-lookup"><span data-stu-id="71e8c-130">Click Quick add.</span></span>
15. <span data-ttu-id="71e8c-131">Érték beírása a Címmezőbe.</span><span class="sxs-lookup"><span data-stu-id="71e8c-131">In the Title field, type a value.</span></span>
16. <span data-ttu-id="71e8c-132">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="71e8c-132">In the Description field, type a value.</span></span>
17. <span data-ttu-id="71e8c-133">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="71e8c-133">Click Save.</span></span>
18. <span data-ttu-id="71e8c-134">Kattintson a Dicséret küldése elemre.</span><span class="sxs-lookup"><span data-stu-id="71e8c-134">Click Send praise.</span></span>
19. <span data-ttu-id="71e8c-135">Válasszon ki valakit a cég alkalmazottainak listájából.</span><span class="sxs-lookup"><span data-stu-id="71e8c-135">Select a person from the list of employees in the company.</span></span>
20. <span data-ttu-id="71e8c-136">A Leírás mezőbe írja be a „Köszönöm a konferencián nyújtott sok segítséget!” szöveget.</span><span class="sxs-lookup"><span data-stu-id="71e8c-136">In the Description field, enter 'Thanks for all the help at the conference!'.</span></span>
21. <span data-ttu-id="71e8c-137">Kattintson a Küldés gombra.</span><span class="sxs-lookup"><span data-stu-id="71e8c-137">Click Send.</span></span>

