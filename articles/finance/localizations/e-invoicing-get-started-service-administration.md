---
title: Első lépések az elektronikus számlázási szolgáltatás adminisztrálása során
description: Ez a témakör bemutatja az Elektronikus számlázás szolgáltatásfelügyeletének használatának első lépéseit.
author: gionoder
ms.date: 03/29/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: ec431cb4a3620459d905f64a80fd820a2113290f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840148"
---
# <a name="get-started-with-electronic-invoicing-service-administration"></a><span data-ttu-id="1b00a-103">Első lépések az elektronikus számlázási szolgáltatás adminisztrálása során</span><span class="sxs-lookup"><span data-stu-id="1b00a-103">Get started with Electronic invoicing service administration</span></span>

[!include [banner](../includes/banner.md)]

## <a name="prerequisites"></a><span data-ttu-id="1b00a-104">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="1b00a-104">Prerequisites</span></span>

<span data-ttu-id="1b00a-105">Mielőtt teljesítené az ebben a témakörben ismertetett eljárásokat, a következő előfeltételeknek kell megfelelnie:</span><span class="sxs-lookup"><span data-stu-id="1b00a-105">Before you complete the procedures in this topic, the following prerequisites must be in place:</span></span>

- <span data-ttu-id="1b00a-106">Hozzá kell férnie a Microsoft Dynamics Lifecycle Services (LCS) fiókjához.</span><span class="sxs-lookup"><span data-stu-id="1b00a-106">You must have access to your Microsoft Dynamics Lifecycle Services (LCS) account.</span></span>
- <span data-ttu-id="1b00a-107">Olyan LCS-projekttel kell rendelkeznie, amely a Microsoft Dynamics 365 Finance és a Dynamics 365 Supply Chain Management 10.0.17-as vagy újabb verzióját tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="1b00a-107">You must have an LCS project that includes version 10.0.17 or later of Microsoft Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="1b00a-108">Ezenkívül ezeket az alkalmazásokat a következő Azure földrajzi régiók egyikében kell telepíteni:</span><span class="sxs-lookup"><span data-stu-id="1b00a-108">Additionally, these apps must be deployed in one of the following Azure geographies:</span></span>

    - <span data-ttu-id="1b00a-109">USA keleti régiója</span><span class="sxs-lookup"><span data-stu-id="1b00a-109">East US</span></span>
    - <span data-ttu-id="1b00a-110">USA nyugati régiója</span><span class="sxs-lookup"><span data-stu-id="1b00a-110">West US</span></span>
    - <span data-ttu-id="1b00a-111">Észak-EU</span><span class="sxs-lookup"><span data-stu-id="1b00a-111">North EU</span></span>
    - <span data-ttu-id="1b00a-112">Nyugat-EU</span><span class="sxs-lookup"><span data-stu-id="1b00a-112">West EU</span></span>

- <span data-ttu-id="1b00a-113">Hozzá kell férnie a Dynamics 365 Regulatory Configuration Services (RCS) fiókjához.</span><span class="sxs-lookup"><span data-stu-id="1b00a-113">You must have access to your Dynamics 365 Regulatory Configuration Services (RCS) account.</span></span>
- <span data-ttu-id="1b00a-114">Aktiválnia kell a Globalizációs funkciót az RCS-fiókjához a Funkciókezelőben.</span><span class="sxs-lookup"><span data-stu-id="1b00a-114">You must activate the Globalization feature for your RCS account in Feature management.</span></span> <span data-ttu-id="1b00a-115">További információért lásd a [Kapcsolódás a Regulatory Configuration Services (RCS) szolgáltatáshoz – Globalizációs funkciók](rcs-globalization-feature.md) részt.</span><span class="sxs-lookup"><span data-stu-id="1b00a-115">For more information, see [Regulatory Configuration Services (RCS) - Globalization features](rcs-globalization-feature.md).</span></span>
- <span data-ttu-id="1b00a-116">Létre kell hoznia egy kulcstartót és egy tárfiókot az Azure szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="1b00a-116">You must create a key vault and a storage account in Azure.</span></span> <span data-ttu-id="1b00a-117">További információért lásd az [Azure tárfiók és kulcstartó létrehozása](e-invoicing-create-azure-storage-account-key-vault.md) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1b00a-117">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>

