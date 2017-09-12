--- 
title: " POS-engedélycsoportok létrehozása"
description: "Ez az eljárás bemutatja, hogyan hozhat létre új POS-engedélycsoportot."
author: scott-tucker
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: e924dc59c3e4cb9b6979014852512453dd3d70db
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---
# <a name="create-pos-permission-groups"></a><span data-ttu-id="221a9-103"> POS-engedélycsoportok létrehozása</span><span class="sxs-lookup"><span data-stu-id="221a9-103">Create POS permission groups</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="221a9-104">Ez az eljárás bemutatja, hogyan hozhat létre új POS-engedélycsoportot.</span><span class="sxs-lookup"><span data-stu-id="221a9-104">This procedure will show how to create a POS permission group.</span></span> <span data-ttu-id="221a9-105">A feladat létrehozásához az USRT bemutató vállalatot használtuk példaként.</span><span class="sxs-lookup"><span data-stu-id="221a9-105">The demo data company used to create this task is USRT.</span></span> <span data-ttu-id="221a9-106">A feladat a Kiskereskedelmi üzemeltetési vezető szerepkör számára készült.</span><span class="sxs-lookup"><span data-stu-id="221a9-106">This task is intended for the Retail operations manager role.</span></span>

1. <span data-ttu-id="221a9-107">Nyissa meg a következőt: Engedélycsoportok.</span><span class="sxs-lookup"><span data-stu-id="221a9-107">Go to Permission groups.</span></span>
2. <span data-ttu-id="221a9-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="221a9-108">Click New.</span></span>
3. <span data-ttu-id="221a9-109">Írjon be egy értéket a POS-engedélycsoport azonosítója mezőbe.</span><span class="sxs-lookup"><span data-stu-id="221a9-109">In the POS permission group ID field, type a value.</span></span>
4. <span data-ttu-id="221a9-110">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="221a9-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="221a9-111">Válassza ki az Igen lehetőséget a Blokkolóóra bejegyzéseinek megtekintése mezőben.</span><span class="sxs-lookup"><span data-stu-id="221a9-111">Select Yes in the View time clock entries field.</span></span>
    * <span data-ttu-id="221a9-112">Most engedélyezheti vagy a letilthatja a POS-engedélycsoport különféle engedélyeit.</span><span class="sxs-lookup"><span data-stu-id="221a9-112">You can now enable or disable various permissions for your POS Permission group.</span></span> <span data-ttu-id="221a9-113">Egyes engedélyekhez beállíthat egy értéket, amely meghatározza, hogy a pénztári felhasználó végrehajthatja-e az adott műveletet.</span><span class="sxs-lookup"><span data-stu-id="221a9-113">For some permission you can set a value that will be used to evaluate if the POS user can perform the action.</span></span>  <span data-ttu-id="221a9-114">Ez a feladat-útmutató beállít néhány, pénztárosoknak adható engedélyt.</span><span class="sxs-lookup"><span data-stu-id="221a9-114">This task guide enables a few permission that might be given to a cashier.</span></span>  
6. <span data-ttu-id="221a9-115">Válassza ki az Igen lehetőséget a Rendelés létrehozásának engedélyezése mezőben.</span><span class="sxs-lookup"><span data-stu-id="221a9-115">Select Yes in the Allow create order field.</span></span>
7. <span data-ttu-id="221a9-116">Válassza ki az Igen lehetőséget a Rendelés szerkesztésének engedélyezése mezőben.</span><span class="sxs-lookup"><span data-stu-id="221a9-116">Select Yes in the Allow edit order field.</span></span>
8. <span data-ttu-id="221a9-117">Válassza ki az Igen lehetőséget a Rendelés beolvasásának engedélyezése mezőben.</span><span class="sxs-lookup"><span data-stu-id="221a9-117">Select Yes in the Allow retrieve order field.</span></span>
9. <span data-ttu-id="221a9-118">Válassza ki az Igen lehetőséget a Jelszómódosítás engedélyezése mezőben.</span><span class="sxs-lookup"><span data-stu-id="221a9-118">Select Yes in the Allow password change field.</span></span>
10. <span data-ttu-id="221a9-119">Válassza ki az Igen lehetőséget a Számlálás nélküli zárás engedélyezése mezőben.</span><span class="sxs-lookup"><span data-stu-id="221a9-119">Select Yes in the Allow blind close field.</span></span>
11. <span data-ttu-id="221a9-120">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="221a9-120">Click Save.</span></span>
    * <span data-ttu-id="221a9-121">A módosítások mentése után futtatnia kell a Személyzetelosztási ütemezést, hogy leküldje a változtatásokat a kiskereskedelmi csatornákba.</span><span class="sxs-lookup"><span data-stu-id="221a9-121">After your changes are saved you need to run the Staff distribution schedule to push the changes to retail channels.</span></span>  
12. <span data-ttu-id="221a9-122">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="221a9-122">Close the page.</span></span>
13. <span data-ttu-id="221a9-123">Nyissa meg a következőt: Feladatok.</span><span class="sxs-lookup"><span data-stu-id="221a9-123">Go to Jobs.</span></span>
    * <span data-ttu-id="221a9-124">A következőkben hozzárendelünk egy POS-engedélycsoportot egy Feladathoz.</span><span class="sxs-lookup"><span data-stu-id="221a9-124">Next we will assign the POS permission group to a Job.</span></span>  
14. <span data-ttu-id="221a9-125">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="221a9-125">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="221a9-126">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="221a9-126">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="221a9-127">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="221a9-127">Click Edit.</span></span>
17. <span data-ttu-id="221a9-128">Bontsa ki a Munkaköri besorolás szakaszt.</span><span class="sxs-lookup"><span data-stu-id="221a9-128">Expand the Job classification section.</span></span>
18. <span data-ttu-id="221a9-129">A POS-engedélycsoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="221a9-129">In the POS permission group field, enter or select a value.</span></span>
    * <span data-ttu-id="221a9-130">Minden, ehhez a Feladathoz rendelt Pozícióban lévő Dolgozó ennek a POS-engedélycsoportnak a beállításait fogja használni, kivéve, ha a dolgozók POS-engedélyeit a Pozíció szintjén felülbírálták.</span><span class="sxs-lookup"><span data-stu-id="221a9-130">All Workers in Positions for this Job will use this POS permission group’s settings unless the workers POS permissions have been overridden at their Position level.</span></span>  
19. <span data-ttu-id="221a9-131">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="221a9-131">Click Save.</span></span>
    * <span data-ttu-id="221a9-132">A módosítások mentése után futtatnia kell a Személyzetelosztási ütemezést, hogy leküldje a változtatásokat a kiskereskedelmi csatornákba.</span><span class="sxs-lookup"><span data-stu-id="221a9-132">After your changes are saved you need to run the Staff distribution schedule to push the changes to retail channels.</span></span>  


