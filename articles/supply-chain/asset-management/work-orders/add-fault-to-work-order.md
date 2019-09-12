---
title: Hiba hozzáadása munkarendeléshez
description: Ez a témakör azt mutatja be, hogyan lehet az Eszközkezelésben a munkarendelésekhez hibás regisztrációkat hozzáadni.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7c86973ca44d9113d14e180e27cc51343da5d2c0
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875698"
---
# <a name="add-fault-to-work-order"></a><span data-ttu-id="c5e4f-103">Hiba hozzáadása munkarendeléshez</span><span class="sxs-lookup"><span data-stu-id="c5e4f-103">Add fault to work order</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="c5e4f-104">A lekérdezéstervezőben megadott hibák a munkarendeléshez adhatók hozzá.</span><span class="sxs-lookup"><span data-stu-id="c5e4f-104">You can add faults set up in the fault designer to a work order.</span></span> <span data-ttu-id="c5e4f-105">A munkarendelésen kiválasztott eszköznek tartalmaznia kell egy vagy több hibarekorddal rendelkező eszköztípust.</span><span class="sxs-lookup"><span data-stu-id="c5e4f-105">The asset selected in the work order must contain asset types that have one or more fault records connected to it.</span></span> <span data-ttu-id="c5e4f-106">További tájékoztatás a beállításról a [Hibakezelés](../setup-for-work-orders/fault-management.md) részben.</span><span class="sxs-lookup"><span data-stu-id="c5e4f-106">Read more about setup in the [Fault management](../setup-for-work-orders/fault-management.md) section.</span></span>

1. <span data-ttu-id="c5e4f-107">Kattintson az **Eszközkezelés** > **Közös** > **Munkarendelések** > **Összes munkarendelés** vagy **Aktív munkarendelések** elemre.</span><span class="sxs-lookup"><span data-stu-id="c5e4f-107">Click **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="c5e4f-108">A listáról válassza ki azt a munkarendelést, amelynél hibaregisztrációt kíván végezni, majd kattintson az **Eszközhiba** elemre.</span><span class="sxs-lookup"><span data-stu-id="c5e4f-108">In the list, select the work order on which you want to make a fault registration and click **Asset fault**.</span></span>

3. <span data-ttu-id="c5e4f-109">A **Tünetek** gyorslapon kattintson a **Sor hozzáadása** parancsra.</span><span class="sxs-lookup"><span data-stu-id="c5e4f-109">On the **Symptoms** FastTab, click **Add line**.</span></span> <span data-ttu-id="c5e4f-110">A **Hiba** mezőben a sorrendben következő hibaszám automatikusan bekerül.</span><span class="sxs-lookup"><span data-stu-id="c5e4f-110">A sequential fault number is automatically inserted in the **Fault** field.</span></span>

4. <span data-ttu-id="c5e4f-111">Válassza ki a megfelelő tünetet a **Hibatünet** mezőben.</span><span class="sxs-lookup"><span data-stu-id="c5e4f-111">Select the relevant symptom in the **Fault symptom** field.</span></span>

5. <span data-ttu-id="c5e4f-112">Válassza ki a **Hibaterületet** és a **Hiba típusát**.</span><span class="sxs-lookup"><span data-stu-id="c5e4f-112">Select **Fault area** and **Fault type**.</span></span>

6. <span data-ttu-id="c5e4f-113">A **Hibadátum** mezőbe automatikusan az aktuális dátum kerül.</span><span class="sxs-lookup"><span data-stu-id="c5e4f-113">In the **Fault date** field, the current date is automatically inserted.</span></span> <span data-ttu-id="c5e4f-114">Szükség esetén másik dátumot is kiválaszthat.</span><span class="sxs-lookup"><span data-stu-id="c5e4f-114">You can select another date, if necessary.</span></span>

7. <span data-ttu-id="c5e4f-115">A **Kiválasztott tünet oka** gyorslapon adja hozzá a probléma okát leíró sort.</span><span class="sxs-lookup"><span data-stu-id="c5e4f-115">On the **Causes for selected symptom** FastTab, add a line describing the cause of the problem.</span></span>

