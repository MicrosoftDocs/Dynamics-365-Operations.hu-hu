---
title: Első lépések az Elektronikus számlázási bővítmény szolgáltatásfelügyeletének használata során
description: Ez a témakör bemutatja az Elektronikus számlázási bővítmény szolgáltatásfelügyeletének használatának első lépéseit.
author: gionoder
manager: AnnBe
ms.date: 01/28/2021
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
ms.openlocfilehash: 111ec65aa826795125d4a9ce835f72e1a0f41b7b
ms.sourcegitcommit: e88c96d1cb817a22db81856cadb563c095ab2671
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/02/2021
ms.locfileid: "5104388"
---
# <a name="get-started-with-electronic-invoicing-add-on-service-administration"></a><span data-ttu-id="98698-103">Első lépések az Elektronikus számlázási bővítmény szolgáltatásfelügyeletének használata során</span><span class="sxs-lookup"><span data-stu-id="98698-103">Get started with Electronic invoicing add-on service administration</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

## <a name="prerequisites"></a><span data-ttu-id="98698-104">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="98698-104">Prerequisites</span></span>

<span data-ttu-id="98698-105">Mielőtt teljesítené az ebben a témakörben ismertetett eljárásokat, a következő előfeltételeknek kell megfelelnie:</span><span class="sxs-lookup"><span data-stu-id="98698-105">Before you complete the procedures in this topic, the following prerequisites must be in place:</span></span>

- <span data-ttu-id="98698-106">Hozzá kell férnie a Microsoft Dynamics Lifecycle Services (LCS) fiókjához.</span><span class="sxs-lookup"><span data-stu-id="98698-106">You must have access to your Microsoft Dynamics Lifecycle Services (LCS) account.</span></span>
- <span data-ttu-id="98698-107">Olyan LCS-projekttel kell rendelkeznie, amely a Microsoft Dynamics 365 Finance és a Dynamics 365 Supply Chain Management 10.0.13-as vagy újabb verzióját tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="98698-107">You must have an LCS project that includes version 10.0.13 or later of Microsoft Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="98698-108">Ezenkívül ezeket az alkalmazásokat a következő Azure földrajzi régiók egyikében kell telepíteni:</span><span class="sxs-lookup"><span data-stu-id="98698-108">Additionally, these apps must be deployed in one of the following Azure geographies:</span></span>

    - <span data-ttu-id="98698-109">USA keleti régiója</span><span class="sxs-lookup"><span data-stu-id="98698-109">East US</span></span>
    - <span data-ttu-id="98698-110">USA nyugati régiója</span><span class="sxs-lookup"><span data-stu-id="98698-110">West US</span></span>
    - <span data-ttu-id="98698-111">Észak-EU</span><span class="sxs-lookup"><span data-stu-id="98698-111">North EU</span></span>
    - <span data-ttu-id="98698-112">Nyugat-EU</span><span class="sxs-lookup"><span data-stu-id="98698-112">West EU</span></span>

- <span data-ttu-id="98698-113">Hozzá kell férnie a Dynamics 365 Regulatory Configuration Services (RCS) fiókjához.</span><span class="sxs-lookup"><span data-stu-id="98698-113">You must have access to your Dynamics 365 Regulatory Configuration Services (RCS) account.</span></span>
- <span data-ttu-id="98698-114">Aktiválnia kell a Globalizációs funkciót az RCS-fiókjához a Funkciókezelőben.</span><span class="sxs-lookup"><span data-stu-id="98698-114">You must activate the Globalization feature for your RCS account in Feature management.</span></span> <span data-ttu-id="98698-115">További információért lásd a [Kapcsolódás a Regulatory Configuration Services (RCS) szolgáltatáshoz – Globalizációs funkciók](rcs-globalization-feature.md) részt.</span><span class="sxs-lookup"><span data-stu-id="98698-115">For more information, see [Regulatory Configuration Services (RCS) - Globalization features](rcs-globalization-feature.md).</span></span>
- <span data-ttu-id="98698-116">Létre kell hoznia egy kulcstartót és egy tárfiókot az Azure szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="98698-116">You must create a key vault and a storage account in Azure.</span></span> <span data-ttu-id="98698-117">További információért lásd az [Azure tárfiók és kulcstartó létrehozása](e-invoicing-create-azure-storage-account-key-vault.md) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="98698-117">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>