## <a name="install-the-add-in-for-microservices-in-lifecycle-services"></a><span data-ttu-id="1b00a-118">A mikroszolgáltatások bővítményének telepítése a Lifecycle Services szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="1b00a-118">Install the add-in for microservices in Lifecycle Services</span></span>

1. <span data-ttu-id="1b00a-119">Jelentkezzen be a LCS-fiók.</span><span class="sxs-lookup"><span data-stu-id="1b00a-119">Sign in to your LCS account.</span></span>
2. <span data-ttu-id="1b00a-120">Válassza az **Előzetes funkció kezelése** csempe lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1b00a-120">Select the **Preview feature management** tile.</span></span>
3. <span data-ttu-id="1b00a-121">A **Nyilvános előzetes verzió** szakaszban válassza az **e-számlázási szolgáltatás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1b00a-121">In the **Public Preview Features** section, select **e-Invoicing service**.</span></span>
4. <span data-ttu-id="1b00a-122">Ellenőrizze, hogy az **Előzetes funkció engedélyezve** értéke **Igen** értékre van-e állítva.</span><span class="sxs-lookup"><span data-stu-id="1b00a-122">Make sure that the **Preview feature enabled** option is set to **Yes**.</span></span>
5. <span data-ttu-id="1b00a-123">Válassza ki az LCS-telepítési projektet az LCS-irányítópulton.</span><span class="sxs-lookup"><span data-stu-id="1b00a-123">On your LCS dashboard, select your LCS deployment project.</span></span> <span data-ttu-id="1b00a-124">Az LCS-projektnek futnia kell.</span><span class="sxs-lookup"><span data-stu-id="1b00a-124">The LCS project must be running.</span></span>
7. <span data-ttu-id="1b00a-125">A **Környezetbővítmények** lapon válassza az **Új bővítmény telepítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1b00a-125">On the **Environment add-ins** tab, select **Install a new add-in**.</span></span>
8. <span data-ttu-id="1b00a-126">Válassza ki az **elektronikus számlázási szolgáltatásokat**.</span><span class="sxs-lookup"><span data-stu-id="1b00a-126">Select **e-invoicing Services**.</span></span>
9. <span data-ttu-id="1b00a-127">Az **AAD-alkalmazásazonosító** mezőbe írja: **091c98b0-a1c9-4b02-b62c-7753395ccabe**.</span><span class="sxs-lookup"><span data-stu-id="1b00a-127">In the **AAD application ID** field, enter **091c98b0-a1c9-4b02-b62c-7753395ccabe**.</span></span> <span data-ttu-id="1b00a-128">Ez egy rögzített érték.</span><span class="sxs-lookup"><span data-stu-id="1b00a-128">This is a fixed value.</span></span>
10. <span data-ttu-id="1b00a-129">Az **AAD-bérlőazonosító** mezőbe írja be az Azure előfizetési fiókja bérlőazonosítóját.</span><span class="sxs-lookup"><span data-stu-id="1b00a-129">In the **AAD tenant ID** field, enter the tenant ID of your Azure subscription account.</span></span>
11. <span data-ttu-id="1b00a-130">Olvassa el az Általános Szerződési Feltételeket, majd jelölje be a jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="1b00a-130">Review the terms and conditions, and then select the check box.</span></span>
12. <span data-ttu-id="1b00a-131">Válassza a **Telepítés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="1b00a-131">Select **Install**.</span></span>


## <a name="set-up-the-parameters-for-rcs-integration-with-electronic-invoicing"></a><span data-ttu-id="1b00a-132">RCS-integráció paramétereinek beállítása az Elektronikus számlázással</span><span class="sxs-lookup"><span data-stu-id="1b00a-132">Set up the parameters for RCS integration with Electronic invoicing</span></span>

