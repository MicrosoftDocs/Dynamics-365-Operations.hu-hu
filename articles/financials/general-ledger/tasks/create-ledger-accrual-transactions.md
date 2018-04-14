--- 
title: "Főkönyvi könyvelés tranzakcióinak létrehozása"
description: "Ez a feladat-útmutató bemutatja a könyvelési sémákon alapuló főkönyvi könyvelési tranzakciók létrehozását."
author: aprilolson
manager: AnnBe
ms.date: 10/26/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: bfc514530149f25e6355992984b9e33f80194b2c
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---
# <a name="create-ledger-accrual-transactions"></a><span data-ttu-id="3f53b-103">Főkönyvi könyvelés tranzakcióinak létrehozása</span><span class="sxs-lookup"><span data-stu-id="3f53b-103">Create ledger accrual transactions</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3f53b-104">A feladat-útmutató bemutatja az olyan főkönyvi könyvelési tranzakciók létrehozását, amelyek alapját a könyvelési sémák adják</span><span class="sxs-lookup"><span data-stu-id="3f53b-104">This task guide steps through generating ledger accrual transactions that are based on accrual schemes</span></span>

1. <span data-ttu-id="3f53b-105">Ugorjon a Főkönyv > Naplóbejegyzések > Általános naplók pontra.</span><span class="sxs-lookup"><span data-stu-id="3f53b-105">Go to General ledger > Journal entries > General journals.</span></span>
2. <span data-ttu-id="3f53b-106">Keresse meg majd válassza ki a listából a kívánt naplót, vagy hozzon létre egyet.</span><span class="sxs-lookup"><span data-stu-id="3f53b-106">In the list, find and select the desired journal or create a new one.</span></span>
3. <span data-ttu-id="3f53b-107">Kattintson a Naplóköteg száma mezőben található hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="3f53b-107">Click to follow the link in the Journal batch number field.</span></span>
4. <span data-ttu-id="3f53b-108">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="3f53b-108">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="3f53b-109">A Számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="3f53b-109">In the Account field, specify the desired values.</span></span>
    * <span data-ttu-id="3f53b-110">Ebben a példában a biztosításhoz a költséget határozzuk meg.</span><span class="sxs-lookup"><span data-stu-id="3f53b-110">In this example, we are defining the expense for the insurance.</span></span> <span data-ttu-id="3f53b-111">Időszakos kiadási összeg lesz.</span><span class="sxs-lookup"><span data-stu-id="3f53b-111">It will become a periodic expense amount.</span></span>  
6. <span data-ttu-id="3f53b-112">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="3f53b-112">In the Description field, type a value.</span></span>
7. <span data-ttu-id="3f53b-113">Adjon meg egy számot a Tartozik mezőben.</span><span class="sxs-lookup"><span data-stu-id="3f53b-113">In the Debit field, enter a number.</span></span>
8. <span data-ttu-id="3f53b-114">Az Ellenszámla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="3f53b-114">In the Offset account field, specify the desired values.</span></span>
9. <span data-ttu-id="3f53b-115">Kattintson a Funkciók elemre.</span><span class="sxs-lookup"><span data-stu-id="3f53b-115">Click Functions.</span></span>
10. <span data-ttu-id="3f53b-116">Kattintson a Főkönyvi könyvelések elemre.</span><span class="sxs-lookup"><span data-stu-id="3f53b-116">Click Ledger accruals.</span></span>
11. <span data-ttu-id="3f53b-117">A Könyvelés azonosítója mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="3f53b-117">In the Accrual identification field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="3f53b-118">A listában keresse meg és válassza ki az alkalmazni kívánt könyvelési sémát.</span><span class="sxs-lookup"><span data-stu-id="3f53b-118">In the list, find and select the accrual scheme you want to apply.</span></span>
13. <span data-ttu-id="3f53b-119">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="3f53b-119">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="3f53b-120">Adja meg a dátumot a Kezdő dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="3f53b-120">In the Start date field, enter a date.</span></span>
15. <span data-ttu-id="3f53b-121">Kattintson a Tranzakciók elemre.</span><span class="sxs-lookup"><span data-stu-id="3f53b-121">Click Transactions.</span></span>
16. <span data-ttu-id="3f53b-122">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="3f53b-122">Close the page.</span></span>
17. <span data-ttu-id="3f53b-123">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="3f53b-123">Click OK.</span></span>
18. <span data-ttu-id="3f53b-124">Kattintson a Feladás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3f53b-124">Click Post.</span></span>


