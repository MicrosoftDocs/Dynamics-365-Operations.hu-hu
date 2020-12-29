---
title: Készlet láthatósága bővítmény
description: Ez a témakör a Készlet láthatósága bővítmény telepítését és konfigurálását ismerteti a Dynamics 365 Supply Chain Management rendszerhez.
author: chuzheng
manager: tfehr
ms.date: 10/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 2976153a6a7e4b4130e8f7673ed128945aeabf65
ms.sourcegitcommit: 03c2e1717b31e4c17ee7bb9004d2ba8cf379a036
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/24/2020
ms.locfileid: "4625065"
---
# <a name="inventory-visibility-add-in"></a><span data-ttu-id="6cc2b-103">Készlet láthatósága bővítmény</span><span class="sxs-lookup"><span data-stu-id="6cc2b-103">Inventory Visibility Add-in</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="6cc2b-104">A Készlet láthatósága bővítmény egy független és jól méretezhető mikroszolgáltatás, amely lehetővé teszi a valós idejű aktuális készletkövetést, így globális képet nyújt a készlet láthatóságáról.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-104">The Inventory Visibility Add-in is an independent and highly scalable microservice that enables real-time on-hand inventory tracking, thus providing a global view of inventory visibility.</span></span>

<span data-ttu-id="6cc2b-105">Az aktuális készlethez kapcsolódó összes információt a rendszer közel valós időben exportálja a szolgáltatásba alacsony szintű SQL-integráció révén.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-105">All information that relates to on-hand inventory is exported to the service in near real-time through low-level SQL integration.</span></span> <span data-ttu-id="6cc2b-106">A külső rendszerek RESTful API-kon keresztül érik el a szolgáltatást, hogy aktuális információkat kérdezzenek le adott dimenziókészletekről, így lekérve a rendelkezésre álló aktuális pozíciók listáját.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-106">External systems access the service through RESTful APIs to query on-hand information on given sets of dimensions, thus retrieving a list of available on-hand positions.</span></span>

<span data-ttu-id="6cc2b-107">A Készlet láthatósága egy mikroszolgáltatás, amely a Common Data Service rendszerre épül, ami azt jelenti, hogy bővítheti Power Apps alkalmazások készítésével és Power BI alkalmazásával, hogy személyre szabott funkciókat biztosítson, amelyek megfelelnek az üzleti követelményeknek.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-107">Inventory Visibility is a microservice built on the Common Data Service, which means you can extend it by building Power Apps and applying Power BI to provide customized functionality to meet your business requirements.</span></span> <span data-ttu-id="6cc2b-108">Lehetőség van az index frissítésére is a készletlekérdezésekhez.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-108">It is also possible to upgrade the index to do inventory queries.</span></span>

<span data-ttu-id="6cc2b-109">A Készlet láthatósága olyan konfigurációs beállításokat biztosít, amelyek lehetővé teszik, hogy több külső gyártótól származó rendszerrel integrálódjon.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-109">Inventory Visibility provides configuration options that let it integrate with multiple third-party systems.</span></span> <span data-ttu-id="6cc2b-110">Támogatja a szabványosított készletdimenziót, a testreszabott bővíthetőséget és a szabványosított, konfigurálható számított mennyiségeket.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-110">It supports the standardized inventory dimension, customized extensibility, and standardized, configurable calculated quantities.</span></span>

<span data-ttu-id="6cc2b-111">Ez a témakör azt ismerteti, hogyan telepítheti és konfigurálhatja az Készlet láthatósága bővítményt a Dynamics 365 Supply Chain Management rendszerhez, és hogyan használhatja az alkalmazásprogramozási felületét (API).</span><span class="sxs-lookup"><span data-stu-id="6cc2b-111">This topic describes how to install and configure the Inventory Visibility Add-in for Dynamics 365 Supply Chain Management, and how to use its application programming interface (API).</span></span>

## <a name="install-the-inventory-visibility-add-in"></a><span data-ttu-id="6cc2b-112">A Készlet láthatósága bővítmény telepítése</span><span class="sxs-lookup"><span data-stu-id="6cc2b-112">Install the Inventory Visibility Add-in</span></span>

<span data-ttu-id="6cc2b-113">Telepítenie kell a Készlet láthatósága bővítményt a Microsoft Dynamics Lifecycle Services (LCS) használatával.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-113">You need to install the Inventory Visibility Add-in using Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="6cc2b-114">Az LCS egy együttműködési portál, amely egy környezetet és rendszeresen frissített szolgáltatások készletét biztosítja, amelyek segítenek a Dynamics 365 Finance and Operations-alkalmazások alkalmazás-életciklusának kezelésében.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-114">LCS is a collaboration portal that provides an environment and a set of regularly updated services that help you manage the application lifecycle of your Dynamics 365 Finance and Operations apps.</span></span>

<span data-ttu-id="6cc2b-115">További tudnivalókért lásd: [Lifecycle Services-erőforrások](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs).</span><span class="sxs-lookup"><span data-stu-id="6cc2b-115">For more information, see [Lifecycle Services resources](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs).</span></span>

### <a name="prerequisites"></a><span data-ttu-id="6cc2b-116">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="6cc2b-116">Prerequisites</span></span>

<span data-ttu-id="6cc2b-117">A Készlet láthatósága bővítmény telepítése előtt a következőket kell tennie:</span><span class="sxs-lookup"><span data-stu-id="6cc2b-117">Before you install the Inventory Visibility Add-in, you must do the following:</span></span>

- <span data-ttu-id="6cc2b-118">Szerezzen be egy LCS-megvalósítási projektet legalább egy üzembe helyezett környezettel.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-118">Obtain an LCS implementation project with at least one environment deployed.</span></span>
- <span data-ttu-id="6cc2b-119">Hozza létre az ajánlat bétakulcsait az LCS-ben.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-119">Generate the beta keys for your offering in LCS.</span></span>
- <span data-ttu-id="6cc2b-120">Engedélyezze a felhasználójának szóló ajánlat bétakulcsait az LCS-ben.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-120">Enable the beta keys for your offering for your user in LCS.</span></span>
- <span data-ttu-id="6cc2b-121">Lépjen kapcsolatba a Microsoft Készlet láthatósága termékcsapatával, és adja meg a környezeti azonosítót, ahol telepíteni szeretné a Készlet láthatósága bővítményt.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-121">Contact the Microsoft Inventory Visibility product team and provide an environment ID where you want to deploy the Inventory Visibility Add-in.</span></span>

