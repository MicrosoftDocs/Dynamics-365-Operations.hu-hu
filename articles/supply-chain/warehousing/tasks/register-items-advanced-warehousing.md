---
title: Cikkek regisztrálása speciális raktározásra engedélyezett cikkre, cikkérkeztetési napló használatával
description: Ez az eljárás megmutatja, hogyan regisztrálhat cikkeket a cikkérkeztetési napló segítségével, ha a készletkezelési folyamatban speciális raktárkezelést használ.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSJournalTable, WMSJournalCreate, WHSLicensePlate
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2550e32db8b0d769f62c13654aa1dc1d201388ff
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3148329"
---
# <a name="register-items-for-an-advanced-warehousing-enabled-item-using-an-item-arrival-journal"></a><span data-ttu-id="722c0-103">Cikkek regisztrálása speciális raktározásra engedélyezett cikkre, cikkérkeztetési napló használatával</span><span class="sxs-lookup"><span data-stu-id="722c0-103">Register items for an advanced warehousing enabled item using an item arrival journal</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="722c0-104">Ez az eljárás megmutatja, hogyan regisztrálhat cikkeket a cikkérkeztetési napló segítségével, ha a készletkezelési folyamatban speciális raktárkezelést használ.</span><span class="sxs-lookup"><span data-stu-id="722c0-104">This procedure shows you how to register items using the item arrival journal when you are using advanced warehouse management processes.</span></span> <span data-ttu-id="722c0-105">Ezt általában egy bevételezési adminisztrátor végzi.</span><span class="sxs-lookup"><span data-stu-id="722c0-105">This would usually be done by a receiving clerk.</span></span> 

<span data-ttu-id="722c0-106">Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is futtathatja.</span><span class="sxs-lookup"><span data-stu-id="722c0-106">You can run this procedure in demo data company USMF, or on your own data.</span></span> <span data-ttu-id="722c0-107">Az útmutató elkezdése előtt jóváhagyott beszerzési rendelésre van szüksége nyitott beszerzésirendelés-sorral.</span><span class="sxs-lookup"><span data-stu-id="722c0-107">You need to have a confirmed purchase order with an open purchase order line before you start this guide.</span></span> <span data-ttu-id="722c0-108">A sorban szereplő cikknek raktározottnak kell lennie, és nem használhat termékváltozatokat, és nem lehet nyomon követési dimenziója.</span><span class="sxs-lookup"><span data-stu-id="722c0-108">The item on the line must be stocked, and it must not use product variants, and must not have tracking dimensions.</span></span> <span data-ttu-id="722c0-109">A cikket egy raktárkezelési folyamatra képes tárolásidimenzió-csoporthoz kell hozzárendelni.</span><span class="sxs-lookup"><span data-stu-id="722c0-109">And the item needs to be associated with a warehouse management process enabled storage dimension group.</span></span> <span data-ttu-id="722c0-110">A használt raktár számára engedélyezni kell a raktárkezelési folyamatot és a használt helynek azonosítótáblás szabályozásúnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="722c0-110">The warehouse that's used must be enabled for warehouse management processes and the location that you use for receiving must be license plate controlled.</span></span> <span data-ttu-id="722c0-111">Ha USMF-et használ, a beszerzési megrendeléshez használhatja a 1001-es vállalati számlát, az 51-es raktárat, és az M9200 számú cikket.</span><span class="sxs-lookup"><span data-stu-id="722c0-111">If you're using USMF, you can use company account 1001, Warehouse 51, and item M9200 to create your PO.</span></span> 

<span data-ttu-id="722c0-112">Jegyezze fel a beszerzési rendelés létrehozásakor a számot, valamint a cikkszámot és a helyet, amelyet a beszerzési rendelési sorhoz használt.</span><span class="sxs-lookup"><span data-stu-id="722c0-112">Make a note of the number of the purchase order that you create, and also note the item number and the site that you used for your purchase order line.</span></span>


## <a name="create-an-item-arrival-journal-header"></a><span data-ttu-id="722c0-113">Cikkérkeztetési napló fejlécének létrehozása</span><span class="sxs-lookup"><span data-stu-id="722c0-113">Create an item arrival journal header</span></span>
1. <span data-ttu-id="722c0-114">Ugorjon a Cikkérkeztetés pontra.</span><span class="sxs-lookup"><span data-stu-id="722c0-114">Go to Item arrival.</span></span>
2. <span data-ttu-id="722c0-115">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="722c0-115">Click New.</span></span>
3. <span data-ttu-id="722c0-116">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="722c0-116">In the Name field, type a value.</span></span>
    * <span data-ttu-id="722c0-117">Az USMF használata esetén beírhatja a „WHS” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="722c0-117">If you are using USMF, you can type WHS.</span></span> <span data-ttu-id="722c0-118">Ha más adatokat használ, a kiválasztott naplót az alábbiak szerint kell beállítania: A Kitárolási hely ellenőrzése legyen a Nem beállításon, és a Karanténkezelés legyen a Nem beállításon.</span><span class="sxs-lookup"><span data-stu-id="722c0-118">If you're using other data, the journal whose name you choose has to have the following properties: Check picking location must be set to No, and Quarantine management must be set to No.</span></span>  
