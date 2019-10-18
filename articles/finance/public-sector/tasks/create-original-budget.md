---
title: Eredeti költségvetés létrehozása, majd az előzetes költségvetési bejegyzések sztornírozása az állami szektorban.
description: Amikor eredeti költségvetési bejegyzést hoz létre és az előzetes költségvetési összegeket tartalmazó költségvetési modellt és dimenzió értékeket használja, az előzetes költségvetési összegeket sztornírozni lehet.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetTransaction, BudgetAccountStructureLookup, BudgetTransactionMultiPost
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4895a48622d5bbd80ea284be8fe0b8e59622e488
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2185359"
---
# <a name="create-an-original-budget-and-then-reverse-preliminary-budget-entries-in-the-public-sector"></a><span data-ttu-id="64964-103">Eredeti költségvetés létrehozása, majd az előzetes költségvetési bejegyzések sztornírozása az állami szektorban.</span><span class="sxs-lookup"><span data-stu-id="64964-103">Create an original budget and then reverse preliminary budget entries in the public sector</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="64964-104">Amikor eredeti költségvetési bejegyzést hoz létre és az előzetes költségvetési összegeket tartalmazó költségvetési modellt és dimenzió értékeket használja, az előzetes költségvetési összegeket sztornírozni lehet.</span><span class="sxs-lookup"><span data-stu-id="64964-104">When you create an original budget entry and use the budget model and dimension values that contain preliminary budget amounts, the preliminary budget amounts can be reversed.</span></span> <span data-ttu-id="64964-105">Ez az eljárás az állami szektor partícióban lévő PSUS bemutató vállalati adatok használatával készült.</span><span class="sxs-lookup"><span data-stu-id="64964-105">This procedure was created using the PSUS demo company data in the public sector partition.</span></span>

1. <span data-ttu-id="64964-106">Ugorjon a Költségvetés > Költségvetési tételjegyzék-bejegyzések pontra.</span><span class="sxs-lookup"><span data-stu-id="64964-106">Go to Budgeting > Budget register entries.</span></span>
2. <span data-ttu-id="64964-107">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="64964-107">Click New.</span></span>
3. <span data-ttu-id="64964-108">A Költségvetési modell mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="64964-108">In the Budget model field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="64964-109">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="64964-109">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="64964-110">A Költségvetési kód mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="64964-110">In the Budget code field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="64964-111">Kattintson a listában az Eredeti költségvetés elemre.</span><span class="sxs-lookup"><span data-stu-id="64964-111">In the list, click Original budget.</span></span>
7. <span data-ttu-id="64964-112">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="64964-112">Click Save.</span></span>
8. <span data-ttu-id="64964-113">Kattintson az Új sor hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="64964-113">Click Add line.</span></span>
9. <span data-ttu-id="64964-114">Választható: Ha módosítani kívánja a dátumot a fejlécben beállítotthoz képest, adjon meg egy új dátumot.</span><span class="sxs-lookup"><span data-stu-id="64964-114">Optional: If you want to change the date from the one in the header, enter a new date.</span></span> <span data-ttu-id="64964-115">Ez a dátum határozza meg azt a pénzügyi időszakot, amelyre a költségvetés rögzítésre kerül.</span><span class="sxs-lookup"><span data-stu-id="64964-115">This date determines the fiscal period that the budget will be recorded to.</span></span>
10. <span data-ttu-id="64964-116">A Számlastruktúra mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="64964-116">In the Account structure field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="64964-117">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="64964-117">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="64964-118">A Dimenzióértékek mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="64964-118">In the Dimension values field, specify the desired values.</span></span>
13. <span data-ttu-id="64964-119">Az Összeg mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="64964-119">In the Amount field, enter a number.</span></span>
14. <span data-ttu-id="64964-120">A Pénznem mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="64964-120">In the Currency field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="64964-121">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="64964-121">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="64964-122">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="64964-122">Click Save.</span></span>
17. <span data-ttu-id="64964-123">Kattintson a Költségvetési egyenlegek frissítése gombra.</span><span class="sxs-lookup"><span data-stu-id="64964-123">Click Update budget balances.</span></span>
    * <span data-ttu-id="64964-124">Választható: Kiválaszthatja a Fordított előzetes költségvetés beállítást.</span><span class="sxs-lookup"><span data-stu-id="64964-124">Optional: You can select the Reverse preliminary budget option.</span></span> <span data-ttu-id="64964-125">Sztornírozható minden előzetes költségvetési tétel, vagy csak azon előzetes költségvetési tételek, amelyek a megadott költségvetési kóddal rendelkeznek.</span><span class="sxs-lookup"><span data-stu-id="64964-125">Note that you can reverse all preliminary budget entries, or only the preliminary budget entries that have the budget code that you specify.</span></span>  
    * <span data-ttu-id="64964-126">Opcionális választásokhoz kattintson a Feloldás ikonra az oldal tetején.</span><span class="sxs-lookup"><span data-stu-id="64964-126">To make optional selections, click the Unlock icon at the top of the page.</span></span>  
18. <span data-ttu-id="64964-127">Kattintson a Módosítás gombra.</span><span class="sxs-lookup"><span data-stu-id="64964-127">Click Update.</span></span>

