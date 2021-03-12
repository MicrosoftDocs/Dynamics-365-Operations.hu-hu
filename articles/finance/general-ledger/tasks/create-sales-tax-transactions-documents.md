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
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1a807ee2743f051528b6b96ddf1eaada65283933
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4968654"
---
# <a name="create-sales-tax-transactions-on-documents"></a><span data-ttu-id="1896d-103">Áfatranzakciók létrehozása dokumentumokra</span><span class="sxs-lookup"><span data-stu-id="1896d-103">Create sales tax transactions on documents</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1896d-104">A dokumentumok áfájának számítása az Áfacsoport és Cikkáfacsoport megadásával történik a bizonylatsorokra.</span><span class="sxs-lookup"><span data-stu-id="1896d-104">Sales tax on documents is calculated by providing a Sales tax group and an Item sales tax group on document lines.</span></span> <span data-ttu-id="1896d-105">Ezek alapértelmezés szerint eltérnek az alapadatoktól, de manuálisan módosíthatók szükség esetén.</span><span class="sxs-lookup"><span data-stu-id="1896d-105">These default from master data but can be changed manually if necessary.</span></span> <span data-ttu-id="1896d-106">A számított áfa a sor- és dokumentumszinten is ellenőrizhető.</span><span class="sxs-lookup"><span data-stu-id="1896d-106">The calculated sales tax can be checked on a line and document level.</span></span> <span data-ttu-id="1896d-107">Ez a feladat az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="1896d-107">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="1896d-108">Ugorjon a Kinnlevőségek > Rendelések > Minden értékesítési rendelés elemre.</span><span class="sxs-lookup"><span data-stu-id="1896d-108">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="1896d-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1896d-109">Click New.</span></span>
3. <span data-ttu-id="1896d-110">A Vevői számla mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="1896d-110">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="1896d-111">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="1896d-111">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="1896d-112">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="1896d-112">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="1896d-113">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="1896d-113">Click OK.</span></span>
7. <span data-ttu-id="1896d-114">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="1896d-114">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="1896d-115">A Cikkszám mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="1896d-115">In the Item number field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="1896d-116">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="1896d-116">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="1896d-117">Adjon meg egy számot az Egységár mezőben.</span><span class="sxs-lookup"><span data-stu-id="1896d-117">In the Unit price field, enter a number.</span></span>
11. <span data-ttu-id="1896d-118">Bontsa ki vagy csukja össze a Soradatok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="1896d-118">Expand or collapse the Line details section.</span></span>
12. <span data-ttu-id="1896d-119">Kattintson a Beállítások fülre.</span><span class="sxs-lookup"><span data-stu-id="1896d-119">Click the Setup tab.</span></span>
13. <span data-ttu-id="1896d-120">A Cikkáfacsoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="1896d-120">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="1896d-121">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="1896d-121">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="1896d-122">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="1896d-122">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="1896d-123">Kattintson a Pénzügyre.</span><span class="sxs-lookup"><span data-stu-id="1896d-123">Click Financials.</span></span>
17. <span data-ttu-id="1896d-124">Kattintson az Áfa elemre.</span><span class="sxs-lookup"><span data-stu-id="1896d-124">Click Sales tax.</span></span>
18. <span data-ttu-id="1896d-125">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="1896d-125">Click OK.</span></span>
19. <span data-ttu-id="1896d-126">Kattintson az Új sor hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1896d-126">Click Add line.</span></span>
20. <span data-ttu-id="1896d-127">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="1896d-127">In the list, mark the selected row.</span></span>
21. <span data-ttu-id="1896d-128">A Cikkszám mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="1896d-128">In the Item number field, click the drop-down button to open the lookup.</span></span>
22. <span data-ttu-id="1896d-129">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="1896d-129">In the list, find and select the desired record.</span></span>
23. <span data-ttu-id="1896d-130">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="1896d-130">In the list, click the link in the selected row.</span></span>
24. <span data-ttu-id="1896d-131">Adjon meg egy számot az Egységár mezőben.</span><span class="sxs-lookup"><span data-stu-id="1896d-131">In the Unit price field, enter a number.</span></span>
25. <span data-ttu-id="1896d-132">A Cikkáfacsoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="1896d-132">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
26. <span data-ttu-id="1896d-133">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="1896d-133">In the list, find and select the desired record.</span></span>
27. <span data-ttu-id="1896d-134">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="1896d-134">In the list, click the link in the selected row.</span></span>
28. <span data-ttu-id="1896d-135">A Művelet panelen kattintson az Értékesítés elemre.</span><span class="sxs-lookup"><span data-stu-id="1896d-135">On the Action Pane, click Sell.</span></span>
29. <span data-ttu-id="1896d-136">Kattintson az Áfa elemre.</span><span class="sxs-lookup"><span data-stu-id="1896d-136">Click Sales tax.</span></span>
30. <span data-ttu-id="1896d-137">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="1896d-137">Click OK.</span></span>

