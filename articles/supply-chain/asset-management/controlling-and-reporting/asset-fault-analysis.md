---
title: Eszköz hibájának elemzése
description: Ez a cikk az Eszközkezelés hibás eszköz elemzésének költségét ismerteti.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
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
ms.openlocfilehash: 7c9330cc7b3a8839d94c8945418548033254786b
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918441"
---
# <a name="asset-fault-analysis"></a><span data-ttu-id="e2f80-103">Eszköz hibájának elemzése</span><span class="sxs-lookup"><span data-stu-id="e2f80-103">Asset fault analysis</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="e2f80-104">Az Eszközkezeléssel elemezheti az eszközök hibaregisztrációit, hogy áttekintést kapjon egy adott időszakra vonatkozóan regisztrált hibák teljes számáról.</span><span class="sxs-lookup"><span data-stu-id="e2f80-104">In Asset Management, you can analyze asset fault registrations to get an overview of the total number of faults registered during a specific period.</span></span> <span data-ttu-id="e2f80-105">A hibarögzítéseket különböző szempontok alapján lehet elemezni, például az eszközökre, eszközök típusára, funkcionális helyekre, hibatünetekre vagy hibatípusokra koncentrálva.</span><span class="sxs-lookup"><span data-stu-id="e2f80-105">Fault registrations can be analyzed from different perspectives, for example with focus on assets, asset types, functional locations, fault symptoms, or fault types.</span></span>

1. <span data-ttu-id="e2f80-106">Kattintson az **Eszközkezelés** > **Lekérdezések** > **Eszközhiba** > **Eszköz hibájának elemzése**.</span><span class="sxs-lookup"><span data-stu-id="e2f80-106">Click **Asset management** > **Inquiries** > **Asset fault** > **Asset fault analysis**.</span></span>

2. <span data-ttu-id="e2f80-107">Az **Eszköz hibájának elemzése számítás** párbeszédpaneljén a **Szint** mező segítségével jelezheti, hogy milyen részletesen szeretné megjeleníteni az eszköz hibás sorait a funkcionális helyekre vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="e2f80-107">In the **Asset fault analysis calculation** dialog, you can use the **Level** field to indicate how detailed you want the asset fault lines to be regarding functional locations.</span></span> <span data-ttu-id="e2f80-108">Ha például az „1” értéket adja meg a mezőben, és többszintű struktúrát használ a munkavégzési helyszínekhez, akkor a hibás eszköz minden munkavégzési helyszínhez tartozó sora a legfelső szinten jelenik meg, így a sorban szereplő óraszámok hozzáadhatók az alacsonyabb szinten található munkavégzési helyszínekből.</span><span class="sxs-lookup"><span data-stu-id="e2f80-108">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all asset fault lines for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> <span data-ttu-id="e2f80-109">Ha a „0” értéket adja meg a **Szint** mezőben, akkor részletes eredmény jelenik meg, amely az eszközhiba minden sorát megjeleníti az összes olyan munkavégzési helyszín szintnél, amelyhez a sor kapcsolódik.</span><span class="sxs-lookup"><span data-stu-id="e2f80-109">If you insert the number "0" in the **Level** field, you will see a detailed result showing all asset fault lines on all the functional location level to which they are related.</span></span>

3. <span data-ttu-id="e2f80-110">Ha szűkíteni szeretné a keresést, kiválaszthat meghatározott eszközöket, meghibásodási dátumokat, hibaokokat és hibamegoldásokat a **Szerepeltetni kívánt rekordok** gyorslapon.</span><span class="sxs-lookup"><span data-stu-id="e2f80-110">If you want to limit the search, you can select specific assets, fault dates, fault causes, and fault remedies on the **Records to include** FastTab.</span></span>

4. <span data-ttu-id="e2f80-111">Kattintson az **OK** gombra az számítás indításához.</span><span class="sxs-lookup"><span data-stu-id="e2f80-111">Click **OK** to start the calculation.</span></span>

5. <span data-ttu-id="e2f80-112">Az **Eszköz hibájának elemzése** lapon kattintson a **Csoportosítás alapja** műveletlap csoport egy vagy több gombjára a látni kívánt részletességi szint megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="e2f80-112">On the **Asset fault analysis** tab, click one or more buttons in the **Group by...** action pane groups to display the detail level you want to see.</span></span> <span data-ttu-id="e2f80-113">Az aktivált gombok ki vannak emelve.</span><span class="sxs-lookup"><span data-stu-id="e2f80-113">Activated buttons are highlighted.</span></span> <span data-ttu-id="e2f80-114">A gombra kattintva aktiválhatja vagy inaktiválhatja a gombokat.</span><span class="sxs-lookup"><span data-stu-id="e2f80-114">Activate or deactivate buttons by clicking on them.</span></span>

