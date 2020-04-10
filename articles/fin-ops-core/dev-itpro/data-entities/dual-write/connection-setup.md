---
title: A kettős írás beállítás támogatott forgatókönyvei
description: Ez a témakör azt mutatja be, hogy milyen eseteket támogat a kettős írás beállítás.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: d7ff514768ee8e4797b591da89e190a855385885
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172854"
---
# <a name="supported-scenarios-for-dual-write-setup"></a><span data-ttu-id="d83ea-103">A kettős írás beállítás támogatott forgatókönyvei</span><span class="sxs-lookup"><span data-stu-id="d83ea-103">Supported scenarios for dual-write setup</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

<span data-ttu-id="d83ea-104">Egy Finance and Operations-környezet és egy Common Data Service-környezet között kettős írás kapcsolatot állíthat be.</span><span class="sxs-lookup"><span data-stu-id="d83ea-104">You can set up a dual-write connection between a Finance and Operations environment and a Common Data Service environment.</span></span>

+ <span data-ttu-id="d83ea-105">Egy **Finance and Operations-környezet** a háttérplatformot biztosítja a **Finance and Operations-alkalmazásokhoz** (például a Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Retail és Dynamics 365 Human Resources).</span><span class="sxs-lookup"><span data-stu-id="d83ea-105">A **Finance and Operations environment** provides the underlying platform for **Finance and Operations apps** (for example, Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Retail, and Dynamics 365 Human Resources).</span></span>
+ <span data-ttu-id="d83ea-106">A **Common Data Service-környezet** biztosítja a **Dynamics 365 modellvezérelt alkalmazások alapjául szolgáló platformot** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing, és Dynamics 365 Project Service Automation).</span><span class="sxs-lookup"><span data-stu-id="d83ea-106">A **Common Data Service environment** provides the underlying platform for **model-driven apps in Dynamics 365** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing, and Dynamics 365 Project Service Automation).</span></span>

<span data-ttu-id="d83ea-107">A beállítási mechanizmus az előfizetéstől és a környezettől függően változik.</span><span class="sxs-lookup"><span data-stu-id="d83ea-107">The setup mechanism varies, depending on your subscription and the environment.</span></span>

+ <span data-ttu-id="d83ea-108">A Finance and Operations-alkalmazások új példányainál a kettős írás kapcsolat beállítása a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban kezdődik.</span><span class="sxs-lookup"><span data-stu-id="d83ea-108">For new instances of Finance and Operations apps, the setup of a dual-write connection begins in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="d83ea-109">Ha rendelkezik licenccel a Microsoft Power Platform szolgáltatáshoz, akkor új Common Data Service-környezetbe kerül, ha a bérlő nem rendelkezik eggyel.</span><span class="sxs-lookup"><span data-stu-id="d83ea-109">If you have a license for Microsoft Power Platform, you will get a new Common Data Service environment if your tenant doesn't have one.</span></span>
+ <span data-ttu-id="d83ea-110">A meglévő példányú Finance and Operations-alkalmazások esetében a kettős írás kapcsolat beállítása a Finance and Operations-környezetben kezdődik.</span><span class="sxs-lookup"><span data-stu-id="d83ea-110">For existing instances Finance and Operations apps, the setup of a dual-write connection begins in the Finance and Operations environment.</span></span>

<span data-ttu-id="d83ea-111">A következő beállítású forgatókönyvek támogatottak:</span><span class="sxs-lookup"><span data-stu-id="d83ea-111">The following setup scenarios are supported:</span></span>

