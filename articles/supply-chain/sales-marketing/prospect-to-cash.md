---
title: "A potenciális ügyfelek készpénzre váltása"
description: "Ez a témakör áttekintést nyújt A potenciális ügyfelek készpénzre váltása megoldásról a Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition és a Microsoft Dynamics 365 for Sales szolgáltatásokban."
author: ChristianRytt
manager: AnnBe
ms.date: 02/08/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustTable, SalesTable, EcoResProductListPage
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 1f76359878d162e93d8f8b7c11be529c43c94455
ms.openlocfilehash: 9b150bfca362303b4ac35a38ab818229082c7330
ms.contentlocale: hu-hu
ms.lasthandoff: 02/08/2018

---

# <a name="prospect-to-cash"></a><span data-ttu-id="9b4e8-103">A potenciális ügyfelek készpénzre váltása</span><span class="sxs-lookup"><span data-stu-id="9b4e8-103">Prospect to cash</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="9b4e8-104">A potenciális ügyfelek készpénzre váltása megoldás közvetlen szinkronizálást biztosít a Dynamics 365 for Finance and Operations, Enterprise Edition és a Dynamics 365 for Sales között.</span><span class="sxs-lookup"><span data-stu-id="9b4e8-104">The Prospect to cash solution provides direct synchronization across Dynamics 365 for Finance and Operations, Enterprise edition, and Dynamics 365 for Sales.</span></span> <span data-ttu-id="9b4e8-105">Az Adatintegrációs szolgáltatásban rendelkezésre álló A potenciális ügyfelek készpénzre váltása sablonok lehetővé teszik a termék-, ügyfél-, kapcsolatfelvételi és eladási számlákra vonatkozó adatok áramlását a Finance and Operations és a Sales között.</span><span class="sxs-lookup"><span data-stu-id="9b4e8-105">The Prospect to cash templates that are available with the Data Integration feature enable the flow of data for accounts, contacts, products, sales quotations, sales orders, and sales invoices between Finance and Operations and Sales.</span></span> <span data-ttu-id="9b4e8-106">Miközben az adatok áramlanak a Finance and Operations és a Sales között, Ön értékesítési és marketingtevékenységeket végezhet a Sales programban, illetve kezelheti a megrendelések teljesítését a Finance and Operations készletkezelésének használatával.</span><span class="sxs-lookup"><span data-stu-id="9b4e8-106">While data is flowing between Finance and Operations and Sales, you can perform sales and marketing activities in Sales, and you can handle order fulfillment by using inventory management in Finance and Operations.</span></span> 

<span data-ttu-id="9b4e8-107">A potenciális ügyfelek készpénzre váltásának integrációjával kapcsolatos további tájékoztatáshoz nézze meg a rövid YouTube-videót:</span><span class="sxs-lookup"><span data-stu-id="9b4e8-107">For more information about the Prospect to cash integration, watch the short YouTube video:</span></span>

