---
title: Munkaóra-ellenőrzés
description: Ez a témakör az Eszközkezelés munkaóra-ellenőrzését ismerteti.
author: josaw1
manager: tfehr
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 4ba1c9548ac7ad54a459f42fd9f8f20c6936f14c
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3216368"
---
# <a name="work-hour-control"></a><span data-ttu-id="71940-103">Munkaóra-ellenőrzés</span><span class="sxs-lookup"><span data-stu-id="71940-103">Work hour control</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="71940-104">Az eszközkezelésben kiszámíthatja az órákat, amelyekkel áttekintést kaphat a tényleges órákról a költségvetésben meghatározott órákkal szemben az eszközökön, munkavégzési helyszínekn vagy munkarendeléseken.</span><span class="sxs-lookup"><span data-stu-id="71940-104">In Asset Management, you can calculate hours to get an overview of actual hours compared to budget hours on assets, functional locations, or work orders.</span></span> <span data-ttu-id="71940-105">A tényleges órák a feladott tranzakciókon alapulnak.</span><span class="sxs-lookup"><span data-stu-id="71940-105">Actual hours are based on posted transactions.</span></span>

## <a name="work-hour-control-for-assets-functional-locations-and-work-orders"></a><span data-ttu-id="71940-106">Munkaóra-ellenőrzés az eszközökhöz, a munkavégzési helyszínekhez és a munkarendelésekhez</span><span class="sxs-lookup"><span data-stu-id="71940-106">Work hour control for assets, functional locations, and work orders</span></span>

<span data-ttu-id="71940-107">Az eszközökre, munkavégzési helyszínekre és munkarendelésekre vonatkozó számítások szinte megegyeznek.</span><span class="sxs-lookup"><span data-stu-id="71940-107">The calculations made for assets, functional locations, and work orders are almost identical.</span></span> <span data-ttu-id="71940-108">Az egyetlen különbség az, hogy az eszközök és munkavégzési helyszínek esetén a számításban szerepelnek aleszközök és al-munkavégzési helyszínek is.</span><span class="sxs-lookup"><span data-stu-id="71940-108">Only difference is that for assets and functional locations, you can also include sub assets and sub locations in your calculation.</span></span> <span data-ttu-id="71940-109">A dátum a tranzakció dátuma, amikor a regisztráció rögzítése megtörtént.</span><span class="sxs-lookup"><span data-stu-id="71940-109">The date is the transaction date when the registration was recorded.</span></span>

1. <span data-ttu-id="71940-110">Kattintson az **Eszközkezelés** > **Lekérdezések** > **Eszközök** > **Eszközórák ellenőrzése** vagy **Munkavégzési helyszín óráinak ellenőrzése** elemre, vagy az **Eszközkezelés** > **Lekérdezések** > **Munkarendelések** > **Munkarendelések óráinak ellenőzése** elemre.</span><span class="sxs-lookup"><span data-stu-id="71940-110">Click **Asset management** > **Inquiries** > **Assets** > **Asset hour control** or **Functional location hour control**, or **Asset management** > **Inquiries** > **Work orders** > **Work order hour control**.</span></span>

2. <span data-ttu-id="71940-111">Az **Eszközórák ellenőrzése** párbeszédpanelen, .</span><span class="sxs-lookup"><span data-stu-id="71940-111">In the **Asset hour control** dialog, .</span></span>

3. <span data-ttu-id="71940-112">Az **Eszközórák ellenőrzése** / **Munkavégzési helyszín óráinak ellenőrzése** / **Munkarendelés óráinak ellenőrzése** párbeszédpanelen válassza ki a számítási időszakot a **Nyitó dátum** és a **Záró dátum** mezőkben.</span><span class="sxs-lookup"><span data-stu-id="71940-112">In the **Asset hour control** / **Functional location hour control** / **Work order hour control** dialog, select a period to be calculated in the **From date** and **To date** fields.</span></span>

4. <span data-ttu-id="71940-113">Szükség szerint válasszon egy **Pénzügyi dimenziókészlet** elemet, amit szerepeltetni szeretne a számításban.</span><span class="sxs-lookup"><span data-stu-id="71940-113">If required, select a **Financial dimension set** to be included in the calculation.</span></span>

5. <span data-ttu-id="71940-114">Ha a nulla órát tartalmazó eredményeket nem szeretné megjeleníteni, állítsa a **Nulla kihagyása** választógombot „Igen” értékre.</span><span class="sxs-lookup"><span data-stu-id="71940-114">Select "Yes" on the **Skip zero** toggle button if you don't want to show results containing zero hours.</span></span>

6. <span data-ttu-id="71940-115">A **Szint** mezőben megadhatja, hogy az óraellenőrzési sorok milyen részletesen jelenítsék meg a munkavégzési helyszíneket.</span><span class="sxs-lookup"><span data-stu-id="71940-115">You can use the **Level** field to indicate how detailed you want the hour control lines to be regarding functional locations.</span></span> 

    <span data-ttu-id="71940-116">Ha például az „1” értéket adja meg a mezőben, és többszintű struktúrát használ a munkavégzési helyszínek hierarchiájához, akkor a munkavégzési helyszínekhez tartozó óraellenőrzési sorok a legfelső szinten jelennek meg, így a sorban szereplő órák hozzáadhatók az alacsonyabb szinten található munkavégzési helyszínekből.</span><span class="sxs-lookup"><span data-stu-id="71940-116">For example, if you insert the number "1" in the field, and you have a multi-level functional location hierarchy, all hour control lines for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> 
    
    <span data-ttu-id="71940-117">Ha a „0” értéket adja meg a **Szint** mezőben, akkor részletes eredmény jelenik meg, amely a óraellenőrzés minden sorát megjeleníti az összes olyan munkavégzési helyszínnél, amelyhez a sor kapcsolódik.</span><span class="sxs-lookup"><span data-stu-id="71940-117">If you insert the number "0" in the **Level** field, you will see a detailed result showing all hour control lines on all the functional location levels to which they are related.</span></span>