1. <span data-ttu-id="1b00a-133">Jelentkezzen be a RCS-fiókba.</span><span class="sxs-lookup"><span data-stu-id="1b00a-133">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="1b00a-134">Az **Elektronikus jelentéskészítés** munkaterületen, a **Kapcsolódó hivatkozások** szakaszban, válassza az **Elektronikus jelentéskészítés paraméterei** elemet.</span><span class="sxs-lookup"><span data-stu-id="1b00a-134">In the **Electronic reporting** workspace, in the **Related links** section, select **Electronic reporting parameters**.</span></span>
3. <span data-ttu-id="1b00a-135">Az **e-számlázási szolgáltatás** lapon a **Szolgáltatási végpont URI** mezőben adja meg az Azure földrajzi régió megfelelő szolgáltatási végpontját, amint azt a következő tábla mutatja.</span><span class="sxs-lookup"><span data-stu-id="1b00a-135">On the **e-Invoicing service** tab, in the **Service endpoint URI** field, enter the appropriate service endpoint for your Azure geography, as shown in the following table.</span></span>

    | <span data-ttu-id="1b00a-136">Adatközpont Azure földrajzi régió</span><span class="sxs-lookup"><span data-stu-id="1b00a-136">Datacenter Azure geography</span></span> | <span data-ttu-id="1b00a-137">Szolgáltatási végpont URI-címe</span><span class="sxs-lookup"><span data-stu-id="1b00a-137">Service endpoint URI</span></span>                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | <span data-ttu-id="1b00a-138">USA keleti régiója</span><span class="sxs-lookup"><span data-stu-id="1b00a-138">East US</span></span>                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="1b00a-139">USA nyugati régiója</span><span class="sxs-lookup"><span data-stu-id="1b00a-139">West US</span></span>                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="1b00a-140">Észak-EU</span><span class="sxs-lookup"><span data-stu-id="1b00a-140">North EU</span></span>                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="1b00a-141">Nyugat-EU</span><span class="sxs-lookup"><span data-stu-id="1b00a-141">West EU</span></span>                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

4. <span data-ttu-id="1b00a-142">Ellenőrizze, hogy az **Alkalmazásazonosító** mező **0cdb527f-a8d1-4bf8-9436-b352c68682b2** értékre legyen állítva.</span><span class="sxs-lookup"><span data-stu-id="1b00a-142">Verify that the **Application Id** field is set to **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span></span> <span data-ttu-id="1b00a-143">Ez egy rögzített érték.</span><span class="sxs-lookup"><span data-stu-id="1b00a-143">This value is a fixed value.</span></span>
5. <span data-ttu-id="1b00a-144">Az **LCS-környezet azonosítója** mezőbe írja be az LCS környezet azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="1b00a-144">In the **LCS Environment Id** field, enter the ID of your LCS environment.</span></span>
6. <span data-ttu-id="1b00a-145">Válassza a **Mentés** gombot, majd zárja be az oldalt.</span><span class="sxs-lookup"><span data-stu-id="1b00a-145">Select **Save**, and then close the page.</span></span>

## <a name="create-key-vault-references"></a><span data-ttu-id="1b00a-146">Key Vault-hivatkozások létrehozása</span><span class="sxs-lookup"><span data-stu-id="1b00a-146">Create Key Vault references</span></span>