> [!Video https://www.youtube.com/embed/AVV9x5x-XCg]

<span data-ttu-id="9b4e8-108">A jelenlegi verzióban A potenciális ügyfelek készpénzre váltása megoldás a következő típusú közvetlen szinkronizálást biztosítja:</span><span class="sxs-lookup"><span data-stu-id="9b4e8-108">In the current version, the Prospect to cash solution provides the following types of direct synchronization:</span></span>

- [<span data-ttu-id="9b4e8-109">Sales-fiókok fenntartása és azok szinkronizálása közvetlenül a Sales-től a Finance and Operations szolgáltatással</span><span class="sxs-lookup"><span data-stu-id="9b4e8-109">Maintain accounts in Sales and sync them directly from Sales to Finance and Operations</span></span>](accounts-template-mapping-direct.md)
- [<span data-ttu-id="9b4e8-110">Termékek karbantartása a Finance and Operations szolgáltatásban, majd szinkronizálásuk közvetlenül a Sales szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="9b4e8-110">Maintain products in Finance and Operations and sync them directly to Sales</span></span>](products-template-mapping-direct.md)
- [<span data-ttu-id="9b4e8-111">Névjegyek karbantartása a Sales szolgáltatásban, majd szinkronizálásuk névjegyekként vagy ügyfelekként közvetlenül a Finance and Operations szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="9b4e8-111">Maintain contacts in Sales and sync them directly to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping-direct.md)
- [<span data-ttu-id="9b4e8-112">Értékesítési ajánlatok közvetlen szinkronizálása a Sales szolgáltatásból a Finance and Operations szolgáltatásba (sablon kiadása függőben)</span><span class="sxs-lookup"><span data-stu-id="9b4e8-112">Synchronize sales quotation directly from Sales to Finance and Operations (template pending release)</span></span>](sales-quotation-template-mapping-sales-fin.md)
- [<span data-ttu-id="9b4e8-113">Értékesítési rendelések közvetlen szinkronizálása a Finance and Operations szolgáltatásból a Sales szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="9b4e8-113">Synchronize sales orders directly from Finance and Operations to Sales</span></span>](sales-order-template-mapping-direct.md)
- [<span data-ttu-id="9b4e8-114">Értékesítési rendelések közvetlen szinkronizálása a Sales és a Finance and Operations szolgáltatások között (sablon kiadása függőben)</span><span class="sxs-lookup"><span data-stu-id="9b4e8-114">Synchronize sales orders directly between Sales and Finance and Operations (template pending release)</span></span>](sales-order-template-mapping-direct-two-ways.md)
- [<span data-ttu-id="9b4e8-115">Értékesítési számla közvetlen szinkronizálása a Finance and Operations szolgáltatásból a Sales szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="9b4e8-115">Synchronize sales invoice directly from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping-direct.md)

<span data-ttu-id="9b4e8-116">A korábbi verziókban A potenciális ügyfelek készpénzre váltása megoldás a következő típusú nem közvetlen szinkronizálásokat biztosította:</span><span class="sxs-lookup"><span data-stu-id="9b4e8-116">In earlier versions, the Prospect to cash solution provides the following types of non-direct synchronization:</span></span>

- [<span data-ttu-id="9b4e8-117">Sales-fiókok fenntartása és azok szinkronizálása a Finance and Operations szolgáltatással</span><span class="sxs-lookup"><span data-stu-id="9b4e8-117">Maintain accounts in Sales and sync them to Finance and Operations</span></span>](accounts-template-mapping.md)
- [<span data-ttu-id="9b4e8-118">Névjegyek karbantartása a Sales szolgáltatásban, majd szinkronizálásuk a Finance and Operations szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="9b4e8-118">Maintain contacts in Sales and sync them to Finance and Operations</span></span>](contacts-template-mapping.md)
- [<span data-ttu-id="9b4e8-119">Termékek karbantartása a Finance and Operations szolgáltatásban, majd szinkronizálásuk a Sales szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="9b4e8-119">Maintain products in Finance and Operations and sync them to Sales</span></span>](products-template-mapping.md)
- [<span data-ttu-id="9b4e8-120">Értékesítési ajánlatok létrehozása a Sales szolgáltatásban, majd szinkronizálásuk a Finance and Operations szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="9b4e8-120">Create sales quotes in Sales and sync them to Finance and Operations</span></span>](sales-quotation-template-mapping.md)
- [<span data-ttu-id="9b4e8-121">Értékesítési rendelések létrehozása a Finance and Operations szolgáltatásban, majd szinkronizálásuk a Sales szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="9b4e8-121">Create sales orders in Finance and Operations and sync them to Sales</span></span>](sales-order-template-mapping.md)
- [<span data-ttu-id="9b4e8-122">Értékesítési számlák létrehozása a Finance and Operations szolgáltatásban, majd szinkronizálásuk a Sales szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="9b4e8-122">Create sales invoices in Finance and Operations and sync them to Sales</span></span>](sales-invoice-template-mapping.md)

## <a name="system-requirements-for-finance-and-operations"></a><span data-ttu-id="9b4e8-123">Rendszerigény a Finance and Operations rendszerhez</span><span class="sxs-lookup"><span data-stu-id="9b4e8-123">System requirements for Finance and Operations</span></span>

<span data-ttu-id="9b4e8-124">A potenciális ügyfelek készpénzre váltásának integrációja a következő verziókban támogatott:</span><span class="sxs-lookup"><span data-stu-id="9b4e8-124">Prospect to cash integration is supported on the following versions:</span></span>

### <a name="microsoft-dynamics-365-for-finance-and-operations-enterprise-edition-73-december-2017"></a><span data-ttu-id="9b4e8-125">Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition 7.3 (2017. december)</span><span class="sxs-lookup"><span data-stu-id="9b4e8-125">Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3 (December 2017)</span></span>

- <span data-ttu-id="9b4e8-126">Dynamics 365 for Finance and Operations, Enterprise Edition (2017. december - Alkalmazás buildszáma 7.3.11971.56116, 12-es platformfrissítéssel (7.0.4709.41129)</span><span class="sxs-lookup"><span data-stu-id="9b4e8-126">Dynamics 365 for Finance and Operations, Enterprise edition (December 2017) - Application build 7.3.11971.56116 with Platform Update 12 (7.0.4709.41129)</span></span>

### <a name="dynamics-365-for-finance-and-operations-enterprise-edition-july-2017"></a><span data-ttu-id="9b4e8-127">Dynamics 365 for Finance and Operations, Enterprise Edition (2017. július)</span><span class="sxs-lookup"><span data-stu-id="9b4e8-127">Dynamics 365 for Finance and Operations, Enterprise edition (July 2017)</span></span>

- <span data-ttu-id="9b4e8-128">Dynamics 365 for Finance and Operations, Enterprise Edition (2017. július) - 8-as platformfrissítéssel (alkalmazás buildszáma 7.2.11792.56024, platform buildszáma 7.0.4565.16212).</span><span class="sxs-lookup"><span data-stu-id="9b4e8-128">Dynamics 365 for Finance and Operations, Enterprise edition (July 2017) - with platform update 8 (application build 7.2.11792.56024 with platform build 7.0.4565.16212).</span></span>
- <span data-ttu-id="9b4e8-129">A következők gyorsjavítások szükségesek:</span><span class="sxs-lookup"><span data-stu-id="9b4e8-129">The following hotfixes are required:</span></span>

    - <span data-ttu-id="9b4e8-130">**[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160)** – Ez a gyorsjavítás lehetővé teszi az értékesítési rendelés szinkronizálását az adatintegrációs szolgáltatással a Sales rendszerből a Finance and Operations alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="9b4e8-130">**[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160)** – This hotfix enables sales order synchronization from Sales to Finance and Operations via the Data Integration feature.</span></span> <span data-ttu-id="9b4e8-131">Ezenkívül számos más fejlesztést is biztosít.</span><span class="sxs-lookup"><span data-stu-id="9b4e8-131">It also provides several other enhancements.</span></span>
    - <span data-ttu-id="9b4e8-132">**[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – Ez a gyorsjavítás lehetővé teszi az értékesítésirendelés-sor szinkronizálását az adatintegrációs szolgáltatással a Finance and Operations rendszerből a Sales alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="9b4e8-132">**[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – This hotfix enables sales order line synchronization from Finance and Operations to Sales via the Data Integration feature.</span></span>
    - <span data-ttu-id="9b4e8-133">**[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – Ez a gyorsjavítás lehetővé teszi az értékesítési rendelés szinkronizálását az adatintegrációs szolgáltatással a Finance and Operations rendszerből a Sales alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="9b4e8-133">**[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – This hotfix enables sales order synchronization from Finance and Operations to Sales via the Data Integration feature.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9b4e8-134">Csak a KB4045570-et kell telepíteni, mivel a telepítés tartalmazza a többi gyorsjavítás változásait.</span><span class="sxs-lookup"><span data-stu-id="9b4e8-134">You only have to install KB4045570 because the installation includes the changes from other hotfixes.</span></span> 

### <a name="dynamics-365-for-finance-and-operations-version-1611-november-2016"></a><span data-ttu-id="9b4e8-135">Dynamics 365 for Finance and Operations 1611-es verzió (2016. november)</span><span class="sxs-lookup"><span data-stu-id="9b4e8-135">Dynamics 365 for Finance and Operations version 1611 (November 2016)</span></span>

- <span data-ttu-id="9b4e8-136">Dynamics 365 for Finance and Operations, 1611-es verzió (2016. november) 8-as vagy újabb platformfrissítéssel</span><span class="sxs-lookup"><span data-stu-id="9b4e8-136">Dynamics 365 for Finance and Operations version 1611 (November 2016)  with platform update 8 or higher</span></span>

- <span data-ttu-id="9b4e8-137">A következők gyorsjavítások szükségesek:</span><span class="sxs-lookup"><span data-stu-id="9b4e8-137">The following hotfixes are required:</span></span>

    - <span data-ttu-id="9b4e8-138">**[KB4051266](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4051266&bugId=3863566&qc=ee80faaa7bc6c77b368d5eaf456c9c08e0b9fba5903a7b6fd8c13756c3a4b757)** - lehetővé teszi az értékesítési rendelések szinkronizálását az adatintegrációs szolgáltatással a Finance and Operations rendszerből a Sales alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="9b4e8-138">**[KB4051266](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4051266&bugId=3863566&qc=ee80faaa7bc6c77b368d5eaf456c9c08e0b9fba5903a7b6fd8c13756c3a4b757)** - Enable sales order synchronization with Data integrator from Finance and Operations to Sales.</span></span> 
    - <span data-ttu-id="9b4e8-139">**[KB4037542](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4037542&bugId=3848253&qc=8323b93c15280172c5ab4159e0256e37104ced1729462c91ab2f7d00cb8d419c)** - lehetővé teszi az értékesítési rendelések fejlécénak és sorainak szinkronizálását az adatintegrációs szolgáltatással a Finance and Operations rendszerből a Sales alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="9b4e8-139">**[KB4037542](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4037542&bugId=3848253&qc=8323b93c15280172c5ab4159e0256e37104ced1729462c91ab2f7d00cb8d419c)** - Enable sales order header and line synchronization with Data integrator from Finance and Operations to Sales.</span></span>
    - <span data-ttu-id="9b4e8-140">**[KB4033093](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4033093&bugId=3824604&qc=bd7e15e1fb56066b3a82ce48b691cf1ffbc934a7473fa888545b2211a8d416c5)** - A potenciális ügyfelek készpénzre váltása támogatása szükséges adatentitások révén.</span><span class="sxs-lookup"><span data-stu-id="9b4e8-140">**[KB4033093](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4033093&bugId=3824604&qc=bd7e15e1fb56066b3a82ce48b691cf1ffbc934a7473fa888545b2211a8d416c5)** - Support for prospect to cash integration through data entities is required.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9b4e8-141">A gyorsjavítások telepítése után a következő kötegelt munkát kell aktiválnia a **SalesPopulateProspectToCash** űrlapról.</span><span class="sxs-lookup"><span data-stu-id="9b4e8-141">After you install the hotfixes, you must trigger the following batch job from the **SalesPopulateProspectToCash** form.</span></span> <span data-ttu-id="9b4e8-142">Ez az űrlap el van rejtve, mivel csak egyszer van rá szükség.</span><span class="sxs-lookup"><span data-stu-id="9b4e8-142">This form is hidden because you only need it once.</span></span> <span data-ttu-id="9b4e8-143">Az űrlap eléréséhez jelentkezzen be a környezetbe, és adja hozzá a következőt az URL-címhez a böngésző címsorában: &mi=action:SalesPopulateProspectToCash, for example, https://ax123456.cloud.test.dynamics.com/?cmp=USMF&mi=action:SalesPopulateProspectToCash.</span><span class="sxs-lookup"><span data-stu-id="9b4e8-143">To access the form, log in to the environment and add the following to the URL in your browser address: &mi=action:SalesPopulateProspectToCash, for example, https://ax123456.cloud.test.dynamics.com/?cmp=USMF&mi=action:SalesPopulateProspectToCash.</span></span> <span data-ttu-id="9b4e8-144">Az űrlap megnyílásakor kattintson az OK lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9b4e8-144">When the form opens, click OK.</span></span> <span data-ttu-id="9b4e8-145">Ez egyedi értékekkel tölt ki egy új **LineCreationSequnceNumber** mezőt a **SalesLine**, **SalesQuotationLine** és **CustInvoiceTrans** táblákban, és frissíti a terméklistát.</span><span class="sxs-lookup"><span data-stu-id="9b4e8-145">This will populate a new **LineCreationSequnceNumber** field in the **SalesLine**, **SalesQuotationLine**, and **CustInvoiceTrans** tables with unique values, and the product list will be refreshed.</span></span> <span data-ttu-id="9b4e8-146">Ez a potenciális ügyfél készpénzre váltása integráció működéséhez szükség.</span><span class="sxs-lookup"><span data-stu-id="9b4e8-146">This is required for the Prospect to cash integration to work.</span></span>


## <a name="system-requirements-for-sales"></a><span data-ttu-id="9b4e8-147">A Sales rendszerkövetelményei</span><span class="sxs-lookup"><span data-stu-id="9b4e8-147">System requirements for Sales</span></span>

<span data-ttu-id="9b4e8-148">A Potenciális ügyfelek készpénzre váltása megoldás használatához telepítenie kell a következő összetevőket:</span><span class="sxs-lookup"><span data-stu-id="9b4e8-148">To use the Prospect to cash solution, you must install the following components:</span></span>

- <span data-ttu-id="9b4e8-149">Dynamics 365 for Sales, verzió: 1612 (8.2.1.207) (DB 8.2.1.207) online</span><span class="sxs-lookup"><span data-stu-id="9b4e8-149">Dynamics 365 for Sales version 1612 (8.2.1.207) (DB 8.2.1.207) online</span></span>
- <span data-ttu-id="9b4e8-150">A potenciális ügyfelek készpénzre váltása megoldás Dynamics 365 for Sales szolgáltatáshoz, 1.15.0.0 (v15)</span><span class="sxs-lookup"><span data-stu-id="9b4e8-150">Prospect to cash solution for Dynamics 365 for Sales, version 1.15.0.0 (v15)</span></span> 

   > [!NOTE]
   >
   > <span data-ttu-id="9b4e8-151">Az 1.0.0.0 és 1.0.0.1 verziójú sablonok támogatottak Dynamics 365 for Sales rendszerhez tartozó A potenciális ügyfelek készpénzre váltása szolgáltatás 1.14.1.0 verziójánál</span><span class="sxs-lookup"><span data-stu-id="9b4e8-151">Templates with version 1.0.0.0 and 1.0.0.1 are supported on Prospect to cash solution for Dynamics 365 for Sales, version 1.14.1.0</span></span>
   >
   > <span data-ttu-id="9b4e8-152">Az 2.0.0.0 és 2.1.0.0 verziójú sablonok támogatottak Dynamics 365 for Sales rendszerhez tartozó A potenciális ügyfelek készpénzre váltása szolgáltatás 1.15.0.0 verziójánál</span><span class="sxs-lookup"><span data-stu-id="9b4e8-152">Templates with version 2.0.0.0 and 2.1.0.0 are supported on Prospect to cash solution for Dynamics 365 for Sales, version 1.15.0.0</span></span>

### <a name="install-the-prospect-to-cash-solution-for-sales"></a><span data-ttu-id="9b4e8-153">Telepítse A potenciális ügyfelek készpénzre váltása megoldást a Salesbe</span><span class="sxs-lookup"><span data-stu-id="9b4e8-153">Install the Prospect to cash solution for Sales</span></span>

1. <span data-ttu-id="9b4e8-154">Töltse le a [A potenciális ügyfelek készpénzre váltása Dynamics 365 for Saleshez megoldás csomagolt zip-fájlját](https://mbs.microsoft.com/customersource/Global/365Enterprise/downloads/product-releases/MD365FNOPENTProspectToCash) a CustomerSource-ról.</span><span class="sxs-lookup"><span data-stu-id="9b4e8-154">Download the [Prospect to cash for Dynamics 365 for Sales solution package zip file](https://mbs.microsoft.com/customersource/Global/365Enterprise/downloads/product-releases/MD365FNOPENTProspectToCash) from CustomerSource.</span></span>
2. <span data-ttu-id="9b4e8-155">Ellenőrizze, hogy a zip-fájl zárolatlan.</span><span class="sxs-lookup"><span data-stu-id="9b4e8-155">Make sure that the zip file is unblocked.</span></span> <span data-ttu-id="9b4e8-156">Ellenkező esetben a megoldási csomag telepítésekor a következő hibaüzenet jelenhet meg: „Nem található importálási csomag”.</span><span class="sxs-lookup"><span data-stu-id="9b4e8-156">Otherwise, when you try to install the solution package, you may receive the following error message, "No import packages were found."</span></span> <span data-ttu-id="9b4e8-157">A zip-fájl zárolásának feloldásához kattintson rá a jobb gombbal, majd válassza a **Tulajdonságok** elemet.</span><span class="sxs-lookup"><span data-stu-id="9b4e8-157">To unblock the zip file, right-click it, and select **Properties**.</span></span> <span data-ttu-id="9b4e8-158">Válassza a **Blokkolás feloldása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9b4e8-158">Select **Unblock**.</span></span>
3. <span data-ttu-id="9b4e8-159">Bontsa ki, majd futtassa a **PackageDeployer.exe** fájlt.</span><span class="sxs-lookup"><span data-stu-id="9b4e8-159">Unzip and run **PackageDeployer.exe**.</span></span>
4. <span data-ttu-id="9b4e8-160">Telepítse A potenciális ügyfelek készpénzre váltása megoldást a Sales-példányba:</span><span class="sxs-lookup"><span data-stu-id="9b4e8-160">Install the Prospect to cash solution on your Sales instance:</span></span>

    1. <span data-ttu-id="9b4e8-161">Válassza az **Office 365** telepítési típust.</span><span class="sxs-lookup"><span data-stu-id="9b4e8-161">Select **Office 365** as the deployment type.</span></span>
    2. <span data-ttu-id="9b4e8-162">Válassza a **Speciális megjelenítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9b4e8-162">Select **Show advanced**.</span></span>
    3. <span data-ttu-id="9b4e8-163">A gyors telepítéshez válasszon régiót.</span><span class="sxs-lookup"><span data-stu-id="9b4e8-163">For a quick installation, select a region.</span></span> <span data-ttu-id="9b4e8-164">Ha a **Nem tudom** lehetőséget választja, a rendszer az összes régiót végigkeresi, és a telepítés hosszabb ideig tart.</span><span class="sxs-lookup"><span data-stu-id="9b4e8-164">If you select **Don't know**, the system searches for all regions, and the installation will take more time.</span></span>
    4. <span data-ttu-id="9b4e8-165">Adja meg egy olyan adminisztrátori felhasználó felhasználónevét és jelszavát, aki telepítési felhasználói jogosultságokkal rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="9b4e8-165">Enter the user name and password of an admin user who has installation rights.</span></span>



