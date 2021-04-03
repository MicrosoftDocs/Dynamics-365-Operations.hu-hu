---
title: Éles indítás GYIK
description: Ez a témakör a Dynamics 365 Human Resources megvalósítási projekttel kapcsolatos gyakori kérdéseket sorolja fel.
author: rachel-profitt
manager: tfehr
ms.date: 10/13/2020
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
ms.author: raprofit
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d667d94983d5c8f8e6140259922396d4299a15e3
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/17/2021
ms.locfileid: "5467590"
---
# <a name="go-live-faq"></a><span data-ttu-id="03b31-103">Éles indítás GYIK</span><span class="sxs-lookup"><span data-stu-id="03b31-103">Go-live FAQ</span></span> 

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="03b31-104">Ez a témakör a Dynamics 365 Human Resources megvalósítási projekttel kapcsolatos gyakori kérdéseket sorolja fel.</span><span class="sxs-lookup"><span data-stu-id="03b31-104">This topic lists frequently asked questions about how to go live with a Dynamics 365 Human Resources implementation project.</span></span> 

## <a name="when-can-i-configure-and-request-my-production-environment"></a><span data-ttu-id="03b31-105">Mikor konfigurálhatom és kérelmezhetem az éles környezetemet?</span><span class="sxs-lookup"><span data-stu-id="03b31-105">When can I configure and request my production environment?</span></span> 

<span data-ttu-id="03b31-106">Az éles környezet általában a következő feltételek teljesítése után kerül üzembe helyezésre:</span><span class="sxs-lookup"><span data-stu-id="03b31-106">Typically, a production environment is deployed after meeting the following criteria:</span></span>

- <span data-ttu-id="03b31-107">Minden testreszabás kódja teljeskörű.</span><span class="sxs-lookup"><span data-stu-id="03b31-107">All customizations are code-complete.</span></span>
- <span data-ttu-id="03b31-108">A felhasználói elfogadási tesztelés (UAT) befejeződött.</span><span class="sxs-lookup"><span data-stu-id="03b31-108">User acceptance testing (UAT) is complete.</span></span>
- <span data-ttu-id="03b31-109">Az ügyfél jóváhagyta a megoldást.</span><span class="sxs-lookup"><span data-stu-id="03b31-109">The customer has signed off on the solution.</span></span>
- <span data-ttu-id="03b31-110">Nincsenek blokkoló problémák az éles indítással kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="03b31-110">There are no blocking issues for go-live.</span></span> 

<span data-ttu-id="03b31-111">Ha a minősített ügyfelek ebben a szakaszban vannak, a Microsoft FastTrack csapata a projektcsapattal együttműködve élő indítási értékelést készít.</span><span class="sxs-lookup"><span data-stu-id="03b31-111">When qualified customers are at this stage, the Microsoft FastTrack team will work with the project team to do a go-live assessment.</span></span> 

## <a name="what-are-the-prerequisites-to-deploying-a-production-environment"></a><span data-ttu-id="03b31-112">Milyen előfeltételei vannak az éles környezet üzembe helyezésének?</span><span class="sxs-lookup"><span data-stu-id="03b31-112">What are the prerequisites to deploying a production environment?</span></span> 

<span data-ttu-id="03b31-113">Az előfeltételek listáját a  [Felkészülés az élő indításra](hr-admin-go-live-prepare.md) című témakörben találja.</span><span class="sxs-lookup"><span data-stu-id="03b31-113">For a list of the prerequisites, see [Prepare for go-live](hr-admin-go-live-prepare.md).</span></span> 

## <a name="what-is-a-go-live-assessment"></a><span data-ttu-id="03b31-114">Mi az az élő indítási értékelés?</span><span class="sxs-lookup"><span data-stu-id="03b31-114">What is a go-live assessment?</span></span>  

<span data-ttu-id="03b31-115">Az élő indítási értékelés a  [Microsoft FastTrack program](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/fasttrack-dynamics-365-overview) része.</span><span class="sxs-lookup"><span data-stu-id="03b31-115">The go-live assessment is part of the [Microsoft FastTrack program](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/fasttrack-dynamics-365-overview).</span></span> <span data-ttu-id="03b31-116">A felülvizsgálat során a megoldástervező felméri, hogy egy megvalósítási projekt készen áll-e a sikeres átállásra és az éles indításra.</span><span class="sxs-lookup"><span data-stu-id="03b31-116">During this review, a solution architect assesses whether an implementation project is ready for a successful cutover and go-live.</span></span> <span data-ttu-id="03b31-117">Ez a felülvizsgálat minden megvalósítási projekthez kötelező, mielőtt éles környezetben való éles indítást kérelmez.</span><span class="sxs-lookup"><span data-stu-id="03b31-117">This review is mandatory for every implementation project before you can request to go live in a production environment.</span></span> 

