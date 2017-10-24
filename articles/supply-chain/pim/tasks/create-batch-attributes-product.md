--- 
title: "Termék kötegattribútumainak létrehozása"
description: "Ez az eljárás bemutatja, hogyan hozható létre kötegattribútum, hogyan rendelhető hozzá alapértelmezett értéktartomány, hogyan szerepeltethető az attribútum egy csoportban."
author: YuyuScheller
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 5694ac4ec47b446c19681bfb5c6b07ff82f4575f
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="create-batch-attributes-for-a-product"></a><span data-ttu-id="6cf51-103">Termék kötegattribútumainak létrehozása</span><span class="sxs-lookup"><span data-stu-id="6cf51-103">Create batch attributes for a product</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6cf51-104">Ez az eljárás bemutatja, hogyan hozható létre kötegattribútum, hogyan rendelhető hozzá alapértelmezett értéktartomány, hogyan szerepeltethető az attribútum egy csoportban.</span><span class="sxs-lookup"><span data-stu-id="6cf51-104">This procedure shows how to create a batch attribute, assign default value ranges, and include the attribute in a group.</span></span> <span data-ttu-id="6cf51-105">Az eljárás létrehozásához az USP2 bemutatócéget használtuk.</span><span class="sxs-lookup"><span data-stu-id="6cf51-105">The demo data company used to create this procedure is the USP2 Company.</span></span>

1. <span data-ttu-id="6cf51-106">Ugorjon a Készletkezelés > Beállítás > Köteg > Kötegattribútumok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6cf51-106">Go to Inventory management > Setup > Batch > Batch attributes.</span></span>
2. <span data-ttu-id="6cf51-107">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6cf51-107">Click New.</span></span>
3. <span data-ttu-id="6cf51-108">Írjon be egy értéket az Attribútum mezőbe.</span><span class="sxs-lookup"><span data-stu-id="6cf51-108">In the Attribute field, type a value.</span></span>
4. <span data-ttu-id="6cf51-109">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6cf51-109">In the Description field, type a value.</span></span>
5. <span data-ttu-id="6cf51-110">Válassza ki a Tört lehetőséget az Attribútum mezőben.</span><span class="sxs-lookup"><span data-stu-id="6cf51-110">In the Attribute type field, select 'Fraction'.</span></span>
    * <span data-ttu-id="6cf51-111">Ezzel az eljárással engedélyezheti a tizedes értékeket a Tört típussal.</span><span class="sxs-lookup"><span data-stu-id="6cf51-111">This procedure uses the Fraction type to enable decimal values.</span></span> <span data-ttu-id="6cf51-112">Egyéb attribútumtípusokat is választhat.</span><span class="sxs-lookup"><span data-stu-id="6cf51-112">You can select other attribute types.</span></span> <span data-ttu-id="6cf51-113">A Felsorolási típus választásakor meg kell adni értékeket a felsorolási listában, mielőtt megadhat egy értéket a Cél mezőben.</span><span class="sxs-lookup"><span data-stu-id="6cf51-113">If you select the Enumeration type, you must enter values in the enumeration list before you can enter a value in the Target field.</span></span>  
6. <span data-ttu-id="6cf51-114">Adjon meg egy számot a Minimum mezőben.</span><span class="sxs-lookup"><span data-stu-id="6cf51-114">In the Minimum field, enter a number.</span></span>
7. <span data-ttu-id="6cf51-115">Adjon meg egy számot a Maximum mezőben.</span><span class="sxs-lookup"><span data-stu-id="6cf51-115">In the Maximum field, enter a number.</span></span>
8. <span data-ttu-id="6cf51-116">Adjon meg egy számot a Növekmény mezőben.</span><span class="sxs-lookup"><span data-stu-id="6cf51-116">In the Increment field, enter a number.</span></span>
9. <span data-ttu-id="6cf51-117">Írjon be egy értéket a Cél mezőbe.</span><span class="sxs-lookup"><span data-stu-id="6cf51-117">In the Target field, type a value.</span></span>
10. <span data-ttu-id="6cf51-118">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="6cf51-118">Click Save.</span></span>
11. <span data-ttu-id="6cf51-119">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="6cf51-119">Close the page.</span></span>
12. <span data-ttu-id="6cf51-120">Ugorjon a Készletkezelés > Beállítás > Köteg > Kötegattribútum-csoportok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6cf51-120">Go to Inventory management > Setup > Batch > Batch attribute groups.</span></span>
13. <span data-ttu-id="6cf51-121">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6cf51-121">Click New.</span></span>
14. <span data-ttu-id="6cf51-122">Írjon be egy értéket az Attribútum mezőbe.</span><span class="sxs-lookup"><span data-stu-id="6cf51-122">In the Attribute group field, type a value.</span></span>
15. <span data-ttu-id="6cf51-123">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6cf51-123">In the Description field, type a value.</span></span>
16. <span data-ttu-id="6cf51-124">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="6cf51-124">Click Save.</span></span>
17. <span data-ttu-id="6cf51-125">Csoportattribútumok</span><span class="sxs-lookup"><span data-stu-id="6cf51-125">Click Group attributes.</span></span>
18. <span data-ttu-id="6cf51-126">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6cf51-126">Click New.</span></span>
19. <span data-ttu-id="6cf51-127">Az Attribútum mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="6cf51-127">In the Attribute field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="6cf51-128">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="6cf51-128">In the list, find and select the desired record.</span></span>
21. <span data-ttu-id="6cf51-129">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="6cf51-129">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="6cf51-130">Attribútum szerepelhet a csoportok bármelyikében.</span><span class="sxs-lookup"><span data-stu-id="6cf51-130">An attribute can be included in any of the groups.</span></span>  
22. <span data-ttu-id="6cf51-131">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="6cf51-131">Click Save.</span></span>
23. <span data-ttu-id="6cf51-132">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="6cf51-132">Close the page.</span></span>


