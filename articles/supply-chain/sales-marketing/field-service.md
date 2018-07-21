---
title: "Integráció a Microsoft Dynamics 365 for Field Service szolgáltatással"
description: "Ez a témakör áttekintést nyújt a Microsoft Dynamics 365 for Field Service szolgáltatással való integrációról."
author: ChristianRytt
manager: AnnBe
ms.date: 04/25/2018
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
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 841ea53f754f61c2930e77fdafc85eac72f47d7a
ms.openlocfilehash: 29e5748a1e1c381febae80d02b4ac311c3f0008e
ms.contentlocale: hu-hu
ms.lasthandoff: 07/21/2018

---


# <a name="integration-with-microsoft-dynamics-365-for-field-service"></a><span data-ttu-id="20bbd-103">Integráció a Microsoft Dynamics 365 for Field Service szolgáltatással</span><span class="sxs-lookup"><span data-stu-id="20bbd-103">Integration with Microsoft Dynamics 365 for Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="20bbd-104">A Microsoft Dynamics 365 for Finance and Operations lehetővé teszik az üzleti folyamatok szinkronizálását a Finance and Operations és a Microsoft Dynamics 365 for Field Service között.</span><span class="sxs-lookup"><span data-stu-id="20bbd-104">Microsoft Dynamics 365 for Finance and Operations enables synchronization of business processes between Finance and Operations and Microsoft Dynamics 365 for Field Service.</span></span> <span data-ttu-id="20bbd-105">Az integrációs forgatókönyvek konfigurálása bővíthető adatintegrációs sablonok és a Common Data Service (CDS) segítségével történik az üzleti folyamatok szinkronizálása érdekében.</span><span class="sxs-lookup"><span data-stu-id="20bbd-105">The integration scenarios are configured by using extensible Data integrator templates and the Common Data Service (CDS) to enable the synchronization of business processes.</span></span>

<span data-ttu-id="20bbd-106">[![Üzleti folyamatok szinkronizálása a Finance and Operations és a Field Service között](./media/field-service-integration.png)](./media/field-service-integration.png)</span><span class="sxs-lookup"><span data-stu-id="20bbd-106">[![Synchronization of business processes between Finance and Operations and Field Service](./media/field-service-integration.png)](./media/field-service-integration.png)</span></span>

<span data-ttu-id="20bbd-107">A Field Service és a Finance and Operations közötti integráció első fázisa a Field Service szolgáltatásban lévő munkarendelések és szerződések a Finance and Operations szolgáltatásban történő számlázásának lehetővé tételére irányul.</span><span class="sxs-lookup"><span data-stu-id="20bbd-107">The first phase  of the integration between Field Service and Finance and Operations is focused on enabling work orders and agreements in Field Service to be invoiced in Finance and Operations.</span></span> <span data-ttu-id="20bbd-108">A támogatott forgalom a Field Service-ben kezdődik, ahol a munkarendelésekből származó információk értékesítési rendelésekként szinkronizálódnak a Finance and Operations szolgáltatásba.</span><span class="sxs-lookup"><span data-stu-id="20bbd-108">The supported flow starts in Field Service, where information from work orders is synchronized to Finance and Operations as sales orders.</span></span> <span data-ttu-id="20bbd-109">A Finance and Operations szolgáltatásban megtörténik az értékesítési rendelések számlázása számlabizonylatok létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="20bbd-109">In Finance and Operations, the sales orders are invoiced to generate invoice documents.</span></span> <span data-ttu-id="20bbd-110">Emellett a Field Service-ben lévő szerződéses számlákban lévő információk szinkronizálódnak a Finance and Operations szolgáltatásba.</span><span class="sxs-lookup"><span data-stu-id="20bbd-110">In addition, the information from Field Service agreement invoices is synchronized to Finance and Operations.</span></span> <span data-ttu-id="20bbd-111">A Microsoft Dynamics 365 adatintegrátor testreszabható projektek használatával szinkronizálja az adatokat.</span><span class="sxs-lookup"><span data-stu-id="20bbd-111">The Microsoft Dynamics 365 Data integrator synchronizes data by using customizable projects.</span></span> <span data-ttu-id="20bbd-112">Szabványos sablonok használhatók egyéni integrációs projektek létrehozására, ahol további szabványos és egyéni mezők, valamint entitások is leképezhetők az integráció módosítására és speciális követelmények teljesítésére.</span><span class="sxs-lookup"><span data-stu-id="20bbd-112">Standard templates can be used to create custom integration projects where additional standard and custom fields, and also entities, can be mapped to adjust the integration and meet specific requirements.</span></span>

<span data-ttu-id="20bbd-113">A Field Service és a Finance and Operations közötti integráció első fázisa a következő elemek szinkronizálását teszi lehetővé:</span><span class="sxs-lookup"><span data-stu-id="20bbd-113">The first phase of the integration between Field Service and Finance and Operations enables synchronization of the following items:</span></span>

- [<span data-ttu-id="20bbd-114">Termékek a Finance and Operations szolgáltatásból termékekké a Field Service szolgáltatásban, amelyek terméktípus-információkat tartalmaznak</span><span class="sxs-lookup"><span data-stu-id="20bbd-114">Products in Finance and Operations to products in Field Service that include Product Type information</span></span>](field-service-product.md)
- [<span data-ttu-id="20bbd-115">Finance and Operations-munkarendelések Field Service vevői rendelésekké</span><span class="sxs-lookup"><span data-stu-id="20bbd-115">Work orders in Field Service to sales orders in Finance and Operations</span></span>](field-service-work-order.md)
- [<span data-ttu-id="20bbd-116">Finance and Operations-számlák Field Service szabadszöveges számlákká</span><span class="sxs-lookup"><span data-stu-id="20bbd-116">Invoices in Field Service to free text invoices in Finance and Operations</span></span>](field-service-invoice.md)

