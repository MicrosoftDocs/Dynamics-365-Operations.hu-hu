--- 
title: "Bizományosi készlet tulajdonosának módosítása gyártási igény alapján"
description: "Ez az eljárás bemutatja, hogyan módosítható a bizományosi készlet tulajdonosa a szállítóról a jogi személyére, amikor a készletre gyártási igény van."
author: perlynne
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventJournalOwnershipChange, InventJournalCreate
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: 5dd00e6f53d13305949d225e73223ab54947c804
ms.contentlocale: hu-hu
ms.lasthandoff: 09/11/2018

---
# <a name="change-the-ownership-of-consignment-inventory-based-on-production-demand"></a><span data-ttu-id="29fa4-103">Bizományosi készlet tulajdonosának módosítása gyártási igény alapján</span><span class="sxs-lookup"><span data-stu-id="29fa4-103">Change the ownership of consignment inventory based on production demand</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="29fa4-104">Ez az eljárás bemutatja, hogyan módosítható a bizományosi készlet tulajdonosa a szállítóról a jogi személyére, amikor a készletre gyártási igény van.</span><span class="sxs-lookup"><span data-stu-id="29fa4-104">This procedure shows how to change the owner of consignment inventory from the vendor to your legal entity when there is demand for the inventory in production.</span></span> <span data-ttu-id="29fa4-105">A tulajdonjog-változás készlettulajdonos-változási napló létrehozásával és feladásával történik.</span><span class="sxs-lookup"><span data-stu-id="29fa4-105">This change of ownership is done by creating and posting an inventory ownership change journal.</span></span> <span data-ttu-id="29fa4-106">A tulajdonosváltozási napló sorai létrehozhatók manuálisan, illetve, ahogy az a felvételen látható, meglévő gyártási igény alapján is.</span><span class="sxs-lookup"><span data-stu-id="29fa4-106">The ownership change journal lines can be created manually or, as shown in this recording, based on existing production demand.</span></span> <span data-ttu-id="29fa4-107">Ezt a feladatot általában egy üzemirányítási felügyelő végzi el.</span><span class="sxs-lookup"><span data-stu-id="29fa4-107">Typically, a shop floor supervisor performs this task.</span></span> <span data-ttu-id="29fa4-108">Ezt a folyamatot az USMF bemutatócégnél vagy a saját adataiban is használhatja.</span><span class="sxs-lookup"><span data-stu-id="29fa4-108">You can use this procedure in the USMF demo data company or on your own data.</span></span> <span data-ttu-id="29fa4-109">Saját adatok használatakor győződjön meg arról, hogy teljesíti a következő előfeltételeket: be van állítva egy készletnaplónév, amely be van állítva a készlet tulajdonjog-változásához, vannak fizikailag rögzített szállító tulajdonában lévő aktuális készletelemek, és egy vagy több gyártási rendelés sor az anyaghoz.</span><span class="sxs-lookup"><span data-stu-id="29fa4-109">If you're using your own data, make sure that you have the following prerequisites: an inventory journal name that has been set up for inventory ownership change, physically recorded vendor-owned on-hand items, and one or more production order lines for the material.</span></span> <span data-ttu-id="29fa4-110">Ez az eljárás egy olyan funkcióra vonatkozik, amely a Dynamics 365 for Operations 1611-es verziójába került be.</span><span class="sxs-lookup"><span data-stu-id="29fa4-110">This procedure is for a feature that was added in Dynamics 365 for Operations, version 1611.</span></span>


## <a name="create-an-inventory-ownership-journal"></a><span data-ttu-id="29fa4-111">Készlettulajdonosi napló létrehozása</span><span class="sxs-lookup"><span data-stu-id="29fa4-111">Create an inventory ownership journal</span></span>
1. <span data-ttu-id="29fa4-112">Lépjen a Készletgazdálkodás > Naplóbejegyzések > Cikkek > Készlet tulajdonosváltozása elemre.</span><span class="sxs-lookup"><span data-stu-id="29fa4-112">Go to Inventory management > Journal entries > Items > Inventory ownership change.</span></span>
2. <span data-ttu-id="29fa4-113">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="29fa4-113">Click New.</span></span>
    * <span data-ttu-id="29fa4-114">A készlettulajdonos-változási naplót a bizományosi készlet tulajdonosának módosítására használjuk a szállítóról az aktuális jogi személyre.</span><span class="sxs-lookup"><span data-stu-id="29fa4-114">The inventory ownership change journal is used to change the owner of consignment inventory from the vendor to the current legal entity.</span></span> <span data-ttu-id="29fa4-115">A tulajdonjog-változás úgy történik, hogy feloldjuk a szállító tulajdonában álló aktuális készletet, majd bevételezzük a készletet az aktuális jogi személy számára.</span><span class="sxs-lookup"><span data-stu-id="29fa4-115">This change of ownership is done by releasing the on-hand inventory that is owned by the vendor and then receiving that inventory in the current legal entity.</span></span>  