<span data-ttu-id="6cc2b-122">Ha bármilyen kérdése van ezekkel az előfeltételekkel kapcsolatban, kérjük, forduljon a Készlet láthatósága termékcsapatához.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-122">If you have any questions about these prerequisites, please contact the Inventory Visibility product team.</span></span>

### <a name="install-the-add-in"></a><a name="install-add-in"></a><span data-ttu-id="6cc2b-123">Telepítse a bővítményt</span><span class="sxs-lookup"><span data-stu-id="6cc2b-123">Install the add-in</span></span>

<span data-ttu-id="6cc2b-124">A Készlet láthatósága bővítmény telepítéséhez a következőket kell tennie:</span><span class="sxs-lookup"><span data-stu-id="6cc2b-124">To install the Inventory Visibility Add-in, do the following:</span></span>

1. <span data-ttu-id="6cc2b-125">Jelentkezzen be a [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index) portálra.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-125">Sign in to the [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index) portal.</span></span>
1. <span data-ttu-id="6cc2b-126">A kezdőlapon válassza ki azt a projektet, amelyben a környezet telepítve van.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-126">On the home page, select the project where your environment is deployed.</span></span>
1. <span data-ttu-id="6cc2b-127">A projekt oldalon jelölje ki azt a környezetet, amelyben telepíteni szeretné a bővítményt.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-127">On the project page, select the environment where you want to install the add-in.</span></span>
1. <span data-ttu-id="6cc2b-128">A környezet oldalon görgessen lefelé, amíg meg nem jelenik a **Környezeti bővítmények** szakasz.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-128">On the environment page, scroll down until you see the **Environment add-ins** section.</span></span> <span data-ttu-id="6cc2b-129">Ha a szakasz nem látható, ellenőrizze, hogy az előfeltétel-bétakulcsok teljes mértékben fel lettek-e dolgozva.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-129">If the section isn't visible, make sure the prerequisite beta keys have been fully processed.</span></span>
1. <span data-ttu-id="6cc2b-130">A **Környezeti bővítmények** szakaszban válassza az **Új bővítmény telepítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-130">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>
    <span data-ttu-id="6cc2b-131">![A környezeti oldal az LCS-ben](media/inventory-visibility-environment.png "A környezeti oldal az LCS-ben")</span><span class="sxs-lookup"><span data-stu-id="6cc2b-131">![The environment page in LCS](media/inventory-visibility-environment.png "The environment page in LCS")</span></span>
1. <span data-ttu-id="6cc2b-132">Válassza az **Új bővítmény telepítése** hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-132">Select the **Install a new add-in** link.</span></span> <span data-ttu-id="6cc2b-133">Megnyílik az elérhető bővítmények listája.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-133">A list of available add-ins opens.</span></span>
1. <span data-ttu-id="6cc2b-134">Válassza a **Készletszolgáltatás** elemet a listából.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-134">Select **Inventory service** from the list.</span></span> <span data-ttu-id="6cc2b-135">(Megjegyzés: ez most már lehet, hogy **Készlet láthatósága bővítmény a Dynamics 365 Supply Chain Management rendszerhez** néven szerepel.)</span><span class="sxs-lookup"><span data-stu-id="6cc2b-135">(Note, this may now be listed as **Inventory Visibility Add-in for Dynamics 365 Supply Chain Management**.)</span></span>
1. <span data-ttu-id="6cc2b-136">Adja meg a környezet alábbi mezőinek értékeit:</span><span class="sxs-lookup"><span data-stu-id="6cc2b-136">Enter values for the following fields for your environment:</span></span>

    - <span data-ttu-id="6cc2b-137">**AAD alkalmazás azonosítója**</span><span class="sxs-lookup"><span data-stu-id="6cc2b-137">**AAD application ID**</span></span>
    - <span data-ttu-id="6cc2b-138">**AAD bérlő azonosítója**</span><span class="sxs-lookup"><span data-stu-id="6cc2b-138">**AAD tenant ID**</span></span>

    <span data-ttu-id="6cc2b-139">![Hozzáadás a beállítási lapon](media/inventory-visibility-setup.png "Hozzáadás a beállítási lapon")</span><span class="sxs-lookup"><span data-stu-id="6cc2b-139">![Add in setup page](media/inventory-visibility-setup.png "Add-in setup page")</span></span>

1. <span data-ttu-id="6cc2b-140">Fogadja el a feltételeket az **Általános Szerződési feltételek** jelölőnégyzet bejelölésével.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-140">Agree to the terms and condition by selecting the **Terms and conditions** check box.</span></span>
1. <span data-ttu-id="6cc2b-141">Válassza a **Telepítés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-141">Select **Install**.</span></span> <span data-ttu-id="6cc2b-142">A bővítmény állapota **Telepítés** értékkel jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-142">The status of the add-in will show as **Installing**.</span></span> <span data-ttu-id="6cc2b-143">Ha befejeződött, frissítse a lapot, hogy lássa, ahogy a **Telepített** állapotra változik.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-143">When it's done, refresh the page to see the status change to **Installed**.</span></span>

### <a name="get-a-security-service-token"></a><span data-ttu-id="6cc2b-144">Biztonsági szolgáltatás jogkivonatának beszerzése</span><span class="sxs-lookup"><span data-stu-id="6cc2b-144">Get a security service token</span></span>

<span data-ttu-id="6cc2b-145">Biztonsági szolgáltatás jogkivonatának beszerzéséhez tegye a következőket:</span><span class="sxs-lookup"><span data-stu-id="6cc2b-145">To get a security service token, do the following:</span></span>

