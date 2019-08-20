---
title: Áfatranzakciók létrehozása dokumentumokra
description: A dokumentumok áfájának számítása az Áfacsoport és Cikkáfacsoport megadásával történik a bizonylatsorokra.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, TaxTmpWorkTrans
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 653b93744f5b891655cade0cb669d34179fca9cd
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1846535"
---
# <a name="create-sales-tax-transactions-on-documents"></a><span data-ttu-id="f716b-103">Áfatranzakciók létrehozása dokumentumokra</span><span class="sxs-lookup"><span data-stu-id="f716b-103">Create sales tax transactions on documents</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f716b-104">A dokumentumok áfájának számítása az Áfacsoport és Cikkáfacsoport megadásával történik a bizonylatsorokra.</span><span class="sxs-lookup"><span data-stu-id="f716b-104">Sales tax on documents is calculated by providing a Sales tax group and an Item sales tax group on document lines.</span></span> <span data-ttu-id="f716b-105">Ezek alapértelmezés szerint eltérnek az alapadatoktól, de manuálisan módosíthatók szükség esetén.</span><span class="sxs-lookup"><span data-stu-id="f716b-105">These default from master data but can be changed manually if necessary.</span></span> <span data-ttu-id="f716b-106">A számított áfa a sor- és dokumentumszinten is ellenőrizhető.</span><span class="sxs-lookup"><span data-stu-id="f716b-106">The calculated sales tax can be checked on a line and document level.</span></span> <span data-ttu-id="f716b-107">Ez a feladat az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="f716b-107">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="f716b-108">Ugorjon a Kinnlevőségek > Rendelések > Minden értékesítési rendelés elemre.</span><span class="sxs-lookup"><span data-stu-id="f716b-108">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="f716b-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f716b-109">Click New.</span></span>
3. <span data-ttu-id="f716b-110">A Vevői számla mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="f716b-110">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="f716b-111">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="f716b-111">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="f716b-112">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="f716b-112">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="f716b-113">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="f716b-113">Click OK.</span></span>
7. <span data-ttu-id="f716b-114">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="f716b-114">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="f716b-115">A Cikkszám mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="f716b-115">In the Item number field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="f716b-116">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="f716b-116">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="f716b-117">Adjon meg egy számot az Egységár mezőben.</span><span class="sxs-lookup"><span data-stu-id="f716b-117">In the Unit price field, enter a number.</span></span>
11. <span data-ttu-id="f716b-118">Bontsa ki vagy csukja össze a Soradatok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="f716b-118">Expand or collapse the Line details section.</span></span>
12. <span data-ttu-id="f716b-119">Kattintson a Beállítások fülre.</span><span class="sxs-lookup"><span data-stu-id="f716b-119">Click the Setup tab.</span></span>
13. <span data-ttu-id="f716b-120">A Cikkáfacsoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="f716b-120">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="f716b-121">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="f716b-121">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="f716b-122">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="f716b-122">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="f716b-123">Kattintson a Pénzügyre.</span><span class="sxs-lookup"><span data-stu-id="f716b-123">Click Financials.</span></span>
17. <span data-ttu-id="f716b-124">Kattintson az Áfa elemre.</span><span class="sxs-lookup"><span data-stu-id="f716b-124">Click Sales tax.</span></span>
18. <span data-ttu-id="f716b-125">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="f716b-125">Click OK.</span></span>
19. <span data-ttu-id="f716b-126">Kattintson az Új sor hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f716b-126">Click Add line.</span></span>
20. <span data-ttu-id="f716b-127">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="f716b-127">In the list, mark the selected row.</span></span>
21. <span data-ttu-id="f716b-128">A Cikkszám mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="f716b-128">In the Item number field, click the drop-down button to open the lookup.</span></span>
22. <span data-ttu-id="f716b-129">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="f716b-129">In the list, find and select the desired record.</span></span>
23. <span data-ttu-id="f716b-130">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="f716b-130">In the list, click the link in the selected row.</span></span>
24. <span data-ttu-id="f716b-131">Adjon meg egy számot az Egységár mezőben.</span><span class="sxs-lookup"><span data-stu-id="f716b-131">In the Unit price field, enter a number.</span></span>
25. <span data-ttu-id="f716b-132">A Cikkáfacsoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="f716b-132">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
26. <span data-ttu-id="f716b-133">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="f716b-133">In the list, find and select the desired record.</span></span>
27. <span data-ttu-id="f716b-134">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="f716b-134">In the list, click the link in the selected row.</span></span>
28. <span data-ttu-id="f716b-135">A Művelet panelen kattintson az Értékesítés elemre.</span><span class="sxs-lookup"><span data-stu-id="f716b-135">On the Action Pane, click Sell.</span></span>
29. <span data-ttu-id="f716b-136">Kattintson az Áfa elemre.</span><span class="sxs-lookup"><span data-stu-id="f716b-136">Click Sales tax.</span></span>
30. <span data-ttu-id="f716b-137">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="f716b-137">Click OK.</span></span>