<span data-ttu-id="20bbd-117">A Field Service és a Finance and Operations közötti szinkronizálás példamódjának megtekintéséhez tekintse meg a rövid YouTube videót [Munkarendelések szinkronizálása a Dynamics 365 for Field Service és a Finance and Operations között](https://www.youtube.com/watch?v=hAB4TDVMjxU).</span><span class="sxs-lookup"><span data-stu-id="20bbd-117">To see an example of how you can synchronize a work order between Field Service and Finance and Operations, watch the short YouTube video [Synchronize a work order between Dynamics 365 for Field Service and Finance and Operations](https://www.youtube.com/watch?v=hAB4TDVMjxU).</span></span>

[![](https://img.youtube.com/vi/hAB4TDVMjxU/0.jpg)](https://www.youtube.com/watch?v=hAB4TDVMjxU)

## <a name="system-requirements-for-finance-and-operations"></a><span data-ttu-id="20bbd-118">Rendszerigény a Finance and Operations rendszerhez</span><span class="sxs-lookup"><span data-stu-id="20bbd-118">System requirements for Finance and Operations</span></span>
<span data-ttu-id="20bbd-119">A Field Service integráció a következő verziókat támogatja:</span><span class="sxs-lookup"><span data-stu-id="20bbd-119">Field Service integration supports the following versions:</span></span>

### <a name="dynamics-365-for-finance-and-operations-version-80-april-2018-or-later"></a><span data-ttu-id="20bbd-120">Dynamics 365 for Finance and Operations 8.0-es verzió (2018. április) vagy újabb</span><span class="sxs-lookup"><span data-stu-id="20bbd-120">Dynamics 365 for Finance and Operations version 8.0 (April 2018) or later</span></span>

- <span data-ttu-id="20bbd-121">A Dynamics 365 for Finance and Operations 8.0 verziója (2018. április) 2018 áprilisában jelent, meg, az alkalmazás buildszáma 8.0.30.8020, 15-ös platformfrissítés (7.0.4841.35234).</span><span class="sxs-lookup"><span data-stu-id="20bbd-121">Dynamics 365 for Finance and Operations version 8.0 (April 2018) was released in April 2018 and has an application build number 8.0.30.8020 with Platform Update 15 (7.0.4841.35234).</span></span> 

## <a name="system-requirements-for-field-service"></a><span data-ttu-id="20bbd-122">A Field Service rendszerkövetelményei</span><span class="sxs-lookup"><span data-stu-id="20bbd-122">System requirements for Field Service</span></span>
<span data-ttu-id="20bbd-123">A Field Service integrációs megoldás használatához telepítenie kell a következő összetevőket:</span><span class="sxs-lookup"><span data-stu-id="20bbd-123">To use the Field Service integration solution, you must install the following components:</span></span>

### <a name="microsoft-dynamics-365-for-field-service-90-or-later"></a><span data-ttu-id="20bbd-124">Microsoft Dynamics 365 for Field Service 9.0 vagy újabb</span><span class="sxs-lookup"><span data-stu-id="20bbd-124">Microsoft Dynamics 365 for Field Service 9.0 or later</span></span>

- <span data-ttu-id="20bbd-125">Dynamics 365 for Field Service, verzió: 1612 (9.0.1.733) (DB 9.0.1.733) online vagy későbbi verzió.</span><span class="sxs-lookup"><span data-stu-id="20bbd-125">Dynamics 365 for Field Service version 1612 (9.0.1.733) (DB 9.0.1.733) online or a later version.</span></span>
- <span data-ttu-id="20bbd-126">A potenciális ügyfelek készpénzre váltása (P2C) megoldás Dynamics 365 szolgáltatáshoz, 1.15.0.1 vagy későbbi verzió.</span><span class="sxs-lookup"><span data-stu-id="20bbd-126">Prospect to Cash (P2C) solution for Dynamics 365, version 1.15.0.1 or a later version.</span></span> <span data-ttu-id="20bbd-127">A megoldás letölthető az [AppSource](https://appsource.microsoft.com/en-us/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3)-ból.</span><span class="sxs-lookup"><span data-stu-id="20bbd-127">The solution is available for download from [AppSource](https://appsource.microsoft.com/en-us/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).</span></span>
- <span data-ttu-id="20bbd-128">Field Service integrációs megoldás Dynamics 365-höz, 1.0.0.0 vagy későbbi verzió..</span><span class="sxs-lookup"><span data-stu-id="20bbd-128">Field Service integration solution for Dynamics 365, version 1.0.0.0 or a later version.</span></span> <span data-ttu-id="20bbd-129">A megoldás letölthető az [AppSource](https://appsource.microsoft.com/en-us/product/dynamics-365/mscrm.p2cfieldserviceintegration)-ból.</span><span class="sxs-lookup"><span data-stu-id="20bbd-129">The solution is available for download from [AppSource](https://appsource.microsoft.com/en-us/product/dynamics-365/mscrm.p2cfieldserviceintegration).</span></span>

