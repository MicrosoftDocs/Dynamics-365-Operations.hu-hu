---
title: Áfaszámítás (előzetes verzió)
description: Ez a témakör az adószámítási funkció általános hatókörét és jellemzőit ismerteti.
author: wangchen
ms.date: 04/12/2021
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
ms.openlocfilehash: 3df952e0632807e55f176e63dc2047be5e622ec2
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2021
ms.locfileid: "5892349"
---
# <a name="tax-calculation-preview"></a><span data-ttu-id="5c439-103">Áfaszámítás (előzetes verzió)</span><span class="sxs-lookup"><span data-stu-id="5c439-103">Tax Calculation (Preview)</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="5c439-104">Az adószámítás egy hiperskálázható több-bérlős szolgáltatás, amely lehetővé teszi a Global Tax Engine számára, hogy automatizálja és egyszerűsítse az adómeghatározási és számítási folyamatot.</span><span class="sxs-lookup"><span data-stu-id="5c439-104">Tax Calculation is a hyper-scalable multitenant service that enables the global tax engine to automate and simplify the tax determination and calculation process.</span></span> <span data-ttu-id="5c439-105">Az adómotor teljesen konfigurálható.</span><span class="sxs-lookup"><span data-stu-id="5c439-105">The tax engine is fully configurable.</span></span> <span data-ttu-id="5c439-106">A konfigurálható elemek közé tartozik többek között az adóköteles adatmodell, az adókód, az adóalkalmazási mátrix és az adószámítási képlet.</span><span class="sxs-lookup"><span data-stu-id="5c439-106">The elements that can be configured include, but aren't limited to, the taxable data model, tax code, tax applicability matrix, and tax calculation formula.</span></span> <span data-ttu-id="5c439-107">Az adómotor a Microsoft Azure alapszolgáltatási platformon fut, és modern technológiát és exponenciális méretezhetőséget kínál.</span><span class="sxs-lookup"><span data-stu-id="5c439-107">The tax engine runs on the Microsoft Azure core services platform, and offers modern technology and exponential scalability.</span></span>

<span data-ttu-id="5c439-108">Az adószámítás integrálva van a Dynamics 365 Finance és a Dynamics 365 Supply Chain Management szolgáltatásokkal.</span><span class="sxs-lookup"><span data-stu-id="5c439-108">Tax Calculation integrates with Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="5c439-109">Végül integrálva lesz a Dynamics 365 Project Operations, Dynamics 365 Commerce és más saját és harmadik féltől származó alkalmazásokkal is.</span><span class="sxs-lookup"><span data-stu-id="5c439-109">Eventually, it will also integrate with Dynamics 365 Project Operations, Dynamics 365 Commerce, and other first-party and third-party applications.</span></span>

<span data-ttu-id="5c439-110">Az adószámítás egy mikroszolgáltatás-alapú adómotor, amely exponenciális méretezhetőséget kínál.</span><span class="sxs-lookup"><span data-stu-id="5c439-110">Tax Calculation is a microservice-based tax engine that offers exponential scalability.</span></span> <span data-ttu-id="5c439-111">A következő feladatok elvégzésében segíthet Önnek:</span><span class="sxs-lookup"><span data-stu-id="5c439-111">It can help you perform the following tasks:</span></span>

- <span data-ttu-id="5c439-112">Konfigurálhatja az adószámítást a Regulatory Configuration Service (RCS) szolgáltatáson keresztül.</span><span class="sxs-lookup"><span data-stu-id="5c439-112">Configure Tax Calculation through Regulatory Configuration Service (RCS).</span></span> <span data-ttu-id="5c439-113">Az RCS az elektronikus jelentéskészítési (ER) tervező továbbfejlesztett változata, és önálló szolgáltatásként érhető el.</span><span class="sxs-lookup"><span data-stu-id="5c439-113">RCS is an enhanced version of the Electronic reporting (ER) designer and is available as a standalone service.</span></span>
- <span data-ttu-id="5c439-114">Konfigurálhatja az adómátrixot az adókódok és adómértékek automatikus meghatározásához.</span><span class="sxs-lookup"><span data-stu-id="5c439-114">Configure the tax matrix to automatically determine tax codes and rates.</span></span>
- <span data-ttu-id="5c439-115">Konfigurálhatja az adószám automatikus meghatározásához.</span><span class="sxs-lookup"><span data-stu-id="5c439-115">Configure the tax matrix to automatically determine the tax registration number.</span></span>
- <span data-ttu-id="5c439-116">Konfigurálhatja az adószámítás tervezőjét képletek és feltételek meghatározására.</span><span class="sxs-lookup"><span data-stu-id="5c439-116">Configure the tax calculation designer to define formulas and conditions.</span></span>
- <span data-ttu-id="5c439-117">Megoszthatja az adómeghatározási és számítási megoldást jogi személyek között.</span><span class="sxs-lookup"><span data-stu-id="5c439-117">Share the tax determination and calculation solution across legal entities.</span></span>

