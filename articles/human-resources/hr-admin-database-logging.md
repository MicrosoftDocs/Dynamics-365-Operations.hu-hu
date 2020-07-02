---
title: Adatbázis-naplózás konfigurálása és kezelése
description: Nyomon követheti a táblák és a mezők módosításait az Dynamics 365 Human Resources adatbázisnaplózás funkciójával.
author: Darinkramer
manager: AnnBe
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3dc4658a0a13af95978c66f5aab882902f754a2d
ms.sourcegitcommit: 88f38d584c5befb96e4d1daab4b28af5519ef125
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/11/2020
ms.locfileid: "3443579"
---
# <a name="configure-and-manage-database-logging"></a><span data-ttu-id="53e59-103">Adatbázis-naplózás konfigurálása és kezelése</span><span class="sxs-lookup"><span data-stu-id="53e59-103">Configure and manage database logging</span></span>

<span data-ttu-id="53e59-104">Nyomon követheti a táblák és a mezők módosításait az Dynamics 365 Human Resources adatbázisnaplózás funkciójával.</span><span class="sxs-lookup"><span data-stu-id="53e59-104">You can track changes to tables and fields in Dynamics 365 Human Resources with database logging.</span></span> <span data-ttu-id="53e59-105">Ez a témakör ismerteti, hogyan végezheti el a következőket:</span><span class="sxs-lookup"><span data-stu-id="53e59-105">This topic describes how to:</span></span>

- <span data-ttu-id="53e59-106">Adatbázis-naplózás biztonságának és teljesítményének kezelése</span><span class="sxs-lookup"><span data-stu-id="53e59-106">Manage security and performance for database logging</span></span>
- <span data-ttu-id="53e59-107">Adatbázis-naplózás beállítása</span><span class="sxs-lookup"><span data-stu-id="53e59-107">Set up database logging</span></span>
- <span data-ttu-id="53e59-108">Adatbázisnaplók karbantartása</span><span class="sxs-lookup"><span data-stu-id="53e59-108">Clean up database logs</span></span>

## <a name="overview-of-database-logging"></a><span data-ttu-id="53e59-109">Adatbázisnaplózás áttekintése</span><span class="sxs-lookup"><span data-stu-id="53e59-109">Overview of database logging</span></span>

<span data-ttu-id="53e59-110">Az adatbázisnaplózás nyomon követi a Microsoft Dynamics 365 Human Resources tábláinak és mezőinek bizonyos módosításait.</span><span class="sxs-lookup"><span data-stu-id="53e59-110">Database logging tracks specific changes to Microsoft Dynamics 365 Human Resources tables and fields.</span></span> <span data-ttu-id="53e59-111">Ilyen módosítások a beszúrást, a frissítés vagy a törlés.</span><span class="sxs-lookup"><span data-stu-id="53e59-111">These changes include inserting, updating, or deleting.</span></span> <span data-ttu-id="53e59-112">Az adatbázis-naplózás egy rekordot tárol az adatbázis-napló táblájában lévő táblák és mezők változásairól.</span><span class="sxs-lookup"><span data-stu-id="53e59-112">Database logging stores a record of changes to tables or fields in the database log table.</span></span>

<span data-ttu-id="53e59-113">Az adatbázis-naplózás üzleti felhasználási módjai a következők:</span><span class="sxs-lookup"><span data-stu-id="53e59-113">The business uses of database logging include:</span></span>

- <span data-ttu-id="53e59-114">A bizalmas adatokat tartalmazó konkrét táblák változásai naplózási rekordjának létrehozása.</span><span class="sxs-lookup"><span data-stu-id="53e59-114">Creating an audit record of changes to specific tables that contain sensitive information.</span></span>
- <span data-ttu-id="53e59-115">Egyes tranzakciók nyomon követése.</span><span class="sxs-lookup"><span data-stu-id="53e59-115">Tracking single transactions.</span></span> <span data-ttu-id="53e59-116">Az adatbázis-naplózás nem a kötegelt feladatokban futó automatizált tranzakciók nyomon követésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="53e59-116">Database logging isn't intended for tracking automated transactions that run in batch jobs.</span></span>

