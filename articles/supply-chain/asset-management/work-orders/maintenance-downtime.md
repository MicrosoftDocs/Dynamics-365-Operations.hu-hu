---
title: Karbantartás miatti üzemkimaradás munkarendelések esetén
description: Ez a témakör leírja, hogy a karbantartás miatti üzemkimaradás regisztrációkat a munkarendelésen kiválasztott eszközre vonatkozóan hogyan lehet létrehozni.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5c0c584ed53dc4ec8a761065838127dc67cbc41e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813725"
---
# <a name="maintenance-downtime-for-work-orders"></a><span data-ttu-id="a7ec4-103">Karbantartás miatti üzemkimaradás munkarendelések esetén</span><span class="sxs-lookup"><span data-stu-id="a7ec4-103">Maintenance downtime for work orders</span></span>

[!include [banner](../../includes/banner.md)]


<span data-ttu-id="a7ec4-104">A karbantartás miatti üzemkimaradás regisztrációkat a munkarendelésen kiválasztott eszközre vonatkozóan lehet létrehozni.</span><span class="sxs-lookup"><span data-stu-id="a7ec4-104">You can create maintenance downtime registrations on the asset that is selected on a work order.</span></span> <span data-ttu-id="a7ec4-105">Ez a képesség akkor lehet hasznos, ha a termelési területen egy vagy több gépen szeretné rögzíteni a karbantartás miatti üzemkimaradást.</span><span class="sxs-lookup"><span data-stu-id="a7ec4-105">This capability is useful if you want to register maintenance downtime on one or more machines in the production area.</span></span> <span data-ttu-id="a7ec4-106">Először létre kell hoznia azokat a karbantartás miatti üzemkimaradásokat, amelyeket használni szeretne, például a **Meghibásodás** és a **Tervezett leállítás**.</span><span class="sxs-lookup"><span data-stu-id="a7ec4-106">You first create the maintenance downtime reason codes that you want to use, such as **Breakdown** and **Planned stop**.</span></span> <span data-ttu-id="a7ec4-107">Ezt a lépést a **Karbantartás miatti üzemkimaradás okkódjai** oldalon teheti meg.</span><span class="sxs-lookup"><span data-stu-id="a7ec4-107">This step is done on the **Maintenance downtime reason codes** page.</span></span> <span data-ttu-id="a7ec4-108">Majd létrehozhatja a karbantartás miatti üzemkimaradás regisztrációkat a **Karbantartás miatti üzemkimaradás** helyen, és hozzáadhatja a megfelelő karbantartás miatti üzemkimaradás okkódokat.</span><span class="sxs-lookup"><span data-stu-id="a7ec4-108">You can then create maintenance downtime registrations on the **Maintenance downtime** page and add the relevant maintenance downtime reason codes.</span></span>

## <a name="create-maintenance-downtime-reason-codes"></a><span data-ttu-id="a7ec4-109">karbantartás miatti üzemkimaradás okkódjainak létrehozása</span><span class="sxs-lookup"><span data-stu-id="a7ec4-109">Create maintenance downtime reason codes</span></span>

1. <span data-ttu-id="a7ec4-110">Válassza az **Eszközkezelés** > **Beállítás** > **Munkarendelések** > **Karbantartás miatti üzemkimaradás okkódjai** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a7ec4-110">Select **Asset management** > **Setup** > **Work orders** > **Maintenance downtime reason codes**.</span></span>

2. <span data-ttu-id="a7ec4-111">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a7ec4-111">Select **New**.</span></span>

3. <span data-ttu-id="a7ec4-112">A **Karbantartás miatti üzemkimaradás okkódja** mezőben adjon meg egy azonosítót a karbantartás miatti üzemkimaradás okkódjához.</span><span class="sxs-lookup"><span data-stu-id="a7ec4-112">In the **Maintenance downtime reason code** field, enter an ID for the maintenance downtime reason code.</span></span>

4. <span data-ttu-id="a7ec4-113">A **Név** mezőben adjon meg egy nevet.</span><span class="sxs-lookup"><span data-stu-id="a7ec4-113">In the **Name** field, enter a name.</span></span>

5. <span data-ttu-id="a7ec4-114">Jelölje be a **KPI -k szerepeltetése** jelölőnégyzetet, ha az okkódot figyelembe kell venni az eszköz fő teljesítménymutatóinak (KPI) számítása során.</span><span class="sxs-lookup"><span data-stu-id="a7ec4-114">Select the **KPI include** check box if the reason code should be included in calculations of key performance indicators (KPIs) for the asset.</span></span> <span data-ttu-id="a7ec4-115">A tervezett termelési leállások általában nem szerepelnek a KPI-számításokban, mivel ezek nem befolyásolják a várt teljesítményt.</span><span class="sxs-lookup"><span data-stu-id="a7ec4-115">In general, planned production stops should not be included in KPI calculations, because they don't affect expected performance.</span></span>

6. <span data-ttu-id="a7ec4-116">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a7ec4-116">Select **Save**.</span></span>

<span data-ttu-id="a7ec4-117">A lenti ábra a **Karbantartás miatti üzemkimaradási okkódok** oldalt szemlélteti.</span><span class="sxs-lookup"><span data-stu-id="a7ec4-117">The illustration below shows an example of the **Maintenance downtime reason codes** page.</span></span>

![1. ábra](media/15-work-orders.png)

