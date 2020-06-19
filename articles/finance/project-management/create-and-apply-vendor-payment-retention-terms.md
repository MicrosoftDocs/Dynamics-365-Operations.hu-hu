---
title: Szállítói kifizetések visszatartási feltételeinek létrehozása és alkalmazása
description: Ez a témakör a szállítói kifizetések visszatartási feltételeinek beállításával és karbantartásával kapcsolatban tartalmaz tájékoztatást.
author: kfend
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 0e14050a79220b5d02763a025040edb934489d00
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410229"
---
# <a name="create-and-apply-vendor-payment-retention-terms"></a><span data-ttu-id="5e466-103">Szállítói kifizetések visszatartási feltételeinek létrehozása és alkalmazása</span><span class="sxs-lookup"><span data-stu-id="5e466-103">Create and apply vendor payment retention terms</span></span>

[!include [banner](../includes/banner.md)] 

<span data-ttu-id="5e466-104">Szállítói fizetés-visszatartási feltételek beállítása egy projekthez akkor hasznos, ha a szervezet vissza szeretné tartani a szállítónak teljesített kifizetések egy részét.</span><span class="sxs-lookup"><span data-stu-id="5e466-104">Setting up vendor payment retention terms for a project is useful when your organization wants to retain part of the payments made to a vendor.</span></span> <span data-ttu-id="5e466-105">Például, ha a kifizetést egy szállítónál vissza szeretné tartani, addig, amíg a szállított termékek megfelelnek az elvárásainak.</span><span class="sxs-lookup"><span data-stu-id="5e466-105">For example, when you want to hold payment to a vendor until the products delivered meet your expectations.</span></span> <span data-ttu-id="5e466-106">A szállítóval való egyeztetés során meghatározhatja a szállító kifizetésének visszatartási feltételeit.</span><span class="sxs-lookup"><span data-stu-id="5e466-106">Vendor payment retention terms can be specified when you negotiate a vendor contract.</span></span>

## <a name="create-vendor-payment-retention-terms"></a><span data-ttu-id="5e466-107">Szállító fizetés-visszatartási feltételek létrehozása</span><span class="sxs-lookup"><span data-stu-id="5e466-107">Create vendor payment retention terms</span></span>

<span data-ttu-id="5e466-108">Megadhatja a szállítói kifizetés visszatartani kívánt részének százalékos arányát, illetve a korábban visszatartott összegek feloldani kívánt százalékát is.</span><span class="sxs-lookup"><span data-stu-id="5e466-108">You can enter the percentage of vendor payment for retention and the percentage of the previously retained amounts to be released.</span></span> <span data-ttu-id="5e466-109">Az érintett összegeket a rendszer automatikusan visszatartja a szállítói számlákon, amíg a szerződés eléri a megadott teljesítési szakaszt.</span><span class="sxs-lookup"><span data-stu-id="5e466-109">Amounts are automatically retained on vendor invoices until the contract reaches the specified state of completion.</span></span> <span data-ttu-id="5e466-110">Miután visszatartási feltételeket állított be, azokat bármely projektre alkalmazhatja, amely az adott szállítóhoz tartozik.</span><span class="sxs-lookup"><span data-stu-id="5e466-110">After you set up the retention terms, you can apply them to any project for that vendor.</span></span>

<span data-ttu-id="5e466-111">A szállítói kifizetések visszatartási feltételeinek beállítását és karbantartását az alábbi lépésekkel végezheti el.</span><span class="sxs-lookup"><span data-stu-id="5e466-111">Use the following steps to set up and maintain retention terms for vendor payments.</span></span> 

