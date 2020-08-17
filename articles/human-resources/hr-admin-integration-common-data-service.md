---
title: Common Data Service-integráció konfigurálása
description: A Common Data Service és a Dynamics 365 Human Resources között be- és kikacsolhatja az integrációt. Ezenkívül megtekintheti a szinkronizálási adatokat, törölheti a nyomonkövetési adatokat, valamint újraszinkronizálhat egy entitást a két környezet közötti adatproblémák elhárítása érdekében.
author: andreabichsel
manager: AnnBe
ms.date: 07/27/2020
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
ms.openlocfilehash: 8cbead2961c4576a5394080aae2fec109bce3f10
ms.sourcegitcommit: 4a981ee4be6d7e6c0e55541535d386bce2565cba
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/27/2020
ms.locfileid: "3621304"
---
# <a name="configure-common-data-service-integration"></a><span data-ttu-id="fa5b9-104">Common Data Service-integráció konfigurálása</span><span class="sxs-lookup"><span data-stu-id="fa5b9-104">Configure Common Data Service integration</span></span>

<span data-ttu-id="fa5b9-105">A Common Data Service és a Dynamics 365 Human Resources között be- és kikacsolhatja az integrációt.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-105">You can turn integration between Common Data Service and Dynamics 365 Human Resources on or off.</span></span> <span data-ttu-id="fa5b9-106">Ezenkívül megtekintheti a szinkronizálási adatokat, törölheti a nyomonkövetési adatokat, valamint újraszinkronizálhat egy entitást a két környezet közötti adatproblémák elhárítása érdekében.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-106">You can also view the synchronization details, clear tracking data, and resync an entity to help troubleshoot data issues between the two environments.</span></span>

<span data-ttu-id="fa5b9-107">Ha kikapcsolja az integrációt, a felhasználók módosíthatják az emberi erőforrásokat vagy a Common Data Service megoldást, de ezek a módosítások nem szinkronizálhatók a két környezet között.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-107">When you turn off integration, users can make changes in Human Resources or Common Data Service, but those changes aren't synced between the two environments.</span></span>

<span data-ttu-id="fa5b9-108">Az adatintegráció Human Resources és a Common Data Service között alapértelmezetten ki van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-108">By default, integration between Human Resources and Common Data Service is turned off.</span></span>

<span data-ttu-id="fa5b9-109">Előfordulhat, hogy a következő helyzetekben ki szeretné kapcsolni az integrációt:</span><span class="sxs-lookup"><span data-stu-id="fa5b9-109">You might want to turn off integration in these situations:</span></span>

- <span data-ttu-id="fa5b9-110">Az adatokat az adatkezelési keretrendszeren keresztül tölti ki, és az adatokat többször kell importálni, hogy a megfelelő állapotba kerüljenek.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-110">You're filling in data through the Data Management Framework and must import the data multiple times to get it into a correct state.</span></span>

- <span data-ttu-id="fa5b9-111">Probléma adódott az adatokkal a Human Resources vagy a Common Data Service programok valamelyikében.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-111">There are issues with data in either Human Resources or Common Data Service.</span></span> <span data-ttu-id="fa5b9-112">Ha kikapcsolta az integrációt, akkor úgy törölhet egy rekordot az egyik környezetből, hogy az a másikban megmarad.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-112">If you turn off integration, you can delete a record in one environment without deleting it in the other.</span></span> <span data-ttu-id="fa5b9-113">Amikor újra bekapcsolja az integrációt, az a rekord, amelynek környezetében nem történt törlés, szinkronizálva lesz abba a környezetbe, ahonnan törölte azt.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-113">When you turn integration back on, the record in the environment where it wasn't deleted sync to the environment where it was deleted.</span></span> <span data-ttu-id="fa5b9-114">A szinkronizálás azután kezdődik, hogy a **Common Data Service-integráció nem fogadott kérelemszinkronizálási** kötegelt feladatot futtatja.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-114">Synchronization begins the next time the **Common Data Service integration missed request sync** batch job runs.</span></span>

> [!WARNING]
> <span data-ttu-id="fa5b9-115">Az adatintegráció kikapcsolásakor ügyeljen arra, hogy ne szerkessze mindkét környezetben ugyanazt a rekordot.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-115">When you turn off data integration, make sure that you don't edit the same record in both environments.</span></span> <span data-ttu-id="fa5b9-116">Az integráció visszakapcsolásakor az utoljára szerkesztett rekordot szinkronizálja a rendszer.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-116">When you turn integration back on, the record that you last edited will be synced.</span></span> <span data-ttu-id="fa5b9-117">Ezért ha nem ugyanazokat a változtatásokat hajtotta végre a rekordon mindkét környezetben, adatvesztés léphet fel.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-117">Therefore, if you didn't make the same changes to the record in both environments, data loss can occur.</span></span>

