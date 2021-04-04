---
title: Dataverse-integráció konfigurálása
description: A Microsoft Dataverse és a Dynamics 365 Human Resources között be- és kikacsolhatja az integrációt. Ezenkívül megtekintheti a szinkronizálási adatokat, törölheti a nyomonkövetési adatokat, valamint újraszinkronizálhat egy táblát a két környezet közötti adatproblémák elhárítása érdekében.
author: andreabichsel
manager: tfehr
ms.date: 01/25/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: CDSIntegrationAdministration
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 73e2d2d56da812060961c34d7cb72b71b6b2df34
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/17/2021
ms.locfileid: "5465798"
---
# <a name="configure-dataverse-integration"></a><span data-ttu-id="d6607-104">Dataverse-integráció konfigurálása</span><span class="sxs-lookup"><span data-stu-id="d6607-104">Configure Dataverse integration</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="d6607-105">A Microsoft Dataverse és a Dynamics 365 Human Resources között be- és kikacsolhatja az integrációt.</span><span class="sxs-lookup"><span data-stu-id="d6607-105">You can turn integration between Microsoft Dataverse and Dynamics 365 Human Resources on or off.</span></span> <span data-ttu-id="d6607-106">Ezenkívül megtekintheti a szinkronizálási adatokat, törölheti a nyomonkövetési adatokat, valamint újraszinkronizálhat egy táblát a két környezet közötti adatproblémák elhárítása érdekében.</span><span class="sxs-lookup"><span data-stu-id="d6607-106">You can also view the synchronization details, clear tracking data, and resync a table to help troubleshoot data issues between the two environments.</span></span>

> [!NOTE]
> <span data-ttu-id="d6607-107">A Dataverse (a korábbi Common Data Service) rendszer kapcsolatos további tudnivalókat és a terminológiai frissítéseket lásd: [Mi a Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)</span><span class="sxs-lookup"><span data-stu-id="d6607-107">For more information about Dataverse (formerly Common Data Service) and terminology updates, see [What is Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)</span></span>

<span data-ttu-id="d6607-108">Ha kikapcsolja az integrációt, a felhasználók módosíthatják az emberi erőforrásokat vagy a Dataverse megoldást, de ezek a módosítások nem szinkronizálhatók a két környezet között.</span><span class="sxs-lookup"><span data-stu-id="d6607-108">When you turn off integration, users can make changes in Human Resources or Dataverse, but those changes aren't synced between the two environments.</span></span>

<span data-ttu-id="d6607-109">Az adatintegráció Human Resources és a Dataverse között alapértelmezetten ki van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="d6607-109">By default, integration between Human Resources and Dataverse is turned off.</span></span>

<span data-ttu-id="d6607-110">Előfordulhat, hogy a következő helyzetekben ki szeretné kapcsolni az integrációt:</span><span class="sxs-lookup"><span data-stu-id="d6607-110">You might want to turn off integration in these situations:</span></span>

- <span data-ttu-id="d6607-111">Az adatokat az adatkezelési keretrendszeren keresztül tölti ki, és az adatokat többször kell importálni, hogy a megfelelő állapotba kerüljenek.</span><span class="sxs-lookup"><span data-stu-id="d6607-111">You're filling in data through the Data Management Framework and must import the data multiple times to get it into a correct state.</span></span>

- <span data-ttu-id="d6607-112">Probléma adódott az adatokkal a Human Resources vagy a Dataverse programok valamelyikében.</span><span class="sxs-lookup"><span data-stu-id="d6607-112">There are issues with data in either Human Resources or Dataverse.</span></span> <span data-ttu-id="d6607-113">Ha kikapcsolta az integrációt, akkor úgy törölhet egy rekordot az egyik környezetből, hogy az a másikban megmarad.</span><span class="sxs-lookup"><span data-stu-id="d6607-113">If you turn off integration, you can delete a record in one environment without deleting it in the other.</span></span> <span data-ttu-id="d6607-114">Amikor újra bekapcsolja az integrációt, az a rekord, amelynek környezetében nem történt törlés, szinkronizálva lesz abba a környezetbe, ahonnan törölte azt.</span><span class="sxs-lookup"><span data-stu-id="d6607-114">When you turn integration back on, the record in the environment where it wasn't deleted sync to the environment where it was deleted.</span></span> <span data-ttu-id="d6607-115">A szinkronizálás azután kezdődik, hogy a **Dataverse-integráció nem fogadott kérelemszinkronizálási** kötegelt feladatot futtatja.</span><span class="sxs-lookup"><span data-stu-id="d6607-115">Synchronization begins the next time the **Dataverse integration missed request sync** batch job runs.</span></span>

