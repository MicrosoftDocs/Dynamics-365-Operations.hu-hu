---
title: Felhasználási jelentések létrehozása
description: Ez a témakör azt mutatja be, hogyan lehet felhasználási jelentéseket létrehozni az Eszközkezelés modulban.
author: josaw1
manager: tfehr
ms.date: 08/21/2019
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
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 0cda21addfdc524537177740ebba6414ef8b4b96
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5260010"
---
# <a name="create-consumption-reports"></a><span data-ttu-id="e0798-103">Felhasználási jelentések létrehozása</span><span class="sxs-lookup"><span data-stu-id="e0798-103">Create consumption reports</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="e0798-104">Amikor létrehozta és feladta a felhasználási regisztrációkat a munkarendelésekre az Eszközkezelőben, két jelentés használható a felhasználás adatainak megjelenítésére.</span><span class="sxs-lookup"><span data-stu-id="e0798-104">When you've created and posted consumption registrations on work orders in Asset Management, two reports are available to display consumption details.</span></span>


## <a name="asset-consumption-report"></a><span data-ttu-id="e0798-105">Eszközfelhasználási jelentés</span><span class="sxs-lookup"><span data-stu-id="e0798-105">Asset consumption report</span></span>

<span data-ttu-id="e0798-106">A felhasználás munkarendelésekre való feladásakor kinyomtathatja az eszközfelhasználási jelentést.</span><span class="sxs-lookup"><span data-stu-id="e0798-106">When you have posted consumption on work orders, you can print an asset consumption report.</span></span> <span data-ttu-id="e0798-107">A jelentés megjeleníti az eszközökre feladott órákat, óraköltségeket, cikk-költségeket és költségeket.</span><span class="sxs-lookup"><span data-stu-id="e0798-107">The report displays hours, hour costs, item costs, and expenses posted on assets.</span></span>

1. <span data-ttu-id="e0798-108">Kattintson az **Eszközkezelés** > **Jelentések** > **Eszközök** > **Eszközfelhasználás** elemre.</span><span class="sxs-lookup"><span data-stu-id="e0798-108">Click **Asset management** > **Reports** > **Assets** > **Asset consumption**.</span></span>

2. <span data-ttu-id="e0798-109">Az **Eszközfelhasználás** párbeszédpaneljén válassza ki azokat a paramétereket és részletességi szintet, amelyet meg szeretne jeleníteni az **Igen** gombra kattintva a megfelelő gombsoron, és beadva a munkavégzési helyszín szintjét a **Megjelenítés** szakaszba.</span><span class="sxs-lookup"><span data-stu-id="e0798-109">In the **Asset consumption** dialog, select the parameters and detail level you want to see by selecting **Yes** on the relevant toggle buttons, and inserting a functional location level in the **Show** section.</span></span>
    - <span data-ttu-id="e0798-110">A **Szintek** mezőben megadhatja, hogy az eszközsorok milyen részletesen jelenítsék meg a munkavégzési helyszíneket.</span><span class="sxs-lookup"><span data-stu-id="e0798-110">You can use the **Levels** field to indicate how detailed you want the asset lines to be regarding functional locations.</span></span> 
    
        <span data-ttu-id="e0798-111">Ha például az „1” értéket adja meg a mezőben, és többszintű struktúrát használ a munkavégzési helyszínekhez, akkor minden munkavégzési helyszínhez tartozó eszköz a legfelső szinten jelenik meg, így a sorban hozzáadhatók az alacsonyabb szinten található munkavégzési helyszínekből.</span><span class="sxs-lookup"><span data-stu-id="e0798-111">For example, if you enter the number "1" in the field, and you have a multi-level functional location structure, all assets for a functional location will be shown on the top level, and therefore a line may be added up from functional locations located at a lower level.</span></span> 
        
        <span data-ttu-id="e0798-112">Ha a „0” értéket adja meg a **Szintek** mezőben, akkor részletes eredmény jelenik meg, amely minden eszközt megjeleníti az összes olyan munkavégzési helyszín szintnél, amelyhez a sor kapcsolódik.</span><span class="sxs-lookup"><span data-stu-id="e0798-112">If you enter the number "0" in the **Levels** field, you will see a detailed result showing all assets on all the functional location levels to which they are related.</span></span> 
        
    - <span data-ttu-id="e0798-113">Válassza az **Igen** beállítást az **Összes aleszköz összegei** átváltási gombján, ha a jelentésben szereplő minden egyes aleszköz összegeit meg szeretné tekinteni.</span><span class="sxs-lookup"><span data-stu-id="e0798-113">Select **Yes** on the **Sum on all sub assets** toggle button to see sums for each sub asset in the report.</span></span>

3. <span data-ttu-id="e0798-114">Válassza ki a dátumtartomány értékét a **Dátumok** részben.</span><span class="sxs-lookup"><span data-stu-id="e0798-114">Select a date interval in the **Dates** section.</span></span>

