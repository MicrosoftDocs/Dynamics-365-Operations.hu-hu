---
title: Első lépések a mexikói elektronikus számlázásbővítménnyel
description: Ez a témakör olyan információkat tartalmaz, amelyek bemutatják az Első lépéseket a mexikói elektronikus számlázásbővítmény Microsoft Dynamics 365 Finance és Dynamics 365 Supply Chain Management szolgáltatásban való használatát.
author: gionoder
manager: AnnBe
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 6d15a79a359b3c708b2b33893d700377a57c3eb7
ms.sourcegitcommit: cfd84321fba38e02e270d361df369a536a48efa3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/11/2020
ms.locfileid: "4512234"
---
# <a name="get-started-with-the-electronic-invoicing-add-on-for-mexico"></a><span data-ttu-id="b8a00-103">Első lépések a mexikói elektronikus számlázásbővítménnyel</span><span class="sxs-lookup"><span data-stu-id="b8a00-103">Get started with the Electronic invoicing add-on for Mexico</span></span>

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> <span data-ttu-id="b8a00-104">Előfordulhat, hogy a Mexikói elektronikus számlázásbővítmény jelenleg nem támogatja a CFDI dokumentumban elérhető összes funkciót, valamint a Microsoft Dynamics 365 Finance vagy Dynamics 365 Supply Chain Management szolgáltatással kapcsolatos beépített integrációt.</span><span class="sxs-lookup"><span data-stu-id="b8a00-104">The Electronic invoicing add-on for Mexico might not currently support all the functions that are available in the Comprobante Fiscal Digital por Internet (CFDI) document, and in the related integration that is built into Microsoft Dynamics 365 Finance or Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="b8a00-105">Ez a témakör olyan információkat tartalmaz, amelyek bemutatják a mexikói elektronikus számlázásbővítménnyel kapcsolatos első lépéseket.</span><span class="sxs-lookup"><span data-stu-id="b8a00-105">This topic provides information that will help you get started with the Electronic invoicing add-on for Mexico.</span></span> <span data-ttu-id="b8a00-106">Végigvezeti a Regulatory Configuration Services (RCS) és a Finance szolgáltatásban található ország-függő konfigurációs lépéseken.</span><span class="sxs-lookup"><span data-stu-id="b8a00-106">It guides you through the configuration steps that are country-dependent in Regulatory Configuration Services (RCS) and Finance.</span></span> <span data-ttu-id="b8a00-107">Ezenkívül végigvezeti azokon a lépéseken, amelyeket a CFDI a szolgáltatáson keresztül történő elküldése érdekében, a Finance szolgáltatásban követnie kell, valamint bemutatja, hogyan kell áttekinteni a feldolgozási eredményeket és a CFDI-számlák állapotát.</span><span class="sxs-lookup"><span data-stu-id="b8a00-107">It also guides you through the steps that you must follow in Finance to submit CFDI invoices through the service, and it explains how to review the processing results and the status of CFDI invoices.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b8a00-108">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="b8a00-108">Prerequisites</span></span>

<span data-ttu-id="b8a00-109">A témakör lépéseinek végrehajtása előtt végre kell hajtania az [Első lépések az Elektronikus számlázásbővítménnyel](e-invoicing-get-started.md) részben található lépéseket.</span><span class="sxs-lookup"><span data-stu-id="b8a00-109">Before you complete the steps in this topic, you must complete the steps in [Get started with the Electronic invoicing add-on](e-invoicing-get-started.md).</span></span>

## <a name="rcs-setup"></a><span data-ttu-id="b8a00-110">RCS beállítása</span><span class="sxs-lookup"><span data-stu-id="b8a00-110">RCS setup</span></span>

<span data-ttu-id="b8a00-111">Az RCS beállítása során a következő feladatokat kell elvégeznie:</span><span class="sxs-lookup"><span data-stu-id="b8a00-111">During the RCS setup, you will complete these tasks:</span></span>

1. <span data-ttu-id="b8a00-112">Az e-számlázási funkció importálása a CFDI-számlák feldolgozásához.</span><span class="sxs-lookup"><span data-stu-id="b8a00-112">Import the e-Invoicing feature for processing CFDI invoices.</span></span>
2. <span data-ttu-id="b8a00-113">Tekintse át azokat a formátumkonfigurációkat, amelyek a CFDI-számlákkal kapcsolatos válaszok létrehozásához, beküldéséhez és fogadásához, valamint a törléssel kapcsolatos válaszok elküldéséhez és fogadásához szükségesek.</span><span class="sxs-lookup"><span data-stu-id="b8a00-113">Review the format configurations that are required to generate, submit, and receive responses about CFDI invoices, and to submit and receive responses about cancellation.</span></span>
3. <span data-ttu-id="b8a00-114">A CFDI számlabeküldési forgatókönyveket támogató események konfigurálása.</span><span class="sxs-lookup"><span data-stu-id="b8a00-114">Configure the events that support the CFDI invoice submission scenarios.</span></span>
4. <span data-ttu-id="b8a00-115">Tegye közzé az e-számlázási funkciót a CFDI-számlákhoz.</span><span class="sxs-lookup"><span data-stu-id="b8a00-115">Publish the e-Invoicing feature for CFDI invoices.</span></span>

> [!NOTE]
> <span data-ttu-id="b8a00-116">„Az e-számlázás funkció” annak az erőforrásnak az általános neve, amely az Elektronikus számlázási bővítmény kiszolgáló felhasználásához van konfigurálva és közzétéve.</span><span class="sxs-lookup"><span data-stu-id="b8a00-116">"The e-Invoicing feature" is the generic name for the resource that is configured and published to consume the Electronic invoicing add-on server.</span></span> <span data-ttu-id="b8a00-117">Ebben az esetben a CFDI-számlák (MX) számítanak annak az e-számlázási funkciónak, amelyet be fog állítani.</span><span class="sxs-lookup"><span data-stu-id="b8a00-117">In this case, CFDI invoices (MX) are the e-Invoicing feature that you will set up.</span></span>

## <a name="import-the-e-invoicing-feature"></a><span data-ttu-id="b8a00-118">Az e-számlázási funkció importálása</span><span class="sxs-lookup"><span data-stu-id="b8a00-118">Import the e-Invoicing feature</span></span>

1. <span data-ttu-id="b8a00-119">Jelentkezzen be a RCS-fiókba.</span><span class="sxs-lookup"><span data-stu-id="b8a00-119">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="b8a00-120">Nyissa meg a **Globalizációs funkciók** munkaterületet, a **Funkciók** szakaszban válassza az **e-számlázás** csempét.</span><span class="sxs-lookup"><span data-stu-id="b8a00-120">In the **Globalization features** workspace, in the **Features** section, select the **e-Invoicing** tile.</span></span>
3. <span data-ttu-id="b8a00-121">Az **e-számlázási funkciók** oldalon jelölje be az **Importálás** lehetőséget a **CFDI-számlák (MX)** funkció Globális adattárból történő importálásához.</span><span class="sxs-lookup"><span data-stu-id="b8a00-121">On the **e-Invoicing Features** page, select **Import** to import the **CFDI invoices (MX)** feature from the Global repository.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b8a00-122">Ha nem látható a funkció a listán, válassza a **Szinkronizálás** elemet, majd ismételje meg a 3. lépést.</span><span class="sxs-lookup"><span data-stu-id="b8a00-122">If you don't see the feature in the list, select **Synchronize**, and then repeat step 3.</span></span>

