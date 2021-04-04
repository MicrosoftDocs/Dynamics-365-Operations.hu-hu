---
title: Útmutató a kettős írás beállításához
description: Ez a témakör azt mutatja be, hogy milyen eseteket támogat a kettős írás beállítás.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 10/12/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: dee6bc52a0967dfd6134258d3a02dc18feb404a5
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5560225"
---
# <a name="guidance-for-dual-write-setup"></a><span data-ttu-id="978b8-103">Útmutató a kettős írás beállításához</span><span class="sxs-lookup"><span data-stu-id="978b8-103">Guidance for dual-write setup</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="978b8-104">Egy Finance and Operations-környezet és egy Dataverse-környezet között kettős írás kapcsolatot állíthat be.</span><span class="sxs-lookup"><span data-stu-id="978b8-104">You can set up a dual-write connection between a Finance and Operations environment and a Dataverse environment.</span></span>

+ <span data-ttu-id="978b8-105">Egy **Finance and Operations-környezet** a háttérplatformot biztosítja a **Finance and Operations-alkalmazásokhoz** (például a Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce és Dynamics 365 Human Resources).</span><span class="sxs-lookup"><span data-stu-id="978b8-105">A **Finance and Operations environment** provides the underlying platform for **Finance and Operations apps** (for example, Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce, and Dynamics 365 Human Resources).</span></span>
+ <span data-ttu-id="978b8-106">A **Dataverse-környezet** biztosítja az **ügyfélkapcsolati alkalmazások** alapjául szolgáló platformot (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 column Service, Dynamics 365 Marketing és Dynamics 365 Project Service Automation).</span><span class="sxs-lookup"><span data-stu-id="978b8-106">A **Dataverse environment** provides the underlying platform for **customer engagement apps** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 column Service, Dynamics 365 Marketing, and Dynamics 365 Project Service Automation).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="978b8-107">A Human Resources modul a Dynamics 365 Finance kettős írás kapcsolatok használatát támogatják, de az Dynamics 365 Human Resources alkalmazás nem.</span><span class="sxs-lookup"><span data-stu-id="978b8-107">The Human Resources module in Dynamics 365 Finance supports dual-write connections, but the Dynamics 365 Human Resources app doesn't.</span></span>

<span data-ttu-id="978b8-108">A beállítási mechanizmus az előfizetéstől és a környezettől függően változik:</span><span class="sxs-lookup"><span data-stu-id="978b8-108">The setup mechanism varies, depending on your subscription and the environment:</span></span>

+ <span data-ttu-id="978b8-109">A Finance and Operations-alkalmazások új példányainál a kettős írás kapcsolat beállítása a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban kezdődik.</span><span class="sxs-lookup"><span data-stu-id="978b8-109">For new instances of Finance and Operations apps, the setup of a dual-write connection begins in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="978b8-110">Ha rendelkezik licenccel a Microsoft Power Platform szolgáltatáshoz, akkor új Dataverse-környezetbe kerül, ha a bérlő nem rendelkezik eggyel.</span><span class="sxs-lookup"><span data-stu-id="978b8-110">If you have a license for Microsoft Power Platform, you will get a new Dataverse environment if your tenant doesn't have one.</span></span>
+ <span data-ttu-id="978b8-111">A meglévő példányú Finance and Operations-alkalmazások esetében a kettős írás kapcsolat beállítása a Finance and Operations-környezetben kezdődik.</span><span class="sxs-lookup"><span data-stu-id="978b8-111">For existing instances Finance and Operations apps, the setup of a dual-write connection begins in the Finance and Operations environment.</span></span>

<span data-ttu-id="978b8-112">Mielőtt egy entitásra kettős írást alkalmaz, futtathatja a kezdeti szinkronizálást, amely az Finance and Operations alkalmazások és az ügyfélkapcsolati alkalmazások mindkét oldalán meglévő adatokat kezeli.</span><span class="sxs-lookup"><span data-stu-id="978b8-112">Before you start dual-write on an entity, you can run an initial synchronization to handle existing data on both sides: Finance and Operations apps and customer engagement apps.</span></span> <span data-ttu-id="978b8-113">Ha nem szükséges szinkronizálni a két környezet adatait, akkor ki lehet hagyni a kezdeti szinkronizálást.</span><span class="sxs-lookup"><span data-stu-id="978b8-113">You can skip the initial synchronization if you don't have to sync data between the two environments.</span></span>