1. <span data-ttu-id="1b00a-147">Jelentkezzen be a RCS-fiókba.</span><span class="sxs-lookup"><span data-stu-id="1b00a-147">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="1b00a-148">A **Globalizációs funkció** munkaterületen a **Környezet** szakaszban válassza ki az **Elektronikus számlázás bővítmény** csempét.</span><span class="sxs-lookup"><span data-stu-id="1b00a-148">In the **Globalization feature** workspace, in the **Environment** section, select the **Electronic invoicing** tile.</span></span>
3. <span data-ttu-id="1b00a-149">A **Környezet beállítása** lapon a Művelet ablaktáblán válassza ki a **Szolgáltatási környezet**, majd a **Key Vault-paraméterek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1b00a-149">On the **Environment setups** page, on the action Pane, select **Service environment**, and then select **Key Vault parameters**.</span></span>
4. <span data-ttu-id="1b00a-150">Kulcstartó hivatkozás létrehozásához válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1b00a-150">Select **New** to create a key vault reference.</span></span>
5. <span data-ttu-id="1b00a-151">A **Név** mezőben adja meg a kulcstartó hivatkozásának nevét.</span><span class="sxs-lookup"><span data-stu-id="1b00a-151">In the **Name** field, enter the name of the key vault reference.</span></span> <span data-ttu-id="1b00a-152">Adjon meg egy leírást a **Leírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1b00a-152">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="1b00a-153">A **Key Vault – URI** mezőbe másolja be a kulcstartó titkos kódját az Azure Key Vault megoldásból.</span><span class="sxs-lookup"><span data-stu-id="1b00a-153">In the **Key Vault URI** field, paste the key vault secret from Azure Key Vault.</span></span> <span data-ttu-id="1b00a-154">További információért lásd az [Azure tárfiók és kulcstartó létrehozása](e-invoicing-create-azure-storage-account-key-vault.md) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1b00a-154">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>
7. <span data-ttu-id="1b00a-155">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1b00a-155">Select **Save**.</span></span>

## <a name="create-storage-account-secret"></a><span data-ttu-id="1b00a-156">Titkos kód létrehozása tárfiókhoz</span><span class="sxs-lookup"><span data-stu-id="1b00a-156">Create Storage account secret</span></span>

1. <span data-ttu-id="1b00a-157">A **Környezet beállítása** lapon a Műveleti ablaktáblán válassza ki a **Szolgáltatási környezet** > **Key Vault-paraméterek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1b00a-157">On the **Environment setups** page, on the Action Pane, select **Service environment** > **Key Vault parameters**.</span></span>
2. <span data-ttu-id="1b00a-158">Jelöljön ki egy **Key Vault-hivatkozást**, és a **Tanúsítványok** szakaszban válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1b00a-158">Select a **Key Vault reference** and in the **Certificates** section, select **Add**.</span></span>
3. <span data-ttu-id="1b00a-159">A **Név** mezőbe írja be a tárfiók titkos kódjának nevét.</span><span class="sxs-lookup"><span data-stu-id="1b00a-159">In the **Name** field, enter the name of the storage account secret.</span></span> <span data-ttu-id="1b00a-160">További információért lásd az [Azure tárfiók és kulcstartó létrehozása](e-invoicing-create-azure-storage-account-key-vault.md) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1b00a-160">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>
4. <span data-ttu-id="1b00a-161">Adjon meg egy leírást a **Leírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1b00a-161">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="1b00a-162">A **Típus** mezőben válassza ki a **Titok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1b00a-162">In the **Type** field, select **Secret**.</span></span>
6. <span data-ttu-id="1b00a-163">Válassza a **Mentés** gombot, majd zárja be az oldalt.</span><span class="sxs-lookup"><span data-stu-id="1b00a-163">Select **Save**, and then close the page.</span></span>

## <a name="create-a-digital-certificate-secret"></a><span data-ttu-id="1b00a-164">Digitális tanúsítvány titkos kódjának létrehozása</span><span class="sxs-lookup"><span data-stu-id="1b00a-164">Create a digital certificate secret</span></span>

1. <span data-ttu-id="1b00a-165">A **Környezet beállítása** lapon a Művelet ablaktáblán válassza ki a **Szolgáltatási környezet**, majd a **Key Vault-paraméterek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1b00a-165">On the **Environment setups** page, on the action Pane, select **Service environment** and then select **Key Vault parameters**.</span></span>
2. <span data-ttu-id="1b00a-166">Jelöljön ki egy **Key Vault-hivatkozást**, majd a **Tanúsítványok** szakaszban válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1b00a-166">Select a **Key Vault reference** and then in the **Certificates** section, select **Add**.</span></span>
3. <span data-ttu-id="1b00a-167">A **Név** mezőbe írja be a digitális tanúsítvány titkának a nevét.</span><span class="sxs-lookup"><span data-stu-id="1b00a-167">In the **Name** field, enter the name of the digital certificate secret.</span></span> <span data-ttu-id="1b00a-168">További információért lásd az [Azure tárfiók és kulcstartó létrehozása](e-invoicing-create-azure-storage-account-key-vault.md) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1b00a-168">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>
4. <span data-ttu-id="1b00a-169">Adjon meg egy leírást a **Leírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1b00a-169">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="1b00a-170">A **Típus** mezőben válassza ki a **Tanúsítvány** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1b00a-170">In the **Type** field, select **Certificate**.</span></span>
6. <span data-ttu-id="1b00a-171">Válassza a **Mentés** gombot, majd zárja be az oldalt.</span><span class="sxs-lookup"><span data-stu-id="1b00a-171">Select **Save**, and then close the page.</span></span>