3. <span data-ttu-id="29fa4-116">A Név mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="29fa4-116">In the Name field, enter or select a value.</span></span>
    * <span data-ttu-id="29fa4-117">Csak az olyan készletnaplónevek választhatók ki, amelyeknek a naplótípusa Tulajdonosváltozás.</span><span class="sxs-lookup"><span data-stu-id="29fa4-117">You can select only inventory journal names that have a journal type of Ownership change.</span></span>  
4. <span data-ttu-id="29fa4-118">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="29fa4-118">Click OK.</span></span>
5. <span data-ttu-id="29fa4-119">Kattintson a Funkciók elemre.</span><span class="sxs-lookup"><span data-stu-id="29fa4-119">Click Functions.</span></span>
6. <span data-ttu-id="29fa4-120">Kattintson a Naplósorok létrehozása termelési rendelésekből elemre.</span><span class="sxs-lookup"><span data-stu-id="29fa4-120">Click Create journal lines from production orders.</span></span>
    * <span data-ttu-id="29fa4-121">A tulajdonjog módosítása folyamat az összes olyan gyártósor lekérdezésével indítható, amelyeknek nyersanyag-felhasználás iránti igénye van.</span><span class="sxs-lookup"><span data-stu-id="29fa4-121">You can start the change of ownership process by querying all the production lines that have demand for consumption of raw material.</span></span>  
7. <span data-ttu-id="29fa4-122">A Befoglalandó készletkiadási állapotok mezőben válasszon egy beállítást.</span><span class="sxs-lookup"><span data-stu-id="29fa4-122">In the Inventory issue statuses to include field, select an option.</span></span>
    * <span data-ttu-id="29fa4-123">Ez a beállítás lehetővé teszi a szűrést a készlettranzakciók kiadási állapota alapján.</span><span class="sxs-lookup"><span data-stu-id="29fa4-123">This option lets you filter by the issue status of the inventory transactions.</span></span> <span data-ttu-id="29fa4-124">Létrehozhatók például naplósorok olyan készlethez, amelynek a fizikai állapota Kitárolva és Lefoglalva.</span><span class="sxs-lookup"><span data-stu-id="29fa4-124">For example, you can create journal lines for inventory that has the Picked and Reserved physical statuses.</span></span>  
8. <span data-ttu-id="29fa4-125">Bontsa ki a Szerepeltetni kívánt rekordok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="29fa4-125">Expand the Records to include section.</span></span>
    * <span data-ttu-id="29fa4-126">Ez a rész további szűrést tesz lehetővé.</span><span class="sxs-lookup"><span data-stu-id="29fa4-126">This section lets you apply additional filtering.</span></span> <span data-ttu-id="29fa4-127">Kiválasztható például egy bizonyos nyersanyag dátuma.</span><span class="sxs-lookup"><span data-stu-id="29fa4-127">For example, you can select a specific raw material date.</span></span>  
9. <span data-ttu-id="29fa4-128">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="29fa4-128">Click OK.</span></span>

## <a name="post-the-inventory-ownership-change-journal"></a><span data-ttu-id="29fa4-129">Készlettulajdonos-változási napló feladása</span><span class="sxs-lookup"><span data-stu-id="29fa4-129">Post the inventory ownership change journal</span></span>
1. <span data-ttu-id="29fa4-130">Kattintson a Feladás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="29fa4-130">Click Post.</span></span>
    * <span data-ttu-id="29fa4-131">A napló feladásakor megtörténik a szállító tulajdonában lévő készlet felszabadítása egy „Tulajdonosváltozás” hivatkozás segítségével.</span><span class="sxs-lookup"><span data-stu-id="29fa4-131">When the journal is posted, the vendor-owned inventory is released by using an "Ownership change" reference.</span></span> <span data-ttu-id="29fa4-132">Ezután megtörténik a készlet érkeztetése aktuális készletként egy készlettranzakcióval, amely egy beszerzési rendelés termékbevételezéssel frissül.</span><span class="sxs-lookup"><span data-stu-id="29fa4-132">The inventory is then received as on-hand by using an inventory transaction that is updated with a purchase order product receipt.</span></span> <span data-ttu-id="29fa4-133">Vegye figyelembe, hogy csak a feladott naplóval kapcsolatos tranzakciók jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="29fa4-133">Note that only transactions that are related to the posted journal are created.</span></span> <span data-ttu-id="29fa4-134">Nem jönnek létre várt készlettranzakciók.</span><span class="sxs-lookup"><span data-stu-id="29fa4-134">No expected inventory transactions are created.</span></span>  
2. <span data-ttu-id="29fa4-135">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="29fa4-135">Click OK.</span></span>
3. <span data-ttu-id="29fa4-136">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="29fa4-136">Close the page.</span></span>


