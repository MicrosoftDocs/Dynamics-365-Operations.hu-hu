---
title: Első lépések az olasz elektronikus számlázásbővítménnyel
description: Ez a témakör olyan információkat tartalmaz, amelyek bemutatják az Első lépéseket az olasz elektronikus számlázásbővítmény Microsoft Dynamics 365 Finance és Dynamics 365 Supply Chain Management szolgáltatásban való használatát.
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
ms.openlocfilehash: c513141f820c95fe3842478361693701f1e3641b
ms.sourcegitcommit: f860ac2b18f6bbbfc4a46b497baec2477105b116
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/19/2020
ms.locfileid: "4444156"
---
# <a name="get-started-with-the-electronic-invoicing-add-on-for-italy"></a><span data-ttu-id="39f46-103">Első lépések az olasz elektronikus számlázásbővítménnyel</span><span class="sxs-lookup"><span data-stu-id="39f46-103">Get started with the Electronic invoicing add-on for Italy</span></span>

[!include [banner](../includes/banner.md)]


> [!IMPORTANT]
> <span data-ttu-id="39f46-104">Előfordulhat, hogy az Olasz elektronikus számlázásbővítmény jelenleg nem támogatja az elektronikus számlákhoz rendelkezésre álló összes funkciót a Microsoft Dynamics 365 Finance és Dynamics 365 Supply Chain Management számára.</span><span class="sxs-lookup"><span data-stu-id="39f46-104">The Electronic invoicing add-on for Italy might not currently support all the functions that are available for electronic invoices in Microsoft Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> 

<span data-ttu-id="39f46-105">Ez a témakör olyan információkat tartalmaz, amelyek bemutatják az olasz elektronikus számlázásbővítménnyel kapcsolatos első lépéseket.</span><span class="sxs-lookup"><span data-stu-id="39f46-105">This topic provides information that will help you get started with the Electronic invoicing add-on for Italy.</span></span> <span data-ttu-id="39f46-106">Végigvezeti a Regulatory Configuration Services (RCS) és a Finance szolgáltatásban található ország-függő konfigurációs lépéseken.</span><span class="sxs-lookup"><span data-stu-id="39f46-106">It guides you through the configuration steps that are country-dependent in Regulatory Configuration Services (RCS) and Finance.</span></span> <span data-ttu-id="39f46-107">Továbbá a szolgáltatáson keresztül végigvezeti az Olaszország-specifikus **FatturaPA**-formátumban létrejövő elektronikus számlák küldésének folyamatán, és elmagyarázza, hogyan kell áttekinteni a feldolgozás eredményeit.</span><span class="sxs-lookup"><span data-stu-id="39f46-107">It also guides you through the process for submitting electronic invoices that are generated in the Italy-specific **FatturaPA** format through the service, and it explains how to review the results of processing.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="39f46-108">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="39f46-108">Prerequisites</span></span>

<span data-ttu-id="39f46-109">A témakör lépéseinek végrehajtása előtt végre kell hajtania az [Első lépések az Elektronikus számlázásbővítménnyel](e-invoicing-get-started.md) részben található lépéseket.</span><span class="sxs-lookup"><span data-stu-id="39f46-109">Before you complete the steps in this topic, you must complete the steps in [Get started with the Electronic invoicing add-on](e-invoicing-get-started.md).</span></span>

## <a name="rcs-setup"></a><span data-ttu-id="39f46-110">RCS beállítása</span><span class="sxs-lookup"><span data-stu-id="39f46-110">RCS setup</span></span>

<span data-ttu-id="39f46-111">Az RCS beállítása során a következő feladatokat kell elvégeznie:</span><span class="sxs-lookup"><span data-stu-id="39f46-111">During the RCS setup, you will complete these tasks:</span></span>

1. <span data-ttu-id="39f46-112">A vevő elektronikus számlák exportálásához használt e-számlázási funkció importálása **FatturaPA**-formátumba.</span><span class="sxs-lookup"><span data-stu-id="39f46-112">Import the e-Invoicing feature for the export of customer electronic invoices in the **FatturaPA** format.</span></span>
2. <span data-ttu-id="39f46-113">Az elektronikus számlákkal kapcsolatos válaszok létrehozásához, küldéséhez és fogadásához szükséges fájlformátum-konfigurációk áttekintése.</span><span class="sxs-lookup"><span data-stu-id="39f46-113">Review the format configurations that are required to generate, submit, and receive responses about electronic invoices.</span></span>
3. <span data-ttu-id="39f46-114">Az elektronikus számlabeküldési forgatókönyveket támogató események konfigurálása.</span><span class="sxs-lookup"><span data-stu-id="39f46-114">Configure the events that support the electronic invoice submission scenarios.</span></span>
4. <span data-ttu-id="39f46-115">Tegye közzé az e-számlázási funkciót.</span><span class="sxs-lookup"><span data-stu-id="39f46-115">Publish the e-Invoicing feature.</span></span>

