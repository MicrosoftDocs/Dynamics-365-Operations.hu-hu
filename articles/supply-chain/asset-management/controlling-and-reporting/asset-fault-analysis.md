---
title: Eszköz hibájának elemzése
description: Ez a cikk az Eszközkezelés hibás eszköz elemzésének költségét ismerteti.
author: josaw1
manager: tfehr
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetObjectFaultCalculate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e911f7ca3b67acd9d5a1b170d8c99135da730847
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429633"
---
# <a name="asset-fault-analysis"></a><span data-ttu-id="24332-103">Eszköz hibájának elemzése</span><span class="sxs-lookup"><span data-stu-id="24332-103">Asset fault analysis</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="24332-104">Az Eszközkezeléssel elemezheti az eszközök hibaregisztrációit, hogy áttekintést kapjon egy adott időszakra vonatkozóan regisztrált hibák teljes számáról.</span><span class="sxs-lookup"><span data-stu-id="24332-104">In Asset Management, you can analyze asset fault registrations to get an overview of the total number of faults registered during a specific period.</span></span> <span data-ttu-id="24332-105">A hibarögzítéseket különböző szempontok alapján lehet elemezni, például az eszközökre, eszközök típusára, funkcionális helyekre, hibatünetekre vagy hibatípusokra koncentrálva.</span><span class="sxs-lookup"><span data-stu-id="24332-105">Fault registrations can be analyzed from different perspectives, for example with focus on assets, asset types, functional locations, fault symptoms, or fault types.</span></span>

1. <span data-ttu-id="24332-106">Kattintson az **Eszközkezelés** > **Lekérdezések** > **Eszközhiba** > **Eszköz hibájának elemzése**.</span><span class="sxs-lookup"><span data-stu-id="24332-106">Click **Asset management** > **Inquiries** > **Asset fault** > **Asset fault analysis**.</span></span>

2. <span data-ttu-id="24332-107">Az **Eszköz hibájának elemzése számítás** párbeszédpaneljén a **Szint** mező segítségével jelezheti, hogy milyen részletesen szeretné megjeleníteni az eszköz hibás sorait a funkcionális helyekre vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="24332-107">In the **Asset fault analysis calculation** dialog, you can use the **Level** field to indicate how detailed you want the asset fault lines to be regarding functional locations.</span></span> 

    <span data-ttu-id="24332-108">Ha például az „1” értéket adja meg a mezőben, és többszintű struktúrát használ a munkavégzési helyszínekhez, akkor a hibás eszköz minden munkavégzési helyszínhez tartozó sora a legfelső szinten jelenik meg, így a sorban szereplő óraszámok hozzáadhatók az alacsonyabb szinten található munkavégzési helyszínekből.</span><span class="sxs-lookup"><span data-stu-id="24332-108">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all asset fault lines for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> 
        
    <span data-ttu-id="24332-109">Ha a „0” értéket adja meg a **Szint** mezőben, akkor részletes eredmény jelenik meg, amely az eszközhiba minden sorát megjeleníti az összes olyan munkavégzési helyszín szintnél, amelyhez a sor kapcsolódik.</span><span class="sxs-lookup"><span data-stu-id="24332-109">If you insert the number "0" in the **Level** field, you will see a detailed result showing all asset fault lines on all the functional location level to which they are related.</span></span>

3. <span data-ttu-id="24332-110">Ha szűkíteni szeretné a keresést, kiválaszthat meghatározott eszközöket, meghibásodási dátumokat, hibaokokat és hibamegoldásokat a **Szerepeltetni kívánt rekordok** gyorslapon.</span><span class="sxs-lookup"><span data-stu-id="24332-110">If you want to limit the search, you can select specific assets, fault dates, fault causes, and fault remedies on the **Records to include** FastTab.</span></span>

4. <span data-ttu-id="24332-111">Kattintson az **OK** gombra az számítás indításához.</span><span class="sxs-lookup"><span data-stu-id="24332-111">Click **OK** to start the calculation.</span></span>

5. <span data-ttu-id="24332-112">Az **Eszköz hibájának elemzése** lapon kattintson a **Csoportosítás alapja** műveletlap csoport gombjaira a látni kívánt részletességi szint megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="24332-112">On the **Asset fault analysis** tab, click one or more **Group by** buttons to display the detail level you want to see.</span></span> <span data-ttu-id="24332-113">Az aktivált gombok ki vannak emelve.</span><span class="sxs-lookup"><span data-stu-id="24332-113">Activated buttons are highlighted.</span></span> <span data-ttu-id="24332-114">A gombra kattintva aktiválhatja vagy inaktiválhatja a gombokat.</span><span class="sxs-lookup"><span data-stu-id="24332-114">Activate or deactivate buttons by clicking on them.</span></span>