4. <span data-ttu-id="e0798-115">A **Cél** gyorslapon válassza ki, hogy a jelentést a képernyőn szeretné megjeleníteni, nyomtatni szeretné, vagy fájlként vagy e-mailben menteni.</span><span class="sxs-lookup"><span data-stu-id="e0798-115">On the **Destination** FastTab, select if you want to display the report on screen, print it, or save it as a file or email.</span></span>

5. <span data-ttu-id="e0798-116">Szükség esetén kiválaszthatja a jelentésben megjelenítendő eszközöket is.</span><span class="sxs-lookup"><span data-stu-id="e0798-116">If required, you can select specific assets to be displayed in the report.</span></span> <span data-ttu-id="e0798-117">A **Szerepeltetni kívánt rekordok** gyorslapján kattintson a **Szűrő** elemre, és adja hozzá a jelentésben szerepeltetni kívánt eszközöket.</span><span class="sxs-lookup"><span data-stu-id="e0798-117">On the **Records to include** FastTab, click **Filter**, and add the assets you want to include in the report.</span></span>

6. <span data-ttu-id="e0798-118">A jelentés előállításához kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="e0798-118">Click **OK** to generate the report.</span></span>


## <a name="work-order-consumption-report"></a><span data-ttu-id="e0798-119">Munkarendelés felhasználási jelentése</span><span class="sxs-lookup"><span data-stu-id="e0798-119">Work order consumption report</span></span>

<span data-ttu-id="e0798-120">A felhasználás munkarendelésekre való feladásakor kinyomtathatja a munkarendelés-felhasználási jelentést.</span><span class="sxs-lookup"><span data-stu-id="e0798-120">When you have posted consumption on work orders, you can print a work order consumption report.</span></span> <span data-ttu-id="e0798-121">A jelentés megjeleníti a munkarendelésekre feladott órákat, óraköltségeket, cikk-költségeket és költségeket.</span><span class="sxs-lookup"><span data-stu-id="e0798-121">The report displays hours, hour costs, item costs, and expenses posted on work orders.</span></span>

1. <span data-ttu-id="e0798-122">Kattintson az **Eszközkezelés** > **Jelentések** > **Munkarendelések** > **Munkarendelés felhasználás** pontra.</span><span class="sxs-lookup"><span data-stu-id="e0798-122">Click **Asset management** > **Reports** > **Work orders** > **Work order consumption**.</span></span>

2. <span data-ttu-id="e0798-123">A **Munkarendelési felhasználási** párbeszédpaneljén válassza ki azokat a paramétereket, amelyeket bele szeretne foglalni a jelentésbe, az **Igen** lehetőséget kiválasztásával a megfelelő gombokon a **Megjelenítés** szakaszban.</span><span class="sxs-lookup"><span data-stu-id="e0798-123">In the **Work order consumption** dialog, select the parameters you want to include in the report by selecting **Yes** on the relevant toggle buttons in the **Show** section.</span></span>

3. <span data-ttu-id="e0798-124">Válassza ki a dátumtartomány értékét a **Dátumok** részben.</span><span class="sxs-lookup"><span data-stu-id="e0798-124">Select a date interval in the **Dates** section.</span></span>

4. <span data-ttu-id="e0798-125">A **Cél** gyorslapon válassza ki, hogy a jelentést a képernyőn szeretné megjeleníteni, nyomtatni szeretné, vagy fájlként vagy e-mailben menteni.</span><span class="sxs-lookup"><span data-stu-id="e0798-125">On the **Destination** FastTab, select if you want to display the report on screen, print it, or save it as a file or email.</span></span>

5. <span data-ttu-id="e0798-126">Szükség esetén kiválaszthatja a jelentésben megjelenítendő munkarendeléseket is.</span><span class="sxs-lookup"><span data-stu-id="e0798-126">If required, you can select specific work orders to be displayed in the report.</span></span> <span data-ttu-id="e0798-127">A **Szerepeltetni kívánt rekordok** gyorslapján kattintson a **Szűrő** elemre, és adja hozzá a jelentésben szerepeltetni kívánt munkarendeléseket.</span><span class="sxs-lookup"><span data-stu-id="e0798-127">On the **Records to include** FastTab, click **Filter**, and add the work orders you want to include in the report.</span></span>

6. <span data-ttu-id="e0798-128">A jelentés előállításához kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="e0798-128">Click **OK** to generate the report.</span></span>


>[!NOTE]
><span data-ttu-id="e0798-129">Létrehozhat egy [munkarendelési jelentést](../work-orders/work-order-report.md) is, amely több munkarendelési adatot tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="e0798-129">You can also generate a [work order report](../work-orders/work-order-report.md), which contains more work order details.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]