![A CFDI-számlák (MX) funkció importálása](media/e-Invoicing-services-get-started-MEX-Select-Import-CFDI-feature.png)

<span data-ttu-id="b8a00-124">A **CFDI-számlák (MX)** funkció Globális adattárból történő importálásakor az összes funkcióbeállítás – ideértve a konfigurációkat és a műveleteket is – importálva lesz.</span><span class="sxs-lookup"><span data-stu-id="b8a00-124">When you import the **CFDI invoices (MX)** feature from the Global repository, all the feature settings, including configurations and actions, are also imported.</span></span>

### <a name="create-a-new-version-of-the-cfdi-invoices-mx-feature"></a><span data-ttu-id="b8a00-125">A CFDI-számlák (MX) funkció új verziójának létrehozása</span><span class="sxs-lookup"><span data-stu-id="b8a00-125">Create a new version of the CFDI invoices (MX) feature</span></span>

<span data-ttu-id="b8a00-126">Új verziót akkor lehet létrehozni, ha például az URL-címeket frissíteni kell.</span><span class="sxs-lookup"><span data-stu-id="b8a00-126">You can create a new version if, for example, URLs must be updated.</span></span> <span data-ttu-id="b8a00-127">További tájékoztatást az [E-számlázás CFDI](tasks/mx-00010-e-invoicing-cfdi.md) részben talál.</span><span class="sxs-lookup"><span data-stu-id="b8a00-127">For more information, see [E-invoicing CFDI](tasks/mx-00010-e-invoicing-cfdi.md).</span></span>

- <span data-ttu-id="b8a00-128">Az **e-számlázási funkciók** oldal **Verziók** lapján válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8a00-128">On the **e-Invoicing Features** page, on the **Versions** tab, select **New**.</span></span>

![Új e-számlázási funkcióverzió hozzáadása](media/e-Invoicing-services-get-started-MEX-Select-New-e-Invoicing-feature.png)

### <a name="update-the-configuration-version"></a><span data-ttu-id="b8a00-130">A konfigurációverzió frissítése</span><span class="sxs-lookup"><span data-stu-id="b8a00-130">Update the configuration version</span></span>

1. <span data-ttu-id="b8a00-131">Az **e-számlázási funkciók** oldal **Konfigurációk** lapján válassza ki a **Hozzáadás** vagy a **Törlés** lehetőséget a konfigurációverziók (ER-fájlformátum-konfigurációk) kezeléséhez.</span><span class="sxs-lookup"><span data-stu-id="b8a00-131">On the **e-Invoicing Features** page, on the **Configurations** tab, select **Add** or **Delete** to manage the configuration versions (ER file format configurations).</span></span>

    ![E-számlázás funkciókonfigurációk kezelése](media/e-Invoicing-services-get-started-MEX-Manage-e-Invoicing-feature-Configurations.png)

    <span data-ttu-id="b8a00-133">Új verzió létrehozásakor az összes konfiguráció a legutóbbi közzétett verzióból öröklődik.</span><span class="sxs-lookup"><span data-stu-id="b8a00-133">When you create a new version, all configurations are inherited from the last published version.</span></span> <span data-ttu-id="b8a00-134">A CFDI-számlák feldolgozásához a következő konfigurációk szükségesek:</span><span class="sxs-lookup"><span data-stu-id="b8a00-134">To process CFDI invoices, the following configurations are required:</span></span>

    - <span data-ttu-id="b8a00-135">CFDI-számla (BusinessDocumentService)</span><span class="sxs-lookup"><span data-stu-id="b8a00-135">CFDI invoice (BusinessDocumentService)</span></span>
    - <span data-ttu-id="b8a00-136">CFDI-válaszüzenet importálása</span><span class="sxs-lookup"><span data-stu-id="b8a00-136">CFDI response message import</span></span>
    - <span data-ttu-id="b8a00-137">CFDI-hibanapló importálása</span><span class="sxs-lookup"><span data-stu-id="b8a00-137">CFDI error log import</span></span>
    - <span data-ttu-id="b8a00-138">CFDI-törlési kérelem (MX) (BusinessDocumentService)</span><span class="sxs-lookup"><span data-stu-id="b8a00-138">CFDI cancelation request (MX) (BusinessDocumentService)</span></span>
    - <span data-ttu-id="b8a00-139">CFDI-számla (BusinessDocumentService)</span><span class="sxs-lookup"><span data-stu-id="b8a00-139">CFDI invoice (BusinessDocumentService)</span></span>

2. <span data-ttu-id="b8a00-140">A listáról válassza ki a kívánt konfigurációverziót, majd a **Szerkesztés** vagy **Nézet** elemet kijelölve nyissa meg a **Formátumtervező** oldalt, amelyen szerkesztheti és megtekintheti a konfigurációt.</span><span class="sxs-lookup"><span data-stu-id="b8a00-140">In the list, select a configuration version, and then select **Edit** or **View** to open the **Format designer** page, where you can edit or view the configuration.</span></span>

    ![A Formátumtervező lap megnyitása](media/e-Invoicing-services-get-started-MEX-Configuration-ER-format-designer.png)