## <a name="create-a-service-environment"></a><span data-ttu-id="1b00a-172">Szolgáltatási környezet létrehozása</span><span class="sxs-lookup"><span data-stu-id="1b00a-172">Create a service environment</span></span>

1. <span data-ttu-id="1b00a-173">Jelentkezzen be a RCS-fiókba.</span><span class="sxs-lookup"><span data-stu-id="1b00a-173">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="1b00a-174">A **Globalizációs funkció** munkaterületen a **Környezet** szakaszban válassza ki az **Elektronikus számlázás bővítmény** csempét.</span><span class="sxs-lookup"><span data-stu-id="1b00a-174">In the **Globalization feature** workspace, in the **Environment** section, select the **Electronic invoicing** tile.</span></span>
3. <span data-ttu-id="1b00a-175">A **Környezet beállítása** oldalon a Művelet ablaktáblán válassza a **Szolgáltatási környezet** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1b00a-175">On the **Environment setups** page, on the Action Pane, select **Service environment**.</span></span>
4. <span data-ttu-id="1b00a-176">Válassza ki az **Új** lehetőséget egy új szolgáltatási környezet létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="1b00a-176">Select **New** to create a new service environment.</span></span>
5. <span data-ttu-id="1b00a-177">A **Név** mezőben adja meg az e-számlázási környezet nevét.</span><span class="sxs-lookup"><span data-stu-id="1b00a-177">In the **Name** field, enter the name of the e-Invoicing environment.</span></span> <span data-ttu-id="1b00a-178">Adjon meg egy leírást a **Leírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1b00a-178">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="1b00a-179">A **Tárterület SAS-token titkos kód** mezőben válassza ki azon tárfiók titkos kódjának a nevét, amely a tárfiókhoz való hozzáférés hitelesítéséhez szükséges.</span><span class="sxs-lookup"><span data-stu-id="1b00a-179">In the **Storage SAS token secret** field, select the name of the storage account secret that must be used to authenticate access to the storage account.</span></span>
7. <span data-ttu-id="1b00a-180">A **Felhasználók** szakaszban válassza a **Hozzáadás** lehetőséget annak a felhasználónak a hozzáadásához, aki számára engedélyezett az elektronikus számlák elküldése a környezetben, valamint a tárfiókhoz való csatlakozás.</span><span class="sxs-lookup"><span data-stu-id="1b00a-180">In the **Users** section, select **Add** to add a user who is allowed to submit electronic invoices through the environment and also connect to the storage account.</span></span>
8. <span data-ttu-id="1b00a-181">A **Felhasználói azonosító** mezőbe írja be a felhasználó aliasát.</span><span class="sxs-lookup"><span data-stu-id="1b00a-181">In the **User ID** field, enter the alias of the user.</span></span> <span data-ttu-id="1b00a-182">Az **E-mail** mezőbe írja be a feladó e-mail-címét.</span><span class="sxs-lookup"><span data-stu-id="1b00a-182">In the **Email** field, enter the user's email address.</span></span>
9. <span data-ttu-id="1b00a-183">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1b00a-183">Select **Save**.</span></span>
10. <span data-ttu-id="1b00a-184">Ha az ország-/régióspecifikus számlákhoz egy tanúsítványlánc szükséges a digitális aláírások alkalmazásához, akkor válassza a Művelet ablaktábla **Key Vault-paraméterek** elemét, majd a **Tanúsítványlánc** lehetőséget, és kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="1b00a-184">If your country/region-specific invoices require a chain of certificates to apply digital signatures, on the Action pane, select **Key Vault parameters**, then select **Chain of certificates**, and follow these steps:</span></span>
    1. <span data-ttu-id="1b00a-185">Tanúsítványlánc létrehozásához válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1b00a-185">Select **New** to create a chain of certificates.</span></span>
    2. <span data-ttu-id="1b00a-186">A **Név** mezőbe írja be a tanúsítványlánc nevét.</span><span class="sxs-lookup"><span data-stu-id="1b00a-186">In the **Name** field, enter the name of the chain of certificate.</span></span> <span data-ttu-id="1b00a-187">Adjon meg egy leírást a **Leírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1b00a-187">In the **Description** field, enter a description.</span></span>
    3. <span data-ttu-id="1b00a-188">A **Tanúsítványok** szakaszban válassza a **Hozzáadás** lehetőséget, ha tanúsítványt szeretne hozzáadni a lánchoz.</span><span class="sxs-lookup"><span data-stu-id="1b00a-188">In the **Certificates** section, select **Add** to add a certificate to the chain.</span></span>
    4. <span data-ttu-id="1b00a-189">A **Fel** és a **Le** gombbal módosíthatja a tanúsítványnak a láncon belül elfoglalt pozícióját.</span><span class="sxs-lookup"><span data-stu-id="1b00a-189">Use the **Up** or **Down** button to change the position of the certificate in the chain.</span></span>
    5. <span data-ttu-id="1b00a-190">Válassza a **Mentés** gombot, majd zárja be az oldalt.</span><span class="sxs-lookup"><span data-stu-id="1b00a-190">Select **Save**, and then close the page.</span></span>
    6. <span data-ttu-id="1b00a-191">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="1b00a-191">Close the page.</span></span>
