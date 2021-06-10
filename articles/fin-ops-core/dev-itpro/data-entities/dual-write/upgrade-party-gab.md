---
title: Frissítés a fél és globális címjegyzék modelljére
description: Ez a témakör azt ismerteti, hogyan lehet kettős írású adatot frissíteni a partner és a globális címjegyzék modellel.
author: RamaKrishnamoorthy
ms.date: 03/31/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-03-31
ms.openlocfilehash: 90ddbe704ab21d62752b581a813601e8986c2103
ms.sourcegitcommit: 180548e3c10459776cf199989d3753e0c1555912
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/28/2021
ms.locfileid: "6112673"
---
# <a name="upgrade-to-the-party-and-global-address-book-model"></a><span data-ttu-id="bf2a0-103">Frissítés a fél és globális címjegyzék modelljére</span><span class="sxs-lookup"><span data-stu-id="bf2a0-103">Upgrade to the party and global address book model</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="bf2a0-104">A [Microsoft Azure Data Factory sablon](https://aka.ms/dual-write-gab-adf) segít frissíteni a kettős írású **Fiók**, **Kapcsolattartó** és **Szállító** táblaadatokat a partneri és a globális címjegyzék modelljére.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-104">The [Microsoft Azure Data Factory template](https://aka.ms/dual-write-gab-adf) helps you upgrade existing **Account**, **Contact**, and **Vendor** table data in dual-write to the party and global address book model.</span></span> <span data-ttu-id="bf2a0-105">A sablon a Finance and Operations- és a Customer Engagement-alkalmazásokból származó adatokat is egyezteti.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-105">The template reconciles the data from both finance and operations apps and customer engagement applications.</span></span> <span data-ttu-id="bf2a0-106">A folyamat végén a **Partner** rekordjaihoz tartozó **Partner** és **Kapcsolattartó** mezők létrejönnek, és társítva lesznek az ügyfélkapcsolati pályázatok **Számla**, **Kapcsolattartó** és **Szállító** rekordjaihoz.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-106">At the end of the process, **Party** and **Contact** fields for **Party** records will be created and associated with **Account**, **Contact**, and **Vendor** records in customer engagement applications.</span></span> <span data-ttu-id="bf2a0-107">A rendszer .csv fájlt (`FONewParty.csv`) hoz létre, hogy új **Partner** rekordokat hozzon létre a Finance and Operations-alkalmazáson belül.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-107">A .csv file (`FONewParty.csv`) is generated to create new **Party** records inside the finance and operations app.</span></span> <span data-ttu-id="bf2a0-108">Ez a témakör a Data Factory-sablon használatára és az adatok frissítésére vonatkozó útmutatást tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-108">This topic provides instructions about how to use the Data Factory template and upgrade your data.</span></span>

<span data-ttu-id="bf2a0-109">Ha nincsenek testreszabásai, a sablont használhatja úgy, ahogy van.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-109">If you don’t have any customizations, you can use the template as is.</span></span> <span data-ttu-id="bf2a0-110">Ha testreszabott beállításai vannak a **számlához**, a **kapcsolattartóhoz** és a **szállítóhoz**, akkor a következő útmutatásokkal kell módosítania a sablont.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-110">If you have customizations for **Account**, **Contact**, and **Vendor** then you must modify the template using the following instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="bf2a0-111">A sablon csak a **Partner** adatait frissíti.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-111">The template only upgrades the **Party** data.</span></span> <span data-ttu-id="bf2a0-112">Egy későbbi verzióban a postai és az elektronikus címek is szerepelni fognak.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-112">In a future release, postal and electronic addresses will be included.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bf2a0-113">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="bf2a0-113">Prerequisites</span></span>

<span data-ttu-id="bf2a0-114">A partneri és a globális címjegyzék modelljére való frissítéséhez a következő előfeltételek szükségesek:</span><span class="sxs-lookup"><span data-stu-id="bf2a0-114">The following prerequisites are required to upgrade to the party and global address book model:</span></span>