3. <span data-ttu-id="b8a00-142">Az ER-formátum fájlkonfiguráció szerkesztéséhez és megtekintéséhez használja a **Formátumtervező** lapot.</span><span class="sxs-lookup"><span data-stu-id="b8a00-142">Use the **Format designer** page to edit and view the ER format file configurations.</span></span> <span data-ttu-id="b8a00-143">További információ: [Elektronikus dokumentum-konfigurációk létrehozása](../../dev-itpro/analytics/electronic-reporting-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="b8a00-143">For more information, see [Create electronic document configurations](../../dev-itpro/analytics/electronic-reporting-configuration.md).</span></span>

    ![Formátumtervező oldal](media/e-Invoicing-services-get-started-MEX-ER-format-designer.png)

## <a name="manage-the-e-invoicing-feature-setups"></a><span data-ttu-id="b8a00-145">Kezelje az e-számlázás funkció beállításait</span><span class="sxs-lookup"><span data-stu-id="b8a00-145">Manage the e-Invoicing feature setups</span></span>

- <span data-ttu-id="b8a00-146">Az **e-számlázási funkciók** oldal **Beállítások** lapján válassza a **Hozzáadás**, **Törlés** vagy **Szerkesztés** parancsot az e-számlázási funkciók beállításainak kezeléséhez.</span><span class="sxs-lookup"><span data-stu-id="b8a00-146">On the **e-Invoicing Features** page, on the **Setups** tab, select **Add**, **Delete**, or **Edit** to manage the e-Invoicing feature setups.</span></span>

![Az e-számlázás funkció beállításainak kezelése](media/e-Invoicing-services-get-started-MEX-Manage-e-Invoicing-feature-Setup.png)

<span data-ttu-id="b8a00-148">A CFDI-számlák engedélyezésre való beküldéséhez (XML-fájl létrehozásához, XML-fájl elküldéséhez és a válasz feldolgozásához) be kell állítani az **Értékesítési számla** funkciót.</span><span class="sxs-lookup"><span data-stu-id="b8a00-148">To submit CFDI invoices for authorization (generate the XML file, submit the XML file, and process the response), the **Sales invoice** feature setup is required.</span></span>

<span data-ttu-id="b8a00-149">A CFDI-számla érvénytelenítésre való beküldéséhez az **Érvénytelenítés** és a **Visszavonás** funkció beállítására van szükség.</span><span class="sxs-lookup"><span data-stu-id="b8a00-149">To submit CFDI invoice cancellation, the **Cancellation** and **Cancel** feature setups are required.</span></span>

### <a name="configure-the-sales-invoice-feature-setup"></a><span data-ttu-id="b8a00-150">Az Értékesítési számla funkció beállításainak konfigurálása</span><span class="sxs-lookup"><span data-stu-id="b8a00-150">Configure the Sales invoice feature setup</span></span>

1. <span data-ttu-id="b8a00-151">Az **e-számlázási funkciók** oldal **Beállítások** lapjának **Funkcióbeállítás** oszlopában válassza ki az **Értékesítési számla** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8a00-151">On the **e-Invoicing Features** page, on the **Setups** tab, in the **Feature setup** column, select **Sales invoice**.</span></span>
2. <span data-ttu-id="b8a00-152">Válassza a **Szerkesztés** lehetőséget a műveletek, alkalmazhatósági szabályokat és a változók konfigurálásához.</span><span class="sxs-lookup"><span data-stu-id="b8a00-152">Select **Edit** to configure the actions, applicability rules, and variables.</span></span>

    ![Az e-számlázás funkció beállításainak szerkesztése](media/e-Invoicing-services-get-started-MEX-Edit-e-Invoicing-feature-setup.png)

3. <span data-ttu-id="b8a00-154">A **Funkcióverzió beállítása** oldalon válassza ki a **Műveletek** lapot a műveletek listájának kezeléséhez.</span><span class="sxs-lookup"><span data-stu-id="b8a00-154">On the **Feature version setup** page, select the **Actions** tab to manage the list of actions.</span></span> <span data-ttu-id="b8a00-155">A műveletek határozzák meg azokat a műveleteket, amelyeket az esemény teljes végrehajtásához sorrendben kell végrehajtani.</span><span class="sxs-lookup"><span data-stu-id="b8a00-155">Actions define a list of operations that must be run in sequential order to accomplish full execution of the event.</span></span>

    ![Műveletek lap](media/e-Invoicing-services-get-started-MEX-Select-Actions.png)

    | <span data-ttu-id="b8a00-157">Műveletazonosító</span><span class="sxs-lookup"><span data-stu-id="b8a00-157">Action ID</span></span> | <span data-ttu-id="b8a00-158">Művelet</span><span class="sxs-lookup"><span data-stu-id="b8a00-158">Action</span></span>                   | <span data-ttu-id="b8a00-159">Művelet neve</span><span class="sxs-lookup"><span data-stu-id="b8a00-159">Action name</span></span>                                  | <span data-ttu-id="b8a00-160">Művelet leírása</span><span class="sxs-lookup"><span data-stu-id="b8a00-160">Action description</span></span>                                          |
    |-----------|--------------------------|----------------------------------------------|-------------------------------------------------------------|
    | <span data-ttu-id="b8a00-161">1</span><span class="sxs-lookup"><span data-stu-id="b8a00-161">1</span></span>         | <span data-ttu-id="b8a00-162">Dokumentum átalakítása</span><span class="sxs-lookup"><span data-stu-id="b8a00-162">Transform document</span></span>       | <span data-ttu-id="b8a00-163">CFDI e-számla létrehozása digitális bejelentkezés nélkül</span><span class="sxs-lookup"><span data-stu-id="b8a00-163">Generate CFDI E-Invoice without digital sign</span></span> | <span data-ttu-id="b8a00-164">CFDI e-számla létrehozása.</span><span class="sxs-lookup"><span data-stu-id="b8a00-164">Generate the CFDI e-invoice.</span></span>                                |
    | <span data-ttu-id="b8a00-165">2</span><span class="sxs-lookup"><span data-stu-id="b8a00-165">2</span></span>         | <span data-ttu-id="b8a00-166">Dokumentum aláírása</span><span class="sxs-lookup"><span data-stu-id="b8a00-166">Sign document</span></span>            | <span data-ttu-id="b8a00-167">Digitális aláírás</span><span class="sxs-lookup"><span data-stu-id="b8a00-167">Digital sign</span></span>                                 | <span data-ttu-id="b8a00-168">A beküldeni kívánt e-számla digitális aláírása.</span><span class="sxs-lookup"><span data-stu-id="b8a00-168">Digitally sign the e-invoice for submission.</span></span>                |
    | <span data-ttu-id="b8a00-169">3</span><span class="sxs-lookup"><span data-stu-id="b8a00-169">3</span></span>         | <span data-ttu-id="b8a00-170">Mexikói PAC-szolgáltatás hívása</span><span class="sxs-lookup"><span data-stu-id="b8a00-170">Call Mexican PAC service</span></span> | <span data-ttu-id="b8a00-171">CFDI e-számla beküldése</span><span class="sxs-lookup"><span data-stu-id="b8a00-171">Submit CFDI E-Invoice</span></span>                        | <span data-ttu-id="b8a00-172">A Windows kommunikációs alaprendszer (WCF) vevő elküldi a CFDI e-számlát.</span><span class="sxs-lookup"><span data-stu-id="b8a00-172">The Windows Communication Foundation (WCF) client submits the CFDI e-invoice.</span></span> |
    | <span data-ttu-id="b8a00-173">4</span><span class="sxs-lookup"><span data-stu-id="b8a00-173">4</span></span>         | <span data-ttu-id="b8a00-174">Folyamatválasz</span><span class="sxs-lookup"><span data-stu-id="b8a00-174">Process response</span></span>         | <span data-ttu-id="b8a00-175">Webszolgáltatás válaszának elemzése</span><span class="sxs-lookup"><span data-stu-id="b8a00-175">Analyze web service response</span></span>                 | <span data-ttu-id="b8a00-176">Elemezze a webszolgáltatás válaszát, és küldje vissza a hibanaplót.</span><span class="sxs-lookup"><span data-stu-id="b8a00-176">Analyze the web service response, and return the error log.</span></span> |

### <a name="set-up-the-url-for-mexican-pac-web-services"></a><span data-ttu-id="b8a00-177">A mexikói PAC webszolgáltatások URL-címének beállítása</span><span class="sxs-lookup"><span data-stu-id="b8a00-177">Set up the URL for Mexican PAC web services</span></span> 

1. <span data-ttu-id="b8a00-178">A **Funkcióverzió beállítása** oldal **Műveletek** lapjának **Műveletek** gyorslapján válassza a **mexikói PAC szolgáltatás hívása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8a00-178">On the **Feature version setup** page, on the **Actions** tab, on the **Actions** FastTab, select **Call Mexican PAC service**.</span></span>
2. <span data-ttu-id="b8a00-179">A **Paraméterek** gyorslap **URL-cím** mezőjébe írja be a webszolgáltatás URL-címét a CFDI-számla küldéséhez.</span><span class="sxs-lookup"><span data-stu-id="b8a00-179">On the **Parameters** FastTab, in the **URL address** field, enter the URL of the web service for CFDI invoice submission.</span></span>

> [!NOTE]
> <span data-ttu-id="b8a00-180">Kövesse ugyanezeket a lépéseket a **Visszavonás** és az **Érvénytelenítési kérelem** funkció beállításaihoz a **mexikói PAC szolgáltatás** művelet URL-címének frissítéséhez.</span><span class="sxs-lookup"><span data-stu-id="b8a00-180">Use the same steps to update the URL for **Call Mexican PAC service** action for the **Cancel** and **Cancelation request** feature setups.</span></span>

## <a name="assign-the-draft-version-to-an-e-invoicing-environment"></a><span data-ttu-id="b8a00-181">A Piszkozat verzió hozzárendelése e-számlázási környezethez</span><span class="sxs-lookup"><span data-stu-id="b8a00-181">Assign the Draft version to an e-Invoicing environment</span></span>

1. <span data-ttu-id="b8a00-182">Az **e-számlázási funkciók** oldal **Környezetek** lapján válassza az **Engedélyezés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8a00-182">On the **e-Invoicing Features** page, on the **Environments** tab, select **Enable**.</span></span>
2. <span data-ttu-id="b8a00-183">A **Környezet** mezőben válassza ki a környezetet.</span><span class="sxs-lookup"><span data-stu-id="b8a00-183">In the **Environment** field, select the environment.</span></span>
3. <span data-ttu-id="b8a00-184">A **Hatálybalépés dátuma** mezőben válassza ki azt a dátumot, amikortól a környezetnek hatályossá kell válnia.</span><span class="sxs-lookup"><span data-stu-id="b8a00-184">In the **Effective from** field, select the date when the environment should become effective.</span></span>
3. <span data-ttu-id="b8a00-185">Válassza az **Engedélyezés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8a00-185">Select **Enable**.</span></span>

![E-számlázási környezet engedélyezése](media/e-Invoicing-services-get-started-MEX-Enable-e-Invoicing-Environment.png)

## <a name="change-the-version-status-to-completed"></a><span data-ttu-id="b8a00-187">A verzió állapotának módosítása Befejezett értékre</span><span class="sxs-lookup"><span data-stu-id="b8a00-187">Change the version status to Completed</span></span>

1. <span data-ttu-id="b8a00-188">Az **e-számlázási funkciók** oldal **Verziók** lapján válassza ki a **Piszkozat** állapotú e-számlázási funkció verzióját.</span><span class="sxs-lookup"><span data-stu-id="b8a00-188">On the **e-Invoicing Features** page, on the **Versions** tab, select the version of the e-Invoicing feature that has a status of **Draft**.</span></span>
2. <span data-ttu-id="b8a00-189">Válassza az **Állapot módosítása \>Teljes** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8a00-189">Select **Change status \> Complete**.</span></span>

## <a name="change-the-version-status-to-published"></a><span data-ttu-id="b8a00-190">A verzió állapotának módosítása Közzétett értékre</span><span class="sxs-lookup"><span data-stu-id="b8a00-190">Change the version status to Published</span></span>

- <span data-ttu-id="b8a00-191">Az **e-számlázási funkciók** oldal **Verziók** lapján válassza az **Állapot módosítása \> Közzétett** értékre lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8a00-191">On the **e-Invoicing Features** page, on the **Versions** tab, select **Change status \> Publish**.</span></span>

## <a name="publish-the-e-invoicing-feature"></a><span data-ttu-id="b8a00-192">Tegye közzé az e-számlázási funkciót</span><span class="sxs-lookup"><span data-stu-id="b8a00-192">Publish the e-Invoicing feature</span></span>

1. <span data-ttu-id="b8a00-193">Az **e-számlázási funkciók** oldalon jelölje be a **Verziók** lapot a **CFDI-számlák (MX)** funkció állapotának kezeléséhez.</span><span class="sxs-lookup"><span data-stu-id="b8a00-193">On the **e-Invoicing Features** page, select the **Versions** tab to manage the status of the **CFDI invoices (MX)** feature.</span></span>
2. <span data-ttu-id="b8a00-194">A funkció állapotának módosításához jelölje be az **Állapot módosítésa** elemet.</span><span class="sxs-lookup"><span data-stu-id="b8a00-194">Select **Change status** to change the status of the feature.</span></span>

![Az e-számlázási funkció állapotának módosítása](media/e-Invoicing-services-get-started-MEX-Change-status-of-e-Invoicing-feature.png)

## <a name="set-up-electronic-invoicing-add-on-integration-in-finance"></a><span data-ttu-id="b8a00-196">Az Elektronikus számlázásbővítmény integrációjának beállítása a Finance szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="b8a00-196">Set up Electronic invoicing add-on integration in Finance</span></span>

<span data-ttu-id="b8a00-197">Az Elektronikus számlázásbővítmény Finance szolgáltatásban történő beállításához a következő feladatokat kell elvégeznie:</span><span class="sxs-lookup"><span data-stu-id="b8a00-197">To set up the Electronic invoicing add-on in Finance, you will complete these tasks:</span></span>

1. <span data-ttu-id="b8a00-198">Importálja az ER-adatmodellt, az ER-adatmodell-leképezést, valamint a CFDI-számlákhoz szükséges formátumokat.</span><span class="sxs-lookup"><span data-stu-id="b8a00-198">Import the ER data model, the ER data model mapping, and the formats that are required for CFDI invoices.</span></span>
2. <span data-ttu-id="b8a00-199">A CFDI-számlák frissítéséhez szükséges választípusok konfigurálása.</span><span class="sxs-lookup"><span data-stu-id="b8a00-199">Configure response types for updating the CFDI invoices.</span></span> <span data-ttu-id="b8a00-200">Ezek a választípusok a jogosult minősítésszolgáltató (PAC) kiszolgáló válaszához használatosak.</span><span class="sxs-lookup"><span data-stu-id="b8a00-200">These response types are used for the response from the authorized certification provider (PAC) server.</span></span>

### <a name="import-the-er-data-model-er-data-model-mapping-and-context-configurations-for-cfdi-invoices"></a><span data-ttu-id="b8a00-201">Importálja az ER-adatmodellt, az ER-adatmodell-leképezést, valamint a kontextus-konfigurációkat a CFDI-számlákhoz</span><span class="sxs-lookup"><span data-stu-id="b8a00-201">Import the ER data model, ER data model mapping, and context configurations for CFDI invoices</span></span>

1. <span data-ttu-id="b8a00-202">Bejelentkezés a Finance szolgáltatásba.</span><span class="sxs-lookup"><span data-stu-id="b8a00-202">Sign in to Finance.</span></span>
2. <span data-ttu-id="b8a00-203">Az **Elektronikus jelentéskészítés** munkaterületen, a **Konfigurációszolgáltatók** szakaszban, válassza a **Microsoft** címet.</span><span class="sxs-lookup"><span data-stu-id="b8a00-203">In the **Electronic reporting** workspace, in the **Configuration providers** section, select the **Microsoft** title.</span></span> <span data-ttu-id="b8a00-204">Győződjön meg róla, hogy ez a konfigurációszolgáltató **Aktív** értékre van állítva.</span><span class="sxs-lookup"><span data-stu-id="b8a00-204">Make sure that this configuration provider is set to **Active**.</span></span> <span data-ttu-id="b8a00-205">A szolgáltatók **Aktív** értékre állításával kapcsolatban tekintse át a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11) elemet.</span><span class="sxs-lookup"><span data-stu-id="b8a00-205">For information about how to set a provider to **Active**, see [Create configuration providers and mark them as active](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11).</span></span>
3. <span data-ttu-id="b8a00-206">Válassza ki a **Tárházak** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8a00-206">Select **Repositories**.</span></span>
4. <span data-ttu-id="b8a00-207">Válassza ki a **Globális erőforrás \> Megnyitás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8a00-207">Select **Global resource \> Open**.</span></span>
5. <span data-ttu-id="b8a00-208">**Számlamodell**, **Számlamodell-lekérdezés**, **CFDI-számlaformátum (MX)**, **CFDI-számlavisszavonási kérelemformátum (MX)**, és a **CFDI-számla érvénytelenítés formátum (MX)** importálása.</span><span class="sxs-lookup"><span data-stu-id="b8a00-208">Import **Invoice model**, **Invoice model mapping**, **CFDI invoice format (MX)**, **CFDI invoice cancelation request format (MX)**, and **CFDI invoice cancel format (MX)**.</span></span>

