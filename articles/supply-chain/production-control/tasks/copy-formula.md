--- 
title: "Receptúra másolása"
description: "Ez az eljárás olyan receptúra létrehozására koncentrál, amely ugyanazokat az összetevőket tartalmazza, mint a meglévő receptúra, apró eltérésekkel."
author: YuyuScheller
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 61985d18f03a4afd8d94b23486cc462d2a868493
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---
# <a name="copy-a-formula"></a><span data-ttu-id="3e022-103">Receptúra másolása</span><span class="sxs-lookup"><span data-stu-id="3e022-103">Copy a formula</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3e022-104">Ez az eljárás olyan receptúra létrehozására koncentrál, amely ugyanazokat az összetevőket tartalmazza, mint a meglévő receptúra, apró eltérésekkel.</span><span class="sxs-lookup"><span data-stu-id="3e022-104">This procedure focuses on creating a formula that includes the same ingredients as an existing formula, but with minor differences.</span></span> <span data-ttu-id="3e022-105">A receptúrasorok létrehozásához a Másolás funkció segítségével másolhat egy meglévő receptúra, amely tartalmazza a legtöbb szükséges összetevőt.</span><span class="sxs-lookup"><span data-stu-id="3e022-105">To create the formula lines, you can use the Copy function to copy an existing formula that has most of the ingredients that you need.</span></span> <span data-ttu-id="3e022-106">Ezután az új verzióban az egyes sorokban elvégezheti a szükséges módosításokat.</span><span class="sxs-lookup"><span data-stu-id="3e022-106">You can then make any necessary changes to the individual lines in the new version.</span></span> <span data-ttu-id="3e022-107">A Másolás funkcióval nem szükséges több, szinte megegyező receptúrát elkészítenie.</span><span class="sxs-lookup"><span data-stu-id="3e022-107">By using the Copy function, you do not have to create multiple formulas that are almost identical.</span></span> <span data-ttu-id="3e022-108">A bemutató adatsor, amelyet a vállalat használt ezen feladat készítéséhez, az USP2.</span><span class="sxs-lookup"><span data-stu-id="3e022-108">The demo data company used to create this task is USP2.</span></span>


## <a name="create-a-formula"></a><span data-ttu-id="3e022-109">Receptúra létrehozása</span><span class="sxs-lookup"><span data-stu-id="3e022-109">Create a formula</span></span>
1. <span data-ttu-id="3e022-110">Ugorjon a Termékinformációk kezelése > Anyagjegyzékek anyagok és képletek > Receptúrák pontra.</span><span class="sxs-lookup"><span data-stu-id="3e022-110">Go to Product information management > Bills of materials and formulas > Formulas.</span></span>
2. <span data-ttu-id="3e022-111">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3e022-111">Click New.</span></span>
3. <span data-ttu-id="3e022-112">Írjon be egy értéket a Receptúra mezőbe.</span><span class="sxs-lookup"><span data-stu-id="3e022-112">In the Formula field, type a value.</span></span>
4. <span data-ttu-id="3e022-113">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="3e022-113">In the Name field, type a value.</span></span>
    * <span data-ttu-id="3e022-114">Adjon meg egy értelmes nevet a képletnek.</span><span class="sxs-lookup"><span data-stu-id="3e022-114">Type a meaningful name for the formula.</span></span>  
5. <span data-ttu-id="3e022-115">A Hely mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="3e022-115">In the Site field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="3e022-116">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="3e022-116">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="3e022-117">A Cikkcsoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="3e022-117">In the Item group field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="3e022-118">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="3e022-118">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="3e022-119">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="3e022-119">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="3e022-120">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="3e022-120">Click Save.</span></span>

## <a name="copy-formula-lines"></a><span data-ttu-id="3e022-121">Receptúrasorok másolása</span><span class="sxs-lookup"><span data-stu-id="3e022-121">Copy formula lines</span></span>
1. <span data-ttu-id="3e022-122">A Művelet panelen kattintson a Receptúra elemre.</span><span class="sxs-lookup"><span data-stu-id="3e022-122">On the Action Pane, click Formula.</span></span>
2. <span data-ttu-id="3e022-123">Kattintson a Másolás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3e022-123">Click Copy.</span></span>
3. <span data-ttu-id="3e022-124">A Cikkszám mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="3e022-124">In the Item number field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="3e022-125">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="3e022-125">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="3e022-126">A Receptúraverzió mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="3e022-126">In the Formula version field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="3e022-127">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="3e022-127">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="3e022-128">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="3e022-128">Click OK.</span></span>

## <a name="adjust-copied-formula-lines"></a><span data-ttu-id="3e022-129">Másolt receptúrasorok beállítása</span><span class="sxs-lookup"><span data-stu-id="3e022-129">Adjust copied formula lines</span></span>
1. <span data-ttu-id="3e022-130">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="3e022-130">In the list, mark the selected row.</span></span>
2. <span data-ttu-id="3e022-131">Kattintson a Törlés gombra.</span><span class="sxs-lookup"><span data-stu-id="3e022-131">Click Delete.</span></span>
3. <span data-ttu-id="3e022-132">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="3e022-132">Click Yes.</span></span>

## <a name="approve-formula"></a><span data-ttu-id="3e022-133">Receptúra jóváhagyása</span><span class="sxs-lookup"><span data-stu-id="3e022-133">Approve formula</span></span>
1. <span data-ttu-id="3e022-134">A Művelet panelen kattintson a Receptúra elemre.</span><span class="sxs-lookup"><span data-stu-id="3e022-134">On the Action Pane, click Formula.</span></span>
2. <span data-ttu-id="3e022-135">Kattintson a Receptúra jóváhagyása pontra.</span><span class="sxs-lookup"><span data-stu-id="3e022-135">Click Approve formula.</span></span>
3. <span data-ttu-id="3e022-136">A Jóváhagyó mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="3e022-136">In the Approved by field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="3e022-137">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="3e022-137">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="3e022-138">Kattintson a Kiválasztás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3e022-138">Click Select.</span></span>
6. <span data-ttu-id="3e022-139">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="3e022-139">Click OK.</span></span>


