---
title: Karbantartás állapota
description: Ez a témakör azt mutatja be, hogyan lehet kiszámítani a karbantartási állapotot az Eszközkezelés modulban.
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
ms.openlocfilehash: fbe2b3fd9ce63c34aedb790583dea572d3d9b079
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3205470"
---
# <a name="maintenance-status"></a><span data-ttu-id="7ce77-103">Karbantartás állapota</span><span class="sxs-lookup"><span data-stu-id="7ce77-103">Maintenance status</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="7ce77-104">Az Eszközkezelésben számítást végezhet, hogy egy adott időszakra vonatkozóan áttekintést kapjon az új, az aktív és a befejezett karbantartási kérésekről, munkarendelésekről és karbantartás miatti üzemkimaradásokról.</span><span class="sxs-lookup"><span data-stu-id="7ce77-104">In Asset Management, you can make an overview calculation for a specific period for new, active, and completed maintenance requests, work orders, and maintenance downtime activities.</span></span> <span data-ttu-id="7ce77-105">Az időszakra vonatkozóan megtekintheti az elvégzett állapotfelmérések számát is.</span><span class="sxs-lookup"><span data-stu-id="7ce77-105">You can also see the number of completed condition assessments for the same period.</span></span> <span data-ttu-id="7ce77-106">A számítással áttekintést kaphat a beérkező és a teljesített karbantartási kérésekre és munkarendelésekre vonatkozó terhelésekről.</span><span class="sxs-lookup"><span data-stu-id="7ce77-106">Use this calculation to get an overview of workload for incoming and completed maintenance requests and work orders.</span></span>

## <a name="make-a-maintenance-status-calculation"></a><span data-ttu-id="7ce77-107">Karbantartási állapot számításának elkészítése</span><span class="sxs-lookup"><span data-stu-id="7ce77-107">Make a maintenance status calculation</span></span>

1. <span data-ttu-id="7ce77-108">Kattintson az **Eszközkezelő** > **Lekérdezések** > **Karbantartás állapota** elemre.</span><span class="sxs-lookup"><span data-stu-id="7ce77-108">Click **Asset management** > **Inquiries** > **Maintenance status**.</span></span>

2. <span data-ttu-id="7ce77-109">Az **Állapot kiszámítása** párbeszédpanel **Kezdő dátum** és **Záró dátum** mezőjében válassza ki azt az időtartományt, amelyhez el szeretné végezni a számítást.</span><span class="sxs-lookup"><span data-stu-id="7ce77-109">In the **Calculate status** dialog, select the time range that you want to make the calculation in the **From date** and **To date** fields.</span></span>

3. <span data-ttu-id="7ce77-110">A **Szint** mezőben megadhatja, hogy a karbantartási sorok milyen részletesen jelenítsék meg a munkavégzési helyszíneket.</span><span class="sxs-lookup"><span data-stu-id="7ce77-110">You can use the **Level** field to indicate how detailed you want the maintenance lines to be regarding functional locations.</span></span> 

  <span data-ttu-id="7ce77-111">Ha például az „1” értéket adja meg a mezőben, és többszintű struktúrát használ a munkavégzési helyszínekhez, akkor a munkavégzési helyszínekhez tartozó karbantartási sorok a legfelső szinten jelenik meg, így a sorban szereplő állapot hozzáadható az alacsonyabb szinten található munkavégzési helyszínekből.</span><span class="sxs-lookup"><span data-stu-id="7ce77-111">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all maintenance lines for a functional location will be shown on the top level, and therefore the status on a line may be added up from functional locations located at a lower level.</span></span> 
  
  <span data-ttu-id="7ce77-112">Ha a „0” értéket adja meg a **Szint** mezőben, akkor részletes eredmény jelenik meg, amely minden karbantartási sort megjelenít az összes olyan munkavégzési helyszínnél, amelyhez a sor kapcsolódik.</span><span class="sxs-lookup"><span data-stu-id="7ce77-112">If you insert the number "0" in the **Level** field, you see a detailed result showing all maintenance lines on all the functional location levels to which they are related.</span></span>

4. <span data-ttu-id="7ce77-113">Kattintson az **OK** gombra az számítás indításához.</span><span class="sxs-lookup"><span data-stu-id="7ce77-113">Click **OK** to start the calculation.</span></span>

