---
title: A IoT Intelligencia Azure-erőforrásainak beállítása
description: Ez a témakör azt mutatja be, hogyan lehet létrehozni és konfigurálni a Microsoft Azure-erőforrásokat, amelyekre az IoT Intelligencia alkalmazáshoz szükség van.
author: robinarh
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: ''
ms.custom: ''
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 722904aa75a9d95b99c83f39a1d79b9c796714b3
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5821105"
---
# <a name="set-up-azure-resources-for-iot-intelligence"></a><span data-ttu-id="d5da6-103">A IoT Intelligencia Azure-erőforrásainak beállítása</span><span class="sxs-lookup"><span data-stu-id="d5da6-103">Set up Azure resources for IoT Intelligence</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d5da6-104">Ez a témakör azt mutatja be, hogyan lehet létrehozni és konfigurálni a Microsoft Azure-erőforrásokat, amelyekre az IoT Intelligencia alkalmazáshoz szükség van.</span><span class="sxs-lookup"><span data-stu-id="d5da6-104">This topic explains how to create and configure the Microsoft Azure resources that you require for IoT Intelligence.</span></span>

## <a name="create-azure-resources"></a><span data-ttu-id="d5da6-105">Azure-erőforrások létrehozása</span><span class="sxs-lookup"><span data-stu-id="d5da6-105">Create Azure resources</span></span>

<span data-ttu-id="d5da6-106">Hajtsa végre az alábbi lépéseket egy IoT-központ, egy Redis-gyorsítótár és egy a Microsoft Dynamics 365 Supply Chain Management által elérhető kulcstároló létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="d5da6-106">Follow these steps to create an IoT hub, a Redis cache, and a key vault that can be accessed by Microsoft Dynamics 365 Supply Chain Management.</span></span>

### <a name="verify-that-the-microsoft-dynamics-erp-microservices-first-party-app-id-is-in-your-tenant"></a><span data-ttu-id="d5da6-107">Győződjön meg róla, hogy a Microsoft Dynamics ERP Microservices belső alkalmazás azonosítója a bérlőben található.</span><span class="sxs-lookup"><span data-stu-id="d5da6-107">Verify that the Microsoft Dynamics ERP Microservices first-party app ID is in your tenant</span></span>

<span data-ttu-id="d5da6-108">Ha ellenőrizni szeretné, hogy a Microsoft Dynamics ERP Microservices -szolgáltatások belső alkalmazás azonosítója a bérlőben található, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="d5da6-108">To verify that the app ID for the Microsoft Dynamics ERP Microservices first-party app is in your tenant, follow these steps.</span></span>