> [!NOTE]
> <span data-ttu-id="39f46-116">„Az e-számlázás funkció” annak az erőforrásnak az általános neve, amely az Elektronikus számlázási bővítmény kiszolgáló felhasználásához van konfigurálva és közzétéve.</span><span class="sxs-lookup"><span data-stu-id="39f46-116">"The e-Invoicing feature" is the generic name for the resource that is configured and published to consume the Electronic invoicing add-on server.</span></span> <span data-ttu-id="39f46-117">Ebben az esetben a vevő elektronikus számlák exportálásához használt e-számlázási funkciót fogja beállítani.</span><span class="sxs-lookup"><span data-stu-id="39f46-117">In this case, the export of customer electronic invoices is the e-Invoicing feature that you will set up.</span></span>

## <a name="import-the-e-invoicing-feature"></a><span data-ttu-id="39f46-118">Az e-számlázási funkció importálása</span><span class="sxs-lookup"><span data-stu-id="39f46-118">Import the e-Invoicing feature</span></span>

1. <span data-ttu-id="39f46-119">Jelentkezzen be a RCS-fiókba.</span><span class="sxs-lookup"><span data-stu-id="39f46-119">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="39f46-120">Nyissa meg a **Globalizációs funkciók** munkaterületet, a **Funkciók** szakaszban válassza az **e-számlázás** csempét.</span><span class="sxs-lookup"><span data-stu-id="39f46-120">In the **Globalization features** workspace, in the **Features** section, select the **e-Invoicing** tile.</span></span>
3. <span data-ttu-id="39f46-121">Az **e-számlázási funkciók** oldalon jelölje be az **Importálás** lehetőséget a e-számlák funkció Globális adattárból történő importálásához.</span><span class="sxs-lookup"><span data-stu-id="39f46-121">On the **e-Invoicing Features** page, select **Import** to import the e-Invoicing feature from the Global repository.</span></span>

    > [!NOTE]
    > <span data-ttu-id="39f46-122">Ha nem látja az elérhető szolgáltatások listáját, akkor válassza a **Szinkronizálás** elemet.</span><span class="sxs-lookup"><span data-stu-id="39f46-122">If you don't see the list of available features, select **Synchronize**.</span></span> 

4. <span data-ttu-id="39f46-123">Válassza ki az **e-számlák exportálása (IT)** funkciót, majd válassza az **Importálás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="39f46-123">Select the **e-Invoices Export (IT)** feature, and then select **Import**.</span></span>

![Az e-számlák exportálása (IT) funkció importálása](media/e-Invoicing-services-get-started-ITA-Select-Import-e-Invoicing-feature.png)

<span data-ttu-id="39f46-125">Amikor az **e-számlák exportálása (IT)** funkciót a globális adattárból importálja, akkor azzal a következő szakaszokban ismertetett összes beállítást is importálja.</span><span class="sxs-lookup"><span data-stu-id="39f46-125">When you import the **e-Invoices Export (IT)** feature from the Global repository, all the settings that are described in the next sections are also imported.</span></span>

## <a name="create-a-new-version-of-the-e-invoices-export-it-feature"></a><span data-ttu-id="39f46-126">Az e-számlák exportálása (IT) funkció új verziójának létrehozása</span><span class="sxs-lookup"><span data-stu-id="39f46-126">Create a new version of the e-Invoices Export (IT) feature</span></span>

1. <span data-ttu-id="39f46-127">Az **e-számlázási funkciók** oldal **Verziók** lapján válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="39f46-127">On the **e-Invoicing Features** page, on the **Versions** tab, select **New**.</span></span> 

    ![Új e-számlázási funkcióverzió hozzáadása](media/e-Invoicing-services-get-started-ITA-Select-New-e-Invoicing-feature-version.png)

    <span data-ttu-id="39f46-129">Ezután konfigurálhatja az e-számlázási funkcióhoz társított Elektronikus jelentéskészítési (ER) formátumokat.</span><span class="sxs-lookup"><span data-stu-id="39f46-129">Next, you will configure the Electronic reporting (ER) formats that are associated with the e-Invoicing feature.</span></span>

2. <span data-ttu-id="39f46-130">A **Konfigurációk** lapon válassza a **Hozzáadás** lehetőséget a konfigurációs verziók kezeléséhez.</span><span class="sxs-lookup"><span data-stu-id="39f46-130">On the **Configurations** tab, select **Add** to manage the configuration versions.</span></span>

    ![E-számlázás funkció-konfigurációverziók kezelése](media/e-Invoicing-services-get-started-ITA-Manage-e-Invoicing-feature-configurations.png)

    <span data-ttu-id="39f46-132">Ebben a lépésben hozzáadja és konfigurálja az olasz e-számlák exportálásához használt különböző fájlok ER-formátumát.</span><span class="sxs-lookup"><span data-stu-id="39f46-132">In this step, you're adding and configuring the ER formats of different files that are used to export Italian e-invoices.</span></span> <span data-ttu-id="39f46-133">Az olasz FatturaPA e-számlák esetében a következő szokásos konfigurációkat, illetve az e-számlázáshoz használt tényleges egyéni konfigurációkat kell használni:</span><span class="sxs-lookup"><span data-stu-id="39f46-133">For Italian FatturaPA e-invoices, use either the following standard configurations or the actual customized configurations that you use for e-invoicing:</span></span>

    - <span data-ttu-id="39f46-134">Értékesítési számla (IT)</span><span class="sxs-lookup"><span data-stu-id="39f46-134">Sales invoice (IT)</span></span>
    - <span data-ttu-id="39f46-135">Projektszámla (IT)</span><span class="sxs-lookup"><span data-stu-id="39f46-135">Project invoice (IT)</span></span>

    <span data-ttu-id="39f46-136">Amikor egy másik e-számlázási funkcióból származtatott e-számlázási funkciót hoz létre, a program az eredeti funkcióból örökli az összes ER-formátumot.</span><span class="sxs-lookup"><span data-stu-id="39f46-136">When you create an e-Invoicing feature that is derived from another e-Invoicing feature, all ER formats are inherited from the original feature.</span></span>

