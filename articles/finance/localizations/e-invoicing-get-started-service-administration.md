---
title: Első lépések az Elektronikus számlázási bővítmény szolgáltatásfelügyeletének használata során
description: Ez a témakör bemutatja az Elektronikus számlázási bővítmény szolgáltatásfelügyeletének használatának első lépéseit.
author: gionoder
manager: AnnBe
ms.date: 03/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 05b00380cec7511adad2467d3f252799a4aaee5c
ms.sourcegitcommit: 543772ee97efe215cf6f2ec6e092cc1568919f20
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/13/2021
ms.locfileid: "5592526"
---
# <a name="get-started-with-electronic-invoicing-add-on-service-administration"></a><span data-ttu-id="9ddbc-103">Első lépések az Elektronikus számlázási bővítmény szolgáltatásfelügyeletének használata során</span><span class="sxs-lookup"><span data-stu-id="9ddbc-103">Get started with Electronic invoicing add-on service administration</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

## <a name="prerequisites"></a><span data-ttu-id="9ddbc-104">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="9ddbc-104">Prerequisites</span></span>

<span data-ttu-id="9ddbc-105">Mielőtt teljesítené az ebben a témakörben ismertetett eljárásokat, a következő előfeltételeknek kell megfelelnie:</span><span class="sxs-lookup"><span data-stu-id="9ddbc-105">Before you complete the procedures in this topic, the following prerequisites must be in place:</span></span>

- <span data-ttu-id="9ddbc-106">Hozzá kell férnie a Microsoft Dynamics Lifecycle Services (LCS) fiókjához.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-106">You must have access to your Microsoft Dynamics Lifecycle Services (LCS) account.</span></span>
- <span data-ttu-id="9ddbc-107">Olyan LCS-projekttel kell rendelkeznie, amely a Microsoft Dynamics 365 Finance és a Dynamics 365 Supply Chain Management 10.0.17-as vagy újabb verzióját tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-107">You must have an LCS project that includes version 10.0.17 or later of Microsoft Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="9ddbc-108">Ezenkívül ezeket az alkalmazásokat a következő Azure földrajzi régiók egyikében kell telepíteni:</span><span class="sxs-lookup"><span data-stu-id="9ddbc-108">Additionally, these apps must be deployed in one of the following Azure geographies:</span></span>

    - <span data-ttu-id="9ddbc-109">USA keleti régiója</span><span class="sxs-lookup"><span data-stu-id="9ddbc-109">East US</span></span>
    - <span data-ttu-id="9ddbc-110">USA nyugati régiója</span><span class="sxs-lookup"><span data-stu-id="9ddbc-110">West US</span></span>
    - <span data-ttu-id="9ddbc-111">Észak-EU</span><span class="sxs-lookup"><span data-stu-id="9ddbc-111">North EU</span></span>
    - <span data-ttu-id="9ddbc-112">Nyugat-EU</span><span class="sxs-lookup"><span data-stu-id="9ddbc-112">West EU</span></span>

- <span data-ttu-id="9ddbc-113">Hozzá kell férnie a Dynamics 365 Regulatory Configuration Services (RCS) fiókjához.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-113">You must have access to your Dynamics 365 Regulatory Configuration Services (RCS) account.</span></span>
- <span data-ttu-id="9ddbc-114">Aktiválnia kell a Globalizációs funkciót az RCS-fiókjához a Funkciókezelőben.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-114">You must activate the Globalization feature for your RCS account in Feature management.</span></span> <span data-ttu-id="9ddbc-115">További információért lásd a [Kapcsolódás a Regulatory Configuration Services (RCS) szolgáltatáshoz – Globalizációs funkciók](rcs-globalization-feature.md) részt.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-115">For more information, see [Regulatory Configuration Services (RCS) - Globalization features](rcs-globalization-feature.md).</span></span>
- <span data-ttu-id="9ddbc-116">Létre kell hoznia egy kulcstartót és egy tárfiókot az Azure szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-116">You must create a key vault and a storage account in Azure.</span></span> <span data-ttu-id="9ddbc-117">További információért lásd az [Azure tárfiók és kulcstartó létrehozása](e-invoicing-create-azure-storage-account-key-vault.md) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-117">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>