1. <span data-ttu-id="6cc2b-146">Szerezze meg az `aadToken` elemet, és hívja a végpontot: https://securityservice.operations365.dynamics.com/token.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-146">Get your `aadToken` and call the endpoint: https://securityservice.operations365.dynamics.com/token.</span></span>
1. <span data-ttu-id="6cc2b-147">Cserélje ki a `client_assertion` elemet az `aadToken` törzsében.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-147">Replace the `client_assertion` in the body with your `aadToken`.</span></span>
1. <span data-ttu-id="6cc2b-148">Cserélje le a kontextust a törzsben arra a környezetre, ahol a bővítményt telepíteni szeretné.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-148">Replace the context in the body with the environment where you want to deploy the add-in.</span></span>
1. <span data-ttu-id="6cc2b-149">Cserélje ki a törzsben lévő hatókört a következőkre:</span><span class="sxs-lookup"><span data-stu-id="6cc2b-149">Replace the scope in the body with the following:</span></span>

    - <span data-ttu-id="6cc2b-150">Az MCK hatóköre - "https://inventoryservice.operations365.dynamics.cn/.default"</span><span class="sxs-lookup"><span data-stu-id="6cc2b-150">Scope for MCK - "https://inventoryservice.operations365.dynamics.cn/.default"</span></span>  
    <span data-ttu-id="6cc2b-151">(Az Azure Active Directory alkalmazásazonosítóját és bérlőazonosítóját az MCK-hoz a `appsettings.mck.json` tartalmazza.)</span><span class="sxs-lookup"><span data-stu-id="6cc2b-151">(You can find the Azure Active Directory application ID and tenant ID for MCK in `appsettings.mck.json`.)</span></span>
    - <span data-ttu-id="6cc2b-152">Az PROD hatóköre - "https://inventoryservice.operations365.dynamics.com/.default"</span><span class="sxs-lookup"><span data-stu-id="6cc2b-152">Scope for PROD - "https://inventoryservice.operations365.dynamics.com/.default"</span></span>  
    <span data-ttu-id="6cc2b-153">(Az Azure Active Directory alkalmazásazonosítóját és bérlőazonosítóját az PROD-hoz a `appsettings.prod.json` tartalmazza.)</span><span class="sxs-lookup"><span data-stu-id="6cc2b-153">(You can find the Azure Active Directory application ID and tenant ID for PROD in `appsettings.prod.json`.)</span></span>

    <span data-ttu-id="6cc2b-154">Az eredmény az alábbi példához hasonlóan jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-154">The result should resemble the following example.</span></span>

    ```json
    {
        "grant_type": "client_credentials",
        "client_assertion_type":"aad_app",
        "client_assertion": "{**Your_AADToken**}",
        "scope":"**https://inventoryservice.operations365.dynamics.com/.default**",
        "context": "**5dbf6cc8-255e-4de2-8a25-2101cd5649b4**",
        "context_type": "finops-env"
    }
    ```

1. <span data-ttu-id="6cc2b-155">Kap egy `access_token` elemet válaszul.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-155">You will get an `access_token` in response.</span></span> <span data-ttu-id="6cc2b-156">Ez az, amire szüksége van, mint tulajdonosi jogkivonat, hogy meghívja meg a Készlet láthatósága API-t.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-156">This is what you need as a bearer token to call the Inventory Visibility API.</span></span> <span data-ttu-id="6cc2b-157">Íme, egy példa.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-157">Here is an example.</span></span>

    ```json
    {
        "access_token": "{Returned_Token}",
        "token_type": "bearer",
        "expires_in": 1200
    }
    ```

### <a name="uninstall-the-add-in"></a><span data-ttu-id="6cc2b-158">A bővítmény eltávolítása</span><span class="sxs-lookup"><span data-stu-id="6cc2b-158">Uninstall the add-in</span></span>

<span data-ttu-id="6cc2b-159">A bővítmény eltávolításához válassza az **Eltávolítás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-159">To uninstall the add-in, select **Uninstall**.</span></span> <span data-ttu-id="6cc2b-160">Frissítse az LCS-t, és a Készlet láthatósága bővítmény törlődik.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-160">Refresh LCS and the Inventory Visibility Add-in will be removed.</span></span> <span data-ttu-id="6cc2b-161">Az eltávolítási folyamat eltávolítja a bővítmény regisztrációját, és elindít egy feladatot a szolgáltatásban tárolt összes üzleti adat törléséhez.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-161">The uninstall process will remove the add-in registration and also start a job to clean up all of the business data stored in the service.</span></span>

## <a name="inventory-visibility-add-in-public-api"></a><span data-ttu-id="6cc2b-162">Készlet láthatósága bővítmény nyilvános API</span><span class="sxs-lookup"><span data-stu-id="6cc2b-162">Inventory Visibility Add-in public API</span></span>

<span data-ttu-id="6cc2b-163">A Készlet láthatósága bővítmény nyilvános REST API-ja az integráció több konkrét végpontját mutatja be.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-163">The public REST API of the of the Inventory Visibility Add-in presents several specific endpoints of integration.</span></span> <span data-ttu-id="6cc2b-164">Három fő interakciós típust támogat:</span><span class="sxs-lookup"><span data-stu-id="6cc2b-164">It supports three main interaction types:</span></span>

- <span data-ttu-id="6cc2b-165">A bővítmény aktuális módosításainak külső rendszerből történő feladása.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-165">Posting on-hand changes to the add-in from an external system.</span></span>
- <span data-ttu-id="6cc2b-166">Aktuális rendelkezésre álló mennyiségek lekérdezése külső rendszerből.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-166">Querying current on-hand quantities from an external system.</span></span>
- <span data-ttu-id="6cc2b-167">Automatikus szinkronizálás a Supply Chain Management aktuális adataival.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-167">Automatic synchronization with Supply Chain Management on-hand.</span></span>

<span data-ttu-id="6cc2b-168">Az automatikus szinkronizálás nem része a nyilvános API-nak, hanem a rendszer a háttérben kezeli azon környezetek esetében, amelyek engedélyezték a Készlet láthatósága bővítményt.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-168">The automatic synchronization isn't part of the public API but is instead handled in the background for environments that have enabled the Inventory Visibility Add-in.</span></span>

### <a name="authentication"></a><span data-ttu-id="6cc2b-169">Hitelesítés</span><span class="sxs-lookup"><span data-stu-id="6cc2b-169">Authentication</span></span>

<span data-ttu-id="6cc2b-170">A platform biztonsági jogkivonata a Készlet láthatósága bővítmény hívására szolgál, ezért létre kell hoznia egy Azure Active Directory-jogkivonatot az Azure Active Directory alkalmazás használatával.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-170">The platform security token is used to call the Inventory Visibility Add-in, so you must generate an Azure Active Directory token using your Azure Active Directory application.</span></span>

