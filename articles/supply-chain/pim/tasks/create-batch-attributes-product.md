---
title: Termék kötegattribútumainak létrehozása
description: Ez az eljárás bemutatja, hogyan hozható létre kötegattribútum, hogyan rendelhető hozzá alapértelmezett értéktartomány, hogyan szerepeltethető az attribútum egy csoportban.
author: ShylaThompson
manager: tfehr
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PdsBatchAttrib
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6d51cecc800a827fe91583b6086fd88b10aedc41
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4986929"
---
# <a name="create-batch-attributes-for-a-product"></a><span data-ttu-id="41355-103">Termék kötegattribútumainak létrehozása</span><span class="sxs-lookup"><span data-stu-id="41355-103">Create batch attributes for a product</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="41355-104">Ez az eljárás bemutatja, hogyan hozható létre kötegattribútum, hogyan rendelhető hozzá alapértelmezett értéktartomány, hogyan szerepeltethető az attribútum egy csoportban.</span><span class="sxs-lookup"><span data-stu-id="41355-104">This procedure shows how to create a batch attribute, assign default value ranges, and include the attribute in a group.</span></span> <span data-ttu-id="41355-105">Az eljárás létrehozásához az USP2 bemutatócéget használtuk.</span><span class="sxs-lookup"><span data-stu-id="41355-105">The demo data company used to create this procedure is the USP2 Company.</span></span>

1. <span data-ttu-id="41355-106">Ugorjon a Készletkezelés > Beállítás > Köteg > Kötegattribútumok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="41355-106">Go to Inventory management > Setup > Batch > Batch attributes.</span></span>
2. <span data-ttu-id="41355-107">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="41355-107">Click New.</span></span>
3. <span data-ttu-id="41355-108">Írjon be egy értéket az Attribútum mezőbe.</span><span class="sxs-lookup"><span data-stu-id="41355-108">In the Attribute field, type a value.</span></span>
4. <span data-ttu-id="41355-109">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="41355-109">In the Description field, type a value.</span></span>
5. <span data-ttu-id="41355-110">Válassza ki a Tört lehetőséget az Attribútum mezőben.</span><span class="sxs-lookup"><span data-stu-id="41355-110">In the Attribute type field, select 'Fraction'.</span></span>
    * <span data-ttu-id="41355-111">Ezzel az eljárással engedélyezheti a tizedes értékeket a Tört típussal.</span><span class="sxs-lookup"><span data-stu-id="41355-111">This procedure uses the Fraction type to enable decimal values.</span></span> <span data-ttu-id="41355-112">Egyéb attribútumtípusokat is választhat.</span><span class="sxs-lookup"><span data-stu-id="41355-112">You can select other attribute types.</span></span> <span data-ttu-id="41355-113">A Felsorolási típus választásakor meg kell adni értékeket a felsorolási listában, mielőtt megadhat egy értéket a Cél mezőben.</span><span class="sxs-lookup"><span data-stu-id="41355-113">If you select the Enumeration type, you must enter values in the enumeration list before you can enter a value in the Target field.</span></span>  
6. <span data-ttu-id="41355-114">Adjon meg egy számot a Minimum mezőben.</span><span class="sxs-lookup"><span data-stu-id="41355-114">In the Minimum field, enter a number.</span></span>
7. <span data-ttu-id="41355-115">Adjon meg egy számot a Maximum mezőben.</span><span class="sxs-lookup"><span data-stu-id="41355-115">In the Maximum field, enter a number.</span></span>
8. <span data-ttu-id="41355-116">Adjon meg egy számot a Növekmény mezőben.</span><span class="sxs-lookup"><span data-stu-id="41355-116">In the Increment field, enter a number.</span></span>
9. <span data-ttu-id="41355-117">Írjon be egy értéket a Cél mezőbe.</span><span class="sxs-lookup"><span data-stu-id="41355-117">In the Target field, type a value.</span></span>
10. <span data-ttu-id="41355-118">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="41355-118">Click Save.</span></span>
11. <span data-ttu-id="41355-119">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="41355-119">Close the page.</span></span>
12. <span data-ttu-id="41355-120">Ugorjon a Készletkezelés > Beállítás > Köteg > Kötegattribútum-csoportok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="41355-120">Go to Inventory management > Setup > Batch > Batch attribute groups.</span></span>
13. <span data-ttu-id="41355-121">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="41355-121">Click New.</span></span>
14. <span data-ttu-id="41355-122">Írjon be egy értéket az Attribútum mezőbe.</span><span class="sxs-lookup"><span data-stu-id="41355-122">In the Attribute group field, type a value.</span></span>
15. <span data-ttu-id="41355-123">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="41355-123">In the Description field, type a value.</span></span>
16. <span data-ttu-id="41355-124">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="41355-124">Click Save.</span></span>
17. <span data-ttu-id="41355-125">Csoportattribútumok</span><span class="sxs-lookup"><span data-stu-id="41355-125">Click Group attributes.</span></span>
18. <span data-ttu-id="41355-126">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="41355-126">Click New.</span></span>
19. <span data-ttu-id="41355-127">Az Attribútum mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="41355-127">In the Attribute field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="41355-128">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="41355-128">In the list, find and select the desired record.</span></span>
21. <span data-ttu-id="41355-129">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="41355-129">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="41355-130">Attribútum szerepelhet a csoportok bármelyikében.</span><span class="sxs-lookup"><span data-stu-id="41355-130">An attribute can be included in any of the groups.</span></span>  
22. <span data-ttu-id="41355-131">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="41355-131">Click Save.</span></span>
23. <span data-ttu-id="41355-132">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="41355-132">Close the page.</span></span>

