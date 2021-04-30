---
title: Frissítés a fél és globális címjegyzék modelljére
description: Ez a témakör azt ismerteti, hogyan lehet kettős írású adatot frissíteni a partner és a globális címjegyzék modellel.
author: RamaKrishnamoorthy
ms.date: 03/31/2021
ms.topic: article
ms.service: dynamics-ax-applications
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-03-31
ms.openlocfilehash: 76e64d483e833782733277a64d8dc37cbeba6130
ms.sourcegitcommit: 011468a6cffea8641bebc2922e0676d9f44b36fc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/06/2021
ms.locfileid: "5857370"
---
# <a name="upgrade-to-the-party-and-global-address-book-model"></a><span data-ttu-id="e7192-103">Frissítés a fél és globális címjegyzék modelljére</span><span class="sxs-lookup"><span data-stu-id="e7192-103">Upgrade to the party and global address book model</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="e7192-104">Az [Azure Data Factory sablon](https://aka.ms/dual-write-gab-adf) segít frissíteni a partner és a globális címjegyzék modellbe a kettős írású, meglévő **Partner**, **Kapcsolattartó** és **Szállító** táblaadatokat.</span><span class="sxs-lookup"><span data-stu-id="e7192-104">The [Azure Data Factory template](https://aka.ms/dual-write-gab-adf) helps you upgrade existing **Account**, **Contact**, and **Vendor** table data in dual-write to the party and global address book model.</span></span> <span data-ttu-id="e7192-105">A sablon az Finance and Operations alkalmazásokból és az ügyfélkapcsolati alkalmazásokból származó adatokat is egyezteti.</span><span class="sxs-lookup"><span data-stu-id="e7192-105">The template reconciles the data from both Finance and Operations apps and customer engagement applications.</span></span> <span data-ttu-id="e7192-106">A folyamat végén a **Partner** rekordjaihoz tartozó **Partner** és **Kapcsolattartó** mezők létrejönnek, és társítva lesznek az ügyfélkapcsolati pályázatok **Számla**, **Kapcsolattartó** és **Szállító** rekordjaihoz.</span><span class="sxs-lookup"><span data-stu-id="e7192-106">At the end of the process, **Party** and **Contact** fields for **Party** records will be created and associated with **Account**, **Contact**, and **Vendor** records in customer engagement applications.</span></span> <span data-ttu-id="e7192-107">A rendszer .csv fájlt (`FONewParty.csv`) hoz létre, hogy új **Partner** rekordokat hozzon létre az Finance and Operations alkalmazáson belül.</span><span class="sxs-lookup"><span data-stu-id="e7192-107">A .csv file (`FONewParty.csv`) is generated to create new **Party** records inside the Finance and Operations app.</span></span> <span data-ttu-id="e7192-108">Ez a témakör az adat-előállító sablon használatára és az adatok frissítésére vonatkozó útmutatást tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="e7192-108">This topic provides the instructions to use the Data Factory template and upgrade your data.</span></span>

<span data-ttu-id="e7192-109">Ha nincsenek testreszabásai, a sablont használhatja úgy, ahogy van.</span><span class="sxs-lookup"><span data-stu-id="e7192-109">If you don’t have any customizations, you can use the template as-is.</span></span> <span data-ttu-id="e7192-110">Ha testreszabott beállításai vannak a **számlához**, a **kapcsolattartóhoz** és a **szállítóhoz**, akkor a következő útmutatásokkal kell módosítania a sablont.</span><span class="sxs-lookup"><span data-stu-id="e7192-110">If you have customizations for **Account**, **Contact**, and **Vendor** then you must modify the template using the following instructions.</span></span>

> [!Note]
> <span data-ttu-id="e7192-111">A sablon csak a **Partner** adatait frissíti.</span><span class="sxs-lookup"><span data-stu-id="e7192-111">The template helps to upgrade only the **Party** data.</span></span> <span data-ttu-id="e7192-112">Egy későbbi verzióban a postai és az elektronikus címek is szerepelni fognak.</span><span class="sxs-lookup"><span data-stu-id="e7192-112">In a future release, postal and electronic addresses will be included.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e7192-113">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="e7192-113">Prerequisites</span></span>

<span data-ttu-id="e7192-114">Ezek az előfeltételek kötelezők:</span><span class="sxs-lookup"><span data-stu-id="e7192-114">These prerequisites are required:</span></span>