## <a name="install-the-add-on-for-microservices-in-lifecycle-services"></a><span data-ttu-id="98698-118">A mikroszolgáltatások bővítményének telepítése a Lifecycle Services szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="98698-118">Install the add-on for microservices in Lifecycle Services</span></span>

1. <span data-ttu-id="98698-119">Jelentkezzen be a LCS-fiók.</span><span class="sxs-lookup"><span data-stu-id="98698-119">Sign in to your LCS account.</span></span>
2. <span data-ttu-id="98698-120">Válassza az **Előzetes funkció kezelése** csempe lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="98698-120">Select the **Preview feature management** tile.</span></span>
3. <span data-ttu-id="98698-121">A **Nyilvános előzetes verzió** szakaszban válassza az **e-számlázási szolgáltatás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="98698-121">In the **Public Preview Features** section, select **e-Invoicing service**.</span></span>
4. <span data-ttu-id="98698-122">Ellenőrizze, hogy az **Előzetes funkció engedélyezve** értéke **Igen** értékre van-e állítva.</span><span class="sxs-lookup"><span data-stu-id="98698-122">Make sure that the **Preview feature enabled** option is set to **Yes**.</span></span>

## <a name="set-up-the-parameters-for-rcs-integration-with-the-electronic-invoicing-add-on"></a><span data-ttu-id="98698-123">RCS-integráció paramétereinek beállítása az Elektronikus számlázási bővítménnyel</span><span class="sxs-lookup"><span data-stu-id="98698-123">Set up the parameters for RCS integration with the Electronic invoicing add-on</span></span>

1. <span data-ttu-id="98698-124">Jelentkezzen be a RCS-fiókba.</span><span class="sxs-lookup"><span data-stu-id="98698-124">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="98698-125">Az **Elektronikus jelentéskészítés** munkaterületen, a **Kapcsolódó hivatkozások** szakaszban, válassza az **Elektronikus jelentéskészítés paraméterei** elemet.</span><span class="sxs-lookup"><span data-stu-id="98698-125">In the **Electronic reporting** workspace, in the **Related links** section, select **Electronic reporting parameters**.</span></span>
3. <span data-ttu-id="98698-126">Az **e-számlázási szolgáltatás** lapon a **Szolgáltatási végpont URI** mezőben adja meg az Azure földrajzi régió megfelelő szolgáltatási végpontját, amint azt a következő tábla mutatja.</span><span class="sxs-lookup"><span data-stu-id="98698-126">On the **e-Invoicing service** tab, in the **Service endpoint URI** field, enter the appropriate service endpoint for your Azure geography, as shown in the following table.</span></span>

    | <span data-ttu-id="98698-127">Adatközpont Azure földrajzi régió</span><span class="sxs-lookup"><span data-stu-id="98698-127">Datacenter Azure geography</span></span> | <span data-ttu-id="98698-128">Szolgáltatási végpont URI-címe</span><span class="sxs-lookup"><span data-stu-id="98698-128">Service endpoint URI</span></span>                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | <span data-ttu-id="98698-129">USA keleti régiója</span><span class="sxs-lookup"><span data-stu-id="98698-129">East US</span></span>                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="98698-130">USA nyugati régiója</span><span class="sxs-lookup"><span data-stu-id="98698-130">West US</span></span>                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="98698-131">Észak-EU</span><span class="sxs-lookup"><span data-stu-id="98698-131">North EU</span></span>                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="98698-132">Nyugat-EU</span><span class="sxs-lookup"><span data-stu-id="98698-132">West EU</span></span>                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

4. <span data-ttu-id="98698-133">Ellenőrizze, hogy az **Alkalmazásazonosító** mező **0cdb527f-a8d1-4bf8-9436-b352c68682b2** értékre legyen állítva.</span><span class="sxs-lookup"><span data-stu-id="98698-133">Verify that the **Application Id** field is set to **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span></span> <span data-ttu-id="98698-134">Ez egy rögzített érték.</span><span class="sxs-lookup"><span data-stu-id="98698-134">This value is a fixed value.</span></span>
5. <span data-ttu-id="98698-135">Az **LCS-környezet azonosítója** mezőbe írja be az LCS előfizetési fiókja azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="98698-135">In the **LCS Environment Id** field, enter the ID of your LCS subscription account.</span></span>
6. <span data-ttu-id="98698-136">Válassza a **Mentés** gombot, majd zárja be az oldalt.</span><span class="sxs-lookup"><span data-stu-id="98698-136">Select **Save**, and then close the page.</span></span>