## <a name="install-the-add-on-for-microservices-in-lifecycle-services"></a><span data-ttu-id="9ddbc-118">A mikroszolgáltatások bővítményének telepítése a Lifecycle Services szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="9ddbc-118">Install the add-on for microservices in Lifecycle Services</span></span>

1. <span data-ttu-id="9ddbc-119">Jelentkezzen be a LCS-fiók.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-119">Sign in to your LCS account.</span></span>
2. <span data-ttu-id="9ddbc-120">Válassza az **Előzetes funkció kezelése** csempe lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-120">Select the **Preview feature management** tile.</span></span>
3. <span data-ttu-id="9ddbc-121">A **Nyilvános előzetes verzió** szakaszban válassza az **e-számlázási szolgáltatás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-121">In the **Public Preview Features** section, select **e-Invoicing service**.</span></span>
4. <span data-ttu-id="9ddbc-122">Ellenőrizze, hogy az **Előzetes funkció engedélyezve** értéke **Igen** értékre van-e állítva.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-122">Make sure that the **Preview feature enabled** option is set to **Yes**.</span></span>
5. <span data-ttu-id="9ddbc-123">Válassza ki az LCS-telepítési projektet az LCS-irányítópulton.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-123">On your LCS dashboard, select your LCS deployment project.</span></span> <span data-ttu-id="9ddbc-124">Az LCS-projektnek futnia kell.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-124">The LCS project must be running.</span></span>
7. <span data-ttu-id="9ddbc-125">A **Környezetbővítmények** lapon válassza az **Új bővítmény telepítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-125">On the **Environment add-ins** tab, select **Install a new add-in**.</span></span>
8. <span data-ttu-id="9ddbc-126">Válassza ki az **e-számlázási szolgáltatások** lehetőséget, az **AAD alkalmazás azonosítója** mezőbe pedig írja be a következőt: **091c98b0-a1c9-4b02-b62c-7753395ccabe**.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-126">Select **e-invoicing Services** and in the **AAD application ID** field, enter **091c98b0-a1c9-4b02-b62c-7753395ccabe**.</span></span> <span data-ttu-id="9ddbc-127">Ez egy rögzített érték.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-127">This is a fixed value.</span></span>
10. <span data-ttu-id="9ddbc-128">Az **AAD-bérlőazonosító** mezőbe írja be az Azure előfizetési fiókja bérlőazonosítóját.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-128">In the **AAD tenant ID** field, enter the tenant ID of your Azure subscription account.</span></span>
11. <span data-ttu-id="9ddbc-129">Olvassa el az Általános Szerződési Feltételeket, majd jelölje be a jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-129">Review the terms and conditions, and then select the check box.</span></span>
12. <span data-ttu-id="9ddbc-130">Válassza a **Telepítés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-130">Select **Install**.</span></span>


## <a name="set-up-the-parameters-for-rcs-integration-with-the-electronic-invoicing-add-on"></a><span data-ttu-id="9ddbc-131">RCS-integráció paramétereinek beállítása az Elektronikus számlázási bővítménnyel</span><span class="sxs-lookup"><span data-stu-id="9ddbc-131">Set up the parameters for RCS integration with the Electronic invoicing add-on</span></span>

