---
title: Hiba hozzáadása munkarendeléshez
description: Ez a témakör azt mutatja be, hogyan lehet az Eszközkezelésben a munkarendelésekhez hibás regisztrációkat hozzáadni.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 083ceca9605ad044c172ba7aa23739d170f8c301
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/16/2021
ms.locfileid: "5019304"
---
# <a name="add-fault-to-work-order"></a><span data-ttu-id="f8b96-103">Hiba hozzáadása munkarendeléshez</span><span class="sxs-lookup"><span data-stu-id="f8b96-103">Add fault to work order</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="f8b96-104">A lekérdezéstervezőben megadott hibák a munkarendeléshez hozzáadhatók.</span><span class="sxs-lookup"><span data-stu-id="f8b96-104">You can add faults that were set up in the fault designer to a work order.</span></span> <span data-ttu-id="f8b96-105">A munkarendelésen kijelölt eszköznek tartalmaznia kell egy vagy több hibarekorddal rendelkező eszköztípust.</span><span class="sxs-lookup"><span data-stu-id="f8b96-105">One or more fault records must be connected to the asset types that are used for the asset that is selected in the work order.</span></span> <span data-ttu-id="f8b96-106">A szolgáltatásokról további tájékoztatásért lásd: [Hibakezelés](../setup-for-work-orders/fault-management.md).</span><span class="sxs-lookup"><span data-stu-id="f8b96-106">For more information about the setup, see [Fault management](../setup-for-work-orders/fault-management.md).</span></span>

1. <span data-ttu-id="f8b96-107">Válassza az **Eszközkezelés** > **Közös** > **Munkarendelések** > **Összes munkarendelés** vagy **Aktív munkarendelések** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f8b96-107">Select **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="f8b96-108">Válassza ki azt a munkarendelést, amelynek a hibaregisztrációját kívánja végezni, majd kattintson a művelet ablaktábla **Munkarendelés** lapján az **Eszköz** csoport **Eszközhiba** elemére.</span><span class="sxs-lookup"><span data-stu-id="f8b96-108">Select the work order to make a fault registration on, and then, on the Action Pane, on the **Work order** tab, in the **Asset** group, select **Asset fault**.</span></span>

3. <span data-ttu-id="f8b96-109">A **Tünetek** gyorslapon válassza a **Sor hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f8b96-109">On the **Symptoms** FastTab, select **Add line**.</span></span> <span data-ttu-id="f8b96-110">A **Hiba** mezőben a sorrendben következő hibaszám automatikusan bekerül.</span><span class="sxs-lookup"><span data-stu-id="f8b96-110">A sequential fault number is automatically entered in the **Fault** field.</span></span>

4. <span data-ttu-id="f8b96-111">A **Hibatünet** mezőben válassza ki a megfelelő tünetet.</span><span class="sxs-lookup"><span data-stu-id="f8b96-111">In the **Fault symptom** field, select the relevant symptom.</span></span>

5. <span data-ttu-id="f8b96-112">Válassza ki a megfelelő értékeket a **Hibaterület** és a **Hibatípus** mezőkben.</span><span class="sxs-lookup"><span data-stu-id="f8b96-112">In the **Fault area** and **Fault type** fields, select the appropriate values.</span></span>

6. <span data-ttu-id="f8b96-113">A **Hibadátum** mezőbe automatikusan az aktuális dátum kerül.</span><span class="sxs-lookup"><span data-stu-id="f8b96-113">In the **Fault date** field, the current date is automatically inserted.</span></span> <span data-ttu-id="f8b96-114">Igény esetén más dátumot is megadhat.</span><span class="sxs-lookup"><span data-stu-id="f8b96-114">You can select a different date as you require.</span></span>

7. <span data-ttu-id="f8b96-115">A **Kiválasztott tünet oka** gyorslapon adja hozzá a probléma okát leíró sort.</span><span class="sxs-lookup"><span data-stu-id="f8b96-115">On the **Causes for selected symptom** FastTab, add a line to describe the cause of the issue.</span></span>

