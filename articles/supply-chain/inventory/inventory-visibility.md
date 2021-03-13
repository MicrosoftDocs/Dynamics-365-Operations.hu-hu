---
title: Készlet láthatósága bővítmény
description: Ez a témakör a Készlet láthatósága bővítmény telepítését és konfigurálását ismerteti a Dynamics 365 Supply Chain Management rendszerhez.
author: sherry-zheng
manager: tfehr
ms.date: 10/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 4e6f7e0a3978bbf7e520f8cbcfd27c4cfe507777
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2021
ms.locfileid: "5114670"
---
# <a name="inventory-visibility-add-in"></a><span data-ttu-id="cf95b-103">Készlet láthatósága bővítmény</span><span class="sxs-lookup"><span data-stu-id="cf95b-103">Inventory Visibility Add-in</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

<span data-ttu-id="cf95b-104">A Készlet láthatósága bővítmény egy független és jól méretezhető mikroszolgáltatás, amely lehetővé teszi a valós idejű aktuális készletkövetést, így globális képet nyújt a készlet láthatóságáról.</span><span class="sxs-lookup"><span data-stu-id="cf95b-104">The Inventory Visibility Add-in is an independent and highly scalable microservice that enables real-time on-hand inventory tracking, thus providing a global view of inventory visibility.</span></span>

<span data-ttu-id="cf95b-105">Az aktuális készlethez kapcsolódó összes információt a rendszer közel valós időben exportálja a szolgáltatásba alacsony szintű SQL-integráció révén.</span><span class="sxs-lookup"><span data-stu-id="cf95b-105">All information that relates to on-hand inventory is exported to the service in near real-time through low-level SQL integration.</span></span> <span data-ttu-id="cf95b-106">A külső rendszerek RESTful API-kon keresztül érik el a szolgáltatást, hogy aktuális információkat kérdezzenek le adott dimenziókészletekről, így lekérve a rendelkezésre álló aktuális pozíciók listáját.</span><span class="sxs-lookup"><span data-stu-id="cf95b-106">External systems access the service through RESTful APIs to query on-hand information on given sets of dimensions, thus retrieving a list of available on-hand positions.</span></span>

<span data-ttu-id="cf95b-107">A Készlet láthatósága egy mikroszolgáltatás, amely a Microsoft Dataverse rendszerre épül, ami azt jelenti, hogy bővítheti Power Apps alkalmazások készítésével és Power BI alkalmazásával, hogy személyre szabott funkciókat biztosítson, amelyek megfelelnek az üzleti követelményeknek.</span><span class="sxs-lookup"><span data-stu-id="cf95b-107">Inventory Visibility is a microservice built on Microsoft Dataverse, which means you can extend it by building Power Apps and applying Power BI to provide customized functionality to meet your business requirements.</span></span> <span data-ttu-id="cf95b-108">Lehetőség van az index frissítésére is a készletlekérdezésekhez.</span><span class="sxs-lookup"><span data-stu-id="cf95b-108">It is also possible to upgrade the index to do inventory queries.</span></span>

<span data-ttu-id="cf95b-109">A Készlet láthatósága olyan konfigurációs beállításokat biztosít, amelyek lehetővé teszik, hogy több külső gyártótól származó rendszerrel integrálódjon.</span><span class="sxs-lookup"><span data-stu-id="cf95b-109">Inventory Visibility provides configuration options that let it integrate with multiple third-party systems.</span></span> <span data-ttu-id="cf95b-110">Támogatja a szabványosított készletdimenziót, a testreszabott bővíthetőséget és a szabványosított, konfigurálható számított mennyiségeket.</span><span class="sxs-lookup"><span data-stu-id="cf95b-110">It supports the standardized inventory dimension, customized extensibility, and standardized, configurable calculated quantities.</span></span>

<span data-ttu-id="cf95b-111">Ez a témakör azt ismerteti, hogyan telepítheti és konfigurálhatja az Készlet láthatósága bővítményt a Dynamics 365 Supply Chain Management rendszerhez, és hogyan használhatja az alkalmazásprogramozási felületét (API).</span><span class="sxs-lookup"><span data-stu-id="cf95b-111">This topic describes how to install and configure the Inventory Visibility Add-in for Dynamics 365 Supply Chain Management, and how to use its application programming interface (API).</span></span>

## <a name="install-the-inventory-visibility-add-in"></a><span data-ttu-id="cf95b-112">A Készlet láthatósága bővítmény telepítése</span><span class="sxs-lookup"><span data-stu-id="cf95b-112">Install the Inventory Visibility Add-in</span></span>

<span data-ttu-id="cf95b-113">Telepítenie kell a Készlet láthatósága bővítményt a Microsoft Dynamics Lifecycle Services (LCS) használatával.</span><span class="sxs-lookup"><span data-stu-id="cf95b-113">You need to install the Inventory Visibility Add-in using Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="cf95b-114">Az LCS egy együttműködési portál, amely egy környezetet és rendszeresen frissített szolgáltatások készletét biztosítja, amelyek segítenek a Dynamics 365 Finance and Operations-alkalmazások alkalmazás-életciklusának kezelésében.</span><span class="sxs-lookup"><span data-stu-id="cf95b-114">LCS is a collaboration portal that provides an environment and a set of regularly updated services that help you manage the application lifecycle of your Dynamics 365 Finance and Operations apps.</span></span>

<span data-ttu-id="cf95b-115">További tudnivalókért lásd: [Lifecycle Services-erőforrások](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs).</span><span class="sxs-lookup"><span data-stu-id="cf95b-115">For more information, see [Lifecycle Services resources](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs).</span></span>

### <a name="prerequisites"></a><span data-ttu-id="cf95b-116">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="cf95b-116">Prerequisites</span></span>

<span data-ttu-id="cf95b-117">A Készlet láthatósága bővítmény telepítése előtt a következőket kell tennie:</span><span class="sxs-lookup"><span data-stu-id="cf95b-117">Before you install the Inventory Visibility Add-in, you must do the following:</span></span>

- <span data-ttu-id="cf95b-118">Szerezzen be egy LCS-megvalósítási projektet legalább egy üzembe helyezett környezettel.</span><span class="sxs-lookup"><span data-stu-id="cf95b-118">Obtain an LCS implementation project with at least one environment deployed.</span></span>
- <span data-ttu-id="cf95b-119">Hozza létre az ajánlat bétakulcsait az LCS-ben.</span><span class="sxs-lookup"><span data-stu-id="cf95b-119">Generate the beta keys for your offering in LCS.</span></span>
- <span data-ttu-id="cf95b-120">Engedélyezze a felhasználójának szóló ajánlat bétakulcsait az LCS-ben.</span><span class="sxs-lookup"><span data-stu-id="cf95b-120">Enable the beta keys for your offering for your user in LCS.</span></span>
- <span data-ttu-id="cf95b-121">Lépjen kapcsolatba a Microsoft Készlet láthatósága termékcsapatával, és adja meg a környezeti azonosítót, ahol telepíteni szeretné a Készlet láthatósága bővítményt.</span><span class="sxs-lookup"><span data-stu-id="cf95b-121">Contact the Microsoft Inventory Visibility product team and provide an environment ID where you want to deploy the Inventory Visibility Add-in.</span></span>

