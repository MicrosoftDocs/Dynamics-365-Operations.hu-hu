---
title: Adószámítási szolgáltatás (előzetes verzió)
description: Ez a témakör az adószámítási szolgáltatás általános hatókörét és jellemzőit ismerteti.
author: wangchen
ms.date: 03/02/2021
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
ms.openlocfilehash: 518d3fda7b97e55d23beea6a1ba0e50b44a7aa0e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818224"
---
# <a name="tax-calculation-service-preview"></a><span data-ttu-id="2352f-103">Adószámítási szolgáltatás (előzetes verzió)</span><span class="sxs-lookup"><span data-stu-id="2352f-103">Tax calculation service (Preview)</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="2352f-104">Az adószámítási szolgáltatás egy hiperskálázható több-bérlős szolgáltatás, amely lehetővé teszi a Global Tax Engine számára, hogy automatizálja és egyszerűsítse az adómeghatározási és számítási folyamatot.</span><span class="sxs-lookup"><span data-stu-id="2352f-104">The tax calculation service is a hyper-scalable multitenant service that enables the global tax engine to automate and simplify the tax determination and calculation process.</span></span> <span data-ttu-id="2352f-105">Az adómotor teljesen konfigurálható.</span><span class="sxs-lookup"><span data-stu-id="2352f-105">The tax engine is fully configurable.</span></span> <span data-ttu-id="2352f-106">A konfigurálható elemek közé tartozik többek között az adóköteles adatmodell, az adókód, az adóalkalmazási mátrix és az adószámítási képlet.</span><span class="sxs-lookup"><span data-stu-id="2352f-106">The elements that can be configured include, but aren't limited to, the taxable data model, tax code, tax applicability matrix, and tax calculation formula.</span></span> <span data-ttu-id="2352f-107">Az adómotor a Microsoft Azure alapszolgáltatási platformon fut, és modern technológiát és exponenciális méretezhetőséget kínál.</span><span class="sxs-lookup"><span data-stu-id="2352f-107">The tax engine runs on the Microsoft Azure core services platform, and offers modern technology and exponential scalability.</span></span>

<span data-ttu-id="2352f-108">Az adószámítási szolgáltatás integrálva van a Dynamics 365 Finance és a Dynamics 365 Supply Chain Management szolgáltatásokkal.</span><span class="sxs-lookup"><span data-stu-id="2352f-108">The tax calculation service integrates with Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="2352f-109">Végül integrálva lesz a Dynamics 365 Project Operations, Dynamics 365 Commerce és más saját és harmadik féltől származó alkalmazásokkal is.</span><span class="sxs-lookup"><span data-stu-id="2352f-109">Eventually, it will also integrate with Dynamics 365 Project Operations, Dynamics 365 Commerce, and other first-party and third-party applications.</span></span>

<span data-ttu-id="2352f-110">Az adószámítási szolgáltatás egy Microsoft-alapú adómotor, amely exponenciális méretezhetőséget kínál.</span><span class="sxs-lookup"><span data-stu-id="2352f-110">The tax calculation service is a Microsoft-based tax engine that offers exponential scalability.</span></span> <span data-ttu-id="2352f-111">A következő feladatok elvégzésében segíthet Önnek:</span><span class="sxs-lookup"><span data-stu-id="2352f-111">It can help you perform the following tasks:</span></span>

- <span data-ttu-id="2352f-112">Konfigurálhatja az adószámítási szolgáltatást a Regulatory Configuration Services (RCS) szolgáltatáson keresztül.</span><span class="sxs-lookup"><span data-stu-id="2352f-112">Configure the tax calculation service through Regulatory Configuration Service (RCS).</span></span> <span data-ttu-id="2352f-113">Az RCS az elektronikus jelentéskészítési (ER) tervező továbbfejlesztett változata, és önálló szolgáltatásként érhető el.</span><span class="sxs-lookup"><span data-stu-id="2352f-113">RCS is an enhanced version of the Electronic reporting (ER) designer and is available as a standalone service.</span></span>
- <span data-ttu-id="2352f-114">Konfigurálhatja az adómátrixot az adókódok és adómértékek automatikus meghatározásához.</span><span class="sxs-lookup"><span data-stu-id="2352f-114">Configure the tax matrix to automatically determine tax codes and rates.</span></span>
- <span data-ttu-id="2352f-115">Konfigurálhatja az adószám automatikus meghatározásához.</span><span class="sxs-lookup"><span data-stu-id="2352f-115">Configure the tax matrix to automatically determine the tax registration number.</span></span>
- <span data-ttu-id="2352f-116">Konfigurálhatja az adószámítás tervezőjét képletek és feltételek meghatározására.</span><span class="sxs-lookup"><span data-stu-id="2352f-116">Configure the tax calculation designer to define formulas and conditions.</span></span>
- <span data-ttu-id="2352f-117">Megoszthatja az adómeghatározási és számítási megoldást jogi személyek között.</span><span class="sxs-lookup"><span data-stu-id="2352f-117">Share the tax determination and calculation solution across legal entities.</span></span>