3. <span data-ttu-id="39f46-137">A specifikus ER-formátum fájlkonfigurációjának kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="39f46-137">Select a specific ER format file configuration.</span></span>
4. <span data-ttu-id="39f46-138">Válassza a **Szerkesztés** vagy **Megtekintés** lehetőséget a **Formátumtervező** lap megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="39f46-138">Select **Edit** or **View** to open the **Format designer** page.</span></span>

    ![A Formátumtervező lap megnyitása](media/e-Invoicing-services-get-started-ITA-Configuration-ER-format-designer.png)

5. <span data-ttu-id="39f46-140">Az ER-formátum fájlkonfiguráció szerkesztéséhez és megtekintéséhez használja a **Formátumtervező** lapot.</span><span class="sxs-lookup"><span data-stu-id="39f46-140">Use the **Format designer** page to edit and view the ER format file configurations.</span></span>

    ![Formátumtervező oldal](media/e-Invoicing-services-get-started-ITA-ER-format-designer.png)

## <a name="manage-the-e-invoicing-feature-setups"></a><span data-ttu-id="39f46-142">Kezelje az e-számlázás funkció beállításait</span><span class="sxs-lookup"><span data-stu-id="39f46-142">Manage the e-Invoicing feature setups</span></span>

- <span data-ttu-id="39f46-143">Az **e-számlázási funkciók** oldal **Beállítások** lapján válassza a **Hozzáadás**, **Törlés** vagy **Szerkesztés** parancsot az e-számlázási funkciók beállításainak kezeléséhez.</span><span class="sxs-lookup"><span data-stu-id="39f46-143">On the **e-Invoicing Features** page, on the **Setups** tab, select **Add**, **Delete**, or **Edit** to manage the e-Invoicing feature setups.</span></span>

![Az e-számlázás funkció beállításainak kezelése](media/e-Invoicing-services-get-started-ITA-Manage-e-Invoicing-feature-setup.png)

<span data-ttu-id="39f46-145">Ebben a lépésben konfigurálhatja az elektronikus számlákra vonatkozó eseményeket, többek között az XML kimeneti fájlok **FatturaPA**-formátumban történő létrehozását, valamint a digitális aláírást (ha szükséges).</span><span class="sxs-lookup"><span data-stu-id="39f46-145">In this step, you configure the events that are applicable to electronic invoices, including generation of the XML output files in **FatturaPA** format and digital signing (if required).</span></span>

### <a name="configure-the-sales-invoice-feature-setup"></a><span data-ttu-id="39f46-146">Az Értékesítési számla funkció beállításainak konfigurálása</span><span class="sxs-lookup"><span data-stu-id="39f46-146">Configure the Sales invoice feature setup</span></span>