7. <span data-ttu-id="71940-118">Ha az aleszközökhöz tartozó költségeket külön sorként szeretné megjeleníteni, állítsa az **Aleszközök szerepeltetése** beállítást „Igen” értékre.</span><span class="sxs-lookup"><span data-stu-id="71940-118">Select "Yes" on the **Include sub assets** toggle button to show costs related to sub assets as separate lines.</span></span>

8. <span data-ttu-id="71940-119">Ha szűkíteni szeretné a keresést, kiválaszthat meghatározott eszközöket/munkavégzési helyszíneket/munkarendeléseket a **Szerepeltetni kívánt rekordok** gyorslapon.</span><span class="sxs-lookup"><span data-stu-id="71940-119">If you want to limit the search, you can select specific assets / functional locations / work orders on the **Records to include** FastTab.</span></span>

9. <span data-ttu-id="71940-120">Kattintson az **OK** gombra az számítás indításához.</span><span class="sxs-lookup"><span data-stu-id="71940-120">Click **OK** to start the calculation.</span></span>

10. <span data-ttu-id="71940-121">Az **Eszközórák ellenőrzése** lapon a **Csoportosítási szempont...** műveleti ablaktáblacsoportjaiban kattintson a megfelelő gombokra a költségszámításhoz kívánt részletességi szintjének a megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="71940-121">On the **Asset hour control** page, click the **Group by** buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="71940-122">A kiválasztott **Csoportosítási szempont…** ablaktáblacsoport gombjai ki vannak emelve.</span><span class="sxs-lookup"><span data-stu-id="71940-122">The selected **Group by** buttons are highlighted.</span></span> <span data-ttu-id="71940-123">A gombra kattintva aktiválhatja vagy inaktiválhatja a funkciót.</span><span class="sxs-lookup"><span data-stu-id="71940-123">Click on a button to activate or deactivate it.</span></span>

## <a name="example"></a><span data-ttu-id="71940-124">Példa</span><span class="sxs-lookup"><span data-stu-id="71940-124">Example</span></span>

<span data-ttu-id="71940-125">Az alábbi képernyőfotón az **Eszközórák ellenőrzése** számítás egyik példája látható.</span><span class="sxs-lookup"><span data-stu-id="71940-125">The screenshot below shows an example of an **Asset hour control** calculation.</span></span>

- <span data-ttu-id="71940-126">Az **Eredeti költségvetés** mezőben a munkarendelési előrejelzésből származó költségvetési órák láthatók.</span><span class="sxs-lookup"><span data-stu-id="71940-126">The **Original budget** field shows budget hours from the work order forecast.</span></span> 
- <span data-ttu-id="71940-127">A **Tényleges órák** mező a munkarendeléseken feladott órákat jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="71940-127">The **Actual hours** field shows posted hours on work orders.</span></span> 
- <span data-ttu-id="71940-128">A **Vállalt óraszám** mezőben az órák összes száma látható, amelyet a vállalat a munkarendelésekkel kapcsolatban vállalt.</span><span class="sxs-lookup"><span data-stu-id="71940-128">The **Committed hours** field shows total amount of hours that your company is committed to in relation to work orders.</span></span>

![Példa a tárgyi eszköz óraellenőrzési számítására](media/04-controlling-and-reporting.png)

<span data-ttu-id="71940-130">Az órák számításának másik módja az, ha többszörös kiválasztással kiválasztja az eszközöket az **Összes eszköz** vagy **Aktív eszközök** pontban.</span><span class="sxs-lookup"><span data-stu-id="71940-130">Another way of making an hour calculation is to multi-select assets in **All assets** or **Active assets**.</span></span> <span data-ttu-id="71940-131">Ezután kattintson az **Óraellenőrzés** gombra az **Általános** gyorslapon.</span><span class="sxs-lookup"><span data-stu-id="71940-131">Then you click the **Hour control** button on the **General** FastTab.</span></span> <span data-ttu-id="71940-132">A rendszer automatikusan beilleszti a kiválasztott eszközöket az **Eszköz** mezőbe a **Szerepeltetni kívánt rekordok** gyorslapon.</span><span class="sxs-lookup"><span data-stu-id="71940-132">The selected assets are automatically inserted in the **Asset** field on the **Records to include** FastTab.</span></span> <span data-ttu-id="71940-133">Kattintson az **OK** gombra az **Eszközórák ellenőrzése** párbeszédablakban, és megjelenik a kiválasztott eszközökre vonatkozó számítás.</span><span class="sxs-lookup"><span data-stu-id="71940-133">Click **OK** in the **Asset hour control** dialog, and the calculation for the selected assets is shown.</span></span> <span data-ttu-id="71940-134">Ugyanez az eljárás hajtható végre az **Összes munkavégzési helyszín** vagy **Aktív munkavégzési helyszínek** pontban található munkavégzési helyszíneknél, valamint a munkarendeléseknél az **Összes munkarendelés** vagy **Aktív munkarendelések** pontban.</span><span class="sxs-lookup"><span data-stu-id="71940-134">The same procedure can be done for functional locations in **All functional locations** or **Active functional locations**, and for work orders in **All work orders** or **Active work orders**.</span></span>