## <a name="create-key-vault-secret"></a><span data-ttu-id="98698-137">Key Vault titkos kód létrehozása</span><span class="sxs-lookup"><span data-stu-id="98698-137">Create Key Vault secret</span></span>

1. <span data-ttu-id="98698-138">Jelentkezzen be a RCS-fiókba.</span><span class="sxs-lookup"><span data-stu-id="98698-138">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="98698-139">Nyissa meg a **Globalizációs funkció** munkaterületet, a **Környezet** szakaszban válassza az **e-számlázás** csempét.</span><span class="sxs-lookup"><span data-stu-id="98698-139">In the **Globalization feature** workspace, in the **Environment** section, select the **e-Invoicing** tile.</span></span>
3. <span data-ttu-id="98698-140">A **Környezet beállítása** lapon a Művelet ablaktáblán válassza ki a **Szolgáltatási környezet**, majd a **Key Vault-paraméterek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="98698-140">On the **Environment setups** page, on the action Pane, select **Service environment**, and then select **Key Vault parameters**.</span></span>
4. <span data-ttu-id="98698-141">Kulcstartó titkos kód létrehozásához válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="98698-141">Select **New** to create a key vault secret.</span></span>
5. <span data-ttu-id="98698-142">A **Név** mezőben adja meg a kulcstartó titkos kód nevét.</span><span class="sxs-lookup"><span data-stu-id="98698-142">In the **Name** field, enter the name of the key vault secret.</span></span> <span data-ttu-id="98698-143">Adjon meg egy leírást a **Leírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="98698-143">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="98698-144">A **Key Vault – URI** mezőbe másolja be a titkos kódot az Azure Key Vault megoldásból.</span><span class="sxs-lookup"><span data-stu-id="98698-144">In the **Key Vault URI** field, paste the secret from Azure Key Vault.</span></span>
7. <span data-ttu-id="98698-145">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="98698-145">Select **Save**.</span></span>

## <a name="create-storage-account-secret"></a><span data-ttu-id="98698-146">Titkos kód létrehozása tárfiókhoz</span><span class="sxs-lookup"><span data-stu-id="98698-146">Create Storage account secret</span></span>

1. <span data-ttu-id="98698-147">A **Kulcstartó paraméterei** oldalon a **Tanúsítványok** szakaszban válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="98698-147">On **Key vault parameters** page, in the **Certificates** section, select **Add**.</span></span>
2. <span data-ttu-id="98698-148">A **Név** mezőbe írja be ugyanazon tárfiók titkos kódját.</span><span class="sxs-lookup"><span data-stu-id="98698-148">In the **Name** field, enter the same of the storage account secret.</span></span> <span data-ttu-id="98698-149">Adjon meg egy leírást a **Leírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="98698-149">In the **Description** field, enter a description.</span></span>
3. <span data-ttu-id="98698-150">A **Típus** mezőben válassza ki a **Tanúsítvány** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="98698-150">In the **Type** field, select **Certificate**.</span></span>
4. <span data-ttu-id="98698-151">Válassza a **Mentés** gombot, majd zárja be az oldalt.</span><span class="sxs-lookup"><span data-stu-id="98698-151">Select **Save**, and then close the page.</span></span>

## <a name="create-an-electronic-invoicing-add-on-environment"></a><span data-ttu-id="98698-152">Az Elektronikus számlázási bővítmény környezetének létrehozása</span><span class="sxs-lookup"><span data-stu-id="98698-152">Create an Electronic invoicing add-on environment</span></span>

1. <span data-ttu-id="98698-153">Jelentkezzen be a RCS-fiókba.</span><span class="sxs-lookup"><span data-stu-id="98698-153">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="98698-154">Nyissa meg a **Globalizációs funkció** munkaterületet, a **Környezet** szakaszban válassza az **e-számlázás** csempét.</span><span class="sxs-lookup"><span data-stu-id="98698-154">In the **Globalization feature** workspace, in the **Environment** section, select the **e-Invoicing** tile.</span></span>