### <a name="turn-on-the-feature-for-processing-cfdi-invoices"></a><span data-ttu-id="b8a00-209">Kapcsolja be a CFDI-számlák feldolgozására szolgáló funkciót</span><span class="sxs-lookup"><span data-stu-id="b8a00-209">Turn on the feature for processing CFDI invoices</span></span>

1. <span data-ttu-id="b8a00-210">Menjen a **Szervezeti adminisztráció \> Beállítás \> Elektronikus dokumentumparaméterek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b8a00-210">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="b8a00-211">A **Funkciók** lapon válassza ki az **Engedélyezés** jelölőnégyzetet az **MX-00010** és **MX-00016** funkcióhivatkozások soraiban.</span><span class="sxs-lookup"><span data-stu-id="b8a00-211">On the **Features** tab, select the **Enable** check box in the rows for feature references **MX-00010** and **MX-00016**.</span></span>

![A CFDI-számlák feldolgozására szolgáló funkció bekapcsolása](media/e-Invoicing-services-get-started-MEX-Enable-CFDI-feature.png)

### <a name="import-er-configurations-and-set-up-the-response-types-for-updating-cfdi-invoices"></a><span data-ttu-id="b8a00-213">A választípusok beállítása a CFDI-számlák frissítésére, illetve az ER-konfigurációk importálása</span><span class="sxs-lookup"><span data-stu-id="b8a00-213">Import ER configurations and set up the response types for updating CFDI invoices</span></span>

