---
title: A kettős írás beállítás támogatott forgatókönyvei
description: Ez a témakör azt mutatja be, hogy milyen eseteket támogat a kettős írás beállítás.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 08/17/2020
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
ms.openlocfilehash: b4f69e7933bc5a50cccad6911c99cf08d2768578
ms.sourcegitcommit: b3df62842e62234e8eaa16992375582518976131
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/17/2020
ms.locfileid: "3818596"
---
# <a name="supported-scenarios-for-dual-write-setup"></a><span data-ttu-id="93510-103">A kettős írás beállítás támogatott forgatókönyvei</span><span class="sxs-lookup"><span data-stu-id="93510-103">Supported scenarios for dual-write setup</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

<span data-ttu-id="93510-104">Egy Finance and Operations-környezet és egy Common Data Service-környezet között kettős írás kapcsolatot állíthat be.</span><span class="sxs-lookup"><span data-stu-id="93510-104">You can set up a dual-write connection between a Finance and Operations environment and a Common Data Service environment.</span></span>

+ <span data-ttu-id="93510-105">Egy **Finance and Operations-környezet** a háttérplatformot biztosítja a **Finance and Operations-alkalmazásokhoz** (például Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, és Dynamics 365 Retail).</span><span class="sxs-lookup"><span data-stu-id="93510-105">A **Finance and Operations environment** provides the underlying platform for **Finance and Operations apps** (for example, Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, and Dynamics 365 Retail).</span></span>
+ <span data-ttu-id="93510-106">A **Common Data Service-környezet** biztosítja a **Dynamics 365 modellvezérelt alkalmazások alapjául szolgáló platformot** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing, és Dynamics 365 Project Service Automation).</span><span class="sxs-lookup"><span data-stu-id="93510-106">A **Common Data Service environment** provides the underlying platform for **model-driven apps in Dynamics 365** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing, and Dynamics 365 Project Service Automation).</span></span>

>[!IMPORTANT]
><span data-ttu-id="93510-107">Az Emberi erőforrások a Finance and Operations kettős írás kapcsolatok használatát támogatják, de az Dynamics 365 Human Resources alkalmazás nem.</span><span class="sxs-lookup"><span data-stu-id="93510-107">Human Resources in Finance and Operations supports dual-write connections, but the Dynamics 365 Human Resources app doesn't.</span></span>

<span data-ttu-id="93510-108">A beállítási mechanizmus az előfizetéstől és a környezettől függően változik.</span><span class="sxs-lookup"><span data-stu-id="93510-108">The setup mechanism varies, depending on your subscription and the environment.</span></span>

+ <span data-ttu-id="93510-109">A Finance and Operations-alkalmazások új példányainál a kettős írás kapcsolat beállítása a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban kezdődik.</span><span class="sxs-lookup"><span data-stu-id="93510-109">For new instances of Finance and Operations apps, the setup of a dual-write connection begins in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="93510-110">Ha rendelkezik licenccel a Power Platform szolgáltatáshoz, akkor új Common Data Service-környezetbe kerül, ha a bérlő nem rendelkezik eggyel.</span><span class="sxs-lookup"><span data-stu-id="93510-110">If you have a license for Power Platform, you will get a new Common Data Service environment if your tenant doesn't have one.</span></span>
+ <span data-ttu-id="93510-111">A meglévő példányú Finance and Operations-alkalmazások esetében a kettős írás kapcsolat beállítása a Finance and Operations-környezetben kezdődik.</span><span class="sxs-lookup"><span data-stu-id="93510-111">For existing instances Finance and Operations apps, the setup of a dual-write connection begins in the Finance and Operations environment.</span></span>

<span data-ttu-id="93510-112">A következő beállítású forgatókönyvek támogatottak:</span><span class="sxs-lookup"><span data-stu-id="93510-112">The following setup scenarios are supported:</span></span>

