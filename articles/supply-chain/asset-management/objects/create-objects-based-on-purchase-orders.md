---
title: Eszközök létrehozása beszerzési rendelések alapján
description: Ez a témakör bemutatja, hogyan hozhat létre olyan eszközelemeket tartalmazó listát, amelyet az Eszközmenedzsment területén a karbantartási feladatokhoz használt eszközök létrehozásának alapjául használhat fel.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8dd52d877ee7f862577d8bfea113f22eca03c597
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3209881"
---
# <a name="create-assets-based-on-purchase-orders"></a><span data-ttu-id="77b35-103">Eszközök létrehozása beszerzési rendelések alapján</span><span class="sxs-lookup"><span data-stu-id="77b35-103">Create assets based on purchase orders</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="77b35-104">Ez a témakör bemutatja, hogyan hozhat létre olyan eszközelemeket tartalmazó listát, amelyet az Eszközmenedzsment területén a karbantartási feladatokhoz használt eszközök létrehozásának alapjául használhat fel.</span><span class="sxs-lookup"><span data-stu-id="77b35-104">This topic explains how you can create a list of asset items that can be used as a basis for creating assets for maintenance jobs in Asset Management.</span></span> <span data-ttu-id="77b35-105">Az eszköztételek alapján megtekintheti az ezekre a cikkekre létrehozott beszerzésirendelés-sorok listáját.</span><span class="sxs-lookup"><span data-stu-id="77b35-105">Based on the asset items, you are able to view a list of the purchase order lines that have been created on those items.</span></span> <span data-ttu-id="77b35-106">Ennek a funkciónak a célja, hogy a beszerzési rendelés alapján könnyen létre lehessen hozni egy eszközt az Eszközkezelésben.</span><span class="sxs-lookup"><span data-stu-id="77b35-106">The purpose of this functionality is to easily create an asset in Asset Management based on a purchase order.</span></span>

<span data-ttu-id="77b35-107">Először be kell állítania az eszközök beszerzési rendelésből történő létrehozására szolgáló cikkeket az **Eszköztételek** helyen.</span><span class="sxs-lookup"><span data-stu-id="77b35-107">First, you set up the items to be used for creating assets from a purchase order in **Asset items**.</span></span> <span data-ttu-id="77b35-108">A beszerzésirendelés-sor létrehozása után az eszközök a **Függőben lévő eszközök** között hozhatók létre.</span><span class="sxs-lookup"><span data-stu-id="77b35-108">After creating a purchase order line, you create the assets in **Pending assets**.</span></span> <span data-ttu-id="77b35-109">Meg lehet határozni azt, hogy a beszerzési rendelés melyik szakaszában kell létrehozni az eszközt.</span><span class="sxs-lookup"><span data-stu-id="77b35-109">It is possible to decide at which stage of the purchase order the asset should be created.</span></span>


## <a name="select-asset-items"></a><span data-ttu-id="77b35-110">Eszközelemek kiválasztása</span><span class="sxs-lookup"><span data-stu-id="77b35-110">Select asset items</span></span>

1. <span data-ttu-id="77b35-111">Kattintson az **Eszközkezelés** > **Beállítások** > **Eszközök** > **Elemek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="77b35-111">Click **Asset management** > **Setup** > **Assets** > **Items**.</span></span>
2. <span data-ttu-id="77b35-112">Új eszközelem létrehozásához kattintson az **Új** gombra.</span><span class="sxs-lookup"><span data-stu-id="77b35-112">Click **New** to create a new asset item.</span></span>
3. <span data-ttu-id="77b35-113">Válassza ki a cikket a **Cikkszám** mezőben.</span><span class="sxs-lookup"><span data-stu-id="77b35-113">Select the item in the **Item number** field.</span></span> <span data-ttu-id="77b35-114">Ha elhagyja ezt a mezőt, a program automatikusan beszúrja a cikk nevét a **Terméknév** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="77b35-114">When you leave that field, the item name is automatically inserted in the **Product name** field.</span></span>
4. <span data-ttu-id="77b35-115">Az **Általános** gyorslapon válasszon ki egy eszköztípust a cikkhez.</span><span class="sxs-lookup"><span data-stu-id="77b35-115">On the **General** FastTab, select an asset type for the item.</span></span>
5. <span data-ttu-id="77b35-116">Válassza ki a cikkhez tartozó eszközgyártót és modellt.</span><span class="sxs-lookup"><span data-stu-id="77b35-116">Select asset manufacturer and model for the item.</span></span>
6. <span data-ttu-id="77b35-117">Mentse a cikket.</span><span class="sxs-lookup"><span data-stu-id="77b35-117">Save the item.</span></span>


