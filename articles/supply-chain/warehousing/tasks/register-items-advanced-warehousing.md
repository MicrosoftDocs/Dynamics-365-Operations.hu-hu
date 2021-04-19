---
title: Cikkek regisztrálása speciális raktározásra engedélyezett cikkre, cikkérkeztetési napló használatával
description: Ez a témakör egy olyan forgatókönyvet mutat be, hogy hogyan regisztrálhat cikkeket a cikkérkeztetési napló segítségével, ha a készletkezelési folyamatban speciális raktárkezelést használ.
author: ShylaThompson
ms.date: 03/24/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WMSJournalTable, WMSJournalCreate, WHSLicensePlate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c58aa1cec6c0bfe33fa1ef90267dcd8ac1218157
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5830834"
---
# <a name="register-items-for-an-advanced-warehousing-enabled-item-using-an-item-arrival-journal"></a><span data-ttu-id="a4ae1-103">Cikkek regisztrálása speciális raktározásra engedélyezett cikkre, cikkérkeztetési napló használatával</span><span class="sxs-lookup"><span data-stu-id="a4ae1-103">Register items for an advanced warehousing enabled item using an item arrival journal</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a4ae1-104">Ez a témakör egy olyan forgatókönyvet mutat be, hogy hogyan regisztrálhat cikkeket a cikkérkeztetési napló segítségével, ha a készletkezelési folyamatban speciális raktárkezelést használ.</span><span class="sxs-lookup"><span data-stu-id="a4ae1-104">This topic presents a scenario that shows how to register items using the item arrival journal when you are using advanced warehouse management processes.</span></span> <span data-ttu-id="a4ae1-105">Ezt általában egy bevételezési adminisztrátor végzi.</span><span class="sxs-lookup"><span data-stu-id="a4ae1-105">This would usually be done by a receiving clerk.</span></span>

## <a name="enable-sample-data"></a><span data-ttu-id="a4ae1-106">Mintaadatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="a4ae1-106">Enable sample data</span></span>

<span data-ttu-id="a4ae1-107">Ha a témakörben megadott mintarekordokat és értékeket használva szeretne végigmenni ezen a forgatókönyvön, olyan rendszert kell használnia, amelyben telepítve vannak a szabványos bemutatóadatok, és mielőtt hozzákezd, ki kell választania az *USMF* jogi személyt.</span><span class="sxs-lookup"><span data-stu-id="a4ae1-107">To work through this scenario using the sample records and values specified in this topic, you must be using a system where the standard demo data is installed, and you must select the *USMF* legal entity before you begin.</span></span>

<span data-ttu-id="a4ae1-108">Ehelyett a saját adatokból származó értékeket behelyettesítésével is dolgozhat, feltéve, hogy rendelkezésre állnak a következő adatok:</span><span class="sxs-lookup"><span data-stu-id="a4ae1-108">You can instead work through this scenario by substituting values from your own data provided that you have the following data available:</span></span>

- <span data-ttu-id="a4ae1-109">Rendelkeznie kell egy visszaigazolt beszerzési rendeléssel, amelyhez nyitott beszerzésirendelés-sor tartozik.</span><span class="sxs-lookup"><span data-stu-id="a4ae1-109">You must have a confirmed purchase order with an open purchase order line.</span></span>
- <span data-ttu-id="a4ae1-110">A sorban szereplő cikket raktárazni kell.</span><span class="sxs-lookup"><span data-stu-id="a4ae1-110">The item on the line must be stocked.</span></span> <span data-ttu-id="a4ae1-111">Nem használhat termékváltozatokat, és nem használhat nyomon követési dimenziókat.</span><span class="sxs-lookup"><span data-stu-id="a4ae1-111">It must not use product variants, and must not have tracking dimensions.</span></span>
- <span data-ttu-id="a4ae1-112">A cikket olyan tárolásidimenzió-csoporthoz kell társítani, amelynél engedélyezve van a raktárkezelési folyamat.</span><span class="sxs-lookup"><span data-stu-id="a4ae1-112">The item must be associated with a storage dimension group that has warehouse management process enabled.</span></span>
- <span data-ttu-id="a4ae1-113">A használt raktár számára engedélyezni kell a raktárkezelési folyamatot és a használt helynek azonosítótáblás szabályozásúnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="a4ae1-113">The warehouse that's used must be enabled for warehouse management processes and the location that you use for receiving must be license plate controlled.</span></span>

## <a name="create-an-item-arrival-journal-header-that-uses-warehouse-management"></a><span data-ttu-id="a4ae1-114">Raktárkezelést használó cikkérkezési naplófejléc létrehozása</span><span class="sxs-lookup"><span data-stu-id="a4ae1-114">Create an item arrival journal header that uses warehouse management</span></span>

<span data-ttu-id="a4ae1-115">A következő helyzet bemutatja, hogyan lehet létrehozni a raktárkezelést használó cikkérkezési naplófejléceket:</span><span class="sxs-lookup"><span data-stu-id="a4ae1-115">The following scenario shows how to create an item arrival journal header that uses warehouse management:</span></span>