<span data-ttu-id="6cc2b-171">A biztonsági jogkivonat beszerzéséről a [Készlet láthatósága bővítmény telepítése](#install-add-in) című témakörben talál további információt.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-171">For more information about how to get the security token, see [Install the Inventory Visibility Add-in](#install-add-in).</span></span>

### <a name="configure-the-inventory-visibility-api"></a><span data-ttu-id="6cc2b-172">A Készlet láthatósága API konfigurálása</span><span class="sxs-lookup"><span data-stu-id="6cc2b-172">Configure the Inventory Visibility API</span></span>

<span data-ttu-id="6cc2b-173">A szolgáltatás használata előtt ki kell töltenie az alábbi alszakaszokban ismertetett konfigurációkat.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-173">Before using the service, you must complete the configurations described in the following subsections.</span></span> <span data-ttu-id="6cc2b-174">A konfiguráció a környezet részleteitől függően változhat.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-174">The configuration may vary based on the details of your environment.</span></span> <span data-ttu-id="6cc2b-175">Ez elsősorban négy részből áll:</span><span class="sxs-lookup"><span data-stu-id="6cc2b-175">It primarily includes four parts:</span></span>

- [<span data-ttu-id="6cc2b-176">Particionálás</span><span class="sxs-lookup"><span data-stu-id="6cc2b-176">Partitioning</span></span>](#partitioning)
- [<span data-ttu-id="6cc2b-177">Dimenziókonfigurációk</span><span class="sxs-lookup"><span data-stu-id="6cc2b-177">Dimension configurations</span></span>](#dimension-configurations)
- [<span data-ttu-id="6cc2b-178">Indexelés</span><span class="sxs-lookup"><span data-stu-id="6cc2b-178">Indexing</span></span>](#indexing)
- [<span data-ttu-id="6cc2b-179">Egyéni mérés</span><span class="sxs-lookup"><span data-stu-id="6cc2b-179">Custom measurement</span></span>](#custom-measurement)

#### <a name="partitioning"></a><span data-ttu-id="6cc2b-180">Particionálás</span><span class="sxs-lookup"><span data-stu-id="6cc2b-180">Partitioning</span></span>

<span data-ttu-id="6cc2b-181">A particionálás jelentősen befolyásolhatja a Készlet láthatósága API teljesítményét.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-181">Partitioning can significantly influence the performance of the Inventory Visibility API.</span></span> <span data-ttu-id="6cc2b-182">Célszerű olyan sémát definiálni, amely lehetővé teszi az adatok kis csoportjait, miközben továbbra is lehetővé teszi az értelmezhető adatlekérdezéseket.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-182">It's a good idea to define a scheme that allows for small groupings of data while still allowing for meaningful data queries.</span></span>

<span data-ttu-id="6cc2b-183">Az `organizationId` (`dataAreaId` a Supply Chain Management esetében) mindig a particionálás része lesz, és alapértelmezés szerint a Készlet láthatósága dimenziók szerinti particionálásra van beállítva *Telephely + Hely* szerint.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-183">The `organizationId` (`dataAreaId` in Supply Chain Management) will always be part of the partitioning, and by default Inventory Visibility is set to partition by dimensions as *Site + Location*.</span></span> <span data-ttu-id="6cc2b-184">Ez azt jelenti, hogy a szolgáltatást mindig le kell kérdezni ezekkel a szűrőkön definiált dimenziókkal.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-184">This means that the service must always be queried with these dimensions defined on the filters.</span></span>

> [!NOTE]
> <span data-ttu-id="6cc2b-185">A *Telephely* és a *Hely* két általános alapértelmezett dimenzió a Készlet láthatóságában.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-185">*Site* and *Location* are two general default dimensions in Inventory Visibility.</span></span> <span data-ttu-id="6cc2b-186">A Supply Chain Managementben ezeket a dimenziók *Telephely* (`InventSiteId`) és *Raktár* (`InventLocationId`) néven szerepelnek</span><span class="sxs-lookup"><span data-stu-id="6cc2b-186">In Supply Chain Management, those dimensions are called *Site* (`InventSiteId`) and *Warehouse* (`InventLocationId`)</span></span>

### <a name="dimension-configurations"></a><span data-ttu-id="6cc2b-187">Dimenziókonfigurációk</span><span class="sxs-lookup"><span data-stu-id="6cc2b-187">Dimension configurations</span></span>

<span data-ttu-id="6cc2b-188">A Készlet láthatósága az általános alapértelmezett dimenziók listáját tartalmazza a több forrásrendszer integrációjának engedélyezéséhez.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-188">Inventory Visibility will provide a list of general default dimensions to enable the multiple source system integration.</span></span>

<span data-ttu-id="6cc2b-189">Az alábbi táblázat azokat a készletdimenziókat sorolja fel, amelyek a Készlet láthatósága alapértelmezett dimenziónevei lesznek.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-189">The following table lists the inventory dimensions that will be the default dimension names in Inventory Visibility.</span></span>

| <span data-ttu-id="6cc2b-190">Dimenzió típusa</span><span class="sxs-lookup"><span data-stu-id="6cc2b-190">Dimension type</span></span> | <span data-ttu-id="6cc2b-191">Dimenzió neve</span><span class="sxs-lookup"><span data-stu-id="6cc2b-191">Dimension name</span></span> |
|---|---|
| <span data-ttu-id="6cc2b-192">Termék</span><span class="sxs-lookup"><span data-stu-id="6cc2b-192">Product</span></span> | `ColorId` |
| <span data-ttu-id="6cc2b-193">Termék</span><span class="sxs-lookup"><span data-stu-id="6cc2b-193">Product</span></span> | `SizeId` |
| <span data-ttu-id="6cc2b-194">Termék</span><span class="sxs-lookup"><span data-stu-id="6cc2b-194">Product</span></span> | `StyleId` |
| <span data-ttu-id="6cc2b-195">Termék</span><span class="sxs-lookup"><span data-stu-id="6cc2b-195">Product</span></span> | `ConfigId` |
| <span data-ttu-id="6cc2b-196">Nyomon követés</span><span class="sxs-lookup"><span data-stu-id="6cc2b-196">Tracking</span></span> | `BatchId` |
| <span data-ttu-id="6cc2b-197">Nyomon követés</span><span class="sxs-lookup"><span data-stu-id="6cc2b-197">Tracking</span></span> | `SerialId` |
| <span data-ttu-id="6cc2b-198">Helyszín</span><span class="sxs-lookup"><span data-stu-id="6cc2b-198">Location</span></span> | `LocationId` |
| <span data-ttu-id="6cc2b-199">Helyszín</span><span class="sxs-lookup"><span data-stu-id="6cc2b-199">Location</span></span> | `SiteId` |
| <span data-ttu-id="6cc2b-200">Készlet állapota</span><span class="sxs-lookup"><span data-stu-id="6cc2b-200">Inventory Status</span></span> | `StatusId` |
| <span data-ttu-id="6cc2b-201">Raktárspecifikus</span><span class="sxs-lookup"><span data-stu-id="6cc2b-201">Warehouse Specific</span></span> | `WMSLocationId` |
| <span data-ttu-id="6cc2b-202">Raktárspecifikus</span><span class="sxs-lookup"><span data-stu-id="6cc2b-202">Warehouse Specific</span></span> | `WMSPalletId` |
| <span data-ttu-id="6cc2b-203">Raktárspecifikus</span><span class="sxs-lookup"><span data-stu-id="6cc2b-203">Warehouse Specific</span></span> | `LicensePlateId` |

> [!NOTE]
> <span data-ttu-id="6cc2b-204">Az előző táblában felsorolt dimenziótípus csak tájékoztató jellegű.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-204">The dimension type listed in the previous table is for reference only.</span></span> <span data-ttu-id="6cc2b-205">A dimenziótípust nem kell definiálnia a Készlet láthatósága bővítményben.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-205">You don't need to define the dimension type in Inventory Visibility.</span></span>

<span data-ttu-id="6cc2b-206">Ha létezik egyéni dimenzió, és a Készlet láthatósága által felhasznált alapértelmezett értékre kell áramlania, az **Egyéni dimenzió** nevét a Készlet láthatóságában konfigurálhatja.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-206">If a custom dimension exists and needs to flow to a default value when consumed by Inventory Visibility, you can configure the **Custom dimension** name in Inventory Visibility.</span></span>

<span data-ttu-id="6cc2b-207">A külső rendszerek RESTful API-kon keresztül férnek hozzá a Készlet láthatóságához, amelyek lehetővé teszik az adott dimenziókészletek aktuális információinak lekérdezését.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-207">External systems access Inventory Visibility through RESTful APIs that enable on-hand information on given sets of dimensions to be queried.</span></span> <span data-ttu-id="6cc2b-208">Az integrációhoz a Készlet láthatósága lehetővé teszi a *külső csatorna adatforrásának* és a forrásdimenziónak a Készlet láthatósága *céldimenzióihoz* való konfigurálását.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-208">For the integration, Inventory Visibility enables you to configure the *external channel data source* and the source dimension to the *target dimensions* in Inventory Visibility.</span></span>

<span data-ttu-id="6cc2b-209">A céldimenzióknak a következők egyikének kell lenniük:</span><span class="sxs-lookup"><span data-stu-id="6cc2b-209">The target dimensions should be one of the following:</span></span>

- <span data-ttu-id="6cc2b-210">Alapértelmezett dimenziók a Készlet láthatóságában</span><span class="sxs-lookup"><span data-stu-id="6cc2b-210">Default dimensions in Inventory Visibility</span></span>
- <span data-ttu-id="6cc2b-211">Egyéni dimenziók</span><span class="sxs-lookup"><span data-stu-id="6cc2b-211">Custom dimensions</span></span>

<span data-ttu-id="6cc2b-212">A dimenziókonfiguráció célja a dimenziókra irányuló lekérdezések és a dimenziókkal való feladási esemény többrendszeres integrációjának szabványosítása.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-212">The purpose of dimension configuration is to standardize the multi-system integration for the query on dimensions and the posting event with dimensions.</span></span>

#### <a name="indexing"></a><span data-ttu-id="6cc2b-213">Indexelés</span><span class="sxs-lookup"><span data-stu-id="6cc2b-213">Indexing</span></span>

<span data-ttu-id="6cc2b-214">Az aktuális készlet lekérdezése a legtöbb alkalommal nem csak a legmagasabb "teljes" szinten lesz, de előfordulhat, hogy a készletdimenziók alapján összesítve szeretné látni az eredményeket.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-214">Most of the time, the inventory on-hand query will not only be on the highest "total" level, but you may want to see results aggregated based on the inventory dimensions.</span></span>

<span data-ttu-id="6cc2b-215">A Készlet láthatósága rugalmasságot biztosít azáltal, hogy lehetővé teszi az indexek beállítását, amelyek a dimenzión vagy a dimenziók kombinációján alapulnak.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-215">Inventory Visibility provides flexibility by allowing you to set up the indexes, which are based on the dimension or the combination of the dimensions.</span></span>

> [!NOTE]
> <span data-ttu-id="6cc2b-216">Jelenleg csak legfeljebb öt indexet konfigurálhat.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-216">Currently, you can only configure indexes to a maximum of five.</span></span> <span data-ttu-id="6cc2b-217">Alaposan meg kell fontolnia, hogy melyik dimenziót vagy dimenziókombinációt fogja használni a megvalósítás előtt annak érdekében, hogy megfeleljen az üzleti igényeinek.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-217">You need to carefully consider which dimension or dimension combination you will use before the implementation to ensure that it will meet your business needs.</span></span> <span data-ttu-id="6cc2b-218">Ha például a következőképpen szeretne lekérdezni a termékeket:</span><span class="sxs-lookup"><span data-stu-id="6cc2b-218">For example, if you want to query products as follows:</span></span>

- <span data-ttu-id="6cc2b-219">Az összesített termék lekérdezése a *Szín* és *Méret* dimenziókkal.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-219">Query the aggregated product on-hand by the *Color* and *Size* dimensions.</span></span>
- <span data-ttu-id="6cc2b-220">Bizonyos esetekben csak a termék összesített értékét szeretné lekérdezni.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-220">In some cases, you just want to query on the product in total.</span></span>

<span data-ttu-id="6cc2b-221">Két indexet kell definiálni a következőképpen:</span><span class="sxs-lookup"><span data-stu-id="6cc2b-221">You would have two indexes defined as the following:</span></span>

- `["ColorId", "SizeId"]`
- `[]`

<span data-ttu-id="6cc2b-222">Az üres zárójel a partíción belül termékazonosító alapján összesít.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-222">The empty bracket will aggregate based on the product ID within the partition.</span></span>

<span data-ttu-id="6cc2b-223">Az indexelés határozza meg, hogyan csoportosíthatja az eredményeket a `groupBy` lekérdezési beállítás alapján.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-223">The indexing defines how you can group your results based on the `groupBy` query setting.</span></span> <span data-ttu-id="6cc2b-224">Ebben az esetben, ha nem határoz meg `groupBy` értékeket, `productid` szerinti összegeket kap.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-224">In this case if you don't define any `groupBy` values, you'll get totals by `productid`.</span></span> <span data-ttu-id="6cc2b-225">Ellenkező esetben, ha a `groupBy` a `groupBy=ColorId&groupBy=SizeId` értékkel van megadva, a rendszer a különböző szín- és méretkombinációk alapján több sort ad vissza.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-225">Otherwise if you define `groupBy` as `groupBy=ColorId&groupBy=SizeId`, you'll get multiple lines returned, based on the different color and size combinations in the system.</span></span>

<span data-ttu-id="6cc2b-226">A lekérdezési feltételt a kérelem törzsébe teheti.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-226">You can put your query criteria in the request body.</span></span>

<span data-ttu-id="6cc2b-227">Itt egy példa a termék szín- és méretkombinációját tartalmazó lekérdezésre.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-227">Here is a sample query on the product with color and size combination.</span></span>

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "LocationId": ["21"],
        "SiteId": ["2"],
        "ColorId": ["Red"]
    },
    "groupByValues": [
        "SizeId",
        "ColorId"
    ],
    "returnNegative": true
}
```

#### <a name="custom-measurement"></a><span data-ttu-id="6cc2b-228">Egyéni mérés</span><span class="sxs-lookup"><span data-stu-id="6cc2b-228">Custom measurement</span></span>

<span data-ttu-id="6cc2b-229">Az alapértelmezett mértékegység-mennyiségek a Supply Chain Managementhez kötődnek, de előfordulhat, hogy egy olyan mennyiséget kell létrehozni, amely az alapértelmezett mértékegységek kombinációjából áll.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-229">The default measurement quantities are linked to Supply Chain Management, however you may want to have a quantity that is made up of a combination of the default measurements.</span></span> <span data-ttu-id="6cc2b-230">Ehhez egyéni mennyiségek konfigurációját kell megadni, amely az aktuáliskészlet-lekérdezések kimenetéhez lesz hozzáadva.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-230">To do this, you can have a configuration of custom quantities, which will be added to the output of the on-hand queries.</span></span>

<span data-ttu-id="6cc2b-231">A funkció segítségével egyszerűen meghatározhat egy sor olyan mért értéket, amelyet hozzá kell adni, és/vagy egy sor olyan mért értéket, amelyet ki kell vonni az egyéni mérések kialakításához.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-231">The functionality simply allows you to define a set of measures that will be added, and/or a set of measures that will be subtracted, in order to form the custom measurement.</span></span>

<span data-ttu-id="6cc2b-232">Például a következő lekérdezési feltétel esetén az egyéni mértékegységet úgy kell konfigurálni, mint a `MyCustomAvailableforReservation` elemet, hogy a felhasználó rendszer felhasználja a mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-232">For example, with the following query condition, you will configure the custom measurement quantity as `MyCustomAvailableforReservation` to be consumed by the consumption system.</span></span>

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            }
        }
    }
]

```



| <span data-ttu-id="6cc2b-233">Felhasználó rendszer</span><span class="sxs-lookup"><span data-stu-id="6cc2b-233">Consumption system</span></span> | <span data-ttu-id="6cc2b-234">Számított mértékek</span><span class="sxs-lookup"><span data-stu-id="6cc2b-234">Calculated measurers</span></span> | <span data-ttu-id="6cc2b-235">Adatforrás</span><span class="sxs-lookup"><span data-stu-id="6cc2b-235">Data source</span></span> | <span data-ttu-id="6cc2b-236">Módosító</span><span class="sxs-lookup"><span data-stu-id="6cc2b-236">Modifier</span></span> | <span data-ttu-id="6cc2b-237">Módosítószámítási típus</span><span class="sxs-lookup"><span data-stu-id="6cc2b-237">Modifier calculation type</span></span> |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | <span data-ttu-id="6cc2b-238">Hozzáadás</span><span class="sxs-lookup"><span data-stu-id="6cc2b-238">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | <span data-ttu-id="6cc2b-239">Hozzáadás</span><span class="sxs-lookup"><span data-stu-id="6cc2b-239">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | <span data-ttu-id="6cc2b-240">Kivonás</span><span class="sxs-lookup"><span data-stu-id="6cc2b-240">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `inbound` | <span data-ttu-id="6cc2b-241">Hozzáadás</span><span class="sxs-lookup"><span data-stu-id="6cc2b-241">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `outbound` | <span data-ttu-id="6cc2b-242">Kivonás</span><span class="sxs-lookup"><span data-stu-id="6cc2b-242">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `received` | <span data-ttu-id="6cc2b-243">Hozzáadás</span><span class="sxs-lookup"><span data-stu-id="6cc2b-243">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `scheduled` | <span data-ttu-id="6cc2b-244">Hozzáadás</span><span class="sxs-lookup"><span data-stu-id="6cc2b-244">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `issued` | <span data-ttu-id="6cc2b-245">Kivonás</span><span class="sxs-lookup"><span data-stu-id="6cc2b-245">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `reserved` | <span data-ttu-id="6cc2b-246">Kivonás</span><span class="sxs-lookup"><span data-stu-id="6cc2b-246">Subtraction</span></span> |

<span data-ttu-id="6cc2b-247">Ezzel az egyéni mérték mennyiség lekérdezése a következő kimenetet fogja visszaadni.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-247">With that, the query on the custom measurement quantity will return the following output.</span></span>

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CustomChannel": {
                "MyCustomAvailableforReservation": 220.0
            }
        }
    }
]
```

<span data-ttu-id="6cc2b-248">A `MyCustomAvailableforReservation` kimenet az egyéni mértékek számítási beállításán alapul, a következők szerint:</span><span class="sxs-lookup"><span data-stu-id="6cc2b-248">The `MyCustomAvailableforReservation` output is based on the calculation setting in the custom measurements as:</span></span>  
 <span data-ttu-id="6cc2b-249">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span><span class="sxs-lookup"><span data-stu-id="6cc2b-249">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span></span>

### <a name="posting-on-hand-changes"></a><span data-ttu-id="6cc2b-250">Aktuális készletváltoztatások feladása</span><span class="sxs-lookup"><span data-stu-id="6cc2b-250">Posting on-hand changes</span></span>

<span data-ttu-id="6cc2b-251">A pontos URL-cím, amelyre az esemény feladása történik, a földrajzi régiótól függ.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-251">The exact URL that the event will be posted to will depend on your geographical region.</span></span> <span data-ttu-id="6cc2b-252">Ez a következő formát veszi fel:</span><span class="sxs-lookup"><span data-stu-id="6cc2b-252">It will take the form:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand`

