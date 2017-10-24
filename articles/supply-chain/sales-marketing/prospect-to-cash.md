---
title: "A potenciális ügyfelek készpénzre váltása"
description: "A témakör áttekintést nyújt A potenciális ügyfelek készpénzre váltása megoldásról a Dynamics 365 for Finance and Operations, Enterprise edition és a Dynamics 365 for Sales szolgáltatásokban."
author: ChristianRytt
manager: AnnBe
ms.date: 08/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 47e70cb1291e390b42b7feff844b2aca141f09b7
ms.openlocfilehash: a5f1ecd5f8b46287839439a963e571531ae161a7
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="prospect-to-cash"></a><span data-ttu-id="eba18-103">A potenciális ügyfelek készpénzre váltása</span><span class="sxs-lookup"><span data-stu-id="eba18-103">Prospect to cash</span></span>  

[!include[banner](../includes/banner.md)]

<span data-ttu-id="eba18-104">A potenciális ügyfelek készpénzre váltása megoldás az [Adatintegráció](/common-data-service/entity-reference/dynamics-365-integration) segítségével szinkronizálja az adatokat a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition és a Dynamics 365 for Sales példányai között a Common Data Service (CDS) környezetben.</span><span class="sxs-lookup"><span data-stu-id="eba18-104">The Prospect to cash solution uses [Data Integration](/common-data-service/entity-reference/dynamics-365-integration) to synchronize data across Microsoft Dynamics 365 for Finance and Operations, Enterprise edition and Dynamics 365 for Sales instances via the Common Data Service (CDS).</span></span> <span data-ttu-id="eba18-105">Az Adatintegrációs szolgáltatásban rendelkezésre álló A potenciális ügyfelek készpénzre váltása sablonok lehetővé teszik a termék-, ügyfél-, kapcsolatfelvételi és eladási számlákra vonatkozó adatok áramlását a Finance and Operations és a Sales között.</span><span class="sxs-lookup"><span data-stu-id="eba18-105">The Prospect to cash templates available with the Data Integration feature enable the flow of accounts, contacts, products, sales quotes, sales orders, and sales invoices data between Finance and Operations and Sales.</span></span> <span data-ttu-id="eba18-106">Miközben az adatok áramlanak a Finance and Operations és a Sales között, Ön értékesítési és marketingtevékenységeket végezhet a Sales programban, illetve kezelheti a megrendelések teljesítését a Finance and Operations készletkezelésével.</span><span class="sxs-lookup"><span data-stu-id="eba18-106">While the data is flowing between Finance and Operations and Sales, you can carry out sales and marketing activities in Sales and handle the order fulfillment with inventory management in Finance and Operations.</span></span> 

<span data-ttu-id="eba18-107">Ez a megoldás integrációt nyújt az alábbi területeken:</span><span class="sxs-lookup"><span data-stu-id="eba18-107">This solution provides integration in the following areas:</span></span> 

-   [<span data-ttu-id="eba18-108">Sales-fiókok fenntartása és azok szinkronizálása a Finance and Operations szolgáltatással</span><span class="sxs-lookup"><span data-stu-id="eba18-108">Maintain accounts in Sales and sync them to Finance and Operations</span></span>](accounts-template-mapping.md)
-   [<span data-ttu-id="eba18-109">Sales-kapcsolattartók fenntartása és azok szinkronizálása a Finance and Operations szolgáltatással</span><span class="sxs-lookup"><span data-stu-id="eba18-109">Maintain contacts in Sales and sync them to Finance and Operations</span></span>](contacts-template-mapping.md)
-   [<span data-ttu-id="eba18-110">Termékek fenntartása és azok szinkronizálása a Finance and Operations és a Sales szolgáltatás között</span><span class="sxs-lookup"><span data-stu-id="eba18-110">Maintain products in Finance and Operations and sync them to Sales</span></span>](products-template-mapping.md)
-   [<span data-ttu-id="eba18-111">Értékesítési ajánlatok létrehozása a Sales-ben és azok szinkronizálása a Finance and Operations szolgáltatással</span><span class="sxs-lookup"><span data-stu-id="eba18-111">Create sales quotes in Sales and sync them to Finance and Operations</span></span>](sales-quotation-template-mapping.md)
-   [<span data-ttu-id="eba18-112">Értékesítési ajánlatok létrehozása a Finance and Operationsben és azok szinkronizálása a Sales szolgáltatással</span><span class="sxs-lookup"><span data-stu-id="eba18-112">Create sales orders in Finance and Operations and sync them to Sales</span></span>](sales-order-template-mapping.md)
-   [<span data-ttu-id="eba18-113">Értékesítési számlák létrehozása a Finance and Operationsben és azok szinkronizálása a Sales szolgáltatással</span><span class="sxs-lookup"><span data-stu-id="eba18-113">Create sales invoices in Finance and Operations and sync them to Sales</span></span>](sales-invoice-template-mapping.md)

