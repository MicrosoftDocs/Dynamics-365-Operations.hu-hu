---
title: Bérlista-integráció konfigurálása a Talnet és a Dayforce közötti
description: Ez a témakör bemutatja, hogyan kell konfigurálni az integrációt a Microsoft Dynamics 365 for Talent és a Ceridian Dayforce között úgy, hogy fel lehessen dolgozni fizetési időszakot.
author: jcart1106
manager: AnnBe
ms.date: 07/10/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: fcddf82cffb9f0ba94b83eb21809b810585ebc9e
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "304657"
---
# <a name="configure-the-payroll-integration-between-talent-and-dayforce"></a><span data-ttu-id="1fe13-103">Bérlista-integráció konfigurálása a Talent és a Dayforce között</span><span class="sxs-lookup"><span data-stu-id="1fe13-103">Configure the payroll integration between Talent and Dayforce</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="1fe13-104">A Microsoft Dynamics 365 for Talent és Ceridian Dayforce integrálásához több konfigurációs lépést szükséges elvégezni, melyek ebben a témakörben vannak ismertetve.</span><span class="sxs-lookup"><span data-stu-id="1fe13-104">The integration between Microsoft Dynamics 365 for Talent and Ceridian Dayforce relies on several configuration steps that are described in this topic.</span></span> <span data-ttu-id="1fe13-105">Be kell állítania az integrációt a Talent a Dayforce alkalmazásokban is a fizetési időszak feldolgozása előtt.</span><span class="sxs-lookup"><span data-stu-id="1fe13-105">You must configure the integration in both Talent and Dayforce before you can process a pay run.</span></span>

<span data-ttu-id="1fe13-106">Ha olyan szolgáltatást használ a fizetési időszakokhoz, mint a Dayforce, engedélyeznie kell az integrációt a Talentben.</span><span class="sxs-lookup"><span data-stu-id="1fe13-106">When you use a service such as Dayforce to complete pay runs, you must enable the integration in Talent.</span></span> <span data-ttu-id="1fe13-107">Az integrációhoz meghatározott adatok szükségesek a Talentből.</span><span class="sxs-lookup"><span data-stu-id="1fe13-107">The integration requires specific data from Talent.</span></span> <span data-ttu-id="1fe13-108">Ezért ellenőriznie kell, hogy a Dayforce-ban hozzárendelt adatok olyan módon vannak konfigurálva a Talentben, hogy az támogassa az integrációt.</span><span class="sxs-lookup"><span data-stu-id="1fe13-108">Therefore, you must verify that data that is mapped to Dayforce is configured in Talent in a manner that supports the integration.</span></span> <span data-ttu-id="1fe13-109">Az integráció a következő szélesebb adatkategóriákat használja:</span><span class="sxs-lookup"><span data-stu-id="1fe13-109">The integration uses the following broad categories of data:</span></span>

- <span data-ttu-id="1fe13-110">Emberierőforrás-adatok</span><span class="sxs-lookup"><span data-stu-id="1fe13-110">Human resources data</span></span>
- <span data-ttu-id="1fe13-111">Kompenzációadatok</span><span class="sxs-lookup"><span data-stu-id="1fe13-111">Compensation data</span></span>
- <span data-ttu-id="1fe13-112">Bérlistaadatok, mint kifizetési ciklus, fizetési időszakok és bevételkódok</span><span class="sxs-lookup"><span data-stu-id="1fe13-112">Payroll data, such as pay cycles, pay periods, and earning codes</span></span>
- <span data-ttu-id="1fe13-113">Dolgozóadatok</span><span class="sxs-lookup"><span data-stu-id="1fe13-113">Worker data</span></span>

<span data-ttu-id="1fe13-114">Ez a témakör leírja a lépéseket, amelyeket követni kell az integráció engedélyezéséhez.</span><span class="sxs-lookup"><span data-stu-id="1fe13-114">This topic describes the steps that you must follow to enable the integration.</span></span> <span data-ttu-id="1fe13-115">Azt is bemutatja, hogy milyen típusú adatok és konfiguráció szükséges az integrációhoz.</span><span class="sxs-lookup"><span data-stu-id="1fe13-115">It also explains the types of data and the configuration details that the integration requires.</span></span>

## <a name="enable-the-integration"></a><span data-ttu-id="1fe13-116">Engedélyezze az integrációt</span><span class="sxs-lookup"><span data-stu-id="1fe13-116">Enable the integration</span></span>

<span data-ttu-id="1fe13-117">A Talentben be kell kapcsolja a műveletek integrációját, meg kell adnia a konfiguráció adatait, hogy tudjon a Dayforcehoz csatlakozni.</span><span class="sxs-lookup"><span data-stu-id="1fe13-117">In Talent, you must turn on the integration and enter the configuration information to connect to Dayforce.</span></span> <span data-ttu-id="1fe13-118">Ha azt szeretné, hogy a létrehozott általános főkönyvi tranzakció importálva legyen a Microsoft Dynamics 365 for Finance and Operations alkalmazásba, be kell állítania egy Microsoft Azure tárolási fiókot, majd adja meg, majd Azure tárolási kapcsolat karakterláncát a Finance and Operations alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="1fe13-118">If you want the general ledger transaction that is produced to be imported into Microsoft Dynamics 365 for Finance and Operations, you must also set up a Microsoft Azure storage account and enter the Azure Storage connection string in Finance and Operations.</span></span>

<span data-ttu-id="1fe13-119">Az integráció engedélyezéséhez a Talentben kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="1fe13-119">To turn on the integration in Talent, follow these steps.</span></span>

1. <span data-ttu-id="1fe13-120">A **Rendszerfelügyelet** oldalon válassza az **Integrációkonfiguráció** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1fe13-120">On the **System administration** page, select **Integration configuration**.</span></span>
2. <span data-ttu-id="1fe13-121">Adja meg a biztonságos fájl átviteli protokollt (FTP) végpontot és a biztonságos FTP-mappa elérési útja.</span><span class="sxs-lookup"><span data-stu-id="1fe13-121">Enter the secure File Transfer Protocol (FTP) endpoint and the secure FTP folder path.</span></span>
3. <span data-ttu-id="1fe13-122">Adja meg azon felhasználó felhasználónevét és jelszavát, aki hozzáfér a biztonságos FTP végponthoz és a mappa elérési útjához.</span><span class="sxs-lookup"><span data-stu-id="1fe13-122">Enter the user name and password of the user who will access the secure FTP endpoint and folder path.</span></span>
4. <span data-ttu-id="1fe13-123">Tesztelje a kapcsolatot szükség szerint, és állítsa a **Bérlista-integráció engedélyezése** lehetőséggel **Igenre**.</span><span class="sxs-lookup"><span data-stu-id="1fe13-123">Test the connection, as required, and set the **Enable payroll integration** option to **Yes**.</span></span>

<span data-ttu-id="1fe13-124">Ha az integráció engedélyezve van, adatexport adatcsomagok és fájlok jönnek létre, valamint a gyakoriság is be van állítva.</span><span class="sxs-lookup"><span data-stu-id="1fe13-124">When the integration is turned on, the data export package and files are created, and the frequency is set.</span></span> <span data-ttu-id="1fe13-125">Igény szerint módosíthatja a gyakoriságot.</span><span class="sxs-lookup"><span data-stu-id="1fe13-125">You can change this frequency as you require.</span></span>

<span data-ttu-id="1fe13-126">Azure tárolási fiókokkal és Azure tárolási kapcsolati karakterláncokat kapcsolatos további információt az alábbi Azure-témakörökben találja:</span><span class="sxs-lookup"><span data-stu-id="1fe13-126">For more information about Azure storage accounts and Azure Storage connection strings, see the following Azure topics:</span></span>

