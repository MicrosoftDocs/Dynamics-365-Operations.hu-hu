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
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8c2e207efe0eeec6fc7e679a6ae12edcb21b291f
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6058584"
---
# <a name="configure-dataverse-virtual-tables"></a><span data-ttu-id="6aee9-104">Dataverse-virtuális táblák konfigurálása</span><span class="sxs-lookup"><span data-stu-id="6aee9-104">Configure Dataverse virtual tables</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="6aee9-105">A Dynamics 365 Human Resources egy virtuális adatforrás a következőben: Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="6aee9-105">Dynamics 365 Human Resources is a virtual data source in Microsoft Dataverse.</span></span> <span data-ttu-id="6aee9-106">Teljes körű létrehozási, olvasási, frissítési és törlési (CRUD) műveletek végrehajtását teszi lehetővé a következőkből: Dataverse és Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="6aee9-106">It provides full create, read, update, and delete (CRUD) operations from Dataverse and Microsoft Power Platform.</span></span> <span data-ttu-id="6aee9-107">A virtuális táblák adatait a Dataverse tárolja, hanem az alkalmazás-adatbázis.</span><span class="sxs-lookup"><span data-stu-id="6aee9-107">The data for virtual tables isn't stored in Dataverse, but in the application database.</span></span>

<span data-ttu-id="6aee9-108">A HR-entitásokon, Dataverse segítségével végrehajtandó CRUD-műveletek engedélyezéséhez virtuális táblákként elérhetővé kell tennie az entitásokat a következőben: Dataverse.</span><span class="sxs-lookup"><span data-stu-id="6aee9-108">To enable CRUD operations on Human Resources entities from Dataverse, you must make the entities available as virtual tables in Dataverse.</span></span> <span data-ttu-id="6aee9-109">Ezáltal CRUD-műveleteket hajthat végre Dataverse és Microsoft Power Platform segítségével a HR-ben található adatokon.</span><span class="sxs-lookup"><span data-stu-id="6aee9-109">This lets you perform CRUD operations from Dataverse and Microsoft Power Platform on data that's in Human Resources.</span></span> <span data-ttu-id="6aee9-110">A műveletek támogatják továbbá a HR teljes üzleti logikájának érvényesülését, hogy az adatok épsége biztosított legyen az adatoknak az entitásokba írásakor.</span><span class="sxs-lookup"><span data-stu-id="6aee9-110">The operations also support the full business logic validations of Human Resources to ensure data integrity when writing data to the entities.</span></span>

> [!NOTE]
> <span data-ttu-id="6aee9-111">A Human Resources entitások Dataverse-tábláknak felelnek meg.</span><span class="sxs-lookup"><span data-stu-id="6aee9-111">Human Resources entities correspond to Dataverse tables.</span></span> <span data-ttu-id="6aee9-112">A Dataverse (a korábbi Common Data Service) rendszer kapcsolatos további tudnivalókat és a terminológiai frissítéseket lásd: [Mi a Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)</span><span class="sxs-lookup"><span data-stu-id="6aee9-112">For more information about Dataverse (formerly Common Data Service) and terminology updates, see [What is Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)</span></span>

## <a name="available-virtual-tables-for-human-resources"></a><span data-ttu-id="6aee9-113">A Human Resources számára elérhető virtuális táblák</span><span class="sxs-lookup"><span data-stu-id="6aee9-113">Available virtual tables for Human Resources</span></span>

