---
title: Szállítói számla létrehozása
description: Ez az eljárás bemutatja, hogyan hozzon létre egy szállítói számlát, és adjon hozzá címet és kapcsolattartási adatokat.
author: mkirknel
manager: AnnBe
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, LogisticsPostalAddressGrid, DirPartyLookup, LogisticsPostalAddress, SysLookupMultiSelectGrid
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ba585a9bb1a296bbf7181530e151d737bfa22fc2
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3149596"
---
# <a name="create-a-vendor-account"></a><span data-ttu-id="6665b-103">Szállítói számla létrehozása</span><span class="sxs-lookup"><span data-stu-id="6665b-103">Create a vendor account</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6665b-104">Ez az eljárás bemutatja, hogyan hozzon létre egy szállítói számlát, és adjon hozzá címet és kapcsolattartási adatokat.</span><span class="sxs-lookup"><span data-stu-id="6665b-104">This procedure shows how to create a vendor account, and add an address and contact information.</span></span> <span data-ttu-id="6665b-105">Az eljárás nem mutatja be, hogyan töltheti ki az összes mezőt a beszerzési és pénzügyi célokra.</span><span class="sxs-lookup"><span data-stu-id="6665b-105">The procedure does not show how to populate all fields for purchasing and financial purposes.</span></span> <span data-ttu-id="6665b-106">Az említett mezőkről további információkért olvassa el a mezőleírásokat.</span><span class="sxs-lookup"><span data-stu-id="6665b-106">To learn more about those fields, please read the field descriptions.</span></span> <span data-ttu-id="6665b-107">Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is használhatja.</span><span class="sxs-lookup"><span data-stu-id="6665b-107">You can use this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="6665b-108">Szállítói számlákat általában egy beszerzési vagy kinnlevőségi szakember hozza létre.</span><span class="sxs-lookup"><span data-stu-id="6665b-108">Vendor accounts are typically created by a procurement professional or accounts receivable personnel.</span></span>


## <a name="create-a-vendor-account"></a><span data-ttu-id="6665b-109">Szállítói számla létrehozása</span><span class="sxs-lookup"><span data-stu-id="6665b-109">Create a vendor account</span></span>
1. <span data-ttu-id="6665b-110">Válassza ezt: **Navigációs ablaktábla > Modulok > Beszerzés és forrás > Szállítók > Összes beszállító**.</span><span class="sxs-lookup"><span data-stu-id="6665b-110">Go to **Navigation pane > Modules > Procurement and sourcing > Vendors > All vendors**.</span></span>
2. <span data-ttu-id="6665b-111">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="6665b-111">Click **New**.</span></span>
3. <span data-ttu-id="6665b-112">A **Szállítói számla** mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6665b-112">In the **Vendor account** field, type a value.</span></span>
    - <span data-ttu-id="6665b-113">Az érték kitöltése automatikusan történhet.</span><span class="sxs-lookup"><span data-stu-id="6665b-113">The value may be populated automatically.</span></span> <span data-ttu-id="6665b-114">Ebben az esetben ezt a lépést kihagyhatja.</span><span class="sxs-lookup"><span data-stu-id="6665b-114">If so, you can skip this step.</span></span>  
    - <span data-ttu-id="6665b-115">Szállítói számlákat hozhat létre egy személyhez vagy szervezethez.</span><span class="sxs-lookup"><span data-stu-id="6665b-115">You can create vendor accounts for a person or organization.</span></span> <span data-ttu-id="6665b-116">Ez hatással lesz arra, hogy mely mezők érhetők el.</span><span class="sxs-lookup"><span data-stu-id="6665b-116">This will affect which fields are available.</span></span> <span data-ttu-id="6665b-117">Ebben a példában egy szállítói számlát hozunk létre egy szervezet számára.</span><span class="sxs-lookup"><span data-stu-id="6665b-117">In this example, we'll create a vendor account for an organization.</span></span>   
