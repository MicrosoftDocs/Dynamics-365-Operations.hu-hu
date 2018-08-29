---
title: "Bérlista-integráció konfigurálása a Talnet és a Dayforce közötti"
description: "Ez a témakör bemutatja, hogyan kell konfigurálni az integrációt a Microsoft Dynamics 365 for Talent és a Ceridian Dayforce között úgy, hogy fel lehessen dolgozni fizetési időszakot.."
author: jcart1106
manager: AnnBe
ms.date: 07/10/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: 82f039b305503c604d64610f39838fa86a8eb08a
ms.openlocfilehash: fcddf82cffb9f0ba94b83eb21809b810585ebc9e
ms.contentlocale: hu-hu
ms.lasthandoff: 08/09/2018

---

# <a name="configure-the-payroll-integration-between-talent-and-dayforce"></a><span data-ttu-id="af1a3-103">Bérlista-integráció konfigurálása a Talnet és a Dayforce közötti</span><span class="sxs-lookup"><span data-stu-id="af1a3-103">Configure the payroll integration between Talent and Dayforce</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="af1a3-104">A Microsoft Dynamics 365 Talent és Ceridian Dayforce integrálásához több konfigurációs lépést szükséges elvégezni, melyek ebben a témakörben vannak ismertetve.</span><span class="sxs-lookup"><span data-stu-id="af1a3-104">The integration between Microsoft Dynamics 365 for Talent and Ceridian Dayforce relies on several configuration steps that are described in this topic.</span></span> <span data-ttu-id="af1a3-105">Be kell állítania az integrációt a Talent a Dayforce alkalmazásokban is a fizetési időszak feldolgozása előtt.</span><span class="sxs-lookup"><span data-stu-id="af1a3-105">You must configure the integration in both Talent and Dayforce before you can process a pay run.</span></span>

<span data-ttu-id="af1a3-106">Ha olyan szolgáltatást használ a fizetési időszakokhoz, mint a Dayforce, engedélyeznie kell az integrációt a Talentben.</span><span class="sxs-lookup"><span data-stu-id="af1a3-106">When you use a service such as Dayforce to complete pay runs, you must enable the integration in Talent.</span></span> <span data-ttu-id="af1a3-107">Az integrációhoz meghatározott adatok szükségesek a Talentből.</span><span class="sxs-lookup"><span data-stu-id="af1a3-107">The integration requires specific data from Talent.</span></span> <span data-ttu-id="af1a3-108">Ezért ellenőriznie kell, hogy a Dayforce-ban hozzárendelt adatok olyan módon vannak konfigurálva a Talentben, hogy az támogassa az integrációt.</span><span class="sxs-lookup"><span data-stu-id="af1a3-108">Therefore, you must verify that data that is mapped to Dayforce is configured in Talent in a manner that supports the integration.</span></span> <span data-ttu-id="af1a3-109">Az integráció a következő szélesebb adatkategóriákat használja:</span><span class="sxs-lookup"><span data-stu-id="af1a3-109">The integration uses the following broad categories of data:</span></span>

- <span data-ttu-id="af1a3-110">Emberierőforrás-adatok</span><span class="sxs-lookup"><span data-stu-id="af1a3-110">Human resources data</span></span>
- <span data-ttu-id="af1a3-111">Kompenzációadatok</span><span class="sxs-lookup"><span data-stu-id="af1a3-111">Compensation data</span></span>
- <span data-ttu-id="af1a3-112">Bérlistaadatok, mint kifizetési ciklus, fizetési időszakok és bevételkódok</span><span class="sxs-lookup"><span data-stu-id="af1a3-112">Payroll data, such as pay cycles, pay periods, and earning codes</span></span>
- <span data-ttu-id="af1a3-113">Dolgozóadatok</span><span class="sxs-lookup"><span data-stu-id="af1a3-113">Worker data</span></span>

<span data-ttu-id="af1a3-114">Ez a témakör leírja a lépéseket, amelyeket követni kell az integráció engedélyezéséhez.</span><span class="sxs-lookup"><span data-stu-id="af1a3-114">This topic describes the steps that you must follow to enable the integration.</span></span> <span data-ttu-id="af1a3-115">Azt is bemutatja, hogy milyen típusú adatok és konfiguráció szükséges az integrációhoz.</span><span class="sxs-lookup"><span data-stu-id="af1a3-115">It also explains the types of data and the configuration details that the integration requires.</span></span>

## <a name="enable-the-integration"></a><span data-ttu-id="af1a3-116">Engedélyezze az integrációt</span><span class="sxs-lookup"><span data-stu-id="af1a3-116">Enable the integration</span></span>

<span data-ttu-id="af1a3-117">A Talentben be kell kapcsolja a műveletek integrációját, meg kell adnia a konfiguráció adatait, hogy tudjon a Dayforcehoz csatlakozni.</span><span class="sxs-lookup"><span data-stu-id="af1a3-117">In Talent, you must turn on the integration and enter the configuration information to connect to Dayforce.</span></span> <span data-ttu-id="af1a3-118">Ha azt szeretné, hogy a létrehozott általános főkönyvi tranzakció importálva legyen a Microsoft Dynamics 365 for Finance and Operations alkalmazásba, be kell állítania egy Microsoft Azure tárolási fiókot, majd adja meg, majd Azure tárolási kapcsolat karakterláncát a Finance and Operations alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="af1a3-118">If you want the general ledger transaction that is produced to be imported into Microsoft Dynamics 365 for Finance and Operations, you must also set up a Microsoft Azure storage account and enter the Azure Storage connection string in Finance and Operations.</span></span>

<span data-ttu-id="af1a3-119">Az integráció engedélyezéséhez a Talentben kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="af1a3-119">To turn on the integration in Talent, follow these steps.</span></span>

1. <span data-ttu-id="af1a3-120">A **Rendszerfelügyelet** oldalon válassza az **Integrációkonfiguráció** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="af1a3-120">On the **System administration** page, select **Integration configuration**.</span></span>
2. <span data-ttu-id="af1a3-121">Adja meg a biztonságos fájl átviteli protokollt (FTP) végpontot és a biztonságos FTP-mappa elérési útja.</span><span class="sxs-lookup"><span data-stu-id="af1a3-121">Enter the secure File Transfer Protocol (FTP) endpoint and the secure FTP folder path.</span></span>
3. <span data-ttu-id="af1a3-122">Adja meg azon felhasználó felhasználónevét és jelszavát, aki hozzáfér a biztonságos FTP végponthoz és a mappa elérési útjához.</span><span class="sxs-lookup"><span data-stu-id="af1a3-122">Enter the user name and password of the user who will access the secure FTP endpoint and folder path.</span></span>
4. <span data-ttu-id="af1a3-123">Tesztelje a kapcsolatot szükség szerint, és állítsa a **Bérlista-integráció engedélyezése** lehetőséggel **Igenre**.</span><span class="sxs-lookup"><span data-stu-id="af1a3-123">Test the connection, as required, and set the **Enable payroll integration** option to **Yes**.</span></span>

<span data-ttu-id="af1a3-124">Ha az integráció engedélyezve van, adatexport adatcsomagok és fájlok jönnek létre, valamint a gyakoriság is be van állítva.</span><span class="sxs-lookup"><span data-stu-id="af1a3-124">When the integration is turned on, the data export package and files are created, and the frequency is set.</span></span> <span data-ttu-id="af1a3-125">Igény szerint módosíthatja a gyakoriságot.</span><span class="sxs-lookup"><span data-stu-id="af1a3-125">You can change this frequency as you require.</span></span>

<span data-ttu-id="af1a3-126">Azure tárolási fiókokkal és Azure tárolási kapcsolati karakterláncokat kapcsolatos további információt az alábbi Azure-témakörökben találja:</span><span class="sxs-lookup"><span data-stu-id="af1a3-126">For more information about Azure storage accounts and Azure Storage connection strings, see the following Azure topics:</span></span>