<span data-ttu-id="6aee9-114">A HR-ben található összes Open Data Protocol (OData) entitások virtuális táblákként elérhetők a Dataverse rendszerben.</span><span class="sxs-lookup"><span data-stu-id="6aee9-114">All Open Data Protocol (OData) entities in Human Resources are available as virtual tables in Dataverse.</span></span> <span data-ttu-id="6aee9-115">Ezek itt is elérhetők: Power Platform.</span><span class="sxs-lookup"><span data-stu-id="6aee9-115">They're also available in Power Platform.</span></span> <span data-ttu-id="6aee9-116">Mostantól a teljes CRUD-funkcionalitással hozhat létre alkalmazásokat és élményeket közvetlenül a HR-től származó adatokkal – mindezt anélkül, hogy az adatokat a Dataverse-be kellene másolni vagy azzal szinkronizálni kellene.</span><span class="sxs-lookup"><span data-stu-id="6aee9-116">You can now build apps and experiences with data directly from Human Resources with full CRUD capability, without copying or synchronizing data to Dataverse.</span></span> <span data-ttu-id="6aee9-117">A Power Apps portálok segítségével külső webhelyeket is létrehozhat, amelyekkel együttműködési forgatókönyvek alakíthatók ki a HR-en belüli üzleti folyamatokhoz.</span><span class="sxs-lookup"><span data-stu-id="6aee9-117">You can use Power Apps portals to build external-facing websites that enable collaboration scenarios for business processes in Human Resources.</span></span>

