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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 036bd9f592ca584afad9d4b9b7a49a9787076056
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---
# <a name="copy-a-formula"></a><span data-ttu-id="1f2a0-103">Receptúra másolása</span><span class="sxs-lookup"><span data-stu-id="1f2a0-103">Copy a formula</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1f2a0-104">Ez az eljárás olyan receptúra létrehozására koncentrál, amely ugyanazokat az összetevőket tartalmazza, mint a meglévő receptúra, apró eltérésekkel.</span><span class="sxs-lookup"><span data-stu-id="1f2a0-104">This procedure focuses on creating a formula that includes the same ingredients as an existing formula, but with minor differences.</span></span> <span data-ttu-id="1f2a0-105">A receptúrasorok létrehozásához a Másolás funkció segítségével másolhat egy meglévő receptúra, amely tartalmazza a legtöbb szükséges összetevőt.</span><span class="sxs-lookup"><span data-stu-id="1f2a0-105">To create the formula lines, you can use the Copy function to copy an existing formula that has most of the ingredients that you need.</span></span> <span data-ttu-id="1f2a0-106">Ezután az új verzióban az egyes sorokban elvégezheti a szükséges módosításokat.</span><span class="sxs-lookup"><span data-stu-id="1f2a0-106">You can then make any necessary changes to the individual lines in the new version.</span></span> <span data-ttu-id="1f2a0-107">A Másolás funkcióval nem szükséges több, szinte megegyező receptúrát elkészítenie.</span><span class="sxs-lookup"><span data-stu-id="1f2a0-107">By using the Copy function, you do not have to create multiple formulas that are almost identical.</span></span> <span data-ttu-id="1f2a0-108">A bemutató adatsor, amelyet a vállalat használt ezen feladat készítéséhez, az USP2.</span><span class="sxs-lookup"><span data-stu-id="1f2a0-108">The demo data company used to create this task is USP2.</span></span>


## <a name="create-a-formula"></a><span data-ttu-id="1f2a0-109">Receptúra létrehozása</span><span class="sxs-lookup"><span data-stu-id="1f2a0-109">Create a formula</span></span>
1. <span data-ttu-id="1f2a0-110">Ugorjon a Termékinformációk kezelése > Anyagjegyzékek anyagok és képletek > Receptúrák pontra.</span><span class="sxs-lookup"><span data-stu-id="1f2a0-110">Go to Product information management > Bills of materials and formulas > Formulas.</span></span>
2. <span data-ttu-id="1f2a0-111">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1f2a0-111">Click New.</span></span>
3. <span data-ttu-id="1f2a0-112">Írjon be egy értéket a Receptúra mezőbe.</span><span class="sxs-lookup"><span data-stu-id="1f2a0-112">In the Formula field, type a value.</span></span>
4. <span data-ttu-id="1f2a0-113">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="1f2a0-113">In the Name field, type a value.</span></span>
    * <span data-ttu-id="1f2a0-114">Adjon meg egy értelmes nevet a képletnek.</span><span class="sxs-lookup"><span data-stu-id="1f2a0-114">Type a meaningful name for the formula.</span></span>  
5. <span data-ttu-id="1f2a0-115">A Hely mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="1f2a0-115">In the Site field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="1f2a0-116">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="1f2a0-116">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="1f2a0-117">A Cikkcsoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="1f2a0-117">In the Item group field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="1f2a0-118">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="1f2a0-118">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="1f2a0-119">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="1f2a0-119">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="1f2a0-120">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="1f2a0-120">Click Save.</span></span>

## <a name="copy-formula-lines"></a><span data-ttu-id="1f2a0-121">Receptúrasorok másolása</span><span class="sxs-lookup"><span data-stu-id="1f2a0-121">Copy formula lines</span></span>
1. <span data-ttu-id="1f2a0-122">A Művelet panelen kattintson a Receptúra elemre.</span><span class="sxs-lookup"><span data-stu-id="1f2a0-122">On the Action Pane, click Formula.</span></span>
2. <span data-ttu-id="1f2a0-123">Kattintson a Másolás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1f2a0-123">Click Copy.</span></span>
3. <span data-ttu-id="1f2a0-124">A Cikkszám mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="1f2a0-124">In the Item number field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="1f2a0-125">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="1f2a0-125">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="1f2a0-126">A Receptúraverzió mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="1f2a0-126">In the Formula version field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="1f2a0-127">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="1f2a0-127">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="1f2a0-128">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="1f2a0-128">Click OK.</span></span>

## <a name="adjust-copied-formula-lines"></a><span data-ttu-id="1f2a0-129">Másolt receptúrasorok beállítása</span><span class="sxs-lookup"><span data-stu-id="1f2a0-129">Adjust copied formula lines</span></span>
1. <span data-ttu-id="1f2a0-130">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="1f2a0-130">In the list, mark the selected row.</span></span>
2. <span data-ttu-id="1f2a0-131">Kattintson a Törlés gombra.</span><span class="sxs-lookup"><span data-stu-id="1f2a0-131">Click Delete.</span></span>
3. <span data-ttu-id="1f2a0-132">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="1f2a0-132">Click Yes.</span></span>

## <a name="approve-formula"></a><span data-ttu-id="1f2a0-133">Receptúra jóváhagyása</span><span class="sxs-lookup"><span data-stu-id="1f2a0-133">Approve formula</span></span>
1. <span data-ttu-id="1f2a0-134">A Művelet panelen kattintson a Receptúra elemre.</span><span class="sxs-lookup"><span data-stu-id="1f2a0-134">On the Action Pane, click Formula.</span></span>
2. <span data-ttu-id="1f2a0-135">Kattintson a Receptúra jóváhagyása pontra.</span><span class="sxs-lookup"><span data-stu-id="1f2a0-135">Click Approve formula.</span></span>
3. <span data-ttu-id="1f2a0-136">A Jóváhagyó mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="1f2a0-136">In the Approved by field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="1f2a0-137">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="1f2a0-137">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="1f2a0-138">Kattintson a Kiválasztás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1f2a0-138">Click Select.</span></span>
6. <span data-ttu-id="1f2a0-139">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="1f2a0-139">Click OK.</span></span>