## <a name="create-assets-from-pending-assets"></a><span data-ttu-id="77b35-118">Eszközök létrehozása függőben lévő eszközökből</span><span class="sxs-lookup"><span data-stu-id="77b35-118">Create assets from pending assets</span></span>

1. <span data-ttu-id="77b35-119">Kattintson az **Eszközkezelés** > **Általános** > **Eszközök** > **Függőben lévő eszközök** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="77b35-119">Click **Asset management** > **Common** > **Assets** > **Pending Assets**.</span></span>
2. <span data-ttu-id="77b35-120">A beszerzési rendelések frissített listája az **Eszközcikkek** helyen kiválasztott cikkek alapján jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="77b35-120">You will see an updated list of the purchase orders based on the items selected in **Asset items**.</span></span>
3. <span data-ttu-id="77b35-121">A beszerzési rendelések állapotát szűrheti, így kiválaszthatja, hogy melyik életciklus-állapotban kell létrehozni az eszközt.</span><span class="sxs-lookup"><span data-stu-id="77b35-121">You can filter the status of purchase orders to select at which lifecycle state the asset should be created.</span></span> <span data-ttu-id="77b35-122">Előfordulhat például, hogy csak akkor szeretne eszközöket létrehozni, ha egy termékbevételezés fel lett adva egy beszerzési rendelésre.</span><span class="sxs-lookup"><span data-stu-id="77b35-122">For example, you may only want to create assets when a product receipt has been posted on a purchase order.</span></span>
4. <span data-ttu-id="77b35-123">A cikkre vonatkozó részletes információk megtekintéséhez válassza ki a beszerzési rendelési sor **Hivatkozási szám** linkjét.</span><span class="sxs-lookup"><span data-stu-id="77b35-123">Select the **Reference number** link on a purchase order line to view detailed information about the item.</span></span>
5. <span data-ttu-id="77b35-124">Ha módosítani szeretné, hogy mely dimenziók jelenjenek meg a **Készletdimenziók** gyorslapon, kattintson a **Dimenziók megjelenítése** gombra, és adja meg a kívánt beállításokat.</span><span class="sxs-lookup"><span data-stu-id="77b35-124">If you want to edit which dimensions are displayed on the **Inventory dimensions** FastTab, click the **Display Dimensions** button, and make your selections.</span></span>
6. <span data-ttu-id="77b35-125">Ha beszerzésirendelés-soron alapuló eszközt szeretne létrehozni, jelölje be a jelölőnégyzetét a **Jelölés** oszlopnál ahhoz a sorhoz a listaoldalon, majd kattintson az **Eszközök létrehozása** parancsra.</span><span class="sxs-lookup"><span data-stu-id="77b35-125">If you want to create an asset based on a purchase order line, select the check box in the **Mark** column for that line on the list page, and click **Create assets**.</span></span> <span data-ttu-id="77b35-126">Ekkor megjelenik egy üzenet, amely tájékoztatja az eszközazonosítóról.</span><span class="sxs-lookup"><span data-stu-id="77b35-126">A message will be displayed informing you of the asset ID.</span></span>
7. <span data-ttu-id="77b35-127">Válassza ki az eszközt az **Összes eszköz** listából, majd kattintson a **Szerkesztés** gombra, hogy további információkat adjon hozzá az eszközhöz.</span><span class="sxs-lookup"><span data-stu-id="77b35-127">Select the asset in the **All assets** list and click **Edit** to add more information to the asset.</span></span>
8. <span data-ttu-id="77b35-128">Ha a **Függőbenlévő eszközök** mezőben törölni szeretne egy sort, mert nem szeretne létrehozni egy eszközt, akkor jelölje be a sorhoz tartozó **Jelölés** oszlopban lévő jelölőnégyzetet, majd kattintson a **Függőben lévő eszközökelvetése** parancsra.</span><span class="sxs-lookup"><span data-stu-id="77b35-128">In **Pending assets**, if you want to delete a line because you don't want to create an asset, select the check box in the **Mark** column for that line, and click **Discard pending assets**.</span></span> <span data-ttu-id="77b35-129">Ekkor megjelenik egy üzenet, amely tájékoztatja az eszközazonosítóról.</span><span class="sxs-lookup"><span data-stu-id="77b35-129">A message will be displayed informing you of the asset ID.</span></span> <span data-ttu-id="77b35-130">Nem törli a beszerzési rendelést vagy értékesítéi rendelést, csak azt a rekordot, amelyből az eszközt az **Eszközkezelésben** létrehozhatta volna.</span><span class="sxs-lookup"><span data-stu-id="77b35-130">You are not deleting the purchase order or sales order, just the record from which you could have created an asset in **Asset Management**.</span></span>