> [!WARNING]
> <span data-ttu-id="d6607-116">Az adatintegráció kikapcsolásakor ügyeljen arra, hogy ne szerkessze mindkét környezetben ugyanazt a rekordot.</span><span class="sxs-lookup"><span data-stu-id="d6607-116">When you turn off data integration, make sure that you don't edit the same record in both environments.</span></span> <span data-ttu-id="d6607-117">Az integráció visszakapcsolásakor az utoljára szerkesztett rekordot szinkronizálja a rendszer.</span><span class="sxs-lookup"><span data-stu-id="d6607-117">When you turn integration back on, the record that you last edited will be synced.</span></span> <span data-ttu-id="d6607-118">Ezért ha nem ugyanazokat a változtatásokat hajtotta végre a rekordon mindkét környezetben, adatvesztés léphet fel.</span><span class="sxs-lookup"><span data-stu-id="d6607-118">Therefore, if you didn't make the same changes to the record in both environments, data loss can occur.</span></span>

## <a name="access-the-dataverse-integration-page"></a><span data-ttu-id="d6607-119">A Dataverse-integráció oldal elérése</span><span class="sxs-lookup"><span data-stu-id="d6607-119">Access the Dataverse integration page</span></span>

1. <span data-ttu-id="d6607-120">Abban a Human Resources példányban, ahol megtekinteni vagy konfigurálni szeretné a Dataverse rendszerrel való integrációs beállításokat, válassza ki a **Rendszerfelügyelet** csempét.</span><span class="sxs-lookup"><span data-stu-id="d6607-120">In the Human Resources instance where you want to view or configure settings for the integration with Dataverse, select the **System administration** tile.</span></span>

    <span data-ttu-id="d6607-121">[![Rendszerfelügyelet csempe](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)</span><span class="sxs-lookup"><span data-stu-id="d6607-121">[![System administration tile](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)</span></span>

2. <span data-ttu-id="d6607-122">Válassza ki a **Hivatkozások** lapot.</span><span class="sxs-lookup"><span data-stu-id="d6607-122">Select the **Links** tab.</span></span>

    <span data-ttu-id="d6607-123">[![Hivatkozások lap](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)</span><span class="sxs-lookup"><span data-stu-id="d6607-123">[![Links tab](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)</span></span>

3. <span data-ttu-id="d6607-124">Az **Integrációk** menüpontban válassza a **Dataverse konfigurációja** elemet.</span><span class="sxs-lookup"><span data-stu-id="d6607-124">Under **Integrations**, select **Dataverse configuration**.</span></span>

    <span data-ttu-id="d6607-125">[![Dataverse konfigurációs hivatkozása](./media/hr-admin-integration-dataverse-select.png)](./media/hr-admin-integration-dataverse-select.png)</span><span class="sxs-lookup"><span data-stu-id="d6607-125">[![Dataverse configuration link](./media/hr-admin-integration-dataverse-select.png)](./media/hr-admin-integration-dataverse-select.png)</span></span>

## <a name="turn-data-integration-between-human-resources-and-dataverse-on-or-off"></a><span data-ttu-id="d6607-126">Adatintegráció be- vagy kikapcsolása a Human Resources és a Dataverse között</span><span class="sxs-lookup"><span data-stu-id="d6607-126">Turn data integration between Human Resources and Dataverse on or off</span></span>

- <span data-ttu-id="d6607-127">Ha be szeretné kapcsolni az integrációt, állítsa be, hogy **Microsoft Dataverse-integráció** oldalon a **Dataverse-integráció engedélyezése** értéke **Igen** legyen.</span><span class="sxs-lookup"><span data-stu-id="d6607-127">To turn on integration, set the **Enable Dataverse integration** option to **Yes** on the **Microsoft Dataverse integration** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d6607-128">Amikor bekapcsolja az integrációt, az adatok szinkronizálása az után történik meg, hogy a **Dataverse-integráció nem fogadott kérelemszinkronizálási** kötegelt feladatot futtatja.</span><span class="sxs-lookup"><span data-stu-id="d6607-128">When you turn on integration, data will be synced the next time that the **Dataverse integration missed request sync** batch job runs.</span></span> <span data-ttu-id="d6607-129">Minden adatnak elérhetőnek kell lennie a kötegelt feladat befejezése után.</span><span class="sxs-lookup"><span data-stu-id="d6607-129">All data should be available after the batch job is completed.</span></span>

- <span data-ttu-id="d6607-130">Ha ki szeretné kapcsolni az integrációt, állítsa át a beállítást **Nem** értékre.</span><span class="sxs-lookup"><span data-stu-id="d6607-130">To turn off integration, set the option to **No**.</span></span>

<span data-ttu-id="d6607-131">[![Dataverse-integráció be- és kikapcsolása](./media/hr-admin-integration-dataverse-enable-disable.png)](./media/hr-admin-integration-dataverse-enable-disable.png)</span><span class="sxs-lookup"><span data-stu-id="d6607-131">[![Turning the Dataverse integration on or off](./media/hr-admin-integration-dataverse-enable-disable.png)](./media/hr-admin-integration-dataverse-enable-disable.png)</span></span>

> [!WARNING]
> <span data-ttu-id="d6607-132">Az adatáttelepítési feladatok végrehajtása közben erősen ajánlott kikapcsolni a Dataverse integrációt.</span><span class="sxs-lookup"><span data-stu-id="d6607-132">We strongly recommend turning off Dataverse integration while performing data migration tasks.</span></span> <span data-ttu-id="d6607-133">A nagyméretű adatfeltöltések jelentősen befolyásolhatják a teljesítményt.</span><span class="sxs-lookup"><span data-stu-id="d6607-133">Large data uploads can significantly impact performance.</span></span> <span data-ttu-id="d6607-134">Például 2000 dolgozó feltöltése több óráig is eltarthat, ha engedélyezve van az integráció, viszont kevesebb mint egy óráig tart, ha le van letiltva.</span><span class="sxs-lookup"><span data-stu-id="d6607-134">For example, uploading 2000 workers can take several hours when integration is enabled, and less than one hour when it's disabled.</span></span> <span data-ttu-id="d6607-135">A jelen példában megadott számok csak bemutató célt szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="d6607-135">The numbers provided in this example are for demonstration purposes only.</span></span> <span data-ttu-id="d6607-136">A rekordok importálásához szükséges idő pontos mértékét számos tényező befolyásolhatja.</span><span class="sxs-lookup"><span data-stu-id="d6607-136">The exact amount of time it takes to import records can vary greatly based on many factors.</span></span>

## <a name="view-data-integration-details"></a><span data-ttu-id="d6607-137">Az adatintegráció részleteinek áttekintése</span><span class="sxs-lookup"><span data-stu-id="d6607-137">View data integration details</span></span>

<span data-ttu-id="d6607-138">Az **Adminisztráció** gyorslapon, amely a **Microsoft Dataverse-integráció** oldalon található, megtekintheti a sorok összekapcsolásának módját a Human Resources és a Dataverse között.</span><span class="sxs-lookup"><span data-stu-id="d6607-138">On the **Administration** FastTab of the **Microsoft Dataverse integration** page, you can see how rows are linked together between Human Resources and Dataverse.</span></span>

- <span data-ttu-id="d6607-139">A tábla sorainak megtekintéséhez válassza ki táblát a **Dataverse-tábla** mezőben.</span><span class="sxs-lookup"><span data-stu-id="d6607-139">To view the rows for a table, select the table in the **Dataverse table** field.</span></span> <span data-ttu-id="d6607-140">A rács a kiválasztott táblához kapcsolódó összes sort megjeleníti.</span><span class="sxs-lookup"><span data-stu-id="d6607-140">The grid shows all the rows that are linked to the selected table.</span></span>

> [!NOTE]
> <span data-ttu-id="d6607-141">Jelenleg nem minden Dataverse-tábla szerepel a listán.</span><span class="sxs-lookup"><span data-stu-id="d6607-141">Not all Dataverse tables are currently listed.</span></span> <span data-ttu-id="d6607-142">Csak olyan táblák jelennek meg, amelyek támogatják az egyéni mezők használatát a rácsban.</span><span class="sxs-lookup"><span data-stu-id="d6607-142">Only tables that support the use of custom fields appear in the grid.</span></span> <span data-ttu-id="d6607-143">Az új táblák a Human Resources folyamatos termékkiadásai révén válnak elérhetővé.</span><span class="sxs-lookup"><span data-stu-id="d6607-143">New tables become available through continuous releases of Human Resources.</span></span>

<span data-ttu-id="d6607-144">A rács a következő mezőket tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="d6607-144">The grid includes the following fields:</span></span>

- <span data-ttu-id="d6607-145">**Dataverse-tábla** – a Dataverse-tábla neve.</span><span class="sxs-lookup"><span data-stu-id="d6607-145">**Dataverse table** – The name of the table in Dataverse.</span></span>
- <span data-ttu-id="d6607-146">**Dataverse-tábla referenciája** – a Dataverse által rekord azonosítására használt azonosító.</span><span class="sxs-lookup"><span data-stu-id="d6607-146">**Dataverse table reference** – The identifier that Dataverse uses to identify a record.</span></span> <span data-ttu-id="d6607-147">Ez az érték egyenértékű a Human Resources rendszerben található **RecId**-értékkel.</span><span class="sxs-lookup"><span data-stu-id="d6607-147">This value is equivalent to a Human Resources **RecId** value.</span></span> <span data-ttu-id="d6607-148">Az azonosítót akkor találja meg, ha megnyitja a Dataverse-táblát a Microsoft Excel programban.</span><span class="sxs-lookup"><span data-stu-id="d6607-148">You can find the identifier when you open the Dataverse table in Microsoft Excel.</span></span>
- <span data-ttu-id="d6607-149">**Human Resources-entitás neve** – az a Human Resources-entitás, amely utoljára szinkronizált adatokat a Dataverse rendszerbe.</span><span class="sxs-lookup"><span data-stu-id="d6607-149">**Human Resources entity name** – The Human Resources entity that last synced data to Dataverse.</span></span> <span data-ttu-id="d6607-150">Az entitás Dataverse előtaggal vagy egy másik előtaggal rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="d6607-150">The entity can have either the Dataverse prefix or another prefix.</span></span>
- <span data-ttu-id="d6607-151">**Human Resources-referencia** – az a **RecId**-érték, amely a Human Resources alkalmazásban található rekordhoz van társítva.</span><span class="sxs-lookup"><span data-stu-id="d6607-151">**Human Resources reference** – The **RecId** value that is associated with the record in Human Resources.</span></span>
- <span data-ttu-id="d6607-152">**Törölve a Dataverse-ből** – az az érték, amely azt jelzi, hogy a sort törölték-e a Dataverse rendszerből.</span><span class="sxs-lookup"><span data-stu-id="d6607-152">**Deleted from Dataverse** – A value that indicates whether the row was deleted from Dataverse.</span></span>

> [!NOTE]
> <span data-ttu-id="d6607-153">A Human Resources rekordjai a Dataverse rendszerben lévő soroknak felelnek meg.</span><span class="sxs-lookup"><span data-stu-id="d6607-153">Records in Human Resources correspond to rows in Dataverse.</span></span>

## <a name="remove-the-association-of-a-human-resources-record-from-a-dataverse-row"></a><span data-ttu-id="d6607-154">Human Resources-rekordtársítás eltávolítása egy Dataverse-sorból</span><span class="sxs-lookup"><span data-stu-id="d6607-154">Remove the association of a Human Resources record from a Dataverse row</span></span>

<span data-ttu-id="d6607-155">Ha problémák merülnének fel a Human Resources és a Dataverse közötti adatszinkronizálás során, a nyomon követés törlésével és a nyomonkövetési tábla újraszinkronizálásával feloldhatja őket.</span><span class="sxs-lookup"><span data-stu-id="d6607-155">If you experience issues during data synchronization between Human Resources and Dataverse, you might be able to resolve them by clearing the tracking and letting the tracking table be resynced.</span></span> <span data-ttu-id="d6607-156">Ha eltávolítja a társítást, majd módosítja vagy törli a sort a Dataverse rendszerben, a rendszer a módosításokat nem szinkronizálja a Human Resources alkalmazással.</span><span class="sxs-lookup"><span data-stu-id="d6607-156">If you remove the association, and then change or delete a row in Dataverse, the changes won't be synced to Human Resources.</span></span> <span data-ttu-id="d6607-157">Ha módosításokat hajt végre a Human Resources alkalmazásban, létrejön egy új nyomonkövetési rekord, majd a sor frissül a Dataverse rendszerben.</span><span class="sxs-lookup"><span data-stu-id="d6607-157">If you make changes in Human Resources, a new tracking record is created, and the row is updated in Dataverse.</span></span>

- <span data-ttu-id="d6607-158">Ha el szeretne távolítani egy rekordtársítást a Human Resources és a Dataverse-sor között, válassza ki az entitást a **Dataverse-tábla** mezőben, majd válassza a **Nyomonkövetési adatok törlése** elemet.</span><span class="sxs-lookup"><span data-stu-id="d6607-158">To remove the association of a Human Resources record and a Dataverse row, select the table in the **Dataverse table** field, and then select **Clear tracking information**.</span></span>

<span data-ttu-id="d6607-159">[![Nyomonkövetési adatok törlése](./media/hr-admin-integration-dataverse-clear-tracking.png)](./media/hr-admin-integration-dataverse-clear-tracking.png)</span><span class="sxs-lookup"><span data-stu-id="d6607-159">[![Clearing tracking information](./media/hr-admin-integration-dataverse-clear-tracking.png)](./media/hr-admin-integration-dataverse-clear-tracking.png)</span></span>

<span data-ttu-id="d6607-160">Ha szeretné, hogy a nyomon követés törlése után teljes szinkronizálás fusson a táblán, tekintse meg a következő eljárást.</span><span class="sxs-lookup"><span data-stu-id="d6607-160">To run a full synchronization on the table after you clear the tracking, see the next procedure.</span></span>

## <a name="sync-a-table-between-human-resources-and-dataverse"></a><span data-ttu-id="d6607-161">Tábla szinkronizálása a Human Resources és a Dataverse között</span><span class="sxs-lookup"><span data-stu-id="d6607-161">Sync a table between Human Resources and Dataverse</span></span>

<span data-ttu-id="d6607-162">Ez a művelet akkor használható, ha:</span><span class="sxs-lookup"><span data-stu-id="d6607-162">Use this procedure when:</span></span>

- <span data-ttu-id="d6607-163">A Dataverse változásai túl lassan jelennek meg a Human Resources alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="d6607-163">Changes from Dataverse take too long to appear in Human Resources.</span></span>

- <span data-ttu-id="d6607-164">A nyomon követés törlése után frissítenie kell a nyomon követési táblát.</span><span class="sxs-lookup"><span data-stu-id="d6607-164">You must refresh the tracking table after clearing the tracking.</span></span>

<span data-ttu-id="d6607-165">Teljes szinkronizálás futtatása egy táblához a Human Resources és Dataverse között:</span><span class="sxs-lookup"><span data-stu-id="d6607-165">To run a full synchronization on a table between Human Resources and Dataverse:</span></span>

1. <span data-ttu-id="d6607-166">A **Dataverse-tábla** mezőben válassza ki a táblát.</span><span class="sxs-lookup"><span data-stu-id="d6607-166">Select the table in the **Dataverse table** field.</span></span>

2. <span data-ttu-id="d6607-167">Válassza a **Szinkronizálás most** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d6607-167">Select **Sync now**.</span></span>

<span data-ttu-id="d6607-168">[![Teljes szinkronizálás futtatása](./media/hr-admin-integration-dataverse-sync-now.png)](./media/hr-admin-integration-dataverse-sync-now.png)</span><span class="sxs-lookup"><span data-stu-id="d6607-168">[![Running a full synchronization](./media/hr-admin-integration-dataverse-sync-now.png)](./media/hr-admin-integration-dataverse-sync-now.png)</span></span>

## <a name="see-also"></a><span data-ttu-id="d6607-169">Lásd még</span><span class="sxs-lookup"><span data-stu-id="d6607-169">See also</span></span>

[<span data-ttu-id="d6607-170">Dataverse-táblák</span><span class="sxs-lookup"><span data-stu-id="d6607-170">Dataverse tables</span></span>](hr-developer-entities.md)<br>
[<span data-ttu-id="d6607-171">Dataverse virtuális táblák konfigurálása</span><span class="sxs-lookup"><span data-stu-id="d6607-171">Configure Dataverse virtual tables</span></span>](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[<span data-ttu-id="d6607-172">A Human Resources számára elérhető virtuális táblák – GYIK</span><span class="sxs-lookup"><span data-stu-id="d6607-172">Human Resources virtual tables FAQ</span></span>](hr-admin-virtual-entity-faq.md)<br>
[<span data-ttu-id="d6607-173">Mi az a Microsoft Dataverse?</span><span class="sxs-lookup"><span data-stu-id="d6607-173">What is Microsoft Dataverse?</span></span>](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)<br>
[<span data-ttu-id="d6607-174">Terminológia frissítései</span><span class="sxs-lookup"><span data-stu-id="d6607-174">Terminology updates</span></span>](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro#terminology-updates)


[!INCLUDE[footer-include](../includes/footer-banner.md)]