1. <span data-ttu-id="5e466-112">Nyissa meg a **Projektvezetés és könyvelés** > **Visszatartás** > **Szállító fizetés-visszatartási feltételei** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5e466-112">Go to **Project management and accounting** > **Retention** > **Vendor payment retention terms**.</span></span>
2. <span data-ttu-id="5e466-113">Új szállítói visszatartási feltétel hozzáadásához válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5e466-113">Select **New** to add a new vendor retention term.</span></span> <span data-ttu-id="5e466-114">Az új feltétel **Szabály azonosítója** értéke automatikusan megjelenik a mezőben.</span><span class="sxs-lookup"><span data-stu-id="5e466-114">The **Rule ID** value for the new term is automatically entered.</span></span> 
3. <span data-ttu-id="5e466-115">Írjon be egy rövid leírást a **Leírás** mezőbe, majd a **Feltételek** gyorslapon válassza a **Sor hozzáadása** parancsot a következő feltétel-értékek megadásához:</span><span class="sxs-lookup"><span data-stu-id="5e466-115">Enter a brief description in the **Description** field, and on the **Terms** FastTab, select **Add line** to enter term values for the following:</span></span>

   - <span data-ttu-id="5e466-116">**Szállított cikkek százaléka**: Adja meg a feltételhez tartozó teljesítési százalékot.</span><span class="sxs-lookup"><span data-stu-id="5e466-116">**Percentage of units delivered**: Enter a percentage of completion for the term.</span></span> <span data-ttu-id="5e466-117">A rendszer automatikusan visszatartja a megfelelő összegeket a szállítói számlákon egészen addig, amíg a projekt teljesítési aránya el nem éri a megadott százalékos értéket.</span><span class="sxs-lookup"><span data-stu-id="5e466-117">Amounts are automatically retained on vendor invoices until the project stage of completion is equal to the specified percentage.</span></span> <span data-ttu-id="5e466-118">Ha például az 50,00 értéket adja meg, a rendszer a projekt 50%-ának teljesítéséig visszatartja a kifizetendő összegeket.</span><span class="sxs-lookup"><span data-stu-id="5e466-118">For example, if you enter 50.00, amounts are retained until the project is 50 percent completed.</span></span>
   - <span data-ttu-id="5e466-119">A **Visszatartandó százalék** Adja meg a szállítói számla visszatartandó összegének százalékos arányát.</span><span class="sxs-lookup"><span data-stu-id="5e466-119">**Percentage to retain**: Enter a percentage of the vendor invoice amount to be retained.</span></span> <span data-ttu-id="5e466-120">Ha például a 10,00 értéket adja meg a mezőben, a rendszer a szállítói számlán szereplő összeg 10 százalékát tartja vissza addig, amíg a projekt el nem éri a **Szállított cikkek százaléka** mezőben megadott teljesítési százalékot.</span><span class="sxs-lookup"><span data-stu-id="5e466-120">For example, if you enter 10.00, then 10 percent of the amount on a vendor invoice is retained until the project reaches the percentage of completion as set in the **Percentage of units delivered field**.</span></span>
   - <span data-ttu-id="5e466-121">**Felszabadítandó százalék** Válassza a **Sor hozzáadása** lehetőséget a százalékos érték megadásához, amelyet a korábban visszatartott összegekből fel kíván szabadítani a projekt teljesítésének kiválasztott szintjén.</span><span class="sxs-lookup"><span data-stu-id="5e466-121">**Percentage to release**: Select **Add line** to enter a percentage of any previously retained amounts to be released for the selected level of project completion.</span></span>

> [!NOTE]
> <span data-ttu-id="5e466-122">Ha több mérföldkő van meghatározva a projekt teljesítésének különböző szintjeihez, minden egyes visszatartási szabályhoz külön szállítói visszatartási feltételsort adjon meg.</span><span class="sxs-lookup"><span data-stu-id="5e466-122">If you have more than one milestone for different levels of project completion, enter a separate vendor retention term line for each retention rule.</span></span> <span data-ttu-id="5e466-123">Minden sorban különböző százalékos értéket adhat meg a visszatartandó és a felszabadítandó százalékokhoz a projekt teljesítésének minden egyes szintjén.</span><span class="sxs-lookup"><span data-stu-id="5e466-123">Each line can specify a different retention percentage and a different release percentage for each designated level of project completion.</span></span>