<span data-ttu-id="6cc2b-253">Ha hitelesítve van, ez az URL-cím együtt használható a HTTP `POST`-metódussal, amellyel a tényleges módosítási eseményeket elküldheti a szolgáltatásnak.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-253">When authenticated, this URL can be used along with the HTTP `POST` method to send on-hand change events to the service.</span></span>

<span data-ttu-id="6cc2b-254">Speciális fejléc használatos a Dynamics 365-szolgáltatásokkal történő kommunikációra HTTP-kérések révén, megjelölve a Supply Chain Management-példány környezeti azonosítóját, amely az adatokhoz van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-254">A special header is used for communicating with Dynamics 365 services through HTTP requests, denoting the environment ID of the Supply Chain Management instance the data is linked to.</span></span> <span data-ttu-id="6cc2b-255">Példa:</span><span class="sxs-lookup"><span data-stu-id="6cc2b-255">For example:</span></span>

`x-ms-environment-id: 2db79622-f97a-4d64-9844-d12efed41796`

#### <a name="posting-on-hand-changes-query-example-1"></a><span data-ttu-id="6cc2b-256">Az aktuális készleten elvégzett módosításlekérdezések küldése – 1. példa</span><span class="sxs-lookup"><span data-stu-id="6cc2b-256">Posting on-hand changes query example 1</span></span>