## <a name="our-sandbox-environments-are-deployed-in-the-central-us-datacenter-we-want-our-production-environments-to-be-deployed-in-the-west-us-datacenter-can-i-select-west-us-as-the-datacenter-in-my-production-configuration"></a><span data-ttu-id="03b31-118">A tesztkörnyezetek az USA középső régiójában található adatközpontjában vannak telepítve.</span><span class="sxs-lookup"><span data-stu-id="03b31-118">Our Sandbox environments are deployed in the Central US datacenter.</span></span> <span data-ttu-id="03b31-119">Azt szeretnénk, hogy éles környezeteink az USA nyugati régiójának adatközpontjában legyenek telepítve.</span><span class="sxs-lookup"><span data-stu-id="03b31-119">We want our Production environments to be deployed in the West US datacenter.</span></span> <span data-ttu-id="03b31-120">Kiválaszthatom az USA nyugati régióját adatközpontként az éles konfigurációban?</span><span class="sxs-lookup"><span data-stu-id="03b31-120">Can I select West US as the datacenter in my Production configuration?</span></span> 

<span data-ttu-id="03b31-121">Az LCS nem korlátozza, hogy egy másik adatközpontot válasszon a Human Resources környezetének üzembe helyezésekor, de azt javasoljuk, hogy ne válasszon másik adatközpontot.</span><span class="sxs-lookup"><span data-stu-id="03b31-121">LCS doesn't restrict you from selecting a different data center when you deploy a Human Resources environment, but we strongly recommend not selecting a different data center.</span></span>  

<span data-ttu-id="03b31-122">Ha azt szeretné, hogy az éles környezet az USA nyugati régiójának adatközpontjában legyen, először telepítse újra a tesztkörnyezeteket a USA nyugati régiójának adatközpontjában, tesztelje őket, és hagyja jóvá.</span><span class="sxs-lookup"><span data-stu-id="03b31-122">If you want your Production environment to be in the West US datacenter, you should first redeploy your Sandbox environments to the West US datacenter, test them, and sign off.</span></span> 