6. <span data-ttu-id="e2f80-115">A képernyőn látható választások megjelenítéséhez kattintson a **Számítások frissítése** hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e2f80-115">Click **Update calculations** to show your selections on the screen.</span></span> 

>[!NOTE]
><span data-ttu-id="e2f80-116">Minden alkalommal, amikor aktiválja vagy inaktiválja a **Csoportosítás alapja** műveletlap csoport gombjait, ne felejtsen el a beállítások kiválasztása után a **Számítások frissítése** gombra kattintani.</span><span class="sxs-lookup"><span data-stu-id="e2f80-116">Every time you activate or deactivate buttons in the **Group by...** action pane groups, remember to click the **Update calculations** button after you changed the selections.</span></span> <span data-ttu-id="e2f80-117">Erre azért van szükség, mert a rendszer nagy mennyiségű adatot dolgoz fel a hiba valószínűségének újraszámításakor.</span><span class="sxs-lookup"><span data-stu-id="e2f80-117">This is required because a large amount of data is processed as you are recalculating fault probability.</span></span>

<span data-ttu-id="e2f80-118">A hibaregisztrációk elemzésére számos mód van.</span><span class="sxs-lookup"><span data-stu-id="e2f80-118">There are many ways to analyze fault registrations.</span></span> <span data-ttu-id="e2f80-119">A lentebb látható példák öt képernyőfotón mutatják meg, hogy a különböző adatválasztások milyen különböző adatokat adnak meg.</span><span class="sxs-lookup"><span data-stu-id="e2f80-119">Below you see examples in five screenshots of how different data selections provide different pieces of information.</span></span> <span data-ttu-id="e2f80-120">Megtekintheti, hogy a különböző választások milyen módon tudnak betekintést és részleteket szolgáltatni az eszközhibák regisztrálásának elemzésekor.</span><span class="sxs-lookup"><span data-stu-id="e2f80-120">You will see how different selections provide more insight and detail when analyzing asset fault registrations.</span></span>

<span data-ttu-id="e2f80-121">A lenti képernyőfotón csak a **Tünet** gomb van kiválasztva.</span><span class="sxs-lookup"><span data-stu-id="e2f80-121">In the screenshot below, only the **Symptom** button is selected.</span></span>

- <span data-ttu-id="e2f80-122">A hibaregisztrációk három hibatüneten történtek: „Légszivárgás”, „Kiégett biztosíték” és „Elakadtak berendezések”.</span><span class="sxs-lookup"><span data-stu-id="e2f80-122">Fault registrations have been made on three fault symptoms: "Air leak", "Blown fuse", and "Equipment jammed".</span></span>  
- <span data-ttu-id="e2f80-123">A **Valószínűség %** oszlopban a százalékos értékek 100%-ig adhatók.</span><span class="sxs-lookup"><span data-stu-id="e2f80-123">In the **Probability %** column, all percentages add up to 100%.</span></span> <span data-ttu-id="e2f80-124">A valószínűség a hibaelemzés összes **Tünet** regisztrációján alapul.</span><span class="sxs-lookup"><span data-stu-id="e2f80-124">Probability is based on all **Symptom** registrations in this fault analysis.</span></span>

![1. ábra](media/06-controlling-and-reporting.png)


<span data-ttu-id="e2f80-126">A lenti képen az **Év** és a **Hónap** hozzáadódik annak a megjelenítéséhez, hogy hogyan lehet megtekinteni a hibák regisztrálását a kiválasztott időszakban.</span><span class="sxs-lookup"><span data-stu-id="e2f80-126">In the screenshot below, **Year** and **Month** are added to show how you can view fault registrations during a selected period.</span></span>

