---
title: Adatbázis-naplózás konfigurálása és kezelése
description: Nyomon követheti a táblák és a mezők módosításait az Dynamics 365 Human Resources adatbázisnaplózás funkciójával.
author: andreabichsel
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ae974436469c00a3df6fd40d9d60521a0883a917
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054812"
---
# <a name="configure-and-manage-database-logging"></a><span data-ttu-id="58dda-103">Adatbázis-naplózás konfigurálása és kezelése</span><span class="sxs-lookup"><span data-stu-id="58dda-103">Configure and manage database logging</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="58dda-104">Nyomon követheti a táblák és a mezők módosításait az Dynamics 365 Human Resources adatbázisnaplózás funkciójával.</span><span class="sxs-lookup"><span data-stu-id="58dda-104">You can track changes to tables and fields in Dynamics 365 Human Resources with database logging.</span></span> <span data-ttu-id="58dda-105">Ez a témakör ismerteti, hogyan végezheti el a következőket:</span><span class="sxs-lookup"><span data-stu-id="58dda-105">This topic describes how to:</span></span>

- <span data-ttu-id="58dda-106">Adatbázis-naplózás biztonságának és teljesítményének kezelése</span><span class="sxs-lookup"><span data-stu-id="58dda-106">Manage security and performance for database logging</span></span>
- <span data-ttu-id="58dda-107">Adatbázis-naplózás beállítása</span><span class="sxs-lookup"><span data-stu-id="58dda-107">Set up database logging</span></span>
- <span data-ttu-id="58dda-108">Adatbázisnaplók karbantartása</span><span class="sxs-lookup"><span data-stu-id="58dda-108">Clean up database logs</span></span>

## <a name="overview-of-database-logging"></a><span data-ttu-id="58dda-109">Adatbázisnaplózás áttekintése</span><span class="sxs-lookup"><span data-stu-id="58dda-109">Overview of database logging</span></span>

<span data-ttu-id="58dda-110">Az adatbázisnaplózás nyomon követi a Microsoft Dynamics 365 Human Resources tábláinak és mezőinek bizonyos módosításait.</span><span class="sxs-lookup"><span data-stu-id="58dda-110">Database logging tracks specific changes to Microsoft Dynamics 365 Human Resources tables and fields.</span></span> <span data-ttu-id="58dda-111">Ilyen módosítások a beszúrást, a frissítés vagy a törlés.</span><span class="sxs-lookup"><span data-stu-id="58dda-111">These changes include inserting, updating, or deleting.</span></span> <span data-ttu-id="58dda-112">Az adatbázis-naplózás egy rekordot tárol az adatbázis-napló táblájában lévő táblák és mezők változásairól.</span><span class="sxs-lookup"><span data-stu-id="58dda-112">Database logging stores a record of changes to tables or fields in the database log table.</span></span>

<span data-ttu-id="58dda-113">Az adatbázis-naplózás üzleti felhasználási módjai a következők:</span><span class="sxs-lookup"><span data-stu-id="58dda-113">The business uses of database logging include:</span></span>

- <span data-ttu-id="58dda-114">A bizalmas adatokat tartalmazó konkrét táblák változásai naplózási rekordjának létrehozása.</span><span class="sxs-lookup"><span data-stu-id="58dda-114">Creating an audit record of changes to specific tables that contain sensitive information.</span></span>
- <span data-ttu-id="58dda-115">Egyes tranzakciók nyomon követése.</span><span class="sxs-lookup"><span data-stu-id="58dda-115">Tracking single transactions.</span></span> <span data-ttu-id="58dda-116">Az adatbázis-naplózás nem a kötegelt feladatokban futó automatizált tranzakciók nyomon követésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="58dda-116">Database logging isn't intended for tracking automated transactions that run in batch jobs.</span></span>

## <a name="security-for-database-logging"></a><span data-ttu-id="58dda-117">Adatbázisnaplózás biztonsága</span><span class="sxs-lookup"><span data-stu-id="58dda-117">Security for database logging</span></span>

<span data-ttu-id="58dda-118">Az adatbázisnaplók bizalmas adatokat tartalmazhatnak.</span><span class="sxs-lookup"><span data-stu-id="58dda-118">Database logs can contain sensitive data.</span></span> <span data-ttu-id="58dda-119">A hozzáférés korlátozásával csak azokat a biztonsági jogosítja fel, amelyek számára a napló adatainak elérése szükséges.</span><span class="sxs-lookup"><span data-stu-id="58dda-119">Limit access to include only security roles that need access to the log data.</span></span>