+ [<span data-ttu-id="d83ea-112">Egy új Finance and Operations-alkalmazáspéldány és egy új modellvezérelt alkalmazáspéldány</span><span class="sxs-lookup"><span data-stu-id="d83ea-112">A new Finance and Operations app instance and a new model-driven app instance</span></span>](#new-new)
+ [<span data-ttu-id="d83ea-113">Egy új Finance and Operations-alkalmazáspéldány és egy meglévő modellvezérelt alkalmazáspéldány</span><span class="sxs-lookup"><span data-stu-id="d83ea-113">A new Finance and Operations app instance and an existing model-driven app instance</span></span>](#new-existing)
+ [<span data-ttu-id="d83ea-114">Egy új Finance and Operations-alkalmazáspéldány, amely bemutatóadatokkal rendelkezik, és egy új modellvezérelt alkalmazáspéldány</span><span class="sxs-lookup"><span data-stu-id="d83ea-114">A new Finance and Operations app instance that has demo data and a new model-driven app instance</span></span>](#new-demo-new)
+ [<span data-ttu-id="d83ea-115">Egy új Finance and Operations-alkalmazáspéldány, amely bemutatóadatokkal rendelkezik, és egy meglévő modellvezérelt alkalmazáspéldány</span><span class="sxs-lookup"><span data-stu-id="d83ea-115">A new Finance and Operations app instance that has demo data and an existing model-driven app instance</span></span>](#new-demo-existing)
+ [<span data-ttu-id="d83ea-116">Egy meglévő Finance and Operations-alkalmazáspéldány és egy új vagy meglévő modellvezérelt alkalmazáspéldány</span><span class="sxs-lookup"><span data-stu-id="d83ea-116">An existing Finance and Operations app instance and a new or existing model-driven app instance</span></span>](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-model-driven-app-instance"></a><a id="new-new"></a><span data-ttu-id="d83ea-117">Egy új Finance and Operations-alkalmazáspéldány és egy új modellvezérelt alkalmazáspéldány</span><span class="sxs-lookup"><span data-stu-id="d83ea-117">A new Finance and Operations app instance and a new model-driven app instance</span></span>

<span data-ttu-id="d83ea-118">Ha a kettős írás kapcsolatot olyan Finance and Operations-alkalmazás új példányával szeretné beállítani, amelyben nincsenek adatok, és a Dynamics 365 modellvezérelt alkalmazásainak egy új példányával, kövesse a lépéseket itt: [Kettős írás beállítása a Lifecycle Services szolgáltatásból](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="d83ea-118">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and a new instance of a model-driven app in Dynamics 365, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="d83ea-119">A kapcsolat beállításának végeztével a következő műveletek történnek automatikusan:</span><span class="sxs-lookup"><span data-stu-id="d83ea-119">When the connection setup is completed, the following actions occur automatically:</span></span>

- <span data-ttu-id="d83ea-120">Egy új, üres Finance and Operations-környezet létesítése megtörténik.</span><span class="sxs-lookup"><span data-stu-id="d83ea-120">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="d83ea-121">A modellvezérelt alkalmazások egy új, üres példánya létesítésre kerül, ahol a CRM Prime megoldást telepítik.</span><span class="sxs-lookup"><span data-stu-id="d83ea-121">A new, empty instance of a model-driven app is provisioned, where the CRM prime solution is installed.</span></span>
- <span data-ttu-id="d83ea-122">A DAT vállalati adatokhoz egy kettős írás kapcsolat jön létre.</span><span class="sxs-lookup"><span data-stu-id="d83ea-122">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="d83ea-123">Az entitás-leképezések engedélyezve vannak az élő szinkronizáláshoz.</span><span class="sxs-lookup"><span data-stu-id="d83ea-123">Entity maps are enabled for live synchronization.</span></span>

<span data-ttu-id="d83ea-124">A két környezet készen áll az élő adatszinkronizálására.</span><span class="sxs-lookup"><span data-stu-id="d83ea-124">Both environments are then ready for live data synchronization.</span></span>

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-model-driven-app-instance"></a><a id="new-existing"></a><span data-ttu-id="d83ea-125">Egy új Finance and Operations-alkalmazáspéldány és egy meglévő modellvezérelt alkalmazáspéldány</span><span class="sxs-lookup"><span data-stu-id="d83ea-125">A new Finance and Operations app instance and an existing model-driven app instance</span></span>

<span data-ttu-id="d83ea-126">Ha a kettős írás kapcsolatot olyan Finance and Operations-alkalmazás új példányával szeretné beállítani, amelyben nincsenek adatok, és a Dynamics 365 modellvezérelt alkalmazásainak egy meglévő példányával, kövesse a lépéseket itt: [Kettős írás beállítása a Lifecycle Services szolgáltatásból](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="d83ea-126">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and an existing instance of a model-driven app in Dynamics 365, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="d83ea-127">A kapcsolat beállításának végeztével a következő műveletek történnek automatikusan:</span><span class="sxs-lookup"><span data-stu-id="d83ea-127">When the connection setup is completed, the following actions occur automatically:</span></span>

- <span data-ttu-id="d83ea-128">Egy új, üres Finance and Operations-környezet létesítése megtörténik.</span><span class="sxs-lookup"><span data-stu-id="d83ea-128">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="d83ea-129">A DAT vállalati adatokhoz egy kettős írás kapcsolat jön létre.</span><span class="sxs-lookup"><span data-stu-id="d83ea-129">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="d83ea-130">Az entitás-leképezések engedélyezve vannak az élő szinkronizáláshoz.</span><span class="sxs-lookup"><span data-stu-id="d83ea-130">Entity maps are enabled for live synchronization.</span></span>

<span data-ttu-id="d83ea-131">A két környezet készen áll az élő adatszinkronizálására.</span><span class="sxs-lookup"><span data-stu-id="d83ea-131">Both environments are then ready for live data synchronization.</span></span>

<span data-ttu-id="d83ea-132">Ha a meglévő Common Data Service-adatokat szinkronizálni szeretné Finance and Operations-alkalmazással, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="d83ea-132">To sync the existing Common Data Service data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="d83ea-133">Hozzon létre egy új vállalatot az Finance and Operations alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="d83ea-133">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="d83ea-134">Adja hozzá a vállalatot a kettős írás kapcsolat beállításhoz.</span><span class="sxs-lookup"><span data-stu-id="d83ea-134">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="d83ea-135">[Rendszerindítás](bootstrap-company-data.md) a Common Data Service-adatokkal a három betűs Nemzetközi Szabványügyi Szervezet (ISO) vállalati kóddal.</span><span class="sxs-lookup"><span data-stu-id="d83ea-135">[Bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter International Organization for Standardization (ISO) company code.</span></span>

<span data-ttu-id="d83ea-136">Mivel a kettős írás élő szinkronizálási módban van, a Common Data Service adatai automatikusan átáramlanak a Finance and Operations alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="d83ea-136">Because dual-write is in live synchronization mode, the data from Common Data Service automatically starts to flow to the Finance and Operations app.</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-demo-data-and-a-new-model-driven-app-instance"></a><a id="new-demo-new"></a><span data-ttu-id="d83ea-137">Egy új Finance and Operations-alkalmazáspéldány, amely bemutatóadatokkal rendelkezik, és egy új modellvezérelt alkalmazáspéldány</span><span class="sxs-lookup"><span data-stu-id="d83ea-137">A new Finance and Operations app instance that has demo data and a new model-driven app instance</span></span>

<span data-ttu-id="d83ea-138">Ha a kettős írás kapcsolatot olyan Finance and Operations-alkalmazás új példányával szeretné beállítani, amelyben bemutatóadatok vannak, és a Dynamics 365 modellvezérelt alkalmazásainak egy új példányával, kövesse a lépéseket itt: [Az új Finance and Operations alkalmazáspéldány és egy új modellvezérelt alkalmazáspéldány](#new-new) szakaszt a témakör korábbi részében.</span><span class="sxs-lookup"><span data-stu-id="d83ea-138">To set up a dual-write connection between a new instance of a Finance and Operations app that has demo data and a new instance of a model-driven app in Dynamics 365, follow the steps in the [A new Finance and Operations app instance and a new model-driven app instance](#new-new) section earlier in this topic.</span></span> <span data-ttu-id="d83ea-139">Ha befejezte a kapcsolat beállítását, hajtsa végre az alábbi lépéseket, ha szinkronizálni szeretné a demó adatait a modell alapú alkalmazással.</span><span class="sxs-lookup"><span data-stu-id="d83ea-139">When the connection setup is completed, if you want to sync the demo data to the model-driven app, follow these steps.</span></span>

1. <span data-ttu-id="d83ea-140">Nyissa meg a Finance and Operations alkalmazást a LCS oldalon, jelentkezzen be, majd kattintson az **Adatkezelés \> kettős írás** elemre.</span><span class="sxs-lookup"><span data-stu-id="d83ea-140">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="d83ea-141">Futtassa a **kezdeti szinkronizálási** funkciókat azon entitások esetében, amelyekhez szinkronizálni szeretné az adatokat.</span><span class="sxs-lookup"><span data-stu-id="d83ea-141">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-demo-data-and-an-existing-model-driven-app-instance"></a><a id="new-demo-existing"></a><span data-ttu-id="d83ea-142">Egy új Finance and Operations-alkalmazáspéldány, amely bemutatóadatokkal rendelkezik, és egy meglévő modellvezérelt alkalmazáspéldány</span><span class="sxs-lookup"><span data-stu-id="d83ea-142">A new Finance and Operations app instance that has demo data and an existing model-driven app instance</span></span>

<span data-ttu-id="d83ea-143">Ha a kettős írás kapcsolatot olyan Finance and Operations-alkalmazás új példányával szeretné beállítani, amelyben bemutatóadatok vannak, és a Dynamics 365 modellvezérelt alkalmazásainak egy meglévő példányával, kövesse a lépéseket itt: [Az új Finance and Operations alkalmazáspéldány és egy meglévő modellvezérelt alkalmazáspéldány](#new-existing) szakaszt a témakör korábbi részében.</span><span class="sxs-lookup"><span data-stu-id="d83ea-143">To set up a dual-write connection between a new instance of a Finance and Operations app that has demo data and an existing instance of a model-driven app in Dynamics 365, follow the steps in the [A new Finance and Operations app instance and an existing model-driven app instance](#new-existing) section earlier in this topic.</span></span> <span data-ttu-id="d83ea-144">Ha befejezte a kapcsolat beállítását, hajtsa végre az alábbi lépéseket, ha szinkronizálni szeretné a demó adatait a modell alapú alkalmazással.</span><span class="sxs-lookup"><span data-stu-id="d83ea-144">When the connection setup is completed, if you want to sync the demo data to the model-driven app, follow these steps.</span></span>

1. <span data-ttu-id="d83ea-145">Nyissa meg a Finance and Operations alkalmazást a LCS oldalon, jelentkezzen be, majd kattintson az **Adatkezelés \> kettős írás** elemre.</span><span class="sxs-lookup"><span data-stu-id="d83ea-145">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="d83ea-146">Futtassa a **kezdeti szinkronizálási** funkciókat azon entitások esetében, amelyekhez szinkronizálni szeretné az adatokat.</span><span class="sxs-lookup"><span data-stu-id="d83ea-146">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

<span data-ttu-id="d83ea-147">Ha a meglévő Common Data Service-adatokat szinkronizálni szeretné Finance and Operations-alkalmazással, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="d83ea-147">To sync the existing Common Data Service data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="d83ea-148">Hozzon létre egy új vállalatot az Finance and Operations alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="d83ea-148">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="d83ea-149">Adja hozzá a vállalatot a kettős írás kapcsolat beállításhoz.</span><span class="sxs-lookup"><span data-stu-id="d83ea-149">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="d83ea-150">[Rendszerindítás](bootstrap-company-data.md) a Common Data Service-adatokkal a három betűs ISO vállalati kóddal.</span><span class="sxs-lookup"><span data-stu-id="d83ea-150">[Bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter ISO company code.</span></span>

<span data-ttu-id="d83ea-151">Mivel a kettős írás élő szinkronizálási módban van, a Common Data Service adatai automatikusan átáramlanak a Finance and Operations alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="d83ea-151">Because dual-write is in live synchronization mode, the data from Common Data Service automatically starts to flow to the Finance and Operations app.</span></span>

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-or-existing-model-driven-app-instance"></a><a id="existing-existing"></a><span data-ttu-id="d83ea-152">Egy meglévő Finance and Operations-alkalmazáspéldány és egy új vagy meglévő modellvezérelt alkalmazáspéldány</span><span class="sxs-lookup"><span data-stu-id="d83ea-152">An existing Finance and Operations app instance and a new or existing model-driven app instance</span></span>

<span data-ttu-id="d83ea-153">A Finance and Operations alkalmazás egy létező példánya és a Dynamics 365 modellvezérelt alkalmazás új vagy létező példánya között egy kettős írás kapcsolat létrehozása a Finance and Operation környezetben történik.</span><span class="sxs-lookup"><span data-stu-id="d83ea-153">The setup of a dual-write connection between an existing instance of a Finance and Operations app and a new or existing instance of a model-driven app in Dynamics 365 occurs in the Finance and Operation environment.</span></span>

1. <span data-ttu-id="d83ea-154">A kapcsolat beállítása az Finance and Operations alkalmazásból.</span><span class="sxs-lookup"><span data-stu-id="d83ea-154">Set up the connection from the Finance and Operations app.</span></span>
2. <span data-ttu-id="d83ea-155">Ha a meglévő Common Data Service-adatokat szinkronizálni szeretné Finance and Operations alkalmazással, [indítson rendszerindítást](bootstrap-company-data.md) a Common Data Service adatokkal a három betűs ISO vállalati kóddal.</span><span class="sxs-lookup"><span data-stu-id="d83ea-155">To sync the existing Common Data Service data to the Finance and Operations app, [bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter ISO company code.</span></span>

<span data-ttu-id="d83ea-156">Mivel a kettős írás élő szinkronizálási módban van, a Common Data Service adatai automatikusan átáramlanak a Finance and Operations alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="d83ea-156">Because dual-write is in live synchronization mode, the data from Common Data Service automatically starts to flow to the Finance and Operations app.</span></span>