<span data-ttu-id="5c439-118">Az adószámítási szolgáltatás használatához telepítse a projektből származó adószámítási szolgáltatásbővítményt az Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="5c439-118">To use the tax calculation service, install the tax calculation service add-in from your project in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="5c439-119">Ezután fejezze be a beállítást az RCS-ben, és engedélyezze az adószámítási szolgáltatást a Finance és a Supply Chain Management alkalmazásokban.</span><span class="sxs-lookup"><span data-stu-id="5c439-119">Then complete the setup in RCS, and enable the tax calculation service in Finance and Supply Chain Management.</span></span> <span data-ttu-id="5c439-120">További tájékoztatás: [Első lépések az adószolgáltatással](./global-get-started-with-tax-calculation-service.md).</span><span class="sxs-lookup"><span data-stu-id="5c439-120">For more information, see [Get started with tax service](./global-get-started-with-tax-calculation-service.md).</span></span>

## <a name="availability"></a><span data-ttu-id="5c439-121">Elérhetőség</span><span class="sxs-lookup"><span data-stu-id="5c439-121">Availability</span></span>

<span data-ttu-id="5c439-122">Az adószámítás csak tesztkörnyezetben és kiválasztott ügyfelek számára érhető el egy nyilvános előzetes programon keresztül.</span><span class="sxs-lookup"><span data-stu-id="5c439-122">Tax Calculation is available only in sandbox environments and to selected customers, through a public preview program.</span></span> <span data-ttu-id="5c439-123">Végül általánosan elérhetővé válik minden ügyfél számára és éles környezetekben is.</span><span class="sxs-lookup"><span data-stu-id="5c439-123">Eventually, it will become generally available to all customers and in production environments.</span></span>

<span data-ttu-id="5c439-124">Folyamatosan érkeznek az új funkciót, ezért győződjön meg róla, hogy gyakran ellenőrizze a legfrissebb dokumentációt, hogy megismerje a támogatott szolgáltatások kiterjedését és hatókörét.</span><span class="sxs-lookup"><span data-stu-id="5c439-124">New features will continue to be delivered, so be sure to check the most up-to-date documentation often to learn about the coverage and scope of supported features.</span></span>

<span data-ttu-id="5c439-125">Az adószámítás a következő Azure-földrajzi területeken van telepítve.</span><span class="sxs-lookup"><span data-stu-id="5c439-125">Tax Calculation is deployed in the following Azure geographies.</span></span> <span data-ttu-id="5c439-126">Más Azure földrajzi területeken is be lesz vezetve az ügyfelek igényeinek megfelelően:</span><span class="sxs-lookup"><span data-stu-id="5c439-126">It will also be deployed to more Azure geographies, based on customer needs:</span></span>

- <span data-ttu-id="5c439-127">Amerikai Egyesült Államok</span><span class="sxs-lookup"><span data-stu-id="5c439-127">United States</span></span>
- <span data-ttu-id="5c439-128">Európa</span><span class="sxs-lookup"><span data-stu-id="5c439-128">Europe</span></span>

> [!NOTE]
> <span data-ttu-id="5c439-129">Az adószámítás nem támogatja a Dynamics 365 helyszíni telepítését.</span><span class="sxs-lookup"><span data-stu-id="5c439-129">Tax Calculation doesn't support on-premises deployments of Dynamics 365.</span></span> <span data-ttu-id="5c439-130">Nem támogatja a korábbi verziókat sem, például a Dynamics AX 2012-t.</span><span class="sxs-lookup"><span data-stu-id="5c439-130">It also doesn't support earlier versions, such as Dynamics AX 2012.</span></span>

