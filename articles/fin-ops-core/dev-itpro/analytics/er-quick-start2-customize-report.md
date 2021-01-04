---
title: ER-formátum módosítása egyéni elektronikus dokumentum generálásához
description: Ez a témakör azt mutatja be, hogyan lehet módosítani a Microsoft által biztosított elektronikus jelentéskészítési (ER) formátumot, hogy az egyedi elektronikus dokumentumot generáljon.
author: NickSelin
manager: AnnBe
ms.date: 06/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERParameters, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, EROperationDesigner, ERVendorTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 20e7a32ac5f6ab21f89ed3c11c64458286864c9d
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680170"
---
# <a name="adjust-an-er-format-to-generate-a-custom-electronic-document"></a><span data-ttu-id="87124-103">ER-formátum módosítása egyéni elektronikus dokumentum generálásához</span><span class="sxs-lookup"><span data-stu-id="87124-103">Adjust an ER format to generate a custom electronic document</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="87124-104">Az ebben a témakörben ismertetett eljárások azt mutatják be, hogy a Rendszergazda vagy az Elektronikus jelentéskészítési funkció tanácsadói szerepkörével rendelkező felhasználó hogyan hajthatja végre ezeket a feladatokat:</span><span class="sxs-lookup"><span data-stu-id="87124-104">The procedures in this topic explain how a user in the System Administrator or Electronic Reporting Functional Consultant role can perform these tasks:</span></span>

- <span data-ttu-id="87124-105">Az [Elektronikus jelentéskészítési (ER) keretrendszer](general-electronic-reporting.md) paramétereinek konfigurálása.</span><span class="sxs-lookup"><span data-stu-id="87124-105">Configure parameters for the [Electronic reporting (ER) framework](general-electronic-reporting.md).</span></span>
- <span data-ttu-id="87124-106">A Microsoft által biztosított és a [szállítói kifizetések](../../../finance/cash-bank-management/tasks/vendor-payment-overview.md) feldolgozása során a fizetési fájlok előállításához használt ER-konfigurációk importálása.</span><span class="sxs-lookup"><span data-stu-id="87124-106">Import ER configurations that are provided by Microsoft and used to generate a payment file while a [vendor payment](../../../finance/cash-bank-management/tasks/vendor-payment-overview.md) is being processed.</span></span>
- <span data-ttu-id="87124-107">A Microsoft által biztosított szabvány ER-formátum konfiguráció egyéni verziójának létrehozása.</span><span class="sxs-lookup"><span data-stu-id="87124-107">Create a custom version of a standard ER format configuration that is provided by Microsoft.</span></span>
- <span data-ttu-id="87124-108">Az egyéni ER-formátum konfigurációjának módosítása, hogy olyan kifizetési fájlokat generáljon, amelyek megfelelnek egy adott bank követelményeinek.</span><span class="sxs-lookup"><span data-stu-id="87124-108">Modify the custom ER format configuration so that it generates payment files that meets the requirements of a specific bank.</span></span>
- <span data-ttu-id="87124-109">A szabvány ER-formátum konfigurációnak az egyéni ER-formátum konfigurációban végzett módosításainak adoptálása.</span><span class="sxs-lookup"><span data-stu-id="87124-109">Adopt changes that are made to the standard ER format configuration in the custom ER format configuration.</span></span>

<span data-ttu-id="87124-110">A **GBSI** vállalatban valamennyi következő eljárást végrehajthatja.</span><span class="sxs-lookup"><span data-stu-id="87124-110">All the following procedures can be done in the **GBSI** company.</span></span> <span data-ttu-id="87124-111">Nincs szükség kódolásra.</span><span class="sxs-lookup"><span data-stu-id="87124-111">No coding is required.</span></span>

