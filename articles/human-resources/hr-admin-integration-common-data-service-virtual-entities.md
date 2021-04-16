---
title: Dataverse-virtuális táblák konfigurálása
description: Ez a témakör azt mutatja be, hogyan lehet beállítani a virtuális táblákat a Dynamics 365 Human Resources esetén. Meglévő virtuális táblák létrehozása és frissítése, valamint létrehozott és elérhető táblák elemzése.
author: andreabichsel
ms.date: 01/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CDSIntegrationAdministration
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4d80680f66d8669425482a54066f48af8ebcfbc8
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5805106"
---
# <a name="configure-dataverse-virtual-tables"></a><span data-ttu-id="05f78-104">Dataverse-virtuális táblák konfigurálása</span><span class="sxs-lookup"><span data-stu-id="05f78-104">Configure Dataverse virtual tables</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="05f78-105">A Dynamics 365 Human Resources egy virtuális adatforrás a következőben: Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="05f78-105">Dynamics 365 Human Resources is a virtual data source in Microsoft Dataverse.</span></span> <span data-ttu-id="05f78-106">Teljes körű létrehozási, olvasási, frissítési és törlési (CRUD) műveletek végrehajtását teszi lehetővé a következőkből: Dataverse és Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="05f78-106">It provides full create, read, update, and delete (CRUD) operations from Dataverse and Microsoft Power Platform.</span></span> <span data-ttu-id="05f78-107">A virtuális táblák adatait a Dataverse tárolja, hanem az alkalmazás-adatbázis.</span><span class="sxs-lookup"><span data-stu-id="05f78-107">The data for virtual tables isn't stored in Dataverse, but in the application database.</span></span>

<span data-ttu-id="05f78-108">A HR-entitásokon, Dataverse segítségével végrehajtandó CRUD-műveletek engedélyezéséhez virtuális táblákként elérhetővé kell tennie az entitásokat a következőben: Dataverse.</span><span class="sxs-lookup"><span data-stu-id="05f78-108">To enable CRUD operations on Human Resources entities from Dataverse, you must make the entities available as virtual tables in Dataverse.</span></span> <span data-ttu-id="05f78-109">Ezáltal CRUD-műveleteket hajthat végre Dataverse és Microsoft Power Platform segítségével a HR-ben található adatokon.</span><span class="sxs-lookup"><span data-stu-id="05f78-109">This lets you perform CRUD operations from Dataverse and Microsoft Power Platform on data that's in Human Resources.</span></span> <span data-ttu-id="05f78-110">A műveletek támogatják továbbá a HR teljes üzleti logikájának érvényesülését, hogy az adatok épsége biztosított legyen az adatoknak az entitásokba írásakor.</span><span class="sxs-lookup"><span data-stu-id="05f78-110">The operations also support the full business logic validations of Human Resources to ensure data integrity when writing data to the entities.</span></span>

> [!NOTE]
> <span data-ttu-id="05f78-111">A Human Resources entitások Dataverse-tábláknak felelnek meg.</span><span class="sxs-lookup"><span data-stu-id="05f78-111">Human Resources entities correspond to Dataverse tables.</span></span> <span data-ttu-id="05f78-112">A Dataverse (a korábbi Common Data Service) rendszer kapcsolatos további tudnivalókat és a terminológiai frissítéseket lásd: [Mi a Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)</span><span class="sxs-lookup"><span data-stu-id="05f78-112">For more information about Dataverse (formerly Common Data Service) and terminology updates, see [What is Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)</span></span>

## <a name="available-virtual-tables-for-human-resources"></a><span data-ttu-id="05f78-113">A Human Resources számára elérhető virtuális táblák</span><span class="sxs-lookup"><span data-stu-id="05f78-113">Available virtual tables for Human Resources</span></span>

