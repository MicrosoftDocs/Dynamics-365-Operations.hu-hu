---
title: Eszközkritikusságok típusai
description: Ez a témakör bemutatja az eszközkritikussági típusokat az Eszközkezelés modulban.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetCriticality, EntAssetObjectCriticality
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c9d2c5e8b6676abf03fe0d3de8b23f125713d6f2
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/16/2021
ms.locfileid: "5021704"
---
# <a name="asset-criticality-types"></a><span data-ttu-id="a4979-103">Eszközkritikusságok típusai</span><span class="sxs-lookup"><span data-stu-id="a4979-103">Asset criticality types</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="a4979-104">Ez a témakör bemutatja az eszközkritikussági típusokat az Eszközkezelés modulban.</span><span class="sxs-lookup"><span data-stu-id="a4979-104">The topic explains asset criticality types in Asset Management.</span></span> <span data-ttu-id="a4979-105">Az eszközkritikusság kapcsolódik az eszközökhöz, és átkerül a munkarendelésekre.</span><span class="sxs-lookup"><span data-stu-id="a4979-105">Asset criticality is related to assets and is transferred to work orders.</span></span> <span data-ttu-id="a4979-106">A munkarendeléseken nem módosítható.</span><span class="sxs-lookup"><span data-stu-id="a4979-106">It can't be changed on a work order.</span></span> <span data-ttu-id="a4979-107">Az eszközkritikusság segítségével kiszámíthatja a munkarendelés kritikusságát a munkarendelés ütemezése során.</span><span class="sxs-lookup"><span data-stu-id="a4979-107">Asset criticality is used to calculate work order criticality during work order scheduling.</span></span> <span data-ttu-id="a4979-108">Más szavakkal élve, annak kiszámítására használják, hogy egy eszköz karbantartási feladata milyen mértékben befolyásolja a vállalat termelési ütemezését és termelékenységét.</span><span class="sxs-lookup"><span data-stu-id="a4979-108">In other words, it's used to calculate the extent to which a maintenance job on an asset affects the production schedule and productivity in your company.</span></span> <span data-ttu-id="a4979-109">A munkarendelés ütemezéséhez szükséges értékelési pontszámok kiszámításával kapcsolatos beállításra vonatkozó további információkat az [Eszközkezelés paraméterei](../setup-for-objects/enterprise-asset-management-parameters.md) részben találhat.</span><span class="sxs-lookup"><span data-stu-id="a4979-109">For more information about the setup that is related to the calculation of rating scores for work order scheduling, see [Asset Management parameters](../setup-for-objects/enterprise-asset-management-parameters.md).</span></span>

<span data-ttu-id="a4979-110">A kritikusság beállításához először létre kell hozni a kritikusságtípusokat, amelyeket az eszköz beállítása során kell használni.</span><span class="sxs-lookup"><span data-stu-id="a4979-110">To set up criticality, you first create the criticality types that should be used in the asset setup.</span></span> <span data-ttu-id="a4979-111">Ezután beállíthat eszközkritikusságokat.</span><span class="sxs-lookup"><span data-stu-id="a4979-111">You then set up asset criticalities.</span></span>

## <a name="set-up-criticality-types"></a><span data-ttu-id="a4979-112">Kritikusságtípusok beállítása</span><span class="sxs-lookup"><span data-stu-id="a4979-112">Set up criticality types</span></span>