- <span data-ttu-id="e2f80-127">A hibatünetek most már éves/havi regisztrációkként jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="e2f80-127">The fault symptoms are now shown as registrations per year/month.</span></span>  
- <span data-ttu-id="e2f80-128">Ha minden hónap minden százalékát hozzáadja a **Valószínűség%** oszlopban, akkor 100%-ot ad hozzá.</span><span class="sxs-lookup"><span data-stu-id="e2f80-128">In the **Probability %** column, if you add all percentages for each month, they add up to 100%.</span></span> <span data-ttu-id="e2f80-129">A valószínűség az adott hibaelemzés **Tünet** regisztrációján alapul.</span><span class="sxs-lookup"><span data-stu-id="e2f80-129">Probability is based on the **Symptom** registrations in this fault analysis.</span></span> <span data-ttu-id="e2f80-130">Ha egy eszköznek nagy számú sora van, de nagy százalék egy sorban jelenik meg, ezt a hibatünetet jobban meg kell vizsgálni, hogy milyen módon korlátozhatja az adott hiba miatti regisztrációk számát.</span><span class="sxs-lookup"><span data-stu-id="e2f80-130">If you have a large number of lines on an asset, but a large percentage stands out on a line, that would be an indication of a fault symptom to examine more closely to find a way to limit the number of registrations for that fault symptom.</span></span>

![2. ábra](media/07-controlling-and-reporting.png)


- <span data-ttu-id="e2f80-132">Az eszközök és az eszköztípus kombinációja az alábbi három képernyőfotón megjelenített számítások alapjaként használatos, ami növelni fogja a részletek szintjét.</span><span class="sxs-lookup"><span data-stu-id="e2f80-132">The combination of assets and an asset type is used as a basis for the calculations shown in the three screenshots below, which will increase in detail level.</span></span>  
- <span data-ttu-id="e2f80-133">Általában a **Csoportosítás dátum szerint**, a **Csoportosítás eszköz szerint**, a **Csoportosítás munkavégzési helyszín szerint** műveletiablaktábla-csoportok, valamint a **Hiba** gomb (hibaazonosító), tartalmaz időszakokat vagy eszközkapcsolatokat.</span><span class="sxs-lookup"><span data-stu-id="e2f80-133">Generally, the buttons in the **Group by date**, **Group by asset**, **Group by functional location** action pane groups, as well as the **Fault** button (Fault ID), contain periods or asset relations.</span></span> <span data-ttu-id="e2f80-134">A **Hibajelenség**, a **Terület**, a **Típus**, az **Ok**, az **Orvoslás** gomb a hibakezeléshez használt kategóriák, amelyek az eszközhiba-regisztrációk elemzéséhez és a problématerületek lehatárolásához szükségesek.</span><span class="sxs-lookup"><span data-stu-id="e2f80-134">The **Symptom**, **Area**, **Type**, **Cause**, and **Remedy** buttons are categorizations used in fault management to analyze asset fault registrations and pinpoint problem areas.</span></span>  

<span data-ttu-id="e2f80-135">A lenti képernyőfotón hozzáadtuk az **Eszköz** és **Eszköztípus** elemeket, hogy több részletet kapjunk a hibák regisztrálásával kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="e2f80-135">In the screenshot below, **Asset** and **Asset type** were added to provide more detail regarding fault registrations.</span></span>

- <span data-ttu-id="e2f80-136">A hiba tünetei most fel vannak osztva az **Eszköz** / **Eszköztípus** / **Tünet** kombinációkban.</span><span class="sxs-lookup"><span data-stu-id="e2f80-136">The fault symptoms are now split up in **Asset** / **Asset type** / **Symptom** combinations.</span></span>  
- <span data-ttu-id="e2f80-137">Ha minden hónap minden százalékát hozzáadja a **Valószínűség%** oszlopban az **Eszköz** / **Eszköztípus** / **Tünet** kombinációknak ebben a sorrendben, akkor mindegyik legfeljebb 100% lehet.</span><span class="sxs-lookup"><span data-stu-id="e2f80-137">In the **Probability %** column, if you add all percentages for the combination of **Asset** / **Asset type** / **Symptom** respectively, they each add up to 100%.</span></span> <span data-ttu-id="e2f80-138">A valószínűség az adott hibaelemzés **Tünet** regisztrációján alapul.</span><span class="sxs-lookup"><span data-stu-id="e2f80-138">Probability is based on **Symptom** registrations in this fault analysis.</span></span> <span data-ttu-id="e2f80-139">Ha egy eszköznek nagy számú sora van, de nagy százalék egy sorban jelenik meg, ezt a hibatünetet jobban meg kell vizsgálni, hogy milyen módon korlátozhatja az adott hiba miatti regisztrációk számát.</span><span class="sxs-lookup"><span data-stu-id="e2f80-139">If you have a large number of lines on an asset, but a large percentage stands out on a line, that would be an indication of a fault symptom to examine more closely to find a way to limit the number of registrations for that fault symptom.</span></span>

![3. ábra](media/08-controlling-and-reporting.png)


