---
title: Kinnlevőségek korosítási adatainak beállítás és létrehozása
description: Az útmutató segít a korosítási időszak definíciójának, vevői egyenlegek korosításának beállításában és az egyenlegek megtekintésében a Gyűjtések oldal Korosított egyenleg listájában.
author: mikefalkner
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustVendReportInterval, CustAgingSnapshot, CustCollectionsPoolsListPage, CustCollections
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9fd8738cfd3466464c9fec1760e9a369ff3a4a67
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1568235"
---
# <a name="set-up-and-generate-accounts-receivable-aging-information"></a><span data-ttu-id="cc597-103">Kinnlevőségek korosítási adatainak beállítás és létrehozása</span><span class="sxs-lookup"><span data-stu-id="cc597-103">Set up and generate accounts receivable aging information</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="cc597-104">Az útmutató segít a korosítási időszak definíciójának, vevői egyenlegek korosításának beállításában és az egyenlegek megtekintésében a Gyűjtések oldal Korosított egyenleg listájában.</span><span class="sxs-lookup"><span data-stu-id="cc597-104">This guide will help you set up an aging period definition, age customer balances, and view balances in the Aged balance list and the Collections page.</span></span> <span data-ttu-id="cc597-105">Ez a felvétel az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="cc597-105">This recording uses the USMF demo company.</span></span>


## <a name="create-an-aging-period-definition"></a><span data-ttu-id="cc597-106">Korosítási időszak definícióinak létrehozása.</span><span class="sxs-lookup"><span data-stu-id="cc597-106">Create an aging period definition</span></span>
1. <span data-ttu-id="cc597-107">Ugorjon a Követel és beszedések > Beállítás > Korosítási időszak definíciók pontra.</span><span class="sxs-lookup"><span data-stu-id="cc597-107">Go to Credit and collections > Setup > Aging period definitions.</span></span>
2. <span data-ttu-id="cc597-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cc597-108">Click New.</span></span>
3. <span data-ttu-id="cc597-109">Írjon be egy értéket a Korosítási időszak meghatározása mezőbe.</span><span class="sxs-lookup"><span data-stu-id="cc597-109">In the Aging period definition field, type a value.</span></span>
4. <span data-ttu-id="cc597-110">Írjon egy értéket a „Leírás” mezőbe.</span><span class="sxs-lookup"><span data-stu-id="cc597-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="cc597-111">Új korosítási időszak beszúrásához kattintson a Hozzáadás hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="cc597-111">Click Add below to insert a new aging period.</span></span>
6. <span data-ttu-id="cc597-112">A Periódus mezőbe írja be a leírást a korosodási jelentések megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="cc597-112">In the Period field, enter the description to show on aging reports.</span></span>
7. <span data-ttu-id="cc597-113">Az Egység mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="cc597-113">In the Unit field, enter a number.</span></span>
8. <span data-ttu-id="cc597-114">Egy lehetőség kiválasztása a Intervallum mezőben.</span><span class="sxs-lookup"><span data-stu-id="cc597-114">In the Interval field, select an option.</span></span>
    * <span data-ttu-id="cc597-115">A Főkönyvi időszak megegyezik a főkönyvi naptári időszakkal.</span><span class="sxs-lookup"><span data-stu-id="cc597-115">Ledger period matches the period to your ledger calendar.</span></span> <span data-ttu-id="cc597-116">Napok, hetek, hónapok, negyedévek és évek határozzák meg a dátumtartományok típusának méretét.</span><span class="sxs-lookup"><span data-stu-id="cc597-116">Day, week, month, quarter and years define the size of the interval by date type.</span></span> <span data-ttu-id="cc597-117">A Korlátlan lehetőség kiválasztja az összes tranzakció előtti vagy utáni periódust, attól függően, hogy ez az első vagy az utolsó periódus.</span><span class="sxs-lookup"><span data-stu-id="cc597-117">Unlimited selects all transactions before or after the previous period, depending on whether it is the first or last period.</span></span>  
9. <span data-ttu-id="cc597-118">Egy lehetőség kiválasztása a Korosítás jelölője mezőben.</span><span class="sxs-lookup"><span data-stu-id="cc597-118">In the Aging indicator field, select an option.</span></span>
10. <span data-ttu-id="cc597-119">A rács tetején válassza ki a periódust.</span><span class="sxs-lookup"><span data-stu-id="cc597-119">Select the period at the top of the grid.</span></span> <span data-ttu-id="cc597-120">Frissítse a leírást a korosítási időszak definíciójában a legrégebbi periódus leírásához</span><span class="sxs-lookup"><span data-stu-id="cc597-120">Update the description to describe the oldest period in the aging period definition</span></span>
11. <span data-ttu-id="cc597-121">A Periódus mezőbe írja be a korosítási időszak új leírását.</span><span class="sxs-lookup"><span data-stu-id="cc597-121">In the Period field, enter the new description of the aging period.</span></span>
12. <span data-ttu-id="cc597-122">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="cc597-122">Close the page.</span></span>

