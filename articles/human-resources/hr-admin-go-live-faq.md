---
title: Éles indítás GYIK
description: Ez a témakör a Dynamics 365 Human Resources megvalósítási projekttel kapcsolatos gyakori kérdéseket sorolja fel.
author: rachel-profitt
ms.date: 10/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 550e094fd34bfbdc66665be2ceed306de722c0d9
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6055340"
---
# <a name="go-live-faq"></a><span data-ttu-id="26e34-103">Éles indítás GYIK</span><span class="sxs-lookup"><span data-stu-id="26e34-103">Go-live FAQ</span></span> 

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="26e34-104">Ez a témakör a Dynamics 365 Human Resources megvalósítási projekttel kapcsolatos gyakori kérdéseket sorolja fel.</span><span class="sxs-lookup"><span data-stu-id="26e34-104">This topic lists frequently asked questions about how to go live with a Dynamics 365 Human Resources implementation project.</span></span> 

## <a name="when-can-i-configure-and-request-my-production-environment"></a><span data-ttu-id="26e34-105">Mikor konfigurálhatom és kérelmezhetem az éles környezetemet?</span><span class="sxs-lookup"><span data-stu-id="26e34-105">When can I configure and request my production environment?</span></span> 

<span data-ttu-id="26e34-106">Az éles környezet általában a következő feltételek teljesítése után kerül üzembe helyezésre:</span><span class="sxs-lookup"><span data-stu-id="26e34-106">Typically, a production environment is deployed after meeting the following criteria:</span></span>

- <span data-ttu-id="26e34-107">Minden testreszabás kódja teljeskörű.</span><span class="sxs-lookup"><span data-stu-id="26e34-107">All customizations are code-complete.</span></span>
- <span data-ttu-id="26e34-108">A felhasználói elfogadási tesztelés (UAT) befejeződött.</span><span class="sxs-lookup"><span data-stu-id="26e34-108">User acceptance testing (UAT) is complete.</span></span>
- <span data-ttu-id="26e34-109">Az ügyfél jóváhagyta a megoldást.</span><span class="sxs-lookup"><span data-stu-id="26e34-109">The customer has signed off on the solution.</span></span>
- <span data-ttu-id="26e34-110">Nincsenek blokkoló problémák az éles indítással kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="26e34-110">There are no blocking issues for go-live.</span></span> 

<span data-ttu-id="26e34-111">Ha a minősített ügyfelek ebben a szakaszban vannak, a Microsoft FastTrack csapata a projektcsapattal együttműködve élő indítási értékelést készít.</span><span class="sxs-lookup"><span data-stu-id="26e34-111">When qualified customers are at this stage, the Microsoft FastTrack team will work with the project team to do a go-live assessment.</span></span> 

## <a name="what-are-the-prerequisites-to-deploying-a-production-environment"></a><span data-ttu-id="26e34-112">Milyen előfeltételei vannak az éles környezet üzembe helyezésének?</span><span class="sxs-lookup"><span data-stu-id="26e34-112">What are the prerequisites to deploying a production environment?</span></span> 

<span data-ttu-id="26e34-113">Az előfeltételek listáját a  [Felkészülés az élő indításra](hr-admin-go-live-prepare.md) című témakörben találja.</span><span class="sxs-lookup"><span data-stu-id="26e34-113">For a list of the prerequisites, see [Prepare for go-live](hr-admin-go-live-prepare.md).</span></span> 

## <a name="what-is-a-go-live-assessment"></a><span data-ttu-id="26e34-114">Mi az az élő indítási értékelés?</span><span class="sxs-lookup"><span data-stu-id="26e34-114">What is a go-live assessment?</span></span>  

<span data-ttu-id="26e34-115">Az élő indítási értékelés a  [Microsoft FastTrack program](/dynamics365/fasttrack/) része.</span><span class="sxs-lookup"><span data-stu-id="26e34-115">The go-live assessment is part of the [Microsoft FastTrack program](/dynamics365/fasttrack/).</span></span> <span data-ttu-id="26e34-116">A felülvizsgálat során a megoldástervező felméri, hogy egy megvalósítási projekt készen áll-e a sikeres átállásra és az éles indításra.</span><span class="sxs-lookup"><span data-stu-id="26e34-116">During this review, a solution architect assesses whether an implementation project is ready for a successful cutover and go-live.</span></span> <span data-ttu-id="26e34-117">Ez a felülvizsgálat minden megvalósítási projekthez kötelező, mielőtt éles környezetben való éles indítást kérelmez.</span><span class="sxs-lookup"><span data-stu-id="26e34-117">This review is mandatory for every implementation project before you can request to go live in a production environment.</span></span> 

