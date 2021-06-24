---
title: Használat kezelése irányítópult
description: Ez a témakör bemutatja, hogy hogyan lehet a Használatkezelés irányítópult segítségével figyelni az elektronikus számlázási szolgáltatás használatát, és megfelelni az előírásoknak.
author: gionoder
ms.date: 06/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 411c2d33c81738dcacfb7c8feec991d0fd06fb78
ms.sourcegitcommit: 9069a8511dfe11d09a2b51d32547ba10fea48bed
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/02/2021
ms.locfileid: "6130506"
---
# <a name="usage-management-dashboard"></a><span data-ttu-id="da340-103">Használat kezelése irányítópult</span><span class="sxs-lookup"><span data-stu-id="da340-103">Usage management dashboard</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="da340-104">A **Használat kezelése** irányítópult segítségével nyomon követheti az Elektronikus számlázási szolgáltatás használatát, így szervezete a havi használat tekintetében is megfelel az előírásoknak.</span><span class="sxs-lookup"><span data-stu-id="da340-104">The **Usage management** dashboard helps you monitor usage of the Electronic Invoicing service, and therefore helps your organization remain compliant in terms of its monthly usage.</span></span> <span data-ttu-id="da340-105">A megfelelés meghatározása a benyújtás mennyiségének kiszámításával és az fogadott mennyiség összehasonlításával határozza meg, hogy a beszerzett mennyiség és a felhasznált mennyiség között eltérés van-e.</span><span class="sxs-lookup"><span data-stu-id="da340-105">Compliance is determined by calculating the submission volume and comparing it with the acquired volume of submissions to identify any deviations between the acquired volume and the used volume.</span></span>

<span data-ttu-id="da340-106">A irányítópult a következő kijelzéseket tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="da340-106">The dashboard includes the following indicators:</span></span>

- <span data-ttu-id="da340-107">Egy költségmutató, amely a felhasználás nyomon követésére használható a licencelési megfelelés céljából:</span><span class="sxs-lookup"><span data-stu-id="da340-107">One cost indicator that you can use to monitor consumption for licensing compliance purposes:</span></span>

    - <span data-ttu-id="da340-108">Havi használat (export)</span><span class="sxs-lookup"><span data-stu-id="da340-108">Usage per month (export)</span></span>

- <span data-ttu-id="da340-109">Három működési mutató, amelyek az elektronikus számlázási szolgáltatás használatának nyomon követésére használhatók kezelési célokra:</span><span class="sxs-lookup"><span data-stu-id="da340-109">Three operational indicators that you can use to track usage of the Electronic Invoicing service for management purposes:</span></span>

    - <span data-ttu-id="da340-110">Felhasználás funkció szerint</span><span class="sxs-lookup"><span data-stu-id="da340-110">Usage by feature</span></span>
    - <span data-ttu-id="da340-111">Felhasználás környezet szerint</span><span class="sxs-lookup"><span data-stu-id="da340-111">Usage by environment</span></span>
    - <span data-ttu-id="da340-112">Havi használat (import)</span><span class="sxs-lookup"><span data-stu-id="da340-112">Usage per month (import)</span></span>

## <a name="measurement-scope"></a><span data-ttu-id="da340-113">A mérés hatálya</span><span class="sxs-lookup"><span data-stu-id="da340-113">Measurement scope</span></span>

- <span data-ttu-id="da340-114">Mértékegység:</span><span class="sxs-lookup"><span data-stu-id="da340-114">Unit of measure:</span></span> 

    <span data-ttu-id="da340-115">A **Használatkezelés** irányítópult az üzleti dokumentumok és az importált elektronikus számlák benyújtását számolja meg.</span><span class="sxs-lookup"><span data-stu-id="da340-115">The **Usage management** dashboard counts the submission of business documents and imported electronic invoices.</span></span>

