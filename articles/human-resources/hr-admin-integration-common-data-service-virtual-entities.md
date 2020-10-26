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
ms.openlocfilehash: 0848b7556100fba38fcab0aa2a1a109e2e055fc9
ms.sourcegitcommit: b89baab13e530b5b1f079231619c628309a4742d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/05/2020
ms.locfileid: "3959575"
---
# <a name="configure-common-data-service-virtual-entities"></a><span data-ttu-id="de656-104">Common Data Service-virtuális entitások konfigurálása</span><span class="sxs-lookup"><span data-stu-id="de656-104">Configure Common Data Service virtual entities</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="de656-105">A Dynamics 365 Human Resources egy virtuális adatforrás a következőben: Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="de656-105">Dynamics 365 Human Resources is a virtual data source in Common Data Service.</span></span> <span data-ttu-id="de656-106">Teljes körű létrehozási, olvasási, frissítési és törlési (CRUD) műveletek végrehajtását teszi lehetővé a következőkből: Common Data Service és Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="de656-106">It provides full create, read, update, and delete (CRUD) operations from Common Data Service and Microsoft Power Platform.</span></span> <span data-ttu-id="de656-107">A virtuális entitások adatait a Common Data Service tárolja, hanem az alkalmazás-adatbázis.</span><span class="sxs-lookup"><span data-stu-id="de656-107">The data for virtual entities isn't stored in Common Data Service, but in the application database.</span></span> 

<span data-ttu-id="de656-108">A HR-entitásokon, Common Data Service segítségével végrehajtandó CRUD-műveletek engedélyezéséhez virtuális entitásokként elérhetővé kell tennie az entitásokat a következőben: Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="de656-108">To enable CRUD operations on Human Resources entities from Common Data Service, you must make the entities available as virtual entities in Common Data Service.</span></span> <span data-ttu-id="de656-109">Ezáltal CRUD-műveleteket hajthat végre Common Data Service és Microsoft Power Platform segítségével a HR-ben található adatokon.</span><span class="sxs-lookup"><span data-stu-id="de656-109">This lets you perform CRUD operations from Common Data Service and Microsoft Power Platform on data that's in Human Resources.</span></span> <span data-ttu-id="de656-110">A műveletek támogatják továbbá a HR teljes üzleti logikájának érvényesülését, hogy az adatok épsége biztosított legyen az adatoknak az entitásokba írásakor.</span><span class="sxs-lookup"><span data-stu-id="de656-110">The operations also support the full business logic validations of Human Resources to ensure data integrity when writing data to the entities.</span></span>

## <a name="available-virtual-entities-for-human-resources"></a><span data-ttu-id="de656-111">A HR számára elérhető virtuális entitások</span><span class="sxs-lookup"><span data-stu-id="de656-111">Available virtual entities for Human Resources</span></span>

<span data-ttu-id="de656-112">A HR-ben található összes Open Data Protocol (OData) entitás virtuális entitásként elérhető a következőben: Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="de656-112">All Open Data Protocol (OData) entities in Human Resources are available as virtual entities in Common Data Service.</span></span> <span data-ttu-id="de656-113">Ezek itt is elérhetők: Power Platform.</span><span class="sxs-lookup"><span data-stu-id="de656-113">They're also available in Power Platform.</span></span> <span data-ttu-id="de656-114">Mostantól a teljes CRUD-funkcionalitással hozhat létre alkalmazásokat és élményeket közvetlenül a HR-től származó adatokkal – mindezt anélkül, hogy az adatokat a Common Data Service-be kellene másolni vagy azzal szinkronizálni kellene.</span><span class="sxs-lookup"><span data-stu-id="de656-114">You can now build apps and experiences with data directly from Human Resources with full CRUD capability, without copying or synchronizing data to Common Data Service.</span></span> <span data-ttu-id="de656-115">A Power Apps portálok segítségével külső webhelyeket is létrehozhat, amelyekkel együttműködési forgatókönyvek alakíthatók ki a HR-en belüli üzleti folyamatokhoz.</span><span class="sxs-lookup"><span data-stu-id="de656-115">You can use Power Apps portals to build external-facing websites that enable collaboration scenarios for business processes in Human Resources.</span></span>