<span data-ttu-id="6cc2b-257">Ez a példa egy olyan esetet mutat be, amelyben a dimenzió konfigurációját be kell állítania a Power Appsben.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-257">This example shows a scenario where you will set up the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="6cc2b-258">A dimenzió-hozzárendelés konfigurálásához használja a következő lekérdezést a Power Appsben:</span><span class="sxs-lookup"><span data-stu-id="6cc2b-258">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="6cc2b-259">Itt megadhatja a `dimensionDataSource` elemet és a lekérdezésekben használt egyéni dimenziókat.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-259">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="6cc2b-260">A rendszer automatikusan átváltja az egyéni dimenziókat az alapdimenziókra.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-260">The system will automatically convert custom dimensions to base dimensions.</span></span>

```json
{
    "id": "demo-test-00007",
    "organizationId": "usmf",
    "productId": "MyProduct",
    "quantities": {
        "pos": {
            "Outbound": 1
        }
    },
    "dimensionDataSource": "pos",
    "dimensions": {
        "PosSizeId": "Large",
        "PosColorId": "Red",
        "PosSiteId": "2",
        "PosLocationId": "21"
    }
}
```

#### <a name="posting-on-hand-changes-query-example-2"></a><span data-ttu-id="6cc2b-261">Az aktuális készleten elvégzett módosításlekérdezések küldése – 2. példa</span><span class="sxs-lookup"><span data-stu-id="6cc2b-261">Posting on-hand changes query example 2</span></span>

