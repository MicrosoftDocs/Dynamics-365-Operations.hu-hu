---
title: Common Data Service-integráció konfigurálása
description: A Common Data Service és a Microsoft Dynamics 365 Human Resources egy példánya között be- és kikacsolhatja az integrációt. Ezenkívül megtekintheti a szinkronizálási adatokat, törölheti a nyomonkövetési adatokat, valamint újraszinkronizálhat egy entitást a két környezet közötti adatproblémák elhárítása érdekében.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
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
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 042daf3fdf7a906086af726472da050467d217e3
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009252"
---
# <a name="configure-common-data-service-integration"></a><span data-ttu-id="4076b-104">Common Data Service-integráció konfigurálása</span><span class="sxs-lookup"><span data-stu-id="4076b-104">Configure Common Data Service integration</span></span>

<span data-ttu-id="4076b-105">A Common Data Service és a Microsoft Dynamics 365 Human Resources egy példánya között be- és kikacsolhatja az integrációt.</span><span class="sxs-lookup"><span data-stu-id="4076b-105">You can turn integration between Common Data Service and an instance of Microsoft Dynamics 365 Human Resources on or off.</span></span> <span data-ttu-id="4076b-106">Ezenkívül megtekintheti a szinkronizálási adatokat, törölheti a nyomonkövetési adatokat, valamint újraszinkronizálhat egy entitást a két környezet közötti adatproblémák elhárítása érdekében.</span><span class="sxs-lookup"><span data-stu-id="4076b-106">You can also view the synchronization details, clear tracking data, and resync an entity to help troubleshoot data issues between the two environments.</span></span>

<span data-ttu-id="4076b-107">Ha kikapcsolja az integrációt, a felhasználók módosíthatják az emberi erőforrásokat vagy a Common Data Service megoldást, de ezek a módosítások nem szinkronizálhatók a két környezet között.</span><span class="sxs-lookup"><span data-stu-id="4076b-107">When you turn off integration, users can make changes in Human Resources or Common Data Service, but those changes aren't synced between the two environments.</span></span>

<span data-ttu-id="4076b-108">Alapértelmezés szerint a Human Resources és a Common Data Service megoldás közötti integráció kikapcsolt vagy bekapcsolt állapotban van a környezetekben lévő bemutatóadatok jelenlététől függően:</span><span class="sxs-lookup"><span data-stu-id="4076b-108">By default, integration between Human Resources and Common Data Service is turned either off or on, depending on the presence of demo data in the environments:</span></span>

- <span data-ttu-id="4076b-109">**Kikapcsolva** olyan új környezetek számára, amelyek nem tartalmaznak bemutatóadatokat</span><span class="sxs-lookup"><span data-stu-id="4076b-109">**Off** for new environments that don't include demo data</span></span>
- <span data-ttu-id="4076b-110">**Bekapcsolva** olyan új környezetek számára, amelyek tartalmaznak bemutatóadatokat</span><span class="sxs-lookup"><span data-stu-id="4076b-110">**On** for new environments that include demo data</span></span>

<span data-ttu-id="4076b-111">A bemutatóadatokat tartalmazó új környezetek a létesítéskor megkezdik az adatok szinkronizálását.</span><span class="sxs-lookup"><span data-stu-id="4076b-111">New environments that include demo data will start to sync data when they are provisioned.</span></span>

<span data-ttu-id="4076b-112">Előfordulhat, hogy a következő helyzetekben ki szeretné kapcsolni az integrációt:</span><span class="sxs-lookup"><span data-stu-id="4076b-112">You might want to turn off integration in these situations:</span></span>

- <span data-ttu-id="4076b-113">Az adatokat az adatkezelési keretrendszeren keresztül tölti ki, és az adatokat többször kell importálni, hogy a megfelelő állapotba kerüljenek.</span><span class="sxs-lookup"><span data-stu-id="4076b-113">You're filling in data through the Data Management Framework and must import the data multiple times to get it into a correct state.</span></span>