8. <span data-ttu-id="f8b96-116">A **Kiválasztott tünet orvoslása** gyorslapon adja hozzá a probléma lehetséges megoldását leíró sort.</span><span class="sxs-lookup"><span data-stu-id="f8b96-116">On the **Remedies for selected symptom** FastTab, add a line to describe a possible solution to the issue.</span></span>

9. <span data-ttu-id="f8b96-117">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f8b96-117">Select **Save**.</span></span>

<span data-ttu-id="f8b96-118">A következő ábrán egy hibaregisztráció példája látható.</span><span class="sxs-lookup"><span data-stu-id="f8b96-118">The illustration below shows an example of a fault registration.</span></span>

![1. ábra](media/19-work-orders.png)


## <a name="view-asset-faults"></a><span data-ttu-id="f8b96-120">Eszközhibák megtekintése</span><span class="sxs-lookup"><span data-stu-id="f8b96-120">View asset faults</span></span>

<span data-ttu-id="f8b96-121">Az **Eszközhibák** listán áttekintést kaphat az összes eszközön regisztrált hibáról.</span><span class="sxs-lookup"><span data-stu-id="f8b96-121">In the **Asset faults** list, you can get an overview of all faults registered on assets.</span></span>

<span data-ttu-id="f8b96-122">Az **Eszközhibák** listaoldalon áttekintést kaphat az összes eszközön regisztrált hibáról.</span><span class="sxs-lookup"><span data-stu-id="f8b96-122">On the **Asset faults** list page, you can get an overview of all faults that have been registered on assets.</span></span> <span data-ttu-id="f8b96-123">A lap megnyitásához kattintson az **Eszközkezelés** > **Lekérdezések** > **Eszközhiba** > **Eszközhibák** elemre.</span><span class="sxs-lookup"><span data-stu-id="f8b96-123">To open the page, select **Asset management** > **Inquiries** > **Asset fault** > **Asset faults**.</span></span>


## <a name="print-asset-fault-report"></a><span data-ttu-id="f8b96-124">Eszközhiba-jelentés nyomtatása</span><span class="sxs-lookup"><span data-stu-id="f8b96-124">Print asset fault report</span></span>

<span data-ttu-id="f8b96-125">Az **Összes eszköz** listája lapon kinyomtathat egy eszközhiba-jelentést, amely minden hibaregisztrációt megjelenít, valamint a hibák statisztikáinak grafikus áttekintését is.</span><span class="sxs-lookup"><span data-stu-id="f8b96-125">From the **All assets** list page, you can print an asset fault report that shows all fault registrations and a graphical overview of fault statistics.</span></span>

1. <span data-ttu-id="f8b96-126">Válassza ki az **Eszközkezelés** > **Általános** > **Eszközök** > **Összes eszköz** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f8b96-126">Select **Asset management** > **Common** > **Assets** > **All assets**.</span></span>

2. <span data-ttu-id="f8b96-127">Jelölje ki az eszközt amelyhez hibajelentést szeretne nyomtatni.</span><span class="sxs-lookup"><span data-stu-id="f8b96-127">Select the asset to print a fault report for.</span></span>

3. <span data-ttu-id="f8b96-128">A Művelet ablaktábla **Általános** lapjának **Jelentések** csoportjában válassza az **Eszközhiba** elemet.</span><span class="sxs-lookup"><span data-stu-id="f8b96-128">On the Action Pane, on the **General** tab, in the **Reports** group, select **Asset fault**.</span></span>

4. <span data-ttu-id="f8b96-129">Egy adott időszak megadása vagy a hiba típusának kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="f8b96-129">Enter a specific period, or select a fault type.</span></span>

5. <span data-ttu-id="f8b96-130">A jelentés nyomtatásához válassza az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f8b96-130">Select **OK** to print the report.</span></span>

>[!NOTE]
><span data-ttu-id="f8b96-131">Számos eszközre vagy eszköztípusra vonatkozó hibajelentést is kinyomtathat úgy, hogy ezt választja: **Eszközkezelés** > **Jelentések** > **Eszközök** > **Eszközhiba**.</span><span class="sxs-lookup"><span data-stu-id="f8b96-131">To print a fault report for several assets or asset types, select **Asset management** > **Reports** > **Assets** > **Asset fault**.</span></span>

