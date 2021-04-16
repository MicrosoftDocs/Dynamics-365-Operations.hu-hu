---
title: Adatmezők hozzáadása adókonfigurációkhoz
description: Ez a témakör az adókonfigurációk adatmezők hozzáadásával való testreszabását ismerteti.
author: kailiang
ms.date: 03/25/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: b9d9fce81151ad70d57c69e389e238a6f9137d56
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5819424"
---
# <a name="add-data-fields-in-tax-configurations"></a><span data-ttu-id="02e8b-103">Adatmezők hozzáadása adókonfigurációkhoz</span><span class="sxs-lookup"><span data-stu-id="02e8b-103">Add data fields in tax configurations</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="02e8b-104">Ez a témakör ismerteti az adókonfigurációk testreszabását az [adóintegrációban hozzáadott adatmezők használatával](tax-service-add-data-fields-tax-integration-by-extension.md).</span><span class="sxs-lookup"><span data-stu-id="02e8b-104">This topic explains how to customize tax configurations by using [data fields that are added in the tax integration](tax-service-add-data-fields-tax-integration-by-extension.md).</span></span>

## <a name="customize-the-tax-data-model"></a><span data-ttu-id="02e8b-105">Az adóadatmodell konfigurációjának testreszabása</span><span class="sxs-lookup"><span data-stu-id="02e8b-105">Customize the tax data model</span></span>

1. <span data-ttu-id="02e8b-106">A Microsoft Dynamics 365 Finance alkalmazásban nyissa meg az **Elektronikus jelentéskészítés** \> **Konfigurációk** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="02e8b-106">In Microsoft Dynamics 365 Finance, go to **Electronic Reporting** \> **Tax configurations**.</span></span>
2. <span data-ttu-id="02e8b-107">A konfigurációs fán válassza az **Adóadat-modell - Európa** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="02e8b-107">In the configuration tree, select **Tax Data Model - Europe**.</span></span> <span data-ttu-id="02e8b-108">Majd a Műveleti ablaktáblán kattintson a **Konfiguráció létrehozása** elemre.</span><span class="sxs-lookup"><span data-stu-id="02e8b-108">Then, on the Action Pane, select **Create configuration**.</span></span>
3. <span data-ttu-id="02e8b-109">A legördülő párbeszédpanelen jelölje ki az **Adóköteles dokumentummodell származtatva névből: Adóadatmodell - Európa** lehetőséget, írja be az új adóadatmodell nevét, majd válassza a **Konfiguráció létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="02e8b-109">In the drop-down dialog box, select the **Taxable document model derived from Name: Tax Data Model -- Europe, Microsoft** option, enter a name for the new tax data model, and then select **Create configuration**.</span></span>
4. <span data-ttu-id="02e8b-110">Jelölje ki az éppen létrehozott adóadatmodellt, majd a Műveleti panelen válassza a **Tervező** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="02e8b-110">Select the tax data model that you just created, and then, on the Action Pane, select **Designer**.</span></span>
5. <span data-ttu-id="02e8b-111">Bontsa ki az adatmodellfát, válassza a **Sorok** lehetőséget, majd válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="02e8b-111">Expand the data model tree, select **Lines**, and then select **New**.</span></span>
6. <span data-ttu-id="02e8b-112">A **Csomópont létrehozása** párbeszédpanelen adjon meg egy nevet, adja meg az elemtípust, majd válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="02e8b-112">In the **Create node** dialog box, enter a name, specify the item type, and then select **Add**.</span></span>
7. <span data-ttu-id="02e8b-113">Adja hozzá a szükséges oszlopokat.</span><span class="sxs-lookup"><span data-stu-id="02e8b-113">Add any required columns.</span></span>
8. <span data-ttu-id="02e8b-114">Válassza a Művelet panel **Mentés** elemét, majd válassza az **Befejezés** elemet.</span><span class="sxs-lookup"><span data-stu-id="02e8b-114">On the Action Pane, select **Save**, and then select **Complete**.</span></span>
9. <span data-ttu-id="02e8b-115">Zárja be a lapot, és tekintse meg az adóadat-modell befejezett verzióját.</span><span class="sxs-lookup"><span data-stu-id="02e8b-115">Close the page, and view the completed version of your tax data model.</span></span>

## <a name="customize-the-tax-configuration"></a><span data-ttu-id="02e8b-116">Az adókonfiguráció testreszabása</span><span class="sxs-lookup"><span data-stu-id="02e8b-116">Customize the tax configuration</span></span>

