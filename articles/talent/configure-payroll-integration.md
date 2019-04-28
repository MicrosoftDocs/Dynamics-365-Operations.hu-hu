---
title: Bérlista-integráció konfigurálása a Talnet és a Dayforce közötti
description: Ez a témakör bemutatja, hogyan kell konfigurálni az integrációt a Microsoft Dynamics 365 for Talent és a Ceridian Dayforce között úgy, hogy fel lehessen dolgozni fizetési időszakot.
author: andreabichsel
manager: AnnBe
ms.date: 03/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 9a88bf61dbb12520b555ceb7363b1c646d95386e
ms.sourcegitcommit: 204e4554e409c39fbbf7b273ad138ce2809931a8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/26/2019
ms.locfileid: "898444"
---
# <a name="configure-the-payroll-integration-between-talent-and-dayforce"></a><span data-ttu-id="09e9f-103">Bérlista-integráció konfigurálása a Talent és a Dayforce között</span><span class="sxs-lookup"><span data-stu-id="09e9f-103">Configure the payroll integration between Talent and Dayforce</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="09e9f-104">A Microsoft Dynamics 365 for Talent és Ceridian Dayforce integrálásához több konfigurációs lépést szükséges elvégezni, melyek ebben a témakörben vannak ismertetve.</span><span class="sxs-lookup"><span data-stu-id="09e9f-104">The integration between Microsoft Dynamics 365 for Talent and Ceridian Dayforce relies on several configuration steps that are described in this topic.</span></span> <span data-ttu-id="09e9f-105">Be kell állítania az integrációt a Talent a Dayforce alkalmazásokban is a fizetési időszak feldolgozása előtt.</span><span class="sxs-lookup"><span data-stu-id="09e9f-105">You must configure the integration in both Talent and Dayforce before you can process a pay run.</span></span>

<span data-ttu-id="09e9f-106">Ha olyan szolgáltatást használ a fizetési időszakokhoz, mint a Dayforce, engedélyeznie kell az integrációt a Talentben.</span><span class="sxs-lookup"><span data-stu-id="09e9f-106">When you use a service such as Dayforce to complete pay runs, you must enable the integration in Talent.</span></span> <span data-ttu-id="09e9f-107">Az integrációhoz meghatározott adatok szükségesek a Talentből.</span><span class="sxs-lookup"><span data-stu-id="09e9f-107">The integration requires specific data from Talent.</span></span> <span data-ttu-id="09e9f-108">Ezért ellenőriznie kell, hogy a Dayforce-ban hozzárendelt adatok olyan módon vannak konfigurálva a Talentben, hogy az támogassa az integrációt.</span><span class="sxs-lookup"><span data-stu-id="09e9f-108">Therefore, you must verify that data that is mapped to Dayforce is configured in Talent in a manner that supports the integration.</span></span> <span data-ttu-id="09e9f-109">Az integráció a következő szélesebb adatkategóriákat használja:</span><span class="sxs-lookup"><span data-stu-id="09e9f-109">The integration uses the following broad categories of data:</span></span>

- <span data-ttu-id="09e9f-110">Emberierőforrás-adatok</span><span class="sxs-lookup"><span data-stu-id="09e9f-110">Human resources data</span></span>
- <span data-ttu-id="09e9f-111">Kompenzációadatok</span><span class="sxs-lookup"><span data-stu-id="09e9f-111">Compensation data</span></span>
- <span data-ttu-id="09e9f-112">Bérlistaadatok, mint kifizetési ciklus, fizetési időszakok és bevételkódok</span><span class="sxs-lookup"><span data-stu-id="09e9f-112">Payroll data, such as pay cycles, pay periods, and earning codes</span></span>
- <span data-ttu-id="09e9f-113">Dolgozóadatok</span><span class="sxs-lookup"><span data-stu-id="09e9f-113">Worker data</span></span>

<span data-ttu-id="09e9f-114">Ez a témakör leírja a lépéseket, amelyeket követni kell az integráció engedélyezéséhez.</span><span class="sxs-lookup"><span data-stu-id="09e9f-114">This topic describes the steps that you must follow to enable the integration.</span></span> <span data-ttu-id="09e9f-115">Azt is bemutatja, hogy milyen típusú adatok és konfiguráció szükséges az integrációhoz.</span><span class="sxs-lookup"><span data-stu-id="09e9f-115">It also explains the types of data and the configuration details that the integration requires.</span></span>

## <a name="enable-the-integration"></a><span data-ttu-id="09e9f-116">Engedélyezze az integrációt</span><span class="sxs-lookup"><span data-stu-id="09e9f-116">Enable the integration</span></span>

<span data-ttu-id="09e9f-117">A Talentben be kell kapcsolja a műveletek integrációját, meg kell adnia a konfiguráció adatait, hogy tudjon a Dayforcehoz csatlakozni.</span><span class="sxs-lookup"><span data-stu-id="09e9f-117">In Talent, you must turn on the integration and enter the configuration information to connect to Dayforce.</span></span> <span data-ttu-id="09e9f-118">Ha azt szeretné, hogy a létrehozott általános főkönyvi tranzakció importálva legyen a Microsoft Dynamics 365 for Finance and Operations alkalmazásba, be kell állítania egy Microsoft Azure tárolási fiókot, majd adja meg, majd Azure tárolási kapcsolat karakterláncát a Finance and Operations alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="09e9f-118">If you want the general ledger transaction that is produced to be imported into Microsoft Dynamics 365 for Finance and Operations, you must also set up a Microsoft Azure storage account and enter the Azure Storage connection string in Finance and Operations.</span></span>

<span data-ttu-id="09e9f-119">Az integráció engedélyezéséhez a Talentben kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="09e9f-119">To turn on the integration in Talent, follow these steps.</span></span>

1. <span data-ttu-id="09e9f-120">A **Rendszerfelügyelet** oldalon válassza az **Integrációkonfiguráció** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="09e9f-120">On the **System administration** page, select **Integration configuration**.</span></span>
2. <span data-ttu-id="09e9f-121">Adja meg a biztonságos fájl átviteli protokollt (FTP) végpontot és a biztonságos FTP-mappa elérési útja.</span><span class="sxs-lookup"><span data-stu-id="09e9f-121">Enter the secure File Transfer Protocol (FTP) endpoint and the secure FTP folder path.</span></span>
3. <span data-ttu-id="09e9f-122">Adja meg azon felhasználó felhasználónevét és jelszavát, aki hozzáfér a biztonságos FTP végponthoz és a mappa elérési útjához.</span><span class="sxs-lookup"><span data-stu-id="09e9f-122">Enter the user name and password of the user who will access the secure FTP endpoint and folder path.</span></span>
4. <span data-ttu-id="09e9f-123">Tesztelje a kapcsolatot szükség szerint, és állítsa a **Bérlista-integráció engedélyezése** lehetőséggel **Igenre**.</span><span class="sxs-lookup"><span data-stu-id="09e9f-123">Test the connection, as required, and set the **Enable payroll integration** option to **Yes**.</span></span>

<span data-ttu-id="09e9f-124">Ha az integráció engedélyezve van, adatexport adatcsomagok és fájlok jönnek létre, valamint a gyakoriság is be van állítva.</span><span class="sxs-lookup"><span data-stu-id="09e9f-124">When the integration is turned on, the data export package and files are created, and the frequency is set.</span></span> <span data-ttu-id="09e9f-125">Igény szerint módosíthatja a gyakoriságot.</span><span class="sxs-lookup"><span data-stu-id="09e9f-125">You can change this frequency as you require.</span></span>

<span data-ttu-id="09e9f-126">Azure tárolási fiókokkal és Azure tárolási kapcsolati karakterláncokat kapcsolatos további információt az alábbi Azure-témakörökben találja:</span><span class="sxs-lookup"><span data-stu-id="09e9f-126">For more information about Azure storage accounts and Azure Storage connection strings, see the following Azure topics:</span></span>