5. <span data-ttu-id="7ce77-114">Kattintson a **Csoportosítási szempont...** gombokra a költségszámításhoz kívánt részletességi szintjének a megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="7ce77-114">Click the **Group by** buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="7ce77-115">A kiválasztott **Csoportosítási szempont…** ablaktáblacsoport gombjai ki vannak emelve.</span><span class="sxs-lookup"><span data-stu-id="7ce77-115">The selected **Group by** buttons are highlighted.</span></span> <span data-ttu-id="7ce77-116">A gombra kattintva aktiválhatja vagy inaktiválhatja a funkciót.</span><span class="sxs-lookup"><span data-stu-id="7ce77-116">Click on a button to activate or deactivate it.</span></span>

6. <span data-ttu-id="7ce77-117">Ne felejtsen a **Frissítés** gombra kattintani frissíteni a számítást, amikor a **Csoportosítás alapja...** gombok aktiválásával vagy inaktiválásával módosítást végez, vagy új időszakhoz végez számítást.</span><span class="sxs-lookup"><span data-stu-id="7ce77-117">Remember to click the **Update** button to update the calculation each time you make changes by activating or deactivating **Group by** buttons, or by making a calculation for a new period.</span></span>

7. <span data-ttu-id="7ce77-118">Ha új karbantartási állapothoz szeretne számítást végezni, kattintson az **Állapot** elemre.</span><span class="sxs-lookup"><span data-stu-id="7ce77-118">Click **Status** if you want to create a new maintenance status calculation.</span></span>

>[!NOTE]
><span data-ttu-id="7ce77-119">A **Karbantartás állapota** részen látható eredmények csak a tényleges kezdési dátummal és idővel rendelkező karbantartási kéréseket és munkarendeléseket tartalmazzák.</span><span class="sxs-lookup"><span data-stu-id="7ce77-119">The results shown in **Maintenance status** only include maintenance requests and work orders that have an actual start date and time.</span></span> <span data-ttu-id="7ce77-120">A záró dátum és időpont üres is lehet.</span><span class="sxs-lookup"><span data-stu-id="7ce77-120">End date and time may be blank.</span></span>

## <a name="example-1"></a><span data-ttu-id="7ce77-121">1. példa</span><span class="sxs-lookup"><span data-stu-id="7ce77-121">Example 1</span></span>

<span data-ttu-id="7ce77-122">Az alábbi képernyőfotón az **Év** és a **Hónap** gomb aktiválva látható.</span><span class="sxs-lookup"><span data-stu-id="7ce77-122">In the screenshot below, the **Year** and **Month** buttons have been activated.</span></span> <span data-ttu-id="7ce77-123">Ezen **Csoportosítási szempot…** beállítások kiválasztásával havi szinten általános áttekintést kaphat a karbantartási kérésekhez és a munkarendelésekhez kapcsolódó terhelésről és teljesítményről.</span><span class="sxs-lookup"><span data-stu-id="7ce77-123">With these **Group by** options selected, you get a general overview on a monthly basis of workload and throughput related to maintenance requests and work orders.</span></span> 

![Példa a havi terhelésre](media/13-controlling-and-reporting.png)

## <a name="example-2"></a><span data-ttu-id="7ce77-125">2. példa</span><span class="sxs-lookup"><span data-stu-id="7ce77-125">Example 2</span></span>

<span data-ttu-id="7ce77-126">Az alábbi képernyőfotón a munkavégzési helyszínekkel kapcsolatos információk is hozzá lettek adva.</span><span class="sxs-lookup"><span data-stu-id="7ce77-126">In the screenshot below, information about functional locations has been added.</span></span> <span data-ttu-id="7ce77-127">Most összehasonlíthatja a többek között földrajzi helyeket, gyárakat vagy munkaterületeket jelölő munkavégzési helyszínek terhelését és teljesítményét.</span><span class="sxs-lookup"><span data-stu-id="7ce77-127">Now it is possible to compare workload and throughput across functional locations, which may represent geographical locations, factories, or work areas.</span></span> 

![Példa a munkavégzési helyszíneket tartalmazó havi terhelésre](media/14-controlling-and-reporting.png)

