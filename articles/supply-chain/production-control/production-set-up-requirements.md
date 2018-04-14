---
title: "A termelésbeállítás követelményei"
description: "Ez a cikk tájékoztatást ad a beállítási követelményekről a Gyártásvezérlés használatba vétele előtt."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProdParameters, RouteOpr, RouteOprTable, WorkCalendarTable, WorkTimeTable, WrkCtrTable
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 55561
ms.assetid: 1953059f-478d-4706-b461-25b89ace5fc3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: bcca20889fa0b79a289175ab901167509a908f3f
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---

# <a name="production-setup-requirements"></a><span data-ttu-id="19db3-103">A termelésbeállítás követelményei</span><span class="sxs-lookup"><span data-stu-id="19db3-103">Production setup requirements</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="19db3-104">Ez a cikk tájékoztatást ad a beállítási követelményekről a Gyártásvezérlés használatba vétele előtt.</span><span class="sxs-lookup"><span data-stu-id="19db3-104">This article provides information about setup requirements before you can work with Production control.</span></span> 

<span data-ttu-id="19db3-105">A gyártásvezérlés integrálva van más modulokban lévő funkciókkal.</span><span class="sxs-lookup"><span data-stu-id="19db3-105">Production control is integrated with features in other modules.</span></span> <span data-ttu-id="19db3-106">Ez a kapcsolat lehetővé, hogy módosítsa a termelési megrendeléseket és megbizonyosodjon, hogy automatikusan frissítésre kerülnek minden vonatkozó folyamatban és számításban a rendszerben.</span><span class="sxs-lookup"><span data-stu-id="19db3-106">This interconnectivity lets you change production orders and make sure that they are automatically updated in all other related processes and calculations in the system.</span></span> <span data-ttu-id="19db3-107">A következő beállítási folyamatok abban a sorrendben vannak felsorolva, amelyben teljesítenie kell őket.</span><span class="sxs-lookup"><span data-stu-id="19db3-107">The following setup processes are listed in the order that you should complete them in.</span></span>

## <a name="required-baseline-setup-in-other-modules"></a><span data-ttu-id="19db3-108">Kötelező alapbeállítás más modulokban</span><span class="sxs-lookup"><span data-stu-id="19db3-108">Required baseline setup in other modules</span></span>
<span data-ttu-id="19db3-109">Az egyéb modulokban található információkat be kell állítania, mielőtt dolgozhat a gyártásvezérléssel.</span><span class="sxs-lookup"><span data-stu-id="19db3-109">Information in other modules must be set up before you can work with Production control.</span></span> <span data-ttu-id="19db3-110">Az a beállítás a következő feladatokat tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="19db3-110">This setup includes the following tasks:</span></span>

-   <span data-ttu-id="19db3-111">Általános vállalati információk beállítása.</span><span class="sxs-lookup"><span data-stu-id="19db3-111">Set up general company information.</span></span>
-   <span data-ttu-id="19db3-112">A főkönyv beállítása.</span><span class="sxs-lookup"><span data-stu-id="19db3-112">Set up the general ledger.</span></span>
-   <span data-ttu-id="19db3-113">A cikkcsoportok meghatározása.</span><span class="sxs-lookup"><span data-stu-id="19db3-113">Define item groups.</span></span>
-   <span data-ttu-id="19db3-114">A cikkcsoportok főkönyvi számláinak beállítása.</span><span class="sxs-lookup"><span data-stu-id="19db3-114">Set up ledger accounts for item groups.</span></span>
-   <span data-ttu-id="19db3-115">A készletcikk-táblázat beállítása a készletgazdálkodásban.</span><span class="sxs-lookup"><span data-stu-id="19db3-115">Set up the inventory item table in Inventory management.</span></span>
-   <span data-ttu-id="19db3-116">Anyagjegyzékek (AJ) és az anyagjegyzék-verziók létrehozása a készletgazdálkodásban.</span><span class="sxs-lookup"><span data-stu-id="19db3-116">Create bills of materials (BOMs) and BOM versions in Inventory management.</span></span>

