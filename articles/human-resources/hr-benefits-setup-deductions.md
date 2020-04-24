---
title: Levonások konfigurálása
description: A Microsoft Dynamics 365 Human Resources rendszerben levonásokat használhat annak meghatározására, hogy mennyit kell levonni (ha kell) az alkalmazottak fizetéséből az egyes juttatások esetében.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 5e645c3f098163626cb686aba347897781d7ebc0
ms.sourcegitcommit: a9461650d11d6845e1942865ebf7e35f75f61ad3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/06/2020
ms.locfileid: "3230062"
---
# <a name="configure-deductions"></a><span data-ttu-id="7ef93-103">Levonások konfigurálása</span><span class="sxs-lookup"><span data-stu-id="7ef93-103">Configure deductions</span></span>

<span data-ttu-id="7ef93-104">A Microsoft Dynamics 365 Human Resources rendszerben levonásokat használhat annak meghatározására, hogy mennyit kell levonni (ha kell) az alkalmazottak fizetéséből az egyes juttatások esetében.</span><span class="sxs-lookup"><span data-stu-id="7ef93-104">Use deductions in Microsoft Dynamics 365 Human Resources to determine how much, if any, to deduct from an employee’s paycheck for each benefit.</span></span> <span data-ttu-id="7ef93-105">A levonásokhoz érvényességi dátum tartozik, így megőrizheti a levonási adatok előzményeinek nyilvántartását.</span><span class="sxs-lookup"><span data-stu-id="7ef93-105">Deductions are date-effective, so you can keep a historical record of deduction information.</span></span> 

1. <span data-ttu-id="7ef93-106">A **Juttatások kezelése** munkaterület **Beállítás** részén válassza a **Levonások** elemet.</span><span class="sxs-lookup"><span data-stu-id="7ef93-106">In the **Benefits management** workspace, under **Setup**, select **Deductions**.</span></span>

2. <span data-ttu-id="7ef93-107">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7ef93-107">Select **New**.</span></span>