<span data-ttu-id="cf95b-122">Ha bármilyen kérdése van ezekkel az előfeltételekkel kapcsolatban, kérjük, forduljon a Készlet láthatósága termékcsapatához.</span><span class="sxs-lookup"><span data-stu-id="cf95b-122">If you have any questions about these prerequisites, please contact the Inventory Visibility product team.</span></span>

### <a name="install-the-add-in"></a><a name="install-add-in"></a><span data-ttu-id="cf95b-123">Telepítse a bővítményt</span><span class="sxs-lookup"><span data-stu-id="cf95b-123">Install the add-in</span></span>

<span data-ttu-id="cf95b-124">A Készlet láthatósága bővítmény telepítéséhez a következőket kell tennie:</span><span class="sxs-lookup"><span data-stu-id="cf95b-124">To install the Inventory Visibility Add-in, do the following:</span></span>

1. <span data-ttu-id="cf95b-125">Jelentkezzen be a [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index) portálra.</span><span class="sxs-lookup"><span data-stu-id="cf95b-125">Sign in to the [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index) portal.</span></span>
1. <span data-ttu-id="cf95b-126">A kezdőlapon válassza ki azt a projektet, amelyben a környezet telepítve van.</span><span class="sxs-lookup"><span data-stu-id="cf95b-126">On the home page, select the project where your environment is deployed.</span></span>
1. <span data-ttu-id="cf95b-127">A projekt oldalon jelölje ki azt a környezetet, amelyben telepíteni szeretné a bővítményt.</span><span class="sxs-lookup"><span data-stu-id="cf95b-127">On the project page, select the environment where you want to install the add-in.</span></span>
1. <span data-ttu-id="cf95b-128">A környezet oldalon görgessen lefelé, amíg meg nem jelenik a **Környezeti bővítmények** szakasz.</span><span class="sxs-lookup"><span data-stu-id="cf95b-128">On the environment page, scroll down until you see the **Environment add-ins** section.</span></span> <span data-ttu-id="cf95b-129">Ha a szakasz nem látható, ellenőrizze, hogy az előfeltétel-bétakulcsok teljes mértékben fel lettek-e dolgozva.</span><span class="sxs-lookup"><span data-stu-id="cf95b-129">If the section isn't visible, make sure the prerequisite beta keys have been fully processed.</span></span>
1. <span data-ttu-id="cf95b-130">A **Környezeti bővítmények** szakaszban válassza az **Új bővítmény telepítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cf95b-130">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>
    <span data-ttu-id="cf95b-131">![A környezeti oldal az LCS-ben](media/inventory-visibility-environment.png "A környezeti oldal az LCS-ben")</span><span class="sxs-lookup"><span data-stu-id="cf95b-131">![The environment page in LCS](media/inventory-visibility-environment.png "The environment page in LCS")</span></span>
1. <span data-ttu-id="cf95b-132">Válassza az **Új bővítmény telepítése** hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="cf95b-132">Select the **Install a new add-in** link.</span></span> <span data-ttu-id="cf95b-133">Megnyílik az elérhető bővítmények listája.</span><span class="sxs-lookup"><span data-stu-id="cf95b-133">A list of available add-ins opens.</span></span>
1. <span data-ttu-id="cf95b-134">Válassza a **Készletszolgáltatás** elemet a listából.</span><span class="sxs-lookup"><span data-stu-id="cf95b-134">Select **Inventory service** from the list.</span></span> <span data-ttu-id="cf95b-135">(Megjegyzés: ez most már lehet, hogy **Készlet láthatósága bővítmény a Dynamics 365 Supply Chain Management rendszerhez** néven szerepel.)</span><span class="sxs-lookup"><span data-stu-id="cf95b-135">(Note, this may now be listed as **Inventory Visibility Add-in for Dynamics 365 Supply Chain Management**.)</span></span>
1. <span data-ttu-id="cf95b-136">Adja meg a környezet alábbi mezőinek értékeit:</span><span class="sxs-lookup"><span data-stu-id="cf95b-136">Enter values for the following fields for your environment:</span></span>

    - <span data-ttu-id="cf95b-137">**AAD alkalmazás azonosítója**</span><span class="sxs-lookup"><span data-stu-id="cf95b-137">**AAD application ID**</span></span>
    - <span data-ttu-id="cf95b-138">**AAD bérlő azonosítója**</span><span class="sxs-lookup"><span data-stu-id="cf95b-138">**AAD tenant ID**</span></span>

    <span data-ttu-id="cf95b-139">![Hozzáadás a beállítási lapon](media/inventory-visibility-setup.png "Hozzáadás a beállítási lapon")</span><span class="sxs-lookup"><span data-stu-id="cf95b-139">![Add in setup page](media/inventory-visibility-setup.png "Add-in setup page")</span></span>

1. <span data-ttu-id="cf95b-140">Fogadja el a feltételeket az **Általános Szerződési feltételek** jelölőnégyzet bejelölésével.</span><span class="sxs-lookup"><span data-stu-id="cf95b-140">Agree to the terms and condition by selecting the **Terms and conditions** check box.</span></span>
1. <span data-ttu-id="cf95b-141">Válassza a **Telepítés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="cf95b-141">Select **Install**.</span></span> <span data-ttu-id="cf95b-142">A bővítmény állapota **Telepítés** értékkel jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="cf95b-142">The status of the add-in will show as **Installing**.</span></span> <span data-ttu-id="cf95b-143">Ha befejeződött, frissítse a lapot, hogy lássa, ahogy a **Telepített** állapotra változik.</span><span class="sxs-lookup"><span data-stu-id="cf95b-143">When it's done, refresh the page to see the status change to **Installed**.</span></span>

### <a name="get-a-security-service-token"></a><span data-ttu-id="cf95b-144">Biztonsági szolgáltatás jogkivonatának beszerzése</span><span class="sxs-lookup"><span data-stu-id="cf95b-144">Get a security service token</span></span>

<span data-ttu-id="cf95b-145">Biztonsági szolgáltatás jogkivonatának beszerzéséhez tegye a következőket:</span><span class="sxs-lookup"><span data-stu-id="cf95b-145">Get a security service token by doing the following:</span></span>