4. <span data-ttu-id="722c0-119">Érték beírása a Szám mezőbe.</span><span class="sxs-lookup"><span data-stu-id="722c0-119">In the Number field, type a value.</span></span>
5. <span data-ttu-id="722c0-120">Érték beírása a Telephely mezőbe.</span><span class="sxs-lookup"><span data-stu-id="722c0-120">In the Site field, type a value.</span></span>
    * <span data-ttu-id="722c0-121">Válassza ki a helyet, amelyet a beszerzési rendelési sorhoz használt.</span><span class="sxs-lookup"><span data-stu-id="722c0-121">Select the site that you used for your purchase order line.</span></span> <span data-ttu-id="722c0-122">Ez egy alapértelmezett értéket biztosít a napló minden sorához.</span><span class="sxs-lookup"><span data-stu-id="722c0-122">This will serve as a default value, which will default to all lines in the journal.</span></span> <span data-ttu-id="722c0-123">Ha az 51-es raktárt használta USMF-hez, válassza az 5-ös helyet.</span><span class="sxs-lookup"><span data-stu-id="722c0-123">If you used warehouse 51 in USMF, choose site 5.</span></span>  
6. <span data-ttu-id="722c0-124">Érték beírása a Raktár mezőbe.</span><span class="sxs-lookup"><span data-stu-id="722c0-124">In the Warehouse field, type a value.</span></span>
    * <span data-ttu-id="722c0-125">Válasszon ki egy érvényes raktárat a kiválasztott helyhez.</span><span class="sxs-lookup"><span data-stu-id="722c0-125">Select a valid warehouse for the site that you've selected.</span></span> <span data-ttu-id="722c0-126">Ez egy alapértelmezett értéket biztosít a napló minden sorához.</span><span class="sxs-lookup"><span data-stu-id="722c0-126">This will serve as a default value, which will default to all lines in the journal.</span></span> <span data-ttu-id="722c0-127">Ha az USMF-ben a példaértékeket használja, válassza az 51-et.</span><span class="sxs-lookup"><span data-stu-id="722c0-127">If you're using the example values in USMF, select 51.</span></span>  
7. <span data-ttu-id="722c0-128">Írjon be egy értéket a Hely mezőbe.</span><span class="sxs-lookup"><span data-stu-id="722c0-128">In the Location field, type a value.</span></span>
    * <span data-ttu-id="722c0-129">Válasszon ki egy érvényes helyet a kiválasztott raktárban.</span><span class="sxs-lookup"><span data-stu-id="722c0-129">Select a valid location in the warehouse that you've selected.</span></span> <span data-ttu-id="722c0-130">A helyhez hozzárendelt helyprofil kell, amelyet az azonosítótábla vezérel.</span><span class="sxs-lookup"><span data-stu-id="722c0-130">The location has to be associated with a location profile, which is license plate controlled.</span></span> <span data-ttu-id="722c0-131">Ez egy alapértelmezett értéket biztosít a napló minden sorához.</span><span class="sxs-lookup"><span data-stu-id="722c0-131">This will serve as a default value, which will default to all lines in the journal.</span></span> <span data-ttu-id="722c0-132">Ha az USMF-ben a példaértékeket használja, válassza a Bulk-008-et.</span><span class="sxs-lookup"><span data-stu-id="722c0-132">If you're using the example values in USMF, select Bulk-008.</span></span>  
8. <span data-ttu-id="722c0-133">Kattintson a jobb gombbal a legördülő lista nyilára az Azonosítótábla mezőben, és válassza a Részletek megtekintése lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="722c0-133">Right-click on the drop-down arrow in the License plate field and then select View details.</span></span>
9. <span data-ttu-id="722c0-134">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="722c0-134">Click New.</span></span>
10. <span data-ttu-id="722c0-135">Érték beírása az Azonosítótábla mezőbe.</span><span class="sxs-lookup"><span data-stu-id="722c0-135">In the License plate field, type a value.</span></span>
    * <span data-ttu-id="722c0-136">Jegyezze fel az értéket.</span><span class="sxs-lookup"><span data-stu-id="722c0-136">Make a note of the value.</span></span>  
11. <span data-ttu-id="722c0-137">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="722c0-137">Click Save.</span></span>
12. <span data-ttu-id="722c0-138">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="722c0-138">Close the page.</span></span>
13. <span data-ttu-id="722c0-139">Érték beírása az Azonosítótábla mezőbe.</span><span class="sxs-lookup"><span data-stu-id="722c0-139">In the License plate field, type a value.</span></span>
    * <span data-ttu-id="722c0-140">Adja meg az újonnan létrehozott azonosítótábla értékét.</span><span class="sxs-lookup"><span data-stu-id="722c0-140">Enter the value of the license plate that you just created.</span></span> <span data-ttu-id="722c0-141">Ez egy alapértelmezett értéket biztosít a napló minden sorához.</span><span class="sxs-lookup"><span data-stu-id="722c0-141">This will serve as a default value, which will default to all lines in the journal.</span></span>  