1. <span data-ttu-id="39f46-147">Az **e-számlázási funkciók** oldal **Beállítások** lapjának **Funkcióbeállítás** oszlopában válassza ki az **Értékesítési számla** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="39f46-147">On the **e-Invoicing Features** page, on the **Setups** tab, in the **Feature setup** column, select **Sales invoice**.</span></span>
2. <span data-ttu-id="39f46-148">Válassza ki a **Szerkesztés** opciót.</span><span class="sxs-lookup"><span data-stu-id="39f46-148">Select **Edit**.</span></span>
3. <span data-ttu-id="39f46-149">A **Funkcióverzió beállítása** oldalon válassza ki a **Műveletek** lapot a műveletek listájának kezeléséhez.</span><span class="sxs-lookup"><span data-stu-id="39f46-149">On the **Feature version setup** page, select the **Actions** tab to manage the list of actions.</span></span> <span data-ttu-id="39f46-150">A műveletek határozzák meg azokat a műveleteket, amelyeket az esemény teljes végrehajtásához sorrendben kell végrehajtani.</span><span class="sxs-lookup"><span data-stu-id="39f46-150">Actions define a list of operations that must be run in sequential order to accomplish full execution of the event.</span></span>

    ![Műveletek lap](media/e-Invoicing-services-get-started-ITA-Select-Actions.png)

    | <span data-ttu-id="39f46-152">Műveletazonosító</span><span class="sxs-lookup"><span data-stu-id="39f46-152">Action ID</span></span> | <span data-ttu-id="39f46-153">Művelet neve</span><span class="sxs-lookup"><span data-stu-id="39f46-153">Action name</span></span>        | <span data-ttu-id="39f46-154">Művelet leírása</span><span class="sxs-lookup"><span data-stu-id="39f46-154">Action description</span></span>                                     |
    |-----------|--------------------|--------------------------------------------------------|
    | <span data-ttu-id="39f46-155">1</span><span class="sxs-lookup"><span data-stu-id="39f46-155">1</span></span>         | <span data-ttu-id="39f46-156">Dokumentum átalakítása</span><span class="sxs-lookup"><span data-stu-id="39f46-156">Transform document</span></span> | <span data-ttu-id="39f46-157">Az e-számla XML-fájljának létrehozása **FatturaPA**-formátumban.</span><span class="sxs-lookup"><span data-stu-id="39f46-157">Create the e-invoice XML file in **FatturaPA** format.</span></span> |
    | <span data-ttu-id="39f46-158">2</span><span class="sxs-lookup"><span data-stu-id="39f46-158">2</span></span>         | <span data-ttu-id="39f46-159">Dokumentum aláírása</span><span class="sxs-lookup"><span data-stu-id="39f46-159">Sign document</span></span>      | <span data-ttu-id="39f46-160">Digitális aláírás alkalmazása az XML-fájlon.</span><span class="sxs-lookup"><span data-stu-id="39f46-160">Apply a digital signature to the XML file.</span></span>             |

4. <span data-ttu-id="39f46-161">Válassza az **Alkalmazhatósági szabályok** lapot az alkalmazhatósági szabályok megtekintéséhez és kezeléséhez.</span><span class="sxs-lookup"><span data-stu-id="39f46-161">Select the **Applicability rules** tab to view and maintain the applicability rules.</span></span> <span data-ttu-id="39f46-162">Az alkalmazhatósági szabályok határozzák meg, hogy melyik környezetben fusson a művelet.</span><span class="sxs-lookup"><span data-stu-id="39f46-162">Applicability rules define the context where the action will be run.</span></span>

    ![Alkalmazhatósági szabályok lap](media/e-Invoicing-services-get-started-ITA-Select-Applicability-rules.png)

5. <span data-ttu-id="39f46-164">A **Változók** lapon megtekintheti és karbantarthatja a változókat.</span><span class="sxs-lookup"><span data-stu-id="39f46-164">Select the **Variables** tab to view and maintain the variables.</span></span>

    ![Változók lap](media/e-Invoicing-services-get-started-ITA-Select-Variables.png)

6. <span data-ttu-id="39f46-166">A műveletek futtatásához szükséges nyilvános változók meghatározása.</span><span class="sxs-lookup"><span data-stu-id="39f46-166">Define the public variables that are required to run the actions.</span></span>

### <a name="configure-the-project-invoice-feature-setup"></a><span data-ttu-id="39f46-167">A Projektszámla funkció beállításainak konfigurálása</span><span class="sxs-lookup"><span data-stu-id="39f46-167">Configure the Project invoice feature setup</span></span> 

<span data-ttu-id="39f46-168">A **Projektszámla** funkció konfigurálásához szükséges lépések és beállítások nagyon hasonlóak az **Értékesítési számla** funkcióbeállítás lépéseihez és beállításaihoz.</span><span class="sxs-lookup"><span data-stu-id="39f46-168">The steps and settings that are required to configure the **Project invoice** feature setup are very similar to the steps and settings for the **Sales invoice** feature setup.</span></span> <span data-ttu-id="39f46-169">A projektszámlákkal való munkák során lásd az értékesítési számlák eljárásait.</span><span class="sxs-lookup"><span data-stu-id="39f46-169">When you work with project invoices, see the procedures for sales invoices.</span></span>

## <a name="assign-the-e-invoicing-feature-to-the-environment"></a><span data-ttu-id="39f46-170">Az e-számlázási funkció társítása a környezethez</span><span class="sxs-lookup"><span data-stu-id="39f46-170">Assign the e-Invoicing feature to the environment</span></span>

1. <span data-ttu-id="39f46-171">Az **e-számlázási funkciók** oldal **Környezetek** lapján válassza az **Engedélyezés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="39f46-171">On the **e-Invoicing Features** page, on the **Environments** tab, select **Enable**.</span></span>
2. <span data-ttu-id="39f46-172">A **Környezet** mezőben válassza ki a környezetet.</span><span class="sxs-lookup"><span data-stu-id="39f46-172">In the **Environment** field, select the environment.</span></span>
3. <span data-ttu-id="39f46-173">A **Hatálybalépés dátuma** mezőben válassza ki azt a dátumot, amikortól a környezetnek hatályossá kell válnia.</span><span class="sxs-lookup"><span data-stu-id="39f46-173">In the **Effective from** field, select the date when the environment should become effective.</span></span>
4. <span data-ttu-id="39f46-174">Válassza az **Engedélyezés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="39f46-174">Select **Enable**.</span></span> 