<span data-ttu-id="03b31-123">A megfelelő adatközpont kiválasztásáról a [Hálózati követelmények](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/system-requirements#network-requirements) című témakörben talál további információt.</span><span class="sxs-lookup"><span data-stu-id="03b31-123">For information about selecting the correct datacenter, see [Network requirements](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/system-requirements#network-requirements).</span></span> 

## <a name="what-level-of-access-do-i-have-to-the-azure-resources-for-my-human-resources-environments"></a><span data-ttu-id="03b31-124">Milyen szintű hozzáféréssel kell rendelkeznem az Azure-erőforrásokhoz a Human Resources környezeteimhez?</span><span class="sxs-lookup"><span data-stu-id="03b31-124">What level of access do I have to the Azure resources for my Human Resources environments?</span></span>  

<span data-ttu-id="03b31-125">A Human Resources környezethez való hozzáférés korlátozott.</span><span class="sxs-lookup"><span data-stu-id="03b31-125">Access to the Human Resources environments is limited.</span></span> <span data-ttu-id="03b31-126">A virtuális gép (VM) vagy a Microsoft Internet Information Services (IIS) nem érhető el.</span><span class="sxs-lookup"><span data-stu-id="03b31-126">You can't access the virtual machine (VM) or Microsoft Internet Information Services (IIS).</span></span> <span data-ttu-id="03b31-127">Az adatbázis a Microsoft SQL Server Felügyeleti stúdión keresztül sem érhető el.</span><span class="sxs-lookup"><span data-stu-id="03b31-127">You also can't access the database through Microsoft SQL Server Management Studio.</span></span> 

<span data-ttu-id="03b31-128">Bár közvetlenül nem tud hozzáférni az Azure-erőforrásokhoz vagy a Dynamics 365 Human Resources-környezethez, további funkciókat is használhat az adatok eléréséhez:</span><span class="sxs-lookup"><span data-stu-id="03b31-128">Although you can't access your Azure resources or Dynamics 365 Human Resources environment directly, there are additional features you can use to access your data:</span></span>

- <span data-ttu-id="03b31-129">Az Azure SQL-adatbázist telepítheti a saját Azure-bérlőben, és a Bring Your Own Database (BYOD) szolgáltatás használatával szinkronizálhatja az adatokat.</span><span class="sxs-lookup"><span data-stu-id="03b31-129">You can deploy an Azure SQL database in your own Azure tenant and use the Bring Your Own Database (BYOD) feature to synchronize data.</span></span> <span data-ttu-id="03b31-130">A további tudnivalókat lásd: [Használja saját adatbázisát (BYOD)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database).</span><span class="sxs-lookup"><span data-stu-id="03b31-130">For more information, see [Bring your own database (BYOD)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database).</span></span>

- <span data-ttu-id="03b31-131">A Dataverse integráció segítségével szinkronizálhatja a kijelölt entitásokat a Dataverse-adatbázisba.</span><span class="sxs-lookup"><span data-stu-id="03b31-131">You can use Dataverse integration to synchronize select entities into the Dataverse database.</span></span> <span data-ttu-id="03b31-132">A további tudnivalókat lásd: [Dataverse-táblák](hr-developer-entities.md).</span><span class="sxs-lookup"><span data-stu-id="03b31-132">For more information, see [Dataverse tables](hr-developer-entities.md).</span></span> 

## <a name="how-often-is-my-production-database-backed-up"></a><span data-ttu-id="03b31-133">Milyen gyakran készül biztonsági másolat az éles adatbázisról?</span><span class="sxs-lookup"><span data-stu-id="03b31-133">How often is my production database backed up?</span></span> 

<span data-ttu-id="03b31-134">Az adatbázisokat automatikus biztonsági mentés védi a következő frekvenciákon:</span><span class="sxs-lookup"><span data-stu-id="03b31-134">Databases are protected by automatic backups at the following frequencies:</span></span>

| <span data-ttu-id="03b31-135">A biztonsági mentés típusa</span><span class="sxs-lookup"><span data-stu-id="03b31-135">Type of backup</span></span> | <span data-ttu-id="03b31-136">Gyakoriság</span><span class="sxs-lookup"><span data-stu-id="03b31-136">Frequency</span></span> |
| --- | --- |
| <span data-ttu-id="03b31-137">Adatbázis teljes biztonsági mentése</span><span class="sxs-lookup"><span data-stu-id="03b31-137">Full database backup</span></span> | <span data-ttu-id="03b31-138">Heti</span><span class="sxs-lookup"><span data-stu-id="03b31-138">Weekly</span></span> |
| <span data-ttu-id="03b31-139">Különbözeti adatbázis biztonsági mentése</span><span class="sxs-lookup"><span data-stu-id="03b31-139">Differential database backup</span></span> | <span data-ttu-id="03b31-140">12-24 óránként</span><span class="sxs-lookup"><span data-stu-id="03b31-140">Every 12-24 hours</span></span> |
| <span data-ttu-id="03b31-141">Tranzakciónapló biztonsági mentése</span><span class="sxs-lookup"><span data-stu-id="03b31-141">Transaction log backup</span></span> | <span data-ttu-id="03b31-142">5-10 percenként</span><span class="sxs-lookup"><span data-stu-id="03b31-142">Every 5 to 10 minutes</span></span> |

<span data-ttu-id="03b31-143">A Microsoft elegendő biztonsági mentést tart meg ahhoz, hogy az elmúlt 14 napban lehetővé tegye az Időponthoz kötött visszaállítás (PITR) használatát.</span><span class="sxs-lookup"><span data-stu-id="03b31-143">Microsoft retains sufficient backups to allow for Point in Time Restore (PITR) within the last 14 days.</span></span> 

<span data-ttu-id="03b31-144">A további tudnivalókat lásd: [Tudnivalók az automatikus SQL-adatbázis biztonsági másolatokról](https://docs.microsoft.com/azure/azure-sql/database/automated-backups-overview?tabs=single-database).</span><span class="sxs-lookup"><span data-stu-id="03b31-144">For more information, see [Learn about automatic SQL Database backups](https://docs.microsoft.com/azure/azure-sql/database/automated-backups-overview?tabs=single-database).</span></span> 

## <a name="can-i-request-a-copy-of-the-backup-of-my-production-database"></a><span data-ttu-id="03b31-145">Kérhetek másolatot az éles adatbázis biztonsági másolatáról?</span><span class="sxs-lookup"><span data-stu-id="03b31-145">Can I request a copy of the backup of my production database?</span></span> 

<span data-ttu-id="03b31-146">Nem.</span><span class="sxs-lookup"><span data-stu-id="03b31-146">No.</span></span> <span data-ttu-id="03b31-147">Azonban az adatbázis-frissítési szolgáltatáskérést elküldheti, hogy az éles környezetet a tesztkörnyzetbe másolja.</span><span class="sxs-lookup"><span data-stu-id="03b31-147">You can submit a database refresh service request to copy your Production environment to your Sandbox environment, however.</span></span> <span data-ttu-id="03b31-148">Az Azure SQL-adatbázist telepítheti a saját Azure-bérlőben, és a BYOD funkció használatával szinkronizálhatja az adatokat az éles környezetből.</span><span class="sxs-lookup"><span data-stu-id="03b31-148">You can deploy an Azure SQL database in your own Azure tenant and use the BYOD feature to synchronize data from your Production environment.</span></span> <span data-ttu-id="03b31-149">A további tudnivalókat lásd: [Használja saját adatbázisát (BYOD)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database).</span><span class="sxs-lookup"><span data-stu-id="03b31-149">For more information, see [Bring your own database (BYOD)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database).</span></span> 

## <a name="how-do-i-move-my-sandbox-environment-to-production-for-go-live"></a><span data-ttu-id="03b31-150">Hogyan helyezhetem át a tesztkörnyezetemet az élesbe éles indításra?</span><span class="sxs-lookup"><span data-stu-id="03b31-150">How do I move my Sandbox environment to Production for go-live?</span></span> 

<span data-ttu-id="03b31-151">Mivel másolási szolgáltatás nem érhető el a környezet tesztkörnyezetből éles környezetbe való áthelyezéséhez, adatcsomagokat kell használnia az adatok éles környezetbe való áthelyezéséhez.</span><span class="sxs-lookup"><span data-stu-id="03b31-151">Because a copy feature isn't available to move your environment from a Sandbox to a Production environment, you must use data packages to move data into your Production environment.</span></span>  

<span data-ttu-id="03b31-152">Azt javasoljuk, hogy a projekt során a tesztkörnyezetben konfigurált entitások egyértelmű listáját tartsa fenn.</span><span class="sxs-lookup"><span data-stu-id="03b31-152">We recommend maintaining a clear list of entities configured in your Sandbox throughout the project.</span></span> <span data-ttu-id="03b31-153">Ezután tesztelje az átállás és az áttelepítés folyamatát az éles indításhoz szükséges adatcsomagok esetében.</span><span class="sxs-lookup"><span data-stu-id="03b31-153">Then test the process of cutover and migration of any data packages needed for your go-live.</span></span> <span data-ttu-id="03b31-154">Ha készen áll az éles indításra, manuálisan kell áthelyeznie az adatcsomagokat az éles környezetbe.</span><span class="sxs-lookup"><span data-stu-id="03b31-154">You must manually move any data packages into the Production environment when you are ready to go live.</span></span> 

## <a name="what-should-i-do-if-my-production-environment-is-down"></a><span data-ttu-id="03b31-155">Mit tegyek, ha az éles környezetem nem üzemel?</span><span class="sxs-lookup"><span data-stu-id="03b31-155">What should I do if my Production environment is down?</span></span> 

<span data-ttu-id="03b31-156">A termeléskimaradás jelentéséhez kövesse a  [Termeléskimaradás jelentése](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/report-production-outage) című részben leírt eljárást.</span><span class="sxs-lookup"><span data-stu-id="03b31-156">To report a Production outage, follow the process described in [Report a production outage](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/report-production-outage).</span></span> 

 ## <a name="see-also"></a><span data-ttu-id="03b31-157">Lásd még</span><span class="sxs-lookup"><span data-stu-id="03b31-157">See also</span></span>

 [<span data-ttu-id="03b31-158">Felkészülés az éles indításra</span><span class="sxs-lookup"><span data-stu-id="03b31-158">Prepare for go-live</span></span>](hr-admin-go-live-prepare.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]