- <span data-ttu-id="da340-116">Szervezet:</span><span class="sxs-lookup"><span data-stu-id="da340-116">Organization:</span></span> 

    <span data-ttu-id="da340-117">A számítás összegzése szervezet bérlői azonosítója szerint történik, függetlenül attól, hogy hány példányban van engedélyezve a Microsoft Dynamics 365 Finance vagy Dynamics 365 Supply Chain Management, illetve, hogy hány jogi személynél van engedélyezve az Elektronikus számlázás szolgáltatás.</span><span class="sxs-lookup"><span data-stu-id="da340-117">Counting is summarized by the tenant ID of your organization, regardless of the number of instances of Microsoft Dynamics 365 Finance or Dynamics 365 Supply Chain Management, or the number of legal entities where the Electronic Invoicing service is enabled.</span></span>


## <a name="indicator-usage-per-month-export"></a><span data-ttu-id="da340-118">Mutató: Havi használat (export)</span><span class="sxs-lookup"><span data-stu-id="da340-118">Indicator: Usage per month (export)</span></span>

<span data-ttu-id="da340-119">Ez a mutató részletes adatokat nyújt az elektronikus számlákról, amelyek a szervezetnél egy adott időszakban ki lettek bocsátva.</span><span class="sxs-lookup"><span data-stu-id="da340-119">This indicator provides details about the electronic invoices that your organization issues during a defined period.</span></span>

### <a name="scope"></a><span data-ttu-id="da340-120">Hatókör</span><span class="sxs-lookup"><span data-stu-id="da340-120">Scope</span></span>
- <span data-ttu-id="da340-121">A Supply Chain Management modulból az elektronikus számlázási szolgáltatásba elküldött üzleti dokumentumok száma, függetlenül attól, hogy az üzleti dokumentumok hány sort tartalmaznak.</span><span class="sxs-lookup"><span data-stu-id="da340-121">The number of business documents that are submitted from Finance and Supply Chain Management to the Electronic Invoicing service, regardless of number of lines that those business documents contain.</span></span>
- <span data-ttu-id="da340-122">Az Elektronikus számlázási szolgáltatás által sikeresen feldolgozott elküldött üzleti dokumentumok száma.</span><span class="sxs-lookup"><span data-stu-id="da340-122">The number of submitted business documents that are successfully processed by the Electronic Invoicing service.</span></span> <span data-ttu-id="da340-123">A dokumentum sikeresen feldolgozottnak minősül, amikor befejeződött a funkcióbeállításban meghatározott műveletek folyamata.</span><span class="sxs-lookup"><span data-stu-id="da340-123">A document is considered successfully processed when the flow of actions that are defined in the feature setup is completed.</span></span>

> [!NOTE]
> <span data-ttu-id="da340-124">Amikor egy elektronikus számlát elküldnek egy külső webszolgáltatásnak, a számolás független a webszolgáltatás feldolgozásának eredményeitől (elfogadva, elutasítva vagy sémaérvényesítési hiba).</span><span class="sxs-lookup"><span data-stu-id="da340-124">When an electronic invoice is submitted to an external web service, counting is independent of the results of web service processing (accepted, rejected, or schema validation error).</span></span> <span data-ttu-id="da340-125">Ha a webszolgáltatás az elektronikus számlázási szolgáltatás kérését megkapta és választ küldött, a beküldés érvényes mennyiségnek számít.</span><span class="sxs-lookup"><span data-stu-id="da340-125">If the web service received and responded to the request from the Electronic Invoicing service, the submission is considered a valid counting.</span></span>

- <span data-ttu-id="da340-126">**Kivétel:** Az üzleti dokumentumokat nem számolja a rendszer, ha újraküldik őket a Finance és a Supply Chain Management modulból az Elektronikus számlázási szolgáltatásba, például olyan helyzetekben, amikor ugyanannak az üzleti dokumentumnak az újraküldése szükséges az elektronikus számla állapotának a módosítása érdekében.</span><span class="sxs-lookup"><span data-stu-id="da340-126">**Exception:** Business documents aren't counted if they are resubmitted from Finance and Supply Chain Management to the Electronic Invoicing service, such as in the scenarios where a resubmission of the same business document is required to change the status of the electronic invoice.</span></span> <span data-ttu-id="da340-127">Például egy brazil elektronikus számla (pénzügyi bizonylat) kiállítása érvényesnek számít, de az ahhoz érvénytelenítési kérelem nem számít.</span><span class="sxs-lookup"><span data-stu-id="da340-127">For example, issuance of a Brazilian electronic invoice (fiscal document) is counted as valid, but the cancellation request for it isn't counted.</span></span>