1. <span data-ttu-id="d5da6-109">Jelentkezzen be az Azure portálon: <https://portal.azure.com>.</span><span class="sxs-lookup"><span data-stu-id="d5da6-109">Sign in to the Azure portal at <https://portal.azure.com>.</span></span>
2. <span data-ttu-id="d5da6-110">Ugorjon ide: **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="d5da6-110">Go to **Azure Active Directory**.</span></span>
3. <span data-ttu-id="d5da6-111">Nyissa meg a **Vállalati alkalmazásokat**.</span><span class="sxs-lookup"><span data-stu-id="d5da6-111">Go to **Enterprise applications**.</span></span>
4. <span data-ttu-id="d5da6-112">Az **Alkalmazás típusa** mezőben válassza ki a **Microsoft-alkalmazások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d5da6-112">In the **Application type** field, select **Microsoft applications**.</span></span>
5. <span data-ttu-id="d5da6-113">A keresőmezőbe írja be a **Microsoft Dynamics ERP Microservices** kifejezést.</span><span class="sxs-lookup"><span data-stu-id="d5da6-113">In the search field, enter **Microsoft Dynamics ERP Microservices**.</span></span>
6. <span data-ttu-id="d5da6-114">Ellenőrizze, hogy a **Microsoft Dynamics ERP Microservices** szerepel-e a listán.</span><span class="sxs-lookup"><span data-stu-id="d5da6-114">Verify that **Microsoft Dynamics ERP Microservices** is in the list.</span></span> <span data-ttu-id="d5da6-115">Más alkalmazások neve hasonló lehet.</span><span class="sxs-lookup"><span data-stu-id="d5da6-115">Other applications have similar names.</span></span> <span data-ttu-id="d5da6-116">Ezért győződjön meg arról, hogy megtalálta a megfelelő alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="d5da6-116">Therefore, make sure that you find the correct application.</span></span> <span data-ttu-id="d5da6-117">Az alkalmazás azonosítója: **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span><span class="sxs-lookup"><span data-stu-id="d5da6-117">The app ID is **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span></span>

    <span data-ttu-id="d5da6-118">Ha az alkalmazás nem szerepel a listában, akkor azt fel kell venni a bérlőhöz:</span><span class="sxs-lookup"><span data-stu-id="d5da6-118">If the application isn't in the list, you must add it to your tenant:</span></span>

    1. <span data-ttu-id="d5da6-119">Az Azure portál eszköztárán válassza ki a gombot az Azure Cloud Shell megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d5da6-119">In the Azure portal, on the toolbar, select the button to open Azure Cloud Shell.</span></span>
    2. <span data-ttu-id="d5da6-120">Futtassa az **Install-Module AzureAD** parancsot.</span><span class="sxs-lookup"><span data-stu-id="d5da6-120">Run the command **Install-Module AzureAD**.</span></span> <span data-ttu-id="d5da6-121">Adja meg az **Y** értéket a modul telepítéséhez.</span><span class="sxs-lookup"><span data-stu-id="d5da6-121">Enter **Y** to install the module.</span></span>
    3. <span data-ttu-id="d5da6-122">Futtassa a **Get-InstalledModule -Name "AzureAD"** parancsot annak ellenőrzéséhez, hogy a modul telepítve van.</span><span class="sxs-lookup"><span data-stu-id="d5da6-122">Run the command **Get-InstalledModule -Name "AzureAD"** to verify that the module is installed.</span></span>
    4. <span data-ttu-id="d5da6-123">Futtassa a **Connect-AzureAD -Confirm** parancsot a hitelesítés futtatásához.</span><span class="sxs-lookup"><span data-stu-id="d5da6-123">Run the command **Connect-AzureAD -Confirm** to run the authentication.</span></span>
    5. <span data-ttu-id="d5da6-124">Futtassa a **New-AzureADServicePrincipal -AppId 0cdb527f-a8d1-4bf8-9436-b352c68682b2** parancsot.</span><span class="sxs-lookup"><span data-stu-id="d5da6-124">Run the command **New-AzureADServicePrincipal -AppId 0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span></span>

    <span data-ttu-id="d5da6-125">Most ismételje meg az 1–6. lépést, és győződjön meg róla, hogy az alkalmazás azonosítója a bérlőben található.</span><span class="sxs-lookup"><span data-stu-id="d5da6-125">You can now repeat steps 1 through 6 to verify that the app ID is in your tenant.</span></span>

### <a name="create-a-key-vault-resource"></a><span data-ttu-id="d5da6-126">Kulcstároló erőforrás létrehozása</span><span class="sxs-lookup"><span data-stu-id="d5da6-126">Create a key vault resource</span></span>

<span data-ttu-id="d5da6-127">Kulcstároló erőforrás létrehozásához az alábbi lépéseket hajtsa végre.</span><span class="sxs-lookup"><span data-stu-id="d5da6-127">To create a key vault resource, follow these steps.</span></span>