## <a name="create-a-service-environment"></a><span data-ttu-id="98698-155">Szolgáltatási környezet létrehozása</span><span class="sxs-lookup"><span data-stu-id="98698-155">Create a service environment</span></span>

1. <span data-ttu-id="98698-156">A **Környezet beállítása** oldalon a Művelet ablaktáblán válassza a **Szolgáltatási környezet** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="98698-156">On the **Environment setups** page, on the action Pane, select **Service environment**.</span></span>
2. <span data-ttu-id="98698-157">Válassza ki az **Új** lehetőséget egy új szolgáltatási környezet létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="98698-157">Select **New** to create a new service environment.</span></span>
3. <span data-ttu-id="98698-158">A **Név** mezőben adja meg az e-számlázási környezet nevét.</span><span class="sxs-lookup"><span data-stu-id="98698-158">In the **Name** field, enter the name of the e-Invoicing environment.</span></span> <span data-ttu-id="98698-159">Adjon meg egy leírást a **Leírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="98698-159">In the **Description** field, enter a description.</span></span>
4. <span data-ttu-id="98698-160">A **Tárterület SAS-token titkos kód** mezőben válassza ki annak a tanúsítványnak a nevét, amely a tárfiókhoz való hozzáférés hitelesítéséhez szükséges.</span><span class="sxs-lookup"><span data-stu-id="98698-160">In the **Storage SAS token secret** field, select the name of the certificate that must be used to authenticate access to the storage account.</span></span>
5. <span data-ttu-id="98698-161">A **Felhasználók** szakaszban válassza a **Hozzáadás** lehetőséget annak a felhasználónak a hozzáadásához, aki számára engedélyezett az elektronikus számlák elküldése a környezetben, valamint a tárfiókhoz való csatlakozás.</span><span class="sxs-lookup"><span data-stu-id="98698-161">In the **Users** section, select **Add** to add a user who is allowed to submit electronic invoices through the environment and also connect to the storage account.</span></span>
6. <span data-ttu-id="98698-162">A **Felhasználói azonosító** mezőbe írja be a felhasználó aliasát.</span><span class="sxs-lookup"><span data-stu-id="98698-162">In the **User ID** field, enter the alias of the user.</span></span> <span data-ttu-id="98698-163">Az **E-mail** mezőbe írja be a feladó e-mail-címét.</span><span class="sxs-lookup"><span data-stu-id="98698-163">In the **Email** field, enter the user's email address.</span></span>
7. <span data-ttu-id="98698-164">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="98698-164">Select **Save**.</span></span>
8. <span data-ttu-id="98698-165">Ha az ország-/régióspecifikus számlákhoz egy tanúsítványlánc szükséges a digitális aláírások alkalmazásához, akkor válassza a Művelet ablaktábla **Key Vault-paraméterek** elemét, majd a **Tanúsítványlánc** lehetőséget, és kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="98698-165">If your country/region-specific invoices require a chain of certificates to apply digital signatures, on the Action pane, select **Key Vault parameters**, then select **Chain of certificates**, and follow these steps:</span></span>

    1. <span data-ttu-id="98698-166">Tanúsítványlánc létrehozásához válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="98698-166">Select **New** to create a chain of certificates.</span></span>
    2. <span data-ttu-id="98698-167">A **Név** mezőbe írja be a tanúsítványlánc nevét.</span><span class="sxs-lookup"><span data-stu-id="98698-167">In the **Name** field, enter the name of the chain of certificate.</span></span> <span data-ttu-id="98698-168">Adjon meg egy leírást a **Leírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="98698-168">In the **Description** field, enter a description.</span></span>
    3. <span data-ttu-id="98698-169">A **Tanúsítványok** szakaszban válassza a **Hozzáadás** lehetőséget, ha tanúsítványt szeretne hozzáadni a lánchoz.</span><span class="sxs-lookup"><span data-stu-id="98698-169">In the **Certificates** section, select **Add** to add a certificate to the chain.</span></span>
    4. <span data-ttu-id="98698-170">A **Fel** és a **Le** gombbal módosíthatja a tanúsítványnak a láncon belül elfoglalt pozícióját.</span><span class="sxs-lookup"><span data-stu-id="98698-170">Use the **Up** or **Down** button to change the position of the certificate in the chain.</span></span>
    5. <span data-ttu-id="98698-171">Válassza a **Mentés** gombot, majd zárja be az oldalt.</span><span class="sxs-lookup"><span data-stu-id="98698-171">Select **Save**, and then close the page.</span></span>
    6. <span data-ttu-id="98698-172">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="98698-172">Close the page.</span></span>