<span data-ttu-id="6aee9-118">A [Power Apps](https://make.powerapps.com)-ben megtekintheti a környezetben engedélyezett virtuális táblák listáját, valamint elkezdheti a munkát az táblákon a **Dynamics 365 HR Virtual Tables** megoldásban.</span><span class="sxs-lookup"><span data-stu-id="6aee9-118">You can view the list of virtual tables enabled in the environment, and begin working with the tables in [Power Apps](https://make.powerapps.com), in the **Dynamics 365 HR Virtual Tables** solution.</span></span>

![Dynamics 365 HR Virtual Tables a Power Apps rendszerben](./media/hr-admin-integration-virtual-entities-power-apps.jpg)

## <a name="virtual-tables-versus-native-tables"></a><span data-ttu-id="6aee9-120">Virtuális táblák és natív táblák</span><span class="sxs-lookup"><span data-stu-id="6aee9-120">Virtual tables versus native tables</span></span>

<span data-ttu-id="6aee9-121">A HR-hez tartozó virtuális táblák nem azonosak a HR számára létrehozott natív Dataverse-táblákkal.</span><span class="sxs-lookup"><span data-stu-id="6aee9-121">Virtual tables for Human Resources aren't the same as the native Dataverse tables created for Human Resources.</span></span> 

<span data-ttu-id="6aee9-122">A HR-hez tartozó natív táblákat külön hozzák létre és kezelik a Dataverse szolgáltatáson belüli közös humántőke-menedzsment megoldásban.</span><span class="sxs-lookup"><span data-stu-id="6aee9-122">The native tables for Human Resources are generated separately and maintained in the HCM Common solution in Dataverse.</span></span> <span data-ttu-id="6aee9-123">A natív táblák esetén az adatok tárolása a Dataverse szolgáltatásban történik, és szinkronizálni kell őket a HR alkalmazás-adatbázisával.</span><span class="sxs-lookup"><span data-stu-id="6aee9-123">With native tables, the data is stored in Dataverse and requires synchronization with the Human Resources application database.</span></span>

> [!NOTE]
> <span data-ttu-id="6aee9-124">A HR-hez tartozó natív Dataverse-táblák listájához lásd: [Dataverse-táblák](./hr-developer-entities.md).</span><span class="sxs-lookup"><span data-stu-id="6aee9-124">For a list of the native Dataverse tables for Human Resources, see [Dataverse tables](./hr-developer-entities.md).</span></span>

## <a name="setup"></a><span data-ttu-id="6aee9-125">Beállítás</span><span class="sxs-lookup"><span data-stu-id="6aee9-125">Setup</span></span>

<span data-ttu-id="6aee9-126">A következő lépésekkel engedélyezheti a virtuális táblák telepítését a környezetben.</span><span class="sxs-lookup"><span data-stu-id="6aee9-126">Follow these setup steps to enable virtual tables in your environment.</span></span>

### <a name="enable-virtual-tables-in-human-resources"></a><span data-ttu-id="6aee9-127">Virtuális táblák engedélyezése a Human Resources alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="6aee9-127">Enable virtual tables in Human Resources</span></span>

<span data-ttu-id="6aee9-128">Először engedélyeznie kell a virtuális táblákat a **Szolgáltatáskezelés** munkaterületen.</span><span class="sxs-lookup"><span data-stu-id="6aee9-128">First, you must enable virtual tables in the **Feature management** workspace.</span></span>

1. <span data-ttu-id="6aee9-129">A Human Resources alkalmazásban válassza a **Rendszerfelügyelet** elemet.</span><span class="sxs-lookup"><span data-stu-id="6aee9-129">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="6aee9-130">Válassza ki a **Funkció kezelése** csempét.</span><span class="sxs-lookup"><span data-stu-id="6aee9-130">Select the **Feature management** tile.</span></span>

3. <span data-ttu-id="6aee9-131">Válassza a **Virtuális táblák támogatása a HR számára a Dataverse rendszerben** elemet, majd az **Engedélyezés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6aee9-131">Select **Virtual table support for HR in Dataverse**, and then select **Enable**.</span></span>

<span data-ttu-id="6aee9-132">A funkciók aktiválásával és letiltásával kapcsolatos további részletekért tekintse meg a [Szolgáltatások kezelése](hr-admin-manage-features.md) oldalt.</span><span class="sxs-lookup"><span data-stu-id="6aee9-132">For more information about enabling and disabling features, see [Manage features](hr-admin-manage-features.md).</span></span>

### <a name="register-the-app-in-microsoft-azure"></a><span data-ttu-id="6aee9-133">Regisztrálja az alkalmazást a Microsoft Azure-ban</span><span class="sxs-lookup"><span data-stu-id="6aee9-133">Register the app in Microsoft Azure</span></span>

<span data-ttu-id="6aee9-134">Először az Azure Portal webhelyen kell regisztrálnia a Human Resources példányt, hogy a Microsoft identitásplatform hitelesítési és engedélyezési szolgáltatásokat nyújthasson az alkalmazás és a felhasználók számára.</span><span class="sxs-lookup"><span data-stu-id="6aee9-134">You must register your Human Resources instance in the Azure portal so the Microsoft identity platform can provide authentication and authorization services for the app and users.</span></span> <span data-ttu-id="6aee9-135">Az alkalmazások Azure-ban való regisztrálásával kapcsolatos további tudnivalókat lásd: [Rövid útmutató: Alkalmazások regisztrálása a Microsoft Identity platformmal](/azure/active-directory/develop/quickstart-register-app).</span><span class="sxs-lookup"><span data-stu-id="6aee9-135">For more information about registering apps in Azure, see [Quickstart: Register an application with the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app).</span></span>

1. <span data-ttu-id="6aee9-136">Nyissa meg a [Microsoft Azure portált](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="6aee9-136">Open the [Microsoft Azure portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="6aee9-137">Az Azure-szolgáltatások listáján válassza ki az **Alkalmazásregisztrációk** elemet.</span><span class="sxs-lookup"><span data-stu-id="6aee9-137">In the Azure services list, select **App registrations**.</span></span>

3. <span data-ttu-id="6aee9-138">Válassza ki az **Új regisztráció** elemet.</span><span class="sxs-lookup"><span data-stu-id="6aee9-138">Select **New registration**.</span></span>

4. <span data-ttu-id="6aee9-139">A **Név** mezőbe írja be az alkalmazás ismertető nevét.</span><span class="sxs-lookup"><span data-stu-id="6aee9-139">In the **Name** field, enter a descriptive name for the app.</span></span> <span data-ttu-id="6aee9-140">Például **Dynamics 365 Human Resources Virtuális táblák**.</span><span class="sxs-lookup"><span data-stu-id="6aee9-140">For example, **Dynamics 365 Human Resources Virtual Tables**.</span></span>

5. <span data-ttu-id="6aee9-141">Az **Átirányítási URL-cím** mezőben adja meg a saját HR-instancia URL-névterét.</span><span class="sxs-lookup"><span data-stu-id="6aee9-141">In the **Redirect URI** field, enter the namespace URL of your instance of Human Resources.</span></span>

6. <span data-ttu-id="6aee9-142">Válassza a **Regisztrálás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6aee9-142">Select **Register**.</span></span>

7. <span data-ttu-id="6aee9-143">A regisztráció befejezését követően az Azure Portal megjeleníti az alkalmazás regisztrációjának **Áttekintés** ablaka, amelyen látható az **alkalmazás (ügyfél) azonosítója**.</span><span class="sxs-lookup"><span data-stu-id="6aee9-143">When registration completes, the Azure portal displays the app registration's **Overview** pane, which includes its **Application (client) ID**.</span></span> <span data-ttu-id="6aee9-144">Ekkor jegyezze fel az **alkalmazás (ügyfél) azonosítóját**.</span><span class="sxs-lookup"><span data-stu-id="6aee9-144">Take note of the **Application (client) ID** at this time.</span></span> <span data-ttu-id="6aee9-145">Ezt az információt akkor kell megadnia, amikor a [virtuális tábla adatforrását konfigurálja](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span><span class="sxs-lookup"><span data-stu-id="6aee9-145">You'll enter this information when you [Configure the virtual table data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span></span>

8. <span data-ttu-id="6aee9-146">A bal oldali navigációs ablakban válassza ki a **Tanúsítványok és titkos kódok** elemet.</span><span class="sxs-lookup"><span data-stu-id="6aee9-146">In the left navigation pane, select **Certificates and secrets**.</span></span>

9. <span data-ttu-id="6aee9-147">Az oldal **Ügyfél titkai** részén válassza az **Új ügyféltitok** elemet.</span><span class="sxs-lookup"><span data-stu-id="6aee9-147">In the **Client secrets** section of the page, select **New client secret**.</span></span>

10. <span data-ttu-id="6aee9-148">Adjon meg egy leírást, válassza ki az időtartamot, majd válassza a **Hozzáadás** elemet.</span><span class="sxs-lookup"><span data-stu-id="6aee9-148">Provide a description, select a duration, and select **Add**.</span></span>

11. <span data-ttu-id="6aee9-149">A titkos érték rekordja a tábla **Érték** tulajdonságából.</span><span class="sxs-lookup"><span data-stu-id="6aee9-149">Record the secret's value from the **Value** property of the table.</span></span> <span data-ttu-id="6aee9-150">Ezt az információt akkor kell megadnia, amikor a [virtuális tábla adatforrását konfigurálja](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span><span class="sxs-lookup"><span data-stu-id="6aee9-150">You'll enter this information when you [Configure the virtual table data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="6aee9-151">A titok értéket ekkor feltétlenül rögzítse.</span><span class="sxs-lookup"><span data-stu-id="6aee9-151">Be sure to take note of the secret's value at this time.</span></span> <span data-ttu-id="6aee9-152">A titok az oldal elhagyása után már többé nem fog megjelenni.</span><span class="sxs-lookup"><span data-stu-id="6aee9-152">The secret is never displayed again after you leave this page.</span></span>

### <a name="install-the-dynamics-365-hr-virtual-table-app"></a><span data-ttu-id="6aee9-153">A Dynamics 365 HR Virtual Table alkalmazás telepítése</span><span class="sxs-lookup"><span data-stu-id="6aee9-153">Install the Dynamics 365 HR Virtual Table app</span></span>

<span data-ttu-id="6aee9-154">Telepítse a Dynamics 365 HR Virtual Table alkalmazást a saját Power Apps környezetében, hogy a virtuális tábla megoldáscsomagot telepíthesse a Dataverse szolgáltatáshoz.</span><span class="sxs-lookup"><span data-stu-id="6aee9-154">Install the Dynamics 365 HR Virtual Table app in your Power Apps environment to deploy the virtual table solution package to Dataverse.</span></span>

1. <span data-ttu-id="6aee9-155">A HR-modulban nyissa meg a **Microsoft Dataverse integrációja** oldalt.</span><span class="sxs-lookup"><span data-stu-id="6aee9-155">In Human Resources, open the **Microsoft Dataverse integration** page.</span></span>

2. <span data-ttu-id="6aee9-156">Válassza ki a **Virtuális táblák** lapot.</span><span class="sxs-lookup"><span data-stu-id="6aee9-156">Select the **Virtual tables** tab.</span></span>

3. <span data-ttu-id="6aee9-157">Válassza a **Virtuális táblaalkalmazás telepítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6aee9-157">Select **Install virtual table app**.</span></span>

### <a name="configure-the-virtual-table-data-source"></a><span data-ttu-id="6aee9-158">A virtuális tábla adatforrásának konfigurálása</span><span class="sxs-lookup"><span data-stu-id="6aee9-158">Configure the virtual table data source</span></span>

<span data-ttu-id="6aee9-159">A következő lépésben a virtuális tábla adatforrásának a Power Apps környezetben történő konfigurálása történik.</span><span class="sxs-lookup"><span data-stu-id="6aee9-159">The next step is to configure the virtual table data source in the Power Apps environment.</span></span>

1. <span data-ttu-id="6aee9-160">Nyissa meg a [Power Platform felügyeleti központot](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="6aee9-160">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="6aee9-161">A **Környezetek** listán válassza ki a saját HR-instanciájához társított Power Apps környezetet.</span><span class="sxs-lookup"><span data-stu-id="6aee9-161">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="6aee9-162">Válassza ki a **Környezet URL-je** elemet az oldal **Részletek** részében.</span><span class="sxs-lookup"><span data-stu-id="6aee9-162">Select the **Environment URL** in the **Details** section of the page.</span></span>

4. <span data-ttu-id="6aee9-163">A **Megoldás-állapotfelügyeleti központ** felületén válassza ki az alkalmazásoldal jobb felső sarkában található **Összetett keresés** ikont.</span><span class="sxs-lookup"><span data-stu-id="6aee9-163">In the **Solution Health Hub**, select the **Advanced Find** icon in the top right of the application page.</span></span>

5. <span data-ttu-id="6aee9-164">Az **Összetett keresés** oldalon, az **Elem keresése** legördülő listán válassza ki a **Finance and Operations virtuális adatforrás konfigurációi** elemet.</span><span class="sxs-lookup"><span data-stu-id="6aee9-164">On the **Advanced Find** page, in the **Look for** dropdown list, select **Finance and Operations Virtual Data Source Configurations**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="6aee9-165">Az előző beállítási lépés virtuális tábla alkalmazás telepítése néhány percig is eltarthat.</span><span class="sxs-lookup"><span data-stu-id="6aee9-165">The installation of the virtual table app from the previous setup step can take a few minutes.</span></span> <span data-ttu-id="6aee9-166">Ha a **Finance and Operations virtuális adatforrás konfigurációi** nem érhetők el a listában, várjon egy percet, és frissítse a listát.</span><span class="sxs-lookup"><span data-stu-id="6aee9-166">If **Finance and Operations Virtual Data Source Configurations** isn't available in the list, wait for a minute and refresh the list.</span></span>

6. <span data-ttu-id="6aee9-167">Válassza az **Eredmények** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6aee9-167">Select **Results**.</span></span>

7. <span data-ttu-id="6aee9-168">Válassza ki a **Microsoft HR-adatforrás** rekordot.</span><span class="sxs-lookup"><span data-stu-id="6aee9-168">Select the **Microsoft HR Data Source** record.</span></span>

8. <span data-ttu-id="6aee9-169">Adja meg az adatforrás-konfigurációhoz szükséges adatokat:</span><span class="sxs-lookup"><span data-stu-id="6aee9-169">Enter the required information for the data source configuration:</span></span>

   - <span data-ttu-id="6aee9-170">**Cél URL**: A saját HR-névtér URL-je.</span><span class="sxs-lookup"><span data-stu-id="6aee9-170">**Target URL**: The URL of your Human Resources namespace.</span></span> <span data-ttu-id="6aee9-171">A cél URL formátuma:</span><span class="sxs-lookup"><span data-stu-id="6aee9-171">The format of the target URL is:</span></span>
     
     <span data-ttu-id="6aee9-172">https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/</span><span class="sxs-lookup"><span data-stu-id="6aee9-172">https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/</span></span>

     <span data-ttu-id="6aee9-173">Példa:</span><span class="sxs-lookup"><span data-stu-id="6aee9-173">For example:</span></span>
     
     `https://aos.rts-sf-5ea54e35c68-westus2.hr.talent.dynamics.com/namespaces/49d24c565-8f4d-4891-b174-bf83d948ed0c/`

     >[!NOTE]
     ><span data-ttu-id="6aee9-174">Ügyeljen arra, hogy az URL-cím végén a „**/**” karakter is szerepeljen a hibák elkerülése érdekében.</span><span class="sxs-lookup"><span data-stu-id="6aee9-174">Be sure to include the "**/**" character at the end of the URL to avoid receiving an error.</span></span>

   - <span data-ttu-id="6aee9-175">**Bérlő azonosítója**: az Azure Active Directory (Azure AD) bérlő azonosítója.</span><span class="sxs-lookup"><span data-stu-id="6aee9-175">**Tenant ID**: The Azure Active Directory (Azure AD) tenant ID.</span></span>

   - <span data-ttu-id="6aee9-176">**AAD-alkalmazásazonosító**: Az Microsoft Azure portálon regisztrált alkalmazáshoz létrehozott alkalmazásazonosító (ügyfél-azonosító).</span><span class="sxs-lookup"><span data-stu-id="6aee9-176">**AAD Application ID**: The application (client) ID created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="6aee9-177">Ezt az információt korábban, az [Alkalmazás regisztrálása a Microsoft Azure-ban](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure) lépésben kapta meg.</span><span class="sxs-lookup"><span data-stu-id="6aee9-177">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>

   - <span data-ttu-id="6aee9-178">**AAD-alkalmazástitok**: A Microsoft Azure portálon regisztrált alkalmazáshoz létrehozott ügyféltitok.</span><span class="sxs-lookup"><span data-stu-id="6aee9-178">**AAD Application Secret**: The client secret created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="6aee9-179">Ezt az információt korábban, az [Alkalmazás regisztrálása a Microsoft Azure-ban](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure) lépésben kapta meg.</span><span class="sxs-lookup"><span data-stu-id="6aee9-179">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>

   ![Microsoft HR-adatforrás](./media/hr-admin-integration-virtual-entities-hr-data-source.jpg)

9. <span data-ttu-id="6aee9-181">Válassza ki a **Mentés és bezárás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6aee9-181">Select **Save & Close**.</span></span>

### <a name="grant-app-permissions-in-human-resources"></a><span data-ttu-id="6aee9-182">Alkalmazásengedélyek kiosztása a HR-ben</span><span class="sxs-lookup"><span data-stu-id="6aee9-182">Grant app permissions in Human Resources</span></span>

<span data-ttu-id="6aee9-183">Engedélyek kiosztása a HR-ben lévő két Azure AD-alkalmazáshoz:</span><span class="sxs-lookup"><span data-stu-id="6aee9-183">Grant permissions for the two Azure AD applications in Human Resources:</span></span>

- <span data-ttu-id="6aee9-184">A Microsoft Azure portálon a bérlője számára létrehozott alkalmazás</span><span class="sxs-lookup"><span data-stu-id="6aee9-184">The app created for your tenant in the Microsoft Azure portal</span></span>
- <span data-ttu-id="6aee9-185">A Dynamics 365 HR Virtual Table alkalmazás a Power Apps környezetben telepítve</span><span class="sxs-lookup"><span data-stu-id="6aee9-185">The Dynamics 365 HR Virtual Table app installed in the Power Apps environment</span></span> 

1. <span data-ttu-id="6aee9-186">A HR-modulban nyissa meg az **Azure Active Directory-alkalmazások** oldalt.</span><span class="sxs-lookup"><span data-stu-id="6aee9-186">In Human Resources, open the **Azure Active Directory applications** page.</span></span>

2. <span data-ttu-id="6aee9-187">Válassza ki az **Új** lehetőséget egy új alkalmazásrekord létrehozásához:</span><span class="sxs-lookup"><span data-stu-id="6aee9-187">Select **New** to create a new application record:</span></span>

    - <span data-ttu-id="6aee9-188">Az **Ügyfél-azonosító** mezőbe írja be a Microsoft Azure portálon regisztrált alkalmazás ügyfél-azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="6aee9-188">In the **Client ID** field, enter the client ID of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="6aee9-189">A **Név** mezőbe írja be a Microsoft Azure portálon regisztrált alkalmazás nevét.</span><span class="sxs-lookup"><span data-stu-id="6aee9-189">In the **Name** field, enter the name of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="6aee9-190">A **Felhasználóazonosító** mezőben válassza ki azt a felhasználót, aki rendszergazdai jogokkal rendelkezik a HR-modulban és a Power Apps környezetben.</span><span class="sxs-lookup"><span data-stu-id="6aee9-190">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

3. <span data-ttu-id="6aee9-191">Válassza ki az **Új** lehetőséget egy második alkalmazásrekord létrehozásához:</span><span class="sxs-lookup"><span data-stu-id="6aee9-191">Select **New** to create a second application record:</span></span>

    - <span data-ttu-id="6aee9-192">**Ügyfél-azonosító**: f9be0c49-aa22-4ec6-911a-c5da515226ff</span><span class="sxs-lookup"><span data-stu-id="6aee9-192">**Client Id**: f9be0c49-aa22-4ec6-911a-c5da515226ff</span></span>
    - <span data-ttu-id="6aee9-193">**Név**: Dynamics 365 HR Virtual Table</span><span class="sxs-lookup"><span data-stu-id="6aee9-193">**Name**: Dynamics 365 HR Virtual Table</span></span>
    - <span data-ttu-id="6aee9-194">A **Felhasználóazonosító** mezőben válassza ki azt a felhasználót, aki rendszergazdai jogokkal rendelkezik a HR-modulban és a Power Apps környezetben.</span><span class="sxs-lookup"><span data-stu-id="6aee9-194">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

## <a name="generate-virtual-tables"></a><span data-ttu-id="6aee9-195">Virtuális táblák létrehozása</span><span class="sxs-lookup"><span data-stu-id="6aee9-195">Generate virtual tables</span></span>

<span data-ttu-id="6aee9-196">A telepítés befejezését követően kiválaszthatja, hogy mely virtuális táblákat szeretné létrehozni és engedélyezni a saját Dataverse-példányában.</span><span class="sxs-lookup"><span data-stu-id="6aee9-196">When setup completes, you can select the virtual tables you want to generate and enable in your Dataverse instance.</span></span>

1. <span data-ttu-id="6aee9-197">A HR-modulban nyissa meg a **Microsoft Dataverse integrációja** oldalt.</span><span class="sxs-lookup"><span data-stu-id="6aee9-197">In Human Resources, open the **Microsoft Dataverse integration** page.</span></span>

2. <span data-ttu-id="6aee9-198">Válassza ki a **Virtuális táblák** lapot.</span><span class="sxs-lookup"><span data-stu-id="6aee9-198">Select the **Virtual tables** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="6aee9-199">A **Virtuális táblák engedélyezése** váltógombot a rendszer automatikusan az **Igen** értékre állítja, ha befejezte a szükséges beállításokat.</span><span class="sxs-lookup"><span data-stu-id="6aee9-199">The **Enable virtual tables** toggle will be set to **Yes** automatically when all required setup has been completed.</span></span> <span data-ttu-id="6aee9-200">Ha a váltógomb értéke **Nem**, tekintse át a dokumentum előző szakaszaiban ismertetett lépéseket, és győződjön meg arról, hogy minden előfeltétel-beállítást befejezett.</span><span class="sxs-lookup"><span data-stu-id="6aee9-200">If the toggle is set to **No**, review the steps in previous sections of this document to ensure all prerequisite setup is completed.</span></span>

3. <span data-ttu-id="6aee9-201">Válassza ki a Dataverse szolgáltatásban létrehozni kívánt táblát vagy táblákat.</span><span class="sxs-lookup"><span data-stu-id="6aee9-201">Select the table or tables you want to generate in Dataverse.</span></span>

4. <span data-ttu-id="6aee9-202">Válassza a **Létrehozás/frissítés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6aee9-202">Select **Generate/refresh**.</span></span>

![Dataverse-integráció](./media/hr-admin-integration-dataverse-integration.png)

## <a name="check-table-generation-status"></a><span data-ttu-id="6aee9-204">Táblagenerálási állapot ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="6aee9-204">Check table generation status</span></span>

<span data-ttu-id="6aee9-205">A virtuális táblák a Dataverse szolgáltatásban aszinkron háttérfolyamatok során jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="6aee9-205">Virtual tables are generated in Dataverse through an asynchronous background process.</span></span> <span data-ttu-id="6aee9-206">A folyamat frissítései a műveleti központban láthatók.</span><span class="sxs-lookup"><span data-stu-id="6aee9-206">Updates on the process display in the action center.</span></span> <span data-ttu-id="6aee9-207">A folyamatra vonatkozó részletek, többek között a hibanaplók, a **Folyamatok automatizálása** oldalon láthatók.</span><span class="sxs-lookup"><span data-stu-id="6aee9-207">Details on the process, including error logs, appear in the **Process automations** page.</span></span>

1. <span data-ttu-id="6aee9-208">Az Emberi Erőforrások modulban nyissa meg **Folyamatok automatizálása** lapot.</span><span class="sxs-lookup"><span data-stu-id="6aee9-208">In Human Resources, open the **Process automations** page.</span></span>

2. <span data-ttu-id="6aee9-209">Válassza ki a **Háttérfolyamatok** lapot.</span><span class="sxs-lookup"><span data-stu-id="6aee9-209">Select the **Background processes** tab.</span></span>

3. <span data-ttu-id="6aee9-210">Válassza ki a **Virtuális tábla lekérdezése – aszinkron háttérfolyamat** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6aee9-210">Select **Virtual table poll async operation background process**.</span></span>

4. <span data-ttu-id="6aee9-211">Válassza ki a **Legutóbbi eredmények megtekintése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6aee9-211">Select **View most recent results**.</span></span>

<span data-ttu-id="6aee9-212">A kicsúszó ablaktábla megjeleníti a folyamat legutóbbi végrehajtásának eredményeit.</span><span class="sxs-lookup"><span data-stu-id="6aee9-212">The slideout pane displays the most recent execution results for the process.</span></span> <span data-ttu-id="6aee9-213">Megtekintheti a folyamat naplóját, többek között a Dataverse szolgáltatásból visszaküldött hibákat is.</span><span class="sxs-lookup"><span data-stu-id="6aee9-213">You can view the log for the process, including any errors returned from Dataverse.</span></span>

## <a name="see-also"></a><span data-ttu-id="6aee9-214">Lásd még</span><span class="sxs-lookup"><span data-stu-id="6aee9-214">See also</span></span>

[<span data-ttu-id="6aee9-215">Mi az a Dataverse?</span><span class="sxs-lookup"><span data-stu-id="6aee9-215">What is Dataverse?</span></span>](/powerapps/maker/common-data-service/data-platform-intro)<br>
[<span data-ttu-id="6aee9-216">Táblák a Dataverse-rendszerben</span><span class="sxs-lookup"><span data-stu-id="6aee9-216">Tables in Dataverse</span></span>](/powerapps/maker/common-data-service/entity-overview)<br>
[<span data-ttu-id="6aee9-217">Táblakapcsolatok áttekintése</span><span class="sxs-lookup"><span data-stu-id="6aee9-217">Table relationships overview</span></span>](/powerapps/maker/common-data-service/relationships-overview)<br>
[<span data-ttu-id="6aee9-218">Külső adatforrásból származó adatokat tartalmazó virtuális táblák létrehozása és szerkesztése</span><span class="sxs-lookup"><span data-stu-id="6aee9-218">Create and edit virtual tables that contain data from an external data source</span></span>](/powerapps/maker/common-data-service/create-edit-virtual-entities)<br>
[<span data-ttu-id="6aee9-219">Mik azok a Power Apps portálok?</span><span class="sxs-lookup"><span data-stu-id="6aee9-219">What is Power Apps portals?</span></span>](/powerapps/maker/portals/overview)<br>
[<span data-ttu-id="6aee9-220">Alkalmazások Power Apps-ben való létrehozásának áttekintése</span><span class="sxs-lookup"><span data-stu-id="6aee9-220">Overview of creating apps in Power Apps</span></span>](/powerapps/maker/)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
