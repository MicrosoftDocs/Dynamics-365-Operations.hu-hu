---
title: "Adja meg a számla és dimenzió kombinációkat (szegmentált bejegyzés ellenőrzés)"
description: "A cikk bemutatja, hogyan adhat meg számla és dimenzió kombinációkat vagy főkönyvi számlákat. A bejegyzés tapasztalatot gyakran nevezik szegmentált bejegyzés ellenőrzésnek."
author: aprilolson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 14071
ms.assetid: e6fce826-c403-4d91-a78b-e9a58c44ac03
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 610b21069d9f13a511f8017d0069fda0371abf10
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---

# <a name="enter-account-and-dimension-combinations-segmented-entry-control"></a><span data-ttu-id="2302c-104">Adja meg a számla és dimenzió kombinációkat (szegmentált bejegyzés ellenőrzés)</span><span class="sxs-lookup"><span data-stu-id="2302c-104">Enter account and dimension combinations (segmented entry control)</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="2302c-105">A cikk bemutatja, hogyan adhat meg számla és dimenzió kombinációkat vagy főkönyvi számlákat.</span><span class="sxs-lookup"><span data-stu-id="2302c-105">This article describes how to enter account and dimension combinations or ledger accounts.</span></span> <span data-ttu-id="2302c-106">A bejegyzés tapasztalatot gyakran nevezik szegmentált bejegyzés ellenőrzésnek.</span><span class="sxs-lookup"><span data-stu-id="2302c-106">The entry experience is often referred to as segmented entry control.</span></span>

<span data-ttu-id="2302c-107">A felhasználók több oldalon adhatnak meg számla- és dimenziókombinációkat, például általános naplók, költségvetés-tervezés és feladásdefiníciók.</span><span class="sxs-lookup"><span data-stu-id="2302c-107">Users enter account and dimension combinations on various pages, such as pages for general journals, budgeting, and posting definitions.</span></span> <span data-ttu-id="2302c-108">Az érvényes számla és dimenzió kombináció a főkönyvhöz rendelt számlastruktúrától és a számlastruktúrához rendelt speciális szabályok függ.</span><span class="sxs-lookup"><span data-stu-id="2302c-108">The valid account and dimension combinations depend on the account structures that are assigned to the ledger and the advanced rules that are assigned to the account structures.</span></span> <span data-ttu-id="2302c-109">Amikor egy felhasználó megad egy kombinációt, begépelheti az értékeket vagy élvezheti a gazdag keresési tapasztalatok előnyeit.</span><span class="sxs-lookup"><span data-stu-id="2302c-109">When users enter a combination, they can either manually type the values or take advantage of a rich, lookup experience.</span></span> <span data-ttu-id="2302c-110">Amikor belép a mezőbe, elkezdhet gépelni, és a rendszer megkeresi az értéket és a leírást.</span><span class="sxs-lookup"><span data-stu-id="2302c-110">When you enter the field, you can start to type and it will search the value and the description.</span></span> <span data-ttu-id="2302c-111">Például ha 180-at ír be, a rendszer minden értéket megkeres, amely ezzel a számkombinációval kezdődik.</span><span class="sxs-lookup"><span data-stu-id="2302c-111">For example, if you type 180 it will search any value that begins with that number combination.</span></span> <span data-ttu-id="2302c-112">Vagy ha azt írja be, hogy Készpénz, a rendszer minden értéket megkeres, amely leírása a Készpénz szóval kezdődik.</span><span class="sxs-lookup"><span data-stu-id="2302c-112">Or you may type Cash and it will search any value that has a description that begins with Cash.</span></span> <span data-ttu-id="2302c-113">Helyettesítő karaktert is használhat (például \*Készpénz vagy \*180) a keresésre, ha az érték vagy a leírás tartalmazza a keresési feltételeket.</span><span class="sxs-lookup"><span data-stu-id="2302c-113">You can also use a wildcard, such as \*Cash or \*180 to search if the value or description contain the search criteria.</span></span> 