### <a name="calculation"></a><span data-ttu-id="da340-128">Számítás</span><span class="sxs-lookup"><span data-stu-id="da340-128">Calculation</span></span>

<span data-ttu-id="da340-129">Az egyenleg számítása a következő módon történik:</span><span class="sxs-lookup"><span data-stu-id="da340-129">The calculation of the balance is calculated as follows:</span></span>

<span data-ttu-id="da340-130">Egyenleg = Ingyenes + Megvásárolt – Felhasznált</span><span class="sxs-lookup"><span data-stu-id="da340-130">Balance = Free + Purchased – Used</span></span>

<span data-ttu-id="da340-131">Ahol:</span><span class="sxs-lookup"><span data-stu-id="da340-131">Where:</span></span>

- <span data-ttu-id="da340-132">Ingyenes:</span><span class="sxs-lookup"><span data-stu-id="da340-132">Free:</span></span>
  
    <span data-ttu-id="da340-133">A vevő által havonta elküldhető üzleti dokumentumok ingyenes mennyisége.</span><span class="sxs-lookup"><span data-stu-id="da340-133">A free volume of business documents the customer can submit per month.</span></span> <span data-ttu-id="da340-134">Ez a csomag 100 üzleti dokumentumot tartalmaz, amelyek benyújthatóak az elektronikus számlázási szolgáltatásnak.</span><span class="sxs-lookup"><span data-stu-id="da340-134">It includes a package of 100 business documents that can be submitted to the Electronic Invoicing service.</span></span> <span data-ttu-id="da340-135">Az ingyenes mennyiség nem kumulatív, és a fennmaradó egyenleg nem lesz átgördítve a következő időszakra.</span><span class="sxs-lookup"><span data-stu-id="da340-135">Free volume isn't cumulative, and any remaining balance isn't rolled over to the next period.</span></span>
  
- <span data-ttu-id="da340-136">Megvásárolt:</span><span class="sxs-lookup"><span data-stu-id="da340-136">Purchased:</span></span>
  
    <span data-ttu-id="da340-137">Egy csomag 1000 üzleti dokumentumot tartalmaz, amelyek benyújthatóak az elektronikus számlázási szolgáltatásnak.</span><span class="sxs-lookup"><span data-stu-id="da340-137">A package of 1,000 business documents that can be submitted to the Electronic Invoicing service.</span></span> <span data-ttu-id="da340-138">Ezt a csomagot havonta kell beszerezni az Ön szervezete számára.</span><span class="sxs-lookup"><span data-stu-id="da340-138">This package must be acquired for your organization on a monthly basis.</span></span> <span data-ttu-id="da340-139">Az megvásárolt mennyiség nem kumulatív, és a fennmaradó egyenleg nem lesz átgördítve a következő időszakra.</span><span class="sxs-lookup"><span data-stu-id="da340-139">Purchased volume isn't cumulative, and any remaining balance isn't rolled over to the next period.</span></span>
  
- <span data-ttu-id="da340-140">Felhasznált:</span><span class="sxs-lookup"><span data-stu-id="da340-140">Used:</span></span> 

    <span data-ttu-id="da340-141">Az Elektronikus számlázási szolgáltatásba küldött üzleti dokumentumok száma a meghatározott feltételeknek megfelelően.</span><span class="sxs-lookup"><span data-stu-id="da340-141">The count of business document submissions to the Electronic Invoicing service according to defined criteria.</span></span>
   