<span data-ttu-id="5e466-124">Miután szállítói visszatartási feltételeket állított be, a feltételeket alkalmazhatja egy projektre.</span><span class="sxs-lookup"><span data-stu-id="5e466-124">After you create vendor retention terms for a vendor, you can apply the terms to a project.</span></span>

## <a name="apply-vendor-retention-terms-to-a-project"></a><span data-ttu-id="5e466-125">Szállítói visszatartási feltételek alkalmazása egy projektre</span><span class="sxs-lookup"><span data-stu-id="5e466-125">Apply vendor retention terms to a project</span></span>

1. <span data-ttu-id="5e466-126">Nyissa meg a **Projektvezetés és könyvelés** > **Projektek** > **Összes projekt** lehetőséget majd nyissa meg a projektet a projektek listaoldaláról.</span><span class="sxs-lookup"><span data-stu-id="5e466-126">Go to **Project management and accounting** > **Projects** > **All projects** and open a project from the project list page.</span></span>
2. <span data-ttu-id="5e466-127">A **Szállítói megállapodások** gyorslapon válassza a **Sor hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5e466-127">On the **Vendor agreements** FastTab, select **Add line**.</span></span>
3. <span data-ttu-id="5e466-128">A **Számlakód mezőben** válasszon egyet a következő lehetőségek közül:</span><span class="sxs-lookup"><span data-stu-id="5e466-128">In the **Account code field**, select one of the following options:</span></span> 

   - <span data-ttu-id="5e466-129">**Tábla**: – A szállítói visszatartási feltételek egyetlen szállítóra vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="5e466-129">**Table**: The vendor retention terms apply to a single vendor.</span></span>
   - <span data-ttu-id="5e466-130">**Csoport**: – A szállítói visszatartási feltételek egy adott szállítócsoport összes szállítójára vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="5e466-130">**Group**: The vendor retention terms apply to all vendors in a vendor group.</span></span>
   - <span data-ttu-id="5e466-131">**Mind**: – A szállítói visszatartási szabályok az összes szállítóra vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="5e466-131">**All**: The vendor retention terms apply to all vendors.</span></span>

4. <span data-ttu-id="5e466-132">A **Szállító/szállítói csoport mezőben** jelölje ki azt a szállítót vagy szállítócsoportot, amelyre a szállítói visszatartási feltételek vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="5e466-132">In the **Vendor/Vendor group field**, select the vendor or vendor group to which the vendor retention terms apply.</span></span> <span data-ttu-id="5e466-133">Ha az előző lépésben a **Mind** lehetőséget választotta, ez a mező nem érhető el.</span><span class="sxs-lookup"><span data-stu-id="5e466-133">If you selected **All** in the previous step, this field is unavailable.</span></span>
5. <span data-ttu-id="5e466-134">A **Szállítói visszatartási feltételek** mezőben válasszon egyet az előző eljárás során létrehozott visszatartási feltételek közül.</span><span class="sxs-lookup"><span data-stu-id="5e466-134">In the **Vendor retention terms** field, select the retention terms that you created in the previous procedure.</span></span>
6. <span data-ttu-id="5e466-135">Ha a projektben „saját fizetés beérkezésekor fizetendő” (pay-when-paid; PWP) feltételek is be vannak állítva a szállítóhoz, a **PWP-küszöbérték százaléka** mezőben adja meg a kívánt küszöbérték-százalékot a projekthez.</span><span class="sxs-lookup"><span data-stu-id="5e466-135">If the project also has pay-when-paid (PWP) terms set up for the vendor, enter the threshold percentage for the project in the **PWP threshold percentage** field.</span></span>

<span data-ttu-id="5e466-136">A szállítói visszatartási szabályok a szállító számára létrehozott beszerzési rendeléseken is megjelennek.</span><span class="sxs-lookup"><span data-stu-id="5e466-136">The vendor retention terms are also displayed on purchase orders that you create for the vendor.</span></span>