<span data-ttu-id="6cc2b-262">Ez a példa egy olyan esetet mutat be, amikor nincs beállítva hozzárendelés a dimenziókonfigurációhoz a Power Appsben, így a feladásnak is az alapdimenziókat kell használnia.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-262">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="6cc2b-263">Minden dimenziónak alapdimenziónak kell lennie, ha a `dimensionDataSource` mező null, üres vagy szóköz.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-263">All dimensions must be base dimensions when the `dimensionDataSource` field is null, empty, or whitespace.</span></span>

```json
{
    "id": "demo-test-00007",
    "organizationId": "usmf",
    "productId": "MyProduct",
    "quantities": {
        "pos": {
            "Outbound": 1
        }
    },
    "dimensions": {
        "SizeId": "Large",
        "ColorId": "Red",
        "SiteId": "2",
        "LocationId": "21"
    }
}
```

#### <a name="json-document-field-properties"></a><span data-ttu-id="6cc2b-264">JSON-dokumentummező tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="6cc2b-264">JSON document field properties</span></span>

<span data-ttu-id="6cc2b-265">A JSON-lekérdezés korábban megadott példáiban szereplő mezők a következő táblázatban látható tulajdonságokkal rendelkeznek.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-265">The fields from the JSON query examples provided previously have the properties listed in the following table.</span></span>

