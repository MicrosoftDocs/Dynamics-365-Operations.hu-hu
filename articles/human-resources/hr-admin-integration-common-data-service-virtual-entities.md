---
title: Common Data Service-virtuális entitások konfigurálása
description: Ez a témakör azt mutatja be, hogyan lehet beállítani a virtuális entitásokat a Dynamics 365 Human Resources esetén. Meglévő virtuális entitások létrehozása és frissítése, valamint létrehozott és elérhető entitások analizálása.
author: andreabichsel
manager: tfehr
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
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
ms.openlocfilehash: 0d6f79ea569a7a9b0d25e73e8666bf9ba19095d0
ms.sourcegitcommit: a8665c47696028d371cdc4671db1fd8fcf9e1088
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/21/2020
ms.locfileid: "4058154"
---
# <a name="configure-common-data-service-virtual-entities"></a><span data-ttu-id="2e86b-104">Common Data Service-virtuális entitások konfigurálása</span><span class="sxs-lookup"><span data-stu-id="2e86b-104">Configure Common Data Service virtual entities</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="2e86b-105">A Dynamics 365 Human Resources egy virtuális adatforrás a következőben: Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="2e86b-105">Dynamics 365 Human Resources is a virtual data source in Common Data Service.</span></span> <span data-ttu-id="2e86b-106">Teljes körű létrehozási, olvasási, frissítési és törlési (CRUD) műveletek végrehajtását teszi lehetővé a következőkből: Common Data Service és Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="2e86b-106">It provides full create, read, update, and delete (CRUD) operations from Common Data Service and Microsoft Power Platform.</span></span> <span data-ttu-id="2e86b-107">A virtuális entitások adatait a Common Data Service tárolja, hanem az alkalmazás-adatbázis.</span><span class="sxs-lookup"><span data-stu-id="2e86b-107">The data for virtual entities isn't stored in Common Data Service, but in the application database.</span></span> 

<span data-ttu-id="2e86b-108">A HR-entitásokon, Common Data Service segítségével végrehajtandó CRUD-műveletek engedélyezéséhez virtuális entitásokként elérhetővé kell tennie az entitásokat a következőben: Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="2e86b-108">To enable CRUD operations on Human Resources entities from Common Data Service, you must make the entities available as virtual entities in Common Data Service.</span></span> <span data-ttu-id="2e86b-109">Ezáltal CRUD-műveleteket hajthat végre Common Data Service és Microsoft Power Platform segítségével a HR-ben található adatokon.</span><span class="sxs-lookup"><span data-stu-id="2e86b-109">This lets you perform CRUD operations from Common Data Service and Microsoft Power Platform on data that's in Human Resources.</span></span> <span data-ttu-id="2e86b-110">A műveletek támogatják továbbá a HR teljes üzleti logikájának érvényesülését, hogy az adatok épsége biztosított legyen az adatoknak az entitásokba írásakor.</span><span class="sxs-lookup"><span data-stu-id="2e86b-110">The operations also support the full business logic validations of Human Resources to ensure data integrity when writing data to the entities.</span></span>

## <a name="available-virtual-entities-for-human-resources"></a><span data-ttu-id="2e86b-111">A HR számára elérhető virtuális entitások</span><span class="sxs-lookup"><span data-stu-id="2e86b-111">Available virtual entities for Human Resources</span></span>

<span data-ttu-id="2e86b-112">A HR-ben található összes Open Data Protocol (OData) entitás virtuális entitásként elérhető a következőben: Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="2e86b-112">All Open Data Protocol (OData) entities in Human Resources are available as virtual entities in Common Data Service.</span></span> <span data-ttu-id="2e86b-113">Ezek itt is elérhetők: Power Platform.</span><span class="sxs-lookup"><span data-stu-id="2e86b-113">They're also available in Power Platform.</span></span> <span data-ttu-id="2e86b-114">Mostantól a teljes CRUD-funkcionalitással hozhat létre alkalmazásokat és élményeket közvetlenül a HR-től származó adatokkal – mindezt anélkül, hogy az adatokat a Common Data Service-be kellene másolni vagy azzal szinkronizálni kellene.</span><span class="sxs-lookup"><span data-stu-id="2e86b-114">You can now build apps and experiences with data directly from Human Resources with full CRUD capability, without copying or synchronizing data to Common Data Service.</span></span> <span data-ttu-id="2e86b-115">A Power Apps portálok segítségével külső webhelyeket is létrehozhat, amelyekkel együttműködési forgatókönyvek alakíthatók ki a HR-en belüli üzleti folyamatokhoz.</span><span class="sxs-lookup"><span data-stu-id="2e86b-115">You can use Power Apps portals to build external-facing websites that enable collaboration scenarios for business processes in Human Resources.</span></span>