+ [<span data-ttu-id="bf2a0-115">Azure-előfizetés</span><span class="sxs-lookup"><span data-stu-id="bf2a0-115">Azure subscription</span></span>](https://portal.azure.com/)
+ [<span data-ttu-id="bf2a0-116">Hozzáférés a sablonhoz</span><span class="sxs-lookup"><span data-stu-id="bf2a0-116">Access to the template</span></span>](https://aka.ms/dual-write-gab-adf)
+ <span data-ttu-id="bf2a0-117">Önnek kettős írású ügyfélnek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-117">You must be an existing dual-write customer.</span></span>

## <a name="prepare-for-the-upgrade"></a><span data-ttu-id="bf2a0-118">Felkészülés a frissítésre</span><span class="sxs-lookup"><span data-stu-id="bf2a0-118">Prepare for the upgrade</span></span>
<span data-ttu-id="bf2a0-119">A frissítés előkészítéséhez a következő tevékenységek szükségesek:</span><span class="sxs-lookup"><span data-stu-id="bf2a0-119">The following activities are needed to prepare for the upgrade:</span></span>

+ <span data-ttu-id="bf2a0-120">**Teljesen szinkronizálva:** Mindkét környezet teljesen szinkronizálva van a **Számla (vevő)**, a **Kapcsolattartó** és a **Szállító** esetében.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-120">**Fully synced**: Both environments are in a fully synced state for **Account (Customer)**, **Contact**, and **Vendor**.</span></span>
+ <span data-ttu-id="bf2a0-121">**Integrációs kulcsok**: a **Számla (Vevő)**, a **Kapcsolattartó** és a **Szállító** tábla az ügyfélkapcsolati alkalmazásokban a gyárilag beépített integrációs kulcsokat használja.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-121">**Integration keys**: **Account (Customer)**, **Contact**, and **Vendor** tables in customer engagement apps are using the integration keys that shipped out-of-the-box.</span></span> <span data-ttu-id="bf2a0-122">Ha testre szabta az integrációs kulcsokat, testre kell szabni a sablont.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-122">If you customized the integration keys, you must customize the template.</span></span>
+ <span data-ttu-id="bf2a0-123">**Partnerszámszám**: a frissítésre sorra kerülő összes **Számla (Vevő)**, **Kapcsolattartó** és **Szállító** rekordnak van **partnerszáma**.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-123">**Party number**: All **Account (Customer)**, **Contact**, and **Vendor** records that will be upgraded have a **Party** number.</span></span> <span data-ttu-id="bf2a0-124">A **Partnerszám** nélküli rekordokat figyelmen kívül hagyja a rendszer.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-124">Records without a **Party** number will be ignored.</span></span> <span data-ttu-id="bf2a0-125">Ha frissíteni szeretné ezeket a rekordokat, a frissítési folyamat kezdete előtt adjon hozzá egy **Partnerszámot**.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-125">If you want to upgrade those records, add a **Party** number to them before you start the upgrade process.</span></span>
+ <span data-ttu-id="bf2a0-126">**Rendszerszünet**: A frissítési folyamat során mind a Finance and Operations-, mind a Customer Engagement-környezeteket kapcsolat nélkül módba kell vinni.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-126">**System outage**: During the upgrade process, you will have to take both the finance and operations and customer engagement environments offline.</span></span>
+ <span data-ttu-id="bf2a0-127">**Pillanatkép**: Pillanatkép készítése mind a Finance and Operations-, mind a Customer Engagement-alkalmazásokról.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-127">**Snapshot**: Take snapshots of both the finance and operations apps and customer engagement apps.</span></span> <span data-ttu-id="bf2a0-128">A pillanatképek segítségével szükség esetén visszaállíthatja az előző állapotot.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-128">Use the snapshots to restore the previous state if you need to.</span></span>

## <a name="deployment"></a><span data-ttu-id="bf2a0-129">Telepítés</span><span class="sxs-lookup"><span data-stu-id="bf2a0-129">Deployment</span></span>

1. <span data-ttu-id="bf2a0-130">Töltse le a sablont a [Dynamics-365-FastTrack-Implementation-Assets](https://aka.ms/dual-write-gab-adf) eszközből.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-130">Download the template from [Dynamics-365-FastTrack-Implementation-Assets](https://aka.ms/dual-write-gab-adf).</span></span>

2. <span data-ttu-id="bf2a0-131">Jelentkezzen be ide: [Microsoft Azure](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="bf2a0-131">Sign in to [Microsoft Azure](https://portal.azure.com/).</span></span>

3. <span data-ttu-id="bf2a0-132">Hozzon létre egy [erőforráscsoportot](/azure/azure-resource-manager/management/manage-resource-groups-portal).</span><span class="sxs-lookup"><span data-stu-id="bf2a0-132">Create a [resource group](/azure/azure-resource-manager/management/manage-resource-groups-portal).</span></span>

4. <span data-ttu-id="bf2a0-133">Hozzon létre egy [tárolási fiókot](/azure/storage/common/storage-account-create?tabs=azure-portal) a létrehozott erőforráscsoportban.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-133">Create a [storage account](/azure/storage/common/storage-account-create?tabs=azure-portal) in the resource group that you created.</span></span>

5. <span data-ttu-id="bf2a0-134">Hozzon létre egy [adat-előállítót](/azure/data-factory/quickstart-create-data-factory-portal) a fent létrehozott erőforráscsoportban.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-134">Create a [data factory](/azure/data-factory/quickstart-create-data-factory-portal) in above resource group that you created.</span></span>

6. <span data-ttu-id="bf2a0-135">Nyissa meg az adat-előállítót, és válassza a **Szerző & Monitor** csempét.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-135">Open the data factory and select the **Author & Monitor** tile.</span></span>

7. <span data-ttu-id="bf2a0-136">A **Kezelés** lapon válassza ki az **ARM-sablont**.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-136">On the **Manage** tab, select **ARM template**.</span></span>

8. <span data-ttu-id="bf2a0-137">Válassza ki az **ARM-sablon importálása** lehetőséget a **Partner** sablon importálásához.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-137">Select the **Import ARM template** to import the **Party** template.</span></span>

9. <span data-ttu-id="bf2a0-138">A sablon importálása az adat-előállítóba.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-138">Import the template into the data factory.</span></span> <span data-ttu-id="bf2a0-139">Adja meg az alábbi értékeket a **projekt részleteinél** és a **példányok részleteinél**.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-139">Enter the following values for **Project details** and **Instance details**.</span></span>

    <span data-ttu-id="bf2a0-140">Mező</span><span class="sxs-lookup"><span data-stu-id="bf2a0-140">Field</span></span> | <span data-ttu-id="bf2a0-141">Érték</span><span class="sxs-lookup"><span data-stu-id="bf2a0-141">Value</span></span>
    ---|---
    <span data-ttu-id="bf2a0-142">Előfizetés</span><span class="sxs-lookup"><span data-stu-id="bf2a0-142">Subscription</span></span> | <span data-ttu-id="bf2a0-143">Azure-előfizetés</span><span class="sxs-lookup"><span data-stu-id="bf2a0-143">Azure subscription</span></span>
    <span data-ttu-id="bf2a0-144">Erőforráscsoport</span><span class="sxs-lookup"><span data-stu-id="bf2a0-144">Resource group</span></span> | <span data-ttu-id="bf2a0-145">Adja meg ugyanazt az erőforrást, amelyhez a tárolási fiókot létrehozták.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-145">Provide same resource under which storage account is created.</span></span>
    <span data-ttu-id="bf2a0-146">Régió</span><span class="sxs-lookup"><span data-stu-id="bf2a0-146">Region</span></span> | <span data-ttu-id="bf2a0-147">Adja meg a régiót.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-147">Specify region.</span></span>
    <span data-ttu-id="bf2a0-148">Gyár neve</span><span class="sxs-lookup"><span data-stu-id="bf2a0-148">Factory Name</span></span> | <span data-ttu-id="bf2a0-149">Adja meg a gyár nevét.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-149">Specify factory name.</span></span>
    <span data-ttu-id="bf2a0-150">FO összekapcsolt Service_service alapkulcs</span><span class="sxs-lookup"><span data-stu-id="bf2a0-150">FO Linked Service_service Principal Key</span></span> | <span data-ttu-id="bf2a0-151">Az alkalmazás kulcsának megadása.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-151">Specify the application's key.</span></span>
    <span data-ttu-id="bf2a0-152">Azure Blob Storage_connection karakterlánc</span><span class="sxs-lookup"><span data-stu-id="bf2a0-152">Azure Blob Storage_connection String</span></span> | <span data-ttu-id="bf2a0-153">Azure Blob Storage kapcsolati karakterlánc.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-153">Azure Blob storage connection string.</span></span>
    <span data-ttu-id="bf2a0-154">Dynamics Crm kapcsolt Service_password</span><span class="sxs-lookup"><span data-stu-id="bf2a0-154">Dynamics Crm Linked Service_password</span></span> | <span data-ttu-id="bf2a0-155">A felhasználónévként megadott felhasználói fiók jelszava.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-155">The password for the user account you specified as the username.</span></span>
    <span data-ttu-id="bf2a0-156">FO összekapcsolt Service_properties_type Properties_url</span><span class="sxs-lookup"><span data-stu-id="bf2a0-156">FO Linked Service_properties_type Properties_url</span></span>  | `https://sampledynamics.sandbox-operationsdynamics.com/data`
    <span data-ttu-id="bf2a0-157">FO összekapcsolt Service_properties_type Properties_tenant</span><span class="sxs-lookup"><span data-stu-id="bf2a0-157">FO Linked Service_properties_type Properties_tenant</span></span> | <span data-ttu-id="bf2a0-158">Adja meg azt a bérlői információt (tartománynevet vagy bérlőazonosítót), amely alatt az alkalmazás található.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-158">Specify the tenant information (domain name or tenant ID) under which your application resides.</span></span>
    <span data-ttu-id="bf2a0-159">FO összekapcsolt Service_properties_type Properties_aad Resource Id</span><span class="sxs-lookup"><span data-stu-id="bf2a0-159">FO Linked Service_properties_type Properties_aad Resource Id</span></span> | `https://sampledynamics.sandboxoperationsdynamics.com`
    <span data-ttu-id="bf2a0-160">FO összekapcsolt Service_properties_type Properties_service Principal Id</span><span class="sxs-lookup"><span data-stu-id="bf2a0-160">FO Linked Service_properties_type Properties_service Principal Id</span></span> | <span data-ttu-id="bf2a0-161">Az alkalmazás ügyfélazonosítójának megadása.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-161">Specify the application's client ID.</span></span>
    <span data-ttu-id="bf2a0-162">Dynamics Crm csatolt Service_properties_type Properties_username</span><span class="sxs-lookup"><span data-stu-id="bf2a0-162">Dynamics Crm Linked Service_properties_type Properties_username</span></span> | <span data-ttu-id="bf2a0-163">A Dynamics 365-csatlakozáshoz használt felhasználónév.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-163">The username to connect to Dynamics 365.</span></span>

    <span data-ttu-id="bf2a0-164">További tájékoztatás a következő témakörökben található:</span><span class="sxs-lookup"><span data-stu-id="bf2a0-164">For additional information, refer to the following topics:</span></span> 
    
    - [<span data-ttu-id="bf2a0-165">Erőforrás-kezelő sablon manuális promóciója az egyes környezetek számára</span><span class="sxs-lookup"><span data-stu-id="bf2a0-165">Manually promote a Resource Manager template for each environment</span></span>](/azure/data-factory/continuous-integration-deployment#manually-promote-a-resource-manager-template-for-each-environment)
    - [<span data-ttu-id="bf2a0-166">Kapcsolt szolgáltatás tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="bf2a0-166">Linked service properties</span></span>](/azure/data-factory/connector-dynamics-ax#linked-service-properties)
    - [<span data-ttu-id="bf2a0-167">Adatok másolása az Azure Data Factory segítségével</span><span class="sxs-lookup"><span data-stu-id="bf2a0-167">Copy data using Azure Data Factory</span></span>](/azure/data-factory/connector-dynamics-crm-office-365#dynamics-365-and-dynamics-crm-online)

10. <span data-ttu-id="bf2a0-168">A telepítést követően ellenőrizze az adattárat, az adatáramlást és az adat-előállító kapcsolt szolgáltatását.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-168">After deployment, validate the datasets, data flow, and linked service of the data factory.</span></span>

   ![Adatkészletek, adatáramlás és csatolt szolgáltatás](media/data-factory-validate.png)

11. <span data-ttu-id="bf2a0-170">Lépjen a **Kezelés** elemre.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-170">Navigate to **Manage**.</span></span> <span data-ttu-id="bf2a0-171">A **Kapcsolatok** alatt válassza a **Csatolt szolgáltatás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-171">Under **Connections**, select **Linked Service**.</span></span> <span data-ttu-id="bf2a0-172">Válassza a **DynamicsCrmLinkedService** elemet.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-172">Select **DynamicsCrmLinkedService**.</span></span> <span data-ttu-id="bf2a0-173">A **Csatolt szolgáltatás szerkesztése (Dynamics CRM)** űrlapon írja be a következő értékeket.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-173">In the **Edit linked service (Dynamics CRM)** form, enter the following values.</span></span>

    <span data-ttu-id="bf2a0-174">Mező</span><span class="sxs-lookup"><span data-stu-id="bf2a0-174">Field</span></span> | <span data-ttu-id="bf2a0-175">Érték</span><span class="sxs-lookup"><span data-stu-id="bf2a0-175">Value</span></span>
    ---|---
    <span data-ttu-id="bf2a0-176">Név</span><span class="sxs-lookup"><span data-stu-id="bf2a0-176">Name</span></span> | <span data-ttu-id="bf2a0-177">DynamicsCrmLinkedService</span><span class="sxs-lookup"><span data-stu-id="bf2a0-177">DynamicsCrmLinkedService</span></span>
    <span data-ttu-id="bf2a0-178">Leírás</span><span class="sxs-lookup"><span data-stu-id="bf2a0-178">Description</span></span> | <span data-ttu-id="bf2a0-179">Az entitások adatainak beolvasására és a CRM-példányhoz való kapcsolódásra szolgáló kapcsolt szolgáltatások</span><span class="sxs-lookup"><span data-stu-id="bf2a0-179">Linked services to connect with CRM instance to fetch entities data</span></span>
    <span data-ttu-id="bf2a0-180">Csatlakozás integrációs modulon keresztül</span><span class="sxs-lookup"><span data-stu-id="bf2a0-180">Connect via integration runtime</span></span> | <span data-ttu-id="bf2a0-181">AutoResolvelntegrationRuntime</span><span class="sxs-lookup"><span data-stu-id="bf2a0-181">AutoResolvelntegrationRuntime</span></span>
    <span data-ttu-id="bf2a0-182">Telepítés típusa</span><span class="sxs-lookup"><span data-stu-id="bf2a0-182">Deployment type</span></span> | <span data-ttu-id="bf2a0-183">Online</span><span class="sxs-lookup"><span data-stu-id="bf2a0-183">Online</span></span>
    <span data-ttu-id="bf2a0-184">Szolgáltatási URI</span><span class="sxs-lookup"><span data-stu-id="bf2a0-184">Service Uri</span></span> | `https://<organization-name>.crm[x].dynamics.com`
    <span data-ttu-id="bf2a0-185">Hitelesítési típus</span><span class="sxs-lookup"><span data-stu-id="bf2a0-185">Authentication type</span></span> | <span data-ttu-id="bf2a0-186">Office365</span><span class="sxs-lookup"><span data-stu-id="bf2a0-186">Office365</span></span>
    <span data-ttu-id="bf2a0-187">Felhasználónév</span><span class="sxs-lookup"><span data-stu-id="bf2a0-187">User name</span></span> |
    <span data-ttu-id="bf2a0-188">Jelszó vagy Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="bf2a0-188">Password or Azure Key Vault</span></span> | <span data-ttu-id="bf2a0-189">Jelszó</span><span class="sxs-lookup"><span data-stu-id="bf2a0-189">Password</span></span>
    <span data-ttu-id="bf2a0-190">Jelszó</span><span class="sxs-lookup"><span data-stu-id="bf2a0-190">Password</span></span> |

## <a name="run-the-template"></a><span data-ttu-id="bf2a0-191">Futtassa a sablont</span><span class="sxs-lookup"><span data-stu-id="bf2a0-191">Run the template</span></span>

1. <span data-ttu-id="bf2a0-192">Állítsa le a következő **Számla**, **Kapcsolattartó** és **Szállító** kettős írású leképezését a Finance and Operations alkalmazás segítségével.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-192">Stop the following **Account**, **Contact**, and **Vendor** dual-write maps using the Finance and Operations app.</span></span>

    + <span data-ttu-id="bf2a0-193">Vevők V3 .(partnerek)</span><span class="sxs-lookup"><span data-stu-id="bf2a0-193">Customers V3(accounts)</span></span>
    + <span data-ttu-id="bf2a0-194">Vevők V3(kapcsolattartók)</span><span class="sxs-lookup"><span data-stu-id="bf2a0-194">Customers V3(contacts)</span></span>
    + <span data-ttu-id="bf2a0-195">CDS kapcsolattartók V2(kapcsolattartók)</span><span class="sxs-lookup"><span data-stu-id="bf2a0-195">CDS Contacts V2(contacts)</span></span>
    + <span data-ttu-id="bf2a0-196">CDS kapcsolattartók V2(kapcsolattartók)</span><span class="sxs-lookup"><span data-stu-id="bf2a0-196">CDS Contacts V2(contacts)</span></span>
    + <span data-ttu-id="bf2a0-197">Szállító V2 (msdyn_vendors)</span><span class="sxs-lookup"><span data-stu-id="bf2a0-197">Vendor V2 (msdyn_vendor)</span></span>

2. <span data-ttu-id="bf2a0-198">Győződjön meg róla, hogy a leképezések el vannak távolítva a `msdy_dualwriteruntimeconfig` táblából itt: Dataverse.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-198">Make sure the maps are removed from the `msdy_dualwriteruntimeconfig` table in Dataverse.</span></span>

3. <span data-ttu-id="bf2a0-199">[Kettős írású fél és globális címjegyzék megoldások](https://aka.ms/dual-write-gab) telepítése innen: AppSource.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-199">Install [Dual-write Party and Global Address Book Solutions](https://aka.ms/dual-write-gab) from AppSource.</span></span>

4. <span data-ttu-id="bf2a0-200">Ha a Finance and Operations alkalmazásban a következő táblák adatokat tartalmaznak, futtassa a **Kezdeti szinkronizálás** műveletet.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-200">In the finance and operations app, if the following tables contain data, then run **Initial Sync** for them.</span></span>

    + <span data-ttu-id="bf2a0-201">Üdvözlések</span><span class="sxs-lookup"><span data-stu-id="bf2a0-201">Salutations</span></span>
    + <span data-ttu-id="bf2a0-202">Személyes karaktertípusok</span><span class="sxs-lookup"><span data-stu-id="bf2a0-202">Personal character types</span></span>
    + <span data-ttu-id="bf2a0-203">Udvarias levélzárás</span><span class="sxs-lookup"><span data-stu-id="bf2a0-203">Complimentary closing</span></span>
    + <span data-ttu-id="bf2a0-204">Kapcsolattartó megszólításai</span><span class="sxs-lookup"><span data-stu-id="bf2a0-204">Contact person titles</span></span>
    + <span data-ttu-id="bf2a0-205">Döntéshozatali szerepkörök</span><span class="sxs-lookup"><span data-stu-id="bf2a0-205">Decision making roles</span></span>
    + <span data-ttu-id="bf2a0-206">Hűségszintek</span><span class="sxs-lookup"><span data-stu-id="bf2a0-206">Loyalty levels</span></span>

5. <span data-ttu-id="bf2a0-207">A Customer Engagement alkalmazásban tiltsa le a következő beépülőmodul-lépéseket.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-207">In the customer engagement app, disable the following plug-in steps.</span></span>

    + <span data-ttu-id="bf2a0-208">Számla frissítése</span><span class="sxs-lookup"><span data-stu-id="bf2a0-208">Account Update</span></span>
         + <span data-ttu-id="bf2a0-209">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: Számla frissítése</span><span class="sxs-lookup"><span data-stu-id="bf2a0-209">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: Update of account</span></span>
         + <span data-ttu-id="bf2a0-210">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: Számla frissítése</span><span class="sxs-lookup"><span data-stu-id="bf2a0-210">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: Update of account</span></span>
    + <span data-ttu-id="bf2a0-211">Névjegyfrissítés</span><span class="sxs-lookup"><span data-stu-id="bf2a0-211">Contact Update</span></span>
         + <span data-ttu-id="bf2a0-212">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: Névjegyfrissítés</span><span class="sxs-lookup"><span data-stu-id="bf2a0-212">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: Update of contact</span></span>
         + <span data-ttu-id="bf2a0-213">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: Névjegyfrissítés</span><span class="sxs-lookup"><span data-stu-id="bf2a0-213">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: Update of contact</span></span>
    + <span data-ttu-id="bf2a0-214">msdyn_party frissítése</span><span class="sxs-lookup"><span data-stu-id="bf2a0-214">msdyn_party Update</span></span>
         + <span data-ttu-id="bf2a0-215">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: msdyn_party frissítése</span><span class="sxs-lookup"><span data-stu-id="bf2a0-215">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: Update of msdyn_party</span></span>
    + <span data-ttu-id="bf2a0-216">msdyn_vendor frissítése</span><span class="sxs-lookup"><span data-stu-id="bf2a0-216">msdyn_vendor Update</span></span>
         + <span data-ttu-id="bf2a0-217">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: msdyn_vendor frissítése</span><span class="sxs-lookup"><span data-stu-id="bf2a0-217">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: Update of msdyn_vendor</span></span>

6. <span data-ttu-id="bf2a0-218">Az ügyfélkapcsolati alkalmazásban tiltsa le a következő munkafolyamatokat.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-218">In the customer engagement app, disable the following workflows:</span></span>

    + <span data-ttu-id="bf2a0-219">Szállítók létrehozása a Partnerek táblában</span><span class="sxs-lookup"><span data-stu-id="bf2a0-219">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="bf2a0-220">Szállítók létrehozása a Partnerek táblában</span><span class="sxs-lookup"><span data-stu-id="bf2a0-220">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="bf2a0-221">Személy típusú szállítók létrehozása a Kapcsolattartók táblában</span><span class="sxs-lookup"><span data-stu-id="bf2a0-221">Create Vendors of type person in Contacts Table</span></span>
    + <span data-ttu-id="bf2a0-222">Személy típusú szállítók létrehozása a Szállítók táblában</span><span class="sxs-lookup"><span data-stu-id="bf2a0-222">Create Vendors of type Person in Vendors Table</span></span>
    + <span data-ttu-id="bf2a0-223">Szállítók frissítése a Fiókok táblában</span><span class="sxs-lookup"><span data-stu-id="bf2a0-223">Update Vendors in Accounts Table</span></span>
    + <span data-ttu-id="bf2a0-224">Szállítók frissítése a Szállítók táblában</span><span class="sxs-lookup"><span data-stu-id="bf2a0-224">Update Vendors in Vendors Table</span></span>
    + <span data-ttu-id="bf2a0-225">Személy típusú szállítók frissítése a Kapcsolattartók táblában</span><span class="sxs-lookup"><span data-stu-id="bf2a0-225">Update Vendors of type Person in Contacts Table</span></span>
    + <span data-ttu-id="bf2a0-226">Személy típusú szállítók frissítése a Szállítók táblában</span><span class="sxs-lookup"><span data-stu-id="bf2a0-226">Update Vendors of type Person in Vendors Table</span></span>

7. <span data-ttu-id="bf2a0-227">Az adat-előállítóban futtassa a sablont úgy, hogy kiválasztja a **Kiváltás most** elemet úgy, ahogy az a következő képen látható.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-227">In the data factory, run the template by selecting **Trigger now** as shown in the following image.</span></span> <span data-ttu-id="bf2a0-228">Ez a folyamat az adatok mennyisége alapján néhány óráig is igénybe vehet.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-228">This process might take a few hours to complete based on the data volume.</span></span>

    ![Futtatás kiváltása](media/data-factory-trigger.png)

    > [!NOTE]
    > <span data-ttu-id="bf2a0-230">Ha testre szabott beállításai vannak a **Számlához**, a **Kapcsolattartóhoz** és a **Szállítóhoz**, módosítania kell a sablont.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-230">If you have customizations for **Account**, **Contact**, and **Vendor**, then you need to modify the template.</span></span>

8. <span data-ttu-id="bf2a0-231">Importálja az új **Partner** rekordjait az Finance and Operations alkalmazásból.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-231">Import the new **Party** records in the Finance and Operations app.</span></span>

    + <span data-ttu-id="bf2a0-232">Töltse le a `FONewParty.csv` fájlt az Azure blobtárolóból.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-232">Download the `FONewParty.csv` file from Azure blob storage.</span></span> <span data-ttu-id="bf2a0-233">Elérési út a következő: `partybootstrapping/output/FONewParty.csv`.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-233">The path is `partybootstrapping/output/FONewParty.csv`.</span></span>
    + <span data-ttu-id="bf2a0-234">Konvertálja a `FONewParty.csv` fájlt Excel-fájlba, és az Excel-fájlt importálja a Finance and Operations alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-234">Convert the `FONewParty.csv` file into an Excel file and import the Excel file into the finance and operations app.</span></span> <span data-ttu-id="bf2a0-235">Ha a csv import megfelelő, akkor közvetlenül importálhatja a csv fájlt.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-235">If the csv import works for you, you can import the csv file directly.</span></span> <span data-ttu-id="bf2a0-236">Az importálás az adatmennyiségtől függően néhány óráig is igénybe vehet.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-236">The import could take a few hours to run, depending on the data volume.</span></span> <span data-ttu-id="bf2a0-237">A további tudnivalókat lásd: [Adatimportálási és -exportálási feladatok áttekintése](../data-import-export-job.md).</span><span class="sxs-lookup"><span data-stu-id="bf2a0-237">For more information, see [Data import and export jobs overview](../data-import-export-job.md).</span></span>

    ![A Datavers fél rekordjainak importálása](media/data-factory-import-party.png)

9. <span data-ttu-id="bf2a0-239">A Customer Engagement-alkalmazásokban engedélyezze a következő beépülőmodul-lépéseket:</span><span class="sxs-lookup"><span data-stu-id="bf2a0-239">In the customer engagement apps, enable the following plug-in steps:</span></span>

    + <span data-ttu-id="bf2a0-240">Számla frissítése</span><span class="sxs-lookup"><span data-stu-id="bf2a0-240">Account Update</span></span>
         + <span data-ttu-id="bf2a0-241">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: Számla frissítése</span><span class="sxs-lookup"><span data-stu-id="bf2a0-241">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: Update of account</span></span>
         + <span data-ttu-id="bf2a0-242">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: Számla frissítése</span><span class="sxs-lookup"><span data-stu-id="bf2a0-242">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: Update of account</span></span>
    + <span data-ttu-id="bf2a0-243">Névjegyfrissítés</span><span class="sxs-lookup"><span data-stu-id="bf2a0-243">Contact Update</span></span>
         + <span data-ttu-id="bf2a0-244">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: Névjegyfrissítés</span><span class="sxs-lookup"><span data-stu-id="bf2a0-244">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: Update of contact</span></span>
         + <span data-ttu-id="bf2a0-245">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: Névjegyfrissítés</span><span class="sxs-lookup"><span data-stu-id="bf2a0-245">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: Update of contact</span></span>
    + <span data-ttu-id="bf2a0-246">msdyn_party frissítése</span><span class="sxs-lookup"><span data-stu-id="bf2a0-246">msdyn_party Update</span></span>
         + <span data-ttu-id="bf2a0-247">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: msdyn_party frissítése</span><span class="sxs-lookup"><span data-stu-id="bf2a0-247">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: Update of msdyn_party</span></span>
    + <span data-ttu-id="bf2a0-248">msdyn_vendor frissítése</span><span class="sxs-lookup"><span data-stu-id="bf2a0-248">msdyn_vendor Update</span></span>
         + <span data-ttu-id="bf2a0-249">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: msdyn_vendor frissítése</span><span class="sxs-lookup"><span data-stu-id="bf2a0-249">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: Update of msdyn_vendor</span></span>

10. <span data-ttu-id="bf2a0-250">Ha az előző lépések során inaktiválta őket, aktiválja a következő munkafolyamatokat az ügyfélkapcsolati alkalmazásokban:</span><span class="sxs-lookup"><span data-stu-id="bf2a0-250">In the customer engagement apps, activate the following workflows if you deactivated them in previous steps:</span></span>

    + <span data-ttu-id="bf2a0-251">Szállítók létrehozása a Partnerek táblában</span><span class="sxs-lookup"><span data-stu-id="bf2a0-251">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="bf2a0-252">Szállítók létrehozása a Partnerek táblában</span><span class="sxs-lookup"><span data-stu-id="bf2a0-252">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="bf2a0-253">Személy típusú szállítók létrehozása a Kapcsolattartók táblában</span><span class="sxs-lookup"><span data-stu-id="bf2a0-253">Create Vendors of type person in Contacts Table</span></span>
    + <span data-ttu-id="bf2a0-254">Személy típusú szállítók létrehozása a Szállítók táblában</span><span class="sxs-lookup"><span data-stu-id="bf2a0-254">Create Vendors of type Person in Vendors Table</span></span>
    + <span data-ttu-id="bf2a0-255">Szállítók frissítése a Fiókok táblában</span><span class="sxs-lookup"><span data-stu-id="bf2a0-255">Update Vendors in Accounts Table</span></span>
    + <span data-ttu-id="bf2a0-256">Szállítók frissítése a Szállítók táblában</span><span class="sxs-lookup"><span data-stu-id="bf2a0-256">Update Vendors in Vendors Table</span></span>
    + <span data-ttu-id="bf2a0-257">Személy típusú szállítók frissítése a Kapcsolattartók táblában</span><span class="sxs-lookup"><span data-stu-id="bf2a0-257">Update Vendors of type Person in Contacts Table</span></span>
    + <span data-ttu-id="bf2a0-258">Személy típusú szállítók frissítése a Szállítók táblában</span><span class="sxs-lookup"><span data-stu-id="bf2a0-258">Update Vendors of type Person in Vendors Table</span></span>

11. <span data-ttu-id="bf2a0-259">A **Partnerhez** kapcsolódó leképezések futtatása a [Partner és a globális címjegyzék](party-gab.md) utasításának megfelelően.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-259">Run the **Party**-related maps as instructed in [Party and global address book](party-gab.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="bf2a0-260">Hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="bf2a0-260">Troubleshooting</span></span>

1. <span data-ttu-id="bf2a0-261">A folyamat sikertelen végrehajtása esetén futtassa újra az adat-előállítót, a sikertelen tevékenységtől kezdve.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-261">If the process fails, rerun the data factory starting from the failed activity.</span></span>
2. <span data-ttu-id="bf2a0-262">Egyes fájlokat az adat-előállító hoz létre, amely adatellenőrzési célokra használható.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-262">Some files are generated by the data factory that you can use for data validation purpose.</span></span>
3. <span data-ttu-id="bf2a0-263">Az adat-előállító vesszővel tagolt csv-fájlokon alapulva fut.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-263">The data factory runs based on csv files that are comma-delimited.</span></span> <span data-ttu-id="bf2a0-264">Ha olyan mezőérték van, amelynél vessző van, akkor az hatással lehet az eredményre.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-264">If there is a field value that has a comma, it may interfere with the results.</span></span> <span data-ttu-id="bf2a0-265">El kell távolítania a vesszőket.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-265">You need to remove the commas.</span></span>
4. <span data-ttu-id="bf2a0-266">A **Figyelés** lapon található tájékoztatás az összes lépésről és a feldolgozott adatokról.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-266">The **Monitoring** tab provides information about all steps and data processed.</span></span> <span data-ttu-id="bf2a0-267">A hibakereséshez válasszon egy lépést.</span><span class="sxs-lookup"><span data-stu-id="bf2a0-267">Select a specific step to debug it.</span></span>

    ![Figyelés lap](media/data-factory-monitor.png)

## <a name="learn-more-about-the-template"></a><span data-ttu-id="bf2a0-269">További tudnivalók a sablonról</span><span class="sxs-lookup"><span data-stu-id="bf2a0-269">Learn more about the template</span></span>

<span data-ttu-id="bf2a0-270">További információk a sablonról: [Az Azure Data Factory-sablonra vonatkozó megjegyzések, readme](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/readme.md).</span><span class="sxs-lookup"><span data-stu-id="bf2a0-270">You can find additional information about the template in [Comments for Azure Data Factory template readme](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/readme.md).</span></span>
