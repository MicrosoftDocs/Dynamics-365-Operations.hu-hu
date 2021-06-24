---
title: Áfaszámítás (előzetes verzió)
description: Ez a témakör az adószámítási funkció általános hatókörét és jellemzőit ismerteti.
author: wangchen
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 9daa6e001200d03a2639974fb6de618d77ddf09d
ms.sourcegitcommit: cb282e8d2306ab71adf80a84346a6863d2d019e8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2021
ms.locfileid: "6184101"
---
# <a name="tax-calculation-preview"></a><span data-ttu-id="d07a9-103">Áfaszámítás (előzetes verzió)</span><span class="sxs-lookup"><span data-stu-id="d07a9-103">Tax Calculation (Preview)</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="d07a9-104">Az adószámítás egy hiperskálázható több-bérlős szolgáltatás, amely lehetővé teszi a Global Tax Engine számára, hogy automatizálja és egyszerűsítse az adómeghatározási és számítási folyamatot.</span><span class="sxs-lookup"><span data-stu-id="d07a9-104">Tax Calculation is a hyper-scalable multitenant service that enables the global tax engine to automate and simplify the tax determination and calculation process.</span></span> <span data-ttu-id="d07a9-105">Az adómotor teljesen konfigurálható.</span><span class="sxs-lookup"><span data-stu-id="d07a9-105">The tax engine is fully configurable.</span></span> <span data-ttu-id="d07a9-106">A konfigurálható elemek közé tartozik többek között az adóköteles adatmodell, az adókód, az adóalkalmazási mátrix és az adószámítási képlet.</span><span class="sxs-lookup"><span data-stu-id="d07a9-106">The elements that can be configured include, but aren't limited to, the taxable data model, tax code, tax applicability matrix, and tax calculation formula.</span></span> <span data-ttu-id="d07a9-107">Az adómotor a Microsoft Azure alapszolgáltatási platformon fut, és modern technológiát és exponenciális méretezhetőséget kínál.</span><span class="sxs-lookup"><span data-stu-id="d07a9-107">The tax engine runs on the Microsoft Azure core services platform, and offers modern technology and exponential scalability.</span></span>

<span data-ttu-id="d07a9-108">Az adószámítás integrálva van a Dynamics 365 Finance és a Dynamics 365 Supply Chain Management szolgáltatásokkal.</span><span class="sxs-lookup"><span data-stu-id="d07a9-108">Tax Calculation integrates with Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="d07a9-109">Végül integrálva lesz a Dynamics 365 Project Operations, Dynamics 365 Commerce és más saját és harmadik féltől származó alkalmazásokkal is.</span><span class="sxs-lookup"><span data-stu-id="d07a9-109">Eventually, it will also integrate with Dynamics 365 Project Operations, Dynamics 365 Commerce, and other first-party and third-party applications.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d07a9-110">Ha engedélyezi az Adószámítás szolgáltatást, a kapcsolódó adatokon bizonyos műveleteket a szolgáltatási adatokat karbantartó adatforrástól függően más adatközpontban is végre lehet hajtani.</span><span class="sxs-lookup"><span data-stu-id="d07a9-110">When you enable the Tax Calculation service, some operations on related data might be performed in a data center other than the data center that maintains your service data.</span></span> <span data-ttu-id="d07a9-111">Az Adószámítási szolgáltatás engedélyezése előtt tekintse át a [Feltételeket és kikötéseket](../../fin-ops-core/fin-ops/get-started/public-preview-terms.md).</span><span class="sxs-lookup"><span data-stu-id="d07a9-111">Review the [Terms and Conditions](../../fin-ops-core/fin-ops/get-started/public-preview-terms.md) before you enable the Tax Calculation service.</span></span> <span data-ttu-id="d07a9-112">Az Ön személyes adatainak védelme fontos a számunkra.</span><span class="sxs-lookup"><span data-stu-id="d07a9-112">Your privacy is important to us.</span></span> <span data-ttu-id="d07a9-113">További információt az [adatvédelmi nyilatkozatban találhat](https://go.microsoft.com/fwlink/?LinkId=521839).</span><span class="sxs-lookup"><span data-stu-id="d07a9-113">To learn more, read our [Privacy Statement](https://go.microsoft.com/fwlink/?LinkId=521839).</span></span>

<span data-ttu-id="d07a9-114">Az adószámítás egy mikroszolgáltatás-alapú adómotor, amely exponenciális méretezhetőséget kínál.</span><span class="sxs-lookup"><span data-stu-id="d07a9-114">Tax Calculation is a microservice-based tax engine that offers exponential scalability.</span></span> <span data-ttu-id="d07a9-115">A következő feladatok elvégzésében segíthet Önnek:</span><span class="sxs-lookup"><span data-stu-id="d07a9-115">It can help you perform the following tasks:</span></span>

