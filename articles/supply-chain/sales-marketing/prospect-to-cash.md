---
title: "A potenciális ügyfelek készpénzre váltása"
description: "A témakör áttekintést nyújt A potenciális ügyfelek készpénzre váltása megoldásról a Dynamics 365 for Finance and Operations, Enterprise edition és a Dynamics 365 for Sales szolgáltatásokban."
author: ChristianRytt
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 674d2e1f2c5cdbccf43618a9083ca01abed0735a
ms.openlocfilehash: 2accf77c5241adff7ad1648737dde451153fde46
ms.contentlocale: hu-hu
ms.lasthandoff: 11/14/2017

---

# <a name="prospect-to-cash"></a><span data-ttu-id="82b26-103">A potenciális ügyfelek készpénzre váltása</span><span class="sxs-lookup"><span data-stu-id="82b26-103">Prospect to cash</span></span>  

[!include[banner](../includes/banner.md)]

<span data-ttu-id="82b26-104">A potenciális ügyfelek készpénzre váltása megoldás az [Adatintegráció](/common-data-service/entity-reference/dynamics-365-integration) segítségével szinkronizálja az adatokat a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition és a Dynamics 365 for Sales példányai között a Common Data Service (CDS) környezetben.</span><span class="sxs-lookup"><span data-stu-id="82b26-104">The Prospect to cash solution uses [Data Integration](/common-data-service/entity-reference/dynamics-365-integration) to synchronize data across Microsoft Dynamics 365 for Finance and Operations, Enterprise edition and Dynamics 365 for Sales instances via the Common Data Service (CDS).</span></span> <span data-ttu-id="82b26-105">Az Adatintegrációs szolgáltatásban rendelkezésre álló A potenciális ügyfelek készpénzre váltása sablonok lehetővé teszik a termék-, ügyfél-, kapcsolatfelvételi és eladási számlákra vonatkozó adatok áramlását a Finance and Operations és a Sales között.</span><span class="sxs-lookup"><span data-stu-id="82b26-105">The Prospect to cash templates available with the Data Integration feature enable the flow of accounts, contacts, products, sales quotes, sales orders, and sales invoices data between Finance and Operations and Sales.</span></span> <span data-ttu-id="82b26-106">Miközben az adatok áramlanak a Finance and Operations és a Sales között, Ön értékesítési és marketingtevékenységeket végezhet a Sales programban, illetve kezelheti a megrendelések teljesítését a Finance and Operations készletkezelésével.</span><span class="sxs-lookup"><span data-stu-id="82b26-106">While the data is flowing between Finance and Operations and Sales, you can carry out sales and marketing activities in Sales and handle the order fulfillment with inventory management in Finance and Operations.</span></span> 

<span data-ttu-id="82b26-107">Ez a megoldás integrációt nyújt az alábbi területeken:</span><span class="sxs-lookup"><span data-stu-id="82b26-107">This solution provides integration in the following areas:</span></span> 

-   [<span data-ttu-id="82b26-108">Sales-fiókok fenntartása és azok szinkronizálása a Finance and Operations szolgáltatással</span><span class="sxs-lookup"><span data-stu-id="82b26-108">Maintain accounts in Sales and sync them to Finance and Operations</span></span>](accounts-template-mapping.md)
-   [<span data-ttu-id="82b26-109">Sales-kapcsolattartók fenntartása és azok szinkronizálása a Finance and Operations szolgáltatással</span><span class="sxs-lookup"><span data-stu-id="82b26-109">Maintain contacts in Sales and sync them to Finance and Operations</span></span>](contacts-template-mapping.md)
-   [<span data-ttu-id="82b26-110">Termékek fenntartása és azok szinkronizálása a Finance and Operations és a Sales szolgáltatás között</span><span class="sxs-lookup"><span data-stu-id="82b26-110">Maintain products in Finance and Operations and sync them to Sales</span></span>](products-template-mapping.md)
-   [<span data-ttu-id="82b26-111">Értékesítési ajánlatok létrehozása a Sales-ben és azok szinkronizálása a Finance and Operations szolgáltatással</span><span class="sxs-lookup"><span data-stu-id="82b26-111">Create sales quotes in Sales and sync them to Finance and Operations</span></span>](sales-quotation-template-mapping.md)
-   [<span data-ttu-id="82b26-112">Értékesítési ajánlatok létrehozása a Finance and Operationsben és azok szinkronizálása a Sales szolgáltatással</span><span class="sxs-lookup"><span data-stu-id="82b26-112">Create sales orders in Finance and Operations and sync them to Sales</span></span>](sales-order-template-mapping.md)
-   [<span data-ttu-id="82b26-113">Értékesítési számlák létrehozása a Finance and Operationsben és azok szinkronizálása a Sales szolgáltatással</span><span class="sxs-lookup"><span data-stu-id="82b26-113">Create sales invoices in Finance and Operations and sync them to Sales</span></span>](sales-invoice-template-mapping.md)

