---
title: Kinnlevőségek korosítási adatainak beállítás és létrehozása
description: Az útmutató segít a korosítási időszak definíciójának, vevői egyenlegek korosításának beállításában és az egyenlegek megtekintésében a Gyűjtések oldal Korosított egyenleg listájában.
author: mikefalkner
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustVendReportInterval, CustAgingSnapshot, CustCollectionsPoolsListPage, CustCollections
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 77b5dd5feb16cc3bd6d64b6520cc47087c5b5224
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1834367"
---
# <a name="set-up-and-generate-accounts-receivable-aging-information"></a><span data-ttu-id="8f591-103">Kinnlevőségek korosítási adatainak beállítás és létrehozása</span><span class="sxs-lookup"><span data-stu-id="8f591-103">Set up and generate accounts receivable aging information</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8f591-104">Az útmutató segít a korosítási időszak definíciójának, vevői egyenlegek korosításának beállításában és az egyenlegek megtekintésében a Gyűjtések oldal Korosított egyenleg listájában.</span><span class="sxs-lookup"><span data-stu-id="8f591-104">This guide will help you set up an aging period definition, age customer balances, and view balances in the Aged balance list and the Collections page.</span></span> <span data-ttu-id="8f591-105">Ez a felvétel az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="8f591-105">This recording uses the USMF demo company.</span></span>


## <a name="create-an-aging-period-definition"></a><span data-ttu-id="8f591-106">Korosítási időszak definícióinak létrehozása.</span><span class="sxs-lookup"><span data-stu-id="8f591-106">Create an aging period definition</span></span>
1. <span data-ttu-id="8f591-107">Ugorjon a **Navigációs ablaktábla > Modulok > Követelések és beszedések > Beállítás > Korosítási időszak definíciói** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8f591-107">Go to **Navigation pane > Modules > Credit and collections > Setup > Aging period definitions**.</span></span>
2. <span data-ttu-id="8f591-108">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="8f591-108">Click **New**.</span></span>
3. <span data-ttu-id="8f591-109">Írjon be egy értéket a **Korosítási időszak definíciója** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="8f591-109">In the **Aging period definition** field, type a value.</span></span>
4. <span data-ttu-id="8f591-110">Írjon egy értéket a **Leírás** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="8f591-110">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="8f591-111">Új korosítási időszak beszúrásához kattintson a **Hozzáadás alá** hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="8f591-111">Click **Add below** to insert a new aging period.</span></span>
6. <span data-ttu-id="8f591-112">Az **Időszak** mezőben adja meg a leírást a korosodási jelentések megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="8f591-112">In the **Period** field, enter the description to show on aging reports.</span></span>
7. <span data-ttu-id="8f591-113">Az **Egység** mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="8f591-113">In the **Unit** field, enter a number.</span></span>
8. <span data-ttu-id="8f591-114">Válasszon ki egy lehetőséget az **Intervallum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="8f591-114">In the **Interval** field, select an option.</span></span> <span data-ttu-id="8f591-115">A Főkönyvi időszak megegyezik a főkönyvi naptári időszakkal.</span><span class="sxs-lookup"><span data-stu-id="8f591-115">Ledger period matches the period to your ledger calendar.</span></span> <span data-ttu-id="8f591-116">Napok, hetek, hónapok, negyedévek és évek határozzák meg a dátumtartományok típusának méretét.</span><span class="sxs-lookup"><span data-stu-id="8f591-116">Day, week, month, quarter and years define the size of the interval by date type.</span></span> <span data-ttu-id="8f591-117">A Korlátlan lehetőség kiválasztja az összes tranzakció előtti vagy utáni periódust, attól függően, hogy ez az első vagy az utolsó periódus.</span><span class="sxs-lookup"><span data-stu-id="8f591-117">Unlimited selects all transactions before or after the previous period, depending on whether it is the first or last period.</span></span>  
9. <span data-ttu-id="8f591-118">Válasszon ki egy lehetőséget a **Korosítás jelölője** mezőben.</span><span class="sxs-lookup"><span data-stu-id="8f591-118">In the **Aging indicator** field, select an option.</span></span>
10. <span data-ttu-id="8f591-119">A rács tetején válassza ki a periódust.</span><span class="sxs-lookup"><span data-stu-id="8f591-119">Select the period at the top of the grid.</span></span> <span data-ttu-id="8f591-120">Frissítse a leírást a korosítási időszak definíciójában a legrégebbi periódus leírásához</span><span class="sxs-lookup"><span data-stu-id="8f591-120">Update the description to describe the oldest period in the aging period definition</span></span>
11. <span data-ttu-id="8f591-121">Az **Időszak** mezőben adja meg a korosítási időszak új leírását.</span><span class="sxs-lookup"><span data-stu-id="8f591-121">In the **Period** field, enter the new description of the aging period.</span></span>
12. <span data-ttu-id="8f591-122">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="8f591-122">Close the page.</span></span>