<span data-ttu-id="de656-116">A [Power Apps](https://make.powerapps.com)-ben megtekintheti a környezetben engedélyezett virtuális entitások listáját, valamint elkezdheti a munkát az entitásokon a **Dynamics 365 HR Virtual Entities** megoldásban.</span><span class="sxs-lookup"><span data-stu-id="de656-116">You can view the list of virtual entities enabled in the environment, and begin working with the entities in [Power Apps](https://make.powerapps.com), in the **Dynamics 365 HR Virtual Entities** solution.</span></span>

![Dynamics 365 HR virtuális entitások a következőben: Power Apps](./media/hr-admin-integration-virtual-entities-power-apps.jpg)

## <a name="virtual-entities-versus-natural-entities"></a><span data-ttu-id="de656-118">Virtuális entitások kontra természetes entitások</span><span class="sxs-lookup"><span data-stu-id="de656-118">Virtual entities versus natural entities</span></span>

<span data-ttu-id="de656-119">A HR-hez tartozó virtuális entitások nem azonosak a HR számára létrehozott természetes Common Data Service entitásokkal.</span><span class="sxs-lookup"><span data-stu-id="de656-119">Virtual entities for Human Resources aren't the same as the natural Common Data Service entities created for Human Resources.</span></span> <span data-ttu-id="de656-120">A HR-hez tartozó természetes entitásokat külön hozzák létre és kezelik a Common Data Service szolgáltatáson belüli közös humántőke-menedzsment megoldásban.</span><span class="sxs-lookup"><span data-stu-id="de656-120">The natural entities for Human Resources are generated separately and maintained in the HCM Common solution in Common Data Service.</span></span> <span data-ttu-id="de656-121">A természetes entitások esetén az adatok a Common Data Service szolgáltatásban tárolódnak, és szinkronizálni kell őket a HR alkalmazás-adatbázisával.</span><span class="sxs-lookup"><span data-stu-id="de656-121">With natural entities, the data is stored in Common Data Service and requires synchronization with the Human Resources application database.</span></span>

> [!NOTE]
> <span data-ttu-id="de656-122">A HR-hez tartozó természetes Common Data Service entitások listájához lásd a [Common Data Service entitásokat](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).</span><span class="sxs-lookup"><span data-stu-id="de656-122">For a list of the natural Common Data Service entities for Human Resources, see [Common Data Service entities](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).</span></span>

## <a name="setup"></a><span data-ttu-id="de656-123">Beállítás</span><span class="sxs-lookup"><span data-stu-id="de656-123">Setup</span></span>

<span data-ttu-id="de656-124">A következő lépésekkel engedélyezheti a virtuális entitások telepítését a környezetben.</span><span class="sxs-lookup"><span data-stu-id="de656-124">Follow these setup steps to enable virtual entities in your environment.</span></span> 

### <a name="register-the-app-in-microsoft-azure"></a><span data-ttu-id="de656-125">Regisztrálja az alkalmazást a Microsoft Azure-ban</span><span class="sxs-lookup"><span data-stu-id="de656-125">Register the app in Microsoft Azure</span></span>

<span data-ttu-id="de656-126">Először az Azure Portal webhelyen kell regisztrálnia az alkalmazást, hogy a Microsoft Identity platform hitelesítési és engedélyezési szolgáltatásokat nyújthasson az alkalmazás és a felhasználók számára.</span><span class="sxs-lookup"><span data-stu-id="de656-126">First, you need to register the app in the Azure portal so the Microsoft identity platform can provide authentication and authorization services for the app and users.</span></span> <span data-ttu-id="de656-127">Az alkalmazások Azure-ban való regisztrálásával kapcsolatos további tudnivalókat lásd: [Rövid útmutató: Alkalmazások regisztrálása a Microsoft Identity platformmal](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span><span class="sxs-lookup"><span data-stu-id="de656-127">For more information about registering apps in Azure, see [Quickstart: Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>

1. <span data-ttu-id="de656-128">Nyissa meg a [Microsoft Azure portált](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="de656-128">Open the [Microsoft Azure portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="de656-129">Az Azure-szolgáltatások listáján válassza ki az **Alkalmazásregisztrációk** elemet.</span><span class="sxs-lookup"><span data-stu-id="de656-129">In the Azure services list, select **App registrations** .</span></span>

3. <span data-ttu-id="de656-130">Válassza ki az **Új regisztráció** elemet.</span><span class="sxs-lookup"><span data-stu-id="de656-130">Select **New registration** .</span></span>

4. <span data-ttu-id="de656-131">A **Név** mezőbe írja be az alkalmazás ismertető nevét.</span><span class="sxs-lookup"><span data-stu-id="de656-131">In the **Name** field, enter a descriptive name for the app.</span></span> <span data-ttu-id="de656-132">Például **Dynamics 365 Human Resources Virtuális entitások** .</span><span class="sxs-lookup"><span data-stu-id="de656-132">For example, **Dynamics 365 Human Resources Virtual Entities** .</span></span>

5. <span data-ttu-id="de656-133">Az **Átirányítási URL-cím** mezőben adja meg a saját HR-instancia URL-névterét.</span><span class="sxs-lookup"><span data-stu-id="de656-133">In the **Redirect URI** field, enter the namespace URL of your instance of Human Resources.</span></span>

6. <span data-ttu-id="de656-134">Válassza a **Regisztrálás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="de656-134">Select **Register** .</span></span>

7. <span data-ttu-id="de656-135">A regisztráció befejezését követően az Azure Portal megjeleníti az alkalmazás regisztrációjának **Áttekintés** ablaka, amelyen látható az **alkalmazás (ügyfél) azonosítója** .</span><span class="sxs-lookup"><span data-stu-id="de656-135">When registration completes, the Azure portal displays the app registration's **Overview** pane, which includes its **Application (client) ID** .</span></span> <span data-ttu-id="de656-136">Ekkor jegyezze fel az **alkalmazás (ügyfél) azonosítóját** .</span><span class="sxs-lookup"><span data-stu-id="de656-136">Take note of the **Application (client) ID** at this time.</span></span> <span data-ttu-id="de656-137">Ezt az információt akkor kell megadnia, amikor a [virtuális entitás adatforrását konfigurálja](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span><span class="sxs-lookup"><span data-stu-id="de656-137">You'll enter this information when you [Configure the virtual entity data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span></span>

8. <span data-ttu-id="de656-138">A bal oldali navigációs ablakban válassza ki a **Tanúsítványok és titkos kódok** elemet.</span><span class="sxs-lookup"><span data-stu-id="de656-138">In the left navigation pane, select **Certificates and secrets** .</span></span>

9. <span data-ttu-id="de656-139">Az oldal **Ügyfél titkai** részén válassza az **Új ügyféltitok** elemet.</span><span class="sxs-lookup"><span data-stu-id="de656-139">In the **Client secrets** section of the page, select **New client secret** .</span></span>

10. <span data-ttu-id="de656-140">Adjon meg egy leírást, válassza ki az időtartamot, majd válassza a **Hozzáadás** elemet.</span><span class="sxs-lookup"><span data-stu-id="de656-140">Provide a description, select a duration, and select **Add** .</span></span>

11. <span data-ttu-id="de656-141">Rögzítse a titok értékét.</span><span class="sxs-lookup"><span data-stu-id="de656-141">Record the secret's value.</span></span> <span data-ttu-id="de656-142">Ezt az információt akkor kell megadnia, amikor a [virtuális entitás adatforrását konfigurálja](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span><span class="sxs-lookup"><span data-stu-id="de656-142">You'll enter this information when you [Configure the virtual entity data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="de656-143">A titok értéket ekkor feltétlenül rögzítse.</span><span class="sxs-lookup"><span data-stu-id="de656-143">Be sure to take note of the secret's value at this time.</span></span> <span data-ttu-id="de656-144">A titok az oldal elhagyása után már többé nem fog megjelenni.</span><span class="sxs-lookup"><span data-stu-id="de656-144">The secret is never displayed again after you leave this page.</span></span>

### <a name="install-the-dynamics-365-hr-virtual-entity-app"></a><span data-ttu-id="de656-145">A Dynamics 365 HR Virtual Entity alkalmazás telepítése</span><span class="sxs-lookup"><span data-stu-id="de656-145">Install the Dynamics 365 HR Virtual Entity app</span></span>

<span data-ttu-id="de656-146">Telepítse a Dynamics 365 HR Virtual Entity alkalmazást a saját Power Apps környezetében, hogy a virtuális entitás megoldáscsomagot telepíthesse a Common Data Service szolgáltatáshoz.</span><span class="sxs-lookup"><span data-stu-id="de656-146">Install the Dynamics 365 HR Virtual Entity app in your Power Apps environment to deploy the virtual entity solution package to Common Data Service.</span></span>

1. <span data-ttu-id="de656-147">Nyissa meg a [Power Platform felügyeleti központot](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="de656-147">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="de656-148">A **Környezetek** listán válassza ki a saját HR-instanciájához társított Power Apps környezetet.</span><span class="sxs-lookup"><span data-stu-id="de656-148">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="de656-149">Az oldal **Erőforrások** részében válassza ki a **Dynamics 365 alkalmazások** elemet.</span><span class="sxs-lookup"><span data-stu-id="de656-149">In the **Resources** section of the page, select **Dynamics 365 apps** .</span></span>

4. <span data-ttu-id="de656-150">Válassza ki az **Alkalmazás telepítése** műveletet.</span><span class="sxs-lookup"><span data-stu-id="de656-150">Select the **Install app** action.</span></span>

5. <span data-ttu-id="de656-151">Válassza ki a **Dynamics 365 HR Virtual Entity** elemet, majd pedig a **Tovább** elemet.</span><span class="sxs-lookup"><span data-stu-id="de656-151">Select **Dynamics 365 HR Virtual Entity** , and select **Next** .</span></span>

6. <span data-ttu-id="de656-152">Olvassa át, majd pedig kijelöléssel jelezze, hogy elfogadja-e a szolgáltatási feltételeket.</span><span class="sxs-lookup"><span data-stu-id="de656-152">Review and mark to agree to the terms of service.</span></span>

7. <span data-ttu-id="de656-153">Válassza a **Telepítés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="de656-153">Select **Install** .</span></span>

<span data-ttu-id="de656-154">A telepítés néhány percet igényel.</span><span class="sxs-lookup"><span data-stu-id="de656-154">The install takes a few minutes.</span></span> <span data-ttu-id="de656-155">Befejezéskor folytassa a következő lépésekkel.</span><span class="sxs-lookup"><span data-stu-id="de656-155">When it completes, continue to the next steps.</span></span>

![A Dynamics 365 HR Virtual Entity alkalmazás telepítése a Power Platform felügyeleti központból](./media/hr-admin-integration-virtual-entities-power-platform-install.jpg)

### <a name="configure-the-virtual-entity-data-source"></a><span data-ttu-id="de656-157">A virtuális entitás adatforrásának konfigurálása</span><span class="sxs-lookup"><span data-stu-id="de656-157">Configure the virtual entity data source</span></span> 

<span data-ttu-id="de656-158">A következő lépésben a virtuális entitás adatforrásának a Power Apps környezetben történő konfigurálása történik.</span><span class="sxs-lookup"><span data-stu-id="de656-158">The next step is to configure the virtual entity data source in the Power Apps environment.</span></span> 

1. <span data-ttu-id="de656-159">Nyissa meg a [Power Platform felügyeleti központot](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="de656-159">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="de656-160">A **Környezetek** listán válassza ki a saját HR-instanciájához társított Power Apps környezetet.</span><span class="sxs-lookup"><span data-stu-id="de656-160">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="de656-161">Válassza ki a **Környezet URL-je** elemet az oldal **Részletek** részében.</span><span class="sxs-lookup"><span data-stu-id="de656-161">Select the **Environment URL** in the **Details** section of the page.</span></span>

4. <span data-ttu-id="de656-162">A **Megoldás-állapotfelügyeleti központ** felületén válassza ki az alkalmazásoldal jobb felső sarkában található **Összetett keresés** ikont.</span><span class="sxs-lookup"><span data-stu-id="de656-162">In the **Solution Health Hub** , select the **Advanced Find** icon in the top right of the application page.</span></span>

5. <span data-ttu-id="de656-163">Az **Összetett keresés** oldalon, az **Elem keresése** legördülő listán válassza ki a **Finance and Operations virtuális adatforrás konfigurációi** elemet.</span><span class="sxs-lookup"><span data-stu-id="de656-163">On the **Advanced Find** page, in the **Look for** dropdown list, select **Finance and Operations Virtual Data Source Configurations** .</span></span>

6. <span data-ttu-id="de656-164">Válassza az **Eredmények** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="de656-164">Select **Results** .</span></span>

7. <span data-ttu-id="de656-165">Válassza ki a **Microsoft HR-adatforrás** rekordot.</span><span class="sxs-lookup"><span data-stu-id="de656-165">Select the **Microsoft HR Data Source** record.</span></span>

8. <span data-ttu-id="de656-166">Adja meg az adatforrás-konfigurációhoz szükséges adatokat.</span><span class="sxs-lookup"><span data-stu-id="de656-166">Enter the required information for the data source configuration.</span></span>

   - <span data-ttu-id="de656-167">**Cél URL** : A saját HR-névtér URL-je.</span><span class="sxs-lookup"><span data-stu-id="de656-167">**Target URL** : The URL of your Human Resources namespace.</span></span>
   - <span data-ttu-id="de656-168">**Bérlő azonosítója** : az Azure Active Directory (Azure AD) bérlő azonosítója.</span><span class="sxs-lookup"><span data-stu-id="de656-168">**Tenant ID** : The Azure Active Directory (Azure AD) tenant ID.</span></span>
   - <span data-ttu-id="de656-169">**AAD-alkalmazásazonosító** : Az Microsoft Azure portálon regisztrált alkalmazáshoz létrehozott alkalmazásazonosító (ügyfél-azonosító).</span><span class="sxs-lookup"><span data-stu-id="de656-169">**AAD Application ID** : The application (client) ID created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="de656-170">Ezt az információt korábban, az [Alkalmazás regisztrálása a Microsoft Azure-ban](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure) lépésben kapta meg.</span><span class="sxs-lookup"><span data-stu-id="de656-170">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>
   - <span data-ttu-id="de656-171">**AAD-alkalmazástitok** : A Microsoft Azure portálon regisztrált alkalmazáshoz létrehozott ügyféltitok.</span><span class="sxs-lookup"><span data-stu-id="de656-171">**AAD Application Secret** : The client secret created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="de656-172">Ezt az információt korábban, az [Alkalmazás regisztrálása a Microsoft Azure-ban](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure) lépésben kapta meg.</span><span class="sxs-lookup"><span data-stu-id="de656-172">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>

9. <span data-ttu-id="de656-173">Válassza ki a **Mentés és bezárás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="de656-173">Select **Save & Close** .</span></span>

   ![Microsoft HR-adatforrás](./media/hr-admin-integration-virtual-entities-hr-data-source.jpg)

### <a name="grant-app-permissions-in-human-resources"></a><span data-ttu-id="de656-175">Alkalmazásengedélyek kiosztása a HR-ben</span><span class="sxs-lookup"><span data-stu-id="de656-175">Grant app permissions in Human Resources</span></span>

<span data-ttu-id="de656-176">Engedélyek kiosztása a HR-ben lévő két Azure AD-alkalmazáshoz:</span><span class="sxs-lookup"><span data-stu-id="de656-176">Grant permissions for the two Azure AD applications in Human Resources:</span></span>

- <span data-ttu-id="de656-177">A Microsoft Azure portálon a bérlője számára létrehozott alkalmazás</span><span class="sxs-lookup"><span data-stu-id="de656-177">The app created for your tenant in the Microsoft Azure portal</span></span>
- <span data-ttu-id="de656-178">A Dynamics 365 HR Virtual Entity alkalmazás a Power Apps környezetben telepítve</span><span class="sxs-lookup"><span data-stu-id="de656-178">The Dynamics 365 HR Virtual Entity app installed in the Power Apps environment</span></span> 

1. <span data-ttu-id="de656-179">A HR-modulban nyissa meg az **Azure Active Directory-alkalmazások** oldalt.</span><span class="sxs-lookup"><span data-stu-id="de656-179">In Human Resources, open the **Azure Active Directory applications** page.</span></span>

2. <span data-ttu-id="de656-180">Válassza ki az **Új** lehetőséget egy új alkalmazásrekord létrehozásához:</span><span class="sxs-lookup"><span data-stu-id="de656-180">Select **New** to create a new application record:</span></span>

    - <span data-ttu-id="de656-181">Az **Ügyfél-azonosító** mezőbe írja be a Microsoft Azure portálon regisztrált alkalmazás ügyfél-azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="de656-181">In the **Client ID** field, enter the client ID of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="de656-182">A **Név** mezőbe írja be a Microsoft Azure portálon regisztrált alkalmazás nevét.</span><span class="sxs-lookup"><span data-stu-id="de656-182">In the **Name** field, enter the name of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="de656-183">A **Felhasználóazonosító** mezőben válassza ki azt a felhasználót, aki rendszergazdai jogokkal rendelkezik a HR-modulban és a Power Apps környezetben.</span><span class="sxs-lookup"><span data-stu-id="de656-183">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

3. <span data-ttu-id="de656-184">Válassza ki az **Új** lehetőséget egy második alkalmazásrekord létrehozásához:</span><span class="sxs-lookup"><span data-stu-id="de656-184">Select **New** to create a second application record:</span></span>

    - <span data-ttu-id="de656-185">**Ügyfél-azonosító** : f9be0c49-aa22-4ec6-911a-c5da515226ff</span><span class="sxs-lookup"><span data-stu-id="de656-185">**Client Id** : f9be0c49-aa22-4ec6-911a-c5da515226ff</span></span>
    - <span data-ttu-id="de656-186">**Név** : Dynamics 365 HR Virtual Entity</span><span class="sxs-lookup"><span data-stu-id="de656-186">**Name** : Dynamics 365 HR Virtual Entity</span></span>
    - <span data-ttu-id="de656-187">A **Felhasználóazonosító** mezőben válassza ki azt a felhasználót, aki rendszergazdai jogokkal rendelkezik a HR-modulban és a Power Apps környezetben.</span><span class="sxs-lookup"><span data-stu-id="de656-187">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

## <a name="generate-virtual-entities"></a><span data-ttu-id="de656-188">Virtuális entitások létrehozása</span><span class="sxs-lookup"><span data-stu-id="de656-188">Generate virtual entities</span></span>

<span data-ttu-id="de656-189">A telepítés befejezését követően kiválaszthatja, hogy mely virtuális entitásokat szeretné létrehozni és engedélyezni a saját Common Data Service-példányában.</span><span class="sxs-lookup"><span data-stu-id="de656-189">When setup completes, you can select the virtual entities you want to generate and enable in your Common Data Service instance.</span></span>

1. <span data-ttu-id="de656-190">Nyissa meg a [Power Platform felügyeleti központot](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="de656-190">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="de656-191">A **Környezetek** listán válassza ki a saját HR-instanciájához társított Power Apps környezetet.</span><span class="sxs-lookup"><span data-stu-id="de656-191">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="de656-192">Válassza ki a **Környezet URL-je** elemet az oldal **Részletek** részében.</span><span class="sxs-lookup"><span data-stu-id="de656-192">Select the **Environment URL** in the **Details** section of the page.</span></span>

4. <span data-ttu-id="de656-193">A **Megoldás-állapotfelügyeleti központ** felületén válassza ki az oldal jobb felső sarkában található **Összetett keresés** ikont.</span><span class="sxs-lookup"><span data-stu-id="de656-193">In the **Solution Health Hub** , select the **Advanced Find** icon in the top right of the page.</span></span>

5. <span data-ttu-id="de656-194">Az **Összetett keresés** oldalon, az **Elem keresése** legördülő listán válassza ki az **Elérhető HR-entitások** elemet.</span><span class="sxs-lookup"><span data-stu-id="de656-194">On the **Advanced Find** page, in the **Look for** dropdown list, select **Available HR Entities** .</span></span>

6. <span data-ttu-id="de656-195">A szűrőbeállítások segítségével megkeresheti az engedélyezni kívánt entitást vagy entitásokat.</span><span class="sxs-lookup"><span data-stu-id="de656-195">Use the filter options to find the entity or entities you want to enable.</span></span>

7. <span data-ttu-id="de656-196">Válasszon egy entitást a listából.</span><span class="sxs-lookup"><span data-stu-id="de656-196">Select an entity from the list.</span></span>

8. <span data-ttu-id="de656-197">Az entitás oldalán módosítsa a **Létrehozva** tulajdonságot **Igen** értékre az adott entitáshoz.</span><span class="sxs-lookup"><span data-stu-id="de656-197">On the entity page, change the **Has Been Generated** property to **Yes** for the entity.</span></span>

9. <span data-ttu-id="de656-198">Mentse el és zárja be az entitás oldalát.</span><span class="sxs-lookup"><span data-stu-id="de656-198">Save and close the entity page.</span></span>

> [!NOTE]
> <span data-ttu-id="de656-199">A **Több rekord módosítása** oldalon egyszerre több virtuális entitást is létre lehet hozni.</span><span class="sxs-lookup"><span data-stu-id="de656-199">You can generate multiple virtual entities at once by using the **Change Multiple Records** page.</span></span> <span data-ttu-id="de656-200">Jelöljön ki több rekordot az oldalon, és válassza a **Szerkesztés** elemet a menüszalagon.</span><span class="sxs-lookup"><span data-stu-id="de656-200">Select multiple records on the page, and select **Edit** on the ribbon.</span></span> <span data-ttu-id="de656-201">Ezután a **Létrehozva** tulajdonságot összes kiválasztott rekordra vonatkozóan módosíthatja.</span><span class="sxs-lookup"><span data-stu-id="de656-201">You can then change the **Has Been Generated** property for all selected records.</span></span>

![Elérhető HR-entitások](./media/hr-admin-integration-virtual-entities-available.jpg)

> [!NOTE]
> <span data-ttu-id="de656-203">Annak érdekében, hogy a virtuális entitások létrehozási folyamat egyszerűbb legyen a jövőbeli verziókban is, a folyamat egy HR-en belüli oldalon megy végbe.</span><span class="sxs-lookup"><span data-stu-id="de656-203">To streamline the process of generating virtual entities in future releases, the process will occur in a page in Human Resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="de656-204">Lásd még</span><span class="sxs-lookup"><span data-stu-id="de656-204">See also</span></span>

[<span data-ttu-id="de656-205">Mi az a Common Data Service?</span><span class="sxs-lookup"><span data-stu-id="de656-205">What is Common Data Service?</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)<br>
[<span data-ttu-id="de656-206">Entitások áttekintése</span><span class="sxs-lookup"><span data-stu-id="de656-206">Entity overview</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/entity-overview)<br>
[<span data-ttu-id="de656-207">Entitáskapcsolatok áttekintése</span><span class="sxs-lookup"><span data-stu-id="de656-207">Entity relationships overview</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/relationships-overview)<br>
[<span data-ttu-id="de656-208">Külső adatforrásból származó adatokat tartalmazó virtuális entitások létrehozása és szerkesztése</span><span class="sxs-lookup"><span data-stu-id="de656-208">Create and edit virtual entities that contain data from an external data source</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/create-edit-virtual-entities)<br>
[<span data-ttu-id="de656-209">Mik azok a Power Apps portálok?</span><span class="sxs-lookup"><span data-stu-id="de656-209">What is Power Apps portals?</span></span>](https://docs.microsoft.com/powerapps/maker/portals/overview)<br>
[<span data-ttu-id="de656-210">Alkalmazások Power Apps-ben való létrehozásának áttekintése</span><span class="sxs-lookup"><span data-stu-id="de656-210">Overview of creating apps in Power Apps</span></span>](https://docs.microsoft.com/powerapps/maker/)