## <a name="database-logging-and-performance"></a><span data-ttu-id="58dda-120">Adatbázis naplózása és teljesítménye</span><span class="sxs-lookup"><span data-stu-id="58dda-120">Database logging and performance</span></span>

<span data-ttu-id="58dda-121">Ugyan üzleti szempontok alapján értékes, az adatbázis-naplózás költséges lehet az erőforrás-felhasználás és-kezelés modulban.szempontjából.</span><span class="sxs-lookup"><span data-stu-id="58dda-121">While valuable from a business perspective, database logging can be expensive in resource use and management.</span></span> <span data-ttu-id="58dda-122">Az adatbázis-naplózás teljesítményre gyakorolt hatásai a következők:</span><span class="sxs-lookup"><span data-stu-id="58dda-122">The performance implications of database logging include:</span></span>

- <span data-ttu-id="58dda-123">Az adatbázisnapló-tábla gyorsan nőhet, ami növeli az adatbázis méretét.</span><span class="sxs-lookup"><span data-stu-id="58dda-123">The database log table can grow quickly and cause an increase in the size of the database.</span></span> <span data-ttu-id="58dda-124">A növekedés a megtartani kívánt naplózott adatok mennyiségétől függ.</span><span class="sxs-lookup"><span data-stu-id="58dda-124">Growth depends on the amount of logged data that you decide to keep.</span></span> <span data-ttu-id="58dda-125">Alapértelmezés szerint az adatbázis-napló tábla csak 30 napnyi naplóadatot tart meg.</span><span class="sxs-lookup"><span data-stu-id="58dda-125">By default, the database log table maintains only 30 days of log data.</span></span> 

- <span data-ttu-id="58dda-126">Az adatbázis naplózása hátrányosan érintheti a hosszú ideig futó automatizált folyamatokat, például a hosszú ideig futó adatimportálásokat.</span><span class="sxs-lookup"><span data-stu-id="58dda-126">Database logging can adversely affect long-running automated processes, such as long-running data imports.</span></span>

### <a name="best-practices"></a><span data-ttu-id="58dda-127">Gyakorlati tanácsok</span><span class="sxs-lookup"><span data-stu-id="58dda-127">Best practices</span></span>

<span data-ttu-id="58dda-128">A teljesítmény javítása érdekében a teljes táblák naplózása helyett csak bizonyos mezőket válasszon ki naplózásra, így korlátozhatja a naplóbejegyzések számát.</span><span class="sxs-lookup"><span data-stu-id="58dda-128">To improve performance, limit log entries by selecting specific fields to log instead of whole tables.</span></span> <span data-ttu-id="58dda-129">Az általános teljesítmény fenntartásához az adatbázis naplózása legfeljebb 20 táblára korlátozódik.</span><span class="sxs-lookup"><span data-stu-id="58dda-129">To help maintain overall performance, database logging is limited to 20 tables.</span></span>

> [!NOTE]
> <span data-ttu-id="58dda-130">Az egyedi mezők esetében csak a frissítéseket lehet naplózni.</span><span class="sxs-lookup"><span data-stu-id="58dda-130">Only updates can be logged for individual fields.</span></span>

## <a name="set-up-database-logging"></a><span data-ttu-id="58dda-131">Adatbázis-naplózás beállítása</span><span class="sxs-lookup"><span data-stu-id="58dda-131">Set up database logging</span></span>

<span data-ttu-id="58dda-132">Az **Adatbázis-változások naplózása** varázsló használatával állíthatja be az adatbázis naplózását.</span><span class="sxs-lookup"><span data-stu-id="58dda-132">You can use the **Logging database changes** wizard to set up database logging.</span></span> <span data-ttu-id="58dda-133">A varázslóval rugalmasan beállíthatja a táblák és a mezők naplózását.</span><span class="sxs-lookup"><span data-stu-id="58dda-133">The wizard provides a flexible way to set up logging for tables or fields.</span></span>