## <a name="feature-highlights"></a><span data-ttu-id="5c439-131">A funkció újdonságai</span><span class="sxs-lookup"><span data-stu-id="5c439-131">Feature highlights</span></span>

- <span data-ttu-id="5c439-132">Konfigurálható adómátrix az adókódok és adó automatikus meghatározásához és számításához</span><span class="sxs-lookup"><span data-stu-id="5c439-132">A configurable tax matrix to automatically determine and calculate tax</span></span>
- <span data-ttu-id="5c439-133">Több adónyilvántartási szám támogatása</span><span class="sxs-lookup"><span data-stu-id="5c439-133">Support for multiple tax registration numbers</span></span>
- <span data-ttu-id="5c439-134">Átmozgatási rendelés támogatása az adó meghatározásához és kiszámításához</span><span class="sxs-lookup"><span data-stu-id="5c439-134">Transfer order support for tax determination and calculation</span></span>
- <span data-ttu-id="5c439-135">Átmozgatási rendelés támogatása több adóregisztrációs szám meghatározásához</span><span class="sxs-lookup"><span data-stu-id="5c439-135">Transfer order support for determination of multiple tax registration numbers</span></span>

## <a name="supported-transactions"></a><span data-ttu-id="5c439-136">Támogatott tranzakciók</span><span class="sxs-lookup"><span data-stu-id="5c439-136">Supported transactions</span></span>

<span data-ttu-id="5c439-137">Az adószámítást jogi személy és tranzakció engedélyezheti.</span><span class="sxs-lookup"><span data-stu-id="5c439-137">Tax Calculation can be enabled by legal entity and transaction.</span></span> <span data-ttu-id="5c439-138">A varázsló a következő tranzakciókat támogatja:</span><span class="sxs-lookup"><span data-stu-id="5c439-138">The following transactions are supported:</span></span>

- <span data-ttu-id="5c439-139">Értékesítési folyamat</span><span class="sxs-lookup"><span data-stu-id="5c439-139">Sales process</span></span>

    - <span data-ttu-id="5c439-140">Értékesítési ajánlat</span><span class="sxs-lookup"><span data-stu-id="5c439-140">Sales quotation</span></span>
    - <span data-ttu-id="5c439-141">Értékesítési rendelés</span><span class="sxs-lookup"><span data-stu-id="5c439-141">Sales order</span></span>
    - <span data-ttu-id="5c439-142">Visszaigazolás</span><span class="sxs-lookup"><span data-stu-id="5c439-142">Confirmation</span></span>
    - <span data-ttu-id="5c439-143">Kitárolási lista</span><span class="sxs-lookup"><span data-stu-id="5c439-143">Picking list</span></span>
    - <span data-ttu-id="5c439-144">Szállítólevél</span><span class="sxs-lookup"><span data-stu-id="5c439-144">Packing slip</span></span>
    - <span data-ttu-id="5c439-145">Értékesítési számla</span><span class="sxs-lookup"><span data-stu-id="5c439-145">Sales invoice</span></span>
    - <span data-ttu-id="5c439-146">Jóváírás</span><span class="sxs-lookup"><span data-stu-id="5c439-146">Credit note</span></span>
    - <span data-ttu-id="5c439-147">Visszárurendelés</span><span class="sxs-lookup"><span data-stu-id="5c439-147">Return order</span></span>
    - <span data-ttu-id="5c439-148">Fejléc vegyes költségek</span><span class="sxs-lookup"><span data-stu-id="5c439-148">Header miscellaneous charge</span></span>
    - <span data-ttu-id="5c439-149">Sor vegyes költsége</span><span class="sxs-lookup"><span data-stu-id="5c439-149">Line miscellaneous charge</span></span>