11. <span data-ttu-id="1b00a-192">A Művelet ablaktáblán válassza a **Szolgáltatási környezet**, majd a **Közzététel** lehetőséget a környezet felhőben történő közzétételéhez.</span><span class="sxs-lookup"><span data-stu-id="1b00a-192">On **Service environment** page, on the Action Pane, select **Publish** to publish the environment to the cloud.</span></span> <span data-ttu-id="1b00a-193">Az **Állapot** mező értéke **Közzétéve** értékre módosul.</span><span class="sxs-lookup"><span data-stu-id="1b00a-193">The value of the **Status** field is changed to **Published**.</span></span>

## <a name="create-a-connected-application"></a><span data-ttu-id="1b00a-194">Csatlakoztatott alkalmazás létrehozása</span><span class="sxs-lookup"><span data-stu-id="1b00a-194">Create a connected application</span></span>

1. <span data-ttu-id="1b00a-195">A **Környezet beállítása** oldalon a Művelet ablaktáblán válassza a **Csatlakoztatott alkalmazások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1b00a-195">On the **Environment setups** page, on the action Pane, select **Connected applications**.</span></span>
2. <span data-ttu-id="1b00a-196">Válassza ki az **Új** lehetőséget egy csatlakoztatott alkalmazás létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="1b00a-196">Select **New** to create a connected application.</span></span>
3. <span data-ttu-id="1b00a-197">A **Név** mezőben adja meg a csatlakoztatni kívánt alkalmazás nevét.</span><span class="sxs-lookup"><span data-stu-id="1b00a-197">In the **Name** field, enter the name of the application to connect.</span></span>
4. <span data-ttu-id="1b00a-198">Az **Alkalmazás** mezőben adja meg a csatlakozáshoz szükséges Finance and Supply Chain Management környezet URL-címét.</span><span class="sxs-lookup"><span data-stu-id="1b00a-198">In the **Application** field, enter the URL of the Finance and Supply Chain Management environment to connect.</span></span>
4. <span data-ttu-id="1b00a-199">A **Bérlő** mezőben adja meg a Finance and Supply Chain Management környezet bérlőjét.</span><span class="sxs-lookup"><span data-stu-id="1b00a-199">In the **Tenant** field, enter the tenant of the Finance and Supply Chain Management environment.</span></span>
5. <span data-ttu-id="1b00a-200">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1b00a-200">Select **Save**.</span></span>
6. <span data-ttu-id="1b00a-201">A Művelet ablaktáblán válassza a **Kapcsolat ellenőrzése** lehetőséget a környezettel való kapcsolat teszteléséhez.</span><span class="sxs-lookup"><span data-stu-id="1b00a-201">On the Action Pane, select **Check connection** to test the connection with the environment.</span></span> <span data-ttu-id="1b00a-202">Ezután zárja be az oldalt.</span><span class="sxs-lookup"><span data-stu-id="1b00a-202">Then close the page.</span></span>

