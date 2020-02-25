---
title: Levonások konfigurálása
description: ''
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
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
ms.openlocfilehash: 7ee9e8f3bc0e9027e41d3aa91bd097a3f046cbb4
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009300"
---
# <a name="configure-deductions"></a><span data-ttu-id="b82fb-102">Levonások konfigurálása</span><span class="sxs-lookup"><span data-stu-id="b82fb-102">Configure deductions</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="b82fb-103">A Microsoft Dynamics 365 Human Resources rendszerben levonásokat használhat annak meghatározására, hogy mennyit kell levonni (ha kell) az alkalmazottak fizetéséből az egyes juttatások esetében.</span><span class="sxs-lookup"><span data-stu-id="b82fb-103">Use deductions in Microsoft Dynamics 365 Human Resources to determine how much, if any, to deduct from an employee’s paycheck for each benefit.</span></span> <span data-ttu-id="b82fb-104">A levonásokhoz érvényességi dátum tartozik, így megőrizheti a levonási adatok előzményeinek nyilvántartását.</span><span class="sxs-lookup"><span data-stu-id="b82fb-104">Deductions are date effective, so you can keep a historical record of deduction information.</span></span> 

1. <span data-ttu-id="b82fb-105">A **Juttatások kezelése** munkaterület **Beállítás** részén válassza a **Levonások** elemet.</span><span class="sxs-lookup"><span data-stu-id="b82fb-105">In the **Benefits management** workspace, under **Setup**, select **Deductions**.</span></span>

2. <span data-ttu-id="b82fb-106">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b82fb-106">Select **New**.</span></span>