1. <span data-ttu-id="58dda-134">Nyissa meg a **Rendszeradminisztráció > Hivatkozások > Adatbázis-> Adatbázis-napló beállítása** elemet.</span><span class="sxs-lookup"><span data-stu-id="58dda-134">Go to **System administration > Links > Database > Database log setup**.</span></span> <span data-ttu-id="58dda-135">Válassza az **Új** parancsot a **Adatbázis-változások naplózása** varázsló elindításához.</span><span class="sxs-lookup"><span data-stu-id="58dda-135">Select **New** to start the **Logging database changes** wizard.</span></span>
2. <span data-ttu-id="58dda-136">Válassza ki **Következő** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="58dda-136">Select **Next**.</span></span> 
3. <span data-ttu-id="58dda-137">A varázsló **Táblák és mezők** lapján jelölje ki azokat a táblákat és mezőket, amelyeken engedélyezni szeretné az adatbázis naplózását, és válassza a **Tovább** gombot.</span><span class="sxs-lookup"><span data-stu-id="58dda-137">On the **Tables and fields** page of the wizard, select the the tables and fields on which you want to enable database logging, and select **Next**.</span></span>

   > [!Note]
   > <span data-ttu-id="58dda-138">Az adatbázis naplózása nem érhető el a Human Resources adatbázisának minden táblája esetén.</span><span class="sxs-lookup"><span data-stu-id="58dda-138">Database logging is not available on all tables in the Human Resources database.</span></span> <span data-ttu-id="58dda-139">A lista alatti **Összes tábla megjelenítése** lehetőség választásával kibontja a táblák és mezők listáját, hogy minden olyan adatbázistábla látható legyen, amelyekhez az adatbázisnaplózás elérhető, de ez az adatbázistáblák teljes listájának részhalmaza lesz.</span><span class="sxs-lookup"><span data-stu-id="58dda-139">Selecting **Show all tables** below the list expands the list of tables and fields to show all database tables for which database logging is available, but this will be a subset of the full list of database tables.</span></span>

4. <span data-ttu-id="58dda-140">A varázsló **Módosítás típusai** lapján jelölje ki azokat az adatműveleteket, amelyekben nyomon szeretné követni az egyes táblák és mezők módosításait, majd válassza a **Tovább** gombot.</span><span class="sxs-lookup"><span data-stu-id="58dda-140">On the **Types of change** page of the wizard, select the data operations for which you want to track changes for each of the tables and fields, and select **Next**.</span></span> <span data-ttu-id="58dda-141">Az alábbi táblázatban található a naplózáshoz elérhető adatműveletek leírása.</span><span class="sxs-lookup"><span data-stu-id="58dda-141">See the table below for a description of the data operations that are available for logging.</span></span>
5. <span data-ttu-id="58dda-142">Tekintse át a módosításokat a **Befejezés** lapon, és válassza a **Befejezés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="58dda-142">On the **Finish** page, review the changes that will be made, and select **Finish**.</span></span>

| <span data-ttu-id="58dda-143">Művelet</span><span class="sxs-lookup"><span data-stu-id="58dda-143">Operation</span></span> | <span data-ttu-id="58dda-144">Leírás</span><span class="sxs-lookup"><span data-stu-id="58dda-144">Description</span></span> |
| -- | -- |
| <span data-ttu-id="58dda-145">Új tranzakciók nyomon követése</span><span class="sxs-lookup"><span data-stu-id="58dda-145">Track new transactions</span></span> | <span data-ttu-id="58dda-146">Napló létrehozása a táblában létrehozott új rekordokhoz.</span><span class="sxs-lookup"><span data-stu-id="58dda-146">Create a log for new records that are created in the table.</span></span> |
| <span data-ttu-id="58dda-147">Módosítás</span><span class="sxs-lookup"><span data-stu-id="58dda-147">Update</span></span> | <span data-ttu-id="58dda-148">Napló létrehozása a táblarekordok frissítéséhez, illetve a tábla egyes kiválasztott mezőinek frissítéséhez.</span><span class="sxs-lookup"><span data-stu-id="58dda-148">Create a log for updates to table records, or updates to individually selected fields in the table.</span></span> <span data-ttu-id="58dda-149">Ha a táblához választ naplófrissítést, akkor minden alkalommal létrejön egy naplórekord, amikor a tábla bármely mezőjében frissítés történik.</span><span class="sxs-lookup"><span data-stu-id="58dda-149">If you select to log updates for the table, then a log record is created each time an update is made to any field of any record on the table.</span></span> <span data-ttu-id="58dda-150">Ha azt választja, hogy bizonyos mezők frissítéseit naplózza, akkor egy naplórekord csak akkor jön létre, amikor a táblarekordok ezen mezőiben frissítés történik.</span><span class="sxs-lookup"><span data-stu-id="58dda-150">If you select to log updates for specific fields, then a log record is created only when updates are made to those fields of table records.</span></span> |
| <span data-ttu-id="58dda-151">Eltávolítás</span><span class="sxs-lookup"><span data-stu-id="58dda-151">Delete</span></span> | <span data-ttu-id="58dda-152">Napló létrehozása a táblából törölt rekordokhoz.</span><span class="sxs-lookup"><span data-stu-id="58dda-152">Create a log for records deleted from the table.</span></span> |
| <span data-ttu-id="58dda-153">Kulcs átnevezése</span><span class="sxs-lookup"><span data-stu-id="58dda-153">Rename key</span></span> | <span data-ttu-id="58dda-154">Naplórekord létrehozása táblakulcs átnevezése után.</span><span class="sxs-lookup"><span data-stu-id="58dda-154">Create a log record when a table key is renamed.</span></span> |