<span data-ttu-id="e2f80-141">A lenti képernyőfotón hozzáadtuk a **Terület** elemet a **Tünet**, **Eszköz** és **Eszköztípus** elemekhez, hogy több részletet kapjunk a hibák regisztrálásával kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="e2f80-141">In the screenshot below, **Area** was added to **Symptom**, **Asset**, and **Asset type** to provide more detail regarding fault registrations.</span></span>

- <span data-ttu-id="e2f80-142">Ha minden hónap minden százalékát hozzáadja a **Valószínűség%** oszlopban az **Eszköz** / **Eszköztípus** / **Tünet** kombinációt az eszköznek, akkor mindegyik legfeljebb 100% lehet.</span><span class="sxs-lookup"><span data-stu-id="e2f80-142">In the **Probability %** column, if you add all percentages for the combination of **Asset** / **Asset type** / **Symptom** on an asset, they each add up to 100%.</span></span> <span data-ttu-id="e2f80-143">A valószínűség az adott hibaelemzés **Tünet** és **Terület** kombinációján alapul.</span><span class="sxs-lookup"><span data-stu-id="e2f80-143">Probability is based on the combination of **Symptom** and **Area** in this fault analysis.</span></span> <span data-ttu-id="e2f80-144">Ha egy eszköznek nagy számú sora van, de nagy százalék egy sorban jelenik meg, ezt a hibaterületet jobban meg kell vizsgálni, hogy milyen módon korlátozhatja az adott hibaterület miatti regisztrációk számát.</span><span class="sxs-lookup"><span data-stu-id="e2f80-144">If you have a large number of lines on an asset, but a large percentage stands out on a line, that would be an indication of a fault area to examine more closely to find a way to limit the number of registrations for that fault area.</span></span>  

![4. ábra](media/09-controlling-and-reporting.png)


<span data-ttu-id="e2f80-146">A lenti képernyőfotón a **Típus** lett hozzáadva, és megjelenik a példaként használt legrészletesebb számítás.</span><span class="sxs-lookup"><span data-stu-id="e2f80-146">In the screenshot below, **Type** was added, and the most detailed calculation in this example is shown.</span></span>
 
- <span data-ttu-id="e2f80-147">Ha minden hónap minden százalékát hozzáadja a **Valószínűség%** oszlopban az **Eszköz** / **Eszköztípus** / **Tünet** kombinációt az eszköznek, akkor mindegyik legfeljebb 100% lehet.</span><span class="sxs-lookup"><span data-stu-id="e2f80-147">In the **Probability %** column, if you add all percentages for the combination of **Asset** / **Asset type** / **Symptom** on an asset, they each add up to 100%.</span></span> <span data-ttu-id="e2f80-148">A valószínűség az adott hibaelemzés **Tünet**, **Terület** és **Típus** kombinációján alapul.</span><span class="sxs-lookup"><span data-stu-id="e2f80-148">Probability is based on the combination of **Symptom**, **Area**, and **Type** in this fault analysis.</span></span> <span data-ttu-id="e2f80-149">Ha egy eszköznek nagy számú sora van, de nagy százalék egy sorban jelenik meg, ezt a hibatípust jobban meg kell vizsgálni, hogy milyen módon korlátozhatja az adott hibatípus regisztrációinak számát.</span><span class="sxs-lookup"><span data-stu-id="e2f80-149">If you have a large number of lines on an asset, but a large percentage stands out on a line, that would be an indication of a fault type to examine more closely to find a way to limit the number of registrations on that fault type.</span></span>

![5. ábra](media/10-controlling-and-reporting.png)


>[!NOTE]
><span data-ttu-id="e2f80-151">A munkarendeléseken és a karbantartási kérelmeken létrehozott összes hibaregisztráció áttekintéséhez kattintson ide: **Eszközkezelés** > **Lekérdezések** > **Eszközhiba** > **Eszközhibák**.</span><span class="sxs-lookup"><span data-stu-id="e2f80-151">For an overview of all fault registrations created on work orders and maintenance requests, click **Asset management** > **Inquiries** > **Asset fault** > **Asset faults**.</span></span> <span data-ttu-id="e2f80-152">Az **Eszközhibák** oldalon válasszon ki egy eszközhiba-regisztrációt, és a **Kapcsolódó információ** ablaktábla kibontásával megtekintheti a kapcsolódó munkarendeléssel vagy karbantartási kérelemmel kapcsolatos információkat.</span><span class="sxs-lookup"><span data-stu-id="e2f80-152">On the **Asset faults** page, select an asset fault registration and expand the **Related information** pane to see information regarding the related work order or maintenance request.</span></span>