4. <span data-ttu-id="6665b-118">A **Név** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6665b-118">In the **Name** field, enter or select a value.</span></span> <span data-ttu-id="6665b-119">Ha a szállító egy már a rendszerben regisztrált fél, használhatja a legördülő listát, kiválaszthatja őket ebben a mezőben, és az új szállítói számla örökli a címet vagy elérhetőségi adatokat, amelyek már regisztrálva vannak.</span><span class="sxs-lookup"><span data-stu-id="6665b-119">If your vendor is an already a registered party in your system you can use drop down and select them in this field and the new vendor account will inherit the address and contact information that's already registered.</span></span>
5. <span data-ttu-id="6665b-120">A **Csoport** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6665b-120">In the **Group** field, enter or select a value.</span></span> <span data-ttu-id="6665b-121">A szállítói csoportba olyan szállítók tartoznak, amelyek a következő közös paraméterekkel rendelkeznek: Fizetési feltételek, kiegyenlítési időszak, készlet feladási főkönyvi számlák – például áfacsoport; alapértelmezett főkönyvi számlák; termékszűrő kódok vagy kínálat-előrejelzési konfiguráció.</span><span class="sxs-lookup"><span data-stu-id="6665b-121">The vendor group is used to group vendors that have any of the following parameters in common: Terms of payment, settle period, inventory posting ledger accounts – including the sales tax group, default ledger accounts, product filter codes, or supply forecast configuration.</span></span>
6. <span data-ttu-id="6665b-122">Adjon meg egy számot az **Alkalmazottak száma** mezőben.</span><span class="sxs-lookup"><span data-stu-id="6665b-122">In the **Number of employees** field, enter a number.</span></span>
7. <span data-ttu-id="6665b-123">Írjon be egy értéket a **Szervezet száma** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="6665b-123">In the **Organization number** field, type a value.</span></span>

## <a name="add-an-address"></a><span data-ttu-id="6665b-124">Cím hozzáadása</span><span class="sxs-lookup"><span data-stu-id="6665b-124">Add an address</span></span>
1. <span data-ttu-id="6665b-125">Bontsa ki a **Címek** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="6665b-125">Expand the **Addresses** section.</span></span>
2. <span data-ttu-id="6665b-126">Kattintson a **Hozzáadás** parancsra.</span><span class="sxs-lookup"><span data-stu-id="6665b-126">Click **Add**.</span></span>
3. <span data-ttu-id="6665b-127">A **Cél** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6665b-127">In the **Purpose** field, enter or select a value.</span></span> <span data-ttu-id="6665b-128">Egy vagy több célt is bejelölhet.</span><span class="sxs-lookup"><span data-stu-id="6665b-128">You can select one or more purposes.</span></span> <span data-ttu-id="6665b-129">Ezek segítségével válassza ki a megfelelő címet egy adott célra vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="6665b-129">These are used to select the correct address for a given purpose.</span></span> <span data-ttu-id="6665b-130">Például, ha a cél a „Számla”, azt a címet használja a program a számlák küldésekor.</span><span class="sxs-lookup"><span data-stu-id="6665b-130">For example, if the purpose is "Invoice" that address will be used when you send invoices.</span></span>
4. <span data-ttu-id="6665b-131">Adjon meg egy értéket a **Név vagy leírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="6665b-131">In the **Name or description** field, type a value.</span></span>
5. <span data-ttu-id="6665b-132">Az **Ország/régió** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6665b-132">In the **Country/region** field, enter or select a value.</span></span> <span data-ttu-id="6665b-133">Adja meg a cím adatait.</span><span class="sxs-lookup"><span data-stu-id="6665b-133">Enter the address details.</span></span> <span data-ttu-id="6665b-134">A kiválasztott ország/régió határozza meg a megjelenő megőket, az ország/régió címformátumának megfelelően.</span><span class="sxs-lookup"><span data-stu-id="6665b-134">The country/region that you selected will determine the fields you are presented with, corresponding to the address format for the country/region.</span></span> 
6. <span data-ttu-id="6665b-135">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="6665b-135">Click **OK**.</span></span>

## <a name="add-contact-information"></a><span data-ttu-id="6665b-136">Kapcsolattartási adatok hozzáadása</span><span class="sxs-lookup"><span data-stu-id="6665b-136">Add contact information</span></span>
1. <span data-ttu-id="6665b-137">Bontsa ki a **Kapcsolattartási adatok** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="6665b-137">Expand the **Contact information** section.</span></span>
2. <span data-ttu-id="6665b-138">Kattintson a **Hozzáadás** parancsra.</span><span class="sxs-lookup"><span data-stu-id="6665b-138">Click **Add**.</span></span>
3. <span data-ttu-id="6665b-139">Írjon egy értéket a **Leírás** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="6665b-139">In the **Description** field, type a value.</span></span>
4. <span data-ttu-id="6665b-140">A **Típus** mezőben válasszon ki egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6665b-140">In the **Type** field, select an option.</span></span>
5. <span data-ttu-id="6665b-141">Írjon be egy értéket a **Kapcsolattartó száma/címe** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="6665b-141">In the **Contact number/address** field, type a value.</span></span> <span data-ttu-id="6665b-142">Kiválaszthatja az Elsődleges jelölőnégyzetet, ha ez az elsődleges kapcsolattartó.</span><span class="sxs-lookup"><span data-stu-id="6665b-142">You can select the Primary check box if this is the primary contact.</span></span>  
6. <span data-ttu-id="6665b-143">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="6665b-143">Click **Save**.</span></span>
7. <span data-ttu-id="6665b-144">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="6665b-144">Close the page.</span></span>
8. <span data-ttu-id="6665b-145">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="6665b-145">Close the page.</span></span>