## <a name="clean-up-database-logs"></a><span data-ttu-id="58dda-155">Adatbázisnaplók karbantartása</span><span class="sxs-lookup"><span data-stu-id="58dda-155">Clean up database logs</span></span>

<span data-ttu-id="58dda-156">Az adatbázis-naplókat egészben vagy egy részben törölheti a következő beállításokkal:</span><span class="sxs-lookup"><span data-stu-id="58dda-156">You can delete all or part of the database logs, using the following options:</span></span>

- <span data-ttu-id="58dda-157">Egy adott táblához tartozó összes napló kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="58dda-157">Select all logs for a particular table.</span></span>
- <span data-ttu-id="58dda-158">Adja meg az adatbázis-napló meghatározott típusait.</span><span class="sxs-lookup"><span data-stu-id="58dda-158">Select specific types of database log.</span></span>
- <span data-ttu-id="58dda-159">Válassza ki a napló létrehozásának dátumát és időpontját.</span><span class="sxs-lookup"><span data-stu-id="58dda-159">Select a date and time that a log was created.</span></span>

<span data-ttu-id="58dda-160">Az adatbázis-tisztítás beállításához kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="58dda-160">To set up database log cleanup, follow these steps:</span></span> 

1. <span data-ttu-id="58dda-161">Nyissa meg a **Rendszeradminisztráció > Hivatkozások > Adatbázis-> Adatbázis-napló** elemet.</span><span class="sxs-lookup"><span data-stu-id="58dda-161">Go to **System administration > Links > Database > Database log**.</span></span> <span data-ttu-id="58dda-162">Válassza ki a **Napló tisztítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="58dda-162">Select **Clean up log**.</span></span>

2. <span data-ttu-id="58dda-163">Válassza ki a törölni kívánt naplók kiválasztására szolgáló módszert a következő lehetőségek egyikének megadásával:</span><span class="sxs-lookup"><span data-stu-id="58dda-163">Choose a method of selecting logs to delete by entering one of the following options:</span></span>

   - <span data-ttu-id="58dda-164">Táblaazonosító (ID)</span><span class="sxs-lookup"><span data-stu-id="58dda-164">Table ID</span></span>
   - <span data-ttu-id="58dda-165">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="58dda-165">Type of log</span></span>
   - <span data-ttu-id="58dda-166">Létrehozás dátuma és időpontja</span><span class="sxs-lookup"><span data-stu-id="58dda-166">Created date and time</span></span>

3. <span data-ttu-id="58dda-167">Az **Adatbázis-napló tisztítása** lapon megadhatja, hogy mikor fusson a naplókarbantartási feladat.</span><span class="sxs-lookup"><span data-stu-id="58dda-167">Use the **Database log cleanup** tab to determine when to run the log cleanup task.</span></span> <span data-ttu-id="58dda-168">Alapértelmezés szerint az adatbázisnaplók 30 napig érhetők el.</span><span class="sxs-lookup"><span data-stu-id="58dda-168">By default, database logs are available for 30 days.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
