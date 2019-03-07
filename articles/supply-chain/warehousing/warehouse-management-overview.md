---
title: Raktárkezelés
description: Raktárkezelési funkció használata a raktározási folyamatok figyelésére és automatizálására.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7c9613070e077bced4b272b136985de5f4ddbdd0
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "335255"
---
# <a name="warehouse-management"></a><span data-ttu-id="36835-103">Raktárkezelés</span><span class="sxs-lookup"><span data-stu-id="36835-103">Warehouse management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="36835-104">A raktárkezelési modul a Dynamics 365 for Finance and Operations rendszerben lehetővé teszi a raktározási folyamatok kezelését a gyártási, elosztási és kiskereskedelmi vállalatokban.</span><span class="sxs-lookup"><span data-stu-id="36835-104">The Warehouse management module for Dynamics 365 for Finance and Operations lets you manage warehouse processes in manufacturing, distribution, and retail companies.</span></span> <span data-ttu-id="36835-105">A modul sokféle funkciót kínál a raktári létesítmények mindenkori optimális támogatásához.</span><span class="sxs-lookup"><span data-stu-id="36835-105">This module has a wide range of features to support the warehouse facility at an optimal level, at any time.</span></span> <span data-ttu-id="36835-106">A raktárkezelés teljes mértékben integrált a Finance and Operationsben megtalálható más üzleti folyamatokkal, például a szállítással, gyártással, minőség-ellenőrzéssel, beszerzéssel, átmozgatással, értékesítéssel és visszárukkal.</span><span class="sxs-lookup"><span data-stu-id="36835-106">Warehouse management is fully integrated with other business processes in Finance and Operations such as transportation, manufacturing, quality control, purchase, transfer, sales, and returns.</span></span>

## <a name="get-started"></a><span data-ttu-id="36835-107">Első lépések</span><span class="sxs-lookup"><span data-stu-id="36835-107">Get started</span></span>
<span data-ttu-id="36835-108">A raktárkezelés használatának megkezdéséhez meg kell adnia a raktár általános beállításait a vállalat üzleti folyamatainak támogatásához.</span><span class="sxs-lookup"><span data-stu-id="36835-108">To start working with Warehouse management, you need to complete the setup of the general warehouse parameters to support the business processes of you company.</span></span>

- <span data-ttu-id="36835-109">Lépjen a **Raktárkezelési paraméterek** oldalra a **Raktárkezelés** > **Beállítás** pontban a raktár általános paramétereinek beállításához.</span><span class="sxs-lookup"><span data-stu-id="36835-109">Go to the **Warehouse management parameters** page under **Warehouse management** > **Setup** to set up general warehouse parameters.</span></span>

<span data-ttu-id="36835-110">Bejövő és kimenő raktározási folyamat-munkafolyamatok összetevőit az üzleti igényeknek megfelelően kell konfigurálni.</span><span class="sxs-lookup"><span data-stu-id="36835-110">You must configure components for inbound and outbound warehouse process workflows according to business requirements.</span></span> <span data-ttu-id="36835-111">A legfontosabb összetevők, amelyeket konfigurálnia kell, a hullámsablonok, munkasablonok, munkagyűjtők és helyutasítások.</span><span class="sxs-lookup"><span data-stu-id="36835-111">The most important components that you must configure are wave templates, work templates, work pools, and location directives.</span></span>

- [<span data-ttu-id="36835-112">Raktár konfigurálása</span><span class="sxs-lookup"><span data-stu-id="36835-112">Warehouse configuration</span></span>](warehouse-configuration.md)
- [<span data-ttu-id="36835-113">Raktári munka ellenőrzése munkasablonok és helyutasítások használatával</span><span class="sxs-lookup"><span data-stu-id="36835-113">Control warehouse work by using work templates and location directives</span></span>](control-warehouse-location-directives.md)
- [<span data-ttu-id="36835-114">Mobileszközök beállítása raktári munkához</span><span class="sxs-lookup"><span data-stu-id="36835-114">Set up mobile devices for warehouse work</span></span>](configure-mobile-devices-warehouse.md)
- [<span data-ttu-id="36835-115">Helyutasítás beállítása beszerzési rendelés eltárolásához</span><span class="sxs-lookup"><span data-stu-id="36835-115">Set up a location directive for purchase order put-away</span></span>](../transportation/tasks/set-up-location-directive-purchase-order-put-away.md)
- [<span data-ttu-id="36835-116">A beszerzési rendelések munkasablonjának beállítása</span><span class="sxs-lookup"><span data-stu-id="36835-116">Set up a work template for purchase orders</span></span>](./tasks/set-up-work-template-purchase-orders.md)