1. <span data-ttu-id="9ddbc-132">Jelentkezzen be a RCS-fiókba.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-132">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="9ddbc-133">Az **Elektronikus jelentéskészítés** munkaterületen, a **Kapcsolódó hivatkozások** szakaszban, válassza az **Elektronikus jelentéskészítés paraméterei** elemet.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-133">In the **Electronic reporting** workspace, in the **Related links** section, select **Electronic reporting parameters**.</span></span>
3. <span data-ttu-id="9ddbc-134">Az **e-számlázási szolgáltatás** lapon a **Szolgáltatási végpont URI** mezőben adja meg az Azure földrajzi régió megfelelő szolgáltatási végpontját, amint azt a következő tábla mutatja.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-134">On the **e-Invoicing service** tab, in the **Service endpoint URI** field, enter the appropriate service endpoint for your Azure geography, as shown in the following table.</span></span>

    | <span data-ttu-id="9ddbc-135">Adatközpont Azure földrajzi régió</span><span class="sxs-lookup"><span data-stu-id="9ddbc-135">Datacenter Azure geography</span></span> | <span data-ttu-id="9ddbc-136">Szolgáltatási végpont URI-címe</span><span class="sxs-lookup"><span data-stu-id="9ddbc-136">Service endpoint URI</span></span>                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | <span data-ttu-id="9ddbc-137">USA keleti régiója</span><span class="sxs-lookup"><span data-stu-id="9ddbc-137">East US</span></span>                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="9ddbc-138">USA nyugati régiója</span><span class="sxs-lookup"><span data-stu-id="9ddbc-138">West US</span></span>                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="9ddbc-139">Észak-EU</span><span class="sxs-lookup"><span data-stu-id="9ddbc-139">North EU</span></span>                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="9ddbc-140">Nyugat-EU</span><span class="sxs-lookup"><span data-stu-id="9ddbc-140">West EU</span></span>                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

4. <span data-ttu-id="9ddbc-141">Ellenőrizze, hogy az **Alkalmazásazonosító** mező **0cdb527f-a8d1-4bf8-9436-b352c68682b2** értékre legyen állítva.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-141">Verify that the **Application Id** field is set to **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span></span> <span data-ttu-id="9ddbc-142">Ez egy rögzített érték.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-142">This value is a fixed value.</span></span>
5. <span data-ttu-id="9ddbc-143">Az **LCS-környezet azonosítója** mezőbe írja be az LCS előfizetési fiókja azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-143">In the **LCS Environment Id** field, enter the ID of your LCS subscription account.</span></span>
6. <span data-ttu-id="9ddbc-144">Válassza a **Mentés** gombot, majd zárja be az oldalt.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-144">Select **Save**, and then close the page.</span></span>

## <a name="create-key-vault-secret"></a><span data-ttu-id="9ddbc-145">Key Vault titkos kód létrehozása</span><span class="sxs-lookup"><span data-stu-id="9ddbc-145">Create Key Vault secret</span></span>

1. <span data-ttu-id="9ddbc-146">Jelentkezzen be a RCS-fiókba.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-146">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="9ddbc-147">A **Globalizációs funkció** munkaterületen a **Környezet** szakaszban válassza ki az **Elektronikus számlázás bővítmény** csempét.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-147">In the **Globalization feature** workspace, in the **Environment** section, select the **Electronic invoicing add-on** tile.</span></span>
3. <span data-ttu-id="9ddbc-148">A **Környezet beállítása** lapon a Művelet ablaktáblán válassza ki a **Szolgáltatási környezet**, majd a **Key Vault-paraméterek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-148">On the **Environment setups** page, on the action Pane, select **Service environment**, and then select **Key Vault parameters**.</span></span>
4. <span data-ttu-id="9ddbc-149">Kulcstartó titkos kód létrehozásához válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-149">Select **New** to create a key vault secret.</span></span>
5. <span data-ttu-id="9ddbc-150">A **Név** mezőben adja meg a kulcstartó titkos kód nevét.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-150">In the **Name** field, enter the name of the key vault secret.</span></span> <span data-ttu-id="9ddbc-151">Adjon meg egy leírást a **Leírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-151">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="9ddbc-152">A **Key Vault – URI** mezőbe másolja be a titkos kódot az Azure Key Vault megoldásból.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-152">In the **Key Vault URI** field, paste the secret from Azure Key Vault.</span></span>
7. <span data-ttu-id="9ddbc-153">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-153">Select **Save**.</span></span>