- <span data-ttu-id="5c439-150">Beszerzési folyamat</span><span class="sxs-lookup"><span data-stu-id="5c439-150">Purchase process</span></span>

    - <span data-ttu-id="5c439-151">Beszerzési rendelés</span><span class="sxs-lookup"><span data-stu-id="5c439-151">Purchase order</span></span>
    - <span data-ttu-id="5c439-152">Visszaigazolás</span><span class="sxs-lookup"><span data-stu-id="5c439-152">Confirmation</span></span>
    - <span data-ttu-id="5c439-153">Bevételezések listája</span><span class="sxs-lookup"><span data-stu-id="5c439-153">Receipts list</span></span>
    - <span data-ttu-id="5c439-154">Termékbevételezés</span><span class="sxs-lookup"><span data-stu-id="5c439-154">Product receipt</span></span>
    - <span data-ttu-id="5c439-155">Beszerzési számla</span><span class="sxs-lookup"><span data-stu-id="5c439-155">Purchase invoice</span></span>
    - <span data-ttu-id="5c439-156">Fejléc vegyes költségek</span><span class="sxs-lookup"><span data-stu-id="5c439-156">Header miscellaneous charge</span></span>
    - <span data-ttu-id="5c439-157">Sor vegyes költsége</span><span class="sxs-lookup"><span data-stu-id="5c439-157">Line miscellaneous charge</span></span>
    - <span data-ttu-id="5c439-158">Jóváírás</span><span class="sxs-lookup"><span data-stu-id="5c439-158">Credit note</span></span>
    - <span data-ttu-id="5c439-159">Visszárurendelés</span><span class="sxs-lookup"><span data-stu-id="5c439-159">Return order</span></span>
    - <span data-ttu-id="5c439-160">Beszerzési igénylés</span><span class="sxs-lookup"><span data-stu-id="5c439-160">Purchase requisition</span></span>
    - <span data-ttu-id="5c439-161">A beszerzési igénylési sor vegyes díja</span><span class="sxs-lookup"><span data-stu-id="5c439-161">Purchase requisition line miscellaneous charge</span></span>
    - <span data-ttu-id="5c439-162">Ajánlatkérés</span><span class="sxs-lookup"><span data-stu-id="5c439-162">Request for quotation</span></span>
    - <span data-ttu-id="5c439-163">Ajánlatkérés fejlécének vegyes díja</span><span class="sxs-lookup"><span data-stu-id="5c439-163">Request for quotation header miscellaneous charge</span></span>
    - <span data-ttu-id="5c439-164">Ajánlatkérés sorának vegyes díja</span><span class="sxs-lookup"><span data-stu-id="5c439-164">Request for quotation line miscellaneous charge</span></span>

- <span data-ttu-id="5c439-165">Készletfolyamat</span><span class="sxs-lookup"><span data-stu-id="5c439-165">Inventory process</span></span>

    - <span data-ttu-id="5c439-166">Átmozgatási rendelések – szállítás</span><span class="sxs-lookup"><span data-stu-id="5c439-166">Transfer order – ship</span></span>
    - <span data-ttu-id="5c439-167">Átmozgatási rendelés – bevételezés</span><span class="sxs-lookup"><span data-stu-id="5c439-167">Transfer order – receive</span></span>

## <a name="related-resources"></a><span data-ttu-id="5c439-168">Kapcsolódó erőforrások</span><span class="sxs-lookup"><span data-stu-id="5c439-168">Related resources</span></span>

[<span data-ttu-id="5c439-169">Az adószolgáltatás első lépései</span><span class="sxs-lookup"><span data-stu-id="5c439-169">Get started with tax service</span></span>](./global-get-started-with-tax-calculation-service.md)

[<span data-ttu-id="5c439-170">Több adószám</span><span class="sxs-lookup"><span data-stu-id="5c439-170">Multiple VAT registration number</span></span>](./emea-multiple-vat-registration-numbers.md)

[<span data-ttu-id="5c439-171">Adófunkció támogatása átmozgatási rendeléshez</span><span class="sxs-lookup"><span data-stu-id="5c439-171">Tax feature support for transfer order</span></span>](./tasks/tax-feature-support-for-transfer-order.md)

[<span data-ttu-id="5c439-172">Hogyan építsünk bővítményt az adószolgáltatásban?</span><span class="sxs-lookup"><span data-stu-id="5c439-172">How to build extension in tax service</span></span>](./tax-service-add-data-fields-tax-integration-by-extension.md)