## <a name="link-connected-applications-to-environments"></a><span data-ttu-id="1b00a-203">Csatlakoztatott alkalmazások csatolása környezetekhez</span><span class="sxs-lookup"><span data-stu-id="1b00a-203">Link connected applications to environments</span></span>

1. <span data-ttu-id="1b00a-204">A **Környezet beállítása** oldalon válassza az **Új** lehetőséget, ha a környezethez hozzá szeretne rendelni egy csatlakoztatott alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="1b00a-204">On the **Environment setups** page, select **New** to assign a connected application to an environment.</span></span>
2. <span data-ttu-id="1b00a-205">A **Csatlakoztatott alkalmazás** mezőben válasszaon ki egy csatlakoztatott alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="1b00a-205">In the **Connected application** field, select a connected application.</span></span>
3. <span data-ttu-id="1b00a-206">Válassza ki a szolgáltatási környezetet a **Szolgáltatási környezet** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1b00a-206">In the **Service environment** field, select a service environment.</span></span>
4. <span data-ttu-id="1b00a-207">Válassza a **Mentés** gombot, majd zárja be az oldalt.</span><span class="sxs-lookup"><span data-stu-id="1b00a-207">Select **Save**, and then close the page.</span></span>

## <a name="set-up-electronic-invoicing-integration-in-finance-and-supply-chain-management"></a><span data-ttu-id="1b00a-208">Elektronikus számlázásbővítmény integráció beállítása a Finance és a Supply Chain Management szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="1b00a-208">Set up Electronic invoicing integration in Finance and Supply Chain Management</span></span>

### <a name="turn-on-the-electronic-invoicing-integration-feature"></a><span data-ttu-id="1b00a-209">Az Elektronikus számlázás integráció funkció bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="1b00a-209">Turn on the Electronic invoicing integration feature</span></span>

1. <span data-ttu-id="1b00a-210">Jelentkezzen be a Finance vagy Supply Chain Management-példányába.</span><span class="sxs-lookup"><span data-stu-id="1b00a-210">Sign in to your Finance or Supply Chain Management instance.</span></span>
2. <span data-ttu-id="1b00a-211">A **Funkciókezelés** munkaterületen keresse meg az **Elektronikus számlázás integrációja** funkciót.</span><span class="sxs-lookup"><span data-stu-id="1b00a-211">In the **Feature management** workspace, search for the **Electronic invoicing integration** feature.</span></span> <span data-ttu-id="1b00a-212">Ha ez a funkció nem jelenik meg az oldalon, válassza a **Frissítések keresése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1b00a-212">If this feature doesn't appear on the page, select **Check for updates**.</span></span>
3. <span data-ttu-id="1b00a-213">Válassza ki a bekapcsolni kívánt funkciót, majd a részletek ablaktáblán válassza az **Engedélyezés most** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1b00a-213">Select the feature, and then select **Enable now**.</span></span>

### <a name="set-up-the-service-endpoint-url"></a><span data-ttu-id="1b00a-214">A szolgáltatásvégpont URL-címének beállítása</span><span class="sxs-lookup"><span data-stu-id="1b00a-214">Set up the service endpoint URL</span></span>