<span data-ttu-id="05f78-114">A HR-ben található összes Open Data Protocol (OData) entitások virtuális táblákként elérhetők a Dataverse rendszerben.</span><span class="sxs-lookup"><span data-stu-id="05f78-114">All Open Data Protocol (OData) entities in Human Resources are available as virtual tables in Dataverse.</span></span> <span data-ttu-id="05f78-115">Ezek itt is elérhetők: Power Platform.</span><span class="sxs-lookup"><span data-stu-id="05f78-115">They're also available in Power Platform.</span></span> <span data-ttu-id="05f78-116">Mostantól a teljes CRUD-funkcionalitással hozhat létre alkalmazásokat és élményeket közvetlenül a HR-től származó adatokkal – mindezt anélkül, hogy az adatokat a Dataverse-be kellene másolni vagy azzal szinkronizálni kellene.</span><span class="sxs-lookup"><span data-stu-id="05f78-116">You can now build apps and experiences with data directly from Human Resources with full CRUD capability, without copying or synchronizing data to Dataverse.</span></span> <span data-ttu-id="05f78-117">A Power Apps portálok segítségével külső webhelyeket is létrehozhat, amelyekkel együttműködési forgatókönyvek alakíthatók ki a HR-en belüli üzleti folyamatokhoz.</span><span class="sxs-lookup"><span data-stu-id="05f78-117">You can use Power Apps portals to build external-facing websites that enable collaboration scenarios for business processes in Human Resources.</span></span>