1. <span data-ttu-id="a4ae1-116">Győződjön meg róla, hogy a rendszer olyan visszaigazolt beszerzési rendelést tartalmaz, amely megfelel az előző szakaszban meghatározott követelményeknek.</span><span class="sxs-lookup"><span data-stu-id="a4ae1-116">Make sure your system contains a confirmed purchase order that fulfils the requirements outlined in the previous section.</span></span> <span data-ttu-id="a4ae1-117">Ez az eset az *USMF* vállalatra, az *1001*-es szállítói számlára és az *51*-es raktárra vonatkozó beszerzési rendelést használ, amelyben szerepel egy rendelési sor a *M9200* cikkszámhoz *10 PL* (10 raklap) mennyiség.</span><span class="sxs-lookup"><span data-stu-id="a4ae1-117">This scenario uses a purchase order for company *USMF*, vendor account *1001*, warehouse *51*, with an order line for *10 PL* (10 pallets) of item number *M9200*.</span></span>
1. <span data-ttu-id="a4ae1-118">Jegyezze fel a beszerzési rendelés számát, amit használni fog.</span><span class="sxs-lookup"><span data-stu-id="a4ae1-118">Make a note of the purchase order number that you will use.</span></span>
1. <span data-ttu-id="a4ae1-119">Lépjen a **Készletgazdálkodás \> Naplóbejegyzések \> Cikkérkeztetés \> Cikkérkeztetés** menüpontra.</span><span class="sxs-lookup"><span data-stu-id="a4ae1-119">Go to **Inventory management \> Journal entries \> Item arrival \> Item arrival**.</span></span>
1. <span data-ttu-id="a4ae1-120">A Művelet panelen válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a4ae1-120">Select **New** on the Action Pane.</span></span>
1. <span data-ttu-id="a4ae1-121">Megjelenik a **Raktárkezelési napló létrehozása** párbeszédpanel.</span><span class="sxs-lookup"><span data-stu-id="a4ae1-121">The **Create warehouse management journal** dialog box opens.</span></span> <span data-ttu-id="a4ae1-122">A **Név** mezőben válassza ki a napló nevét.</span><span class="sxs-lookup"><span data-stu-id="a4ae1-122">Select a journal name in the **Name** field.</span></span>
    - <span data-ttu-id="a4ae1-123">Az *USMF* mintaadatok használata esetén válassza az *WHS* lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a4ae1-123">If you are using *USMF* sample data, select *WHS*.</span></span>
    - <span data-ttu-id="a4ae1-124">Ha saját adatait használja, akkor a választott naplóban a **Kitárolási hely ellenőrzése** beállítás értéke legyen *Nem*, a **Karanténkezelés** beállítása pedig *Nem* lehet.</span><span class="sxs-lookup"><span data-stu-id="a4ae1-124">If you're using your own data, the journal you choose must have **Check picking location** set to *No* and **Quarantine management** set to *No*.</span></span>
1. <span data-ttu-id="a4ae1-125">A **Hivatkozás** beállítása legyen *Beszerzési rendelés*.</span><span class="sxs-lookup"><span data-stu-id="a4ae1-125">Set **Reference** to *Purchase order*.</span></span>
1. <span data-ttu-id="a4ae1-126">A **Számlaszám** értéke legyen *1001*.</span><span class="sxs-lookup"><span data-stu-id="a4ae1-126">Set **Account number** to *1001*.</span></span>
1. <span data-ttu-id="a4ae1-127">Állítsa be a **Szám** értékét azon beszerzési rendelés számára, amelyet meghatározott ehhez a gyakorlathoz.</span><span class="sxs-lookup"><span data-stu-id="a4ae1-127">Set **Number** to the number of the purchase order that you identified for this exercise.</span></span>

    <span data-ttu-id="a4ae1-128">![Cikkbeérkezési napló](../media/item-arrival-journal-header.png "Cikkbeérkezési napló")</span><span class="sxs-lookup"><span data-stu-id="a4ae1-128">![Item arrival journal](../media/item-arrival-journal-header.png "Item arrival journal")</span></span>

