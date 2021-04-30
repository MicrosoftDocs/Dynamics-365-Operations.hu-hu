---
title: Alapadat-keresés környezetének beállítása
description: Ez a témakör bemutatja, hogy hogyan lehet beállítani a környezetet az adószámítási alapadat-keresési funkció használatához.
author: kai-cloud
ms.date: 03/31/2021
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
ms.openlocfilehash: eda093a75898bace2f3c7968933b83ccafa7fabb
ms.sourcegitcommit: 66095f1b7e0fd2756aa29fd7deb9ce5392b7e0b2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/08/2021
ms.locfileid: "5869070"
---
# <a name="set-up-an-environment-for-master-data-lookup"></a><span data-ttu-id="ac4e2-103">Alapadat-keresés környezetének beállítása</span><span class="sxs-lookup"><span data-stu-id="ac4e2-103">Set up an environment for master data lookup</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="ac4e2-104">Ez a témakör bemutatja, hogy hogyan lehet beállítani a környezetet az adószámítási alapadat-keresési funkció használatához.</span><span class="sxs-lookup"><span data-stu-id="ac4e2-104">This topic explains how to set up your environment to use the Tax Calculation master data lookup functionality.</span></span>

1. <span data-ttu-id="ac4e2-105">A Power Platform integráció beállítása a Lifecycle Services (LCS) szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="ac4e2-105">Set up power platform integration in Lifecycle Services (LCS).</span></span> <span data-ttu-id="ac4e2-106">További informáciért lásd: [Microsoft Power Platform integráció – Bővítmények áttekintése](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ac4e2-106">For more information, see [Microsoft Power Platform integration - Add-ins overview](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).</span></span>
2. <span data-ttu-id="ac4e2-107">Dynamics 365 Finance és Microsoft Dataverse beállítása.</span><span class="sxs-lookup"><span data-stu-id="ac4e2-107">Set up Dynamics 365 Finance and Microsoft Dataverse.</span></span> <span data-ttu-id="ac4e2-108">A további tudnivalókat lásd [A megoldás beszerzése](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#getting-the-solution), valamint [Hitelesítés és engedélyezés ](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#authentication-and-authorization).</span><span class="sxs-lookup"><span data-stu-id="ac4e2-108">For more information, see [Getting the solution](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#getting-the-solution) and [Authentication and authorization](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#authentication-and-authorization).</span></span>
3. <span data-ttu-id="ac4e2-109">Importálja az *Előfeltétel-adó szolgáltatás virtuális entitás megoldást* az [Adószolgáltatás virtuális entitásból](https://go.microsoft.com/fwlink/?linkid=2158160).</span><span class="sxs-lookup"><span data-stu-id="ac4e2-109">Import the *Prerequisite tax service virtual entity solution* from the [Tax service virtual entity](https://go.microsoft.com/fwlink/?linkid=2158160).</span></span>
4. <span data-ttu-id="ac4e2-110">A Dynamics 365 Regulatory Configuration Service (RCS) beállítása.</span><span class="sxs-lookup"><span data-stu-id="ac4e2-110">Set up the Dynamics 365 Regulatory Configuration Service (RCS).</span></span> 
5. <span data-ttu-id="ac4e2-111">Szolgáltatáskérés létrehozása a Microsoft számára a következő funkciók tesztelésének engedélyezéséhez:</span><span class="sxs-lookup"><span data-stu-id="ac4e2-111">Create a service request for Microsoft to enable flighting of the following features:</span></span>

      - <span data-ttu-id="ac4e2-112">ERCdsFeature</span><span class="sxs-lookup"><span data-stu-id="ac4e2-112">ERCdsFeature</span></span>
      - <span data-ttu-id="ac4e2-113">TaxServiceCDSFeature</span><span class="sxs-lookup"><span data-stu-id="ac4e2-113">TaxServiceCDSFeature</span></span>

6. <span data-ttu-id="ac4e2-114">Engedélyezze a következő funkciót a **Funkció kezelése** munkaterületen a Finance megoldásban:</span><span class="sxs-lookup"><span data-stu-id="ac4e2-114">In Finance, go to the **Feature management** workspace, and enable the following features:</span></span>

      - <span data-ttu-id="ac4e2-115">(Előnézet) Elektronikus jelentés Dataverse-adatforrások támogatása</span><span class="sxs-lookup"><span data-stu-id="ac4e2-115">(Preview) Electronic reporting Dataverse datasources support</span></span>
      - <span data-ttu-id="ac4e2-116">(Előzetes verzió) Adószolgáltatás Dataverse-adatforrásainak támogatása</span><span class="sxs-lookup"><span data-stu-id="ac4e2-116">(Preview) Tax Service Dataverse datasources support</span></span>
      - <span data-ttu-id="ac4e2-117">(előzetes verzió) Globalizációs funkciók</span><span class="sxs-lookup"><span data-stu-id="ac4e2-117">(Preview) Globalization features</span></span>

5. <span data-ttu-id="ac4e2-118">Jelentkezzen be az RCS-be bérlői rendszergazdai fiók használatával.</span><span class="sxs-lookup"><span data-stu-id="ac4e2-118">Sign in to RCS using a tenant admin account.</span></span>
6. <span data-ttu-id="ac4e2-119">Ugrás az **Elektronikus jelentéskészítés** > **Kapcsolódó alkalmazások** elemhez.</span><span class="sxs-lookup"><span data-stu-id="ac4e2-119">Go to **Electronic reporting** > **Connected applications**.</span></span> 
7. <span data-ttu-id="ac4e2-120">Rekord hozzáadásához válassza az **Új** lehetőséget, és adja meg a következő mezőadatokat.</span><span class="sxs-lookup"><span data-stu-id="ac4e2-120">Select **New** to add a record, and enter the following field information.</span></span> 

   - <span data-ttu-id="ac4e2-121">A **Név** mezőben adjon meg egy nevet.</span><span class="sxs-lookup"><span data-stu-id="ac4e2-121">In the **Name** field, enter a name.</span></span>
   - <span data-ttu-id="ac4e2-122">A **Típus** mezőben válassza ki a **Dataverse** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ac4e2-122">In the **Type** field, select **Dataverse**.</span></span>
   - <span data-ttu-id="ac4e2-123">Az **Alkalmazás** mezőbe írja az Dataverse URL-címét.</span><span class="sxs-lookup"><span data-stu-id="ac4e2-123">In the **Application** field, enter your Dataverse URL.</span></span>
   - <span data-ttu-id="ac4e2-124">A **Bérlő** mezőben adja meg a bérlőt.</span><span class="sxs-lookup"><span data-stu-id="ac4e2-124">In the **Tenant** field, enter your tenant.</span></span>
   - <span data-ttu-id="ac4e2-125">Az **Egyéni URL-cím** mezőben adja meg az Dataverse URL-címet, és fűzze hozzá az "/api/data/v9.1" szöveghez.</span><span class="sxs-lookup"><span data-stu-id="ac4e2-125">In the **Custom URL** field, enter your Dataverse URL and append it with "/api/data/v9.1".</span></span>

8. <span data-ttu-id="ac4e2-126">Válassza a **Kapcsolat ellenőrzése** lehetőséget, és fejezze be a kapcsolódási folyamatot.</span><span class="sxs-lookup"><span data-stu-id="ac4e2-126">Select **Check connection**, and finish the connection process.</span></span> 

   <span data-ttu-id="ac4e2-127">[![Kapcsolat ellenőrzése gomb](./media/tax-service-setup-environment-for-mater-date-pic1.png)](./media/tax-service-setup-environment-for-mater-date-pic1.png)</span><span class="sxs-lookup"><span data-stu-id="ac4e2-127">[![Check connection button](./media/tax-service-setup-environment-for-mater-date-pic1.png)](./media/tax-service-setup-environment-for-mater-date-pic1.png)</span></span>

9. <span data-ttu-id="ac4e2-128">Ugrás az **Elektronikus jelentés** > **Adókonfigurációk** elemhez, és importálja az adókonfigurációkat az [Adókonfigurációk](https://go.microsoft.com/fwlink/?linkid=2158352) elemből.</span><span class="sxs-lookup"><span data-stu-id="ac4e2-128">Go to **Electronic reporting** > **Tax configurations**, and import tax configurations from [Tax configurations](https://go.microsoft.com/fwlink/?linkid=2158352).</span></span>

   <span data-ttu-id="ac4e2-129">[![Adókonfigurációs oldal, adóadatmodellfa](./media/tax-service-setup-environment-for-mater-date-pic2.png)](./media/tax-service-setup-environment-for-mater-date-pic2.png)</span><span class="sxs-lookup"><span data-stu-id="ac4e2-129">[![Tax configurations page, Tax data model tree](./media/tax-service-setup-environment-for-mater-date-pic2.png)](./media/tax-service-setup-environment-for-mater-date-pic2.png)</span></span>

10. <span data-ttu-id="ac4e2-130">Ha Microsoft-konfigurációt használ, lépjen az **Adóköteles dokumentummodell-hozzárendelés** vagy a **Dataverse modellleképezés** elemhez, és a **Kapcsolódó alkalmazás** mezőben válassza ki a 7. lépésben létrehozott rekordot.</span><span class="sxs-lookup"><span data-stu-id="ac4e2-130">Go to the **Taxable document model mapping**, or **Dataverse Model Mapping** if you are using a Microsoft configuration, and in the **Connected application** field, select the record that you created in step 7.</span></span>
11. <span data-ttu-id="ac4e2-131">Állítsa az **Alapértelmezett modell-hozzárendelés** beállítást **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="ac4e2-131">Set **Default for model mapping** to **Yes**.</span></span>

   <span data-ttu-id="ac4e2-132">[![Modell-leképezés oldal](./media/tax-service-setup-environment-for-mater-date-pic3.png)](./media/tax-service-setup-environment-for-mater-date-pic3.png)</span><span class="sxs-lookup"><span data-stu-id="ac4e2-132">[![Model mapping page](./media/tax-service-setup-environment-for-mater-date-pic3.png)](./media/tax-service-setup-environment-for-mater-date-pic3.png)</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