## <a name="required-calendar-and-resource-setup"></a><span data-ttu-id="19db3-117">Kötelező naptár- és erőforrás beállítás</span><span class="sxs-lookup"><span data-stu-id="19db3-117">Required calendar and resource setup</span></span>
<span data-ttu-id="19db3-118">Mielőtt használja a gyártásvezérlést nyissa meg a szervezeti adminisztrációt és hozzon létre és határozzon meg egy naptárat és műveleti erőforrásokat a következő sorrendben:</span><span class="sxs-lookup"><span data-stu-id="19db3-118">Before you use Production control, open Organization administration, and create and define the calendar and operations resources in the following order:</span></span>

1.  <span data-ttu-id="19db3-119">**Munkaidősablonok** – Állítsa be a munkaidősablonokat, hogy meghatározza az időket, amelyek elérhetőek a termelési ütemezés számára.</span><span class="sxs-lookup"><span data-stu-id="19db3-119">**Working time templates** – Set up working time templates to define the times that are available for production scheduling.</span></span>
2.  <span data-ttu-id="19db3-120">**Naptárak** – Állítson be munkaidő naptárakat, hogy meghatározza az év azon napjait, amelyek elérhetőek a termelésütemezés számára.</span><span class="sxs-lookup"><span data-stu-id="19db3-120">**Calendars** – Set up working time calendars to define the days of the year that are available for production scheduling.</span></span>
3.  <span data-ttu-id="19db3-121">**Erőforráscsoportok** – Állítsa be az erőforráscsoportokat, hogy csoportosítsák a műveleti erőforrásokat, hogy áttekintést kaphasson a szabad kapacitásról, amikor az ütemezést futtatja.</span><span class="sxs-lookup"><span data-stu-id="19db3-121">**Resource groups** – Set up resource groups to group the operations resources, so that you can get an overview of any free capacity when you run scheduling.</span></span> <span data-ttu-id="19db3-122">Az erőforráscsoportokat nem kell a műveleti erőforrások előtt beállítnia.</span><span class="sxs-lookup"><span data-stu-id="19db3-122">You don't have to set up resource groups before you set up operations resources.</span></span> <span data-ttu-id="19db3-123">Azonban azt javasoljuk, hogy értse az erőforrások csoportosítását, amikor gyártásvezérlést állít be.</span><span class="sxs-lookup"><span data-stu-id="19db3-123">However, we recommend that you understand how to group resources when you set up Production control.</span></span>
4.  <span data-ttu-id="19db3-124">**Erőforrások** – Állítson be műveleti erőforrásokat, hogy meghatározza az erőforrásokat, amelyek ahhoz használatosak, hogy elvégezze a termelési folyamatot és kapacitást tervezzen.</span><span class="sxs-lookup"><span data-stu-id="19db3-124">**Resources** – Set up operations resources to define the resources that are used to complete the production process and plan for capacity.</span></span>

## <a name="required-production-parameters-setup"></a><span data-ttu-id="19db3-125">Kötelező termelési paraméterek beállítása</span><span class="sxs-lookup"><span data-stu-id="19db3-125">Required production parameters setup</span></span>
<span data-ttu-id="19db3-126">**Gyártásvezérlési paraméterek** – Állítson be alapvető termelési paramétereket, hogy meghatározza, hogy a rendszer hogyan kezelje a folyamatokat és termelési rendeléseket.</span><span class="sxs-lookup"><span data-stu-id="19db3-126">**Production control parameters** – Set up basic production parameters to define how the system handles and processes production orders.</span></span> <span data-ttu-id="19db3-127">Határozz meg a termelési rendelések létrehozását, becslését, ütemezését és elhasználódását.</span><span class="sxs-lookup"><span data-stu-id="19db3-127">Define how production orders are created, estimated, scheduled, and consumed.</span></span> <span data-ttu-id="19db3-128">Kijelölheti, hogy milyen visszajelzést kíván kapni és hogy hogyan történjen a költségkönyvelés.</span><span class="sxs-lookup"><span data-stu-id="19db3-128">You can also select what kind of feedback you want and how cost accounting is done.</span></span>