> [!IMPORTANT]
> <span data-ttu-id="da340-142">Ha a szervezet tervezi, hogy meghaladja a havi 100 ingyenesen beküldhető mennyiséget, akkor a maximális mennyiség megvásárlásával gondoskodhat arról, hogy az elektronikus számlázási szolgáltatás Microsoft licencelési irányelveinek megfelelő maradjon.</span><span class="sxs-lookup"><span data-stu-id="da340-142">If your organization plans to exceed the monthly volume of 100 free submissions, purchase the peak volume to ensure that you remain compliant with the Microsoft licensing policy for the Electronic Invoicing service.</span></span>
>
> <span data-ttu-id="da340-143">Jelenleg a megvásárolt mennyiséget manuálisan kell megadni a beszerzés dátumának megfelelően, 1000 beküldést tartalmazó csomagonként.</span><span class="sxs-lookup"><span data-stu-id="da340-143">Currently, purchased volume must be manually entered, according to the date of acquisition, as multiple packages of 1,000 submissions.</span></span>

## <a name="indicator-usage-by-feature"></a><span data-ttu-id="da340-144">Mutató: Funkció szerint való felhasználás</span><span class="sxs-lookup"><span data-stu-id="da340-144">Indicator: Usage by feature</span></span>

<span data-ttu-id="da340-145">Ez a mutató azt mutatja, hogy egy adott időszakban az elektronikus számlák kiállítása során az elektronikus számlázási funkciók használatát mutatja meg.</span><span class="sxs-lookup"><span data-stu-id="da340-145">This indicator shows the usage of electronic invoicing features for issuance of electronic invoices during a defined period.</span></span>

- <span data-ttu-id="da340-146">Számítás:</span><span class="sxs-lookup"><span data-stu-id="da340-146">Calculation:</span></span>
  
    <span data-ttu-id="da340-147">Felhasznált = Annak száma, hogy hányszor használta az egyes elektronikus számlázási funkciókat az üzleti dokumentumoknak az Elektronikus számlázási szolgáltatásba történő benyújtásakor.</span><span class="sxs-lookup"><span data-stu-id="da340-147">Used = The count of how many times each electronic invoicing feature was used during the submission of business documents to the Electronic Invoicing service.</span></span>

## <a name="indicator-usage-by-environment"></a><span data-ttu-id="da340-148">Mutató: Környezet szerint való felhasználás</span><span class="sxs-lookup"><span data-stu-id="da340-148">Indicator: Usage by environment</span></span>

<span data-ttu-id="da340-149">Ez a mutató az elektronikus számlázási szolgáltatási környezet használatát mutatja egy adott időszakban.</span><span class="sxs-lookup"><span data-stu-id="da340-149">This indicator shows the usage of electronic invoicing service environments during a defined period.</span></span>

- <span data-ttu-id="da340-150">Számítás:</span><span class="sxs-lookup"><span data-stu-id="da340-150">Calculation:</span></span>
    
    <span data-ttu-id="da340-151">Felhasznált = Annak száma, hogy hányszor használta az egyes elektronikus számlázási szolgáltatási környezeteket az üzleti dokumentumoknak az Elektronikus számlázási szolgáltatásba történő benyújtásakor.</span><span class="sxs-lookup"><span data-stu-id="da340-151">Used = The count of how many times each electronic invoicing service environment was used during the submission of business documents to the Electronic Invoicing service.</span></span>

## <a name="indicator-usage-per-month-import"></a><span data-ttu-id="da340-152">Mutató: Havi használat (import)</span><span class="sxs-lookup"><span data-stu-id="da340-152">Indicator: Usage per month (import)</span></span>

<span data-ttu-id="da340-153">Ez a mutató azt mutatja, hogy egy adott időszakban az elektronikus számlázási szolgáltatásból mennyi elektronikus számla lett importálva a Finance és a Supply Chain Management alkalmazásokba.</span><span class="sxs-lookup"><span data-stu-id="da340-153">This indicator shows the volume of importation of electronic invoices by Electronic Invoicing service into Finance and Supply Chain Management during a defined period.</span></span>

- <span data-ttu-id="da340-154">Hatókör:</span><span class="sxs-lookup"><span data-stu-id="da340-154">Scope:</span></span>

    <span data-ttu-id="da340-155">A Finance és a Supply Chain Management alkalmazásokba importált elektronikus számlák, függetlenül attól, hogy hány sort tartalmaznak ezek az elektronikus számlák.</span><span class="sxs-lookup"><span data-stu-id="da340-155">Electronic invoices that are imported into Finance and Supply Chain Management, regardless of the number of lines that those electronic invoices contain.</span></span>