- [<span data-ttu-id="af1a3-127">Az Azure Storage-fiókokról</span><span class="sxs-lookup"><span data-stu-id="af1a3-127">About Azure storage accounts</span></span>](https://docs.microsoft.com/en-us/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [<span data-ttu-id="af1a3-128">Azure Storage kapcsolati karakterláncok konfigurálása</span><span class="sxs-lookup"><span data-stu-id="af1a3-128">Configure Azure Storage connection strings</span></span>](https://docs.microsoft.com/en-us/azure/storage/common/storage-configure-connection-string)

## <a name="configure-your-data"></a><span data-ttu-id="af1a3-129">Adatai konfigurálása</span><span class="sxs-lookup"><span data-stu-id="af1a3-129">Configure your data</span></span> 

<span data-ttu-id="af1a3-130">A bérlista feldolgozásához konfigurálnia kell az emberi erőforrás adatokat a Talentben.</span><span class="sxs-lookup"><span data-stu-id="af1a3-130">To process payroll, you must configure human resource data in Talent.</span></span> <span data-ttu-id="af1a3-131">Be kell állítani a szervezeti adatokat, például a feladatokat és beosztásokat, valamint juttatásokra és a kompenzációra vonatkozó adatokat.</span><span class="sxs-lookup"><span data-stu-id="af1a3-131">You must set up organizational data, such as jobs and positions, together with benefits and compensation information.</span></span> <span data-ttu-id="af1a3-132">Ez az információ megadja a foglalkoztatásra, fizetésre és levonásokra vonatkozó információkat, melyek szükségesek az alkalmazott fizetések generálásához.</span><span class="sxs-lookup"><span data-stu-id="af1a3-132">This information provides the employment, pay, and deduction information that is required in order to generate employee pay.</span></span>

### <a name="human-resource-data"></a><span data-ttu-id="af1a3-133">Emberierőforrás-adatok</span><span class="sxs-lookup"><span data-stu-id="af1a3-133">Human resource data</span></span>

#### <a name="benefits"></a><span data-ttu-id="af1a3-134">Juttatások</span><span class="sxs-lookup"><span data-stu-id="af1a3-134">Benefits</span></span> 

<span data-ttu-id="af1a3-135">Az emberi erőforrások számos beállítási és karbantartási eszközt biztosít, amelyek segítségével beállíthatja és karbantarthatja a szervezet által a dolgozónak biztosított juttatásokat, levonásokat és dolgozói kompenzációs terveket.</span><span class="sxs-lookup"><span data-stu-id="af1a3-135">Human resources provides tools for the setup and maintenance of the benefits, deductions, and worker compensation plans that an organization offers or processes for its workers.</span></span>

<span data-ttu-id="af1a3-136">Juttatások létrehozása esetén ne felejtse el a következő adatokat és beállításokat, amelyeket a Dayforce használ.</span><span class="sxs-lookup"><span data-stu-id="af1a3-136">When you create benefits, keep in mind the following data and configurations that are used in Dayforce.</span></span>

##### <a name="benefit-plans"></a><span data-ttu-id="af1a3-137">Juttatási tervek</span><span class="sxs-lookup"><span data-stu-id="af1a3-137">Benefit plans</span></span>

- <span data-ttu-id="af1a3-138">Terv (szükséges)</span><span class="sxs-lookup"><span data-stu-id="af1a3-138">Plan (required)</span></span>
- <span data-ttu-id="af1a3-139">Típus (szükséges)</span><span class="sxs-lookup"><span data-stu-id="af1a3-139">Type (required)</span></span>
- <span data-ttu-id="af1a3-140">Bérlista hatása (szükséges)</span><span class="sxs-lookup"><span data-stu-id="af1a3-140">Payroll impact (required)</span></span>
- <span data-ttu-id="af1a3-141">Hátralékok helyreállítása</span><span class="sxs-lookup"><span data-stu-id="af1a3-141">Recover arrears</span></span>
- <span data-ttu-id="af1a3-142">Levonási módszer</span><span class="sxs-lookup"><span data-stu-id="af1a3-142">Deduction method</span></span>
- <span data-ttu-id="af1a3-143">Levonás prioritása</span><span class="sxs-lookup"><span data-stu-id="af1a3-143">Deduction priority</span></span>
- <span data-ttu-id="af1a3-144">Időszak korlátozása</span><span class="sxs-lookup"><span data-stu-id="af1a3-144">Limit period</span></span>
- <span data-ttu-id="af1a3-145">Összeghatár</span><span class="sxs-lookup"><span data-stu-id="af1a3-145">Limit amount</span></span>

##### <a name="benefits"></a><span data-ttu-id="af1a3-146">Juttatások</span><span class="sxs-lookup"><span data-stu-id="af1a3-146">Benefits</span></span>

- <span data-ttu-id="af1a3-147">Terv (szükséges)</span><span class="sxs-lookup"><span data-stu-id="af1a3-147">Plan (required)</span></span>
- <span data-ttu-id="af1a3-148">Típus (szükséges)</span><span class="sxs-lookup"><span data-stu-id="af1a3-148">Type (required)</span></span>
- <span data-ttu-id="af1a3-149">Lehetőség (szükséges)</span><span class="sxs-lookup"><span data-stu-id="af1a3-149">Option (required)</span></span>
- <span data-ttu-id="af1a3-150">Juttatás azonosítója (szükséges)</span><span class="sxs-lookup"><span data-stu-id="af1a3-150">Benefit ID (required)</span></span>
- <span data-ttu-id="af1a3-151">Gyakoriság</span><span class="sxs-lookup"><span data-stu-id="af1a3-151">Frequency</span></span>
- <span data-ttu-id="af1a3-152">Alap</span><span class="sxs-lookup"><span data-stu-id="af1a3-152">Basis</span></span>
- <span data-ttu-id="af1a3-153">Összeg vagy mérték</span><span class="sxs-lookup"><span data-stu-id="af1a3-153">Amount or rate</span></span>
- <span data-ttu-id="af1a3-154">Bevételkód</span><span class="sxs-lookup"><span data-stu-id="af1a3-154">Earning code</span></span>

##### <a name="supported-frequencies"></a><span data-ttu-id="af1a3-155">Támogatott gyakoriságok</span><span class="sxs-lookup"><span data-stu-id="af1a3-155">Supported frequencies</span></span> 

- <span data-ttu-id="af1a3-156">Heti</span><span class="sxs-lookup"><span data-stu-id="af1a3-156">Weekly</span></span>
- <span data-ttu-id="af1a3-157">Kétheti</span><span class="sxs-lookup"><span data-stu-id="af1a3-157">Bi-weekly</span></span>
- <span data-ttu-id="af1a3-158">Félhavi</span><span class="sxs-lookup"><span data-stu-id="af1a3-158">Semi-monthly</span></span>
- <span data-ttu-id="af1a3-159">Havi</span><span class="sxs-lookup"><span data-stu-id="af1a3-159">Monthly</span></span>

##### <a name="supported-bases"></a><span data-ttu-id="af1a3-160">Támogatott alapok</span><span class="sxs-lookup"><span data-stu-id="af1a3-160">Supported bases</span></span> 

- <span data-ttu-id="af1a3-161">Rögzített összeg</span><span class="sxs-lookup"><span data-stu-id="af1a3-161">Fixed amount</span></span>
- <span data-ttu-id="af1a3-162">Bevételek százaléka</span><span class="sxs-lookup"><span data-stu-id="af1a3-162">Percent of earnings</span></span>
- <span data-ttu-id="af1a3-163">Produktív órák</span><span class="sxs-lookup"><span data-stu-id="af1a3-163">Productive hours</span></span>

<span data-ttu-id="af1a3-164">A Dayforce létrehozza a következő levonásokat, a juttatási tervben definiált bérlistahatás alapján.</span><span class="sxs-lookup"><span data-stu-id="af1a3-164">Dayforce creates the following deductions, based on the payroll impact that is defined on the benefit plan.</span></span>

| <span data-ttu-id="af1a3-165">Kiválasztás a Talentben</span><span class="sxs-lookup"><span data-stu-id="af1a3-165">Selection in Talent</span></span>        | <span data-ttu-id="af1a3-166">Eredmény a Dayforce-ban</span><span class="sxs-lookup"><span data-stu-id="af1a3-166">Result in Dayforce</span></span>                            |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="af1a3-167">Nincs</span><span class="sxs-lookup"><span data-stu-id="af1a3-167">None</span></span>                       | <span data-ttu-id="af1a3-168">Nincs létrehozva levonás.</span><span class="sxs-lookup"><span data-stu-id="af1a3-168">No deduction is created.</span></span>                      |
| <span data-ttu-id="af1a3-169">Csak levonás</span><span class="sxs-lookup"><span data-stu-id="af1a3-169">Deduction only</span></span>             | <span data-ttu-id="af1a3-170">Alkalmazotti levonás jön létre.</span><span class="sxs-lookup"><span data-stu-id="af1a3-170">An employee deduction is created.</span></span>             |
| <span data-ttu-id="af1a3-171">Csak hozzájárulás</span><span class="sxs-lookup"><span data-stu-id="af1a3-171">Contribution only</span></span>          | <span data-ttu-id="af1a3-172">Egy alkalmazotti levonás jön létre.</span><span class="sxs-lookup"><span data-stu-id="af1a3-172">An employer deduction is created.</span></span>             |
| <span data-ttu-id="af1a3-173">Levonás és hozzájárulás</span><span class="sxs-lookup"><span data-stu-id="af1a3-173">Deduction and contribution</span></span> | <span data-ttu-id="af1a3-174">Alkalmazotti és a munkáltatói levonások jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="af1a3-174">Employee and employer deductions are created.</span></span> |

<span data-ttu-id="af1a3-175">A juttatási programok definiálásával és kezelésével kapcsolatosan további tájékoztatás a következő témakörökben talál:</span><span class="sxs-lookup"><span data-stu-id="af1a3-175">For more information about how to define and manage a benefits program, see the following topics:</span></span>

- [<span data-ttu-id="af1a3-176">Alkalmazotti juttatási program megvalósítása</span><span class="sxs-lookup"><span data-stu-id="af1a3-176">Deliver an employee benefits program</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [<span data-ttu-id="af1a3-177">Új juttatás létrehozása</span><span class="sxs-lookup"><span data-stu-id="af1a3-177">Create a new benefit</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [<span data-ttu-id="af1a3-178">Juttatásra való jogosultsági szabályok és irányelvek meghatározása</span><span class="sxs-lookup"><span data-stu-id="af1a3-178">Define benefit eligibility rules and policies</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [<span data-ttu-id="af1a3-179">Dolgozók juttatásainak felvétele és eltávolítása</span><span class="sxs-lookup"><span data-stu-id="af1a3-179">Enroll and remove benefits from workers</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a><span data-ttu-id="af1a3-180">Kompenzáció</span><span class="sxs-lookup"><span data-stu-id="af1a3-180">Compensation</span></span> 

<span data-ttu-id="af1a3-181">A kompenzációkezeléssel szabályozható az alapfizetés és a jutalmak kifizetése.</span><span class="sxs-lookup"><span data-stu-id="af1a3-181">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="af1a3-182">Egy alkalmazott fix fizetési díjalapja és érdemeken alapuló fizetése kezelhető a fix kompenzációs tervekkel.</span><span class="sxs-lookup"><span data-stu-id="af1a3-182">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="af1a3-183">Az ösztönző díjak kifizetése, például bónuszok, teljesítménydíjak, részvényopciók és kölcsönök, továbbá az egyszeri jutalmak a változó kompenzációs tervekben szabályozhatók.</span><span class="sxs-lookup"><span data-stu-id="af1a3-183">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span>

<span data-ttu-id="af1a3-184">A Dayforce a kompenzációs adatok segítségével kiszámítja az alkalmazott óradíját vagy éves díját.</span><span class="sxs-lookup"><span data-stu-id="af1a3-184">Dayforce uses compensation information to calculate an employee's hourly or annual rate.</span></span> <span data-ttu-id="af1a3-185">Fix kompenzációs tervek és a fizetési díjalap átalakítások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="af1a3-185">Fixed compensation plans and pay rate conversions are required.</span></span> <span data-ttu-id="af1a3-186">Az alkalmazottakat hozzá kell rendelni a fix kompenzációs tervhez.</span><span class="sxs-lookup"><span data-stu-id="af1a3-186">Employees must be associated with a fixed compensation plan.</span></span>

<span data-ttu-id="af1a3-187">A következő témakörökben bővebben olvashat a kompenzációs tervekről:</span><span class="sxs-lookup"><span data-stu-id="af1a3-187">For more information about compensation plans, see the following topics:</span></span>

- [<span data-ttu-id="af1a3-188">Fix kompenzációs konstrukciók létrehozása</span><span class="sxs-lookup"><span data-stu-id="af1a3-188">Create fixed compensation plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [<span data-ttu-id="af1a3-189">Változó kompenzációs konstrukciók létrehozása</span><span class="sxs-lookup"><span data-stu-id="af1a3-189">Create variable compensation plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [<span data-ttu-id="af1a3-190">Munkabér-/kompenzációs struktúra és tervek kialakítása</span><span class="sxs-lookup"><span data-stu-id="af1a3-190">Develop salary/compensation structure and plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [<span data-ttu-id="af1a3-191">Folyamatkompenzáció</span><span class="sxs-lookup"><span data-stu-id="af1a3-191">Process compensation</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/process-compensation)
- [<span data-ttu-id="af1a3-192">Kompenzációs folyamat meghatározása és eredmények kiszámítása</span><span class="sxs-lookup"><span data-stu-id="af1a3-192">Define compensation process and calculate results</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [<span data-ttu-id="af1a3-193">Alkalmazottak felvétele fix kompenzációs konstrukcióba</span><span class="sxs-lookup"><span data-stu-id="af1a3-193">Enroll an employee in a fixed compensation plan</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [<span data-ttu-id="af1a3-194">Alkalmazottak felvétele változó kompenzációs konstrukcióba</span><span class="sxs-lookup"><span data-stu-id="af1a3-194">Enroll an employee in a variable compensation plan</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a><span data-ttu-id="af1a3-195">Beosztások</span><span class="sxs-lookup"><span data-stu-id="af1a3-195">Jobs</span></span> 

<span data-ttu-id="af1a3-196">A munkakör azon feladatok és felelősségek gyűjteménye, amelyek egy adott munkát végrehajtó személytől elvártak.</span><span class="sxs-lookup"><span data-stu-id="af1a3-196">A job is a collection of the tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="af1a3-197">További információ a következő témakörökben olvasható:</span><span class="sxs-lookup"><span data-stu-id="af1a3-197">For more information, see the following topics:</span></span>

- [<span data-ttu-id="af1a3-198">Feladat összetevőinek beállítása</span><span class="sxs-lookup"><span data-stu-id="af1a3-198">Setting up the components of a job</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-job)
- [<span data-ttu-id="af1a3-199">Új feladatok meghatározása</span><span class="sxs-lookup"><span data-stu-id="af1a3-199">Define new jobs</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a><span data-ttu-id="af1a3-200">Beosztások</span><span class="sxs-lookup"><span data-stu-id="af1a3-200">Positions</span></span>

<span data-ttu-id="af1a3-201">Egy beosztás egy feladat egyedi példánya.</span><span class="sxs-lookup"><span data-stu-id="af1a3-201">A position is an individual instance of a job.</span></span> <span data-ttu-id="af1a3-202">Például az „Értékesítési igazgató (Kelet)” pozíció egyike azon beosztásoknak, amelyek társíthatók az „Értékesítési igazgató” feladathoz.</span><span class="sxs-lookup"><span data-stu-id="af1a3-202">For example, the "Sales manager (East)" position is one of the positions that are associated with the "Sales manager" job.</span></span> <span data-ttu-id="af1a3-203">A beosztás létezik a részlegben.</span><span class="sxs-lookup"><span data-stu-id="af1a3-203">A position exists in a department.</span></span> <span data-ttu-id="af1a3-204">Egy beosztáshoz csak egy dolgozó rendelhető.</span><span class="sxs-lookup"><span data-stu-id="af1a3-204">Only one worker can be associated with each position.</span></span>

<span data-ttu-id="af1a3-205">A következő adatokat és konfigurációkat szem előtt tartani beosztások beállításakor:</span><span class="sxs-lookup"><span data-stu-id="af1a3-205">Keep the following data and configuration in mind when you set up positions:</span></span>

- <span data-ttu-id="af1a3-206">Beosztás (szükséges)</span><span class="sxs-lookup"><span data-stu-id="af1a3-206">Position (required)</span></span>
- <span data-ttu-id="af1a3-207">Leírás (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-207">Description (required)</span></span>
- <span data-ttu-id="af1a3-208">Munka (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-208">Job (required)</span></span>
- <span data-ttu-id="af1a3-209">Részleg (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-209">Department (required)</span></span>
- <span data-ttu-id="af1a3-210">Beosztás típusa (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-210">Position type (required)</span></span>
- <span data-ttu-id="af1a3-211">Teljes munkaidőssel egyenértékű</span><span class="sxs-lookup"><span data-stu-id="af1a3-211">Full-time equivalent</span></span>
- <span data-ttu-id="af1a3-212">Éves rendes munkaidő (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-212">Annual regular hours (required)</span></span>
- <span data-ttu-id="af1a3-213">Jogi személy által fizetett (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-213">Paid by legal entity (required)</span></span>
- <span data-ttu-id="af1a3-214">Fizetési ciklus (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-214">Pay cycle (required)</span></span>
- <span data-ttu-id="af1a3-215">Alapértelmezett pénzügyi dimenzió – Költséghely (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-215">Default financial dimension – Cost center (required)</span></span>
- <span data-ttu-id="af1a3-216">Dolgozó-hozzárendelés – dolgozó-hozzárendelés kezdete, hozzárendelés vége és okkód</span><span class="sxs-lookup"><span data-stu-id="af1a3-216">Worker assignment – Worker, assignment start, assignment end, reason code</span></span>

<span data-ttu-id="af1a3-217">A azonos osztály több beosztása társítva van az ugyanazon a feladathoz, azok össze lesznek vonva a Dayforce egyetlen pozíciójába.</span><span class="sxs-lookup"><span data-stu-id="af1a3-217">If multiple positions in the same department are associated with the same job, they are consolidated into a single position in Dayforce.</span></span>

<span data-ttu-id="af1a3-218">További információ a következő témakörökben olvasható:</span><span class="sxs-lookup"><span data-stu-id="af1a3-218">For more information, see the following topics:</span></span>

- [<span data-ttu-id="af1a3-219">Munkaerő szervezése részlegek, munkák és beosztások szerint</span><span class="sxs-lookup"><span data-stu-id="af1a3-219">Organize your workforce using departments, jobs, and positions</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [<span data-ttu-id="af1a3-220">Beosztások beállítása</span><span class="sxs-lookup"><span data-stu-id="af1a3-220">Set up positions</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a><span data-ttu-id="af1a3-221">Osztályok</span><span class="sxs-lookup"><span data-stu-id="af1a3-221">Departments</span></span>

<span data-ttu-id="af1a3-222">A részleg egy működési egység, amely a szervezet egy kategóriáját vagy működési területét képviseli.</span><span class="sxs-lookup"><span data-stu-id="af1a3-222">A department is an operating unit that represents a category or functional area of an organization.</span></span> <span data-ttu-id="af1a3-223">Egy részleg a szervezet egy konkrét területen végzett tevékenységeiért felel (például értékesítés, könyvelés, emberi erőforrások).</span><span class="sxs-lookup"><span data-stu-id="af1a3-223">A department is responsible for a specific area of the organization, such as sales, accounting, or human resources.</span></span> <span data-ttu-id="af1a3-224">A részlegek segítségével hozhatók létre jelentések a működési területekről.</span><span class="sxs-lookup"><span data-stu-id="af1a3-224">You can use departments to report on functional areas.</span></span> <span data-ttu-id="af1a3-225">A részlegeknek lehet eredménykimutatási felelőssége.</span><span class="sxs-lookup"><span data-stu-id="af1a3-225">Departments might have profit and loss responsibility.</span></span>

<span data-ttu-id="af1a3-226">További információ a következő témakörökben olvasható:</span><span class="sxs-lookup"><span data-stu-id="af1a3-226">For more information, see the following topics:</span></span>

- [<span data-ttu-id="af1a3-227">Részleg létrehozása és társítása a szervezeti hierarchiához</span><span class="sxs-lookup"><span data-stu-id="af1a3-227">Create a department and associate it with the department hierarchy</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [<span data-ttu-id="af1a3-228">Új részlegek meghatározása</span><span class="sxs-lookup"><span data-stu-id="af1a3-228">Define new departments</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a><span data-ttu-id="af1a3-229">Fizetési ciklusok és fizetési időszakok</span><span class="sxs-lookup"><span data-stu-id="af1a3-229">Pay cycles and pay periods</span></span>

<span data-ttu-id="af1a3-230">A fizetési ciklus meghatározza, hogy milyen gyakran történik a bérlista folyósítása, és a dolgozók mely napokon kapnak fizetést,.</span><span class="sxs-lookup"><span data-stu-id="af1a3-230">A pay cycle determines how often payroll is run and the specific days when workers are paid.</span></span> <span data-ttu-id="af1a3-231">Például a kifizetési ciklus lehet, havi, és az alkalmazottak kaphatják a hónap utolsó napján a fizetésüket.</span><span class="sxs-lookup"><span data-stu-id="af1a3-231">For example, a pay cycle might be monthly, and employees might be paid on the last day of the month.</span></span> <span data-ttu-id="af1a3-232">Vagy a kifizetési ciklus lehet heti, és az alkalmazottak a fizetési időszak utáni kedden kaphatják fizetésüket.</span><span class="sxs-lookup"><span data-stu-id="af1a3-232">Alternatively, a pay cycle might be weekly, and employees might be paid on the Tuesday after the end of the pay period.</span></span> <span data-ttu-id="af1a3-233">Kifizetési ciklusok beosztásokhoz vannak rendelve, és szabályozzák, hogy az ebben a beosztásban lévő dolgozók mikor kapnak fizetést.</span><span class="sxs-lookup"><span data-stu-id="af1a3-233">Pay cycles are assigned to positions to control when workers in those positions are paid.</span></span>

<span data-ttu-id="af1a3-234">Miután létrehozott fizetési ciklusokat, minden egyes ciklushoz fizetési időszakot hozhat létre.</span><span class="sxs-lookup"><span data-stu-id="af1a3-234">After you create pay cycles, you can generate pay periods for each cycle.</span></span> <span data-ttu-id="af1a3-235">Minden fizetési időszakban egy alapértelmezett fizetési dátum van, amely a megadott adatokon alapul.</span><span class="sxs-lookup"><span data-stu-id="af1a3-235">Each pay period includes a default payment date that is based on information that you provide.</span></span> <span data-ttu-id="af1a3-236">Ugyanakkor az alapértelmezett fizetési dátumot a fizetési időszakban módosíthatja kivételekhez például amikor egy kifizetési dátum ünnepnapra esik.</span><span class="sxs-lookup"><span data-stu-id="af1a3-236">However, you can modify the default payment date in a pay period to allow for exceptions, such as when the payment date falls on a holiday.</span></span>

<span data-ttu-id="af1a3-237">A következő adatokat használja a Dayforce:</span><span class="sxs-lookup"><span data-stu-id="af1a3-237">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="af1a3-238">Fizetési ciklus (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-238">Pay cycle (required)</span></span>
- <span data-ttu-id="af1a3-239">Fizetési ciklus gyakorisága (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-239">Pay cycle frequency (required)</span></span>
- <span data-ttu-id="af1a3-240">Az időszak kezdő dátuma (az első fizetési időszak szükséges)</span><span class="sxs-lookup"><span data-stu-id="af1a3-240">Period start date (first pay period required)</span></span>
- <span data-ttu-id="af1a3-241">Alapértelmezett fizetési dátum (az első fizetési időszak szükséges)</span><span class="sxs-lookup"><span data-stu-id="af1a3-241">Default payment date (first pay period required)</span></span>

<span data-ttu-id="af1a3-242">Ez az információ Dayforceba fizetési csoportokként van integrálva országonként vagy régiónként le van választva egyes kifizetési ciklusokhoz.</span><span class="sxs-lookup"><span data-stu-id="af1a3-242">This information is integrated with Dayforce as pay groups, and is separated by country or region for each pay cycle.</span></span> <span data-ttu-id="af1a3-243">Legalább egy fizetési időszakot kell létrehozni az integráció előtt.</span><span class="sxs-lookup"><span data-stu-id="af1a3-243">At least one pay period must be generated before integration.</span></span> <span data-ttu-id="af1a3-244">Dayforce létrehoz fizetési csoport naptárakat és a kifizetési dátumokat, az első fizetési időszak kezdő dátuma és az alapértelmezett fizetési dátum alapján, melyek a Talentben vannak beállítva.</span><span class="sxs-lookup"><span data-stu-id="af1a3-244">Dayforce generates pay group calendars and payment dates, based on the start date of the first pay period and the default payment date that is set up in Talent.</span></span>

#### <a name="earning-codes"></a><span data-ttu-id="af1a3-245">Bevételkódok</span><span class="sxs-lookup"><span data-stu-id="af1a3-245">Earning codes</span></span>

<span data-ttu-id="af1a3-246">A bevételkódok egyedi módon azonosítják a dolgozók által kapott fizetéstípusokat.</span><span class="sxs-lookup"><span data-stu-id="af1a3-246">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="af1a3-247">A kódoknak különböző paraméterei vannak, amelyek a bevételekhez kapcsolódnak, például könyvelési szabályok, jelentési követelmények és bruttósítási lehetőségek.</span><span class="sxs-lookup"><span data-stu-id="af1a3-247">The codes have various parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span>

<span data-ttu-id="af1a3-248">A következő adatokat használja a Dayforce:</span><span class="sxs-lookup"><span data-stu-id="af1a3-248">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="af1a3-249">Bevételkód (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-249">Earning Code (required)</span></span>
- <span data-ttu-id="af1a3-250">Leírás</span><span class="sxs-lookup"><span data-stu-id="af1a3-250">Description</span></span>
- <span data-ttu-id="af1a3-251">Mértékegység</span><span class="sxs-lookup"><span data-stu-id="af1a3-251">Unit of measure</span></span>
- <span data-ttu-id="af1a3-252">Produktív</span><span class="sxs-lookup"><span data-stu-id="af1a3-252">Productive</span></span>

### <a name="worker-data"></a><span data-ttu-id="af1a3-253">Dolgozóadatok</span><span class="sxs-lookup"><span data-stu-id="af1a3-253">Worker data</span></span>

<span data-ttu-id="af1a3-254">A dolgozók különböző típusaihoz tartozó rekordok, melyek fontosak az emberi erőforrásoknak és a bérlistarendszerekhez.</span><span class="sxs-lookup"><span data-stu-id="af1a3-254">Records for the various types of workers that you have are important to your human resources and payroll systems.</span></span> <span data-ttu-id="af1a3-255">A bevitt információk felhasználhatók az dolgozói és személyes adatok nyilvántartására.</span><span class="sxs-lookup"><span data-stu-id="af1a3-255">The information that you enter can be used to track workers and personal information.</span></span>

<span data-ttu-id="af1a3-256">A dolgozók következő adatait tarthatja karban:</span><span class="sxs-lookup"><span data-stu-id="af1a3-256">You can maintain the following information for workers:</span></span>

- <span data-ttu-id="af1a3-257">**Alapvető** – A dolgozók alapvető információi, például a kapcsolattartási adatok, demográfiai adatok azonosító adatok, családi adatok, a katonai szolgálat állapota, kiküldetésekre vonatkozó adatok, illetve személyes és rendkívüli kapcsolattartók.</span><span class="sxs-lookup"><span data-stu-id="af1a3-257">**Basic** – Maintain basic information about a worker, such as contact information, demographic information, identification information, family information, military service status, expatriate information, and personal and emergency contacts.</span></span>
- <span data-ttu-id="af1a3-258">**Foglalkoztatás** – Információk a dolgozó munkaviszonyáról, például a vállalati vagy szervezeti kapcsolat, hozzárendelt pozíció, kezdő és záró dátumok, munkajogosultság, foglalkoztatás feltételei, nyugdíj, szabadság és áthelyezéssel kapcsolatos információk.</span><span class="sxs-lookup"><span data-stu-id="af1a3-258">**Employment** – Maintain information about a worker's employment, such as company or organization affiliation, position assignment, start and end dates, work eligibility, terms of employment, pension, vacation, and relocation information.</span></span>
- <span data-ttu-id="af1a3-259">**Szabadság és a távollét** – A dolgozó távolléteinek kezelése, például a munkaidő-naptárak, a távolléti tranzakciók és távollét beállítása.</span><span class="sxs-lookup"><span data-stu-id="af1a3-259">**Leave and absence** – Maintain information about a worker's absences, such as working calendars, absence transactions, and absence setup.</span></span>
- <span data-ttu-id="af1a3-260">**Kompenzáció és bérlista** – dolgozói kompenzációs tervek és bérlistainformációk kezelése, például felvétel konstrukciója, jutalmak, teljesítmény, jutalék, adózási információk, nyugdíj és fizetéslevonások.</span><span class="sxs-lookup"><span data-stu-id="af1a3-260">**Compensation and payroll** – Maintain information about a worker's compensation plans and payroll information, such as plan enrollment, awards, performance, commission, tax information, retirement, and salary deductions.</span></span>

<span data-ttu-id="af1a3-261">A dolgozóinformációk létrehozása esetén ne felejtse el a következő adatokat és beállításokat, amelyeket a Dayforce használ.</span><span class="sxs-lookup"><span data-stu-id="af1a3-261">When you enter worker information, keep in mind the following data and configurations that are used in Dayforce.</span></span>

#### <a name="general-information"></a><span data-ttu-id="af1a3-262">Általános információk</span><span class="sxs-lookup"><span data-stu-id="af1a3-262">General information</span></span>

- <span data-ttu-id="af1a3-263">Személyzeti szám (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-263">Personnel number (required)</span></span>
- <span data-ttu-id="af1a3-264">Utónév (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-264">First name (required)</span></span>
- <span data-ttu-id="af1a3-265">Vezetéknév (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-265">Last name (required)</span></span>
- <span data-ttu-id="af1a3-266">Második keresztnév</span><span class="sxs-lookup"><span data-stu-id="af1a3-266">Middle name</span></span>
- <span data-ttu-id="af1a3-267">Szolgálati idő dátuma</span><span class="sxs-lookup"><span data-stu-id="af1a3-267">Seniority date</span></span>
- <span data-ttu-id="af1a3-268">Más néven</span><span class="sxs-lookup"><span data-stu-id="af1a3-268">Known as</span></span>

#### <a name="personal-information"></a><span data-ttu-id="af1a3-269">Személyes információ</span><span class="sxs-lookup"><span data-stu-id="af1a3-269">Personal information</span></span>

- <span data-ttu-id="af1a3-270">Családi állapot (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-270">Marital status (required)</span></span>
- <span data-ttu-id="af1a3-271">Születési dátum (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-271">Birth date (required)</span></span>
- <span data-ttu-id="af1a3-272">Nem (szükséges)</span><span class="sxs-lookup"><span data-stu-id="af1a3-272">Gender (required)</span></span>
- <span data-ttu-id="af1a3-273">Fogyatékkal élő személy</span><span class="sxs-lookup"><span data-stu-id="af1a3-273">Person with disabilities</span></span>
- <span data-ttu-id="af1a3-274">Állampolgárság ország régió (csak a Mexikó)</span><span class="sxs-lookup"><span data-stu-id="af1a3-274">Nationality country region (only for Mexico)</span></span>

#### <a name="address-information"></a><span data-ttu-id="af1a3-275">Címadatok</span><span class="sxs-lookup"><span data-stu-id="af1a3-275">Address information</span></span>

- <span data-ttu-id="af1a3-276">Elsődleges (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-276">Primary (required)</span></span>
- <span data-ttu-id="af1a3-277">Ország/régiót (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-277">Country/region (required)</span></span>
- <span data-ttu-id="af1a3-278">Irányítószámot (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-278">Postal code (required)</span></span>
- <span data-ttu-id="af1a3-279">Utca, házszám (kötelező) (csak Mexikó esetén)</span><span class="sxs-lookup"><span data-stu-id="af1a3-279">Street Number (required) (Only for Mexico)</span></span>
- <span data-ttu-id="af1a3-280">Épületblokk (csak a Mexikó)</span><span class="sxs-lookup"><span data-stu-id="af1a3-280">Building Complement (Only for Mexico)</span></span>
- <span data-ttu-id="af1a3-281">Város (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-281">City (required)</span></span>
- <span data-ttu-id="af1a3-282">Állam (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-282">State (required)</span></span>
- <span data-ttu-id="af1a3-283">Megye (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-283">County (required)</span></span>

#### <a name="contact-information"></a><span data-ttu-id="af1a3-284">Névjegy adatai</span><span class="sxs-lookup"><span data-stu-id="af1a3-284">Contact information</span></span> 

- <span data-ttu-id="af1a3-285">Elsődleges (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-285">Primary (required)</span></span>
- <span data-ttu-id="af1a3-286">Kapcsolattartó száma (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-286">Contact number (required)</span></span>
- <span data-ttu-id="af1a3-287">Mellék</span><span class="sxs-lookup"><span data-stu-id="af1a3-287">Extension</span></span>

#### <a name="payroll-information-and-earning-codes"></a><span data-ttu-id="af1a3-288">Bérlistaadatok és bevételkódok</span><span class="sxs-lookup"><span data-stu-id="af1a3-288">Payroll information and earning codes</span></span>

<span data-ttu-id="af1a3-289">Alkalmazottak hozzárendelhetők meghatározott bevételekhez adott fizetési gyakorisággal, és magadható elsődleges fizetési mód.</span><span class="sxs-lookup"><span data-stu-id="af1a3-289">Employees may be assigned specific earnings at a given frequency of payment and have a preferred payment method.</span></span> <span data-ttu-id="af1a3-290">A következő mezőket a Dayforce arra használja, hogy garantálja, hogy ezeket a preferenciákat és beállításokat használja.</span><span class="sxs-lookup"><span data-stu-id="af1a3-290">The following fields are used in Dayforce to help guarantee that those preferences and settings are used.</span></span>

##### <a name="earning-codes"></a><span data-ttu-id="af1a3-291">Bevételkódok</span><span class="sxs-lookup"><span data-stu-id="af1a3-291">Earning codes</span></span>

- <span data-ttu-id="af1a3-292">Beosztás (szükséges)</span><span class="sxs-lookup"><span data-stu-id="af1a3-292">Position (required)</span></span>
- <span data-ttu-id="af1a3-293">Bevételkód (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-293">Earning Code (required)</span></span>
- <span data-ttu-id="af1a3-294">Gyakoriság (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-294">Frequency (required)</span></span>
- <span data-ttu-id="af1a3-295">Összeg (szükséges)</span><span class="sxs-lookup"><span data-stu-id="af1a3-295">Amount (required)</span></span>

##### <a name="payroll-information"></a><span data-ttu-id="af1a3-296">Bérlistaadatok</span><span class="sxs-lookup"><span data-stu-id="af1a3-296">Payroll information</span></span>

- <span data-ttu-id="af1a3-297">Kifizetési mód</span><span class="sxs-lookup"><span data-stu-id="af1a3-297">Payment Method</span></span>
- <span data-ttu-id="af1a3-298">Gazdasági régió (szükséges)</span><span class="sxs-lookup"><span data-stu-id="af1a3-298">Economic Region (required)</span></span>
- <span data-ttu-id="af1a3-299">Alkalmazott juttatásainak azonosítója</span><span class="sxs-lookup"><span data-stu-id="af1a3-299">Employee Benefits ID</span></span>
- <span data-ttu-id="af1a3-300">Nemzeti azonosító (szükséges)</span><span class="sxs-lookup"><span data-stu-id="af1a3-300">National ID Number (required)</span></span>
- <span data-ttu-id="af1a3-301">Katonai szolgálat száma</span><span class="sxs-lookup"><span data-stu-id="af1a3-301">Military Service Number</span></span>
- <span data-ttu-id="af1a3-302">Műszakazonosító (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-302">Shift ID (required)</span></span>
- <span data-ttu-id="af1a3-303">Adószám (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-303">Tax Number (required)</span></span>
- <span data-ttu-id="af1a3-304">Szakszervezeti azonosító (szükséges)</span><span class="sxs-lookup"><span data-stu-id="af1a3-304">Union ID (required)</span></span>
- <span data-ttu-id="af1a3-305">Munkanap azonosítója (szükséges)</span><span class="sxs-lookup"><span data-stu-id="af1a3-305">Work Day ID (required)</span></span>
- <span data-ttu-id="af1a3-306">Munkavállalási engedély száma</span><span class="sxs-lookup"><span data-stu-id="af1a3-306">Work Permit Number</span></span>

> [!NOTE]
> <span data-ttu-id="af1a3-307">A fizetési módhoz Mexikó támogatja a **Készpénzt**, **Csekket** (a vállalat fizikai csekkjét és az **Elektronikus fizetést**.</span><span class="sxs-lookup"><span data-stu-id="af1a3-307">For the payment method, Mexico supports **Cash**, **Check** (the company's physical check), and **Electronic Payment**.</span></span> <span data-ttu-id="af1a3-308">Ha nincs fizetési mód van megadva, alapértelmezés szerint a **Csekk** használt.</span><span class="sxs-lookup"><span data-stu-id="af1a3-308">If np payment method is specified, **Check** is used by default.</span></span>

#### <a name="employment-details"></a><span data-ttu-id="af1a3-309">Foglalkoztatás részletei</span><span class="sxs-lookup"><span data-stu-id="af1a3-309">Employment details</span></span>

<span data-ttu-id="af1a3-310">Foglalkoztatási előzményei kulcsfontosságú információkat tartalmaznak a munkavállaók felvételi, elbocsátási, és újbóli felvétele állapotával kapcsolatosan a Dayforce-ban.</span><span class="sxs-lookup"><span data-stu-id="af1a3-310">Employment detail history is used as key information to derive an employee's hire, termination, and rehire statuses in Dayforce.</span></span> <span data-ttu-id="af1a3-311">Dayforce egyszerre csak egy aktív foglalkoztatásrekordot tesz lehetővé.</span><span class="sxs-lookup"><span data-stu-id="af1a3-311">Dayforce supports only one active employment record at a time.</span></span>

- <span data-ttu-id="af1a3-312">Foglalkoztatás kezdődátuma (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-312">Employment start date (required)</span></span>
- <span data-ttu-id="af1a3-313">Munkaviszony záró dátuma</span><span class="sxs-lookup"><span data-stu-id="af1a3-313">Employment end date</span></span>
- <span data-ttu-id="af1a3-314">Kezdő dátum</span><span class="sxs-lookup"><span data-stu-id="af1a3-314">Start date</span></span>
- <span data-ttu-id="af1a3-315">Módosított kezdési időpont</span><span class="sxs-lookup"><span data-stu-id="af1a3-315">Adjusted start date</span></span>
- <span data-ttu-id="af1a3-316">Munkaviszony megszűnésének dátuma (megszűntetéskor kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-316">Termination date (required upon termination)</span></span>
- <span data-ttu-id="af1a3-317">Felmondás oka (megszűntetéskor kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-317">Termination reason (required upon termination)</span></span>

<span data-ttu-id="af1a3-318">Az alkalmazott legfontosabb dátumai a következő adatokból vannak származtatva.</span><span class="sxs-lookup"><span data-stu-id="af1a3-318">An employee's key dates are derived by using the following information.</span></span>

| <span data-ttu-id="af1a3-319">Talent</span><span class="sxs-lookup"><span data-stu-id="af1a3-319">Talent</span></span>                | <span data-ttu-id="af1a3-320">Dayforce</span><span class="sxs-lookup"><span data-stu-id="af1a3-320">Dayforce</span></span>                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="af1a3-321">Legutóbbi felvételi dátum</span><span class="sxs-lookup"><span data-stu-id="af1a3-321">Most recent hire date</span></span> | <span data-ttu-id="af1a3-322">Foglalkoztatás kezdete az aktuális nem megszűntetett előzményrekordra</span><span class="sxs-lookup"><span data-stu-id="af1a3-322">Employment start of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="af1a3-323">Munkaviszony megszűnésének dátuma</span><span class="sxs-lookup"><span data-stu-id="af1a3-323">Termination date</span></span>      | <span data-ttu-id="af1a3-324">Foglalkoztatás befejezése az aktuális nem megszűntetett előzményrekordra</span><span class="sxs-lookup"><span data-stu-id="af1a3-324">Termination date of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="af1a3-325">Kezdő dátum</span><span class="sxs-lookup"><span data-stu-id="af1a3-325">Start date</span></span>            | <span data-ttu-id="af1a3-326">Módosított kezdési időpont, kezdődátum vagy foglalkoztatás kezdete az aktuális nem aktív előzményrekordra</span><span class="sxs-lookup"><span data-stu-id="af1a3-326">Adjusted start date, start date, or employment start of current non-active employment history record</span></span> |
| <span data-ttu-id="af1a3-327">Eredeti felvételi dátum</span><span class="sxs-lookup"><span data-stu-id="af1a3-327">Original hire date</span></span>    | <span data-ttu-id="af1a3-328">Foglalkoztatás kezdete legkorábbi foglalkoztatási előzményrekordra</span><span class="sxs-lookup"><span data-stu-id="af1a3-328">Employment start of earliest employment history record</span></span>                                               |

#### <a name="compensation"></a><span data-ttu-id="af1a3-329">Kompenzáció</span><span class="sxs-lookup"><span data-stu-id="af1a3-329">Compensation</span></span>

<span data-ttu-id="af1a3-330">Egy fix kompenzációs tervet kell társítani minden alkalmazott elsődleges pozíciójához az alkalmazási időszak alatt.</span><span class="sxs-lookup"><span data-stu-id="af1a3-330">A fixed compensation plan must be associated with every employee's primary position throughout an employment period.</span></span> <span data-ttu-id="af1a3-331">Az időszak a belépés dátumával (vagy a foglalkoztatás kezdő dátumával) kezdődik, és a munkaviszony megszűnéséig tart .</span><span class="sxs-lookup"><span data-stu-id="af1a3-331">This period starts on the date that the employee was hired (or the employment start date) and continues until termination.</span></span>

- <span data-ttu-id="af1a3-332">Érvényesség dátuma (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-332">Effective Date (required)</span></span>
- <span data-ttu-id="af1a3-333">Lejárati dátum</span><span class="sxs-lookup"><span data-stu-id="af1a3-333">Expiration date</span></span>
- <span data-ttu-id="af1a3-334">Fizetési díjalap (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-334">Pay Rate (required)</span></span>
- <span data-ttu-id="af1a3-335">Fizetési díjalapok átalakításai (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-335">Pay Rate Conversions (required)</span></span>
- <span data-ttu-id="af1a3-336">Évi egyenérték (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-336">Annual equivalent (required)</span></span>
- <span data-ttu-id="af1a3-337">Óránkénti egyenérték (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-337">Hourly equivalent (required)</span></span>

<span data-ttu-id="af1a3-338">Ha az óránkénti alkalmazottnak több beosztása van, az elsődleges beosztásához tartozó fix kompenzációja importálva lesz a Dayforce-ba, alkalmazott szintű alapdíj/-fizetés.</span><span class="sxs-lookup"><span data-stu-id="af1a3-338">If an hourly employee has multiple positions, the fixed compensation of the primary position is imported into Dayforce as the employee-level base rate/salary.</span></span> <span data-ttu-id="af1a3-339">A nem elsődleges beosztások esetén, az óránkénti díj a megfelelő pozícióba lesz mentve Dayforce-ban.</span><span class="sxs-lookup"><span data-stu-id="af1a3-339">For non-primary positions, the hourly rate is saved to the corresponding position in Dayforce.</span></span>

<span data-ttu-id="af1a3-340">Ha a fizetett alkalmazott több beosztással rendelkezik, a összesített óradíj és éves fizetés származtatva lesz az összes aktív beosztásból mint az alkalmazotti szintű alapdíj/-fizetés.</span><span class="sxs-lookup"><span data-stu-id="af1a3-340">If a salaried employee has multiple positions, the cumulative hour rate and annual salary across all active positions are derived and used as the employee-level base rate/salary.</span></span>

#### <a name="identification-numbers"></a><span data-ttu-id="af1a3-341">Azonosítószámok</span><span class="sxs-lookup"><span data-stu-id="af1a3-341">Identification numbers</span></span>

##### <a name="social-security-identifier"></a><span data-ttu-id="af1a3-342">Társadalombiztosítási azonosító</span><span class="sxs-lookup"><span data-stu-id="af1a3-342">Social Security identifier</span></span> 

<span data-ttu-id="af1a3-343">Minden alkalmazottnak kell egy elsődleges azonosítóval rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="af1a3-343">Every employee must have one primary identifier.</span></span> <span data-ttu-id="af1a3-344">Ez az azonosító legyen **TAJ-szám** azonosítótípus kell legyen.</span><span class="sxs-lookup"><span data-stu-id="af1a3-344">This identifier must be of **SSN** identification type.</span></span> <span data-ttu-id="af1a3-345">A Dayforce-ban automatikusan van származtatva az alkalmazott társadalombiztosítási azonosítójából, mely a felvételhez szükséges.</span><span class="sxs-lookup"><span data-stu-id="af1a3-345">In Dayforce, it's automatically derived as the employee's Social Security identifier that is required for hire.</span></span>

- <span data-ttu-id="af1a3-346">Elsődleges (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-346">Primary (required)</span></span>
- <span data-ttu-id="af1a3-347">Azonosító típusa = „TAJ-szám”</span><span class="sxs-lookup"><span data-stu-id="af1a3-347">Identification Type = "SSN"</span></span>
- <span data-ttu-id="af1a3-348">Kibocsátás dátuma</span><span class="sxs-lookup"><span data-stu-id="af1a3-348">Issued Date</span></span>
- <span data-ttu-id="af1a3-349">Lejárat dátuma</span><span class="sxs-lookup"><span data-stu-id="af1a3-349">Expiration Date</span></span>

<span data-ttu-id="af1a3-350">Az alkalmazottak több azonosítószámot is megadhatnak **TAJ-szám** azonosítótípushoz.</span><span class="sxs-lookup"><span data-stu-id="af1a3-350">Employees can declare multiple identification numbers of the **SSN** identification type.</span></span> <span data-ttu-id="af1a3-351">Azonban csak az **Elsődlegesként** megjelölt rekord van integrálva Dayforce-ba, függetlenül attól, hogy a szám aktív vagy lejárt.</span><span class="sxs-lookup"><span data-stu-id="af1a3-351">However, only the record that is marked as **Primary** is integrated into Dayforce, regardless of whether the number is active or expired.</span></span>

#### <a name="bank-accounts-and-disbursements"></a><span data-ttu-id="af1a3-352">Bankszámlák és kifizetések</span><span class="sxs-lookup"><span data-stu-id="af1a3-352">Bank accounts and disbursements</span></span>

<span data-ttu-id="af1a3-353">Érvényes bankszámlaadatokat meg kell adni minden olyan alkalmazotthoz, aki úgy dönt, hogy a banki átutalással kéri fizetését.</span><span class="sxs-lookup"><span data-stu-id="af1a3-353">Valid bank account information must be entered for any employee who chooses to be paid via bank account transfers.</span></span>

| <span data-ttu-id="af1a3-354">Talent</span><span class="sxs-lookup"><span data-stu-id="af1a3-354">Talent</span></span>                         | <span data-ttu-id="af1a3-355">Dayforce</span><span class="sxs-lookup"><span data-stu-id="af1a3-355">Dayforce</span></span>                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="af1a3-356">Bankszámlaszám (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-356">Bank account number (required)</span></span> |                                                                                                             |
| <span data-ttu-id="af1a3-357">SWIFT-kód (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-357">SWIFT code (required)</span></span>          | <span data-ttu-id="af1a3-358">**Bankazonosító** ez a mező Mexikóban történő bérlistafeldolgozáskor használatos.</span><span class="sxs-lookup"><span data-stu-id="af1a3-358">**Bank ID** field used when processing payroll in Mexico.</span></span>                                                             |
| <span data-ttu-id="af1a3-359">Ágazati szám (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-359">Branch number (required)</span></span>       |                                                                                                             |
| <span data-ttu-id="af1a3-360">Bankszámla típusa (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-360">Bank account type (required)</span></span>   | <span data-ttu-id="af1a3-361">**Számlatípus** ez a mező Mexikóban történő bérlistafeldolgozáskor használatos.</span><span class="sxs-lookup"><span data-stu-id="af1a3-361">**Account type** field used when processing payroll in Mexico.</span></span> <span data-ttu-id="af1a3-362">Támogatott értékek: **Folyószámla** és **Bérlista**</span><span class="sxs-lookup"><span data-stu-id="af1a3-362">Supported values include **Checking** and **Payroll**.</span></span> |

> [!NOTE]
> <span data-ttu-id="af1a3-363">Alkalmazottak, akik úgy döntenek, hogy a banki átutaláson keresztülkérik fizetésük, meg kell adniuk egy hivatkozást egy jogi személyhez tartozó egyenlegszámlához, melynek elsődleges címének Mexikóban kell lennie és egy Mexikói bank érvényes bankszámlájához van társítva.</span><span class="sxs-lookup"><span data-stu-id="af1a3-363">Employees who choose to be paid via bank account transfers must provide a link to a remainder account that is under a legal entity that has its primary address in Mexico and associated with a valid bank account from a Mexican bank.</span></span> <span data-ttu-id="af1a3-364">Minden egyéb nem egyenlegszámla figyelmen kívül lesz hagyva.</span><span class="sxs-lookup"><span data-stu-id="af1a3-364">All other non-remainder accounts are ignored.</span></span>

#### <a name="address-information"></a><span data-ttu-id="af1a3-365">Címadatok</span><span class="sxs-lookup"><span data-stu-id="af1a3-365">Address information</span></span>

<span data-ttu-id="af1a3-366">Minden alkalmazottnak kell egy elsődleges hellyel rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="af1a3-366">Every employee must have one primary location.</span></span> <span data-ttu-id="af1a3-367">A Dayforce-ban ezen hely alapján van meghatározva az alkalmazott elsődleges tartózkodási helye adózási célokból.</span><span class="sxs-lookup"><span data-stu-id="af1a3-367">In Dayforce, this location is used to determine the employee's primary residence for tax purposes.</span></span>

- <span data-ttu-id="af1a3-368">Elsődleges (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-368">Primary (required)</span></span>
- <span data-ttu-id="af1a3-369">Ország/régiót (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-369">Country/region (required)</span></span>
- <span data-ttu-id="af1a3-370">Irányítószám/postai kód (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-370">Zip/postal code (required)</span></span>
- <span data-ttu-id="af1a3-371">Utca (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-371">Street (required)</span></span>
- <span data-ttu-id="af1a3-372">Házszám (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-372">Street Number (required)</span></span>
- <span data-ttu-id="af1a3-373">Épületblokk</span><span class="sxs-lookup"><span data-stu-id="af1a3-373">Building Complement</span></span>
- <span data-ttu-id="af1a3-374">Város (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-374">City (required)</span></span>
- <span data-ttu-id="af1a3-375">Állam (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-375">State (required)</span></span>
- <span data-ttu-id="af1a3-376">Megye (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-376">County (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a><span data-ttu-id="af1a3-377">Az adatok konfigurálása bérlista létrehozásához az Egyesült Államokban és Kanadában</span><span class="sxs-lookup"><span data-stu-id="af1a3-377">Configure your data to generate payroll in United States and Canada</span></span>

<span data-ttu-id="af1a3-378">Ha a fizetést generálása alkalmazottaknak az Egyesült Államokban és Kanadában, a következő elemeket kell beállítani:</span><span class="sxs-lookup"><span data-stu-id="af1a3-378">If you're generating pay for employees in the United States and Canada, the following elements must be configured:</span></span>

- <span data-ttu-id="af1a3-379">Részlegek szükségesek beosztásokhoz.</span><span class="sxs-lookup"><span data-stu-id="af1a3-379">Departments are required on positions.</span></span>
- <span data-ttu-id="af1a3-380">Költséghelyek pénzügyi dimenziókként kell beállítani, és az alapértelmezett pénzügyi dimenzió karakterlánc első elemének kell lennie.</span><span class="sxs-lookup"><span data-stu-id="af1a3-380">Cost centers must be set as financial dimensions and must be the first element in the default financial dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="af1a3-381">Beosztástípusok</span><span class="sxs-lookup"><span data-stu-id="af1a3-381">Job types</span></span>

<span data-ttu-id="af1a3-382">Beosztástípusok használatával a hasonló feladatok kategóriákba sorolhatók.</span><span class="sxs-lookup"><span data-stu-id="af1a3-382">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="af1a3-383">A beosztástípusok szükségesek az Egyesült Államokban és Kanadában a bérlisták feldolgozásához.</span><span class="sxs-lookup"><span data-stu-id="af1a3-383">Job types are required in order to process payroll in the United States and Canada.</span></span> <span data-ttu-id="af1a3-384">Beosztástípusok többek között a teljes és részmunkaidős, illetve a munkabéres és az órabéres.</span><span class="sxs-lookup"><span data-stu-id="af1a3-384">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="af1a3-385">A beosztástípusok a fizetéstípusokként vannak hozzárendelve a Dayforce-hoz, melyek jelzik, hogy a munkavállaló órás vagy bérezéses.</span><span class="sxs-lookup"><span data-stu-id="af1a3-385">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="af1a3-386">A következő feladattípusok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="af1a3-386">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="af1a3-387">Feladattípus</span><span class="sxs-lookup"><span data-stu-id="af1a3-387">Job type</span></span>   | <span data-ttu-id="af1a3-388">Leírás</span><span class="sxs-lookup"><span data-stu-id="af1a3-388">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="af1a3-389">Óránként</span><span class="sxs-lookup"><span data-stu-id="af1a3-389">Hourly</span></span>     | <span data-ttu-id="af1a3-390">Óránként</span><span class="sxs-lookup"><span data-stu-id="af1a3-390">Hourly</span></span>      |
| <span data-ttu-id="af1a3-391">Bérezéses</span><span class="sxs-lookup"><span data-stu-id="af1a3-391">Salaried</span></span>   | <span data-ttu-id="af1a3-392">Bérezéses</span><span class="sxs-lookup"><span data-stu-id="af1a3-392">Salaried</span></span>    |

### <a name="position-types"></a><span data-ttu-id="af1a3-393">Beosztási típusok</span><span class="sxs-lookup"><span data-stu-id="af1a3-393">Position types</span></span> 

<span data-ttu-id="af1a3-394">Ne használjon beosztástípusokat annak leírására, hogy a beosztás teljes munkaidős, részmunkaidős vagy más.</span><span class="sxs-lookup"><span data-stu-id="af1a3-394">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="af1a3-395">A feladattípusok a fizetésosztályokként vannak hozzárendelve a Dayforce-hoz, melyek jelzik, hogy a munkavállaló teljes- vagy részmunkaidős.</span><span class="sxs-lookup"><span data-stu-id="af1a3-395">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="af1a3-396">A következő beosztástípusok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="af1a3-396">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="af1a3-397">Beosztás típusa</span><span class="sxs-lookup"><span data-stu-id="af1a3-397">Position type</span></span>   | <span data-ttu-id="af1a3-398">Leírás</span><span class="sxs-lookup"><span data-stu-id="af1a3-398">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="af1a3-399">Teljes munkaidős</span><span class="sxs-lookup"><span data-stu-id="af1a3-399">Full-time</span></span>       | <span data-ttu-id="af1a3-400">Teljes munkaidős alkalmazott</span><span class="sxs-lookup"><span data-stu-id="af1a3-400">Full time employee</span></span> |
| <span data-ttu-id="af1a3-401">Részmunkaidős</span><span class="sxs-lookup"><span data-stu-id="af1a3-401">Part-time</span></span>       | <span data-ttu-id="af1a3-402">Részmunkaidős alkalmazott</span><span class="sxs-lookup"><span data-stu-id="af1a3-402">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="af1a3-403">Okkódok</span><span class="sxs-lookup"><span data-stu-id="af1a3-403">Reason codes</span></span>

<span data-ttu-id="af1a3-404">Az alkalmazottak állapotával kapcsolatos okkódok tájékoztatnak.</span><span class="sxs-lookup"><span data-stu-id="af1a3-404">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="af1a3-405">Okkódok a Dayforce-hoz állapot okaként vannak hozzárendelve, melyek jelzik egy alkalmazott beosztásában vagy alkalmazotti státuszában bekövetkezett változások okát.</span><span class="sxs-lookup"><span data-stu-id="af1a3-405">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="af1a3-406">A következő okkódok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="af1a3-406">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="af1a3-407">Okkód</span><span class="sxs-lookup"><span data-stu-id="af1a3-407">Reason code</span></span>    | <span data-ttu-id="af1a3-408">Leírás</span><span class="sxs-lookup"><span data-stu-id="af1a3-408">Description</span></span>      | <span data-ttu-id="af1a3-409">Alkalmazandó forgatókönyvek</span><span class="sxs-lookup"><span data-stu-id="af1a3-409">Applicable scenarios</span></span> |
|----------------|------------------|----------------------|
| <span data-ttu-id="af1a3-410">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="af1a3-410">RESIGNATION</span></span>    | <span data-ttu-id="af1a3-411">Felmondás</span><span class="sxs-lookup"><span data-stu-id="af1a3-411">Resignation</span></span>      | <span data-ttu-id="af1a3-412">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="af1a3-412">Terminate worker</span></span>     |
| <span data-ttu-id="af1a3-413">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="af1a3-413">TERMINATION</span></span>    | <span data-ttu-id="af1a3-414">Befejezés</span><span class="sxs-lookup"><span data-stu-id="af1a3-414">Termination</span></span>      | <span data-ttu-id="af1a3-415">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="af1a3-415">Terminate worker</span></span>     |
| <span data-ttu-id="af1a3-416">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="af1a3-416">RETIREMENT</span></span>     | <span data-ttu-id="af1a3-417">Megszüntetés</span><span class="sxs-lookup"><span data-stu-id="af1a3-417">Retirement</span></span>       | <span data-ttu-id="af1a3-418">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="af1a3-418">Terminate worker</span></span>     |
| <span data-ttu-id="af1a3-419">EGYÉB</span><span class="sxs-lookup"><span data-stu-id="af1a3-419">OTHER</span></span>          | <span data-ttu-id="af1a3-420">Egyéb okok</span><span class="sxs-lookup"><span data-stu-id="af1a3-420">Other Reasons</span></span>    | <span data-ttu-id="af1a3-421">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="af1a3-421">Terminate worker</span></span>     |
| <span data-ttu-id="af1a3-422">DEATH</span><span class="sxs-lookup"><span data-stu-id="af1a3-422">DEATH</span></span>          | <span data-ttu-id="af1a3-423">Elhalálozás</span><span class="sxs-lookup"><span data-stu-id="af1a3-423">Death</span></span>            | <span data-ttu-id="af1a3-424">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="af1a3-424">Terminate worker</span></span>     |
| <span data-ttu-id="af1a3-425">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="af1a3-425">LEAVEOFABSENCE</span></span> | <span data-ttu-id="af1a3-426">Szabadság</span><span class="sxs-lookup"><span data-stu-id="af1a3-426">Leave of Absence</span></span> | <span data-ttu-id="af1a3-427">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="af1a3-427">Terminate worker</span></span>     |
| <span data-ttu-id="af1a3-428">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="af1a3-428">CONTRACTEND</span></span>    | <span data-ttu-id="af1a3-429">Szerződés vége</span><span class="sxs-lookup"><span data-stu-id="af1a3-429">End of Contract</span></span>  | <span data-ttu-id="af1a3-430">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="af1a3-430">Terminate worker</span></span>     |
| <span data-ttu-id="af1a3-431">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="af1a3-431">SALARYCHANGE</span></span>   | <span data-ttu-id="af1a3-432">Munkabér módosítása</span><span class="sxs-lookup"><span data-stu-id="af1a3-432">Change of Salary</span></span> | <span data-ttu-id="af1a3-433">Kompenzáció</span><span class="sxs-lookup"><span data-stu-id="af1a3-433">Compensation</span></span>         |

### <a name="marital-status"></a><span data-ttu-id="af1a3-434">Családi állapot</span><span class="sxs-lookup"><span data-stu-id="af1a3-434">Marital status</span></span>

<span data-ttu-id="af1a3-435">Családi állapot értékei Dayforce-hoz vannak rendelve és konvertálva szükség esetén az elfogadható értékekre az integráció során.</span><span class="sxs-lookup"><span data-stu-id="af1a3-435">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="af1a3-436">Az alábbi táblázat bemutatja, hogy családi állapot értékek hogyan vannak leképezve a Dayforce -ban.</span><span class="sxs-lookup"><span data-stu-id="af1a3-436">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="af1a3-437">Talent</span><span class="sxs-lookup"><span data-stu-id="af1a3-437">Talent</span></span>                 | <span data-ttu-id="af1a3-438">Dayforce</span><span class="sxs-lookup"><span data-stu-id="af1a3-438">Dayforce</span></span>             |
|------------------------|----------------------|
| <span data-ttu-id="af1a3-439">Házas</span><span class="sxs-lookup"><span data-stu-id="af1a3-439">Married</span></span>                | <span data-ttu-id="af1a3-440">Házas</span><span class="sxs-lookup"><span data-stu-id="af1a3-440">Married</span></span>              |
| <span data-ttu-id="af1a3-441">Egy</span><span class="sxs-lookup"><span data-stu-id="af1a3-441">Single</span></span>                 | <span data-ttu-id="af1a3-442">Egy</span><span class="sxs-lookup"><span data-stu-id="af1a3-442">Single</span></span>               |
| <span data-ttu-id="af1a3-443">Özvegy</span><span class="sxs-lookup"><span data-stu-id="af1a3-443">Widowed</span></span>                | <span data-ttu-id="af1a3-444">Özvegy</span><span class="sxs-lookup"><span data-stu-id="af1a3-444">Widowed</span></span>              |
| <span data-ttu-id="af1a3-445">Elvált</span><span class="sxs-lookup"><span data-stu-id="af1a3-445">Divorced</span></span>               | <span data-ttu-id="af1a3-446">Elvált</span><span class="sxs-lookup"><span data-stu-id="af1a3-446">Divorced</span></span>             |
| <span data-ttu-id="af1a3-447">Bejegyzett élettársi kapcsolat</span><span class="sxs-lookup"><span data-stu-id="af1a3-447">Registered Partnership</span></span> | <span data-ttu-id="af1a3-448">Élettársi viszony</span><span class="sxs-lookup"><span data-stu-id="af1a3-448">Domestic Partnership</span></span> |
| <span data-ttu-id="af1a3-449">Nincs</span><span class="sxs-lookup"><span data-stu-id="af1a3-449">None</span></span>                   | <span data-ttu-id="af1a3-450">Nincs</span><span class="sxs-lookup"><span data-stu-id="af1a3-450">None</span></span>                 |
| <span data-ttu-id="af1a3-451">Együttélés</span><span class="sxs-lookup"><span data-stu-id="af1a3-451">Cohabiting</span></span>             | <span data-ttu-id="af1a3-452">Együttélés</span><span class="sxs-lookup"><span data-stu-id="af1a3-452">Cohabiting</span></span>           |

### <a name="gender"></a><span data-ttu-id="af1a3-453">Nem</span><span class="sxs-lookup"><span data-stu-id="af1a3-453">Gender</span></span>

<span data-ttu-id="af1a3-454">A nemek a Dayforce-hoz vannak rendelve és konvertálva szükség esetén az elfogadható értékekre az integráció során.</span><span class="sxs-lookup"><span data-stu-id="af1a3-454">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="af1a3-455">Az alábbi táblázat bemutatja, hogy a nemek hogyan vannak leképezve a Dayforce-ban.</span><span class="sxs-lookup"><span data-stu-id="af1a3-455">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="af1a3-456">Talent</span><span class="sxs-lookup"><span data-stu-id="af1a3-456">Talent</span></span>       | <span data-ttu-id="af1a3-457">Dayforce</span><span class="sxs-lookup"><span data-stu-id="af1a3-457">Dayforce</span></span>        |
|--------------|-----------------|
| <span data-ttu-id="af1a3-458">Férfi</span><span class="sxs-lookup"><span data-stu-id="af1a3-458">Male</span></span>         | <span data-ttu-id="af1a3-459">Férfi</span><span class="sxs-lookup"><span data-stu-id="af1a3-459">Male</span></span>            |
| <span data-ttu-id="af1a3-460">Nő</span><span class="sxs-lookup"><span data-stu-id="af1a3-460">Female</span></span>       | <span data-ttu-id="af1a3-461">Nő</span><span class="sxs-lookup"><span data-stu-id="af1a3-461">Female</span></span>          |
| <span data-ttu-id="af1a3-462">Nem meghatározott</span><span class="sxs-lookup"><span data-stu-id="af1a3-462">Non-specific</span></span> | <span data-ttu-id="af1a3-463">*Nem támogatott*</span><span class="sxs-lookup"><span data-stu-id="af1a3-463">*Not supported*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="af1a3-464">Bevételkódok</span><span class="sxs-lookup"><span data-stu-id="af1a3-464">Earning codes</span></span>

<span data-ttu-id="af1a3-465">A bevételkódok egyedi módon azonosítják a dolgozók által kapott fizetéstípusokat.</span><span class="sxs-lookup"><span data-stu-id="af1a3-465">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="af1a3-466">A kódoknak különböző paramétereket fednek le, amelyek a bevételekhez kapcsolódnak, például könyvelési szabályok, jelentési követelmények és bruttósítási lehetőségek.</span><span class="sxs-lookup"><span data-stu-id="af1a3-466">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="af1a3-467">Ha egy nem támogatott gyakoriság van használatban, a **Minden fizetés** gyakorisága van alapértelmezés szerint használva a kiszámításhoz.</span><span class="sxs-lookup"><span data-stu-id="af1a3-467">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="af1a3-468">Támogatott gyakoriságok</span><span class="sxs-lookup"><span data-stu-id="af1a3-468">Supported frequencies</span></span>

- <span data-ttu-id="af1a3-469">Összes</span><span class="sxs-lookup"><span data-stu-id="af1a3-469">All</span></span>
- <span data-ttu-id="af1a3-470">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="af1a3-470">EVERYPAY</span></span>
- <span data-ttu-id="af1a3-471">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="af1a3-471">EACHPAYPERIOD</span></span>
- <span data-ttu-id="af1a3-472">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="af1a3-472">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="af1a3-473">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="af1a3-473">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="af1a3-474">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="af1a3-474">1OFMTH</span></span>
- <span data-ttu-id="af1a3-475">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="af1a3-475">LASTOFMTH</span></span>
- <span data-ttu-id="af1a3-476">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="af1a3-476">2OFMTH</span></span>
- <span data-ttu-id="af1a3-477">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="af1a3-477">3OFMTH</span></span>
- <span data-ttu-id="af1a3-478">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="af1a3-478">4OFMTH</span></span>
- <span data-ttu-id="af1a3-479">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="af1a3-479">5OFMTH</span></span>
- <span data-ttu-id="af1a3-480">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="af1a3-480">1N2OFMTH</span></span>
- <span data-ttu-id="af1a3-481">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="af1a3-481">3N4OFMTH</span></span>
- <span data-ttu-id="af1a3-482">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="af1a3-482">1N3OFMTH</span></span>
- <span data-ttu-id="af1a3-483">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="af1a3-483">1N4OFMTH</span></span>
- <span data-ttu-id="af1a3-484">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="af1a3-484">2N3OFMTH</span></span>
- <span data-ttu-id="af1a3-485">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="af1a3-485">2N4OFMTH</span></span>
- <span data-ttu-id="af1a3-486">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="af1a3-486">1N2N3OFMTH</span></span>
- <span data-ttu-id="af1a3-487">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="af1a3-487">1N2N4OFMTH</span></span>
- <span data-ttu-id="af1a3-488">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="af1a3-488">1N3N4OFMTH</span></span>
- <span data-ttu-id="af1a3-489">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="af1a3-489">2N3N4OFMTH</span></span>
- <span data-ttu-id="af1a3-490">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="af1a3-490">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="af1a3-491">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="af1a3-491">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="af1a3-492">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="af1a3-492">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="af1a3-493">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="af1a3-493">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="af1a3-494">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="af1a3-494">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="af1a3-495">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="af1a3-495">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="af1a3-496">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="af1a3-496">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="af1a3-497">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="af1a3-497">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="af1a3-498">Címek</span><span class="sxs-lookup"><span data-stu-id="af1a3-498">Addresses</span></span>

<span data-ttu-id="af1a3-499">Az adott ország vagy régió, állam és megye (település) kódok specifikus formátumokat követelnek, hogy Dayforce és az országos és regionális szolgáltatók felismerjék azokat.</span><span class="sxs-lookup"><span data-stu-id="af1a3-499">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="af1a3-500">Annak ellenére, hogy a városok formátuma rugalmas, minden városnak társítva kell lennie egy államhoz.</span><span class="sxs-lookup"><span data-stu-id="af1a3-500">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="af1a3-501">Talent</span><span class="sxs-lookup"><span data-stu-id="af1a3-501">Talent</span></span>          | <span data-ttu-id="af1a3-502">Dayforce</span><span class="sxs-lookup"><span data-stu-id="af1a3-502">Dayforce</span></span>              |
|-----------------|-----------------------|
| <span data-ttu-id="af1a3-503">Ország/régió</span><span class="sxs-lookup"><span data-stu-id="af1a3-503">Country/Region</span></span>  | <span data-ttu-id="af1a3-504">Országkód</span><span class="sxs-lookup"><span data-stu-id="af1a3-504">Country Code</span></span>          |
| <span data-ttu-id="af1a3-505">Irányítószám / postai kód</span><span class="sxs-lookup"><span data-stu-id="af1a3-505">Zip/Postal Code</span></span> | <span data-ttu-id="af1a3-506">Irányítószám</span><span class="sxs-lookup"><span data-stu-id="af1a3-506">Postal Code</span></span>           |
| <span data-ttu-id="af1a3-507">Állami</span><span class="sxs-lookup"><span data-stu-id="af1a3-507">State</span></span>           | <span data-ttu-id="af1a3-508">Államkód</span><span class="sxs-lookup"><span data-stu-id="af1a3-508">State Code</span></span>            |
| <span data-ttu-id="af1a3-509">Város</span><span class="sxs-lookup"><span data-stu-id="af1a3-509">City</span></span>            | <span data-ttu-id="af1a3-510">Város</span><span class="sxs-lookup"><span data-stu-id="af1a3-510">City</span></span>                  |
| <span data-ttu-id="af1a3-511">Megye</span><span class="sxs-lookup"><span data-stu-id="af1a3-511">County</span></span>          | <span data-ttu-id="af1a3-512">Megye (Helyhatóság)</span><span class="sxs-lookup"><span data-stu-id="af1a3-512">County (Municipality)</span></span> |
| <span data-ttu-id="af1a3-513">Utca</span><span class="sxs-lookup"><span data-stu-id="af1a3-513">Street</span></span>          | <span data-ttu-id="af1a3-514">Cím 1. sora</span><span class="sxs-lookup"><span data-stu-id="af1a3-514">Address Line 1</span></span>        |

### <a name="tax-regions"></a><span data-ttu-id="af1a3-515">Adórégiók</span><span class="sxs-lookup"><span data-stu-id="af1a3-515">Tax regions</span></span>

<span data-ttu-id="af1a3-516">Az adórégiók a megfelelő adó megállapítására szolgálnak, amelyet a bérlista létrehozásakor kell alkalmazni.</span><span class="sxs-lookup"><span data-stu-id="af1a3-516">Tax regions are used to determine the appropriate tax that should be applied during payroll generation.</span></span> <span data-ttu-id="af1a3-517">Az adórégiók helycímként vannak a Dayforce-hoz rendelve.</span><span class="sxs-lookup"><span data-stu-id="af1a3-517">Tax regions are mapped to Dayforce as location addresses.</span></span> <span data-ttu-id="af1a3-518">Az alapértelmezett adórégiót a dolgozó aktív beosztásával kell társítani.</span><span class="sxs-lookup"><span data-stu-id="af1a3-518">The default tax region must be associated with the worker's active position.</span></span> 

- <span data-ttu-id="af1a3-519">Adórégió (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-519">Tax region (required)</span></span>
- <span data-ttu-id="af1a3-520">Ország/régió (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-520">Country/Region (required)</span></span>
- <span data-ttu-id="af1a3-521">Állam (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-521">State (required)</span></span>
- <span data-ttu-id="af1a3-522">Megye</span><span class="sxs-lookup"><span data-stu-id="af1a3-522">County</span></span> 
- <span data-ttu-id="af1a3-523">Város (kötelező)</span><span class="sxs-lookup"><span data-stu-id="af1a3-523">City (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a><span data-ttu-id="af1a3-524">Adatok konfigurálása bérlista létrehozásához Mexikóban</span><span class="sxs-lookup"><span data-stu-id="af1a3-524">Configure your data to generate payroll in Mexico</span></span>

<span data-ttu-id="af1a3-525">Ha a fizetést generál alkalmazottaknak Mexikóban, a következő elemeket kell beállítani:</span><span class="sxs-lookup"><span data-stu-id="af1a3-525">If you're generating pay for employees in Mexico, the following elements must be configured:</span></span>

- <span data-ttu-id="af1a3-526">Részlegek szükségesek beosztásokhoz.</span><span class="sxs-lookup"><span data-stu-id="af1a3-526">Departments are required on positions.</span></span>
- <span data-ttu-id="af1a3-527">Költséghelyek pénzügyi dimenziókként kell beállítani, és az Alapértelmezett pénzügyi dimenzió karakterlánc első elemének kell lennie.</span><span class="sxs-lookup"><span data-stu-id="af1a3-527">Cost centers must be set as financial dimensions and must be the first element in the Default Financial Dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="af1a3-528">Beosztástípusok</span><span class="sxs-lookup"><span data-stu-id="af1a3-528">Job types</span></span>

<span data-ttu-id="af1a3-529">Beosztástípusok használatával a hasonló feladatok kategóriákba sorolhatók.</span><span class="sxs-lookup"><span data-stu-id="af1a3-529">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="af1a3-530">Mexikóban a Bérlista feldolgozásához feladattípusok szükségesek.</span><span class="sxs-lookup"><span data-stu-id="af1a3-530">Job types are required in order to process payroll in Mexico.</span></span> <span data-ttu-id="af1a3-531">Beosztástípusok többek között a teljes és részmunkaidős, illetve a munkabéres és az órabéres.</span><span class="sxs-lookup"><span data-stu-id="af1a3-531">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="af1a3-532">A beosztástípusok a fizetéstípusokként vannak hozzárendelve a Dayforce-hoz, melyek jelzik, hogy a munkavállaló órás vagy bérezéses.</span><span class="sxs-lookup"><span data-stu-id="af1a3-532">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="af1a3-533">A következő feladattípusok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="af1a3-533">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="af1a3-534">Feladattípus</span><span class="sxs-lookup"><span data-stu-id="af1a3-534">Job type</span></span>   | <span data-ttu-id="af1a3-535">Leírás</span><span class="sxs-lookup"><span data-stu-id="af1a3-535">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="af1a3-536">Óránként</span><span class="sxs-lookup"><span data-stu-id="af1a3-536">Hourly</span></span>     | <span data-ttu-id="af1a3-537">MX Órabér</span><span class="sxs-lookup"><span data-stu-id="af1a3-537">MX Hourly</span></span>   |
| <span data-ttu-id="af1a3-538">Bérezéses</span><span class="sxs-lookup"><span data-stu-id="af1a3-538">Salaried</span></span>   | <span data-ttu-id="af1a3-539">MX Bérezéses</span><span class="sxs-lookup"><span data-stu-id="af1a3-539">MX Salaried</span></span> |

### <a name="position-types"></a><span data-ttu-id="af1a3-540">Beosztási típusok</span><span class="sxs-lookup"><span data-stu-id="af1a3-540">Position types</span></span> 

<span data-ttu-id="af1a3-541">Ne használjon beosztástípusokat annak leírására, hogy a beosztás teljes munkaidős, részmunkaidős vagy más.</span><span class="sxs-lookup"><span data-stu-id="af1a3-541">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="af1a3-542">A feladattípusok a fizetésosztályokként vannak hozzárendelve a Dayforce-hoz, melyek jelzik, hogy a munkavállaló teljes- vagy részmunkaidős.</span><span class="sxs-lookup"><span data-stu-id="af1a3-542">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="af1a3-543">A következő beosztástípusok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="af1a3-543">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="af1a3-544">Beosztás típusa</span><span class="sxs-lookup"><span data-stu-id="af1a3-544">Position type</span></span>   | <span data-ttu-id="af1a3-545">Leírás</span><span class="sxs-lookup"><span data-stu-id="af1a3-545">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="af1a3-546">Teljes munkaidős</span><span class="sxs-lookup"><span data-stu-id="af1a3-546">Full-time</span></span>       | <span data-ttu-id="af1a3-547">Teljes munkaidős alkalmazott</span><span class="sxs-lookup"><span data-stu-id="af1a3-547">Full time employee</span></span> |
| <span data-ttu-id="af1a3-548">Részmunkaidős</span><span class="sxs-lookup"><span data-stu-id="af1a3-548">Part-time</span></span>       | <span data-ttu-id="af1a3-549">Részmunkaidős alkalmazott</span><span class="sxs-lookup"><span data-stu-id="af1a3-549">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="af1a3-550">Okkódok</span><span class="sxs-lookup"><span data-stu-id="af1a3-550">Reason codes</span></span>

<span data-ttu-id="af1a3-551">Az alkalmazottak állapotával kapcsolatos okkódok tájékoztatnak.</span><span class="sxs-lookup"><span data-stu-id="af1a3-551">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="af1a3-552">Okkódok a Dayforce-hoz állapot okaként vannak hozzárendelve, melyek jelzik egy alkalmazott beosztásában vagy alkalmazotti státuszában bekövetkezett változások okát.</span><span class="sxs-lookup"><span data-stu-id="af1a3-552">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="af1a3-553">A következő okkódok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="af1a3-553">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="af1a3-554">Okkód</span><span class="sxs-lookup"><span data-stu-id="af1a3-554">Reason code</span></span>            | <span data-ttu-id="af1a3-555">Leírás</span><span class="sxs-lookup"><span data-stu-id="af1a3-555">Description</span></span>                    | <span data-ttu-id="af1a3-556">Alkalmazandó forgatókönyvek</span><span class="sxs-lookup"><span data-stu-id="af1a3-556">Applicable scenarios</span></span> |
|------------------------|--------------------------------|----------------------|
| <span data-ttu-id="af1a3-557">DEPARTUREBEFOREPAYMENT</span><span class="sxs-lookup"><span data-stu-id="af1a3-557">DEPARTUREBEFOREPAYMENT</span></span> | <span data-ttu-id="af1a3-558">Indulás első bérlista előtt</span><span class="sxs-lookup"><span data-stu-id="af1a3-558">Departure before first payroll</span></span> | <span data-ttu-id="af1a3-559">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="af1a3-559">Terminate worker</span></span>     |
| <span data-ttu-id="af1a3-560">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="af1a3-560">RESIGNATION</span></span>            | <span data-ttu-id="af1a3-561">Felmondás</span><span class="sxs-lookup"><span data-stu-id="af1a3-561">Resignation</span></span>                    | <span data-ttu-id="af1a3-562">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="af1a3-562">Terminate worker</span></span>     |
| <span data-ttu-id="af1a3-563">PENSION</span><span class="sxs-lookup"><span data-stu-id="af1a3-563">PENSION</span></span>                | <span data-ttu-id="af1a3-564">Nyugdíj</span><span class="sxs-lookup"><span data-stu-id="af1a3-564">Pension</span></span>                        | <span data-ttu-id="af1a3-565">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="af1a3-565">Terminate worker</span></span>     |
| <span data-ttu-id="af1a3-566">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="af1a3-566">TERMINATION</span></span>            | <span data-ttu-id="af1a3-567">Befejezés</span><span class="sxs-lookup"><span data-stu-id="af1a3-567">Termination</span></span>                    | <span data-ttu-id="af1a3-568">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="af1a3-568">Terminate worker</span></span>     |
| <span data-ttu-id="af1a3-569">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="af1a3-569">RETIREMENT</span></span>             | <span data-ttu-id="af1a3-570">Megszüntetés</span><span class="sxs-lookup"><span data-stu-id="af1a3-570">Retirement</span></span>                     | <span data-ttu-id="af1a3-571">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="af1a3-571">Terminate worker</span></span>     |
| <span data-ttu-id="af1a3-572">ABSENTEE</span><span class="sxs-lookup"><span data-stu-id="af1a3-572">ABSENTEE</span></span>               | <span data-ttu-id="af1a3-573">Távollevő</span><span class="sxs-lookup"><span data-stu-id="af1a3-573">Absentee</span></span>                       | <span data-ttu-id="af1a3-574">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="af1a3-574">Terminate worker</span></span>     |
| <span data-ttu-id="af1a3-575">EGYÉB</span><span class="sxs-lookup"><span data-stu-id="af1a3-575">OTHER</span></span>                  | <span data-ttu-id="af1a3-576">Egyéb okok</span><span class="sxs-lookup"><span data-stu-id="af1a3-576">Other Reasons</span></span>                  | <span data-ttu-id="af1a3-577">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="af1a3-577">Terminate worker</span></span>     |
| <span data-ttu-id="af1a3-578">CLOSURE</span><span class="sxs-lookup"><span data-stu-id="af1a3-578">CLOSURE</span></span>                | <span data-ttu-id="af1a3-579">Üzletzárás</span><span class="sxs-lookup"><span data-stu-id="af1a3-579">Business Closure</span></span>               | <span data-ttu-id="af1a3-580">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="af1a3-580">Terminate worker</span></span>     |
| <span data-ttu-id="af1a3-581">DEATH</span><span class="sxs-lookup"><span data-stu-id="af1a3-581">DEATH</span></span>                  | <span data-ttu-id="af1a3-582">Elhalálozás</span><span class="sxs-lookup"><span data-stu-id="af1a3-582">Death</span></span>                          | <span data-ttu-id="af1a3-583">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="af1a3-583">Terminate worker</span></span>     |
| <span data-ttu-id="af1a3-584">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="af1a3-584">LEAVEOFABSENCE</span></span>         | <span data-ttu-id="af1a3-585">Szabadság</span><span class="sxs-lookup"><span data-stu-id="af1a3-585">Leave of Absence</span></span>               | <span data-ttu-id="af1a3-586">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="af1a3-586">Terminate worker</span></span>     |
| <span data-ttu-id="af1a3-587">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="af1a3-587">CONTRACTEND</span></span>            | <span data-ttu-id="af1a3-588">Szerződés vége</span><span class="sxs-lookup"><span data-stu-id="af1a3-588">End of Contract</span></span>                | <span data-ttu-id="af1a3-589">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="af1a3-589">Terminate worker</span></span>     |
| <span data-ttu-id="af1a3-590">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="af1a3-590">SALARYCHANGE</span></span>           | <span data-ttu-id="af1a3-591">Munkabér módosítása</span><span class="sxs-lookup"><span data-stu-id="af1a3-591">Change of Salary</span></span>               | <span data-ttu-id="af1a3-592">Kompenzáció</span><span class="sxs-lookup"><span data-stu-id="af1a3-592">Compensation</span></span>         |

### <a name="terms-of-employment"></a><span data-ttu-id="af1a3-593">Foglalkoztatási feltételek</span><span class="sxs-lookup"><span data-stu-id="af1a3-593">Terms of employment</span></span>

<span data-ttu-id="af1a3-594">A Foglalkoztatási feltételek foglalkoztatási feltételkategóriák létrehozására használatosak.</span><span class="sxs-lookup"><span data-stu-id="af1a3-594">Terms of employment are used to create categories of employment terms.</span></span> <span data-ttu-id="af1a3-595">A feltételek alkalmazási mutató értékekként vannak a Dayforce-hoz rendelve.</span><span class="sxs-lookup"><span data-stu-id="af1a3-595">The terms are mapped to Dayforce as employment indicator values.</span></span>

<span data-ttu-id="af1a3-596">A következő alkalmazási feltételek és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="af1a3-596">The following terms of employment and descriptions are required.</span></span>

| <span data-ttu-id="af1a3-597">Foglalkoztatási feltételek</span><span class="sxs-lookup"><span data-stu-id="af1a3-597">Terms of employment</span></span>   | <span data-ttu-id="af1a3-598">Leírás</span><span class="sxs-lookup"><span data-stu-id="af1a3-598">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="af1a3-599">Szabályos</span><span class="sxs-lookup"><span data-stu-id="af1a3-599">Regular</span></span>               | <span data-ttu-id="af1a3-600">Szabályos</span><span class="sxs-lookup"><span data-stu-id="af1a3-600">Regular</span></span>     |
| <span data-ttu-id="af1a3-601">Közvetlen</span><span class="sxs-lookup"><span data-stu-id="af1a3-601">Direct</span></span>                | <span data-ttu-id="af1a3-602">Közvetlen</span><span class="sxs-lookup"><span data-stu-id="af1a3-602">Direct</span></span>      |
| <span data-ttu-id="af1a3-603">Szakmai gyakorlat</span><span class="sxs-lookup"><span data-stu-id="af1a3-603">Internship</span></span>            | <span data-ttu-id="af1a3-604">Szakmai gyakorlat</span><span class="sxs-lookup"><span data-stu-id="af1a3-604">Internship</span></span>  |
| <span data-ttu-id="af1a3-605">Állandó</span><span class="sxs-lookup"><span data-stu-id="af1a3-605">Permanent</span></span>             | <span data-ttu-id="af1a3-606">Állandó</span><span class="sxs-lookup"><span data-stu-id="af1a3-606">Permanent</span></span>   |

### <a name="marital-status"></a><span data-ttu-id="af1a3-607">Családi állapot</span><span class="sxs-lookup"><span data-stu-id="af1a3-607">Marital status</span></span>

<span data-ttu-id="af1a3-608">Családi állapot értékei Dayforce-hoz vannak rendelve és konvertálva szükség esetén az elfogadható értékekre az integráció során.</span><span class="sxs-lookup"><span data-stu-id="af1a3-608">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="af1a3-609">Az alábbi táblázat bemutatja, hogy családi állapot értékek hogyan vannak leképezve a Dayforce -ban.</span><span class="sxs-lookup"><span data-stu-id="af1a3-609">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="af1a3-610">Talent</span><span class="sxs-lookup"><span data-stu-id="af1a3-610">Talent</span></span>                 | <span data-ttu-id="af1a3-611">Dayforce</span><span class="sxs-lookup"><span data-stu-id="af1a3-611">Dayforce</span></span>                  |
|------------------------|---------------------------|
| <span data-ttu-id="af1a3-612">Házas</span><span class="sxs-lookup"><span data-stu-id="af1a3-612">Married</span></span>                | <span data-ttu-id="af1a3-613">Házas</span><span class="sxs-lookup"><span data-stu-id="af1a3-613">Married</span></span>                   |
| <span data-ttu-id="af1a3-614">Egy</span><span class="sxs-lookup"><span data-stu-id="af1a3-614">Single</span></span>                 | <span data-ttu-id="af1a3-615">Egy</span><span class="sxs-lookup"><span data-stu-id="af1a3-615">Single</span></span>                    |
| <span data-ttu-id="af1a3-616">Özvegy</span><span class="sxs-lookup"><span data-stu-id="af1a3-616">Widowed</span></span>                | <span data-ttu-id="af1a3-617">Özvegy</span><span class="sxs-lookup"><span data-stu-id="af1a3-617">Widowed</span></span>                   |
| <span data-ttu-id="af1a3-618">Elvált</span><span class="sxs-lookup"><span data-stu-id="af1a3-618">Divorced</span></span>               | <span data-ttu-id="af1a3-619">Elvált</span><span class="sxs-lookup"><span data-stu-id="af1a3-619">Divorced</span></span>                  |
| <span data-ttu-id="af1a3-620">Bejegyzett élettársi kapcsolat</span><span class="sxs-lookup"><span data-stu-id="af1a3-620">Registered Partnership</span></span> | <span data-ttu-id="af1a3-621">Élettársi viszony</span><span class="sxs-lookup"><span data-stu-id="af1a3-621">Domestic Partnership</span></span>      |
| <span data-ttu-id="af1a3-622">Nincs</span><span class="sxs-lookup"><span data-stu-id="af1a3-622">None</span></span>                   | <span data-ttu-id="af1a3-623">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="af1a3-623">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="af1a3-624">Együttélés</span><span class="sxs-lookup"><span data-stu-id="af1a3-624">Cohabiting</span></span>             | <span data-ttu-id="af1a3-625">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="af1a3-625">*Not supported by Mexico*</span></span> |

### <a name="gender"></a><span data-ttu-id="af1a3-626">Nem</span><span class="sxs-lookup"><span data-stu-id="af1a3-626">Gender</span></span>

<span data-ttu-id="af1a3-627">A nemek a Dayforce-hoz vannak rendelve és konvertálva szükség esetén az elfogadható értékekre az integráció során.</span><span class="sxs-lookup"><span data-stu-id="af1a3-627">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="af1a3-628">Az alábbi táblázat bemutatja, hogy a nemek hogyan vannak leképezve a Dayforce-ban.</span><span class="sxs-lookup"><span data-stu-id="af1a3-628">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="af1a3-629">Talent</span><span class="sxs-lookup"><span data-stu-id="af1a3-629">Talent</span></span>       | <span data-ttu-id="af1a3-630">Dayforce</span><span class="sxs-lookup"><span data-stu-id="af1a3-630">Dayforce</span></span>                  |
|--------------|---------------------------|
| <span data-ttu-id="af1a3-631">Férfi</span><span class="sxs-lookup"><span data-stu-id="af1a3-631">Male</span></span>         | <span data-ttu-id="af1a3-632">Férfi</span><span class="sxs-lookup"><span data-stu-id="af1a3-632">Male</span></span>                      |
| <span data-ttu-id="af1a3-633">Nő</span><span class="sxs-lookup"><span data-stu-id="af1a3-633">Female</span></span>       | <span data-ttu-id="af1a3-634">Nő</span><span class="sxs-lookup"><span data-stu-id="af1a3-634">Female</span></span>                    |
| <span data-ttu-id="af1a3-635">Nem meghatározott</span><span class="sxs-lookup"><span data-stu-id="af1a3-635">Non-specific</span></span> | <span data-ttu-id="af1a3-636">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="af1a3-636">*Not supported by Mexico*</span></span> |

### <a name="payment-method"></a><span data-ttu-id="af1a3-637">Kifizetési mód</span><span class="sxs-lookup"><span data-stu-id="af1a3-637">Payment method</span></span>

<span data-ttu-id="af1a3-638">A Fizetési módok adják meg az alkalmazott és a vállalat számára az alkalmazott kifizetésének módja leírásának lehetőségét.</span><span class="sxs-lookup"><span data-stu-id="af1a3-638">Payment methods give the employee and the company a way to describe how employees will be paid.</span></span> <span data-ttu-id="af1a3-639">A Fizetési módok a Dayforce-hoz vannak rendelve és konvertálva szükség esetén az elfogadható értékekre az integráció során.</span><span class="sxs-lookup"><span data-stu-id="af1a3-639">Payment methods are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="af1a3-640">Az alábbi táblázat bemutatja, hogy a fizetés módok hogyan vannak leképezve a Dayforce-ban.</span><span class="sxs-lookup"><span data-stu-id="af1a3-640">The following table shows how payment methods are mapped to Dayforce.</span></span>

| <span data-ttu-id="af1a3-641">Talent</span><span class="sxs-lookup"><span data-stu-id="af1a3-641">Talent</span></span>             | <span data-ttu-id="af1a3-642">Dayforce</span><span class="sxs-lookup"><span data-stu-id="af1a3-642">Dayforce</span></span>                  |
|--------------------|---------------------------|
| <span data-ttu-id="af1a3-643">Készpénz</span><span class="sxs-lookup"><span data-stu-id="af1a3-643">Cash</span></span>               | <span data-ttu-id="af1a3-644">Készpénz</span><span class="sxs-lookup"><span data-stu-id="af1a3-644">Cash</span></span>                      |
| <span data-ttu-id="af1a3-645">Elektronikus fizetés</span><span class="sxs-lookup"><span data-stu-id="af1a3-645">Electronic Payment</span></span> | <span data-ttu-id="af1a3-646">Átvitel</span><span class="sxs-lookup"><span data-stu-id="af1a3-646">Transfer</span></span>                  |
| <span data-ttu-id="af1a3-647">Csekkes</span><span class="sxs-lookup"><span data-stu-id="af1a3-647">Check</span></span>              | <span data-ttu-id="af1a3-648">Csekk</span><span class="sxs-lookup"><span data-stu-id="af1a3-648">Cheque</span></span>                    |
| <span data-ttu-id="af1a3-649">Váltó</span><span class="sxs-lookup"><span data-stu-id="af1a3-649">Bank Draft</span></span>         | <span data-ttu-id="af1a3-650">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="af1a3-650">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="af1a3-651">Egyéb</span><span class="sxs-lookup"><span data-stu-id="af1a3-651">Other</span></span>              | <span data-ttu-id="af1a3-652">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="af1a3-652">*Not supported by Mexico*</span></span> |

### <a name="bank-account-type"></a><span data-ttu-id="af1a3-653">Bankszámla típusa</span><span class="sxs-lookup"><span data-stu-id="af1a3-653">Bank account type</span></span>

<span data-ttu-id="af1a3-654">Bankszámla-típusok az alkalmazottaknak történő elektronikus kifizetésekhez szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="af1a3-654">Bank account types are used for electronic payments to employees.</span></span> <span data-ttu-id="af1a3-655">Bankszámla típusa a Dayforce-ba átutalási számlaadatként van rendelve.</span><span class="sxs-lookup"><span data-stu-id="af1a3-655">Bank account types are mapped to Dayforce as transfer account information.</span></span> <span data-ttu-id="af1a3-656">A bankszámlatípusok szükség esetén konvertálva vannak az elfogadható értékekké az integráció során.</span><span class="sxs-lookup"><span data-stu-id="af1a3-656">The bank account types are translated, as appropriate, to the accepted values upon integration.</span></span>

| <span data-ttu-id="af1a3-657">Talent</span><span class="sxs-lookup"><span data-stu-id="af1a3-657">Talent</span></span>            | <span data-ttu-id="af1a3-658">Dayforce</span><span class="sxs-lookup"><span data-stu-id="af1a3-658">Dayforce</span></span>                  |
|-------------------|---------------------------|
| <span data-ttu-id="af1a3-659">Folyószámla</span><span class="sxs-lookup"><span data-stu-id="af1a3-659">Checking Account</span></span>  | <span data-ttu-id="af1a3-660">CheckingAccount</span><span class="sxs-lookup"><span data-stu-id="af1a3-660">CheckingAccount</span></span>           |
| <span data-ttu-id="af1a3-661">Bérlista elszámolási számlája</span><span class="sxs-lookup"><span data-stu-id="af1a3-661">Payroll Account</span></span>   | <span data-ttu-id="af1a3-662">PayrollAccount</span><span class="sxs-lookup"><span data-stu-id="af1a3-662">PayrollAccount</span></span>            |
| <span data-ttu-id="af1a3-663">Megtakarítási számla</span><span class="sxs-lookup"><span data-stu-id="af1a3-663">Savings Account</span></span>   | <span data-ttu-id="af1a3-664">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="af1a3-664">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="af1a3-665">BankGirot-számla</span><span class="sxs-lookup"><span data-stu-id="af1a3-665">BankGirot account</span></span> | <span data-ttu-id="af1a3-666">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="af1a3-666">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="af1a3-667">PlusGirot-számla</span><span class="sxs-lookup"><span data-stu-id="af1a3-667">PlusGirot account</span></span> | <span data-ttu-id="af1a3-668">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="af1a3-668">*Not supported by Mexico*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="af1a3-669">Bevételkódok</span><span class="sxs-lookup"><span data-stu-id="af1a3-669">Earning codes</span></span>

<span data-ttu-id="af1a3-670">A bevételkódok egyedi módon azonosítják a dolgozók által kapott fizetéstípusokat.</span><span class="sxs-lookup"><span data-stu-id="af1a3-670">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="af1a3-671">A kódoknak különböző paramétereket fednek le, amelyek a bevételekhez kapcsolódnak, például könyvelési szabályok, jelentési követelmények és bruttósítási lehetőségek.</span><span class="sxs-lookup"><span data-stu-id="af1a3-671">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="af1a3-672">Ha egy nem támogatott gyakoriság van használatban, a **Minden fizetés** gyakorisága van alapértelmezés szerint használva a kiszámításhoz.</span><span class="sxs-lookup"><span data-stu-id="af1a3-672">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="af1a3-673">Támogatott gyakoriságok</span><span class="sxs-lookup"><span data-stu-id="af1a3-673">Supported frequencies</span></span>

- <span data-ttu-id="af1a3-674">Összes</span><span class="sxs-lookup"><span data-stu-id="af1a3-674">All</span></span>
- <span data-ttu-id="af1a3-675">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="af1a3-675">EVERYPAY</span></span>
- <span data-ttu-id="af1a3-676">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="af1a3-676">EACHPAYPERIOD</span></span>
- <span data-ttu-id="af1a3-677">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="af1a3-677">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="af1a3-678">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="af1a3-678">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="af1a3-679">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="af1a3-679">1OFMTH</span></span>
- <span data-ttu-id="af1a3-680">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="af1a3-680">LASTOFMTH</span></span>
- <span data-ttu-id="af1a3-681">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="af1a3-681">2OFMTH</span></span>
- <span data-ttu-id="af1a3-682">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="af1a3-682">3OFMTH</span></span>
- <span data-ttu-id="af1a3-683">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="af1a3-683">4OFMTH</span></span>
- <span data-ttu-id="af1a3-684">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="af1a3-684">5OFMTH</span></span>
- <span data-ttu-id="af1a3-685">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="af1a3-685">1N2OFMTH</span></span>
- <span data-ttu-id="af1a3-686">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="af1a3-686">3N4OFMTH</span></span>
- <span data-ttu-id="af1a3-687">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="af1a3-687">1N3OFMTH</span></span>
- <span data-ttu-id="af1a3-688">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="af1a3-688">1N4OFMTH</span></span>
- <span data-ttu-id="af1a3-689">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="af1a3-689">2N3OFMTH</span></span>
- <span data-ttu-id="af1a3-690">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="af1a3-690">2N4OFMTH</span></span>
- <span data-ttu-id="af1a3-691">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="af1a3-691">1N2N3OFMTH</span></span>
- <span data-ttu-id="af1a3-692">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="af1a3-692">1N2N4OFMTH</span></span>
- <span data-ttu-id="af1a3-693">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="af1a3-693">1N3N4OFMTH</span></span>
- <span data-ttu-id="af1a3-694">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="af1a3-694">2N3N4OFMTH</span></span>
- <span data-ttu-id="af1a3-695">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="af1a3-695">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="af1a3-696">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="af1a3-696">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="af1a3-697">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="af1a3-697">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="af1a3-698">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="af1a3-698">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="af1a3-699">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="af1a3-699">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="af1a3-700">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="af1a3-700">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="af1a3-701">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="af1a3-701">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="af1a3-702">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="af1a3-702">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="af1a3-703">Címek</span><span class="sxs-lookup"><span data-stu-id="af1a3-703">Addresses</span></span>

<span data-ttu-id="af1a3-704">Az adott ország vagy régió, állam és megye (település) kódok specifikus formátumokat követelnek, hogy Dayforce és az országos és regionális szolgáltatók felismerjék azokat.</span><span class="sxs-lookup"><span data-stu-id="af1a3-704">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="af1a3-705">Annak ellenére, hogy a városok formátuma rugalmas, minden városnak társítva kell lennie egy államhoz.</span><span class="sxs-lookup"><span data-stu-id="af1a3-705">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="af1a3-706">Talent</span><span class="sxs-lookup"><span data-stu-id="af1a3-706">Talent</span></span>              | <span data-ttu-id="af1a3-707">Dayforce</span><span class="sxs-lookup"><span data-stu-id="af1a3-707">Dayforce</span></span>              |
|---------------------|-----------------------|
| <span data-ttu-id="af1a3-708">Ország/régió</span><span class="sxs-lookup"><span data-stu-id="af1a3-708">Country/Region</span></span>      | <span data-ttu-id="af1a3-709">Országkód</span><span class="sxs-lookup"><span data-stu-id="af1a3-709">Country Code</span></span>          |
| <span data-ttu-id="af1a3-710">Irányítószám / postai kód</span><span class="sxs-lookup"><span data-stu-id="af1a3-710">Zip/Postal Code</span></span>     | <span data-ttu-id="af1a3-711">Irányítószám</span><span class="sxs-lookup"><span data-stu-id="af1a3-711">Postal Code</span></span>           |
| <span data-ttu-id="af1a3-712">Állami</span><span class="sxs-lookup"><span data-stu-id="af1a3-712">State</span></span>               | <span data-ttu-id="af1a3-713">Államkód</span><span class="sxs-lookup"><span data-stu-id="af1a3-713">State Code</span></span>            |
| <span data-ttu-id="af1a3-714">Város</span><span class="sxs-lookup"><span data-stu-id="af1a3-714">City</span></span>                | <span data-ttu-id="af1a3-715">Város</span><span class="sxs-lookup"><span data-stu-id="af1a3-715">City</span></span>                  |
| <span data-ttu-id="af1a3-716">Megye</span><span class="sxs-lookup"><span data-stu-id="af1a3-716">County</span></span>              | <span data-ttu-id="af1a3-717">Megye (Helyhatóság)</span><span class="sxs-lookup"><span data-stu-id="af1a3-717">County (Municipality)</span></span> |
| <span data-ttu-id="af1a3-718">Utca</span><span class="sxs-lookup"><span data-stu-id="af1a3-718">Street</span></span>              | <span data-ttu-id="af1a3-719">Cím 1. sora</span><span class="sxs-lookup"><span data-stu-id="af1a3-719">Address Line 1</span></span>        |
| <span data-ttu-id="af1a3-720">Utca, házszám</span><span class="sxs-lookup"><span data-stu-id="af1a3-720">Street Number</span></span>       | <span data-ttu-id="af1a3-721">Cím 2. sora</span><span class="sxs-lookup"><span data-stu-id="af1a3-721">Address Line 2</span></span>        |
| <span data-ttu-id="af1a3-722">Épületblokk</span><span class="sxs-lookup"><span data-stu-id="af1a3-722">Building Complement</span></span> | <span data-ttu-id="af1a3-723">Cím 5. sora</span><span class="sxs-lookup"><span data-stu-id="af1a3-723">Address Line 5</span></span>        |

### <a name="passport-number"></a><span data-ttu-id="af1a3-724">Útlevél száma</span><span class="sxs-lookup"><span data-stu-id="af1a3-724">Passport number</span></span>

<span data-ttu-id="af1a3-725">Az alkalmazottak útlevél adatokat is nyilatkozhatnak.</span><span class="sxs-lookup"><span data-stu-id="af1a3-725">Employees can declare passport information.</span></span> <span data-ttu-id="af1a3-726">Az információ a **Útlevél** azonosítótípusra vonatkozik, és az alkalmazott Mexikó-specifikus adataiként van a Dayforce-ba integrálva.</span><span class="sxs-lookup"><span data-stu-id="af1a3-726">This information is of the **Passport** identification type and is integrated into Dayforce as part of an employee's Mexico-specific information.</span></span>

- <span data-ttu-id="af1a3-727">Azonosító típusa = „Útlevél”</span><span class="sxs-lookup"><span data-stu-id="af1a3-727">Identification Type = "Passport"</span></span>
- <span data-ttu-id="af1a3-728">Kibocsátás dátuma</span><span class="sxs-lookup"><span data-stu-id="af1a3-728">Issued Date</span></span>
- <span data-ttu-id="af1a3-729">Lejárat dátuma</span><span class="sxs-lookup"><span data-stu-id="af1a3-729">Expiration Date</span></span>

<span data-ttu-id="af1a3-730">Az alkalmazottak több azonosítószámot is megadhatnak az **Útlevél** azonosítótípushoz.</span><span class="sxs-lookup"><span data-stu-id="af1a3-730">Employees can declare multiple identification numbers of the **Passport** identification type.</span></span> <span data-ttu-id="af1a3-731">Azonban csak az aktuális aktív útlevélbejegyzés van integrálva a Dayforce-ba.</span><span class="sxs-lookup"><span data-stu-id="af1a3-731">However, only the current active passport entry is integrated into Dayforce.</span></span> <span data-ttu-id="af1a3-732">Ha az összes útlevélbejegyzés lejárt, a legutóbb kiállított lesz integrálva a Dayforce-ba.</span><span class="sxs-lookup"><span data-stu-id="af1a3-732">If all passport entries are expired, the passport that was most recently issued is integrated into Dayforce.</span></span>