## <a name="create-storage-account-secret"></a><span data-ttu-id="9ddbc-154">Titkos kód létrehozása tárfiókhoz</span><span class="sxs-lookup"><span data-stu-id="9ddbc-154">Create Storage account secret</span></span>

1. <span data-ttu-id="9ddbc-155">Menjen a **Rendszerfelügyelet** > **Beállítás** > **Key Vault-paraméterek** pontra , és válassza ki a kulcstartó titkos kódját.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-155">Go to **System administration** > **Setup** > **Key Vault parameters**, and select a Key vault secret.</span></span>
2. <span data-ttu-id="9ddbc-156">A **Tanúsítványok** szakaszban válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-156">In the **Certificates** section, select **Add**.</span></span>
3. <span data-ttu-id="9ddbc-157">A **Név** mezőbe írja be a tárfiók titkos kódjának nevét, és adjon meg egy leírást a **Leírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-157">In the **Name** field, enter the name of the storage account secret and in the **Description** field, enter a description.</span></span>
4. <span data-ttu-id="9ddbc-158">A **Típus** mezőben válassza ki a **Tanúsítvány** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-158">In the **Type** field, select **Certificate**.</span></span>
5. <span data-ttu-id="9ddbc-159">Válassza a **Mentés** gombot, majd zárja be az oldalt.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-159">Select **Save**, and then close the page.</span></span>

## <a name="create-a-digital-certificate-secret"></a><span data-ttu-id="9ddbc-160">Digitális tanúsítvány titkos kódjának létrehozása</span><span class="sxs-lookup"><span data-stu-id="9ddbc-160">Create a digital certificate secret</span></span>

1. <span data-ttu-id="9ddbc-161">Menjen a **Rendszerfelügyelet** > **Beállítás** > **Key Vault-paraméterek** pontra , és válassza ki a kulcstartó titkos kódját.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-161">Go to **System administration** > **Setup** > **Key Vault parameters**, and select a Key vault secret.</span></span>
2. <span data-ttu-id="9ddbc-162">A **Tanúsítványok** szakaszban válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-162">In the **Certificates** section, select **Add**.</span></span>
3. <span data-ttu-id="9ddbc-163">A **Név** mezőbe írja be a digitális tanúsítvány titkos kódjának nevét, és adjon meg egy leírást a **Leírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-163">In the **Name** field, enter the name of the digital certificate secret and in the **Description** field, enter a description.</span></span>
4. <span data-ttu-id="9ddbc-164">A **Típus** mezőben válassza ki a **Tanúsítvány** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-164">In the **Type** field, select **Certificate**.</span></span>
5. <span data-ttu-id="9ddbc-165">Válassza a **Mentés** gombot, majd zárja be az oldalt.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-165">Select **Save**, and then close the page.</span></span>

## <a name="create-an-electronic-invoicing-add-on-environment"></a><span data-ttu-id="9ddbc-166">Az Elektronikus számlázási bővítmény környezetének létrehozása</span><span class="sxs-lookup"><span data-stu-id="9ddbc-166">Create an Electronic invoicing add-on environment</span></span>

1. <span data-ttu-id="9ddbc-167">Jelentkezzen be a RCS-fiókba.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-167">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="9ddbc-168">A **Globalizációs funkció** munkaterületen a **Környezet** szakaszban válassza ki az **Elektronikus számlázás bővítmény** csempét.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-168">In the **Globalization feature** workspace, in the **Environment** section, select the **Electronic invoicing add-on** tile.</span></span>

## <a name="create-a-service-environment"></a><span data-ttu-id="9ddbc-169">Szolgáltatási környezet létrehozása</span><span class="sxs-lookup"><span data-stu-id="9ddbc-169">Create a service environment</span></span>