9. <span data-ttu-id="98698-173">A Művelet ablaktáblán válassza a **Szolgáltatási környezet**, majd a **Közzététel** lehetőséget a környezet felhőben történő közzétételéhez.</span><span class="sxs-lookup"><span data-stu-id="98698-173">On **Service environment** page, on the Action Pane, select **Publish** to publish the environment to the cloud.</span></span> <span data-ttu-id="98698-174">Az **Állapot** mező értéke **Közzétéve** értékre módosul.</span><span class="sxs-lookup"><span data-stu-id="98698-174">The value of the **Status** field is changed to **Published**.</span></span>

## <a name="create-a-connected-application"></a><span data-ttu-id="98698-175">Csatlakoztatott alkalmazás létrehozása</span><span class="sxs-lookup"><span data-stu-id="98698-175">Create a connected application</span></span>

1. <span data-ttu-id="98698-176">A **Környezet beállítása** oldalon a Művelet ablaktáblán válassza a **Csatlakoztatott alkalmazások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="98698-176">On the **Environment setups** page, on the action Pane, select **Connected applications**.</span></span>
2. <span data-ttu-id="98698-177">Válassza ki az **Új** lehetőséget egy csatlakoztatott alkalmazás létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="98698-177">Select **New** to create a connected application.</span></span>
3. <span data-ttu-id="98698-178">A **Név** mezőben adja meg a csatlakoztatni kívánt alkalmazás nevét.</span><span class="sxs-lookup"><span data-stu-id="98698-178">In the **Name** field, enter the name of the application to connect.</span></span>
4. <span data-ttu-id="98698-179">Az **Alkalmazás** mezőben adja meg a csatlakozáshoz szükséges Finance and Supply Chain Management környezet URL-címét.</span><span class="sxs-lookup"><span data-stu-id="98698-179">In the **Application** field, enter the URL of the Finance and Supply Chain Management environment to connect.</span></span>
4. <span data-ttu-id="98698-180">A **Bérlő** mezőben adja meg a Finance and Supply Chain Management környezet bérlőjét.</span><span class="sxs-lookup"><span data-stu-id="98698-180">In the **Tenant** field, enter the tenant of the Finance and Supply Chain Management environment.</span></span>
5. <span data-ttu-id="98698-181">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="98698-181">Select **Save**.</span></span>
6. <span data-ttu-id="98698-182">A Művelet ablaktáblán válassza a **Kapcsolat ellenőrzése** lehetőséget a környezettel való kapcsolat teszteléséhez.</span><span class="sxs-lookup"><span data-stu-id="98698-182">On the Action Pane, select **Check connection** to test the connection with the environment.</span></span> <span data-ttu-id="98698-183">Ezután zárja be az oldalt.</span><span class="sxs-lookup"><span data-stu-id="98698-183">Then close the page.</span></span>

## <a name="link-connected-applications-to-environments"></a><span data-ttu-id="98698-184">Csatlakoztatott alkalmazások csatolása környezetekhez</span><span class="sxs-lookup"><span data-stu-id="98698-184">Link connected applications to environments</span></span>

1. <span data-ttu-id="98698-185">A **Környezet beállítása** oldalon válassza az **Új** lehetőséget, ha a környezethez hozzá szeretne rendelni egy csatlakoztatott alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="98698-185">On the **Environment setups** page, select **New** to assign a connected application to an environment.</span></span>
2. <span data-ttu-id="98698-186">A **Csatlakoztatott alkalmazás** mezőben válasszaon ki egy csatlakoztatott alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="98698-186">In the **Connected application** field, select a connected application.</span></span>
3. <span data-ttu-id="98698-187">Válassza ki a szolgáltatási környezetet a **Szolgáltatási környezet** mezőben.</span><span class="sxs-lookup"><span data-stu-id="98698-187">In the **Service environment** field, select a service environment.</span></span>
4. <span data-ttu-id="98698-188">Válassza a **Mentés** gombot, majd zárja be az oldalt.</span><span class="sxs-lookup"><span data-stu-id="98698-188">Select **Save**, and then close the page.</span></span>