## <a name="security-for-database-logging"></a><span data-ttu-id="53e59-117">Adatbázisnaplózás biztonsága</span><span class="sxs-lookup"><span data-stu-id="53e59-117">Security for database logging</span></span>

<span data-ttu-id="53e59-118">Az adatbázisnaplók bizalmas adatokat tartalmazhatnak.</span><span class="sxs-lookup"><span data-stu-id="53e59-118">Database logs can contain sensitive data.</span></span> <span data-ttu-id="53e59-119">A hozzáférés korlátozásával csak azokat a biztonsági jogosítja fel, amelyek számára a napló adatainak elérése szükséges.</span><span class="sxs-lookup"><span data-stu-id="53e59-119">Limit access to include only security roles that need access to the log data.</span></span>

## <a name="database-logging-and-performance"></a><span data-ttu-id="53e59-120">Adatbázis naplózása és teljesítménye</span><span class="sxs-lookup"><span data-stu-id="53e59-120">Database logging and performance</span></span>

<span data-ttu-id="53e59-121">Ugyan üzleti szempontok alapján értékes, az adatbázis-naplózás költséges lehet az erőforrás-felhasználás és-kezelés modulban.szempontjából.</span><span class="sxs-lookup"><span data-stu-id="53e59-121">While valuable from a business perspective, database logging can be expensive in resource use and management.</span></span> <span data-ttu-id="53e59-122">Az adatbázis-naplózás teljesítményre gyakorolt hatásai a következők:</span><span class="sxs-lookup"><span data-stu-id="53e59-122">The performance implications of database logging include:</span></span>

- <span data-ttu-id="53e59-123">Az adatbázisnapló-tábla gyorsan nőhet, ami növeli az adatbázis méretét.</span><span class="sxs-lookup"><span data-stu-id="53e59-123">The database log table can grow quickly and cause an increase in the size of the database.</span></span> <span data-ttu-id="53e59-124">A növekedés a megtartani kívánt naplózott adatok mennyiségétől függ.</span><span class="sxs-lookup"><span data-stu-id="53e59-124">Growth depends on the amount of logged data that you decide to keep.</span></span> <span data-ttu-id="53e59-125">Alapértelmezés szerint az adatbázis-napló tábla csak 30 napnyi naplóadatot tart meg.</span><span class="sxs-lookup"><span data-stu-id="53e59-125">By default, the database log table maintains only 30 days of log data.</span></span> 

- <span data-ttu-id="53e59-126">Az adatbázis naplózása hátrányosan érintheti a hosszú ideig futó automatizált folyamatokat, például a hosszú ideig futó adatimportálásokat.</span><span class="sxs-lookup"><span data-stu-id="53e59-126">Database logging can adversely affect long-running automated processes, such as long-running data imports.</span></span>

### <a name="best-practices"></a><span data-ttu-id="53e59-127">Gyakorlati tanácsok</span><span class="sxs-lookup"><span data-stu-id="53e59-127">Best practices</span></span>

<span data-ttu-id="53e59-128">A teljesítmény javítása érdekében a teljes táblák naplózása helyett csak bizonyos mezőket válasszon ki naplózásra, így korlátozhatja a naplóbejegyzések számát.</span><span class="sxs-lookup"><span data-stu-id="53e59-128">To improve performance, limit log entries by selecting specific fields to log instead of whole tables.</span></span> <span data-ttu-id="53e59-129">Az általános teljesítmény fenntartásához az adatbázis naplózása legfeljebb 20 táblára korlátozódik.</span><span class="sxs-lookup"><span data-stu-id="53e59-129">To help maintain overall performance, database logging is limited to 20 tables.</span></span>

> [!NOTE]
> <span data-ttu-id="53e59-130">Az egyedi mezők esetében csak a frissítéseket lehet naplózni.</span><span class="sxs-lookup"><span data-stu-id="53e59-130">Only updates can be logged for individual fields.</span></span>

## <a name="set-up-database-logging"></a><span data-ttu-id="53e59-131">Adatbázis-naplózás beállítása</span><span class="sxs-lookup"><span data-stu-id="53e59-131">Set up database logging</span></span>

