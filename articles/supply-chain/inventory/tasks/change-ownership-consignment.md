---
title: Bizományosi készlet tulajdonosának módosítása gyártási igény alapján
description: Ez az eljárás bemutatja, hogyan módosítható a bizományosi készlet tulajdonosa a szállítóról a jogi személyére, amikor a készletre gyártási igény van.
author: perlynne
manager: tfehr
ms.date: 08/14/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalOwnershipChange, InventJournalCreate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7c50affa05b8df53d31660854f4d1ead6aeff820
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3204240"
---
# <a name="change-the-ownership-of-consignment-inventory-based-on-production-demand"></a><span data-ttu-id="21e03-103">Bizományosi készlet tulajdonosának módosítása gyártási igény alapján</span><span class="sxs-lookup"><span data-stu-id="21e03-103">Change the ownership of consignment inventory based on production demand</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="21e03-104">Ez az eljárás bemutatja, hogyan módosítható a bizományosi készlet tulajdonosa a szállítóról a jogi személyére, amikor a készletre gyártási igény van.</span><span class="sxs-lookup"><span data-stu-id="21e03-104">This procedure shows how to change the owner of consignment inventory from the vendor to your legal entity when there is demand for the inventory in production.</span></span> <span data-ttu-id="21e03-105">A tulajdonjog-változás készlettulajdonos-változási napló létrehozásával és feladásával történik.</span><span class="sxs-lookup"><span data-stu-id="21e03-105">This change of ownership is done by creating and posting an inventory ownership change journal.</span></span> <span data-ttu-id="21e03-106">A tulajdonosváltozási napló sorai létrehozhatók manuálisan, illetve, ahogy az a felvételen látható, meglévő gyártási igény alapján is.</span><span class="sxs-lookup"><span data-stu-id="21e03-106">The ownership change journal lines can be created manually or, as shown in this recording, based on existing production demand.</span></span> <span data-ttu-id="21e03-107">Ezt a feladatot általában egy üzemirányítási felügyelő végzi el.</span><span class="sxs-lookup"><span data-stu-id="21e03-107">Typically, a shop floor supervisor performs this task.</span></span> <span data-ttu-id="21e03-108">Ezt a folyamatot az USMF bemutatócégnél vagy a saját adataiban is használhatja.</span><span class="sxs-lookup"><span data-stu-id="21e03-108">You can use this procedure in the USMF demo data company or on your own data.</span></span> <span data-ttu-id="21e03-109">Saját adatok használatakor győződjön meg arról, hogy teljesíti a következő előfeltételeket: be van állítva egy készletnaplónév, amely be van állítva a készlet tulajdonjog-változásához, vannak fizikailag rögzített szállító tulajdonában lévő aktuális készletelemek, és egy vagy több gyártási rendelés sor az anyaghoz.</span><span class="sxs-lookup"><span data-stu-id="21e03-109">If you're using your own data, make sure that you have the following prerequisites: an inventory journal name that has been set up for inventory ownership change, physically recorded vendor-owned on-hand items, and one or more production order lines for the material.</span></span> <span data-ttu-id="21e03-110">Ez az eljárás egy olyan funkcióra vonatkozik, amely a Dynamics 365 for Operations 1611-es verziójába került be.</span><span class="sxs-lookup"><span data-stu-id="21e03-110">This procedure is for a feature that was added in Dynamics 365 for Operations, version 1611.</span></span>

> [!NOTE]
> <span data-ttu-id="21e03-111">A kimenő szállítmányok folyamatai nem támogatottak gyárilag, és a rendszer nem támogatja az automatikus tulajdonlási napló feldolgozását.</span><span class="sxs-lookup"><span data-stu-id="21e03-111">Outbound consignment processes are not supported out-of-the-box and automatic ownership journal processing is not supported.</span></span>

## <a name="create-an-inventory-ownership-journal"></a><span data-ttu-id="21e03-112">Készlettulajdonosi napló létrehozása</span><span class="sxs-lookup"><span data-stu-id="21e03-112">Create an inventory ownership journal</span></span>
1. <span data-ttu-id="21e03-113">Lépjen a Készletgazdálkodás > Naplóbejegyzések > Cikkek > Készlet tulajdonosváltozása elemre.</span><span class="sxs-lookup"><span data-stu-id="21e03-113">Go to Inventory management > Journal entries > Items > Inventory ownership change.</span></span>
2. <span data-ttu-id="21e03-114">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="21e03-114">Click New.</span></span>
    * <span data-ttu-id="21e03-115">A készlettulajdonos-változási naplót a bizományosi készlet tulajdonosának módosítására használjuk a szállítóról az aktuális jogi személyre.</span><span class="sxs-lookup"><span data-stu-id="21e03-115">The inventory ownership change journal is used to change the owner of consignment inventory from the vendor to the current legal entity.</span></span> <span data-ttu-id="21e03-116">A tulajdonjog-változás úgy történik, hogy feloldjuk a szállító tulajdonában álló aktuális készletet, majd bevételezzük a készletet az aktuális jogi személy számára.</span><span class="sxs-lookup"><span data-stu-id="21e03-116">This change of ownership is done by releasing the on-hand inventory that is owned by the vendor and then receiving that inventory in the current legal entity.</span></span>  