1. <span data-ttu-id="d5da6-128">Az Azure portálon hozzon létre vagy nyisson meg egy erőforráscsoportot.</span><span class="sxs-lookup"><span data-stu-id="d5da6-128">In the Azure portal, create or go to a resource group.</span></span>
2. <span data-ttu-id="d5da6-129">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d5da6-129">Select **Add**.</span></span>
3. <span data-ttu-id="d5da6-130">Az **Új** oldalon, a keresés mezőben írja be a **Kulcstároló** értéket.</span><span class="sxs-lookup"><span data-stu-id="d5da6-130">On the **New** page, in the search field, enter **Key vault**.</span></span> <span data-ttu-id="d5da6-131">Ezután válassza a **Létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d5da6-131">Then select **Create**.</span></span>
4. <span data-ttu-id="d5da6-132">A **Kulcstároló létrehozása** oldalon, a **Kulcstároló neve** mezőben adjon meg egy nevet.</span><span class="sxs-lookup"><span data-stu-id="d5da6-132">On the **Create key vault** page, in the **Key vault name** field, enter a name.</span></span>
5. <span data-ttu-id="d5da6-133">Tekintse át az alapértelmezett értékeket, majd válassza az **Ellenőrzés és létrehozás** elemet.</span><span class="sxs-lookup"><span data-stu-id="d5da6-133">Review the default values, and then select **Review + create**.</span></span>
6. <span data-ttu-id="d5da6-134">Válassza a **Létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d5da6-134">Select **Create**.</span></span>

<span data-ttu-id="d5da6-135">A kulcstároló a háttérben jön létre.</span><span class="sxs-lookup"><span data-stu-id="d5da6-135">The key vault is created in the background.</span></span>

### <a name="create-an-iot-hub-resource"></a><span data-ttu-id="d5da6-136">IoT-központ erőforrásának létrehozása</span><span class="sxs-lookup"><span data-stu-id="d5da6-136">Create an IoT hub resource</span></span>

<span data-ttu-id="d5da6-137">Egy IoT-központ erőforrás létrehozásához az alábbi lépéseket hajtsa végre.</span><span class="sxs-lookup"><span data-stu-id="d5da6-137">To create an IoT hub resource, follow these steps.</span></span>

1. <span data-ttu-id="d5da6-138">Hozzon létre vagy nyisson meg egy erőforráscsoportot.</span><span class="sxs-lookup"><span data-stu-id="d5da6-138">Create or go to a resource group.</span></span>
2. <span data-ttu-id="d5da6-139">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d5da6-139">Select **Add**.</span></span>
3. <span data-ttu-id="d5da6-140">Az **Új** oldalon, a keresés mezőben írja be az **IoT-központ** értéket.</span><span class="sxs-lookup"><span data-stu-id="d5da6-140">On the **New** page, in the search field, enter **Iot Hub**.</span></span> <span data-ttu-id="d5da6-141">Ezután válassza a **Létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d5da6-141">Then select **Create**.</span></span>
4. <span data-ttu-id="d5da6-142">Az **IoT-központ neve** mezőben adjon meg egy nevet.</span><span class="sxs-lookup"><span data-stu-id="d5da6-142">In the **IoT hub name** field, enter a name.</span></span>
5. <span data-ttu-id="d5da6-143">Tekintse át az alapértelmezett értékeket, majd válassza az **Ellenőrzés és létrehozás** elemet.</span><span class="sxs-lookup"><span data-stu-id="d5da6-143">Review the default values, and then select **Review + create**.</span></span>
6. <span data-ttu-id="d5da6-144">Válassza a **Létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d5da6-144">Select **Create**.</span></span>

<span data-ttu-id="d5da6-145">Az IoT-központ a háttérben jön létre.</span><span class="sxs-lookup"><span data-stu-id="d5da6-145">The IoT hub is created in the background.</span></span>

> [!NOTE]
> <span data-ttu-id="d5da6-146">Azt ajánljuk, hogy az egyes környezetekben csak egy IoT-központ erőforrást hozzon létre.</span><span class="sxs-lookup"><span data-stu-id="d5da6-146">We recommend that you create only one IoT hub resource per environment.</span></span>

### <a name="create-a-redis-cache-resource"></a><span data-ttu-id="d5da6-147">Redis-gyorsítótár erőforrásának létrehozása</span><span class="sxs-lookup"><span data-stu-id="d5da6-147">Create a Redis cache resource</span></span>

<span data-ttu-id="d5da6-148">Redis-gyorsítótár erőforrás létrehozásához az alábbi lépéseket hajtsa végre.</span><span class="sxs-lookup"><span data-stu-id="d5da6-148">To create a Redis cache resource, follow these steps.</span></span>