>[!NOTE]
><span data-ttu-id="77b35-131">Minden termékdimenzió (méret, szín, konfiguráció stb) automatikusan van átvíve az eszközattribútumokhoz.</span><span class="sxs-lookup"><span data-stu-id="77b35-131">All product dimensions (size, color, configuration etc.) are automatically transferred to the asset attributes.</span></span> <span data-ttu-id="77b35-132">A nyomon követési dimenziók (sorozatszám) az eszköz létrehozásakor közvetlenül az eszközben lesznek tárolva.</span><span class="sxs-lookup"><span data-stu-id="77b35-132">Tracking dimensions (serial number) are stored directly on the asset when the asset is created.</span></span>


## <a name="find-pending-assets"></a><span data-ttu-id="77b35-133">Függőben lévő eszközök megkeresése</span><span class="sxs-lookup"><span data-stu-id="77b35-133">Find pending assets</span></span>

<span data-ttu-id="77b35-134">A függőben lévő eszközök ellenőrzéséhez futtathat egy **Függőben lévő eszközszám** parancsot.</span><span class="sxs-lookup"><span data-stu-id="77b35-134">You can run a **Pending asset count** to check for pending assets.</span></span> <span data-ttu-id="77b35-135">Ez a funkció például arra használható, hogy értesítést kapjon valahányszor egy függőben lévő eszköz készen áll eszközként történő létrehozásra.</span><span class="sxs-lookup"><span data-stu-id="77b35-135">For example, this function can be used for receiving a notification each time a pending asset is ready to be created as an asset.</span></span>

1. <span data-ttu-id="77b35-136">Kattintson az **Eszközkezelés** > **Időszakos** > **Eszközök** > **Függőben lévő eszközök száma** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="77b35-136">Click **Asset management** > **Periodic** > **Assets** > **Pending asset count**.</span></span>
2. <span data-ttu-id="77b35-137">Kattintson az **Ok** gombra a feladat futtatásához, és a lista frissítéséhez a **Függőben lévő eszközök** helyen.</span><span class="sxs-lookup"><span data-stu-id="77b35-137">Click **OK** to run the job and update the list in **Pending assets**.</span></span>
3. <span data-ttu-id="77b35-138">Beállíthatja, hogy a feladat kötegelt feladatként fusson, például naponta egyszer.</span><span class="sxs-lookup"><span data-stu-id="77b35-138">You can set up this job to run as a batch job, for example, once each day.</span></span>

<span data-ttu-id="77b35-139">**Figyelmeztetés:** Ha az adatok módosulnak egy beszerzési rendelésen *miután* létrehozott egy eszközt kapcsolódó cikk alapján, ezek a módosítások nem jelennek meg az eszköznél.</span><span class="sxs-lookup"><span data-stu-id="77b35-139">**Caution:** If data is changed on a purchase order *after* you have created an asset based on the appertaining item, those changes will not be reflected on the asset.</span></span>