3. <span data-ttu-id="21e03-117">A Név mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="21e03-117">In the Name field, enter or select a value.</span></span>
    * <span data-ttu-id="21e03-118">Csak az olyan készletnaplónevek választhatók ki, amelyeknek a naplótípusa Tulajdonosváltozás.</span><span class="sxs-lookup"><span data-stu-id="21e03-118">You can select only inventory journal names that have a journal type of Ownership change.</span></span>  
4. <span data-ttu-id="21e03-119">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="21e03-119">Click OK.</span></span>
5. <span data-ttu-id="21e03-120">Kattintson a Funkciók elemre.</span><span class="sxs-lookup"><span data-stu-id="21e03-120">Click Functions.</span></span>
6. <span data-ttu-id="21e03-121">Kattintson a Naplósorok létrehozása termelési rendelésekből elemre.</span><span class="sxs-lookup"><span data-stu-id="21e03-121">Click Create journal lines from production orders.</span></span>
    * <span data-ttu-id="21e03-122">A tulajdonjog módosítása folyamat az összes olyan gyártósor lekérdezésével indítható, amelyeknek nyersanyag-felhasználás iránti igénye van.</span><span class="sxs-lookup"><span data-stu-id="21e03-122">You can start the change of ownership process by querying all the production lines that have demand for consumption of raw material.</span></span>  
7. <span data-ttu-id="21e03-123">A Befoglalandó készletkiadási állapotok mezőben válasszon egy beállítást.</span><span class="sxs-lookup"><span data-stu-id="21e03-123">In the Inventory issue statuses to include field, select an option.</span></span>
    * <span data-ttu-id="21e03-124">Ez a beállítás lehetővé teszi a szűrést a készlettranzakciók kiadási állapota alapján.</span><span class="sxs-lookup"><span data-stu-id="21e03-124">This option lets you filter by the issue status of the inventory transactions.</span></span> <span data-ttu-id="21e03-125">Létrehozhatók például naplósorok olyan készlethez, amelynek a fizikai állapota Kitárolva és Lefoglalva.</span><span class="sxs-lookup"><span data-stu-id="21e03-125">For example, you can create journal lines for inventory that has the Picked and Reserved physical statuses.</span></span>  
8. <span data-ttu-id="21e03-126">Bontsa ki a Szerepeltetni kívánt rekordok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="21e03-126">Expand the Records to include section.</span></span>
    * <span data-ttu-id="21e03-127">Ez a rész további szűrést tesz lehetővé.</span><span class="sxs-lookup"><span data-stu-id="21e03-127">This section lets you apply additional filtering.</span></span> <span data-ttu-id="21e03-128">Kiválasztható például egy bizonyos nyersanyag dátuma.</span><span class="sxs-lookup"><span data-stu-id="21e03-128">For example, you can select a specific raw material date.</span></span>  
9. <span data-ttu-id="21e03-129">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="21e03-129">Click OK.</span></span>

## <a name="post-the-inventory-ownership-change-journal"></a><span data-ttu-id="21e03-130">Készlettulajdonos-változási napló feladása</span><span class="sxs-lookup"><span data-stu-id="21e03-130">Post the inventory ownership change journal</span></span>
1. <span data-ttu-id="21e03-131">Kattintson a Feladás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="21e03-131">Click Post.</span></span>
    * <span data-ttu-id="21e03-132">A napló feladásakor megtörténik a szállító tulajdonában lévő készlet felszabadítása egy „Tulajdonosváltozás” hivatkozás segítségével.</span><span class="sxs-lookup"><span data-stu-id="21e03-132">When the journal is posted, the vendor-owned inventory is released by using an "Ownership change" reference.</span></span> <span data-ttu-id="21e03-133">Ezután megtörténik a készlet érkeztetése aktuális készletként egy készlettranzakcióval, amely egy beszerzési rendelés termékbevételezéssel frissül.</span><span class="sxs-lookup"><span data-stu-id="21e03-133">The inventory is then received as on-hand by using an inventory transaction that is updated with a purchase order product receipt.</span></span> <span data-ttu-id="21e03-134">Vegye figyelembe, hogy csak a feladott naplóval kapcsolatos tranzakciók jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="21e03-134">Note that only transactions that are related to the posted journal are created.</span></span> <span data-ttu-id="21e03-135">Nem jönnek létre várt készlettranzakciók.</span><span class="sxs-lookup"><span data-stu-id="21e03-135">No expected inventory transactions are created.</span></span>  
2. <span data-ttu-id="21e03-136">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="21e03-136">Click OK.</span></span>
3. <span data-ttu-id="21e03-137">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="21e03-137">Close the page.</span></span>

