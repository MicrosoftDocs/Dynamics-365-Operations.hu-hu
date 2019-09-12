---
title: Raktárkezelés áttekintése
description: Raktárkezelési funkció használata a raktározási folyamatok figyelésére és automatizálására.
author: ShylaThompson
manager: AnnBe
ms.date: 07/25/2019
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
ms.openlocfilehash: c900ef715b62484c1fb6576b7f0c97cdea4e4284
ms.sourcegitcommit: e286572ce94a9442a5b3076c3ff5b429be0ed512
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/06/2019
ms.locfileid: "1865136"
---
# <a name="warehouse-management-overview"></a><span data-ttu-id="c8790-103">Raktárkezelés áttekintése</span><span class="sxs-lookup"><span data-stu-id="c8790-103">Warehouse management overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c8790-104">A raktárkezelési modul a Dynamics 365 for Finance and Operations rendszerben lehetővé teszi a raktározási folyamatok kezelését a gyártási, elosztási és kiskereskedelmi vállalatokban.</span><span class="sxs-lookup"><span data-stu-id="c8790-104">The Warehouse management module for Dynamics 365 for Finance and Operations lets you manage warehouse processes in manufacturing, distribution, and retail companies.</span></span> <span data-ttu-id="c8790-105">A modul sokféle funkciót kínál a raktári létesítmények mindenkori optimális támogatásához.</span><span class="sxs-lookup"><span data-stu-id="c8790-105">This module has a wide range of features to support the warehouse facility at an optimal level, at any time.</span></span> <span data-ttu-id="c8790-106">A raktárkezelés teljes mértékben integrált a Finance and Operationsben megtalálható más üzleti folyamatokkal, például a szállítással, gyártással, minőség-ellenőrzéssel, beszerzéssel, átmozgatással, értékesítéssel és visszárukkal.</span><span class="sxs-lookup"><span data-stu-id="c8790-106">Warehouse management is fully integrated with other business processes in Finance and Operations such as transportation, manufacturing, quality control, purchase, transfer, sales, and returns.</span></span>

## <a name="get-started"></a><span data-ttu-id="c8790-107">Első lépések</span><span class="sxs-lookup"><span data-stu-id="c8790-107">Get started</span></span>
<span data-ttu-id="c8790-108">A raktárkezelés használatának megkezdéséhez meg kell adnia a raktár általános beállításait a vállalat üzleti folyamatainak támogatásához.</span><span class="sxs-lookup"><span data-stu-id="c8790-108">To start working with Warehouse management, you need to complete the setup of the general warehouse parameters to support the business processes of you company.</span></span>

- <span data-ttu-id="c8790-109">Lépjen a **Raktárkezelési paraméterek** oldalra a **Raktárkezelés** > **Beállítás** pontban a raktár általános paramétereinek beállításához.</span><span class="sxs-lookup"><span data-stu-id="c8790-109">Go to the **Warehouse management parameters** page under **Warehouse management** > **Setup** to set up general warehouse parameters.</span></span>

<span data-ttu-id="c8790-110">Bejövő és kimenő raktározási folyamat-munkafolyamatok összetevőit az üzleti igényeknek megfelelően kell konfigurálni.</span><span class="sxs-lookup"><span data-stu-id="c8790-110">You must configure components for inbound and outbound warehouse process workflows according to business requirements.</span></span> <span data-ttu-id="c8790-111">A legfontosabb összetevők, amelyeket konfigurálnia kell, a hullámsablonok, munkasablonok, munkagyűjtők és helyutasítások.</span><span class="sxs-lookup"><span data-stu-id="c8790-111">The most important components that you must configure are wave templates, work templates, work pools, and location directives.</span></span>

- [<span data-ttu-id="c8790-112">Raktár konfigurálása</span><span class="sxs-lookup"><span data-stu-id="c8790-112">Warehouse configuration</span></span>](warehouse-configuration.md)
- [<span data-ttu-id="c8790-113">Raktári munka ellenőrzése munkasablonok és helyutasítások használatával</span><span class="sxs-lookup"><span data-stu-id="c8790-113">Control warehouse work by using work templates and location directives</span></span>](control-warehouse-location-directives.md)
- [<span data-ttu-id="c8790-114">Mobileszközök beállítása raktári munkához</span><span class="sxs-lookup"><span data-stu-id="c8790-114">Set up mobile devices for warehouse work</span></span>](configure-mobile-devices-warehouse.md)
- [<span data-ttu-id="c8790-115">Helyutasítás beállítása beszerzési rendelés eltárolásához</span><span class="sxs-lookup"><span data-stu-id="c8790-115">Set up a location directive for purchase order put-away</span></span>](../transportation/tasks/set-up-location-directive-purchase-order-put-away.md)
- [<span data-ttu-id="c8790-116">A beszerzési rendelések munkasablonjának beállítása</span><span class="sxs-lookup"><span data-stu-id="c8790-116">Set up a work template for purchase orders</span></span>](./tasks/set-up-work-template-purchase-orders.md)