#### <a name="import-er-configurations"></a><span data-ttu-id="b8a00-214">ER-konfigurációk importálása</span><span class="sxs-lookup"><span data-stu-id="b8a00-214">Import ER configurations</span></span>

1. <span data-ttu-id="b8a00-215">Az **Elektronikus jelentéskészítés** munkaterületen, a **Konfigurációszolgáltatók** szakaszban, válassza a **Microsoft** címet.</span><span class="sxs-lookup"><span data-stu-id="b8a00-215">In the **Electronic reporting** workspace, in the **Configuration providers** section, select the **Microsoft** title.</span></span>
3. <span data-ttu-id="b8a00-216">Válassza ki a **Tárházak** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8a00-216">Select **Repositories**.</span></span>
4. <span data-ttu-id="b8a00-217">Válassza ki a **Globális erőforrás \> Megnyitás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8a00-217">Select **Global resource \> Open**.</span></span>
5. <span data-ttu-id="b8a00-218">A **Válaszüzenet-modell**, a **CFDI-hibanapló-importálás (MX)**, és a **CFDI-üzenetválasz-importálás (MX)** importálása.</span><span class="sxs-lookup"><span data-stu-id="b8a00-218">Import **Response message model**, **CFDI error log import (MX)**, and **CFDI response message import (MX)**.</span></span>

#### <a name="set-up-the-response-types"></a><span data-ttu-id="b8a00-219">A választípusok beállítása</span><span class="sxs-lookup"><span data-stu-id="b8a00-219">Set up the response types</span></span>

1. <span data-ttu-id="b8a00-220">Menjen a **Szervezeti adminisztráció \> Beállítás \> Elektronikus dokumentumparaméterek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b8a00-220">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="b8a00-221">Az **Elektronikus dokument** lapon válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8a00-221">On the **Electronic document** tab, select **Add**.</span></span>
3. <span data-ttu-id="b8a00-222">Adja meg a vevői számla naplóját, majd a **Tábla neve** mezőben válassza ki a projekt számláját.</span><span class="sxs-lookup"><span data-stu-id="b8a00-222">Enter the customer invoice journal, and then, in the **Table name** field, select the project invoice.</span></span>
4. <span data-ttu-id="b8a00-223">Minden táblához határozzon meg egy kapcsolódó dokumentumkontextust:</span><span class="sxs-lookup"><span data-stu-id="b8a00-223">For each table, define a related document context:</span></span>

    - <span data-ttu-id="b8a00-224">A **Vevői számla naplóban** adja meg az **Vevői számla kontextusát**.</span><span class="sxs-lookup"><span data-stu-id="b8a00-224">For **Customer invoice journal**, enter **Customer invoice context**.</span></span>
    - <span data-ttu-id="b8a00-225">A **Projektszámlához** adja meg a **Projektszámla kontextusát**.</span><span class="sxs-lookup"><span data-stu-id="b8a00-225">For **Project invoice**, enter **Project invoice context**.</span></span>

4. <span data-ttu-id="b8a00-226">Válassza ki azokat a konfigurálni kívánt **Választípusokat**, amelyek a vevői számlanaplón vagy a projektszámlán keresztül visszaállíthatók az elektronikus számlázásból.</span><span class="sxs-lookup"><span data-stu-id="b8a00-226">Select **Response types** to configure the response types that can be returned from the Electronic invoicing add-on and included in a customer invoice journal or project invoice.</span></span>
5. <span data-ttu-id="b8a00-227">Válassza az **Új**, majd a **Válasz típusa** mezőt, majd a **Válasz** elemet.</span><span class="sxs-lookup"><span data-stu-id="b8a00-227">Select **New**, and then, in the **Response type** field, select **Response**.</span></span>
6. <span data-ttu-id="b8a00-228">A **Beküldés állapota** mezőben válassza a **Függőben** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8a00-228">In the **Submission status** field, select **Pending**.</span></span>
7. <span data-ttu-id="b8a00-229">A **Modell-leképezés** mezőben válassza a **Válaszüzenet importálási formátuma – Modell-leképezés válaszüzenetből** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8a00-229">In the **Model mapping** field, select **Response message import format – Model mapping from response message**.</span></span>
8. <span data-ttu-id="b8a00-230">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8a00-230">Select **Save**.</span></span>
9. <span data-ttu-id="b8a00-231">Válassza az **Új**, majd a **Válasz típusa** mezőt, majd a **Válaszadatok** elemet.</span><span class="sxs-lookup"><span data-stu-id="b8a00-231">Select **New**, and then, in the **Response type** field, select **ResponseData**.</span></span>
10. <span data-ttu-id="b8a00-232">A **Beküldés állapota** mezőben válassza a **Függőben** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8a00-232">In the **Submission status** field, select **Pending**.</span></span>
11. <span data-ttu-id="b8a00-233">A **Modell-leképezés** mezőben válassza ki a **CFDI-válaszadatok importálási formátuma (részletek) – Válaszadatok importálása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8a00-233">In the **Model mapping** field, select **CFDI response data import format (details) – Response data import**.</span></span>
12. <span data-ttu-id="b8a00-234">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8a00-234">Select **Save**.</span></span>

## <a name="process-electronic-invoices-in-finance"></a><span data-ttu-id="b8a00-235">Elektronikus számlák feldolgozása a Finance szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="b8a00-235">Process electronic invoices in Finance</span></span> 

<span data-ttu-id="b8a00-236">A CFDI-számlák Finance szolgáltatásban lévő Elektronikus számlázásbővítményen keresztül történő feldolgozásakor a következő feladatokat lehet végrehajtani:</span><span class="sxs-lookup"><span data-stu-id="b8a00-236">During the processing of CFDI invoices in Finance through the Electronic invoicing add-on, you can perform the following tasks:</span></span>