6. <span data-ttu-id="24332-115">A képernyőn látható választások megjelenítéséhez kattintson a **Számítások frissítése** hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="24332-115">Click **Update calculations** to show your selections on the screen.</span></span> 

>[!NOTE]
><span data-ttu-id="24332-116">Minden alkalommal, amikor aktiválja vagy inaktiválja a **Csoportosítás alapja** gombot, ne felejtsen el a **Számítások frissítése** gombra kattintani.</span><span class="sxs-lookup"><span data-stu-id="24332-116">Every time you activate or deactivate a **Group by** button, remember to click the **Update calculations** button.</span></span> <span data-ttu-id="24332-117">Erre azért van szükség, mert a rendszer nagy mennyiségű adatot dolgoz fel a hiba valószínűségének újraszámításakor.</span><span class="sxs-lookup"><span data-stu-id="24332-117">This is required because a large amount of data is processed as you are recalculating fault probability.</span></span>

## <a name="examples"></a><span data-ttu-id="24332-118">Példák</span><span class="sxs-lookup"><span data-stu-id="24332-118">Examples</span></span>

<span data-ttu-id="24332-119">A hibaregisztrációk elemzésére számos mód van.</span><span class="sxs-lookup"><span data-stu-id="24332-119">There are many ways to analyze fault registrations.</span></span> <span data-ttu-id="24332-120">Ebben a szakaszban öt példát láthat arra, hogy a különböző választások milyen módon tudnak betekintést és részleteket szolgáltatni az eszközhibák regisztrálásának elemzésekor.</span><span class="sxs-lookup"><span data-stu-id="24332-120">This section has five examples of how different data selections can provide more insight and detail when analyzing asset fault registrations.</span></span>

### <a name="group-by-symptoms"></a><span data-ttu-id="24332-121">Csoportosítás tünetek szerint</span><span class="sxs-lookup"><span data-stu-id="24332-121">Group by symptoms</span></span>

<span data-ttu-id="24332-122">A lenti képernyőfotón csak a **Tünet** gomb van kiválasztva.</span><span class="sxs-lookup"><span data-stu-id="24332-122">In the screenshot below, only the **Symptom** button is selected.</span></span>

- <span data-ttu-id="24332-123">A hibaregisztrációk három hibatüneten történtek: „Légszivárgás”, „Kiégett biztosíték” és „Elakadtak berendezések”.</span><span class="sxs-lookup"><span data-stu-id="24332-123">Fault registrations have been made on three fault symptoms: "Air leak", "Blown fuse", and "Equipment jammed".</span></span>  
- <span data-ttu-id="24332-124">A **Valószínűség %** oszlopban a százalékos értékek 100%-ig adhatók.</span><span class="sxs-lookup"><span data-stu-id="24332-124">In the **Probability %** column, all percentages add up to 100%.</span></span> <span data-ttu-id="24332-125">A valószínűség a hibaelemzés összes **Tünet** regisztrációján alapul.</span><span class="sxs-lookup"><span data-stu-id="24332-125">Probability is based on all **Symptom** registrations in this fault analysis.</span></span>

![1. ábra](media/06-controlling-and-reporting.png)

### <a name="group-by-symptoms-and-time-period"></a><span data-ttu-id="24332-127">Csoportosítás a tünetek és időszak szerint</span><span class="sxs-lookup"><span data-stu-id="24332-127">Group by symptoms and time period</span></span>

<span data-ttu-id="24332-128">A lenti képen az **Év** és a **Hónap** hozzáadódik annak a megjelenítéséhez, hogy hogyan lehet megtekinteni a hibák regisztrálását a kiválasztott időszakban.</span><span class="sxs-lookup"><span data-stu-id="24332-128">In the screenshot below, **Year** and **Month** are added to show how you can view fault registrations during a selected period.</span></span>

- <span data-ttu-id="24332-129">A hibatünetek most már éves/havi regisztrációkként jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="24332-129">The fault symptoms are now shown as registrations per year/month.</span></span>  
- <span data-ttu-id="24332-130">Ha minden hónap minden százalékát hozzáadja a **Valószínűség%** oszlopban, akkor 100%-ot ad hozzá.</span><span class="sxs-lookup"><span data-stu-id="24332-130">In the **Probability %** column, if you add all percentages for each month, they add up to 100%.</span></span> <span data-ttu-id="24332-131">A valószínűség az adott hibaelemzés **Tünet** regisztrációján alapul.</span><span class="sxs-lookup"><span data-stu-id="24332-131">Probability is based on the **Symptom** registrations in this fault analysis.</span></span> <span data-ttu-id="24332-132">Ha egy eszköznek nagy számú sora van, de nagy százalék egy sorban jelenik meg, ezt a hibatünetet jobban meg kell vizsgálni, hogy milyen módon korlátozhatja az adott hiba miatti regisztrációk számát.</span><span class="sxs-lookup"><span data-stu-id="24332-132">If you have a large number of lines on an asset, but a large percentage stands out on a line, that would be an indication of a fault symptom to examine more closely to find a way to limit the number of registrations for that fault symptom.</span></span>