8. <span data-ttu-id="c5e4f-116">A **Kiválasztott tünet orvoslása** gyorslapon adja hozzá a probléma lehetséges megoldását leíró sort.</span><span class="sxs-lookup"><span data-stu-id="c5e4f-116">On the **Remedies for selected symptom** FastTab, add a line describing a possible solution to the problem.</span></span>

9. <span data-ttu-id="c5e4f-117">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="c5e4f-117">Click **Save**.</span></span>

![1. ábra](media/19-work-orders.png)


## <a name="view-asset-faults"></a><span data-ttu-id="c5e4f-119">Eszközhibák megtekintése</span><span class="sxs-lookup"><span data-stu-id="c5e4f-119">View asset faults</span></span>

<span data-ttu-id="c5e4f-120">Az **Eszközhibák** listán áttekintést kaphat az összes eszközön regisztrált hibáról.</span><span class="sxs-lookup"><span data-stu-id="c5e4f-120">In the **Asset faults** list, you can get an overview of all faults registered on assets.</span></span>

<span data-ttu-id="c5e4f-121">Kattintson az **Eszközkezelés** > **Lekérdezések** > **Eszközhiba** > **Eszközhibák** elemre.</span><span class="sxs-lookup"><span data-stu-id="c5e4f-121">Click **Asset management** > **Inquiries** > **Asset fault** > **Asset faults** to open the list.</span></span>


## <a name="print-asset-fault-report"></a><span data-ttu-id="c5e4f-122">Eszközhiba-jelentés nyomtatása</span><span class="sxs-lookup"><span data-stu-id="c5e4f-122">Print asset fault report</span></span>

<span data-ttu-id="c5e4f-123">Az **Összes eszköz** listája lapon kinyomtathat egy eszközhiba-jelentést, amely minden hibaregisztrációt megjelenít, valamint a hibák statisztikáinak grafikus áttekintését is.</span><span class="sxs-lookup"><span data-stu-id="c5e4f-123">From the **All assets** list page, you can print an asset fault report displaying all fault registrations as well as a graphic overview of fault statistics.</span></span>

1. <span data-ttu-id="c5e4f-124">Kattintson az **Eszközkezelés** > **Általános** > **Eszközök** > **Összes eszköz** elemre.</span><span class="sxs-lookup"><span data-stu-id="c5e4f-124">Click **Asset management** > **Common** > **Assets** > **All assets**.</span></span>

2. <span data-ttu-id="c5e4f-125">Az **Eszközök** listáról válassza ki azt az eszközt, amelyhez hibajelentés szeretne nyomtatni.</span><span class="sxs-lookup"><span data-stu-id="c5e4f-125">In the **Assets** list, select the asset for which you want to print a fault report.</span></span>

3. <span data-ttu-id="c5e4f-126">Kattintson az **Általános** lap > **Jelentések szakasz** **Eszközhiba** elemére.</span><span class="sxs-lookup"><span data-stu-id="c5e4f-126">On the **General** tab > **Reports section**, click **Asset fault**.</span></span>

4. <span data-ttu-id="c5e4f-127">Egy adott időszak beszúrása vagy a hiba típusának kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="c5e4f-127">Insert a specific period, or select a fault type.</span></span>

5. <span data-ttu-id="c5e4f-128">A jelentés nyomtatásához kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="c5e4f-128">Click **OK** to print the report.</span></span>

>[!NOTE]
><span data-ttu-id="c5e4f-129">Számos eszközre vagy eszköztípusra vonatkozó hibajelentést is ki lehet nyomtatni úgy, hogy ide kattint: **Eszközkezelés** > **Jelentések** > **Eszközök** > **Eszközhiba**.</span><span class="sxs-lookup"><span data-stu-id="c5e4f-129">You can also print a fault report for several assets or asset types by clicking **Asset management** > **Reports** > **Assets** > **Asset fault**.</span></span>