1. <span data-ttu-id="a4979-113">Válassza ki az **Eszközkezelés** \> **Beállítás** \> **Eszközök** \> **Kritikusságtípusok** elemet.</span><span class="sxs-lookup"><span data-stu-id="a4979-113">Select **Asset management** \> **Setup** \> **Assets** \> **Criticality types**.</span></span>
2. <span data-ttu-id="a4979-114">Válassza az **Új** lehetőséget egy rekord létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="a4979-114">Select **New** to create a record.</span></span>
3. <span data-ttu-id="a4979-115">A **Kritikusság** mezőben adjon meg egy számot, amely a kritikusságot jelzi.</span><span class="sxs-lookup"><span data-stu-id="a4979-115">In the **Criticality** field, enter a number that indicates the criticality.</span></span>
4. <span data-ttu-id="a4979-116">A **Név** mezőbe írja be a kritikussátípus nevét.</span><span class="sxs-lookup"><span data-stu-id="a4979-116">In the **Name** field, enter a name for the criticality type.</span></span>
5. <span data-ttu-id="a4979-117">A **Szorzó** mezőben adjon meg egy szorzót.</span><span class="sxs-lookup"><span data-stu-id="a4979-117">In the **Factor** field, enter a factor.</span></span> <span data-ttu-id="a4979-118">A rendszer ezt a szorzót használja a munkarendelés-ütemezés számítása során, amellyel megállapítja a használandó kritikusságrekordot.</span><span class="sxs-lookup"><span data-stu-id="a4979-118">This factor is used during the calculation of work order scheduling to determine the criticality record that should be used.</span></span> <span data-ttu-id="a4979-119">(A rendszer mindig a legmagasabb szorzójú rekordot használja.) Ez a beállítás akkor releváns, ha – ahogy a következő ábrán látható – olyan kritikussági sorokat hoznak létre, amelyek kritikussági értéke megegyezik.</span><span class="sxs-lookup"><span data-stu-id="a4979-119">(The record that has the highest factor is always used.) This setting is relevant if, as shown in the following illustration, criticality lines are created that have the same criticality value.</span></span>

    ![Kritikussági típusok oldal](media/23-setup-for-objects.png)

## <a name="set-up-asset-criticalities"></a><span data-ttu-id="a4979-121">Eszközkritikusságok beállítása</span><span class="sxs-lookup"><span data-stu-id="a4979-121">Set up asset criticalities</span></span>

1. <span data-ttu-id="a4979-122">Válassza ki az **Eszközkezelés** \> **Beállítás** \> **Eszközkritikusságok** elemet.</span><span class="sxs-lookup"><span data-stu-id="a4979-122">Select **Asset management** \> **Setup** \> **Asset criticalities**.</span></span>
2. <span data-ttu-id="a4979-123">Válassza az **Új** lehetőséget egy rekord létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="a4979-123">Select **New** to create a record.</span></span>
3. <span data-ttu-id="a4979-124">Az eszközkritikusság részletességének szükséges szintjétől függően végezze el a releváns kiválasztásokat a **Munkavégzési helyszín**, **Eszköztípus**, **Gyártó**, **Modell**, **Eszköz**, **Feladattípus-kategória**, **Feladattípus**, **Feladattípus változata** és **Feladat követelménye** mezőkben.</span><span class="sxs-lookup"><span data-stu-id="a4979-124">Depending on the required level of detail for asset criticality, make relevant selections in the **Functional location**, **Asset type**, **Manufacturer**, **Model**, **Asset**, **Job type category**, **Job type**, **Job type variant**, and **Job requirement** fields.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a4979-125">Ha kiválasztotta az eszközkritikusságot, az Eszközkezelés végigmegy az összes eszközkritikussági rekordon lehetséges egyezést keresve.</span><span class="sxs-lookup"><span data-stu-id="a4979-125">When an asset criticality is selected, Asset Management goes through all asset criticality records to check for a possible match.</span></span> <span data-ttu-id="a4979-126">Mindig a leginkább meghatározott kombinációt ellenőrzi először.</span><span class="sxs-lookup"><span data-stu-id="a4979-126">It always checks the most specific combination first.</span></span> <span data-ttu-id="a4979-127">Más szavakkal az Eszközkezelés először a **Feladat követelménye** értékét ellenőrzi.</span><span class="sxs-lookup"><span data-stu-id="a4979-127">In other words, Asset Management first checks **Job requirement**.</span></span> <span data-ttu-id="a4979-128">Ha nem talál egyezést, ellenőrzi a **Munkatípus-változat** értékét.</span><span class="sxs-lookup"><span data-stu-id="a4979-128">If no match is found, it checks **Job type variant**.</span></span> <span data-ttu-id="a4979-129">Ha nem talál egyezést, ellenőrzi a **Munkatípus** értékét, és így tovább.</span><span class="sxs-lookup"><span data-stu-id="a4979-129">If no match is found, it checks **Job type**, and so on.</span></span> <span data-ttu-id="a4979-130">Ahogy az az oldal elrendezésében is látható, ez a viselkedésmód azt jelenti, hogy a legspecifikusabb kombináció megkereséséhez az Eszközkezelés minden egyes rekordot jobbról balra ellenőriz egyezést keresve.</span><span class="sxs-lookup"><span data-stu-id="a4979-130">As you can see in the layout of the page, this behavior means that, to find the most specific combination, Asset Management checks each record from right to left for a match.</span></span> <span data-ttu-id="a4979-131">Ha nem talál egyezést, akkor a rendszer azt az „alapértelmezett” rekordot használja, amelynél nincsenek kiválasztások.</span><span class="sxs-lookup"><span data-stu-id="a4979-131">If no match is found, the "default" record that has no selections is used.</span></span>