<span data-ttu-id="2302c-114">A következő táblázat leírja a gyorsbillentyűket, amelyek akkor használhatóak, amikor a keresés le van zárva.</span><span class="sxs-lookup"><span data-stu-id="2302c-114">The following table describes the keyboard shortcuts that can be used when the lookup is closed.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2302c-115">Billentyűparancs</span><span class="sxs-lookup"><span data-stu-id="2302c-115">Keyboard shortcut</span></span></th>
<th><span data-ttu-id="2302c-116">Művelet</span><span class="sxs-lookup"><span data-stu-id="2302c-116">Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="2302c-117">Alt+Lefelé nyíl</span><span class="sxs-lookup"><span data-stu-id="2302c-117">Alt+Down Arrow</span></span></td>
<td><span data-ttu-id="2302c-118">A keresés megnyitása</span><span class="sxs-lookup"><span data-stu-id="2302c-118">Open the lookup.</span></span> <span data-ttu-id="2302c-119">Alt + le billentyű másodszori lenyomása után a fókusz a menü szegmenseire áll.</span><span class="sxs-lookup"><span data-stu-id="2302c-119">If you press Alt+Down Arrow a second time, the focus moves to the segments in the flyout.</span></span></td>
</tr>
<tr class="even">
<td><ul>
<li><span data-ttu-id="2302c-120">Adja meg, és nyomja le a Shift + Enter kombinációt</span><span class="sxs-lookup"><span data-stu-id="2302c-120">Enter and Shift+Enter</span></span></li>
<li><span data-ttu-id="2302c-121">Számlatükör-elválasztó</span><span class="sxs-lookup"><span data-stu-id="2302c-121">Chart of accounts delimiter</span></span></li>
<li><span data-ttu-id="2302c-122">Felfelé nyíl és jobbra nyíl</span><span class="sxs-lookup"><span data-stu-id="2302c-122">Right Arrow and Left Arrow</span></span></li>
</ul></td>
<td><span data-ttu-id="2302c-123">Ugrás a következő vagy az előző szegmensre</span><span class="sxs-lookup"><span data-stu-id="2302c-123">Move to the next or previous segment.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="2302c-124">Lap</span><span class="sxs-lookup"><span data-stu-id="2302c-124">Tab</span></span></td>
<td><span data-ttu-id="2302c-125">Lépjen a következő mezőre a rácson.</span><span class="sxs-lookup"><span data-stu-id="2302c-125">Move to the next field in the grid.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2302c-126">A következő táblázat leírja a gyorsbillentyűket, amelyek akkor használhatóak, amikor a keresés nyitott.</span><span class="sxs-lookup"><span data-stu-id="2302c-126">The following table describes the keyboard shortcuts that can be used when the lookup is open.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2302c-127">Billentyűparancs</span><span class="sxs-lookup"><span data-stu-id="2302c-127">Keyboard shortcut</span></span></th>
<th><span data-ttu-id="2302c-128">Művelet</span><span class="sxs-lookup"><span data-stu-id="2302c-128">Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="2302c-129">Esc</span><span class="sxs-lookup"><span data-stu-id="2302c-129">Esc</span></span></td>
<td><span data-ttu-id="2302c-130">Zárja be a keresést.</span><span class="sxs-lookup"><span data-stu-id="2302c-130">Close the lookup.</span></span></td>
</tr>
<tr class="even">
<td><ul>
<li><span data-ttu-id="2302c-131">Felfelé nyíl és lefelé nyíl</span><span class="sxs-lookup"><span data-stu-id="2302c-131">Up Arrow and Down Arrow</span></span></li>
<li><span data-ttu-id="2302c-132">Page Up és Page Down</span><span class="sxs-lookup"><span data-stu-id="2302c-132">Page Up and Page Down</span></span></li>
<li><span data-ttu-id="2302c-133">Home és End</span><span class="sxs-lookup"><span data-stu-id="2302c-133">Home and End</span></span></li>
</ul></td>
<td><span data-ttu-id="2302c-134">Lépjen az előző vagy következő értékre a listában, az előző vagy a következő értékcsoportra, vagy a keresés első vagy utolsó elemére.</span><span class="sxs-lookup"><span data-stu-id="2302c-134">Move to the previous or next value in the lists, to the previous or next group of values, or to the first or last element in the lookup.</span></span></td>
</tr>
<tr class="odd">
<td><ul>
<li><span data-ttu-id="2302c-135">Számlatükör-elválasztó</span><span class="sxs-lookup"><span data-stu-id="2302c-135">Chart of accounts delimiter</span></span></li>
<li><span data-ttu-id="2302c-136">Felfelé nyíl és jobbra nyíl</span><span class="sxs-lookup"><span data-stu-id="2302c-136">Right Arrow and Left Arrow</span></span></li>
</ul></td>
<td><span data-ttu-id="2302c-137">Ugrás a következő vagy az előző szegmensre</span><span class="sxs-lookup"><span data-stu-id="2302c-137">Move to the next or previous segment.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="2302c-138">Lap</span><span class="sxs-lookup"><span data-stu-id="2302c-138">Tab</span></span></td>
<td><span data-ttu-id="2302c-139">Lépjen a következő mezőre a rácson.</span><span class="sxs-lookup"><span data-stu-id="2302c-139">Move to the next field in the grid.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="2302c-140">Alt+W</span><span class="sxs-lookup"><span data-stu-id="2302c-140">Alt+W</span></span></td>
<td><span data-ttu-id="2302c-141">Váltás <strong>Minden megjelenítése</strong> és <strong>Érvényesek megjelenítése</strong> módok között.</span><span class="sxs-lookup"><span data-stu-id="2302c-141">Switch between <strong>Show all</strong> and <strong>Show valid</strong>.</span></span></td>
</tr>
</tbody>
</table>

 