<span data-ttu-id="05f78-118">A [Power Apps](https://make.powerapps.com)-ben megtekintheti a környezetben engedélyezett virtuális táblák listáját, valamint elkezdheti a munkát az táblákon a **Dynamics 365 HR Virtual Tables** megoldásban.</span><span class="sxs-lookup"><span data-stu-id="05f78-118">You can view the list of virtual tables enabled in the environment, and begin working with the tables in [Power Apps](https://make.powerapps.com), in the **Dynamics 365 HR Virtual Tables** solution.</span></span>

![Dynamics 365 HR Virtual Tables a Power Apps rendszerben](./media/hr-admin-integration-virtual-entities-power-apps.jpg)

## <a name="virtual-tables-versus-native-tables"></a><span data-ttu-id="05f78-120">Virtuális táblák és natív táblák</span><span class="sxs-lookup"><span data-stu-id="05f78-120">Virtual tables versus native tables</span></span>

<span data-ttu-id="05f78-121">A HR-hez tartozó virtuális táblák nem azonosak a HR számára létrehozott natív Dataverse-táblákkal.</span><span class="sxs-lookup"><span data-stu-id="05f78-121">Virtual tables for Human Resources aren't the same as the native Dataverse tables created for Human Resources.</span></span> 

<span data-ttu-id="05f78-122">A HR-hez tartozó natív táblákat külön hozzák létre és kezelik a Dataverse szolgáltatáson belüli közös humántőke-menedzsment megoldásban.</span><span class="sxs-lookup"><span data-stu-id="05f78-122">The native tables for Human Resources are generated separately and maintained in the HCM Common solution in Dataverse.</span></span> <span data-ttu-id="05f78-123">A natív táblák esetén az adatok tárolása a Dataverse szolgáltatásban történik, és szinkronizálni kell őket a HR alkalmazás-adatbázisával.</span><span class="sxs-lookup"><span data-stu-id="05f78-123">With native tables, the data is stored in Dataverse and requires synchronization with the Human Resources application database.</span></span>

> [!NOTE]
> <span data-ttu-id="05f78-124">A HR-hez tartozó natív Dataverse-táblák listájához lásd: [Dataverse-táblák](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).</span><span class="sxs-lookup"><span data-stu-id="05f78-124">For a list of the native Dataverse tables for Human Resources, see [Dataverse tables](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).</span></span>

## <a name="setup"></a><span data-ttu-id="05f78-125">Beállítás</span><span class="sxs-lookup"><span data-stu-id="05f78-125">Setup</span></span>

<span data-ttu-id="05f78-126">A következő lépésekkel engedélyezheti a virtuális táblák telepítését a környezetben.</span><span class="sxs-lookup"><span data-stu-id="05f78-126">Follow these setup steps to enable virtual tables in your environment.</span></span>

### <a name="enable-virtual-tables-in-human-resources"></a><span data-ttu-id="05f78-127">Virtuális táblák engedélyezése a Human Resources alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="05f78-127">Enable virtual tables in Human Resources</span></span>

<span data-ttu-id="05f78-128">Először engedélyeznie kell a virtuális táblákat a **Szolgáltatáskezelés** munkaterületen.</span><span class="sxs-lookup"><span data-stu-id="05f78-128">First, you must enable virtual tables in the **Feature management** workspace.</span></span>

1. <span data-ttu-id="05f78-129">A Human Resources alkalmazásban válassza a **Rendszerfelügyelet** elemet.</span><span class="sxs-lookup"><span data-stu-id="05f78-129">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="05f78-130">Válassza ki a **Funkció kezelése** csempét.</span><span class="sxs-lookup"><span data-stu-id="05f78-130">Select the **Feature management** tile.</span></span>

3. <span data-ttu-id="05f78-131">Válassza a **Virtuális táblák támogatása a HR számára a Dataverse rendszerben** elemet, majd az **Engedélyezés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="05f78-131">Select **Virtual table support for HR in Dataverse**, and then select **Enable**.</span></span>

<span data-ttu-id="05f78-132">A funkciók aktiválásával és letiltásával kapcsolatos további részletekért tekintse meg a [Szolgáltatások kezelése](hr-admin-manage-features.md) oldalt.</span><span class="sxs-lookup"><span data-stu-id="05f78-132">For more information about enabling and disabling features, see [Manage features](hr-admin-manage-features.md).</span></span>

### <a name="register-the-app-in-microsoft-azure"></a><span data-ttu-id="05f78-133">Regisztrálja az alkalmazást a Microsoft Azure-ban</span><span class="sxs-lookup"><span data-stu-id="05f78-133">Register the app in Microsoft Azure</span></span>

<span data-ttu-id="05f78-134">Először az Azure Portal webhelyen kell regisztrálnia a Human Resources példányt, hogy a Microsoft identitásplatform hitelesítési és engedélyezési szolgáltatásokat nyújthasson az alkalmazás és a felhasználók számára.</span><span class="sxs-lookup"><span data-stu-id="05f78-134">You must register your Human Resources instance in the Azure portal so the Microsoft identity platform can provide authentication and authorization services for the app and users.</span></span> <span data-ttu-id="05f78-135">Az alkalmazások Azure-ban való regisztrálásával kapcsolatos további tudnivalókat lásd: [Rövid útmutató: Alkalmazások regisztrálása a Microsoft Identity platformmal](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span><span class="sxs-lookup"><span data-stu-id="05f78-135">For more information about registering apps in Azure, see [Quickstart: Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>

1. <span data-ttu-id="05f78-136">Nyissa meg a [Microsoft Azure portált](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="05f78-136">Open the [Microsoft Azure portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="05f78-137">Az Azure-szolgáltatások listáján válassza ki az **Alkalmazásregisztrációk** elemet.</span><span class="sxs-lookup"><span data-stu-id="05f78-137">In the Azure services list, select **App registrations**.</span></span>

3. <span data-ttu-id="05f78-138">Válassza ki az **Új regisztráció** elemet.</span><span class="sxs-lookup"><span data-stu-id="05f78-138">Select **New registration**.</span></span>

4. <span data-ttu-id="05f78-139">A **Név** mezőbe írja be az alkalmazás ismertető nevét.</span><span class="sxs-lookup"><span data-stu-id="05f78-139">In the **Name** field, enter a descriptive name for the app.</span></span> <span data-ttu-id="05f78-140">Például **Dynamics 365 Human Resources Virtuális táblák**.</span><span class="sxs-lookup"><span data-stu-id="05f78-140">For example, **Dynamics 365 Human Resources Virtual Tables**.</span></span>

5. <span data-ttu-id="05f78-141">Az **Átirányítási URL-cím** mezőben adja meg a saját HR-instancia URL-névterét.</span><span class="sxs-lookup"><span data-stu-id="05f78-141">In the **Redirect URI** field, enter the namespace URL of your instance of Human Resources.</span></span>

6. <span data-ttu-id="05f78-142">Válassza a **Regisztrálás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="05f78-142">Select **Register**.</span></span>

7. <span data-ttu-id="05f78-143">A regisztráció befejezését követően az Azure Portal megjeleníti az alkalmazás regisztrációjának **Áttekintés** ablaka, amelyen látható az **alkalmazás (ügyfél) azonosítója**.</span><span class="sxs-lookup"><span data-stu-id="05f78-143">When registration completes, the Azure portal displays the app registration's **Overview** pane, which includes its **Application (client) ID**.</span></span> <span data-ttu-id="05f78-144">Ekkor jegyezze fel az **alkalmazás (ügyfél) azonosítóját**.</span><span class="sxs-lookup"><span data-stu-id="05f78-144">Take note of the **Application (client) ID** at this time.</span></span> <span data-ttu-id="05f78-145">Ezt az információt akkor kell megadnia, amikor a [virtuális tábla adatforrását konfigurálja](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span><span class="sxs-lookup"><span data-stu-id="05f78-145">You'll enter this information when you [Configure the virtual table data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span></span>

8. <span data-ttu-id="05f78-146">A bal oldali navigációs ablakban válassza ki a **Tanúsítványok és titkos kódok** elemet.</span><span class="sxs-lookup"><span data-stu-id="05f78-146">In the left navigation pane, select **Certificates and secrets**.</span></span>

9. <span data-ttu-id="05f78-147">Az oldal **Ügyfél titkai** részén válassza az **Új ügyféltitok** elemet.</span><span class="sxs-lookup"><span data-stu-id="05f78-147">In the **Client secrets** section of the page, select **New client secret**.</span></span>

10. <span data-ttu-id="05f78-148">Adjon meg egy leírást, válassza ki az időtartamot, majd válassza a **Hozzáadás** elemet.</span><span class="sxs-lookup"><span data-stu-id="05f78-148">Provide a description, select a duration, and select **Add**.</span></span>

11. <span data-ttu-id="05f78-149">Rögzítse a titok értékét.</span><span class="sxs-lookup"><span data-stu-id="05f78-149">Record the secret's value.</span></span> <span data-ttu-id="05f78-150">Ezt az információt akkor kell megadnia, amikor a [virtuális tábla adatforrását konfigurálja](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span><span class="sxs-lookup"><span data-stu-id="05f78-150">You'll enter this information when you [Configure the virtual table data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="05f78-151">A titok értéket ekkor feltétlenül rögzítse.</span><span class="sxs-lookup"><span data-stu-id="05f78-151">Be sure to take note of the secret's value at this time.</span></span> <span data-ttu-id="05f78-152">A titok az oldal elhagyása után már többé nem fog megjelenni.</span><span class="sxs-lookup"><span data-stu-id="05f78-152">The secret is never displayed again after you leave this page.</span></span>

### <a name="install-the-dynamics-365-hr-virtual-table-app"></a><span data-ttu-id="05f78-153">A Dynamics 365 HR Virtual Table alkalmazás telepítése</span><span class="sxs-lookup"><span data-stu-id="05f78-153">Install the Dynamics 365 HR Virtual Table app</span></span>

<span data-ttu-id="05f78-154">Telepítse a Dynamics 365 HR Virtual Table alkalmazást a saját Power Apps környezetében, hogy a virtuális tábla megoldáscsomagot telepíthesse a Dataverse szolgáltatáshoz.</span><span class="sxs-lookup"><span data-stu-id="05f78-154">Install the Dynamics 365 HR Virtual Table app in your Power Apps environment to deploy the virtual table solution package to Dataverse.</span></span>

1. <span data-ttu-id="05f78-155">Nyissa meg a [Power Platform felügyeleti központot](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="05f78-155">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="05f78-156">A **Környezetek** listán válassza ki a saját HR-instanciájához társított Power Apps környezetet.</span><span class="sxs-lookup"><span data-stu-id="05f78-156">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="05f78-157">Az oldal **Erőforrások** részében válassza ki a **Dynamics 365 alkalmazások** elemet.</span><span class="sxs-lookup"><span data-stu-id="05f78-157">In the **Resources** section of the page, select **Dynamics 365 apps**.</span></span>

4. <span data-ttu-id="05f78-158">Válassza ki az **Alkalmazás telepítése** műveletet.</span><span class="sxs-lookup"><span data-stu-id="05f78-158">Select the **Install app** action.</span></span>

5. <span data-ttu-id="05f78-159">Válassza ki a **Dynamics 365 HR Virtual Table** elemet, majd pedig a **Tovább** elemet.</span><span class="sxs-lookup"><span data-stu-id="05f78-159">Select **Dynamics 365 HR Virtual Table**, and select **Next**.</span></span>

6. <span data-ttu-id="05f78-160">Olvassa át, majd pedig kijelöléssel jelezze, hogy elfogadja-e a szolgáltatási feltételeket.</span><span class="sxs-lookup"><span data-stu-id="05f78-160">Review and mark to agree to the terms of service.</span></span>

7. <span data-ttu-id="05f78-161">Válassza a **Telepítés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="05f78-161">Select **Install**.</span></span>

<span data-ttu-id="05f78-162">A telepítés néhány percet igényel.</span><span class="sxs-lookup"><span data-stu-id="05f78-162">The install takes a few minutes.</span></span> <span data-ttu-id="05f78-163">Befejezéskor folytassa a következő lépésekkel.</span><span class="sxs-lookup"><span data-stu-id="05f78-163">When it completes, continue to the next steps.</span></span>

![A Dynamics 365 HR Virtual Table alkalmazás telepítése a Power Platform felügyeleti központból](./media/hr-admin-integration-virtual-entities-power-platform-install.jpg)

### <a name="configure-the-virtual-table-data-source"></a><span data-ttu-id="05f78-165">A virtuális tábla adatforrásának konfigurálása</span><span class="sxs-lookup"><span data-stu-id="05f78-165">Configure the virtual table data source</span></span> 

<span data-ttu-id="05f78-166">A következő lépésben a virtuális tábla adatforrásának a Power Apps környezetben történő konfigurálása történik.</span><span class="sxs-lookup"><span data-stu-id="05f78-166">The next step is to configure the virtual table data source in the Power Apps environment.</span></span> 

1. <span data-ttu-id="05f78-167">Nyissa meg a [Power Platform felügyeleti központot](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="05f78-167">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="05f78-168">A **Környezetek** listán válassza ki a saját HR-instanciájához társított Power Apps környezetet.</span><span class="sxs-lookup"><span data-stu-id="05f78-168">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="05f78-169">Válassza ki a **Környezet URL-je** elemet az oldal **Részletek** részében.</span><span class="sxs-lookup"><span data-stu-id="05f78-169">Select the **Environment URL** in the **Details** section of the page.</span></span>

4. <span data-ttu-id="05f78-170">A **Megoldás-állapotfelügyeleti központ** felületén válassza ki az alkalmazásoldal jobb felső sarkában található **Összetett keresés** ikont.</span><span class="sxs-lookup"><span data-stu-id="05f78-170">In the **Solution Health Hub**, select the **Advanced Find** icon in the top right of the application page.</span></span>

5. <span data-ttu-id="05f78-171">Az **Összetett keresés** oldalon, az **Elem keresése** legördülő listán válassza ki a **Finance and Operations virtuális adatforrás konfigurációi** elemet.</span><span class="sxs-lookup"><span data-stu-id="05f78-171">On the **Advanced Find** page, in the **Look for** dropdown list, select **Finance and Operations Virtual Data Source Configurations**.</span></span>

6. <span data-ttu-id="05f78-172">Válassza az **Eredmények** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="05f78-172">Select **Results**.</span></span>

7. <span data-ttu-id="05f78-173">Válassza ki a **Microsoft HR-adatforrás** rekordot.</span><span class="sxs-lookup"><span data-stu-id="05f78-173">Select the **Microsoft HR Data Source** record.</span></span>

8. <span data-ttu-id="05f78-174">Adja meg az adatforrás-konfigurációhoz szükséges adatokat:</span><span class="sxs-lookup"><span data-stu-id="05f78-174">Enter the required information for the data source configuration:</span></span>

   - <span data-ttu-id="05f78-175">**Cél URL**: A saját HR-névtér URL-je.</span><span class="sxs-lookup"><span data-stu-id="05f78-175">**Target URL**: The URL of your Human Resources namespace.</span></span> <span data-ttu-id="05f78-176">A cél URL formátuma:</span><span class="sxs-lookup"><span data-stu-id="05f78-176">The format of the target URL is:</span></span>
     
     <span data-ttu-id="05f78-177">https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/</span><span class="sxs-lookup"><span data-stu-id="05f78-177">https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/</span></span>

     <span data-ttu-id="05f78-178">Példa:</span><span class="sxs-lookup"><span data-stu-id="05f78-178">For example:</span></span>
     
     `https://aos.rts-sf-5ea54e35c68-westus2.hr.talent.dynamics.com/namespaces/49d24c565-8f4d-4891-b174-bf83d948ed0c/`

     >[!NOTE]
     ><span data-ttu-id="05f78-179">Ügyeljen arra, hogy az URL-cím végén a „**/**” karakter is szerepeljen a hibák elkerülése érdekében.</span><span class="sxs-lookup"><span data-stu-id="05f78-179">Be sure to include the "**/**" character at the end of the URL to avoid receiving an error.</span></span>

   - <span data-ttu-id="05f78-180">**Bérlő azonosítója**: az Azure Active Directory (Azure AD) bérlő azonosítója.</span><span class="sxs-lookup"><span data-stu-id="05f78-180">**Tenant ID**: The Azure Active Directory (Azure AD) tenant ID.</span></span>

   - <span data-ttu-id="05f78-181">**AAD-alkalmazásazonosító**: Az Microsoft Azure portálon regisztrált alkalmazáshoz létrehozott alkalmazásazonosító (ügyfél-azonosító).</span><span class="sxs-lookup"><span data-stu-id="05f78-181">**AAD Application ID**: The application (client) ID created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="05f78-182">Ezt az információt korábban, az [Alkalmazás regisztrálása a Microsoft Azure-ban](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure) lépésben kapta meg.</span><span class="sxs-lookup"><span data-stu-id="05f78-182">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>

   - <span data-ttu-id="05f78-183">**AAD-alkalmazástitok**: A Microsoft Azure portálon regisztrált alkalmazáshoz létrehozott ügyféltitok.</span><span class="sxs-lookup"><span data-stu-id="05f78-183">**AAD Application Secret**: The client secret created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="05f78-184">Ezt az információt korábban, az [Alkalmazás regisztrálása a Microsoft Azure-ban](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure) lépésben kapta meg.</span><span class="sxs-lookup"><span data-stu-id="05f78-184">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>

   ![Microsoft HR-adatforrás](./media/hr-admin-integration-virtual-entities-hr-data-source.jpg)

9. <span data-ttu-id="05f78-186">Válassza ki a **Mentés és bezárás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="05f78-186">Select **Save & Close**.</span></span>

### <a name="grant-app-permissions-in-human-resources"></a><span data-ttu-id="05f78-187">Alkalmazásengedélyek kiosztása a HR-ben</span><span class="sxs-lookup"><span data-stu-id="05f78-187">Grant app permissions in Human Resources</span></span>

<span data-ttu-id="05f78-188">Engedélyek kiosztása a HR-ben lévő két Azure AD-alkalmazáshoz:</span><span class="sxs-lookup"><span data-stu-id="05f78-188">Grant permissions for the two Azure AD applications in Human Resources:</span></span>

- <span data-ttu-id="05f78-189">A Microsoft Azure portálon a bérlője számára létrehozott alkalmazás</span><span class="sxs-lookup"><span data-stu-id="05f78-189">The app created for your tenant in the Microsoft Azure portal</span></span>
- <span data-ttu-id="05f78-190">A Dynamics 365 HR Virtual Table alkalmazás a Power Apps környezetben telepítve</span><span class="sxs-lookup"><span data-stu-id="05f78-190">The Dynamics 365 HR Virtual Table app installed in the Power Apps environment</span></span> 

1. <span data-ttu-id="05f78-191">A HR-modulban nyissa meg az **Azure Active Directory-alkalmazások** oldalt.</span><span class="sxs-lookup"><span data-stu-id="05f78-191">In Human Resources, open the **Azure Active Directory applications** page.</span></span>

2. <span data-ttu-id="05f78-192">Válassza ki az **Új** lehetőséget egy új alkalmazásrekord létrehozásához:</span><span class="sxs-lookup"><span data-stu-id="05f78-192">Select **New** to create a new application record:</span></span>

    - <span data-ttu-id="05f78-193">Az **Ügyfél-azonosító** mezőbe írja be a Microsoft Azure portálon regisztrált alkalmazás ügyfél-azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="05f78-193">In the **Client ID** field, enter the client ID of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="05f78-194">A **Név** mezőbe írja be a Microsoft Azure portálon regisztrált alkalmazás nevét.</span><span class="sxs-lookup"><span data-stu-id="05f78-194">In the **Name** field, enter the name of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="05f78-195">A **Felhasználóazonosító** mezőben válassza ki azt a felhasználót, aki rendszergazdai jogokkal rendelkezik a HR-modulban és a Power Apps környezetben.</span><span class="sxs-lookup"><span data-stu-id="05f78-195">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

3. <span data-ttu-id="05f78-196">Válassza ki az **Új** lehetőséget egy második alkalmazásrekord létrehozásához:</span><span class="sxs-lookup"><span data-stu-id="05f78-196">Select **New** to create a second application record:</span></span>

    - <span data-ttu-id="05f78-197">**Ügyfél-azonosító**: f9be0c49-aa22-4ec6-911a-c5da515226ff</span><span class="sxs-lookup"><span data-stu-id="05f78-197">**Client Id**: f9be0c49-aa22-4ec6-911a-c5da515226ff</span></span>
    - <span data-ttu-id="05f78-198">**Név**: Dynamics 365 HR Virtual Table</span><span class="sxs-lookup"><span data-stu-id="05f78-198">**Name**: Dynamics 365 HR Virtual Table</span></span>
    - <span data-ttu-id="05f78-199">A **Felhasználóazonosító** mezőben válassza ki azt a felhasználót, aki rendszergazdai jogokkal rendelkezik a HR-modulban és a Power Apps környezetben.</span><span class="sxs-lookup"><span data-stu-id="05f78-199">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

## <a name="generate-virtual-tables"></a><span data-ttu-id="05f78-200">Virtuális táblák létrehozása</span><span class="sxs-lookup"><span data-stu-id="05f78-200">Generate virtual tables</span></span>

<span data-ttu-id="05f78-201">A telepítés befejezését követően kiválaszthatja, hogy mely virtuális táblákat szeretné létrehozni és engedélyezni a saját Dataverse-példányában.</span><span class="sxs-lookup"><span data-stu-id="05f78-201">When setup completes, you can select the virtual tables you want to generate and enable in your Dataverse instance.</span></span>

1. <span data-ttu-id="05f78-202">A HR-modulban nyissa meg a **Dataverse integrációja** oldalt.</span><span class="sxs-lookup"><span data-stu-id="05f78-202">In Human Resources, open the **Dataverse integration** page.</span></span>

2. <span data-ttu-id="05f78-203">Válassza ki a **Virtuális táblák** lapot.</span><span class="sxs-lookup"><span data-stu-id="05f78-203">Select the **Virtual tables** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="05f78-204">A **Virtuális táblák engedélyezése** váltógombot a rendszer automatikusan az **Igen** értékre állítja, ha befejezte a szükséges beállításokat.</span><span class="sxs-lookup"><span data-stu-id="05f78-204">The **Enable virtual tables** toggle will be set to **Yes** automatically when all required setup has been completed.</span></span> <span data-ttu-id="05f78-205">Ha a váltógomb értéke **Nem**, tekintse át a dokumentum előző szakaszaiban ismertetett lépéseket, és győződjön meg arról, hogy minden előfeltétel-beállítást befejezett.</span><span class="sxs-lookup"><span data-stu-id="05f78-205">If the toggle is set to **No**, review the steps in previous sections of this document to ensure all prerequisite setup is completed.</span></span>

3. <span data-ttu-id="05f78-206">Válassza ki a Dataverse szolgáltatásban létrehozni kívánt táblát vagy táblákat.</span><span class="sxs-lookup"><span data-stu-id="05f78-206">Select the table or tables you want to generate in Dataverse.</span></span>

4. <span data-ttu-id="05f78-207">Válassza a **Létrehozás/frissítés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="05f78-207">Select **Generate/refresh**.</span></span>

![Dataverse-integráció](./media/hr-admin-integration-common-data-service-integration.jpg)

## <a name="check-table-generation-status"></a><span data-ttu-id="05f78-209">Táblagenerálási állapot ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="05f78-209">Check table generation status</span></span>

<span data-ttu-id="05f78-210">A virtuális táblák a Dataverse szolgáltatásban aszinkron háttérfolyamatok során jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="05f78-210">Virtual tables are generated in Dataverse through an asynchronous background process.</span></span> <span data-ttu-id="05f78-211">A folyamat frissítései a műveleti központban láthatók.</span><span class="sxs-lookup"><span data-stu-id="05f78-211">Updates on the process display in the action center.</span></span> <span data-ttu-id="05f78-212">A folyamatra vonatkozó részletek, többek között a hibanaplók, a **Folyamatok automatizálása** oldalon láthatók.</span><span class="sxs-lookup"><span data-stu-id="05f78-212">Details on the process, including error logs, appear in the **Process automations** page.</span></span>

1. <span data-ttu-id="05f78-213">Az Emberi Erőforrások modulban nyissa meg **Folyamatok automatizálása** lapot.</span><span class="sxs-lookup"><span data-stu-id="05f78-213">In Human Resources, open the **Process automations** page.</span></span>

2. <span data-ttu-id="05f78-214">Válassza ki a **Háttérfolyamatok** lapot.</span><span class="sxs-lookup"><span data-stu-id="05f78-214">Select the **Background processes** tab.</span></span>

3. <span data-ttu-id="05f78-215">Válassza ki a **Virtuális tábla lekérdezése – aszinkron háttérfolyamat** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="05f78-215">Select **Virtual table poll async operation background process**.</span></span>

4. <span data-ttu-id="05f78-216">Válassza ki a **Legutóbbi eredmények megtekintése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="05f78-216">Select **View most recent results**.</span></span>

<span data-ttu-id="05f78-217">A kicsúszó ablaktábla megjeleníti a folyamat legutóbbi végrehajtásának eredményeit.</span><span class="sxs-lookup"><span data-stu-id="05f78-217">The slideout pane displays the most recent execution results for the process.</span></span> <span data-ttu-id="05f78-218">Megtekintheti a folyamat naplóját, többek között a Dataverse szolgáltatásból visszaküldött hibákat is.</span><span class="sxs-lookup"><span data-stu-id="05f78-218">You can view the log for the process, including any errors returned from Dataverse.</span></span>

## <a name="see-also"></a><span data-ttu-id="05f78-219">Lásd még</span><span class="sxs-lookup"><span data-stu-id="05f78-219">See also</span></span>

[<span data-ttu-id="05f78-220">Mi az a Dataverse?</span><span class="sxs-lookup"><span data-stu-id="05f78-220">What is Dataverse?</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)<br>
[<span data-ttu-id="05f78-221">Táblák a Dataverse-rendszerben</span><span class="sxs-lookup"><span data-stu-id="05f78-221">Tables in Dataverse</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/entity-overview)<br>
[<span data-ttu-id="05f78-222">Táblakapcsolatok áttekintése</span><span class="sxs-lookup"><span data-stu-id="05f78-222">Table relationships overview</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/relationships-overview)<br>
[<span data-ttu-id="05f78-223">Külső adatforrásból származó adatokat tartalmazó virtuális táblák létrehozása és szerkesztése</span><span class="sxs-lookup"><span data-stu-id="05f78-223">Create and edit virtual tables that contain data from an external data source</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/create-edit-virtual-entities)<br>
[<span data-ttu-id="05f78-224">Mik azok a Power Apps portálok?</span><span class="sxs-lookup"><span data-stu-id="05f78-224">What is Power Apps portals?</span></span>](https://docs.microsoft.com/powerapps/maker/portals/overview)<br>
[<span data-ttu-id="05f78-225">Alkalmazások Power Apps-ben való létrehozásának áttekintése</span><span class="sxs-lookup"><span data-stu-id="05f78-225">Overview of creating apps in Power Apps</span></span>](https://docs.microsoft.com/powerapps/maker/)


[!INCLUDE[footer-include](../includes/footer-banner.md)]