1. <span data-ttu-id="1b00a-215">Menjen a **Szervezeti adminisztráció \> Beállítás \> Elektronikus dokumentumparaméterek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1b00a-215">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="1b00a-216">A **Beküldési szolgáltatás** lapon a **Szolgáltatási végpont URL** mezőben adja meg az Azure földrajzi régió megfelelő szolgáltatási végpontját, amint azt a következő tábla mutatja.</span><span class="sxs-lookup"><span data-stu-id="1b00a-216">On the **Submission service** tab, in the **Service endpoint URL** field, enter the appropriate service endpoint for your Azure geography, as shown in the following table.</span></span>

    | <span data-ttu-id="1b00a-217">Adatközpont Azure földrajzi régió</span><span class="sxs-lookup"><span data-stu-id="1b00a-217">Datacenter Azure geography</span></span> | <span data-ttu-id="1b00a-218">Szolgáltatási végpont URL-címe</span><span class="sxs-lookup"><span data-stu-id="1b00a-218">Service endpoint URL</span></span>                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | <span data-ttu-id="1b00a-219">USA keleti régiója</span><span class="sxs-lookup"><span data-stu-id="1b00a-219">East US</span></span>                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="1b00a-220">USA nyugati régiója</span><span class="sxs-lookup"><span data-stu-id="1b00a-220">West US</span></span>                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="1b00a-221">Észak-EU</span><span class="sxs-lookup"><span data-stu-id="1b00a-221">North EU</span></span>                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="1b00a-222">Nyugat-EU</span><span class="sxs-lookup"><span data-stu-id="1b00a-222">West EU</span></span>                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

3. <span data-ttu-id="1b00a-223">A **Környezet** mezőben adja meg az Elektronikus számlázásban közzétett szolgáltatási környezet nevét.</span><span class="sxs-lookup"><span data-stu-id="1b00a-223">In the **Environment** field, enter the name of the service environment published in Electronic invoicing.</span></span>
4. <span data-ttu-id="1b00a-224">Válassza a **Mentés** gombot, majd zárja be az oldalt.</span><span class="sxs-lookup"><span data-stu-id="1b00a-224">Select **Save**, and then close the page.</span></span>

### <a name="enable-flighting-keys"></a><span data-ttu-id="1b00a-225">Tesztkulcsok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="1b00a-225">Enable Flighting keys</span></span>

<span data-ttu-id="1b00a-226">Engedélyezze a tesztkulcsokat a Microsoft Dynamics 365 Finance vagy a Microsoft Dynamics 365 Supply Chain Management 10.0.17-es vagy korábbi verzióihoz.</span><span class="sxs-lookup"><span data-stu-id="1b00a-226">Enable Flight keys for  Microsoft Dynamics 365 Finance or  Microsoft Dynamics 365 Supply Chain Management versions 10.0.17 or earlier.</span></span> 
1. <span data-ttu-id="1b00a-227">Hajtsa végre a következő SQL-parancsot:</span><span class="sxs-lookup"><span data-stu-id="1b00a-227">Execute the following SQL command:</span></span>

    <span data-ttu-id="1b00a-228">ILLESSZE BE A SYSFLIGHTING (JÁRATNÉV, ENGEDÉLYEZETT) ÉRTÉKEKBE ('BusinessDocumentSubmissionServiceEnabled', 1)</span><span class="sxs-lookup"><span data-stu-id="1b00a-228">INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('BusinessDocumentSubmissionServiceEnabled', 1)</span></span>
    
    <span data-ttu-id="1b00a-229">ILLESSZE BE A SYSFLIGHTING (JÁRATNÉV, ENGEDÉLYEZETT) ÉRTÉKEKBE ('ElectronicInvoicingServiceIntegrationFeature', 1)</span><span class="sxs-lookup"><span data-stu-id="1b00a-229">INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('ElectronicInvoicingServiceIntegrationFeature', 1)</span></span>

2. <span data-ttu-id="1b00a-230">IISreset parancs végrehajtása minden AOS-hoz.</span><span class="sxs-lookup"><span data-stu-id="1b00a-230">Perform an IISreset command for all AOS's.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