![Az e-számlázási környezet engedélyezése](media/e-Invoicing-services-get-started-ITA-Enable-e-Invoicing-environment.png)

## <a name="publish-the-e-invoicing-feature"></a><span data-ttu-id="39f46-176">Tegye közzé az e-számlázási funkciót</span><span class="sxs-lookup"><span data-stu-id="39f46-176">Publish the e-invoicing feature</span></span>

<span data-ttu-id="39f46-177">Az e-számlázási funkció közzétehető a verzió állapotának **Befejezett** vagy **Közzétett** értékre módosításával.</span><span class="sxs-lookup"><span data-stu-id="39f46-177">You can publish the e-Invoicing feature by changing the version status to **Completed** or **Published**.</span></span>

### <a name="change-the-version-status-to-completed"></a><span data-ttu-id="39f46-178">A verzió állapotának módosítása Befejezett értékre</span><span class="sxs-lookup"><span data-stu-id="39f46-178">Change the version status to Completed</span></span>

1. <span data-ttu-id="39f46-179">Az **e-számlázási funkciók** oldal **Verziók** lapján válassza ki a **Piszkozat** állapotú e-számlázási funkció verzióját.</span><span class="sxs-lookup"><span data-stu-id="39f46-179">On the **e-Invoicing Features** page, on the **Versions** tab, select the version of the e-Invoicing feature that has a status of **Draft**.</span></span>
2. <span data-ttu-id="39f46-180">Válassza az **Állapot módosítása \>Teljes** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="39f46-180">Select **Change status \> Complete**.</span></span> 

### <a name="change-the-version-status-to-published"></a><span data-ttu-id="39f46-181">A verzió állapotának módosítása Közzétett értékre</span><span class="sxs-lookup"><span data-stu-id="39f46-181">Change the version status to Published</span></span> 

1. <span data-ttu-id="39f46-182">Az **e-számlázási funkciók** oldal **Verziók** lapján válassza ki a **Befejezett** állapotú e-számlázási funkció verzióját.</span><span class="sxs-lookup"><span data-stu-id="39f46-182">On the **e-Invoicing Features** page, on the **Versions** tab, select the version of the e-Invoicing feature that has a status of **Completed**.</span></span>
2. <span data-ttu-id="39f46-183">Válassza az **Állapot módosítása \> Közzétett** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="39f46-183">Select **Change status \> Publish**.</span></span>

![Az e-számlázási funkció állapotának módosítása](media/e-Invoicing-services-get-started-ITA-Change-status-of-e-Invoicing-feature.png)

## <a name="set-up-the-electronic-invoicing-add-on-integration-in-finance"></a><span data-ttu-id="39f46-185">Az Elektronikus számlázásbővítmény integrációjának beállítása a Finance szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="39f46-185">Set up the Electronic invoicing add-on integration in Finance</span></span>

<span data-ttu-id="39f46-186">A Finance szolgáltatás beállítása során a következő feladatokat kell elvégeznie:</span><span class="sxs-lookup"><span data-stu-id="39f46-186">During the setup of Finance, you will complete these tasks:</span></span>

1. <span data-ttu-id="39f46-187">Importálja az ER-adatmodellt, az ER-adatmodell-leképezést, valamint a kontextus-konfigurációkat a FatturaPA-számlákhoz.</span><span class="sxs-lookup"><span data-stu-id="39f46-187">Import the ER data model, the ER data model mapping, and the context configurations for FatturaPA e-invoices.</span></span>
2. <span data-ttu-id="39f46-188">Az olasz e-számlák digitális aláírásához szükséges tanúsítvány konfigurálása.</span><span class="sxs-lookup"><span data-stu-id="39f46-188">Configure the certificate that is required to digitally sign Italian e-invoices.</span></span>

### <a name="import-the-er-data-model-data-model-mapping-and-formats"></a><span data-ttu-id="39f46-189">Az ER-adatmodell, az adatmodell-leképezése és a formátumok importálása</span><span class="sxs-lookup"><span data-stu-id="39f46-189">Import the ER data model, data model mapping, and formats</span></span>

1. <span data-ttu-id="39f46-190">Az **Elektronikus jelentéskészítés** munkaterületen ellenőrizze, hogy az **Üzleti dokumentum szolgáltatás** konfigurációszolgáltatója **Aktív** értékre van állítva.</span><span class="sxs-lookup"><span data-stu-id="39f46-190">In the **Electronic reporting** workspace, verify that the **Business Document Service** configuration provider is set to **Active**.</span></span>
2. <span data-ttu-id="39f46-191">Válassza ki a **Tárházak** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="39f46-191">Select **Repositories**.</span></span>
3. <span data-ttu-id="39f46-192">Válassza ki a **Globális erőforrás \> Megnyitás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="39f46-192">Select **Global resource \> Open**.</span></span>
4. <span data-ttu-id="39f46-193">A **Számlamodell**, a **Számlamodell-leképezése** és a **Vevői számla kontextusmodell** importálása.</span><span class="sxs-lookup"><span data-stu-id="39f46-193">Import **Invoice model**, **Invoice model mapping**, and **Customer invoice context model**.</span></span>