- <span data-ttu-id="b8a00-237">CFDI-számlák beküldése.</span><span class="sxs-lookup"><span data-stu-id="b8a00-237">Submit CFDI invoices.</span></span>
- <span data-ttu-id="b8a00-238">A beküldési végrehajtási naplók megtekintése.</span><span class="sxs-lookup"><span data-stu-id="b8a00-238">View the submission execution logs.</span></span>
- <span data-ttu-id="b8a00-239">CFDI-számla érvénytelenítésének beküldése.</span><span class="sxs-lookup"><span data-stu-id="b8a00-239">Submit the cancellation of a CFDI invoice.</span></span>

### <a name="submit-cfdi-invoices"></a><span data-ttu-id="b8a00-240">CFDI-számlák beküldése</span><span class="sxs-lookup"><span data-stu-id="b8a00-240">Submit CFDI invoices</span></span>

<span data-ttu-id="b8a00-241">A **Konfigurálható elektronikus számlázásbővítmény integrációja** funkció bekapcsolását követően a CFDI-számlák küldéséhez szükséges **Elektronikus számlák exportálása/importálása** folyamat (**Kinnlevőségek \> Számlák \> E-számlák**) már nem használható.</span><span class="sxs-lookup"><span data-stu-id="b8a00-241">After you turn on the **Configurable Electronic invoicing add-on integration** feature, the **Export/Import electronic invoice** process (**Accounts receivable \> Invoices \> E-invoices**) for submitting CFDI invoices can no longer be used.</span></span> <span data-ttu-id="b8a00-242">Ezt felváltotta egy új, **Elektronikus dokumentumok beküldése** nevű folyamat.</span><span class="sxs-lookup"><span data-stu-id="b8a00-242">It's replaced by a new process that is named **Submit electronic documents**.</span></span>