## <a name="our-sandbox-environments-are-deployed-in-the-central-us-datacenter-we-want-our-production-environments-to-be-deployed-in-the-west-us-datacenter-can-i-select-west-us-as-the-datacenter-in-my-production-configuration"></a><span data-ttu-id="26e34-118">A tesztkörnyezetek az USA középső régiójában található adatközpontjában vannak telepítve.</span><span class="sxs-lookup"><span data-stu-id="26e34-118">Our Sandbox environments are deployed in the Central US datacenter.</span></span> <span data-ttu-id="26e34-119">Azt szeretnénk, hogy éles környezeteink az USA nyugati régiójának adatközpontjában legyenek telepítve.</span><span class="sxs-lookup"><span data-stu-id="26e34-119">We want our Production environments to be deployed in the West US datacenter.</span></span> <span data-ttu-id="26e34-120">Kiválaszthatom az USA nyugati régióját adatközpontként az éles konfigurációban?</span><span class="sxs-lookup"><span data-stu-id="26e34-120">Can I select West US as the datacenter in my Production configuration?</span></span> 

<span data-ttu-id="26e34-121">Az LCS nem korlátozza, hogy egy másik adatközpontot válasszon a Human Resources környezetének üzembe helyezésekor, de azt javasoljuk, hogy ne válasszon másik adatközpontot.</span><span class="sxs-lookup"><span data-stu-id="26e34-121">LCS doesn't restrict you from selecting a different data center when you deploy a Human Resources environment, but we strongly recommend not selecting a different data center.</span></span>  

<span data-ttu-id="26e34-122">Ha azt szeretné, hogy az éles környezet az USA nyugati régiójának adatközpontjában legyen, először telepítse újra a tesztkörnyezeteket a USA nyugati régiójának adatközpontjában, tesztelje őket, és hagyja jóvá.</span><span class="sxs-lookup"><span data-stu-id="26e34-122">If you want your Production environment to be in the West US datacenter, you should first redeploy your Sandbox environments to the West US datacenter, test them, and sign off.</span></span> 