<span data-ttu-id="82b26-114">Ez a megoldás közvetlen szinkronizálást nyújt az alábbi területeken:</span><span class="sxs-lookup"><span data-stu-id="82b26-114">This solution provides direct synchronization in the following areas:</span></span>

-   [<span data-ttu-id="82b26-115">Sales-fiókok fenntartása és azok szinkronizálása közvetlenül a Sales-től a Finance and Operations szolgáltatással</span><span class="sxs-lookup"><span data-stu-id="82b26-115">Maintain accounts in Sales and sync them directly from Sales to Finance and Operations</span></span>](accounts-template-mapping-direct.md)
-   [<span data-ttu-id="82b26-116">Termékek fenntartása és azok közvetlen szinkronizálása a Finance and Operations és a Sales szolgáltatás között</span><span class="sxs-lookup"><span data-stu-id="82b26-116">Maintain products in Finance and Operations and sync them directly to Sales</span></span>](products-template-mapping-direct.md)
-   [<span data-ttu-id="82b26-117">A Sales-kapcsolatok karbantartása és közvetlen szinkronizálása a Finance and Operations-kapcsolatokra vagy -ügyfelekre</span><span class="sxs-lookup"><span data-stu-id="82b26-117">Maintain contacts in Sales and sync them directly to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping-direct.md)
-   [<span data-ttu-id="82b26-118">Értékesítésiajánlat-fejlécek és -sorok közvetlen szinkronizálása a Sales szolgáltatásból a Finance and Operations szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="82b26-118">Synchronize sales quotation headers and lines directly from Sales to Finance and Operations</span></span>](sales-quotation-template-mapping-sales-fin.md)
-   [<span data-ttu-id="82b26-119">Értékesítési ajánlatok létrehozása a Finance and Operations szolgáltatásban és azok közvetlen szinkronizálása a Sales szolgáltatással</span><span class="sxs-lookup"><span data-stu-id="82b26-119">Create sales orders in Finance and Operations and sync them directly to Sales</span></span>](sales-order-template-mapping-direct.md)
-  [<span data-ttu-id="82b26-120">Értékesítésirendelés-fejlécek és -sorok közvetlen szinkronizálása a Sales és a Finance and Operations szolgáltatások között</span><span class="sxs-lookup"><span data-stu-id="82b26-120">Synchronize sales order headers and lines directly between Sales and Finance and Operations</span></span>](sales-order-template-mapping-between-sales-fin.md)
-   [<span data-ttu-id="82b26-121">Értékelési rendelések szinkronizálása közvetlenül a Sales és a Finance and Operations között</span><span class="sxs-lookup"><span data-stu-id="82b26-121">Synchronize sales orders directly between Sales and Finance and Operations</span></span>](sales-order-template-mapping-direct-two-ways.md)
-   [<span data-ttu-id="82b26-122">Értékesítési számlák létrehozása a Finance and Operations szolgáltatásban és azok közvetlen szinkronizálása a Sales szolgáltatással</span><span class="sxs-lookup"><span data-stu-id="82b26-122">Create sales invoices in Finance and Operations and sync them directly to Sales</span></span>](sales-invoice-template-mapping-direct.md)


