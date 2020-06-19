---
title: Az ügyfélportál telepítése, beállítása és frissítése
description: Ez a témakör tartalmazza az Ügyfélportál licencelési adatait és telepítési útmutatását.
author: dasani-madipalli
manager: tfehr
ms.date: 04/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: b9d1e742f78254d949dc49fda008d63b8bff4d65
ms.sourcegitcommit: 713b5dfc76a6875d0ba6d86c5cbd585ea502cf9d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/01/2020
ms.locfileid: "3413970"
---
# <a name="install-set-up-and-update-the-customer-portal"></a><span data-ttu-id="fafc8-103">Az ügyfélportál telepítése, beállítása és frissítése</span><span class="sxs-lookup"><span data-stu-id="fafc8-103">Install, set up, and update the Customer portal</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="fafc8-104">Licencelési követelmények</span><span class="sxs-lookup"><span data-stu-id="fafc8-104">Licensing requirements</span></span>

<span data-ttu-id="fafc8-105">A Ügyfélportál kiépítése érdekében a következő licencekkel kell rendelkeznie:</span><span class="sxs-lookup"><span data-stu-id="fafc8-105">To implement the Customer portal, you must have the following licenses:</span></span>

- <span data-ttu-id="fafc8-106">**Power Apps-portálok** – Ez a licenc szükséges a Ügyfélportál hosztolásához.</span><span class="sxs-lookup"><span data-stu-id="fafc8-106">**Power Apps portals** – This license is required to host the Customer portal.</span></span> <span data-ttu-id="fafc8-107">A portálok a használat alapján vannak licencelve.</span><span class="sxs-lookup"><span data-stu-id="fafc8-107">Portals are licensed based on usage.</span></span> <span data-ttu-id="fafc8-108">A további tudnivalókat lásd a [Power Apps-portálok licencelési követelményei](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq#portals) részben.</span><span class="sxs-lookup"><span data-stu-id="fafc8-108">For more information, see the [Power Apps portals licensing requirements](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq#portals).</span></span>
- <span data-ttu-id="fafc8-109">**Kettős írás** – Rendelkeznie kell a szükséges licencekkel, hogy a Supply Chain Management entitások számára lehetővé tegye a kettős írást.</span><span class="sxs-lookup"><span data-stu-id="fafc8-109">**Dual-write** – You must have the necessary licenses to enable dual-write for Supply Chain Management entities.</span></span> <span data-ttu-id="fafc8-110">További tudnivalókért lásd a [kettős írás rendszerkövetelményeit](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-system-req.md).</span><span class="sxs-lookup"><span data-stu-id="fafc8-110">For more information, see the [system requirements for dual-write](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-system-req.md).</span></span>

## <a name="dependencies-on-dual-write-and-power-apps-portals"></a><span data-ttu-id="fafc8-111">A kettős írással és Power Apps-portálokkal kapcsolatos függőségek</span><span class="sxs-lookup"><span data-stu-id="fafc8-111">Dependencies on dual-write and Power Apps portals</span></span>

<span data-ttu-id="fafc8-112">Az Ügyfélportál a Power Apps-portálokon és a kettős íráson alapul, ahogy az a következő ábrán látható.</span><span class="sxs-lookup"><span data-stu-id="fafc8-112">The Customer portal depends on Power Apps portals and dual-write, as shown in the following illustration.</span></span>

![![Ügyfélportál függőségei](media/customer-portal-elements.png "Ügyfélportál függőségei")](media/customer-portal-elements.png "Customer portal dependencies")

<span data-ttu-id="fafc8-114">A Supply Chain Management egyéb szolgáltatásaitól eltérően a Customer Portal-sablon a Power Apps-portálokra épül.</span><span class="sxs-lookup"><span data-stu-id="fafc8-114">Unlike other features from Supply Chain Management, the Customer portal template resides in Power Apps portals.</span></span> <span data-ttu-id="fafc8-115">Ezért az Ügyfélportált korlátozzák a Power Apps portálok és a kettős írás entitásainak funkcionalitása és képességei.</span><span class="sxs-lookup"><span data-stu-id="fafc8-115">Therefore, the Customer portal is limited by the functionality and capabilities that are provided by Power Apps portals and the entities in dual-write.</span></span>

## <a name="required-setup-to-enable-the-customer-portal"></a><a name="required-setup"></a><span data-ttu-id="fafc8-116">A Ügyfélportál engedélyezéséhez szükséges beállítás</span><span class="sxs-lookup"><span data-stu-id="fafc8-116">Required setup to enable the Customer portal</span></span>

<span data-ttu-id="fafc8-117">Miután elvégezte a szükséges licencek megadását, a [kettős írás kezdeti szinkronizálási útmutatóban](../../fin-ops-core/dev-itpro/data-entities/dual-write/initial-sync.md) leírtaknak megfelelően beállíthatja a kettős írást.</span><span class="sxs-lookup"><span data-stu-id="fafc8-117">After you've made sure that you have the required licenses, you can set up dual-write as described in the [dual-write initial synchronization instructions](../../fin-ops-core/dev-itpro/data-entities/dual-write/initial-sync.md).</span></span>

<span data-ttu-id="fafc8-118">Ügyeljen arra, hogy a következő entitás-hozzárendeléseket engedélyezze a kettős írásban:</span><span class="sxs-lookup"><span data-stu-id="fafc8-118">Be sure to enable the following entity mappings in dual-write:</span></span>

- <span data-ttu-id="fafc8-119">Értékesítési rendelés fejléce</span><span class="sxs-lookup"><span data-stu-id="fafc8-119">Sales Order Header</span></span>
- <span data-ttu-id="fafc8-120">Értékesítési rendelés részletei</span><span class="sxs-lookup"><span data-stu-id="fafc8-120">Sales Order Details</span></span>
- <span data-ttu-id="fafc8-121">Számlák</span><span class="sxs-lookup"><span data-stu-id="fafc8-121">Accounts</span></span>
- <span data-ttu-id="fafc8-122">Névjegyek</span><span class="sxs-lookup"><span data-stu-id="fafc8-122">Contacts</span></span>
- <span data-ttu-id="fafc8-123">Termékek</span><span class="sxs-lookup"><span data-stu-id="fafc8-123">Products</span></span>

<span data-ttu-id="fafc8-124">A beállítás befejezése után telepítheti az Ügyfélportál sablonját.</span><span class="sxs-lookup"><span data-stu-id="fafc8-124">After this setup is completed, you can provision the Customer portal template.</span></span>

## <a name="provision-the-customer-portal"></a><span data-ttu-id="fafc8-125">Az Ügyfélportál telepítése</span><span class="sxs-lookup"><span data-stu-id="fafc8-125">Provision the Customer portal</span></span>

<span data-ttu-id="fafc8-126">A Kezdés előtt győződjön meg arról, hogy már végrehajtotta a [szükséges beállításokat](#required-setup).</span><span class="sxs-lookup"><span data-stu-id="fafc8-126">Before you begin, make sure that you've already completed the [required setup](#required-setup).</span></span> <span data-ttu-id="fafc8-127">Ezt követően végezze el a következő lépéseket a Ügyfélportál létesítéséhez.</span><span class="sxs-lookup"><span data-stu-id="fafc8-127">Then follow these steps to provision the Customer portal.</span></span>

1. <span data-ttu-id="fafc8-128">Ugorjon a [make.powerapps.com](https://make.powerapps.com/) oldalra.</span><span class="sxs-lookup"><span data-stu-id="fafc8-128">Go to [make.powerapps.com](https://make.powerapps.com/).</span></span>
2. <span data-ttu-id="fafc8-129">Győződjön meg arról, hogy a környezetben, amit használ a kettős írás engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="fafc8-129">Make sure that you're using the environment where you enabled dual-write.</span></span>
3. <span data-ttu-id="fafc8-130">A **Létrehozás** lapon görgessen a **Kezdés sablonból** szakaszhoz, és válassza ki azt a sablont, amelynek neve a **Supply Chain Management ügyfél**.</span><span class="sxs-lookup"><span data-stu-id="fafc8-130">On the **Create** tab, scroll down to the **Start from template** section, and select the template that is named **Supply Chain Management Customer**.</span></span>
4. <span data-ttu-id="fafc8-131">Kövesse a képernyőn megjelenő utasításokat.</span><span class="sxs-lookup"><span data-stu-id="fafc8-131">Follow the on-screen instructions.</span></span>

<span data-ttu-id="fafc8-132">A létesítés befejezése után a **Kezdőlap** a **Saját alkalmazások** területén érheti el az Ügyfélportált.</span><span class="sxs-lookup"><span data-stu-id="fafc8-132">After provisioning is completed, you can access the Customer portal in the **Your apps** section of the **Home** page.</span></span>

> [!NOTE]
> <span data-ttu-id="fafc8-133">Ha a kettős írás megoldás nincs telepítve a környezetben, amelyen dolgozik, hibaüzenet jelenik meg, és a Ügyfélportál nem lesz kiépítve.</span><span class="sxs-lookup"><span data-stu-id="fafc8-133">If the dual-write solution isn't installed in the environment that you're working in, you will receive an error message, and the Customer portal won't be provisioned.</span></span>

## <a name="update-the-customer-portal"></a><span data-ttu-id="fafc8-134">Az Ügyfélportál frissítése</span><span class="sxs-lookup"><span data-stu-id="fafc8-134">Update the Customer portal</span></span>

<span data-ttu-id="fafc8-135">Később több funkció is hozzáadható a Ügyfélportálhoz.</span><span class="sxs-lookup"><span data-stu-id="fafc8-135">More functionality might be added to the Customer portal later.</span></span> <span data-ttu-id="fafc8-136">A Microsoft által az mögöttes megoldás-összetevőkre vonatkozóan végrehajtott módosítások automatikusan megjelennek az Ön környezetében.</span><span class="sxs-lookup"><span data-stu-id="fafc8-136">Any changes that Microsoft makes to the underlying solution components will automatically appear in your environment.</span></span> <span data-ttu-id="fafc8-137">A környezetben létesített webhely azonban nem fogja automatikusan tükrözni a konfigurációs adatokon elvégzett változtatásokat.</span><span class="sxs-lookup"><span data-stu-id="fafc8-137">However, the website that is provisioned in your environment won't automatically reflect changes that are made to the configuration data.</span></span> <span data-ttu-id="fafc8-138">Ezeket a változtatásokat manuálisan kell alkalmazni a kód új sablonból történő beolvasásával, és a kiépített webhellyel történő egyesítésével.</span><span class="sxs-lookup"><span data-stu-id="fafc8-138">You will have to manually apply those changes by getting the code from the new template and merging it with the provisioned website.</span></span>

## <a name="resources"></a><span data-ttu-id="fafc8-139">Erőforrások</span><span class="sxs-lookup"><span data-stu-id="fafc8-139">Resources</span></span>

<span data-ttu-id="fafc8-140">A Ügyfélportál beállításával és testreszabásával kapcsolatos tudnivalók elsajátítását a következő dokumentációk áttekintésével kezdheti meg:</span><span class="sxs-lookup"><span data-stu-id="fafc8-140">To learn how you can set up and customize the Customer portal, you should start by reviewing the following documentation for the underlying technologies:</span></span>

- [<span data-ttu-id="fafc8-141">Power Apps portálok dokumentációja</span><span class="sxs-lookup"><span data-stu-id="fafc8-141">Power Apps portals documentation</span></span>](https://docs.microsoft.com/powerapps/maker/portals/overview)
- [<span data-ttu-id="fafc8-142">Kettős írás dokumentációja</span><span class="sxs-lookup"><span data-stu-id="fafc8-142">Dual-write documentation</span></span>](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page.md)

<span data-ttu-id="fafc8-143">A portálok hatékony kezeléséhez ismernie kell a Power Apps-portálokat és a Common Data Service-életciklust.</span><span class="sxs-lookup"><span data-stu-id="fafc8-143">To effectively manage your portals, you must understand the Power Apps portals and Common Data Service lifecycle.</span></span> <span data-ttu-id="fafc8-144">További információért tekintse át az alábbi forrásokat:</span><span class="sxs-lookup"><span data-stu-id="fafc8-144">For more information, see the following resources:</span></span>

- [<span data-ttu-id="fafc8-145">A portál életciklusáról</span><span class="sxs-lookup"><span data-stu-id="fafc8-145">About portal lifecycle</span></span>](https://docs.microsoft.com/powerapps/maker/portals/admin/portal-lifecycle)
- [<span data-ttu-id="fafc8-146">Portál frissítése</span><span class="sxs-lookup"><span data-stu-id="fafc8-146">Upgrade a portal</span></span>](https://docs.microsoft.com/powerapps/maker/portals/admin/upgrade-portal)
- [<span data-ttu-id="fafc8-147">Portál konfigurációjának áttelepítése</span><span class="sxs-lookup"><span data-stu-id="fafc8-147">Migrate portal configuration</span></span>](https://docs.microsoft.com/powerapps/maker/portals/admin/migrate-portal-configuration)
- [<span data-ttu-id="fafc8-148">Megoldás életciklus-kezelése: Dynamics 365 for Customer Engagement alkalmazásokhoz</span><span class="sxs-lookup"><span data-stu-id="fafc8-148">Solution Lifecycle Management: Dynamics 365 for Customer Engagement apps</span></span>](https://www.microsoft.com/download/details.aspx?id=57777)