4. <span data-ttu-id="a4979-132">A **Kritikusság** mezőben válasszon egyet az előző eljárás során létrehozott kritikussági értékek közül.</span><span class="sxs-lookup"><span data-stu-id="a4979-132">In the **Criticality** field, select one of the criticality values that you created in the previous procedure.</span></span>

### <a name="notes-about-criticality-setup"></a><span data-ttu-id="a4979-133">Megjegyzések a kritikusság beállításáról</span><span class="sxs-lookup"><span data-stu-id="a4979-133">Notes about criticality setup</span></span>

- <span data-ttu-id="a4979-134">Ha a beállítás során módosítja az eszköz kritikusságát, miután már használta egy munkarendelésen, a munkarendelés kritikussága nem frissül ennek megfelelően.</span><span class="sxs-lookup"><span data-stu-id="a4979-134">If you change an asset criticality in this setup after you've already used it on a work order, the criticality on the work order isn't updated accordingly.</span></span>
- <span data-ttu-id="a4979-135">A program minden alkalommal újraszámolja a munkarendelésen szereplő kritikusságot, amikor a munkarendeléshez hozzáadnak vagy róla eltávolítanak egy munkarendelési sort.</span><span class="sxs-lookup"><span data-stu-id="a4979-135">The criticality on a work order is recalculated every time that a work order line is added to or deleted from the work order.</span></span>
- <span data-ttu-id="a4979-136">Ha a munkarendelés számos munkarendelési feladatot tartalmaz, akkor a rendszer mindig a **Kritikusságtípus** oldal **Szorzó** mezője szerinti legmagasabb kritikusságút használja a munkarendelésen.</span><span class="sxs-lookup"><span data-stu-id="a4979-136">If a work order contains several work order jobs, the highest criticality, according to the **Factor** field on the **Criticality types** page, is always used on the work order.</span></span>
- <span data-ttu-id="a4979-137">Általában az eszközök kritikussága idővel változhat.</span><span class="sxs-lookup"><span data-stu-id="a4979-137">Generally, asset criticality can change over a period.</span></span> <span data-ttu-id="a4979-138">A kritikusságot új berendezések vásárlása, felújítások stb. befolyásolhatják.</span><span class="sxs-lookup"><span data-stu-id="a4979-138">Criticality can be affected by the purchase of new equipment, refurbishments, and so on.</span></span> <span data-ttu-id="a4979-139">Javasoljuk az eszközkritikusságok rendszeres időközönkénti felülvizsgálatát (például évente egyszer vagy kétévente), hogy biztosítsa, hogy a kritikussági meghatározások megfelelnek az aktuális termelési beállításoknak.</span><span class="sxs-lookup"><span data-stu-id="a4979-139">Consider reevaluating your asset criticalities at regular intervals (for example, once per year or every other year) to make sure that your criticality definitions match your current production setup.</span></span>