<span data-ttu-id="a7ec4-119">Miután létrehozta a használni kívánt karbantartás miatti üzemkimaradási okkódokat, létrehozhatja a munkarendelésekhez és a eszközökhöz tartozó karbantartás miatti üzemkimaradás regisztrációkat.</span><span class="sxs-lookup"><span data-stu-id="a7ec4-119">After you've created the maintenance downtime reason codes that you want to use, you can create maintenance downtime registrations for work orders and assets.</span></span>


## <a name="create-maintenance-downtime-registrations"></a><span data-ttu-id="a7ec4-120">karbantartás miatti üzemkimaradás regisztrációinak létrehozása</span><span class="sxs-lookup"><span data-stu-id="a7ec4-120">Create maintenance downtime registrations</span></span>

1. <span data-ttu-id="a7ec4-121">Kattintson az **Eszközkezelés** > **Közös** > **Munkarendelések** > **Összes munkarendelés** vagy **Aktív munkarendelések** elemre.</span><span class="sxs-lookup"><span data-stu-id="a7ec4-121">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="a7ec4-122">Válassza ki a munkarendelést, majd a Művelet panel **Munkarendelés** lapján az **Eszközök** csoportban válassz a **Karbantartási miatti üzemkimaradás** pontot.</span><span class="sxs-lookup"><span data-stu-id="a7ec4-122">Select the work order, and then, on the **Work order** tab, in the **Asset** group, select **Maintenance downtime**.</span></span>

3. <span data-ttu-id="a7ec4-123">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a7ec4-123">Select **New**.</span></span>

4. <span data-ttu-id="a7ec4-124">Dátum-és időintervallum definiálásához a karbantartási leállás regisztrálásához a **Kezdés** és **Befejezés** mezőkbe.</span><span class="sxs-lookup"><span data-stu-id="a7ec4-124">In the **From** and **To** fields, define the date and time interval for the maintenance downtime registration.</span></span>

>[!NOTE]
><span data-ttu-id="a7ec4-125">A **Befejezés** mező kihagyásakor a program automatikusan beszúrja az időtartamot órában az **Időtartam** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="a7ec4-125">When you leave the **To** field, the duration in hours is automatically inserted in the **Duration** field.</span></span>

5. <span data-ttu-id="a7ec4-126">Válasszon egy okkódot a **karbantartás miatti üzemkimaradás okkódja** mezőben.</span><span class="sxs-lookup"><span data-stu-id="a7ec4-126">In the **maintenance downtime reason code** field, select a reason code.</span></span>

6. <span data-ttu-id="a7ec4-127">További regisztrációk hozzáadásához ismételje meg a 3–5. lépéseket.</span><span class="sxs-lookup"><span data-stu-id="a7ec4-127">Repeat steps 3 through 5 to add more registrations.</span></span>

7. <span data-ttu-id="a7ec4-128">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a7ec4-128">Select **Save**.</span></span>

<span data-ttu-id="a7ec4-129">A következő ábrán egy karbantartás miatti üzemkimaradás regisztrációjának példája látható.</span><span class="sxs-lookup"><span data-stu-id="a7ec4-129">The illustration below shows an example of maintenance downtime registration.</span></span>

![2. ábra](media/16-work-orders.png)

<span data-ttu-id="a7ec4-131">A karbantartás miatti üzemkimaradások kiszámításához használt naptár a tárgyi eszközök és paraméterek beállításában megadott beállítástól függ.</span><span class="sxs-lookup"><span data-stu-id="a7ec4-131">The calendar that is used to calculate a maintenance downtime registration depends on your selection in the setup of assets and parameters.</span></span> <span data-ttu-id="a7ec4-132">Ha ki van választva egy erőforrás egy eszközhöz az **Erőforrás** ,mezőben a **Tárgyi eszköz** gyorslapon az **Összes eszköz** oldalon, akkor a program a társított erőforráscsoport naptárát használja, ahogy az a következő ábrán látható.</span><span class="sxs-lookup"><span data-stu-id="a7ec4-132">If a resource is selected on an asset in the **Resource** field on the **Fixed asset** FastTab of the **All assets** page, the calendar that is set up for the associated resource group is used, as shown in the following illustration.</span></span>

![3. ábra](media/17-work-orders.png)

<span data-ttu-id="a7ec4-134">Ha az eszközhöz nincs kiválasztva erőforrás, akkor a program az **Eszközkezelés paraméterei** alatt kiválasztott naptárat használja a következő illusztrációnak megfelelően.</span><span class="sxs-lookup"><span data-stu-id="a7ec4-134">If no resource is selected on the asset, the standard calendar that is selected on the **Asset management parameters** page is used, as shown in the following illustration.</span></span>

![4. ábra](media/18-work-orders.png)

<span data-ttu-id="a7ec4-136">Kattintson a **Vállalati eszközkezelés** > **Lekérdezések** > **Karbantartás miatti üzemkimaradás** lehetőségre az összes karbantartás miatti üzemkimaradás regisztráció megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="a7ec4-136">To see an overview of all maintenance downtime registrations, click **Asset management** > **Inquiries** > **Maintenance downtime**.</span></span>

>[!NOTE]
><span data-ttu-id="a7ec4-137">Az **Eszközkezelés** modulban használt összes naptár a szervezeti felügyelet **Szervezeti adminisztráció** > **Beállítás** > **Naptárak** > **Naptárak** helyen van beállítva.</span><span class="sxs-lookup"><span data-stu-id="a7ec4-137">All calendars that are used in the **Asset Management** module are set up in **Organization administration** > **Setup** > **Calendars** > **Calendars**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]