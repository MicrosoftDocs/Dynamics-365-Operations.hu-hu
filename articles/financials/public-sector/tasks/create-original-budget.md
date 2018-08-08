--- 
title: "Eredeti költségvetés létrehozása és az előzetes költségvetési bejegyzések sztornírozása az állami szektorban"
description: "Amikor eredeti költségvetési bejegyzést hoz létre és az előzetes költségvetési összegeket tartalmazó költségvetési modellt és dimenzió értékeket használja, az előzetes költségvetési összegeket sztornírozni lehet."
author: ShylaThompson
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: a6f9b20658764e1a7584a34b573d103f0a13c7d8
ms.contentlocale: hu-hu
ms.lasthandoff: 08/07/2018

---
# <a name="create-an-original-budget-and-reverse-preliminary-budget-entries-in-the-public-sector"></a><span data-ttu-id="aad13-103">Eredeti költségvetés létrehozása és az előzetes költségvetési bejegyzések sztornírozása az állami szektorban</span><span class="sxs-lookup"><span data-stu-id="aad13-103">Create an original budget and reverse preliminary budget entries in the public sector</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="aad13-104">Amikor eredeti költségvetési bejegyzést hoz létre és az előzetes költségvetési összegeket tartalmazó költségvetési modellt és dimenzió értékeket használja, az előzetes költségvetési összegeket sztornírozni lehet.</span><span class="sxs-lookup"><span data-stu-id="aad13-104">When you create an original budget entry and use the budget model and dimension values that contain preliminary budget amounts, the preliminary budget amounts can be reversed.</span></span> <span data-ttu-id="aad13-105">Ez az eljárás az állami szektor partícióban lévő PSUS bemutató vállalati adatok használatával készült.</span><span class="sxs-lookup"><span data-stu-id="aad13-105">This procedure was created using the PSUS demo company data in the public sector partition.</span></span>

1. <span data-ttu-id="aad13-106">Ugorjon a Költségvetés > Költségvetési tételjegyzék-bejegyzések pontra.</span><span class="sxs-lookup"><span data-stu-id="aad13-106">Go to Budgeting > Budget register entries.</span></span>
2. <span data-ttu-id="aad13-107">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="aad13-107">Click New.</span></span>
3. <span data-ttu-id="aad13-108">A Költségvetési modell mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="aad13-108">In the Budget model field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="aad13-109">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="aad13-109">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="aad13-110">A Költségvetési kód mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="aad13-110">In the Budget code field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="aad13-111">Kattintson a listában az Eredeti költségvetés elemre.</span><span class="sxs-lookup"><span data-stu-id="aad13-111">In the list, click Original budget.</span></span>
7. <span data-ttu-id="aad13-112">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="aad13-112">Click Save.</span></span>
8. <span data-ttu-id="aad13-113">Kattintson az Új sor hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="aad13-113">Click Add line.</span></span>
9. <span data-ttu-id="aad13-114">Választható: Ha módosítani kívánja a dátumot a fejlécben beállítotthoz képest, adjon meg egy új dátumot.</span><span class="sxs-lookup"><span data-stu-id="aad13-114">Optional: If you want to change the date from the one in the header, enter a new date.</span></span> <span data-ttu-id="aad13-115">Ez a dátum határozza meg azt a pénzügyi időszakot, amelyre a költségvetés rögzítésre kerül.</span><span class="sxs-lookup"><span data-stu-id="aad13-115">This date determines the fiscal period that the budget will be recorded to.</span></span>
10. <span data-ttu-id="aad13-116">A Számlastruktúra mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="aad13-116">In the Account structure field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="aad13-117">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="aad13-117">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="aad13-118">A Dimenzióértékek mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="aad13-118">In the Dimension values field, specify the desired values.</span></span>
13. <span data-ttu-id="aad13-119">Az Összeg mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="aad13-119">In the Amount field, enter a number.</span></span>
14. <span data-ttu-id="aad13-120">A Pénznem mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="aad13-120">In the Currency field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="aad13-121">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="aad13-121">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="aad13-122">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="aad13-122">Click Save.</span></span>
17. <span data-ttu-id="aad13-123">Kattintson a Költségvetési egyenlegek frissítése gombra.</span><span class="sxs-lookup"><span data-stu-id="aad13-123">Click Update budget balances.</span></span>
    * <span data-ttu-id="aad13-124">Választható: Kiválaszthatja a Fordított előzetes költségvetés beállítást.</span><span class="sxs-lookup"><span data-stu-id="aad13-124">Optional: You can select the Reverse preliminary budget option.</span></span> <span data-ttu-id="aad13-125">Sztornírozható minden előzetes költségvetési tétel, vagy csak azon előzetes költségvetési tételek, amelyek a megadott költségvetési kóddal rendelkeznek.</span><span class="sxs-lookup"><span data-stu-id="aad13-125">Note that you can reverse all preliminary budget entries, or only the preliminary budget entries that have the budget code that you specify.</span></span>  
    * <span data-ttu-id="aad13-126">Opcionális választásokhoz kattintson a Feloldás ikonra az oldal tetején.</span><span class="sxs-lookup"><span data-stu-id="aad13-126">To make optional selections, click the Unlock icon at the top of the page.</span></span>  
18. <span data-ttu-id="aad13-127">Kattintson a Módosítás gombra.</span><span class="sxs-lookup"><span data-stu-id="aad13-127">Click Update.</span></span>


