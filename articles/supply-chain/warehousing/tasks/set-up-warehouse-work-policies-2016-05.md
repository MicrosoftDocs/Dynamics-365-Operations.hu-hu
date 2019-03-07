---
title: A raktári munka irányelveinek beállítása (Alkalmazás, 2016. május)
description: A raktárkezelési folyamatok nem mindig tartalmazzák a raktári munkát.
author: johanhoffmann
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkPolicy, WMSLocationIdLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 34b4255c85bb53f7e238b60559890571070953a6
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "335324"
---
# <a name="set-up-warehouse-work-policies-application-may-2016"></a><span data-ttu-id="99403-103">A raktári munka irányelveinek beállítása (Alkalmazás, 2016. május)</span><span class="sxs-lookup"><span data-stu-id="99403-103">Set up warehouse work policies (Application, May 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="99403-104">A raktárkezelési folyamatok nem mindig tartalmazzák a raktári munkát.</span><span class="sxs-lookup"><span data-stu-id="99403-104">Warehouse processes don’t always include warehouse work.</span></span> <span data-ttu-id="99403-105">A munka irányelveinek használatával megakadályozhatja a nyersanyag kitárolására és a befejezett termékek betárolására vonatkozó munka létrehozását egy termékkészletre vonatkozóan az adott helyeken.</span><span class="sxs-lookup"><span data-stu-id="99403-105">By defining a work policy, you can prevent the creation of work for raw material picking and put-away of finished goods for a set of products at specific locations.</span></span> <span data-ttu-id="99403-106">A rendszer az USMF bemutatócéget használta a rögzítés létrehozására.</span><span class="sxs-lookup"><span data-stu-id="99403-106">The USMF demo data company was used to create this recording.</span></span> <span data-ttu-id="99403-107">Ez a feladat-útmutató 7.0.1-es vagy újabb verziós Dynamics AX alkalmazást igényel.</span><span class="sxs-lookup"><span data-stu-id="99403-107">This task guide requires Dynamics AX application 7.0.1 or later.</span></span>

1. <span data-ttu-id="99403-108">Ugorjon a Raktárkezelés > Beállítás > Munka > Munkairányelvek pontra.</span><span class="sxs-lookup"><span data-stu-id="99403-108">Go to Warehouse management > Setup > Work > Work policies.</span></span>
2. <span data-ttu-id="99403-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="99403-109">Click New.</span></span>
3. <span data-ttu-id="99403-110">A Munkairányelv neve mezőbe írja be a „Nincs betárolási munka” szöveget.</span><span class="sxs-lookup"><span data-stu-id="99403-110">In the Work policy name field, type 'No put-away work'.</span></span>
4. <span data-ttu-id="99403-111">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="99403-111">Click Save.</span></span>
5. <span data-ttu-id="99403-112">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="99403-112">Click Add.</span></span>
6. <span data-ttu-id="99403-113">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="99403-113">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="99403-114">A Munka rendelési típusa mezőben válassza ki a „Késztermékek betárolása” szöveget.</span><span class="sxs-lookup"><span data-stu-id="99403-114">In the Work order type field, select 'Finished goods put away'.</span></span>
8. <span data-ttu-id="99403-115">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="99403-115">Click Add.</span></span>
9. <span data-ttu-id="99403-116">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="99403-116">In the list, mark the selected row.</span></span>
10. <span data-ttu-id="99403-117">A Munka rendelés típusa mezőben válassza ki a „Társtermék és melléktermék betárolása” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="99403-117">In the Work order type field, select 'Co-product and by-product put away'.</span></span>
11. <span data-ttu-id="99403-118">Bontsa ki a Készlethelyek szakaszt.</span><span class="sxs-lookup"><span data-stu-id="99403-118">Expand the Inventory locations section.</span></span>
12. <span data-ttu-id="99403-119">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="99403-119">Click Add.</span></span>
13. <span data-ttu-id="99403-120">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="99403-120">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="99403-121">Írja be az „51” értéket a Raktár listájában.</span><span class="sxs-lookup"><span data-stu-id="99403-121">In the Warehouse list, enter '51'.</span></span>
15. <span data-ttu-id="99403-122">A Hely mezőben adjon meg vagy válasszon ki a „001” értéket.</span><span class="sxs-lookup"><span data-stu-id="99403-122">In the Location field, enter or select '001'.</span></span>
16. <span data-ttu-id="99403-123">Bontsa ki a Termékek szakaszt.</span><span class="sxs-lookup"><span data-stu-id="99403-123">Expand the Products section.</span></span>
17. <span data-ttu-id="99403-124">A Termékkiválasztás mezőben válassza ki a „Termékaltípus” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="99403-124">In the Product selection field, select 'Selected'.</span></span>
18. <span data-ttu-id="99403-125">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="99403-125">Click Add.</span></span>
19. <span data-ttu-id="99403-126">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="99403-126">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="99403-127">Az Elemszám mezőben adjon meg, vagy válasszon ki „L0101” értéket.</span><span class="sxs-lookup"><span data-stu-id="99403-127">In the Item number field, enter or select 'L0101'.</span></span>
21. <span data-ttu-id="99403-128">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="99403-128">Click Save.</span></span>