1. <span data-ttu-id="d5da6-149">Hozzon létre vagy nyisson meg egy erőforráscsoportot.</span><span class="sxs-lookup"><span data-stu-id="d5da6-149">Create or go to a resource group.</span></span>
2. <span data-ttu-id="d5da6-150">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d5da6-150">Select **Add**.</span></span>
3. <span data-ttu-id="d5da6-151">Az **Új** oldalon, a keresés mezőben írja be az **Azure gyorsítótár Redig számára** értéket.</span><span class="sxs-lookup"><span data-stu-id="d5da6-151">On the **New** page, in the search field, enter **Azure Cache for Redis**.</span></span> <span data-ttu-id="d5da6-152">Ezután válassza a **Létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d5da6-152">Then select **Create**.</span></span>
4. <span data-ttu-id="d5da6-153">A **DNS-név** mezőben adjon meg egy nevet.</span><span class="sxs-lookup"><span data-stu-id="d5da6-153">In the **DNS name** field, enter a name.</span></span>
5. <span data-ttu-id="d5da6-154">Tekintse át az alapértelmezett értékeket, majd válassza a **Létrehozás** elemet.</span><span class="sxs-lookup"><span data-stu-id="d5da6-154">Review the default values, and then select **Create**.</span></span>

<span data-ttu-id="d5da6-155">A Redis-gyorsítótár a háttérben jön létre.</span><span class="sxs-lookup"><span data-stu-id="d5da6-155">The Redis cache is created in the background.</span></span>

> [!NOTE]
> <span data-ttu-id="d5da6-156">Azt ajánljuk, hogy az egyes környezetekben csak egy Redis-gyorsítótárat hozzon létre.</span><span class="sxs-lookup"><span data-stu-id="d5da6-156">We recommend that you create only one Redis cache per environment.</span></span>

<span data-ttu-id="d5da6-157">Az összes erőforrás létrehozásra került.</span><span class="sxs-lookup"><span data-stu-id="d5da6-157">All the resources have now been created.</span></span>

## <a name="configure-the-azure-resources"></a><span data-ttu-id="d5da6-158">Az Azure-erőforrások konfigurálása</span><span class="sxs-lookup"><span data-stu-id="d5da6-158">Configure the Azure resources</span></span>

### <a name="configure-the-iot-hub"></a><span data-ttu-id="d5da6-159">Az IoT-központ konfigurálása</span><span class="sxs-lookup"><span data-stu-id="d5da6-159">Configure the IoT hub</span></span>

<span data-ttu-id="d5da6-160">Az IoT-központ konfigurálásához tegye a következőket.</span><span class="sxs-lookup"><span data-stu-id="d5da6-160">To configure the IoT hub, follow these steps.</span></span>

1. <span data-ttu-id="d5da6-161">Válassza ki az IoT-központ erőforrását az erőforrások között.</span><span class="sxs-lookup"><span data-stu-id="d5da6-161">In your resources, select the IoT hub resource.</span></span>
2. <span data-ttu-id="d5da6-162">A bal oldali navigációs ablakban válassza a **Beépített végpontok** elemet.</span><span class="sxs-lookup"><span data-stu-id="d5da6-162">In the left navigation pane, select **Built-in endpoints**.</span></span>
3. <span data-ttu-id="d5da6-163">A **Fogyasztói csoportok** területen illessze be a következő fogyasztói csoportokat.</span><span class="sxs-lookup"><span data-stu-id="d5da6-163">Under **Consumer groups**, paste the following consumer groups.</span></span> <span data-ttu-id="d5da6-164">Ezek a fogyasztói csoportok megfelelnek a nem beépített eseteknek.</span><span class="sxs-lookup"><span data-stu-id="d5da6-164">These consumer groups correspond to the out-of-box scenarios.</span></span>

    + <span data-ttu-id="d5da6-165">microsoft.dynamics.iotintelligence-1</span><span class="sxs-lookup"><span data-stu-id="d5da6-165">microsoft.dynamics.iotintelligence-1</span></span>
    + <span data-ttu-id="d5da6-166">microsoft.dynamics.iotintelligence-2</span><span class="sxs-lookup"><span data-stu-id="d5da6-166">microsoft.dynamics.iotintelligence-2</span></span>
    + <span data-ttu-id="d5da6-167">microsoft.dynamics.iotintelligence-3</span><span class="sxs-lookup"><span data-stu-id="d5da6-167">microsoft.dynamics.iotintelligence-3</span></span>