## <a name="age-the-balances"></a><span data-ttu-id="8f591-123">Korosítsa az egyenlegeket</span><span class="sxs-lookup"><span data-stu-id="8f591-123">Age the balances</span></span>
1. <span data-ttu-id="8f591-124">Ugorjon a **Követelések és beszedések > Időszakos feladatok > Vevői egyenlegek korosítása** elemre.</span><span class="sxs-lookup"><span data-stu-id="8f591-124">Go to **Credit and collections > Periodic tasks > Age customer balances**.</span></span>
2. <span data-ttu-id="8f591-125">A **Korosítási időszak definíciója** mezőben válassza ki a létrehozott korosítási időszak definícióját.</span><span class="sxs-lookup"><span data-stu-id="8f591-125">In the **Aging period definition** field, select the aging period definition that you created.</span></span>
    + <span data-ttu-id="8f591-126">Egy aktív pillanatképet rendelhet minden egyes korosítási időszak definíciójához.</span><span class="sxs-lookup"><span data-stu-id="8f591-126">You can have one active snapshot for each aging period definition.</span></span>  
    + <span data-ttu-id="8f591-127">Alapértelmezés szerint az összes vevő feldolgozásra kerül.</span><span class="sxs-lookup"><span data-stu-id="8f591-127">All customers are processed by default.</span></span> <span data-ttu-id="8f591-128">Ezzel a választással egyéni gyűjtéseket számolhat vevőgyűjtőhöz.</span><span class="sxs-lookup"><span data-stu-id="8f591-128">You can use this selection to calculate a single collections pool of customers.</span></span>  
    + <span data-ttu-id="8f591-129">Válassza ki a dátumot a tranzakcióból, amelyet a korosításhoz fog használni.</span><span class="sxs-lookup"><span data-stu-id="8f591-129">Select the date from the transaction that you will use for the aging.</span></span>  
    + <span data-ttu-id="8f591-130">Korosítás "kezdete" dátum kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="8f591-130">Select an "as of" date for aging.</span></span> <span data-ttu-id="8f591-131">Az alapértelmezett érték a mai nap, de ez módosítható a Kiválasztott dátum értékére, ilyenkor tetszés szerinti dátumot adhat meg.</span><span class="sxs-lookup"><span data-stu-id="8f591-131">The default is today but, if you change this field to Selected date, you will be able to pick the date that you want.</span></span> <span data-ttu-id="8f591-132">Kötegfolyamathoz használja a mai dátumot.</span><span class="sxs-lookup"><span data-stu-id="8f591-132">For batch processing, use Today's date.</span></span>  
3. <span data-ttu-id="8f591-133">Bővítse ki a **Vállalati** tartományt.</span><span class="sxs-lookup"><span data-stu-id="8f591-133">Expand the **Company** range.</span></span> <span data-ttu-id="8f591-134">Kiválaszthatja a vállalatokat, amelyek bekerülnek pillanatképbe.</span><span class="sxs-lookup"><span data-stu-id="8f591-134">You can select the companies that will be included in the snapshot.</span></span> <span data-ttu-id="8f591-135">A jelenlegi vállalat van kiválasztva az alapértelmezett beállítások szerint.</span><span class="sxs-lookup"><span data-stu-id="8f591-135">The current company is selected by default.</span></span>
4. <span data-ttu-id="8f591-136">A pillanatkép elkészítéséhez kattintson az **Ok** gombra.</span><span class="sxs-lookup"><span data-stu-id="8f591-136">Click **Ok** to process the snapshot.</span></span> <span data-ttu-id="8f591-137">Eltart egy ideig, várjon, amíg a csúszka eltűnik, nézze meg érkezett-e üzenet az üzenetközpontba.</span><span class="sxs-lookup"><span data-stu-id="8f591-137">It will take some time so wait for the slider to disappear and check the message center for a message.</span></span>

## <a name="view-the-balances-on-the-aged-balances-list-and-on-the-collection-page"></a><span data-ttu-id="8f591-138">A Gyűjtések oldalon a Korosított egyenlegek lista egyenlegeinek megtekintése</span><span class="sxs-lookup"><span data-stu-id="8f591-138">View the balances on the Aged balances list and on the Collection page</span></span>
1. <span data-ttu-id="8f591-139">Ugorjon a **Hitelezés és beszedés > Beszedés > Korosított egyenlegek** elemre.</span><span class="sxs-lookup"><span data-stu-id="8f591-139">Go to **Credit and collections > Collections > Aged balances**.</span></span> <span data-ttu-id="8f591-140">A lista oldal a vevő egyenlegeit mutatja.</span><span class="sxs-lookup"><span data-stu-id="8f591-140">The list page shows the balances for the customer.</span></span> <span data-ttu-id="8f591-141">A korosítási ikon a legrégebbi tranzakció korosítási időszakát jelzi.</span><span class="sxs-lookup"><span data-stu-id="8f591-141">The aging icon shows the aging period for the oldest transaction.</span></span>  
2. <span data-ttu-id="8f591-142">Válasszon egy egyenleggel rendelkező vevőt.</span><span class="sxs-lookup"><span data-stu-id="8f591-142">Select a customer with a balance.</span></span>
3. <span data-ttu-id="8f591-143">Bontsa ki a **Korosítás adatterületet** a korosított egyenleg megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="8f591-143">Expand the **Aging fact** box area to view the aged balances.</span></span> <span data-ttu-id="8f591-144">A korosítási időszak definíciója az adatterülethez a paraméterek között meghatározott alapértelmezett korosítási időszak definíciójából származik.</span><span class="sxs-lookup"><span data-stu-id="8f591-144">The aging period definition for the fact box is taken from the default aging period definition specified in the parameters.</span></span> <span data-ttu-id="8f591-145">A Gyűjtés menü segítségével megváltoztathatja.</span><span class="sxs-lookup"><span data-stu-id="8f591-145">You can change it using the Collect menu.</span></span>  