- <span data-ttu-id="4076b-114">Probléma adódott az adatokkal a Human Resources vagy a Common Data Service programok valamelyikében.</span><span class="sxs-lookup"><span data-stu-id="4076b-114">There are issues with data in either Human Resources or Common Data Service.</span></span> <span data-ttu-id="4076b-115">Ha kikapcsolta az integrációt, akkor úgy törölhet egy rekordot az egyik környezetből, hogy az a másikban megmarad.</span><span class="sxs-lookup"><span data-stu-id="4076b-115">If you turn off integration, you can delete a record in one environment without deleting it in the other.</span></span> <span data-ttu-id="4076b-116">Amikor újra bekapcsolja az integrációt, az a rekord, amelynek környezetében nem történt törlés, újra visszaszinkronizálódik abba a környezetbe, ahonnan törölte azt.</span><span class="sxs-lookup"><span data-stu-id="4076b-116">When you turn integration back on, the record in the environment where it wasn't deleted will be synced back to the environment where it was deleted.</span></span> <span data-ttu-id="4076b-117">A szinkronizálás azután kezdődik, hogy a **Common Data Service-integráció nem fogadott kérelemszinkronizálási** kötegelt feladatot futtatja.</span><span class="sxs-lookup"><span data-stu-id="4076b-117">Synchronization begins the next time the **Common Data Service integration missed request sync** batch job runs.</span></span>

> [!WARNING]
> <span data-ttu-id="4076b-118">Az adatintegráció kikapcsolásakor ügyeljen arra, hogy ne szerkessze mindkét környezetben ugyanazt a rekordot.</span><span class="sxs-lookup"><span data-stu-id="4076b-118">When you turn off data integration, make sure that you don't edit the same record in both environments.</span></span> <span data-ttu-id="4076b-119">Az integráció visszakapcsolásakor az utoljára szerkesztett rekordot szinkronizálja a rendszer.</span><span class="sxs-lookup"><span data-stu-id="4076b-119">When you turn integration back on, the record that you last edited will be synced.</span></span> <span data-ttu-id="4076b-120">Ezért ha nem ugyanazokat a változtatásokat hajtotta végre a rekordon mindkét környezetben, adatvesztés léphet fel.</span><span class="sxs-lookup"><span data-stu-id="4076b-120">Therefore, if you didn't make the same changes to the record in both environments, data loss can occur.</span></span>

## <a name="access-the-common-data-service-integration-page"></a><span data-ttu-id="4076b-121">A Common Data Service-integráció oldal elérése</span><span class="sxs-lookup"><span data-stu-id="4076b-121">Access the Common Data Service integration page</span></span>