1. <span data-ttu-id="9ddbc-170">A **Környezet beállítása** oldalon a Művelet ablaktáblán válassza a **Szolgáltatási környezet** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-170">On the **Environment setups** page, on the Action Pane, select **Service environment**.</span></span>
2. <span data-ttu-id="9ddbc-171">Válassza ki az **Új** lehetőséget egy új szolgáltatási környezet létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-171">Select **New** to create a new service environment.</span></span>
3. <span data-ttu-id="9ddbc-172">A **Név** mezőben adja meg az e-számlázási környezet nevét.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-172">In the **Name** field, enter the name of the e-Invoicing environment.</span></span> <span data-ttu-id="9ddbc-173">Adjon meg egy leírást a **Leírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-173">In the **Description** field, enter a description.</span></span>
4. <span data-ttu-id="9ddbc-174">A **Tárterület SAS-token titkos kód** mezőben válassza ki azon tárfiók titkos kódjának a nevét, amely a tárfiókhoz való hozzáférés hitelesítéséhez szükséges.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-174">In the **Storage SAS token secret** field, select the name of the storage account secret that must be used to authenticate access to the storage account.</span></span>
5. <span data-ttu-id="9ddbc-175">A **Felhasználók** szakaszban válassza a **Hozzáadás** lehetőséget annak a felhasználónak a hozzáadásához, aki számára engedélyezett az elektronikus számlák elküldése a környezetben, valamint a tárfiókhoz való csatlakozás.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-175">In the **Users** section, select **Add** to add a user who is allowed to submit electronic invoices through the environment and also connect to the storage account.</span></span>
6. <span data-ttu-id="9ddbc-176">A **Felhasználói azonosító** mezőbe írja be a felhasználó aliasát.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-176">In the **User ID** field, enter the alias of the user.</span></span> <span data-ttu-id="9ddbc-177">Az **E-mail** mezőbe írja be a feladó e-mail-címét.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-177">In the **Email** field, enter the user's email address.</span></span>
7. <span data-ttu-id="9ddbc-178">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-178">Select **Save**.</span></span>
8. <span data-ttu-id="9ddbc-179">Ha az ország-/régióspecifikus számlákhoz egy tanúsítványlánc szükséges a digitális aláírások alkalmazásához, akkor válassza a Művelet ablaktábla **Key Vault-paraméterek** elemét, majd a **Tanúsítványlánc** lehetőséget, és kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="9ddbc-179">If your country/region-specific invoices require a chain of certificates to apply digital signatures, on the Action pane, select **Key Vault parameters**, then select **Chain of certificates**, and follow these steps:</span></span>

    1. <span data-ttu-id="9ddbc-180">Tanúsítványlánc létrehozásához válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-180">Select **New** to create a chain of certificates.</span></span>
    2. <span data-ttu-id="9ddbc-181">A **Név** mezőbe írja be a tanúsítványlánc nevét.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-181">In the **Name** field, enter the name of the chain of certificate.</span></span> <span data-ttu-id="9ddbc-182">Adjon meg egy leírást a **Leírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-182">In the **Description** field, enter a description.</span></span>
    3. <span data-ttu-id="9ddbc-183">A **Tanúsítványok** szakaszban válassza a **Hozzáadás** lehetőséget, ha tanúsítványt szeretne hozzáadni a lánchoz.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-183">In the **Certificates** section, select **Add** to add a certificate to the chain.</span></span>
    4. <span data-ttu-id="9ddbc-184">A **Fel** és a **Le** gombbal módosíthatja a tanúsítványnak a láncon belül elfoglalt pozícióját.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-184">Use the **Up** or **Down** button to change the position of the certificate in the chain.</span></span>
    5. <span data-ttu-id="9ddbc-185">Válassza a **Mentés** gombot, majd zárja be az oldalt.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-185">Select **Save**, and then close the page.</span></span>
    6. <span data-ttu-id="9ddbc-186">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-186">Close the page.</span></span>