### <a name="configure-the-key-vault"></a><span data-ttu-id="d5da6-168">A kulcstároló konfigurálása</span><span class="sxs-lookup"><span data-stu-id="d5da6-168">Configure the key vault</span></span>

<span data-ttu-id="d5da6-169">A kulcstároló konfigurálásához tegye a következőket.</span><span class="sxs-lookup"><span data-stu-id="d5da6-169">To configure the key vault, follow these steps.</span></span>

1. <span data-ttu-id="d5da6-170">Válassza ki a kulcstároló erőforrását az erőforrások között.</span><span class="sxs-lookup"><span data-stu-id="d5da6-170">In your resources, select the key vault resource.</span></span>
2. <span data-ttu-id="d5da6-171">A bal oldali navigációs ablakban válassza ki a **Hozzáférési irányelvek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d5da6-171">In the left navigation pane, select **Access policies**.</span></span>
3. <span data-ttu-id="d5da6-172">Válassza a **Hozzáférési irányelv hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d5da6-172">Select **Add an access policy**.</span></span>
4. <span data-ttu-id="d5da6-173">A **Hozzáférési irányelv hozzáadása** oldalon, a **Titkos engedélyek** mezőben válassza a **Beolvasás** és a **Lista** elemet.</span><span class="sxs-lookup"><span data-stu-id="d5da6-173">On the **Add access policy** page, in the **Secret permissions** field, select **Get** and **List**.</span></span>
5. <span data-ttu-id="d5da6-174">Kattintson a **Főszolgáltató kiválasztása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d5da6-174">Click in the **Select principal**.</span></span>
6. <span data-ttu-id="d5da6-175">A **Főszolgáltató** párbeszédpanelen keresse meg és válassza ki a **Microsoft Dynamics ERP Microservices** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d5da6-175">In the **Principal** dialog box, search for and select **Microsoft Dynamics ERP Microservices**.</span></span> <span data-ttu-id="d5da6-176">Ezután válassza a **Kiválasztás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d5da6-176">Then select **Select**.</span></span>
7. <span data-ttu-id="d5da6-177">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d5da6-177">Select **Add**.</span></span>
8. <span data-ttu-id="d5da6-178">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d5da6-178">Select **Save**.</span></span>

<span data-ttu-id="d5da6-179">Az alkalmazásnak most már van hozzáférése a kulcstároló titkos kódjaihoz.</span><span class="sxs-lookup"><span data-stu-id="d5da6-179">The app now has access to the secrets in the key vault.</span></span>

### <a name="save-the-iot-hub-connection-string-secret"></a><span data-ttu-id="d5da6-180">Mentse az IoT-központ titkos kapcsolati karakterláncát</span><span class="sxs-lookup"><span data-stu-id="d5da6-180">Save the IoT hub connection string secret</span></span>

<span data-ttu-id="d5da6-181">Az IoT-központ kapcsolati karakterláncához tartozó titkos kód mentéséhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="d5da6-181">To save the secret for the IoT hub connection string, follow these steps.</span></span>

1. <span data-ttu-id="d5da6-182">Válassza ki az IoT-központ erőforrását az erőforrások között.</span><span class="sxs-lookup"><span data-stu-id="d5da6-182">In your resources, select the IoT hub resource.</span></span>
2. <span data-ttu-id="d5da6-183">A bal oldali navigációs ablakban válassza a **Beépített végpontok** elemet.</span><span class="sxs-lookup"><span data-stu-id="d5da6-183">In the left navigation pane, select **Built-in endpoints**.</span></span>
3. <span data-ttu-id="d5da6-184">Másolja az értéket az **Eseményközpont-kompatibilis végpont** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="d5da6-184">Copy the value in the **Event Hub-compatible endpoint** field.</span></span>
4. <span data-ttu-id="d5da6-185">Ugrás a kulcstároló-erőforrásra.</span><span class="sxs-lookup"><span data-stu-id="d5da6-185">Go to the key vault resource.</span></span>
5. <span data-ttu-id="d5da6-186">A bal oldali navigációs ablakban válassza ki a **Titkos kódok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d5da6-186">In the left navigation pane, select **Secrets**.</span></span>
6. <span data-ttu-id="d5da6-187">Válassza a **Generálás/Importálás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d5da6-187">Select **Generate/Import**.</span></span>
7. <span data-ttu-id="d5da6-188">A **Név** mezőben adjon meg egy nevet.</span><span class="sxs-lookup"><span data-stu-id="d5da6-188">In the **Name** field, enter a name.</span></span>
8. <span data-ttu-id="d5da6-189">Az **Érték** mezőbe illessze be a korábban másolt végpontértéket.</span><span class="sxs-lookup"><span data-stu-id="d5da6-189">In the **Value** field, paste the endpoint value that you copied earlier.</span></span>
9. <span data-ttu-id="d5da6-190">Válassza a **Létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d5da6-190">Select **Create**.</span></span>