1. <span data-ttu-id="cf95b-146">Jelentkezzen be az Azure Portal webhelyre, és használja a(z) `clientId` és `clientSecret` keresésére a Supply Chain Management alkalmazáshoz.</span><span class="sxs-lookup"><span data-stu-id="cf95b-146">Sign in to Azure Portal and use it to find the `clientId` and `clientSecret` for your Supply Chain Management application.</span></span>
1. <span data-ttu-id="cf95b-147">Azure Active Directory kód beolvasása (`aadToken`) a következő tulajdonságokkal rendelkező HTTP-kérés beküldésével:</span><span class="sxs-lookup"><span data-stu-id="cf95b-147">Fetch an Azure Active Directory token (`aadToken`) by submitting an HTTP request with the following properties:</span></span>
    - <span data-ttu-id="cf95b-148">**URL-cím** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`</span><span class="sxs-lookup"><span data-stu-id="cf95b-148">**URL** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`</span></span>
    - <span data-ttu-id="cf95b-149">**Metódus** - `GET`</span><span class="sxs-lookup"><span data-stu-id="cf95b-149">**Method** - `GET`</span></span>
    - <span data-ttu-id="cf95b-150">**Levél tartalma (űrlapadatok)**:</span><span class="sxs-lookup"><span data-stu-id="cf95b-150">**Body content (form data)**:</span></span>

        | <span data-ttu-id="cf95b-151">kulcs</span><span class="sxs-lookup"><span data-stu-id="cf95b-151">key</span></span> | <span data-ttu-id="cf95b-152">érték</span><span class="sxs-lookup"><span data-stu-id="cf95b-152">value</span></span> |
        | --- | --- |
        | <span data-ttu-id="cf95b-153">ügyfél azonosítója</span><span class="sxs-lookup"><span data-stu-id="cf95b-153">client_id</span></span> | <span data-ttu-id="cf95b-154">${aadAppId}</span><span class="sxs-lookup"><span data-stu-id="cf95b-154">${aadAppId}</span></span> |
        | <span data-ttu-id="cf95b-155">titkos ügyfélkód</span><span class="sxs-lookup"><span data-stu-id="cf95b-155">client_secret</span></span> | <span data-ttu-id="cf95b-156">${aadAppSecret}</span><span class="sxs-lookup"><span data-stu-id="cf95b-156">${aadAppSecret}</span></span> |
        | <span data-ttu-id="cf95b-157">engedélyezési típus</span><span class="sxs-lookup"><span data-stu-id="cf95b-157">grant_type</span></span> | <span data-ttu-id="cf95b-158">ügyfél_azonosító adatai</span><span class="sxs-lookup"><span data-stu-id="cf95b-158">client_credentials</span></span> |
        | <span data-ttu-id="cf95b-159">erőforrás</span><span class="sxs-lookup"><span data-stu-id="cf95b-159">resource</span></span> | <span data-ttu-id="cf95b-160">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span><span class="sxs-lookup"><span data-stu-id="cf95b-160">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span></span> |
1. <span data-ttu-id="cf95b-161">Válaszként egy `aadToken` kódot kell kapnia, amelynek a következő példához kell hasonlítania.</span><span class="sxs-lookup"><span data-stu-id="cf95b-161">You should receive an `aadToken` in response, which resembles the following example.</span></span>

    ```json
    {
    "token_type": "Bearer",
    "expires_in": "3599",
    "ext_expires_in": "3599",
    "expires_on": "1610466645",
    "not_before": "1610462745",
    "resource": "0cdb527f-a8d1-4bf8-9436-b352c68682b2",
    "access_token": "eyJ0eX...8WQ"
    }
    ```

1. <span data-ttu-id="cf95b-162">Fogalmazzon meg egy olyan JSON-kérést, amely hasonlít a következőkre:</span><span class="sxs-lookup"><span data-stu-id="cf95b-162">Formulate a JSON request that resembles the following:</span></span>

    ```json
    {
        "grant_type": "client_credentials",
        "client_assertion_type":"aad_app",
        "client_assertion": "{Your_AADToken}",
        "scope":"https://inventoryservice.operations365.dynamics.com/.default",
        "context": "5dbf6cc8-255e-4de2-8a25-2101cd5649b4",
        "context_type": "finops-env"
    }
    ```

    <span data-ttu-id="cf95b-163">Ahol:</span><span class="sxs-lookup"><span data-stu-id="cf95b-163">Where:</span></span>
    - <span data-ttu-id="cf95b-164">A `client_assertion` értéknek az előző lépésben kapott `aadToken` értéknek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="cf95b-164">The `client_assertion` value must be the `aadToken` you received in the previous step.</span></span>
    - <span data-ttu-id="cf95b-165">A `context` érték az a környezetazonosító, ahová telepíteni szeretné a bővítményt.</span><span class="sxs-lookup"><span data-stu-id="cf95b-165">The `context` value must be the environment ID where you want to deploy the add-in.</span></span>
    - <span data-ttu-id="cf95b-166">Állítsa be az összes többi értéket a példában látható módon.</span><span class="sxs-lookup"><span data-stu-id="cf95b-166">Set all of other values as shown in the example.</span></span>

1. <span data-ttu-id="cf95b-167">HTTP-kérés küldése a következő tulajdonságokkal:</span><span class="sxs-lookup"><span data-stu-id="cf95b-167">Submit an HTTP request with the following properties:</span></span>
    - <span data-ttu-id="cf95b-168">**URL-cím** - `https://securityservice.operations365.dynamics.com/token`</span><span class="sxs-lookup"><span data-stu-id="cf95b-168">**URL** - `https://securityservice.operations365.dynamics.com/token`</span></span>
    - <span data-ttu-id="cf95b-169">**Metódus** - `POST`</span><span class="sxs-lookup"><span data-stu-id="cf95b-169">**Method** - `POST`</span></span>
    - <span data-ttu-id="cf95b-170">**HTTP-fejléc** – tartalmazza az API-verziót (a kulcs `Api-Version` és az érték: `1.0`)</span><span class="sxs-lookup"><span data-stu-id="cf95b-170">**HTTP header** - Include the API version (key is `Api-Version` and value is `1.0`)</span></span>
    - <span data-ttu-id="cf95b-171">**Levél tartalma** – foglalja bele az előző lépésben létrehozott JSON-kérelmet.</span><span class="sxs-lookup"><span data-stu-id="cf95b-171">**Body content** - Include the JSON request that you created in the previous step.</span></span>

1. <span data-ttu-id="cf95b-172">Kap egy `access_token` elemet válaszul.</span><span class="sxs-lookup"><span data-stu-id="cf95b-172">You will get an `access_token` in response.</span></span> <span data-ttu-id="cf95b-173">Ez az, amire szüksége van, mint tulajdonosi jogkivonat, hogy meghívja meg a Készlet láthatósága API-t.</span><span class="sxs-lookup"><span data-stu-id="cf95b-173">This is what you need as a bearer token to call the Inventory Visibility API.</span></span> <span data-ttu-id="cf95b-174">Íme, egy példa.</span><span class="sxs-lookup"><span data-stu-id="cf95b-174">Here is an example.</span></span>

    ```json
    {
        "access_token": "{Returned_Token}",
        "token_type": "bearer",
        "expires_in": 1200
    }
    ```

### <a name="uninstall-the-add-in"></a><span data-ttu-id="cf95b-175">A bővítmény eltávolítása</span><span class="sxs-lookup"><span data-stu-id="cf95b-175">Uninstall the add-in</span></span>

<span data-ttu-id="cf95b-176">A bővítmény eltávolításához válassza az **Eltávolítás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cf95b-176">To uninstall the add-in, select **Uninstall**.</span></span> <span data-ttu-id="cf95b-177">Frissítse az LCS-t, és a Készlet láthatósága bővítmény törlődik.</span><span class="sxs-lookup"><span data-stu-id="cf95b-177">Refresh LCS and the Inventory Visibility Add-in will be removed.</span></span> <span data-ttu-id="cf95b-178">Az eltávolítási folyamat eltávolítja a bővítmény regisztrációját, és elindít egy feladatot a szolgáltatásban tárolt összes üzleti adat törléséhez.</span><span class="sxs-lookup"><span data-stu-id="cf95b-178">The uninstall process will remove the add-in registration and also start a job to clean up all of the business data stored in the service.</span></span>

## <a name="inventory-visibility-add-in-public-api"></a><span data-ttu-id="cf95b-179">Készlet láthatósága bővítmény nyilvános API</span><span class="sxs-lookup"><span data-stu-id="cf95b-179">Inventory Visibility Add-in public API</span></span>