## <a name="system-requirements-for-dynamics-365-for-finance-and-operations-enterprise-edition"></a><span data-ttu-id="eba18-114">A Dynamics 365 for Finance and Operations, Enterprise edition rendszerigénye</span><span class="sxs-lookup"><span data-stu-id="eba18-114">System requirements for Dynamics 365 for Finance and Operations, Enterprise edition</span></span>

<span data-ttu-id="eba18-115">A potenciális ügyfelek készpénzre váltása megoldás használatához telepítenie kell a következőket:</span><span class="sxs-lookup"><span data-stu-id="eba18-115">To use the Prospect to cash solution, you must install the following:</span></span>

- <span data-ttu-id="eba18-116">Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (2017. július) with 8-as platformfrissítéssel (alkalmazás 7.2.11792.56024, platform 7.0.4565.16212)</span><span class="sxs-lookup"><span data-stu-id="eba18-116">Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (July 2017) with Platform update 8 (App 7.2.11792.56024 w/ Platform 7.0.4565.16212)</span></span>

- <span data-ttu-id="eba18-117">Két gyorsjavítás a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition rendszerhez (2017. július).</span><span class="sxs-lookup"><span data-stu-id="eba18-117">Two hotfixes for Dynamics 365 for Finance and Operations, Enterprise edition (July 2017).</span></span>

    -  <span data-ttu-id="eba18-118">[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2) – Ez a gyorsjavítás lehetővé teszi az értékesítési rendelési sor szinkronizálását az adatintegrációs szolgáltatással a Finance and Operations programból a Salesbe.</span><span class="sxs-lookup"><span data-stu-id="eba18-118">[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2) - This hotfix enables sales order line synchronization with the Data Integration feature from Finance and Operations to Sales.</span></span>
        
    -  <span data-ttu-id="eba18-119">[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2) – Ez a gyorsjavítás lehetővé teszi az értékesítési rendelés szinkronizálását az adatintegrációs szolgáltatással a Finance and Operations programból a Salesbe.</span><span class="sxs-lookup"><span data-stu-id="eba18-119">[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2) - This hotfix enables sales order synchronization with the Data Integration feature from Finance and Operations to Sales.</span></span>
    
<span data-ttu-id="eba18-120">**Megjegyzés:**: csak a KB4036524-et kell telepíteni, mivel a telepítés tartalmazza a KB4036461 változásait.</span><span class="sxs-lookup"><span data-stu-id="eba18-120">**Note**: You only need to install KB4036524 because the installation includes the changes from KB4036461.</span></span>
 
## <a name="system-requirements-for-dynamics-365-for-sales"></a><span data-ttu-id="eba18-121">A Dynamics 365 for Sales rendszerkövetelményei</span><span class="sxs-lookup"><span data-stu-id="eba18-121">System requirements for Dynamics 365 for Sales</span></span>

<span data-ttu-id="eba18-122">A potenciális ügyfelek készpénzre váltása megoldás használatához telepítenie kell a következőket:</span><span class="sxs-lookup"><span data-stu-id="eba18-122">To use the Prospect to cash solution, you must install the following:</span></span>