- <span data-ttu-id="d07a9-116">Konfigurálhatja az adószámítást a Regulatory Configuration Service (RCS) szolgáltatáson keresztül.</span><span class="sxs-lookup"><span data-stu-id="d07a9-116">Configure Tax Calculation through Regulatory Configuration Service (RCS).</span></span> <span data-ttu-id="d07a9-117">Az RCS az elektronikus jelentéskészítési (ER) tervező továbbfejlesztett változata, és önálló szolgáltatásként érhető el.</span><span class="sxs-lookup"><span data-stu-id="d07a9-117">RCS is an enhanced version of the Electronic reporting (ER) designer and is available as a standalone service.</span></span>
- <span data-ttu-id="d07a9-118">Konfigurálhatja az adómátrixot az adókódok és adómértékek automatikus meghatározásához.</span><span class="sxs-lookup"><span data-stu-id="d07a9-118">Configure the tax matrix to automatically determine tax codes and rates.</span></span>
- <span data-ttu-id="d07a9-119">Konfigurálhatja az adószám automatikus meghatározásához.</span><span class="sxs-lookup"><span data-stu-id="d07a9-119">Configure the tax matrix to automatically determine the tax registration number.</span></span>
- <span data-ttu-id="d07a9-120">Konfigurálhatja az adószámítás tervezőjét képletek és feltételek meghatározására.</span><span class="sxs-lookup"><span data-stu-id="d07a9-120">Configure the tax calculation designer to define formulas and conditions.</span></span>
- <span data-ttu-id="d07a9-121">Megoszthatja az adómeghatározási és számítási megoldást jogi személyek között.</span><span class="sxs-lookup"><span data-stu-id="d07a9-121">Share the tax determination and calculation solution across legal entities.</span></span>

<span data-ttu-id="d07a9-122">Az adószámítási szolgáltatás használatához telepítse a projektből származó adószámítási szolgáltatásbővítményt az Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="d07a9-122">To use the tax calculation service, install the tax calculation service add-in from your project in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="d07a9-123">Ezután fejezze be a beállítást az RCS-ben, és engedélyezze az adószámítási szolgáltatást a Finance és a Supply Chain Management alkalmazásokban.</span><span class="sxs-lookup"><span data-stu-id="d07a9-123">Then complete the setup in RCS, and enable the tax calculation service in Finance and Supply Chain Management.</span></span> <span data-ttu-id="d07a9-124">További tájékoztatás: [Első lépések az adószolgáltatással](./global-get-started-with-tax-calculation-service.md).</span><span class="sxs-lookup"><span data-stu-id="d07a9-124">For more information, see [Get started with tax service](./global-get-started-with-tax-calculation-service.md).</span></span>

## <a name="availability"></a><span data-ttu-id="d07a9-125">Elérhetőség</span><span class="sxs-lookup"><span data-stu-id="d07a9-125">Availability</span></span>

<span data-ttu-id="d07a9-126">Az adószámítás csak tesztkörnyezetben és kiválasztott ügyfelek számára érhető el egy nyilvános előzetes programon keresztül.</span><span class="sxs-lookup"><span data-stu-id="d07a9-126">Tax Calculation is available only in sandbox environments and to selected customers, through a public preview program.</span></span> <span data-ttu-id="d07a9-127">Végül általánosan elérhetővé válik minden ügyfél számára és éles környezetekben is.</span><span class="sxs-lookup"><span data-stu-id="d07a9-127">Eventually, it will become generally available to all customers and in production environments.</span></span>

<span data-ttu-id="d07a9-128">Folyamatosan érkeznek az új funkciót, ezért győződjön meg róla, hogy gyakran ellenőrizze a legfrissebb dokumentációt, hogy megismerje a támogatott szolgáltatások kiterjedését és hatókörét.</span><span class="sxs-lookup"><span data-stu-id="d07a9-128">New features will continue to be delivered, so be sure to check the most up-to-date documentation often to learn about the coverage and scope of supported features.</span></span>

<span data-ttu-id="d07a9-129">Az adószámítás a következő Azure-földrajzi területeken van telepítve.</span><span class="sxs-lookup"><span data-stu-id="d07a9-129">Tax Calculation is deployed in the following Azure geographies.</span></span> <span data-ttu-id="d07a9-130">Más Azure földrajzi területeken is be lesz vezetve az ügyfelek igényeinek megfelelően:</span><span class="sxs-lookup"><span data-stu-id="d07a9-130">It will also be deployed to more Azure geographies, based on customer needs:</span></span>