## <a name="required-journal-name-identification"></a><span data-ttu-id="19db3-129">Kötelező naplónevek azonosítása</span><span class="sxs-lookup"><span data-stu-id="19db3-129">Required journal name identification</span></span>
<span data-ttu-id="19db3-130">**Termelésinapló-nevek** – Adja meg a termelésinapló-neveket, amelyek tranzakciók feljegyzésénél és feladásánál használatosak.</span><span class="sxs-lookup"><span data-stu-id="19db3-130">**Production journal names** – Specify the production journal names that are used to record and post transactions.</span></span>

## <a name="setup-if-you-use-operations"></a><span data-ttu-id="19db3-131">Beállítás műveletek használata esetén</span><span class="sxs-lookup"><span data-stu-id="19db3-131">Setup if you use operations</span></span>
<span data-ttu-id="19db3-132">A műveletek meghatározott tevékenységeket jelölnek, amelyek a befejezett cikk előállítása érdekében történnek.</span><span class="sxs-lookup"><span data-stu-id="19db3-132">Operations represent the specific activities that are completed to produce the finished product.</span></span> <span data-ttu-id="19db3-133">**Megjegyzés:** Ismernie kell a tevékenységtípusokat, amelyek szükségesek cikk előállításához és ezen tevékenységek sorrendjét és prioritásait.</span><span class="sxs-lookup"><span data-stu-id="19db3-133">**Note:** You must know the types of activities that are required in order to produce your item, and the order and priorities of those activities.</span></span> <span data-ttu-id="19db3-134">Azt is ismernie kell, hogy melyik erőforrásból mennyi kerül bevonásra.</span><span class="sxs-lookup"><span data-stu-id="19db3-134">You must also know which resources are involved, and how many.</span></span>

1.  <span data-ttu-id="19db3-135">**Műveletek** – Állítsa be a műveleteket, hogy jelöljék a feladatokat, amelyeket el kell végezni a befejezett cikk előállításának érdekében.</span><span class="sxs-lookup"><span data-stu-id="19db3-135">**Operations** – Set up operations to represent the tasks that must be completed to produce the finished item.</span></span>
2.  <span data-ttu-id="19db3-136">**Kapcsolatok** – Állítsa be a műveleti kapcsolatok, hogy részletes tulajdonságokat alakítson ki.</span><span class="sxs-lookup"><span data-stu-id="19db3-136">**Relations** – Set up operation relations to establish detailed properties.</span></span> <span data-ttu-id="19db3-137">Műveleti kapcsolatok meghatározásához kattintson a **kapcsolatok** elemre a **műveletek** oldalon.</span><span class="sxs-lookup"><span data-stu-id="19db3-137">To define operation relations, click **Relations** on the **Operations** page.</span></span>

## <a name="setup-if-you-use-routes"></a><span data-ttu-id="19db3-138">Beállítás útvonalak használata esetén</span><span class="sxs-lookup"><span data-stu-id="19db3-138">Setup if you use routes</span></span>
<span data-ttu-id="19db3-139">Ha útvonalakkal dolgozik, a műveleteket minden beállított termelési útvonalhoz meg kell határozni.</span><span class="sxs-lookup"><span data-stu-id="19db3-139">If you're working with routes, operations must be defined for every production route that you set up.</span></span> <span data-ttu-id="19db3-140">Az útvonalak kijelölik a cikk útját műveletről műveletre haladva, a folyamat indításától kezdve egészen a befejezésig.</span><span class="sxs-lookup"><span data-stu-id="19db3-140">The route represents the path that the item takes from operation to operation, from the start of the production process to the end.</span></span>

