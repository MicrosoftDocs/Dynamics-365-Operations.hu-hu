---
title: Alapadat-keresés környezetének beállítása
description: Ez a témakör bemutatja, hogy hogyan lehet beállítani a környezetet az adószámítási alapadat-keresési funkció használatához.
author: kai-cloud
ms.date: 04/21/2021
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
ms.author: pashao
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 9f9b385df1db60b27698d90281c43fabb574af49
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924154"
---
# <a name="set-up-an-environment-for-master-data-lookup"></a><span data-ttu-id="db8c2-103">Alapadat-keresés környezetének beállítása</span><span class="sxs-lookup"><span data-stu-id="db8c2-103">Set up an environment for master data lookup</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="db8c2-104">Ez a témakör bemutatja, hogy hogyan lehet beállítani a környezetet az adószámítási alapadat-keresési funkció használatához.</span><span class="sxs-lookup"><span data-stu-id="db8c2-104">This topic explains how to set up your environment to use the Tax Calculation master data lookup functionality.</span></span>

1. <span data-ttu-id="db8c2-105">A Power Platform integráció beállítása a Lifecycle Services (LCS) szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="db8c2-105">Set up power platform integration in Lifecycle Services (LCS).</span></span> <span data-ttu-id="db8c2-106">További informáciért lásd: [Microsoft Power Platform integráció – Bővítmények áttekintése](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).</span><span class="sxs-lookup"><span data-stu-id="db8c2-106">For more information, see [Microsoft Power Platform integration - Add-ins overview](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).</span></span>
2. <span data-ttu-id="db8c2-107">Dynamics 365 Finance és Microsoft Dataverse beállítása.</span><span class="sxs-lookup"><span data-stu-id="db8c2-107">Set up Dynamics 365 Finance and Microsoft Dataverse.</span></span> <span data-ttu-id="db8c2-108">A további tudnivalókat lásd [A megoldás beszerzése](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#getting-the-solution), valamint [Hitelesítés és engedélyezés ](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#authentication-and-authorization).</span><span class="sxs-lookup"><span data-stu-id="db8c2-108">For more information, see [Getting the solution](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#getting-the-solution) and [Authentication and authorization](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#authentication-and-authorization).</span></span>
3. <span data-ttu-id="db8c2-109">Állítsa be a következő entitásokat:</span><span class="sxs-lookup"><span data-stu-id="db8c2-109">Set up the following entities.</span></span> <span data-ttu-id="db8c2-110">További tudnivalókért lásd: [Virtuális entitások engedélyezése](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#enabling-virtual-entities).</span><span class="sxs-lookup"><span data-stu-id="db8c2-110">For more information, see [Enabling virtual entities](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#enabling-virtual-entities).</span></span>
      - <span data-ttu-id="db8c2-111">CompanyInfoEntity</span><span class="sxs-lookup"><span data-stu-id="db8c2-111">CompanyInfoEntity</span></span>
      - <span data-ttu-id="db8c2-112">CurrencyEntity</span><span class="sxs-lookup"><span data-stu-id="db8c2-112">CurrencyEntity</span></span>
      - <span data-ttu-id="db8c2-113">CustCustomerV3Entity</span><span class="sxs-lookup"><span data-stu-id="db8c2-113">CustCustomerV3Entity</span></span>
      - <span data-ttu-id="db8c2-114">DeliveryTermsEntity</span><span class="sxs-lookup"><span data-stu-id="db8c2-114">DeliveryTermsEntity</span></span>
      - <span data-ttu-id="db8c2-115">EcoResProductCategoryEntity</span><span class="sxs-lookup"><span data-stu-id="db8c2-115">EcoResProductCategoryEntity</span></span>
      - <span data-ttu-id="db8c2-116">EcoResReleasedProductV2Entity</span><span class="sxs-lookup"><span data-stu-id="db8c2-116">EcoResReleasedProductV2Entity</span></span>
      - <span data-ttu-id="db8c2-117">LogisticsAddressCityEntity</span><span class="sxs-lookup"><span data-stu-id="db8c2-117">LogisticsAddressCityEntity</span></span>
      - <span data-ttu-id="db8c2-118">LogisticsAddressCountryRegionTranslationEntity</span><span class="sxs-lookup"><span data-stu-id="db8c2-118">LogisticsAddressCountryRegionTranslationEntity</span></span>
      - <span data-ttu-id="db8c2-119">LogisticsAddressStateEntity</span><span class="sxs-lookup"><span data-stu-id="db8c2-119">LogisticsAddressStateEntity</span></span>
      - <span data-ttu-id="db8c2-120">PurchProcurementChargeCDSEntity</span><span class="sxs-lookup"><span data-stu-id="db8c2-120">PurchProcurementChargeCDSEntity</span></span>
      - <span data-ttu-id="db8c2-121">SalesChargeCDSEntity</span><span class="sxs-lookup"><span data-stu-id="db8c2-121">SalesChargeCDSEntity</span></span>
      - <span data-ttu-id="db8c2-122">TaxGroupEntity</span><span class="sxs-lookup"><span data-stu-id="db8c2-122">TaxGroupEntity</span></span>
      - <span data-ttu-id="db8c2-123">TaxItemGroupHeadingEntity</span><span class="sxs-lookup"><span data-stu-id="db8c2-123">TaxItemGroupHeadingEntity</span></span>
      - <span data-ttu-id="db8c2-124">VendVendorV2Entity</span><span class="sxs-lookup"><span data-stu-id="db8c2-124">VendVendorV2Entity</span></span>
4. <span data-ttu-id="db8c2-125">A Dynamics 365 Regulatory Configuration Service (RCS) beállítása.</span><span class="sxs-lookup"><span data-stu-id="db8c2-125">Set up the Dynamics 365 Regulatory Configuration Service (RCS).</span></span> 
5. <span data-ttu-id="db8c2-126">Szolgáltatáskérés létrehozása a Microsoft számára a következő funkciók tesztelésének engedélyezéséhez:</span><span class="sxs-lookup"><span data-stu-id="db8c2-126">Create a service request for Microsoft to enable flighting of the following features:</span></span>

      - <span data-ttu-id="db8c2-127">ERCdsFeature</span><span class="sxs-lookup"><span data-stu-id="db8c2-127">ERCdsFeature</span></span>
      - <span data-ttu-id="db8c2-128">TaxServiceCDSFeature</span><span class="sxs-lookup"><span data-stu-id="db8c2-128">TaxServiceCDSFeature</span></span>

6. <span data-ttu-id="db8c2-129">A **Funkció kezelése** munkaterületen engedélyezze a következő funkciókat:</span><span class="sxs-lookup"><span data-stu-id="db8c2-129">Go to the **Feature management** workspace, and enable the following features:</span></span>

      - <span data-ttu-id="db8c2-130">(Előnézet) Elektronikus jelentés Dataverse-adatforrások támogatása</span><span class="sxs-lookup"><span data-stu-id="db8c2-130">(Preview) Electronic reporting Dataverse datasources support</span></span>
      - <span data-ttu-id="db8c2-131">(Előzetes verzió) Adószolgáltatás Dataverse-adatforrásainak támogatása</span><span class="sxs-lookup"><span data-stu-id="db8c2-131">(Preview) Tax Service Dataverse datasources support</span></span>
      - <span data-ttu-id="db8c2-132">(előzetes verzió) Globalizációs funkciók</span><span class="sxs-lookup"><span data-stu-id="db8c2-132">(Preview) Globalization features</span></span>

5. <span data-ttu-id="db8c2-133">Jelentkezzen be az RCS-be bérlői rendszergazdai fiók használatával.</span><span class="sxs-lookup"><span data-stu-id="db8c2-133">Sign in to RCS using a tenant admin account.</span></span>
6. <span data-ttu-id="db8c2-134">Ugrás az **Elektronikus jelentéskészítés** > **Kapcsolódó alkalmazások** elemhez.</span><span class="sxs-lookup"><span data-stu-id="db8c2-134">Go to **Electronic reporting** > **Connected applications**.</span></span> 
7. <span data-ttu-id="db8c2-135">Rekord hozzáadásához válassza az **Új** lehetőséget, és adja meg a következő mezőadatokat.</span><span class="sxs-lookup"><span data-stu-id="db8c2-135">Select **New** to add a record, and enter the following field information.</span></span> 

   - <span data-ttu-id="db8c2-136">A **Név** mezőben adjon meg egy nevet.</span><span class="sxs-lookup"><span data-stu-id="db8c2-136">In the **Name** field, enter a name.</span></span>
   - <span data-ttu-id="db8c2-137">A **Típus** mezőben válassza ki a **Dataverse** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="db8c2-137">In the **Type** field, select **Dataverse**.</span></span>
   - <span data-ttu-id="db8c2-138">Az **Alkalmazás** mezőbe írja az Dataverse URL-címét.</span><span class="sxs-lookup"><span data-stu-id="db8c2-138">In the **Application** field, enter your Dataverse URL.</span></span>
   - <span data-ttu-id="db8c2-139">A **Bérlő** mezőben adja meg a bérlőt.</span><span class="sxs-lookup"><span data-stu-id="db8c2-139">In the **Tenant** field, enter your tenant.</span></span>
   - <span data-ttu-id="db8c2-140">Az **Egyéni URL-cím** mezőben adja meg az Dataverse URL-címet, és fűzze hozzá az "/api/data/v9.1" szöveghez.</span><span class="sxs-lookup"><span data-stu-id="db8c2-140">In the **Custom URL** field, enter your Dataverse URL and append it with "/api/data/v9.1".</span></span>

8. <span data-ttu-id="db8c2-141">Válassza a **Kapcsolat ellenőrzése** lehetőséget, és fejezze be a kapcsolódási folyamatot.</span><span class="sxs-lookup"><span data-stu-id="db8c2-141">Select **Check connection**, and finish the connection process.</span></span> 

   <span data-ttu-id="db8c2-142">[![Kapcsolat ellenőrzése gomb](./media/tax-service-setup-environment-for-mater-date-pic1.png)](./media/tax-service-setup-environment-for-mater-date-pic1.png)</span><span class="sxs-lookup"><span data-stu-id="db8c2-142">[![Check connection button](./media/tax-service-setup-environment-for-mater-date-pic1.png)](./media/tax-service-setup-environment-for-mater-date-pic1.png)</span></span>

9. <span data-ttu-id="db8c2-143">Ugrás az **Elektronikus jelentés** > **Adókonfigurációk** elemhez, és importálja az adókonfigurációkat az [Adókonfigurációk](https://go.microsoft.com/fwlink/?linkid=2158352) elemből.</span><span class="sxs-lookup"><span data-stu-id="db8c2-143">Go to **Electronic reporting** > **Tax configurations**, and import tax configurations from [Tax configurations](https://go.microsoft.com/fwlink/?linkid=2158352).</span></span>

   <span data-ttu-id="db8c2-144">[![Adókonfigurációs oldal, adóadatmodellfa](./media/tax-service-setup-environment-for-mater-date-pic2.png)](./media/tax-service-setup-environment-for-mater-date-pic2.png)</span><span class="sxs-lookup"><span data-stu-id="db8c2-144">[![Tax configurations page, Tax data model tree](./media/tax-service-setup-environment-for-mater-date-pic2.png)](./media/tax-service-setup-environment-for-mater-date-pic2.png)</span></span>

10. <span data-ttu-id="db8c2-145">Ha Microsoft-konfigurációt használ, lépjen az **Adóköteles dokumentummodell-hozzárendelés** vagy a **Dataverse modellleképezés** elemhez, és a **Kapcsolódó alkalmazás** mezőben válassza ki a 7. lépésben létrehozott rekordot.</span><span class="sxs-lookup"><span data-stu-id="db8c2-145">Go to the **Taxable document model mapping**, or **Dataverse Model Mapping** if you are using a Microsoft configuration, and in the **Connected application** field, select the record that you created in step 7.</span></span>
11. <span data-ttu-id="db8c2-146">Állítsa az **Alapértelmezett modell-hozzárendelés** beállítást **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="db8c2-146">Set **Default for model mapping** to **Yes**.</span></span>

   <span data-ttu-id="db8c2-147">[![Modell-leképezés oldal](./media/tax-service-setup-environment-for-mater-date-pic3.png)](./media/tax-service-setup-environment-for-mater-date-pic3.png)</span><span class="sxs-lookup"><span data-stu-id="db8c2-147">[![Model mapping page](./media/tax-service-setup-environment-for-mater-date-pic3.png)](./media/tax-service-setup-environment-for-mater-date-pic3.png)</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