3. <span data-ttu-id="7ef93-108">Adjon meg értékeket a következő mezőkben:</span><span class="sxs-lookup"><span data-stu-id="7ef93-108">Specify values for the following fields:</span></span>

   | <span data-ttu-id="7ef93-109">Mező</span><span class="sxs-lookup"><span data-stu-id="7ef93-109">Field</span></span> | <span data-ttu-id="7ef93-110">Leírás</span><span class="sxs-lookup"><span data-stu-id="7ef93-110">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="7ef93-111">**Levonás**</span><span class="sxs-lookup"><span data-stu-id="7ef93-111">**Deduction**</span></span> | <span data-ttu-id="7ef93-112">Egyedi azonosító, amely a juttatási levonás azonosítására szolgál.</span><span class="sxs-lookup"><span data-stu-id="7ef93-112">A unique ID that is used to identify the benefit deduction.</span></span> |
   | <span data-ttu-id="7ef93-113">**Leírás**</span><span class="sxs-lookup"><span data-stu-id="7ef93-113">**Description**</span></span> | <span data-ttu-id="7ef93-114">A levonás leírása.</span><span class="sxs-lookup"><span data-stu-id="7ef93-114">A description for the deduction.</span></span> |
   | <span data-ttu-id="7ef93-115">**Hatályos**</span><span class="sxs-lookup"><span data-stu-id="7ef93-115">**Effective**</span></span> | <span data-ttu-id="7ef93-116">A kezdő dátum.</span><span class="sxs-lookup"><span data-stu-id="7ef93-116">The start date.</span></span> <span data-ttu-id="7ef93-117">Az alapértelmezett érték az aktuális rendszerdátum.</span><span class="sxs-lookup"><span data-stu-id="7ef93-117">The default value is the current system date.</span></span> |
   | <span data-ttu-id="7ef93-118">**Lejárat**</span><span class="sxs-lookup"><span data-stu-id="7ef93-118">**Expiration**</span></span> | <span data-ttu-id="7ef93-119">A záró dátum.</span><span class="sxs-lookup"><span data-stu-id="7ef93-119">The end date.</span></span> <span data-ttu-id="7ef93-120">Az alapértelmezett érték a 2154. 12. 31., ami a „soha” megfelelője.</span><span class="sxs-lookup"><span data-stu-id="7ef93-120">The default value is 12/31/2154, which signifies never.</span></span> |
   | <span data-ttu-id="7ef93-121">**Címsor**</span><span class="sxs-lookup"><span data-stu-id="7ef93-121">**Heading**</span></span> | <span data-ttu-id="7ef93-122">A címsorkód abból a bérszámfejtő rendszerből, amelyet ez a levonás fog használni a levonás alkalmazotti részéhez a juttatások bérszámfejtési feldolgozásakor.</span><span class="sxs-lookup"><span data-stu-id="7ef93-122">The heading code from the payroll system that this deduction will use for the employee portion of the deduction when processing the benefits to payroll.</span></span> <span data-ttu-id="7ef93-123">Ezt akkor alkalmazza a rendszer, amikor külső bérszámfejtő szolgáltatót használ.</span><span class="sxs-lookup"><span data-stu-id="7ef93-123">This is used when you use a third-party payroll provider.</span></span> |
   | <span data-ttu-id="7ef93-124">**Alkalmazotti bérlistalevonási referencia**</span><span class="sxs-lookup"><span data-stu-id="7ef93-124">**Employee payroll deduction reference**</span></span> | <span data-ttu-id="7ef93-125">A bérlistarendszerből származó levonási kód, amelyet ez a levonás alkalmazotti részéhez használ a juttatások bérlistában való feldolgozása során.</span><span class="sxs-lookup"><span data-stu-id="7ef93-125">The deduction code from the payroll system that this deduction will use for the employee portion of the deduction when processing the benefits to payroll.</span></span> |
   | <span data-ttu-id="7ef93-126">**Összeg címsora**</span><span class="sxs-lookup"><span data-stu-id="7ef93-126">**Amount heading**</span></span> | <span data-ttu-id="7ef93-127">A címsorkód abból a bérszámfejtő rendszerből, amelyet ez a levonási összeg fog használni a levonás alkalmazotti részéhez a juttatások bérszámfejtési feldolgozásakor.</span><span class="sxs-lookup"><span data-stu-id="7ef93-127">The heading code from the payroll system that this deduction amount will use for the employee portion of the deduction when processing the benefits to payroll.</span></span> <span data-ttu-id="7ef93-128">Ezt általában akkor alkalmazza a rendszer, amikor külső bérszámfejtő szolgáltatót használ.</span><span class="sxs-lookup"><span data-stu-id="7ef93-128">This is normally used when you use a third-party payroll provider.</span></span> |
   | <span data-ttu-id="7ef93-129">**Törölhető**</span><span class="sxs-lookup"><span data-stu-id="7ef93-129">**Can delete**</span></span> | <span data-ttu-id="7ef93-130">Megadja, hogy a Dynamics 365 for Finance and Operations alkalmazásból exportált érték okozhatja-e az érték törlését a bérszámfejtő rendszerben.</span><span class="sxs-lookup"><span data-stu-id="7ef93-130">Specifies whether an exported value from Dynamics 365 for Finance and Operations can cause the value to be deleted in the payroll system.</span></span> |
   | <span data-ttu-id="7ef93-131">**Párba állított oszlopok**</span><span class="sxs-lookup"><span data-stu-id="7ef93-131">**Paired columns**</span></span> | <span data-ttu-id="7ef93-132">Megadja, hogy az exportálási címsor és a levonási összeg szomszédos oszlopokban, párosítva lesz-e exportálva a bérszámfejtő rendszerbe.</span><span class="sxs-lookup"><span data-stu-id="7ef93-132">Specifies whether to export heading and deduction amount in paired adjacent columns to the payroll system.</span></span> |
   | <span data-ttu-id="7ef93-133">**Módosítás érvénybe lépési dátuma**</span><span class="sxs-lookup"><span data-stu-id="7ef93-133">**Change effective date**</span></span> | <span data-ttu-id="7ef93-134">Az a dátum, amikor a juttatás levonásának módosítása érvénybe lép.</span><span class="sxs-lookup"><span data-stu-id="7ef93-134">The date when the benefit deduction change will become effective.</span></span> <span data-ttu-id="7ef93-135">Ezen a dátumon a rendszer automatikusan megváltoztatja a juttatás levonását, és frissíti az ehhez a levonáshoz kapcsolódó összes juttatási konstrukciót, amikor futtatja a **Levonás módosításának frissítése** feldolgozást.</span><span class="sxs-lookup"><span data-stu-id="7ef93-135">On this date, the system automatically changes the benefit deduction and updates all benefit plans associated with this deduction, as long as you run **Deduction change update** processing.</span></span> |
   | <span data-ttu-id="7ef93-136">**Levonás módosítása befejeződött**</span><span class="sxs-lookup"><span data-stu-id="7ef93-136">**Deduction change completed**</span></span> | <span data-ttu-id="7ef93-137">A rendszer automatikusan bejelöli a **Levonás módosítása befejeződött** jelölőnégyzetet, amikor a levonásfrissítési módosítás feldolgozása végrehajtotta a juttatáslevonási módosításokat.</span><span class="sxs-lookup"><span data-stu-id="7ef93-137">The **Deduction change completed** check box will be automatically selected once the benefit deduction changes have been completed by Deduction update change processing.</span></span> |
   
4. <span data-ttu-id="7ef93-138">A juttatásimérték-beállítások változásainak követéséhez és karbantartásához válassza a **Műveletek**, majd a **Verziók karbantartása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7ef93-138">To track and maintain changes to the benefit rate setup, select **Actions**, and then select **Maintain versions**.</span></span>

5. <span data-ttu-id="7ef93-139">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7ef93-139">Select **Save**.</span></span> 