## <a name="warehouse-management-processes"></a><span data-ttu-id="36835-117">Raktárkezelési folyamatok</span><span class="sxs-lookup"><span data-stu-id="36835-117">Warehouse management processes</span></span>
- <span data-ttu-id="36835-118">Forrásdokumentumok integrált támogatása értékesítési rendelésekhez, visszatérítésekhez, átmozgatási rendelésekhez, termelési rendelésekhez és kanbanhoz</span><span class="sxs-lookup"><span data-stu-id="36835-118">Integrated support for source documents for sales orders, returns, transfer orders, production orders, and kanban</span></span>  
- <span data-ttu-id="36835-119">Bejövő és kimenő anyagok lekérdezéseken alapuló, rugalmas munkafolyamat-támogatása</span><span class="sxs-lookup"><span data-stu-id="36835-119">Flexible, inbound and outbound material workflow support based on queries</span></span>
- <span data-ttu-id="36835-120">A Gyártási és szállítás ajánlatainak teljes integrálása</span><span class="sxs-lookup"><span data-stu-id="36835-120">Full integration with the Manufacturing and Transportation offerings</span></span>
- <span data-ttu-id="36835-121">Helyi rakodási korlátok és helyi térfogatmérés teljes kézben tartása</span><span class="sxs-lookup"><span data-stu-id="36835-121">Full control of location stocking limits and location volumetrics</span></span>
- <span data-ttu-id="36835-122">Készlettulajdonságok vezérlése a készlet állapota szerint</span><span class="sxs-lookup"><span data-stu-id="36835-122">Inventory properties controlled by inventory status</span></span>
- <span data-ttu-id="36835-123">Teljes köteg- és sorozatszámoscikk-támogatás</span><span class="sxs-lookup"><span data-stu-id="36835-123">Full batch and serial item support</span></span>
- <span data-ttu-id="36835-124">Különböző cikkek bevételezésének támogatása</span><span class="sxs-lookup"><span data-stu-id="36835-124">Various item receiving capabilities</span></span>
- <span data-ttu-id="36835-125">Többféle kitárolási stratégia</span><span class="sxs-lookup"><span data-stu-id="36835-125">Multiple picking strategies</span></span>
- <span data-ttu-id="36835-126">A következő generációs vonalkódolvasók paraméterezés nélkül működő támogatása</span><span class="sxs-lookup"><span data-stu-id="36835-126">Out-of-the-box support for the next generation of barcode scanners</span></span>
- <span data-ttu-id="36835-127">Raklap/tárolótípusok raktári folyamatokhoz</span><span class="sxs-lookup"><span data-stu-id="36835-127">Pallet/container types for warehouse processes</span></span>
- <span data-ttu-id="36835-128">Speciális leltárfunkciók</span><span class="sxs-lookup"><span data-stu-id="36835-128">Advanced counting capabilities</span></span>
- <span data-ttu-id="36835-129">Címkenyomtatás és címkeútvonalak Zebra ZPL támogatással</span><span class="sxs-lookup"><span data-stu-id="36835-129">Label printing and label routing with Zebra ZPL support</span></span>
- <span data-ttu-id="36835-130">Üzleti intelligencia integrálása a Power BI-be</span><span class="sxs-lookup"><span data-stu-id="36835-130">Business intelligence integration into Power BI</span></span>
- <span data-ttu-id="36835-131">Kézi és automatikus készletmozgás</span><span class="sxs-lookup"><span data-stu-id="36835-131">Manual and automatic movement of inventory</span></span>
- <span data-ttu-id="36835-132">Teljes mértékben integrált minőségellenőrzés (QMS)</span><span class="sxs-lookup"><span data-stu-id="36835-132">Fully-integrated quality control (QMS)</span></span>
- <span data-ttu-id="36835-133">Dolgozók anyagkezelésének teljes nyomon követése</span><span class="sxs-lookup"><span data-stu-id="36835-133">Full traceability of workers' material handling</span></span>
- <span data-ttu-id="36835-134">Kimenő hullámfeldolgozás</span><span class="sxs-lookup"><span data-stu-id="36835-134">Outbound wave processing</span></span>
- <span data-ttu-id="36835-135">Manuális csomagolási és automatikus tárolólétrehozási támogatás</span><span class="sxs-lookup"><span data-stu-id="36835-135">Manual packing and automatic containerization support</span></span>
- <span data-ttu-id="36835-136">Fürt kitárolása</span><span class="sxs-lookup"><span data-stu-id="36835-136">Cluster picking</span></span>
- <span data-ttu-id="36835-137">Egyszerű áttárolás</span><span class="sxs-lookup"><span data-stu-id="36835-137">Simple cross docking</span></span>

## <a name="additional-resources"></a><span data-ttu-id="36835-138">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="36835-138">Additional resources</span></span>
### <a name="whats-new-and-in-development"></a><span data-ttu-id="36835-139">Újdonságok és fejlesztés alatt levő megoldások</span><span class="sxs-lookup"><span data-stu-id="36835-139">What's new and in development</span></span>
<span data-ttu-id="36835-140">Keresse fel a [Microsoft Dynamics 365 Ütemterv](https://roadmap.dynamics.com/) oldalt a már kiadott új funkciók és a kidolgozás alatt álló új szolgáltatások megtekintése érdekében.</span><span class="sxs-lookup"><span data-stu-id="36835-140">Go to the [Microsoft Dynamics 365 Roadmap](https://roadmap.dynamics.com/) to see what new features have been released and what new features are in development.</span></span>

### <a name="blogs"></a><span data-ttu-id="36835-141">Blogok</span><span class="sxs-lookup"><span data-stu-id="36835-141">Blogs</span></span>
<span data-ttu-id="36835-142">A [Microsoft Dynamics 365 blogon](https://community.dynamics.com/b/msftdynamicsblog) véleményeket, híreket és egyéb információkat talál a Raktárkezeléssel és egyéb megoldásokkal kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="36835-142">You can find opinions, news, and other information about Warehouse management and other solutions on the [Microsoft Dynamics 365 blog](https://community.dynamics.com/b/msftdynamicsblog).</span></span>


 