## <a name="age-the-balances"></a><span data-ttu-id="cc597-123">Korosítsa az egyenlegeket</span><span class="sxs-lookup"><span data-stu-id="cc597-123">Age the balances</span></span>
1. <span data-ttu-id="cc597-124">Ugorjon a Követelések és beszedések > Időszakos feladatok > Vevői egyenlegek korosítása pontra.</span><span class="sxs-lookup"><span data-stu-id="cc597-124">Go to Credit and collections > Periodic tasks > Age customer balances.</span></span>
2. <span data-ttu-id="cc597-125">A Korosítási időszak definíciója mezőben válassza ki a létrehozott korosítási időszak definícióját.</span><span class="sxs-lookup"><span data-stu-id="cc597-125">In the Aging period definition field, select the aging period definition that you created.</span></span>
    * <span data-ttu-id="cc597-126">Egy aktív pillanatképet rendelhet minden egyes korosítási időszak definíciójához.</span><span class="sxs-lookup"><span data-stu-id="cc597-126">You can have one active snapshot for each aging period definition.</span></span>  
    * <span data-ttu-id="cc597-127">Alapértelmezés szerint az összes vevő feldolgozásra kerül.</span><span class="sxs-lookup"><span data-stu-id="cc597-127">All customers are processed by default.</span></span> <span data-ttu-id="cc597-128">Ezzel a választással egyéni gyűjtéseket számolhat vevőgyűjtőhöz.</span><span class="sxs-lookup"><span data-stu-id="cc597-128">You can use this selection to calculate a single collections pool of customers.</span></span>  
    * <span data-ttu-id="cc597-129">Válassza ki a dátumot a tranzakcióból, amelyet a korosításhoz fog használni.</span><span class="sxs-lookup"><span data-stu-id="cc597-129">Select the date from the transaction that you will use for the aging.</span></span>  
    * <span data-ttu-id="cc597-130">Korosítás "kezdete" dátum kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="cc597-130">Select an "as of" date for aging.</span></span> <span data-ttu-id="cc597-131">Az alapértelmezett érték a mai nap, de ez módosítható a Kiválasztott dátum értékére, ilyenkor tetszés szerinti dátumot adhat meg.</span><span class="sxs-lookup"><span data-stu-id="cc597-131">The default is today but, if you change this field to Selected date, you will be able to pick the date that you want.</span></span> <span data-ttu-id="cc597-132">Kötegfolyamathoz használja a mai dátumot.</span><span class="sxs-lookup"><span data-stu-id="cc597-132">For batch processing, use Today's date.</span></span>  
3. <span data-ttu-id="cc597-133">Bővítse ki a vállalati tartományt.</span><span class="sxs-lookup"><span data-stu-id="cc597-133">Expand the Company range.</span></span> <span data-ttu-id="cc597-134">Kiválaszthatja a vállalatokat, amelyek bekerülnek pillanatképbe.</span><span class="sxs-lookup"><span data-stu-id="cc597-134">You can select the companies that will be included in the snapshot.</span></span> <span data-ttu-id="cc597-135">A jelenlegi vállalat van kiválasztva az alapértelmezett beállítások szerint.</span><span class="sxs-lookup"><span data-stu-id="cc597-135">The current company is selected by default.</span></span>
4. <span data-ttu-id="cc597-136">A pillanatkép elkészítéséhez kattintson az Ok gombra.</span><span class="sxs-lookup"><span data-stu-id="cc597-136">Click Ok to process the snapshot.</span></span> <span data-ttu-id="cc597-137">Eltart egy ideig, várjon, amíg a csúszka eltűnik, nézze meg érkezett-e üzenet az üzenetközpontba.</span><span class="sxs-lookup"><span data-stu-id="cc597-137">It will take some time so wait for the slider to disappear and check the message center for a message.</span></span>

## <a name="view-the-balances-on-the-aged-balances-list-and-on-the-collection-page"></a><span data-ttu-id="cc597-138">A Gyűjtések oldalon a Korosított egyenlegek lista egyenlegeinek megtekintése</span><span class="sxs-lookup"><span data-stu-id="cc597-138">View the balances on the Aged balances list and on the Collection page</span></span>
1. <span data-ttu-id="cc597-139">Ugorjon a Hitelezés és beszedés > Beszedés > Korosított egyenlegek pontra.</span><span class="sxs-lookup"><span data-stu-id="cc597-139">Go to Credit and collections > Collections > Aged balances.</span></span>
    * <span data-ttu-id="cc597-140">A lista oldal a vevő egyenlegeit mutatja.</span><span class="sxs-lookup"><span data-stu-id="cc597-140">The list page shows the balances for the customer.</span></span> <span data-ttu-id="cc597-141">A korosítási ikon a legrégebbi tranzakció korosítási időszakát jelzi.</span><span class="sxs-lookup"><span data-stu-id="cc597-141">The aging icon shows the aging period for the oldest transaction.</span></span>  
2. <span data-ttu-id="cc597-142">Válasszon egy egyenleggel rendelkező vevőt.</span><span class="sxs-lookup"><span data-stu-id="cc597-142">Select a customer with a balance.</span></span>
3. <span data-ttu-id="cc597-143">Bontsa ki a Korosítás adatterületet a korosított egyenleg megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="cc597-143">Expand the Aging fact box area to view the aged balances.</span></span>
    * <span data-ttu-id="cc597-144">A korosítási időszak definíciója az adatterülethez a paraméterek között meghatározott alapértelmezett korosítási időszak definíciójából származik.</span><span class="sxs-lookup"><span data-stu-id="cc597-144">The aging period definition for the fact box is taken from the default aging period definition specified in the parameters.</span></span> <span data-ttu-id="cc597-145">A Gyűjtés menü segítségével megváltoztathatja.</span><span class="sxs-lookup"><span data-stu-id="cc597-145">You can change it using the Collect menu.</span></span>  