<span data-ttu-id="2e86b-116">A [Power Apps](https://make.powerapps.com)-ben megtekintheti a környezetben engedélyezett virtuális entitások listáját, valamint elkezdheti a munkát az entitásokon a **Dynamics 365 HR Virtual Entities** megoldásban.</span><span class="sxs-lookup"><span data-stu-id="2e86b-116">You can view the list of virtual entities enabled in the environment, and begin working with the entities in [Power Apps](https://make.powerapps.com), in the **Dynamics 365 HR Virtual Entities** solution.</span></span>

![Dynamics 365 HR virtuális entitások a következőben: Power Apps](./media/hr-admin-integration-virtual-entities-power-apps.jpg)

## <a name="virtual-entities-versus-natural-entities"></a><span data-ttu-id="2e86b-118">Virtuális entitások kontra természetes entitások</span><span class="sxs-lookup"><span data-stu-id="2e86b-118">Virtual entities versus natural entities</span></span>

<span data-ttu-id="2e86b-119">A HR-hez tartozó virtuális entitások nem azonosak a HR számára létrehozott természetes Common Data Service entitásokkal.</span><span class="sxs-lookup"><span data-stu-id="2e86b-119">Virtual entities for Human Resources aren't the same as the natural Common Data Service entities created for Human Resources.</span></span> <span data-ttu-id="2e86b-120">A HR-hez tartozó természetes entitásokat külön hozzák létre és kezelik a Common Data Service szolgáltatáson belüli közös humántőke-menedzsment megoldásban.</span><span class="sxs-lookup"><span data-stu-id="2e86b-120">The natural entities for Human Resources are generated separately and maintained in the HCM Common solution in Common Data Service.</span></span> <span data-ttu-id="2e86b-121">A természetes entitások esetén az adatok a Common Data Service szolgáltatásban tárolódnak, és szinkronizálni kell őket a HR alkalmazás-adatbázisával.</span><span class="sxs-lookup"><span data-stu-id="2e86b-121">With natural entities, the data is stored in Common Data Service and requires synchronization with the Human Resources application database.</span></span>

> [!NOTE]
> <span data-ttu-id="2e86b-122">A HR-hez tartozó természetes Common Data Service entitások listájához lásd a [Common Data Service entitásokat](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).</span><span class="sxs-lookup"><span data-stu-id="2e86b-122">For a list of the natural Common Data Service entities for Human Resources, see [Common Data Service entities](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).</span></span>

## <a name="setup"></a><span data-ttu-id="2e86b-123">Beállítás</span><span class="sxs-lookup"><span data-stu-id="2e86b-123">Setup</span></span>

<span data-ttu-id="2e86b-124">A következő lépésekkel engedélyezheti a virtuális entitások telepítését a környezetben.</span><span class="sxs-lookup"><span data-stu-id="2e86b-124">Follow these setup steps to enable virtual entities in your environment.</span></span> 

### <a name="register-the-app-in-microsoft-azure"></a><span data-ttu-id="2e86b-125">Regisztrálja az alkalmazást a Microsoft Azure-ban</span><span class="sxs-lookup"><span data-stu-id="2e86b-125">Register the app in Microsoft Azure</span></span>

<span data-ttu-id="2e86b-126">Először az Azure Portal webhelyen kell regisztrálnia az alkalmazást, hogy a Microsoft Identity platform hitelesítési és engedélyezési szolgáltatásokat nyújthasson az alkalmazás és a felhasználók számára.</span><span class="sxs-lookup"><span data-stu-id="2e86b-126">First, you need to register the app in the Azure portal so the Microsoft identity platform can provide authentication and authorization services for the app and users.</span></span> <span data-ttu-id="2e86b-127">Az alkalmazások Azure-ban való regisztrálásával kapcsolatos további tudnivalókat lásd: [Rövid útmutató: Alkalmazások regisztrálása a Microsoft Identity platformmal](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span><span class="sxs-lookup"><span data-stu-id="2e86b-127">For more information about registering apps in Azure, see [Quickstart: Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>

1. <span data-ttu-id="2e86b-128">Nyissa meg a [Microsoft Azure portált](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="2e86b-128">Open the [Microsoft Azure portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="2e86b-129">Az Azure-szolgáltatások listáján válassza ki az **Alkalmazásregisztrációk** elemet.</span><span class="sxs-lookup"><span data-stu-id="2e86b-129">In the Azure services list, select **App registrations**.</span></span>

3. <span data-ttu-id="2e86b-130">Válassza ki az **Új regisztráció** elemet.</span><span class="sxs-lookup"><span data-stu-id="2e86b-130">Select **New registration**.</span></span>

4. <span data-ttu-id="2e86b-131">A **Név** mezőbe írja be az alkalmazás ismertető nevét.</span><span class="sxs-lookup"><span data-stu-id="2e86b-131">In the **Name** field, enter a descriptive name for the app.</span></span> <span data-ttu-id="2e86b-132">Például **Dynamics 365 Human Resources Virtuális entitások**.</span><span class="sxs-lookup"><span data-stu-id="2e86b-132">For example, **Dynamics 365 Human Resources Virtual Entities**.</span></span>

5. <span data-ttu-id="2e86b-133">Az **Átirányítási URL-cím** mezőben adja meg a saját HR-instancia URL-névterét.</span><span class="sxs-lookup"><span data-stu-id="2e86b-133">In the **Redirect URI** field, enter the namespace URL of your instance of Human Resources.</span></span>

6. <span data-ttu-id="2e86b-134">Válassza a **Regisztrálás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2e86b-134">Select **Register**.</span></span>

7. <span data-ttu-id="2e86b-135">A regisztráció befejezését követően az Azure Portal megjeleníti az alkalmazás regisztrációjának **Áttekintés** ablaka, amelyen látható az **alkalmazás (ügyfél) azonosítója**.</span><span class="sxs-lookup"><span data-stu-id="2e86b-135">When registration completes, the Azure portal displays the app registration's **Overview** pane, which includes its **Application (client) ID**.</span></span> <span data-ttu-id="2e86b-136">Ekkor jegyezze fel az **alkalmazás (ügyfél) azonosítóját**.</span><span class="sxs-lookup"><span data-stu-id="2e86b-136">Take note of the **Application (client) ID** at this time.</span></span> <span data-ttu-id="2e86b-137">Ezt az információt akkor kell megadnia, amikor a [virtuális entitás adatforrását konfigurálja](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span><span class="sxs-lookup"><span data-stu-id="2e86b-137">You'll enter this information when you [Configure the virtual entity data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span></span>

8. <span data-ttu-id="2e86b-138">A bal oldali navigációs ablakban válassza ki a **Tanúsítványok és titkos kódok** elemet.</span><span class="sxs-lookup"><span data-stu-id="2e86b-138">In the left navigation pane, select **Certificates and secrets**.</span></span>

9. <span data-ttu-id="2e86b-139">Az oldal **Ügyfél titkai** részén válassza az **Új ügyféltitok** elemet.</span><span class="sxs-lookup"><span data-stu-id="2e86b-139">In the **Client secrets** section of the page, select **New client secret**.</span></span>

10. <span data-ttu-id="2e86b-140">Adjon meg egy leírást, válassza ki az időtartamot, majd válassza a **Hozzáadás** elemet.</span><span class="sxs-lookup"><span data-stu-id="2e86b-140">Provide a description, select a duration, and select **Add**.</span></span>

11. <span data-ttu-id="2e86b-141">Rögzítse a titok értékét.</span><span class="sxs-lookup"><span data-stu-id="2e86b-141">Record the secret's value.</span></span> <span data-ttu-id="2e86b-142">Ezt az információt akkor kell megadnia, amikor a [virtuális entitás adatforrását konfigurálja](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span><span class="sxs-lookup"><span data-stu-id="2e86b-142">You'll enter this information when you [Configure the virtual entity data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="2e86b-143">A titok értéket ekkor feltétlenül rögzítse.</span><span class="sxs-lookup"><span data-stu-id="2e86b-143">Be sure to take note of the secret's value at this time.</span></span> <span data-ttu-id="2e86b-144">A titok az oldal elhagyása után már többé nem fog megjelenni.</span><span class="sxs-lookup"><span data-stu-id="2e86b-144">The secret is never displayed again after you leave this page.</span></span>

### <a name="install-the-dynamics-365-hr-virtual-entity-app"></a><span data-ttu-id="2e86b-145">A Dynamics 365 HR Virtual Entity alkalmazás telepítése</span><span class="sxs-lookup"><span data-stu-id="2e86b-145">Install the Dynamics 365 HR Virtual Entity app</span></span>

<span data-ttu-id="2e86b-146">Telepítse a Dynamics 365 HR Virtual Entity alkalmazást a saját Power Apps környezetében, hogy a virtuális entitás megoldáscsomagot telepíthesse a Common Data Service szolgáltatáshoz.</span><span class="sxs-lookup"><span data-stu-id="2e86b-146">Install the Dynamics 365 HR Virtual Entity app in your Power Apps environment to deploy the virtual entity solution package to Common Data Service.</span></span>

1. <span data-ttu-id="2e86b-147">Nyissa meg a [Power Platform felügyeleti központot](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="2e86b-147">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="2e86b-148">A **Környezetek** listán válassza ki a saját HR-instanciájához társított Power Apps környezetet.</span><span class="sxs-lookup"><span data-stu-id="2e86b-148">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="2e86b-149">Az oldal **Erőforrások** részében válassza ki a **Dynamics 365 alkalmazások** elemet.</span><span class="sxs-lookup"><span data-stu-id="2e86b-149">In the **Resources** section of the page, select **Dynamics 365 apps**.</span></span>

4. <span data-ttu-id="2e86b-150">Válassza ki az **Alkalmazás telepítése** műveletet.</span><span class="sxs-lookup"><span data-stu-id="2e86b-150">Select the **Install app** action.</span></span>

5. <span data-ttu-id="2e86b-151">Válassza ki a **Dynamics 365 HR Virtual Entity** elemet, majd pedig a **Tovább** elemet.</span><span class="sxs-lookup"><span data-stu-id="2e86b-151">Select **Dynamics 365 HR Virtual Entity** , and select **Next**.</span></span>

6. <span data-ttu-id="2e86b-152">Olvassa át, majd pedig kijelöléssel jelezze, hogy elfogadja-e a szolgáltatási feltételeket.</span><span class="sxs-lookup"><span data-stu-id="2e86b-152">Review and mark to agree to the terms of service.</span></span>

7. <span data-ttu-id="2e86b-153">Válassza a **Telepítés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="2e86b-153">Select **Install**.</span></span>

<span data-ttu-id="2e86b-154">A telepítés néhány percet igényel.</span><span class="sxs-lookup"><span data-stu-id="2e86b-154">The install takes a few minutes.</span></span> <span data-ttu-id="2e86b-155">Befejezéskor folytassa a következő lépésekkel.</span><span class="sxs-lookup"><span data-stu-id="2e86b-155">When it completes, continue to the next steps.</span></span>

![A Dynamics 365 HR Virtual Entity alkalmazás telepítése a Power Platform felügyeleti központból](./media/hr-admin-integration-virtual-entities-power-platform-install.jpg)

### <a name="configure-the-virtual-entity-data-source"></a><span data-ttu-id="2e86b-157">A virtuális entitás adatforrásának konfigurálása</span><span class="sxs-lookup"><span data-stu-id="2e86b-157">Configure the virtual entity data source</span></span> 

<span data-ttu-id="2e86b-158">A következő lépésben a virtuális entitás adatforrásának a Power Apps környezetben történő konfigurálása történik.</span><span class="sxs-lookup"><span data-stu-id="2e86b-158">The next step is to configure the virtual entity data source in the Power Apps environment.</span></span> 

1. <span data-ttu-id="2e86b-159">Nyissa meg a [Power Platform felügyeleti központot](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="2e86b-159">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="2e86b-160">A **Környezetek** listán válassza ki a saját HR-instanciájához társított Power Apps környezetet.</span><span class="sxs-lookup"><span data-stu-id="2e86b-160">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="2e86b-161">Válassza ki a **Környezet URL-je** elemet az oldal **Részletek** részében.</span><span class="sxs-lookup"><span data-stu-id="2e86b-161">Select the **Environment URL** in the **Details** section of the page.</span></span>

4. <span data-ttu-id="2e86b-162">A **Megoldás-állapotfelügyeleti központ** felületén válassza ki az alkalmazásoldal jobb felső sarkában található **Összetett keresés** ikont.</span><span class="sxs-lookup"><span data-stu-id="2e86b-162">In the **Solution Health Hub** , select the **Advanced Find** icon in the top right of the application page.</span></span>

5. <span data-ttu-id="2e86b-163">Az **Összetett keresés** oldalon, az **Elem keresése** legördülő listán válassza ki a **Finance and Operations virtuális adatforrás konfigurációi** elemet.</span><span class="sxs-lookup"><span data-stu-id="2e86b-163">On the **Advanced Find** page, in the **Look for** dropdown list, select **Finance and Operations Virtual Data Source Configurations**.</span></span>

6. <span data-ttu-id="2e86b-164">Válassza az **Eredmények** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2e86b-164">Select **Results**.</span></span>

7. <span data-ttu-id="2e86b-165">Válassza ki a **Microsoft HR-adatforrás** rekordot.</span><span class="sxs-lookup"><span data-stu-id="2e86b-165">Select the **Microsoft HR Data Source** record.</span></span>

8. <span data-ttu-id="2e86b-166">Adja meg az adatforrás-konfigurációhoz szükséges adatokat.</span><span class="sxs-lookup"><span data-stu-id="2e86b-166">Enter the required information for the data source configuration.</span></span>

   - <span data-ttu-id="2e86b-167">**Cél URL** : A saját HR-névtér URL-je.</span><span class="sxs-lookup"><span data-stu-id="2e86b-167">**Target URL** : The URL of your Human Resources namespace.</span></span>
   - <span data-ttu-id="2e86b-168">**Bérlő azonosítója** : az Azure Active Directory (Azure AD) bérlő azonosítója.</span><span class="sxs-lookup"><span data-stu-id="2e86b-168">**Tenant ID** : The Azure Active Directory (Azure AD) tenant ID.</span></span>
   - <span data-ttu-id="2e86b-169">**AAD-alkalmazásazonosító** : Az Microsoft Azure portálon regisztrált alkalmazáshoz létrehozott alkalmazásazonosító (ügyfél-azonosító).</span><span class="sxs-lookup"><span data-stu-id="2e86b-169">**AAD Application ID** : The application (client) ID created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="2e86b-170">Ezt az információt korábban, az [Alkalmazás regisztrálása a Microsoft Azure-ban](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure) lépésben kapta meg.</span><span class="sxs-lookup"><span data-stu-id="2e86b-170">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>
   - <span data-ttu-id="2e86b-171">**AAD-alkalmazástitok** : A Microsoft Azure portálon regisztrált alkalmazáshoz létrehozott ügyféltitok.</span><span class="sxs-lookup"><span data-stu-id="2e86b-171">**AAD Application Secret** : The client secret created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="2e86b-172">Ezt az információt korábban, az [Alkalmazás regisztrálása a Microsoft Azure-ban](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure) lépésben kapta meg.</span><span class="sxs-lookup"><span data-stu-id="2e86b-172">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>

9. <span data-ttu-id="2e86b-173">Válassza ki a **Mentés és bezárás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2e86b-173">Select **Save & Close**.</span></span>

   ![Microsoft HR-adatforrás](./media/hr-admin-integration-virtual-entities-hr-data-source.jpg)

### <a name="grant-app-permissions-in-human-resources"></a><span data-ttu-id="2e86b-175">Alkalmazásengedélyek kiosztása a HR-ben</span><span class="sxs-lookup"><span data-stu-id="2e86b-175">Grant app permissions in Human Resources</span></span>

<span data-ttu-id="2e86b-176">Engedélyek kiosztása a HR-ben lévő két Azure AD-alkalmazáshoz:</span><span class="sxs-lookup"><span data-stu-id="2e86b-176">Grant permissions for the two Azure AD applications in Human Resources:</span></span>

- <span data-ttu-id="2e86b-177">A Microsoft Azure portálon a bérlője számára létrehozott alkalmazás</span><span class="sxs-lookup"><span data-stu-id="2e86b-177">The app created for your tenant in the Microsoft Azure portal</span></span>
- <span data-ttu-id="2e86b-178">A Dynamics 365 HR Virtual Entity alkalmazás a Power Apps környezetben telepítve</span><span class="sxs-lookup"><span data-stu-id="2e86b-178">The Dynamics 365 HR Virtual Entity app installed in the Power Apps environment</span></span> 

1. <span data-ttu-id="2e86b-179">A HR-modulban nyissa meg az **Azure Active Directory-alkalmazások** oldalt.</span><span class="sxs-lookup"><span data-stu-id="2e86b-179">In Human Resources, open the **Azure Active Directory applications** page.</span></span>

2. <span data-ttu-id="2e86b-180">Válassza ki az **Új** lehetőséget egy új alkalmazásrekord létrehozásához:</span><span class="sxs-lookup"><span data-stu-id="2e86b-180">Select **New** to create a new application record:</span></span>

    - <span data-ttu-id="2e86b-181">Az **Ügyfél-azonosító** mezőbe írja be a Microsoft Azure portálon regisztrált alkalmazás ügyfél-azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="2e86b-181">In the **Client ID** field, enter the client ID of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="2e86b-182">A **Név** mezőbe írja be a Microsoft Azure portálon regisztrált alkalmazás nevét.</span><span class="sxs-lookup"><span data-stu-id="2e86b-182">In the **Name** field, enter the name of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="2e86b-183">A **Felhasználóazonosító** mezőben válassza ki azt a felhasználót, aki rendszergazdai jogokkal rendelkezik a HR-modulban és a Power Apps környezetben.</span><span class="sxs-lookup"><span data-stu-id="2e86b-183">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

3. <span data-ttu-id="2e86b-184">Válassza ki az **Új** lehetőséget egy második alkalmazásrekord létrehozásához:</span><span class="sxs-lookup"><span data-stu-id="2e86b-184">Select **New** to create a second application record:</span></span>

    - <span data-ttu-id="2e86b-185">**Ügyfél-azonosító** : f9be0c49-aa22-4ec6-911a-c5da515226ff</span><span class="sxs-lookup"><span data-stu-id="2e86b-185">**Client Id** : f9be0c49-aa22-4ec6-911a-c5da515226ff</span></span>
    - <span data-ttu-id="2e86b-186">**Név** : Dynamics 365 HR Virtual Entity</span><span class="sxs-lookup"><span data-stu-id="2e86b-186">**Name** : Dynamics 365 HR Virtual Entity</span></span>
    - <span data-ttu-id="2e86b-187">A **Felhasználóazonosító** mezőben válassza ki azt a felhasználót, aki rendszergazdai jogokkal rendelkezik a HR-modulban és a Power Apps környezetben.</span><span class="sxs-lookup"><span data-stu-id="2e86b-187">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

## <a name="generate-virtual-entities"></a><span data-ttu-id="2e86b-188">Virtuális entitások létrehozása</span><span class="sxs-lookup"><span data-stu-id="2e86b-188">Generate virtual entities</span></span>

<span data-ttu-id="2e86b-189">A telepítés befejezését követően kiválaszthatja, hogy mely virtuális entitásokat szeretné létrehozni és engedélyezni a saját Common Data Service-példányában.</span><span class="sxs-lookup"><span data-stu-id="2e86b-189">When setup completes, you can select the virtual entities you want to generate and enable in your Common Data Service instance.</span></span>

1. <span data-ttu-id="2e86b-190">A HR-modulban nyissa meg a **Common Data Service (CDS) integrációja** oldalt.</span><span class="sxs-lookup"><span data-stu-id="2e86b-190">In Human Resources, open the **Common Data Service (CDS) integration** page.</span></span>

2. <span data-ttu-id="2e86b-191">Válassza ki a **Virtuális entitások** lapot.</span><span class="sxs-lookup"><span data-stu-id="2e86b-191">Select the **Virtual entities** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="2e86b-192">A **Virtuális entitások engedélyezése** váltógombot a rendszer automatikusan az **Igen** értékre állítja, ha befejezte a szükséges beállításokat.</span><span class="sxs-lookup"><span data-stu-id="2e86b-192">The **Enable the virtual entity** toggle will be set to **Yes** automatically when all required setup has been completed.</span></span> <span data-ttu-id="2e86b-193">Ha a váltógomb értéke **Nem** , tekintse át a dokumentum előző szakaszaiban ismertetett lépéseket, és győződjön meg arról, hogy minden előfeltétel-beállítást befejezett.</span><span class="sxs-lookup"><span data-stu-id="2e86b-193">If the toggle is set to **No** , review the steps in previous sections of this document to ensure all prerequisite setup is completed.</span></span>

3. <span data-ttu-id="2e86b-194">Válassza ki a Common Data Service szolgáltatásban létrehozni kívánt entitást vagy entitásokat.</span><span class="sxs-lookup"><span data-stu-id="2e86b-194">Select the entity or entities you want to generate in Common Data Service.</span></span>

4. <span data-ttu-id="2e86b-195">Válassza a **Létrehozás/frissítés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2e86b-195">Select **Generate/refresh**.</span></span>

![Common Data Service-integráció](./media/hr-admin-integration-common-data-service-integration.jpg)

## <a name="check-entity-generation-status"></a><span data-ttu-id="2e86b-197">Entitásgenerálási állapot ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="2e86b-197">Check entity generation status</span></span>

<span data-ttu-id="2e86b-198">A virtuális entitások a Common Data Service szolgáltatásban aszinkron háttérfolyamatok során jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="2e86b-198">Virtual entities are generated in Common Data Service through an asynchronous background process.</span></span> <span data-ttu-id="2e86b-199">A folyamat frissítései a műveleti központban láthatók.</span><span class="sxs-lookup"><span data-stu-id="2e86b-199">Updates on the process display in the action center.</span></span> <span data-ttu-id="2e86b-200">A folyamatra vonatkozó részletek, többek között a hibanaplók, a **Folyamatok automatizálása** oldalon láthatók.</span><span class="sxs-lookup"><span data-stu-id="2e86b-200">Details on the process, including error logs, appear in the **Process automations** page.</span></span>

1. <span data-ttu-id="2e86b-201">Az Emberi Erőforrások modulban nyissa meg **Folyamatok automatizálása** lapot.</span><span class="sxs-lookup"><span data-stu-id="2e86b-201">In Human Resources, open the **Process automations** page.</span></span>

2. <span data-ttu-id="2e86b-202">Válassza ki a **Háttérfolyamatok** lapot.</span><span class="sxs-lookup"><span data-stu-id="2e86b-202">Select the **Background processes** tab.</span></span>

3. <span data-ttu-id="2e86b-203">Válassza ki a **Virtuális entitás lekérdezése – aszinkron háttérfolyamat** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2e86b-203">Select **Virtual entity poll async operation background process**.</span></span>

4. <span data-ttu-id="2e86b-204">Válassza ki a **Legutóbbi eredmények megtekintése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2e86b-204">Select **View most recent results**.</span></span>

<span data-ttu-id="2e86b-205">A kicsúszó ablaktábla megjeleníti a folyamat legutóbbi végrehajtásának eredményeit.</span><span class="sxs-lookup"><span data-stu-id="2e86b-205">The slideout pane displays the most recent execution results for the process.</span></span> <span data-ttu-id="2e86b-206">Megtekintheti a folyamat naplóját, többek között a Common Data Service szolgáltatásból visszaküldött hibákat is.</span><span class="sxs-lookup"><span data-stu-id="2e86b-206">You can view the log for the process, including any errors returned from Common Data Service.</span></span>

## <a name="see-also"></a><span data-ttu-id="2e86b-207">Lásd még</span><span class="sxs-lookup"><span data-stu-id="2e86b-207">See also</span></span>

[<span data-ttu-id="2e86b-208">Mi az a Common Data Service?</span><span class="sxs-lookup"><span data-stu-id="2e86b-208">What is Common Data Service?</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)<br>
[<span data-ttu-id="2e86b-209">Entitások áttekintése</span><span class="sxs-lookup"><span data-stu-id="2e86b-209">Entity overview</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/entity-overview)<br>
[<span data-ttu-id="2e86b-210">Entitáskapcsolatok áttekintése</span><span class="sxs-lookup"><span data-stu-id="2e86b-210">Entity relationships overview</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/relationships-overview)<br>
[<span data-ttu-id="2e86b-211">Külső adatforrásból származó adatokat tartalmazó virtuális entitások létrehozása és szerkesztése</span><span class="sxs-lookup"><span data-stu-id="2e86b-211">Create and edit virtual entities that contain data from an external data source</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/create-edit-virtual-entities)<br>
[<span data-ttu-id="2e86b-212">Mik azok a Power Apps portálok?</span><span class="sxs-lookup"><span data-stu-id="2e86b-212">What is Power Apps portals?</span></span>](https://docs.microsoft.com/powerapps/maker/portals/overview)<br>
[<span data-ttu-id="2e86b-213">Alkalmazások Power Apps-ben való létrehozásának áttekintése</span><span class="sxs-lookup"><span data-stu-id="2e86b-213">Overview of creating apps in Power Apps</span></span>](https://docs.microsoft.com/powerapps/maker/)