- <span data-ttu-id="da340-156">Számítás:</span><span class="sxs-lookup"><span data-stu-id="da340-156">Calculation:</span></span>

    <span data-ttu-id="da340-157">Beérkezett = Az importált elektronikus számlák száma a Finance és a Supply Chain Management alkalmazásokban.</span><span class="sxs-lookup"><span data-stu-id="da340-157">Received = The count of imported electronic invoices into Finance and Supply Chain Management.</span></span>

## <a name="functions"></a><span data-ttu-id="da340-158">Funkciók</span><span class="sxs-lookup"><span data-stu-id="da340-158">Functions</span></span>
### <a name="purchase"></a><span data-ttu-id="da340-159">Beszerzés</span><span class="sxs-lookup"><span data-stu-id="da340-159">Purchase</span></span>

<span data-ttu-id="da340-160">Válassza a **Vásárlás** lehetőséget a **Havi használat (export)** lapon a beszerzett beküldések mennyiségének manuális regisztrálása érdekében.</span><span class="sxs-lookup"><span data-stu-id="da340-160">On the **Usage per month (export)** tab, select **Purchase** to manually register the amount of acquired submissions.</span></span>

<span data-ttu-id="da340-161">Egy adott dátumhoz válassza az **Új** lehetőséget, és adja meg az adott napon beszerzett **Csomagok** számát.</span><span class="sxs-lookup"><span data-stu-id="da340-161">For a given date, select **New** and enter the number of **Packages** acquired for on that date.</span></span>

<span data-ttu-id="da340-162">A **Mennyiség** kiszámítása:</span><span class="sxs-lookup"><span data-stu-id="da340-162">The **Quantity** is calculated as:</span></span>

<span data-ttu-id="da340-163">Mennyiség = Csomagok \* 1000</span><span class="sxs-lookup"><span data-stu-id="da340-163">Quantity = Packages \* 1.000</span></span>

<span data-ttu-id="da340-164">A számított **Mennyiség** a **Havi használat (export)** mutató alapján **Megvásárolt** értéknek megfelelő.</span><span class="sxs-lookup"><span data-stu-id="da340-164">The calculated **Quantity** reflects in the **Purchased** from the indicator **Usage per month (export)**.</span></span>

### <a name="update"></a><span data-ttu-id="da340-165">Módosítás</span><span class="sxs-lookup"><span data-stu-id="da340-165">Update</span></span>

<span data-ttu-id="da340-166">A Műveleti panelen a **Frissítés** gombra kattintva frissítse a számítást, és frissítse a lapon és a diagramon megjelenő adatokat.</span><span class="sxs-lookup"><span data-stu-id="da340-166">On the Action Pane, select **Update** to refresh the calculation and update the data shown on the page and in the chart.</span></span>

### <a name="reset-history-data"></a><span data-ttu-id="da340-167">Előzményadatok alaphelyzetbe állítása</span><span class="sxs-lookup"><span data-stu-id="da340-167">Reset history data</span></span>

<span data-ttu-id="da340-168">A Műveleti panelen válassza az **Előzményadatok alaphelyzetbe állítása** lehetőséget annak az adatbázisnak a frissítéséhez, ahonnan a mutatók számítása történik.</span><span class="sxs-lookup"><span data-stu-id="da340-168">On the Action Pane, select **Reset history data** to refresh the database from where the indicators are calculated.</span></span>




> [!NOTE]
> <span data-ttu-id="da340-169">A **Használat kezelése** irányítópultja nem mutat pénzösszegeket.</span><span class="sxs-lookup"><span data-stu-id="da340-169">The **Usage management** dashboard doesn't show monetary amounts.</span></span> <span data-ttu-id="da340-170">Ehelyett csak a számolt beküldések és az importált dokumentumok mennyiségét jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="da340-170">Instead, it shows only the volume of counted submissions and imported documents.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