- [<span data-ttu-id="09e9f-127">Az Azure Storage-fiókokról</span><span class="sxs-lookup"><span data-stu-id="09e9f-127">About Azure storage accounts</span></span>](https://docs.microsoft.com/en-us/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [<span data-ttu-id="09e9f-128">Azure Storage kapcsolati karakterláncok konfigurálása</span><span class="sxs-lookup"><span data-stu-id="09e9f-128">Configure Azure Storage connection strings</span></span>](https://docs.microsoft.com/en-us/azure/storage/common/storage-configure-connection-string)

## <a name="configure-your-data"></a><span data-ttu-id="09e9f-129">Adatai konfigurálása</span><span class="sxs-lookup"><span data-stu-id="09e9f-129">Configure your data</span></span> 

<span data-ttu-id="09e9f-130">A bérlista feldolgozásához konfigurálnia kell az emberi erőforrás adatokat a Talentben.</span><span class="sxs-lookup"><span data-stu-id="09e9f-130">To process payroll, you must configure human resource data in Talent.</span></span> <span data-ttu-id="09e9f-131">Be kell állítani a szervezeti adatokat, például a feladatokat és beosztásokat, valamint juttatásokra és a kompenzációra vonatkozó adatokat.</span><span class="sxs-lookup"><span data-stu-id="09e9f-131">You must set up organizational data, such as jobs and positions, together with benefits and compensation information.</span></span> <span data-ttu-id="09e9f-132">Ez az információ megadja a foglalkoztatásra, fizetésre és levonásokra vonatkozó információkat, melyek szükségesek az alkalmazott fizetések generálásához.</span><span class="sxs-lookup"><span data-stu-id="09e9f-132">This information provides the employment, pay, and deduction information that is required in order to generate employee pay.</span></span>

### <a name="human-resource-data"></a><span data-ttu-id="09e9f-133">Emberierőforrás-adatok</span><span class="sxs-lookup"><span data-stu-id="09e9f-133">Human resource data</span></span>

#### <a name="benefits"></a><span data-ttu-id="09e9f-134">Juttatások</span><span class="sxs-lookup"><span data-stu-id="09e9f-134">Benefits</span></span> 

<span data-ttu-id="09e9f-135">Az emberi erőforrások számos beállítási és karbantartási eszközt biztosít, amelyek segítségével beállíthatja és karbantarthatja a szervezet által a dolgozónak biztosított juttatásokat, levonásokat és dolgozói kompenzációs terveket.</span><span class="sxs-lookup"><span data-stu-id="09e9f-135">Human resources provides tools for the setup and maintenance of the benefits, deductions, and worker compensation plans that an organization offers or processes for its workers.</span></span>

<span data-ttu-id="09e9f-136">Juttatások létrehozása esetén ne felejtse el a következő adatokat és beállításokat, amelyeket a Dayforce használ.</span><span class="sxs-lookup"><span data-stu-id="09e9f-136">When you create benefits, keep in mind the following data and configurations that are used in Dayforce.</span></span>

##### <a name="benefit-plans"></a><span data-ttu-id="09e9f-137">Juttatási tervek</span><span class="sxs-lookup"><span data-stu-id="09e9f-137">Benefit plans</span></span>

- <span data-ttu-id="09e9f-138">Terv (szükséges)</span><span class="sxs-lookup"><span data-stu-id="09e9f-138">Plan (required)</span></span>
- <span data-ttu-id="09e9f-139">Típus (szükséges)</span><span class="sxs-lookup"><span data-stu-id="09e9f-139">Type (required)</span></span>
- <span data-ttu-id="09e9f-140">Bérlista hatása (szükséges)</span><span class="sxs-lookup"><span data-stu-id="09e9f-140">Payroll impact (required)</span></span>
- <span data-ttu-id="09e9f-141">Hátralékok helyreállítása</span><span class="sxs-lookup"><span data-stu-id="09e9f-141">Recover arrears</span></span>
- <span data-ttu-id="09e9f-142">Levonási módszer</span><span class="sxs-lookup"><span data-stu-id="09e9f-142">Deduction method</span></span>
- <span data-ttu-id="09e9f-143">Levonás prioritása</span><span class="sxs-lookup"><span data-stu-id="09e9f-143">Deduction priority</span></span>
- <span data-ttu-id="09e9f-144">Időszak korlátozása</span><span class="sxs-lookup"><span data-stu-id="09e9f-144">Limit period</span></span>
- <span data-ttu-id="09e9f-145">Összeghatár</span><span class="sxs-lookup"><span data-stu-id="09e9f-145">Limit amount</span></span>

##### <a name="benefits"></a><span data-ttu-id="09e9f-146">Juttatások</span><span class="sxs-lookup"><span data-stu-id="09e9f-146">Benefits</span></span>

- <span data-ttu-id="09e9f-147">Terv (szükséges)</span><span class="sxs-lookup"><span data-stu-id="09e9f-147">Plan (required)</span></span>
- <span data-ttu-id="09e9f-148">Típus (szükséges)</span><span class="sxs-lookup"><span data-stu-id="09e9f-148">Type (required)</span></span>
- <span data-ttu-id="09e9f-149">Lehetőség (szükséges)</span><span class="sxs-lookup"><span data-stu-id="09e9f-149">Option (required)</span></span>
- <span data-ttu-id="09e9f-150">Juttatás azonosítója (szükséges)</span><span class="sxs-lookup"><span data-stu-id="09e9f-150">Benefit ID (required)</span></span>
- <span data-ttu-id="09e9f-151">Gyakoriság</span><span class="sxs-lookup"><span data-stu-id="09e9f-151">Frequency</span></span>
- <span data-ttu-id="09e9f-152">Alap</span><span class="sxs-lookup"><span data-stu-id="09e9f-152">Basis</span></span>
- <span data-ttu-id="09e9f-153">Összeg vagy mérték</span><span class="sxs-lookup"><span data-stu-id="09e9f-153">Amount or rate</span></span>
- <span data-ttu-id="09e9f-154">Bevételkód</span><span class="sxs-lookup"><span data-stu-id="09e9f-154">Earning code</span></span>

##### <a name="supported-frequencies"></a><span data-ttu-id="09e9f-155">Támogatott gyakoriságok</span><span class="sxs-lookup"><span data-stu-id="09e9f-155">Supported frequencies</span></span> 

- <span data-ttu-id="09e9f-156">Heti</span><span class="sxs-lookup"><span data-stu-id="09e9f-156">Weekly</span></span>
- <span data-ttu-id="09e9f-157">Kétheti</span><span class="sxs-lookup"><span data-stu-id="09e9f-157">Bi-weekly</span></span>
- <span data-ttu-id="09e9f-158">Félhavi</span><span class="sxs-lookup"><span data-stu-id="09e9f-158">Semi-monthly</span></span>
- <span data-ttu-id="09e9f-159">Havi</span><span class="sxs-lookup"><span data-stu-id="09e9f-159">Monthly</span></span>

##### <a name="supported-bases"></a><span data-ttu-id="09e9f-160">Támogatott alapok</span><span class="sxs-lookup"><span data-stu-id="09e9f-160">Supported bases</span></span> 

- <span data-ttu-id="09e9f-161">Rögzített összeg</span><span class="sxs-lookup"><span data-stu-id="09e9f-161">Fixed amount</span></span>
- <span data-ttu-id="09e9f-162">Bevételek százaléka</span><span class="sxs-lookup"><span data-stu-id="09e9f-162">Percent of earnings</span></span>
- <span data-ttu-id="09e9f-163">Produktív órák</span><span class="sxs-lookup"><span data-stu-id="09e9f-163">Productive hours</span></span>

<span data-ttu-id="09e9f-164">A Dayforce létrehozza a következő levonásokat, a juttatási tervben definiált bérlistahatás alapján.</span><span class="sxs-lookup"><span data-stu-id="09e9f-164">Dayforce creates the following deductions, based on the payroll impact that is defined on the benefit plan.</span></span>

| <span data-ttu-id="09e9f-165">Kiválasztás a Talentben</span><span class="sxs-lookup"><span data-stu-id="09e9f-165">Selection in Talent</span></span>        | <span data-ttu-id="09e9f-166">Eredmény a Dayforce-ban</span><span class="sxs-lookup"><span data-stu-id="09e9f-166">Result in Dayforce</span></span>                            |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="09e9f-167">Nincs</span><span class="sxs-lookup"><span data-stu-id="09e9f-167">None</span></span>                       | <span data-ttu-id="09e9f-168">Nincs létrehozva levonás.</span><span class="sxs-lookup"><span data-stu-id="09e9f-168">No deduction is created.</span></span>                      |
| <span data-ttu-id="09e9f-169">Csak levonás</span><span class="sxs-lookup"><span data-stu-id="09e9f-169">Deduction only</span></span>             | <span data-ttu-id="09e9f-170">Alkalmazotti levonás jön létre.</span><span class="sxs-lookup"><span data-stu-id="09e9f-170">An employee deduction is created.</span></span>             |
| <span data-ttu-id="09e9f-171">Csak hozzájárulás</span><span class="sxs-lookup"><span data-stu-id="09e9f-171">Contribution only</span></span>          | <span data-ttu-id="09e9f-172">Egy alkalmazotti levonás jön létre.</span><span class="sxs-lookup"><span data-stu-id="09e9f-172">An employer deduction is created.</span></span>             |
| <span data-ttu-id="09e9f-173">Levonás és hozzájárulás</span><span class="sxs-lookup"><span data-stu-id="09e9f-173">Deduction and contribution</span></span> | <span data-ttu-id="09e9f-174">Alkalmazotti és a munkáltatói levonások jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="09e9f-174">Employee and employer deductions are created.</span></span> |

<span data-ttu-id="09e9f-175">A juttatási programok definiálásával és kezelésével kapcsolatosan további tájékoztatás a következő témakörökben talál:</span><span class="sxs-lookup"><span data-stu-id="09e9f-175">For more information about how to define and manage a benefits program, see the following topics:</span></span>

- [<span data-ttu-id="09e9f-176">Alkalmazotti juttatási program megvalósítása</span><span class="sxs-lookup"><span data-stu-id="09e9f-176">Deliver an employee benefits program</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [<span data-ttu-id="09e9f-177">Új juttatás létrehozása</span><span class="sxs-lookup"><span data-stu-id="09e9f-177">Create a new benefit</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [<span data-ttu-id="09e9f-178">Juttatásra való jogosultsági szabályok és irányelvek meghatározása</span><span class="sxs-lookup"><span data-stu-id="09e9f-178">Define benefit eligibility rules and policies</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [<span data-ttu-id="09e9f-179">Dolgozók juttatásainak felvétele és eltávolítása</span><span class="sxs-lookup"><span data-stu-id="09e9f-179">Enroll and remove benefits from workers</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a><span data-ttu-id="09e9f-180">Kompenzáció</span><span class="sxs-lookup"><span data-stu-id="09e9f-180">Compensation</span></span> 

<span data-ttu-id="09e9f-181">A kompenzációkezeléssel szabályozható az alapfizetés és a jutalmak kifizetése.</span><span class="sxs-lookup"><span data-stu-id="09e9f-181">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="09e9f-182">Egy alkalmazott fix fizetési díjalapja és érdemeken alapuló fizetése kezelhető a fix kompenzációs tervekkel.</span><span class="sxs-lookup"><span data-stu-id="09e9f-182">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="09e9f-183">Az ösztönző díjak kifizetése, például bónuszok, teljesítménydíjak, részvényopciók és kölcsönök, továbbá az egyszeri jutalmak a változó kompenzációs tervekben szabályozhatók.</span><span class="sxs-lookup"><span data-stu-id="09e9f-183">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span>

<span data-ttu-id="09e9f-184">A Dayforce a kompenzációs adatok segítségével kiszámítja az alkalmazott óradíját vagy éves díját.</span><span class="sxs-lookup"><span data-stu-id="09e9f-184">Dayforce uses compensation information to calculate an employee's hourly or annual rate.</span></span> <span data-ttu-id="09e9f-185">Fix kompenzációs tervek és a fizetési díjalap átalakítások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="09e9f-185">Fixed compensation plans and pay rate conversions are required.</span></span> <span data-ttu-id="09e9f-186">Az alkalmazottakat hozzá kell rendelni a fix kompenzációs tervhez.</span><span class="sxs-lookup"><span data-stu-id="09e9f-186">Employees must be associated with a fixed compensation plan.</span></span>

<span data-ttu-id="09e9f-187">A következő témakörökben bővebben olvashat a kompenzációs tervekről:</span><span class="sxs-lookup"><span data-stu-id="09e9f-187">For more information about compensation plans, see the following topics:</span></span>

- [<span data-ttu-id="09e9f-188">Fix kompenzációs konstrukciók létrehozása</span><span class="sxs-lookup"><span data-stu-id="09e9f-188">Create fixed compensation plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [<span data-ttu-id="09e9f-189">Változó kompenzációs konstrukciók létrehozása</span><span class="sxs-lookup"><span data-stu-id="09e9f-189">Create variable compensation plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [<span data-ttu-id="09e9f-190">Munkabér-/kompenzációs struktúra és tervek kialakítása</span><span class="sxs-lookup"><span data-stu-id="09e9f-190">Develop salary/compensation structure and plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [<span data-ttu-id="09e9f-191">Folyamatkompenzáció</span><span class="sxs-lookup"><span data-stu-id="09e9f-191">Process compensation</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/process-compensation)
- [<span data-ttu-id="09e9f-192">Kompenzációs folyamat meghatározása és eredmények kiszámítása</span><span class="sxs-lookup"><span data-stu-id="09e9f-192">Define compensation process and calculate results</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [<span data-ttu-id="09e9f-193">Alkalmazottak felvétele fix kompenzációs konstrukcióba</span><span class="sxs-lookup"><span data-stu-id="09e9f-193">Enroll an employee in a fixed compensation plan</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [<span data-ttu-id="09e9f-194">Alkalmazottak felvétele változó kompenzációs konstrukcióba</span><span class="sxs-lookup"><span data-stu-id="09e9f-194">Enroll an employee in a variable compensation plan</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a><span data-ttu-id="09e9f-195">Beosztások</span><span class="sxs-lookup"><span data-stu-id="09e9f-195">Jobs</span></span> 

<span data-ttu-id="09e9f-196">A munkakör azon feladatok és felelősségek gyűjteménye, amelyek egy adott munkát végrehajtó személytől elvártak.</span><span class="sxs-lookup"><span data-stu-id="09e9f-196">A job is a collection of the tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="09e9f-197">További információ a következő témakörökben olvasható:</span><span class="sxs-lookup"><span data-stu-id="09e9f-197">For more information, see the following topics:</span></span>

- [<span data-ttu-id="09e9f-198">Feladat összetevőinek beállítása</span><span class="sxs-lookup"><span data-stu-id="09e9f-198">Setting up the components of a job</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-job)
- [<span data-ttu-id="09e9f-199">Új feladatok meghatározása</span><span class="sxs-lookup"><span data-stu-id="09e9f-199">Define new jobs</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a><span data-ttu-id="09e9f-200">Beosztások</span><span class="sxs-lookup"><span data-stu-id="09e9f-200">Positions</span></span>

<span data-ttu-id="09e9f-201">Egy beosztás egy feladat egyedi példánya.</span><span class="sxs-lookup"><span data-stu-id="09e9f-201">A position is an individual instance of a job.</span></span> <span data-ttu-id="09e9f-202">Például az „Értékesítési igazgató (Kelet)” pozíció egyike azon beosztásoknak, amelyek társíthatók az „Értékesítési igazgató” feladathoz.</span><span class="sxs-lookup"><span data-stu-id="09e9f-202">For example, the "Sales manager (East)" position is one of the positions that are associated with the "Sales manager" job.</span></span> <span data-ttu-id="09e9f-203">A beosztás létezik a részlegben.</span><span class="sxs-lookup"><span data-stu-id="09e9f-203">A position exists in a department.</span></span> <span data-ttu-id="09e9f-204">Egy beosztáshoz csak egy dolgozó rendelhető.</span><span class="sxs-lookup"><span data-stu-id="09e9f-204">Only one worker can be associated with each position.</span></span>

<span data-ttu-id="09e9f-205">A következő adatokat és konfigurációkat szem előtt tartani beosztások beállításakor:</span><span class="sxs-lookup"><span data-stu-id="09e9f-205">Keep the following data and configuration in mind when you set up positions:</span></span>

- <span data-ttu-id="09e9f-206">Beosztás (szükséges)</span><span class="sxs-lookup"><span data-stu-id="09e9f-206">Position (required)</span></span>
- <span data-ttu-id="09e9f-207">Leírás (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-207">Description (required)</span></span>
- <span data-ttu-id="09e9f-208">Munka (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-208">Job (required)</span></span>
- <span data-ttu-id="09e9f-209">Részleg (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-209">Department (required)</span></span>
- <span data-ttu-id="09e9f-210">Beosztás típusa (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-210">Position type (required)</span></span>
- <span data-ttu-id="09e9f-211">Teljes munkaidőssel egyenértékű</span><span class="sxs-lookup"><span data-stu-id="09e9f-211">Full-time equivalent</span></span>
- <span data-ttu-id="09e9f-212">Éves rendes munkaidő (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-212">Annual regular hours (required)</span></span>
- <span data-ttu-id="09e9f-213">Jogi személy által fizetett (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-213">Paid by legal entity (required)</span></span>
- <span data-ttu-id="09e9f-214">Fizetési ciklus (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-214">Pay cycle (required)</span></span>
- <span data-ttu-id="09e9f-215">Alapértelmezett pénzügyi dimenzió – Költséghely (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-215">Default financial dimension – Cost center (required)</span></span>
- <span data-ttu-id="09e9f-216">Dolgozó-hozzárendelés – dolgozó-hozzárendelés kezdete, hozzárendelés vége és okkód</span><span class="sxs-lookup"><span data-stu-id="09e9f-216">Worker assignment – Worker, assignment start, assignment end, reason code</span></span>

<span data-ttu-id="09e9f-217">A azonos osztály több beosztása társítva van az ugyanazon a feladathoz, azok össze lesznek vonva a Dayforce egyetlen pozíciójába.</span><span class="sxs-lookup"><span data-stu-id="09e9f-217">If multiple positions in the same department are associated with the same job, they are consolidated into a single position in Dayforce.</span></span>

<span data-ttu-id="09e9f-218">További információ a következő témakörökben olvasható:</span><span class="sxs-lookup"><span data-stu-id="09e9f-218">For more information, see the following topics:</span></span>

- [<span data-ttu-id="09e9f-219">Munkaerő szervezése részlegek, munkák és beosztások szerint</span><span class="sxs-lookup"><span data-stu-id="09e9f-219">Organize your workforce using departments, jobs, and positions</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [<span data-ttu-id="09e9f-220">Beosztások beállítása</span><span class="sxs-lookup"><span data-stu-id="09e9f-220">Set up positions</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a><span data-ttu-id="09e9f-221">Osztályok</span><span class="sxs-lookup"><span data-stu-id="09e9f-221">Departments</span></span>

<span data-ttu-id="09e9f-222">A részleg egy működési egység, amely a szervezet egy kategóriáját vagy működési területét képviseli.</span><span class="sxs-lookup"><span data-stu-id="09e9f-222">A department is an operating unit that represents a category or functional area of an organization.</span></span> <span data-ttu-id="09e9f-223">Egy részleg a szervezet egy konkrét területen végzett tevékenységeiért felel (például értékesítés, könyvelés, emberi erőforrások).</span><span class="sxs-lookup"><span data-stu-id="09e9f-223">A department is responsible for a specific area of the organization, such as sales, accounting, or human resources.</span></span> <span data-ttu-id="09e9f-224">A részlegek segítségével hozhatók létre jelentések a működési területekről.</span><span class="sxs-lookup"><span data-stu-id="09e9f-224">You can use departments to report on functional areas.</span></span> <span data-ttu-id="09e9f-225">A részlegeknek lehet eredménykimutatási felelőssége.</span><span class="sxs-lookup"><span data-stu-id="09e9f-225">Departments might have profit and loss responsibility.</span></span>

<span data-ttu-id="09e9f-226">További információ a következő témakörökben olvasható:</span><span class="sxs-lookup"><span data-stu-id="09e9f-226">For more information, see the following topics:</span></span>

- [<span data-ttu-id="09e9f-227">Részleg létrehozása és társítása a szervezeti hierarchiához</span><span class="sxs-lookup"><span data-stu-id="09e9f-227">Create a department and associate it with the department hierarchy</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [<span data-ttu-id="09e9f-228">Új részlegek meghatározása</span><span class="sxs-lookup"><span data-stu-id="09e9f-228">Define new departments</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a><span data-ttu-id="09e9f-229">Fizetési ciklusok és fizetési időszakok</span><span class="sxs-lookup"><span data-stu-id="09e9f-229">Pay cycles and pay periods</span></span>

<span data-ttu-id="09e9f-230">A fizetési ciklus meghatározza, hogy milyen gyakran történik a bérlista folyósítása, és a dolgozók mely napokon kapnak fizetést,.</span><span class="sxs-lookup"><span data-stu-id="09e9f-230">A pay cycle determines how often payroll is run and the specific days when workers are paid.</span></span> <span data-ttu-id="09e9f-231">Például a kifizetési ciklus lehet, havi, és az alkalmazottak kaphatják a hónap utolsó napján a fizetésüket.</span><span class="sxs-lookup"><span data-stu-id="09e9f-231">For example, a pay cycle might be monthly, and employees might be paid on the last day of the month.</span></span> <span data-ttu-id="09e9f-232">Vagy a kifizetési ciklus lehet heti, és az alkalmazottak a fizetési időszak utáni kedden kaphatják fizetésüket.</span><span class="sxs-lookup"><span data-stu-id="09e9f-232">Alternatively, a pay cycle might be weekly, and employees might be paid on the Tuesday after the end of the pay period.</span></span> <span data-ttu-id="09e9f-233">Kifizetési ciklusok beosztásokhoz vannak rendelve, és szabályozzák, hogy az ebben a beosztásban lévő dolgozók mikor kapnak fizetést.</span><span class="sxs-lookup"><span data-stu-id="09e9f-233">Pay cycles are assigned to positions to control when workers in those positions are paid.</span></span>

<span data-ttu-id="09e9f-234">Miután létrehozott fizetési ciklusokat, minden egyes ciklushoz fizetési időszakot hozhat létre.</span><span class="sxs-lookup"><span data-stu-id="09e9f-234">After you create pay cycles, you can generate pay periods for each cycle.</span></span> <span data-ttu-id="09e9f-235">Minden fizetési időszakban egy alapértelmezett fizetési dátum van, amely a megadott adatokon alapul.</span><span class="sxs-lookup"><span data-stu-id="09e9f-235">Each pay period includes a default payment date that is based on information that you provide.</span></span> <span data-ttu-id="09e9f-236">Ugyanakkor az alapértelmezett fizetési dátumot a fizetési időszakban módosíthatja kivételekhez például amikor egy kifizetési dátum ünnepnapra esik.</span><span class="sxs-lookup"><span data-stu-id="09e9f-236">However, you can modify the default payment date in a pay period to allow for exceptions, such as when the payment date falls on a holiday.</span></span>

<span data-ttu-id="09e9f-237">A következő adatokat használja a Dayforce:</span><span class="sxs-lookup"><span data-stu-id="09e9f-237">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="09e9f-238">Fizetési ciklus (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-238">Pay cycle (required)</span></span>
- <span data-ttu-id="09e9f-239">Fizetési ciklus gyakorisága (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-239">Pay cycle frequency (required)</span></span>
- <span data-ttu-id="09e9f-240">Az időszak kezdő dátuma (az első fizetési időszak szükséges)</span><span class="sxs-lookup"><span data-stu-id="09e9f-240">Period start date (first pay period required)</span></span>
- <span data-ttu-id="09e9f-241">Alapértelmezett fizetési dátum (az első fizetési időszak szükséges)</span><span class="sxs-lookup"><span data-stu-id="09e9f-241">Default payment date (first pay period required)</span></span>

<span data-ttu-id="09e9f-242">Ez az információ Dayforceba fizetési csoportokként van integrálva országonként vagy régiónként le van választva egyes kifizetési ciklusokhoz.</span><span class="sxs-lookup"><span data-stu-id="09e9f-242">This information is integrated with Dayforce as pay groups, and is separated by country or region for each pay cycle.</span></span> <span data-ttu-id="09e9f-243">Legalább egy fizetési időszakot kell létrehozni az integráció előtt.</span><span class="sxs-lookup"><span data-stu-id="09e9f-243">At least one pay period must be generated before integration.</span></span> <span data-ttu-id="09e9f-244">Dayforce létrehoz fizetési csoport naptárakat és a kifizetési dátumokat, az első fizetési időszak kezdő dátuma és az alapértelmezett fizetési dátum alapján, melyek a Talentben vannak beállítva.</span><span class="sxs-lookup"><span data-stu-id="09e9f-244">Dayforce generates pay group calendars and payment dates, based on the start date of the first pay period and the default payment date that is set up in Talent.</span></span>

#### <a name="earning-codes"></a><span data-ttu-id="09e9f-245">Bevételkódok</span><span class="sxs-lookup"><span data-stu-id="09e9f-245">Earning codes</span></span>

<span data-ttu-id="09e9f-246">A bevételkódok egyedi módon azonosítják a dolgozók által kapott fizetéstípusokat.</span><span class="sxs-lookup"><span data-stu-id="09e9f-246">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="09e9f-247">A kódoknak különböző paraméterei vannak, amelyek a bevételekhez kapcsolódnak, például könyvelési szabályok, jelentési követelmények és bruttósítási lehetőségek.</span><span class="sxs-lookup"><span data-stu-id="09e9f-247">The codes have various parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span>

<span data-ttu-id="09e9f-248">A következő adatokat használja a Dayforce:</span><span class="sxs-lookup"><span data-stu-id="09e9f-248">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="09e9f-249">Bevételkód (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-249">Earning Code (required)</span></span>
- <span data-ttu-id="09e9f-250">Leírás</span><span class="sxs-lookup"><span data-stu-id="09e9f-250">Description</span></span>
- <span data-ttu-id="09e9f-251">Mértékegység</span><span class="sxs-lookup"><span data-stu-id="09e9f-251">Unit of measure</span></span>
- <span data-ttu-id="09e9f-252">Produktív</span><span class="sxs-lookup"><span data-stu-id="09e9f-252">Productive</span></span>

### <a name="worker-data"></a><span data-ttu-id="09e9f-253">Dolgozóadatok</span><span class="sxs-lookup"><span data-stu-id="09e9f-253">Worker data</span></span>

<span data-ttu-id="09e9f-254">A dolgozók különböző típusaihoz tartozó rekordok, melyek fontosak az emberi erőforrásoknak és a bérlistarendszerekhez.</span><span class="sxs-lookup"><span data-stu-id="09e9f-254">Records for the various types of workers that you have are important to your human resources and payroll systems.</span></span> <span data-ttu-id="09e9f-255">A bevitt információk felhasználhatók az dolgozói és személyes adatok nyilvántartására.</span><span class="sxs-lookup"><span data-stu-id="09e9f-255">The information that you enter can be used to track workers and personal information.</span></span>

<span data-ttu-id="09e9f-256">A dolgozók következő adatait tarthatja karban:</span><span class="sxs-lookup"><span data-stu-id="09e9f-256">You can maintain the following information for workers:</span></span>

- <span data-ttu-id="09e9f-257">**Alapvető** – A dolgozók alapvető információi, például a kapcsolattartási adatok, demográfiai adatok azonosító adatok, családi adatok, a katonai szolgálat állapota, kiküldetésekre vonatkozó adatok, illetve személyes és rendkívüli kapcsolattartók.</span><span class="sxs-lookup"><span data-stu-id="09e9f-257">**Basic** – Maintain basic information about a worker, such as contact information, demographic information, identification information, family information, military service status, expatriate information, and personal and emergency contacts.</span></span>
- <span data-ttu-id="09e9f-258">**Foglalkoztatás** – Információk a dolgozó munkaviszonyáról, például a vállalati vagy szervezeti kapcsolat, hozzárendelt pozíció, kezdő és záró dátumok, munkajogosultság, foglalkoztatás feltételei, nyugdíj, szabadság és áthelyezéssel kapcsolatos információk.</span><span class="sxs-lookup"><span data-stu-id="09e9f-258">**Employment** – Maintain information about a worker's employment, such as company or organization affiliation, position assignment, start and end dates, work eligibility, terms of employment, pension, vacation, and relocation information.</span></span>
- <span data-ttu-id="09e9f-259">**Szabadság és a távollét** – A dolgozó távolléteinek kezelése, például a munkaidő-naptárak, a távolléti tranzakciók és távollét beállítása.</span><span class="sxs-lookup"><span data-stu-id="09e9f-259">**Leave and absence** – Maintain information about a worker's absences, such as working calendars, absence transactions, and absence setup.</span></span>
- <span data-ttu-id="09e9f-260">**Kompenzáció és bérlista** – dolgozói kompenzációs tervek és bérlistainformációk kezelése, például felvétel konstrukciója, jutalmak, teljesítmény, jutalék, adózási információk, nyugdíj és fizetéslevonások.</span><span class="sxs-lookup"><span data-stu-id="09e9f-260">**Compensation and payroll** – Maintain information about a worker's compensation plans and payroll information, such as plan enrollment, awards, performance, commission, tax information, retirement, and salary deductions.</span></span>

<span data-ttu-id="09e9f-261">A dolgozóinformációk létrehozása esetén ne felejtse el a következő adatokat és beállításokat, amelyeket a Dayforce használ.</span><span class="sxs-lookup"><span data-stu-id="09e9f-261">When you enter worker information, keep in mind the following data and configurations that are used in Dayforce.</span></span>

#### <a name="general-information"></a><span data-ttu-id="09e9f-262">Általános információk</span><span class="sxs-lookup"><span data-stu-id="09e9f-262">General information</span></span>

- <span data-ttu-id="09e9f-263">Személyzeti szám (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-263">Personnel number (required)</span></span>
- <span data-ttu-id="09e9f-264">Utónév (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-264">First name (required)</span></span>
- <span data-ttu-id="09e9f-265">Vezetéknév (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-265">Last name (required)</span></span>
- <span data-ttu-id="09e9f-266">Második keresztnév</span><span class="sxs-lookup"><span data-stu-id="09e9f-266">Middle name</span></span>
- <span data-ttu-id="09e9f-267">Szolgálati idő dátuma</span><span class="sxs-lookup"><span data-stu-id="09e9f-267">Seniority date</span></span>
- <span data-ttu-id="09e9f-268">Más néven</span><span class="sxs-lookup"><span data-stu-id="09e9f-268">Known as</span></span>

#### <a name="personal-information"></a><span data-ttu-id="09e9f-269">Személyes információ</span><span class="sxs-lookup"><span data-stu-id="09e9f-269">Personal information</span></span>

- <span data-ttu-id="09e9f-270">Családi állapot (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-270">Marital status (required)</span></span>
- <span data-ttu-id="09e9f-271">Születési dátum (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-271">Birth date (required)</span></span>
- <span data-ttu-id="09e9f-272">Nem (szükséges)</span><span class="sxs-lookup"><span data-stu-id="09e9f-272">Gender (required)</span></span>
- <span data-ttu-id="09e9f-273">Fogyatékkal élő személy</span><span class="sxs-lookup"><span data-stu-id="09e9f-273">Person with disabilities</span></span>
- <span data-ttu-id="09e9f-274">Állampolgárság ország régió (csak a Mexikó)</span><span class="sxs-lookup"><span data-stu-id="09e9f-274">Nationality country region (only for Mexico)</span></span>

#### <a name="address-information"></a><span data-ttu-id="09e9f-275">Címadatok</span><span class="sxs-lookup"><span data-stu-id="09e9f-275">Address information</span></span>

- <span data-ttu-id="09e9f-276">Elsődleges (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-276">Primary (required)</span></span>
- <span data-ttu-id="09e9f-277">Ország/régiót (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-277">Country/region (required)</span></span>
- <span data-ttu-id="09e9f-278">Irányítószámot (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-278">Postal code (required)</span></span>
- <span data-ttu-id="09e9f-279">Utca, házszám (kötelező) (csak Mexikó esetén)</span><span class="sxs-lookup"><span data-stu-id="09e9f-279">Street Number (required) (Only for Mexico)</span></span>
- <span data-ttu-id="09e9f-280">Épületblokk (csak a Mexikó)</span><span class="sxs-lookup"><span data-stu-id="09e9f-280">Building Complement (Only for Mexico)</span></span>
- <span data-ttu-id="09e9f-281">Város (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-281">City (required)</span></span>
- <span data-ttu-id="09e9f-282">Állam (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-282">State (required)</span></span>
- <span data-ttu-id="09e9f-283">Megye (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-283">County (required)</span></span>

#### <a name="contact-information"></a><span data-ttu-id="09e9f-284">Névjegy adatai</span><span class="sxs-lookup"><span data-stu-id="09e9f-284">Contact information</span></span> 

- <span data-ttu-id="09e9f-285">Elsődleges (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-285">Primary (required)</span></span>
- <span data-ttu-id="09e9f-286">Kapcsolattartó száma (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-286">Contact number (required)</span></span>
- <span data-ttu-id="09e9f-287">Mellék</span><span class="sxs-lookup"><span data-stu-id="09e9f-287">Extension</span></span>

#### <a name="payroll-information-and-earning-codes"></a><span data-ttu-id="09e9f-288">Bérlistaadatok és bevételkódok</span><span class="sxs-lookup"><span data-stu-id="09e9f-288">Payroll information and earning codes</span></span>

<span data-ttu-id="09e9f-289">Alkalmazottak hozzárendelhetők meghatározott bevételekhez adott fizetési gyakorisággal, és magadható elsődleges fizetési mód.</span><span class="sxs-lookup"><span data-stu-id="09e9f-289">Employees may be assigned specific earnings at a given frequency of payment and have a preferred payment method.</span></span> <span data-ttu-id="09e9f-290">A következő mezőket a Dayforce arra használja, hogy garantálja, hogy ezeket a preferenciákat és beállításokat használja.</span><span class="sxs-lookup"><span data-stu-id="09e9f-290">The following fields are used in Dayforce to help guarantee that those preferences and settings are used.</span></span>

##### <a name="earning-codes"></a><span data-ttu-id="09e9f-291">Bevételkódok</span><span class="sxs-lookup"><span data-stu-id="09e9f-291">Earning codes</span></span>

- <span data-ttu-id="09e9f-292">Beosztás (szükséges)</span><span class="sxs-lookup"><span data-stu-id="09e9f-292">Position (required)</span></span>
- <span data-ttu-id="09e9f-293">Bevételkód (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-293">Earning Code (required)</span></span>
- <span data-ttu-id="09e9f-294">Gyakoriság (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-294">Frequency (required)</span></span>
- <span data-ttu-id="09e9f-295">Összeg (szükséges)</span><span class="sxs-lookup"><span data-stu-id="09e9f-295">Amount (required)</span></span>

##### <a name="payroll-information"></a><span data-ttu-id="09e9f-296">Bérlistaadatok</span><span class="sxs-lookup"><span data-stu-id="09e9f-296">Payroll information</span></span>

- <span data-ttu-id="09e9f-297">Kifizetési mód</span><span class="sxs-lookup"><span data-stu-id="09e9f-297">Payment Method</span></span>
- <span data-ttu-id="09e9f-298">Gazdasági régió (szükséges)</span><span class="sxs-lookup"><span data-stu-id="09e9f-298">Economic Region (required)</span></span>
- <span data-ttu-id="09e9f-299">Alkalmazott juttatásainak azonosítója</span><span class="sxs-lookup"><span data-stu-id="09e9f-299">Employee Benefits ID</span></span>
- <span data-ttu-id="09e9f-300">Nemzeti azonosító (szükséges)</span><span class="sxs-lookup"><span data-stu-id="09e9f-300">National ID Number (required)</span></span>
- <span data-ttu-id="09e9f-301">Katonai szolgálat száma</span><span class="sxs-lookup"><span data-stu-id="09e9f-301">Military Service Number</span></span>
- <span data-ttu-id="09e9f-302">Műszakazonosító (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-302">Shift ID (required)</span></span>
- <span data-ttu-id="09e9f-303">Adószám (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-303">Tax Number (required)</span></span>
- <span data-ttu-id="09e9f-304">Szakszervezeti azonosító (szükséges)</span><span class="sxs-lookup"><span data-stu-id="09e9f-304">Union ID (required)</span></span>
- <span data-ttu-id="09e9f-305">Munkanap azonosítója (szükséges)</span><span class="sxs-lookup"><span data-stu-id="09e9f-305">Work Day ID (required)</span></span>
- <span data-ttu-id="09e9f-306">Munkavállalási engedély száma</span><span class="sxs-lookup"><span data-stu-id="09e9f-306">Work Permit Number</span></span>

> [!NOTE]
> <span data-ttu-id="09e9f-307">A fizetési módhoz Mexikó támogatja a **Készpénzt**, **Csekket** (a vállalat fizikai csekkjét és az **Elektronikus fizetést**.</span><span class="sxs-lookup"><span data-stu-id="09e9f-307">For the payment method, Mexico supports **Cash**, **Check** (the company's physical check), and **Electronic Payment**.</span></span> <span data-ttu-id="09e9f-308">Ha nincs fizetési mód van megadva, alapértelmezés szerint a **Csekk** használt.</span><span class="sxs-lookup"><span data-stu-id="09e9f-308">If np payment method is specified, **Check** is used by default.</span></span>

#### <a name="employment-details"></a><span data-ttu-id="09e9f-309">Foglalkoztatás részletei</span><span class="sxs-lookup"><span data-stu-id="09e9f-309">Employment details</span></span>

<span data-ttu-id="09e9f-310">Foglalkoztatási előzményei kulcsfontosságú információkat tartalmaznak a munkavállaók felvételi, elbocsátási, és újbóli felvétele állapotával kapcsolatosan a Dayforce-ban.</span><span class="sxs-lookup"><span data-stu-id="09e9f-310">Employment detail history is used as key information to derive an employee's hire, termination, and rehire statuses in Dayforce.</span></span> <span data-ttu-id="09e9f-311">Dayforce egyszerre csak egy aktív foglalkoztatásrekordot tesz lehetővé.</span><span class="sxs-lookup"><span data-stu-id="09e9f-311">Dayforce supports only one active employment record at a time.</span></span>

- <span data-ttu-id="09e9f-312">Foglalkoztatás kezdődátuma (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-312">Employment start date (required)</span></span>
- <span data-ttu-id="09e9f-313">Munkaviszony záró dátuma</span><span class="sxs-lookup"><span data-stu-id="09e9f-313">Employment end date</span></span>
- <span data-ttu-id="09e9f-314">Kezdő dátum</span><span class="sxs-lookup"><span data-stu-id="09e9f-314">Start date</span></span>
- <span data-ttu-id="09e9f-315">Módosított kezdési időpont</span><span class="sxs-lookup"><span data-stu-id="09e9f-315">Adjusted start date</span></span>
- <span data-ttu-id="09e9f-316">Munkaviszony megszűnésének dátuma (megszűntetéskor kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-316">Termination date (required upon termination)</span></span>
- <span data-ttu-id="09e9f-317">Felmondás oka (megszűntetéskor kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-317">Termination reason (required upon termination)</span></span>

<span data-ttu-id="09e9f-318">Az alkalmazott legfontosabb dátumai a következő adatokból vannak származtatva.</span><span class="sxs-lookup"><span data-stu-id="09e9f-318">An employee's key dates are derived by using the following information.</span></span>

| <span data-ttu-id="09e9f-319">Talent</span><span class="sxs-lookup"><span data-stu-id="09e9f-319">Talent</span></span>                | <span data-ttu-id="09e9f-320">Dayforce</span><span class="sxs-lookup"><span data-stu-id="09e9f-320">Dayforce</span></span>                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="09e9f-321">Legutóbbi felvételi dátum</span><span class="sxs-lookup"><span data-stu-id="09e9f-321">Most recent hire date</span></span> | <span data-ttu-id="09e9f-322">Foglalkoztatás kezdete az aktuális nem megszűntetett előzményrekordra</span><span class="sxs-lookup"><span data-stu-id="09e9f-322">Employment start of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="09e9f-323">Munkaviszony megszűnésének dátuma</span><span class="sxs-lookup"><span data-stu-id="09e9f-323">Termination date</span></span>      | <span data-ttu-id="09e9f-324">Foglalkoztatás befejezése az aktuális nem megszűntetett előzményrekordra</span><span class="sxs-lookup"><span data-stu-id="09e9f-324">Termination date of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="09e9f-325">Kezdő dátum</span><span class="sxs-lookup"><span data-stu-id="09e9f-325">Start date</span></span>            | <span data-ttu-id="09e9f-326">Módosított kezdési időpont, kezdődátum vagy foglalkoztatás kezdete az aktuális nem aktív előzményrekordra</span><span class="sxs-lookup"><span data-stu-id="09e9f-326">Adjusted start date, start date, or employment start of current non-active employment history record</span></span> |
| <span data-ttu-id="09e9f-327">Eredeti felvételi dátum</span><span class="sxs-lookup"><span data-stu-id="09e9f-327">Original hire date</span></span>    | <span data-ttu-id="09e9f-328">Foglalkoztatás kezdete legkorábbi foglalkoztatási előzményrekordra</span><span class="sxs-lookup"><span data-stu-id="09e9f-328">Employment start of earliest employment history record</span></span>                                               |

#### <a name="compensation"></a><span data-ttu-id="09e9f-329">Kompenzáció</span><span class="sxs-lookup"><span data-stu-id="09e9f-329">Compensation</span></span>

<span data-ttu-id="09e9f-330">Egy fix kompenzációs tervet kell társítani minden alkalmazott elsődleges pozíciójához az alkalmazási időszak alatt.</span><span class="sxs-lookup"><span data-stu-id="09e9f-330">A fixed compensation plan must be associated with every employee's primary position throughout an employment period.</span></span> <span data-ttu-id="09e9f-331">Az időszak a belépés dátumával (vagy a foglalkoztatás kezdő dátumával) kezdődik, és a munkaviszony megszűnéséig tart .</span><span class="sxs-lookup"><span data-stu-id="09e9f-331">This period starts on the date that the employee was hired (or the employment start date) and continues until termination.</span></span>

- <span data-ttu-id="09e9f-332">Érvényesség dátuma (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-332">Effective Date (required)</span></span>
- <span data-ttu-id="09e9f-333">Lejárati dátum</span><span class="sxs-lookup"><span data-stu-id="09e9f-333">Expiration date</span></span>
- <span data-ttu-id="09e9f-334">Fizetési díjalap (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-334">Pay Rate (required)</span></span>
- <span data-ttu-id="09e9f-335">Fizetési díjalapok átalakításai (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-335">Pay Rate Conversions (required)</span></span>
- <span data-ttu-id="09e9f-336">Évi egyenérték (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-336">Annual equivalent (required)</span></span>
- <span data-ttu-id="09e9f-337">Óránkénti egyenérték (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-337">Hourly equivalent (required)</span></span>

<span data-ttu-id="09e9f-338">Ha az óránkénti alkalmazottnak több beosztása van, az elsődleges beosztásához tartozó fix kompenzációja importálva lesz a Dayforce-ba, alkalmazott szintű alapdíj/-fizetés.</span><span class="sxs-lookup"><span data-stu-id="09e9f-338">If an hourly employee has multiple positions, the fixed compensation of the primary position is imported into Dayforce as the employee-level base rate/salary.</span></span> <span data-ttu-id="09e9f-339">A nem elsődleges beosztások esetén, az óránkénti díj a megfelelő pozícióba lesz mentve Dayforce-ban.</span><span class="sxs-lookup"><span data-stu-id="09e9f-339">For non-primary positions, the hourly rate is saved to the corresponding position in Dayforce.</span></span>

<span data-ttu-id="09e9f-340">Ha a fizetett alkalmazott több beosztással rendelkezik, a összesített óradíj és éves fizetés származtatva lesz az összes aktív beosztásból mint az alkalmazotti szintű alapdíj/-fizetés.</span><span class="sxs-lookup"><span data-stu-id="09e9f-340">If a salaried employee has multiple positions, the cumulative hour rate and annual salary across all active positions are derived and used as the employee-level base rate/salary.</span></span>

#### <a name="identification-numbers"></a><span data-ttu-id="09e9f-341">Azonosítószámok</span><span class="sxs-lookup"><span data-stu-id="09e9f-341">Identification numbers</span></span>

##### <a name="social-security-identifier"></a><span data-ttu-id="09e9f-342">Társadalombiztosítási azonosító</span><span class="sxs-lookup"><span data-stu-id="09e9f-342">Social Security identifier</span></span> 

<span data-ttu-id="09e9f-343">Minden alkalmazottnak kell egy elsődleges azonosítóval rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="09e9f-343">Every employee must have one primary identifier.</span></span> <span data-ttu-id="09e9f-344">Ez az azonosító legyen **TAJ-szám** azonosítótípus kell legyen.</span><span class="sxs-lookup"><span data-stu-id="09e9f-344">This identifier must be of **SSN** identification type.</span></span> <span data-ttu-id="09e9f-345">A Dayforce-ban automatikusan van származtatva az alkalmazott társadalombiztosítási azonosítójából, mely a felvételhez szükséges.</span><span class="sxs-lookup"><span data-stu-id="09e9f-345">In Dayforce, it's automatically derived as the employee's Social Security identifier that is required for hire.</span></span>

- <span data-ttu-id="09e9f-346">Elsődleges (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-346">Primary (required)</span></span>
- <span data-ttu-id="09e9f-347">Azonosító típusa = „TAJ-szám”</span><span class="sxs-lookup"><span data-stu-id="09e9f-347">Identification Type = "SSN"</span></span>
- <span data-ttu-id="09e9f-348">Kibocsátás dátuma</span><span class="sxs-lookup"><span data-stu-id="09e9f-348">Issued Date</span></span>
- <span data-ttu-id="09e9f-349">Lejárat dátuma</span><span class="sxs-lookup"><span data-stu-id="09e9f-349">Expiration Date</span></span>

<span data-ttu-id="09e9f-350">Az alkalmazottak több azonosítószámot is megadhatnak **TAJ-szám** azonosítótípushoz.</span><span class="sxs-lookup"><span data-stu-id="09e9f-350">Employees can declare multiple identification numbers of the **SSN** identification type.</span></span> <span data-ttu-id="09e9f-351">Azonban csak az **Elsődlegesként** megjelölt rekord van integrálva Dayforce-ba, függetlenül attól, hogy a szám aktív vagy lejárt.</span><span class="sxs-lookup"><span data-stu-id="09e9f-351">However, only the record that is marked as **Primary** is integrated into Dayforce, regardless of whether the number is active or expired.</span></span>

#### <a name="bank-accounts-and-disbursements"></a><span data-ttu-id="09e9f-352">Bankszámlák és kifizetések</span><span class="sxs-lookup"><span data-stu-id="09e9f-352">Bank accounts and disbursements</span></span>

<span data-ttu-id="09e9f-353">Érvényes bankszámlaadatokat meg kell adni minden olyan alkalmazotthoz, aki úgy dönt, hogy a banki átutalással kéri fizetését.</span><span class="sxs-lookup"><span data-stu-id="09e9f-353">Valid bank account information must be entered for any employee who chooses to be paid via bank account transfers.</span></span>

| <span data-ttu-id="09e9f-354">Talent</span><span class="sxs-lookup"><span data-stu-id="09e9f-354">Talent</span></span>                         | <span data-ttu-id="09e9f-355">Dayforce</span><span class="sxs-lookup"><span data-stu-id="09e9f-355">Dayforce</span></span>                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="09e9f-356">Bankszámlaszám (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-356">Bank account number (required)</span></span> |                                                                                                             |
| <span data-ttu-id="09e9f-357">SWIFT-kód (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-357">SWIFT code (required)</span></span>          | <span data-ttu-id="09e9f-358">**Bankazonosító** ez a mező Mexikóban történő bérlistafeldolgozáskor használatos.</span><span class="sxs-lookup"><span data-stu-id="09e9f-358">**Bank ID** field used when processing payroll in Mexico.</span></span>                                                             |
| <span data-ttu-id="09e9f-359">Ágazati szám (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-359">Branch number (required)</span></span>       |                                                                                                             |
| <span data-ttu-id="09e9f-360">Bankszámla típusa (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-360">Bank account type (required)</span></span>   | <span data-ttu-id="09e9f-361">**Számlatípus** ez a mező Mexikóban történő bérlistafeldolgozáskor használatos.</span><span class="sxs-lookup"><span data-stu-id="09e9f-361">**Account type** field used when processing payroll in Mexico.</span></span> <span data-ttu-id="09e9f-362">Támogatott értékek: **Folyószámla** és **Bérlista**</span><span class="sxs-lookup"><span data-stu-id="09e9f-362">Supported values include **Checking** and **Payroll**.</span></span> |

> [!NOTE]
> <span data-ttu-id="09e9f-363">Alkalmazottak, akik úgy döntenek, hogy a banki átutaláson keresztülkérik fizetésük, meg kell adniuk egy hivatkozást egy jogi személyhez tartozó egyenlegszámlához, melynek elsődleges címének Mexikóban kell lennie és egy Mexikói bank érvényes bankszámlájához van társítva.</span><span class="sxs-lookup"><span data-stu-id="09e9f-363">Employees who choose to be paid via bank account transfers must provide a link to a remainder account that is under a legal entity that has its primary address in Mexico and associated with a valid bank account from a Mexican bank.</span></span> <span data-ttu-id="09e9f-364">Minden egyéb nem egyenlegszámla figyelmen kívül lesz hagyva.</span><span class="sxs-lookup"><span data-stu-id="09e9f-364">All other non-remainder accounts are ignored.</span></span>

#### <a name="address-information"></a><span data-ttu-id="09e9f-365">Címadatok</span><span class="sxs-lookup"><span data-stu-id="09e9f-365">Address information</span></span>

<span data-ttu-id="09e9f-366">Minden alkalmazottnak kell egy elsődleges hellyel rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="09e9f-366">Every employee must have one primary location.</span></span> <span data-ttu-id="09e9f-367">A Dayforce-ban ezen hely alapján van meghatározva az alkalmazott elsődleges tartózkodási helye adózási célokból.</span><span class="sxs-lookup"><span data-stu-id="09e9f-367">In Dayforce, this location is used to determine the employee's primary residence for tax purposes.</span></span>

- <span data-ttu-id="09e9f-368">Elsődleges (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-368">Primary (required)</span></span>
- <span data-ttu-id="09e9f-369">Ország/régiót (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-369">Country/region (required)</span></span>
- <span data-ttu-id="09e9f-370">Irányítószám/postai kód (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-370">Zip/postal code (required)</span></span>
- <span data-ttu-id="09e9f-371">Utca (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-371">Street (required)</span></span>
- <span data-ttu-id="09e9f-372">Házszám (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-372">Street Number (required)</span></span>
- <span data-ttu-id="09e9f-373">Épületblokk</span><span class="sxs-lookup"><span data-stu-id="09e9f-373">Building Complement</span></span>
- <span data-ttu-id="09e9f-374">Város (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-374">City (required)</span></span>
- <span data-ttu-id="09e9f-375">Állam (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-375">State (required)</span></span>
- <span data-ttu-id="09e9f-376">Megye (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-376">County (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a><span data-ttu-id="09e9f-377">Az adatok konfigurálása bérlista létrehozásához az Egyesült Államokban és Kanadában</span><span class="sxs-lookup"><span data-stu-id="09e9f-377">Configure your data to generate payroll in United States and Canada</span></span>

<span data-ttu-id="09e9f-378">Ha a fizetést generálása alkalmazottaknak az Egyesült Államokban és Kanadában, a következő elemeket kell beállítani:</span><span class="sxs-lookup"><span data-stu-id="09e9f-378">If you're generating pay for employees in the United States and Canada, the following elements must be configured:</span></span>

- <span data-ttu-id="09e9f-379">Részlegek szükségesek beosztásokhoz.</span><span class="sxs-lookup"><span data-stu-id="09e9f-379">Departments are required on positions.</span></span>
- <span data-ttu-id="09e9f-380">Költséghelyek pénzügyi dimenziókként kell beállítani, és az alapértelmezett pénzügyi dimenzió karakterlánc első elemének kell lennie.</span><span class="sxs-lookup"><span data-stu-id="09e9f-380">Cost centers must be set as financial dimensions and must be the first element in the default financial dimension string.</span></span>

> [!NOTE] 
> <span data-ttu-id="09e9f-381">Beállíthatja a Talent szolgáltatást úgy, hogy a Beosztásokhoz kötelező legyen beállítani Részleget.</span><span class="sxs-lookup"><span data-stu-id="09e9f-381">You can configure Talent to require that Positions specify a Department.</span></span> <span data-ttu-id="09e9f-382">Ehhez kattintson a **Emberi erőforrások megosztott beosztásai > Beosztások > Részlegek szükségesek beosztásokhoz.** elemre.</span><span class="sxs-lookup"><span data-stu-id="09e9f-382">To do this, go to **Human Resources Shared Positions > Positions > Require departments on positions**.</span></span> <span data-ttu-id="09e9f-383">Azt ajánljuk, hogy ezt a beállítást tartassa be az integráció során.</span><span class="sxs-lookup"><span data-stu-id="09e9f-383">We recommend that this setting be enforced for the integration.</span></span>

### <a name="job-types"></a><span data-ttu-id="09e9f-384">Feladattípusok</span><span class="sxs-lookup"><span data-stu-id="09e9f-384">Job types</span></span>

<span data-ttu-id="09e9f-385">Beosztástípusok használatával a hasonló feladatok kategóriákba sorolhatók.</span><span class="sxs-lookup"><span data-stu-id="09e9f-385">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="09e9f-386">A beosztástípusok szükségesek az Egyesült Államokban és Kanadában a bérlisták feldolgozásához.</span><span class="sxs-lookup"><span data-stu-id="09e9f-386">Job types are required in order to process payroll in the United States and Canada.</span></span> <span data-ttu-id="09e9f-387">Beosztástípusok többek között a teljes és részmunkaidős, illetve a munkabéres és az órabéres.</span><span class="sxs-lookup"><span data-stu-id="09e9f-387">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="09e9f-388">A beosztástípusok a fizetéstípusokként vannak hozzárendelve a Dayforce-hoz, melyek jelzik, hogy a munkavállaló órás vagy bérezéses.</span><span class="sxs-lookup"><span data-stu-id="09e9f-388">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="09e9f-389">A következő feladattípusok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="09e9f-389">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="09e9f-390">Feladattípus</span><span class="sxs-lookup"><span data-stu-id="09e9f-390">Job type</span></span>   | <span data-ttu-id="09e9f-391">Leírás</span><span class="sxs-lookup"><span data-stu-id="09e9f-391">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="09e9f-392">Óránként</span><span class="sxs-lookup"><span data-stu-id="09e9f-392">Hourly</span></span>     | <span data-ttu-id="09e9f-393">Óránként</span><span class="sxs-lookup"><span data-stu-id="09e9f-393">Hourly</span></span>      |
| <span data-ttu-id="09e9f-394">Bérezéses</span><span class="sxs-lookup"><span data-stu-id="09e9f-394">Salaried</span></span>   | <span data-ttu-id="09e9f-395">Bérezéses</span><span class="sxs-lookup"><span data-stu-id="09e9f-395">Salaried</span></span>    |

### <a name="position-types"></a><span data-ttu-id="09e9f-396">Beosztási típusok</span><span class="sxs-lookup"><span data-stu-id="09e9f-396">Position types</span></span> 

<span data-ttu-id="09e9f-397">Ne használjon beosztástípusokat annak leírására, hogy a beosztás teljes munkaidős, részmunkaidős vagy más.</span><span class="sxs-lookup"><span data-stu-id="09e9f-397">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="09e9f-398">A feladattípusok a fizetésosztályokként vannak hozzárendelve a Dayforce-hoz, melyek jelzik, hogy a munkavállaló teljes- vagy részmunkaidős.</span><span class="sxs-lookup"><span data-stu-id="09e9f-398">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="09e9f-399">A következő beosztástípusok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="09e9f-399">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="09e9f-400">Beosztás típusa</span><span class="sxs-lookup"><span data-stu-id="09e9f-400">Position type</span></span>   | <span data-ttu-id="09e9f-401">Leírás</span><span class="sxs-lookup"><span data-stu-id="09e9f-401">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="09e9f-402">Teljes munkaidős</span><span class="sxs-lookup"><span data-stu-id="09e9f-402">Full-time</span></span>       | <span data-ttu-id="09e9f-403">Teljes munkaidős alkalmazott</span><span class="sxs-lookup"><span data-stu-id="09e9f-403">Full time employee</span></span> |
| <span data-ttu-id="09e9f-404">Részmunkaidős</span><span class="sxs-lookup"><span data-stu-id="09e9f-404">Part-time</span></span>       | <span data-ttu-id="09e9f-405">Részmunkaidős alkalmazott</span><span class="sxs-lookup"><span data-stu-id="09e9f-405">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="09e9f-406">Okkódok</span><span class="sxs-lookup"><span data-stu-id="09e9f-406">Reason codes</span></span>

<span data-ttu-id="09e9f-407">Az alkalmazottak állapotával kapcsolatos okkódok tájékoztatnak.</span><span class="sxs-lookup"><span data-stu-id="09e9f-407">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="09e9f-408">Okkódok a Dayforce-hoz állapot okaként vannak hozzárendelve, melyek jelzik egy alkalmazott beosztásában vagy alkalmazotti státuszában bekövetkezett változások okát.</span><span class="sxs-lookup"><span data-stu-id="09e9f-408">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="09e9f-409">A következő okkódok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="09e9f-409">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="09e9f-410">Okkód</span><span class="sxs-lookup"><span data-stu-id="09e9f-410">Reason code</span></span>    | <span data-ttu-id="09e9f-411">Leírás</span><span class="sxs-lookup"><span data-stu-id="09e9f-411">Description</span></span>      | <span data-ttu-id="09e9f-412">Alkalmazandó forgatókönyvek</span><span class="sxs-lookup"><span data-stu-id="09e9f-412">Applicable scenarios</span></span> |
|----------------|------------------|----------------------|
| <span data-ttu-id="09e9f-413">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="09e9f-413">RESIGNATION</span></span>    | <span data-ttu-id="09e9f-414">Felmondás</span><span class="sxs-lookup"><span data-stu-id="09e9f-414">Resignation</span></span>      | <span data-ttu-id="09e9f-415">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="09e9f-415">Terminate worker</span></span>     |
| <span data-ttu-id="09e9f-416">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="09e9f-416">TERMINATION</span></span>    | <span data-ttu-id="09e9f-417">Befejezés</span><span class="sxs-lookup"><span data-stu-id="09e9f-417">Termination</span></span>      | <span data-ttu-id="09e9f-418">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="09e9f-418">Terminate worker</span></span>     |
| <span data-ttu-id="09e9f-419">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="09e9f-419">RETIREMENT</span></span>     | <span data-ttu-id="09e9f-420">Megszüntetés</span><span class="sxs-lookup"><span data-stu-id="09e9f-420">Retirement</span></span>       | <span data-ttu-id="09e9f-421">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="09e9f-421">Terminate worker</span></span>     |
| <span data-ttu-id="09e9f-422">EGYÉB</span><span class="sxs-lookup"><span data-stu-id="09e9f-422">OTHER</span></span>          | <span data-ttu-id="09e9f-423">Egyéb okok</span><span class="sxs-lookup"><span data-stu-id="09e9f-423">Other Reasons</span></span>    | <span data-ttu-id="09e9f-424">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="09e9f-424">Terminate worker</span></span>     |
| <span data-ttu-id="09e9f-425">DEATH</span><span class="sxs-lookup"><span data-stu-id="09e9f-425">DEATH</span></span>          | <span data-ttu-id="09e9f-426">Elhalálozás</span><span class="sxs-lookup"><span data-stu-id="09e9f-426">Death</span></span>            | <span data-ttu-id="09e9f-427">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="09e9f-427">Terminate worker</span></span>     |
| <span data-ttu-id="09e9f-428">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="09e9f-428">LEAVEOFABSENCE</span></span> | <span data-ttu-id="09e9f-429">Szabadság</span><span class="sxs-lookup"><span data-stu-id="09e9f-429">Leave of Absence</span></span> | <span data-ttu-id="09e9f-430">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="09e9f-430">Terminate worker</span></span>     |
| <span data-ttu-id="09e9f-431">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="09e9f-431">CONTRACTEND</span></span>    | <span data-ttu-id="09e9f-432">Szerződés vége</span><span class="sxs-lookup"><span data-stu-id="09e9f-432">End of Contract</span></span>  | <span data-ttu-id="09e9f-433">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="09e9f-433">Terminate worker</span></span>     |
| <span data-ttu-id="09e9f-434">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="09e9f-434">SALARYCHANGE</span></span>   | <span data-ttu-id="09e9f-435">Munkabér módosítása</span><span class="sxs-lookup"><span data-stu-id="09e9f-435">Change of Salary</span></span> | <span data-ttu-id="09e9f-436">Kompenzáció</span><span class="sxs-lookup"><span data-stu-id="09e9f-436">Compensation</span></span>         |

### <a name="marital-status"></a><span data-ttu-id="09e9f-437">Családi állapot</span><span class="sxs-lookup"><span data-stu-id="09e9f-437">Marital status</span></span>

<span data-ttu-id="09e9f-438">Családi állapot értékei Dayforce-hoz vannak rendelve és konvertálva szükség esetén az elfogadható értékekre az integráció során.</span><span class="sxs-lookup"><span data-stu-id="09e9f-438">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="09e9f-439">Az alábbi táblázat bemutatja, hogy családi állapot értékek hogyan vannak leképezve a Dayforce -ban.</span><span class="sxs-lookup"><span data-stu-id="09e9f-439">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="09e9f-440">Talent</span><span class="sxs-lookup"><span data-stu-id="09e9f-440">Talent</span></span>                 | <span data-ttu-id="09e9f-441">Dayforce</span><span class="sxs-lookup"><span data-stu-id="09e9f-441">Dayforce</span></span>             |
|------------------------|----------------------|
| <span data-ttu-id="09e9f-442">Házas</span><span class="sxs-lookup"><span data-stu-id="09e9f-442">Married</span></span>                | <span data-ttu-id="09e9f-443">Házas</span><span class="sxs-lookup"><span data-stu-id="09e9f-443">Married</span></span>              |
| <span data-ttu-id="09e9f-444">Egy</span><span class="sxs-lookup"><span data-stu-id="09e9f-444">Single</span></span>                 | <span data-ttu-id="09e9f-445">Egy</span><span class="sxs-lookup"><span data-stu-id="09e9f-445">Single</span></span>               |
| <span data-ttu-id="09e9f-446">Özvegy</span><span class="sxs-lookup"><span data-stu-id="09e9f-446">Widowed</span></span>                | <span data-ttu-id="09e9f-447">Özvegy</span><span class="sxs-lookup"><span data-stu-id="09e9f-447">Widowed</span></span>              |
| <span data-ttu-id="09e9f-448">Elvált</span><span class="sxs-lookup"><span data-stu-id="09e9f-448">Divorced</span></span>               | <span data-ttu-id="09e9f-449">Elvált</span><span class="sxs-lookup"><span data-stu-id="09e9f-449">Divorced</span></span>             |
| <span data-ttu-id="09e9f-450">Bejegyzett élettársi kapcsolat</span><span class="sxs-lookup"><span data-stu-id="09e9f-450">Registered Partnership</span></span> | <span data-ttu-id="09e9f-451">Élettársi viszony</span><span class="sxs-lookup"><span data-stu-id="09e9f-451">Domestic Partnership</span></span> |
| <span data-ttu-id="09e9f-452">Nincs</span><span class="sxs-lookup"><span data-stu-id="09e9f-452">None</span></span>                   | <span data-ttu-id="09e9f-453">Nincs</span><span class="sxs-lookup"><span data-stu-id="09e9f-453">None</span></span>                 |
| <span data-ttu-id="09e9f-454">Együttélés</span><span class="sxs-lookup"><span data-stu-id="09e9f-454">Cohabiting</span></span>             | <span data-ttu-id="09e9f-455">Együttélés</span><span class="sxs-lookup"><span data-stu-id="09e9f-455">Cohabiting</span></span>           |

### <a name="gender"></a><span data-ttu-id="09e9f-456">Nem</span><span class="sxs-lookup"><span data-stu-id="09e9f-456">Gender</span></span>

<span data-ttu-id="09e9f-457">A nemek a Dayforce-hoz vannak rendelve és konvertálva szükség esetén az elfogadható értékekre az integráció során.</span><span class="sxs-lookup"><span data-stu-id="09e9f-457">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="09e9f-458">Az alábbi táblázat bemutatja, hogy a nemek hogyan vannak leképezve a Dayforce-ban.</span><span class="sxs-lookup"><span data-stu-id="09e9f-458">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="09e9f-459">Talent</span><span class="sxs-lookup"><span data-stu-id="09e9f-459">Talent</span></span>       | <span data-ttu-id="09e9f-460">Dayforce</span><span class="sxs-lookup"><span data-stu-id="09e9f-460">Dayforce</span></span>        |
|--------------|-----------------|
| <span data-ttu-id="09e9f-461">Férfi</span><span class="sxs-lookup"><span data-stu-id="09e9f-461">Male</span></span>         | <span data-ttu-id="09e9f-462">Férfi</span><span class="sxs-lookup"><span data-stu-id="09e9f-462">Male</span></span>            |
| <span data-ttu-id="09e9f-463">Nő</span><span class="sxs-lookup"><span data-stu-id="09e9f-463">Female</span></span>       | <span data-ttu-id="09e9f-464">Nő</span><span class="sxs-lookup"><span data-stu-id="09e9f-464">Female</span></span>          |
| <span data-ttu-id="09e9f-465">Nem meghatározott</span><span class="sxs-lookup"><span data-stu-id="09e9f-465">Non-specific</span></span> | <span data-ttu-id="09e9f-466">*Nem támogatott*</span><span class="sxs-lookup"><span data-stu-id="09e9f-466">*Not supported*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="09e9f-467">Bevételkódok</span><span class="sxs-lookup"><span data-stu-id="09e9f-467">Earning codes</span></span>

<span data-ttu-id="09e9f-468">A bevételkódok egyedi módon azonosítják a dolgozók által kapott fizetéstípusokat.</span><span class="sxs-lookup"><span data-stu-id="09e9f-468">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="09e9f-469">A kódoknak különböző paramétereket fednek le, amelyek a bevételekhez kapcsolódnak, például könyvelési szabályok, jelentési követelmények és bruttósítási lehetőségek.</span><span class="sxs-lookup"><span data-stu-id="09e9f-469">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="09e9f-470">Ha egy nem támogatott gyakoriság van használatban, a **Minden fizetés** gyakorisága van alapértelmezés szerint használva a kiszámításhoz.</span><span class="sxs-lookup"><span data-stu-id="09e9f-470">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="09e9f-471">Támogatott gyakoriságok</span><span class="sxs-lookup"><span data-stu-id="09e9f-471">Supported frequencies</span></span>

- <span data-ttu-id="09e9f-472">Összes</span><span class="sxs-lookup"><span data-stu-id="09e9f-472">All</span></span>
- <span data-ttu-id="09e9f-473">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="09e9f-473">EVERYPAY</span></span>
- <span data-ttu-id="09e9f-474">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="09e9f-474">EACHPAYPERIOD</span></span>
- <span data-ttu-id="09e9f-475">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="09e9f-475">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="09e9f-476">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="09e9f-476">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="09e9f-477">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="09e9f-477">1OFMTH</span></span>
- <span data-ttu-id="09e9f-478">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="09e9f-478">LASTOFMTH</span></span>
- <span data-ttu-id="09e9f-479">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="09e9f-479">2OFMTH</span></span>
- <span data-ttu-id="09e9f-480">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="09e9f-480">3OFMTH</span></span>
- <span data-ttu-id="09e9f-481">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="09e9f-481">4OFMTH</span></span>
- <span data-ttu-id="09e9f-482">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="09e9f-482">5OFMTH</span></span>
- <span data-ttu-id="09e9f-483">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="09e9f-483">1N2OFMTH</span></span>
- <span data-ttu-id="09e9f-484">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="09e9f-484">3N4OFMTH</span></span>
- <span data-ttu-id="09e9f-485">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="09e9f-485">1N3OFMTH</span></span>
- <span data-ttu-id="09e9f-486">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="09e9f-486">1N4OFMTH</span></span>
- <span data-ttu-id="09e9f-487">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="09e9f-487">2N3OFMTH</span></span>
- <span data-ttu-id="09e9f-488">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="09e9f-488">2N4OFMTH</span></span>
- <span data-ttu-id="09e9f-489">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="09e9f-489">1N2N3OFMTH</span></span>
- <span data-ttu-id="09e9f-490">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="09e9f-490">1N2N4OFMTH</span></span>
- <span data-ttu-id="09e9f-491">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="09e9f-491">1N3N4OFMTH</span></span>
- <span data-ttu-id="09e9f-492">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="09e9f-492">2N3N4OFMTH</span></span>
- <span data-ttu-id="09e9f-493">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="09e9f-493">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="09e9f-494">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="09e9f-494">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="09e9f-495">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="09e9f-495">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="09e9f-496">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="09e9f-496">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="09e9f-497">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="09e9f-497">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="09e9f-498">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="09e9f-498">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="09e9f-499">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="09e9f-499">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="09e9f-500">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="09e9f-500">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="09e9f-501">Címek</span><span class="sxs-lookup"><span data-stu-id="09e9f-501">Addresses</span></span>

<span data-ttu-id="09e9f-502">Az adott ország vagy régió, állam és megye (település) kódok specifikus formátumokat követelnek, hogy Dayforce és az országos és regionális szolgáltatók felismerjék azokat.</span><span class="sxs-lookup"><span data-stu-id="09e9f-502">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="09e9f-503">Annak ellenére, hogy a városok formátuma rugalmas, minden városnak társítva kell lennie egy államhoz.</span><span class="sxs-lookup"><span data-stu-id="09e9f-503">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="09e9f-504">Talent</span><span class="sxs-lookup"><span data-stu-id="09e9f-504">Talent</span></span>          | <span data-ttu-id="09e9f-505">Dayforce</span><span class="sxs-lookup"><span data-stu-id="09e9f-505">Dayforce</span></span>              |
|-----------------|-----------------------|
| <span data-ttu-id="09e9f-506">Ország/régió</span><span class="sxs-lookup"><span data-stu-id="09e9f-506">Country/Region</span></span>  | <span data-ttu-id="09e9f-507">Országkód</span><span class="sxs-lookup"><span data-stu-id="09e9f-507">Country Code</span></span>          |
| <span data-ttu-id="09e9f-508">Irányítószám / postai kód</span><span class="sxs-lookup"><span data-stu-id="09e9f-508">Zip/Postal Code</span></span> | <span data-ttu-id="09e9f-509">Irányítószám</span><span class="sxs-lookup"><span data-stu-id="09e9f-509">Postal Code</span></span>           |
| <span data-ttu-id="09e9f-510">Állami</span><span class="sxs-lookup"><span data-stu-id="09e9f-510">State</span></span>           | <span data-ttu-id="09e9f-511">Államkód</span><span class="sxs-lookup"><span data-stu-id="09e9f-511">State Code</span></span>            |
| <span data-ttu-id="09e9f-512">Város</span><span class="sxs-lookup"><span data-stu-id="09e9f-512">City</span></span>            | <span data-ttu-id="09e9f-513">Város</span><span class="sxs-lookup"><span data-stu-id="09e9f-513">City</span></span>                  |
| <span data-ttu-id="09e9f-514">Megye</span><span class="sxs-lookup"><span data-stu-id="09e9f-514">County</span></span>          | <span data-ttu-id="09e9f-515">Megye (Helyhatóság)</span><span class="sxs-lookup"><span data-stu-id="09e9f-515">County (Municipality)</span></span> |
| <span data-ttu-id="09e9f-516">Utca</span><span class="sxs-lookup"><span data-stu-id="09e9f-516">Street</span></span>          | <span data-ttu-id="09e9f-517">Cím 1. sora</span><span class="sxs-lookup"><span data-stu-id="09e9f-517">Address Line 1</span></span>        |

### <a name="tax-regions"></a><span data-ttu-id="09e9f-518">Adórégiók</span><span class="sxs-lookup"><span data-stu-id="09e9f-518">Tax regions</span></span>

<span data-ttu-id="09e9f-519">Az adórégiók a megfelelő adó megállapítására szolgálnak, amelyet a bérlista létrehozásakor kell alkalmazni.</span><span class="sxs-lookup"><span data-stu-id="09e9f-519">Tax regions are used to determine the appropriate tax that should be applied during payroll generation.</span></span> <span data-ttu-id="09e9f-520">Az adórégiók helycímként vannak a Dayforce-hoz rendelve.</span><span class="sxs-lookup"><span data-stu-id="09e9f-520">Tax regions are mapped to Dayforce as location addresses.</span></span> <span data-ttu-id="09e9f-521">Az alapértelmezett adórégiót a dolgozó aktív beosztásával kell társítani.</span><span class="sxs-lookup"><span data-stu-id="09e9f-521">The default tax region must be associated with the worker's active position.</span></span> 

- <span data-ttu-id="09e9f-522">Adórégió (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-522">Tax region (required)</span></span>
- <span data-ttu-id="09e9f-523">Ország/régió (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-523">Country/Region (required)</span></span>
- <span data-ttu-id="09e9f-524">Állam (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-524">State (required)</span></span>
- <span data-ttu-id="09e9f-525">Megye</span><span class="sxs-lookup"><span data-stu-id="09e9f-525">County</span></span> 
- <span data-ttu-id="09e9f-526">Város (kötelező)</span><span class="sxs-lookup"><span data-stu-id="09e9f-526">City (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a><span data-ttu-id="09e9f-527">Adatok konfigurálása bérlista létrehozásához Mexikóban</span><span class="sxs-lookup"><span data-stu-id="09e9f-527">Configure your data to generate payroll in Mexico</span></span>

<span data-ttu-id="09e9f-528">Ha a fizetést generál alkalmazottaknak Mexikóban, a következő elemeket kell beállítani:</span><span class="sxs-lookup"><span data-stu-id="09e9f-528">If you're generating pay for employees in Mexico, the following elements must be configured:</span></span>

- <span data-ttu-id="09e9f-529">Részlegek szükségesek beosztásokhoz.</span><span class="sxs-lookup"><span data-stu-id="09e9f-529">Departments are required on positions.</span></span>
- <span data-ttu-id="09e9f-530">Költséghelyek pénzügyi dimenziókként kell beállítani, és az Alapértelmezett pénzügyi dimenzió karakterlánc első elemének kell lennie.</span><span class="sxs-lookup"><span data-stu-id="09e9f-530">Cost centers must be set as financial dimensions and must be the first element in the Default Financial Dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="09e9f-531">Beosztástípusok</span><span class="sxs-lookup"><span data-stu-id="09e9f-531">Job types</span></span>

<span data-ttu-id="09e9f-532">Beosztástípusok használatával a hasonló feladatok kategóriákba sorolhatók.</span><span class="sxs-lookup"><span data-stu-id="09e9f-532">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="09e9f-533">Mexikóban a Bérlista feldolgozásához feladattípusok szükségesek.</span><span class="sxs-lookup"><span data-stu-id="09e9f-533">Job types are required in order to process payroll in Mexico.</span></span> <span data-ttu-id="09e9f-534">Beosztástípusok többek között a teljes és részmunkaidős, illetve a munkabéres és az órabéres.</span><span class="sxs-lookup"><span data-stu-id="09e9f-534">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="09e9f-535">A beosztástípusok a fizetéstípusokként vannak hozzárendelve a Dayforce-hoz, melyek jelzik, hogy a munkavállaló órás vagy bérezéses.</span><span class="sxs-lookup"><span data-stu-id="09e9f-535">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="09e9f-536">A következő feladattípusok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="09e9f-536">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="09e9f-537">Feladattípus</span><span class="sxs-lookup"><span data-stu-id="09e9f-537">Job type</span></span>   | <span data-ttu-id="09e9f-538">Leírás</span><span class="sxs-lookup"><span data-stu-id="09e9f-538">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="09e9f-539">Óránként</span><span class="sxs-lookup"><span data-stu-id="09e9f-539">Hourly</span></span>     | <span data-ttu-id="09e9f-540">MX Órabér</span><span class="sxs-lookup"><span data-stu-id="09e9f-540">MX Hourly</span></span>   |
| <span data-ttu-id="09e9f-541">Bérezéses</span><span class="sxs-lookup"><span data-stu-id="09e9f-541">Salaried</span></span>   | <span data-ttu-id="09e9f-542">MX Bérezéses</span><span class="sxs-lookup"><span data-stu-id="09e9f-542">MX Salaried</span></span> |

### <a name="position-types"></a><span data-ttu-id="09e9f-543">Beosztási típusok</span><span class="sxs-lookup"><span data-stu-id="09e9f-543">Position types</span></span> 

<span data-ttu-id="09e9f-544">Ne használjon beosztástípusokat annak leírására, hogy a beosztás teljes munkaidős, részmunkaidős vagy más.</span><span class="sxs-lookup"><span data-stu-id="09e9f-544">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="09e9f-545">A feladattípusok a fizetésosztályokként vannak hozzárendelve a Dayforce-hoz, melyek jelzik, hogy a munkavállaló teljes- vagy részmunkaidős.</span><span class="sxs-lookup"><span data-stu-id="09e9f-545">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="09e9f-546">A következő beosztástípusok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="09e9f-546">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="09e9f-547">Beosztás típusa</span><span class="sxs-lookup"><span data-stu-id="09e9f-547">Position type</span></span>   | <span data-ttu-id="09e9f-548">Leírás</span><span class="sxs-lookup"><span data-stu-id="09e9f-548">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="09e9f-549">Teljes munkaidős</span><span class="sxs-lookup"><span data-stu-id="09e9f-549">Full-time</span></span>       | <span data-ttu-id="09e9f-550">Teljes munkaidős alkalmazott</span><span class="sxs-lookup"><span data-stu-id="09e9f-550">Full time employee</span></span> |
| <span data-ttu-id="09e9f-551">Részmunkaidős</span><span class="sxs-lookup"><span data-stu-id="09e9f-551">Part-time</span></span>       | <span data-ttu-id="09e9f-552">Részmunkaidős alkalmazott</span><span class="sxs-lookup"><span data-stu-id="09e9f-552">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="09e9f-553">Okkódok</span><span class="sxs-lookup"><span data-stu-id="09e9f-553">Reason codes</span></span>

<span data-ttu-id="09e9f-554">Az alkalmazottak állapotával kapcsolatos okkódok tájékoztatnak.</span><span class="sxs-lookup"><span data-stu-id="09e9f-554">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="09e9f-555">Okkódok a Dayforce-hoz állapot okaként vannak hozzárendelve, melyek jelzik egy alkalmazott beosztásában vagy alkalmazotti státuszában bekövetkezett változások okát.</span><span class="sxs-lookup"><span data-stu-id="09e9f-555">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="09e9f-556">A következő okkódok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="09e9f-556">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="09e9f-557">Okkód</span><span class="sxs-lookup"><span data-stu-id="09e9f-557">Reason code</span></span>            | <span data-ttu-id="09e9f-558">Leírás</span><span class="sxs-lookup"><span data-stu-id="09e9f-558">Description</span></span>                    | <span data-ttu-id="09e9f-559">Alkalmazandó forgatókönyvek</span><span class="sxs-lookup"><span data-stu-id="09e9f-559">Applicable scenarios</span></span> |
|------------------------|--------------------------------|----------------------|
| <span data-ttu-id="09e9f-560">DEPARTUREBEFOREPAYMENT</span><span class="sxs-lookup"><span data-stu-id="09e9f-560">DEPARTUREBEFOREPAYMENT</span></span> | <span data-ttu-id="09e9f-561">Indulás első bérlista előtt</span><span class="sxs-lookup"><span data-stu-id="09e9f-561">Departure before first payroll</span></span> | <span data-ttu-id="09e9f-562">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="09e9f-562">Terminate worker</span></span>     |
| <span data-ttu-id="09e9f-563">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="09e9f-563">RESIGNATION</span></span>            | <span data-ttu-id="09e9f-564">Felmondás</span><span class="sxs-lookup"><span data-stu-id="09e9f-564">Resignation</span></span>                    | <span data-ttu-id="09e9f-565">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="09e9f-565">Terminate worker</span></span>     |
| <span data-ttu-id="09e9f-566">PENSION</span><span class="sxs-lookup"><span data-stu-id="09e9f-566">PENSION</span></span>                | <span data-ttu-id="09e9f-567">Nyugdíj</span><span class="sxs-lookup"><span data-stu-id="09e9f-567">Pension</span></span>                        | <span data-ttu-id="09e9f-568">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="09e9f-568">Terminate worker</span></span>     |
| <span data-ttu-id="09e9f-569">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="09e9f-569">TERMINATION</span></span>            | <span data-ttu-id="09e9f-570">Befejezés</span><span class="sxs-lookup"><span data-stu-id="09e9f-570">Termination</span></span>                    | <span data-ttu-id="09e9f-571">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="09e9f-571">Terminate worker</span></span>     |
| <span data-ttu-id="09e9f-572">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="09e9f-572">RETIREMENT</span></span>             | <span data-ttu-id="09e9f-573">Megszüntetés</span><span class="sxs-lookup"><span data-stu-id="09e9f-573">Retirement</span></span>                     | <span data-ttu-id="09e9f-574">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="09e9f-574">Terminate worker</span></span>     |
| <span data-ttu-id="09e9f-575">ABSENTEE</span><span class="sxs-lookup"><span data-stu-id="09e9f-575">ABSENTEE</span></span>               | <span data-ttu-id="09e9f-576">Távollevő</span><span class="sxs-lookup"><span data-stu-id="09e9f-576">Absentee</span></span>                       | <span data-ttu-id="09e9f-577">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="09e9f-577">Terminate worker</span></span>     |
| <span data-ttu-id="09e9f-578">EGYÉB</span><span class="sxs-lookup"><span data-stu-id="09e9f-578">OTHER</span></span>                  | <span data-ttu-id="09e9f-579">Egyéb okok</span><span class="sxs-lookup"><span data-stu-id="09e9f-579">Other Reasons</span></span>                  | <span data-ttu-id="09e9f-580">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="09e9f-580">Terminate worker</span></span>     |
| <span data-ttu-id="09e9f-581">CLOSURE</span><span class="sxs-lookup"><span data-stu-id="09e9f-581">CLOSURE</span></span>                | <span data-ttu-id="09e9f-582">Üzletzárás</span><span class="sxs-lookup"><span data-stu-id="09e9f-582">Business Closure</span></span>               | <span data-ttu-id="09e9f-583">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="09e9f-583">Terminate worker</span></span>     |
| <span data-ttu-id="09e9f-584">DEATH</span><span class="sxs-lookup"><span data-stu-id="09e9f-584">DEATH</span></span>                  | <span data-ttu-id="09e9f-585">Elhalálozás</span><span class="sxs-lookup"><span data-stu-id="09e9f-585">Death</span></span>                          | <span data-ttu-id="09e9f-586">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="09e9f-586">Terminate worker</span></span>     |
| <span data-ttu-id="09e9f-587">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="09e9f-587">LEAVEOFABSENCE</span></span>         | <span data-ttu-id="09e9f-588">Szabadság</span><span class="sxs-lookup"><span data-stu-id="09e9f-588">Leave of Absence</span></span>               | <span data-ttu-id="09e9f-589">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="09e9f-589">Terminate worker</span></span>     |
| <span data-ttu-id="09e9f-590">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="09e9f-590">CONTRACTEND</span></span>            | <span data-ttu-id="09e9f-591">Szerződés vége</span><span class="sxs-lookup"><span data-stu-id="09e9f-591">End of Contract</span></span>                | <span data-ttu-id="09e9f-592">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="09e9f-592">Terminate worker</span></span>     |
| <span data-ttu-id="09e9f-593">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="09e9f-593">SALARYCHANGE</span></span>           | <span data-ttu-id="09e9f-594">Munkabér módosítása</span><span class="sxs-lookup"><span data-stu-id="09e9f-594">Change of Salary</span></span>               | <span data-ttu-id="09e9f-595">Kompenzáció</span><span class="sxs-lookup"><span data-stu-id="09e9f-595">Compensation</span></span>         |

### <a name="terms-of-employment"></a><span data-ttu-id="09e9f-596">Foglalkoztatási feltételek</span><span class="sxs-lookup"><span data-stu-id="09e9f-596">Terms of employment</span></span>

<span data-ttu-id="09e9f-597">A Foglalkoztatási feltételek foglalkoztatási feltételkategóriák létrehozására használatosak.</span><span class="sxs-lookup"><span data-stu-id="09e9f-597">Terms of employment are used to create categories of employment terms.</span></span> <span data-ttu-id="09e9f-598">A feltételek alkalmazási mutató értékekként vannak a Dayforce-hoz rendelve.</span><span class="sxs-lookup"><span data-stu-id="09e9f-598">The terms are mapped to Dayforce as employment indicator values.</span></span>

<span data-ttu-id="09e9f-599">A következő alkalmazási feltételek és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="09e9f-599">The following terms of employment and descriptions are required.</span></span>

| <span data-ttu-id="09e9f-600">Foglalkoztatási feltételek</span><span class="sxs-lookup"><span data-stu-id="09e9f-600">Terms of employment</span></span>   | <span data-ttu-id="09e9f-601">Leírás</span><span class="sxs-lookup"><span data-stu-id="09e9f-601">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="09e9f-602">Szabályos</span><span class="sxs-lookup"><span data-stu-id="09e9f-602">Regular</span></span>               | <span data-ttu-id="09e9f-603">Szabályos</span><span class="sxs-lookup"><span data-stu-id="09e9f-603">Regular</span></span>     |
| <span data-ttu-id="09e9f-604">Közvetlen</span><span class="sxs-lookup"><span data-stu-id="09e9f-604">Direct</span></span>                | <span data-ttu-id="09e9f-605">Közvetlen</span><span class="sxs-lookup"><span data-stu-id="09e9f-605">Direct</span></span>      |
| <span data-ttu-id="09e9f-606">Szakmai gyakorlat</span><span class="sxs-lookup"><span data-stu-id="09e9f-606">Internship</span></span>            | <span data-ttu-id="09e9f-607">Szakmai gyakorlat</span><span class="sxs-lookup"><span data-stu-id="09e9f-607">Internship</span></span>  |
| <span data-ttu-id="09e9f-608">Állandó</span><span class="sxs-lookup"><span data-stu-id="09e9f-608">Permanent</span></span>             | <span data-ttu-id="09e9f-609">Állandó</span><span class="sxs-lookup"><span data-stu-id="09e9f-609">Permanent</span></span>   |

### <a name="marital-status"></a><span data-ttu-id="09e9f-610">Családi állapot</span><span class="sxs-lookup"><span data-stu-id="09e9f-610">Marital status</span></span>

<span data-ttu-id="09e9f-611">Családi állapot értékei Dayforce-hoz vannak rendelve és konvertálva szükség esetén az elfogadható értékekre az integráció során.</span><span class="sxs-lookup"><span data-stu-id="09e9f-611">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="09e9f-612">Az alábbi táblázat bemutatja, hogy családi állapot értékek hogyan vannak leképezve a Dayforce -ban.</span><span class="sxs-lookup"><span data-stu-id="09e9f-612">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="09e9f-613">Talent</span><span class="sxs-lookup"><span data-stu-id="09e9f-613">Talent</span></span>                 | <span data-ttu-id="09e9f-614">Dayforce</span><span class="sxs-lookup"><span data-stu-id="09e9f-614">Dayforce</span></span>                  |
|------------------------|---------------------------|
| <span data-ttu-id="09e9f-615">Házas</span><span class="sxs-lookup"><span data-stu-id="09e9f-615">Married</span></span>                | <span data-ttu-id="09e9f-616">Házas</span><span class="sxs-lookup"><span data-stu-id="09e9f-616">Married</span></span>                   |
| <span data-ttu-id="09e9f-617">Egy</span><span class="sxs-lookup"><span data-stu-id="09e9f-617">Single</span></span>                 | <span data-ttu-id="09e9f-618">Egy</span><span class="sxs-lookup"><span data-stu-id="09e9f-618">Single</span></span>                    |
| <span data-ttu-id="09e9f-619">Özvegy</span><span class="sxs-lookup"><span data-stu-id="09e9f-619">Widowed</span></span>                | <span data-ttu-id="09e9f-620">Özvegy</span><span class="sxs-lookup"><span data-stu-id="09e9f-620">Widowed</span></span>                   |
| <span data-ttu-id="09e9f-621">Elvált</span><span class="sxs-lookup"><span data-stu-id="09e9f-621">Divorced</span></span>               | <span data-ttu-id="09e9f-622">Elvált</span><span class="sxs-lookup"><span data-stu-id="09e9f-622">Divorced</span></span>                  |
| <span data-ttu-id="09e9f-623">Bejegyzett élettársi kapcsolat</span><span class="sxs-lookup"><span data-stu-id="09e9f-623">Registered Partnership</span></span> | <span data-ttu-id="09e9f-624">Élettársi viszony</span><span class="sxs-lookup"><span data-stu-id="09e9f-624">Domestic Partnership</span></span>      |
| <span data-ttu-id="09e9f-625">Nincs</span><span class="sxs-lookup"><span data-stu-id="09e9f-625">None</span></span>                   | <span data-ttu-id="09e9f-626">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="09e9f-626">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="09e9f-627">Együttélés</span><span class="sxs-lookup"><span data-stu-id="09e9f-627">Cohabiting</span></span>             | <span data-ttu-id="09e9f-628">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="09e9f-628">*Not supported by Mexico*</span></span> |

### <a name="gender"></a><span data-ttu-id="09e9f-629">Nem</span><span class="sxs-lookup"><span data-stu-id="09e9f-629">Gender</span></span>

<span data-ttu-id="09e9f-630">A nemek a Dayforce-hoz vannak rendelve és konvertálva szükség esetén az elfogadható értékekre az integráció során.</span><span class="sxs-lookup"><span data-stu-id="09e9f-630">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="09e9f-631">Az alábbi táblázat bemutatja, hogy a nemek hogyan vannak leképezve a Dayforce-ban.</span><span class="sxs-lookup"><span data-stu-id="09e9f-631">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="09e9f-632">Talent</span><span class="sxs-lookup"><span data-stu-id="09e9f-632">Talent</span></span>       | <span data-ttu-id="09e9f-633">Dayforce</span><span class="sxs-lookup"><span data-stu-id="09e9f-633">Dayforce</span></span>                  |
|--------------|---------------------------|
| <span data-ttu-id="09e9f-634">Férfi</span><span class="sxs-lookup"><span data-stu-id="09e9f-634">Male</span></span>         | <span data-ttu-id="09e9f-635">Férfi</span><span class="sxs-lookup"><span data-stu-id="09e9f-635">Male</span></span>                      |
| <span data-ttu-id="09e9f-636">Nő</span><span class="sxs-lookup"><span data-stu-id="09e9f-636">Female</span></span>       | <span data-ttu-id="09e9f-637">Nő</span><span class="sxs-lookup"><span data-stu-id="09e9f-637">Female</span></span>                    |
| <span data-ttu-id="09e9f-638">Nem meghatározott</span><span class="sxs-lookup"><span data-stu-id="09e9f-638">Non-specific</span></span> | <span data-ttu-id="09e9f-639">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="09e9f-639">*Not supported by Mexico*</span></span> |

### <a name="payment-method"></a><span data-ttu-id="09e9f-640">Kifizetési mód</span><span class="sxs-lookup"><span data-stu-id="09e9f-640">Payment method</span></span>

<span data-ttu-id="09e9f-641">A Fizetési módok adják meg az alkalmazott és a vállalat számára az alkalmazott kifizetésének módja leírásának lehetőségét.</span><span class="sxs-lookup"><span data-stu-id="09e9f-641">Payment methods give the employee and the company a way to describe how employees will be paid.</span></span> <span data-ttu-id="09e9f-642">A Fizetési módok a Dayforce-hoz vannak rendelve és konvertálva szükség esetén az elfogadható értékekre az integráció során.</span><span class="sxs-lookup"><span data-stu-id="09e9f-642">Payment methods are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="09e9f-643">Az alábbi táblázat bemutatja, hogy a fizetés módok hogyan vannak leképezve a Dayforce-ban.</span><span class="sxs-lookup"><span data-stu-id="09e9f-643">The following table shows how payment methods are mapped to Dayforce.</span></span>

| <span data-ttu-id="09e9f-644">Talent</span><span class="sxs-lookup"><span data-stu-id="09e9f-644">Talent</span></span>             | <span data-ttu-id="09e9f-645">Dayforce</span><span class="sxs-lookup"><span data-stu-id="09e9f-645">Dayforce</span></span>                  |
|--------------------|---------------------------|
| <span data-ttu-id="09e9f-646">Készpénz</span><span class="sxs-lookup"><span data-stu-id="09e9f-646">Cash</span></span>               | <span data-ttu-id="09e9f-647">Készpénz</span><span class="sxs-lookup"><span data-stu-id="09e9f-647">Cash</span></span>                      |
| <span data-ttu-id="09e9f-648">Elektronikus fizetés</span><span class="sxs-lookup"><span data-stu-id="09e9f-648">Electronic Payment</span></span> | <span data-ttu-id="09e9f-649">Átvitel</span><span class="sxs-lookup"><span data-stu-id="09e9f-649">Transfer</span></span>                  |
| <span data-ttu-id="09e9f-650">Csekkes</span><span class="sxs-lookup"><span data-stu-id="09e9f-650">Check</span></span>              | <span data-ttu-id="09e9f-651">Csekk</span><span class="sxs-lookup"><span data-stu-id="09e9f-651">Cheque</span></span>                    |
| <span data-ttu-id="09e9f-652">Váltó</span><span class="sxs-lookup"><span data-stu-id="09e9f-652">Bank Draft</span></span>         | <span data-ttu-id="09e9f-653">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="09e9f-653">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="09e9f-654">Egyéb</span><span class="sxs-lookup"><span data-stu-id="09e9f-654">Other</span></span>              | <span data-ttu-id="09e9f-655">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="09e9f-655">*Not supported by Mexico*</span></span> |

### <a name="bank-account-type"></a><span data-ttu-id="09e9f-656">Bankszámla típusa</span><span class="sxs-lookup"><span data-stu-id="09e9f-656">Bank account type</span></span>

<span data-ttu-id="09e9f-657">Bankszámla-típusok az alkalmazottaknak történő elektronikus kifizetésekhez szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="09e9f-657">Bank account types are used for electronic payments to employees.</span></span> <span data-ttu-id="09e9f-658">Bankszámla típusa a Dayforce-ba átutalási számlaadatként van rendelve.</span><span class="sxs-lookup"><span data-stu-id="09e9f-658">Bank account types are mapped to Dayforce as transfer account information.</span></span> <span data-ttu-id="09e9f-659">A bankszámlatípusok szükség esetén konvertálva vannak az elfogadható értékekké az integráció során.</span><span class="sxs-lookup"><span data-stu-id="09e9f-659">The bank account types are translated, as appropriate, to the accepted values upon integration.</span></span>

| <span data-ttu-id="09e9f-660">Talent</span><span class="sxs-lookup"><span data-stu-id="09e9f-660">Talent</span></span>            | <span data-ttu-id="09e9f-661">Dayforce</span><span class="sxs-lookup"><span data-stu-id="09e9f-661">Dayforce</span></span>                  |
|-------------------|---------------------------|
| <span data-ttu-id="09e9f-662">Folyószámla</span><span class="sxs-lookup"><span data-stu-id="09e9f-662">Checking Account</span></span>  | <span data-ttu-id="09e9f-663">CheckingAccount</span><span class="sxs-lookup"><span data-stu-id="09e9f-663">CheckingAccount</span></span>           |
| <span data-ttu-id="09e9f-664">Bérlista elszámolási számlája</span><span class="sxs-lookup"><span data-stu-id="09e9f-664">Payroll Account</span></span>   | <span data-ttu-id="09e9f-665">PayrollAccount</span><span class="sxs-lookup"><span data-stu-id="09e9f-665">PayrollAccount</span></span>            |
| <span data-ttu-id="09e9f-666">Megtakarítási számla</span><span class="sxs-lookup"><span data-stu-id="09e9f-666">Savings Account</span></span>   | <span data-ttu-id="09e9f-667">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="09e9f-667">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="09e9f-668">BankGirot-számla</span><span class="sxs-lookup"><span data-stu-id="09e9f-668">BankGirot account</span></span> | <span data-ttu-id="09e9f-669">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="09e9f-669">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="09e9f-670">PlusGirot-számla</span><span class="sxs-lookup"><span data-stu-id="09e9f-670">PlusGirot account</span></span> | <span data-ttu-id="09e9f-671">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="09e9f-671">*Not supported by Mexico*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="09e9f-672">Bevételkódok</span><span class="sxs-lookup"><span data-stu-id="09e9f-672">Earning codes</span></span>

<span data-ttu-id="09e9f-673">A bevételkódok egyedi módon azonosítják a dolgozók által kapott fizetéstípusokat.</span><span class="sxs-lookup"><span data-stu-id="09e9f-673">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="09e9f-674">A kódoknak különböző paramétereket fednek le, amelyek a bevételekhez kapcsolódnak, például könyvelési szabályok, jelentési követelmények és bruttósítási lehetőségek.</span><span class="sxs-lookup"><span data-stu-id="09e9f-674">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="09e9f-675">Ha egy nem támogatott gyakoriság van használatban, a **Minden fizetés** gyakorisága van alapértelmezés szerint használva a kiszámításhoz.</span><span class="sxs-lookup"><span data-stu-id="09e9f-675">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="09e9f-676">Támogatott gyakoriságok</span><span class="sxs-lookup"><span data-stu-id="09e9f-676">Supported frequencies</span></span>

- <span data-ttu-id="09e9f-677">Összes</span><span class="sxs-lookup"><span data-stu-id="09e9f-677">All</span></span>
- <span data-ttu-id="09e9f-678">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="09e9f-678">EVERYPAY</span></span>
- <span data-ttu-id="09e9f-679">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="09e9f-679">EACHPAYPERIOD</span></span>
- <span data-ttu-id="09e9f-680">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="09e9f-680">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="09e9f-681">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="09e9f-681">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="09e9f-682">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="09e9f-682">1OFMTH</span></span>
- <span data-ttu-id="09e9f-683">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="09e9f-683">LASTOFMTH</span></span>
- <span data-ttu-id="09e9f-684">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="09e9f-684">2OFMTH</span></span>
- <span data-ttu-id="09e9f-685">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="09e9f-685">3OFMTH</span></span>
- <span data-ttu-id="09e9f-686">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="09e9f-686">4OFMTH</span></span>
- <span data-ttu-id="09e9f-687">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="09e9f-687">5OFMTH</span></span>
- <span data-ttu-id="09e9f-688">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="09e9f-688">1N2OFMTH</span></span>
- <span data-ttu-id="09e9f-689">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="09e9f-689">3N4OFMTH</span></span>
- <span data-ttu-id="09e9f-690">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="09e9f-690">1N3OFMTH</span></span>
- <span data-ttu-id="09e9f-691">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="09e9f-691">1N4OFMTH</span></span>
- <span data-ttu-id="09e9f-692">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="09e9f-692">2N3OFMTH</span></span>
- <span data-ttu-id="09e9f-693">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="09e9f-693">2N4OFMTH</span></span>
- <span data-ttu-id="09e9f-694">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="09e9f-694">1N2N3OFMTH</span></span>
- <span data-ttu-id="09e9f-695">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="09e9f-695">1N2N4OFMTH</span></span>
- <span data-ttu-id="09e9f-696">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="09e9f-696">1N3N4OFMTH</span></span>
- <span data-ttu-id="09e9f-697">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="09e9f-697">2N3N4OFMTH</span></span>
- <span data-ttu-id="09e9f-698">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="09e9f-698">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="09e9f-699">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="09e9f-699">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="09e9f-700">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="09e9f-700">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="09e9f-701">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="09e9f-701">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="09e9f-702">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="09e9f-702">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="09e9f-703">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="09e9f-703">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="09e9f-704">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="09e9f-704">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="09e9f-705">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="09e9f-705">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="09e9f-706">Címek</span><span class="sxs-lookup"><span data-stu-id="09e9f-706">Addresses</span></span>

<span data-ttu-id="09e9f-707">Az adott ország vagy régió, állam és megye (település) kódok specifikus formátumokat követelnek, hogy Dayforce és az országos és regionális szolgáltatók felismerjék azokat.</span><span class="sxs-lookup"><span data-stu-id="09e9f-707">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="09e9f-708">Annak ellenére, hogy a városok formátuma rugalmas, minden városnak társítva kell lennie egy államhoz.</span><span class="sxs-lookup"><span data-stu-id="09e9f-708">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="09e9f-709">Talent</span><span class="sxs-lookup"><span data-stu-id="09e9f-709">Talent</span></span>              | <span data-ttu-id="09e9f-710">Dayforce</span><span class="sxs-lookup"><span data-stu-id="09e9f-710">Dayforce</span></span>              |
|---------------------|-----------------------|
| <span data-ttu-id="09e9f-711">Ország/régió</span><span class="sxs-lookup"><span data-stu-id="09e9f-711">Country/Region</span></span>      | <span data-ttu-id="09e9f-712">Országkód</span><span class="sxs-lookup"><span data-stu-id="09e9f-712">Country Code</span></span>          |
| <span data-ttu-id="09e9f-713">Irányítószám / postai kód</span><span class="sxs-lookup"><span data-stu-id="09e9f-713">Zip/Postal Code</span></span>     | <span data-ttu-id="09e9f-714">Irányítószám</span><span class="sxs-lookup"><span data-stu-id="09e9f-714">Postal Code</span></span>           |
| <span data-ttu-id="09e9f-715">Állami</span><span class="sxs-lookup"><span data-stu-id="09e9f-715">State</span></span>               | <span data-ttu-id="09e9f-716">Államkód</span><span class="sxs-lookup"><span data-stu-id="09e9f-716">State Code</span></span>            |
| <span data-ttu-id="09e9f-717">Város</span><span class="sxs-lookup"><span data-stu-id="09e9f-717">City</span></span>                | <span data-ttu-id="09e9f-718">Város</span><span class="sxs-lookup"><span data-stu-id="09e9f-718">City</span></span>                  |
| <span data-ttu-id="09e9f-719">Megye</span><span class="sxs-lookup"><span data-stu-id="09e9f-719">County</span></span>              | <span data-ttu-id="09e9f-720">Megye (Helyhatóság)</span><span class="sxs-lookup"><span data-stu-id="09e9f-720">County (Municipality)</span></span> |
| <span data-ttu-id="09e9f-721">Utca</span><span class="sxs-lookup"><span data-stu-id="09e9f-721">Street</span></span>              | <span data-ttu-id="09e9f-722">Cím 1. sora</span><span class="sxs-lookup"><span data-stu-id="09e9f-722">Address Line 1</span></span>        |
| <span data-ttu-id="09e9f-723">Utca, házszám</span><span class="sxs-lookup"><span data-stu-id="09e9f-723">Street Number</span></span>       | <span data-ttu-id="09e9f-724">Cím 2. sora</span><span class="sxs-lookup"><span data-stu-id="09e9f-724">Address Line 2</span></span>        |
| <span data-ttu-id="09e9f-725">Épületblokk</span><span class="sxs-lookup"><span data-stu-id="09e9f-725">Building Complement</span></span> | <span data-ttu-id="09e9f-726">Cím 5. sora</span><span class="sxs-lookup"><span data-stu-id="09e9f-726">Address Line 5</span></span>        |

### <a name="passport-number"></a><span data-ttu-id="09e9f-727">Útlevél száma</span><span class="sxs-lookup"><span data-stu-id="09e9f-727">Passport number</span></span>

<span data-ttu-id="09e9f-728">Az alkalmazottak útlevél adatokat is nyilatkozhatnak.</span><span class="sxs-lookup"><span data-stu-id="09e9f-728">Employees can declare passport information.</span></span> <span data-ttu-id="09e9f-729">Az információ a **Útlevél** azonosítótípusra vonatkozik, és az alkalmazott Mexikó-specifikus adataiként van a Dayforce-ba integrálva.</span><span class="sxs-lookup"><span data-stu-id="09e9f-729">This information is of the **Passport** identification type and is integrated into Dayforce as part of an employee's Mexico-specific information.</span></span>

- <span data-ttu-id="09e9f-730">Azonosító típusa = „Útlevél”</span><span class="sxs-lookup"><span data-stu-id="09e9f-730">Identification Type = "Passport"</span></span>
- <span data-ttu-id="09e9f-731">Kibocsátás dátuma</span><span class="sxs-lookup"><span data-stu-id="09e9f-731">Issued Date</span></span>
- <span data-ttu-id="09e9f-732">Lejárat dátuma</span><span class="sxs-lookup"><span data-stu-id="09e9f-732">Expiration Date</span></span>

<span data-ttu-id="09e9f-733">Az alkalmazottak több azonosítószámot is megadhatnak az **Útlevél** azonosítótípushoz.</span><span class="sxs-lookup"><span data-stu-id="09e9f-733">Employees can declare multiple identification numbers of the **Passport** identification type.</span></span> <span data-ttu-id="09e9f-734">Azonban csak az aktuális aktív útlevélbejegyzés van integrálva a Dayforce-ba.</span><span class="sxs-lookup"><span data-stu-id="09e9f-734">However, only the current active passport entry is integrated into Dayforce.</span></span> <span data-ttu-id="09e9f-735">Ha az összes útlevélbejegyzés lejárt, a legutóbb kiállított lesz integrálva a Dayforce-ba.</span><span class="sxs-lookup"><span data-stu-id="09e9f-735">If all passport entries are expired, the passport that was most recently issued is integrated into Dayforce.</span></span>
