---
title: Pénzügyi dimenziók létrehozása Retail csatornákhoz és a dimenzióértékek konfigurálása az üzletekben
description: Ez az eljárás egy kereskedelmi csatorna pénzügyi dimenzió, az üzletekkel kapcsolatos pénzügyi dimenzióértékek konfigurálásában szerepet játszó dimenzióértékekkel és lépésekkel együtt történő létrehozását mutatja be.
author: jashanno
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 86fc9c9a400bee1280b32f10b1e8f55e581e1984
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4964745"
---
# <a name="create-financial-dimensions-for-retail-channels-and-configure-dimension-values-on-stores"></a><span data-ttu-id="95483-103">Pénzügyi dimenziók létrehozása Retail csatornákhoz és a dimenzióértékek konfigurálása az üzletekben</span><span class="sxs-lookup"><span data-stu-id="95483-103">Create financial dimensions for retail channels and configure dimension values on stores</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="95483-104">Ez az eljárás egy kereskedelmi csatorna pénzügyi dimenzió, az üzletekkel kapcsolatos pénzügyi dimenzióértékek konfigurálásában szerepet játszó dimenzióértékekkel és lépésekkel együtt történő létrehozását mutatja be.</span><span class="sxs-lookup"><span data-stu-id="95483-104">This procedure walks through creating a commerce channel financial dimension with dimension values and steps to configure financial dimension values on stores.</span></span> <span data-ttu-id="95483-105">A témakör nem tér ki olyan kapcsolódó lépésekre, mint a dimenziókészletek és számlastruktúrák létrehozása.</span><span class="sxs-lookup"><span data-stu-id="95483-105">The topic does not include other related steps, such as creating dimension sets and account structures.</span></span> <span data-ttu-id="95483-106">Ez az eljárás az USRT cég adatait használja, mint bemutatóadatokat.</span><span class="sxs-lookup"><span data-stu-id="95483-106">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="95483-107">Ugrás a következő útvonalra: Főkönyv > Számlatükör > Dimenziók > Pénzügyi dimenziók.</span><span class="sxs-lookup"><span data-stu-id="95483-107">Go to General ledger > Chart of accounts > Dimensions > Financial dimensions.</span></span>
2. <span data-ttu-id="95483-108">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="95483-108">Click New.</span></span>
3. <span data-ttu-id="95483-109">Az Értékek forrása mezőben válassza a „Kereskedelmi csatornák” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="95483-109">In the Use values from field, select 'Commerce channels'.</span></span>
4. <span data-ttu-id="95483-110">Írjon be egy értéket a Dimenziónév mezőbe.</span><span class="sxs-lookup"><span data-stu-id="95483-110">In the Dimension name field, type a value.</span></span>
5. <span data-ttu-id="95483-111">Kattintson az Aktiválás gombra.</span><span class="sxs-lookup"><span data-stu-id="95483-111">Click Activate.</span></span>
6. <span data-ttu-id="95483-112">Kattintson a Bezárás gombra.</span><span class="sxs-lookup"><span data-stu-id="95483-112">Click Close.</span></span>
7. <span data-ttu-id="95483-113">Kattintson az Aktiválás gombra.</span><span class="sxs-lookup"><span data-stu-id="95483-113">Click Activate.</span></span>
8. <span data-ttu-id="95483-114">Kattintson a Dimenzióértékek elemre.</span><span class="sxs-lookup"><span data-stu-id="95483-114">Click Dimension values.</span></span>
9. <span data-ttu-id="95483-115">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="95483-115">Close the page.</span></span>
10. <span data-ttu-id="95483-116">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="95483-116">Click Save.</span></span>
11. <span data-ttu-id="95483-117">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="95483-117">Close the page.</span></span>
12. <span data-ttu-id="95483-118">Ugorjon a következő oldalra: Retail és Commerce > Csatornák > Üzletek > Minden kiskereskedelmi üzlet.</span><span class="sxs-lookup"><span data-stu-id="95483-118">Go to Retail and Commerce > Channels > Stores > All stores.</span></span>
13. <span data-ttu-id="95483-119">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="95483-119">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="95483-120">Váltson a Pénzügyi dimenziók szakasz kibontására.</span><span class="sxs-lookup"><span data-stu-id="95483-120">Toggle the expansion of the Financial dimensions section.</span></span>
15. <span data-ttu-id="95483-121">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="95483-121">Click Edit.</span></span>
16. <span data-ttu-id="95483-122">A Kereskedelmi csatorna mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="95483-122">In the Commerce channel field, click the drop-down button to open the lookup.</span></span>
17. <span data-ttu-id="95483-123">A listában keresse meg és válassza ki az éppen frissített üzlet dimenzióértékét.</span><span class="sxs-lookup"><span data-stu-id="95483-123">In the list, find and select the dimension value for the store being updated.</span></span>
18. <span data-ttu-id="95483-124">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="95483-124">In the list, click the link in the selected row.</span></span>
19. <span data-ttu-id="95483-125">A CostCenter mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="95483-125">In the CostCenter field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="95483-126">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="95483-126">In the list, find and select the desired record.</span></span>
21. <span data-ttu-id="95483-127">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="95483-127">In the list, click the link in the selected row.</span></span>
22. <span data-ttu-id="95483-128">A Részleg mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="95483-128">In the Department field, click the drop-down button to open the lookup.</span></span>
23. <span data-ttu-id="95483-129">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="95483-129">In the list, find and select the desired record.</span></span>
24. <span data-ttu-id="95483-130">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="95483-130">In the list, click the link in the selected row.</span></span>
25. <span data-ttu-id="95483-131">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="95483-131">Click Save.</span></span>