#### <a name="turn-on-the-feature-for-exporting-customer-electronic-invoices-for-italy"></a><span data-ttu-id="39f46-194">Kapcsolja be a funkciót az olasz vevői elektronikus számlák exportálásához</span><span class="sxs-lookup"><span data-stu-id="39f46-194">Turn on the feature for exporting customer electronic invoices for Italy</span></span>

1. <span data-ttu-id="39f46-195">Menjen a **Szervezeti adminisztráció \> Beállítás \> Elektronikus dokumentumparaméterek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="39f46-195">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="39f46-196">A **Funkciók** lapon válassza ki az **Engedélyezett** jelölőnégyzetet az **IT00036** funkcióhivatkozás sorában.</span><span class="sxs-lookup"><span data-stu-id="39f46-196">On the **Features** tab, select the **Enabled** check box in the row for feature reference **IT00036**.</span></span>

![A FatturaPA funkció bekapcsolása](media/e-Invoicing-services-get-started-ITA-Enable-FatturaPA-feature.png)

#### <a name="configure-electronic-documents"></a><span data-ttu-id="39f46-198">Elektronikus dokumentum konfigurálása</span><span class="sxs-lookup"><span data-stu-id="39f46-198">Configure electronic documents</span></span>

1. <span data-ttu-id="39f46-199">Menjen a **Szervezeti adminisztráció \> Beállítás \> Elektronikus dokumentumparaméterek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="39f46-199">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="39f46-200">Az **Elektronikus dokumentum** lapon válassza a **Hozzáadás** elemet, majd adja meg az olasz e-számlák létrehozásához szükséges táblákat:</span><span class="sxs-lookup"><span data-stu-id="39f46-200">On the **Electronic document** tab, select **Add**, and enter the tables that are required to generate Italian e-invoices:</span></span>

    - <span data-ttu-id="39f46-201">**Tábla neve:** Vevői számla naplója</span><span class="sxs-lookup"><span data-stu-id="39f46-201">**Table name:** Customer invoice journal</span></span>
    - <span data-ttu-id="39f46-202">**Tábla neve:** Projektszámla</span><span class="sxs-lookup"><span data-stu-id="39f46-202">**Table name:** Project invoice</span></span>

3. <span data-ttu-id="39f46-203">Minden táblához határozzon meg egy kapcsolódó dokumentumkontextust:</span><span class="sxs-lookup"><span data-stu-id="39f46-203">For each table, define a related document context:</span></span>

    - <span data-ttu-id="39f46-204">Az **Ügyfélszámla napló** lehetőségben válassza a **Vevői számla kontextusát**.</span><span class="sxs-lookup"><span data-stu-id="39f46-204">For **Customer invoice journal**, select **Customer invoice context**.</span></span>
    - <span data-ttu-id="39f46-205">A **Projektszámla** lehetőségnél válassza ki a **Projektszámla kontextusa** elemet.</span><span class="sxs-lookup"><span data-stu-id="39f46-205">For **Project invoice**, select **Project invoice context**.</span></span>

![Választípusok beállítása](media/e-Invoicing-services-get-started-ITA-Set-up-response-types.png)

## <a name="electronic-invoice-processing"></a><span data-ttu-id="39f46-207">Elektronikus számla feldolgozása</span><span class="sxs-lookup"><span data-stu-id="39f46-207">Electronic invoice processing</span></span>

<span data-ttu-id="39f46-208">A Finance szolgáltatásban történő feldolgozás során a következő feladatokat kell elvégeznie:</span><span class="sxs-lookup"><span data-stu-id="39f46-208">During processing in Finance, you will complete these tasks:</span></span>

1. <span data-ttu-id="39f46-209">Olasz e-számlák létrehozása az Elektronikus számlázásbővítménnyel</span><span class="sxs-lookup"><span data-stu-id="39f46-209">Generate Italian e-invoices through the Electronic invoicing add-on</span></span>
2. <span data-ttu-id="39f46-210">A végrehajtási naplók megtekintése, és a feldolgozás eredményeinek áttekintése</span><span class="sxs-lookup"><span data-stu-id="39f46-210">View the execution logs and review the results of processing</span></span>

### <a name="generate-electronic-invoices"></a><span data-ttu-id="39f46-211">Elektronikus számlák létrehozása</span><span class="sxs-lookup"><span data-stu-id="39f46-211">Generate electronic invoices</span></span>

<span data-ttu-id="39f46-212">Miután bekapcsolta a **Konfigurálható elektronikus számlázásbővítmény integrációja** funkciót, és aktiválta az **IT00036** funkciót, az olasz e-számlák létrehozásához használt régi Finance-folyamatot már nem lehet használni.</span><span class="sxs-lookup"><span data-stu-id="39f46-212">After you turn on the **Configurable Electronic invoicing add-on integration** feature and activate the **IT00036** feature, the old Finance process for generating Italian e-invoices can no longer be used.</span></span> <span data-ttu-id="39f46-213">Ezt felváltotta egy új, **Elektronikus dokumentumok beküldése** nevű folyamat.</span><span class="sxs-lookup"><span data-stu-id="39f46-213">It's replaced by a new process that is named **Submit electronic documents**.</span></span>