9. <span data-ttu-id="9ddbc-187">A Művelet ablaktáblán válassza a **Szolgáltatási környezet**, majd a **Közzététel** lehetőséget a környezet felhőben történő közzétételéhez.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-187">On **Service environment** page, on the Action Pane, select **Publish** to publish the environment to the cloud.</span></span> <span data-ttu-id="9ddbc-188">Az **Állapot** mező értéke **Közzétéve** értékre módosul.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-188">The value of the **Status** field is changed to **Published**.</span></span>

## <a name="create-a-connected-application"></a><span data-ttu-id="9ddbc-189">Csatlakoztatott alkalmazás létrehozása</span><span class="sxs-lookup"><span data-stu-id="9ddbc-189">Create a connected application</span></span>

1. <span data-ttu-id="9ddbc-190">A **Környezet beállítása** oldalon a Művelet ablaktáblán válassza a **Csatlakoztatott alkalmazások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-190">On the **Environment setups** page, on the action Pane, select **Connected applications**.</span></span>
2. <span data-ttu-id="9ddbc-191">Válassza ki az **Új** lehetőséget egy csatlakoztatott alkalmazás létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-191">Select **New** to create a connected application.</span></span>
3. <span data-ttu-id="9ddbc-192">A **Név** mezőben adja meg a csatlakoztatni kívánt alkalmazás nevét.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-192">In the **Name** field, enter the name of the application to connect.</span></span>
4. <span data-ttu-id="9ddbc-193">Az **Alkalmazás** mezőben adja meg a csatlakozáshoz szükséges Finance and Supply Chain Management környezet URL-címét.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-193">In the **Application** field, enter the URL of the Finance and Supply Chain Management environment to connect.</span></span>
4. <span data-ttu-id="9ddbc-194">A **Bérlő** mezőben adja meg a Finance and Supply Chain Management környezet bérlőjét.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-194">In the **Tenant** field, enter the tenant of the Finance and Supply Chain Management environment.</span></span>
5. <span data-ttu-id="9ddbc-195">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-195">Select **Save**.</span></span>
6. <span data-ttu-id="9ddbc-196">A Művelet ablaktáblán válassza a **Kapcsolat ellenőrzése** lehetőséget a környezettel való kapcsolat teszteléséhez.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-196">On the Action Pane, select **Check connection** to test the connection with the environment.</span></span> <span data-ttu-id="9ddbc-197">Ezután zárja be az oldalt.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-197">Then close the page.</span></span>

## <a name="link-connected-applications-to-environments"></a><span data-ttu-id="9ddbc-198">Csatlakoztatott alkalmazások csatolása környezetekhez</span><span class="sxs-lookup"><span data-stu-id="9ddbc-198">Link connected applications to environments</span></span>

1. <span data-ttu-id="9ddbc-199">A **Környezet beállítása** oldalon válassza az **Új** lehetőséget, ha a környezethez hozzá szeretne rendelni egy csatlakoztatott alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-199">On the **Environment setups** page, select **New** to assign a connected application to an environment.</span></span>
2. <span data-ttu-id="9ddbc-200">A **Csatlakoztatott alkalmazás** mezőben válasszaon ki egy csatlakoztatott alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-200">In the **Connected application** field, select a connected application.</span></span>
3. <span data-ttu-id="9ddbc-201">Válassza ki a szolgáltatási környezetet a **Szolgáltatási környezet** mezőben.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-201">In the **Service environment** field, select a service environment.</span></span>
4. <span data-ttu-id="9ddbc-202">Válassza a **Mentés** gombot, majd zárja be az oldalt.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-202">Select **Save**, and then close the page.</span></span>