- <span data-ttu-id="d07a9-131">Amerikai Egyesült Államok</span><span class="sxs-lookup"><span data-stu-id="d07a9-131">United States</span></span>
- <span data-ttu-id="d07a9-132">Európa</span><span class="sxs-lookup"><span data-stu-id="d07a9-132">Europe</span></span>

> [!NOTE]
> <span data-ttu-id="d07a9-133">Az adószámítás nem támogatja a Dynamics 365 helyszíni telepítését.</span><span class="sxs-lookup"><span data-stu-id="d07a9-133">Tax Calculation doesn't support on-premises deployments of Dynamics 365.</span></span> <span data-ttu-id="d07a9-134">Nem támogatja a korábbi verziókat sem, például a Dynamics AX 2012-t.</span><span class="sxs-lookup"><span data-stu-id="d07a9-134">It also doesn't support earlier versions, such as Dynamics AX 2012.</span></span>

## <a name="feature-highlights"></a><span data-ttu-id="d07a9-135">A funkció újdonságai</span><span class="sxs-lookup"><span data-stu-id="d07a9-135">Feature highlights</span></span>

- <span data-ttu-id="d07a9-136">Konfigurálható adómátrix az adókódok és adó automatikus meghatározásához és számításához</span><span class="sxs-lookup"><span data-stu-id="d07a9-136">A configurable tax matrix to automatically determine and calculate tax</span></span>
- <span data-ttu-id="d07a9-137">Több adónyilvántartási szám támogatása</span><span class="sxs-lookup"><span data-stu-id="d07a9-137">Support for multiple tax registration numbers</span></span>
- <span data-ttu-id="d07a9-138">Átmozgatási rendelés támogatása az adó meghatározásához és kiszámításához</span><span class="sxs-lookup"><span data-stu-id="d07a9-138">Transfer order support for tax determination and calculation</span></span>
- <span data-ttu-id="d07a9-139">Átmozgatási rendelés támogatása több adóregisztrációs szám meghatározásához</span><span class="sxs-lookup"><span data-stu-id="d07a9-139">Transfer order support for determination of multiple tax registration numbers</span></span>

## <a name="supported-transactions"></a><span data-ttu-id="d07a9-140">Támogatott tranzakciók</span><span class="sxs-lookup"><span data-stu-id="d07a9-140">Supported transactions</span></span>

<span data-ttu-id="d07a9-141">Az adószámítást jogi személy és tranzakció engedélyezheti.</span><span class="sxs-lookup"><span data-stu-id="d07a9-141">Tax Calculation can be enabled by legal entity and transaction.</span></span> <span data-ttu-id="d07a9-142">A varázsló a következő tranzakciókat támogatja:</span><span class="sxs-lookup"><span data-stu-id="d07a9-142">The following transactions are supported:</span></span>

- <span data-ttu-id="d07a9-143">Értékesítési folyamat</span><span class="sxs-lookup"><span data-stu-id="d07a9-143">Sales process</span></span>

    - <span data-ttu-id="d07a9-144">Értékesítési ajánlat</span><span class="sxs-lookup"><span data-stu-id="d07a9-144">Sales quotation</span></span>
    - <span data-ttu-id="d07a9-145">Értékesítési rendelés</span><span class="sxs-lookup"><span data-stu-id="d07a9-145">Sales order</span></span>
    - <span data-ttu-id="d07a9-146">Visszaigazolás</span><span class="sxs-lookup"><span data-stu-id="d07a9-146">Confirmation</span></span>
    - <span data-ttu-id="d07a9-147">Kitárolási lista</span><span class="sxs-lookup"><span data-stu-id="d07a9-147">Picking list</span></span>
    - <span data-ttu-id="d07a9-148">Szállítólevél</span><span class="sxs-lookup"><span data-stu-id="d07a9-148">Packing slip</span></span>
    - <span data-ttu-id="d07a9-149">Értékesítési számla</span><span class="sxs-lookup"><span data-stu-id="d07a9-149">Sales invoice</span></span>
    - <span data-ttu-id="d07a9-150">Jóváírás</span><span class="sxs-lookup"><span data-stu-id="d07a9-150">Credit note</span></span>
    - <span data-ttu-id="d07a9-151">Visszárurendelés</span><span class="sxs-lookup"><span data-stu-id="d07a9-151">Return order</span></span>
    - <span data-ttu-id="d07a9-152">Fejléc vegyes költségek</span><span class="sxs-lookup"><span data-stu-id="d07a9-152">Header miscellaneous charge</span></span>
    - <span data-ttu-id="d07a9-153">Sor vegyes költsége</span><span class="sxs-lookup"><span data-stu-id="d07a9-153">Line miscellaneous charge</span></span>