+ [<span data-ttu-id="e7192-115">Azure-előfizetés</span><span class="sxs-lookup"><span data-stu-id="e7192-115">Azure subscription</span></span>](https://portal.azure.com/)
+ [<span data-ttu-id="e7192-116">Hozzáférés a sablonhoz</span><span class="sxs-lookup"><span data-stu-id="e7192-116">Access to the template</span></span>](https://aka.ms/dual-write-gab-adf)
+ <span data-ttu-id="e7192-117">Ön már kettős írási ügyfél.</span><span class="sxs-lookup"><span data-stu-id="e7192-117">You are an existing dual-write customer.</span></span>

## <a name="prepare-for-the-upgrade"></a><span data-ttu-id="e7192-118">Felkészülés a frissítésre</span><span class="sxs-lookup"><span data-stu-id="e7192-118">Prepare for the upgrade</span></span>

+ <span data-ttu-id="e7192-119">**Teljesen szinkronizálva:** Mindkét környezet teljesen szinkronizált állapotban van a **számla (vevő)**, a **kapcsolattartó** és a **szállító** esetében.</span><span class="sxs-lookup"><span data-stu-id="e7192-119">**Fully synched**: Both environments are fully synched state for **Account (Customer)**, **Contact**, and **Vendor**.</span></span>
+ <span data-ttu-id="e7192-120">**Integrációs kulcsok**: a **Számla (Vevő)**, a **Kapcsolattartó** és a **Szállító** tábla az ügyfélkapcsolati alkalmazásokban a gyárilag beépített integrációs kulcsokat használja.</span><span class="sxs-lookup"><span data-stu-id="e7192-120">**Integration keys**: **Account (Customer)**, **Contact**, and **Vendor** tables in customer engagement apps are using the integration keys that shipped out-of-the-box.</span></span> <span data-ttu-id="e7192-121">Ha testre szabta az integrációs kulcsokat, testre kell szabni a sablont.</span><span class="sxs-lookup"><span data-stu-id="e7192-121">If you customized the integration keys, you must customize the template.</span></span>
+ <span data-ttu-id="e7192-122">**Partnerszámszám**: a frissítésre sorra kerülő összes **Számla (Vevő)**, **Kapcsolattartó** és **Szállító** rekordnak van **partnerszáma**.</span><span class="sxs-lookup"><span data-stu-id="e7192-122">**Party number**: All **Account (Customer)**, **Contact**, and **Vendor** records that will be upgraded have a **Party** number.</span></span> <span data-ttu-id="e7192-123">A **Partnerszám** nélküli rekordokat figyelmen kívül hagyja a rendszer.</span><span class="sxs-lookup"><span data-stu-id="e7192-123">Records without a **Party** number will be ignored.</span></span> <span data-ttu-id="e7192-124">Ha frissíteni szeretné ezeket a rekordokat, a frissítési folyamat kezdete előtt adjon hozzá egy **Partnerszámot**.</span><span class="sxs-lookup"><span data-stu-id="e7192-124">If you want to upgrade those records, add a **Party** number to them before you start the upgrade process.</span></span>
+ <span data-ttu-id="e7192-125">**Rendszerszünet**: A frissítési folyamat során mind a Finance and Operations, mind az ügyfélkapcsolati környezeteket kapcsolat nélkül módba kell vinni.</span><span class="sxs-lookup"><span data-stu-id="e7192-125">**System outage**: During the upgrade process, you will have to take both the Finance and Operations and customer engagement environments offline.</span></span>
+ <span data-ttu-id="e7192-126">**Pillanatkép**: Pillanatkép készítése mind a Finance and Operations, mind az ügyfélkapcsolati alkalmazásokról.</span><span class="sxs-lookup"><span data-stu-id="e7192-126">**Snapshot**: Take snapshots of both the Finance and Operations and customer engagement apps.</span></span> <span data-ttu-id="e7192-127">A pillanatképek segítségével szükség esetén visszaállíthatja az előző állapotot.</span><span class="sxs-lookup"><span data-stu-id="e7192-127">Use the snapshots to restore the previous state if you need to.</span></span>

## <a name="deployment"></a><span data-ttu-id="e7192-128">Telepítés</span><span class="sxs-lookup"><span data-stu-id="e7192-128">Deployment</span></span>

1. <span data-ttu-id="e7192-129">Töltse le a sablont a [Dynamics-365-FastTrack-Implementation-Assets](https://aka.ms/dual-write-gab-adf) eszközből.</span><span class="sxs-lookup"><span data-stu-id="e7192-129">Download the template from [Dynamics-365-FastTrack-Implementation-Assets](https://aka.ms/dual-write-gab-adf).</span></span>

2. <span data-ttu-id="e7192-130">Jelentkezzen be ide: [Microsoft Azure](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="e7192-130">Sign in to [Microsoft Azure](https://portal.azure.com/).</span></span>

3. <span data-ttu-id="e7192-131">Hozzon létre egy [erőforráscsoportot](https://docs.microsoft.com/azure/azure-resource-manager/management/manage-resource-groups-portal).</span><span class="sxs-lookup"><span data-stu-id="e7192-131">Create a [resource group](https://docs.microsoft.com/azure/azure-resource-manager/management/manage-resource-groups-portal).</span></span>

4. <span data-ttu-id="e7192-132">Hozzon létre egy [tárolási fiókot](https://docs.microsoft.com/azure/storage/common/storage-account-create?tabs=azure-portal) a létrehozott erőforráscsoportban.</span><span class="sxs-lookup"><span data-stu-id="e7192-132">Create a [storage account](https://docs.microsoft.com/azure/storage/common/storage-account-create?tabs=azure-portal) in the resource group that you created.</span></span>

5. <span data-ttu-id="e7192-133">Hozzon létre egy [adat-előállítót](https://docs.microsoft.com/azure/data-factory/quickstart-create-data-factory-portal) a fent létrehozott erőforráscsoportban.</span><span class="sxs-lookup"><span data-stu-id="e7192-133">Create a [data factory](https://docs.microsoft.com/azure/data-factory/quickstart-create-data-factory-portal) in above resource group that you created.</span></span>

6. <span data-ttu-id="e7192-134">Nyissa meg az adat-előállítót, és válassza a **Szerző & Monitor** csempét.</span><span class="sxs-lookup"><span data-stu-id="e7192-134">Open the data factory and select the **Author & Monitor** tile.</span></span>

7. <span data-ttu-id="e7192-135">A **Kezelés** lapon válassza ki az **ARM-sablont**.</span><span class="sxs-lookup"><span data-stu-id="e7192-135">On the **Manage** tab, select **ARM template**.</span></span>

8. <span data-ttu-id="e7192-136">Válassza ki az **ARM-sablon importálása** lehetőséget a **Partner** sablon importálásához.</span><span class="sxs-lookup"><span data-stu-id="e7192-136">Select the **Import ARM template** to import the **Party** template.</span></span>

9. <span data-ttu-id="e7192-137">A sablon importálása az adat-előállítóba.</span><span class="sxs-lookup"><span data-stu-id="e7192-137">Import the template into the data factory.</span></span> <span data-ttu-id="e7192-138">Adja meg az alábbi értékeket a **projekt részleteinél** és a **példányok részleteinél**.</span><span class="sxs-lookup"><span data-stu-id="e7192-138">Enter the following values for **Project details** and **Instance details**.</span></span>

    <span data-ttu-id="e7192-139">Mező</span><span class="sxs-lookup"><span data-stu-id="e7192-139">Field</span></span> | <span data-ttu-id="e7192-140">Érték</span><span class="sxs-lookup"><span data-stu-id="e7192-140">Value</span></span>
    ---|---
    <span data-ttu-id="e7192-141">Előfizetés</span><span class="sxs-lookup"><span data-stu-id="e7192-141">Subscription</span></span> | <span data-ttu-id="e7192-142">Azure-előfizetés</span><span class="sxs-lookup"><span data-stu-id="e7192-142">Azure subscription</span></span>
    <span data-ttu-id="e7192-143">Erőforráscsoport</span><span class="sxs-lookup"><span data-stu-id="e7192-143">Resource group</span></span> | <span data-ttu-id="e7192-144">Adja meg ugyanazt az erőforrást, amelyhez a tárolási fiókot létrehozták.</span><span class="sxs-lookup"><span data-stu-id="e7192-144">Provide same resource under which storage account is created.</span></span>
    <span data-ttu-id="e7192-145">Régió</span><span class="sxs-lookup"><span data-stu-id="e7192-145">Region</span></span> | <span data-ttu-id="e7192-146">Adja meg a régiót.</span><span class="sxs-lookup"><span data-stu-id="e7192-146">Specify region.</span></span>
    <span data-ttu-id="e7192-147">Gyár neve</span><span class="sxs-lookup"><span data-stu-id="e7192-147">Factory Name</span></span> | <span data-ttu-id="e7192-148">Adja meg a gyár nevét.</span><span class="sxs-lookup"><span data-stu-id="e7192-148">Specify factory name.</span></span>
    <span data-ttu-id="e7192-149">FO összekapcsolt Service_service alapkulcs</span><span class="sxs-lookup"><span data-stu-id="e7192-149">FO Linked Service_service Principal Key</span></span> | <span data-ttu-id="e7192-150">Az alkalmazás kulcsának megadása.</span><span class="sxs-lookup"><span data-stu-id="e7192-150">Specify the application's key.</span></span>
    <span data-ttu-id="e7192-151">Azure Blob Storage_connection karakterlánc</span><span class="sxs-lookup"><span data-stu-id="e7192-151">Azure Blob Storage_connection String</span></span> | <span data-ttu-id="e7192-152">Azure Blob Storage kapcsolati karakterlánc.</span><span class="sxs-lookup"><span data-stu-id="e7192-152">Azure Blob storage connection string.</span></span>
    <span data-ttu-id="e7192-153">Dynamics Crm kapcsolt Service_password</span><span class="sxs-lookup"><span data-stu-id="e7192-153">Dynamics Crm Linked Service_password</span></span> | <span data-ttu-id="e7192-154">A felhasználónévként megadott felhasználói fiók jelszava.</span><span class="sxs-lookup"><span data-stu-id="e7192-154">The password for the user account you specified as the username.</span></span>
    <span data-ttu-id="e7192-155">FO összekapcsolt Service_properties_type Properties_url</span><span class="sxs-lookup"><span data-stu-id="e7192-155">FO Linked Service_properties_type Properties_url</span></span>  | `https://sampledynamics.sandbox-operationsdynamics.com/data`
    <span data-ttu-id="e7192-156">FO összekapcsolt Service_properties_type Properties_tenant</span><span class="sxs-lookup"><span data-stu-id="e7192-156">FO Linked Service_properties_type Properties_tenant</span></span> | <span data-ttu-id="e7192-157">Adja meg azt a bérlői információt (tartománynevet vagy bérlőazonosítót), amely alatt az alkalmazás található.</span><span class="sxs-lookup"><span data-stu-id="e7192-157">Specify the tenant information (domain name or tenant ID) under which your application resides.</span></span>
    <span data-ttu-id="e7192-158">FO összekapcsolt Service_properties_type Properties_aad Resource Id</span><span class="sxs-lookup"><span data-stu-id="e7192-158">FO Linked Service_properties_type Properties_aad Resource Id</span></span> | `https://sampledynamics.sandboxoperationsdynamics.com`
    <span data-ttu-id="e7192-159">FO összekapcsolt Service_properties_type Properties_service Principal Id</span><span class="sxs-lookup"><span data-stu-id="e7192-159">FO Linked Service_properties_type Properties_service Principal Id</span></span> | <span data-ttu-id="e7192-160">Az alkalmazás ügyfélazonosítójának megadása.</span><span class="sxs-lookup"><span data-stu-id="e7192-160">Specify the application's client ID.</span></span>
    <span data-ttu-id="e7192-161">Dynamics Crm csatolt Service_properties_type Properties_username</span><span class="sxs-lookup"><span data-stu-id="e7192-161">Dynamics Crm Linked Service_properties_type Properties_username</span></span> | <span data-ttu-id="e7192-162">A Dynamics-csatlakozáshoz használt felhasználónév.</span><span class="sxs-lookup"><span data-stu-id="e7192-162">The username to connect to Dynamics.</span></span>

    <span data-ttu-id="e7192-163">A további tudnivalókat lásd: [Erőforrás-kezelő sablon manuális promóciója az egyes környezetek számára](https://docs.microsoft.com/azure/data-factory/continuous-integration-deployment#manually-promote-a-resource-manager-template-for-each-environment), a [Kapcsolt szolgáltatás tulajdonságai](https://docs.microsoft.com/azure/data-factory/connector-dynamics-ax#linked-service-properties), valamint [Adatok másolása az Azure Data Factory segítségével](https://docs.microsoft.com/azure/data-factory/connector-dynamics-crm-office-365#dynamics-365-and-dynamics-crm-online)</span><span class="sxs-lookup"><span data-stu-id="e7192-163">For more information, see [Manually promote a Resource Manager template for each environment](https://docs.microsoft.com/azure/data-factory/continuous-integration-deployment#manually-promote-a-resource-manager-template-for-each-environment), [Linked service properties](https://docs.microsoft.com/azure/data-factory/connector-dynamics-ax#linked-service-properties), and [Copy data using Azure Data Factory](https://docs.microsoft.com/azure/data-factory/connector-dynamics-crm-office-365#dynamics-365-and-dynamics-crm-online)</span></span>

10. <span data-ttu-id="e7192-164">A telepítést követően ellenőrizze az adattárat, az adatáramlást és az adat-előállító kapcsolt szolgáltatását.</span><span class="sxs-lookup"><span data-stu-id="e7192-164">After deployment, validate the datasets, data flow, and linked service of the data factory.</span></span>

   ![Adatkészletek, adatáramlás és csatolt szolgáltatás](media/data-factory-validate.png)

11. <span data-ttu-id="e7192-166">Lépjen a **Kezelés** elemre.</span><span class="sxs-lookup"><span data-stu-id="e7192-166">Navigate to **Manage**.</span></span> <span data-ttu-id="e7192-167">A **Kapcsolatok** alatt válassza a **Csatolt szolgáltatás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e7192-167">Under **Connections**, select **Linked Service**.</span></span> <span data-ttu-id="e7192-168">Válassza a **DynamicsCrmLinkedService** elemet.</span><span class="sxs-lookup"><span data-stu-id="e7192-168">Select **DynamicsCrmLinkedService**.</span></span> <span data-ttu-id="e7192-169">A **Csatolt szolgáltatás szerkesztése képernyőn (Dynamics CRM)** írja be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="e7192-169">In the **Edit linked service (Dynamics CRM)** form, enter the following values:</span></span>

    <span data-ttu-id="e7192-170">Mező</span><span class="sxs-lookup"><span data-stu-id="e7192-170">Field</span></span> | <span data-ttu-id="e7192-171">Érték</span><span class="sxs-lookup"><span data-stu-id="e7192-171">Value</span></span>
    ---|---
    <span data-ttu-id="e7192-172">Név</span><span class="sxs-lookup"><span data-stu-id="e7192-172">Name</span></span> | <span data-ttu-id="e7192-173">DynamicsCrmLinkedService</span><span class="sxs-lookup"><span data-stu-id="e7192-173">DynamicsCrmLinkedService</span></span>
    <span data-ttu-id="e7192-174">Leírás</span><span class="sxs-lookup"><span data-stu-id="e7192-174">Description</span></span> | <span data-ttu-id="e7192-175">Az entitások adatainak beolvasására és a CRM-példányhoz való kapcsolódásra szolgáló kapcsolt szolgáltatások</span><span class="sxs-lookup"><span data-stu-id="e7192-175">Linked services to connect with CRM instance to fetch entities data</span></span>
    <span data-ttu-id="e7192-176">Csatlakozás integrációs modulon keresztül</span><span class="sxs-lookup"><span data-stu-id="e7192-176">Connect via integration runtime</span></span> | <span data-ttu-id="e7192-177">AutoResolvelntegrationRuntime</span><span class="sxs-lookup"><span data-stu-id="e7192-177">AutoResolvelntegrationRuntime</span></span>
    <span data-ttu-id="e7192-178">Telepítés típusa</span><span class="sxs-lookup"><span data-stu-id="e7192-178">Deployment type</span></span> | <span data-ttu-id="e7192-179">Online</span><span class="sxs-lookup"><span data-stu-id="e7192-179">Online</span></span>
    <span data-ttu-id="e7192-180">Szolgáltatási URI</span><span class="sxs-lookup"><span data-stu-id="e7192-180">Service Uri</span></span> | `https://<organization-name>.crm[x].dynamics.com`
    <span data-ttu-id="e7192-181">Hitelesítési típus</span><span class="sxs-lookup"><span data-stu-id="e7192-181">Authentication type</span></span> | <span data-ttu-id="e7192-182">Office365</span><span class="sxs-lookup"><span data-stu-id="e7192-182">Office365</span></span>
    <span data-ttu-id="e7192-183">Felhasználónév</span><span class="sxs-lookup"><span data-stu-id="e7192-183">User name</span></span> |
    <span data-ttu-id="e7192-184">Jelszó vagy Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="e7192-184">Password or Azure Key Vault</span></span> | <span data-ttu-id="e7192-185">Jelszó</span><span class="sxs-lookup"><span data-stu-id="e7192-185">Password</span></span>
    <span data-ttu-id="e7192-186">Jelszó</span><span class="sxs-lookup"><span data-stu-id="e7192-186">Password</span></span> |

## <a name="run-the-template"></a><span data-ttu-id="e7192-187">Futtassa a sablont</span><span class="sxs-lookup"><span data-stu-id="e7192-187">Run the template</span></span>

1. <span data-ttu-id="e7192-188">A következő **Számla**, **Kapcsolattartó** és **Szállító** kettős írásának leállítása az Finance and Operations alkalmazás segítségével.</span><span class="sxs-lookup"><span data-stu-id="e7192-188">Stop the following **Account**, **Contact**, and **Vendor** dual-write using the Finance and Operations app.</span></span>

    + <span data-ttu-id="e7192-189">Vevők V3 .(partnerek)</span><span class="sxs-lookup"><span data-stu-id="e7192-189">Customers V3(accounts)</span></span>
    + <span data-ttu-id="e7192-190">Vevők V3(kapcsolattartók)</span><span class="sxs-lookup"><span data-stu-id="e7192-190">Customers V3(contacts)</span></span>
    + <span data-ttu-id="e7192-191">CDS kapcsolattartók V2(kapcsolattartók)</span><span class="sxs-lookup"><span data-stu-id="e7192-191">CDS Contacts V2(contacts)</span></span>
    + <span data-ttu-id="e7192-192">CDS kapcsolattartók V2(kapcsolattartók)</span><span class="sxs-lookup"><span data-stu-id="e7192-192">CDS Contacts V2(contacts)</span></span>
    + <span data-ttu-id="e7192-193">Szállító V2 (msdyn_vendors)</span><span class="sxs-lookup"><span data-stu-id="e7192-193">Vendor V2 (msdyn_vendor)</span></span>

2. <span data-ttu-id="e7192-194">Győződjön meg róla, hogy a leképezések el vannak távolítva a `msdy_dualwriteruntimeconfig` táblából itt: Dataverse.</span><span class="sxs-lookup"><span data-stu-id="e7192-194">Make sure the maps are removed from the `msdy_dualwriteruntimeconfig` table in Dataverse.</span></span>

3. <span data-ttu-id="e7192-195">[Kettős írású fél és globális címjegyzék megoldások](https://aka.ms/dual-write-gab) telepítése innen: AppSource.</span><span class="sxs-lookup"><span data-stu-id="e7192-195">Install [Dual-write Party and Global Address Book Solutions](https://aka.ms/dual-write-gab) from AppSource.</span></span>

4. <span data-ttu-id="e7192-196">Az Finance and Operations alkalmazásban, ha a következő táblák adatokat tartalmaznak, futtassa az **Kezdeit szinkronizálás** műveletet.</span><span class="sxs-lookup"><span data-stu-id="e7192-196">In the Finance and Operations app, if the following tables contain data, then run **Initial Sync** for them.</span></span>

    + <span data-ttu-id="e7192-197">Üdvözlések</span><span class="sxs-lookup"><span data-stu-id="e7192-197">Salutations</span></span>
    + <span data-ttu-id="e7192-198">Személyes karaktertípusok</span><span class="sxs-lookup"><span data-stu-id="e7192-198">Personal character types</span></span>
    + <span data-ttu-id="e7192-199">Udvarias levélzárás</span><span class="sxs-lookup"><span data-stu-id="e7192-199">Complimentary closing</span></span>
    + <span data-ttu-id="e7192-200">Kapcsolattartó megszólításai</span><span class="sxs-lookup"><span data-stu-id="e7192-200">Contact person titles</span></span>
    + <span data-ttu-id="e7192-201">Döntéshozatali szerepkörök</span><span class="sxs-lookup"><span data-stu-id="e7192-201">Decision making roles</span></span>
    + <span data-ttu-id="e7192-202">Hűségszintek</span><span class="sxs-lookup"><span data-stu-id="e7192-202">Loyalty levels</span></span>

5. <span data-ttu-id="e7192-203">Az ügyfélkapcsolati alkalmazásban tiltsa le a következő beépülőmodul-lépéseket.</span><span class="sxs-lookup"><span data-stu-id="e7192-203">In the customer engagement app, disable the following plugin steps.</span></span>

    + <span data-ttu-id="e7192-204">Számla frissítése</span><span class="sxs-lookup"><span data-stu-id="e7192-204">Account Update</span></span>
         + <span data-ttu-id="e7192-205">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: Számla frissítése</span><span class="sxs-lookup"><span data-stu-id="e7192-205">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: Update of account</span></span>
         + <span data-ttu-id="e7192-206">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: Számla frissítése</span><span class="sxs-lookup"><span data-stu-id="e7192-206">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: Update of account</span></span>
    + <span data-ttu-id="e7192-207">Névjegyfrissítés</span><span class="sxs-lookup"><span data-stu-id="e7192-207">Contact Update</span></span>
         + <span data-ttu-id="e7192-208">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: Névjegyfrissítés</span><span class="sxs-lookup"><span data-stu-id="e7192-208">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: Update of contact</span></span>
         + <span data-ttu-id="e7192-209">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: Névjegyfrissítés</span><span class="sxs-lookup"><span data-stu-id="e7192-209">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: Update of contact</span></span>
    + <span data-ttu-id="e7192-210">msdyn_party frissítése</span><span class="sxs-lookup"><span data-stu-id="e7192-210">msdyn_party Update</span></span>
         + <span data-ttu-id="e7192-211">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: msdyn_party frissítése</span><span class="sxs-lookup"><span data-stu-id="e7192-211">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: Update of msdyn_party</span></span>
    + <span data-ttu-id="e7192-212">msdyn_vendor frissítése</span><span class="sxs-lookup"><span data-stu-id="e7192-212">msdyn_vendor Update</span></span>
         + <span data-ttu-id="e7192-213">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: msdyn_vendor frissítése</span><span class="sxs-lookup"><span data-stu-id="e7192-213">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: Update of msdyn_vendor</span></span>

6. <span data-ttu-id="e7192-214">Az ügyfélkapcsolati alkalmazásban tiltsa le a következő munkafolyamatokat.</span><span class="sxs-lookup"><span data-stu-id="e7192-214">In the customer engagement app, disable the following workflows:</span></span>

    + <span data-ttu-id="e7192-215">Szállítók létrehozása a Partnerek táblában</span><span class="sxs-lookup"><span data-stu-id="e7192-215">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="e7192-216">Szállítók létrehozása a Partnerek táblában</span><span class="sxs-lookup"><span data-stu-id="e7192-216">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="e7192-217">Személy típusú szállítók létrehozása a Kapcsolattartók táblában</span><span class="sxs-lookup"><span data-stu-id="e7192-217">Create Vendors of type person in Contacts Table</span></span>
    + <span data-ttu-id="e7192-218">Személy típusú szállítók létrehozása a Szállítók táblában</span><span class="sxs-lookup"><span data-stu-id="e7192-218">Create Vendors of type Person in Vendors Table</span></span>
    + <span data-ttu-id="e7192-219">Szállítók frissítése a Fiókok táblában</span><span class="sxs-lookup"><span data-stu-id="e7192-219">Update Vendors in Accounts Table</span></span>
    + <span data-ttu-id="e7192-220">Szállítók frissítése a Szállítók táblában</span><span class="sxs-lookup"><span data-stu-id="e7192-220">Update Vendors in Vendors Table</span></span>
    + <span data-ttu-id="e7192-221">Személy típusú szállítók frissítése a Kapcsolattartók táblában</span><span class="sxs-lookup"><span data-stu-id="e7192-221">Update Vendors of type Person in Contacts Table</span></span>
    + <span data-ttu-id="e7192-222">Személy típusú szállítók frissítése a Szállítók táblában</span><span class="sxs-lookup"><span data-stu-id="e7192-222">Update Vendors of type Person in Vendors Table</span></span>

7. <span data-ttu-id="e7192-223">Az adat-előállítóban futtassa a sablont úgy, hogy kiválasztja a **Kiváltás most** elemet úgy, ahogy az a következő képen látható.</span><span class="sxs-lookup"><span data-stu-id="e7192-223">In the data factory, run the template by selecting **Trigger now** as shown in the following image.</span></span> <span data-ttu-id="e7192-224">Ez a folyamat az adatok mennyisége alapján néhány óráig is igénybe vehet.</span><span class="sxs-lookup"><span data-stu-id="e7192-224">This process might take a few hours to complete based on the data volume.</span></span>

    ![Futtatás kiváltása](media/data-factory-trigger.png)

    > [!NOTE]
    > <span data-ttu-id="e7192-226">Ha testreszabott beállításai vannak a **számlához**, a **kapcsolattartóhoz** és a **szállítóhoz**, módosítania kell a sablont.</span><span class="sxs-lookup"><span data-stu-id="e7192-226">If you have customizations for **Account**, **Contact**, and **Vendor** then you must modify the template.</span></span>

8. <span data-ttu-id="e7192-227">Importálja az új **Partner** rekordjait az Finance and Operations alkalmazásból.</span><span class="sxs-lookup"><span data-stu-id="e7192-227">Import the new **Party** records in the Finance and Operations app.</span></span>

    + <span data-ttu-id="e7192-228">Töltse le a `FONewParty.csv` fájlt az Azure blobtárolóból.</span><span class="sxs-lookup"><span data-stu-id="e7192-228">Download the `FONewParty.csv` file from Azure blob storage.</span></span> <span data-ttu-id="e7192-229">Elérési út a következő: `partybootstrapping/output/FONewParty.csv`.</span><span class="sxs-lookup"><span data-stu-id="e7192-229">The path is `partybootstrapping/output/FONewParty.csv`.</span></span>
    + <span data-ttu-id="e7192-230">Konvertálja a `FONewParty.csv` fájlt Excel-fájlba és az Excel-fájlt importálja az Finance and Operations alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="e7192-230">Convert the `FONewParty.csv` file into an Excel file and import the Excel file into the Finance and Operations app.</span></span>  <span data-ttu-id="e7192-231">Ha a csv import megfelelő, akkor közvetlenül importálhatja a csv fájlt.</span><span class="sxs-lookup"><span data-stu-id="e7192-231">If the csv import works for you, you can import csv file directly.</span></span> <span data-ttu-id="e7192-232">Az importálás az adatmennyiségtől függően néhány óráig is igénybe vehet.</span><span class="sxs-lookup"><span data-stu-id="e7192-232">The import could take a few hours to run, depending on the data volume.</span></span> <span data-ttu-id="e7192-233">A további tudnivalókat lásd: [Adatimportálási és -exportálási feladatok áttekintése](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/data-import-export-job).</span><span class="sxs-lookup"><span data-stu-id="e7192-233">For more information, see [Data import and export jobs overview](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/data-import-export-job).</span></span>

    ![A Datavers fél rekordjainak importálása](media/data-factory-import-party.png)

9. <span data-ttu-id="e7192-235">Az ügyfélkapcsolati alkalmazásokban engedélyezze a következő beépülőmodul-lépéseket:</span><span class="sxs-lookup"><span data-stu-id="e7192-235">In the customer engagement apps, enable the following plugin steps:</span></span>

    + <span data-ttu-id="e7192-236">Számla frissítése</span><span class="sxs-lookup"><span data-stu-id="e7192-236">Account Update</span></span>
         + <span data-ttu-id="e7192-237">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: Számla frissítése</span><span class="sxs-lookup"><span data-stu-id="e7192-237">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: Update of account</span></span>
         + <span data-ttu-id="e7192-238">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: Számla frissítése</span><span class="sxs-lookup"><span data-stu-id="e7192-238">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: Update of account</span></span>
    + <span data-ttu-id="e7192-239">Névjegyfrissítés</span><span class="sxs-lookup"><span data-stu-id="e7192-239">Contact Update</span></span>
         + <span data-ttu-id="e7192-240">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: Névjegyfrissítés</span><span class="sxs-lookup"><span data-stu-id="e7192-240">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: Update of contact</span></span>
         + <span data-ttu-id="e7192-241">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: Névjegyfrissítés</span><span class="sxs-lookup"><span data-stu-id="e7192-241">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: Update of contact</span></span>
    + <span data-ttu-id="e7192-242">msdyn_party frissítése</span><span class="sxs-lookup"><span data-stu-id="e7192-242">msdyn_party Update</span></span>
         + <span data-ttu-id="e7192-243">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: msdyn_party frissítése</span><span class="sxs-lookup"><span data-stu-id="e7192-243">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: Update of msdyn_party</span></span>
    + <span data-ttu-id="e7192-244">msdyn_vendor frissítése</span><span class="sxs-lookup"><span data-stu-id="e7192-244">msdyn_vendor Update</span></span>
         + <span data-ttu-id="e7192-245">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: msdyn_vendor frissítése</span><span class="sxs-lookup"><span data-stu-id="e7192-245">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: Update of msdyn_vendor</span></span>

10. <span data-ttu-id="e7192-246">Ha az előző lépések során inaktiválta őket, aktiválja a következő munkafolyamatokat az ügyfélkapcsolati alkalmazásokban:</span><span class="sxs-lookup"><span data-stu-id="e7192-246">In the customer engagement apps, activate the following workflows if you deactivated them in previous steps:</span></span>

    + <span data-ttu-id="e7192-247">Szállítók létrehozása a Partnerek táblában</span><span class="sxs-lookup"><span data-stu-id="e7192-247">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="e7192-248">Szállítók létrehozása a Partnerek táblában</span><span class="sxs-lookup"><span data-stu-id="e7192-248">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="e7192-249">Személy típusú szállítók létrehozása a Kapcsolattartók táblában</span><span class="sxs-lookup"><span data-stu-id="e7192-249">Create Vendors of type person in Contacts Table</span></span>
    + <span data-ttu-id="e7192-250">Személy típusú szállítók létrehozása a Szállítók táblában</span><span class="sxs-lookup"><span data-stu-id="e7192-250">Create Vendors of type Person in Vendors Table</span></span>
    + <span data-ttu-id="e7192-251">Szállítók frissítése a Fiókok táblában</span><span class="sxs-lookup"><span data-stu-id="e7192-251">Update Vendors in Accounts Table</span></span>
    + <span data-ttu-id="e7192-252">Szállítók frissítése a Szállítók táblában</span><span class="sxs-lookup"><span data-stu-id="e7192-252">Update Vendors in Vendors Table</span></span>
    + <span data-ttu-id="e7192-253">Személy típusú szállítók frissítése a Kapcsolattartók táblában</span><span class="sxs-lookup"><span data-stu-id="e7192-253">Update Vendors of type Person in Contacts Table</span></span>
    + <span data-ttu-id="e7192-254">Személy típusú szállítók frissítése a Szállítók táblában</span><span class="sxs-lookup"><span data-stu-id="e7192-254">Update Vendors of type Person in Vendors Table</span></span>

11. <span data-ttu-id="e7192-255">A **Partnerhez** kapcsolódó leképezések futtatása a [Partner és a globális címjegyzék](party-gab.md) utasításának megfelelően.</span><span class="sxs-lookup"><span data-stu-id="e7192-255">Run the **Party**-related maps as instructed in [Party and global address book](party-gab.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="e7192-256">Hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="e7192-256">Troubleshooting</span></span>

1. <span data-ttu-id="e7192-257">A folyamat sikertelen végrehajtása esetén futtassa újra az adat-előállítót, a sikertelen tevékenységtől kezdve.</span><span class="sxs-lookup"><span data-stu-id="e7192-257">In the process fails, rerun the data factory starting from the failed activity.</span></span>
2. <span data-ttu-id="e7192-258">Egyes fájlokat az adat-előállító hoz létre, amely adatellenőrzési célokra használható.</span><span class="sxs-lookup"><span data-stu-id="e7192-258">Some files are generated by the data factory that you can use for data validation purpose.</span></span>
3. <span data-ttu-id="e7192-259">Az adat-előállító vesszővel tagolt csv-fájlokon alapulva fut.</span><span class="sxs-lookup"><span data-stu-id="e7192-259">The data factory runs based on csv files that are comma-delimited.</span></span> <span data-ttu-id="e7192-260">Ha olyan mezőérték van, amelynél vessző van, akkor az hatással lehet az eredményre.</span><span class="sxs-lookup"><span data-stu-id="e7192-260">If there is a field value that has a comma, it may interfere with the results.</span></span> <span data-ttu-id="e7192-261">El kell távolítania a vesszőket.</span><span class="sxs-lookup"><span data-stu-id="e7192-261">You need to remove the commas.</span></span>
4. <span data-ttu-id="e7192-262">A **Figyelés** lapon található tájékoztatás az összes lépésről és a feldolgozott adatokról.</span><span class="sxs-lookup"><span data-stu-id="e7192-262">The **Monitoring** tab provides information about all steps and data processed.</span></span> <span data-ttu-id="e7192-263">A hibakereséshez válasszon egy lépést.</span><span class="sxs-lookup"><span data-stu-id="e7192-263">Select a specific step to debug it.</span></span>

    ![Figyelés lap](media/data-factory-monitor.png)

## <a name="learn-more-about-the-template"></a><span data-ttu-id="e7192-265">További tudnivalók a sablonról</span><span class="sxs-lookup"><span data-stu-id="e7192-265">Learn more about the template</span></span>

<span data-ttu-id="e7192-266">A sablonhoz tartozó megjegyzések a [readme.md](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/readme.md) fájlban találhatók.</span><span class="sxs-lookup"><span data-stu-id="e7192-266">You can find comments for the template the [readme.md](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/readme.md) file.</span></span>