1. <span data-ttu-id="02e8b-117">A Finance alkalmazásban nyissa meg az **Elektronikus jelentéskészítés** \> **Konfigurációk** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="02e8b-117">In Finance, go to **Electronic reporting** \> **Tax configurations**.</span></span>
2. <span data-ttu-id="02e8b-118">A konfigurációs fán válassza az **Adókonfiguráció - Európa** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="02e8b-118">In the configuration tree, select **Tax Configuration -- Europe**.</span></span> <span data-ttu-id="02e8b-119">Majd a Műveleti ablaktáblán kattintson a **Konfiguráció létrehozása** elemre.</span><span class="sxs-lookup"><span data-stu-id="02e8b-119">Then, on the Action Pane, select **Create configuration**.</span></span>
3. <span data-ttu-id="02e8b-120">A legördülő párbeszédpanelen jelölje ki az **Adószolgáltatás-konfiguráció származtatva névből: Adókonfiguráció - Európa** lehetőséget, írja be az új adókonfiguráció nevét, majd válassza a **Konfiguráció létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="02e8b-120">In the drop-down dialog box, select the **Tax service configuration derived from Name: Tax Configuration -- Europe, Microsoft** option, enter a name for the new tax configuration, and then select **Create configuration**.</span></span>
4. <span data-ttu-id="02e8b-121">Jelölje ki az éppen létrehozott adókonfigurációt, majd a Műveleti panelen válassza a **Tervező** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="02e8b-121">Select the tax configuration that you just created, and then, on the Action Pane, select **Designer**.</span></span>
5. <span data-ttu-id="02e8b-122">A **Tulajdonságok** szakaszban az **Adatmodell** mezőben válassza ki a korábban létrehozott testreszabott adó-adatmodellt.</span><span class="sxs-lookup"><span data-stu-id="02e8b-122">In the **Properties** section, in the **Data model** field, select the customized tax data model that you created earlier.</span></span>
6. <span data-ttu-id="02e8b-123">Az **Adatmodell verzió** mezőben válassza ki az adóadat-modell kész verzióját.</span><span class="sxs-lookup"><span data-stu-id="02e8b-123">In the **Data model version** field, select the completed version of the tax data model.</span></span>
7. <span data-ttu-id="02e8b-124">Válassza a **Hozzáadás** lehetőséget, és adja hozzá a szükséges adóintézkedéseket.</span><span class="sxs-lookup"><span data-stu-id="02e8b-124">Select **Add**, and add the required tax measures.</span></span>
8. <span data-ttu-id="02e8b-125">Válassza a Művelet panel **Mentés** elemét, majd válassza az **Befejezés** elemet.</span><span class="sxs-lookup"><span data-stu-id="02e8b-125">On the Action Pane, select **Save**, and then select **Complete**.</span></span>
9. <span data-ttu-id="02e8b-126">Zárja be a lapot, és tekintse meg az adóadatkonfiguráció befejezett verzióját.</span><span class="sxs-lookup"><span data-stu-id="02e8b-126">Close page, and view the completed version of your tax configuration.</span></span>

## <a name="implement-tax-features-in-the-customized-tax-configuration"></a><span data-ttu-id="02e8b-127">Adófunkciók implementása a testreszabott adókonfigurációban</span><span class="sxs-lookup"><span data-stu-id="02e8b-127">Implement tax features in the customized tax configuration</span></span>

1. <span data-ttu-id="02e8b-128">A Regulatory Configuration Services (RCS) szolgáltatásban nyissa meg a **Globalizációs funkciók** \> **Adó** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="02e8b-128">In Regulatory Configuration Service (RCS), go to **Globalization Features** \> **Tax**.</span></span>
2. <span data-ttu-id="02e8b-129">Válassza a **Hozzáadás** lehetőséget, írja be az új funkció adatait, majd válassza a **Funkció létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="02e8b-129">Select **Add**, enter information about the new feature, and then select **Create feature**.</span></span>
3. <span data-ttu-id="02e8b-130">A **Verziók** lapon válassza ki a funkciót, majd kattintson a **Szerkesztés** gombra.</span><span class="sxs-lookup"><span data-stu-id="02e8b-130">On the **Versions** tab, select the feature, and then select **Edit**.</span></span>
4. <span data-ttu-id="02e8b-131">Az **Általános** lap **Konfigurációs verzió** mezőjében jelölje ki a testreszabott adókonfigurációt és -verziót.</span><span class="sxs-lookup"><span data-stu-id="02e8b-131">On the **General** tab, in the **Configuration version** field, select the customized tax configuration and version.</span></span>
5. <span data-ttu-id="02e8b-132">Az **Oszlopok kezelése** párbeszédpanelen jelölje ki a testreszabott adómértékbe felvenni kívánt fejléc- és soroszlopokat, majd a megfelelő nyílgombot válassza a **Kijelölt oszlopok** listájához való hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="02e8b-132">In the **Manage columns** dialog box, select the header and line columns that you want to include in your customized tax measure, and then select the right arrow button to add them to the **Selected columns** list.</span></span>