<span data-ttu-id="2352f-118">Az adószámítási szolgáltatás használatához telepítse a projektből származó adószámítási szolgáltatásbővítményt az Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="2352f-118">To use the tax calculation service, install the tax calculation service add-in from your project in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="2352f-119">Ezután fejezze be a beállítást az RCS-ben, és engedélyezze az adószámítási szolgáltatást a Finance és a Supply Chain Management alkalmazásokban.</span><span class="sxs-lookup"><span data-stu-id="2352f-119">Then complete the setup in RCS, and enable the tax calculation service in Finance and Supply Chain Management.</span></span> <span data-ttu-id="2352f-120">További tájékoztatás: [Első lépések az adószolgáltatással](https://go.microsoft.com/fwlink/?linkid=2138482).</span><span class="sxs-lookup"><span data-stu-id="2352f-120">For more information, see [Get started with tax service](https://go.microsoft.com/fwlink/?linkid=2138482).</span></span>

## <a name="availability"></a><span data-ttu-id="2352f-121">Elérhetőség</span><span class="sxs-lookup"><span data-stu-id="2352f-121">Availability</span></span>

<span data-ttu-id="2352f-122">Az adószámítási szolgáltatás csak tesztkörnyezetben és kiválasztott ügyfelek számára érhető el egy nyilvános előzetes programon keresztül.</span><span class="sxs-lookup"><span data-stu-id="2352f-122">The tax calculation service is available only in sandbox environments and to selected customers, through a public preview program.</span></span> <span data-ttu-id="2352f-123">Végül általánosan elérhetővé válik minden ügyfél számára és éles környezetekben is.</span><span class="sxs-lookup"><span data-stu-id="2352f-123">Eventually, it will become generally available to all customers and in production environments.</span></span>

<span data-ttu-id="2352f-124">Az adószámítási szolgáltatásban továbbra is új funkciók kerülnek szolgáltatásra.</span><span class="sxs-lookup"><span data-stu-id="2352f-124">New features will continue to be delivered in the tax calculation service.</span></span> <span data-ttu-id="2352f-125">Ezért győződjön meg róla, hogy gyakran ellenőrizze a legfrissebb dokumentációt, hogy megismerje a támogatott szolgáltatások kiterjedését és hatókörét.</span><span class="sxs-lookup"><span data-stu-id="2352f-125">Therefore, be sure to check the most up-to-date documentation often to learn about the coverage and scope of supported features.</span></span>

<span data-ttu-id="2352f-126">Az adószámítási szolgáltatás a következő Azure-földrajzi területeken van telepítve.</span><span class="sxs-lookup"><span data-stu-id="2352f-126">The tax calculation service is deployed in the following Azure geographies.</span></span> <span data-ttu-id="2352f-127">Más Azure földrajzi területeken is be lesz vezetve az ügyfelek igényeinek megfelelően:</span><span class="sxs-lookup"><span data-stu-id="2352f-127">It will also be deployed to more Azure geographies, based on customer needs:</span></span>

- <span data-ttu-id="2352f-128">Amerikai Egyesült Államok</span><span class="sxs-lookup"><span data-stu-id="2352f-128">United States</span></span>
- <span data-ttu-id="2352f-129">Európa</span><span class="sxs-lookup"><span data-stu-id="2352f-129">Europe</span></span>
- <span data-ttu-id="2352f-130">Franciaország</span><span class="sxs-lookup"><span data-stu-id="2352f-130">France</span></span>
- <span data-ttu-id="2352f-131">Egyesült Királyság</span><span class="sxs-lookup"><span data-stu-id="2352f-131">United Kingdom</span></span>

> [!NOTE]
> <span data-ttu-id="2352f-132">Az adószámítási szolgáltatás nem támogatja a Dynamics 365 helyszíni telepítését.</span><span class="sxs-lookup"><span data-stu-id="2352f-132">The tax calculation service doesn't support on-premises deployments of Dynamics 365.</span></span> <span data-ttu-id="2352f-133">Nem támogatja a korábbi verziókat sem, például a Dynamics AX 2012-t.</span><span class="sxs-lookup"><span data-stu-id="2352f-133">It also doesn't support earlier versions, such as Dynamics AX 2012.</span></span>

## <a name="feature-highlights"></a><span data-ttu-id="2352f-134">A funkció újdonságai</span><span class="sxs-lookup"><span data-stu-id="2352f-134">Feature highlights</span></span>

- <span data-ttu-id="2352f-135">Konfigurálható adómátrix az adókódok és adó automatikus meghatározásához és számításához</span><span class="sxs-lookup"><span data-stu-id="2352f-135">A configurable tax matrix to automatically determine and calculate tax</span></span>
- <span data-ttu-id="2352f-136">Több forgalmi adó (ÁFA) nyilvántartási szám támogatása</span><span class="sxs-lookup"><span data-stu-id="2352f-136">Support for multiple value-added tax (VAT) registration numbers</span></span>
- <span data-ttu-id="2352f-137">Átmozgatási rendelés támogatása az adó meghatározásához és kiszámításához</span><span class="sxs-lookup"><span data-stu-id="2352f-137">Transfer order support for tax determination and calculation</span></span>
- <span data-ttu-id="2352f-138">Átmozgatási rendelés támogatása több áfaregisztrációs szám meghatározásához</span><span class="sxs-lookup"><span data-stu-id="2352f-138">Transfer order support for determination of multiple VAT registration numbers</span></span>

## <a name="supported-transactions"></a><span data-ttu-id="2352f-139">Támogatott tranzakciók</span><span class="sxs-lookup"><span data-stu-id="2352f-139">Supported transactions</span></span>

<span data-ttu-id="2352f-140">Az adószámítási szolgáltatást jogi személy és tranzakció engedélyezheti.</span><span class="sxs-lookup"><span data-stu-id="2352f-140">The tax calculation service can be enabled by legal entity and transaction.</span></span> <span data-ttu-id="2352f-141">A varázsló a következő tranzakciókat támogatja:</span><span class="sxs-lookup"><span data-stu-id="2352f-141">The following transactions are supported:</span></span>

- <span data-ttu-id="2352f-142">Értékesítési folyamat</span><span class="sxs-lookup"><span data-stu-id="2352f-142">Sales process</span></span>

    - <span data-ttu-id="2352f-143">Értékesítési ajánlat</span><span class="sxs-lookup"><span data-stu-id="2352f-143">Sales quotation</span></span>
    - <span data-ttu-id="2352f-144">Értékesítési rendelés</span><span class="sxs-lookup"><span data-stu-id="2352f-144">Sales order</span></span>
    - <span data-ttu-id="2352f-145">Visszaigazolás</span><span class="sxs-lookup"><span data-stu-id="2352f-145">Confirmation</span></span>
    - <span data-ttu-id="2352f-146">Kitárolási lista</span><span class="sxs-lookup"><span data-stu-id="2352f-146">Picking list</span></span>
    - <span data-ttu-id="2352f-147">Szállítólevél</span><span class="sxs-lookup"><span data-stu-id="2352f-147">Packing slip</span></span>
    - <span data-ttu-id="2352f-148">Értékesítési számla</span><span class="sxs-lookup"><span data-stu-id="2352f-148">Sales invoice</span></span>
    - <span data-ttu-id="2352f-149">Jóváírás</span><span class="sxs-lookup"><span data-stu-id="2352f-149">Credit note</span></span>
    - <span data-ttu-id="2352f-150">Visszárurendelés</span><span class="sxs-lookup"><span data-stu-id="2352f-150">Return order</span></span>
    - <span data-ttu-id="2352f-151">Fejléc vegyes költségek</span><span class="sxs-lookup"><span data-stu-id="2352f-151">Header miscellaneous charge</span></span>
    - <span data-ttu-id="2352f-152">Sor vegyes költsége</span><span class="sxs-lookup"><span data-stu-id="2352f-152">Line miscellaneous charge</span></span>

- <span data-ttu-id="2352f-153">Beszerzési folyamat</span><span class="sxs-lookup"><span data-stu-id="2352f-153">Purchase process</span></span>

    - <span data-ttu-id="2352f-154">Beszerzési rendelés</span><span class="sxs-lookup"><span data-stu-id="2352f-154">Purchase order</span></span>
    - <span data-ttu-id="2352f-155">Visszaigazolás</span><span class="sxs-lookup"><span data-stu-id="2352f-155">Confirmation</span></span>
    - <span data-ttu-id="2352f-156">Bevételezések listája</span><span class="sxs-lookup"><span data-stu-id="2352f-156">Receipts list</span></span>
    - <span data-ttu-id="2352f-157">Termékbevételezés</span><span class="sxs-lookup"><span data-stu-id="2352f-157">Product receipt</span></span>
    - <span data-ttu-id="2352f-158">Beszerzési számla</span><span class="sxs-lookup"><span data-stu-id="2352f-158">Purchase invoice</span></span>
    - <span data-ttu-id="2352f-159">Fejléc vegyes költségek</span><span class="sxs-lookup"><span data-stu-id="2352f-159">Header miscellaneous charge</span></span>
    - <span data-ttu-id="2352f-160">Sor vegyes költsége</span><span class="sxs-lookup"><span data-stu-id="2352f-160">Line miscellaneous charge</span></span>
    - <span data-ttu-id="2352f-161">Jóváírás</span><span class="sxs-lookup"><span data-stu-id="2352f-161">Credit note</span></span>
    - <span data-ttu-id="2352f-162">Visszárurendelés</span><span class="sxs-lookup"><span data-stu-id="2352f-162">Return order</span></span>
    - <span data-ttu-id="2352f-163">Beszerzési igénylés</span><span class="sxs-lookup"><span data-stu-id="2352f-163">Purchase requisition</span></span>
    - <span data-ttu-id="2352f-164">A beszerzési igénylési sor vegyes díja</span><span class="sxs-lookup"><span data-stu-id="2352f-164">Purchase requisition line miscellaneous charge</span></span>
    - <span data-ttu-id="2352f-165">Ajánlatkérés</span><span class="sxs-lookup"><span data-stu-id="2352f-165">Request for quotation</span></span>
    - <span data-ttu-id="2352f-166">Ajánlatkérés fejlécének vegyes díja</span><span class="sxs-lookup"><span data-stu-id="2352f-166">Request for quotation header miscellaneous charge</span></span>
    - <span data-ttu-id="2352f-167">Ajánlatkérés sorának vegyes díja</span><span class="sxs-lookup"><span data-stu-id="2352f-167">Request for quotation line miscellaneous charge</span></span>

- <span data-ttu-id="2352f-168">Készletfolyamat</span><span class="sxs-lookup"><span data-stu-id="2352f-168">Inventory process</span></span>

    - <span data-ttu-id="2352f-169">Átmozgatási rendelések – szállítás</span><span class="sxs-lookup"><span data-stu-id="2352f-169">Transfer order – ship</span></span>
    - <span data-ttu-id="2352f-170">Átmozgatási rendelés – bevételezés</span><span class="sxs-lookup"><span data-stu-id="2352f-170">Transfer order – receive</span></span>

## <a name="related-resources"></a><span data-ttu-id="2352f-171">Kapcsolódó erőforrások</span><span class="sxs-lookup"><span data-stu-id="2352f-171">Related resources</span></span>

[<span data-ttu-id="2352f-172">Az adószolgáltatás első lépései</span><span class="sxs-lookup"><span data-stu-id="2352f-172">Get started with tax service</span></span>](https://go.microsoft.com/fwlink/?linkid=2138482)

[<span data-ttu-id="2352f-173">Több adószám</span><span class="sxs-lookup"><span data-stu-id="2352f-173">Multiple VAT registration number</span></span>](https://go.microsoft.com/fwlink/?linkid=2153387)

[<span data-ttu-id="2352f-174">Adófunkció támogatása átmozgatási rendeléshez</span><span class="sxs-lookup"><span data-stu-id="2352f-174">Tax feature support for transfer order</span></span>](https://go.microsoft.com/fwlink/?linkid=2153388)

[<span data-ttu-id="2352f-175">Hogyan építsünk bővítményt az adószolgáltatásban?</span><span class="sxs-lookup"><span data-stu-id="2352f-175">How to build extension in tax service</span></span>](https://go.microsoft.com/fwlink/?linkid=2138483)