14. <span data-ttu-id="722c0-142">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="722c0-142">Click OK.</span></span>

## <a name="add-a-line"></a><span data-ttu-id="722c0-143">Sor hozzáadása</span><span class="sxs-lookup"><span data-stu-id="722c0-143">Add a line</span></span>
1. <span data-ttu-id="722c0-144">Kattintson az Új sor hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="722c0-144">Click Add line.</span></span>
2. <span data-ttu-id="722c0-145">A cikkmezőbe írjon egy értéket.</span><span class="sxs-lookup"><span data-stu-id="722c0-145">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="722c0-146">Adja meg a cikkszámot, amelyet a beszerzési rendelés sorban használt.</span><span class="sxs-lookup"><span data-stu-id="722c0-146">Enter the item number that you used on the purchase order line.</span></span>  
3. <span data-ttu-id="722c0-147">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="722c0-147">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="722c0-148">Adja meg a regisztrálandó mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="722c0-148">Enter the quantity that you want to register.</span></span>  
    * <span data-ttu-id="722c0-149">A Dátum mező határozza meg, hogy mikor lesz a cikk elérhető mennyisége regisztrálva a készletbe.</span><span class="sxs-lookup"><span data-stu-id="722c0-149">The Date field determines the date on which the on-hand quantity of this item will be registered in the inventory.</span></span>  
    * <span data-ttu-id="722c0-150">Az Adagazonosítót kitölti a rendszer, ha egyedileg azonosítható a megadott adatok alapján.</span><span class="sxs-lookup"><span data-stu-id="722c0-150">The lot ID will be populated by the system if it can be uniquely identified from the information provided.</span></span> <span data-ttu-id="722c0-151">Ellenkező esetben manuálisan kell hozzáadni.</span><span class="sxs-lookup"><span data-stu-id="722c0-151">Otherwise you will have to add this manually.</span></span> <span data-ttu-id="722c0-152">Ez a mező kötelező, egy adott forrásbizonylatsorhoz kapcsolja a regisztrációt.</span><span class="sxs-lookup"><span data-stu-id="722c0-152">This is a mandatory field, which links this registration to a specific source document line.</span></span>  

## <a name="complete-the-registration"></a><span data-ttu-id="722c0-153">Véglegesítse a regisztrációt.</span><span class="sxs-lookup"><span data-stu-id="722c0-153">Complete the registration</span></span>
1. <span data-ttu-id="722c0-154">Kattintson az Érvényesítés gombra.</span><span class="sxs-lookup"><span data-stu-id="722c0-154">Click Validate.</span></span>
    * <span data-ttu-id="722c0-155">Ez ellenőrzi, hogy a napló feladásra kész.</span><span class="sxs-lookup"><span data-stu-id="722c0-155">This checks that the journal is ready to be posted.</span></span> <span data-ttu-id="722c0-156">Ha az ellenőrzés sikertelen, a hibákat helyre kell állítani a napló feladása előtt.</span><span class="sxs-lookup"><span data-stu-id="722c0-156">If the validation fails you will need to fix the errors before you can post the journal.</span></span>  
2. <span data-ttu-id="722c0-157">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="722c0-157">Click OK.</span></span>
    * <span data-ttu-id="722c0-158">Ha az OK gombra kattintott, ellenőrizze az üzenetet.</span><span class="sxs-lookup"><span data-stu-id="722c0-158">After you clicked OK, check the message.</span></span> <span data-ttu-id="722c0-159">Egy üzenet látható, amely arról tájékoztat, hogy a napló rendben van.</span><span class="sxs-lookup"><span data-stu-id="722c0-159">There should be a message saying that the journal is OK.</span></span>  
3. <span data-ttu-id="722c0-160">Kattintson a Feladás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="722c0-160">Click Post.</span></span>
4. <span data-ttu-id="722c0-161">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="722c0-161">Click OK.</span></span>
    * <span data-ttu-id="722c0-162">Ha az OK gombra kattintott, ellenőrizze az üzenetsávot.</span><span class="sxs-lookup"><span data-stu-id="722c0-162">After you have clicked OK, check the message bar.</span></span> <span data-ttu-id="722c0-163">Egy üzenet látható, amely arról tájékoztat, hogy a művelet befejeződött.</span><span class="sxs-lookup"><span data-stu-id="722c0-163">There should be a message saying that the operation completed.</span></span>  
5. <span data-ttu-id="722c0-164">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="722c0-164">Close the page.</span></span>