- [<span data-ttu-id="1fe13-127">Az Azure Storage-fiókokról</span><span class="sxs-lookup"><span data-stu-id="1fe13-127">About Azure storage accounts</span></span>](https://docs.microsoft.com/en-us/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [<span data-ttu-id="1fe13-128">Azure Storage kapcsolati karakterláncok konfigurálása</span><span class="sxs-lookup"><span data-stu-id="1fe13-128">Configure Azure Storage connection strings</span></span>](https://docs.microsoft.com/en-us/azure/storage/common/storage-configure-connection-string)

## <a name="configure-your-data"></a><span data-ttu-id="1fe13-129">Adatai konfigurálása</span><span class="sxs-lookup"><span data-stu-id="1fe13-129">Configure your data</span></span> 

<span data-ttu-id="1fe13-130">A bérlista feldolgozásához konfigurálnia kell az emberi erőforrás adatokat a Talentben.</span><span class="sxs-lookup"><span data-stu-id="1fe13-130">To process payroll, you must configure human resource data in Talent.</span></span> <span data-ttu-id="1fe13-131">Be kell állítani a szervezeti adatokat, például a feladatokat és beosztásokat, valamint juttatásokra és a kompenzációra vonatkozó adatokat.</span><span class="sxs-lookup"><span data-stu-id="1fe13-131">You must set up organizational data, such as jobs and positions, together with benefits and compensation information.</span></span> <span data-ttu-id="1fe13-132">Ez az információ megadja a foglalkoztatásra, fizetésre és levonásokra vonatkozó információkat, melyek szükségesek az alkalmazott fizetések generálásához.</span><span class="sxs-lookup"><span data-stu-id="1fe13-132">This information provides the employment, pay, and deduction information that is required in order to generate employee pay.</span></span>

### <a name="human-resource-data"></a><span data-ttu-id="1fe13-133">Emberierőforrás-adatok</span><span class="sxs-lookup"><span data-stu-id="1fe13-133">Human resource data</span></span>

#### <a name="benefits"></a><span data-ttu-id="1fe13-134">Juttatások</span><span class="sxs-lookup"><span data-stu-id="1fe13-134">Benefits</span></span> 

<span data-ttu-id="1fe13-135">Az emberi erőforrások számos beállítási és karbantartási eszközt biztosít, amelyek segítségével beállíthatja és karbantarthatja a szervezet által a dolgozónak biztosított juttatásokat, levonásokat és dolgozói kompenzációs terveket.</span><span class="sxs-lookup"><span data-stu-id="1fe13-135">Human resources provides tools for the setup and maintenance of the benefits, deductions, and worker compensation plans that an organization offers or processes for its workers.</span></span>

<span data-ttu-id="1fe13-136">Juttatások létrehozása esetén ne felejtse el a következő adatokat és beállításokat, amelyeket a Dayforce használ.</span><span class="sxs-lookup"><span data-stu-id="1fe13-136">When you create benefits, keep in mind the following data and configurations that are used in Dayforce.</span></span>

##### <a name="benefit-plans"></a><span data-ttu-id="1fe13-137">Juttatási tervek</span><span class="sxs-lookup"><span data-stu-id="1fe13-137">Benefit plans</span></span>

- <span data-ttu-id="1fe13-138">Terv (szükséges)</span><span class="sxs-lookup"><span data-stu-id="1fe13-138">Plan (required)</span></span>
- <span data-ttu-id="1fe13-139">Típus (szükséges)</span><span class="sxs-lookup"><span data-stu-id="1fe13-139">Type (required)</span></span>
- <span data-ttu-id="1fe13-140">Bérlista hatása (szükséges)</span><span class="sxs-lookup"><span data-stu-id="1fe13-140">Payroll impact (required)</span></span>
- <span data-ttu-id="1fe13-141">Hátralékok helyreállítása</span><span class="sxs-lookup"><span data-stu-id="1fe13-141">Recover arrears</span></span>
- <span data-ttu-id="1fe13-142">Levonási módszer</span><span class="sxs-lookup"><span data-stu-id="1fe13-142">Deduction method</span></span>
- <span data-ttu-id="1fe13-143">Levonás prioritása</span><span class="sxs-lookup"><span data-stu-id="1fe13-143">Deduction priority</span></span>
- <span data-ttu-id="1fe13-144">Időszak korlátozása</span><span class="sxs-lookup"><span data-stu-id="1fe13-144">Limit period</span></span>
- <span data-ttu-id="1fe13-145">Összeghatár</span><span class="sxs-lookup"><span data-stu-id="1fe13-145">Limit amount</span></span>

##### <a name="benefits"></a><span data-ttu-id="1fe13-146">Juttatások</span><span class="sxs-lookup"><span data-stu-id="1fe13-146">Benefits</span></span>

- <span data-ttu-id="1fe13-147">Terv (szükséges)</span><span class="sxs-lookup"><span data-stu-id="1fe13-147">Plan (required)</span></span>
- <span data-ttu-id="1fe13-148">Típus (szükséges)</span><span class="sxs-lookup"><span data-stu-id="1fe13-148">Type (required)</span></span>
- <span data-ttu-id="1fe13-149">Lehetőség (szükséges)</span><span class="sxs-lookup"><span data-stu-id="1fe13-149">Option (required)</span></span>
- <span data-ttu-id="1fe13-150">Juttatás azonosítója (szükséges)</span><span class="sxs-lookup"><span data-stu-id="1fe13-150">Benefit ID (required)</span></span>
- <span data-ttu-id="1fe13-151">Gyakoriság</span><span class="sxs-lookup"><span data-stu-id="1fe13-151">Frequency</span></span>
- <span data-ttu-id="1fe13-152">Alap</span><span class="sxs-lookup"><span data-stu-id="1fe13-152">Basis</span></span>
- <span data-ttu-id="1fe13-153">Összeg vagy mérték</span><span class="sxs-lookup"><span data-stu-id="1fe13-153">Amount or rate</span></span>
- <span data-ttu-id="1fe13-154">Bevételkód</span><span class="sxs-lookup"><span data-stu-id="1fe13-154">Earning code</span></span>

##### <a name="supported-frequencies"></a><span data-ttu-id="1fe13-155">Támogatott gyakoriságok</span><span class="sxs-lookup"><span data-stu-id="1fe13-155">Supported frequencies</span></span> 

- <span data-ttu-id="1fe13-156">Heti</span><span class="sxs-lookup"><span data-stu-id="1fe13-156">Weekly</span></span>
- <span data-ttu-id="1fe13-157">Kétheti</span><span class="sxs-lookup"><span data-stu-id="1fe13-157">Bi-weekly</span></span>
- <span data-ttu-id="1fe13-158">Félhavi</span><span class="sxs-lookup"><span data-stu-id="1fe13-158">Semi-monthly</span></span>
- <span data-ttu-id="1fe13-159">Havi</span><span class="sxs-lookup"><span data-stu-id="1fe13-159">Monthly</span></span>

##### <a name="supported-bases"></a><span data-ttu-id="1fe13-160">Támogatott alapok</span><span class="sxs-lookup"><span data-stu-id="1fe13-160">Supported bases</span></span> 

- <span data-ttu-id="1fe13-161">Rögzített összeg</span><span class="sxs-lookup"><span data-stu-id="1fe13-161">Fixed amount</span></span>
- <span data-ttu-id="1fe13-162">Bevételek százaléka</span><span class="sxs-lookup"><span data-stu-id="1fe13-162">Percent of earnings</span></span>
- <span data-ttu-id="1fe13-163">Produktív órák</span><span class="sxs-lookup"><span data-stu-id="1fe13-163">Productive hours</span></span>

<span data-ttu-id="1fe13-164">A Dayforce létrehozza a következő levonásokat, a juttatási tervben definiált bérlistahatás alapján.</span><span class="sxs-lookup"><span data-stu-id="1fe13-164">Dayforce creates the following deductions, based on the payroll impact that is defined on the benefit plan.</span></span>

| <span data-ttu-id="1fe13-165">Kiválasztás a Talentben</span><span class="sxs-lookup"><span data-stu-id="1fe13-165">Selection in Talent</span></span>        | <span data-ttu-id="1fe13-166">Eredmény a Dayforce-ban</span><span class="sxs-lookup"><span data-stu-id="1fe13-166">Result in Dayforce</span></span>                            |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="1fe13-167">Nincs</span><span class="sxs-lookup"><span data-stu-id="1fe13-167">None</span></span>                       | <span data-ttu-id="1fe13-168">Nincs létrehozva levonás.</span><span class="sxs-lookup"><span data-stu-id="1fe13-168">No deduction is created.</span></span>                      |
| <span data-ttu-id="1fe13-169">Csak levonás</span><span class="sxs-lookup"><span data-stu-id="1fe13-169">Deduction only</span></span>             | <span data-ttu-id="1fe13-170">Alkalmazotti levonás jön létre.</span><span class="sxs-lookup"><span data-stu-id="1fe13-170">An employee deduction is created.</span></span>             |
| <span data-ttu-id="1fe13-171">Csak hozzájárulás</span><span class="sxs-lookup"><span data-stu-id="1fe13-171">Contribution only</span></span>          | <span data-ttu-id="1fe13-172">Egy alkalmazotti levonás jön létre.</span><span class="sxs-lookup"><span data-stu-id="1fe13-172">An employer deduction is created.</span></span>             |
| <span data-ttu-id="1fe13-173">Levonás és hozzájárulás</span><span class="sxs-lookup"><span data-stu-id="1fe13-173">Deduction and contribution</span></span> | <span data-ttu-id="1fe13-174">Alkalmazotti és a munkáltatói levonások jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="1fe13-174">Employee and employer deductions are created.</span></span> |

<span data-ttu-id="1fe13-175">A juttatási programok definiálásával és kezelésével kapcsolatosan további tájékoztatás a következő témakörökben talál:</span><span class="sxs-lookup"><span data-stu-id="1fe13-175">For more information about how to define and manage a benefits program, see the following topics:</span></span>

- [<span data-ttu-id="1fe13-176">Alkalmazotti juttatási program megvalósítása</span><span class="sxs-lookup"><span data-stu-id="1fe13-176">Deliver an employee benefits program</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [<span data-ttu-id="1fe13-177">Új juttatás létrehozása</span><span class="sxs-lookup"><span data-stu-id="1fe13-177">Create a new benefit</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [<span data-ttu-id="1fe13-178">Juttatásra való jogosultsági szabályok és irányelvek meghatározása</span><span class="sxs-lookup"><span data-stu-id="1fe13-178">Define benefit eligibility rules and policies</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [<span data-ttu-id="1fe13-179">Dolgozók juttatásainak felvétele és eltávolítása</span><span class="sxs-lookup"><span data-stu-id="1fe13-179">Enroll and remove benefits from workers</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a><span data-ttu-id="1fe13-180">Kompenzáció</span><span class="sxs-lookup"><span data-stu-id="1fe13-180">Compensation</span></span> 

<span data-ttu-id="1fe13-181">A kompenzációkezeléssel szabályozható az alapfizetés és a jutalmak kifizetése.</span><span class="sxs-lookup"><span data-stu-id="1fe13-181">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="1fe13-182">Egy alkalmazott fix fizetési díjalapja és érdemeken alapuló fizetése kezelhető a fix kompenzációs tervekkel.</span><span class="sxs-lookup"><span data-stu-id="1fe13-182">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="1fe13-183">Az ösztönző díjak kifizetése, például bónuszok, teljesítménydíjak, részvényopciók és kölcsönök, továbbá az egyszeri jutalmak a változó kompenzációs tervekben szabályozhatók.</span><span class="sxs-lookup"><span data-stu-id="1fe13-183">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span>

<span data-ttu-id="1fe13-184">A Dayforce a kompenzációs adatok segítségével kiszámítja az alkalmazott óradíját vagy éves díját.</span><span class="sxs-lookup"><span data-stu-id="1fe13-184">Dayforce uses compensation information to calculate an employee's hourly or annual rate.</span></span> <span data-ttu-id="1fe13-185">Fix kompenzációs tervek és a fizetési díjalap átalakítások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="1fe13-185">Fixed compensation plans and pay rate conversions are required.</span></span> <span data-ttu-id="1fe13-186">Az alkalmazottakat hozzá kell rendelni a fix kompenzációs tervhez.</span><span class="sxs-lookup"><span data-stu-id="1fe13-186">Employees must be associated with a fixed compensation plan.</span></span>

<span data-ttu-id="1fe13-187">A következő témakörökben bővebben olvashat a kompenzációs tervekről:</span><span class="sxs-lookup"><span data-stu-id="1fe13-187">For more information about compensation plans, see the following topics:</span></span>

- [<span data-ttu-id="1fe13-188">Fix kompenzációs konstrukciók létrehozása</span><span class="sxs-lookup"><span data-stu-id="1fe13-188">Create fixed compensation plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [<span data-ttu-id="1fe13-189">Változó kompenzációs konstrukciók létrehozása</span><span class="sxs-lookup"><span data-stu-id="1fe13-189">Create variable compensation plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [<span data-ttu-id="1fe13-190">Munkabér-/kompenzációs struktúra és tervek kialakítása</span><span class="sxs-lookup"><span data-stu-id="1fe13-190">Develop salary/compensation structure and plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [<span data-ttu-id="1fe13-191">Folyamatkompenzáció</span><span class="sxs-lookup"><span data-stu-id="1fe13-191">Process compensation</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/process-compensation)
- [<span data-ttu-id="1fe13-192">Kompenzációs folyamat meghatározása és eredmények kiszámítása</span><span class="sxs-lookup"><span data-stu-id="1fe13-192">Define compensation process and calculate results</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [<span data-ttu-id="1fe13-193">Alkalmazottak felvétele fix kompenzációs konstrukcióba</span><span class="sxs-lookup"><span data-stu-id="1fe13-193">Enroll an employee in a fixed compensation plan</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [<span data-ttu-id="1fe13-194">Alkalmazottak felvétele változó kompenzációs konstrukcióba</span><span class="sxs-lookup"><span data-stu-id="1fe13-194">Enroll an employee in a variable compensation plan</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a><span data-ttu-id="1fe13-195">Beosztások</span><span class="sxs-lookup"><span data-stu-id="1fe13-195">Jobs</span></span> 

<span data-ttu-id="1fe13-196">A munkakör azon feladatok és felelősségek gyűjteménye, amelyek egy adott munkát végrehajtó személytől elvártak.</span><span class="sxs-lookup"><span data-stu-id="1fe13-196">A job is a collection of the tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="1fe13-197">További információ a következő témakörökben olvasható:</span><span class="sxs-lookup"><span data-stu-id="1fe13-197">For more information, see the following topics:</span></span>

- [<span data-ttu-id="1fe13-198">Feladat összetevőinek beállítása</span><span class="sxs-lookup"><span data-stu-id="1fe13-198">Setting up the components of a job</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-job)
- [<span data-ttu-id="1fe13-199">Új feladatok meghatározása</span><span class="sxs-lookup"><span data-stu-id="1fe13-199">Define new jobs</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a><span data-ttu-id="1fe13-200">Beosztások</span><span class="sxs-lookup"><span data-stu-id="1fe13-200">Positions</span></span>

<span data-ttu-id="1fe13-201">Egy beosztás egy feladat egyedi példánya.</span><span class="sxs-lookup"><span data-stu-id="1fe13-201">A position is an individual instance of a job.</span></span> <span data-ttu-id="1fe13-202">Például az „Értékesítési igazgató (Kelet)” pozíció egyike azon beosztásoknak, amelyek társíthatók az „Értékesítési igazgató” feladathoz.</span><span class="sxs-lookup"><span data-stu-id="1fe13-202">For example, the "Sales manager (East)" position is one of the positions that are associated with the "Sales manager" job.</span></span> <span data-ttu-id="1fe13-203">A beosztás létezik a részlegben.</span><span class="sxs-lookup"><span data-stu-id="1fe13-203">A position exists in a department.</span></span> <span data-ttu-id="1fe13-204">Egy beosztáshoz csak egy dolgozó rendelhető.</span><span class="sxs-lookup"><span data-stu-id="1fe13-204">Only one worker can be associated with each position.</span></span>

<span data-ttu-id="1fe13-205">A következő adatokat és konfigurációkat szem előtt tartani beosztások beállításakor:</span><span class="sxs-lookup"><span data-stu-id="1fe13-205">Keep the following data and configuration in mind when you set up positions:</span></span>

- <span data-ttu-id="1fe13-206">Beosztás (szükséges)</span><span class="sxs-lookup"><span data-stu-id="1fe13-206">Position (required)</span></span>
- <span data-ttu-id="1fe13-207">Leírás (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-207">Description (required)</span></span>
- <span data-ttu-id="1fe13-208">Munka (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-208">Job (required)</span></span>
- <span data-ttu-id="1fe13-209">Részleg (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-209">Department (required)</span></span>
- <span data-ttu-id="1fe13-210">Beosztás típusa (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-210">Position type (required)</span></span>
- <span data-ttu-id="1fe13-211">Teljes munkaidőssel egyenértékű</span><span class="sxs-lookup"><span data-stu-id="1fe13-211">Full-time equivalent</span></span>
- <span data-ttu-id="1fe13-212">Éves rendes munkaidő (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-212">Annual regular hours (required)</span></span>
- <span data-ttu-id="1fe13-213">Jogi személy által fizetett (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-213">Paid by legal entity (required)</span></span>
- <span data-ttu-id="1fe13-214">Fizetési ciklus (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-214">Pay cycle (required)</span></span>
- <span data-ttu-id="1fe13-215">Alapértelmezett pénzügyi dimenzió – Költséghely (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-215">Default financial dimension – Cost center (required)</span></span>
- <span data-ttu-id="1fe13-216">Dolgozó-hozzárendelés – dolgozó-hozzárendelés kezdete, hozzárendelés vége és okkód</span><span class="sxs-lookup"><span data-stu-id="1fe13-216">Worker assignment – Worker, assignment start, assignment end, reason code</span></span>

<span data-ttu-id="1fe13-217">A azonos osztály több beosztása társítva van az ugyanazon a feladathoz, azok össze lesznek vonva a Dayforce egyetlen pozíciójába.</span><span class="sxs-lookup"><span data-stu-id="1fe13-217">If multiple positions in the same department are associated with the same job, they are consolidated into a single position in Dayforce.</span></span>

<span data-ttu-id="1fe13-218">További információ a következő témakörökben olvasható:</span><span class="sxs-lookup"><span data-stu-id="1fe13-218">For more information, see the following topics:</span></span>

- [<span data-ttu-id="1fe13-219">Munkaerő szervezése részlegek, munkák és beosztások szerint</span><span class="sxs-lookup"><span data-stu-id="1fe13-219">Organize your workforce using departments, jobs, and positions</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [<span data-ttu-id="1fe13-220">Beosztások beállítása</span><span class="sxs-lookup"><span data-stu-id="1fe13-220">Set up positions</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a><span data-ttu-id="1fe13-221">Osztályok</span><span class="sxs-lookup"><span data-stu-id="1fe13-221">Departments</span></span>

<span data-ttu-id="1fe13-222">A részleg egy működési egység, amely a szervezet egy kategóriáját vagy működési területét képviseli.</span><span class="sxs-lookup"><span data-stu-id="1fe13-222">A department is an operating unit that represents a category or functional area of an organization.</span></span> <span data-ttu-id="1fe13-223">Egy részleg a szervezet egy konkrét területen végzett tevékenységeiért felel (például értékesítés, könyvelés, emberi erőforrások).</span><span class="sxs-lookup"><span data-stu-id="1fe13-223">A department is responsible for a specific area of the organization, such as sales, accounting, or human resources.</span></span> <span data-ttu-id="1fe13-224">A részlegek segítségével hozhatók létre jelentések a működési területekről.</span><span class="sxs-lookup"><span data-stu-id="1fe13-224">You can use departments to report on functional areas.</span></span> <span data-ttu-id="1fe13-225">A részlegeknek lehet eredménykimutatási felelőssége.</span><span class="sxs-lookup"><span data-stu-id="1fe13-225">Departments might have profit and loss responsibility.</span></span>

<span data-ttu-id="1fe13-226">További információ a következő témakörökben olvasható:</span><span class="sxs-lookup"><span data-stu-id="1fe13-226">For more information, see the following topics:</span></span>

- [<span data-ttu-id="1fe13-227">Részleg létrehozása és társítása a szervezeti hierarchiához</span><span class="sxs-lookup"><span data-stu-id="1fe13-227">Create a department and associate it with the department hierarchy</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [<span data-ttu-id="1fe13-228">Új részlegek meghatározása</span><span class="sxs-lookup"><span data-stu-id="1fe13-228">Define new departments</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a><span data-ttu-id="1fe13-229">Fizetési ciklusok és fizetési időszakok</span><span class="sxs-lookup"><span data-stu-id="1fe13-229">Pay cycles and pay periods</span></span>

<span data-ttu-id="1fe13-230">A fizetési ciklus meghatározza, hogy milyen gyakran történik a bérlista folyósítása, és a dolgozók mely napokon kapnak fizetést,.</span><span class="sxs-lookup"><span data-stu-id="1fe13-230">A pay cycle determines how often payroll is run and the specific days when workers are paid.</span></span> <span data-ttu-id="1fe13-231">Például a kifizetési ciklus lehet, havi, és az alkalmazottak kaphatják a hónap utolsó napján a fizetésüket.</span><span class="sxs-lookup"><span data-stu-id="1fe13-231">For example, a pay cycle might be monthly, and employees might be paid on the last day of the month.</span></span> <span data-ttu-id="1fe13-232">Vagy a kifizetési ciklus lehet heti, és az alkalmazottak a fizetési időszak utáni kedden kaphatják fizetésüket.</span><span class="sxs-lookup"><span data-stu-id="1fe13-232">Alternatively, a pay cycle might be weekly, and employees might be paid on the Tuesday after the end of the pay period.</span></span> <span data-ttu-id="1fe13-233">Kifizetési ciklusok beosztásokhoz vannak rendelve, és szabályozzák, hogy az ebben a beosztásban lévő dolgozók mikor kapnak fizetést.</span><span class="sxs-lookup"><span data-stu-id="1fe13-233">Pay cycles are assigned to positions to control when workers in those positions are paid.</span></span>

<span data-ttu-id="1fe13-234">Miután létrehozott fizetési ciklusokat, minden egyes ciklushoz fizetési időszakot hozhat létre.</span><span class="sxs-lookup"><span data-stu-id="1fe13-234">After you create pay cycles, you can generate pay periods for each cycle.</span></span> <span data-ttu-id="1fe13-235">Minden fizetési időszakban egy alapértelmezett fizetési dátum van, amely a megadott adatokon alapul.</span><span class="sxs-lookup"><span data-stu-id="1fe13-235">Each pay period includes a default payment date that is based on information that you provide.</span></span> <span data-ttu-id="1fe13-236">Ugyanakkor az alapértelmezett fizetési dátumot a fizetési időszakban módosíthatja kivételekhez például amikor egy kifizetési dátum ünnepnapra esik.</span><span class="sxs-lookup"><span data-stu-id="1fe13-236">However, you can modify the default payment date in a pay period to allow for exceptions, such as when the payment date falls on a holiday.</span></span>

<span data-ttu-id="1fe13-237">A következő adatokat használja a Dayforce:</span><span class="sxs-lookup"><span data-stu-id="1fe13-237">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="1fe13-238">Fizetési ciklus (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-238">Pay cycle (required)</span></span>
- <span data-ttu-id="1fe13-239">Fizetési ciklus gyakorisága (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-239">Pay cycle frequency (required)</span></span>
- <span data-ttu-id="1fe13-240">Az időszak kezdő dátuma (az első fizetési időszak szükséges)</span><span class="sxs-lookup"><span data-stu-id="1fe13-240">Period start date (first pay period required)</span></span>
- <span data-ttu-id="1fe13-241">Alapértelmezett fizetési dátum (az első fizetési időszak szükséges)</span><span class="sxs-lookup"><span data-stu-id="1fe13-241">Default payment date (first pay period required)</span></span>

<span data-ttu-id="1fe13-242">Ez az információ Dayforceba fizetési csoportokként van integrálva országonként vagy régiónként le van választva egyes kifizetési ciklusokhoz.</span><span class="sxs-lookup"><span data-stu-id="1fe13-242">This information is integrated with Dayforce as pay groups, and is separated by country or region for each pay cycle.</span></span> <span data-ttu-id="1fe13-243">Legalább egy fizetési időszakot kell létrehozni az integráció előtt.</span><span class="sxs-lookup"><span data-stu-id="1fe13-243">At least one pay period must be generated before integration.</span></span> <span data-ttu-id="1fe13-244">Dayforce létrehoz fizetési csoport naptárakat és a kifizetési dátumokat, az első fizetési időszak kezdő dátuma és az alapértelmezett fizetési dátum alapján, melyek a Talentben vannak beállítva.</span><span class="sxs-lookup"><span data-stu-id="1fe13-244">Dayforce generates pay group calendars and payment dates, based on the start date of the first pay period and the default payment date that is set up in Talent.</span></span>

#### <a name="earning-codes"></a><span data-ttu-id="1fe13-245">Bevételkódok</span><span class="sxs-lookup"><span data-stu-id="1fe13-245">Earning codes</span></span>

<span data-ttu-id="1fe13-246">A bevételkódok egyedi módon azonosítják a dolgozók által kapott fizetéstípusokat.</span><span class="sxs-lookup"><span data-stu-id="1fe13-246">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="1fe13-247">A kódoknak különböző paraméterei vannak, amelyek a bevételekhez kapcsolódnak, például könyvelési szabályok, jelentési követelmények és bruttósítási lehetőségek.</span><span class="sxs-lookup"><span data-stu-id="1fe13-247">The codes have various parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span>

<span data-ttu-id="1fe13-248">A következő adatokat használja a Dayforce:</span><span class="sxs-lookup"><span data-stu-id="1fe13-248">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="1fe13-249">Bevételkód (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-249">Earning Code (required)</span></span>
- <span data-ttu-id="1fe13-250">Leírás</span><span class="sxs-lookup"><span data-stu-id="1fe13-250">Description</span></span>
- <span data-ttu-id="1fe13-251">Mértékegység</span><span class="sxs-lookup"><span data-stu-id="1fe13-251">Unit of measure</span></span>
- <span data-ttu-id="1fe13-252">Produktív</span><span class="sxs-lookup"><span data-stu-id="1fe13-252">Productive</span></span>

### <a name="worker-data"></a><span data-ttu-id="1fe13-253">Dolgozóadatok</span><span class="sxs-lookup"><span data-stu-id="1fe13-253">Worker data</span></span>

<span data-ttu-id="1fe13-254">A dolgozók különböző típusaihoz tartozó rekordok, melyek fontosak az emberi erőforrásoknak és a bérlistarendszerekhez.</span><span class="sxs-lookup"><span data-stu-id="1fe13-254">Records for the various types of workers that you have are important to your human resources and payroll systems.</span></span> <span data-ttu-id="1fe13-255">A bevitt információk felhasználhatók az dolgozói és személyes adatok nyilvántartására.</span><span class="sxs-lookup"><span data-stu-id="1fe13-255">The information that you enter can be used to track workers and personal information.</span></span>

<span data-ttu-id="1fe13-256">A dolgozók következő adatait tarthatja karban:</span><span class="sxs-lookup"><span data-stu-id="1fe13-256">You can maintain the following information for workers:</span></span>

- <span data-ttu-id="1fe13-257">**Alapvető** – A dolgozók alapvető információi, például a kapcsolattartási adatok, demográfiai adatok azonosító adatok, családi adatok, a katonai szolgálat állapota, kiküldetésekre vonatkozó adatok, illetve személyes és rendkívüli kapcsolattartók.</span><span class="sxs-lookup"><span data-stu-id="1fe13-257">**Basic** – Maintain basic information about a worker, such as contact information, demographic information, identification information, family information, military service status, expatriate information, and personal and emergency contacts.</span></span>
- <span data-ttu-id="1fe13-258">**Foglalkoztatás** – Információk a dolgozó munkaviszonyáról, például a vállalati vagy szervezeti kapcsolat, hozzárendelt pozíció, kezdő és záró dátumok, munkajogosultság, foglalkoztatás feltételei, nyugdíj, szabadság és áthelyezéssel kapcsolatos információk.</span><span class="sxs-lookup"><span data-stu-id="1fe13-258">**Employment** – Maintain information about a worker's employment, such as company or organization affiliation, position assignment, start and end dates, work eligibility, terms of employment, pension, vacation, and relocation information.</span></span>
- <span data-ttu-id="1fe13-259">**Szabadság és a távollét** – A dolgozó távolléteinek kezelése, például a munkaidő-naptárak, a távolléti tranzakciók és távollét beállítása.</span><span class="sxs-lookup"><span data-stu-id="1fe13-259">**Leave and absence** – Maintain information about a worker's absences, such as working calendars, absence transactions, and absence setup.</span></span>
- <span data-ttu-id="1fe13-260">**Kompenzáció és bérlista** – dolgozói kompenzációs tervek és bérlistainformációk kezelése, például felvétel konstrukciója, jutalmak, teljesítmény, jutalék, adózási információk, nyugdíj és fizetéslevonások.</span><span class="sxs-lookup"><span data-stu-id="1fe13-260">**Compensation and payroll** – Maintain information about a worker's compensation plans and payroll information, such as plan enrollment, awards, performance, commission, tax information, retirement, and salary deductions.</span></span>

<span data-ttu-id="1fe13-261">A dolgozóinformációk létrehozása esetén ne felejtse el a következő adatokat és beállításokat, amelyeket a Dayforce használ.</span><span class="sxs-lookup"><span data-stu-id="1fe13-261">When you enter worker information, keep in mind the following data and configurations that are used in Dayforce.</span></span>

#### <a name="general-information"></a><span data-ttu-id="1fe13-262">Általános információk</span><span class="sxs-lookup"><span data-stu-id="1fe13-262">General information</span></span>

- <span data-ttu-id="1fe13-263">Személyzeti szám (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-263">Personnel number (required)</span></span>
- <span data-ttu-id="1fe13-264">Utónév (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-264">First name (required)</span></span>
- <span data-ttu-id="1fe13-265">Vezetéknév (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-265">Last name (required)</span></span>
- <span data-ttu-id="1fe13-266">Második keresztnév</span><span class="sxs-lookup"><span data-stu-id="1fe13-266">Middle name</span></span>
- <span data-ttu-id="1fe13-267">Szolgálati idő dátuma</span><span class="sxs-lookup"><span data-stu-id="1fe13-267">Seniority date</span></span>
- <span data-ttu-id="1fe13-268">Más néven</span><span class="sxs-lookup"><span data-stu-id="1fe13-268">Known as</span></span>

#### <a name="personal-information"></a><span data-ttu-id="1fe13-269">Személyes információ</span><span class="sxs-lookup"><span data-stu-id="1fe13-269">Personal information</span></span>

- <span data-ttu-id="1fe13-270">Családi állapot (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-270">Marital status (required)</span></span>
- <span data-ttu-id="1fe13-271">Születési dátum (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-271">Birth date (required)</span></span>
- <span data-ttu-id="1fe13-272">Nem (szükséges)</span><span class="sxs-lookup"><span data-stu-id="1fe13-272">Gender (required)</span></span>
- <span data-ttu-id="1fe13-273">Fogyatékkal élő személy</span><span class="sxs-lookup"><span data-stu-id="1fe13-273">Person with disabilities</span></span>
- <span data-ttu-id="1fe13-274">Állampolgárság ország régió (csak a Mexikó)</span><span class="sxs-lookup"><span data-stu-id="1fe13-274">Nationality country region (only for Mexico)</span></span>

#### <a name="address-information"></a><span data-ttu-id="1fe13-275">Címadatok</span><span class="sxs-lookup"><span data-stu-id="1fe13-275">Address information</span></span>

- <span data-ttu-id="1fe13-276">Elsődleges (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-276">Primary (required)</span></span>
- <span data-ttu-id="1fe13-277">Ország/régiót (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-277">Country/region (required)</span></span>
- <span data-ttu-id="1fe13-278">Irányítószámot (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-278">Postal code (required)</span></span>
- <span data-ttu-id="1fe13-279">Utca, házszám (kötelező) (csak Mexikó esetén)</span><span class="sxs-lookup"><span data-stu-id="1fe13-279">Street Number (required) (Only for Mexico)</span></span>
- <span data-ttu-id="1fe13-280">Épületblokk (csak a Mexikó)</span><span class="sxs-lookup"><span data-stu-id="1fe13-280">Building Complement (Only for Mexico)</span></span>
- <span data-ttu-id="1fe13-281">Város (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-281">City (required)</span></span>
- <span data-ttu-id="1fe13-282">Állam (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-282">State (required)</span></span>
- <span data-ttu-id="1fe13-283">Megye (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-283">County (required)</span></span>

#### <a name="contact-information"></a><span data-ttu-id="1fe13-284">Névjegy adatai</span><span class="sxs-lookup"><span data-stu-id="1fe13-284">Contact information</span></span> 

- <span data-ttu-id="1fe13-285">Elsődleges (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-285">Primary (required)</span></span>
- <span data-ttu-id="1fe13-286">Kapcsolattartó száma (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-286">Contact number (required)</span></span>
- <span data-ttu-id="1fe13-287">Mellék</span><span class="sxs-lookup"><span data-stu-id="1fe13-287">Extension</span></span>

#### <a name="payroll-information-and-earning-codes"></a><span data-ttu-id="1fe13-288">Bérlistaadatok és bevételkódok</span><span class="sxs-lookup"><span data-stu-id="1fe13-288">Payroll information and earning codes</span></span>

<span data-ttu-id="1fe13-289">Alkalmazottak hozzárendelhetők meghatározott bevételekhez adott fizetési gyakorisággal, és magadható elsődleges fizetési mód.</span><span class="sxs-lookup"><span data-stu-id="1fe13-289">Employees may be assigned specific earnings at a given frequency of payment and have a preferred payment method.</span></span> <span data-ttu-id="1fe13-290">A következő mezőket a Dayforce arra használja, hogy garantálja, hogy ezeket a preferenciákat és beállításokat használja.</span><span class="sxs-lookup"><span data-stu-id="1fe13-290">The following fields are used in Dayforce to help guarantee that those preferences and settings are used.</span></span>

##### <a name="earning-codes"></a><span data-ttu-id="1fe13-291">Bevételkódok</span><span class="sxs-lookup"><span data-stu-id="1fe13-291">Earning codes</span></span>

- <span data-ttu-id="1fe13-292">Beosztás (szükséges)</span><span class="sxs-lookup"><span data-stu-id="1fe13-292">Position (required)</span></span>
- <span data-ttu-id="1fe13-293">Bevételkód (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-293">Earning Code (required)</span></span>
- <span data-ttu-id="1fe13-294">Gyakoriság (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-294">Frequency (required)</span></span>
- <span data-ttu-id="1fe13-295">Összeg (szükséges)</span><span class="sxs-lookup"><span data-stu-id="1fe13-295">Amount (required)</span></span>

##### <a name="payroll-information"></a><span data-ttu-id="1fe13-296">Bérlistaadatok</span><span class="sxs-lookup"><span data-stu-id="1fe13-296">Payroll information</span></span>

- <span data-ttu-id="1fe13-297">Kifizetési mód</span><span class="sxs-lookup"><span data-stu-id="1fe13-297">Payment Method</span></span>
- <span data-ttu-id="1fe13-298">Gazdasági régió (szükséges)</span><span class="sxs-lookup"><span data-stu-id="1fe13-298">Economic Region (required)</span></span>
- <span data-ttu-id="1fe13-299">Alkalmazott juttatásainak azonosítója</span><span class="sxs-lookup"><span data-stu-id="1fe13-299">Employee Benefits ID</span></span>
- <span data-ttu-id="1fe13-300">Nemzeti azonosító (szükséges)</span><span class="sxs-lookup"><span data-stu-id="1fe13-300">National ID Number (required)</span></span>
- <span data-ttu-id="1fe13-301">Katonai szolgálat száma</span><span class="sxs-lookup"><span data-stu-id="1fe13-301">Military Service Number</span></span>
- <span data-ttu-id="1fe13-302">Műszakazonosító (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-302">Shift ID (required)</span></span>
- <span data-ttu-id="1fe13-303">Adószám (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-303">Tax Number (required)</span></span>
- <span data-ttu-id="1fe13-304">Szakszervezeti azonosító (szükséges)</span><span class="sxs-lookup"><span data-stu-id="1fe13-304">Union ID (required)</span></span>
- <span data-ttu-id="1fe13-305">Munkanap azonosítója (szükséges)</span><span class="sxs-lookup"><span data-stu-id="1fe13-305">Work Day ID (required)</span></span>
- <span data-ttu-id="1fe13-306">Munkavállalási engedély száma</span><span class="sxs-lookup"><span data-stu-id="1fe13-306">Work Permit Number</span></span>

> [!NOTE]
> <span data-ttu-id="1fe13-307">A fizetési módhoz Mexikó támogatja a **Készpénzt**, **Csekket** (a vállalat fizikai csekkjét és az **Elektronikus fizetést**.</span><span class="sxs-lookup"><span data-stu-id="1fe13-307">For the payment method, Mexico supports **Cash**, **Check** (the company's physical check), and **Electronic Payment**.</span></span> <span data-ttu-id="1fe13-308">Ha nincs fizetési mód van megadva, alapértelmezés szerint a **Csekk** használt.</span><span class="sxs-lookup"><span data-stu-id="1fe13-308">If np payment method is specified, **Check** is used by default.</span></span>

#### <a name="employment-details"></a><span data-ttu-id="1fe13-309">Foglalkoztatás részletei</span><span class="sxs-lookup"><span data-stu-id="1fe13-309">Employment details</span></span>

<span data-ttu-id="1fe13-310">Foglalkoztatási előzményei kulcsfontosságú információkat tartalmaznak a munkavállaók felvételi, elbocsátási, és újbóli felvétele állapotával kapcsolatosan a Dayforce-ban.</span><span class="sxs-lookup"><span data-stu-id="1fe13-310">Employment detail history is used as key information to derive an employee's hire, termination, and rehire statuses in Dayforce.</span></span> <span data-ttu-id="1fe13-311">Dayforce egyszerre csak egy aktív foglalkoztatásrekordot tesz lehetővé.</span><span class="sxs-lookup"><span data-stu-id="1fe13-311">Dayforce supports only one active employment record at a time.</span></span>

- <span data-ttu-id="1fe13-312">Foglalkoztatás kezdődátuma (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-312">Employment start date (required)</span></span>
- <span data-ttu-id="1fe13-313">Munkaviszony záró dátuma</span><span class="sxs-lookup"><span data-stu-id="1fe13-313">Employment end date</span></span>
- <span data-ttu-id="1fe13-314">Kezdő dátum</span><span class="sxs-lookup"><span data-stu-id="1fe13-314">Start date</span></span>
- <span data-ttu-id="1fe13-315">Módosított kezdési időpont</span><span class="sxs-lookup"><span data-stu-id="1fe13-315">Adjusted start date</span></span>
- <span data-ttu-id="1fe13-316">Munkaviszony megszűnésének dátuma (megszűntetéskor kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-316">Termination date (required upon termination)</span></span>
- <span data-ttu-id="1fe13-317">Felmondás oka (megszűntetéskor kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-317">Termination reason (required upon termination)</span></span>

<span data-ttu-id="1fe13-318">Az alkalmazott legfontosabb dátumai a következő adatokból vannak származtatva.</span><span class="sxs-lookup"><span data-stu-id="1fe13-318">An employee's key dates are derived by using the following information.</span></span>

| <span data-ttu-id="1fe13-319">Talent</span><span class="sxs-lookup"><span data-stu-id="1fe13-319">Talent</span></span>                | <span data-ttu-id="1fe13-320">Dayforce</span><span class="sxs-lookup"><span data-stu-id="1fe13-320">Dayforce</span></span>                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="1fe13-321">Legutóbbi felvételi dátum</span><span class="sxs-lookup"><span data-stu-id="1fe13-321">Most recent hire date</span></span> | <span data-ttu-id="1fe13-322">Foglalkoztatás kezdete az aktuális nem megszűntetett előzményrekordra</span><span class="sxs-lookup"><span data-stu-id="1fe13-322">Employment start of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="1fe13-323">Munkaviszony megszűnésének dátuma</span><span class="sxs-lookup"><span data-stu-id="1fe13-323">Termination date</span></span>      | <span data-ttu-id="1fe13-324">Foglalkoztatás befejezése az aktuális nem megszűntetett előzményrekordra</span><span class="sxs-lookup"><span data-stu-id="1fe13-324">Termination date of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="1fe13-325">Kezdő dátum</span><span class="sxs-lookup"><span data-stu-id="1fe13-325">Start date</span></span>            | <span data-ttu-id="1fe13-326">Módosított kezdési időpont, kezdődátum vagy foglalkoztatás kezdete az aktuális nem aktív előzményrekordra</span><span class="sxs-lookup"><span data-stu-id="1fe13-326">Adjusted start date, start date, or employment start of current non-active employment history record</span></span> |
| <span data-ttu-id="1fe13-327">Eredeti felvételi dátum</span><span class="sxs-lookup"><span data-stu-id="1fe13-327">Original hire date</span></span>    | <span data-ttu-id="1fe13-328">Foglalkoztatás kezdete legkorábbi foglalkoztatási előzményrekordra</span><span class="sxs-lookup"><span data-stu-id="1fe13-328">Employment start of earliest employment history record</span></span>                                               |

#### <a name="compensation"></a><span data-ttu-id="1fe13-329">Kompenzáció</span><span class="sxs-lookup"><span data-stu-id="1fe13-329">Compensation</span></span>

<span data-ttu-id="1fe13-330">Egy fix kompenzációs tervet kell társítani minden alkalmazott elsődleges pozíciójához az alkalmazási időszak alatt.</span><span class="sxs-lookup"><span data-stu-id="1fe13-330">A fixed compensation plan must be associated with every employee's primary position throughout an employment period.</span></span> <span data-ttu-id="1fe13-331">Az időszak a belépés dátumával (vagy a foglalkoztatás kezdő dátumával) kezdődik, és a munkaviszony megszűnéséig tart .</span><span class="sxs-lookup"><span data-stu-id="1fe13-331">This period starts on the date that the employee was hired (or the employment start date) and continues until termination.</span></span>

- <span data-ttu-id="1fe13-332">Érvényesség dátuma (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-332">Effective Date (required)</span></span>
- <span data-ttu-id="1fe13-333">Lejárati dátum</span><span class="sxs-lookup"><span data-stu-id="1fe13-333">Expiration date</span></span>
- <span data-ttu-id="1fe13-334">Fizetési díjalap (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-334">Pay Rate (required)</span></span>
- <span data-ttu-id="1fe13-335">Fizetési díjalapok átalakításai (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-335">Pay Rate Conversions (required)</span></span>
- <span data-ttu-id="1fe13-336">Évi egyenérték (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-336">Annual equivalent (required)</span></span>
- <span data-ttu-id="1fe13-337">Óránkénti egyenérték (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-337">Hourly equivalent (required)</span></span>

<span data-ttu-id="1fe13-338">Ha az óránkénti alkalmazottnak több beosztása van, az elsődleges beosztásához tartozó fix kompenzációja importálva lesz a Dayforce-ba, alkalmazott szintű alapdíj/-fizetés.</span><span class="sxs-lookup"><span data-stu-id="1fe13-338">If an hourly employee has multiple positions, the fixed compensation of the primary position is imported into Dayforce as the employee-level base rate/salary.</span></span> <span data-ttu-id="1fe13-339">A nem elsődleges beosztások esetén, az óránkénti díj a megfelelő pozícióba lesz mentve Dayforce-ban.</span><span class="sxs-lookup"><span data-stu-id="1fe13-339">For non-primary positions, the hourly rate is saved to the corresponding position in Dayforce.</span></span>

<span data-ttu-id="1fe13-340">Ha a fizetett alkalmazott több beosztással rendelkezik, a összesített óradíj és éves fizetés származtatva lesz az összes aktív beosztásból mint az alkalmazotti szintű alapdíj/-fizetés.</span><span class="sxs-lookup"><span data-stu-id="1fe13-340">If a salaried employee has multiple positions, the cumulative hour rate and annual salary across all active positions are derived and used as the employee-level base rate/salary.</span></span>

#### <a name="identification-numbers"></a><span data-ttu-id="1fe13-341">Azonosítószámok</span><span class="sxs-lookup"><span data-stu-id="1fe13-341">Identification numbers</span></span>

##### <a name="social-security-identifier"></a><span data-ttu-id="1fe13-342">Társadalombiztosítási azonosító</span><span class="sxs-lookup"><span data-stu-id="1fe13-342">Social Security identifier</span></span> 

<span data-ttu-id="1fe13-343">Minden alkalmazottnak kell egy elsődleges azonosítóval rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="1fe13-343">Every employee must have one primary identifier.</span></span> <span data-ttu-id="1fe13-344">Ez az azonosító legyen **TAJ-szám** azonosítótípus kell legyen.</span><span class="sxs-lookup"><span data-stu-id="1fe13-344">This identifier must be of **SSN** identification type.</span></span> <span data-ttu-id="1fe13-345">A Dayforce-ban automatikusan van származtatva az alkalmazott társadalombiztosítási azonosítójából, mely a felvételhez szükséges.</span><span class="sxs-lookup"><span data-stu-id="1fe13-345">In Dayforce, it's automatically derived as the employee's Social Security identifier that is required for hire.</span></span>

- <span data-ttu-id="1fe13-346">Elsődleges (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-346">Primary (required)</span></span>
- <span data-ttu-id="1fe13-347">Azonosító típusa = „TAJ-szám”</span><span class="sxs-lookup"><span data-stu-id="1fe13-347">Identification Type = "SSN"</span></span>
- <span data-ttu-id="1fe13-348">Kibocsátás dátuma</span><span class="sxs-lookup"><span data-stu-id="1fe13-348">Issued Date</span></span>
- <span data-ttu-id="1fe13-349">Lejárat dátuma</span><span class="sxs-lookup"><span data-stu-id="1fe13-349">Expiration Date</span></span>

<span data-ttu-id="1fe13-350">Az alkalmazottak több azonosítószámot is megadhatnak **TAJ-szám** azonosítótípushoz.</span><span class="sxs-lookup"><span data-stu-id="1fe13-350">Employees can declare multiple identification numbers of the **SSN** identification type.</span></span> <span data-ttu-id="1fe13-351">Azonban csak az **Elsődlegesként** megjelölt rekord van integrálva Dayforce-ba, függetlenül attól, hogy a szám aktív vagy lejárt.</span><span class="sxs-lookup"><span data-stu-id="1fe13-351">However, only the record that is marked as **Primary** is integrated into Dayforce, regardless of whether the number is active or expired.</span></span>

#### <a name="bank-accounts-and-disbursements"></a><span data-ttu-id="1fe13-352">Bankszámlák és kifizetések</span><span class="sxs-lookup"><span data-stu-id="1fe13-352">Bank accounts and disbursements</span></span>

<span data-ttu-id="1fe13-353">Érvényes bankszámlaadatokat meg kell adni minden olyan alkalmazotthoz, aki úgy dönt, hogy a banki átutalással kéri fizetését.</span><span class="sxs-lookup"><span data-stu-id="1fe13-353">Valid bank account information must be entered for any employee who chooses to be paid via bank account transfers.</span></span>

| <span data-ttu-id="1fe13-354">Talent</span><span class="sxs-lookup"><span data-stu-id="1fe13-354">Talent</span></span>                         | <span data-ttu-id="1fe13-355">Dayforce</span><span class="sxs-lookup"><span data-stu-id="1fe13-355">Dayforce</span></span>                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="1fe13-356">Bankszámlaszám (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-356">Bank account number (required)</span></span> |                                                                                                             |
| <span data-ttu-id="1fe13-357">SWIFT-kód (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-357">SWIFT code (required)</span></span>          | <span data-ttu-id="1fe13-358">**Bankazonosító** ez a mező Mexikóban történő bérlistafeldolgozáskor használatos.</span><span class="sxs-lookup"><span data-stu-id="1fe13-358">**Bank ID** field used when processing payroll in Mexico.</span></span>                                                             |
| <span data-ttu-id="1fe13-359">Ágazati szám (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-359">Branch number (required)</span></span>       |                                                                                                             |
| <span data-ttu-id="1fe13-360">Bankszámla típusa (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-360">Bank account type (required)</span></span>   | <span data-ttu-id="1fe13-361">**Számlatípus** ez a mező Mexikóban történő bérlistafeldolgozáskor használatos.</span><span class="sxs-lookup"><span data-stu-id="1fe13-361">**Account type** field used when processing payroll in Mexico.</span></span> <span data-ttu-id="1fe13-362">Támogatott értékek: **Folyószámla** és **Bérlista**</span><span class="sxs-lookup"><span data-stu-id="1fe13-362">Supported values include **Checking** and **Payroll**.</span></span> |

> [!NOTE]
> <span data-ttu-id="1fe13-363">Alkalmazottak, akik úgy döntenek, hogy a banki átutaláson keresztülkérik fizetésük, meg kell adniuk egy hivatkozást egy jogi személyhez tartozó egyenlegszámlához, melynek elsődleges címének Mexikóban kell lennie és egy Mexikói bank érvényes bankszámlájához van társítva.</span><span class="sxs-lookup"><span data-stu-id="1fe13-363">Employees who choose to be paid via bank account transfers must provide a link to a remainder account that is under a legal entity that has its primary address in Mexico and associated with a valid bank account from a Mexican bank.</span></span> <span data-ttu-id="1fe13-364">Minden egyéb nem egyenlegszámla figyelmen kívül lesz hagyva.</span><span class="sxs-lookup"><span data-stu-id="1fe13-364">All other non-remainder accounts are ignored.</span></span>

#### <a name="address-information"></a><span data-ttu-id="1fe13-365">Címadatok</span><span class="sxs-lookup"><span data-stu-id="1fe13-365">Address information</span></span>

<span data-ttu-id="1fe13-366">Minden alkalmazottnak kell egy elsődleges hellyel rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="1fe13-366">Every employee must have one primary location.</span></span> <span data-ttu-id="1fe13-367">A Dayforce-ban ezen hely alapján van meghatározva az alkalmazott elsődleges tartózkodási helye adózási célokból.</span><span class="sxs-lookup"><span data-stu-id="1fe13-367">In Dayforce, this location is used to determine the employee's primary residence for tax purposes.</span></span>

- <span data-ttu-id="1fe13-368">Elsődleges (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-368">Primary (required)</span></span>
- <span data-ttu-id="1fe13-369">Ország/régiót (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-369">Country/region (required)</span></span>
- <span data-ttu-id="1fe13-370">Irányítószám/postai kód (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-370">Zip/postal code (required)</span></span>
- <span data-ttu-id="1fe13-371">Utca (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-371">Street (required)</span></span>
- <span data-ttu-id="1fe13-372">Házszám (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-372">Street Number (required)</span></span>
- <span data-ttu-id="1fe13-373">Épületblokk</span><span class="sxs-lookup"><span data-stu-id="1fe13-373">Building Complement</span></span>
- <span data-ttu-id="1fe13-374">Város (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-374">City (required)</span></span>
- <span data-ttu-id="1fe13-375">Állam (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-375">State (required)</span></span>
- <span data-ttu-id="1fe13-376">Megye (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-376">County (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a><span data-ttu-id="1fe13-377">Az adatok konfigurálása bérlista létrehozásához az Egyesült Államokban és Kanadában</span><span class="sxs-lookup"><span data-stu-id="1fe13-377">Configure your data to generate payroll in United States and Canada</span></span>

<span data-ttu-id="1fe13-378">Ha a fizetést generálása alkalmazottaknak az Egyesült Államokban és Kanadában, a következő elemeket kell beállítani:</span><span class="sxs-lookup"><span data-stu-id="1fe13-378">If you're generating pay for employees in the United States and Canada, the following elements must be configured:</span></span>

- <span data-ttu-id="1fe13-379">Részlegek szükségesek beosztásokhoz.</span><span class="sxs-lookup"><span data-stu-id="1fe13-379">Departments are required on positions.</span></span>
- <span data-ttu-id="1fe13-380">Költséghelyek pénzügyi dimenziókként kell beállítani, és az alapértelmezett pénzügyi dimenzió karakterlánc első elemének kell lennie.</span><span class="sxs-lookup"><span data-stu-id="1fe13-380">Cost centers must be set as financial dimensions and must be the first element in the default financial dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="1fe13-381">Beosztástípusok</span><span class="sxs-lookup"><span data-stu-id="1fe13-381">Job types</span></span>

<span data-ttu-id="1fe13-382">Beosztástípusok használatával a hasonló feladatok kategóriákba sorolhatók.</span><span class="sxs-lookup"><span data-stu-id="1fe13-382">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="1fe13-383">A beosztástípusok szükségesek az Egyesült Államokban és Kanadában a bérlisták feldolgozásához.</span><span class="sxs-lookup"><span data-stu-id="1fe13-383">Job types are required in order to process payroll in the United States and Canada.</span></span> <span data-ttu-id="1fe13-384">Beosztástípusok többek között a teljes és részmunkaidős, illetve a munkabéres és az órabéres.</span><span class="sxs-lookup"><span data-stu-id="1fe13-384">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="1fe13-385">A beosztástípusok a fizetéstípusokként vannak hozzárendelve a Dayforce-hoz, melyek jelzik, hogy a munkavállaló órás vagy bérezéses.</span><span class="sxs-lookup"><span data-stu-id="1fe13-385">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="1fe13-386">A következő feladattípusok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="1fe13-386">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="1fe13-387">Feladattípus</span><span class="sxs-lookup"><span data-stu-id="1fe13-387">Job type</span></span>   | <span data-ttu-id="1fe13-388">Leírás</span><span class="sxs-lookup"><span data-stu-id="1fe13-388">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="1fe13-389">Óránként</span><span class="sxs-lookup"><span data-stu-id="1fe13-389">Hourly</span></span>     | <span data-ttu-id="1fe13-390">Óránként</span><span class="sxs-lookup"><span data-stu-id="1fe13-390">Hourly</span></span>      |
| <span data-ttu-id="1fe13-391">Bérezéses</span><span class="sxs-lookup"><span data-stu-id="1fe13-391">Salaried</span></span>   | <span data-ttu-id="1fe13-392">Bérezéses</span><span class="sxs-lookup"><span data-stu-id="1fe13-392">Salaried</span></span>    |

### <a name="position-types"></a><span data-ttu-id="1fe13-393">Beosztási típusok</span><span class="sxs-lookup"><span data-stu-id="1fe13-393">Position types</span></span> 

<span data-ttu-id="1fe13-394">Ne használjon beosztástípusokat annak leírására, hogy a beosztás teljes munkaidős, részmunkaidős vagy más.</span><span class="sxs-lookup"><span data-stu-id="1fe13-394">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="1fe13-395">A feladattípusok a fizetésosztályokként vannak hozzárendelve a Dayforce-hoz, melyek jelzik, hogy a munkavállaló teljes- vagy részmunkaidős.</span><span class="sxs-lookup"><span data-stu-id="1fe13-395">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="1fe13-396">A következő beosztástípusok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="1fe13-396">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="1fe13-397">Beosztás típusa</span><span class="sxs-lookup"><span data-stu-id="1fe13-397">Position type</span></span>   | <span data-ttu-id="1fe13-398">Leírás</span><span class="sxs-lookup"><span data-stu-id="1fe13-398">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="1fe13-399">Teljes munkaidős</span><span class="sxs-lookup"><span data-stu-id="1fe13-399">Full-time</span></span>       | <span data-ttu-id="1fe13-400">Teljes munkaidős alkalmazott</span><span class="sxs-lookup"><span data-stu-id="1fe13-400">Full time employee</span></span> |
| <span data-ttu-id="1fe13-401">Részmunkaidős</span><span class="sxs-lookup"><span data-stu-id="1fe13-401">Part-time</span></span>       | <span data-ttu-id="1fe13-402">Részmunkaidős alkalmazott</span><span class="sxs-lookup"><span data-stu-id="1fe13-402">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="1fe13-403">Okkódok</span><span class="sxs-lookup"><span data-stu-id="1fe13-403">Reason codes</span></span>

<span data-ttu-id="1fe13-404">Az alkalmazottak állapotával kapcsolatos okkódok tájékoztatnak.</span><span class="sxs-lookup"><span data-stu-id="1fe13-404">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="1fe13-405">Okkódok a Dayforce-hoz állapot okaként vannak hozzárendelve, melyek jelzik egy alkalmazott beosztásában vagy alkalmazotti státuszában bekövetkezett változások okát.</span><span class="sxs-lookup"><span data-stu-id="1fe13-405">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="1fe13-406">A következő okkódok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="1fe13-406">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="1fe13-407">Okkód</span><span class="sxs-lookup"><span data-stu-id="1fe13-407">Reason code</span></span>    | <span data-ttu-id="1fe13-408">Leírás</span><span class="sxs-lookup"><span data-stu-id="1fe13-408">Description</span></span>      | <span data-ttu-id="1fe13-409">Alkalmazandó forgatókönyvek</span><span class="sxs-lookup"><span data-stu-id="1fe13-409">Applicable scenarios</span></span> |
|----------------|------------------|----------------------|
| <span data-ttu-id="1fe13-410">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="1fe13-410">RESIGNATION</span></span>    | <span data-ttu-id="1fe13-411">Felmondás</span><span class="sxs-lookup"><span data-stu-id="1fe13-411">Resignation</span></span>      | <span data-ttu-id="1fe13-412">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="1fe13-412">Terminate worker</span></span>     |
| <span data-ttu-id="1fe13-413">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="1fe13-413">TERMINATION</span></span>    | <span data-ttu-id="1fe13-414">Befejezés</span><span class="sxs-lookup"><span data-stu-id="1fe13-414">Termination</span></span>      | <span data-ttu-id="1fe13-415">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="1fe13-415">Terminate worker</span></span>     |
| <span data-ttu-id="1fe13-416">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="1fe13-416">RETIREMENT</span></span>     | <span data-ttu-id="1fe13-417">Megszüntetés</span><span class="sxs-lookup"><span data-stu-id="1fe13-417">Retirement</span></span>       | <span data-ttu-id="1fe13-418">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="1fe13-418">Terminate worker</span></span>     |
| <span data-ttu-id="1fe13-419">EGYÉB</span><span class="sxs-lookup"><span data-stu-id="1fe13-419">OTHER</span></span>          | <span data-ttu-id="1fe13-420">Egyéb okok</span><span class="sxs-lookup"><span data-stu-id="1fe13-420">Other Reasons</span></span>    | <span data-ttu-id="1fe13-421">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="1fe13-421">Terminate worker</span></span>     |
| <span data-ttu-id="1fe13-422">DEATH</span><span class="sxs-lookup"><span data-stu-id="1fe13-422">DEATH</span></span>          | <span data-ttu-id="1fe13-423">Elhalálozás</span><span class="sxs-lookup"><span data-stu-id="1fe13-423">Death</span></span>            | <span data-ttu-id="1fe13-424">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="1fe13-424">Terminate worker</span></span>     |
| <span data-ttu-id="1fe13-425">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="1fe13-425">LEAVEOFABSENCE</span></span> | <span data-ttu-id="1fe13-426">Szabadság</span><span class="sxs-lookup"><span data-stu-id="1fe13-426">Leave of Absence</span></span> | <span data-ttu-id="1fe13-427">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="1fe13-427">Terminate worker</span></span>     |
| <span data-ttu-id="1fe13-428">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="1fe13-428">CONTRACTEND</span></span>    | <span data-ttu-id="1fe13-429">Szerződés vége</span><span class="sxs-lookup"><span data-stu-id="1fe13-429">End of Contract</span></span>  | <span data-ttu-id="1fe13-430">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="1fe13-430">Terminate worker</span></span>     |
| <span data-ttu-id="1fe13-431">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="1fe13-431">SALARYCHANGE</span></span>   | <span data-ttu-id="1fe13-432">Munkabér módosítása</span><span class="sxs-lookup"><span data-stu-id="1fe13-432">Change of Salary</span></span> | <span data-ttu-id="1fe13-433">Kompenzáció</span><span class="sxs-lookup"><span data-stu-id="1fe13-433">Compensation</span></span>         |

### <a name="marital-status"></a><span data-ttu-id="1fe13-434">Családi állapot</span><span class="sxs-lookup"><span data-stu-id="1fe13-434">Marital status</span></span>

<span data-ttu-id="1fe13-435">Családi állapot értékei Dayforce-hoz vannak rendelve és konvertálva szükség esetén az elfogadható értékekre az integráció során.</span><span class="sxs-lookup"><span data-stu-id="1fe13-435">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="1fe13-436">Az alábbi táblázat bemutatja, hogy családi állapot értékek hogyan vannak leképezve a Dayforce -ban.</span><span class="sxs-lookup"><span data-stu-id="1fe13-436">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="1fe13-437">Talent</span><span class="sxs-lookup"><span data-stu-id="1fe13-437">Talent</span></span>                 | <span data-ttu-id="1fe13-438">Dayforce</span><span class="sxs-lookup"><span data-stu-id="1fe13-438">Dayforce</span></span>             |
|------------------------|----------------------|
| <span data-ttu-id="1fe13-439">Házas</span><span class="sxs-lookup"><span data-stu-id="1fe13-439">Married</span></span>                | <span data-ttu-id="1fe13-440">Házas</span><span class="sxs-lookup"><span data-stu-id="1fe13-440">Married</span></span>              |
| <span data-ttu-id="1fe13-441">Egy</span><span class="sxs-lookup"><span data-stu-id="1fe13-441">Single</span></span>                 | <span data-ttu-id="1fe13-442">Egy</span><span class="sxs-lookup"><span data-stu-id="1fe13-442">Single</span></span>               |
| <span data-ttu-id="1fe13-443">Özvegy</span><span class="sxs-lookup"><span data-stu-id="1fe13-443">Widowed</span></span>                | <span data-ttu-id="1fe13-444">Özvegy</span><span class="sxs-lookup"><span data-stu-id="1fe13-444">Widowed</span></span>              |
| <span data-ttu-id="1fe13-445">Elvált</span><span class="sxs-lookup"><span data-stu-id="1fe13-445">Divorced</span></span>               | <span data-ttu-id="1fe13-446">Elvált</span><span class="sxs-lookup"><span data-stu-id="1fe13-446">Divorced</span></span>             |
| <span data-ttu-id="1fe13-447">Bejegyzett élettársi kapcsolat</span><span class="sxs-lookup"><span data-stu-id="1fe13-447">Registered Partnership</span></span> | <span data-ttu-id="1fe13-448">Élettársi viszony</span><span class="sxs-lookup"><span data-stu-id="1fe13-448">Domestic Partnership</span></span> |
| <span data-ttu-id="1fe13-449">Nincs</span><span class="sxs-lookup"><span data-stu-id="1fe13-449">None</span></span>                   | <span data-ttu-id="1fe13-450">Nincs</span><span class="sxs-lookup"><span data-stu-id="1fe13-450">None</span></span>                 |
| <span data-ttu-id="1fe13-451">Együttélés</span><span class="sxs-lookup"><span data-stu-id="1fe13-451">Cohabiting</span></span>             | <span data-ttu-id="1fe13-452">Együttélés</span><span class="sxs-lookup"><span data-stu-id="1fe13-452">Cohabiting</span></span>           |

### <a name="gender"></a><span data-ttu-id="1fe13-453">Nem</span><span class="sxs-lookup"><span data-stu-id="1fe13-453">Gender</span></span>

<span data-ttu-id="1fe13-454">A nemek a Dayforce-hoz vannak rendelve és konvertálva szükség esetén az elfogadható értékekre az integráció során.</span><span class="sxs-lookup"><span data-stu-id="1fe13-454">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="1fe13-455">Az alábbi táblázat bemutatja, hogy a nemek hogyan vannak leképezve a Dayforce-ban.</span><span class="sxs-lookup"><span data-stu-id="1fe13-455">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="1fe13-456">Talent</span><span class="sxs-lookup"><span data-stu-id="1fe13-456">Talent</span></span>       | <span data-ttu-id="1fe13-457">Dayforce</span><span class="sxs-lookup"><span data-stu-id="1fe13-457">Dayforce</span></span>        |
|--------------|-----------------|
| <span data-ttu-id="1fe13-458">Férfi</span><span class="sxs-lookup"><span data-stu-id="1fe13-458">Male</span></span>         | <span data-ttu-id="1fe13-459">Férfi</span><span class="sxs-lookup"><span data-stu-id="1fe13-459">Male</span></span>            |
| <span data-ttu-id="1fe13-460">Nő</span><span class="sxs-lookup"><span data-stu-id="1fe13-460">Female</span></span>       | <span data-ttu-id="1fe13-461">Nő</span><span class="sxs-lookup"><span data-stu-id="1fe13-461">Female</span></span>          |
| <span data-ttu-id="1fe13-462">Nem meghatározott</span><span class="sxs-lookup"><span data-stu-id="1fe13-462">Non-specific</span></span> | <span data-ttu-id="1fe13-463">*Nem támogatott*</span><span class="sxs-lookup"><span data-stu-id="1fe13-463">*Not supported*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="1fe13-464">Bevételkódok</span><span class="sxs-lookup"><span data-stu-id="1fe13-464">Earning codes</span></span>

<span data-ttu-id="1fe13-465">A bevételkódok egyedi módon azonosítják a dolgozók által kapott fizetéstípusokat.</span><span class="sxs-lookup"><span data-stu-id="1fe13-465">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="1fe13-466">A kódoknak különböző paramétereket fednek le, amelyek a bevételekhez kapcsolódnak, például könyvelési szabályok, jelentési követelmények és bruttósítási lehetőségek.</span><span class="sxs-lookup"><span data-stu-id="1fe13-466">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="1fe13-467">Ha egy nem támogatott gyakoriság van használatban, a **Minden fizetés** gyakorisága van alapértelmezés szerint használva a kiszámításhoz.</span><span class="sxs-lookup"><span data-stu-id="1fe13-467">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="1fe13-468">Támogatott gyakoriságok</span><span class="sxs-lookup"><span data-stu-id="1fe13-468">Supported frequencies</span></span>

- <span data-ttu-id="1fe13-469">Összes</span><span class="sxs-lookup"><span data-stu-id="1fe13-469">All</span></span>
- <span data-ttu-id="1fe13-470">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="1fe13-470">EVERYPAY</span></span>
- <span data-ttu-id="1fe13-471">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="1fe13-471">EACHPAYPERIOD</span></span>
- <span data-ttu-id="1fe13-472">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="1fe13-472">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="1fe13-473">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="1fe13-473">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="1fe13-474">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="1fe13-474">1OFMTH</span></span>
- <span data-ttu-id="1fe13-475">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="1fe13-475">LASTOFMTH</span></span>
- <span data-ttu-id="1fe13-476">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="1fe13-476">2OFMTH</span></span>
- <span data-ttu-id="1fe13-477">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="1fe13-477">3OFMTH</span></span>
- <span data-ttu-id="1fe13-478">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="1fe13-478">4OFMTH</span></span>
- <span data-ttu-id="1fe13-479">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="1fe13-479">5OFMTH</span></span>
- <span data-ttu-id="1fe13-480">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="1fe13-480">1N2OFMTH</span></span>
- <span data-ttu-id="1fe13-481">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="1fe13-481">3N4OFMTH</span></span>
- <span data-ttu-id="1fe13-482">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="1fe13-482">1N3OFMTH</span></span>
- <span data-ttu-id="1fe13-483">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="1fe13-483">1N4OFMTH</span></span>
- <span data-ttu-id="1fe13-484">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="1fe13-484">2N3OFMTH</span></span>
- <span data-ttu-id="1fe13-485">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="1fe13-485">2N4OFMTH</span></span>
- <span data-ttu-id="1fe13-486">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="1fe13-486">1N2N3OFMTH</span></span>
- <span data-ttu-id="1fe13-487">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="1fe13-487">1N2N4OFMTH</span></span>
- <span data-ttu-id="1fe13-488">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="1fe13-488">1N3N4OFMTH</span></span>
- <span data-ttu-id="1fe13-489">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="1fe13-489">2N3N4OFMTH</span></span>
- <span data-ttu-id="1fe13-490">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="1fe13-490">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="1fe13-491">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="1fe13-491">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="1fe13-492">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="1fe13-492">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="1fe13-493">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="1fe13-493">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="1fe13-494">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="1fe13-494">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="1fe13-495">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="1fe13-495">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="1fe13-496">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="1fe13-496">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="1fe13-497">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="1fe13-497">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="1fe13-498">Címek</span><span class="sxs-lookup"><span data-stu-id="1fe13-498">Addresses</span></span>

<span data-ttu-id="1fe13-499">Az adott ország vagy régió, állam és megye (település) kódok specifikus formátumokat követelnek, hogy Dayforce és az országos és regionális szolgáltatók felismerjék azokat.</span><span class="sxs-lookup"><span data-stu-id="1fe13-499">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="1fe13-500">Annak ellenére, hogy a városok formátuma rugalmas, minden városnak társítva kell lennie egy államhoz.</span><span class="sxs-lookup"><span data-stu-id="1fe13-500">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="1fe13-501">Talent</span><span class="sxs-lookup"><span data-stu-id="1fe13-501">Talent</span></span>          | <span data-ttu-id="1fe13-502">Dayforce</span><span class="sxs-lookup"><span data-stu-id="1fe13-502">Dayforce</span></span>              |
|-----------------|-----------------------|
| <span data-ttu-id="1fe13-503">Ország/régió</span><span class="sxs-lookup"><span data-stu-id="1fe13-503">Country/Region</span></span>  | <span data-ttu-id="1fe13-504">Országkód</span><span class="sxs-lookup"><span data-stu-id="1fe13-504">Country Code</span></span>          |
| <span data-ttu-id="1fe13-505">Irányítószám / postai kód</span><span class="sxs-lookup"><span data-stu-id="1fe13-505">Zip/Postal Code</span></span> | <span data-ttu-id="1fe13-506">Irányítószám</span><span class="sxs-lookup"><span data-stu-id="1fe13-506">Postal Code</span></span>           |
| <span data-ttu-id="1fe13-507">Állami</span><span class="sxs-lookup"><span data-stu-id="1fe13-507">State</span></span>           | <span data-ttu-id="1fe13-508">Államkód</span><span class="sxs-lookup"><span data-stu-id="1fe13-508">State Code</span></span>            |
| <span data-ttu-id="1fe13-509">Város</span><span class="sxs-lookup"><span data-stu-id="1fe13-509">City</span></span>            | <span data-ttu-id="1fe13-510">Város</span><span class="sxs-lookup"><span data-stu-id="1fe13-510">City</span></span>                  |
| <span data-ttu-id="1fe13-511">Megye</span><span class="sxs-lookup"><span data-stu-id="1fe13-511">County</span></span>          | <span data-ttu-id="1fe13-512">Megye (Helyhatóság)</span><span class="sxs-lookup"><span data-stu-id="1fe13-512">County (Municipality)</span></span> |
| <span data-ttu-id="1fe13-513">Utca</span><span class="sxs-lookup"><span data-stu-id="1fe13-513">Street</span></span>          | <span data-ttu-id="1fe13-514">Cím 1. sora</span><span class="sxs-lookup"><span data-stu-id="1fe13-514">Address Line 1</span></span>        |

### <a name="tax-regions"></a><span data-ttu-id="1fe13-515">Adórégiók</span><span class="sxs-lookup"><span data-stu-id="1fe13-515">Tax regions</span></span>

<span data-ttu-id="1fe13-516">Az adórégiók a megfelelő adó megállapítására szolgálnak, amelyet a bérlista létrehozásakor kell alkalmazni.</span><span class="sxs-lookup"><span data-stu-id="1fe13-516">Tax regions are used to determine the appropriate tax that should be applied during payroll generation.</span></span> <span data-ttu-id="1fe13-517">Az adórégiók helycímként vannak a Dayforce-hoz rendelve.</span><span class="sxs-lookup"><span data-stu-id="1fe13-517">Tax regions are mapped to Dayforce as location addresses.</span></span> <span data-ttu-id="1fe13-518">Az alapértelmezett adórégiót a dolgozó aktív beosztásával kell társítani.</span><span class="sxs-lookup"><span data-stu-id="1fe13-518">The default tax region must be associated with the worker's active position.</span></span> 

- <span data-ttu-id="1fe13-519">Adórégió (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-519">Tax region (required)</span></span>
- <span data-ttu-id="1fe13-520">Ország/régió (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-520">Country/Region (required)</span></span>
- <span data-ttu-id="1fe13-521">Állam (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-521">State (required)</span></span>
- <span data-ttu-id="1fe13-522">Megye</span><span class="sxs-lookup"><span data-stu-id="1fe13-522">County</span></span> 
- <span data-ttu-id="1fe13-523">Város (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1fe13-523">City (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a><span data-ttu-id="1fe13-524">Adatok konfigurálása bérlista létrehozásához Mexikóban</span><span class="sxs-lookup"><span data-stu-id="1fe13-524">Configure your data to generate payroll in Mexico</span></span>

<span data-ttu-id="1fe13-525">Ha a fizetést generál alkalmazottaknak Mexikóban, a következő elemeket kell beállítani:</span><span class="sxs-lookup"><span data-stu-id="1fe13-525">If you're generating pay for employees in Mexico, the following elements must be configured:</span></span>

- <span data-ttu-id="1fe13-526">Részlegek szükségesek beosztásokhoz.</span><span class="sxs-lookup"><span data-stu-id="1fe13-526">Departments are required on positions.</span></span>
- <span data-ttu-id="1fe13-527">Költséghelyek pénzügyi dimenziókként kell beállítani, és az Alapértelmezett pénzügyi dimenzió karakterlánc első elemének kell lennie.</span><span class="sxs-lookup"><span data-stu-id="1fe13-527">Cost centers must be set as financial dimensions and must be the first element in the Default Financial Dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="1fe13-528">Beosztástípusok</span><span class="sxs-lookup"><span data-stu-id="1fe13-528">Job types</span></span>

<span data-ttu-id="1fe13-529">Beosztástípusok használatával a hasonló feladatok kategóriákba sorolhatók.</span><span class="sxs-lookup"><span data-stu-id="1fe13-529">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="1fe13-530">Mexikóban a Bérlista feldolgozásához feladattípusok szükségesek.</span><span class="sxs-lookup"><span data-stu-id="1fe13-530">Job types are required in order to process payroll in Mexico.</span></span> <span data-ttu-id="1fe13-531">Beosztástípusok többek között a teljes és részmunkaidős, illetve a munkabéres és az órabéres.</span><span class="sxs-lookup"><span data-stu-id="1fe13-531">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="1fe13-532">A beosztástípusok a fizetéstípusokként vannak hozzárendelve a Dayforce-hoz, melyek jelzik, hogy a munkavállaló órás vagy bérezéses.</span><span class="sxs-lookup"><span data-stu-id="1fe13-532">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="1fe13-533">A következő feladattípusok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="1fe13-533">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="1fe13-534">Feladattípus</span><span class="sxs-lookup"><span data-stu-id="1fe13-534">Job type</span></span>   | <span data-ttu-id="1fe13-535">Leírás</span><span class="sxs-lookup"><span data-stu-id="1fe13-535">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="1fe13-536">Óránként</span><span class="sxs-lookup"><span data-stu-id="1fe13-536">Hourly</span></span>     | <span data-ttu-id="1fe13-537">MX Órabér</span><span class="sxs-lookup"><span data-stu-id="1fe13-537">MX Hourly</span></span>   |
| <span data-ttu-id="1fe13-538">Bérezéses</span><span class="sxs-lookup"><span data-stu-id="1fe13-538">Salaried</span></span>   | <span data-ttu-id="1fe13-539">MX Bérezéses</span><span class="sxs-lookup"><span data-stu-id="1fe13-539">MX Salaried</span></span> |

### <a name="position-types"></a><span data-ttu-id="1fe13-540">Beosztási típusok</span><span class="sxs-lookup"><span data-stu-id="1fe13-540">Position types</span></span> 

<span data-ttu-id="1fe13-541">Ne használjon beosztástípusokat annak leírására, hogy a beosztás teljes munkaidős, részmunkaidős vagy más.</span><span class="sxs-lookup"><span data-stu-id="1fe13-541">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="1fe13-542">A feladattípusok a fizetésosztályokként vannak hozzárendelve a Dayforce-hoz, melyek jelzik, hogy a munkavállaló teljes- vagy részmunkaidős.</span><span class="sxs-lookup"><span data-stu-id="1fe13-542">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="1fe13-543">A következő beosztástípusok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="1fe13-543">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="1fe13-544">Beosztás típusa</span><span class="sxs-lookup"><span data-stu-id="1fe13-544">Position type</span></span>   | <span data-ttu-id="1fe13-545">Leírás</span><span class="sxs-lookup"><span data-stu-id="1fe13-545">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="1fe13-546">Teljes munkaidős</span><span class="sxs-lookup"><span data-stu-id="1fe13-546">Full-time</span></span>       | <span data-ttu-id="1fe13-547">Teljes munkaidős alkalmazott</span><span class="sxs-lookup"><span data-stu-id="1fe13-547">Full time employee</span></span> |
| <span data-ttu-id="1fe13-548">Részmunkaidős</span><span class="sxs-lookup"><span data-stu-id="1fe13-548">Part-time</span></span>       | <span data-ttu-id="1fe13-549">Részmunkaidős alkalmazott</span><span class="sxs-lookup"><span data-stu-id="1fe13-549">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="1fe13-550">Okkódok</span><span class="sxs-lookup"><span data-stu-id="1fe13-550">Reason codes</span></span>

<span data-ttu-id="1fe13-551">Az alkalmazottak állapotával kapcsolatos okkódok tájékoztatnak.</span><span class="sxs-lookup"><span data-stu-id="1fe13-551">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="1fe13-552">Okkódok a Dayforce-hoz állapot okaként vannak hozzárendelve, melyek jelzik egy alkalmazott beosztásában vagy alkalmazotti státuszában bekövetkezett változások okát.</span><span class="sxs-lookup"><span data-stu-id="1fe13-552">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="1fe13-553">A következő okkódok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="1fe13-553">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="1fe13-554">Okkód</span><span class="sxs-lookup"><span data-stu-id="1fe13-554">Reason code</span></span>            | <span data-ttu-id="1fe13-555">Leírás</span><span class="sxs-lookup"><span data-stu-id="1fe13-555">Description</span></span>                    | <span data-ttu-id="1fe13-556">Alkalmazandó forgatókönyvek</span><span class="sxs-lookup"><span data-stu-id="1fe13-556">Applicable scenarios</span></span> |
|------------------------|--------------------------------|----------------------|
| <span data-ttu-id="1fe13-557">DEPARTUREBEFOREPAYMENT</span><span class="sxs-lookup"><span data-stu-id="1fe13-557">DEPARTUREBEFOREPAYMENT</span></span> | <span data-ttu-id="1fe13-558">Indulás első bérlista előtt</span><span class="sxs-lookup"><span data-stu-id="1fe13-558">Departure before first payroll</span></span> | <span data-ttu-id="1fe13-559">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="1fe13-559">Terminate worker</span></span>     |
| <span data-ttu-id="1fe13-560">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="1fe13-560">RESIGNATION</span></span>            | <span data-ttu-id="1fe13-561">Felmondás</span><span class="sxs-lookup"><span data-stu-id="1fe13-561">Resignation</span></span>                    | <span data-ttu-id="1fe13-562">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="1fe13-562">Terminate worker</span></span>     |
| <span data-ttu-id="1fe13-563">PENSION</span><span class="sxs-lookup"><span data-stu-id="1fe13-563">PENSION</span></span>                | <span data-ttu-id="1fe13-564">Nyugdíj</span><span class="sxs-lookup"><span data-stu-id="1fe13-564">Pension</span></span>                        | <span data-ttu-id="1fe13-565">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="1fe13-565">Terminate worker</span></span>     |
| <span data-ttu-id="1fe13-566">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="1fe13-566">TERMINATION</span></span>            | <span data-ttu-id="1fe13-567">Befejezés</span><span class="sxs-lookup"><span data-stu-id="1fe13-567">Termination</span></span>                    | <span data-ttu-id="1fe13-568">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="1fe13-568">Terminate worker</span></span>     |
| <span data-ttu-id="1fe13-569">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="1fe13-569">RETIREMENT</span></span>             | <span data-ttu-id="1fe13-570">Megszüntetés</span><span class="sxs-lookup"><span data-stu-id="1fe13-570">Retirement</span></span>                     | <span data-ttu-id="1fe13-571">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="1fe13-571">Terminate worker</span></span>     |
| <span data-ttu-id="1fe13-572">ABSENTEE</span><span class="sxs-lookup"><span data-stu-id="1fe13-572">ABSENTEE</span></span>               | <span data-ttu-id="1fe13-573">Távollevő</span><span class="sxs-lookup"><span data-stu-id="1fe13-573">Absentee</span></span>                       | <span data-ttu-id="1fe13-574">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="1fe13-574">Terminate worker</span></span>     |
| <span data-ttu-id="1fe13-575">EGYÉB</span><span class="sxs-lookup"><span data-stu-id="1fe13-575">OTHER</span></span>                  | <span data-ttu-id="1fe13-576">Egyéb okok</span><span class="sxs-lookup"><span data-stu-id="1fe13-576">Other Reasons</span></span>                  | <span data-ttu-id="1fe13-577">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="1fe13-577">Terminate worker</span></span>     |
| <span data-ttu-id="1fe13-578">CLOSURE</span><span class="sxs-lookup"><span data-stu-id="1fe13-578">CLOSURE</span></span>                | <span data-ttu-id="1fe13-579">Üzletzárás</span><span class="sxs-lookup"><span data-stu-id="1fe13-579">Business Closure</span></span>               | <span data-ttu-id="1fe13-580">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="1fe13-580">Terminate worker</span></span>     |
| <span data-ttu-id="1fe13-581">DEATH</span><span class="sxs-lookup"><span data-stu-id="1fe13-581">DEATH</span></span>                  | <span data-ttu-id="1fe13-582">Elhalálozás</span><span class="sxs-lookup"><span data-stu-id="1fe13-582">Death</span></span>                          | <span data-ttu-id="1fe13-583">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="1fe13-583">Terminate worker</span></span>     |
| <span data-ttu-id="1fe13-584">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="1fe13-584">LEAVEOFABSENCE</span></span>         | <span data-ttu-id="1fe13-585">Szabadság</span><span class="sxs-lookup"><span data-stu-id="1fe13-585">Leave of Absence</span></span>               | <span data-ttu-id="1fe13-586">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="1fe13-586">Terminate worker</span></span>     |
| <span data-ttu-id="1fe13-587">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="1fe13-587">CONTRACTEND</span></span>            | <span data-ttu-id="1fe13-588">Szerződés vége</span><span class="sxs-lookup"><span data-stu-id="1fe13-588">End of Contract</span></span>                | <span data-ttu-id="1fe13-589">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="1fe13-589">Terminate worker</span></span>     |
| <span data-ttu-id="1fe13-590">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="1fe13-590">SALARYCHANGE</span></span>           | <span data-ttu-id="1fe13-591">Munkabér módosítása</span><span class="sxs-lookup"><span data-stu-id="1fe13-591">Change of Salary</span></span>               | <span data-ttu-id="1fe13-592">Kompenzáció</span><span class="sxs-lookup"><span data-stu-id="1fe13-592">Compensation</span></span>         |

### <a name="terms-of-employment"></a><span data-ttu-id="1fe13-593">Foglalkoztatási feltételek</span><span class="sxs-lookup"><span data-stu-id="1fe13-593">Terms of employment</span></span>

<span data-ttu-id="1fe13-594">A Foglalkoztatási feltételek foglalkoztatási feltételkategóriák létrehozására használatosak.</span><span class="sxs-lookup"><span data-stu-id="1fe13-594">Terms of employment are used to create categories of employment terms.</span></span> <span data-ttu-id="1fe13-595">A feltételek alkalmazási mutató értékekként vannak a Dayforce-hoz rendelve.</span><span class="sxs-lookup"><span data-stu-id="1fe13-595">The terms are mapped to Dayforce as employment indicator values.</span></span>

<span data-ttu-id="1fe13-596">A következő alkalmazási feltételek és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="1fe13-596">The following terms of employment and descriptions are required.</span></span>

| <span data-ttu-id="1fe13-597">Foglalkoztatási feltételek</span><span class="sxs-lookup"><span data-stu-id="1fe13-597">Terms of employment</span></span>   | <span data-ttu-id="1fe13-598">Leírás</span><span class="sxs-lookup"><span data-stu-id="1fe13-598">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="1fe13-599">Szabályos</span><span class="sxs-lookup"><span data-stu-id="1fe13-599">Regular</span></span>               | <span data-ttu-id="1fe13-600">Szabályos</span><span class="sxs-lookup"><span data-stu-id="1fe13-600">Regular</span></span>     |
| <span data-ttu-id="1fe13-601">Közvetlen</span><span class="sxs-lookup"><span data-stu-id="1fe13-601">Direct</span></span>                | <span data-ttu-id="1fe13-602">Közvetlen</span><span class="sxs-lookup"><span data-stu-id="1fe13-602">Direct</span></span>      |
| <span data-ttu-id="1fe13-603">Szakmai gyakorlat</span><span class="sxs-lookup"><span data-stu-id="1fe13-603">Internship</span></span>            | <span data-ttu-id="1fe13-604">Szakmai gyakorlat</span><span class="sxs-lookup"><span data-stu-id="1fe13-604">Internship</span></span>  |
| <span data-ttu-id="1fe13-605">Állandó</span><span class="sxs-lookup"><span data-stu-id="1fe13-605">Permanent</span></span>             | <span data-ttu-id="1fe13-606">Állandó</span><span class="sxs-lookup"><span data-stu-id="1fe13-606">Permanent</span></span>   |

### <a name="marital-status"></a><span data-ttu-id="1fe13-607">Családi állapot</span><span class="sxs-lookup"><span data-stu-id="1fe13-607">Marital status</span></span>

<span data-ttu-id="1fe13-608">Családi állapot értékei Dayforce-hoz vannak rendelve és konvertálva szükség esetén az elfogadható értékekre az integráció során.</span><span class="sxs-lookup"><span data-stu-id="1fe13-608">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="1fe13-609">Az alábbi táblázat bemutatja, hogy családi állapot értékek hogyan vannak leképezve a Dayforce -ban.</span><span class="sxs-lookup"><span data-stu-id="1fe13-609">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="1fe13-610">Talent</span><span class="sxs-lookup"><span data-stu-id="1fe13-610">Talent</span></span>                 | <span data-ttu-id="1fe13-611">Dayforce</span><span class="sxs-lookup"><span data-stu-id="1fe13-611">Dayforce</span></span>                  |
|------------------------|---------------------------|
| <span data-ttu-id="1fe13-612">Házas</span><span class="sxs-lookup"><span data-stu-id="1fe13-612">Married</span></span>                | <span data-ttu-id="1fe13-613">Házas</span><span class="sxs-lookup"><span data-stu-id="1fe13-613">Married</span></span>                   |
| <span data-ttu-id="1fe13-614">Egy</span><span class="sxs-lookup"><span data-stu-id="1fe13-614">Single</span></span>                 | <span data-ttu-id="1fe13-615">Egy</span><span class="sxs-lookup"><span data-stu-id="1fe13-615">Single</span></span>                    |
| <span data-ttu-id="1fe13-616">Özvegy</span><span class="sxs-lookup"><span data-stu-id="1fe13-616">Widowed</span></span>                | <span data-ttu-id="1fe13-617">Özvegy</span><span class="sxs-lookup"><span data-stu-id="1fe13-617">Widowed</span></span>                   |
| <span data-ttu-id="1fe13-618">Elvált</span><span class="sxs-lookup"><span data-stu-id="1fe13-618">Divorced</span></span>               | <span data-ttu-id="1fe13-619">Elvált</span><span class="sxs-lookup"><span data-stu-id="1fe13-619">Divorced</span></span>                  |
| <span data-ttu-id="1fe13-620">Bejegyzett élettársi kapcsolat</span><span class="sxs-lookup"><span data-stu-id="1fe13-620">Registered Partnership</span></span> | <span data-ttu-id="1fe13-621">Élettársi viszony</span><span class="sxs-lookup"><span data-stu-id="1fe13-621">Domestic Partnership</span></span>      |
| <span data-ttu-id="1fe13-622">Nincs</span><span class="sxs-lookup"><span data-stu-id="1fe13-622">None</span></span>                   | <span data-ttu-id="1fe13-623">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="1fe13-623">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="1fe13-624">Együttélés</span><span class="sxs-lookup"><span data-stu-id="1fe13-624">Cohabiting</span></span>             | <span data-ttu-id="1fe13-625">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="1fe13-625">*Not supported by Mexico*</span></span> |

### <a name="gender"></a><span data-ttu-id="1fe13-626">Nem</span><span class="sxs-lookup"><span data-stu-id="1fe13-626">Gender</span></span>

<span data-ttu-id="1fe13-627">A nemek a Dayforce-hoz vannak rendelve és konvertálva szükség esetén az elfogadható értékekre az integráció során.</span><span class="sxs-lookup"><span data-stu-id="1fe13-627">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="1fe13-628">Az alábbi táblázat bemutatja, hogy a nemek hogyan vannak leképezve a Dayforce-ban.</span><span class="sxs-lookup"><span data-stu-id="1fe13-628">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="1fe13-629">Talent</span><span class="sxs-lookup"><span data-stu-id="1fe13-629">Talent</span></span>       | <span data-ttu-id="1fe13-630">Dayforce</span><span class="sxs-lookup"><span data-stu-id="1fe13-630">Dayforce</span></span>                  |
|--------------|---------------------------|
| <span data-ttu-id="1fe13-631">Férfi</span><span class="sxs-lookup"><span data-stu-id="1fe13-631">Male</span></span>         | <span data-ttu-id="1fe13-632">Férfi</span><span class="sxs-lookup"><span data-stu-id="1fe13-632">Male</span></span>                      |
| <span data-ttu-id="1fe13-633">Nő</span><span class="sxs-lookup"><span data-stu-id="1fe13-633">Female</span></span>       | <span data-ttu-id="1fe13-634">Nő</span><span class="sxs-lookup"><span data-stu-id="1fe13-634">Female</span></span>                    |
| <span data-ttu-id="1fe13-635">Nem meghatározott</span><span class="sxs-lookup"><span data-stu-id="1fe13-635">Non-specific</span></span> | <span data-ttu-id="1fe13-636">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="1fe13-636">*Not supported by Mexico*</span></span> |

### <a name="payment-method"></a><span data-ttu-id="1fe13-637">Kifizetési mód</span><span class="sxs-lookup"><span data-stu-id="1fe13-637">Payment method</span></span>

<span data-ttu-id="1fe13-638">A Fizetési módok adják meg az alkalmazott és a vállalat számára az alkalmazott kifizetésének módja leírásának lehetőségét.</span><span class="sxs-lookup"><span data-stu-id="1fe13-638">Payment methods give the employee and the company a way to describe how employees will be paid.</span></span> <span data-ttu-id="1fe13-639">A Fizetési módok a Dayforce-hoz vannak rendelve és konvertálva szükség esetén az elfogadható értékekre az integráció során.</span><span class="sxs-lookup"><span data-stu-id="1fe13-639">Payment methods are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="1fe13-640">Az alábbi táblázat bemutatja, hogy a fizetés módok hogyan vannak leképezve a Dayforce-ban.</span><span class="sxs-lookup"><span data-stu-id="1fe13-640">The following table shows how payment methods are mapped to Dayforce.</span></span>

| <span data-ttu-id="1fe13-641">Talent</span><span class="sxs-lookup"><span data-stu-id="1fe13-641">Talent</span></span>             | <span data-ttu-id="1fe13-642">Dayforce</span><span class="sxs-lookup"><span data-stu-id="1fe13-642">Dayforce</span></span>                  |
|--------------------|---------------------------|
| <span data-ttu-id="1fe13-643">Készpénz</span><span class="sxs-lookup"><span data-stu-id="1fe13-643">Cash</span></span>               | <span data-ttu-id="1fe13-644">Készpénz</span><span class="sxs-lookup"><span data-stu-id="1fe13-644">Cash</span></span>                      |
| <span data-ttu-id="1fe13-645">Elektronikus fizetés</span><span class="sxs-lookup"><span data-stu-id="1fe13-645">Electronic Payment</span></span> | <span data-ttu-id="1fe13-646">Átvitel</span><span class="sxs-lookup"><span data-stu-id="1fe13-646">Transfer</span></span>                  |
| <span data-ttu-id="1fe13-647">Csekkes</span><span class="sxs-lookup"><span data-stu-id="1fe13-647">Check</span></span>              | <span data-ttu-id="1fe13-648">Csekk</span><span class="sxs-lookup"><span data-stu-id="1fe13-648">Cheque</span></span>                    |
| <span data-ttu-id="1fe13-649">Váltó</span><span class="sxs-lookup"><span data-stu-id="1fe13-649">Bank Draft</span></span>         | <span data-ttu-id="1fe13-650">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="1fe13-650">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="1fe13-651">Egyéb</span><span class="sxs-lookup"><span data-stu-id="1fe13-651">Other</span></span>              | <span data-ttu-id="1fe13-652">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="1fe13-652">*Not supported by Mexico*</span></span> |

### <a name="bank-account-type"></a><span data-ttu-id="1fe13-653">Bankszámla típusa</span><span class="sxs-lookup"><span data-stu-id="1fe13-653">Bank account type</span></span>

<span data-ttu-id="1fe13-654">Bankszámla-típusok az alkalmazottaknak történő elektronikus kifizetésekhez szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="1fe13-654">Bank account types are used for electronic payments to employees.</span></span> <span data-ttu-id="1fe13-655">Bankszámla típusa a Dayforce-ba átutalási számlaadatként van rendelve.</span><span class="sxs-lookup"><span data-stu-id="1fe13-655">Bank account types are mapped to Dayforce as transfer account information.</span></span> <span data-ttu-id="1fe13-656">A bankszámlatípusok szükség esetén konvertálva vannak az elfogadható értékekké az integráció során.</span><span class="sxs-lookup"><span data-stu-id="1fe13-656">The bank account types are translated, as appropriate, to the accepted values upon integration.</span></span>

| <span data-ttu-id="1fe13-657">Talent</span><span class="sxs-lookup"><span data-stu-id="1fe13-657">Talent</span></span>            | <span data-ttu-id="1fe13-658">Dayforce</span><span class="sxs-lookup"><span data-stu-id="1fe13-658">Dayforce</span></span>                  |
|-------------------|---------------------------|
| <span data-ttu-id="1fe13-659">Folyószámla</span><span class="sxs-lookup"><span data-stu-id="1fe13-659">Checking Account</span></span>  | <span data-ttu-id="1fe13-660">CheckingAccount</span><span class="sxs-lookup"><span data-stu-id="1fe13-660">CheckingAccount</span></span>           |
| <span data-ttu-id="1fe13-661">Bérlista elszámolási számlája</span><span class="sxs-lookup"><span data-stu-id="1fe13-661">Payroll Account</span></span>   | <span data-ttu-id="1fe13-662">PayrollAccount</span><span class="sxs-lookup"><span data-stu-id="1fe13-662">PayrollAccount</span></span>            |
| <span data-ttu-id="1fe13-663">Megtakarítási számla</span><span class="sxs-lookup"><span data-stu-id="1fe13-663">Savings Account</span></span>   | <span data-ttu-id="1fe13-664">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="1fe13-664">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="1fe13-665">BankGirot-számla</span><span class="sxs-lookup"><span data-stu-id="1fe13-665">BankGirot account</span></span> | <span data-ttu-id="1fe13-666">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="1fe13-666">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="1fe13-667">PlusGirot-számla</span><span class="sxs-lookup"><span data-stu-id="1fe13-667">PlusGirot account</span></span> | <span data-ttu-id="1fe13-668">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="1fe13-668">*Not supported by Mexico*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="1fe13-669">Bevételkódok</span><span class="sxs-lookup"><span data-stu-id="1fe13-669">Earning codes</span></span>

<span data-ttu-id="1fe13-670">A bevételkódok egyedi módon azonosítják a dolgozók által kapott fizetéstípusokat.</span><span class="sxs-lookup"><span data-stu-id="1fe13-670">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="1fe13-671">A kódoknak különböző paramétereket fednek le, amelyek a bevételekhez kapcsolódnak, például könyvelési szabályok, jelentési követelmények és bruttósítási lehetőségek.</span><span class="sxs-lookup"><span data-stu-id="1fe13-671">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="1fe13-672">Ha egy nem támogatott gyakoriság van használatban, a **Minden fizetés** gyakorisága van alapértelmezés szerint használva a kiszámításhoz.</span><span class="sxs-lookup"><span data-stu-id="1fe13-672">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="1fe13-673">Támogatott gyakoriságok</span><span class="sxs-lookup"><span data-stu-id="1fe13-673">Supported frequencies</span></span>

- <span data-ttu-id="1fe13-674">Összes</span><span class="sxs-lookup"><span data-stu-id="1fe13-674">All</span></span>
- <span data-ttu-id="1fe13-675">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="1fe13-675">EVERYPAY</span></span>
- <span data-ttu-id="1fe13-676">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="1fe13-676">EACHPAYPERIOD</span></span>
- <span data-ttu-id="1fe13-677">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="1fe13-677">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="1fe13-678">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="1fe13-678">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="1fe13-679">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="1fe13-679">1OFMTH</span></span>
- <span data-ttu-id="1fe13-680">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="1fe13-680">LASTOFMTH</span></span>
- <span data-ttu-id="1fe13-681">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="1fe13-681">2OFMTH</span></span>
- <span data-ttu-id="1fe13-682">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="1fe13-682">3OFMTH</span></span>
- <span data-ttu-id="1fe13-683">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="1fe13-683">4OFMTH</span></span>
- <span data-ttu-id="1fe13-684">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="1fe13-684">5OFMTH</span></span>
- <span data-ttu-id="1fe13-685">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="1fe13-685">1N2OFMTH</span></span>
- <span data-ttu-id="1fe13-686">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="1fe13-686">3N4OFMTH</span></span>
- <span data-ttu-id="1fe13-687">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="1fe13-687">1N3OFMTH</span></span>
- <span data-ttu-id="1fe13-688">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="1fe13-688">1N4OFMTH</span></span>
- <span data-ttu-id="1fe13-689">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="1fe13-689">2N3OFMTH</span></span>
- <span data-ttu-id="1fe13-690">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="1fe13-690">2N4OFMTH</span></span>
- <span data-ttu-id="1fe13-691">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="1fe13-691">1N2N3OFMTH</span></span>
- <span data-ttu-id="1fe13-692">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="1fe13-692">1N2N4OFMTH</span></span>
- <span data-ttu-id="1fe13-693">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="1fe13-693">1N3N4OFMTH</span></span>
- <span data-ttu-id="1fe13-694">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="1fe13-694">2N3N4OFMTH</span></span>
- <span data-ttu-id="1fe13-695">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="1fe13-695">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="1fe13-696">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="1fe13-696">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="1fe13-697">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="1fe13-697">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="1fe13-698">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="1fe13-698">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="1fe13-699">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="1fe13-699">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="1fe13-700">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="1fe13-700">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="1fe13-701">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="1fe13-701">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="1fe13-702">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="1fe13-702">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="1fe13-703">Címek</span><span class="sxs-lookup"><span data-stu-id="1fe13-703">Addresses</span></span>

<span data-ttu-id="1fe13-704">Az adott ország vagy régió, állam és megye (település) kódok specifikus formátumokat követelnek, hogy Dayforce és az országos és regionális szolgáltatók felismerjék azokat.</span><span class="sxs-lookup"><span data-stu-id="1fe13-704">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="1fe13-705">Annak ellenére, hogy a városok formátuma rugalmas, minden városnak társítva kell lennie egy államhoz.</span><span class="sxs-lookup"><span data-stu-id="1fe13-705">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="1fe13-706">Talent</span><span class="sxs-lookup"><span data-stu-id="1fe13-706">Talent</span></span>              | <span data-ttu-id="1fe13-707">Dayforce</span><span class="sxs-lookup"><span data-stu-id="1fe13-707">Dayforce</span></span>              |
|---------------------|-----------------------|
| <span data-ttu-id="1fe13-708">Ország/régió</span><span class="sxs-lookup"><span data-stu-id="1fe13-708">Country/Region</span></span>      | <span data-ttu-id="1fe13-709">Országkód</span><span class="sxs-lookup"><span data-stu-id="1fe13-709">Country Code</span></span>          |
| <span data-ttu-id="1fe13-710">Irányítószám / postai kód</span><span class="sxs-lookup"><span data-stu-id="1fe13-710">Zip/Postal Code</span></span>     | <span data-ttu-id="1fe13-711">Irányítószám</span><span class="sxs-lookup"><span data-stu-id="1fe13-711">Postal Code</span></span>           |
| <span data-ttu-id="1fe13-712">Állami</span><span class="sxs-lookup"><span data-stu-id="1fe13-712">State</span></span>               | <span data-ttu-id="1fe13-713">Államkód</span><span class="sxs-lookup"><span data-stu-id="1fe13-713">State Code</span></span>            |
| <span data-ttu-id="1fe13-714">Város</span><span class="sxs-lookup"><span data-stu-id="1fe13-714">City</span></span>                | <span data-ttu-id="1fe13-715">Város</span><span class="sxs-lookup"><span data-stu-id="1fe13-715">City</span></span>                  |
| <span data-ttu-id="1fe13-716">Megye</span><span class="sxs-lookup"><span data-stu-id="1fe13-716">County</span></span>              | <span data-ttu-id="1fe13-717">Megye (Helyhatóság)</span><span class="sxs-lookup"><span data-stu-id="1fe13-717">County (Municipality)</span></span> |
| <span data-ttu-id="1fe13-718">Utca</span><span class="sxs-lookup"><span data-stu-id="1fe13-718">Street</span></span>              | <span data-ttu-id="1fe13-719">Cím 1. sora</span><span class="sxs-lookup"><span data-stu-id="1fe13-719">Address Line 1</span></span>        |
| <span data-ttu-id="1fe13-720">Utca, házszám</span><span class="sxs-lookup"><span data-stu-id="1fe13-720">Street Number</span></span>       | <span data-ttu-id="1fe13-721">Cím 2. sora</span><span class="sxs-lookup"><span data-stu-id="1fe13-721">Address Line 2</span></span>        |
| <span data-ttu-id="1fe13-722">Épületblokk</span><span class="sxs-lookup"><span data-stu-id="1fe13-722">Building Complement</span></span> | <span data-ttu-id="1fe13-723">Cím 5. sora</span><span class="sxs-lookup"><span data-stu-id="1fe13-723">Address Line 5</span></span>        |

### <a name="passport-number"></a><span data-ttu-id="1fe13-724">Útlevél száma</span><span class="sxs-lookup"><span data-stu-id="1fe13-724">Passport number</span></span>

<span data-ttu-id="1fe13-725">Az alkalmazottak útlevél adatokat is nyilatkozhatnak.</span><span class="sxs-lookup"><span data-stu-id="1fe13-725">Employees can declare passport information.</span></span> <span data-ttu-id="1fe13-726">Az információ a **Útlevél** azonosítótípusra vonatkozik, és az alkalmazott Mexikó-specifikus adataiként van a Dayforce-ba integrálva.</span><span class="sxs-lookup"><span data-stu-id="1fe13-726">This information is of the **Passport** identification type and is integrated into Dayforce as part of an employee's Mexico-specific information.</span></span>

- <span data-ttu-id="1fe13-727">Azonosító típusa = „Útlevél”</span><span class="sxs-lookup"><span data-stu-id="1fe13-727">Identification Type = "Passport"</span></span>
- <span data-ttu-id="1fe13-728">Kibocsátás dátuma</span><span class="sxs-lookup"><span data-stu-id="1fe13-728">Issued Date</span></span>
- <span data-ttu-id="1fe13-729">Lejárat dátuma</span><span class="sxs-lookup"><span data-stu-id="1fe13-729">Expiration Date</span></span>

<span data-ttu-id="1fe13-730">Az alkalmazottak több azonosítószámot is megadhatnak az **Útlevél** azonosítótípushoz.</span><span class="sxs-lookup"><span data-stu-id="1fe13-730">Employees can declare multiple identification numbers of the **Passport** identification type.</span></span> <span data-ttu-id="1fe13-731">Azonban csak az aktuális aktív útlevélbejegyzés van integrálva a Dayforce-ba.</span><span class="sxs-lookup"><span data-stu-id="1fe13-731">However, only the current active passport entry is integrated into Dayforce.</span></span> <span data-ttu-id="1fe13-732">Ha az összes útlevélbejegyzés lejárt, a legutóbb kiállított lesz integrálva a Dayforce-ba.</span><span class="sxs-lookup"><span data-stu-id="1fe13-732">If all passport entries are expired, the passport that was most recently issued is integrated into Dayforce.</span></span>