<span data-ttu-id="cf95b-180">A Készlet láthatósága bővítmény nyilvános REST API-ja az integráció több konkrét végpontját mutatja be.</span><span class="sxs-lookup"><span data-stu-id="cf95b-180">The public REST API of the of the Inventory Visibility Add-in presents several specific endpoints of integration.</span></span> <span data-ttu-id="cf95b-181">Három fő interakciós típust támogat:</span><span class="sxs-lookup"><span data-stu-id="cf95b-181">It supports three main interaction types:</span></span>

- <span data-ttu-id="cf95b-182">A bővítmény aktuális módosításainak külső rendszerből történő feladása.</span><span class="sxs-lookup"><span data-stu-id="cf95b-182">Posting on-hand changes to the add-in from an external system.</span></span>
- <span data-ttu-id="cf95b-183">Aktuális rendelkezésre álló mennyiségek lekérdezése külső rendszerből.</span><span class="sxs-lookup"><span data-stu-id="cf95b-183">Querying current on-hand quantities from an external system.</span></span>
- <span data-ttu-id="cf95b-184">Automatikus szinkronizálás a Supply Chain Management aktuális adataival.</span><span class="sxs-lookup"><span data-stu-id="cf95b-184">Automatic synchronization with Supply Chain Management on-hand.</span></span>

<span data-ttu-id="cf95b-185">Az automatikus szinkronizálás nem része a nyilvános API-nak, hanem a rendszer a háttérben kezeli azon környezetek esetében, amelyek engedélyezték a Készlet láthatósága bővítményt.</span><span class="sxs-lookup"><span data-stu-id="cf95b-185">The automatic synchronization isn't part of the public API but is instead handled in the background for environments that have enabled the Inventory Visibility Add-in.</span></span>

### <a name="authentication"></a><span data-ttu-id="cf95b-186">Hitelesítés</span><span class="sxs-lookup"><span data-stu-id="cf95b-186">Authentication</span></span>

<span data-ttu-id="cf95b-187">A platform biztonsági jogkivonata a Készlet láthatósága bővítmény hívására szolgál, ezért létre kell hoznia egy Azure Active Directory-jogkivonatot az Azure Active Directory alkalmazás használatával.</span><span class="sxs-lookup"><span data-stu-id="cf95b-187">The platform security token is used to call the Inventory Visibility Add-in, so you must generate an Azure Active Directory token using your Azure Active Directory application.</span></span>