<span data-ttu-id="53e59-132">Az **Adatbázis-változások naplózása** varázsló használatával állíthatja be az adatbázis naplózását.</span><span class="sxs-lookup"><span data-stu-id="53e59-132">You can use the **Logging database changes** wizard to set up database logging.</span></span> <span data-ttu-id="53e59-133">A varázslóval rugalmasan beállíthatja a táblák és a mezők naplózását.</span><span class="sxs-lookup"><span data-stu-id="53e59-133">The wizard provides a flexible way to set up logging for tables or fields.</span></span>

1. <span data-ttu-id="53e59-134">Nyissa meg a **Rendszeradminisztráció > Hivatkozások > Adatbázis-> Adatbázis-napló beállítása** elemet.</span><span class="sxs-lookup"><span data-stu-id="53e59-134">Go to **System administration > Links > Database > Database log setup**.</span></span> <span data-ttu-id="53e59-135">Válassza az **Új** parancsot a **Adatbázis-változások naplózása** varázsló elindításához.</span><span class="sxs-lookup"><span data-stu-id="53e59-135">Select **New** to start the **Logging database changes** wizard.</span></span>
2. <span data-ttu-id="53e59-136">Hajtsa végre a varázsló lépéseit.</span><span class="sxs-lookup"><span data-stu-id="53e59-136">Complete the wizard.</span></span>

## <a name="clean-up-database-logs"></a><span data-ttu-id="53e59-137">Adatbázisnaplók karbantartása</span><span class="sxs-lookup"><span data-stu-id="53e59-137">Clean up database logs</span></span>

<span data-ttu-id="53e59-138">Az adatbázis-naplókat egészben vagy egy részben törölheti a következő beállításokkal:</span><span class="sxs-lookup"><span data-stu-id="53e59-138">You can delete all or part of the database logs, using the following options:</span></span>

- <span data-ttu-id="53e59-139">Egy adott táblához tartozó összes napló kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="53e59-139">Select all logs for a particular table.</span></span>
- <span data-ttu-id="53e59-140">Adja meg az adatbázis-napló meghatározott típusait.</span><span class="sxs-lookup"><span data-stu-id="53e59-140">Select specific types of database log.</span></span>
- <span data-ttu-id="53e59-141">Válassza ki a napló létrehozásának dátumát és időpontját.</span><span class="sxs-lookup"><span data-stu-id="53e59-141">Select a date and time that a log was created.</span></span>

<span data-ttu-id="53e59-142">Az adatbázis-tisztítás beállításához kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="53e59-142">To set up database log cleanup, follow these steps:</span></span> 

1. <span data-ttu-id="53e59-143">Nyissa meg a **Rendszeradminisztráció > Hivatkozások > Adatbázis-> Adatbázis-napló** elemet.</span><span class="sxs-lookup"><span data-stu-id="53e59-143">Go to **System administration > Links > Database > Database log**.</span></span> <span data-ttu-id="53e59-144">Válassza ki a **Napló tisztítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="53e59-144">Select **Clean up log**.</span></span>

2. <span data-ttu-id="53e59-145">Válassza ki a törölni kívánt naplók kiválasztására szolgáló módszert a következő lehetőségek egyikének megadásával:</span><span class="sxs-lookup"><span data-stu-id="53e59-145">Choose a method of selecting logs to delete by entering one of the following options:</span></span>

   - <span data-ttu-id="53e59-146">Táblaazonosító (ID)</span><span class="sxs-lookup"><span data-stu-id="53e59-146">Table ID</span></span>
   - <span data-ttu-id="53e59-147">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="53e59-147">Type of log</span></span>
   - <span data-ttu-id="53e59-148">Létrehozás dátuma és időpontja</span><span class="sxs-lookup"><span data-stu-id="53e59-148">Created date and time</span></span>

3. <span data-ttu-id="53e59-149">Az **Adatbázis-napló tisztítása** lapon megadhatja, hogy mikor fusson a naplókarbantartási feladat.</span><span class="sxs-lookup"><span data-stu-id="53e59-149">Use the **Database log cleanup** tab to determine when to run the log cleanup task.</span></span> <span data-ttu-id="53e59-150">Alapértelmezés szerint az adatbázisnaplók 30 napig érhetők el.</span><span class="sxs-lookup"><span data-stu-id="53e59-150">By default, database logs are available for 30 days.</span></span>
