--- 
title: "Főkönyvi számlaalias beállítása"
description: "Ez az eljárás bemutatja, hogyan lehet aliast létrehozni egy számlához, amely parancsikont biztosít egy számlaszámhoz."
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerAccountAlias
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 1ae075d7678ab15157a500c6ee5bd77e8211254a
ms.contentlocale: hu-hu
ms.lasthandoff: 09/14/2018

---
# <a name="set-up-a-ledger-account-alias"></a><span data-ttu-id="5d479-103">Főkönyvi számlaalias beállítása</span><span class="sxs-lookup"><span data-stu-id="5d479-103">Set up a ledger account alias</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5d479-104">Ez az eljárás bemutatja, hogyan lehet aliast létrehozni egy számlához, amely parancsikont biztosít egy számlaszámhoz.</span><span class="sxs-lookup"><span data-stu-id="5d479-104">This procedure shows how to create an account alias that provides a shortcut for entering an account number.</span></span> <span data-ttu-id="5d479-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="5d479-105">This procedure users demo data company USMF.</span></span>

1. <span data-ttu-id="5d479-106">Ugorjon a Főkönyv > Számlatükör > Számlák > Főszámla-alias pontra.</span><span class="sxs-lookup"><span data-stu-id="5d479-106">Go to General ledger > Chart of accounts > Accounts > Ledger account alias.</span></span>
2. <span data-ttu-id="5d479-107">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5d479-107">Click New.</span></span>
3. <span data-ttu-id="5d479-108">Írjon egy értéket a Főkönyvi alias mezőbe.</span><span class="sxs-lookup"><span data-stu-id="5d479-108">In the Ledger account alias field, type a value.</span></span>
4. <span data-ttu-id="5d479-109">A Számlastruktúra mezőben válassza ki azt a struktúrát, amelyhez a számla és a dimenziók tartoznak.</span><span class="sxs-lookup"><span data-stu-id="5d479-109">In the Account structure field, select the structure the account and dimensions belong to.</span></span>
5. <span data-ttu-id="5d479-110">A Cég neve mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="5d479-110">In the Company field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="5d479-111">A listában keresse meg és válassza ki azt a vállalatot, amelyre az alias vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="5d479-111">In the list, find and select the company that the alias applies to.</span></span>
7. <span data-ttu-id="5d479-112">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="5d479-112">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="5d479-113">A Főkönyviszámla-alias definíciója mezőben adja meg a számlát és a dimenziókat.</span><span class="sxs-lookup"><span data-stu-id="5d479-113">In the Ledger account alias definition field, specify the account and dimensions.</span></span>
    * <span data-ttu-id="5d479-114">A számla és a dimenziók adatai a gyorsparancs használata esetén fognak megjelenni.</span><span class="sxs-lookup"><span data-stu-id="5d479-114">The account and dimensions will be populated when using the shortcut.</span></span>  
9. <span data-ttu-id="5d479-115">A Kezdeti fókusz mezőben válassza ki azt a dimenziót, amelyre a fókusz kerül az alias használata esetén.</span><span class="sxs-lookup"><span data-stu-id="5d479-115">In the Initial focus field, select the dimension that will have focus when the alias is used.</span></span>
    * <span data-ttu-id="5d479-116">A gyorsparancs beírása után a számla és a dimenziók adatai megjelennek, a Kezdeti fókusz mező az lesz, ahol a kurzor vagy a fókusz helyezkedik el.</span><span class="sxs-lookup"><span data-stu-id="5d479-116">After you type the shortcut, and the account and dimensions are populated, the Initial focus field is where the cursor or focus will move to.</span></span>  