![2. ábra](media/07-controlling-and-reporting.png)

### <a name="group-by-multiple-symptoms-and-assets"></a><span data-ttu-id="24332-134">Csoportosítás több tünet és eszköz szerint</span><span class="sxs-lookup"><span data-stu-id="24332-134">Group by multiple symptoms and assets</span></span>

<span data-ttu-id="24332-135">Az eszközök és az eszköztípus kombinációja az alábbi három képernyőfotón megjelenített számítások alapjaként használatos, ami növelni fogja a részletek szintjét.</span><span class="sxs-lookup"><span data-stu-id="24332-135">The combination of assets and an asset type is used as a basis for the calculations shown in the three screenshots below, which will increase in detail level.</span></span>  

<span data-ttu-id="24332-136">Általában a **Csoportosítás dátum szerint**, a **Csoportosítás eszköz szerint**, a **Csoportosítás munkavégzési helyszín szerint** műveletiablaktábla-csoportok, valamint a **Hiba** gomb (hibaazonosító), tartalmaz időszakokat vagy eszközkapcsolatokat.</span><span class="sxs-lookup"><span data-stu-id="24332-136">Generally, the buttons in the **Group by date**, **Group by asset**, **Group by functional location** Action Pane groups, as well as the **Fault** button (Fault ID), contain periods or asset relations.</span></span> <span data-ttu-id="24332-137">A **Hibajelenség**, a **Terület**, a **Típus**, az **Ok**, az **Orvoslás** gomb a hibakezeléshez használt kategóriák, amelyek az eszközhiba-regisztrációk elemzéséhez és a problématerületek lehatárolásához szükségesek.</span><span class="sxs-lookup"><span data-stu-id="24332-137">The **Symptom**, **Area**, **Type**, **Cause**, and **Remedy** buttons are categorizations used in fault management to analyze asset fault registrations and pinpoint problem areas.</span></span>  

<span data-ttu-id="24332-138">**Csoportosítás tünet, eszköz és eszköztípus szerint**</span><span class="sxs-lookup"><span data-stu-id="24332-138">**Group by symptom, asset, and asset type**</span></span>

<span data-ttu-id="24332-139">A lenti képernyőfotón hozzáadtuk az **Eszköz** és **Eszköztípus** elemeket, hogy több részletet kapjunk a hibák regisztrálásával kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="24332-139">In the screenshot below, **Asset** and **Asset type** were added to provide more detail regarding fault registrations.</span></span>

- <span data-ttu-id="24332-140">A hiba tünetei most fel vannak osztva az **Eszköz** / **Eszköztípus** / **Tünet** kombinációkban.</span><span class="sxs-lookup"><span data-stu-id="24332-140">The fault symptoms are now split up in **Asset** / **Asset type** / **Symptom** combinations.</span></span>  
- <span data-ttu-id="24332-141">Ha minden hónap minden százalékát hozzáadja a **Valószínűség%** oszlopban az **Eszköz** / **Eszköztípus** / **Tünet** kombinációknak ebben a sorrendben, akkor mindegyik legfeljebb 100% lehet.</span><span class="sxs-lookup"><span data-stu-id="24332-141">In the **Probability %** column, if you add all percentages for the combination of **Asset** / **Asset type** / **Symptom** respectively, they each add up to 100%.</span></span> <span data-ttu-id="24332-142">A valószínűség az adott hibaelemzés **Tünet** regisztrációján alapul.</span><span class="sxs-lookup"><span data-stu-id="24332-142">Probability is based on **Symptom** registrations in this fault analysis.</span></span> <span data-ttu-id="24332-143">Ha egy eszköznek nagy számú sora van, de nagy százalék egy sorban jelenik meg, ezt a hibatünetet jobban meg kell vizsgálni, hogy milyen módon korlátozhatja az adott hiba miatti regisztrációk számát.</span><span class="sxs-lookup"><span data-stu-id="24332-143">If you have a large number of lines on an asset, but a large percentage stands out on a line, that would be an indication of a fault symptom to examine more closely to find a way to limit the number of registrations for that fault symptom.</span></span>

![3. ábra](media/08-controlling-and-reporting.png)

<span data-ttu-id="24332-145">**Csoportosítás két tünet, eszköz és eszköztípus szerint**</span><span class="sxs-lookup"><span data-stu-id="24332-145">**Group by two symptoms, asset, and asset type**</span></span>