## <a name="access-the-common-data-service-integration-page"></a><span data-ttu-id="fa5b9-118">A Common Data Service-integráció oldal elérése</span><span class="sxs-lookup"><span data-stu-id="fa5b9-118">Access the Common Data Service integration page</span></span>

1. <span data-ttu-id="fa5b9-119">Abban a Human Resources példányban, ahol megtekinteni vagy konfigurálni szeretné a Common Data Service rendszerrel való integrációs beállításokat, válassza ki a **Rendszerfelügyelet** csempét.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-119">In the Human Resources instance where you want to view or configure settings for the integration with Common Data Service, select the **System administration** tile.</span></span>

    <span data-ttu-id="fa5b9-120">[![Rendszerfelügyelet csempe](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)</span><span class="sxs-lookup"><span data-stu-id="fa5b9-120">[![System administration tile](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)</span></span>

2. <span data-ttu-id="fa5b9-121">Válassza ki a **Hivatkozások** lapot.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-121">Select the **Links** tab.</span></span>

    <span data-ttu-id="fa5b9-122">[![Hivatkozások lap](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)</span><span class="sxs-lookup"><span data-stu-id="fa5b9-122">[![Links tab](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)</span></span>

3. <span data-ttu-id="fa5b9-123">Az **Integrációk** menüpontban válassza a **Common Data Service konfigurációja** elemet.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-123">Under **Integrations**, select **Common Data Service configuration**.</span></span>

    <span data-ttu-id="fa5b9-124">[![Common Data Service konfigurációs hivatkozása](./media/hr-select-common-data-service-configuration.png)](./media/hr-select-common-data-service-configuration.png)</span><span class="sxs-lookup"><span data-stu-id="fa5b9-124">[![Common Data Service configuration link](./media/hr-select-common-data-service-configuration.png)](./media/hr-select-common-data-service-configuration.png)</span></span>

## <a name="turn-data-integration-between-human-resources-and-common-data-service-on-or-off"></a><span data-ttu-id="fa5b9-125">Adatintegráció be- vagy kikapcsolása a Human Resources és a Common Data Service között</span><span class="sxs-lookup"><span data-stu-id="fa5b9-125">Turn data integration between Human Resources and Common Data Service on or off</span></span>

- <span data-ttu-id="fa5b9-126">Ha be szeretné kapcsolni az integrációt, állítsa be, hogy az **Integráció engedélyezése a Common Data Service rendszerben** beállításának értéke **Igen** legyen.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-126">To turn on integration, set the **Enable the integration to the Common Data Service** option to **Yes**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fa5b9-127">Amikor bekapcsolja az integrációt, az adatok szinkronizálása az után történik meg, hogy a **Common Data Service-integráció nem fogadott kérelemszinkronizálási** kötegelt feladatot futtatja.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-127">When you turn on integration, data will be synced the next time that the **Common Data Service integration missed request sync** batch job runs.</span></span> <span data-ttu-id="fa5b9-128">Minden adatnak elérhetőnek kell lennie a kötegelt feladat befejezése után.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-128">All data should be available after the batch job is completed.</span></span>

- <span data-ttu-id="fa5b9-129">Ha ki szeretné kapcsolni az integrációt, állítsa át a beállítást **Nem** értékre.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-129">To turn off integration, set the option to **No**.</span></span>

<span data-ttu-id="fa5b9-130">[![Common Data Service-integráció be- és kikapcsolása](./media/hr-enable-or-disable-common-data-service-integration.png)](./media/hr-enable-or-disable-common-data-service-integration.png)</span><span class="sxs-lookup"><span data-stu-id="fa5b9-130">[![Turning the Common Data Service integration on or off](./media/hr-enable-or-disable-common-data-service-integration.png)](./media/hr-enable-or-disable-common-data-service-integration.png)</span></span>

> [!WARNING]
> <span data-ttu-id="fa5b9-131">Az adatáttelepítési feladatok végrehajtása közben erősen ajánlott kikapcsolni a Common Data Service integrációt.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-131">We strongly recommend turning off Common Data Service integration while performing data migration tasks.</span></span> <span data-ttu-id="fa5b9-132">A nagyméretű adatfeltöltések jelentősen befolyásolhatják a teljesítményt.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-132">Large data uploads can significantly impact performance.</span></span> <span data-ttu-id="fa5b9-133">Például 2000 dolgozó feltöltése több óráig is eltarthat, ha engedélyezve van az integráció, viszont kevesebb mint egy óráig tart, ha le van letiltva.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-133">For example, uploading 2000 workers can take several hours when integration is enabled, and less than one hour when it's disabled.</span></span> <span data-ttu-id="fa5b9-134">A jelen példában megadott számok csak bemutató célt szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-134">The numbers provided in this example are for demonstration purposes only.</span></span> <span data-ttu-id="fa5b9-135">A rekordok importálásához szükséges idő pontos mértékét számos tényező befolyásolhatja.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-135">The exact amount of time it takes to import records can vary greatly based on many factors.</span></span>

## <a name="view-data-integration-details"></a><span data-ttu-id="fa5b9-136">Az adatintegráció részleteinek áttekintése</span><span class="sxs-lookup"><span data-stu-id="fa5b9-136">View data integration details</span></span>

<span data-ttu-id="fa5b9-137">Az **Adminisztráció** gyorslapon, amely a **Common Data Service-integráció** oldalon található, megtekintheti a rekordok összekapcsolásának módját a Human Resources és a Common Data Service között.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-137">On the **Administration** FastTab of the **Common Data Service integration** page, you can see how records are linked together between Human Resources and Common Data Service.</span></span>

- <span data-ttu-id="fa5b9-138">Egy entitás rekordjainak megtekintéséhez válassza ki az entitást a **CDS-entitás neve** mezőben.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-138">To view the records for an entity, select the entity in the **CDS entity name** field.</span></span> <span data-ttu-id="fa5b9-139">A rács a kiválasztott entitáshoz kapcsolódó összes rekordot megjeleníti.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-139">The grid shows all the records that are linked to the selected entity.</span></span>

<span data-ttu-id="fa5b9-140">[![Entitás rekordjainak megtekintése](./media/hr-common-data-service-configuration-view-entity.png)](./media/hr-common-data-service-configuration-view-entity.png)</span><span class="sxs-lookup"><span data-stu-id="fa5b9-140">[![Viewing the records for an entity](./media/hr-common-data-service-configuration-view-entity.png)](./media/hr-common-data-service-configuration-view-entity.png)</span></span>

> [!NOTE]
> <span data-ttu-id="fa5b9-141">Jelenleg nem minden Common Data Service-entitás szerepel a listán.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-141">Not all Common Data Service entities are currently listed.</span></span> <span data-ttu-id="fa5b9-142">Csak olyan entitások jelennek meg, amelyek támogatják az egyéni mezők használatát a rácsban.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-142">Only entities that support the use of custom fields appear in the grid.</span></span> <span data-ttu-id="fa5b9-143">Az új entitások a Human Resources folyamatos termékkiadásai révén válnak elérhetővé.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-143">New entities become available through continuous releases of Human Resources.</span></span>

<span data-ttu-id="fa5b9-144">A rács a következő mezőket tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="fa5b9-144">The grid includes the following fields:</span></span>

- <span data-ttu-id="fa5b9-145">**CDS-entitás neve** – a Common Data Service rendszerben található entitás neve.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-145">**CDS entity name** – The name of the entity in Common Data Service.</span></span>
- <span data-ttu-id="fa5b9-146">**CDS-entitás referenciája** – a Common Data Service által rekord azonosítására használt azonosító.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-146">**CDS entity reference** – The identifier that Common Data Service uses to identify a record.</span></span> <span data-ttu-id="fa5b9-147">Ez az érték egyenértékű a Human Resources rendszerben található **RecId**-értékkel.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-147">This value is equivalent to a Human Resources **RecId** value.</span></span> <span data-ttu-id="fa5b9-148">Az azonosítót akkor találja meg, ha megnyitja a Common Data Service-entitást a Microsoft Excel programban.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-148">You can find the identifier when you open the Common Data Service entity in Microsoft Excel.</span></span>
- <span data-ttu-id="fa5b9-149">**Human Resources-entitás neve** – az az entitás, amely utoljára szinkronizált adatokat a Common Data Service rendszerbe.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-149">**Human Resources entity name** – The entity that last synced data to Common Data Service.</span></span> <span data-ttu-id="fa5b9-150">Az entitás Common Data Service előtaggal vagy egy másik előtaggal rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-150">The entity can have either the Common Data Service prefix or another prefix.</span></span>
- <span data-ttu-id="fa5b9-151">**Human Resources-referencia** – az a **RecId**-érték, amely a Human Resources alkalmazásban található rekordhoz van társítva.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-151">**Human Resources reference** – The **RecId** value that is associated with the record in Human Resources.</span></span>
- <span data-ttu-id="fa5b9-152">**Törölve a CDS-ből** – az az érték, amely azt jelzi, hogy a rekordot törölték-e a Common Data Service rendszerből.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-152">**Was deleted from CDS** – A value that indicates whether the record was deleted from Common Data Service.</span></span>

## <a name="remove-the-association-of-a-record-in-human-resources-from-common-data-service"></a><span data-ttu-id="fa5b9-153">A Common Data Service rendszerből való rekordtársítás eltávolítása a Human Resources rendszerben</span><span class="sxs-lookup"><span data-stu-id="fa5b9-153">Remove the association of a record in Human Resources from Common Data Service</span></span>

<span data-ttu-id="fa5b9-154">Ha problémák merülnének fel a Human Resources és a Common Data Service közötti adatszinkronizálás során, a nyomon követés törlésével és a nyomonkövetési tábla újraszinkronizálásával feloldhatja őket.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-154">If you experience issues during data synchronization between Human Resources and Common Data Service, you might be able to resolve them by clearing the tracking and letting the tracking table be resynced.</span></span> <span data-ttu-id="fa5b9-155">Ha eltávolítja a társítást, majd módosítja vagy törli a rekordot a Common Data Service rendszerben, a rendszer a módosításokat nem szinkronizálja a Human Resources alkalmazással.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-155">If you remove the association, and then change or delete a record in Common Data Service, the changes won't be synced to Human Resources.</span></span> <span data-ttu-id="fa5b9-156">Ha módosításokat hajt végre a Human Resources alkalmazásban, létrejön egy új nyomonkövetési rekord, majd a rekord frissül a Common Data Service rendszerben.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-156">If you make changes in Human Resources, a new tracking record is created, and the record is updated in Common Data Service.</span></span>

- <span data-ttu-id="fa5b9-157">Ha el szeretne távolítani egy rekordtársítást a Human Resources és a Common Data Service között, válassza ki az entitást a **CDS-entitás neve** mezőben, majd válassza a **Nyomonkövetési adatok törlése** elemet.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-157">To remove the association of a record between Human Resources and Common Data Service, select the entity in the **CDS entity name** field, and then select **Clear tracking information**.</span></span>

<span data-ttu-id="fa5b9-158">[![Nyomonkövetési adatok törlése](./media/hr-common-data-service-configuration-clear-tracking.png)](./media/hr-common-data-service-configuration-clear-tracking.png)</span><span class="sxs-lookup"><span data-stu-id="fa5b9-158">[![Clearing tracking information](./media/hr-common-data-service-configuration-clear-tracking.png)](./media/hr-common-data-service-configuration-clear-tracking.png)</span></span>

<span data-ttu-id="fa5b9-159">Ha szeretné, hogy a nyomon követés törlése után teljes szinkronizálás fusson az entitáson, tekintse meg a következő eljárást.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-159">To run a full synchronization on the entity after you clear the tracking, see the next procedure.</span></span>

## <a name="sync-an-entity-between-human-resources-and-common-data-service"></a><span data-ttu-id="fa5b9-160">Entitás szinkronizálása a Human Resources és a Common Data Service között</span><span class="sxs-lookup"><span data-stu-id="fa5b9-160">Sync an entity between Human Resources and Common Data Service</span></span>

<span data-ttu-id="fa5b9-161">Ez a művelet akkor használható, ha:</span><span class="sxs-lookup"><span data-stu-id="fa5b9-161">Use this procedure when:</span></span>

- <span data-ttu-id="fa5b9-162">A Common Data Service változásai túl lassan jelennek meg a Human Resources alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-162">Changes from Common Data Service take too long to appear in Human Resources.</span></span>

- <span data-ttu-id="fa5b9-163">A nyomon követés törlése után frissítenie kell a nyomon követési táblát.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-163">You must refresh the tracking table after clearing the tracking.</span></span>

<span data-ttu-id="fa5b9-164">Teljes szinkronizálás futtatása egy entitáshoz a Human Resources és Common Data Service között:</span><span class="sxs-lookup"><span data-stu-id="fa5b9-164">To run a full synchronization on an entity between Human Resources and Common Data Service:</span></span>

1. <span data-ttu-id="fa5b9-165">A **CDS-entitás neve** mezőben válassza ki az entitást.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-165">Select the entity in the **CDS entity name** field.</span></span>

2. <span data-ttu-id="fa5b9-166">Válassza a **Szinkronizálás most** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-166">Select **Sync now**.</span></span>

<span data-ttu-id="fa5b9-167">[![Teljes szinkronizálás futtatása](./media/hr-common-data-service-configuration-sync-now.png)](./media/hr-common-data-service-configuration-sync-now.png)</span><span class="sxs-lookup"><span data-stu-id="fa5b9-167">[![Running a full synchronization](./media/hr-common-data-service-configuration-sync-now.png)](./media/hr-common-data-service-configuration-sync-now.png)</span></span>