1.  <span data-ttu-id="19db3-141">**Költségkategóriák** – Állítson be költségkategóriákat, hogy meghatározza a meghatározott folyamatok és beállítási idők óránkénti költségét.</span><span class="sxs-lookup"><span data-stu-id="19db3-141">**Cost categories** – Set up cost categories to define the cost per hour of specified processes and setup times.</span></span>
2.  <span data-ttu-id="19db3-142">**Költségcsoportok** – Állítson be költségcsoportokat, hogy különböző költségszámítási módokat hozzon létre és tartson fent.</span><span class="sxs-lookup"><span data-stu-id="19db3-142">**Cost groups** – Set up cost groups to create and maintain different types of costing.</span></span>
3.  <span data-ttu-id="19db3-143">**Útvonalcsoportok** – Állítson be útvonalcsoportokat, az útvonalak csoportjainak vonatkozó paramétereinek meghatározásához.</span><span class="sxs-lookup"><span data-stu-id="19db3-143">**Route groups** – Set up route groups to define parameters that are related to groups of routes.</span></span> <span data-ttu-id="19db3-144">Be kell állítania az útvonalcsoportokat, mielőtt termelési útvonalakat tud létrehozni.</span><span class="sxs-lookup"><span data-stu-id="19db3-144">You must set up route groups before you can create production routes.</span></span>
4.  <span data-ttu-id="19db3-145">**Útvonalak** – Állítson be termelési útvonalakat, és határozzon meg alapértelmezett beállításokat, hogy irányítsa az útvonalműveletek ütemezését, költségszámítását és árképzését és hogy irányítsa az előrehaladottság jelentést.</span><span class="sxs-lookup"><span data-stu-id="19db3-145">**Routes** – Set up production routes, and define default settings to control scheduling, costing, and pricing of route operations, and to control progress reporting.</span></span>
5.  <span data-ttu-id="19db3-146">**Útvonalak** – Állítson be útvonalverziókat, hogy engedélyezze a cikkváltozatokat a termelésben.</span><span class="sxs-lookup"><span data-stu-id="19db3-146">**Routes** – Set up route versions to enable item variations in production.</span></span>

## <a name="optional-advanced-settings"></a><span data-ttu-id="19db3-147">Opcionális speciális beállítások</span><span class="sxs-lookup"><span data-stu-id="19db3-147">Optional advanced settings</span></span>
1.  <span data-ttu-id="19db3-148">**Termelési csoportok** – Állítson be termelési csoportokat, hogy kapcsolatokat alakítson ki a termelési rendelés és a főkönyvi számlák között.</span><span class="sxs-lookup"><span data-stu-id="19db3-148">**Production groups** – Set up production groups to establish relationships between the production order and ledger accounts.</span></span> <span data-ttu-id="19db3-149">A főkönyvi számlák rendelések jelentésekhez történő feladásához vagy csoportosításához használatosak.</span><span class="sxs-lookup"><span data-stu-id="19db3-149">The ledger accounts are used to post or group orders for reporting.</span></span>
2.  <span data-ttu-id="19db3-150">**Termelési gyűjtők** – Hozzon létre termelési gyűjtőket, hogy csoportosítsa a termelési rendeléseket, annak érdekében, hogy feldolgozhassa a sürgős termelési rendeléseket vagy töröljön és feladjon megrendeléscsoportokat.</span><span class="sxs-lookup"><span data-stu-id="19db3-150">**Production pools** – Create production pools to group production orders so that you can process urgent production orders, or delete and post groups of orders.</span></span>
3.  <span data-ttu-id="19db3-151">**Tulajdonságok** – Határozzon meg tulajdonságokat, hogy különleges attribútumokat hozzon létre, amelyeket az erőforrásaihoz rendelhet a termelési sorrend irányítása érdekében.</span><span class="sxs-lookup"><span data-stu-id="19db3-151">**Properties** – Define properties to create special attributes that you can assign to your resources to control the order of productions.</span></span> <span data-ttu-id="19db3-152">Ezek az attribútumok hozzá vannak kapcsolva a munkaidő sablonnal.</span><span class="sxs-lookup"><span data-stu-id="19db3-152">These attributes are connected to the working time template.</span></span>