<span data-ttu-id="24332-146">A lenti képernyőfotón hozzáadtuk a **Terület** elemet a **Tünet**, **Eszköz** és **Eszköztípus** elemekhez, hogy több részletet kapjunk a hibák regisztrálásával kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="24332-146">In the screenshot below, **Area** was added to **Symptom**, **Asset**, and **Asset type** to provide more detail regarding fault registrations.</span></span>

- <span data-ttu-id="24332-147">Ha minden hónap minden százalékát hozzáadja a **Valószínűség%** oszlopban az **Eszköz** / **Eszköztípus** / **Tünet** kombinációt az eszköznek, akkor mindegyik legfeljebb 100% lehet.</span><span class="sxs-lookup"><span data-stu-id="24332-147">In the **Probability %** column, if you add all percentages for the combination of **Asset** / **Asset type** / **Symptom** on an asset, they each add up to 100%.</span></span> <span data-ttu-id="24332-148">A valószínűség az adott hibaelemzés **Tünet** és **Terület** kombinációján alapul.</span><span class="sxs-lookup"><span data-stu-id="24332-148">Probability is based on the combination of **Symptom** and **Area** in this fault analysis.</span></span> <span data-ttu-id="24332-149">Ha egy eszköznek nagy számú sora van, de nagy százalék egy sorban jelenik meg, ezt a hibaterületet jobban meg kell vizsgálni, hogy milyen módon korlátozhatja az adott hibaterület miatti regisztrációk számát.</span><span class="sxs-lookup"><span data-stu-id="24332-149">If you have a large number of lines on an asset, but a large percentage stands out on a line, that would be an indication of a fault area to examine more closely to find a way to limit the number of registrations for that fault area.</span></span>  

![4. ábra](media/09-controlling-and-reporting.png)

<span data-ttu-id="24332-151">**Csoportosítás három tünet, eszköz és eszköztípus szerint**</span><span class="sxs-lookup"><span data-stu-id="24332-151">**Group by three symptom, asset, and asset type**</span></span>

<span data-ttu-id="24332-152">A lenti képernyőfotón a **Típus** lett hozzáadva, és megjelenik a példaként használt legrészletesebb számítás.</span><span class="sxs-lookup"><span data-stu-id="24332-152">In the screenshot below, **Type** was added, and the most detailed calculation in this example is shown.</span></span>
 
- <span data-ttu-id="24332-153">Ha minden hónap minden százalékát hozzáadja a **Valószínűség%** oszlopban az **Eszköz** / **Eszköztípus** / **Tünet** kombinációt az eszköznek, akkor mindegyik legfeljebb 100% lehet.</span><span class="sxs-lookup"><span data-stu-id="24332-153">In the **Probability %** column, if you add all percentages for the combination of **Asset** / **Asset type** / **Symptom** on an asset, they each add up to 100%.</span></span> <span data-ttu-id="24332-154">A valószínűség az adott hibaelemzés **Tünet**, **Terület** és **Típus** kombinációján alapul.</span><span class="sxs-lookup"><span data-stu-id="24332-154">Probability is based on the combination of **Symptom**, **Area**, and **Type** in this fault analysis.</span></span> <span data-ttu-id="24332-155">Ha egy eszköznek nagy számú sora van, de nagy százalék egy sorban jelenik meg, ezt a hibatípust jobban meg kell vizsgálni, hogy milyen módon korlátozhatja az adott hibatípus regisztrációinak számát.</span><span class="sxs-lookup"><span data-stu-id="24332-155">If you have a large number of lines on an asset, but a large percentage stands out on a line, that would be an indication of a fault type to examine more closely to find a way to limit the number of registrations on that fault type.</span></span>

![5. ábra](media/10-controlling-and-reporting.png)


>[!NOTE]
><span data-ttu-id="24332-157">A munkarendeléseken és a karbantartási kérelmeken létrehozott összes hibaregisztráció áttekintéséhez kattintson ide: **Eszközkezelés** > **Lekérdezések** > **Eszközhiba** > **Eszközhibák**.</span><span class="sxs-lookup"><span data-stu-id="24332-157">For an overview of all fault registrations created on work orders and maintenance requests, click **Asset management** > **Inquiries** > **Asset fault** > **Asset faults**.</span></span> <span data-ttu-id="24332-158">Az **Eszközhibák** oldalon válasszon ki egy eszközhiba-regisztrációt, és a **Kapcsolódó információ** ablaktábla kibontásával megtekintheti a kapcsolódó munkarendeléssel vagy karbantartási kérelemmel kapcsolatos információkat.</span><span class="sxs-lookup"><span data-stu-id="24332-158">On the **Asset faults** page, select an asset fault registration and expand the **Related information** pane to see information regarding the related work order or maintenance request.</span></span>

