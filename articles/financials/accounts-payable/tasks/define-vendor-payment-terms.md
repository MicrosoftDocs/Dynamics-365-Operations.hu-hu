--- 
title: "Szállítói kifizetési feltételek meghatározása"
description: "Fizetési feltételek beállítása szállítói számlákhoz."
author: abruer
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: 4e38b01eb29702be0cc608489aa33277aa2de50a
ms.contentlocale: hu-hu
ms.lasthandoff: 08/07/2018

---
# <a name="define-vendor-payment-terms"></a><span data-ttu-id="fb6bf-103">Szállítói kifizetési feltételek meghatározása</span><span class="sxs-lookup"><span data-stu-id="fb6bf-103">Define vendor payment terms</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fb6bf-104">Fizetési feltételek beállítása szállítói számlákhoz.</span><span class="sxs-lookup"><span data-stu-id="fb6bf-104">Set up payment terms for vendor invoices.</span></span> <span data-ttu-id="fb6bf-105">Ez a feladat az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="fb6bf-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="fb6bf-106">Ugrás a Kötelezettségek > Kifizetés beállítása > Fizetési feltételek elemre.</span><span class="sxs-lookup"><span data-stu-id="fb6bf-106">Go to Accounts payable > Payment setup > Terms of payment.</span></span>
2. <span data-ttu-id="fb6bf-107">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="fb6bf-107">Click New.</span></span>
    * <span data-ttu-id="fb6bf-108">A fizetési feltételek oldalon meghatározhatja az esedékességi dátum számítását.</span><span class="sxs-lookup"><span data-stu-id="fb6bf-108">The Terms of payment page is used to define how the due date will be calculated.</span></span> <span data-ttu-id="fb6bf-109">Ez nem a készpénzfizetési engedmény dátumának számítására való.</span><span class="sxs-lookup"><span data-stu-id="fb6bf-109">It is not used to define how the cash discount date will be calculated.</span></span>  
3. <span data-ttu-id="fb6bf-110">Írjon be egy értéket a Fizetési feltételek mezőbe.</span><span class="sxs-lookup"><span data-stu-id="fb6bf-110">In the Terms of payment field, type a value.</span></span>
4. <span data-ttu-id="fb6bf-111">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="fb6bf-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="fb6bf-112">A Napok mezőbe írjon be egy számot.</span><span class="sxs-lookup"><span data-stu-id="fb6bf-112">In the Days field, enter a number.</span></span>
    * <span data-ttu-id="fb6bf-113">Az itt megadott szám hozzáadódik az esedékességi dátumhoz vagy a fizetési módban meghatározott időszak végéhez.</span><span class="sxs-lookup"><span data-stu-id="fb6bf-113">The number entered here will be used to add to the due date, or to the end of the period identified in the Payment method.</span></span> <span data-ttu-id="fb6bf-114">Ha például a Nettó lehetőséget választja, a szám az esedékességi dátumhoz adódik hozzá.</span><span class="sxs-lookup"><span data-stu-id="fb6bf-114">For example, if you select Net, the number will be added to the due date.</span></span> <span data-ttu-id="fb6bf-115">Ha az Aktuális hónap lehetőséget választja, a szám hozzáadódik az aktuális hónap utolsó napjához, és így kerül kiszámításra az esedékességi dátum.</span><span class="sxs-lookup"><span data-stu-id="fb6bf-115">If you select Current month, it will add the number to the last day of the current month to calculate the due date.</span></span>  