<span data-ttu-id="978b8-114">A kezdeti szinkronizálás lehetővé teszi a meglévő adatok másolását egyik alkalmazásból a másikba.</span><span class="sxs-lookup"><span data-stu-id="978b8-114">An initial synchronization lets you copy existing data from one app to another bidirectionally.</span></span> <span data-ttu-id="978b8-115">Számos telepítési eset van, attól függően, hogy mely környezetekkel rendelkezik már, és milyen típusú adatok találhatók a környezetben.</span><span class="sxs-lookup"><span data-stu-id="978b8-115">There are several setup scenarios, depending on the environments that you already have and the type of data in them.</span></span>

<span data-ttu-id="978b8-116">A következő beállítású forgatókönyvek támogatottak:</span><span class="sxs-lookup"><span data-stu-id="978b8-116">The following setup scenarios are supported:</span></span>

+ [<span data-ttu-id="978b8-117">Egy új Finance and Operations-alkalmazáspéldány és egy új ügyfélkapscsolati alkalmazáspéldány</span><span class="sxs-lookup"><span data-stu-id="978b8-117">A new Finance and Operations app instance and a new customer engagement app instance</span></span>](#new-new)
+ [<span data-ttu-id="978b8-118">Egy új Finance and Operations-alkalmazáspéldány és egy meglévő ügyfélkapcsolati alkalmazáspéldány</span><span class="sxs-lookup"><span data-stu-id="978b8-118">A new Finance and Operations app instance and an existing customer engagement app instance</span></span>](#new-existing)
+ [<span data-ttu-id="978b8-119">Egy új Finance and Operations-alkalmazáspéldány, amely adatokkal rendelkezik, és egy új ügyfélkapcsolati alkalmazáspéldány</span><span class="sxs-lookup"><span data-stu-id="978b8-119">A new Finance and Operations app instance that has data and a new customer engagement app instance</span></span>](#new-data-new)
+ [<span data-ttu-id="978b8-120">Egy új Finance and Operations-alkalmazáspéldány, amely bemutatóadatokkal rendelkezik, és egy meglévő ügyfélkapcsolati alkalmazáspéldány</span><span class="sxs-lookup"><span data-stu-id="978b8-120">A new Finance and Operations app instance that has data and an existing customer engagement app instance</span></span>](#new-data-existing)
+ [<span data-ttu-id="978b8-121">Egy meglévő Finance and Operations-alkalmazáspéldány és egy új ügyfélkapcsolati alkalmazáspéldány</span><span class="sxs-lookup"><span data-stu-id="978b8-121">An existing Finance and Operations app instance and a new customer engagement app instance</span></span>](#existing-new)
+ [<span data-ttu-id="978b8-122">Egy meglévő Finance and Operations-alkalmazáspéldány és egy meglévő ügyfélkapcsolati alkalmazáspéldány</span><span class="sxs-lookup"><span data-stu-id="978b8-122">An existing Finance and Operations app instance and an existing customer engagement app instance</span></span>](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="new-new"></a><span data-ttu-id="978b8-123">Egy új Finance and Operations-alkalmazáspéldány és egy új ügyfélkapscsolati alkalmazáspéldány</span><span class="sxs-lookup"><span data-stu-id="978b8-123">A new Finance and Operations app instance and a new customer engagement app instance</span></span>

<span data-ttu-id="978b8-124">Ha a kettős írás kapcsolatot olyan Finance and Operations-alkalmazás új példányával szeretné beállítani, amelyben nincsenek adatok, és a Dynamics 365 ügyfélkapcsolati alkalmazásainak egy új példányával, kövesse a lépéseket itt: [Kettős írás beállítása a Lifecycle Services szolgáltatásból](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="978b8-124">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and a new instance of a customer engagement app, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="978b8-125">A kapcsolat beállításának végeztével a következő műveletek történnek automatikusan:</span><span class="sxs-lookup"><span data-stu-id="978b8-125">When the connection setup is completed, the following actions automatically occur:</span></span>

- <span data-ttu-id="978b8-126">Egy új, üres Finance and Operations-környezet létesítése megtörténik.</span><span class="sxs-lookup"><span data-stu-id="978b8-126">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="978b8-127">Az ügyfélkapcsolati alkalmazások egy új, üres példánya létesítésre kerül, ahol a CRM Prime megoldást telepítik.</span><span class="sxs-lookup"><span data-stu-id="978b8-127">A new, empty instance of a customer engagement app is provisioned, where the CRM prime solution is installed.</span></span>
- <span data-ttu-id="978b8-128">A DAT vállalati adatokhoz egy kettős írás kapcsolat jön létre.</span><span class="sxs-lookup"><span data-stu-id="978b8-128">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="978b8-129">A táblaleképezések engedélyezve vannak az élő szinkronizáláshoz.</span><span class="sxs-lookup"><span data-stu-id="978b8-129">Table maps are enabled for live synchronization.</span></span>

<span data-ttu-id="978b8-130">A két környezet készen áll az élő adatszinkronizálására.</span><span class="sxs-lookup"><span data-stu-id="978b8-130">Both environments are then ready for live data synchronization.</span></span>

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="new-existing"></a><span data-ttu-id="978b8-131">Egy új Finance and Operations-alkalmazáspéldány és egy meglévő ügyfélkapcsolati alkalmazáspéldány</span><span class="sxs-lookup"><span data-stu-id="978b8-131">A new Finance and Operations app instance and an existing customer engagement app instance</span></span>

<span data-ttu-id="978b8-132">Ha a kettős írás kapcsolatot olyan Finance and Operations-alkalmazás új példányával szeretné beállítani, amelyben nincsenek adatok, és a Dynamics 365 ügyfélkapcsolati alkalmazásainak egy meglévő példányával, kövesse a lépéseket itt: [Kettős írás beállítása a Lifecycle Services szolgáltatásból](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="978b8-132">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and an existing instance of a customer engagement app, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="978b8-133">A kapcsolat beállításának végeztével a következő műveletek történnek automatikusan:</span><span class="sxs-lookup"><span data-stu-id="978b8-133">When the connection setup is completed, the following actions automatically occur:</span></span>

- <span data-ttu-id="978b8-134">Egy új, üres Finance and Operations-környezet létesítése megtörténik.</span><span class="sxs-lookup"><span data-stu-id="978b8-134">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="978b8-135">A DAT vállalati adatokhoz egy kettős írás kapcsolat jön létre.</span><span class="sxs-lookup"><span data-stu-id="978b8-135">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="978b8-136">A táblaleképezések engedélyezve vannak az élő szinkronizáláshoz.</span><span class="sxs-lookup"><span data-stu-id="978b8-136">Table maps are enabled for live synchronization.</span></span>

<span data-ttu-id="978b8-137">A két környezet készen áll az élő adatszinkronizálására.</span><span class="sxs-lookup"><span data-stu-id="978b8-137">Both environments are then ready for live data synchronization.</span></span>

<span data-ttu-id="978b8-138">Ha a meglévő Dataverse-adatokat szinkronizálni szeretné Finance and Operations-alkalmazással, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="978b8-138">To sync the existing Dataverse data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="978b8-139">Hozzon létre egy új vállalatot az Finance and Operations alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="978b8-139">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="978b8-140">Adja hozzá a vállalatot a kettős írás kapcsolat beállításhoz.</span><span class="sxs-lookup"><span data-stu-id="978b8-140">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="978b8-141">[Rendszerindítás](bootstrap-company-data.md) a Dataverse-adatokkal a három betűs Nemzetközi Szabványügyi Szervezet (ISO) vállalati kóddal.</span><span class="sxs-lookup"><span data-stu-id="978b8-141">[Bootstrap](bootstrap-company-data.md) the Dataverse data by using a three-letter International Organization for Standardization (ISO) company code.</span></span>
4. <span data-ttu-id="978b8-142">Futtassa a **kezdeti szinkronizálási** funkciókat azon táblák esetében, amelyekhez szinkronizálni szeretné az adatokat.</span><span class="sxs-lookup"><span data-stu-id="978b8-142">Run the **Initial sync** functionality for the tables that you want to sync data for.</span></span>

<span data-ttu-id="978b8-143">A példaekre mutató hivatkozásokat és az alternatív megközelítést a témakör későbbi [Példa](#example) részében találhatja meg.</span><span class="sxs-lookup"><span data-stu-id="978b8-143">For links to an example and an alternative approach, see the [Example](#example) section later in this topic.</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-a-new-customer-engagement-app-instance"></a><a id="new-data-new"></a><span data-ttu-id="978b8-144">Egy új Finance and Operations-alkalmazáspéldány, amely adatokkal rendelkezik, és egy új ügyfélkapcsolati alkalmazáspéldány</span><span class="sxs-lookup"><span data-stu-id="978b8-144">A new Finance and Operations app instance that has data and a new customer engagement app instance</span></span>

<span data-ttu-id="978b8-145">Ha a kettős írás kapcsolatot olyan Finance and Operations-alkalmazás új példányával szeretné beállítani, amelyben adatok vannak, és a Dynamics 365 ügyfélkapcsolati alkalmazásainak egy új példányával, kövesse a lépéseket itt: [Az új Finance and Operations alkalmazáspéldány és egy új ügyfélkapcsolati alkalmazáspéldány](#new-new) szakaszt a témakör korábbi részében.</span><span class="sxs-lookup"><span data-stu-id="978b8-145">To set up a dual-write connection between a new instance of a Finance and Operations app that has data and a new instance of a customer engagement app, follow the steps in the [A new Finance and Operations app instance and a new customer engagement app instance](#new-new) section earlier in this topic.</span></span> <span data-ttu-id="978b8-146">Ha befejezte a kapcsolat beállítását, hajtsa végre az alábbi lépéseket, ha szinkronizálni szeretné az adatait az ügyfélkapcsolati alkalmazással.</span><span class="sxs-lookup"><span data-stu-id="978b8-146">When the connection setup is completed, if you want to sync the data to the customer engagement app, follow these steps.</span></span>

1. <span data-ttu-id="978b8-147">Nyissa meg a Finance and Operations alkalmazást a LCS oldalon, jelentkezzen be, majd kattintson az **Adatkezelés \> kettős írás** elemre.</span><span class="sxs-lookup"><span data-stu-id="978b8-147">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="978b8-148">Futtassa a **kezdeti szinkronizálási** funkciókat azon táblák esetében, amelyekhez szinkronizálni szeretné az adatokat.</span><span class="sxs-lookup"><span data-stu-id="978b8-148">Run the **Initial sync** functionality for the tables that you want to sync data for.</span></span>

<span data-ttu-id="978b8-149">A példaekre mutató hivatkozásokat és az alternatív megközelítést a [Példa](#example) részben találhatja meg.</span><span class="sxs-lookup"><span data-stu-id="978b8-149">For links to an example and an alternative approach, see the [Example](#example) section.</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-an-existing-customer-engagement-app-instance"></a><a id="new-data-existing"></a><span data-ttu-id="978b8-150">Egy új Finance and Operations-alkalmazáspéldány, amely adatokkal rendelkezik, és egy meglévő ügyfélkapcsolati alkalmazáspéldány</span><span class="sxs-lookup"><span data-stu-id="978b8-150">A new Finance and Operations app instance that has data and an existing customer engagement app instance</span></span>

<span data-ttu-id="978b8-151">Ha a kettős írás kapcsolatot olyan Finance and Operations-alkalmazás új példányával szeretné beállítani, amelyben adatok vannak, és a Dynamics 365 ügyfélkapcsolati alkalmazásainak egy meglévő példányával, kövesse a lépéseket itt: [Az új Finance and Operations alkalmazáspéldány és egy meglévő ügyfélkapcsolati alkalmazáspéldány](#new-existing) szakaszt a témakör korábbi részében.</span><span class="sxs-lookup"><span data-stu-id="978b8-151">To set up a dual-write connection between a new instance of a Finance and Operations app that has data and an existing instance of a customer engagement app, follow the steps in the [A new Finance and Operations app instance and an existing customer engagement app instance](#new-existing) section earlier in this topic.</span></span> <span data-ttu-id="978b8-152">Ha befejezte a kapcsolat beállítását, hajtsa végre az alábbi lépéseket, ha szinkronizálni szeretné az adatait az ügyfélkapcsolati alkalmazással.</span><span class="sxs-lookup"><span data-stu-id="978b8-152">When the connection setup is completed, if you want to sync the data to the customer engagement app, follow these steps.</span></span>

1. <span data-ttu-id="978b8-153">Nyissa meg a Finance and Operations alkalmazást a LCS oldalon, jelentkezzen be, majd kattintson az **Adatkezelés \> kettős írás** elemre.</span><span class="sxs-lookup"><span data-stu-id="978b8-153">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="978b8-154">Futtassa a **kezdeti szinkronizálási** funkciókat azon táblák esetében, amelyekhez szinkronizálni szeretné az adatokat.</span><span class="sxs-lookup"><span data-stu-id="978b8-154">Run the **Initial sync** functionality for the tables that you want to sync data for.</span></span>

<span data-ttu-id="978b8-155">Ha a meglévő Dataverse-adatokat szinkronizálni szeretné Finance and Operations-alkalmazással, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="978b8-155">To sync the existing Dataverse data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="978b8-156">Hozzon létre egy új vállalatot az Finance and Operations alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="978b8-156">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="978b8-157">Adja hozzá a vállalatot a kettős írás kapcsolat beállításhoz.</span><span class="sxs-lookup"><span data-stu-id="978b8-157">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="978b8-158">[Rendszerindítás](bootstrap-company-data.md) a Dataverse-adatokkal a három betűs ISO vállalati kóddal.</span><span class="sxs-lookup"><span data-stu-id="978b8-158">[Bootstrap](bootstrap-company-data.md) the Dataverse data by using a three-letter ISO company code.</span></span>
4. <span data-ttu-id="978b8-159">Futtassa a **kezdeti szinkronizálási** funkciókat azon táblák esetében, amelyekhez szinkronizálni szeretné az adatokat.</span><span class="sxs-lookup"><span data-stu-id="978b8-159">Run the **Initial sync** functionality for the tables that you want to sync data for.</span></span>

<span data-ttu-id="978b8-160">A példaekre mutató hivatkozásokat és az alternatív megközelítést a [Példa](#example) részben találhatja meg.</span><span class="sxs-lookup"><span data-stu-id="978b8-160">For links to an example and an alternative approach, see the [Example](#example) section.</span></span>

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="existing-new"></a><span data-ttu-id="978b8-161">Egy meglévő Finance and Operations-alkalmazáspéldány és egy új ügyfélkapcsolati alkalmazáspéldány</span><span class="sxs-lookup"><span data-stu-id="978b8-161">An existing Finance and Operations app instance and a new customer engagement app instance</span></span>

<span data-ttu-id="978b8-162">A Finance and Operations alkalmazás egy létező példánya és egy ügyfélkapcsolati alkalmazás új példánya között egy kettős írás kapcsolat létrehozása a Finance and Operation környezetben történik.</span><span class="sxs-lookup"><span data-stu-id="978b8-162">The setup of a dual-write connection between an existing instance of a Finance and Operations app and a new instance of a customer engagement app occurs in the Finance and Operation environment.</span></span>

1. <span data-ttu-id="978b8-163">[A kapcsolat beállítása a Finance and Operations alkalmazásból](enable-dual-write.md).</span><span class="sxs-lookup"><span data-stu-id="978b8-163">[Set up the connection from the Finance and Operations app](enable-dual-write.md).</span></span>
2. <span data-ttu-id="978b8-164">Futtassa a **kezdeti szinkronizálási** funkciókat azon táblák esetében, amelyekhez szinkronizálni szeretné az adatokat.</span><span class="sxs-lookup"><span data-stu-id="978b8-164">Run the **Initial sync** functionality for the tables that you want to sync data for.</span></span>

<span data-ttu-id="978b8-165">A példaekre mutató hivatkozásokat és az alternatív megközelítést a [Példa](#example) részben találhatja meg.</span><span class="sxs-lookup"><span data-stu-id="978b8-165">For links to an example and an alternative approach, see the [Example](#example) section.</span></span>

## <a name="an-existing-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="existing-existing"></a><span data-ttu-id="978b8-166">Egy meglévő Finance and Operations-alkalmazáspéldány és egy meglévő ügyfélkapcsolati alkalmazáspéldány</span><span class="sxs-lookup"><span data-stu-id="978b8-166">An existing Finance and Operations app instance and an existing customer engagement app instance</span></span>

<span data-ttu-id="978b8-167">A Finance and Operations alkalmazás egy létező példánya és egy ügyfélkapcsolati alkalmazás meglévő példánya között egy kettős írás kapcsolat létrehozása a Finance and Operation környezetben történik.</span><span class="sxs-lookup"><span data-stu-id="978b8-167">The setup of a dual-write connection between an existing instance of a Finance and Operations app and an existing instance of a customer engagement app occurs in the Finance and Operation environment.</span></span>

1. <span data-ttu-id="978b8-168">[A kapcsolat beállítása a Finance and Operations alkalmazásból](enable-dual-write.md).</span><span class="sxs-lookup"><span data-stu-id="978b8-168">[Set up the connection from the Finance and Operations app](enable-dual-write.md).</span></span>
2. <span data-ttu-id="978b8-169">Ha a meglévő Dataverse-adatokat szinkronizálni szeretné Finance and Operations alkalmazással, [indítson rendszerindítást](bootstrap-company-data.md) a Dataverse adatokkal a három betűs ISO vállalati kóddal.</span><span class="sxs-lookup"><span data-stu-id="978b8-169">To sync the existing Dataverse data to the Finance and Operations app, [bootstrap](bootstrap-company-data.md) the Dataverse data by using a three-letter ISO company code.</span></span>
3. <span data-ttu-id="978b8-170">Futtassa a **kezdeti szinkronizálási** funkciókat azon táblák esetében, amelyekhez szinkronizálni szeretné az adatokat.</span><span class="sxs-lookup"><span data-stu-id="978b8-170">Run the **Initial sync** functionality for the tables that you want to sync data for.</span></span>

<span data-ttu-id="978b8-171">A példaekre mutató hivatkozásokat és az alternatív megközelítést a [Példa](#example) részben találhatja meg.</span><span class="sxs-lookup"><span data-stu-id="978b8-171">For links to an example and an alternative approach, see the [Example](#example) section.</span></span>

## <a name="example"></a><span data-ttu-id="978b8-172">Példa</span><span class="sxs-lookup"><span data-stu-id="978b8-172">Example</span></span>

<span data-ttu-id="978b8-173">Példa: [a Vevők v3-a kapcsolattartó-tábla leképezésének engedélyezése](enable-entity-map.md#enable-table-map)</span><span class="sxs-lookup"><span data-stu-id="978b8-173">For an example, see [Enabling the Customers V3—Contacts table map](enable-entity-map.md#enable-table-map)</span></span>

<span data-ttu-id="978b8-174">A kezdeti szinkronizálás futtatását igénylő entitások adatmennyiségein alapuló alternatív megközelítéshez lásd [a kezdeti szinkronizálás szempontjait](initial-sync-guidance.md).</span><span class="sxs-lookup"><span data-stu-id="978b8-174">For an alternative approach that is based on data volumes in each entity that must run an initial synchronization, see [Considerations for initial synchronization](initial-sync-guidance.md).</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]