<span data-ttu-id="39f46-214">A dokumentumokat a saját e-számla dokumentumok igényeinek megfelelően manuálisan is elküldheti.</span><span class="sxs-lookup"><span data-stu-id="39f46-214">You can submit the documents manually, based on your demand for e-invoice documents.</span></span>

> [!NOTE]
> <span data-ttu-id="39f46-215">Mielőtt folytatná, győződjön meg arról, hogy az olasz e-számlákhoz szükséges beállítások el lettek végezve.</span><span class="sxs-lookup"><span data-stu-id="39f46-215">Before you continue, verify that the setup that is required for Italian e-invoices was completed.</span></span> <span data-ttu-id="39f46-216">A további információkat lásd: [Vevői elektronikus számlák](https://docs.microsoft.com/dynamics365/finance/localizations/emea-ita-e-invoices).</span><span class="sxs-lookup"><span data-stu-id="39f46-216">For more information, see [Customer electronic invoices](https://docs.microsoft.com/dynamics365/finance/localizations/emea-ita-e-invoices).</span></span> <span data-ttu-id="39f46-217">Ne feledje, hogy a témakörben leírt néhány beállítási lépés nem érhető el az elektronikus számlázásbővítmény aktiválása miatt.</span><span class="sxs-lookup"><span data-stu-id="39f46-217">Be aware that some of the setup steps that are described in that topic might be unavailable because of Electronic invoicing add-on activation.</span></span>

1. <span data-ttu-id="39f46-218">Menjen a **Szervezeti adminisztráció \> Időszakos \> Elektronikus dokumentumok \> Elektronikus dokumentumok beküldése** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="39f46-218">Go to **Organization administration \> Periodic \> Electronic documents \> Submit electronic documents**.</span></span>
2. <span data-ttu-id="39f46-219">A dokumentumok első beküldésekor **Nem** értékre kell állítania a **Dokumentumok újraküldése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="39f46-219">For the first submission of any document, set the **Resubmit documents** option to **No**.</span></span> <span data-ttu-id="39f46-220">Ha a szolgáltatáson keresztül újra kell küldenie a dokumentumot, akkor ezt a beállítást állítsa **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="39f46-220">If you must resubmit a document through the service, set this option to **Yes**.</span></span>
3. <span data-ttu-id="39f46-221">A **Szerepeltetni kívánt rekordok** gyorslapon válassza a **Szűrő** lehetőséget a **Lekérdezés** párbeszédpanel megnyitásához, amelyen létrehozhat egy lekérdezést, hogy milyen dokumentumok legyenek kiválasztva a beküldéshez.</span><span class="sxs-lookup"><span data-stu-id="39f46-221">On the **Records to include** FastTab, select **Filter** to open the **Inquiry** dialog box, where you can build a query to select documents for submission.</span></span>

![Elektronikus dokumentumok beküldése párbeszédpanel](media/e-Invoicing-services-get-started-ITA-Submission-form.png)

#### <a name="filter-query"></a><span data-ttu-id="39f46-223">Lekérdezés szűrése</span><span class="sxs-lookup"><span data-stu-id="39f46-223">Filter query</span></span>

1. <span data-ttu-id="39f46-224">A **Lekérdezés** párbeszédpanelben konfigurálja az értékesítési- és a projektszámlák szűrési feltételeit, vagy hagyja üresen az összes feltételt az összes el nem küldött számla szerepeltetéséhez.</span><span class="sxs-lookup"><span data-stu-id="39f46-224">In the **Inquiry** dialog box, configure the filtering conditions for both sales invoices and project invoices, or leave the conditions blank to include all unsubmitted invoices.</span></span>

    ![Beküldési szűrési feltételek beállítása](media/e-Invoicing-services-get-started-ITA-Set-up-Submission-filter-criteria.png)

2. <span data-ttu-id="39f46-226">Kattintson az **OK** gombra a **Lekérdezés** párbeszédpanel bezárásához.</span><span class="sxs-lookup"><span data-stu-id="39f46-226">Select **OK** to close the **Inquiry** dialog box.</span></span>
3. <span data-ttu-id="39f46-227">Kattintson az **OK** gombra a kiválasztott dokumentumok elküldéséhez.</span><span class="sxs-lookup"><span data-stu-id="39f46-227">Select **OK** submit the selected documents.</span></span>

> <span data-ttu-id="39f46-228">![MEGJEGYZÉS]A dokumentum szolgáltatáson keresztüli beküldésének első kísérlete során a program rákérdez, hogy megerősíti-e a kapcsolatot az Elektronikus számlázásbővítménnyel.</span><span class="sxs-lookup"><span data-stu-id="39f46-228">![NOTE] During your first attempt to submit a document through the service, you will be prompted to confirm the connection with the Electronic invoicing add-on.</span></span> <span data-ttu-id="39f46-229">Válassza a **Kattintson az Elektronikus dokumentumbeküldési szolgáltatáshoz való csatlakozáshoz**.</span><span class="sxs-lookup"><span data-stu-id="39f46-229">Select **Click here to connect to Electronic Document Submission Service**.</span></span>

#### <a name="view-submission-logs"></a><span data-ttu-id="39f46-230">Beküldési naplók megtekintése</span><span class="sxs-lookup"><span data-stu-id="39f46-230">View submission logs</span></span>

<span data-ttu-id="39f46-231">Megtekintheti az összes beküldött dokumentum beküldési naplóját.</span><span class="sxs-lookup"><span data-stu-id="39f46-231">You can view the submission logs for all submitted documents.</span></span>

1. <span data-ttu-id="39f46-232">Menjen a **Szervezeti adminisztráció \> Időszakos \> Elektronikus dokumentumok \> Elektronikus dokumentumbeküldési napló** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="39f46-232">Go to **Organization administration \> Periodic \> Electronic documents \> Electronic document submission log**.</span></span>
2. <span data-ttu-id="39f46-233">A **Dokumentumtípus** mezőben válassza ki a **Vevői számlanapló** vagy a **Projektszámla** lehetőséget a szükséges elektronikus dokumentumok szűréséhez.</span><span class="sxs-lookup"><span data-stu-id="39f46-233">In the **Document type** field, select **Customer invoice journal** or **Project invoice** to filter for the required electronic documents.</span></span>

    ![A dokumentumtípus kiválasztása a beküldési naplók megtekintéséhez](media/e-Invoicing-services-get-started-ITA-Select-Document-type-for-viewing-submission-log.png)

    <span data-ttu-id="39f46-235">A **Beküldési állapot** oszlopban látható érték a beküldési folyamat állapotát jelöli.</span><span class="sxs-lookup"><span data-stu-id="39f46-235">The value that is shown in the **Submission status** column represents the status of the submission process.</span></span> <span data-ttu-id="39f46-236">Azt jelzi, hogy a folyamatot konfigurálták-e, és hogy szükség van-e további műveletre.</span><span class="sxs-lookup"><span data-stu-id="39f46-236">It indicates whether the process ran as configured and whether additional action is required.</span></span>

3. <span data-ttu-id="39f46-237">A Művelet ablaktáblán válassza ki a **Lekérdezések \> Beküldések részletei** lehetőséget a beküldési végrehajtási naplók részleteinek megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="39f46-237">On the Action Pane, select **Inquiries \> Submission details** to view the details of the submission execution logs.</span></span>

    ![A beküldési napló részleteinek megtekintése](media/e-Invoicing-services-get-started-ITA-View-Submission-log-details.png)

4. <span data-ttu-id="39f46-239">A **Műveletek feldolgozása** gyorslapon az RCS-ben beállított funkcióverzióban konfigurált műveletekhez tartozó végrehajtási naplót tekintheti meg.</span><span class="sxs-lookup"><span data-stu-id="39f46-239">On the **Processing actions** FastTab, you can view the execution log for the actions that are configured in the feature version that was set up in RCS.</span></span> <span data-ttu-id="39f46-240">Az **Állapot** oszlop azt jelzi, hogy a művelet futtatása sikeres volt-e.</span><span class="sxs-lookup"><span data-stu-id="39f46-240">The **Status** column shows whether the action was successfully run.</span></span>
5. <span data-ttu-id="39f46-241">A **Műveletfájlok** gyorslapon a műveletek végrehajtása során létrehozott közbenső fájlokat tekintheti meg.</span><span class="sxs-lookup"><span data-stu-id="39f46-241">On the **Action files** FastTab, you can view the intermediate files that were generated during execution of the actions.</span></span> <span data-ttu-id="39f46-242">Kiválaszthatja a **Megtekintés** elemet a kimeneti XML-fájl **FatturaPA**-formátumban történő letöltéséhez, illetve annak tartalmának megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="39f46-242">You can select **View** to download the output XML file in **FatturaPA** format and view its content.</span></span>

## <a name="related-topics"></a><span data-ttu-id="39f46-243">Kapcsolódó témakörök</span><span class="sxs-lookup"><span data-stu-id="39f46-243">Related topics</span></span>

- [<span data-ttu-id="39f46-244">Elektronikus számlázásbővítmény – áttekintés</span><span class="sxs-lookup"><span data-stu-id="39f46-244">Electronic invoicing add-on overview</span></span>](e-invoicing-service-overview.md)
- [<span data-ttu-id="39f46-245">Első lépések az Elektronikus számlázásbővítménnyel</span><span class="sxs-lookup"><span data-stu-id="39f46-245">Get started with the Electronic invoicing add-on</span></span>](e-invoicing-get-started.md)
- [<span data-ttu-id="39f46-246">Az Elektronikus számlázásbővítmény beállítása</span><span class="sxs-lookup"><span data-stu-id="39f46-246">Set up the Electronic invoicing add-on</span></span>](e-invoicing-setup.md)
