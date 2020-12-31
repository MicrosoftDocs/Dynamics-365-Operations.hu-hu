---
title: Költségtípusok beállítása
description: Ez a témakör bemutatja, hogyan lehet eszköztípusokat beállítani az Eszközlízing modulban.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2019-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: d27c5653d6305aad23142fa6f803134153661278
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/28/2020
ms.locfileid: "4444173"
---
# <a name="set-up-expense-types"></a><span data-ttu-id="04184-103">Költségtípusok beállítása</span><span class="sxs-lookup"><span data-stu-id="04184-103">Set up expense types</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="04184-104">Ez a témakör bemutatja, hogyan lehet eszköztípusokat beállítani az Eszközlízing modulban.</span><span class="sxs-lookup"><span data-stu-id="04184-104">This topic explains how to set up expense types in Asset leasing.</span></span> <span data-ttu-id="04184-105">A fizetési ütemezés által nem képviselt költségeket *Költségnek* nevezzük.</span><span class="sxs-lookup"><span data-stu-id="04184-105">Costs that aren't represented by the payment schedule are known as *expense costs*.</span></span> <span data-ttu-id="04184-106">Ilyen költségek például a ingatlanadók, a közterület karbantartási költségei és a biztosítási költségek.</span><span class="sxs-lookup"><span data-stu-id="04184-106">Examples of these costs include property taxes, common area maintenance costs, and insurance expenses.</span></span>

## <a name="add-an-administrative-expense-type"></a><span data-ttu-id="04184-107">Adminisztratív költségtípus hozzáadása</span><span class="sxs-lookup"><span data-stu-id="04184-107">Add an administrative expense type</span></span>

1. <span data-ttu-id="04184-108">Nyissa meg az **Eszközlízing \> Beállítás \> Költségtípusok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="04184-108">Go to **Asset leasing \> Setup \> Expense types**.</span></span>
2. <span data-ttu-id="04184-109">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="04184-109">Select **New**.</span></span>
3. <span data-ttu-id="04184-110">A megfelelő mezőkben adja meg az új költségtípust és a megnevezést.</span><span class="sxs-lookup"><span data-stu-id="04184-110">In the appropriate fields, enter the new expense type and a description.</span></span>

## <a name="assign-accounts-to-administrative-costs"></a><span data-ttu-id="04184-111">Számlák hozzárendelése az adminisztrációs költségekhez</span><span class="sxs-lookup"><span data-stu-id="04184-111">Assign accounts to administrative costs</span></span>

<span data-ttu-id="04184-112">Ezután a számlákat a költségtípusokhoz kell társítani.</span><span class="sxs-lookup"><span data-stu-id="04184-112">Next, you should associate accounts with the expense types.</span></span> <span data-ttu-id="04184-113">Ezek a számlák a költségütemezési bejegyzésekkor lesznek terhelve és feladva.</span><span class="sxs-lookup"><span data-stu-id="04184-113">These accounts will be debited when expense schedule entries are posted.</span></span> <span data-ttu-id="04184-114">Az ellenszámla minden lízing **Működési költségfizetési ütemezés** sorában meg van adva.</span><span class="sxs-lookup"><span data-stu-id="04184-114">The offset account is specified on the **Executory costs payment schedule** lines on each lease.</span></span>

1. <span data-ttu-id="04184-115">Nyissa meg az **Eszközlízing \> Beállítás \> Eszközlízing paraméterei** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="04184-115">Go to **Asset leasing \> Setup \> Asset leasing parameters**.</span></span>
2. <span data-ttu-id="04184-116">A **Számlák** fül **Működési költségek** gyorslapján, a **Költségtípus** mezőjében válassza ki a költség típusát.</span><span class="sxs-lookup"><span data-stu-id="04184-116">On the **Accounts** tab, on the **Executory costs** FastTab, in the **Expense type** field, select the expense type.</span></span>
3. <span data-ttu-id="04184-117">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="04184-117">Select **Add**.</span></span>
4. <span data-ttu-id="04184-118">A **Könyv típusa** mezőben válassza ki azt a könyvtípust, amelyet az adminisztratív költségekhez szeretne kapcsolni.</span><span class="sxs-lookup"><span data-stu-id="04184-118">In the **Book type** field, select the book type to link to the administrative costs.</span></span>

    > [!NOTE]
    > <span data-ttu-id="04184-119">Ugyanahhoz a költségszámlához több könyvtípus is csatolható.</span><span class="sxs-lookup"><span data-stu-id="04184-119">Multiple book types can be linked to the same expense account.</span></span>

5. <span data-ttu-id="04184-120">A **Számlakód** mezőben adja meg, hogy a könyv mely lízingekre legyen alkalmazva:</span><span class="sxs-lookup"><span data-stu-id="04184-120">In the **Account code** field, specify which leases the book should be applied to:</span></span>

    - <span data-ttu-id="04184-121">**Mind** – Könyv alkalmazása az összes lízinghez.</span><span class="sxs-lookup"><span data-stu-id="04184-121">**All** – Apply the book to all leases.</span></span>
    - <span data-ttu-id="04184-122">**Csoport** – A könyv alkalmazása a lízingek egy adott csoportjára.</span><span class="sxs-lookup"><span data-stu-id="04184-122">**Group** – Apply the book to a specific group of leases.</span></span>
    - <span data-ttu-id="04184-123">**Tábla** – Könyv alkalmazása egy adott lízinghez.</span><span class="sxs-lookup"><span data-stu-id="04184-123">**Table** – Apply the book to specific leases.</span></span>

6. <span data-ttu-id="04184-124">Ha kiválasztotta a **Csoport** vagy **Tábla** lehetőséget a **Számlakód** mezőben, válassza ki a számlaszámot vagy csoportszámot a **Számla-/Csoportszám** mezőben.</span><span class="sxs-lookup"><span data-stu-id="04184-124">If you selected **Group** or **Table** in the **Account code** field, select an account number or group number in the **Account/Group number** field.</span></span>
7. <span data-ttu-id="04184-125">A megfelelő mezőkben válassza ki a pénzügyi lízing fő számláját és az operatív lízing fő számláját.</span><span class="sxs-lookup"><span data-stu-id="04184-125">In the appropriate fields, select the finance lease main account and the operating lease main account.</span></span>

<span data-ttu-id="04184-126">Miután elvégezte ezeket a lépéseket, hozzáadhatja a költségeket a kijelölt **Lízing részletei** lapján található **Működési költségek fizetési ütemezése** sorokon keresztül.</span><span class="sxs-lookup"><span data-stu-id="04184-126">When you've completed these steps, you can add expenses through the **Executory costs payment schedule** lines on the **Lease details** page of a selected lease.</span></span> <span data-ttu-id="04184-127">Új lízing létrehozásakor költségeket is hozzáadhat.</span><span class="sxs-lookup"><span data-stu-id="04184-127">Alternatively, you can add expenses when you create a new lease.</span></span>