## <a name="system-requirements-for-dynamics-365-for-finance-and-operations-enterprise-edition"></a><span data-ttu-id="82b26-123">A Dynamics 365 for Finance and Operations, Enterprise edition rendszerigénye</span><span class="sxs-lookup"><span data-stu-id="82b26-123">System requirements for Dynamics 365 for Finance and Operations, Enterprise edition</span></span>

<span data-ttu-id="82b26-124">A potenciális ügyfelek készpénzre váltása megoldás használatához telepítenie kell a következőket:</span><span class="sxs-lookup"><span data-stu-id="82b26-124">To use the Prospect to cash solution, you must install the following:</span></span>

- <span data-ttu-id="82b26-125">Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (2017. július) with 8-as platformfrissítéssel (alkalmazás 7.2.11792.56024, platform 7.0.4565.16212)</span><span class="sxs-lookup"><span data-stu-id="82b26-125">Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (July 2017) with Platform update 8 (App 7.2.11792.56024 w/ Platform 7.0.4565.16212)</span></span>

- <span data-ttu-id="82b26-126">Gyorsjavítások a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition rendszerhez (2017. július).</span><span class="sxs-lookup"><span data-stu-id="82b26-126">Hotfixes for Dynamics 365 for Finance and Operations, Enterprise edition (July 2017).</span></span>
        
    -  <span data-ttu-id="82b26-127">[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160) – a gyorsjavítás lehetővé teszi az értékesítési rendelés szinkronizálásának támogatását az Adatok integrálása funkcióval a Sales-től a Finance and Operations-ig számos más fejlesztés mellett.</span><span class="sxs-lookup"><span data-stu-id="82b26-127">[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160) - This hotfix enabels support for sales order synchronization with the Data Integration feature from Sales to Finance and Operations, along with a number of other enhancements.</span></span>

    -  <span data-ttu-id="82b26-128">[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2) – Ez a gyorsjavítás lehetővé teszi az értékesítési rendelési sor szinkronizálását az adatintegrációs szolgáltatással a Finance and Operations programból a Salesbe.</span><span class="sxs-lookup"><span data-stu-id="82b26-128">[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2) - This hotfix enables sales order line synchronization with the Data Integration feature from Finance and Operations to Sales.</span></span>
        
    -  <span data-ttu-id="82b26-129">[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2) – Ez a gyorsjavítás lehetővé teszi az értékesítési rendelés szinkronizálását az adatintegrációs szolgáltatással a Finance and Operations programból a Salesbe.</span><span class="sxs-lookup"><span data-stu-id="82b26-129">[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2) - This hotfix enables sales order synchronization with the Data Integration feature from Finance and Operations to Sales.</span></span>

<span data-ttu-id="82b26-130">**Megjegyzés:**: csak a KB4045570-et kell telepíteni, mivel a telepítés tartalmazza a többi tudásbáziscikk változásait.</span><span class="sxs-lookup"><span data-stu-id="82b26-130">**Note**: You only need to install KB4045570 because the installation includes the changes from the other KB's.</span></span>
 
## <a name="system-requirements-for-dynamics-365-for-sales"></a><span data-ttu-id="82b26-131">A Dynamics 365 for Sales rendszerkövetelményei</span><span class="sxs-lookup"><span data-stu-id="82b26-131">System requirements for Dynamics 365 for Sales</span></span>

<span data-ttu-id="82b26-132">A potenciális ügyfelek készpénzre váltása megoldás használatához telepítenie kell a következőket:</span><span class="sxs-lookup"><span data-stu-id="82b26-132">To use the Prospect to cash solution, you must install the following:</span></span>

- <span data-ttu-id="82b26-133">Dynamics 365 for Sales, verzió: 1612 (8.2.1.207) (DB 8.2.1.207) online.</span><span class="sxs-lookup"><span data-stu-id="82b26-133">Dynamics 365 for Sales version 1612 (8.2.1.207) (DB 8.2.1.207) online.</span></span>
- <span data-ttu-id="82b26-134">A potenciális ügyfelek készpénzre váltása megoldás Dynamics 365 for Sales szolgáltatáshoz, 1.14.0.0 (v14) vagy későbbi verzió.</span><span class="sxs-lookup"><span data-stu-id="82b26-134">Prospect to cash solution for Dynamics 365 for Sales, version 1.14.0.0 (v14) or later.</span></span>