<span data-ttu-id="cf95b-188">A biztonsági jogkivonat beszerzéséről a [Készlet láthatósága bővítmény telepítése](#install-add-in) című témakörben talál további információt.</span><span class="sxs-lookup"><span data-stu-id="cf95b-188">For more information about how to get the security token, see [Install the Inventory Visibility Add-in](#install-add-in).</span></span>

### <a name="configure-the-inventory-visibility-api"></a><span data-ttu-id="cf95b-189">A Készlet láthatósága API konfigurálása</span><span class="sxs-lookup"><span data-stu-id="cf95b-189">Configure the Inventory Visibility API</span></span>

<span data-ttu-id="cf95b-190">A szolgáltatás használata előtt ki kell töltenie az alábbi alszakaszokban ismertetett konfigurációkat.</span><span class="sxs-lookup"><span data-stu-id="cf95b-190">Before using the service, you must complete the configurations described in the following subsections.</span></span> <span data-ttu-id="cf95b-191">A konfiguráció a környezet részleteitől függően változhat.</span><span class="sxs-lookup"><span data-stu-id="cf95b-191">The configuration may vary based on the details of your environment.</span></span> <span data-ttu-id="cf95b-192">Ez elsősorban négy részből áll:</span><span class="sxs-lookup"><span data-stu-id="cf95b-192">It primarily includes four parts:</span></span>

- [<span data-ttu-id="cf95b-193">Particionálás</span><span class="sxs-lookup"><span data-stu-id="cf95b-193">Partitioning</span></span>](#partitioning)
- [<span data-ttu-id="cf95b-194">Dimenziókonfigurációk</span><span class="sxs-lookup"><span data-stu-id="cf95b-194">Dimension configurations</span></span>](#dimension-configurations)
- [<span data-ttu-id="cf95b-195">Indexelés</span><span class="sxs-lookup"><span data-stu-id="cf95b-195">Indexing</span></span>](#indexing)
- [<span data-ttu-id="cf95b-196">Egyéni mérés</span><span class="sxs-lookup"><span data-stu-id="cf95b-196">Custom measurement</span></span>](#custom-measurement)

#### <a name="partitioning"></a><span data-ttu-id="cf95b-197">Particionálás</span><span class="sxs-lookup"><span data-stu-id="cf95b-197">Partitioning</span></span>

<span data-ttu-id="cf95b-198">A particionálás jelentősen befolyásolhatja a Készlet láthatósága API teljesítményét.</span><span class="sxs-lookup"><span data-stu-id="cf95b-198">Partitioning can significantly influence the performance of the Inventory Visibility API.</span></span> <span data-ttu-id="cf95b-199">Célszerű olyan sémát definiálni, amely lehetővé teszi az adatok kis csoportjait, miközben továbbra is lehetővé teszi az értelmezhető adatlekérdezéseket.</span><span class="sxs-lookup"><span data-stu-id="cf95b-199">It's a good idea to define a scheme that allows for small groupings of data while still allowing for meaningful data queries.</span></span>

<span data-ttu-id="cf95b-200">Az `organizationId` (`dataAreaId` a Supply Chain Management esetében) mindig a particionálás része lesz, és alapértelmezés szerint a Készlet láthatósága dimenziók szerinti particionálásra van beállítva *Telephely + Hely* szerint.</span><span class="sxs-lookup"><span data-stu-id="cf95b-200">The `organizationId` (`dataAreaId` in Supply Chain Management) will always be part of the partitioning, and by default Inventory Visibility is set to partition by dimensions as *Site + Location*.</span></span> <span data-ttu-id="cf95b-201">Ez azt jelenti, hogy a szolgáltatást mindig le kell kérdezni ezekkel a szűrőkön definiált dimenziókkal.</span><span class="sxs-lookup"><span data-stu-id="cf95b-201">This means that the service must always be queried with these dimensions defined on the filters.</span></span>

> [!NOTE]
> <span data-ttu-id="cf95b-202">A *Telephely* és a *Hely* két általános alapértelmezett dimenzió a Készlet láthatóságában.</span><span class="sxs-lookup"><span data-stu-id="cf95b-202">*Site* and *Location* are two general default dimensions in Inventory Visibility.</span></span> <span data-ttu-id="cf95b-203">A Supply Chain Managementben ezeket a dimenziók *Telephely* (`InventSiteId`) és *Raktár* (`InventLocationId`) néven szerepelnek</span><span class="sxs-lookup"><span data-stu-id="cf95b-203">In Supply Chain Management, those dimensions are called *Site* (`InventSiteId`) and *Warehouse* (`InventLocationId`)</span></span>

### <a name="dimension-configurations"></a><span data-ttu-id="cf95b-204">Dimenziókonfigurációk</span><span class="sxs-lookup"><span data-stu-id="cf95b-204">Dimension configurations</span></span>

<span data-ttu-id="cf95b-205">A Készlet láthatósága az általános alapértelmezett dimenziók listáját tartalmazza a több forrásrendszer integrációjának engedélyezéséhez.</span><span class="sxs-lookup"><span data-stu-id="cf95b-205">Inventory Visibility will provide a list of general default dimensions to enable the multiple source system integration.</span></span>

<span data-ttu-id="cf95b-206">Az alábbi táblázat azokat a készletdimenziókat sorolja fel, amelyek a Készlet láthatósága alapértelmezett dimenziónevei lesznek.</span><span class="sxs-lookup"><span data-stu-id="cf95b-206">The following table lists the inventory dimensions that will be the default dimension names in Inventory Visibility.</span></span>

| <span data-ttu-id="cf95b-207">Dimenzió típusa</span><span class="sxs-lookup"><span data-stu-id="cf95b-207">Dimension type</span></span> | <span data-ttu-id="cf95b-208">Dimenzió neve</span><span class="sxs-lookup"><span data-stu-id="cf95b-208">Dimension name</span></span> |
|---|---|
| <span data-ttu-id="cf95b-209">Termék</span><span class="sxs-lookup"><span data-stu-id="cf95b-209">Product</span></span> | `ColorId` |
| <span data-ttu-id="cf95b-210">Termék</span><span class="sxs-lookup"><span data-stu-id="cf95b-210">Product</span></span> | `SizeId` |
| <span data-ttu-id="cf95b-211">Termék</span><span class="sxs-lookup"><span data-stu-id="cf95b-211">Product</span></span> | `StyleId` |
| <span data-ttu-id="cf95b-212">Termék</span><span class="sxs-lookup"><span data-stu-id="cf95b-212">Product</span></span> | `ConfigId` |
| <span data-ttu-id="cf95b-213">Nyomon követés</span><span class="sxs-lookup"><span data-stu-id="cf95b-213">Tracking</span></span> | `BatchId` |
| <span data-ttu-id="cf95b-214">Nyomon követés</span><span class="sxs-lookup"><span data-stu-id="cf95b-214">Tracking</span></span> | `SerialId` |
| <span data-ttu-id="cf95b-215">Helyszín</span><span class="sxs-lookup"><span data-stu-id="cf95b-215">Location</span></span> | `LocationId` |
| <span data-ttu-id="cf95b-216">Helyszín</span><span class="sxs-lookup"><span data-stu-id="cf95b-216">Location</span></span> | `SiteId` |
| <span data-ttu-id="cf95b-217">Készlet állapota</span><span class="sxs-lookup"><span data-stu-id="cf95b-217">Inventory Status</span></span> | `StatusId` |
| <span data-ttu-id="cf95b-218">Raktárspecifikus</span><span class="sxs-lookup"><span data-stu-id="cf95b-218">Warehouse Specific</span></span> | `WMSLocationId` |
| <span data-ttu-id="cf95b-219">Raktárspecifikus</span><span class="sxs-lookup"><span data-stu-id="cf95b-219">Warehouse Specific</span></span> | `WMSPalletId` |
| <span data-ttu-id="cf95b-220">Raktárspecifikus</span><span class="sxs-lookup"><span data-stu-id="cf95b-220">Warehouse Specific</span></span> | `LicensePlateId` |

> [!NOTE]
> <span data-ttu-id="cf95b-221">Az előző táblában felsorolt dimenziótípus csak tájékoztató jellegű.</span><span class="sxs-lookup"><span data-stu-id="cf95b-221">The dimension type listed in the previous table is for reference only.</span></span> <span data-ttu-id="cf95b-222">A dimenziótípust nem kell definiálnia a Készlet láthatósága bővítményben.</span><span class="sxs-lookup"><span data-stu-id="cf95b-222">You don't need to define the dimension type in Inventory Visibility.</span></span>

<span data-ttu-id="cf95b-223">Ha létezik egyéni dimenzió, és a Készlet láthatósága által felhasznált alapértelmezett értékre kell áramlania, az **Egyéni dimenzió** nevét a Készlet láthatóságában konfigurálhatja.</span><span class="sxs-lookup"><span data-stu-id="cf95b-223">If a custom dimension exists and needs to flow to a default value when consumed by Inventory Visibility, you can configure the **Custom dimension** name in Inventory Visibility.</span></span>

<span data-ttu-id="cf95b-224">A külső rendszerek RESTful API-kon keresztül férnek hozzá a Készlet láthatóságához, amelyek lehetővé teszik az adott dimenziókészletek aktuális információinak lekérdezését.</span><span class="sxs-lookup"><span data-stu-id="cf95b-224">External systems access Inventory Visibility through RESTful APIs that enable on-hand information on given sets of dimensions to be queried.</span></span> <span data-ttu-id="cf95b-225">Az integrációhoz a Készlet láthatósága lehetővé teszi a *külső csatorna adatforrásának* és a forrásdimenziónak a Készlet láthatósága *céldimenzióihoz* való konfigurálását.</span><span class="sxs-lookup"><span data-stu-id="cf95b-225">For the integration, Inventory Visibility enables you to configure the *external channel data source* and the source dimension to the *target dimensions* in Inventory Visibility.</span></span>

<span data-ttu-id="cf95b-226">A céldimenzióknak a következők egyikének kell lenniük:</span><span class="sxs-lookup"><span data-stu-id="cf95b-226">The target dimensions should be one of the following:</span></span>

- <span data-ttu-id="cf95b-227">Alapértelmezett dimenziók a Készlet láthatóságában</span><span class="sxs-lookup"><span data-stu-id="cf95b-227">Default dimensions in Inventory Visibility</span></span>
- <span data-ttu-id="cf95b-228">Egyéni dimenziók</span><span class="sxs-lookup"><span data-stu-id="cf95b-228">Custom dimensions</span></span>

<span data-ttu-id="cf95b-229">A dimenziókonfiguráció célja a dimenziókra irányuló lekérdezések és a dimenziókkal való feladási esemény többrendszeres integrációjának szabványosítása.</span><span class="sxs-lookup"><span data-stu-id="cf95b-229">The purpose of dimension configuration is to standardize the multi-system integration for the query on dimensions and the posting event with dimensions.</span></span>

#### <a name="indexing"></a><span data-ttu-id="cf95b-230">Indexelés</span><span class="sxs-lookup"><span data-stu-id="cf95b-230">Indexing</span></span>

<span data-ttu-id="cf95b-231">Az aktuális készlet lekérdezése a legtöbb alkalommal nem csak a legmagasabb "teljes" szinten lesz, de előfordulhat, hogy a készletdimenziók alapján összesítve szeretné látni az eredményeket.</span><span class="sxs-lookup"><span data-stu-id="cf95b-231">Most of the time, the inventory on-hand query will not only be on the highest "total" level, but you may want to see results aggregated based on the inventory dimensions.</span></span>

<span data-ttu-id="cf95b-232">A Készlet láthatósága rugalmasságot biztosít azáltal, hogy lehetővé teszi az indexek beállítását, amelyek a dimenzión vagy a dimenziók kombinációján alapulnak.</span><span class="sxs-lookup"><span data-stu-id="cf95b-232">Inventory Visibility provides flexibility by allowing you to set up the indexes, which are based on the dimension or the combination of the dimensions.</span></span>

> [!NOTE]
> <span data-ttu-id="cf95b-233">Jelenleg csak legfeljebb öt indexet konfigurálhat.</span><span class="sxs-lookup"><span data-stu-id="cf95b-233">Currently, you can only configure indexes to a maximum of five.</span></span> <span data-ttu-id="cf95b-234">Alaposan meg kell fontolnia, hogy melyik dimenziót vagy dimenziókombinációt fogja használni a megvalósítás előtt annak érdekében, hogy megfeleljen az üzleti igényeinek.</span><span class="sxs-lookup"><span data-stu-id="cf95b-234">You need to carefully consider which dimension or dimension combination you will use before the implementation to ensure that it will meet your business needs.</span></span> <span data-ttu-id="cf95b-235">Ha például a következőképpen szeretne lekérdezni a termékeket:</span><span class="sxs-lookup"><span data-stu-id="cf95b-235">For example, if you want to query products as follows:</span></span>

- <span data-ttu-id="cf95b-236">Az összesített termék lekérdezése a *Szín* és *Méret* dimenziókkal.</span><span class="sxs-lookup"><span data-stu-id="cf95b-236">Query the aggregated product on-hand by the *Color* and *Size* dimensions.</span></span>
- <span data-ttu-id="cf95b-237">Bizonyos esetekben csak a termék összesített értékét szeretné lekérdezni.</span><span class="sxs-lookup"><span data-stu-id="cf95b-237">In some cases, you just want to query on the product in total.</span></span>

<span data-ttu-id="cf95b-238">Két indexet kell definiálni a következőképpen:</span><span class="sxs-lookup"><span data-stu-id="cf95b-238">You would have two indexes defined as the following:</span></span>

- `["ColorId", "SizeId"]`
- `[]`

<span data-ttu-id="cf95b-239">Az üres zárójel a partíción belül termékazonosító alapján összesít.</span><span class="sxs-lookup"><span data-stu-id="cf95b-239">The empty bracket will aggregate based on the product ID within the partition.</span></span>

<span data-ttu-id="cf95b-240">Az indexelés határozza meg, hogyan csoportosíthatja az eredményeket a `groupBy` lekérdezési beállítás alapján.</span><span class="sxs-lookup"><span data-stu-id="cf95b-240">The indexing defines how you can group your results based on the `groupBy` query setting.</span></span> <span data-ttu-id="cf95b-241">Ebben az esetben, ha nem határoz meg `groupBy` értékeket, `productid` szerinti összegeket kap.</span><span class="sxs-lookup"><span data-stu-id="cf95b-241">In this case if you don't define any `groupBy` values, you'll get totals by `productid`.</span></span> <span data-ttu-id="cf95b-242">Ellenkező esetben, ha a `groupBy` a `groupBy=ColorId&groupBy=SizeId` értékkel van megadva, a rendszer a különböző szín- és méretkombinációk alapján több sort ad vissza.</span><span class="sxs-lookup"><span data-stu-id="cf95b-242">Otherwise if you define `groupBy` as `groupBy=ColorId&groupBy=SizeId`, you'll get multiple lines returned, based on the different color and size combinations in the system.</span></span>

<span data-ttu-id="cf95b-243">A lekérdezési feltételt a kérelem törzsébe teheti.</span><span class="sxs-lookup"><span data-stu-id="cf95b-243">You can put your query criteria in the request body.</span></span>

<span data-ttu-id="cf95b-244">Itt egy példa a termék szín- és méretkombinációját tartalmazó lekérdezésre.</span><span class="sxs-lookup"><span data-stu-id="cf95b-244">Here is a sample query on the product with color and size combination.</span></span>

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

#### <a name="custom-measurement"></a><span data-ttu-id="cf95b-245">Egyéni mérés</span><span class="sxs-lookup"><span data-stu-id="cf95b-245">Custom measurement</span></span>

<span data-ttu-id="cf95b-246">Az alapértelmezett mértékegység-mennyiségek a Supply Chain Managementhez kötődnek, de előfordulhat, hogy egy olyan mennyiséget kell létrehozni, amely az alapértelmezett mértékegységek kombinációjából áll.</span><span class="sxs-lookup"><span data-stu-id="cf95b-246">The default measurement quantities are linked to Supply Chain Management, however you may want to have a quantity that is made up of a combination of the default measurements.</span></span> <span data-ttu-id="cf95b-247">Ehhez egyéni mennyiségek konfigurációját kell megadni, amely az aktuáliskészlet-lekérdezések kimenetéhez lesz hozzáadva.</span><span class="sxs-lookup"><span data-stu-id="cf95b-247">To do this, you can have a configuration of custom quantities, which will be added to the output of the on-hand queries.</span></span>

<span data-ttu-id="cf95b-248">A funkció segítségével egyszerűen meghatározhat egy sor olyan mért értéket, amelyet hozzá kell adni, és/vagy egy sor olyan mért értéket, amelyet ki kell vonni az egyéni mérések kialakításához.</span><span class="sxs-lookup"><span data-stu-id="cf95b-248">The functionality simply allows you to define a set of measures that will be added, and/or a set of measures that will be subtracted, in order to form the custom measurement.</span></span>

<span data-ttu-id="cf95b-249">Például a következő lekérdezési feltétel esetén az egyéni mértékegységet úgy kell konfigurálni, mint a `MyCustomAvailableforReservation` elemet, hogy a felhasználó rendszer felhasználja a mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="cf95b-249">For example, with the following query condition, you will configure the custom measurement quantity as `MyCustomAvailableforReservation` to be consumed by the consumption system.</span></span>

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



| <span data-ttu-id="cf95b-250">Felhasználó rendszer</span><span class="sxs-lookup"><span data-stu-id="cf95b-250">Consumption system</span></span> | <span data-ttu-id="cf95b-251">Számított mértékek</span><span class="sxs-lookup"><span data-stu-id="cf95b-251">Calculated measurers</span></span> | <span data-ttu-id="cf95b-252">Adatforrás</span><span class="sxs-lookup"><span data-stu-id="cf95b-252">Data source</span></span> | <span data-ttu-id="cf95b-253">Módosító</span><span class="sxs-lookup"><span data-stu-id="cf95b-253">Modifier</span></span> | <span data-ttu-id="cf95b-254">Módosítószámítási típus</span><span class="sxs-lookup"><span data-stu-id="cf95b-254">Modifier calculation type</span></span> |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | <span data-ttu-id="cf95b-255">Hozzáadás</span><span class="sxs-lookup"><span data-stu-id="cf95b-255">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | <span data-ttu-id="cf95b-256">Hozzáadás</span><span class="sxs-lookup"><span data-stu-id="cf95b-256">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | <span data-ttu-id="cf95b-257">Kivonás</span><span class="sxs-lookup"><span data-stu-id="cf95b-257">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `inbound` | <span data-ttu-id="cf95b-258">Hozzáadás</span><span class="sxs-lookup"><span data-stu-id="cf95b-258">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `outbound` | <span data-ttu-id="cf95b-259">Kivonás</span><span class="sxs-lookup"><span data-stu-id="cf95b-259">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `received` | <span data-ttu-id="cf95b-260">Hozzáadás</span><span class="sxs-lookup"><span data-stu-id="cf95b-260">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `scheduled` | <span data-ttu-id="cf95b-261">Hozzáadás</span><span class="sxs-lookup"><span data-stu-id="cf95b-261">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `issued` | <span data-ttu-id="cf95b-262">Kivonás</span><span class="sxs-lookup"><span data-stu-id="cf95b-262">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `reserved` | <span data-ttu-id="cf95b-263">Kivonás</span><span class="sxs-lookup"><span data-stu-id="cf95b-263">Subtraction</span></span> |

<span data-ttu-id="cf95b-264">Ezzel az egyéni mérték mennyiség lekérdezése a következő kimenetet fogja visszaadni.</span><span class="sxs-lookup"><span data-stu-id="cf95b-264">With that, the query on the custom measurement quantity will return the following output.</span></span>

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

<span data-ttu-id="cf95b-265">A `MyCustomAvailableforReservation` kimenet az egyéni mértékek számítási beállításán alapul, a következők szerint:</span><span class="sxs-lookup"><span data-stu-id="cf95b-265">The `MyCustomAvailableforReservation` output is based on the calculation setting in the custom measurements as:</span></span>  
 <span data-ttu-id="cf95b-266">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span><span class="sxs-lookup"><span data-stu-id="cf95b-266">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span></span>

### <a name="posting-on-hand-changes"></a><span data-ttu-id="cf95b-267">Aktuális készletváltoztatások feladása</span><span class="sxs-lookup"><span data-stu-id="cf95b-267">Posting on-hand changes</span></span>

<span data-ttu-id="cf95b-268">A pontos URL-cím, amelyre az esemény feladása történik, a földrajzi régiótól függ.</span><span class="sxs-lookup"><span data-stu-id="cf95b-268">The exact URL that the event will be posted to will depend on your geographical region.</span></span> <span data-ttu-id="cf95b-269">Ez a következő formát veszi fel:</span><span class="sxs-lookup"><span data-stu-id="cf95b-269">It will take the form:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand`

<span data-ttu-id="cf95b-270">Ha hitelesítve van, ez az URL-cím együtt használható a HTTP `POST`-metódussal, amellyel a tényleges módosítási eseményeket elküldheti a szolgáltatásnak.</span><span class="sxs-lookup"><span data-stu-id="cf95b-270">When authenticated, this URL can be used along with the HTTP `POST` method to send on-hand change events to the service.</span></span>

<span data-ttu-id="cf95b-271">Speciális fejléc használatos a Dynamics 365-szolgáltatásokkal történő kommunikációra HTTP-kérések révén, megjelölve a Supply Chain Management-példány környezeti azonosítóját, amely az adatokhoz van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="cf95b-271">A special header is used for communicating with Dynamics 365 services through HTTP requests, denoting the environment ID of the Supply Chain Management instance the data is linked to.</span></span> <span data-ttu-id="cf95b-272">Példa:</span><span class="sxs-lookup"><span data-stu-id="cf95b-272">For example:</span></span>

`x-ms-environment-id: 2db79622-f97a-4d64-9844-d12efed41796`

#### <a name="posting-on-hand-changes-query-example-1"></a><span data-ttu-id="cf95b-273">Az aktuális készleten elvégzett módosításlekérdezések küldése – 1. példa</span><span class="sxs-lookup"><span data-stu-id="cf95b-273">Posting on-hand changes query example 1</span></span>

<span data-ttu-id="cf95b-274">Ez a példa egy olyan esetet mutat be, amelyben a dimenzió konfigurációját be kell állítania a Power Appsben.</span><span class="sxs-lookup"><span data-stu-id="cf95b-274">This example shows a scenario where you will set up the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="cf95b-275">A dimenzió-hozzárendelés konfigurálásához használja a következő lekérdezést a Power Appsben:</span><span class="sxs-lookup"><span data-stu-id="cf95b-275">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="cf95b-276">Itt megadhatja a `dimensionDataSource` elemet és a lekérdezésekben használt egyéni dimenziókat.</span><span class="sxs-lookup"><span data-stu-id="cf95b-276">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="cf95b-277">A rendszer automatikusan átváltja az egyéni dimenziókat az alapdimenziókra.</span><span class="sxs-lookup"><span data-stu-id="cf95b-277">The system will automatically convert custom dimensions to base dimensions.</span></span>

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

#### <a name="posting-on-hand-changes-query-example-2"></a><span data-ttu-id="cf95b-278">Az aktuális készleten elvégzett módosításlekérdezések küldése – 2. példa</span><span class="sxs-lookup"><span data-stu-id="cf95b-278">Posting on-hand changes query example 2</span></span>

<span data-ttu-id="cf95b-279">Ez a példa egy olyan esetet mutat be, amikor nincs beállítva hozzárendelés a dimenziókonfigurációhoz a Power Appsben, így a feladásnak is az alapdimenziókat kell használnia.</span><span class="sxs-lookup"><span data-stu-id="cf95b-279">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="cf95b-280">Minden dimenziónak alapdimenziónak kell lennie, ha a `dimensionDataSource` mező null, üres vagy szóköz.</span><span class="sxs-lookup"><span data-stu-id="cf95b-280">All dimensions must be base dimensions when the `dimensionDataSource` field is null, empty, or whitespace.</span></span>

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

#### <a name="json-document-field-properties"></a><span data-ttu-id="cf95b-281">JSON-dokumentummező tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="cf95b-281">JSON document field properties</span></span>

<span data-ttu-id="cf95b-282">A JSON-lekérdezés korábban megadott példáiban szereplő mezők a következő táblázatban látható tulajdonságokkal rendelkeznek.</span><span class="sxs-lookup"><span data-stu-id="cf95b-282">The fields from the JSON query examples provided previously have the properties listed in the following table.</span></span>

| <span data-ttu-id="cf95b-283">Mezőazonosító</span><span class="sxs-lookup"><span data-stu-id="cf95b-283">Field ID</span></span> | <span data-ttu-id="cf95b-284">Leírás</span><span class="sxs-lookup"><span data-stu-id="cf95b-284">Description</span></span> |
|---|---|
| `id` | <span data-ttu-id="cf95b-285">A megadott módosítási esemény egyedi azonosítója.</span><span class="sxs-lookup"><span data-stu-id="cf95b-285">A unique ID for the specific change event.</span></span> <span data-ttu-id="cf95b-286">Ez az azonosító annak biztosítására szolgál, hogy ha a szolgáltatással folytatott kommunikáció nem sikerül a feladás során, akkor az esemény újraküldése nem eredményezi azt, hogy a rendszer kétszer számolja ugyanazt az eseményt.</span><span class="sxs-lookup"><span data-stu-id="cf95b-286">This ID is used to ensure that if communication with the service fails during posting, resubmitting the event would not result in the same event being counted twice in the system.</span></span> |
| `organizationId` | <span data-ttu-id="cf95b-287">Az eseményhez kapcsolt szervezet azonosítója.</span><span class="sxs-lookup"><span data-stu-id="cf95b-287">The identifier of the organization linked to the event.</span></span> <span data-ttu-id="cf95b-288">Ez a leképezés a Supply Chain Management-szervezetekre vagy az adatterület-azonosítóra vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="cf95b-288">This maps to Supply Chain Management organizations or data area IDs.</span></span> |
| `productId` | <span data-ttu-id="cf95b-289">A kérdéses termék azonosítója.</span><span class="sxs-lookup"><span data-stu-id="cf95b-289">The identifier of the product in question.</span></span> |
| `quantity` | <span data-ttu-id="cf95b-290">Az a mennyiség, amellyel az aktuális készletet módosítani kell.</span><span class="sxs-lookup"><span data-stu-id="cf95b-290">The quantity by which the on-hand needs to be changed.</span></span> <span data-ttu-id="cf95b-291">Ha például 10 új bagel került fel egy polcra, ez az érték 10 lesz.</span><span class="sxs-lookup"><span data-stu-id="cf95b-291">If, for instance, 10 new bagels were added to a shelf, this value would be 10.</span></span> <span data-ttu-id="cf95b-292">Ha 3 bagelt eltávolítanak a polcról vagy eladnak, akkor ez az érték – 3.</span><span class="sxs-lookup"><span data-stu-id="cf95b-292">If 3 bagels were then removed from the shelf or sold, this value would be -3.</span></span> |
| `dimensionDataSource` | <span data-ttu-id="cf95b-293">A feladási módosítási eseményben és lekérdezésben használt dimenziók adatforrása.</span><span class="sxs-lookup"><span data-stu-id="cf95b-293">The data source of the dimensions used in the posting change event and query.</span></span> <span data-ttu-id="cf95b-294">Az adatforrás megadása esetén a megadott adatforrás egyéni dimenzióit is használhatja.</span><span class="sxs-lookup"><span data-stu-id="cf95b-294">If you specify the data source, you can use the custom dimensions from the specified data source.</span></span> <span data-ttu-id="cf95b-295">A dimenzió konfigurálása során a Készlet láthatósága az egyéni dimenziókat az általános alapértelmezett dimenziókra tudja leképezni.</span><span class="sxs-lookup"><span data-stu-id="cf95b-295">With the dimension configuration, Inventory Visibility can map the custom dimensions to the general default dimensions.</span></span> <span data-ttu-id="cf95b-296">Ha a `dimensionDataSource` nincs megadva, akkor a lekérdezésekben csak az általános alapértelmezett dimenziókat használhatja.</span><span class="sxs-lookup"><span data-stu-id="cf95b-296">If the `dimensionDataSource` is not specified, you can only use the general default dimensions in your queries.</span></span>   |
| `dimensions` | <span data-ttu-id="cf95b-297">A kulcs/érték párok dinamikus csoportja.</span><span class="sxs-lookup"><span data-stu-id="cf95b-297">A dynamic bag of key/value pairs.</span></span> <span data-ttu-id="cf95b-298">Ezek a Supply Chain Management néhány dimenziójára kerülnek leképezésre, de hozzáadhat egyéni dimenziókat is (például *Forrás*), amely jelezheti, hogy az esemény a Supply Chain Managementből vagy egy külső rendszerből származik.</span><span class="sxs-lookup"><span data-stu-id="cf95b-298">These will map to some of the dimensions in Supply Chain Management, but you could also add custom dimensions (like *Source*) that may denote if the event was coming from Supply Chain Management or an external system.</span></span> |

### <a name="querying-current-on-hand"></a><span data-ttu-id="cf95b-299">Aktuális készlet lekérdezése</span><span class="sxs-lookup"><span data-stu-id="cf95b-299">Querying current on-hand</span></span>

<span data-ttu-id="cf95b-300">Az aktuális készlet lekérdezésének végpontja hasonló URL-címmel rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="cf95b-300">The endpoint for querying the current on-hand will have a similar URL:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand/indexquery`

<span data-ttu-id="cf95b-301">A rendszer lekérdezi a HTTP `POST` metódussal.</span><span class="sxs-lookup"><span data-stu-id="cf95b-301">It will be queried with the HTTP `POST` method.</span></span>

#### <a name="current-on-hand-query-example-1"></a><span data-ttu-id="cf95b-302">Aktuális készleten lévő lekérdezés – 1. példa</span><span class="sxs-lookup"><span data-stu-id="cf95b-302">Current on-hand query example 1</span></span>

<span data-ttu-id="cf95b-303">Ez a példa egy olyan esetet mutat be, amelyben a dimenzió konfigurációját már végrehajtották a Power Appsben.</span><span class="sxs-lookup"><span data-stu-id="cf95b-303">This example shows a scenario where you have already completed the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="cf95b-304">A dimenzió-hozzárendelés konfigurálásához használja a következő lekérdezést a Power Appsben:</span><span class="sxs-lookup"><span data-stu-id="cf95b-304">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="cf95b-305">Itt megadhatja a `dimensionDataSource` elemet és a lekérdezésekben használt egyéni dimenziókat.</span><span class="sxs-lookup"><span data-stu-id="cf95b-305">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="cf95b-306">A rendszer automatikusan átváltja az egyéni dimenziókat az alapdimenziókra.</span><span class="sxs-lookup"><span data-stu-id="cf95b-306">The system will automatically convert custom dimensions to base dimensions.</span></span> <span data-ttu-id="cf95b-307">Megadhatja a `DimensionDataSource` értéket a `filters` számára, és megadhatja az egyéni dimenziókat mind a `filters` és a `groupByValues` esetében.</span><span class="sxs-lookup"><span data-stu-id="cf95b-307">You can specify the `DimensionDataSource` in `filters` and specify custom dimensions in both `filters` and `groupByValues`.</span></span> <span data-ttu-id="cf95b-308">A rendszer automatikusan átváltja az egyéni dimenziókat az alapdimenziókra.</span><span class="sxs-lookup"><span data-stu-id="cf95b-308">The system will automatically convert custom dimensions to base dimensions.</span></span>

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

#### <a name="current-on-hand-query-example-2"></a><span data-ttu-id="cf95b-309">Aktuális készleten lévő lekérdezés – 2. példa</span><span class="sxs-lookup"><span data-stu-id="cf95b-309">Current on-hand query example 2</span></span>

<span data-ttu-id="cf95b-310">Ez a példa egy olyan esetet mutat be, amikor nincs beállítva hozzárendelés a dimenziókonfigurációhoz a Power Appsben, így a feladásnak is az alapdimenziókat kell használnia.</span><span class="sxs-lookup"><span data-stu-id="cf95b-310">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="cf95b-311">Minden dimenziónak alapdimenziónak kell lennie, ha a `dimensionDataSource` mező a `filters` alatt null, üres vagy szóköz.</span><span class="sxs-lookup"><span data-stu-id="cf95b-311">All dimensions must be base dimensions when the `dimensionDataSource` field, under `filters` is null, empty, or whitespace.</span></span>

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

#### <a name="example-return-result"></a><span data-ttu-id="cf95b-312">Példa visszatérési eredményre</span><span class="sxs-lookup"><span data-stu-id="cf95b-312">Example return result</span></span>

<span data-ttu-id="cf95b-313">Az előző példákban megjelenített lekérdezések a következőhöz hasonló eredményt adhatnak vissza.</span><span class="sxs-lookup"><span data-stu-id="cf95b-313">The queries shown in the previous examples could return a result like this.</span></span>

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

<span data-ttu-id="cf95b-314">Ne felejtse el, hogy a mennyiségek mezői a mértékek és a hozzájuk kapcsolódó értékek jegyzékeként vannak strukturálva.</span><span class="sxs-lookup"><span data-stu-id="cf95b-314">Note that the quantities fields are structured as a dictionary of measures and their associated values.</span></span>