## <a name="set-up-the-electronic-invoicing-add-on-integration-in-finance-and-supply-chain-management"></a><span data-ttu-id="98698-189">Elektronikus számlázási bővítmény integrációjának beállítása a Finance and Supply Chain Management szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="98698-189">Set up the Electronic invoicing add-on integration in Finance and Supply Chain Management</span></span>

### <a name="turn-on-the-electronic-invoicing-add-on-integration-feature"></a><span data-ttu-id="98698-190">Az Elektronikus számlázásbővítmény integráció funkció bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="98698-190">Turn on the Electronic invoicing add-on integration feature</span></span>

1. <span data-ttu-id="98698-191">Jelentkezzen be a Finance vagy Supply Chain Management-példányába.</span><span class="sxs-lookup"><span data-stu-id="98698-191">Sign in to your Finance or Supply Chain Management instance.</span></span>
2. <span data-ttu-id="98698-192">A **Funkciókezelés** munkaterületen keresse meg az **Elektronikus számlázási bővítmény integrációja** funkciót.</span><span class="sxs-lookup"><span data-stu-id="98698-192">In the **Feature management** workspace, search for the **Electronic invoicing add-on integration** feature.</span></span> <span data-ttu-id="98698-193">Ha ez a funkció nem jelenik meg az oldalon, válassza a **Frissítések keresése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="98698-193">If this feature doesn't appear on the page, select **Check for updates**.</span></span>
3. <span data-ttu-id="98698-194">Válassza ki a bekapcsolni kívánt funkciót, majd a részletek ablaktáblán válassza az **Engedélyezés most** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="98698-194">Select the feature, and then select **Enable now**.</span></span>

### <a name="set-up-the-service-endpoint-url"></a><span data-ttu-id="98698-195">A szolgáltatásvégpont URL-címének beállítása</span><span class="sxs-lookup"><span data-stu-id="98698-195">Set up the service endpoint URL</span></span>

1. <span data-ttu-id="98698-196">Menjen a **Szervezeti adminisztráció \> Beállítás \> Elektronikus dokumentumparaméterek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="98698-196">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="98698-197">A **Beküldési szolgáltatás** lapon a **Szolgáltatási végpont URL** mezőben adja meg az Azure földrajzi régió megfelelő szolgáltatási végpontját, amint azt a következő tábla mutatja.</span><span class="sxs-lookup"><span data-stu-id="98698-197">On the **Submission service** tab, in the **Service endpoint URL** field, enter the appropriate service endpoint for your Azure geography, as shown in the following table.</span></span>

    | <span data-ttu-id="98698-198">Adatközpont Azure földrajzi régió</span><span class="sxs-lookup"><span data-stu-id="98698-198">Datacenter Azure geography</span></span> | <span data-ttu-id="98698-199">Szolgáltatási végpont URL-címe</span><span class="sxs-lookup"><span data-stu-id="98698-199">Service endpoint URL</span></span>                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | <span data-ttu-id="98698-200">USA keleti régiója</span><span class="sxs-lookup"><span data-stu-id="98698-200">East US</span></span>                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="98698-201">USA nyugati régiója</span><span class="sxs-lookup"><span data-stu-id="98698-201">West US</span></span>                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="98698-202">Észak-EU</span><span class="sxs-lookup"><span data-stu-id="98698-202">North EU</span></span>                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="98698-203">Nyugat-EU</span><span class="sxs-lookup"><span data-stu-id="98698-203">West EU</span></span>                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

3. <span data-ttu-id="98698-204">A **Környezet** mezőben adja meg az Elektronikus számlázási bővítmény környezetének nevét.</span><span class="sxs-lookup"><span data-stu-id="98698-204">In the **Environment** field, enter the name of the Electronic invoicing add-on environment.</span></span>
4. <span data-ttu-id="98698-205">Válassza a **Mentés** gombot, majd zárja be az oldalt.</span><span class="sxs-lookup"><span data-stu-id="98698-205">Select **Save**, and then close the page.</span></span>