## <a name="warehouse-management-processes"></a><span data-ttu-id="c8790-117">Raktárkezelési folyamatok</span><span class="sxs-lookup"><span data-stu-id="c8790-117">Warehouse management processes</span></span>
- <span data-ttu-id="c8790-118">Forrásdokumentumok integrált támogatása értékesítési rendelésekhez, visszatérítésekhez, átmozgatási rendelésekhez, termelési rendelésekhez és kanbanhoz</span><span class="sxs-lookup"><span data-stu-id="c8790-118">Integrated support for source documents for sales orders, returns, transfer orders, production orders, and kanban</span></span>  
- <span data-ttu-id="c8790-119">Bejövő és kimenő anyagok lekérdezéseken alapuló, rugalmas munkafolyamat-támogatása</span><span class="sxs-lookup"><span data-stu-id="c8790-119">Flexible, inbound and outbound material workflow support based on queries</span></span>
- <span data-ttu-id="c8790-120">A Gyártási és szállítás ajánlatainak teljes integrálása</span><span class="sxs-lookup"><span data-stu-id="c8790-120">Full integration with the Manufacturing and Transportation offerings</span></span>
- <span data-ttu-id="c8790-121">Helyi rakodási korlátok és helyi térfogatmérés teljes kézben tartása</span><span class="sxs-lookup"><span data-stu-id="c8790-121">Full control of location stocking limits and location volumetrics</span></span>
- <span data-ttu-id="c8790-122">Készlettulajdonságok vezérlése a készlet állapota szerint</span><span class="sxs-lookup"><span data-stu-id="c8790-122">Inventory properties controlled by inventory status</span></span>
- <span data-ttu-id="c8790-123">Teljes köteg- és sorozatszámoscikk-támogatás</span><span class="sxs-lookup"><span data-stu-id="c8790-123">Full batch and serial item support</span></span>
- <span data-ttu-id="c8790-124">Különböző cikkek bevételezésének támogatása</span><span class="sxs-lookup"><span data-stu-id="c8790-124">Various item receiving capabilities</span></span>
- <span data-ttu-id="c8790-125">Többféle kitárolási stratégia</span><span class="sxs-lookup"><span data-stu-id="c8790-125">Multiple picking strategies</span></span>
- <span data-ttu-id="c8790-126">A következő generációs vonalkódolvasók paraméterezés nélkül működő támogatása</span><span class="sxs-lookup"><span data-stu-id="c8790-126">Out-of-the-box support for the next generation of barcode scanners</span></span>
- <span data-ttu-id="c8790-127">Raklap/tárolótípusok raktári folyamatokhoz</span><span class="sxs-lookup"><span data-stu-id="c8790-127">Pallet/container types for warehouse processes</span></span>
- <span data-ttu-id="c8790-128">Speciális leltárfunkciók</span><span class="sxs-lookup"><span data-stu-id="c8790-128">Advanced counting capabilities</span></span>
- <span data-ttu-id="c8790-129">Címkenyomtatás és címkeútvonalak Zebra ZPL támogatással</span><span class="sxs-lookup"><span data-stu-id="c8790-129">Label printing and label routing with Zebra ZPL support</span></span>
- <span data-ttu-id="c8790-130">Üzleti intelligencia integrálása a Power BI-be</span><span class="sxs-lookup"><span data-stu-id="c8790-130">Business intelligence integration into Power BI</span></span>
- <span data-ttu-id="c8790-131">Kézi és automatikus készletmozgás</span><span class="sxs-lookup"><span data-stu-id="c8790-131">Manual and automatic movement of inventory</span></span>
- <span data-ttu-id="c8790-132">Teljes mértékben integrált minőségellenőrzés (QMS)</span><span class="sxs-lookup"><span data-stu-id="c8790-132">Fully-integrated quality control (QMS)</span></span>
- <span data-ttu-id="c8790-133">Dolgozók anyagkezelésének teljes nyomon követése</span><span class="sxs-lookup"><span data-stu-id="c8790-133">Full traceability of workers' material handling</span></span>
- <span data-ttu-id="c8790-134">Kimenő hullámfeldolgozás</span><span class="sxs-lookup"><span data-stu-id="c8790-134">Outbound wave processing</span></span>
- <span data-ttu-id="c8790-135">Manuális csomagolási és automatikus tárolólétrehozási támogatás</span><span class="sxs-lookup"><span data-stu-id="c8790-135">Manual packing and automatic containerization support</span></span>
- <span data-ttu-id="c8790-136">Fürt kitárolása</span><span class="sxs-lookup"><span data-stu-id="c8790-136">Cluster picking</span></span>
- <span data-ttu-id="c8790-137">Egyszerű áttárolás</span><span class="sxs-lookup"><span data-stu-id="c8790-137">Simple cross docking</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c8790-138">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="c8790-138">Additional resources</span></span>
### <a name="whats-new-and-in-development"></a><span data-ttu-id="c8790-139">Újdonságok és fejlesztés alatt levő megoldások</span><span class="sxs-lookup"><span data-stu-id="c8790-139">What's new and in development</span></span>
<span data-ttu-id="c8790-140">Keresse fel a [Microsoft Dynamics 365 Ütemterv](https://roadmap.dynamics.com/) oldalt a már kiadott új funkciók és a kidolgozás alatt álló új szolgáltatások megtekintése érdekében.</span><span class="sxs-lookup"><span data-stu-id="c8790-140">Go to the [Microsoft Dynamics 365 Roadmap](https://roadmap.dynamics.com/) to see what new features have been released and what new features are in development.</span></span>

### <a name="blogs"></a><span data-ttu-id="c8790-141">Blogok</span><span class="sxs-lookup"><span data-stu-id="c8790-141">Blogs</span></span>
<span data-ttu-id="c8790-142">A [Microsoft Dynamics 365 blogon](https://community.dynamics.com/b/msftdynamicsblog) véleményeket, híreket és egyéb információkat talál a Raktárkezeléssel és egyéb megoldásokkal kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="c8790-142">You can find opinions, news, and other information about Warehouse management and other solutions on the [Microsoft Dynamics 365 blog](https://community.dynamics.com/b/msftdynamicsblog).</span></span>


 