- <span data-ttu-id="eba18-123">Dynamics 365 for Sales, verzió: 1612 (8.2.1.207) (DB 8.2.1.207) online vagy későbbi.</span><span class="sxs-lookup"><span data-stu-id="eba18-123">Dynamics 365 for Sales version 1612 (8.2.1.207) (DB 8.2.1.207) online or later.</span></span>
- <span data-ttu-id="eba18-124">A potenciális ügyfelek készpénzre váltása megoldás Dynamics 365 for Sales szolgáltatáshoz, 1.14.0.0 (v14) vagy későbbi verzió.</span><span class="sxs-lookup"><span data-stu-id="eba18-124">Prospect to cash solution for Dynamics 365 for Sales, version 1.14.0.0 (v14) or later.</span></span>

### <a name="install-the-prospect-to-cash-solution-for-sales"></a><span data-ttu-id="eba18-125">Telepítse A potenciális ügyfelek készpénzre váltása megoldást a Salesbe</span><span class="sxs-lookup"><span data-stu-id="eba18-125">Install the Prospect to cash solution for Sales</span></span>

- <span data-ttu-id="eba18-126">Töltse le a [A potenciális ügyfelek készpénzre váltása Dynamics 365 for Saleshez megoldás csomagolt zip-fájlját](https://mbs.microsoft.com/customersource/Global/365Enterprise/downloads/product-releases/MD365FNOPENTProspectToCash) a CustomerSource-ról.</span><span class="sxs-lookup"><span data-stu-id="eba18-126">Download the [Prospect to cash for Dynamics 365 for Sales solution package zip file](https://mbs.microsoft.com/customersource/Global/365Enterprise/downloads/product-releases/MD365FNOPENTProspectToCash) on CustomerSource.</span></span>

- <span data-ttu-id="eba18-127">Győződjön meg arról, hogy a zip-fájl feloldott, és nem kapja meg az „Importálási csomagok nem találhatók” hibaüzenetet a megoldáscsomag telepítésekor.</span><span class="sxs-lookup"><span data-stu-id="eba18-127">Make sure that the zip file is unblocked so that you do not get the error message "No import packages were found" when you install the solution package.</span></span> <span data-ttu-id="eba18-128">A fájl feloldásához tegye a következőket:</span><span class="sxs-lookup"><span data-stu-id="eba18-128">To unblock the file, do the following:</span></span>

    -  <span data-ttu-id="eba18-129">Kattintson jobb gombbal a fájlra.</span><span class="sxs-lookup"><span data-stu-id="eba18-129">Right-click the zip file.</span></span>
    -  <span data-ttu-id="eba18-130">Válassza ki **Tulajdonságok** majd a **Feloldás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="eba18-130">Select **Properties** and then select **Unblock**.</span></span> 

- <span data-ttu-id="eba18-131">Bontsa ki, majd futtassa a PackageDeployer.exe fájlt.</span><span class="sxs-lookup"><span data-stu-id="eba18-131">Unzip and run PackageDeployer.exe.</span></span>

- <span data-ttu-id="eba18-132">Telepítse A potenciális ügyfelek készpénzre váltása megoldást a Sales-példányba.</span><span class="sxs-lookup"><span data-stu-id="eba18-132">Install the Prospect to Cash solution in your Sales instance.</span></span>

    - <span data-ttu-id="eba18-133">Válassza az **Office 365** telepítési típust.</span><span class="sxs-lookup"><span data-stu-id="eba18-133">Select the **Office 365** Deployment type.</span></span>
    - <span data-ttu-id="eba18-134">Válassza a **Speciális megjelenítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="eba18-134">Select **Show advanced**.</span></span>
    - <span data-ttu-id="eba18-135">Gyors telepítéshez válassza a **Régió** elemet.</span><span class="sxs-lookup"><span data-stu-id="eba18-135">For a quick installation, select a **Region**.</span></span> <span data-ttu-id="eba18-136">Ha a **Nem tudom** lehetőséget választja, a rendszer az összes régiót válasszagigkeresi, és a telepítés hosszabb ideig tart.</span><span class="sxs-lookup"><span data-stu-id="eba18-136">If you select **Don’t know**, the system searches for all regions and it will take longer to install.</span></span>
    - <span data-ttu-id="eba18-137">Adja meg egy olyan adminisztrátori felhasználó **Felhasználónevét** és **Jelszavát**, aki telepítési felhasználói jogosultságokkal rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="eba18-137">Enter **User name** and **Password** for an admin user who has the user rights to install.</span></span>