### <a name="save-the-redis-cache-connection-string-secret"></a><span data-ttu-id="d5da6-191">A Redis-gyorsítótár titkos kapcsolati karakterláncának mentése</span><span class="sxs-lookup"><span data-stu-id="d5da6-191">Save the Redis cache connection string secret</span></span>

<span data-ttu-id="d5da6-192">A Redis-gyorsítótár kapcsolati karakterláncához tartozó titkos kód mentéséhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="d5da6-192">To save the secret for the Redis cache connection string, follow these steps.</span></span>

1. <span data-ttu-id="d5da6-193">Válassza ki a Redis-gyorsítótár erőforrását az erőforrások között.</span><span class="sxs-lookup"><span data-stu-id="d5da6-193">In your resources, select the Redis cache resource.</span></span>
2. <span data-ttu-id="d5da6-194">Válassza a **Hozzáférési kulcsok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d5da6-194">Select **Access keys**.</span></span>
3. <span data-ttu-id="d5da6-195">Másolja az **Elsődleges kapcsolati karakterlánc** mező értékét.</span><span class="sxs-lookup"><span data-stu-id="d5da6-195">Copy the value in the **Primary connection string** field.</span></span>
4. <span data-ttu-id="d5da6-196">Ugrás a kulcstároló-erőforrásra.</span><span class="sxs-lookup"><span data-stu-id="d5da6-196">Go to the key vault resource.</span></span>
5. <span data-ttu-id="d5da6-197">A bal oldali navigációs ablakban válassza ki a **Titkos kódok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d5da6-197">In the left navigation pane, select **Secrets**.</span></span>
6. <span data-ttu-id="d5da6-198">Válassza a **Generálás/Importálás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d5da6-198">Select **Generate/Import**.</span></span>
7. <span data-ttu-id="d5da6-199">A **Név** mezőben adjon meg egy nevet.</span><span class="sxs-lookup"><span data-stu-id="d5da6-199">In the **Name** field, enter a name.</span></span>
8. <span data-ttu-id="d5da6-200">Az **Érték** mezőbe illessze be a korábban másolt kapcsolati karakterláncot.</span><span class="sxs-lookup"><span data-stu-id="d5da6-200">In the **Value** field, paste the connection string that you copied earlier.</span></span>
9. <span data-ttu-id="d5da6-201">Válassza a **Létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d5da6-201">Select **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="d5da6-202">Minden alkalommal, amikor frissít egy kapcsolati karakterláncot, frissítenie kell a titkos értékeket is.</span><span class="sxs-lookup"><span data-stu-id="d5da6-202">Whenever you update one of the connection strings, you must also update the secret values.</span></span>

<span data-ttu-id="d5da6-203">Most befejezte a szükséges Azure-erőforrások létesítését.</span><span class="sxs-lookup"><span data-stu-id="d5da6-203">You've now finished provisioning the required Azure resources.</span></span> <span data-ttu-id="d5da6-204">A következő lépés az [IoT Intelligencia beépülő modul telepítése a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban](iot-lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="d5da6-204">The next step is to [install the IoT Intelligence add-in in Microsoft Dynamics Lifecycle Services (LCS)](iot-lcs-setup.md).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]