1. <span data-ttu-id="4076b-122">Abban a Human Resources példányban, ahol megtekinteni vagy konfigurálni szeretné a Common Data Service rendszerrel való integrációs beállításokat, válassza ki a **Rendszerfelügyelet** csempét.</span><span class="sxs-lookup"><span data-stu-id="4076b-122">In the Human Resources instance where you want to view or configure settings for the integration with Common Data Service, select the **System administration** tile.</span></span>

    <span data-ttu-id="4076b-123">[![Rendszerfelügyelet csempe](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)</span><span class="sxs-lookup"><span data-stu-id="4076b-123">[![System administration tile](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)</span></span>

2. <span data-ttu-id="4076b-124">Válassza ki a **Hivatkozások** lapot.</span><span class="sxs-lookup"><span data-stu-id="4076b-124">Select the **Links** tab.</span></span>

    <span data-ttu-id="4076b-125">[![Hivatkozások lap](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)</span><span class="sxs-lookup"><span data-stu-id="4076b-125">[![Links tab](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)</span></span>

3. <span data-ttu-id="4076b-126">Az **Integrációk** menüpontban válassza a **Common Data Service konfigurációja** elemet.</span><span class="sxs-lookup"><span data-stu-id="4076b-126">Under **Integrations**, select **Common Data Service configuration**.</span></span>

    <span data-ttu-id="4076b-127">[![Common Data Service konfigurációs hivatkozása](./media/hr-select-common-data-service-configuration.png)](./media/hr-select-common-data-service-configuration.png)</span><span class="sxs-lookup"><span data-stu-id="4076b-127">[![Common Data Service configuration link](./media/hr-select-common-data-service-configuration.png)](./media/hr-select-common-data-service-configuration.png)</span></span>

## <a name="turn-data-integration-between-human-resources-and-common-data-service-on-or-off"></a><span data-ttu-id="4076b-128">Adatintegráció be- vagy kikapcsolása a Human Resources és a Common Data Service között</span><span class="sxs-lookup"><span data-stu-id="4076b-128">Turn data integration between Human Resources and Common Data Service on or off</span></span>

- <span data-ttu-id="4076b-129">Ha be szeretné kapcsolni az integrációt, állítsa be, hogy az **Integráció engedélyezése a Common Data Service rendszerben** beállításának értéke **Igen** legyen.</span><span class="sxs-lookup"><span data-stu-id="4076b-129">To turn on integration, set the **Enable the integration to the Common Data Service** option to **Yes**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4076b-130">Amikor bekapcsolja az integrációt, az adatok szinkronizálása az után történik meg, hogy a **Common Data Service-integráció nem fogadott kérelemszinkronizálási** kötegelt feladatot futtatja.</span><span class="sxs-lookup"><span data-stu-id="4076b-130">When you turn on integration, data will be synced the next time that the **Common Data Service integration missed request sync** batch job runs.</span></span> <span data-ttu-id="4076b-131">Minden adatnak elérhetőnek kell lennie a kötegelt feladat befejezése után.</span><span class="sxs-lookup"><span data-stu-id="4076b-131">All data should be available after the batch job is completed.</span></span>

- <span data-ttu-id="4076b-132">Ha ki szeretné kapcsolni az integrációt, állítsa át a beállítást **Nem** értékre.</span><span class="sxs-lookup"><span data-stu-id="4076b-132">To turn off integration, set the option to **No**.</span></span>

<span data-ttu-id="4076b-133">[![Common Data Service-integráció be- és kikapcsolása](./media/hr-enable-or-disable-common-data-service-integration.png)](./media/hr-enable-or-disable-common-data-service-integration.png)</span><span class="sxs-lookup"><span data-stu-id="4076b-133">[![Turning the Common Data Service integration on or off](./media/hr-enable-or-disable-common-data-service-integration.png)](./media/hr-enable-or-disable-common-data-service-integration.png)</span></span>

## <a name="view-data-integration-details"></a><span data-ttu-id="4076b-134">Az adatintegráció részleteinek áttekintése</span><span class="sxs-lookup"><span data-stu-id="4076b-134">View data integration details</span></span>

<span data-ttu-id="4076b-135">Az **Adminisztráció** gyorslapon, amely a **Common Data Service-integráció** oldalon található, megtekintheti a rekordok összekapcsolásának módját a Human Resources és a Common Data Service között.</span><span class="sxs-lookup"><span data-stu-id="4076b-135">On the **Administration** FastTab of the **Common Data Service integration** page, you can see how records are linked together between Human Resources and Common Data Service.</span></span>

- <span data-ttu-id="4076b-136">Egy entitás rekordjainak megtekintéséhez válassza ki az entitást a **CDS-entitás neve** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4076b-136">To view the records for an entity, select the entity in the **CDS entity name** field.</span></span> <span data-ttu-id="4076b-137">A rács a kiválasztott entitáshoz kapcsolódó összes rekordot megjeleníti.</span><span class="sxs-lookup"><span data-stu-id="4076b-137">The grid shows all the records that are linked to the selected entity.</span></span>

<span data-ttu-id="4076b-138">[![Entitás rekordjainak megtekintése](./media/hr-common-data-service-configuration-view-entity.png)](./media/hr-common-data-service-configuration-view-entity.png)</span><span class="sxs-lookup"><span data-stu-id="4076b-138">[![Viewing the records for an entity](./media/hr-common-data-service-configuration-view-entity.png)](./media/hr-common-data-service-configuration-view-entity.png)</span></span>

> [!NOTE]
> <span data-ttu-id="4076b-139">Jelenleg nem minden Common Data Service-entitás szerepel a listán.</span><span class="sxs-lookup"><span data-stu-id="4076b-139">Not all Common Data Service entities are currently listed.</span></span> <span data-ttu-id="4076b-140">Csak olyan entitások jelennek meg, amelyek támogatják az egyéni mezők használatát a rácsban.</span><span class="sxs-lookup"><span data-stu-id="4076b-140">Only entities that support the use of custom fields appear in the grid.</span></span> <span data-ttu-id="4076b-141">Az új entitások a Human Resources folyamatos termékkiadásai révén válnak elérhetővé.</span><span class="sxs-lookup"><span data-stu-id="4076b-141">New entities become available through continuous releases of Human Resources.</span></span>

<span data-ttu-id="4076b-142">A rács a következő mezőket tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="4076b-142">The grid includes the following fields:</span></span>

- <span data-ttu-id="4076b-143">**CDS-entitás neve** – a Common Data Service rendszerben található entitás neve.</span><span class="sxs-lookup"><span data-stu-id="4076b-143">**CDS entity name** – The name of the entity in Common Data Service.</span></span>
- <span data-ttu-id="4076b-144">**CDS-entitás referenciája** – a Common Data Service által rekord azonosítására használt azonosító.</span><span class="sxs-lookup"><span data-stu-id="4076b-144">**CDS entity reference** – The identifier that Common Data Service uses to identify a record.</span></span> <span data-ttu-id="4076b-145">Ez az érték egyenértékű a Human Resources rendszerben található **RecId**-értékkel.</span><span class="sxs-lookup"><span data-stu-id="4076b-145">This value is equivalent to a Human Resources **RecId** value.</span></span> <span data-ttu-id="4076b-146">Az azonosítót akkor találja meg, ha megnyitja a Common Data Service-entitást a Microsoft Excel programban.</span><span class="sxs-lookup"><span data-stu-id="4076b-146">You can find the identifier when you open the Common Data Service entity in Microsoft Excel.</span></span>
- <span data-ttu-id="4076b-147">**Human Resources-entitás neve** – az az entitás, amely utoljára szinkronizált adatokat a Common Data Service rendszerbe.</span><span class="sxs-lookup"><span data-stu-id="4076b-147">**Human Resources entity name** – The entity that last synced data to Common Data Service.</span></span> <span data-ttu-id="4076b-148">Az entitás Common Data Service előtaggal vagy egy másik előtaggal rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="4076b-148">The entity can have either the Common Data Service prefix or another prefix.</span></span>
- <span data-ttu-id="4076b-149">**Human Resources-referencia** – az a **RecId**-érték, amely a Human Resources alkalmazásban található rekordhoz van társítva.</span><span class="sxs-lookup"><span data-stu-id="4076b-149">**Human Resources reference** – The **RecId** value that is associated with the record in Human Resources.</span></span>
- <span data-ttu-id="4076b-150">**Törölve a CDS-ből** – az az érték, amely azt jelzi, hogy a rekordot törölték-e a Common Data Service rendszerből.</span><span class="sxs-lookup"><span data-stu-id="4076b-150">**Was deleted from CDS** – A value that indicates whether the record was deleted from Common Data Service.</span></span>

## <a name="remove-the-association-of-a-record-in-human-resources-from-common-data-service"></a><span data-ttu-id="4076b-151">A Common Data Service rendszerből való rekordtársítás eltávolítása a Human Resources rendszerben</span><span class="sxs-lookup"><span data-stu-id="4076b-151">Remove the association of a record in Human Resources from Common Data Service</span></span>

<span data-ttu-id="4076b-152">Ha problémák merülnének fel a Human Resources és a Common Data Service közötti adatszinkronizálás során, a nyomon követés törlésével és a nyomonkövetési tábla újraszinkronizálásával feloldhatja őket.</span><span class="sxs-lookup"><span data-stu-id="4076b-152">If you experience issues during data synchronization between Human Resources and Common Data Service, you might be able to resolve them by clearing the tracking and letting the tracking table be resynced.</span></span> <span data-ttu-id="4076b-153">Ha eltávolítja a társítást, majd módosítja vagy törli a rekordot a Common Data Service rendszerben, a rendszer a módosításokat nem szinkronizálja a Human Resources alkalmazással.</span><span class="sxs-lookup"><span data-stu-id="4076b-153">If you remove the association, and then change or delete a record in Common Data Service, the changes won't be synced to Human Resources.</span></span> <span data-ttu-id="4076b-154">Ha módosításokat hajt végre a Human Resources alkalmazásban, létrejön egy új nyomonkövetési rekord, majd a rekord frissül a Common Data Service rendszerben.</span><span class="sxs-lookup"><span data-stu-id="4076b-154">If you make changes in Human Resources, a new tracking record is created, and the record is updated in Common Data Service.</span></span>

- <span data-ttu-id="4076b-155">Ha el szeretne távolítani egy rekordtársítást a Human Resources és a Common Data Service között, válassza ki az entitást a **CDS-entitás neve** mezőben, majd válassza a **Nyomonkövetési adatok törlése** elemet.</span><span class="sxs-lookup"><span data-stu-id="4076b-155">To remove the association of a record between Human Resources and Common Data Service, select the entity in the **CDS entity name** field, and then select **Clear tracking information**.</span></span>

<span data-ttu-id="4076b-156">[![Nyomonkövetési adatok törlése](./media/hr-common-data-service-configuration-clear-tracking.png)](./media/hr-common-data-service-configuration-clear-tracking.png)</span><span class="sxs-lookup"><span data-stu-id="4076b-156">[![Clearing tracking information](./media/hr-common-data-service-configuration-clear-tracking.png)](./media/hr-common-data-service-configuration-clear-tracking.png)</span></span>

<span data-ttu-id="4076b-157">Ha szeretné, hogy a nyomon követés törlése után teljes szinkronizálás fusson az entitáson, tekintse meg a következő eljárást.</span><span class="sxs-lookup"><span data-stu-id="4076b-157">To run a full synchronization on the entity after you clear the tracking, see the next procedure.</span></span>

## <a name="sync-an-entity-between-human-resources-and-common-data-service"></a><span data-ttu-id="4076b-158">Entitás szinkronizálása a Human Resources és a Common Data Service között</span><span class="sxs-lookup"><span data-stu-id="4076b-158">Sync an entity between Human Resources and Common Data Service</span></span>

<span data-ttu-id="4076b-159">Akkor használja ezt az eljárást, ha a Common Data Service rendszerben végrehajtott módosítások túl sokára jelennek meg a Human Resources alkalmazásban, vagy ha a nyomon követés törlése után újra frissíteni kell a nyomonkövetési táblát.</span><span class="sxs-lookup"><span data-stu-id="4076b-159">Use this procedure if changes from Common Data Service are taking too long to appear in Human Resources, or if you must refresh the tracking table after you clear the tracking.</span></span>

- <span data-ttu-id="4076b-160">Ha teljes szinkronizálást szeretne futtatni egy entitáson a Human Resources és a Common Data Service között, válassza ki az entitást a **CDS-entitás neve**  mezőben, majd válassza a **Szinkronizálás most** parancsot.</span><span class="sxs-lookup"><span data-stu-id="4076b-160">To run a full synchronization on an entity between Human Resources and Common Data Service, select the entity in the **CDS entity name** field, and then select **Sync now**.</span></span>

<span data-ttu-id="4076b-161">[![Teljes szinkronizálás futtatása](./media/hr-common-data-service-configuration-sync-now.png)](./media/hr-common-data-service-configuration-sync-now.png)</span><span class="sxs-lookup"><span data-stu-id="4076b-161">[![Running a full synchronization](./media/hr-common-data-service-configuration-sync-now.png)](./media/hr-common-data-service-configuration-sync-now.png)</span></span>