3. <span data-ttu-id="b82fb-107">Adjon meg értékeket a következő mezőkben:</span><span class="sxs-lookup"><span data-stu-id="b82fb-107">Specify values for the following fields:</span></span>

   | <span data-ttu-id="b82fb-108">Mező</span><span class="sxs-lookup"><span data-stu-id="b82fb-108">Field</span></span> | <span data-ttu-id="b82fb-109">Leírás</span><span class="sxs-lookup"><span data-stu-id="b82fb-109">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="b82fb-110">Levonás</span><span class="sxs-lookup"><span data-stu-id="b82fb-110">Deduction</span></span> | <span data-ttu-id="b82fb-111">Egyedi azonosító, amely a juttatási levonás azonosítására szolgál.</span><span class="sxs-lookup"><span data-stu-id="b82fb-111">A unique ID that is used to identify the benefit deduction.</span></span> |
   | <span data-ttu-id="b82fb-112">Leírás</span><span class="sxs-lookup"><span data-stu-id="b82fb-112">Description</span></span> | <span data-ttu-id="b82fb-113">A levonás leírása.</span><span class="sxs-lookup"><span data-stu-id="b82fb-113">A description for the deduction.</span></span> |
   | <span data-ttu-id="b82fb-114">Hatályos</span><span class="sxs-lookup"><span data-stu-id="b82fb-114">Effective</span></span> | <span data-ttu-id="b82fb-115">A kezdő dátum.</span><span class="sxs-lookup"><span data-stu-id="b82fb-115">The start date.</span></span> <span data-ttu-id="b82fb-116">Az alapértelmezett érték az aktuális rendszerdátum.</span><span class="sxs-lookup"><span data-stu-id="b82fb-116">The default value is the current system date.</span></span> |
   | <span data-ttu-id="b82fb-117">Lejárat</span><span class="sxs-lookup"><span data-stu-id="b82fb-117">Expiration</span></span> | <span data-ttu-id="b82fb-118">A záró dátum.</span><span class="sxs-lookup"><span data-stu-id="b82fb-118">The end date.</span></span> <span data-ttu-id="b82fb-119">Az alapértelmezett érték a 2154. 12. 31., ami a „soha” megfelelője.</span><span class="sxs-lookup"><span data-stu-id="b82fb-119">The default value is 12/31/2154, which signifies never.</span></span> |
   | <span data-ttu-id="b82fb-120">Címsor</span><span class="sxs-lookup"><span data-stu-id="b82fb-120">Heading</span></span> | <span data-ttu-id="b82fb-121">A címsorkód abból a bérszámfejtő rendszerből, amelyet ez a levonás fog használni a levonás alkalmazotti részéhez a juttatások bérszámfejtési feldolgozásakor.</span><span class="sxs-lookup"><span data-stu-id="b82fb-121">The heading code from the payroll system that this deduction will use for the employee portion of the deduction when processing the benefits to payroll.</span></span> <span data-ttu-id="b82fb-122">Ezt akkor alkalmazza a rendszer, amikor külső bérszámfejtő szolgáltatót használ.</span><span class="sxs-lookup"><span data-stu-id="b82fb-122">This is used when you use a third party payroll provider.</span></span> |
   | <span data-ttu-id="b82fb-123">Alkalmazotti bérlistalevonási referencia</span><span class="sxs-lookup"><span data-stu-id="b82fb-123">Employee payroll deduction reference</span></span> | <span data-ttu-id="b82fb-124">A bérlistarendszerből származó levonási kód, amelyet ez a levonás alkalmazotti részéhez használ a juttatások bérlistában való feldolgozása során.</span><span class="sxs-lookup"><span data-stu-id="b82fb-124">The deduction code from the payroll system that this deduction will use for the employee portion of the deduction when processing the benefits to payroll.</span></span> |
   | <span data-ttu-id="b82fb-125">Összeg címsora</span><span class="sxs-lookup"><span data-stu-id="b82fb-125">Amount heading</span></span> | <span data-ttu-id="b82fb-126">A címsorkód abból a bérszámfejtő rendszerből, amelyet ez a levonási összeg fog használni a levonás alkalmazotti részéhez a juttatások bérszámfejtési feldolgozásakor.</span><span class="sxs-lookup"><span data-stu-id="b82fb-126">The heading code from the payroll system that this deduction amount will use for the employee portion of the deduction when processing the benefits to payroll.</span></span> <span data-ttu-id="b82fb-127">Ezt általában akkor alkalmazza a rendszer, amikor külső bérszámfejtő szolgáltatót használ.</span><span class="sxs-lookup"><span data-stu-id="b82fb-127">This is normally used when you use a third party payroll provider.</span></span> |
   | <span data-ttu-id="b82fb-128">Törölhető</span><span class="sxs-lookup"><span data-stu-id="b82fb-128">Can delete</span></span> | <span data-ttu-id="b82fb-129">Megadja, hogy a Dynamics 365 for Finance and Operations alkalmazásból exportált érték okozhatja-e az érték törlését a bérszámfejtő rendszerben.</span><span class="sxs-lookup"><span data-stu-id="b82fb-129">Specifies whether an exported value from Dynamics 365 for Finance and Operations can cause the value to be deleted in the payroll system.</span></span> |
   | <span data-ttu-id="b82fb-130">Párba állított oszlopok</span><span class="sxs-lookup"><span data-stu-id="b82fb-130">Paired columns</span></span> | <span data-ttu-id="b82fb-131">Megadja, hogy az exportálási címsor és a levonási összeg szomszédos oszlopokban, párosítva lesz-e exportálva a bérszámfejtő rendszerbe.</span><span class="sxs-lookup"><span data-stu-id="b82fb-131">Specifies whether to export heading and deduction amount in paired adjacent columns to the payroll system.</span></span> |
   | <span data-ttu-id="b82fb-132">Módosítás érvénybe lépési dátuma</span><span class="sxs-lookup"><span data-stu-id="b82fb-132">Change effective date</span></span> | <span data-ttu-id="b82fb-133">Az a dátum, amikor a juttatás levonásának módosítása érvénybe lép.</span><span class="sxs-lookup"><span data-stu-id="b82fb-133">The date when the benefit deduction change will become effective.</span></span> <span data-ttu-id="b82fb-134">Ezen a dátumon a rendszer automatikusan megváltoztatja a juttatás levonását, és frissíti az ehhez a levonáshoz kapcsolódó összes juttatási konstrukciót, amikor futtatja a levonás módosításának frissítési feldolgozását.</span><span class="sxs-lookup"><span data-stu-id="b82fb-134">On this date the system will automatically change the benefit deduction and update all benefit plans associated with this deduction, as long as you run Deduction change update processing.</span></span> |
   | <span data-ttu-id="b82fb-135">Levonás módosítása befejeződött</span><span class="sxs-lookup"><span data-stu-id="b82fb-135">Deduction change completed</span></span> | <span data-ttu-id="b82fb-136">A rendszer automatikusan bejelöli a Levonás módosítása befejeződött jelölőnégyzetet, amikor a levonásfrissítési módosítás feldolgozása végrehajtotta a juttatáslevonási módosításokat.</span><span class="sxs-lookup"><span data-stu-id="b82fb-136">The Deduction change completed check box will be automatically selected once the benefit deduction changes have been completed by Deduction update change processing.</span></span> |
   
4. <span data-ttu-id="b82fb-137">A juttatásimérték-beállítások változásainak követéséhez és karbantartásához válassza a **Műveletek**, majd a **Verziók karbantartása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b82fb-137">To track and maintain changes to the benefit rate setup, select **Actions**, and then select **Maintain versions**.</span></span>

5. <span data-ttu-id="b82fb-138">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b82fb-138">Select **Save**.</span></span> 