## <a name="set-up-the-electronic-invoicing-add-on-integration-in-finance-and-supply-chain-management"></a><span data-ttu-id="9ddbc-203">Elektronikus számlázási bővítmény integrációjának beállítása a Finance and Supply Chain Management szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="9ddbc-203">Set up the Electronic invoicing add-on integration in Finance and Supply Chain Management</span></span>

### <a name="turn-on-the-electronic-invoicing-add-on-integration-feature"></a><span data-ttu-id="9ddbc-204">Az Elektronikus számlázásbővítmény integráció funkció bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="9ddbc-204">Turn on the Electronic invoicing add-on integration feature</span></span>

1. <span data-ttu-id="9ddbc-205">Jelentkezzen be a Finance vagy Supply Chain Management-példányába.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-205">Sign in to your Finance or Supply Chain Management instance.</span></span>
2. <span data-ttu-id="9ddbc-206">A **Funkciókezelés** munkaterületen keresse meg az **Elektronikus számlázási bővítmény integrációja** funkciót.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-206">In the **Feature management** workspace, search for the **Electronic invoicing add-on integration** feature.</span></span> <span data-ttu-id="9ddbc-207">Ha ez a funkció nem jelenik meg az oldalon, válassza a **Frissítések keresése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-207">If this feature doesn't appear on the page, select **Check for updates**.</span></span>
3. <span data-ttu-id="9ddbc-208">Válassza ki a bekapcsolni kívánt funkciót, majd a részletek ablaktáblán válassza az **Engedélyezés most** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-208">Select the feature, and then select **Enable now**.</span></span>

### <a name="set-up-the-service-endpoint-url"></a><span data-ttu-id="9ddbc-209">A szolgáltatásvégpont URL-címének beállítása</span><span class="sxs-lookup"><span data-stu-id="9ddbc-209">Set up the service endpoint URL</span></span>

1. <span data-ttu-id="9ddbc-210">Menjen a **Szervezeti adminisztráció \> Beállítás \> Elektronikus dokumentumparaméterek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-210">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="9ddbc-211">A **Beküldési szolgáltatás** lapon a **Szolgáltatási végpont URL** mezőben adja meg az Azure földrajzi régió megfelelő szolgáltatási végpontját, amint azt a következő tábla mutatja.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-211">On the **Submission service** tab, in the **Service endpoint URL** field, enter the appropriate service endpoint for your Azure geography, as shown in the following table.</span></span>

    | <span data-ttu-id="9ddbc-212">Adatközpont Azure földrajzi régió</span><span class="sxs-lookup"><span data-stu-id="9ddbc-212">Datacenter Azure geography</span></span> | <span data-ttu-id="9ddbc-213">Szolgáltatási végpont URL-címe</span><span class="sxs-lookup"><span data-stu-id="9ddbc-213">Service endpoint URL</span></span>                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | <span data-ttu-id="9ddbc-214">USA keleti régiója</span><span class="sxs-lookup"><span data-stu-id="9ddbc-214">East US</span></span>                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="9ddbc-215">USA nyugati régiója</span><span class="sxs-lookup"><span data-stu-id="9ddbc-215">West US</span></span>                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="9ddbc-216">Észak-EU</span><span class="sxs-lookup"><span data-stu-id="9ddbc-216">North EU</span></span>                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="9ddbc-217">Nyugat-EU</span><span class="sxs-lookup"><span data-stu-id="9ddbc-217">West EU</span></span>                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

3. <span data-ttu-id="9ddbc-218">A **Környezet** mezőben adja meg az Elektronikus számlázási bővítmény környezetének nevét.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-218">In the **Environment** field, enter the name of the Electronic invoicing add-on environment.</span></span>
4. <span data-ttu-id="9ddbc-219">Válassza a **Mentés** gombot, majd zárja be az oldalt.</span><span class="sxs-lookup"><span data-stu-id="9ddbc-219">Select **Save**, and then close the page.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
