---
title: "A potenciális ügyfelek készpénzre váltása"
description: "A témakör áttekintést nyújt A potenciális ügyfelek készpénzre váltása megoldásról a Dynamics 365 for Sales és a Dynamics 365 for Finance and Operations, Enterprise edition szolgáltatásokban."
author: YuyuScheller
manager: AnnBe
ms.date: 07/12/2017
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
ms.author: YuyuScheller
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 2c82cc2cb88828e1828ce227e8c3ccd457a3df4d
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---

# <a name="prospect-to-cash"></a><span data-ttu-id="b160d-103">A potenciális ügyfelek készpénzre váltása</span><span class="sxs-lookup"><span data-stu-id="b160d-103">Prospect to cash</span></span>  

[!include[banner](../includes/banner.md)]

<span data-ttu-id="b160d-104">A potenciális ügyfelek készpénzre váltása megoldás az [Adatintegrátor](https://docs.microsoft.com/en-us/common-data-service/entity-reference/dynamics-365-integration) segítségével szinkronizálja az adatokat a Dynamics 365 Finance and Operations és a Dynamics 365 for Sales példányai között a Common Data Service-környezetben.</span><span class="sxs-lookup"><span data-stu-id="b160d-104">The Prospect to cash solution uses [Data Integrator](https://docs.microsoft.com/en-us/common-data-service/entity-reference/dynamics-365-integration) to synchronize data across Dynamics 365 Finance and Operations or Dynamics 365 for Sales instances via the Common Data Service.</span></span> <span data-ttu-id="b160d-105">Az Adatintegrátorban rendelkezésre álló A potenciális ügyfelek készpénzre váltása sablonok lehetővé teszik a termék-, ügyfél-, kapcsolatfelvételi és értékesítési ajánlatokra vnatkozó adatok áramlását a Dynamics 365 for Finance and Operations és a Dynamics 365 for Sales között.</span><span class="sxs-lookup"><span data-stu-id="b160d-105">The Prospect to cash templates available with the Data Integrator enable the flow of product, account, contact, and sales quote data between Dynamics 365 for Finance and Operations and Dynamics 365 for Sales.</span></span> <span data-ttu-id="b160d-106">Miközben az adatok áramlanak a Finance and Operations és a Dynamics 365 for Sales között, Ön értékesítési és marketingtevékenységeket végezhet a Dynamics 365 for Sales programban, illetve kezelheti a megrendelések teljesítését a Finance and Operations készletkezelésével.</span><span class="sxs-lookup"><span data-stu-id="b160d-106">While the data is flowing between Finance and Operations and Dynamics 365 for Sales, you can carry out sales and marketing activities in Dynamics 365 for Sales and handle the order fulfillment with inventory management in Finance and Operations.</span></span> 

<span data-ttu-id="b160d-107">Ez a megoldás integrációt nyújt az alábbi területeken:</span><span class="sxs-lookup"><span data-stu-id="b160d-107">This solution provides integration in the following areas:</span></span> 

-   <span data-ttu-id="b160d-108">Dynamics 365 for Sales-fiókok fenntartása és azok szinkronizálása a Finance and Operations szolgáltatással.</span><span class="sxs-lookup"><span data-stu-id="b160d-108">Maintain accounts in Dynamics 365 for Sales and sync them to Finance and Operations.</span></span>
-   <span data-ttu-id="b160d-109">Dynamics 365 for Sales-névjegyek fenntartása és azok szinkronizálása a Finance and Operations szolgáltatással.</span><span class="sxs-lookup"><span data-stu-id="b160d-109">Maintain contacts in Dynamics 365 for Sales and sync them to Finance and Operations.</span></span>
-   <span data-ttu-id="b160d-110">Értékesítési ajánlatok létrehozása a Dynamics 365 for Sales-ben és azok szinkronizálása a Finance and Operations szolgáltatással.</span><span class="sxs-lookup"><span data-stu-id="b160d-110">Create sales quotes in Dynamics 365 for Sales and sync them to Finance and Operations.</span></span>
-   <span data-ttu-id="b160d-111">Finance and Operations-termékek fenntartása és azok szinkronizálása a Dynamics 365 for Sales szolgáltatással.</span><span class="sxs-lookup"><span data-stu-id="b160d-111">Maintain products in Finance and Operations and sync them to Dynamics 365 for Sales.</span></span>


