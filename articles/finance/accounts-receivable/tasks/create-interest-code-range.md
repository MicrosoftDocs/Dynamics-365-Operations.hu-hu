---
title: Kamatkód létrehozása tartománnyal
description: A kamatkódokat be lehet úgy állítani, hogy különböző kamatösszegeket számoljon egy értéktartomány alapján.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Interest, CustInterestRange
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d684eedd5b40ee9775ab779c243d05cdc6e01f58
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2188855"
---
# <a name="create-an-interest-code-with-a-range"></a><span data-ttu-id="ece31-103">Kamatkód létrehozása tartománnyal</span><span class="sxs-lookup"><span data-stu-id="ece31-103">Create an interest code with a range</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ece31-104">A kamatkódokat be lehet úgy állítani, hogy különböző kamatösszegeket számoljon egy értéktartomány alapján.</span><span class="sxs-lookup"><span data-stu-id="ece31-104">Interest codes can be set up to calculate different interest amounts based on a range of values.</span></span> <span data-ttu-id="ece31-105">Ez az eljárás bemutatja, hogyan adhat hozzá egy kamatkódot, illetve ahhoz egy tartományt.</span><span class="sxs-lookup"><span data-stu-id="ece31-105">This procedure will show you how to add an interest code and add a range to it.</span></span>

1. <span data-ttu-id="ece31-106">Ugorjon a Követel és beszedések > Kamat > Kamatkódok beállítása pontra.</span><span class="sxs-lookup"><span data-stu-id="ece31-106">Go to Credit and collections > Interest > Set up interest codes.</span></span>
2. <span data-ttu-id="ece31-107">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ece31-107">Click New.</span></span>
3. <span data-ttu-id="ece31-108">A Kamtkód mezőbe írja be a kamatkód nevét.</span><span class="sxs-lookup"><span data-stu-id="ece31-108">In the Interest code field, enter the name of the interest code.</span></span>
4. <span data-ttu-id="ece31-109">A Leírás mezőben adja meg a kamatkód leírását.</span><span class="sxs-lookup"><span data-stu-id="ece31-109">In the Description field, enter a description for the interest code.</span></span>
5. <span data-ttu-id="ece31-110">Hónap kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="ece31-110">Select Month.</span></span>
6. <span data-ttu-id="ece31-111">Bontsa ki a Bevételek szakaszt.</span><span class="sxs-lookup"><span data-stu-id="ece31-111">Expand the Earnings section.</span></span>
7. <span data-ttu-id="ece31-112">Bontsa ki a Bevételek pénznemenként szakaszt.</span><span class="sxs-lookup"><span data-stu-id="ece31-112">Expand the Earnings by currency section.</span></span>
8. <span data-ttu-id="ece31-113">A Főkönyvi feladószámla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="ece31-113">In the Ledger posting account field, specify the desired values.</span></span>
9. <span data-ttu-id="ece31-114">Válassza ki a „Hónapok” lehetőséget a Kamat tartomány alapján mezőben.</span><span class="sxs-lookup"><span data-stu-id="ece31-114">In the Interest by range field, select 'Months'.</span></span>
10. <span data-ttu-id="ece31-115">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="ece31-115">Click Add.</span></span>
11. <span data-ttu-id="ece31-116">A Leírás mezőben adja meg a pénznem és a tartomány leírását.</span><span class="sxs-lookup"><span data-stu-id="ece31-116">In the Description field, enter a description for this currency and range.</span></span>
12. <span data-ttu-id="ece31-117">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="ece31-117">Click Save.</span></span>
13. <span data-ttu-id="ece31-118">Kattintson az Tartományok elemre.</span><span class="sxs-lookup"><span data-stu-id="ece31-118">Click Ranges.</span></span>
14. <span data-ttu-id="ece31-119">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ece31-119">Click New.</span></span>
15. <span data-ttu-id="ece31-120">Adja meg a Kezdő értéknek a 0-t, majd adja meg a havi kamatszázalékot, amely alapján számítva lesz a kamat.</span><span class="sxs-lookup"><span data-stu-id="ece31-120">Enter the From value as 0 and then enter the interest percent per month that will be used to calculate the interest.</span></span> <span data-ttu-id="ece31-121">Ezen példa esetében ez 1,5.</span><span class="sxs-lookup"><span data-stu-id="ece31-121">For our example, it is 1.5.</span></span>
16. <span data-ttu-id="ece31-122">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="ece31-122">Click New.</span></span>
17. <span data-ttu-id="ece31-123">Adja meg a következő kezdőértéknek adja meg a 4-et, ez az első hónap, amelyben új kamatösszeget fog számolni.</span><span class="sxs-lookup"><span data-stu-id="ece31-123">Enter the next From value as 4, which is the first month that you will be calculating a new interest amount.</span></span>
18. <span data-ttu-id="ece31-124">Adja meg a havi kamatszázalékot, amelyet a kamat kiszámítására használ a 4. hónaptól kezdődően.</span><span class="sxs-lookup"><span data-stu-id="ece31-124">Enter the interest percent per month that will be used to calculate the interest starting in month 4.</span></span> <span data-ttu-id="ece31-125">Ebben a példában ez 2,0.</span><span class="sxs-lookup"><span data-stu-id="ece31-125">For this example, it is 2.0.</span></span>
19. <span data-ttu-id="ece31-126">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="ece31-126">Click New.</span></span>
20. <span data-ttu-id="ece31-127">Adja meg a következő kezdőértéknek adja meg a 7-et, ez a következő hónap, amelyben új kamatösszeget fog számolni.</span><span class="sxs-lookup"><span data-stu-id="ece31-127">Enter the next From value as 7, which is the next month that you will be calculating a new interest amount.</span></span>
21. <span data-ttu-id="ece31-128">Adja meg a havi kamatszázalékot, amelyet a kamat kiszámítására használ a 7. hónaptól kezdődően.</span><span class="sxs-lookup"><span data-stu-id="ece31-128">Enter the interest percent per month that will be used to calculate the interest starting in month 7.</span></span> <span data-ttu-id="ece31-129">Ebben a példában ez 2,5.</span><span class="sxs-lookup"><span data-stu-id="ece31-129">For this example, it is 2.5.</span></span>
22. <span data-ttu-id="ece31-130">Kattintson a Bezár gombra a beállítás befejezéséhez.</span><span class="sxs-lookup"><span data-stu-id="ece31-130">Click Close to complete the setup.</span></span>