### <a name="install-the-prospect-to-cash-solution-for-sales"></a><span data-ttu-id="82b26-135">Telepítse A potenciális ügyfelek készpénzre váltása megoldást a Salesbe</span><span class="sxs-lookup"><span data-stu-id="82b26-135">Install the Prospect to cash solution for Sales</span></span>

- <span data-ttu-id="82b26-136">Töltse le a [A potenciális ügyfelek készpénzre váltása Dynamics 365 for Saleshez megoldás csomagolt zip-fájlját](https://mbs.microsoft.com/customersource/Global/365Enterprise/downloads/product-releases/MD365FNOPENTProspectToCash) a CustomerSource-ról.</span><span class="sxs-lookup"><span data-stu-id="82b26-136">Download the [Prospect to cash for Dynamics 365 for Sales solution package zip file](https://mbs.microsoft.com/customersource/Global/365Enterprise/downloads/product-releases/MD365FNOPENTProspectToCash) on CustomerSource.</span></span>

- <span data-ttu-id="82b26-137">Győződjön meg arról, hogy a zip-fájl feloldott, és nem kapja meg az „Importálási csomagok nem találhatók” hibaüzenetet a megoldáscsomag telepítésekor.</span><span class="sxs-lookup"><span data-stu-id="82b26-137">Make sure that the zip file is unblocked so that you do not get the error message "No import packages were found" when you install the solution package.</span></span> <span data-ttu-id="82b26-138">A fájl feloldásához tegye a következőket:</span><span class="sxs-lookup"><span data-stu-id="82b26-138">To unblock the file, do the following:</span></span>

    -  <span data-ttu-id="82b26-139">Kattintson jobb gombbal a fájlra.</span><span class="sxs-lookup"><span data-stu-id="82b26-139">Right-click the zip file.</span></span>
    -  <span data-ttu-id="82b26-140">Válassza ki **Tulajdonságok** majd a **Feloldás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="82b26-140">Select **Properties** and then select **Unblock**.</span></span> 

- <span data-ttu-id="82b26-141">Bontsa ki, majd futtassa a PackageDeployer.exe fájlt.</span><span class="sxs-lookup"><span data-stu-id="82b26-141">Unzip and run PackageDeployer.exe.</span></span>

- <span data-ttu-id="82b26-142">Telepítse A potenciális ügyfelek készpénzre váltása megoldást a Sales-példányba.</span><span class="sxs-lookup"><span data-stu-id="82b26-142">Install the Prospect to Cash solution in your Sales instance.</span></span>

    - <span data-ttu-id="82b26-143">Válassza az **Office 365** telepítési típust.</span><span class="sxs-lookup"><span data-stu-id="82b26-143">Select the **Office 365** Deployment type.</span></span>
    - <span data-ttu-id="82b26-144">Válassza a **Speciális megjelenítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="82b26-144">Select **Show advanced**.</span></span>
    - <span data-ttu-id="82b26-145">Gyors telepítéshez válassza a **Régió** elemet.</span><span class="sxs-lookup"><span data-stu-id="82b26-145">For a quick installation, select a **Region**.</span></span> <span data-ttu-id="82b26-146">Ha a **Nem tudom** lehetőséget választja, a rendszer az összes régiót válasszagigkeresi, és a telepítés hosszabb ideig tart.</span><span class="sxs-lookup"><span data-stu-id="82b26-146">If you select **Don’t know**, the system searches for all regions and it will take longer to install.</span></span>
    - <span data-ttu-id="82b26-147">Adja meg egy olyan adminisztrátori felhasználó **Felhasználónevét** és **Jelszavát**, aki telepítési felhasználói jogosultságokkal rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="82b26-147">Enter **User name** and **Password** for an admin user who has the user rights to install.</span></span>