1. <span data-ttu-id="a4ae1-129">A naplófejléc létrehozásához kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="a4ae1-129">Select the **OK** to create the journal header.</span></span>
1. <span data-ttu-id="a4ae1-130">A **Naplósorok** szakaszban válassza a **Sor hozzáadása** lehetőséget, és írja be a következő adatokat:</span><span class="sxs-lookup"><span data-stu-id="a4ae1-130">In the **Journal lines** section, select **Add line** and enter the following data:</span></span>
    - <span data-ttu-id="a4ae1-131">**Cikkszám** – értéke legyen *M9200*.</span><span class="sxs-lookup"><span data-stu-id="a4ae1-131">**Item number** – Set to *M9200*.</span></span> <span data-ttu-id="a4ae1-132">A **Telephely**, a **Raktár** és a **Mennyiség** beállítása a 10 raklap (1000 ea.) készlettranzakció-adatai alapján történik.</span><span class="sxs-lookup"><span data-stu-id="a4ae1-132">The **Site**, **Warehouse**, and **Quantity** will get set based on the inventory transaction data for the 10 pallets (1000 ea.).</span></span>
    - <span data-ttu-id="a4ae1-133">**Hely** – értéke *001*.</span><span class="sxs-lookup"><span data-stu-id="a4ae1-133">**Location** – Set to  *001*.</span></span> <span data-ttu-id="a4ae1-134">Ez a hely nem követi az azonosítótáblákat.</span><span class="sxs-lookup"><span data-stu-id="a4ae1-134">This specific location does not track license plates.</span></span>

    <span data-ttu-id="a4ae1-135">![Cikkérkeztetési naplósor](../media/item-arrival-journal-line.png "Cikkérkeztetési naplósor")</span><span class="sxs-lookup"><span data-stu-id="a4ae1-135">![Item arrival journal line](../media/item-arrival-journal-line.png "Item arrival journal line")</span></span>

    > [!NOTE]
    > <span data-ttu-id="a4ae1-136">A **Dátum** mező határozza meg, hogy mikor lesz a cikk elérhető mennyisége regisztrálva a készletbe.</span><span class="sxs-lookup"><span data-stu-id="a4ae1-136">The **Date** field determines the date on which the on-hand quantity of this item will be registered in the inventory.</span></span>  
    >
    > <span data-ttu-id="a4ae1-137">Az **Adagazonosítót** kitölti a rendszer, ha egyedileg azonosítható a megadott adatok alapján.</span><span class="sxs-lookup"><span data-stu-id="a4ae1-137">The **Lot ID** will be populated by the system if it can be uniquely identified from the information provided.</span></span> <span data-ttu-id="a4ae1-138">Ellenkező esetben manuálisan kell megadni.</span><span class="sxs-lookup"><span data-stu-id="a4ae1-138">Otherwise you will have to enter this manually.</span></span> <span data-ttu-id="a4ae1-139">Ez a mező kötelező, egy adott forrásbizonylatsorhoz kapcsolja a regisztrációt.</span><span class="sxs-lookup"><span data-stu-id="a4ae1-139">This is a required field, which links this registration to a specific source document line.</span></span>  

1. <span data-ttu-id="a4ae1-140">A Művelet panelen válassza ki az **Ellenőrzés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a4ae1-140">Select **Validate** on the Action Pane.</span></span> <span data-ttu-id="a4ae1-141">Ez ellenőrzi, hogy a napló feladásra kész.</span><span class="sxs-lookup"><span data-stu-id="a4ae1-141">This checks that the journal is ready to be posted.</span></span> <span data-ttu-id="a4ae1-142">Ha az ellenőrzés sikertelen, a hibákat helyre kell állítani a napló feladása előtt.</span><span class="sxs-lookup"><span data-stu-id="a4ae1-142">If the validation fails you will need to fix the errors before you can post the journal.</span></span>  
1. <span data-ttu-id="a4ae1-143">Megjelenik a **Napló ellenőrzése** párbeszédpanel.</span><span class="sxs-lookup"><span data-stu-id="a4ae1-143">The **Check journal** dialog box opens.</span></span> <span data-ttu-id="a4ae1-144">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a4ae1-144">Select **OK**.</span></span>
1. <span data-ttu-id="a4ae1-145">Tekintse meg az üzenetsávot.</span><span class="sxs-lookup"><span data-stu-id="a4ae1-145">Review the message bar.</span></span> <span data-ttu-id="a4ae1-146">Egy üzenet látható, amely arról tájékoztat, hogy a művelet befejeződött.</span><span class="sxs-lookup"><span data-stu-id="a4ae1-146">There should be a message denoting that the operation was completed.</span></span>  
1. <span data-ttu-id="a4ae1-147">A műveleti ablaktáblán válassza ki a **Feladás** elemet.</span><span class="sxs-lookup"><span data-stu-id="a4ae1-147">Select **Post** on the Action Pane.</span></span>
1. <span data-ttu-id="a4ae1-148">Megjelenik a **Napló feladása** párbeszédpanel.</span><span class="sxs-lookup"><span data-stu-id="a4ae1-148">The **Post journal** dialog box opens.</span></span> <span data-ttu-id="a4ae1-149">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a4ae1-149">Select **OK**.</span></span>
1. <span data-ttu-id="a4ae1-150">Tekintse meg az üzenetsávot.</span><span class="sxs-lookup"><span data-stu-id="a4ae1-150">Review the message bar.</span></span> <span data-ttu-id="a4ae1-151">Itt üzenetek láthatók, amely arról tájékoztat, hogy a művelet befejeződött.</span><span class="sxs-lookup"><span data-stu-id="a4ae1-151">There should be messages denoting that the operation completed.</span></span>
1. <span data-ttu-id="a4ae1-152">Válassza a **Funkciók > Termékbevételezés** lehetőséget a műveleti ablaktáblán a beszerzésirendelés-sor frissítéséhez és a termékbevételezés feladásához.</span><span class="sxs-lookup"><span data-stu-id="a4ae1-152">Select **Functions > Product receipt** on the Action Pane to update the purchase order line and post a product receipt.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