6. <span data-ttu-id="fb6bf-116">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="fb6bf-116">Click Save.</span></span>
7. <span data-ttu-id="fb6bf-117">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="fb6bf-117">Close the page.</span></span>
8. <span data-ttu-id="fb6bf-118">Ugrás a Kötelezettségek > Kifizetés beállítása > Készpénzfizetési engedmények elemre.</span><span class="sxs-lookup"><span data-stu-id="fb6bf-118">Go to Accounts payable > Payment setup > Cash discounts.</span></span>
9. <span data-ttu-id="fb6bf-119">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="fb6bf-119">Click New.</span></span>
10. <span data-ttu-id="fb6bf-120">A Készpénzfizetési engedmény mezőbe írjon egy azonosítót.</span><span class="sxs-lookup"><span data-stu-id="fb6bf-120">In the Cash discount field, enter an ID.</span></span>
11. <span data-ttu-id="fb6bf-121">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="fb6bf-121">In the Description field, type a value.</span></span>
12. <span data-ttu-id="fb6bf-122">Ha a szállító többszintű engedményt kínál, válassza ki a következő készpénzfizetési engedményt, ha a jelenlegi lejárt.</span><span class="sxs-lookup"><span data-stu-id="fb6bf-122">If the vendor offers a tiered discount, select the next cash discount after the current one is expired.</span></span>
13. <span data-ttu-id="fb6bf-123">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="fb6bf-123">Close the page.</span></span>
14. <span data-ttu-id="fb6bf-124">A Napok mezőbe írjon be egy számot.</span><span class="sxs-lookup"><span data-stu-id="fb6bf-124">In the Days field, enter a number.</span></span>
    * <span data-ttu-id="fb6bf-125">A Napok mezőben megadott mennyiség segítségével a készpénzfizetési engedmény számítása történik a Nettó/Aktuális mezőben megadott lehetőségeket is figyelembe véve.</span><span class="sxs-lookup"><span data-stu-id="fb6bf-125">The quantity entered in the Days field will be used to calculate the Cash discount date, based on what option was selected in the Net/Current field.</span></span> <span data-ttu-id="fb6bf-126">Ha a Nettó lehetőséget választotta, a mennyiség hozzáadódik a számla dátumához, és így kerül kiszámításra a készpénzfizetési engedmény dátuma.</span><span class="sxs-lookup"><span data-stu-id="fb6bf-126">If Net was selected, the quantity will be added to the invoice date to determine the cash discount date.</span></span> <span data-ttu-id="fb6bf-127">Ha az Aktuális hónap lehetőséget választotta, a mennyiség hozzáadódik az aktuális hónap végéhez, így kerül kiszámításra a készpénzfizetési engedmény dátuma.</span><span class="sxs-lookup"><span data-stu-id="fb6bf-127">If Current month was selected, the quantity will be added to the end of the currency month to determine the cash discount date.</span></span>  
15. <span data-ttu-id="fb6bf-128">Az Engedmény mezőben adja meg a készpénzfizetési engedmény százalékát.</span><span class="sxs-lookup"><span data-stu-id="fb6bf-128">Enter the percentage of the cash discount in the Discount field.</span></span> 
16. <span data-ttu-id="fb6bf-129">Adja meg a fő számlát, amelyhez a vevői számlákon feladásra kerül a készpénzfizetési engedmény.</span><span class="sxs-lookup"><span data-stu-id="fb6bf-129">Enter the main account to which the cash discount will be posted for customer invoices.</span></span>
17. <span data-ttu-id="fb6bf-130">Adja meg a fő számlát, amelyhez a szállítói számlákon feladásra kerül a készpénzfizetési engedmény.</span><span class="sxs-lookup"><span data-stu-id="fb6bf-130">Enter the main account to which the cash discount will be posted for vendor invoices.</span></span>
    * <span data-ttu-id="fb6bf-131">Ha a „Kedvezmény ellenszámlák” beállításnál a fő számlát jelöli meg a szállítói kedvezményekhez, akkor a rendszer a fő számlát fogja használni.</span><span class="sxs-lookup"><span data-stu-id="fb6bf-131">If 'Discount offset accounts' is set to Use main account for vendor discount, then the Main account will be used.</span></span>  <span data-ttu-id="fb6bf-132">Ha a beállítás a számlasorokon Számlák, a készpénzfizetési engedmény feladása a számlasor eszköz-/költségszámla részére kerül feladásra.</span><span class="sxs-lookup"><span data-stu-id="fb6bf-132">If the option is set to Accounts on the invoice lines, the cash discount will be posted to the asset/expense accounts on the invoice's lines.</span></span>  
18. <span data-ttu-id="fb6bf-133">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="fb6bf-133">Click Save.</span></span>


