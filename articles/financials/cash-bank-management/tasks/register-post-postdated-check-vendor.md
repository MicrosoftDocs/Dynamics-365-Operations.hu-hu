--- 
title: "Szállító részére kiállított, jövőben esedékes csekk regisztrálása és feladása"
description: "A naplóbizonylat használatával a jövőben esedékes csekk adatainak nyilvántartásba vételét a csekk szállítónak történő kiállítását megelőzően is elvégezheti."
author: kweekley
manager: AnnBe
ms.date: 10/31/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: cd00227ed6d288a4b2041630bc7a604ac94d3c70
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---
# <a name="register-and-post-a-postdated-check-for-a-vendor"></a><span data-ttu-id="fc586-103">Szállító részére kiállított, jövőben esedékes csekk regisztrálása és feladása</span><span class="sxs-lookup"><span data-stu-id="fc586-103">Register and post a postdated check for a vendor</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fc586-104">A naplóbizonylat használatával a jövőben esedékes csekk adatainak nyilvántartásba vételét a csekk szállítónak történő kiállítását megelőzően is elvégezheti.</span><span class="sxs-lookup"><span data-stu-id="fc586-104">You can register the details of a postdated check before you issue the check to a vendor by using the journal voucher.</span></span> <span data-ttu-id="fc586-105">A jövőben esedékes csekket feladhatja és pénzügyi tranzakciókat hozhat létre.</span><span class="sxs-lookup"><span data-stu-id="fc586-105">You can also post the postdated check and generate financial transactions.</span></span> <span data-ttu-id="fc586-106">Mielőtt regisztrálna és feladna egy szállítóhoz tartozó, a jövőben esedékes csekket, hajtsa végre a következő feladatot:</span><span class="sxs-lookup"><span data-stu-id="fc586-106">Before you register and post a postdated check from a vendor, complete the following task:</span></span> 

<span data-ttu-id="fc586-107">Állítsa be a Készpénz- és bankkezelés lapon a jövőben esedékes csekkeket.</span><span class="sxs-lookup"><span data-stu-id="fc586-107">Set up postdated checks in the Cash and bank management page.</span></span> 



<span data-ttu-id="fc586-108">Ezen feladati útmutatóhoz szükséges szerepkör: Pénztáros.</span><span class="sxs-lookup"><span data-stu-id="fc586-108">The role of this task guides is Treasurer.</span></span> <span data-ttu-id="fc586-109">Ez a feladat az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="fc586-109">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="fc586-110">Ugorjon a Kötelezettségek > Fizetési beállítás > Fizetési napló pontra.</span><span class="sxs-lookup"><span data-stu-id="fc586-110">Go to Accounts payable > Payments > Payment journal</span></span>
2. <span data-ttu-id="fc586-111">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="fc586-111">Click New.</span></span>
3. <span data-ttu-id="fc586-112">A Név mezőbe írja be: „VendPay”.</span><span class="sxs-lookup"><span data-stu-id="fc586-112">In the Name field, type 'VendPay'.</span></span>
4. <span data-ttu-id="fc586-113">Kattintson a Sorok pontra.</span><span class="sxs-lookup"><span data-stu-id="fc586-113">Click Lines.</span></span>
5. <span data-ttu-id="fc586-114">A Számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="fc586-114">In the Account field, specify the desired values.</span></span>
6. <span data-ttu-id="fc586-115">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="fc586-115">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="fc586-116">Adjon meg egy számot a Tartozik mezőben.</span><span class="sxs-lookup"><span data-stu-id="fc586-116">In the Debit field, enter a number.</span></span>
8. <span data-ttu-id="fc586-117">A Fizetési mód mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="fc586-117">In the Method of payment field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="fc586-118">Válassza ki a jövőben esedékes csekk fizetési módját.</span><span class="sxs-lookup"><span data-stu-id="fc586-118">Select the method of payment for the postdated check</span></span>  
9. <span data-ttu-id="fc586-119">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="fc586-119">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="fc586-120">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="fc586-120">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="fc586-121">Kattintson a Jövőben esedékes csekkek fülre.</span><span class="sxs-lookup"><span data-stu-id="fc586-121">Click the Postdated checks tab.</span></span>
12. <span data-ttu-id="fc586-122">A Csekk száma mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="fc586-122">In the Check number field, type a value.</span></span>
    * <span data-ttu-id="fc586-123">Adja meg vagy módosítsa a jövőben esedékes csekk számát.</span><span class="sxs-lookup"><span data-stu-id="fc586-123">Enter or modify the number of the postdated check.</span></span>  
13. <span data-ttu-id="fc586-124">A Kiadási bank neve mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="fc586-124">In the Issuing bank name field, type a value.</span></span>
    * <span data-ttu-id="fc586-125">adjon meg további banki információkat a kibocsátó bankkal kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="fc586-125">enter the bank details for the issuing bank.</span></span>  
14. <span data-ttu-id="fc586-126">Kattintson a Lista fülre.</span><span class="sxs-lookup"><span data-stu-id="fc586-126">Click the List tab.</span></span>
15. <span data-ttu-id="fc586-127">Kattintson a Feladás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="fc586-127">Click Post.</span></span>
16. <span data-ttu-id="fc586-128">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="fc586-128">Close the page.</span></span>
17. <span data-ttu-id="fc586-129">Kattintson a Jövőben esedékes csekkek fülre.</span><span class="sxs-lookup"><span data-stu-id="fc586-129">Click the Postdated checks tab.</span></span>


