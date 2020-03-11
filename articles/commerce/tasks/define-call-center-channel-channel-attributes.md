---
title: Hívásközponti csatornák létrehozása és a csatornák attribútumainak meghatározása
description: Ez az eljárás végigvezeti egy új csatorna létrehozásának, és a csatornaattribútumok megadásának lépésein.
author: mugunthanm
manager: AnnBe
ms.date: 05/22/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.author: mumani
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 62075c01ad7e2a4c393e9658fa67f8b536654aec
ms.sourcegitcommit: 12b9d6f2dd24e52e46487748c848864909af6967
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/14/2020
ms.locfileid: "3057164"
---
# <a name="create-call-center-channels-and-define-channel-attributes"></a><span data-ttu-id="8a9a6-103">Hívásközponti csatornák létrehozása és a csatornák attribútumainak meghatározása</span><span class="sxs-lookup"><span data-stu-id="8a9a6-103">Create call center channels and define channel attributes</span></span>

[!include [task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="8a9a6-104">Ez az eljárás végigvezeti egy új kereskedelmi csatorna létrehozásának, és a csatornaattribútumok megadásának lépésein.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-104">This procedure walks through creating a new commerce channel and defining channel attributes.</span></span> <span data-ttu-id="8a9a6-105">A feladat létrehozásához az USRT bemutató vállalatot használtuk példaként.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-105">The demo data company used to create this task is USRT.</span></span> <span data-ttu-id="8a9a6-106">Ezt az eljárást a kereskedelem IT-szerepkör használja.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-106">This procedure is intended for the Commerce IT role.</span></span>


## <a name="create-new-store"></a><span data-ttu-id="8a9a6-107">Új áruház létrehozása</span><span class="sxs-lookup"><span data-stu-id="8a9a6-107">Create new store</span></span>
1. <span data-ttu-id="8a9a6-108">Menjen a Minden munkaterület > Telepítési csatorna almenübe.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-108">Go to All workspaces > Channel deployment.</span></span>
2. <span data-ttu-id="8a9a6-109">Kattintson az Új csatorna lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-109">Click New channel.</span></span>
3. <span data-ttu-id="8a9a6-110">Kattintson az Üzlet lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-110">Click Store.</span></span>
4. <span data-ttu-id="8a9a6-111">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-111">In the Name field, type a value.</span></span>
5. <span data-ttu-id="8a9a6-112">Adjon meg egy értéket az Üzlet száma mezőben.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-112">In the Store number field, type a value.</span></span>
6. <span data-ttu-id="8a9a6-113">A Raktár mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-113">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="8a9a6-114">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-114">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="8a9a6-115">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-115">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="8a9a6-116">Válasszon ki egy lehetőséget az Üzlet időzónája mezőben.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-116">In the Store time zone field, select an option.</span></span>
10. <span data-ttu-id="8a9a6-117">A Csatornaprofil mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-117">In the Channel profile field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="8a9a6-118">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-118">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="8a9a6-119">A Nyelv mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-119">In the Language field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="8a9a6-120">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-120">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="8a9a6-121">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-121">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="8a9a6-122">Az Áfacsoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-122">In the Sales tax group field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="8a9a6-123">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-123">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="8a9a6-124">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-124">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="8a9a6-125">A Vevői címjegyzék mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-125">In the Customer address book field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="8a9a6-126">Válassza ki azt a címjegyzéket, amelyet a vevők ehhez az üzlethez való kötéséhez használtak.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-126">Select the address book used to link customers to this store.</span></span>  
19. <span data-ttu-id="8a9a6-127">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-127">In the list, find and select the desired record.</span></span>
20. <span data-ttu-id="8a9a6-128">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-128">In the list, click the link in the selected row.</span></span>
21. <span data-ttu-id="8a9a6-129">Kattintson a Kiválasztás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-129">Click Select.</span></span>
22. <span data-ttu-id="8a9a6-130">Az Alkalmazotti címjegyzék mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-130">In the Employee address book field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="8a9a6-131">Válassza ki azt a címjegyzéket, amelyet a pénztárosoknak ehhez a csatornához való kötéséhez használtak.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-131">Select the address book used to link cashiers to this channel.</span></span>  
23. <span data-ttu-id="8a9a6-132">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-132">In the list, find and select the desired record.</span></span>
24. <span data-ttu-id="8a9a6-133">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-133">In the list, click the link in the selected row.</span></span>
25. <span data-ttu-id="8a9a6-134">Kattintson a Kiválasztás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-134">Click Select.</span></span>
26. <span data-ttu-id="8a9a6-135">Az Alapértelmezett vevő mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-135">In the Default customer field, click the drop-down button to open the lookup.</span></span>
27. <span data-ttu-id="8a9a6-136">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-136">In the list, click the link in the selected row.</span></span>
28. <span data-ttu-id="8a9a6-137">Bontsa ki vagy csukja össze a Képernyő-elrendezés szakaszt.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-137">Expand or collapse the Screen layout section.</span></span>
29. <span data-ttu-id="8a9a6-138">A Képernyő-elrendezés azonosítója mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-138">In the Screen layout ID field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="8a9a6-139">Válassza ki az alapértelmezett POS képernyő-elrendezést ehhez az üzlethez.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-139">Select the default POS screen layout for this store.</span></span>  
30. <span data-ttu-id="8a9a6-140">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-140">In the list, find and select the desired record.</span></span>
31. <span data-ttu-id="8a9a6-141">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-141">In the list, click the link in the selected row.</span></span>
32. <span data-ttu-id="8a9a6-142">A műveleti ablaktáblán kattintson a Beállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-142">On the Action Pane, click Set up.</span></span>
33. <span data-ttu-id="8a9a6-143">Kattintson a Csatornaattribútumok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-143">Click Channel attributes.</span></span>
34. <span data-ttu-id="8a9a6-144">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-144">Click New.</span></span>
35. <span data-ttu-id="8a9a6-145">A Név mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-145">In the Name field, click the drop-down button to open the lookup.</span></span>
36. <span data-ttu-id="8a9a6-146">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-146">In the list, find and select the desired record.</span></span>
37. <span data-ttu-id="8a9a6-147">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-147">In the list, click the link in the selected row.</span></span>
38. <span data-ttu-id="8a9a6-148">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-148">Click Save.</span></span>
39. <span data-ttu-id="8a9a6-149">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-149">Close the page.</span></span>
40. <span data-ttu-id="8a9a6-150">A műveleti ablaktáblán kattintson a Beállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-150">On the Action Pane, click Set up.</span></span>
41. <span data-ttu-id="8a9a6-151">Kattintson a Kifizetési módok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-151">Click Payment methods.</span></span>
42. <span data-ttu-id="8a9a6-152">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-152">Click New.</span></span>
43. <span data-ttu-id="8a9a6-153">A Fizetési mód mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-153">In the Payment method field, click the drop-down button to open the lookup.</span></span>
44. <span data-ttu-id="8a9a6-154">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-154">In the list, click the link in the selected row.</span></span>
45. <span data-ttu-id="8a9a6-155">Bontsa ki vagy csukja össze a Feladás szakaszt.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-155">Expand or collapse the Posting section.</span></span>
46. <span data-ttu-id="8a9a6-156">A Számlaszám mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-156">In the Account number field, specify the desired values.</span></span>
47. <span data-ttu-id="8a9a6-157">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-157">Click Save.</span></span>
48. <span data-ttu-id="8a9a6-158">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-158">Close the page.</span></span>
49. <span data-ttu-id="8a9a6-159">A műveleti ablaktáblán kattintson a Beállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-159">On the Action Pane, click Set up.</span></span>
50. <span data-ttu-id="8a9a6-160">Kattintson a Készpénzelszámolás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-160">Click Cash declaration.</span></span>
51. <span data-ttu-id="8a9a6-161">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-161">Click New.</span></span>
52. <span data-ttu-id="8a9a6-162">Az Összeg a tranzakció pénznemében mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-162">In the Amount in transaction currency field, enter a number.</span></span>
53. <span data-ttu-id="8a9a6-163">A Pénznem mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-163">In the Currency field, click the drop-down button to open the lookup.</span></span>
54. <span data-ttu-id="8a9a6-164">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-164">In the list, find and select the desired record.</span></span>
55. <span data-ttu-id="8a9a6-165">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-165">In the list, click the link in the selected row.</span></span>
56. <span data-ttu-id="8a9a6-166">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-166">Click Save.</span></span>
57. <span data-ttu-id="8a9a6-167">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-167">Close the page.</span></span>
58. <span data-ttu-id="8a9a6-168">A műveleti ablaktáblán kattintson a Beállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-168">On the Action Pane, click Set up.</span></span>
59. <span data-ttu-id="8a9a6-169">Kattintson az Áruházi lokátorcsoport hozzárendelése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-169">Click Store locator group assignment.</span></span>
60. <span data-ttu-id="8a9a6-170">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-170">Click New.</span></span>
61. <span data-ttu-id="8a9a6-171">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-171">In the list, mark the selected row.</span></span>
62. <span data-ttu-id="8a9a6-172">A Lokátorcsoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-172">In the Locator group field, click the drop-down button to open the lookup.</span></span>
63. <span data-ttu-id="8a9a6-173">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-173">In the list, find and select the desired record.</span></span>
64. <span data-ttu-id="8a9a6-174">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-174">In the list, click the link in the selected row.</span></span>
65. <span data-ttu-id="8a9a6-175">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-175">Click Save.</span></span>
66. <span data-ttu-id="8a9a6-176">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="8a9a6-176">Close the page.</span></span>