<span data-ttu-id="26e34-123">A megfelelő adatközpont kiválasztásáról a [Hálózati követelmények](../fin-ops-core/fin-ops/get-started/system-requirements.md#network-requirements) című témakörben talál további információt.</span><span class="sxs-lookup"><span data-stu-id="26e34-123">For information about selecting the correct datacenter, see [Network requirements](../fin-ops-core/fin-ops/get-started/system-requirements.md#network-requirements).</span></span> 

## <a name="what-level-of-access-do-i-have-to-the-azure-resources-for-my-human-resources-environments"></a><span data-ttu-id="26e34-124">Milyen szintű hozzáféréssel kell rendelkeznem az Azure-erőforrásokhoz a Human Resources környezeteimhez?</span><span class="sxs-lookup"><span data-stu-id="26e34-124">What level of access do I have to the Azure resources for my Human Resources environments?</span></span>  

<span data-ttu-id="26e34-125">A Human Resources környezethez való hozzáférés korlátozott.</span><span class="sxs-lookup"><span data-stu-id="26e34-125">Access to the Human Resources environments is limited.</span></span> <span data-ttu-id="26e34-126">A virtuális gép (VM) vagy a Microsoft Internet Information Services (IIS) nem érhető el.</span><span class="sxs-lookup"><span data-stu-id="26e34-126">You can't access the virtual machine (VM) or Microsoft Internet Information Services (IIS).</span></span> <span data-ttu-id="26e34-127">Az adatbázis a Microsoft SQL Server Felügyeleti stúdión keresztül sem érhető el.</span><span class="sxs-lookup"><span data-stu-id="26e34-127">You also can't access the database through Microsoft SQL Server Management Studio.</span></span> 

<span data-ttu-id="26e34-128">Bár közvetlenül nem tud hozzáférni az Azure-erőforrásokhoz vagy a Dynamics 365 Human Resources-környezethez, további funkciókat is használhat az adatok eléréséhez:</span><span class="sxs-lookup"><span data-stu-id="26e34-128">Although you can't access your Azure resources or Dynamics 365 Human Resources environment directly, there are additional features you can use to access your data:</span></span>

- <span data-ttu-id="26e34-129">Az Azure SQL-adatbázist telepítheti a saját Azure-bérlőben, és a Bring Your Own Database (BYOD) szolgáltatás használatával szinkronizálhatja az adatokat.</span><span class="sxs-lookup"><span data-stu-id="26e34-129">You can deploy an Azure SQL database in your own Azure tenant and use the Bring Your Own Database (BYOD) feature to synchronize data.</span></span> <span data-ttu-id="26e34-130">A további tudnivalókat lásd: [Használja saját adatbázisát (BYOD)](../fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database.md).</span><span class="sxs-lookup"><span data-stu-id="26e34-130">For more information, see [Bring your own database (BYOD)](../fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database.md).</span></span>

- <span data-ttu-id="26e34-131">A Dataverse integráció segítségével szinkronizálhatja a kijelölt entitásokat a Dataverse-adatbázisba.</span><span class="sxs-lookup"><span data-stu-id="26e34-131">You can use Dataverse integration to synchronize select entities into the Dataverse database.</span></span> <span data-ttu-id="26e34-132">A további tudnivalókat lásd: [Dataverse-táblák](hr-developer-entities.md).</span><span class="sxs-lookup"><span data-stu-id="26e34-132">For more information, see [Dataverse tables](hr-developer-entities.md).</span></span> 

## <a name="how-often-is-my-production-database-backed-up"></a><span data-ttu-id="26e34-133">Milyen gyakran készül biztonsági másolat az éles adatbázisról?</span><span class="sxs-lookup"><span data-stu-id="26e34-133">How often is my production database backed up?</span></span> 

<span data-ttu-id="26e34-134">Az adatbázisokat automatikus biztonsági mentés védi a következő frekvenciákon:</span><span class="sxs-lookup"><span data-stu-id="26e34-134">Databases are protected by automatic backups at the following frequencies:</span></span>

| <span data-ttu-id="26e34-135">A biztonsági mentés típusa</span><span class="sxs-lookup"><span data-stu-id="26e34-135">Type of backup</span></span> | <span data-ttu-id="26e34-136">Gyakoriság</span><span class="sxs-lookup"><span data-stu-id="26e34-136">Frequency</span></span> |
| --- | --- |
| <span data-ttu-id="26e34-137">Adatbázis teljes biztonsági mentése</span><span class="sxs-lookup"><span data-stu-id="26e34-137">Full database backup</span></span> | <span data-ttu-id="26e34-138">Heti</span><span class="sxs-lookup"><span data-stu-id="26e34-138">Weekly</span></span> |
| <span data-ttu-id="26e34-139">Különbözeti adatbázis biztonsági mentése</span><span class="sxs-lookup"><span data-stu-id="26e34-139">Differential database backup</span></span> | <span data-ttu-id="26e34-140">12-24 óránként</span><span class="sxs-lookup"><span data-stu-id="26e34-140">Every 12-24 hours</span></span> |
| <span data-ttu-id="26e34-141">Tranzakciónapló biztonsági mentése</span><span class="sxs-lookup"><span data-stu-id="26e34-141">Transaction log backup</span></span> | <span data-ttu-id="26e34-142">5-10 percenként</span><span class="sxs-lookup"><span data-stu-id="26e34-142">Every 5 to 10 minutes</span></span> |

<span data-ttu-id="26e34-143">A Microsoft elegendő biztonsági mentést tart meg ahhoz, hogy az elmúlt 14 napban lehetővé tegye az Időponthoz kötött visszaállítás (PITR) használatát.</span><span class="sxs-lookup"><span data-stu-id="26e34-143">Microsoft retains sufficient backups to allow for Point in Time Restore (PITR) within the last 14 days.</span></span> 

<span data-ttu-id="26e34-144">A további tudnivalókat lásd: [Tudnivalók az automatikus SQL-adatbázis biztonsági másolatokról](/azure/azure-sql/database/automated-backups-overview?tabs=single-database).</span><span class="sxs-lookup"><span data-stu-id="26e34-144">For more information, see [Learn about automatic SQL Database backups](/azure/azure-sql/database/automated-backups-overview?tabs=single-database).</span></span> 

## <a name="can-i-request-a-copy-of-the-backup-of-my-production-database"></a><span data-ttu-id="26e34-145">Kérhetek másolatot az éles adatbázis biztonsági másolatáról?</span><span class="sxs-lookup"><span data-stu-id="26e34-145">Can I request a copy of the backup of my production database?</span></span> 

<span data-ttu-id="26e34-146">Nem.</span><span class="sxs-lookup"><span data-stu-id="26e34-146">No.</span></span> <span data-ttu-id="26e34-147">Azonban az adatbázis-frissítési szolgáltatáskérést elküldheti, hogy az éles környezetet a tesztkörnyzetbe másolja.</span><span class="sxs-lookup"><span data-stu-id="26e34-147">You can submit a database refresh service request to copy your Production environment to your Sandbox environment, however.</span></span> <span data-ttu-id="26e34-148">Az Azure SQL-adatbázist telepítheti a saját Azure-bérlőben, és a BYOD funkció használatával szinkronizálhatja az adatokat az éles környezetből.</span><span class="sxs-lookup"><span data-stu-id="26e34-148">You can deploy an Azure SQL database in your own Azure tenant and use the BYOD feature to synchronize data from your Production environment.</span></span> <span data-ttu-id="26e34-149">A további tudnivalókat lásd: [Használja saját adatbázisát (BYOD)](../fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database.md).</span><span class="sxs-lookup"><span data-stu-id="26e34-149">For more information, see [Bring your own database (BYOD)](../fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database.md).</span></span> 

## <a name="how-do-i-move-my-sandbox-environment-to-production-for-go-live"></a><span data-ttu-id="26e34-150">Hogyan helyezhetem át a tesztkörnyezetemet az élesbe éles indításra?</span><span class="sxs-lookup"><span data-stu-id="26e34-150">How do I move my Sandbox environment to Production for go-live?</span></span> 

<span data-ttu-id="26e34-151">Mivel másolási szolgáltatás nem érhető el a környezet tesztkörnyezetből éles környezetbe való áthelyezéséhez, adatcsomagokat kell használnia az adatok éles környezetbe való áthelyezéséhez.</span><span class="sxs-lookup"><span data-stu-id="26e34-151">Because a copy feature isn't available to move your environment from a Sandbox to a Production environment, you must use data packages to move data into your Production environment.</span></span>  

<span data-ttu-id="26e34-152">Azt javasoljuk, hogy a projekt során a tesztkörnyezetben konfigurált entitások egyértelmű listáját tartsa fenn.</span><span class="sxs-lookup"><span data-stu-id="26e34-152">We recommend maintaining a clear list of entities configured in your Sandbox throughout the project.</span></span> <span data-ttu-id="26e34-153">Ezután tesztelje az átállás és az áttelepítés folyamatát az éles indításhoz szükséges adatcsomagok esetében.</span><span class="sxs-lookup"><span data-stu-id="26e34-153">Then test the process of cutover and migration of any data packages needed for your go-live.</span></span> <span data-ttu-id="26e34-154">Ha készen áll az éles indításra, manuálisan kell áthelyeznie az adatcsomagokat az éles környezetbe.</span><span class="sxs-lookup"><span data-stu-id="26e34-154">You must manually move any data packages into the Production environment when you are ready to go live.</span></span> 

## <a name="what-should-i-do-if-my-production-environment-is-down"></a><span data-ttu-id="26e34-155">Mit tegyek, ha az éles környezetem nem üzemel?</span><span class="sxs-lookup"><span data-stu-id="26e34-155">What should I do if my Production environment is down?</span></span> 

<span data-ttu-id="26e34-156">A termeléskimaradás jelentéséhez kövesse a  [Termeléskimaradás jelentése](../fin-ops-core/dev-itpro/lifecycle-services/report-production-outage.md) című részben leírt eljárást.</span><span class="sxs-lookup"><span data-stu-id="26e34-156">To report a Production outage, follow the process described in [Report a production outage](../fin-ops-core/dev-itpro/lifecycle-services/report-production-outage.md).</span></span> 

 ## <a name="see-also"></a><span data-ttu-id="26e34-157">Lásd még</span><span class="sxs-lookup"><span data-stu-id="26e34-157">See also</span></span>

 [<span data-ttu-id="26e34-158">Felkészülés az éles indításra</span><span class="sxs-lookup"><span data-stu-id="26e34-158">Prepare for go-live</span></span>](hr-admin-go-live-prepare.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]