+ [<span data-ttu-id="93510-113">Egy új Finance and Operations-alkalmazáspéldány és egy új modellvezérelt alkalmazáspéldány</span><span class="sxs-lookup"><span data-stu-id="93510-113">A new Finance and Operations app instance and a new model-driven app instance</span></span>](#new-new)
+ [<span data-ttu-id="93510-114">Egy új Finance and Operations-alkalmazáspéldány és egy meglévő modellvezérelt alkalmazáspéldány</span><span class="sxs-lookup"><span data-stu-id="93510-114">A new Finance and Operations app instance and an existing model-driven app instance</span></span>](#new-existing)
+ [<span data-ttu-id="93510-115">Egy új Finance and Operations-alkalmazáspéldány, amely bemutatóadatokkal rendelkezik, és egy új modellvezérelt alkalmazáspéldány</span><span class="sxs-lookup"><span data-stu-id="93510-115">A new Finance and Operations app instance that has demo data and a new model-driven app instance</span></span>](#new-demo-new)
+ [<span data-ttu-id="93510-116">Egy új Finance and Operations-alkalmazáspéldány, amely bemutatóadatokkal rendelkezik, és egy meglévő modellvezérelt alkalmazáspéldány</span><span class="sxs-lookup"><span data-stu-id="93510-116">A new Finance and Operations app instance that has demo data and an existing model-driven app instance</span></span>](#new-demo-existing)
+ [<span data-ttu-id="93510-117">Egy meglévő Finance and Operations-alkalmazáspéldány és egy új vagy meglévő modellvezérelt alkalmazáspéldány</span><span class="sxs-lookup"><span data-stu-id="93510-117">An existing Finance and Operations app instance and a new or existing model-driven app instance</span></span>](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-model-driven-app-instance"></a><a id="new-new"></a><span data-ttu-id="93510-118">Egy új Finance and Operations-alkalmazáspéldány és egy új modellvezérelt alkalmazáspéldány</span><span class="sxs-lookup"><span data-stu-id="93510-118">A new Finance and Operations app instance and a new model-driven app instance</span></span>

<span data-ttu-id="93510-119">Ha a kettős írás kapcsolatot olyan Finance and Operations-alkalmazás új példányával szeretné beállítani, amelyben nincsenek adatok, és a Dynamics 365 modellvezérelt alkalmazásainak egy új példányával, kövesse a lépéseket itt: [Kettős írás beállítása a Lifecycle Services szolgáltatásból](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="93510-119">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and a new instance of a model-driven app in Dynamics 365, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="93510-120">A kapcsolat beállításának végeztével a következő műveletek történnek automatikusan:</span><span class="sxs-lookup"><span data-stu-id="93510-120">When the connection setup is completed, the following actions occur automatically:</span></span>

- <span data-ttu-id="93510-121">Egy új, üres Finance and Operations-környezet létesítése megtörténik.</span><span class="sxs-lookup"><span data-stu-id="93510-121">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="93510-122">A modellvezérelt alkalmazások egy új, üres példánya létesítésre kerül, ahol a CRM Prime megoldást telepítik.</span><span class="sxs-lookup"><span data-stu-id="93510-122">A new, empty instance of a model-driven app is provisioned, where the CRM prime solution is installed.</span></span>
- <span data-ttu-id="93510-123">A DAT vállalati adatokhoz egy kettős írás kapcsolat jön létre.</span><span class="sxs-lookup"><span data-stu-id="93510-123">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="93510-124">Az entitás-leképezések engedélyezve vannak az élő szinkronizáláshoz.</span><span class="sxs-lookup"><span data-stu-id="93510-124">Entity maps are enabled for live synchronization.</span></span>

<span data-ttu-id="93510-125">A két környezet készen áll az élő adatszinkronizálására.</span><span class="sxs-lookup"><span data-stu-id="93510-125">Both environments are then ready for live data synchronization.</span></span>

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-model-driven-app-instance"></a><a id="new-existing"></a><span data-ttu-id="93510-126">Egy új Finance and Operations-alkalmazáspéldány és egy meglévő modellvezérelt alkalmazáspéldány</span><span class="sxs-lookup"><span data-stu-id="93510-126">A new Finance and Operations app instance and an existing model-driven app instance</span></span>

<span data-ttu-id="93510-127">Ha a kettős írás kapcsolatot olyan Finance and Operations-alkalmazás új példányával szeretné beállítani, amelyben nincsenek adatok, és a Dynamics 365 modellvezérelt alkalmazásainak egy meglévő példányával, kövesse a lépéseket itt: [Kettős írás beállítása a Lifecycle Services szolgáltatásból](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="93510-127">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and an existing instance of a model-driven app in Dynamics 365, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="93510-128">A kapcsolat beállításának végeztével a következő műveletek történnek automatikusan:</span><span class="sxs-lookup"><span data-stu-id="93510-128">When the connection setup is completed, the following actions occur automatically:</span></span>

- <span data-ttu-id="93510-129">Egy új, üres Finance and Operations-környezet létesítése megtörténik.</span><span class="sxs-lookup"><span data-stu-id="93510-129">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="93510-130">A DAT vállalati adatokhoz egy kettős írás kapcsolat jön létre.</span><span class="sxs-lookup"><span data-stu-id="93510-130">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="93510-131">Az entitás-leképezések engedélyezve vannak az élő szinkronizáláshoz.</span><span class="sxs-lookup"><span data-stu-id="93510-131">Entity maps are enabled for live synchronization.</span></span>

<span data-ttu-id="93510-132">A két környezet készen áll az élő adatszinkronizálására.</span><span class="sxs-lookup"><span data-stu-id="93510-132">Both environments are then ready for live data synchronization.</span></span>

<span data-ttu-id="93510-133">Ha a meglévő Common Data Service-adatokat szinkronizálni szeretné Finance and Operations-alkalmazással, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="93510-133">To sync the existing Common Data Service data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="93510-134">Hozzon létre egy új vállalatot az Finance and Operations alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="93510-134">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="93510-135">Adja hozzá a vállalatot a kettős írás kapcsolat beállításhoz.</span><span class="sxs-lookup"><span data-stu-id="93510-135">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="93510-136">[Rendszerindítás](bootstrap-company-data.md) a Common Data Service-adatokkal a három betűs Nemzetközi Szabványügyi Szervezet (ISO) vállalati kóddal.</span><span class="sxs-lookup"><span data-stu-id="93510-136">[Bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter International Organization for Standardization (ISO) company code.</span></span>

<span data-ttu-id="93510-137">Mivel a kettős írás élő szinkronizálási módban van, a Common Data Service adatai automatikusan átáramlanak a Finance and Operations alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="93510-137">Because dual-write is in live synchronization mode, the data from Common Data Service automatically starts to flow to the Finance and Operations app.</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-demo-data-and-a-new-model-driven-app-instance"></a><a id="new-demo-new"></a><span data-ttu-id="93510-138">Egy új Finance and Operations-alkalmazáspéldány, amely bemutatóadatokkal rendelkezik, és egy új modellvezérelt alkalmazáspéldány</span><span class="sxs-lookup"><span data-stu-id="93510-138">A new Finance and Operations app instance that has demo data and a new model-driven app instance</span></span>

<span data-ttu-id="93510-139">Ha a kettős írás kapcsolatot olyan Finance and Operations-alkalmazás új példányával szeretné beállítani, amelyben bemutatóadatok vannak, és a Dynamics 365 modellvezérelt alkalmazásainak egy új példányával, kövesse a lépéseket itt: [Az új Finance and Operations alkalmazáspéldány és egy új modellvezérelt alkalmazáspéldány](#new-new) szakaszt a témakör korábbi részében.</span><span class="sxs-lookup"><span data-stu-id="93510-139">To set up a dual-write connection between a new instance of a Finance and Operations app that has demo data and a new instance of a model-driven app in Dynamics 365, follow the steps in the [A new Finance and Operations app instance and a new model-driven app instance](#new-new) section earlier in this topic.</span></span> <span data-ttu-id="93510-140">Ha befejezte a kapcsolat beállítását, hajtsa végre az alábbi lépéseket, ha szinkronizálni szeretné a demó adatait a modell alapú alkalmazással.</span><span class="sxs-lookup"><span data-stu-id="93510-140">When the connection setup is completed, if you want to sync the demo data to the model-driven app, follow these steps.</span></span>

1. <span data-ttu-id="93510-141">Nyissa meg a Finance and Operations alkalmazást a LCS oldalon, jelentkezzen be, majd kattintson az **Adatkezelés \> kettős írás** elemre.</span><span class="sxs-lookup"><span data-stu-id="93510-141">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="93510-142">Futtassa a **kezdeti szinkronizálási** funkciókat azon entitások esetében, amelyekhez szinkronizálni szeretné az adatokat.</span><span class="sxs-lookup"><span data-stu-id="93510-142">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-demo-data-and-an-existing-model-driven-app-instance"></a><a id="new-demo-existing"></a><span data-ttu-id="93510-143">Egy új Finance and Operations-alkalmazáspéldány, amely bemutatóadatokkal rendelkezik, és egy meglévő modellvezérelt alkalmazáspéldány</span><span class="sxs-lookup"><span data-stu-id="93510-143">A new Finance and Operations app instance that has demo data and an existing model-driven app instance</span></span>

<span data-ttu-id="93510-144">Ha a kettős írás kapcsolatot olyan Finance and Operations-alkalmazás új példányával szeretné beállítani, amelyben bemutatóadatok vannak, és a Dynamics 365 modellvezérelt alkalmazásainak egy meglévő példányával, kövesse a lépéseket itt: [Az új Finance and Operations alkalmazáspéldány és egy meglévő modellvezérelt alkalmazáspéldány](#new-existing) szakaszt a témakör korábbi részében.</span><span class="sxs-lookup"><span data-stu-id="93510-144">To set up a dual-write connection between a new instance of a Finance and Operations app that has demo data and an existing instance of a model-driven app in Dynamics 365, follow the steps in the [A new Finance and Operations app instance and an existing model-driven app instance](#new-existing) section earlier in this topic.</span></span> <span data-ttu-id="93510-145">Ha befejezte a kapcsolat beállítását, hajtsa végre az alábbi lépéseket, ha szinkronizálni szeretné a demó adatait a modell alapú alkalmazással.</span><span class="sxs-lookup"><span data-stu-id="93510-145">When the connection setup is completed, if you want to sync the demo data to the model-driven app, follow these steps.</span></span>

1. <span data-ttu-id="93510-146">Nyissa meg a Finance and Operations alkalmazást a LCS oldalon, jelentkezzen be, majd kattintson az **Adatkezelés \> kettős írás** elemre.</span><span class="sxs-lookup"><span data-stu-id="93510-146">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="93510-147">Futtassa a **kezdeti szinkronizálási** funkciókat azon entitások esetében, amelyekhez szinkronizálni szeretné az adatokat.</span><span class="sxs-lookup"><span data-stu-id="93510-147">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

<span data-ttu-id="93510-148">Ha a meglévő Common Data Service-adatokat szinkronizálni szeretné Finance and Operations-alkalmazással, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="93510-148">To sync the existing Common Data Service data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="93510-149">Hozzon létre egy új vállalatot az Finance and Operations alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="93510-149">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="93510-150">Adja hozzá a vállalatot a kettős írás kapcsolat beállításhoz.</span><span class="sxs-lookup"><span data-stu-id="93510-150">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="93510-151">[Rendszerindítás](bootstrap-company-data.md) a Common Data Service-adatokkal a három betűs ISO vállalati kóddal.</span><span class="sxs-lookup"><span data-stu-id="93510-151">[Bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter ISO company code.</span></span>

<span data-ttu-id="93510-152">Mivel a kettős írás élő szinkronizálási módban van, a Common Data Service adatai automatikusan átáramlanak a Finance and Operations alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="93510-152">Because dual-write is in live synchronization mode, the data from Common Data Service automatically starts to flow to the Finance and Operations app.</span></span>

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-or-existing-model-driven-app-instance"></a><a id="existing-existing"></a><span data-ttu-id="93510-153">Egy meglévő Finance and Operations-alkalmazáspéldány és egy új vagy meglévő modellvezérelt alkalmazáspéldány</span><span class="sxs-lookup"><span data-stu-id="93510-153">An existing Finance and Operations app instance and a new or existing model-driven app instance</span></span>

<span data-ttu-id="93510-154">A Finance and Operations alkalmazás egy létező példánya és a Dynamics 365 modellvezérelt alkalmazás új vagy létező példánya között egy kettős írás kapcsolat létrehozása a Finance and Operation környezetben történik.</span><span class="sxs-lookup"><span data-stu-id="93510-154">The setup of a dual-write connection between an existing instance of a Finance and Operations app and a new or existing instance of a model-driven app in Dynamics 365 occurs in the Finance and Operation environment.</span></span>

1. <span data-ttu-id="93510-155">A kapcsolat beállítása az Finance and Operations alkalmazásból.</span><span class="sxs-lookup"><span data-stu-id="93510-155">Set up the connection from the Finance and Operations app.</span></span>
2. <span data-ttu-id="93510-156">Ha a meglévő Common Data Service-adatokat szinkronizálni szeretné Finance and Operations alkalmazással, [indítson rendszerindítást](bootstrap-company-data.md) a Common Data Service adatokkal a három betűs ISO vállalati kóddal.</span><span class="sxs-lookup"><span data-stu-id="93510-156">To sync the existing Common Data Service data to the Finance and Operations app, [bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter ISO company code.</span></span>

<span data-ttu-id="93510-157">Mivel a kettős írás élő szinkronizálási módban van, a Common Data Service adatai automatikusan átáramlanak a Finance and Operations alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="93510-157">Because dual-write is in live synchronization mode, the data from Common Data Service automatically starts to flow to the Finance and Operations app.</span></span>