- <span data-ttu-id="d07a9-154">Beszerzési folyamat</span><span class="sxs-lookup"><span data-stu-id="d07a9-154">Purchase process</span></span>

    - <span data-ttu-id="d07a9-155">Beszerzési rendelés</span><span class="sxs-lookup"><span data-stu-id="d07a9-155">Purchase order</span></span>
    - <span data-ttu-id="d07a9-156">Visszaigazolás</span><span class="sxs-lookup"><span data-stu-id="d07a9-156">Confirmation</span></span>
    - <span data-ttu-id="d07a9-157">Bevételezések listája</span><span class="sxs-lookup"><span data-stu-id="d07a9-157">Receipts list</span></span>
    - <span data-ttu-id="d07a9-158">Termékbevételezés</span><span class="sxs-lookup"><span data-stu-id="d07a9-158">Product receipt</span></span>
    - <span data-ttu-id="d07a9-159">Beszerzési számla</span><span class="sxs-lookup"><span data-stu-id="d07a9-159">Purchase invoice</span></span>
    - <span data-ttu-id="d07a9-160">Fejléc vegyes költségek</span><span class="sxs-lookup"><span data-stu-id="d07a9-160">Header miscellaneous charge</span></span>
    - <span data-ttu-id="d07a9-161">Sor vegyes költsége</span><span class="sxs-lookup"><span data-stu-id="d07a9-161">Line miscellaneous charge</span></span>
    - <span data-ttu-id="d07a9-162">Jóváírás</span><span class="sxs-lookup"><span data-stu-id="d07a9-162">Credit note</span></span>
    - <span data-ttu-id="d07a9-163">Visszárurendelés</span><span class="sxs-lookup"><span data-stu-id="d07a9-163">Return order</span></span>
    - <span data-ttu-id="d07a9-164">Beszerzési igénylés</span><span class="sxs-lookup"><span data-stu-id="d07a9-164">Purchase requisition</span></span>
    - <span data-ttu-id="d07a9-165">A beszerzési igénylési sor vegyes díja</span><span class="sxs-lookup"><span data-stu-id="d07a9-165">Purchase requisition line miscellaneous charge</span></span>
    - <span data-ttu-id="d07a9-166">Ajánlatkérés</span><span class="sxs-lookup"><span data-stu-id="d07a9-166">Request for quotation</span></span>
    - <span data-ttu-id="d07a9-167">Ajánlatkérés fejlécének vegyes díja</span><span class="sxs-lookup"><span data-stu-id="d07a9-167">Request for quotation header miscellaneous charge</span></span>
    - <span data-ttu-id="d07a9-168">Ajánlatkérés sorának vegyes díja</span><span class="sxs-lookup"><span data-stu-id="d07a9-168">Request for quotation line miscellaneous charge</span></span>

- <span data-ttu-id="d07a9-169">Készletfolyamat</span><span class="sxs-lookup"><span data-stu-id="d07a9-169">Inventory process</span></span>

    - <span data-ttu-id="d07a9-170">Átmozgatási rendelések – szállítás</span><span class="sxs-lookup"><span data-stu-id="d07a9-170">Transfer order – ship</span></span>
    - <span data-ttu-id="d07a9-171">Átmozgatási rendelés – bevételezés</span><span class="sxs-lookup"><span data-stu-id="d07a9-171">Transfer order – receive</span></span>

## <a name="related-resources"></a><span data-ttu-id="d07a9-172">Kapcsolódó erőforrások</span><span class="sxs-lookup"><span data-stu-id="d07a9-172">Related resources</span></span>

[<span data-ttu-id="d07a9-173">Az adószolgáltatás első lépései</span><span class="sxs-lookup"><span data-stu-id="d07a9-173">Get started with tax service</span></span>](./global-get-started-with-tax-calculation-service.md)

[<span data-ttu-id="d07a9-174">Több adószám</span><span class="sxs-lookup"><span data-stu-id="d07a9-174">Multiple VAT registration number</span></span>](./emea-multiple-vat-registration-numbers.md)

[<span data-ttu-id="d07a9-175">Adófunkció támogatása átmozgatási rendeléshez</span><span class="sxs-lookup"><span data-stu-id="d07a9-175">Tax feature support for transfer order</span></span>](./tasks/tax-feature-support-for-transfer-order.md)

[<span data-ttu-id="d07a9-176">Hogyan építsünk bővítményt az adószolgáltatásban?</span><span class="sxs-lookup"><span data-stu-id="d07a9-176">How to build extension in tax service</span></span>](./tax-service-add-data-fields-tax-integration-by-extension.md)