> [!NOTE]
> <span data-ttu-id="b8a00-243">Az új **Elektronikus dokumentumok beküldése folyamat** használata előtt győződjön meg arról, hogy a mexikói e-számlákhoz szükséges beállítások el lettek végezve.</span><span class="sxs-lookup"><span data-stu-id="b8a00-243">Before you use the new **Submit electronic documents** process, verify that the setup that is required for Mexican e-invoices was completed.</span></span> <span data-ttu-id="b8a00-244">További tájékoztatást a [CFDI-elrendezés 3.3-as verziója](https://docs.microsoft.com/dynamics365/finance/localizations/latam-mex-cfdi-3-3) részben talál.</span><span class="sxs-lookup"><span data-stu-id="b8a00-244">For more information, see [CFDI layout version 3.3](https://docs.microsoft.com/dynamics365/finance/localizations/latam-mex-cfdi-3-3).</span></span>

1. <span data-ttu-id="b8a00-245">Menjen a **Szervezeti adminisztráció \> Időszakos \> Elektronikus dokumentumok \> Elektronikus dokumentumok beküldése** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b8a00-245">Go to **Organization administration \> Periodic \> Electronic documents \> Submit electronic documents**.</span></span>
2. <span data-ttu-id="b8a00-246">A dokumentumok első beküldésekor mindig **Nem** értékre kell állítania a **Dokumentumok újraküldése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8a00-246">For the first submission of any document, always set the **Resubmit documents** option to **No**.</span></span> <span data-ttu-id="b8a00-247">Ha a szolgáltatáson keresztül újra kell küldenie a dokumentumot, akkor ezt a beállítást állítsa **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="b8a00-247">If you must resubmit a document through the service, set this option to **Yes**.</span></span>
3. <span data-ttu-id="b8a00-248">A **Szerepeltetni kívánt rekordok** gyorslapon válassza a **Szűrő** lehetőséget a **Lekérdezés** párbeszédpanel megnyitásához, amelyen létrehozhat egy lekérdezést, hogy milyen dokumentumok legyenek kiválasztva a beküldéshez.</span><span class="sxs-lookup"><span data-stu-id="b8a00-248">On the **Records to include** FastTab, select **Filter** to open the **Inquiry** dialog box, where you can build a query to select documents for submission.</span></span>

![CFDI-dokumentum beküldése](media/e-Invoicing-services-get-started-MEX-Submit-CFDI-document.png)

> [!NOTE]
> <span data-ttu-id="b8a00-250">A dokumentum szolgáltatáson keresztüli beküldésének első kísérlete során a program rákérdez, hogy megerősíti-e a kapcsolatot az Elektronikus számlázásbővítménnyel.</span><span class="sxs-lookup"><span data-stu-id="b8a00-250">During your first attempt to submit a document through the service, you will be prompted to confirm the connection with the Electronic invoicing add-on.</span></span> <span data-ttu-id="b8a00-251">Válassza a **Kattintson az Elektronikus dokumentumbeküldési szolgáltatáshoz való csatlakozáshoz**.</span><span class="sxs-lookup"><span data-stu-id="b8a00-251">Select **Click here to connect to Electronic Document Submission Service**.</span></span>

### <a name="view-submission-logs"></a><span data-ttu-id="b8a00-252">Beküldési naplók megtekintése</span><span class="sxs-lookup"><span data-stu-id="b8a00-252">View submission logs</span></span>

<span data-ttu-id="b8a00-253">Megtekintheti az beküldött dokumentumok beküldési naplóit, vagy csak egy adott dokumentumot.</span><span class="sxs-lookup"><span data-stu-id="b8a00-253">You can view the submission logs for all submitted documents or for just one submitted document.</span></span>

#### <a name="view-all-submission-logs"></a><span data-ttu-id="b8a00-254">Az összes beküldési napló megtekintése</span><span class="sxs-lookup"><span data-stu-id="b8a00-254">View all submission logs</span></span>

<span data-ttu-id="b8a00-255">A **Konfigurálható elektronikus számlázásbővítmény integráció** funkció bekapcsolása után egy új lap érhető el, amellyel nyomon követheti a dokumentum beküldési folyamatát.</span><span class="sxs-lookup"><span data-stu-id="b8a00-255">After you turn on the **Configurable Electronic invoicing add-on integration** feature, a new page is available that lets you follow up on the document submission process.</span></span> <span data-ttu-id="b8a00-256">Ezen a lapon megtekintheti az összes beküldött dokumentum beküldési naplóját.</span><span class="sxs-lookup"><span data-stu-id="b8a00-256">You can use this page to view the submission logs for all submitted documents.</span></span>

1. <span data-ttu-id="b8a00-257">Menjen a **Szervezeti adminisztráció \> Időszakos \> Elektronikus dokumentumok \> Elektronikus dokumentumbeküldési napló** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b8a00-257">Go to **Organization administration \> Periodic \> Electronic documents \> Electronic document submission log**.</span></span>
2. <span data-ttu-id="b8a00-258">A **Dokumentumtípus** mezőben válassza ki a **Vevői számlanapló** lehetőséget a szükséges elektronikus dokumentumok szűréséhez.</span><span class="sxs-lookup"><span data-stu-id="b8a00-258">In the **Document type** field, select **Customer invoice journal** to filter for the required electronic documents.</span></span>

    ![A dokumentumtípus kiválasztása a beküldési naplók megtekintéséhez](media/e-Invoicing-services-get-started-MEX-Select-document-type-for-viewing-submission-log.png)

3. <span data-ttu-id="b8a00-260">A Művelet ablaktáblán válassza ki a **Lekérdezések \> Beküldések részletei** lehetőséget a beküldési végrehajtási naplók részleteinek megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="b8a00-260">On the Action Pane, select **Inquiries \> Submission details** to view the details of the submission execution logs.</span></span>

    ![A beküldési napló részleteinek megtekintése](media/e-Invoicing-services-get-started-MEX-View-submission-log-details.png)

<span data-ttu-id="b8a00-262">A beküldési naplókban lévő adatok három gyorslap között vannak felosztva:</span><span class="sxs-lookup"><span data-stu-id="b8a00-262">The information in the submission logs is divided among three FastTabs:</span></span>

- <span data-ttu-id="b8a00-263">**Műveletek feldolgozása** – Ez a gyorslap azon végrehajtási naplót mutatja meg, amely az RCS-ben beállított funkcióverzióban konfigurált műveletekhez tartozik.</span><span class="sxs-lookup"><span data-stu-id="b8a00-263">**Processing actions** – This FastTab shows the execution log for the actions that are configured in the feature version that was set up in RCS.</span></span> <span data-ttu-id="b8a00-264">Az **Állapot** oszlop azt jelzi, hogy a művelet futtatása sikeres volt-e.</span><span class="sxs-lookup"><span data-stu-id="b8a00-264">The **Status** column shows whether the action was successfully run.</span></span>
- <span data-ttu-id="b8a00-265">**Műveletfájlok** – Ez a gyorslap a műveletek végrehajtása során létrehozott közbenső fájlokat jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="b8a00-265">**Action files** – This FastTab shows the intermediate files that were generated during execution of the actions.</span></span> <span data-ttu-id="b8a00-266">A fájl letöltéséhez és megtekintéséhez válassza a **Megtekintés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8a00-266">You can select **View** to download and view the file.</span></span>
- <span data-ttu-id="b8a00-267">**Műveletnapló feldolgozása** – Ez a gyorslap az Elektronikus számlázásbővítmény és a cél webszolgáltatás közötti kommunikáció eredményeit jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="b8a00-267">**Processing action log** – This FastTab shows the results of the communication between the Electronic invoicing add-on and the target web service.</span></span> <span data-ttu-id="b8a00-268">Azt is bemutatja, hogy mit küldött vissza a webszolgáltatásból a feldolgozás.</span><span class="sxs-lookup"><span data-stu-id="b8a00-268">It also shows what was returned by the processing from the web service.</span></span> <span data-ttu-id="b8a00-269">A **Hibakód** oszlop az engedélyezés webszolgáltatása által visszaküldött visszajuttatási kódot jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="b8a00-269">The **Error code** column shows the return code that was returned by the authorization web service.</span></span>

<span data-ttu-id="b8a00-270">Amikor a beküldött CFDI-számla engedélyezve van, az állapota **Engedélyezve** értékre módosul.</span><span class="sxs-lookup"><span data-stu-id="b8a00-270">When the submitted CFDI invoice is authorized, its status is updated to **Approved**.</span></span>

#### <a name="view-submission-logs-from-cfdi-invoices"></a><span data-ttu-id="b8a00-271">Tekintse meg a CFDI-számlákból származó beküldési naplókat</span><span class="sxs-lookup"><span data-stu-id="b8a00-271">View submission logs from CFDI invoices</span></span>

<span data-ttu-id="b8a00-272">A **Konfigurálható elektronikus számlázásbővítmény integrációja** funkció bekapcsolása után megtekintheti a CFDI-számlákból származó beküldési naplókat is.</span><span class="sxs-lookup"><span data-stu-id="b8a00-272">After you turn on the **ConfigurableElectronic invoicing add-on integration** feature, you can also view the submission logs from CFDI invoices.</span></span>

1. <span data-ttu-id="b8a00-273">Menjen a **Kinnlevőségek \> Lekérdezések és jelentések \> CFDI (elektronikus számlák)** pontra.</span><span class="sxs-lookup"><span data-stu-id="b8a00-273">Go to **Accounts receivable \> Inquiries and reports \> CFDI (electronic invoices)**.</span></span>
2. <span data-ttu-id="b8a00-274">Válasszon egy olyan CFDI-számlát, amelyet a **Konfigurálható elektronikus számlázásbővítmény integrációja** funkció bekapcsolása után küldtek be.</span><span class="sxs-lookup"><span data-stu-id="b8a00-274">Select a CFDI invoice that was submitted after the **Configurable Electronic invoicing add-on integration** feature was turned on.</span></span>
3. <span data-ttu-id="b8a00-275">A Művelet panel **Előzmények** lapján válassza az **Elektronikus dokumentumnapló** menüpontot.</span><span class="sxs-lookup"><span data-stu-id="b8a00-275">On the Action Pane, on the **History** tab, select **Electronic document log**.</span></span>

![CFDI-számlákból származó beküldési naplók megtekintése](media/e-Invoicing-services-get-started-MEX-View-submission-log-from-CFDI-invoice.png)

> [!NOTE]
> <span data-ttu-id="b8a00-277">Azon CFDI-számláknál, amelyeket a **Konfigurálható elektronikus számlázásbővítmény integrációja** funkció bekapcsolása előtt küldtek be, elérhető az **Előzmények** gomb.</span><span class="sxs-lookup"><span data-stu-id="b8a00-277">For CFDI invoices that were submitted before the **Configurable Electronic invoicing add-on integration** feature was turned on, the **History** button is available.</span></span> <span data-ttu-id="b8a00-278">Azon CFDI-számláknál, amelyeket a **Konfigurálható elektronikus számlázásbővítmény integrációja** funkció bekapcsolása után küldtek be, nem elérhető az **Előzmények** gomb.</span><span class="sxs-lookup"><span data-stu-id="b8a00-278">The **History** button isn't available for CFDI invoices that were submitted after the **Configurable Electronic invoicing add-on integration** feature was turned on.</span></span>

### <a name="submit-cancellation-of-cfdi-invoices"></a><span data-ttu-id="b8a00-279">CFDI-számlák érvénytelenítésének beküldése</span><span class="sxs-lookup"><span data-stu-id="b8a00-279">Submit cancellation of CFDI invoices</span></span>

<span data-ttu-id="b8a00-280">A **Konfigurálható elektronikus számlázásbővítmény integrációja** funkció bekapcsolása után már nem használható a régi folyamat a CFDI-számlák érvénytelenítésére.</span><span class="sxs-lookup"><span data-stu-id="b8a00-280">After you turn on the **Configurable Electronic invoicing add-on integration** feature, the old process for canceling CFDI invoices can no longer be used.</span></span> <span data-ttu-id="b8a00-281">Egy új érvénytelenítési folyamat váltja fel, amely az **Elektronikus dokumentum beküldési naplója** lapon lesz beágyazva.</span><span class="sxs-lookup"><span data-stu-id="b8a00-281">It's replaced by a new cancellation process that is embedded on the **Electronic document submission log** page.</span></span>

1. <span data-ttu-id="b8a00-282">Menjen a **Kinnlevőségek \> Lekérdezések és jelentések \> CFDI (elektronikus számlák)** pontra.</span><span class="sxs-lookup"><span data-stu-id="b8a00-282">Go to **Accounts receivable \> Inquiries and reports \> CFDI (electronic invoices)**.</span></span>
2. <span data-ttu-id="b8a00-283">Ha a CFDI-számla **Jóváhagyva** állapotú, akkor válassza a **Funkciók \> CFDI érvénytelenítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8a00-283">If the CFDI invoice has a status of **Approved**, select **Functions \> Cancel CFDI**.</span></span>
3. <span data-ttu-id="b8a00-284">Menjen a **Szervezeti adminisztráció \> Időszakos \> Elektronikus dokumentumok \> Elektronikus dokumentumbeküldési napló** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b8a00-284">Go to **Organization administration \> Periodic \> Electronic documents \> Electronic document submission log**.</span></span>
4. <span data-ttu-id="b8a00-285">Válassza ki a CFDI-számla, majd a **Funkciók \> Kapcsolódó beküldés küldése** funkciót.</span><span class="sxs-lookup"><span data-stu-id="b8a00-285">Select the CFDI invoice, and then select **Functions \> Send related submissions**.</span></span>
5. <span data-ttu-id="b8a00-286">Adja meg a kapcsolódó beküldés leírását, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="b8a00-286">Enter a description for the related submission, and then select **OK**.</span></span>

#### <a name="view-cancellation-submission-logs"></a><span data-ttu-id="b8a00-287">Tekintse meg az érvénytelenítési beküldési naplókat</span><span class="sxs-lookup"><span data-stu-id="b8a00-287">View cancellation submission logs</span></span>

1. <span data-ttu-id="b8a00-288">Menjen a **Szervezeti adminisztráció \> Időszakos \> Elektronikus dokumentumok \> Elektronikus dokumentumbeküldési napló** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b8a00-288">Go to **Organization administration \> Periodic \> Electronic documents \> Electronic document submission log**.</span></span>
2. <span data-ttu-id="b8a00-289">A **Dokumentumtípus** mezőben válassza ki a **Vevői számlanapló** lehetőséget kizárólag a vevői számla naplózási dokumentumainak szűréséhez.</span><span class="sxs-lookup"><span data-stu-id="b8a00-289">In the **Document type** field, select **Customer invoice journal** to filter for customer invoice journal documents only.</span></span>
3. <span data-ttu-id="b8a00-290">Válassza ki a CFDI-számlát, majd a Műveleti ablaktáblán válassza ki a **Lekérdezések \> Kapcsolódó beküldés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8a00-290">Select the CFDI invoice, and then, on the Action Pane, select **Inquiries \> Related submission**.</span></span>

    <span data-ttu-id="b8a00-291">A **Kapcsolódó beküldések** oldal egy adott CFDI-számla összes kapcsolódó beküldésér és beküldési állapotát megjeleníti.</span><span class="sxs-lookup"><span data-stu-id="b8a00-291">The **Related submissions** page shows all related submissions, and their submission status, for a given CFDI invoice.</span></span> <span data-ttu-id="b8a00-292">A következő ábrán az első sor azt a beküldést jelöli, amely a CFDI-számla jóváhagyását kérte.</span><span class="sxs-lookup"><span data-stu-id="b8a00-292">In the following illustration, the first line represents the submission that requested approval of the CFDI invoice.</span></span> <span data-ttu-id="b8a00-293">A második sor azt a beküldést jelöli, amely érvénytelenítette az adott CFDI-számlát.</span><span class="sxs-lookup"><span data-stu-id="b8a00-293">The second line represents the submission that canceled that CFDI invoice.</span></span>

    ![Az érvénytelenítési beküldési naplók megtekintése](media/e-Invoicing-services-get-started-MEX-View-cancellation-submission-log.png)

4. <span data-ttu-id="b8a00-295">A Művelet ablaktáblán válassza ki a **Lekérdezések \> Beküldések részletei** lehetőséget a beküldési végrehajtási naplók részleteinek megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="b8a00-295">On the Action Pane, select **Inquiries \> Submission details** to view the details of the submission execution logs.</span></span>

    ![Az érvénytelenítési beküldési napló részleteinek megtekintése](media/e-Invoicing-services-get-started-MEX-View-cancellation-submission-log-details.png)

## <a name="privacy-notice"></a><span data-ttu-id="b8a00-297">Adatvédelmi nyilatkozat</span><span class="sxs-lookup"><span data-stu-id="b8a00-297">Privacy notice</span></span>
<span data-ttu-id="b8a00-298">Az MX-00010 és az MX-00016 (CFDI-számla és CFDI-érvénytelenítés) funkciók engedélyezése korlátozott adatok küldését igényelheti, ideértve a szervezet adóregisztrációs azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="b8a00-298">Enabling the MX-00010 and MX-00016 (CFDI Invoice and CFDI Cancellation) features may require sending limited data, which includes the organization tax registration ID.</span></span> <span data-ttu-id="b8a00-299">Ezek továbbítva lesznek az adóhatóság által kinevezett harmadik fél ügynökségekhez, az elektronikus számlák – kormányzati szervek webszolgáltatással való integrációhoz szükséges, előre meghatározott formátumban való – adott adóhatósághoz történő elküldése céljából.</span><span class="sxs-lookup"><span data-stu-id="b8a00-299">This will be transmitted to third-party agencies authorized by the tax authority for purposes of sending electronic invoices to this tax authority in the predefined format required for integration with the government’s web service.</span></span> <span data-ttu-id="b8a00-300">A rendszergazda engedélyezheti és letilthatja az MX-00010 és az MX-00016 (CFDI-számla és CFDI-érvénytelenítés) funkciókat a **Szervezeti adminisztráció \> Beállítások \> Elektronikus dokumentumparaméterek** lehetőségre való navigálással.</span><span class="sxs-lookup"><span data-stu-id="b8a00-300">An administrator can enable and disable the MX-00010 and MX-00016 (CFDI Invoice and CFDI Cancellation) features by navigating to **Organization administration \> Setup \> Electronic document parameters**.</span></span> <span data-ttu-id="b8a00-301">Válassza ki a **Funkciók** lapot, majd az MX-00010 és az MX-00016 funkciókat tartalmazó sorokat, és végezze el a megfelelő kijelölést.</span><span class="sxs-lookup"><span data-stu-id="b8a00-301">Select the **Features** tab, select the rows containing the MX-00010 and MX-00016 features, and then make the appropriate selection.</span></span> <span data-ttu-id="b8a00-302">A külső rendszerekből ebbe a Dynamics 365 online szolgáltatásba importált adatok az [Adatvédelmi nyilatkozatunk](https://go.microsoft.com/fwlink/?LinkId=512132) hatálya alá tartoznak.</span><span class="sxs-lookup"><span data-stu-id="b8a00-302">Data imported from these external systems into this Dynamics 365 online service are subject to our [privacy statement](https://go.microsoft.com/fwlink/?LinkId=512132).</span></span> <span data-ttu-id="b8a00-303">További tájékoztatásért olvassa el az országspecifikus funkciók dokumentációja szakaszokban található Adatvédelmi nyilatkozatot.</span><span class="sxs-lookup"><span data-stu-id="b8a00-303">Consult the Privacy notice sections in country-specific feature documentation for more information.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b8a00-304">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="b8a00-304">Additional resources</span></span>

- [<span data-ttu-id="b8a00-305">Elektronikus számlázásbővítmény – áttekintés</span><span class="sxs-lookup"><span data-stu-id="b8a00-305">Electronic invoicing add-on overview</span></span>](e-invoicing-service-overview.md)
- [<span data-ttu-id="b8a00-306">Első lépések az Elektronikus számlázásbővítménnyel</span><span class="sxs-lookup"><span data-stu-id="b8a00-306">Get started with the Electronic invoicing add-on</span></span>](e-invoicing-get-started.md)
- [<span data-ttu-id="b8a00-307">Az Elektronikus számlázásbővítmény beállítása</span><span class="sxs-lookup"><span data-stu-id="b8a00-307">Set up the Electronic invoicing add-on</span></span>](e-invoicing-setup.md)