| <span data-ttu-id="6cc2b-266">Mezőazonosító</span><span class="sxs-lookup"><span data-stu-id="6cc2b-266">Field ID</span></span> | <span data-ttu-id="6cc2b-267">Leírás</span><span class="sxs-lookup"><span data-stu-id="6cc2b-267">Description</span></span> |
|---|---|
| `id` | <span data-ttu-id="6cc2b-268">A megadott módosítási esemény egyedi azonosítója.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-268">A unique ID for the specific change event.</span></span> <span data-ttu-id="6cc2b-269">Ez az azonosító annak biztosítására szolgál, hogy ha a szolgáltatással folytatott kommunikáció nem sikerül a feladás során, akkor az esemény újraküldése nem eredményezi azt, hogy a rendszer kétszer számolja ugyanazt az eseményt.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-269">This ID is used to ensure that if communication with the service fails during posting, resubmitting the event would not result in the same event being counted twice in the system.</span></span> |
| `organizationId` | <span data-ttu-id="6cc2b-270">Az eseményhez kapcsolt szervezet azonosítója.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-270">The identifier of the organization linked to the event.</span></span> <span data-ttu-id="6cc2b-271">Ez a leképezés a Supply Chain Management-szervezetekre vagy az adatterület-azonosítóra vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-271">This maps to Supply Chain Management organizations or data area IDs.</span></span> |
| `productId` | <span data-ttu-id="6cc2b-272">A kérdéses termék azonosítója.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-272">The identifier of the product in question.</span></span> |
| `quantity` | <span data-ttu-id="6cc2b-273">Az a mennyiség, amellyel az aktuális készletet módosítani kell.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-273">The quantity by which the on-hand needs to be changed.</span></span> <span data-ttu-id="6cc2b-274">Ha például 10 új bagel került fel egy polcra, ez az érték 10 lesz.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-274">If, for instance, 10 new bagels were added to a shelf, this value would be 10.</span></span> <span data-ttu-id="6cc2b-275">Ha 3 bagelt eltávolítanak a polcról vagy eladnak, akkor ez az érték – 3.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-275">If 3 bagels were then removed from the shelf or sold, this value would be -3.</span></span> |
| `dimensionDataSource` | <span data-ttu-id="6cc2b-276">A feladási módosítási eseményben és lekérdezésben használt dimenziók adatforrása.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-276">The data source of the dimensions used in the posting change event and query.</span></span> <span data-ttu-id="6cc2b-277">Az adatforrás megadása esetén a megadott adatforrás egyéni dimenzióit is használhatja.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-277">If you specify the data source, you can use the custom dimensions from the specified data source.</span></span> <span data-ttu-id="6cc2b-278">A dimenzió konfigurálása során a Készlet láthatósága az egyéni dimenziókat az általános alapértelmezett dimenziókra tudja leképezni.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-278">With the dimension configuration, Inventory Visibility can map the custom dimensions to the general default dimensions.</span></span> <span data-ttu-id="6cc2b-279">Ha a `dimensionDataSource` nincs megadva, akkor a lekérdezésekben csak az általános alapértelmezett dimenziókat használhatja.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-279">If the `dimensionDataSource` is not specified, you can only use the general default dimensions in your queries.</span></span>   |
| `dimensions` | <span data-ttu-id="6cc2b-280">A kulcs/érték párok dinamikus csoportja.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-280">A dynamic bag of key/value pairs.</span></span> <span data-ttu-id="6cc2b-281">Ezek a Supply Chain Management néhány dimenziójára kerülnek leképezésre, de hozzáadhat egyéni dimenziókat is (például *Forrás*), amely jelezheti, hogy az esemény a Supply Chain Managementből vagy egy külső rendszerből származik.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-281">These will map to some of the dimensions in Supply Chain Management, but you could also add custom dimensions (like *Source*) that may denote if the event was coming from Supply Chain Management or an external system.</span></span> |

### <a name="querying-current-on-hand"></a><span data-ttu-id="6cc2b-282">Aktuális készlet lekérdezése</span><span class="sxs-lookup"><span data-stu-id="6cc2b-282">Querying current on-hand</span></span>

<span data-ttu-id="6cc2b-283">Az aktuális készlet lekérdezésének végpontja hasonló URL-címmel rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="6cc2b-283">The endpoint for querying the current on-hand will have a similar URL:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand/indexquery`

<span data-ttu-id="6cc2b-284">A rendszer lekérdezi a HTTP `POST` metódussal.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-284">It will be queried with the HTTP `POST` method.</span></span>

#### <a name="current-on-hand-query-example-1"></a><span data-ttu-id="6cc2b-285">Aktuális készleten lévő lekérdezés – 1. példa</span><span class="sxs-lookup"><span data-stu-id="6cc2b-285">Current on-hand query example 1</span></span>

<span data-ttu-id="6cc2b-286">Ez a példa egy olyan esetet mutat be, amelyben a dimenzió konfigurációját már végrehajtották a Power Appsben.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-286">This example shows a scenario where you have already completed the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="6cc2b-287">A dimenzió-hozzárendelés konfigurálásához használja a következő lekérdezést a Power Appsben:</span><span class="sxs-lookup"><span data-stu-id="6cc2b-287">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="6cc2b-288">Itt megadhatja a `dimensionDataSource` elemet és a lekérdezésekben használt egyéni dimenziókat.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-288">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="6cc2b-289">A rendszer automatikusan átváltja az egyéni dimenziókat az alapdimenziókra.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-289">The system will automatically convert custom dimensions to base dimensions.</span></span> <span data-ttu-id="6cc2b-290">Megadhatja a `DimensionDataSource` értéket a `filters` számára, és megadhatja az egyéni dimenziókat mind a `filters` és a `groupByValues` esetében.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-290">You can specify the `DimensionDataSource` in `filters` and specify custom dimensions in both `filters` and `groupByValues`.</span></span> <span data-ttu-id="6cc2b-291">A rendszer automatikusan átváltja az egyéni dimenziókat az alapdimenziókra.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-291">The system will automatically convert custom dimensions to base dimensions.</span></span>

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "DimensionDataSource": ["Pos"],
        "PosLocationId": ["21"],
        "PosSiteId": ["2"],
        "PosColorId": ["Red"]
    },
    "groupByValues": [
        "PosSizeId",
        "PosColorId"
    ],
    "returnNegative": true
}
```

#### <a name="current-on-hand-query-example-2"></a><span data-ttu-id="6cc2b-292">Aktuális készleten lévő lekérdezés – 2. példa</span><span class="sxs-lookup"><span data-stu-id="6cc2b-292">Current on-hand query example 2</span></span>

<span data-ttu-id="6cc2b-293">Ez a példa egy olyan esetet mutat be, amikor nincs beállítva hozzárendelés a dimenziókonfigurációhoz a Power Appsben, így a feladásnak is az alapdimenziókat kell használnia.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-293">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="6cc2b-294">Minden dimenziónak alapdimenziónak kell lennie, ha a `dimensionDataSource` mező a `filters` alatt null, üres vagy szóköz.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-294">All dimensions must be base dimensions when the `dimensionDataSource` field, under `filters` is null, empty, or whitespace.</span></span>

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "LocationId": ["21"],
        "SiteId": ["2"],
        "ColorId": ["Red"]
    },
    "groupByValues": [
        "SizeId",
        "ColorId"
    ],
    "returnNegative": true
}
```

#### <a name="example-return-result"></a><span data-ttu-id="6cc2b-295">Példa visszatérési eredményre</span><span class="sxs-lookup"><span data-stu-id="6cc2b-295">Example return result</span></span>

<span data-ttu-id="6cc2b-296">Az előző példákban megjelenített lekérdezések a következőhöz hasonló eredményt adhatnak vissza.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-296">The queries shown in the previous examples could return a result like this.</span></span>

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CustomChannel": {
                "MyCustomAvailableforReservation": 220.0
            }
        }
    }
]
```

<span data-ttu-id="6cc2b-297">Ne felejtse el, hogy a mennyiségek mezői a mértékek és a hozzájuk kapcsolódó értékek jegyzékeként vannak strukturálva.</span><span class="sxs-lookup"><span data-stu-id="6cc2b-297">Note that the quantities fields are structured as a dictionary of measures and their associated values.</span></span>