- [<span data-ttu-id="87124-112">ER-keretrendszer konfigurálása</span><span class="sxs-lookup"><span data-stu-id="87124-112">Configure the ER framework</span></span>](#ConfigureFramework)

    - [<span data-ttu-id="87124-113">ER-paraméterek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="87124-113">Configure ER parameters</span></span>](#ConfigureParameters)
    - [<span data-ttu-id="87124-114">ER-konfigurációszolgáltató aktiválása</span><span class="sxs-lookup"><span data-stu-id="87124-114">Activate an ER configuration provider</span></span>](#ActivateProvider)

        - [<span data-ttu-id="87124-115">Az ER-konfigurációszolgáltatók listájának áttekintése</span><span class="sxs-lookup"><span data-stu-id="87124-115">Review the list of ER configuration providers</span></span>](#ReviewProvidersList)
        - [<span data-ttu-id="87124-116">Új ER-konfigurációszolgáltató hozzáadása</span><span class="sxs-lookup"><span data-stu-id="87124-116">Add a new ER configuration provider</span></span>](#ActivateProvider)
        - [<span data-ttu-id="87124-117">ER-konfigurációszolgáltató aktiválása</span><span class="sxs-lookup"><span data-stu-id="87124-117">Activate an ER configuration provider</span></span>](#ActivateAddedProvider)

- [<span data-ttu-id="87124-118">A szabvány ER-formátumkonfigurációk importálása</span><span class="sxs-lookup"><span data-stu-id="87124-118">Import the standard ER format configurations</span></span>](#ImportERSolution1)

    - [<span data-ttu-id="87124-119">A szabvány ER-konfigurációk importálása</span><span class="sxs-lookup"><span data-stu-id="87124-119">Import the standard ER configurations</span></span>](#ImportERFormat1)
    - [<span data-ttu-id="87124-120">Importált ER-konfigurációk áttekintése</span><span class="sxs-lookup"><span data-stu-id="87124-120">Review the imported ER configurations</span></span>](#ReviewImportedERSolution)

- [<span data-ttu-id="87124-121">Szállítói fizetés előkészítése feldolgozásra</span><span class="sxs-lookup"><span data-stu-id="87124-121">Prepare a vendor payment for processing</span></span>](#PrepareVendorPayment)

    - [<span data-ttu-id="87124-122">Banki információ hozzáadása egy szállítói fiókhoz</span><span class="sxs-lookup"><span data-stu-id="87124-122">Add bank information for a vendor account</span></span>](#AddBankAccount)
    - [<span data-ttu-id="87124-123">Szállítói kifizetés bevitele</span><span class="sxs-lookup"><span data-stu-id="87124-123">Enter a vendor payment</span></span>](#EnterVendorPayment)

- [<span data-ttu-id="87124-124">Szállítói kifizetés feldolgozása a szabvány ER-formátum használatával</span><span class="sxs-lookup"><span data-stu-id="87124-124">Process a vendor payment by using the standard ER format</span></span>](#ProcessVendorPayment1)

    - [<span data-ttu-id="87124-125">Elektronikus fizetési mód beállítása</span><span class="sxs-lookup"><span data-stu-id="87124-125">Set up the electronic payment method</span></span>](#ConfigureMethodOfPayment1)
    - [<span data-ttu-id="87124-126">Szállítói kifizetés feldolgozása</span><span class="sxs-lookup"><span data-stu-id="87124-126">Process a vendor payment</span></span>](#ProcessPayment1)

- [<span data-ttu-id="87124-127">A szabvány ER-formátum testreszabása</span><span class="sxs-lookup"><span data-stu-id="87124-127">Customize the standard ER format</span></span>](#CustomizeProvidedFormat)

    - [<span data-ttu-id="87124-128">Egyéni formátum létrehozása</span><span class="sxs-lookup"><span data-stu-id="87124-128">Create a custom format</span></span>](#DeriveProvidedFormat)
    - [<span data-ttu-id="87124-129">Egyéni formátum szerkesztése</span><span class="sxs-lookup"><span data-stu-id="87124-129">Edit a custom format</span></span>](#ConfigureDerivedFormat)
    - [<span data-ttu-id="87124-130">Egyéni formátum megjelölése futtathatóként</span><span class="sxs-lookup"><span data-stu-id="87124-130">Mark a custom format as runnable</span></span>](#MarkFormatRunnable)

- [<span data-ttu-id="87124-131">Szállítói kifizetés feldolgozása az egyéni ER-formátum használatával</span><span class="sxs-lookup"><span data-stu-id="87124-131">Process a vendor payment by using the custom ER format</span></span>](#ProcessVendorPayment2)

    - [<span data-ttu-id="87124-132">Elektronikus fizetési mód beállítása</span><span class="sxs-lookup"><span data-stu-id="87124-132">Set up the electronic payment method</span></span>](#ConfigureMethodOfPayment2)
    - [<span data-ttu-id="87124-133">Szállítói kifizetés feldolgozása</span><span class="sxs-lookup"><span data-stu-id="87124-133">Process a vendor payment</span></span>](#ProcessPayment2)

- [<span data-ttu-id="87124-134">A szabvány ER-formátumkonfigurációk új verzióinak importálása</span><span class="sxs-lookup"><span data-stu-id="87124-134">Import new versions of the standard ER format configurations</span></span>](#ImportERSolution2)

    - [<span data-ttu-id="87124-135">A szabvány ER-konfigurációk új verzióinak importálása</span><span class="sxs-lookup"><span data-stu-id="87124-135">Import new versions of the standard ER configurations</span></span>](#ImportERFormat2)
    - [<span data-ttu-id="87124-136">Importált ER-formátumkonfigurációk áttekintése</span><span class="sxs-lookup"><span data-stu-id="87124-136">Review the imported ER format configurations</span></span>](#ReviewImportedERFormat)

- [<span data-ttu-id="87124-137">Az importált formátum új verziójában szereplő módosítások adoptálása egy egyéni formátumban</span><span class="sxs-lookup"><span data-stu-id="87124-137">Adopt the changes in the new version of an imported format in a custom format</span></span>](#AdoptNewBaseVersion)

    - [<span data-ttu-id="87124-138">Egyéni formátum aktuális tervezet változatának befejezése</span><span class="sxs-lookup"><span data-stu-id="87124-138">Complete the current draft version of a custom format</span></span>](#CompleteDerivedFormat)
    - [<span data-ttu-id="87124-139">Egyéni formátum alapjának áthelyezése új alapverzióra</span><span class="sxs-lookup"><span data-stu-id="87124-139">Rebase a custom format to a new base version</span></span>](#RebaseDerivedFormat)
    - [<span data-ttu-id="87124-140">Szállítói kifizetés feldolgozása egy új alapra helyezett ER-formátum használatával</span><span class="sxs-lookup"><span data-stu-id="87124-140">Process a vendor payment by using a rebased ER format</span></span>](#ProcessPayment3)

- [<span data-ttu-id="87124-141">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="87124-141">Additional resources</span></span>](#References)

## <a name="configure-the-er-framework"></a><a id="ConfigureFramework"></a><span data-ttu-id="87124-142">ER-keretrendszer konfigurálása</span><span class="sxs-lookup"><span data-stu-id="87124-142">Configure the ER framework</span></span>

<span data-ttu-id="87124-143">Az Elektronikus jelentéskészítési funkció tanácsadó szerepkörében lévő felhasználóként konfigurálnia kell a minimálisan szükséges ER-paraméterek készletét, mielőtt elkezdené használni az ER-keretrendszert a szabványos formátum egyéni verziójának tervezéséhez.</span><span class="sxs-lookup"><span data-stu-id="87124-143">As a user in the Electronic Reporting Functional Consultant role, you must configure the minimal set of ER parameters before you can start to use the ER framework to design a custom version of a standard ER format.</span></span>

### <a name="configure-er-parameters"></a><a id="ConfigureParameters"></a><span data-ttu-id="87124-144">ER-paraméterek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="87124-144">Configure ER parameters</span></span>

1. <span data-ttu-id="87124-145">Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.</span><span class="sxs-lookup"><span data-stu-id="87124-145">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="87124-146">A **Lokalizációs konfigurációk** oldalon, a **Kapcsolódó hivatkozások** szakaszban, válassza az **Elektronikus jelentéskészítés paraméterei** elemet.</span><span class="sxs-lookup"><span data-stu-id="87124-146">On the **Localization configurations** page, in the **Related links** section, select **Electronic reporting parameters**.</span></span>
3. <span data-ttu-id="87124-147">Az **Elektronikus jelentéskészítési paraméterek** oldalon, az **Általános** lapon a **Tervezői mód engedélyezése** lehetőséget állítsa **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="87124-147">On the **Electronic reporting parameters** page, on the **General** tab, set the **Enable design mode** option to **Yes**.</span></span>
4. <span data-ttu-id="87124-148">A **Mellékletek** lapon állítsa be a következő paramétereket:</span><span class="sxs-lookup"><span data-stu-id="87124-148">On the **Attachments** tab, set the following parameters:</span></span>

    - <span data-ttu-id="87124-149">A **Konfigurációk** mezőben válassza ki a **Fájl** típust az **USMF** vállalat esetében.</span><span class="sxs-lookup"><span data-stu-id="87124-149">In the **Configurations** field, select the **File** type for the **USMF** company.</span></span>
    - <span data-ttu-id="87124-150">A **Feladatarchívum**, **Ideiglenes**, **Alap** és **Egyebek** mezőkben válassza a **Fájl** típust.</span><span class="sxs-lookup"><span data-stu-id="87124-150">In the **Job archive**, **Temporary**, **Baseline**, and **Others** fields, select the **File** type.</span></span>

<span data-ttu-id="87124-151">Az ER-paraméterekkel kapcsolatos további tudnivalókat lásd: [ER-keretrendszer konfigurálása](electronic-reporting-er-configure-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="87124-151">For more information about ER parameters, see [Configure the ER framework](electronic-reporting-er-configure-parameters.md).</span></span>

### <a name="activate-an-er-configuration-provider"></a><a id="ActivateProvider"></a><span data-ttu-id="87124-152">ER-konfigurációszolgáltató aktiválása</span><span class="sxs-lookup"><span data-stu-id="87124-152">Activate an ER configuration provider</span></span>

<span data-ttu-id="87124-153">Minden hozzáadott ER-konfigurációt egy ER-konfigurációszolgáltató által birtokoltként kell megjelölni.</span><span class="sxs-lookup"><span data-stu-id="87124-153">Every ER configuration that is added is marked as owned by an ER configuration provider.</span></span> <span data-ttu-id="87124-154">Erre a célra az **Elektronikus jelentéskészítés** munkaterületen aktiválható ER-konfigurációszolgáltató használatos.</span><span class="sxs-lookup"><span data-stu-id="87124-154">The ER configuration provider that is activated in the **Electronic reporting** workspace is used for this purpose.</span></span> <span data-ttu-id="87124-155">Éppen ezért aktiválnia kell egy ER-konfigurációszolgáltatót az **Elektronikus jelentéskészítés** munkaterületen, mielőtt elkezdené az ER-konfigurációk hozzáadását vagy szerkesztését.</span><span class="sxs-lookup"><span data-stu-id="87124-155">Therefore, you must activate an ER configuration provider in the **Electronic reporting** workspace before you start to add or edit ER configurations.</span></span>

> [!NOTE]
> <span data-ttu-id="87124-156">Csak az ER-konfiguráció tulajdonosa szerkesztheti.</span><span class="sxs-lookup"><span data-stu-id="87124-156">Only the owner of an ER configuration can edit it.</span></span> <span data-ttu-id="87124-157">Éppen ezért aktiválnia kell a megfelelő ER-konfigurációszolgáltatót az **Elektronikus jelentéskészítés** munkaterületen, mielőtt elkezdené az ER-konfigurációk hozzáadását vagy szerkesztését.</span><span class="sxs-lookup"><span data-stu-id="87124-157">Therefore, before an ER configuration can be edited, the appropriate ER configuration provider must be activated in the **Electronic reporting** workspace.</span></span>

#### <a name="review-the-list-of-er-configuration-providers"></a><a id="ReviewProvidersList"></a><span data-ttu-id="87124-158">Az ER-konfigurációszolgáltatók listájának áttekintése</span><span class="sxs-lookup"><span data-stu-id="87124-158">Review the list of ER configuration providers</span></span>

1. <span data-ttu-id="87124-159">Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.</span><span class="sxs-lookup"><span data-stu-id="87124-159">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="87124-160">A **Lokalizációs konfigurációk** oldalon, a **Kapcsolódó hivatkozások** szakaszban, válassza a **Konfigurációszolgáltatók** elemet.</span><span class="sxs-lookup"><span data-stu-id="87124-160">On the **Localization configurations** page, in the **Related links** section, select **Configuration providers**.</span></span>
3. <span data-ttu-id="87124-161">A **Konfigurációszolgáltatók tábla** oldalon minden szolgáltatói rekordnak egyedi neve és URL-címe van.</span><span class="sxs-lookup"><span data-stu-id="87124-161">On the **Configuration provider table** page, each provider record has a unique name and URL.</span></span> <span data-ttu-id="87124-162">Tekintse át az oldal tartalmát.</span><span class="sxs-lookup"><span data-stu-id="87124-162">Review the contents of this page.</span></span> <span data-ttu-id="87124-163">Ha a már létezik a **Litware, Inc.** (`https://www.litware.com`) rekordja, hagyja ki a következő eljárást: [Új ER-konfigurációszolgáltató hozzáadása](#ActivateProvider).</span><span class="sxs-lookup"><span data-stu-id="87124-163">If a record for **Litware, Inc.** (`https://www.litware.com`) already exists, skip the next procedure, [Add a new ER configuration provider](#ActivateProvider).</span></span>

#### <a name="add-a-new-er-configuration-provider"></a><a id="ActivateProvider"></a><span data-ttu-id="87124-164">Új ER-konfigurációszolgáltató hozzáadása</span><span class="sxs-lookup"><span data-stu-id="87124-164">Add a new ER configuration provider</span></span>

1. <span data-ttu-id="87124-165">Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.</span><span class="sxs-lookup"><span data-stu-id="87124-165">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="87124-166">A **Lokalizációs konfigurációk** oldalon, a **Kapcsolódó hivatkozások** szakaszban, válassza a **Konfigurációszolgáltatók** elemet.</span><span class="sxs-lookup"><span data-stu-id="87124-166">On the **Localization configurations** page, in the **Related links** section, select **Configuration providers**.</span></span>
3. <span data-ttu-id="87124-167">A **Konfigurációszolgáltatók** oldalon válassza az **Új** elemet.</span><span class="sxs-lookup"><span data-stu-id="87124-167">On the **Configuration providers** page, select **New**.</span></span>
4. <span data-ttu-id="87124-168">A **Név** mezőbe írja be a következőt: **Litware, Inc.**.</span><span class="sxs-lookup"><span data-stu-id="87124-168">In the **Name** field, enter **Litware, Inc.**</span></span>
5. <span data-ttu-id="87124-169">Az **Internetcím** mezőben adja meg a következőt: `https://www.litware.com`.</span><span class="sxs-lookup"><span data-stu-id="87124-169">In the **Internet address** field, enter `https://www.litware.com`.</span></span>
6. <span data-ttu-id="87124-170">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87124-170">Select **Save**.</span></span>

#### <a name="activate-an-er-configuration-provider"></a><a id="ActivateAddedProvider"></a><span data-ttu-id="87124-171">ER-konfigurációszolgáltató aktiválása</span><span class="sxs-lookup"><span data-stu-id="87124-171">Activate an ER configuration provider</span></span>

1. <span data-ttu-id="87124-172">Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.</span><span class="sxs-lookup"><span data-stu-id="87124-172">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="87124-173">A **Lokalizációs konfigurációk** oldalon, a **Konfigurációszolgáltatók** szakaszban válassza ki a **Litware, Inc.** csempét, majd válassza a **Beállítás aktívként** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87124-173">On the **Localization configurations** page, in the **Configuration providers** section, select the **Litware, Inc.** tile, and then select **Set active**.</span></span>

<span data-ttu-id="87124-174">További információért az ER-konfigurációszolgáltatókkal kapcsolatban tekintse át a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](tasks/er-configuration-provider-mark-it-active-2016-11.md) eljárást.</span><span class="sxs-lookup"><span data-stu-id="87124-174">For more information about ER configuration providers, see [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>

## <a name="import-the-standard-er-format-configurations"></a><a id="ImportERSolution1"></a><span data-ttu-id="87124-175">A szabvány ER-formátumkonfigurációk importálása</span><span class="sxs-lookup"><span data-stu-id="87124-175">Import the standard ER format configurations</span></span>

### <a name="import-the-standard-er-configurations"></a><a id="ImportERFormat1"></a><span data-ttu-id="87124-176">A szabvány ER-konfigurációk importálása</span><span class="sxs-lookup"><span data-stu-id="87124-176">Import the standard ER configurations</span></span>

<span data-ttu-id="87124-177">Ha a szabvány ER-konfigurációkat a Microsoft Dynamics 365 Finance jelenlegi példányához szeretné hozzáadni, importálnia kell azokat az adott példányhoz konfigurált ER [adattárból](general-electronic-reporting.md#Repository).</span><span class="sxs-lookup"><span data-stu-id="87124-177">To add the standard ER configurations to your current instance of Microsoft Dynamics 365 Finance, you must import them from the ER [repository](general-electronic-reporting.md#Repository) that was configured for that instance.</span></span>

1. <span data-ttu-id="87124-178">Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.</span><span class="sxs-lookup"><span data-stu-id="87124-178">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="87124-179">A **Lokalizációs konfigurációk** oldalon, a **Konfigurációszolgáltatók** szakaszban válassza ki a **Microsoft** csempét, majd válassza ki az **Adattárak** lehetőséget a Microsoft szolgáltatóhoz tartozó adattárak listájának megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="87124-179">On the **Localization configurations** page, in the **Configuration providers** section, select the **Microsoft** tile, and then select **Repositories** to view the list of repositories for the Microsoft provider.</span></span>
3. <span data-ttu-id="87124-180">A **Konfigurációs adattárak** lapon válassza ki a **Globális** típusú adattárat, majd válassza a **Megnyitás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87124-180">On the **Configuration repositories** page, select the repository of the **Global** type, and then select **Open**.</span></span> <span data-ttu-id="87124-181">Ha a rendszer felkéri a hitelesítésre a Regulatory Configuration Service szolgáltatáshoz való kapcsolódáshoz, kövesse a hitelesítési utasításokat.</span><span class="sxs-lookup"><span data-stu-id="87124-181">If you're prompted for authorization to connect to Regulatory Configuration Service, follow the authorization instructions.</span></span>
4. <span data-ttu-id="87124-182">A **Konfigurációs adattárak** oldalon, a bal oldali panel konfigurációs fájában válassza ki a **BACS (UK)** formátumkonfigurációt.</span><span class="sxs-lookup"><span data-stu-id="87124-182">On the **Configuration repository** page, in the configuration tree in the left pane, select the **BACS (UK)** format configuration.</span></span>
5. <span data-ttu-id="87124-183">A **Verziók** gyorslapon válassza ki a kijelölt ER-formátumkonfiguráció **1.1**-es verzióját.</span><span class="sxs-lookup"><span data-stu-id="87124-183">On the **Versions** FastTab, select version **1.1** of the selected ER format configuration.</span></span>
6. <span data-ttu-id="87124-184">Kattintson az **Importálás** lehetőségre a kiválasztott verzió Globális tárból a jelenlegi Finance and Operations példányba történő letöltéséhez.</span><span class="sxs-lookup"><span data-stu-id="87124-184">Select **Import** to download the selected version from the Global repository to the current Finance instance.</span></span>

![Konfigurációk tárháza oldal](./media/er-quick-start2-import-solution1.png)

> [!TIP]
> <span data-ttu-id="87124-186">Ha nem sikerül elérnie a [globális adattárat](er-download-configurations-global-repo.md), akkor lehetősége van ehelyett [letölteni konfigurációkat](download-electronic-reporting-configuration-lcs.md) a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásból.</span><span class="sxs-lookup"><span data-stu-id="87124-186">If you have trouble accessing the [Global repository](er-download-configurations-global-repo.md), you can [download configurations](download-electronic-reporting-configuration-lcs.md) from Microsoft Dynamics Lifecycle Services (LCS) instead.</span></span>

### <a name="review-the-imported-er-configurations"></a><a id="ReviewImportedERSolution"></a><span data-ttu-id="87124-187">Importált ER-konfigurációk áttekintése</span><span class="sxs-lookup"><span data-stu-id="87124-187">Review the imported ER configurations</span></span>

1. <span data-ttu-id="87124-188">Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.</span><span class="sxs-lookup"><span data-stu-id="87124-188">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="87124-189">A **Lokalizációs konfigurációk** oldalon, a **Konfigurációk** szakaszban, válassza ki a **Jelentéskészítési konfiguráció** csempét.</span><span class="sxs-lookup"><span data-stu-id="87124-189">On the **Localization configurations** page, in the **Configurations** section, select the **Reporting configurations** tile.</span></span>
3. <span data-ttu-id="87124-190">A **Konfigurációk** oldalon, a bal oldali panelen található konfigurációk fájában bontsa ki a **Fizetési modell** elemet.</span><span class="sxs-lookup"><span data-stu-id="87124-190">On the **Configurations** page, in the configuration tree in the left pane, expand **Payment model**.</span></span>
4. <span data-ttu-id="87124-191">Figyelje meg, hogy a kiválasztott **BACS (UK)** ER-formátumon kívül más szükséges ER-konfigurációk importálása is megtörtént.</span><span class="sxs-lookup"><span data-stu-id="87124-191">Notice that, in addition to the selected **BACS (UK)** ER format, other required ER configurations were imported.</span></span> <span data-ttu-id="87124-192">Győződjön meg arról, hogy a konfigurációs fában a következő ER-konfigurációk érhetők el:</span><span class="sxs-lookup"><span data-stu-id="87124-192">Make sure that the following ER configurations are available in the configuration tree:</span></span>

    - <span data-ttu-id="87124-193">**Fizetési modell** – Ez a konfiguráció tartalmazza az [adatmodell](general-electronic-reporting.md#data-model-and-model-mapping-components) ER-összetevőt, amely a fizetési üzleti tartomány adatstruktúráját jelöli.</span><span class="sxs-lookup"><span data-stu-id="87124-193">**Payment model** – This configuration contains the [data model](general-electronic-reporting.md#data-model-and-model-mapping-components) ER component that represents the data structure of the payment business domain.</span></span>
    - <span data-ttu-id="87124-194">**Kifizetési modell leképezés 1611** – Ez a konfiguráció tartalmazza a [modell-leképezés](general-electronic-reporting.md#data-model-and-model-mapping-components) összetevőt, amely leírja, hogy az adatmodell milyen módon van kitöltve az alkalmazási adatokkal futási időben.</span><span class="sxs-lookup"><span data-stu-id="87124-194">**Payment model mapping 1611** – This configuration contains the [model mapping](general-electronic-reporting.md#data-model-and-model-mapping-components) ER component that describes how the data model is filled in with application data at runtime.</span></span>
    - <span data-ttu-id="87124-195">**BACS (UK)** – Ez a konfiguráció tartalmazza az ER-összetevők [formátum](general-electronic-reporting.md#FormatComponentOutbound) és formátumleképezés ER-összetevőit.</span><span class="sxs-lookup"><span data-stu-id="87124-195">**BACS (UK)** – This configuration contains the [format](general-electronic-reporting.md#FormatComponentOutbound) and format mapping ER components.</span></span> <span data-ttu-id="87124-196">A formátum összetevő meghatározza a jelentés elrendezését.</span><span class="sxs-lookup"><span data-stu-id="87124-196">The format component specifies the report layout.</span></span> <span data-ttu-id="87124-197">A formátumleképezési összetevő tartalmazza a modell-adatforrást, és meghatározza, hogy a jelentés elrendezését milyen módon kell kitölteni ennek az adatforrásnak a használatával futásidőben.</span><span class="sxs-lookup"><span data-stu-id="87124-197">The format mapping component contains the model data source and specifies how the report layout is filled in by using this data source at runtime.</span></span>

![Konfigurációk oldala](./media/er-quick-start2-imported-solution1.png)

## <a name="prepare-a-vendor-payment-for-processing"></a><a id="PrepareVendorPayment"></a><span data-ttu-id="87124-199">Szállítói fizetés előkészítése feldolgozásra</span><span class="sxs-lookup"><span data-stu-id="87124-199">Prepare a vendor payment for processing</span></span>

### <a name="add-bank-information-for-a-vendor-account"></a><a id="AddBankAccount"></a><span data-ttu-id="87124-200">Banki információ hozzáadása egy szállítói fiókhoz</span><span class="sxs-lookup"><span data-stu-id="87124-200">Add bank information for a vendor account</span></span>

<span data-ttu-id="87124-201">Hozzá kell adni banki információkat egy szállítói számlához, amelyre egy regisztrált fizetésben hivatkoznak.</span><span class="sxs-lookup"><span data-stu-id="87124-201">You must add bank information for a vendor account that will be referred to later in a registered payment.</span></span>

1. <span data-ttu-id="87124-202">Nyissa meg a következőt: **Kötelezettségek** \> **Szállítók** \> **Minden szállító**.</span><span class="sxs-lookup"><span data-stu-id="87124-202">Go to **Accounts payable** \> **Vendors** \> **All vendors**.</span></span>
2. <span data-ttu-id="87124-203">Válassza ki a **Minden szállító** oldalt, válassza ki a **GB_SI_000001** szállítói számlát, majd a Művelet panelen, a **Szállító** lap **Beállítás** csoportjában válassza ki a **Bankszámlák** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87124-203">On the **All vendors** page, select the **GB_SI_000001** vendor account, and then, on the Action Pane, on the **Vendor** tab, in the **Set up** group, select **Bank accounts**.</span></span>
3. <span data-ttu-id="87124-204">A **Szállítói bankszámlák** oldalon válassza az **Új** parancsot, majd adja meg a következő adatokat:</span><span class="sxs-lookup"><span data-stu-id="87124-204">On the **Vendor bank accounts** page, select **New**, and then enter the following information:</span></span>

    1. <span data-ttu-id="87124-205">A **Bankszámla** mezőben adja meg a **GBP OPER** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87124-205">In the **Bank account** field, enter **GBP OPER**.</span></span>
    2. <span data-ttu-id="87124-206">A **Bankcsoportok** mezőben válassza ki a **BankGBP** elemet.</span><span class="sxs-lookup"><span data-stu-id="87124-206">In the **Bank groups** field, select **BankGBP**.</span></span>
    3. <span data-ttu-id="87124-207">A **Bankszámlaszám** mezőben adja meg a **202015** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87124-207">In the **Bank account number** field, enter **202015**.</span></span>
    4. <span data-ttu-id="87124-208">A **SWIFT-kód** mezőben adja meg a <a id="DefineSWIFTCode"></a>**CHASDEFXXXX** értéket.</span><span class="sxs-lookup"><span data-stu-id="87124-208">In the **SWIFT code** field, enter <a id="DefineSWIFTCode"></a>**CHASDEFXXXX**.</span></span>
    5. <span data-ttu-id="87124-209">Az **IBAN** mezőben adja meg a **GB33BUKB20201555555555** értéket.</span><span class="sxs-lookup"><span data-stu-id="87124-209">In the **IBAN** field, enter **GB33BUKB20201555555555**.</span></span>
    6. <span data-ttu-id="87124-210">Az **Útvonalszám** mezőben tartsa meg az <a id="DefineRoutingNumber"></a>**123456** alapértelmezett értéket.</span><span class="sxs-lookup"><span data-stu-id="87124-210">In the **Routing number** field, keep the default value, <a id="DefineRoutingNumber"></a>**123456**.</span></span>

    ![Szállítói bankszámlák oldal](./media/er-quick-start2-bank-account.png)

4. <span data-ttu-id="87124-212">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87124-212">Select **Save**.</span></span>
5. <span data-ttu-id="87124-213">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="87124-213">Close the page.</span></span>
6. <span data-ttu-id="87124-214">A **Minden szállító** lapon nyissa meg a **GB_SI_000001** szállítói számlát.</span><span class="sxs-lookup"><span data-stu-id="87124-214">On the **All vendors** page, open the **GB_SI_000001** vendor account.</span></span>
7. <span data-ttu-id="87124-215">Ha szükséges, a szállítói részletek oldalon válassza a **Szerkesztés** parancsot az oldal szerkeszthetővé tételéhez.</span><span class="sxs-lookup"><span data-stu-id="87124-215">On the vendor details page, select **Edit** to make the page editable, if required.</span></span>
8. <span data-ttu-id="87124-216">A **Fizetés** gyorslap **Bankszámla** mezőjében válassza ki a **GBP OPER** elemet.</span><span class="sxs-lookup"><span data-stu-id="87124-216">On the **Payment** FastTab, in the **Bank account** field, select **GBP OPER**.</span></span>

    ![Szállító részletei oldal](./media/er-quick-start2-bank-account-reference.png)

9. <span data-ttu-id="87124-218">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87124-218">Select **Save**.</span></span>
10. <span data-ttu-id="87124-219">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="87124-219">Close the page.</span></span>

### <a name="enter-a-vendor-payment"></a><a id="EnterVendorPayment"></a><span data-ttu-id="87124-220">Szállítói kifizetés bevitele</span><span class="sxs-lookup"><span data-stu-id="87124-220">Enter a vendor payment</span></span>

<span data-ttu-id="87124-221">Új szállítói kifizetés megadásához a [fizetési javaslatot](https://docs.microsoft.com/dynamics365/finance/accounts-payable/create-vendor-payments-payment-proposal) kell használnia.</span><span class="sxs-lookup"><span data-stu-id="87124-221">You must enter a new vendor payment by using a [payment proposal](https://docs.microsoft.com/dynamics365/finance/accounts-payable/create-vendor-payments-payment-proposal).</span></span>

1. <span data-ttu-id="87124-222">Ugorjon a **Kötelezettségek** \> **Fizetések** \> **Szállítói kifizetés naplója** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="87124-222">Go to **Accounts payable** \> **Payments** \> **Vendor payment journal**.</span></span>
2. <span data-ttu-id="87124-223">A **Szállító kifizetési naplója** oldalon válassza az **Új** elemet.</span><span class="sxs-lookup"><span data-stu-id="87124-223">On the **Vendor payment journal** page, select **New**.</span></span>
3. <span data-ttu-id="87124-224">A **Név** mezőbe válassza a **VendPay** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87124-224">In the **Name** field, select **VendPay**.</span></span>
4. <span data-ttu-id="87124-225">**Sorok** kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="87124-225">Select **Lines**.</span></span>
5. <span data-ttu-id="87124-226">Válassza a **Kifizetési javaslat** \> **Fizetési javaslat létrehozása** elemet.</span><span class="sxs-lookup"><span data-stu-id="87124-226">Select **Payment proposal** \> **Create payment proposal**.</span></span>
6. <span data-ttu-id="87124-227">A **Szállítói fizetési javaslat** párbeszédpanelen konfigurálja azokat a feltételeket, amelyek csak az **GB_SI_000001** szállítói számlához tartozó rekordok szűréséhez szükségesek, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="87124-227">In the **Vendor payment proposal** dialog box, configure conditions to filter for records for the **GB_SI_000001** vendor account only, and then select **OK**.</span></span>
7. <span data-ttu-id="87124-228">Válassza ki a **00000007_Inv** számlához tartozó sort, majd válassza a **Kifizetés létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87124-228">Select the line for the **00000007_Inv** invoice, and then select **Create payment**.</span></span>

    ![Szállítói fizetési javaslatok párbeszédpanel](./media/er-quick-start2-payment-proposal.png)

8. <span data-ttu-id="87124-230">Győződjön meg róla, hogy a megadott fizetés az **Elektronikus** fizetési mód használatára van beállítva.</span><span class="sxs-lookup"><span data-stu-id="87124-230">Verify that the payment that is entered is configured to use the **Electronic** method of payment.</span></span>

    ![Szállítói kifizetések oldala](./media/er-quick-start2-payment-line.png)

## <a name="process-a-vendor-payment-by-using-the-standard-er-format"></a><a id="ProcessVendorPayment1"></a><span data-ttu-id="87124-232">Szállítói kifizetés feldolgozása a szabvány ER-formátum használatával</span><span class="sxs-lookup"><span data-stu-id="87124-232">Process a vendor payment by using the standard ER format</span></span>

### <a name="set-up-the-electronic-payment-method"></a><a id="ConfigureMethodOfPayment1"></a><span data-ttu-id="87124-233">Elektronikus fizetési mód beállítása</span><span class="sxs-lookup"><span data-stu-id="87124-233">Set up the electronic payment method</span></span>

<span data-ttu-id="87124-234">Az elektronikus fizetési módot úgy kell konfigurálni, hogy az az importált ER-formátum konfigurációját használja.</span><span class="sxs-lookup"><span data-stu-id="87124-234">You must configure the electronic method of payment so that it uses the imported ER format configuration.</span></span>

1. <span data-ttu-id="87124-235">Nyissa meg a következőt: **Kötelezettségek** \> **Kifizetés beállítása** \> **Fizetési módok**.</span><span class="sxs-lookup"><span data-stu-id="87124-235">Go to **Accounts payable** \> **Payment setup** \> **Methods of payment**.</span></span>
2. <span data-ttu-id="87124-236">A **Fizetési módok – szállítók** oldalon válassza ki az **Elektronikus** fizetési módot a bal oldali ablaktáblán.</span><span class="sxs-lookup"><span data-stu-id="87124-236">On the **Methods of payment - vendors** page, select the **Electronic** method of payment in the left pane.</span></span>
3. <span data-ttu-id="87124-237">Válassza ki a **Szerkesztés** opciót.</span><span class="sxs-lookup"><span data-stu-id="87124-237">Select **Edit**.</span></span>
4. <span data-ttu-id="87124-238">Adja meg a **Fájlformátumok** gyorslap **Általános elektronikus export formátum** beállítását **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="87124-238">On the **File formats** FastTab, set the **General electronic Export format** option to **Yes**.</span></span>
5. <span data-ttu-id="87124-239">Az **Exportálási formátum konfigurálása** mezőben válassza ki az **BACS (UK)** formátumkonfigurációt.</span><span class="sxs-lookup"><span data-stu-id="87124-239">In the **Export format configuration** field, select the **BACS (UK)** format configuration.</span></span>

    ![Fizetési módok - szállítók oldal](./media/er-quick-start2-method-of-payment1.png)

6. <span data-ttu-id="87124-241">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87124-241">Select **Save**.</span></span>

### <a name="process-a-vendor-payment"></a><a id="ProcessPayment1"></a><span data-ttu-id="87124-242">Szállítói kifizetés feldolgozása</span><span class="sxs-lookup"><span data-stu-id="87124-242">Process a vendor payment</span></span>

1. <span data-ttu-id="87124-243">Ugorjon a **Kötelezettségek** \> **Fizetések** \> **Szállítói kifizetés naplója** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="87124-243">Go to **Accounts payable** \> **Payments** \> **Vendor payment journal**.</span></span>
2. <span data-ttu-id="87124-244">A **Szállítói fizetési napló** lapon válassza ki a korábban hozzáadott fizetési naplót, majd válassza ki a **Sorok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87124-244">On the **Vendor payment journal** page, select the payment journal that you added earlier, and then select **Lines**.</span></span>
3. <span data-ttu-id="87124-245">A **Szállítói kifizetések** oldalon válassza a **Kifizetések létrehozása** elemet.</span><span class="sxs-lookup"><span data-stu-id="87124-245">On the **Vendor payments** page, select **Generate payments**.</span></span>
4. <span data-ttu-id="87124-246">A **Kifizetések létrehozása** párbeszédpanelen adja meg a következő adatokat:</span><span class="sxs-lookup"><span data-stu-id="87124-246">In the **Generate payments** dialog box, enter the following information:</span></span>

    - <span data-ttu-id="87124-247">A **Fizetési mód** mezőben válassza az **Elektronikus** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87124-247">In the **Method of payment** field, select **Electronic**.</span></span>
    - <span data-ttu-id="87124-248">A **Bankszámla** mezőben válassza a **GBSI OPER** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87124-248">In the **Bank account** field, select **GBSI OPER**.</span></span>

5. <span data-ttu-id="87124-249">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87124-249">Select **OK**.</span></span>
6. <span data-ttu-id="87124-250">Az **Elektronikus jelentések paraméterei** párbeszédpanelen állítsa a **Nyomtatási vezérlő jelentés** beállítását **Igen** értékre, majd válassza az **OK** gombot.</span><span class="sxs-lookup"><span data-stu-id="87124-250">In the **Electronic report parameters** dialog box, set the **Print control report** option to **Yes**, and then select **OK**.</span></span>

    ![Elektronikus jelentés paraméterei – párbeszédoldal](./media/er-quick-start2-payment-dialog1.png)

    > [!NOTE]
    > <span data-ttu-id="87124-252">A kifizetési fájlon kívül ellenőrzési jelentés is létrehozható.</span><span class="sxs-lookup"><span data-stu-id="87124-252">In addition to the payment file, you can now generate the control report.</span></span>

7. <span data-ttu-id="87124-253">Töltse le a zip-fájlt, majd csomagolja ki belőle a következő fájlokat:</span><span class="sxs-lookup"><span data-stu-id="87124-253">Download the zip file, and then extract the following files from it:</span></span>

    - <span data-ttu-id="87124-254">Az ellenőrzési jelentést Excel-formátumban</span><span class="sxs-lookup"><span data-stu-id="87124-254">The control report in Excel format</span></span>
    - <span data-ttu-id="87124-255">A fizetési fájl TXT-formátumban</span><span class="sxs-lookup"><span data-stu-id="87124-255">The payment file in TXT format</span></span>

        <span data-ttu-id="87124-256">Figyelje meg, hogy a megadott ER-formátum [struktúrájával](#PositionRoutingNumber) összhangban a létrehozott fájl kifizetési sora a konfigurált bankszámlához [megadott](#DefineRoutingNumber) útválasztási számmal kezdődik.</span><span class="sxs-lookup"><span data-stu-id="87124-256">Notice that, in accordance with the [structure](#PositionRoutingNumber) of the provided ER format, the payment line in the generated file starts with the routing number that was [defined](#DefineRoutingNumber) for the configured bank account.</span></span>

        ![Fizetési fájl TXT-formátum](./media/er-quick-start2-payment-file1.png)

## <a name="customize-the-standard-er-format"></a><a id="CustomizeProvidedFormat"></a><span data-ttu-id="87124-258">A szabvány ER-formátum testreszabása</span><span class="sxs-lookup"><span data-stu-id="87124-258">Customize the standard ER format</span></span>

<span data-ttu-id="87124-259">Az ebben a részben megjelenő példa esetében a Microsoft által biztosított ER-konfigurációkat kell használni a BACS formátumú szállítói kifizetési fájlok létrehozásához, de a megfelelő testreszabással kell ellátni őket egy adott bank követelményeinek támogatásához.</span><span class="sxs-lookup"><span data-stu-id="87124-259">For the example that is shown in this section, you want to use the ER configurations that are provided by Microsoft to generate vendor payment files in BACS format, but you must add a customization to support the requirements of a specific bank.</span></span> <span data-ttu-id="87124-260">Azt is szeretné, hogy a saját egyéni formátuma frissíthető legyen, ha elérhetővé válnak az ER-konfigurációk új verziói.</span><span class="sxs-lookup"><span data-stu-id="87124-260">You also want to be able to upgrade your custom format when new versions of ER configurations become available.</span></span> <span data-ttu-id="87124-261">A frissítést azonban a lehető legalacsonyabb költséggel szeretné elvégezni.</span><span class="sxs-lookup"><span data-stu-id="87124-261">However, you want to be able to do the upgrade at the lowest cost.</span></span>

<span data-ttu-id="87124-262">Ebben az esetben a Litware, Inc. képviselőjeként létre kell hozni (származtatni) egy új ER-formátumkonfigurációt a **BACS (UK)** Microsoft által megadott konfiguráció alapján.</span><span class="sxs-lookup"><span data-stu-id="87124-262">In this case, as the representative of Litware, Inc., you must create (derive) a new ER format configuration by using the **BACS (UK)** Microsoft-provided configuration as a base.</span></span>

### <a name="create-a-custom-format"></a><a id="DeriveProvidedFormat"></a><span data-ttu-id="87124-263">Egyéni formátum létrehozása</span><span class="sxs-lookup"><span data-stu-id="87124-263">Create a custom format</span></span>

1. <span data-ttu-id="87124-264">Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.</span><span class="sxs-lookup"><span data-stu-id="87124-264">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="87124-265">A **Konfigurációk** oldalon, a bal oldali panelen található konfigurációk fájában bontsa ki a **Fizetési modell** elemet, majd válassza a **BACS (UK)** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87124-265">On the **Configurations** page, in the configuration tree in the left pane, expand **Payment model**, and then select **BACS (UK)**.</span></span> <span data-ttu-id="87124-266">A Litware, Inc. ennek az ER-formátumkonfigurációnak az 1.1-es verzióját fogja használni az egyéni verzió alapjaként.</span><span class="sxs-lookup"><span data-stu-id="87124-266">Litware, Inc. will use version 1.1 of this ER format configuration as the base for the custom version.</span></span>
3. <span data-ttu-id="87124-267">A **Konfiguráció létrehozása** kiválasztásával megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="87124-267">Select **Create configuration** to open the drop-down dialog box.</span></span> <span data-ttu-id="87124-268">A párbeszédablak segítségével új konfigurációt hozhat létre az egyéni fizetési formátumra vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="87124-268">You can use this dialog box to create a new configuration for a custom payment format.</span></span>
4. <span data-ttu-id="87124-269">Az **Új** mezőcsoportban válassza ki a **Származtatás innen: BACS (UK), Microsoft** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87124-269">In the **New** field group, select the **Derive from Name: BACS (UK), Microsoft** option.</span></span>
5. <span data-ttu-id="87124-270">A **Név** mezőbe írja be a következőt: **BACS (UK egyéni)**.</span><span class="sxs-lookup"><span data-stu-id="87124-270">In the **Name** field, enter **BACS (UK custom)**.</span></span>

    ![Konfiguráció létrehozása legördülő párbeszédpanel](./media/er-quick-start2-add-derived-format.png)

6. <span data-ttu-id="87124-272">Válassza a **Konfiguráció létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87124-272">Select **Create configuration**.</span></span>

<span data-ttu-id="87124-273">A **BACS (UK egyéni)** ER-formátum konfigurációjának 1.1.1-es verziója jön létre.</span><span class="sxs-lookup"><span data-stu-id="87124-273">Version 1.1.1 of the **BACS (UK custom)** ER format configuration is created.</span></span> <span data-ttu-id="87124-274">Ez a verzió **Piszkozat** [állapottal](general-electronic-reporting.md#component-versioning) rendelkezik, és szerkeszthető.</span><span class="sxs-lookup"><span data-stu-id="87124-274">This version has a [status](general-electronic-reporting.md#component-versioning) of **Draft** and can be edited.</span></span> <span data-ttu-id="87124-275">Az egyéni ER-formátum jelenlegi tartalma megegyezik a Microsoft által biztosított formátum tartalmával.</span><span class="sxs-lookup"><span data-stu-id="87124-275">The current content of your custom ER format matches the content of the format that is provided by Microsoft.</span></span>

![Konfigurációk oldala](./media/er-quick-start2-derived-format-configuration1.png)

### <a name="edit-a-custom-format"></a><a id="ConfigureDerivedFormat"></a><span data-ttu-id="87124-277">Egyéni formátum szerkesztése</span><span class="sxs-lookup"><span data-stu-id="87124-277">Edit a custom format</span></span>

<span data-ttu-id="87124-278">Az egyéni formátumot úgy kell konfigurálni, hogy megfeleljen a bankspecifikus követelményeknek.</span><span class="sxs-lookup"><span data-stu-id="87124-278">You must configure your custom format so that it meets bank-specific requirements.</span></span> <span data-ttu-id="87124-279">Előfordulhat például, hogy a bank előírja, hogy a létrejövő kifizetési fájlok között szerepel egy olyan Society for Worldwide Interbank Financial Telecommunication (SWIFT) kód, amelyhez a feldolgozott szállítói kifizetésben az ügynök szerepkör van hozzárendelve.</span><span class="sxs-lookup"><span data-stu-id="87124-279">For example, a bank might require that payment files that are generated include the Society for Worldwide Interbank Financial Telecommunication (SWIFT) code of a bank that is assigned the agent role in the processed vendor payment.</span></span> <span data-ttu-id="87124-280">A SWIFT-kódok olyan nemzetközi banki kódok, amelyek világszerte meghatározott bankokat határoznak meg.</span><span class="sxs-lookup"><span data-stu-id="87124-280">SWIFT codes are international bank codes that identify specific banks worldwide.</span></span> <span data-ttu-id="87124-281">Más néven banki azonosító kódoknak (BIC) nevezik őket.</span><span class="sxs-lookup"><span data-stu-id="87124-281">They are also known as Bank Identifier Codes (BICs).</span></span> <span data-ttu-id="87124-282">A SWIFT-kódnak 11 karakter hosszúnak kell lennie, és meg kell adni a létrehozott kifizetési fájlok minden fizetési sora kezdetén.</span><span class="sxs-lookup"><span data-stu-id="87124-282">The SWIFT code must be 11 characters long, and it must be entered at the beginning of every payment line in a generated payment file.</span></span>

1. <span data-ttu-id="87124-283">Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.</span><span class="sxs-lookup"><span data-stu-id="87124-283">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="87124-284">A **Konfigurációk** oldalon, a bal oldali panelen található konfigurációk fájában bontsa ki a **Fizetési modell** elemet, majd válassza a **BACS (UK egyéni)** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87124-284">On the **Configurations** page, in the configuration tree in the left pane, expand **Payment model**, and then select **BACS (UK custom)**.</span></span>
3. <span data-ttu-id="87124-285">A **Verziók** gyorslapon válassza ki a kijelölt konfiguráció **1.1.1**-es verzióját.</span><span class="sxs-lookup"><span data-stu-id="87124-285">On the **Versions** FastTab, select version **1.1.1** of the selected configuration.</span></span>
4. <span data-ttu-id="87124-286">Válassza a **Tervező** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87124-286">Select **Designer**.</span></span>
5. <span data-ttu-id="87124-287">A **Formátumtervező** oldalon válassza a **Részletek megjelenítése** lehetőséget, ha további tájékoztatást szeretne látni a formátumelemekről.</span><span class="sxs-lookup"><span data-stu-id="87124-287">On the **Format designer** page, select **Show details** to view more information about the format elements.</span></span>
6. <span data-ttu-id="87124-288">Bontsa ki és tekintése át a következő elemeket:</span><span class="sxs-lookup"><span data-stu-id="87124-288">Expand and review the following elements:</span></span>

    - <span data-ttu-id="87124-289">A **Mappa** típusú **BACSReportsFolder** elemet.</span><span class="sxs-lookup"><span data-stu-id="87124-289">The **BACSReportsFolder** element of the **Folder** type.</span></span> <span data-ttu-id="87124-290">Ez az elem a ZIP formátumú kimenet létrehozásához használatos.</span><span class="sxs-lookup"><span data-stu-id="87124-290">This element is used to generate output in ZIP format.</span></span>
    - <span data-ttu-id="87124-291">A **Fájl** típusú **fájl** elemet.</span><span class="sxs-lookup"><span data-stu-id="87124-291">The **file** element of the **File** type.</span></span> <span data-ttu-id="87124-292">Ez az elem a TXT formátumú kifizetési fájl létrehozásához használatos.</span><span class="sxs-lookup"><span data-stu-id="87124-292">This element is used to generate a payment file in TXT format.</span></span>
    - <span data-ttu-id="87124-293">A **Sorozat** típusú **tranzakciók** elemet.</span><span class="sxs-lookup"><span data-stu-id="87124-293">The **transactions** element of the **Sequence** type.</span></span> <span data-ttu-id="87124-294">Ez az elem a kifizetési fájl egyszeres kifizetési sorának létrehozásához használatos.</span><span class="sxs-lookup"><span data-stu-id="87124-294">This element is used to generate a single payment line in a payment file.</span></span>
    - <span data-ttu-id="87124-295">A **Sorozat** típusú **tranzakció** elemet.</span><span class="sxs-lookup"><span data-stu-id="87124-295">The **transaction** element of the **Sequence** type.</span></span> <span data-ttu-id="87124-296">Ez az elem az egyszeres kifizetési sor egyes mezőinek létrehozásához használatos.</span><span class="sxs-lookup"><span data-stu-id="87124-296">This element is used to generate individual fields of a single payment line.</span></span>

7. <span data-ttu-id="87124-297">Válassza ki a **tranzakció** elemet.</span><span class="sxs-lookup"><span data-stu-id="87124-297">Select the **transaction** element.</span></span>

    ![Tranzakció elem az ER-művelettervezőben](./media/er-quick-start2-derived-format0.png)

    > [!NOTE]
    > <span data-ttu-id="87124-299">A megadott jelentés úgy van beállítva, hogy <a id="PositionRoutingNumber"></a>minden kifizetési sor a banki regisztrációs útválasztási kezdődjön.</span><span class="sxs-lookup"><span data-stu-id="87124-299">The provided report is configured so that <a id="PositionRoutingNumber"></a>every payment line starts with the bank routing number.</span></span> <span data-ttu-id="87124-300">Erre a célra a **vendBankRouteNum** formátumelem használatos.</span><span class="sxs-lookup"><span data-stu-id="87124-300">The **vendBankRouteNum** format element is used for this purpose.</span></span> 

8. <span data-ttu-id="87124-301">Válassza a **Hozzáadás** lehetőséget, majd válassza ki a hozzáadni kívánt formátumelem **Szöveg\\Karakterlánc** típusát:</span><span class="sxs-lookup"><span data-stu-id="87124-301">Select **Add**, and then select the **Text\\String** type of the format element that you're adding:</span></span>

    1. <span data-ttu-id="87124-302">A **Név** mezőbe írja be a következőt: **vendBankSWIFT**.</span><span class="sxs-lookup"><span data-stu-id="87124-302">In the **Name** field, enter **vendBankSWIFT**.</span></span>
    2. <span data-ttu-id="87124-303">Adja meg a **11** értéket a **Minimális hossz** mezőben.</span><span class="sxs-lookup"><span data-stu-id="87124-303">In the **Minimum length** field, enter **11**.</span></span>
    3. <span data-ttu-id="87124-304">Adja meg a **11** értéket a **Maximális hossz** mezőben.</span><span class="sxs-lookup"><span data-stu-id="87124-304">In the **Maximum length** field, enter **11**.</span></span>
    4. <span data-ttu-id="87124-305">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87124-305">Select **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="87124-306">A **vendBankSWIFT** elem a létrejövő fájlokban a szállítói bank SWIFT-kódjának megadására szolgál.</span><span class="sxs-lookup"><span data-stu-id="87124-306">The **vendBankSWIFT** element will be used to enter the SWIFT code of a vendor bank in generated files.</span></span>

9. <span data-ttu-id="87124-307">Válassza ki a **vendBankSWIFT** elemet a formátumstruktúra fájában.</span><span class="sxs-lookup"><span data-stu-id="87124-307">In the format structure tree, select **vendBankSWIFT**.</span></span>
10. <span data-ttu-id="87124-308">Válassza **Mozgatás felfelé** lehetőséget a kiválasztott formátumelem egy szinttel feljebb helyezéséhez.</span><span class="sxs-lookup"><span data-stu-id="87124-308">Select **Move up** to move the selected format element up one level.</span></span> <span data-ttu-id="87124-309">Ismételje meg ezt a lépést addig, amíg a **vendBankSWIFT** elem a <a id="PositionSWIFTCode"></a>szülő **tranzakció** elem alatti első elem lesz.</span><span class="sxs-lookup"><span data-stu-id="87124-309">Repeat this step until the **vendBankSWIFT** element is the <a id="PositionSWIFTCode"></a>first element under the parent **transaction** element.</span></span>

    ![VendBankSWIFT, mint a tranzakció alatti első elem az ER-művelettervezőben](./media/er-quick-start2-derived-format1.png)

11. <span data-ttu-id="87124-311">Miközben a **vendBankSWIFT** még mindig ki van választva a szerkezeti fában, válassza ki a **Leképezés** lapot, majd bontsa ki a **modell** adatforrást.</span><span class="sxs-lookup"><span data-stu-id="87124-311">While the **vendBankSWIFT** is still selected in the format structure tree, select the **Mapping** tab, and then expand the **model** data source.</span></span>
12. <span data-ttu-id="87124-312">Bontsa ki a **model.Payment** \> **model.Payment.CreditorAgent** elemet, majd válassza a **model.Payment.CreditorAgent.BICFI** adatforrásmezőt.</span><span class="sxs-lookup"><span data-stu-id="87124-312">Expand **model.Payment** \> **model.Payment.CreditorAgent**, and select the **model.Payment.CreditorAgent.BICFI** data source field.</span></span> <span data-ttu-id="87124-313">Ez az adatforrásmező kiteszi annak a szállítói banknak a SWIFT-kódját, amely a feldolgozott szállítói kifizetésben szereplő ügynöki szerepkörhöz van rendelve.</span><span class="sxs-lookup"><span data-stu-id="87124-313">This data source field exposes the SWIFT code of a vendor bank that is assigned the agent role in the processed vendor payment.</span></span>
13. <span data-ttu-id="87124-314">Válassza a **Bind** elemet.</span><span class="sxs-lookup"><span data-stu-id="87124-314">Select **Bind**.</span></span> <span data-ttu-id="87124-315">A **vendBankSWIFT** formátumelem most a **model.Payment.CreditorAgent.BICFI** adatforrásmezőhöz van kötve, így a rendszer a létrejövő kifizetési fájlokban rögzíti a SWIFT-kódokat.</span><span class="sxs-lookup"><span data-stu-id="87124-315">The **vendBankSWIFT** format element is now bound with the **model.Payment.CreditorAgent.BICFI** data source field, so that SWIFT codes will be entered in generated payment files.</span></span>

    ![Az ER-művelettervező model.Payment.CreditorAgent.BICFI adatforrásmezőjéhez kötött vendBankSWIFT formátumelem](./media/er-quick-start2-derived-format2.png)

14. <span data-ttu-id="87124-317">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87124-317">Select **Save**.</span></span>
15. <span data-ttu-id="87124-318">Zárja be a tervezőoldalt.</span><span class="sxs-lookup"><span data-stu-id="87124-318">Close the designer page.</span></span>

### <a name="mark-a-custom-format-as-runnable"></a><a id="MarkFormatRunnable"></a><span data-ttu-id="87124-319">Egyéni formátum megjelölése futtathatóként</span><span class="sxs-lookup"><span data-stu-id="87124-319">Mark a custom format as runnable</span></span>

<span data-ttu-id="87124-320">Miután létrehozta az egyéni formátum első verzióját, és az a **Piszkozat** állapottal rendelkezik, tesztelés céljából futtathatja azt.</span><span class="sxs-lookup"><span data-stu-id="87124-320">Now that the first version of your custom format has been created and has a status of **Draft**, you can run it for testing purposes.</span></span> <span data-ttu-id="87124-321">A jelentés futtatásához a szállítói kifizetést az egyéni ER-formátumra hivatkozó fizetési mód használatával kell feldolgoznia.</span><span class="sxs-lookup"><span data-stu-id="87124-321">To run the report, you must process a vendor payment by using the payment method that refers to your custom ER format.</span></span> <span data-ttu-id="87124-322">Alapértelmezésben, amikor egy ER-formátumot hív meg az alkalmazásból, csak a **Befejeződött** vagy **Megosztott** állapotú verziókat [veszi figyelembe](general-electronic-reporting.md#component-versioning) a rendszer.</span><span class="sxs-lookup"><span data-stu-id="87124-322">By default, when you call an ER format from the application, only versions that have a status of **Completed** or **Shared** are [considered](general-electronic-reporting.md#component-versioning).</span></span> <span data-ttu-id="87124-323">Ez a viselkedés segít megakadályozni a befejezetlen konstrukciókkal rendelkező ER-formátumok használatát.</span><span class="sxs-lookup"><span data-stu-id="87124-323">This behavior helps prevent ER formats that have unfinished designs from being used.</span></span> <span data-ttu-id="87124-324">A teszt futtatásakor azonban kényszerítheti az alkalmazást egy **Piszkozat** állapottal rendelkező ER-formátumverzió használatára.</span><span class="sxs-lookup"><span data-stu-id="87124-324">However, for your test runs, you can force the application to use the version of your ER format that has a status of **Draft**.</span></span> <span data-ttu-id="87124-325">Ily módon módosíthatja az aktuális formátum verziószámát, ha bármilyen módosítás szükséges.</span><span class="sxs-lookup"><span data-stu-id="87124-325">In this way, you can adjust the current format version if any modifications are required.</span></span> <span data-ttu-id="87124-326">További információ: [Alkalmazhatóság](electronic-reporting-destinations.md#applicability).</span><span class="sxs-lookup"><span data-stu-id="87124-326">For more information, see [Applicability](electronic-reporting-destinations.md#applicability).</span></span>

<span data-ttu-id="87124-327">Ha egy ER-formátum piszkozat verzióját kívánja használni, ennek kifejezett módon be kell jelölnie az ER-formátumot.</span><span class="sxs-lookup"><span data-stu-id="87124-327">To use the draft version of an ER format, you must explicitly mark the ER format.</span></span>

1. <span data-ttu-id="87124-328">Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.</span><span class="sxs-lookup"><span data-stu-id="87124-328">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="87124-329">A **Konfigurációk** oldal műveleti ablaktábláján, a **Konfigurációk** lapon, a **Speciális beállítások** csoportban válassza a **Felhasználói paraméterek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87124-329">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
3. <span data-ttu-id="87124-330">A **Felhasználói paraméterek** párbeszédpanelen állítsa a **Futtatási beállítások** beállítását **Igen** értékre, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="87124-330">In the **User parameters** dialog box, set the **Run settings** option to **Yes**, and then select **OK**.</span></span>
4. <span data-ttu-id="87124-331">Ha szükséges, a **Szerkesztés** gombbal az aktuális lapot szerkeszthetőre állíthatja.</span><span class="sxs-lookup"><span data-stu-id="87124-331">Select **Edit** to make the current page editable, as required.</span></span>
5. <span data-ttu-id="87124-332">A bal oldali ablak konfigurációs fáján válassza a **BACS (UK custom)** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87124-332">In the configuration tree in the left pane, select **BACS (UK custom)**.</span></span>
6. <span data-ttu-id="87124-333">Állítsa a **Piszkozat futtatása** beállítást **Igen** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="87124-333">Set the **Run Draft** option to **Yes**.</span></span>

    ![Piszkozat futtatása beállítás a Konfigurációk lapon](./media/er-quick-start2-derived-format-configuration2.png)

## <a name="process-a-vendor-payment-by-using-the-custom-er-format"></a><a id="ProcessVendorPayment2"></a><span data-ttu-id="87124-335">Szállítói kifizetés feldolgozása az egyéni ER-formátum használatával</span><span class="sxs-lookup"><span data-stu-id="87124-335">Process a vendor payment by using the custom ER format</span></span>

### <a name="set-up-the-electronic-payment-method"></a><a id="ConfigureMethodOfPayment2"></a><span data-ttu-id="87124-336">Elektronikus fizetési mód beállítása</span><span class="sxs-lookup"><span data-stu-id="87124-336">Set up the electronic payment method</span></span>

<span data-ttu-id="87124-337">Az elektronikus fizetési módot úgy kell konfigurálni, hogy a rendszer a szállítói kifizetéseket a saját egyéni ER-formátumával dolgozza fel.</span><span class="sxs-lookup"><span data-stu-id="87124-337">You must configure the electronic method of payment so that your custom ER format is used to process vendor payments.</span></span>

1. <span data-ttu-id="87124-338">Nyissa meg a következőt: **Kötelezettségek** \> **Kifizetés beállítása** \> **Fizetési módok**.</span><span class="sxs-lookup"><span data-stu-id="87124-338">Go to **Accounts payable** \> **Payment setup** \> **Methods of payment**.</span></span>
2. <span data-ttu-id="87124-339">A **Fizetési módok – szállítók** oldalon válassza ki az **Elektronikus** fizetési módot a bal oldali ablaktáblán.</span><span class="sxs-lookup"><span data-stu-id="87124-339">On the **Methods of payment - vendors** page, select the **Electronic** method of payment in the left pane.</span></span>
3. <span data-ttu-id="87124-340">Válassza ki a **Szerkesztés** opciót.</span><span class="sxs-lookup"><span data-stu-id="87124-340">Select **Edit**.</span></span>
4. <span data-ttu-id="87124-341">Adja meg a **Fájlformátum** gyorslap **Általános elektronikus export formátum** beállítását **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="87124-341">On the **File format** FastTab, set the **General electronic export format** option to **Yes**.</span></span>
5. <span data-ttu-id="87124-342">Az **Exportálási formátum konfigurálása** mezőben válassza ki az **BACS (UK egyéni)** formátumkonfigurációt.</span><span class="sxs-lookup"><span data-stu-id="87124-342">In the **Export format configuration** field, select the **BACS (UK custom)** format configuration.</span></span>

    ![Fizetési módok - szállítók oldal](./media/er-quick-start2-method-of-payment2.png)

6. <span data-ttu-id="87124-344">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87124-344">Select **Save**.</span></span>

### <a name="process-a-vendor-payment"></a><a id="ProcessPayment2"></a><span data-ttu-id="87124-345">Szállítói kifizetés feldolgozása</span><span class="sxs-lookup"><span data-stu-id="87124-345">Process a vendor payment</span></span>

1. <span data-ttu-id="87124-346">Ugorjon a **Kötelezettségek** \> **Fizetések** \> **Szállítói kifizetés naplója** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="87124-346">Go to **Accounts payable** \> **Payments** \> **Vendor payment journal**.</span></span>
2. <span data-ttu-id="87124-347">A **Szállítói fizetési napló** lapon válassza ki a korábban létrehozott fizetési naplót.</span><span class="sxs-lookup"><span data-stu-id="87124-347">On the **Vendor payment journal** page, select the payment journal that you created earlier.</span></span>
3. <span data-ttu-id="87124-348">**Sorok** kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="87124-348">Select **Lines**.</span></span>
4. <span data-ttu-id="87124-349">A **Szállítói kifizetések** oldalon, a rács felett válassza a **Kifizetési állapot** \> **Nincs** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87124-349">On the **Vendor payments** page, above the grid, select **Payment status** \> **None**.</span></span>
5. <span data-ttu-id="87124-350">Válassza a **Fizetés létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87124-350">Select **Generate payment**.</span></span>
6. <span data-ttu-id="87124-351">A **Kifizetések létrehozása** párbeszédpanelen adja meg a következő adatokat:</span><span class="sxs-lookup"><span data-stu-id="87124-351">In the **Generate payments** dialog box, enter the following information:</span></span>

    - <span data-ttu-id="87124-352">A **Fizetési mód** mezőben válassza az **Elektronikus** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87124-352">In the **Method of payment** field, select **Electronic**.</span></span>
    - <span data-ttu-id="87124-353">A **Bankszámla** mezőben válassza a **GBSI OPER** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87124-353">In the **Bank account** field, select **GBSI OPER**.</span></span>

7. <span data-ttu-id="87124-354">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87124-354">Select **OK**.</span></span>
8. <span data-ttu-id="87124-355">Az **Elektronikus jelentések paraméterei** párbeszédpanelen állítsa a **Nyomtatási vezérlő jelentés** beállítását **Igen** értékre, majd válassza az **OK** gombot.</span><span class="sxs-lookup"><span data-stu-id="87124-355">In the **Electronic report parameters** dialog box, set the **Print control report** option to **Yes**, and then select **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="87124-356">A kifizetési fájlon kívül csak ellenőrzési jelentést hozhat létre.</span><span class="sxs-lookup"><span data-stu-id="87124-356">In addition to the payment file, you can generate only the control report.</span></span>

9. <span data-ttu-id="87124-357">Töltse le a zip-fájlt, majd csomagolja ki belőle a következő fájlokat:</span><span class="sxs-lookup"><span data-stu-id="87124-357">Download the zip file, and then extract the following files from it:</span></span>

    - <span data-ttu-id="87124-358">Az ellenőrzési jelentést Excel-formátumban</span><span class="sxs-lookup"><span data-stu-id="87124-358">The control report in Excel format</span></span>
    - <span data-ttu-id="87124-359">A fizetési fájl TXT-formátumban</span><span class="sxs-lookup"><span data-stu-id="87124-359">The payment file in TXT format</span></span>

        <span data-ttu-id="87124-360">Figyelje meg, hogy az egyéni ER-formátum struktúrájával összhangban a létrehozott fájl kifizetési sora most azzal a SWIFT-kóddal [kezdődik](#PositionSWIFTCode), amelyet azon szállító bankszámláján [rögzítettek](#DefineSWIFTCode), amelynek a kifizetését már feldolgozták.</span><span class="sxs-lookup"><span data-stu-id="87124-360">Notice that, in accordance with the structure of your custom ER format, the payment line in the generated file now [starts](#PositionSWIFTCode) with the SWIFT code that was [entered](#DefineSWIFTCode) for the bank account of the vendor whose payment has been processed.</span></span>

        ![Fizetési fájl TXT-formátum](./media/er-quick-start2-payment-file2.png)

## <a name="import-new-versions-of-the-standard-er-format-configurations"></a><a id="ImportERSolution2"></a><span data-ttu-id="87124-362">A szabvány ER-formátumkonfigurációk új verzióinak importálása</span><span class="sxs-lookup"><span data-stu-id="87124-362">Import new versions of the standard ER format configurations</span></span>

<span data-ttu-id="87124-363">Az ebben a részben megjelenő példa esetében értesítést kap a Tudásbázis következő cikkéről: [KB3763330](https://fix.lcs.dynamics.com/Issue/Details?kb=3182046).</span><span class="sxs-lookup"><span data-stu-id="87124-363">For the example that is shown in this section, you receive a notification about Knowledge Base article [KB3763330](https://fix.lcs.dynamics.com/Issue/Details?kb=3182046).</span></span> <span data-ttu-id="87124-364">Ez a tájékoztatás tájékoztatja a **BACS (UK)** Microsoft által közzétett ER-formátum új verziójáról.</span><span class="sxs-lookup"><span data-stu-id="87124-364">This notification informs you about the new version of the **BACS (UK)** ER format that has been published by Microsoft.</span></span> <span data-ttu-id="87124-365">Az ellenőrzési jelentésen kívül ez az új verzió lehetővé teszi a felhasználók számára a kifizetési bizonylatokról szóló jelentés és a részvételi megjegyzés jelentés létrehozását a szállítói kifizetések feldolgozásakor.</span><span class="sxs-lookup"><span data-stu-id="87124-365">In addition to the control report, this new version lets users generate the payment advice report and the attending note report while a vendor payment is being processed.</span></span> <span data-ttu-id="87124-366">Hasznos lehet ennek a funkciónak a használata.</span><span class="sxs-lookup"><span data-stu-id="87124-366">You want to start to use that functionality.</span></span>

### <a name="import-new-versions-of-the-standard-er-configurations"></a><a id="ImportERFormat2"></a><span data-ttu-id="87124-367">A szabvány ER-konfigurációk új verzióinak importálása</span><span class="sxs-lookup"><span data-stu-id="87124-367">Import new versions of the standard ER configurations</span></span>

<span data-ttu-id="87124-368">Ha az ER-konfigurációk új verzióit szeretné hozzáadni az aktuális Finance-példányhoz, importálnia kell azokat a konfigurált ER-[adattárból](general-electronic-reporting.md#Repository).</span><span class="sxs-lookup"><span data-stu-id="87124-368">To add new versions of the ER configurations to the current Finance instance, you must import them from the ER [repository](general-electronic-reporting.md#Repository) that you've configured.</span></span>

1. <span data-ttu-id="87124-369">Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.</span><span class="sxs-lookup"><span data-stu-id="87124-369">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="87124-370">A **Lokalizációs konfigurációk** oldalon, a **Konfigurációszolgáltatók** szakaszban válassza ki a **Microsoft** csempét, majd válassza ki az **Adattárak** lehetőséget a Microsoft szolgáltatóhoz tartozó adattárak listájának megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="87124-370">On the **Localization configurations** page, in the **Configuration providers** section, select the **Microsoft** tile, and then select **Repositories** to view the list of repositories for the Microsoft provider.</span></span>
3. <span data-ttu-id="87124-371">A **Konfigurációs adattárak** lapon válassza ki a **Globális** típusú adattárat, majd válassza a **Megnyitás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87124-371">On the **Configuration repositories** page, select the repository of the **Global** type, and then select **Open**.</span></span> <span data-ttu-id="87124-372">Ha a rendszer felkéri a hitelesítésre a Regulatory Configuration Service szolgáltatáshoz való kapcsolódáshoz, kövesse a hitelesítési utasításokat.</span><span class="sxs-lookup"><span data-stu-id="87124-372">If you're prompted for authorization to connect to Regulatory Configuration Service, follow the authorization instructions.</span></span>
4. <span data-ttu-id="87124-373">A **Konfigurációs adattárak** oldalon, a bal oldali panel konfigurációs fájában válassza ki a **BACS (UK)** formátumkonfigurációt.</span><span class="sxs-lookup"><span data-stu-id="87124-373">On the **Configuration repository** page, in the configuration tree in the left pane, select the **BACS (UK)** format configuration.</span></span>
5. <span data-ttu-id="87124-374">A **Verziók** gyorslapon válassza ki a kijelölt ER-formátumkonfiguráció **3.3**-es verzióját.</span><span class="sxs-lookup"><span data-stu-id="87124-374">On the **Versions** FastTab, select version **3.3** of the selected ER format configuration.</span></span>
6. <span data-ttu-id="87124-375">Kattintson az **Importálás** lehetőségre a kiválasztott verzió Globális tárból a jelenlegi Finance and Operations példányba történő letöltéséhez.</span><span class="sxs-lookup"><span data-stu-id="87124-375">Select **Import** to download the selected version from the Global repository to the current Finance instance.</span></span>

![Konfigurációk tárháza oldal](./media/er-quick-start2-import-solution2.png)

> [!TIP]
> <span data-ttu-id="87124-377">Ha nem sikerül elérnie a [globális adattárat](er-download-configurations-global-repo.md), akkor lehetősége van ehelyett [letölteni konfigurációkat](download-electronic-reporting-configuration-lcs.md) a Lifecycle Services (LCS) szolgáltatásból.</span><span class="sxs-lookup"><span data-stu-id="87124-377">If you have trouble accessing the [Global repository](er-download-configurations-global-repo.md), you can [download configurations](download-electronic-reporting-configuration-lcs.md) from LCS instead.</span></span>

### <a name="review-the-imported-er-format-configurations"></a><a id="ReviewImportedERFormat"></a><span data-ttu-id="87124-378">Importált ER-formátumkonfigurációk áttekintése</span><span class="sxs-lookup"><span data-stu-id="87124-378">Review the imported ER format configurations</span></span>

1. <span data-ttu-id="87124-379">Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.</span><span class="sxs-lookup"><span data-stu-id="87124-379">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="87124-380">A **Lokalizációs konfigurációk** oldalon, a **Konfigurációk** szakaszban, válassza ki a **Jelentéskészítési konfiguráció** csempét.</span><span class="sxs-lookup"><span data-stu-id="87124-380">On the **Localization configurations** page, in the **Configurations** section, select the **Reporting configurations** tile.</span></span>
3. <span data-ttu-id="87124-381">A **Konfigurációk** oldalon, a bal oldali panelen található konfigurációk fájában bontsa ki a **Fizetési modell** elemet, majd válassza a **BACS (UK)** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87124-381">On the **Configurations** page, in the configuration tree in the left pane, expand **Payment model**, and then select **BACS (UK)**.</span></span>
4. <span data-ttu-id="87124-382">Válassza ki a **Verziók** gyorslap **3.3.** verzióját.</span><span class="sxs-lookup"><span data-stu-id="87124-382">On the **Versions** FastTab, select version **3.3**.</span></span>
5. <span data-ttu-id="87124-383">Válassza a **Tervező** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87124-383">Select **Designer**.</span></span>
6. <span data-ttu-id="87124-384">A **Formátumtervező** oldalon bontsa ki a **BACSReportsFolder** formátumelemet.</span><span class="sxs-lookup"><span data-stu-id="87124-384">On the **Format designer** page, expand the **BACSReportsFolder** format element.</span></span>
7.  <span data-ttu-id="87124-385">Figyelje meg, hogy a 3.3-as verzió tartalmazza a **PaymentAdviceReport** formátumelemet, amely a szállítói kifizetések feldolgozásakor a kifizetési bizonylatokról szóló jelentés létrehozásához használatos.</span><span class="sxs-lookup"><span data-stu-id="87124-385">Notice that version 3.3 contains the **PaymentAdviceReport** format element that is used to generate a payment advice report when a vendor payment is processed.</span></span>

    ![PaymentAdviceReport formátumelem az ER-művelettervezőben](./media/er-quick-start2-imported-solution2.png)

8. <span data-ttu-id="87124-387">Zárja be a tervezőoldalt.</span><span class="sxs-lookup"><span data-stu-id="87124-387">Close the designer page.</span></span>

## <a name="adopt-the-changes-in-the-new-version-of-an-imported-format-in-a-custom-format"></a><a id="AdoptNewBaseVersion"></a><span data-ttu-id="87124-388">Az importált formátum új verziójában szereplő módosítások adoptálása egy egyéni formátumban</span><span class="sxs-lookup"><span data-stu-id="87124-388">Adopt the changes in the new version of an imported format in a custom format</span></span>

### <a name="complete-the-current-draft-version-of-a-custom-format"></a><a id="CompleteDerivedFormat"></a><span data-ttu-id="87124-389">Egyéni formátum aktuális tervezet változatának befejezése</span><span class="sxs-lookup"><span data-stu-id="87124-389">Complete the current draft version of a custom format</span></span>

<span data-ttu-id="87124-390">Ha meg szeretné tartani az egyéni formátum jelenlegi állapotát, fejezze be az 1.1.1-es verziót úgy, hogy az állapotát a **Piszkozat** értékről **Befejezett** értékre módosítja.</span><span class="sxs-lookup"><span data-stu-id="87124-390">If you want to keep the current state of your custom format, complete the draft version 1.1.1 by changing its status from **Draft** to **Completed**.</span></span>

1. <span data-ttu-id="87124-391">Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.</span><span class="sxs-lookup"><span data-stu-id="87124-391">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="87124-392">A **Lokalizációs konfigurációk** oldalon, a **Konfigurációk** szakaszban, válassza ki a **Jelentéskészítési konfiguráció** csempét.</span><span class="sxs-lookup"><span data-stu-id="87124-392">On the **Localization configurations** page, in the **Configurations** section, select the **Reporting configurations** tile.</span></span>
3. <span data-ttu-id="87124-393">A **Konfigurációk** oldalon, a bal oldali panelen található konfigurációk fájában bontsa ki a **Fizetési modell** elemet, majd a **BACS (UK)** eleme, és válassza a **BACS (UK egyéni)** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87124-393">On the **Configurations** page, in the configuration tree in the left pane, expand **Payment model**, expand **BACS (UK)**, and then select **BACS (UK custom)**.</span></span>
4. <span data-ttu-id="87124-394">Válassza a **Verziók** gyorslap **Állapot módosítása** \> **Befejezés** elemét, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="87124-394">On the **Versions** FastTab, select **Change status** \> **Complete**, and then select **OK**.</span></span>

<span data-ttu-id="87124-395">Az 1.1.1-es verzió állapota a **Piszkozat** értékről a **Befejezett** értékre módosul , és a verzió írásvédett lesz.</span><span class="sxs-lookup"><span data-stu-id="87124-395">The status of version 1.1.1 is changed from **Draft** to **Completed**, and the version becomes read-only.</span></span> <span data-ttu-id="87124-396">Az új, szerkeszthető verzió (1.1.2) **Piszkozat** állapottal kerül hozzáadásra.</span><span class="sxs-lookup"><span data-stu-id="87124-396">A new editable version, 1.1.2, has been added and has a status of **Draft**.</span></span> <span data-ttu-id="87124-397">Ennek a verziónak a használatával további változtatásokat hajthat végre a saját egyéni ER-formátumában.</span><span class="sxs-lookup"><span data-stu-id="87124-397">You can use this version to make further changes in your custom ER format.</span></span>

### <a name="rebase-a-custom-format-to-a-new-base-version"></a><a id="RebaseDerivedFormat"></a><span data-ttu-id="87124-398">Egyéni formátum alapjának áthelyezése új alapverzióra</span><span class="sxs-lookup"><span data-stu-id="87124-398">Rebase a custom format to a new base version</span></span>

<span data-ttu-id="87124-399">A 3.3-as verziójú **BACS (UK)** formátum új funkcióinak a testreszabásában történő használatához módosítania kell a **BACS (UK egyéni)** egyéni konfiguráció alapkonfigurációját.</span><span class="sxs-lookup"><span data-stu-id="87124-399">To start to use the new functionality of version 3.3 of the **BACS (UK)** format in your customization, you must change the base configuration version for the custom configuration, **BACS (UK custom)**.</span></span> <span data-ttu-id="87124-400">Ennek a folyamatnak a neve [új alap](general-electronic-reporting.md#upgrading-a-format-selecting-a-new-version-of-base-format-rebase) megadása.</span><span class="sxs-lookup"><span data-stu-id="87124-400">This process is known as [rebasing](general-electronic-reporting.md#upgrading-a-format-selecting-a-new-version-of-base-format-rebase).</span></span> <span data-ttu-id="87124-401">Használja az új 3.3-as verziót a **BACS (UK)** 1.1-es verziója helyett.</span><span class="sxs-lookup"><span data-stu-id="87124-401">Instead of version 1.1 of **BACS (UK)**, use version 3.3.</span></span>

1. <span data-ttu-id="87124-402">Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.</span><span class="sxs-lookup"><span data-stu-id="87124-402">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="87124-403">A **Konfigurációk** oldalon, a bal oldali panelen található konfigurációk fájában bontsa ki a **Fizetési modell** elemet, majd válassza a **BACS (UK egyéni)** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87124-403">On the **Configurations** page, in the configuration tree in the left pane, expand **Payment model**, and then select **BACS (UK custom)**.</span></span>
3. <span data-ttu-id="87124-404">A **Verziók** gyorslapon válassza az **1.1.2** verziót, majd válassza az **Új alap** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87124-404">On the **Versions** FastTab, select version **1.1.2**, and then select **Rebase**.</span></span>
4. <span data-ttu-id="87124-405">Válassza az **Új alap** párbeszédpanelt **Cél verzió** mezőben, válassza az alapkonfiguráció **3.3** verzióját, és alkalmazza azt új alapként, valamint használja a konfiguráció frissítésére.</span><span class="sxs-lookup"><span data-stu-id="87124-405">In the **Rebase** dialog box, in the **Target version** field, select version **3.3** of the base configuration to apply it as the new base and use it to update the configuration.</span></span>

    ![Új alap párbeszédpanel](./media/er-quick-start2-rebase1.png)

5. <span data-ttu-id="87124-407">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87124-407">Select **OK**.</span></span>
6. <span data-ttu-id="87124-408">Figyelje meg, hogy a piszkozat verziójának száma **1.1.2**-ről **3.3.2**-re módosult az alapverzió változásainak megfelelően.</span><span class="sxs-lookup"><span data-stu-id="87124-408">Notice that the number of the draft version has been changed from **1.1.2** to **3.3.2** to reflect the change in the base version.</span></span>

    <span data-ttu-id="87124-409">A rendszer bizonyos ütközéseket észlelt az egyéni verzió és az új alapverzió egyesítésekor, mivel néhány formátummódosítást nem lehet automatikusan egyesíteni.</span><span class="sxs-lookup"><span data-stu-id="87124-409">When the custom version and a new base version are merged, some conflicts might be discovered because of format changes that can't be merged automatically.</span></span>

    ![Új alapra helyezett konfiguráció ütközésekkel a Konfigurációk oldalon](./media/er-quick-start2-rebase2.png)

    <span data-ttu-id="87124-411">Ha ütközések merülnek fel, akkor azokat manuálisan kell megoldani a formátumtervező programban.</span><span class="sxs-lookup"><span data-stu-id="87124-411">If conflicts are discovered, they must be manually resolved in the format designer.</span></span>

7. <span data-ttu-id="87124-412">Válassza ki a **Verziók** gyorslap **3.3.2.** verzióját.</span><span class="sxs-lookup"><span data-stu-id="87124-412">On the **Versions** FastTab, select version **3.3.2**.</span></span>
8. <span data-ttu-id="87124-413">Válassza a **Tervező** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87124-413">Select **Designer**.</span></span>
9. <span data-ttu-id="87124-414">A **Formátumtervező** lap **Részletek** gyorslapján jelöljön ki egy új alap ütközési rekordot, majd válassza az **Alapérték alkalmazása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87124-414">On the **Format designer** page, on the **Details** FastTab, select a rebase conflict record, and then select **Apply base value**.</span></span>

    ![Új alap ütközési rekord az ER-művelettervezőben](./media/er-quick-start2-rebase3.png)

10. <span data-ttu-id="87124-416">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87124-416">Select **Save**.</span></span>

    <span data-ttu-id="87124-417">Az új alap ütközési rekordnak ezután többé nem kellene megjelennie **Részletek** gyorslapon.</span><span class="sxs-lookup"><span data-stu-id="87124-417">The rebase conflict record should no longer appear on the **Details** FastTab.</span></span>

    ![Feloldott ütközés az ER-művelettervezőben](./media/er-quick-start2-rebase4.png)

    > [!NOTE]
    > <span data-ttu-id="87124-419">Az ütközést úgy oldotta fel, hogy megerősítette, hogy az alapmodell 3. verzióját kell használni ebben az ER-formátumban.</span><span class="sxs-lookup"><span data-stu-id="87124-419">You resolved the conflict by confirming that version 3 of the base model must be used in this ER format.</span></span>

11. <span data-ttu-id="87124-420">Bontsa ki a **BACSReportsFolder** \> **fájl** \> **tranzakciók** \> **tranzakció** elemet.</span><span class="sxs-lookup"><span data-stu-id="87124-420">Expand **BACSReportsFolder** \> **file** \> **transactions** \> **transaction**.</span></span>
12. <span data-ttu-id="87124-421">A **Feltérképezés** lapon figyelje meg, hogy az egyéni ER-formátumának 3.3.2-es verziója tartalmazza mind a testreszabását (a **vendBankSWIFT** formátumelemet és annak kötését), valamint a Microsoft által biztosított alap ER-formátum 3.3-as verziójának új funkcionalitását (a **PaymentAdviceReport** formátumú elem a beágyazott elemekkel és a konfigurált kötésekkel együtt).</span><span class="sxs-lookup"><span data-stu-id="87124-421">On the **Mapping** tab, notice that version 3.3.2 of your custom ER format contains both your customization (the **vendBankSWIFT** format element and its binding) and the new functionality of version 3.3 of the base ER format that was provided by Microsoft (the **PaymentAdviceReport** format element together with its nested elements and configured bindings).</span></span> <span data-ttu-id="87124-422">Csak néhány egérkattintással adoptálta az új alapverzió módosításait, egyesítve azokat a testreszabásával.</span><span class="sxs-lookup"><span data-stu-id="87124-422">In just a few mouse clicks, you adopted the modifications of a new base version by merging them with your customization.</span></span>

    ![Egyesített formátum az ER-művelettervezőben](./media/er-quick-start2-rebase5.png)

13. <span data-ttu-id="87124-424">Zárja be a tervezőoldalt.</span><span class="sxs-lookup"><span data-stu-id="87124-424">Close the designer page.</span></span>

> [!NOTE]
> <span data-ttu-id="87124-425">Az új alap művelet visszafordítható.</span><span class="sxs-lookup"><span data-stu-id="87124-425">The rebase action is reversible.</span></span> <span data-ttu-id="87124-426">Ha az új alapra helyezést vissza szeretné vonni, válassza ki a **BACS (UK egyéni)** formátum **1.1.1**-es verzióját a **Verziók** gyorslapon, majd válassza ki a **Verzió beszerzése** elemet.</span><span class="sxs-lookup"><span data-stu-id="87124-426">To cancel this rebase, select version **1.1.1** of the **BACS (UK custom)** format on the **Versions** FastTab, and then select **Get this version**.</span></span> <span data-ttu-id="87124-427">A 3.3.2-es verziót ezután a rendszer 1.1.2-esként számozza fel, és az 1.1.2-es piszkozat verzió tartalma megegyezik a 1.1.1-es verzió tartalmával.</span><span class="sxs-lookup"><span data-stu-id="87124-427">Version 3.3.2 will then be renumbered 1.1.2, and the content of draft version 1.1.2 will match the content of version 1.1.1.</span></span>

### <a name="process-a-vendor-payment-by-using-a-rebased-er-format"></a><a id="ProcessPayment3"></a><span data-ttu-id="87124-428">Szállítói kifizetés feldolgozása egy új alapra helyezett ER-formátum használatával</span><span class="sxs-lookup"><span data-stu-id="87124-428">Process a vendor payment by using a rebased ER format</span></span>

1. <span data-ttu-id="87124-429">Ugorjon a **Kötelezettségek** \> **Fizetések** \> **Szállítói kifizetés naplója** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="87124-429">Go to **Accounts payable** \> **Payments** \> **Vendor payment journal**.</span></span>
2. <span data-ttu-id="87124-430">A **Szállítói fizetési napló** lapon válassza ki a korábban létrehozott fizetési naplót.</span><span class="sxs-lookup"><span data-stu-id="87124-430">On the **Vendor payment journal** page, select the payment journal that you created earlier.</span></span>
3. <span data-ttu-id="87124-431">**Sorok** kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="87124-431">Select **Lines**.</span></span>
4. <span data-ttu-id="87124-432">A **Szállítói kifizetések** oldalon, a rács felett válassza a **Kifizetési állapot** \> **Nincs** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87124-432">On the **Vendor payments** page, above the grid, select **Payment status** \> **None**.</span></span>
5. <span data-ttu-id="87124-433">Válassza a **Fizetés létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87124-433">Select **Generate payment**.</span></span>
6. <span data-ttu-id="87124-434">A **Kifizetések létrehozása** párbeszédpanelen adja meg a következő adatokat:</span><span class="sxs-lookup"><span data-stu-id="87124-434">In the **Generate payments** dialog box, enter the following information:</span></span>

    - <span data-ttu-id="87124-435">A **Fizetési mód** mezőben válassza az **Elektronikus** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87124-435">In the **Method of payment** field, select **Electronic**.</span></span>
    - <span data-ttu-id="87124-436">A **Bankszámla** mezőben válassza a **GBSI OPER** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87124-436">In the **Bank account** field, select **GBSI OPER**.</span></span>

7. <span data-ttu-id="87124-437">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87124-437">Select **OK**.</span></span>
8. <span data-ttu-id="87124-438">Az **Elektronikus jelentés paraméterei** párbeszédpanelen adja meg a következő adatokat:</span><span class="sxs-lookup"><span data-stu-id="87124-438">In the **Electronic report parameters** dialog box, enter the following information:</span></span>

    - <span data-ttu-id="87124-439">Állítsa az **Ellenőrzési jelentés nyomtatása** opciót **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="87124-439">Set the **Print control report** option to **Yes**.</span></span>
    - <span data-ttu-id="87124-440">Állítsa az **Kifizetési bizonylat nyomtatása** opciót **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="87124-440">Set the **Print payment advice** option to **Yes**.</span></span>

    ![Elektronikus jelentés paraméterei – párbeszédablak](./media/er-quick-start2-payment-dialog2.png)

    > [!NOTE]
    > <span data-ttu-id="87124-442">A kifizetési fájlon kívül már az ellenőrzési jelentés és a kifizetési bizonylat jelentés is létrehozható.</span><span class="sxs-lookup"><span data-stu-id="87124-442">In addition to the payment file, you can now generate both the control report and the payment advice report.</span></span>

9. <span data-ttu-id="87124-443">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="87124-443">Select **OK**.</span></span>
10. <span data-ttu-id="87124-444">Töltse le a zip-fájlt, majd csomagolja ki belőle a következő fájlokat:</span><span class="sxs-lookup"><span data-stu-id="87124-444">Download the zip file, and then extract the following files from it:</span></span>

    - <span data-ttu-id="87124-445">Az ellenőrzési jelentést Excel-formátumban</span><span class="sxs-lookup"><span data-stu-id="87124-445">The control report in Excel format</span></span>
    - <span data-ttu-id="87124-446">Az kifizetési bizonylat jelentést Excel-formátumban</span><span class="sxs-lookup"><span data-stu-id="87124-446">The payment advice report in Excel format</span></span>

        ![Kifizetési bizonylat jelentést Excel-formátumban](./media/er-quick-start2-payment-advice-report.png)

    - <span data-ttu-id="87124-448">A fizetési fájl TXT-formátumban</span><span class="sxs-lookup"><span data-stu-id="87124-448">The payment file in TXT format</span></span>

        <span data-ttu-id="87124-449">Figyelje meg, hogy a létrehozott fájl kifizetési sora azzal a SWIFT-kóddal kezdődik, amelyet azon szállító bankszámláján rögzítettek, amelynek a kifizetését már feldolgozták.</span><span class="sxs-lookup"><span data-stu-id="87124-449">Notice that the payment line in the generated file starts  with the SWIFT code that was entered for the bank account of a vendor whose payment has been processed.</span></span>

        ![Fizetési fájl TXT-formátum](./media/er-quick-start2-payment-file3.png)

## <a name="additional-resources"></a><a id="References"></a><span data-ttu-id="87124-451">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="87124-451">Additional resources</span></span>

- [<span data-ttu-id="87124-452">Elektronikus jelentések áttekintése</span><span class="sxs-lookup"><span data-stu-id="87124-452">Electronic Reporting overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="87124-453">ER-konfigurációk letöltése a Lifecycle Services szolgáltatásból</span><span class="sxs-lookup"><span data-stu-id="87124-453">Download ER configurations from Lifecycle Services</span></span>](download-electronic-reporting-configuration-lcs.md)
- [<span data-ttu-id="87124-454">ER-konfigurációk letöltése a konfigurációs szolgáltatás globális tárából</span><span class="sxs-lookup"><span data-stu-id="87124-454">Download ER configurations from Global repository of Configuration service</span></span>](er-download-configurations-global-repo.md)
