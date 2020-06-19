---
title: A Dayforce szolgáltatással való integráció konfigurálása
description: A Microsoft Dynamics 365 Human Resources és a Ceridian Dayforce között végbemenő integrálás több olyan konfigurációs lépésre támaszkodik, amelyeket ebben a cikkben ismertünk. A fizetési időszak feldolgozása előtt konfigurálnia kell az integrációt a Human Resources alkalmazásban és a Dayforce alkalmazásban is.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: PersonnelIntegrationConfiguration
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c66ec772ea66732e042f50081f04a6569852f211
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/04/2020
ms.locfileid: "3431291"
---
# <a name="configure-integration-with-dayforce"></a><span data-ttu-id="13958-104">A Dayforce szolgáltatással való integráció konfigurálása</span><span class="sxs-lookup"><span data-stu-id="13958-104">Configure integration with Dayforce</span></span>

<span data-ttu-id="13958-105">A Microsoft Dynamics 365 Human Resources és a Ceridian Dayforce között végbemenő integrálás több olyan konfigurációs lépésre támaszkodik, amelyeket ebben a cikkben ismertünk.</span><span class="sxs-lookup"><span data-stu-id="13958-105">The integration between Microsoft Dynamics 365 Human Resources and Ceridian Dayforce relies on several configuration steps that are described in this article.</span></span> <span data-ttu-id="13958-106">A fizetési időszak feldolgozása előtt konfigurálnia kell az integrációt a Human Resources alkalmazásban és a Dayforce alkalmazásban is.</span><span class="sxs-lookup"><span data-stu-id="13958-106">You must configure the integration in both Human Resources and Dayforce before you can process a pay run.</span></span>

<span data-ttu-id="13958-107">Ha olyan szolgáltatást használ a fizetési időszak teljesítéséhez, mint a Dayforce, engedélyeznie kell az integrációt a Human Resources alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="13958-107">When you use a service such as Dayforce to complete pay runs, you must enable the integration in Human Resources.</span></span> <span data-ttu-id="13958-108">Az integrációhoz szükségesek bizonyos adatok a Human Resources alkalmazásból.</span><span class="sxs-lookup"><span data-stu-id="13958-108">The integration requires specific data from Human Resources.</span></span> <span data-ttu-id="13958-109">Ezért ellenőriznie kell, hogy a Dayforce alkalmazáshoz hozzárendelt adatok olyan módon legyenek konfigurálva a Human Resources alkalmazásban, hogy az támogassa az integrációt.</span><span class="sxs-lookup"><span data-stu-id="13958-109">Therefore, you must verify that data that is mapped to Dayforce is configured in Human Resources in a manner that supports the integration.</span></span> <span data-ttu-id="13958-110">Az integráció a következő szélesebb adatkategóriákat használja:</span><span class="sxs-lookup"><span data-stu-id="13958-110">The integration uses the following broad categories of data:</span></span>

- <span data-ttu-id="13958-111">Emberierőforrás-adatok</span><span class="sxs-lookup"><span data-stu-id="13958-111">Human resources data</span></span>
- <span data-ttu-id="13958-112">Kompenzációadatok</span><span class="sxs-lookup"><span data-stu-id="13958-112">Compensation data</span></span>
- <span data-ttu-id="13958-113">Bérlistaadatok, mint kifizetési ciklus, fizetési időszakok és bevételkódok</span><span class="sxs-lookup"><span data-stu-id="13958-113">Payroll data, such as pay cycles, pay periods, and earning codes</span></span>
- <span data-ttu-id="13958-114">Dolgozóadatok</span><span class="sxs-lookup"><span data-stu-id="13958-114">Worker data</span></span>

<span data-ttu-id="13958-115">Ez a cikk leírja a lépéseket, amelyeket követni kell az integráció engedélyezéséhez.</span><span class="sxs-lookup"><span data-stu-id="13958-115">This article describes the steps that you must follow to enable the integration.</span></span> <span data-ttu-id="13958-116">Azt is bemutatja, hogy milyen típusú adatok és konfiguráció szükséges az integrációhoz.</span><span class="sxs-lookup"><span data-stu-id="13958-116">It also explains the types of data and the configuration details that the integration requires.</span></span>

## <a name="enable-the-integration"></a><span data-ttu-id="13958-117">Engedélyezze az integrációt</span><span class="sxs-lookup"><span data-stu-id="13958-117">Enable the integration</span></span>

<span data-ttu-id="13958-118">A Dayforce alkalmazáshoz való csatlakozáshoz a Human Resources alkalmazásban be kell kapcsolnia az integrációt és meg kell adnia a konfiguráció adatait.</span><span class="sxs-lookup"><span data-stu-id="13958-118">In Human Resources, you must turn on the integration and enter the configuration information to connect to Dayforce.</span></span> <span data-ttu-id="13958-119">Ha azt szeretné, hogy a létrehozott általános főkönyvi tranzakció importálva legyen a Microsoft Dynamics 365 Finance alkalmazásba, be kell állítania egy Microsoft Azure tárolási fiókot, majd adja meg, majd Azure tárolási kapcsolat karakterláncát a Finance alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="13958-119">If you want the general ledger transaction that is produced to be imported into Microsoft Dynamics 365 Finance, you must also set up a Microsoft Azure storage account and enter the Azure Storage connection string in Finance.</span></span>

<span data-ttu-id="13958-120">A Human Resources alkalmazásban lévő integráció bekapcsolásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="13958-120">To turn on the integration in Human Resources, follow these steps.</span></span>

1. <span data-ttu-id="13958-121">A **Rendszerfelügyelet** oldalon válassza az **Integrációkonfiguráció** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="13958-121">On the **System administration** page, select **Integration configuration**.</span></span>
2. <span data-ttu-id="13958-122">Adja meg a biztonságos fájl átviteli protokollt (FTP) végpontot és a biztonságos FTP-mappa elérési útja.</span><span class="sxs-lookup"><span data-stu-id="13958-122">Enter the secure File Transfer Protocol (FTP) endpoint and the secure FTP folder path.</span></span>
3. <span data-ttu-id="13958-123">Adja meg azon felhasználó felhasználónevét és jelszavát, aki hozzáfér a biztonságos FTP végponthoz és a mappa elérési útjához.</span><span class="sxs-lookup"><span data-stu-id="13958-123">Enter the user name and password of the user who will access the secure FTP endpoint and folder path.</span></span>
4. <span data-ttu-id="13958-124">Tesztelje a kapcsolatot szükség szerint, és állítsa a **Bérlista-integráció engedélyezése** lehetőséggel **Igenre**.</span><span class="sxs-lookup"><span data-stu-id="13958-124">Test the connection, as required, and set the **Enable payroll integration** option to **Yes**.</span></span>

<span data-ttu-id="13958-125">Ha az integráció engedélyezve van, adatexport adatcsomagok és fájlok jönnek létre, valamint a gyakoriság is be van állítva.</span><span class="sxs-lookup"><span data-stu-id="13958-125">When the integration is turned on, the data export package and files are created, and the frequency is set.</span></span> <span data-ttu-id="13958-126">Igény szerint módosíthatja a gyakoriságot.</span><span class="sxs-lookup"><span data-stu-id="13958-126">You can change this frequency as you require.</span></span>

<span data-ttu-id="13958-127">Az Azure tárolási fiókokkal és az Azure tárolási kapcsolati karakterláncokkal kapcsolatos további információkat az alábbi Azure-cikkben találja:</span><span class="sxs-lookup"><span data-stu-id="13958-127">For more information about Azure storage accounts and Azure Storage connection strings, see the following Azure articles:</span></span>

- [<span data-ttu-id="13958-128">Az Azure Storage-fiókokról</span><span class="sxs-lookup"><span data-stu-id="13958-128">About Azure storage accounts</span></span>](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [<span data-ttu-id="13958-129">Azure Storage kapcsolati karakterláncok konfigurálása</span><span class="sxs-lookup"><span data-stu-id="13958-129">Configure Azure Storage connection strings</span></span>](https://docs.microsoft.com/azure/storage/common/storage-configure-connection-string)

### <a name="technical-details-when-payroll-integration-is-enabled"></a><span data-ttu-id="13958-130">Technikai részletek a bérlista integrációjának engedélyezésekor</span><span class="sxs-lookup"><span data-stu-id="13958-130">Technical details when payroll integration is enabled</span></span>

<span data-ttu-id="13958-131">A bérlista-integráció bekapcsolása két elsődleges hatással jár:</span><span class="sxs-lookup"><span data-stu-id="13958-131">Turning on the payroll integration has two primary effects:</span></span>

- <span data-ttu-id="13958-132">Létrejön egy „bérlista-integráció exportálása” nevű adatexportálási projekt.</span><span class="sxs-lookup"><span data-stu-id="13958-132">A data export project named "Payroll integration export" is created.</span></span> <span data-ttu-id="13958-133">Ez a projekt a bérlista-integrációhoz szükséges entitásokat és mezőket tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="13958-133">This project contains the entities and fields required for the payroll integration.</span></span> <span data-ttu-id="13958-134">A projekt vizsgálatához nyissa meg a **Rendszerfelügyeletet**, válassza ki az **Adatkezelési** csempét, majd nyissa meg az adatprojektet a projektek listájából.</span><span class="sxs-lookup"><span data-stu-id="13958-134">To examine the project, go to **System administration**, select the **Data management** tile, and then open the data project from the list of projects.</span></span>
- <span data-ttu-id="13958-135">Ez a kötegelt feladat végrehajtja az adatexportálási projektet, titkosítja a létrejövő adatcsomagot, és átviszi az adatcsomag-fájlt az **Integráció konfigurációja** képernyőjén beállított SFTP végpontba.</span><span class="sxs-lookup"><span data-stu-id="13958-135">This batch job executes the data export project, encrypts the resulting data package, and transfers the data package file to the SFTP endpoint configured on the **Integration configuration** screen.</span></span>

> [!NOTE]
> <span data-ttu-id="13958-136">Az SFTP végpontra átvitt adatcsomag titkosítva van a csomag egyedi kulcsával.</span><span class="sxs-lookup"><span data-stu-id="13958-136">The data package transferred to the SFTP endpoint is encrypted using a key that is unique to the package.</span></span> <span data-ttu-id="13958-137">A kulcs egy Azure kulcstárolóban van, amely csak Ceridian számára érhető el.</span><span class="sxs-lookup"><span data-stu-id="13958-137">The key is in an Azure Key Vault that is accessible only by Ceridian.</span></span> <span data-ttu-id="13958-138">Az adatcsomag tartalmát nem lehet dekódolni és megvizsgálni.</span><span class="sxs-lookup"><span data-stu-id="13958-138">It is not possible to decrypt and examine the data package contents.</span></span> <span data-ttu-id="13958-139">Ha meg kell vizsgálnia az adatcsomag tartalmát, akkor manuálisan kell exportálnia a „Bérlista-integráció exportálása” adatprojektet, le kell töltenie, majd meg kell nyitnia.</span><span class="sxs-lookup"><span data-stu-id="13958-139">If you need to examine the contents of the data package, you need to export the "Payroll integration export" data project manually, download it, and then open it.</span></span> <span data-ttu-id="13958-140">A manuális exportálás nem alkalmazza a titkosítást, és nem viszi át a csomagot.</span><span class="sxs-lookup"><span data-stu-id="13958-140">Manual export will not apply encryption or transfer the package.</span></span>

## <a name="configure-your-data"></a><span data-ttu-id="13958-141">Adatai konfigurálása</span><span class="sxs-lookup"><span data-stu-id="13958-141">Configure your data</span></span> 

<span data-ttu-id="13958-142">A bérlista feldolgozásához konfigurálnia kell az emberierőforrás-adatokat a Human Resources alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="13958-142">To process payroll, you must configure human resource data in Human Resources.</span></span> <span data-ttu-id="13958-143">Be kell állítani a szervezeti adatokat, például a feladatokat és beosztásokat, valamint juttatásokra és a kompenzációra vonatkozó adatokat.</span><span class="sxs-lookup"><span data-stu-id="13958-143">You must set up organizational data, such as jobs and positions, together with benefits and compensation information.</span></span> <span data-ttu-id="13958-144">Ez az információ megadja a foglalkoztatásra, fizetésre és levonásokra vonatkozó információkat, melyek szükségesek az alkalmazott fizetések generálásához.</span><span class="sxs-lookup"><span data-stu-id="13958-144">This information provides the employment, pay, and deduction information that is required in order to generate employee pay.</span></span>

### <a name="human-resource-data"></a><span data-ttu-id="13958-145">Emberierőforrás-adatok</span><span class="sxs-lookup"><span data-stu-id="13958-145">Human resource data</span></span>

#### <a name="benefits"></a><span data-ttu-id="13958-146">Juttatások</span><span class="sxs-lookup"><span data-stu-id="13958-146">Benefits</span></span> 

<span data-ttu-id="13958-147">Az emberi erőforrások számos beállítási és karbantartási eszközt biztosít, amelyek segítségével beállíthatja és karbantarthatja a szervezet által a dolgozónak biztosított juttatásokat, levonásokat és dolgozói kompenzációs terveket.</span><span class="sxs-lookup"><span data-stu-id="13958-147">Human resources provides tools for the setup and maintenance of the benefits, deductions, and worker compensation plans that an organization offers or processes for its workers.</span></span>

<span data-ttu-id="13958-148">Juttatások létrehozása esetén ne felejtse el a következő adatokat és beállításokat, amelyeket a Dayforce használ.</span><span class="sxs-lookup"><span data-stu-id="13958-148">When you create benefits, keep in mind the following data and configurations that are used in Dayforce.</span></span>

##### <a name="benefit-plans"></a><span data-ttu-id="13958-149">Juttatási tervek</span><span class="sxs-lookup"><span data-stu-id="13958-149">Benefit plans</span></span>

- <span data-ttu-id="13958-150">Terv (szükséges)</span><span class="sxs-lookup"><span data-stu-id="13958-150">Plan (required)</span></span>
- <span data-ttu-id="13958-151">Típus (szükséges)</span><span class="sxs-lookup"><span data-stu-id="13958-151">Type (required)</span></span>
- <span data-ttu-id="13958-152">Bérlista hatása (szükséges)</span><span class="sxs-lookup"><span data-stu-id="13958-152">Payroll impact (required)</span></span>
- <span data-ttu-id="13958-153">Hátralékok helyreállítása</span><span class="sxs-lookup"><span data-stu-id="13958-153">Recover arrears</span></span>
- <span data-ttu-id="13958-154">Levonási módszer</span><span class="sxs-lookup"><span data-stu-id="13958-154">Deduction method</span></span>
- <span data-ttu-id="13958-155">Levonás prioritása</span><span class="sxs-lookup"><span data-stu-id="13958-155">Deduction priority</span></span>
- <span data-ttu-id="13958-156">Időszak korlátozása</span><span class="sxs-lookup"><span data-stu-id="13958-156">Limit period</span></span>
- <span data-ttu-id="13958-157">Összeghatár</span><span class="sxs-lookup"><span data-stu-id="13958-157">Limit amount</span></span>

##### <a name="benefits"></a><span data-ttu-id="13958-158">Juttatások</span><span class="sxs-lookup"><span data-stu-id="13958-158">Benefits</span></span>

- <span data-ttu-id="13958-159">Terv (szükséges)</span><span class="sxs-lookup"><span data-stu-id="13958-159">Plan (required)</span></span>
- <span data-ttu-id="13958-160">Típus (szükséges)</span><span class="sxs-lookup"><span data-stu-id="13958-160">Type (required)</span></span>
- <span data-ttu-id="13958-161">Lehetőség (szükséges)</span><span class="sxs-lookup"><span data-stu-id="13958-161">Option (required)</span></span>
- <span data-ttu-id="13958-162">Juttatás azonosítója (szükséges)</span><span class="sxs-lookup"><span data-stu-id="13958-162">Benefit ID (required)</span></span>
- <span data-ttu-id="13958-163">Gyakoriság</span><span class="sxs-lookup"><span data-stu-id="13958-163">Frequency</span></span>
- <span data-ttu-id="13958-164">Alap</span><span class="sxs-lookup"><span data-stu-id="13958-164">Basis</span></span>
- <span data-ttu-id="13958-165">Összeg vagy mérték</span><span class="sxs-lookup"><span data-stu-id="13958-165">Amount or rate</span></span>
- <span data-ttu-id="13958-166">Bevételkód</span><span class="sxs-lookup"><span data-stu-id="13958-166">Earning code</span></span>

##### <a name="supported-frequencies"></a><span data-ttu-id="13958-167">Támogatott gyakoriságok</span><span class="sxs-lookup"><span data-stu-id="13958-167">Supported frequencies</span></span> 

- <span data-ttu-id="13958-168">Heti</span><span class="sxs-lookup"><span data-stu-id="13958-168">Weekly</span></span>
- <span data-ttu-id="13958-169">Kétheti</span><span class="sxs-lookup"><span data-stu-id="13958-169">Bi-weekly</span></span>
- <span data-ttu-id="13958-170">Félhavi</span><span class="sxs-lookup"><span data-stu-id="13958-170">Semi-monthly</span></span>
- <span data-ttu-id="13958-171">Havi</span><span class="sxs-lookup"><span data-stu-id="13958-171">Monthly</span></span>

##### <a name="supported-bases"></a><span data-ttu-id="13958-172">Támogatott alapok</span><span class="sxs-lookup"><span data-stu-id="13958-172">Supported bases</span></span> 

- <span data-ttu-id="13958-173">Rögzített összeg</span><span class="sxs-lookup"><span data-stu-id="13958-173">Fixed amount</span></span>
- <span data-ttu-id="13958-174">Bevételek százaléka</span><span class="sxs-lookup"><span data-stu-id="13958-174">Percent of earnings</span></span>
- <span data-ttu-id="13958-175">Produktív órák</span><span class="sxs-lookup"><span data-stu-id="13958-175">Productive hours</span></span>

<span data-ttu-id="13958-176">A Dayforce létrehozza a következő levonásokat, a juttatási tervben definiált bérlistahatás alapján.</span><span class="sxs-lookup"><span data-stu-id="13958-176">Dayforce creates the following deductions, based on the payroll impact that is defined on the benefit plan.</span></span>

| <span data-ttu-id="13958-177">Kiválasztás a Human Resources alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="13958-177">Selection in Human Resources</span></span>        | <span data-ttu-id="13958-178">Eredmény a Dayforce-ban</span><span class="sxs-lookup"><span data-stu-id="13958-178">Result in Dayforce</span></span>                            |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="13958-179">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="13958-179">None</span></span>                       | <span data-ttu-id="13958-180">Nincs létrehozva levonás.</span><span class="sxs-lookup"><span data-stu-id="13958-180">No deduction is created.</span></span>                      |
| <span data-ttu-id="13958-181">Csak levonás</span><span class="sxs-lookup"><span data-stu-id="13958-181">Deduction only</span></span>             | <span data-ttu-id="13958-182">Alkalmazotti levonás jön létre.</span><span class="sxs-lookup"><span data-stu-id="13958-182">An employee deduction is created.</span></span>             |
| <span data-ttu-id="13958-183">Csak hozzájárulás</span><span class="sxs-lookup"><span data-stu-id="13958-183">Contribution only</span></span>          | <span data-ttu-id="13958-184">Egy alkalmazotti levonás jön létre.</span><span class="sxs-lookup"><span data-stu-id="13958-184">An employer deduction is created.</span></span>             |
| <span data-ttu-id="13958-185">Levonás és hozzájárulás</span><span class="sxs-lookup"><span data-stu-id="13958-185">Deduction and contribution</span></span> | <span data-ttu-id="13958-186">Alkalmazotti és a munkáltatói levonások jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="13958-186">Employee and employer deductions are created.</span></span> |

<span data-ttu-id="13958-187">A juttatási programok meghatározásával és kezelésével kapcsolatos további tájékoztatást a következő cikkekben találja:</span><span class="sxs-lookup"><span data-stu-id="13958-187">For more information about how to define and manage a benefits program, see the following articles:</span></span>

- [<span data-ttu-id="13958-188">Alkalmazotti juttatási program végrehajtása</span><span class="sxs-lookup"><span data-stu-id="13958-188">Deliver an employee benefits program</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [<span data-ttu-id="13958-189">Új juttatás létrehozása</span><span class="sxs-lookup"><span data-stu-id="13958-189">Create a new benefit</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [<span data-ttu-id="13958-190">Juttatásra való jogosultsági szabályok és irányelvek meghatározása</span><span class="sxs-lookup"><span data-stu-id="13958-190">Define benefit eligibility rules and policies</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [<span data-ttu-id="13958-191">Dolgozók juttatásainak felvétele és eltávolítása</span><span class="sxs-lookup"><span data-stu-id="13958-191">Enroll and remove benefits from workers</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a><span data-ttu-id="13958-192">Kompenzáció</span><span class="sxs-lookup"><span data-stu-id="13958-192">Compensation</span></span> 

<span data-ttu-id="13958-193">A kompenzációkezeléssel szabályozható az alapfizetés és a jutalmak kifizetése.</span><span class="sxs-lookup"><span data-stu-id="13958-193">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="13958-194">Egy alkalmazott fix fizetési díjalapja és érdemeken alapuló fizetése kezelhető a fix kompenzációs tervekkel.</span><span class="sxs-lookup"><span data-stu-id="13958-194">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="13958-195">Az ösztönző díjak kifizetése, például bónuszok, teljesítménydíjak, részvényopciók és kölcsönök, továbbá az egyszeri jutalmak a változó kompenzációs tervekben szabályozhatók.</span><span class="sxs-lookup"><span data-stu-id="13958-195">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span>

<span data-ttu-id="13958-196">A Dayforce a kompenzációs adatok segítségével kiszámítja az alkalmazott óradíját vagy éves díját.</span><span class="sxs-lookup"><span data-stu-id="13958-196">Dayforce uses compensation information to calculate an employee's hourly or annual rate.</span></span> <span data-ttu-id="13958-197">Fix kompenzációs tervek és a fizetési díjalap átalakítások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="13958-197">Fixed compensation plans and pay rate conversions are required.</span></span> <span data-ttu-id="13958-198">Az alkalmazottakat hozzá kell rendelni a fix kompenzációs tervhez.</span><span class="sxs-lookup"><span data-stu-id="13958-198">Employees must be associated with a fixed compensation plan.</span></span>

<span data-ttu-id="13958-199">A következő cikkekben bővebben olvashat a kompenzációs tervekről:</span><span class="sxs-lookup"><span data-stu-id="13958-199">For more information about compensation plans, see the following articles:</span></span>

- [<span data-ttu-id="13958-200">Fix kompenzációs konstrukciók létrehozása</span><span class="sxs-lookup"><span data-stu-id="13958-200">Create fixed compensation plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [<span data-ttu-id="13958-201">Változó kompenzációs konstrukciók létrehozása</span><span class="sxs-lookup"><span data-stu-id="13958-201">Create variable compensation plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [<span data-ttu-id="13958-202">Munkabér-/kompenzációs struktúra és tervek kialakítása</span><span class="sxs-lookup"><span data-stu-id="13958-202">Develop salary/compensation structure and plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [<span data-ttu-id="13958-203">Folyamatkompenzáció</span><span class="sxs-lookup"><span data-stu-id="13958-203">Process compensation</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/process-compensation)
- [<span data-ttu-id="13958-204">Kompenzációs folyamat meghatározása és eredmények kiszámítása</span><span class="sxs-lookup"><span data-stu-id="13958-204">Define compensation process and calculate results</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [<span data-ttu-id="13958-205">Alkalmazottak felvétele fix kompenzációs konstrukcióba</span><span class="sxs-lookup"><span data-stu-id="13958-205">Enroll an employee in a fixed compensation plan</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [<span data-ttu-id="13958-206">Alkalmazottak felvétele változó kompenzációs konstrukcióba</span><span class="sxs-lookup"><span data-stu-id="13958-206">Enroll an employee in a variable compensation plan</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a><span data-ttu-id="13958-207">Beosztások</span><span class="sxs-lookup"><span data-stu-id="13958-207">Jobs</span></span> 

<span data-ttu-id="13958-208">A munkakör azon feladatok és felelősségek gyűjteménye, amelyek egy adott munkát végrehajtó személytől elvártak.</span><span class="sxs-lookup"><span data-stu-id="13958-208">A job is a collection of the tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="13958-209">További információért tekintse át az alábbi cikkeket:</span><span class="sxs-lookup"><span data-stu-id="13958-209">For more information, see the following articles:</span></span>

- [<span data-ttu-id="13958-210">Feladat összetevőinek beállítása</span><span class="sxs-lookup"><span data-stu-id="13958-210">Setting up the components of a job</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-job)
- [<span data-ttu-id="13958-211">Új feladatok meghatározása</span><span class="sxs-lookup"><span data-stu-id="13958-211">Define new jobs</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a><span data-ttu-id="13958-212">Beosztások</span><span class="sxs-lookup"><span data-stu-id="13958-212">Positions</span></span>

<span data-ttu-id="13958-213">Egy beosztás egy feladat egyedi példánya.</span><span class="sxs-lookup"><span data-stu-id="13958-213">A position is an individual instance of a job.</span></span> <span data-ttu-id="13958-214">Például az „Értékesítési igazgató (Kelet)” pozíció egyike azon beosztásoknak, amelyek társíthatók az „Értékesítési igazgató” feladathoz.</span><span class="sxs-lookup"><span data-stu-id="13958-214">For example, the "Sales manager (East)" position is one of the positions that are associated with the "Sales manager" job.</span></span> <span data-ttu-id="13958-215">A beosztás létezik a részlegben.</span><span class="sxs-lookup"><span data-stu-id="13958-215">A position exists in a department.</span></span> <span data-ttu-id="13958-216">Egy beosztáshoz csak egy dolgozó rendelhető.</span><span class="sxs-lookup"><span data-stu-id="13958-216">Only one worker can be associated with each position.</span></span>

<span data-ttu-id="13958-217">A következő adatokat és konfigurációkat szem előtt tartani beosztások beállításakor:</span><span class="sxs-lookup"><span data-stu-id="13958-217">Keep the following data and configuration in mind when you set up positions:</span></span>

- <span data-ttu-id="13958-218">Beosztás (szükséges)</span><span class="sxs-lookup"><span data-stu-id="13958-218">Position (required)</span></span>
- <span data-ttu-id="13958-219">Leírás (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-219">Description (required)</span></span>
- <span data-ttu-id="13958-220">Munka (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-220">Job (required)</span></span>
- <span data-ttu-id="13958-221">Részleg (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-221">Department (required)</span></span>
- <span data-ttu-id="13958-222">Beosztás típusa (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-222">Position type (required)</span></span>
- <span data-ttu-id="13958-223">Teljes munkaidőssel egyenértékű</span><span class="sxs-lookup"><span data-stu-id="13958-223">Full-time equivalent</span></span>
- <span data-ttu-id="13958-224">Éves rendes munkaidő (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-224">Annual regular hours (required)</span></span>
- <span data-ttu-id="13958-225">Jogi személy által fizetett (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-225">Paid by legal entity (required)</span></span>
- <span data-ttu-id="13958-226">Fizetési ciklus (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-226">Pay cycle (required)</span></span>
- <span data-ttu-id="13958-227">Alapértelmezett pénzügyi dimenzió – Költséghely (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-227">Default financial dimension – Cost center (required)</span></span>
- <span data-ttu-id="13958-228">Dolgozó-hozzárendelés – dolgozó-hozzárendelés kezdete, hozzárendelés vége és okkód</span><span class="sxs-lookup"><span data-stu-id="13958-228">Worker assignment – Worker, assignment start, assignment end, reason code</span></span>

<span data-ttu-id="13958-229">A azonos osztály több beosztása társítva van az ugyanazon a feladathoz, azok össze lesznek vonva a Dayforce egyetlen pozíciójába.</span><span class="sxs-lookup"><span data-stu-id="13958-229">If multiple positions in the same department are associated with the same job, they are consolidated into a single position in Dayforce.</span></span>

<span data-ttu-id="13958-230">További információért tekintse át az alábbi cikkeket:</span><span class="sxs-lookup"><span data-stu-id="13958-230">For more information, see the following articles:</span></span>

- [<span data-ttu-id="13958-231">Munkaerő szervezése részlegek, feladatok és beosztások szerint</span><span class="sxs-lookup"><span data-stu-id="13958-231">Organize your workforce using departments, jobs, and positions</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [<span data-ttu-id="13958-232">Beosztások beállítása</span><span class="sxs-lookup"><span data-stu-id="13958-232">Set up positions</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a><span data-ttu-id="13958-233">Osztályok</span><span class="sxs-lookup"><span data-stu-id="13958-233">Departments</span></span>

<span data-ttu-id="13958-234">A részleg egy működési egység, amely a szervezet egy kategóriáját vagy működési területét képviseli.</span><span class="sxs-lookup"><span data-stu-id="13958-234">A department is an operating unit that represents a category or functional area of an organization.</span></span> <span data-ttu-id="13958-235">Egy részleg a szervezet egy konkrét területen végzett tevékenységeiért felel (például értékesítés, könyvelés, emberi erőforrások).</span><span class="sxs-lookup"><span data-stu-id="13958-235">A department is responsible for a specific area of the organization, such as sales, accounting, or human resources.</span></span> <span data-ttu-id="13958-236">A részlegek segítségével hozhatók létre jelentések a működési területekről.</span><span class="sxs-lookup"><span data-stu-id="13958-236">You can use departments to report on functional areas.</span></span> <span data-ttu-id="13958-237">A részlegeknek lehet eredménykimutatási felelőssége.</span><span class="sxs-lookup"><span data-stu-id="13958-237">Departments might have profit and loss responsibility.</span></span>

<span data-ttu-id="13958-238">További információért tekintse át az alábbi cikkeket:</span><span class="sxs-lookup"><span data-stu-id="13958-238">For more information, see the following articles:</span></span>

- [<span data-ttu-id="13958-239">Részleg létrehozása és társítása a szervezeti hierarchiához</span><span class="sxs-lookup"><span data-stu-id="13958-239">Create a department and associate it with the department hierarchy</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [<span data-ttu-id="13958-240">Új részlegek meghatározása</span><span class="sxs-lookup"><span data-stu-id="13958-240">Define new departments</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a><span data-ttu-id="13958-241">Fizetési ciklusok és fizetési időszakok</span><span class="sxs-lookup"><span data-stu-id="13958-241">Pay cycles and pay periods</span></span>

<span data-ttu-id="13958-242">A fizetési ciklus meghatározza, hogy milyen gyakran történik a bérlista folyósítása, és a dolgozók mely napokon kapnak fizetést,.</span><span class="sxs-lookup"><span data-stu-id="13958-242">A pay cycle determines how often payroll is run and the specific days when workers are paid.</span></span> <span data-ttu-id="13958-243">Például a kifizetési ciklus lehet, havi, és az alkalmazottak kaphatják a hónap utolsó napján a fizetésüket.</span><span class="sxs-lookup"><span data-stu-id="13958-243">For example, a pay cycle might be monthly, and employees might be paid on the last day of the month.</span></span> <span data-ttu-id="13958-244">Vagy a kifizetési ciklus lehet heti, és az alkalmazottak a fizetési időszak utáni kedden kaphatják fizetésüket.</span><span class="sxs-lookup"><span data-stu-id="13958-244">Alternatively, a pay cycle might be weekly, and employees might be paid on the Tuesday after the end of the pay period.</span></span> <span data-ttu-id="13958-245">Kifizetési ciklusok beosztásokhoz vannak rendelve, és szabályozzák, hogy az ebben a beosztásban lévő dolgozók mikor kapnak fizetést.</span><span class="sxs-lookup"><span data-stu-id="13958-245">Pay cycles are assigned to positions to control when workers in those positions are paid.</span></span>

<span data-ttu-id="13958-246">Miután létrehozott fizetési ciklusokat, minden egyes ciklushoz fizetési időszakot hozhat létre.</span><span class="sxs-lookup"><span data-stu-id="13958-246">After you create pay cycles, you can generate pay periods for each cycle.</span></span> <span data-ttu-id="13958-247">Minden fizetési időszakban egy alapértelmezett fizetési dátum van, amely a megadott adatokon alapul.</span><span class="sxs-lookup"><span data-stu-id="13958-247">Each pay period includes a default payment date that is based on information that you provide.</span></span> <span data-ttu-id="13958-248">Ugyanakkor az alapértelmezett fizetési dátumot a fizetési időszakban módosíthatja kivételekhez például amikor egy kifizetési dátum ünnepnapra esik.</span><span class="sxs-lookup"><span data-stu-id="13958-248">However, you can modify the default payment date in a pay period to allow for exceptions, such as when the payment date falls on a holiday.</span></span>

<span data-ttu-id="13958-249">A következő adatokat használja a Dayforce:</span><span class="sxs-lookup"><span data-stu-id="13958-249">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="13958-250">Fizetési ciklus (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-250">Pay cycle (required)</span></span>
- <span data-ttu-id="13958-251">Fizetési ciklus gyakorisága (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-251">Pay cycle frequency (required)</span></span>
- <span data-ttu-id="13958-252">Az időszak kezdő dátuma (az első fizetési időszak szükséges)</span><span class="sxs-lookup"><span data-stu-id="13958-252">Period start date (first pay period required)</span></span>
- <span data-ttu-id="13958-253">Alapértelmezett fizetési dátum (az első fizetési időszak szükséges)</span><span class="sxs-lookup"><span data-stu-id="13958-253">Default payment date (first pay period required)</span></span>

<span data-ttu-id="13958-254">Ez az információ Dayforceba fizetési csoportokként van integrálva országonként vagy régiónként le van választva egyes kifizetési ciklusokhoz.</span><span class="sxs-lookup"><span data-stu-id="13958-254">This information is integrated with Dayforce as pay groups, and is separated by country or region for each pay cycle.</span></span> <span data-ttu-id="13958-255">Legalább egy fizetési időszakot kell létrehozni az integráció előtt.</span><span class="sxs-lookup"><span data-stu-id="13958-255">At least one pay period must be generated before integration.</span></span> <span data-ttu-id="13958-256">A Dayforce fizetési csoportnaptárakat és kifizetési dátumokat hoz létre az első fizetési időszak kezdő dátuma és az alapértelmezett fizetési dátum alapján, amelyek a Human Resources alkalmazásban vannak beállítva.</span><span class="sxs-lookup"><span data-stu-id="13958-256">Dayforce generates pay group calendars and payment dates, based on the start date of the first pay period and the default payment date that is set up in Human Resources.</span></span>

#### <a name="earning-codes"></a><span data-ttu-id="13958-257">Bevételkódok</span><span class="sxs-lookup"><span data-stu-id="13958-257">Earning codes</span></span>

<span data-ttu-id="13958-258">A bevételkódok egyedi módon azonosítják a dolgozók által kapott fizetéstípusokat.</span><span class="sxs-lookup"><span data-stu-id="13958-258">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="13958-259">A kódoknak különböző paraméterei vannak, amelyek a bevételekhez kapcsolódnak, például könyvelési szabályok, jelentési követelmények és bruttósítási lehetőségek.</span><span class="sxs-lookup"><span data-stu-id="13958-259">The codes have various parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span>

<span data-ttu-id="13958-260">A következő adatokat használja a Dayforce:</span><span class="sxs-lookup"><span data-stu-id="13958-260">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="13958-261">Bevételkód (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-261">Earning Code (required)</span></span>
- <span data-ttu-id="13958-262">Leírás</span><span class="sxs-lookup"><span data-stu-id="13958-262">Description</span></span>
- <span data-ttu-id="13958-263">Mértékegység</span><span class="sxs-lookup"><span data-stu-id="13958-263">Unit of measure</span></span>
- <span data-ttu-id="13958-264">Produktív</span><span class="sxs-lookup"><span data-stu-id="13958-264">Productive</span></span>

### <a name="worker-data"></a><span data-ttu-id="13958-265">Dolgozóadatok</span><span class="sxs-lookup"><span data-stu-id="13958-265">Worker data</span></span>

<span data-ttu-id="13958-266">A dolgozók különböző típusaihoz tartozó rekordok, melyek fontosak az emberi erőforrásoknak és a bérlistarendszerekhez.</span><span class="sxs-lookup"><span data-stu-id="13958-266">Records for the various types of workers that you have are important to your human resources and payroll systems.</span></span> <span data-ttu-id="13958-267">A bevitt információk felhasználhatók az dolgozói és személyes adatok nyilvántartására.</span><span class="sxs-lookup"><span data-stu-id="13958-267">The information that you enter can be used to track workers and personal information.</span></span>

<span data-ttu-id="13958-268">A dolgozók következő adatait tarthatja karban:</span><span class="sxs-lookup"><span data-stu-id="13958-268">You can maintain the following information for workers:</span></span>

- <span data-ttu-id="13958-269">**Alapvető** – A dolgozók alapvető információi, például a kapcsolattartási adatok, demográfiai adatok azonosító adatok, családi adatok, a katonai szolgálat állapota, kiküldetésekre vonatkozó adatok, illetve személyes és rendkívüli kapcsolattartók.</span><span class="sxs-lookup"><span data-stu-id="13958-269">**Basic** – Maintain basic information about a worker, such as contact information, demographic information, identification information, family information, military service status, expatriate information, and personal and emergency contacts.</span></span>
- <span data-ttu-id="13958-270">**Foglalkoztatás** – Információk a dolgozó munkaviszonyáról, például a vállalati vagy szervezeti kapcsolat, hozzárendelt pozíció, kezdő és záró dátumok, munkajogosultság, foglalkoztatás feltételei, nyugdíj, szabadság és áthelyezéssel kapcsolatos információk.</span><span class="sxs-lookup"><span data-stu-id="13958-270">**Employment** – Maintain information about a worker's employment, such as company or organization affiliation, position assignment, start and end dates, work eligibility, terms of employment, pension, vacation, and relocation information.</span></span>
- <span data-ttu-id="13958-271">**Szabadság és a távollét** – A dolgozó távolléteinek kezelése, például a munkaidő-naptárak, a távolléti tranzakciók és távollét beállítása.</span><span class="sxs-lookup"><span data-stu-id="13958-271">**Leave and absence** – Maintain information about a worker's absences, such as working calendars, absence transactions, and absence setup.</span></span>
- <span data-ttu-id="13958-272">**Kompenzáció és bérlista** – dolgozói kompenzációs tervek és bérlistainformációk kezelése, például felvétel konstrukciója, jutalmak, teljesítmény, jutalék, adózási információk, nyugdíj és fizetéslevonások.</span><span class="sxs-lookup"><span data-stu-id="13958-272">**Compensation and payroll** – Maintain information about a worker's compensation plans and payroll information, such as plan enrollment, awards, performance, commission, tax information, retirement, and salary deductions.</span></span>

<span data-ttu-id="13958-273">A dolgozóinformációk létrehozása esetén ne felejtse el a következő adatokat és beállításokat, amelyeket a Dayforce használ.</span><span class="sxs-lookup"><span data-stu-id="13958-273">When you enter worker information, keep in mind the following data and configurations that are used in Dayforce.</span></span>

#### <a name="general-information"></a><span data-ttu-id="13958-274">Általános információk</span><span class="sxs-lookup"><span data-stu-id="13958-274">General information</span></span>

- <span data-ttu-id="13958-275">Személyzeti szám (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-275">Personnel number (required)</span></span>
- <span data-ttu-id="13958-276">Utónév (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-276">First name (required)</span></span>
- <span data-ttu-id="13958-277">Vezetéknév (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-277">Last name (required)</span></span>
- <span data-ttu-id="13958-278">Második keresztnév</span><span class="sxs-lookup"><span data-stu-id="13958-278">Middle name</span></span>
- <span data-ttu-id="13958-279">Szolgálati idő dátuma</span><span class="sxs-lookup"><span data-stu-id="13958-279">Seniority date</span></span>
- <span data-ttu-id="13958-280">Más néven</span><span class="sxs-lookup"><span data-stu-id="13958-280">Known as</span></span>

#### <a name="personal-information"></a><span data-ttu-id="13958-281">Személyes információ</span><span class="sxs-lookup"><span data-stu-id="13958-281">Personal information</span></span>

- <span data-ttu-id="13958-282">Családi állapot (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-282">Marital status (required)</span></span>
- <span data-ttu-id="13958-283">Születési dátum (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-283">Birth date (required)</span></span>
- <span data-ttu-id="13958-284">Nem (szükséges)</span><span class="sxs-lookup"><span data-stu-id="13958-284">Gender (required)</span></span>
- <span data-ttu-id="13958-285">Fogyatékkal élő személy</span><span class="sxs-lookup"><span data-stu-id="13958-285">Person with disabilities</span></span>
- <span data-ttu-id="13958-286">Állampolgárság ország régió (csak a Mexikó)</span><span class="sxs-lookup"><span data-stu-id="13958-286">Nationality country region (only for Mexico)</span></span>

#### <a name="address-information"></a><span data-ttu-id="13958-287">Címadatok</span><span class="sxs-lookup"><span data-stu-id="13958-287">Address information</span></span>

- <span data-ttu-id="13958-288">Elsődleges (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-288">Primary (required)</span></span>
- <span data-ttu-id="13958-289">Ország/régiót (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-289">Country/region (required)</span></span>
- <span data-ttu-id="13958-290">Irányítószámot (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-290">Postal code (required)</span></span>
- <span data-ttu-id="13958-291">Utca, házszám (kötelező) (csak Mexikó esetén)</span><span class="sxs-lookup"><span data-stu-id="13958-291">Street Number (required) (Only for Mexico)</span></span>
- <span data-ttu-id="13958-292">Épületblokk (csak a Mexikó)</span><span class="sxs-lookup"><span data-stu-id="13958-292">Building Complement (Only for Mexico)</span></span>
- <span data-ttu-id="13958-293">Város (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-293">City (required)</span></span>
- <span data-ttu-id="13958-294">Állam (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-294">State (required)</span></span>
- <span data-ttu-id="13958-295">Megye (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-295">County (required)</span></span>

#### <a name="contact-information"></a><span data-ttu-id="13958-296">Névjegy adatai</span><span class="sxs-lookup"><span data-stu-id="13958-296">Contact information</span></span> 

- <span data-ttu-id="13958-297">Elsődleges (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-297">Primary (required)</span></span>
- <span data-ttu-id="13958-298">Kapcsolattartó száma (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-298">Contact number (required)</span></span>
- <span data-ttu-id="13958-299">Mellék</span><span class="sxs-lookup"><span data-stu-id="13958-299">Extension</span></span>

#### <a name="payroll-information-and-earning-codes"></a><span data-ttu-id="13958-300">Bérlistaadatok és bevételkódok</span><span class="sxs-lookup"><span data-stu-id="13958-300">Payroll information and earning codes</span></span>

<span data-ttu-id="13958-301">Alkalmazottak hozzárendelhetők meghatározott bevételekhez adott fizetési gyakorisággal, és magadható elsődleges fizetési mód.</span><span class="sxs-lookup"><span data-stu-id="13958-301">Employees may be assigned specific earnings at a given frequency of payment and have a preferred payment method.</span></span> <span data-ttu-id="13958-302">A következő mezőket a Dayforce arra használja, hogy garantálja, hogy ezeket a preferenciákat és beállításokat használja.</span><span class="sxs-lookup"><span data-stu-id="13958-302">The following fields are used in Dayforce to help guarantee that those preferences and settings are used.</span></span>

##### <a name="earning-codes"></a><span data-ttu-id="13958-303">Bevételkódok</span><span class="sxs-lookup"><span data-stu-id="13958-303">Earning codes</span></span>

- <span data-ttu-id="13958-304">Beosztás (szükséges)</span><span class="sxs-lookup"><span data-stu-id="13958-304">Position (required)</span></span>
- <span data-ttu-id="13958-305">Bevételkód (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-305">Earning Code (required)</span></span>
- <span data-ttu-id="13958-306">Gyakoriság (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-306">Frequency (required)</span></span>
- <span data-ttu-id="13958-307">Összeg (szükséges)</span><span class="sxs-lookup"><span data-stu-id="13958-307">Amount (required)</span></span>

##### <a name="payroll-information"></a><span data-ttu-id="13958-308">Bérlistaadatok</span><span class="sxs-lookup"><span data-stu-id="13958-308">Payroll information</span></span>

- <span data-ttu-id="13958-309">Kifizetési mód</span><span class="sxs-lookup"><span data-stu-id="13958-309">Payment Method</span></span>
- <span data-ttu-id="13958-310">Gazdasági régió (szükséges)</span><span class="sxs-lookup"><span data-stu-id="13958-310">Economic Region (required)</span></span>
- <span data-ttu-id="13958-311">Alkalmazott juttatásainak azonosítója</span><span class="sxs-lookup"><span data-stu-id="13958-311">Employee Benefits ID</span></span>
- <span data-ttu-id="13958-312">Nemzeti azonosító (szükséges)</span><span class="sxs-lookup"><span data-stu-id="13958-312">National ID Number (required)</span></span>
- <span data-ttu-id="13958-313">Katonai szolgálat száma</span><span class="sxs-lookup"><span data-stu-id="13958-313">Military Service Number</span></span>
- <span data-ttu-id="13958-314">Műszakazonosító (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-314">Shift ID (required)</span></span>
- <span data-ttu-id="13958-315">Adószám (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-315">Tax Number (required)</span></span>
- <span data-ttu-id="13958-316">Szakszervezeti azonosító (szükséges)</span><span class="sxs-lookup"><span data-stu-id="13958-316">Union ID (required)</span></span>
- <span data-ttu-id="13958-317">Munkanap azonosítója (szükséges)</span><span class="sxs-lookup"><span data-stu-id="13958-317">Work Day ID (required)</span></span>
- <span data-ttu-id="13958-318">Munkavállalási engedély száma</span><span class="sxs-lookup"><span data-stu-id="13958-318">Work Permit Number</span></span>

> [!NOTE]
> <span data-ttu-id="13958-319">A fizetési módhoz Mexikó támogatja a **Készpénzt**, **Csekket** (a vállalat fizikai csekkjét és az **Elektronikus fizetést**.</span><span class="sxs-lookup"><span data-stu-id="13958-319">For the payment method, Mexico supports **Cash**, **Check** (the company's physical check), and **Electronic Payment**.</span></span> <span data-ttu-id="13958-320">Ha nincs fizetési mód van megadva, alapértelmezés szerint a **Csekk** használt.</span><span class="sxs-lookup"><span data-stu-id="13958-320">If np payment method is specified, **Check** is used by default.</span></span>

#### <a name="employment-details"></a><span data-ttu-id="13958-321">Foglalkoztatás részletei</span><span class="sxs-lookup"><span data-stu-id="13958-321">Employment details</span></span>

<span data-ttu-id="13958-322">Foglalkoztatási előzményei kulcsfontosságú információkat tartalmaznak a munkavállaók felvételi, elbocsátási, és újbóli felvétele állapotával kapcsolatosan a Dayforce-ban.</span><span class="sxs-lookup"><span data-stu-id="13958-322">Employment detail history is used as key information to derive an employee's hire, termination, and rehire statuses in Dayforce.</span></span> <span data-ttu-id="13958-323">Dayforce egyszerre csak egy aktív foglalkoztatásrekordot tesz lehetővé.</span><span class="sxs-lookup"><span data-stu-id="13958-323">Dayforce supports only one active employment record at a time.</span></span>

- <span data-ttu-id="13958-324">Foglalkoztatás kezdődátuma (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-324">Employment start date (required)</span></span>
- <span data-ttu-id="13958-325">Munkaviszony záró dátuma</span><span class="sxs-lookup"><span data-stu-id="13958-325">Employment end date</span></span>
- <span data-ttu-id="13958-326">Kezdő dátum</span><span class="sxs-lookup"><span data-stu-id="13958-326">Start date</span></span>
- <span data-ttu-id="13958-327">Módosított kezdési időpont</span><span class="sxs-lookup"><span data-stu-id="13958-327">Adjusted start date</span></span>
- <span data-ttu-id="13958-328">Munkaviszony megszűnésének dátuma (megszűntetéskor kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-328">Termination date (required upon termination)</span></span>
- <span data-ttu-id="13958-329">Felmondás oka (megszűntetéskor kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-329">Termination reason (required upon termination)</span></span>

<span data-ttu-id="13958-330">Az alkalmazott legfontosabb dátumai a következő adatokból vannak származtatva.</span><span class="sxs-lookup"><span data-stu-id="13958-330">An employee's key dates are derived by using the following information.</span></span>

| <span data-ttu-id="13958-331">Emberi erőforrások</span><span class="sxs-lookup"><span data-stu-id="13958-331">Human Resources</span></span>                | <span data-ttu-id="13958-332">Dayforce</span><span class="sxs-lookup"><span data-stu-id="13958-332">Dayforce</span></span>                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="13958-333">Legutóbbi felvételi dátum</span><span class="sxs-lookup"><span data-stu-id="13958-333">Most recent hire date</span></span> | <span data-ttu-id="13958-334">Foglalkoztatás kezdete az aktuális nem megszűntetett előzményrekordra</span><span class="sxs-lookup"><span data-stu-id="13958-334">Employment start of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="13958-335">Munkaviszony megszűnésének dátuma</span><span class="sxs-lookup"><span data-stu-id="13958-335">Termination date</span></span>      | <span data-ttu-id="13958-336">Foglalkoztatás befejezése az aktuális nem megszűntetett előzményrekordra</span><span class="sxs-lookup"><span data-stu-id="13958-336">Termination date of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="13958-337">Kezdő dátum</span><span class="sxs-lookup"><span data-stu-id="13958-337">Start date</span></span>            | <span data-ttu-id="13958-338">Módosított kezdési időpont, kezdődátum vagy foglalkoztatás kezdete az aktuális nem aktív előzményrekordra</span><span class="sxs-lookup"><span data-stu-id="13958-338">Adjusted start date, start date, or employment start of current non-active employment history record</span></span> |
| <span data-ttu-id="13958-339">Eredeti felvételi dátum</span><span class="sxs-lookup"><span data-stu-id="13958-339">Original hire date</span></span>    | <span data-ttu-id="13958-340">Foglalkoztatás kezdete legkorábbi foglalkoztatási előzményrekordra</span><span class="sxs-lookup"><span data-stu-id="13958-340">Employment start of earliest employment history record</span></span>                                               |

#### <a name="compensation"></a><span data-ttu-id="13958-341">Kompenzáció</span><span class="sxs-lookup"><span data-stu-id="13958-341">Compensation</span></span>

<span data-ttu-id="13958-342">Egy fix kompenzációs tervet kell társítani minden alkalmazott elsődleges pozíciójához az alkalmazási időszak alatt.</span><span class="sxs-lookup"><span data-stu-id="13958-342">A fixed compensation plan must be associated with every employee's primary position throughout an employment period.</span></span> <span data-ttu-id="13958-343">Az időszak a belépés dátumával (vagy a foglalkoztatás kezdő dátumával) kezdődik, és a munkaviszony megszűnéséig tart .</span><span class="sxs-lookup"><span data-stu-id="13958-343">This period starts on the date that the employee was hired (or the employment start date) and continues until termination.</span></span>

- <span data-ttu-id="13958-344">Érvényesség dátuma (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-344">Effective Date (required)</span></span>
- <span data-ttu-id="13958-345">Lejárati dátum</span><span class="sxs-lookup"><span data-stu-id="13958-345">Expiration date</span></span>
- <span data-ttu-id="13958-346">Fizetési díjalap (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-346">Pay Rate (required)</span></span>
- <span data-ttu-id="13958-347">Fizetési díjalapok átalakításai (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-347">Pay Rate Conversions (required)</span></span>
- <span data-ttu-id="13958-348">Évi egyenérték (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-348">Annual equivalent (required)</span></span>
- <span data-ttu-id="13958-349">Óránkénti egyenérték (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-349">Hourly equivalent (required)</span></span>

<span data-ttu-id="13958-350">Ha az óránkénti alkalmazottnak több beosztása van, az elsődleges beosztásához tartozó fix kompenzációja importálva lesz a Dayforce-ba, alkalmazott szintű alapdíj/-fizetés.</span><span class="sxs-lookup"><span data-stu-id="13958-350">If an hourly employee has multiple positions, the fixed compensation of the primary position is imported into Dayforce as the employee-level base rate/salary.</span></span> <span data-ttu-id="13958-351">A nem elsődleges beosztások esetén, az óránkénti díj a megfelelő pozícióba lesz mentve Dayforce-ban.</span><span class="sxs-lookup"><span data-stu-id="13958-351">For non-primary positions, the hourly rate is saved to the corresponding position in Dayforce.</span></span>

<span data-ttu-id="13958-352">Ha a fizetett alkalmazott több beosztással rendelkezik, a összesített óradíj és éves fizetés származtatva lesz az összes aktív beosztásból mint az alkalmazotti szintű alapdíj/-fizetés.</span><span class="sxs-lookup"><span data-stu-id="13958-352">If a salaried employee has multiple positions, the cumulative hour rate and annual salary across all active positions are derived and used as the employee-level base rate/salary.</span></span>

#### <a name="identification-numbers"></a><span data-ttu-id="13958-353">Azonosítószámok</span><span class="sxs-lookup"><span data-stu-id="13958-353">Identification numbers</span></span>

##### <a name="social-security-identifier"></a><span data-ttu-id="13958-354">Társadalombiztosítási azonosító</span><span class="sxs-lookup"><span data-stu-id="13958-354">Social Security identifier</span></span> 

<span data-ttu-id="13958-355">Minden alkalmazottnak kell egy elsődleges azonosítóval rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="13958-355">Every employee must have one primary identifier.</span></span> <span data-ttu-id="13958-356">Ez az azonosító legyen **TAJ-szám** azonosítótípus kell legyen.</span><span class="sxs-lookup"><span data-stu-id="13958-356">This identifier must be of **SSN** identification type.</span></span> <span data-ttu-id="13958-357">A Dayforce-ban automatikusan van származtatva az alkalmazott társadalombiztosítási azonosítójából, mely a felvételhez szükséges.</span><span class="sxs-lookup"><span data-stu-id="13958-357">In Dayforce, it's automatically derived as the employee's Social Security identifier that is required for hire.</span></span>

- <span data-ttu-id="13958-358">Elsődleges (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-358">Primary (required)</span></span>
- <span data-ttu-id="13958-359">Azonosító típusa = „TAJ-szám”</span><span class="sxs-lookup"><span data-stu-id="13958-359">Identification Type = "SSN"</span></span>
- <span data-ttu-id="13958-360">Kibocsátás dátuma</span><span class="sxs-lookup"><span data-stu-id="13958-360">Issued Date</span></span>
- <span data-ttu-id="13958-361">Lejárat dátuma</span><span class="sxs-lookup"><span data-stu-id="13958-361">Expiration Date</span></span>

<span data-ttu-id="13958-362">Az alkalmazottak több azonosítószámot is megadhatnak **TAJ-szám** azonosítótípushoz.</span><span class="sxs-lookup"><span data-stu-id="13958-362">Employees can declare multiple identification numbers of the **SSN** identification type.</span></span> <span data-ttu-id="13958-363">Azonban csak az **Elsődlegesként** megjelölt rekord van integrálva Dayforce-ba, függetlenül attól, hogy a szám aktív vagy lejárt.</span><span class="sxs-lookup"><span data-stu-id="13958-363">However, only the record that is marked as **Primary** is integrated into Dayforce, regardless of whether the number is active or expired.</span></span>

#### <a name="bank-accounts-and-disbursements"></a><span data-ttu-id="13958-364">Bankszámlák és kifizetések</span><span class="sxs-lookup"><span data-stu-id="13958-364">Bank accounts and disbursements</span></span>

<span data-ttu-id="13958-365">Érvényes bankszámlaadatokat meg kell adni minden olyan alkalmazotthoz, aki úgy dönt, hogy a banki átutalással kéri fizetését.</span><span class="sxs-lookup"><span data-stu-id="13958-365">Valid bank account information must be entered for any employee who chooses to be paid via bank account transfers.</span></span>

| <span data-ttu-id="13958-366">Emberi erőforrások</span><span class="sxs-lookup"><span data-stu-id="13958-366">Human Resources</span></span>                         | <span data-ttu-id="13958-367">Dayforce</span><span class="sxs-lookup"><span data-stu-id="13958-367">Dayforce</span></span>                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="13958-368">Bankszámlaszám (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-368">Bank account number (required)</span></span> |                                                                                                             |
| <span data-ttu-id="13958-369">SWIFT-kód (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-369">SWIFT code (required)</span></span>          | <span data-ttu-id="13958-370">**Bankazonosító** ez a mező Mexikóban történő bérlistafeldolgozáskor használatos.</span><span class="sxs-lookup"><span data-stu-id="13958-370">**Bank ID** field used when processing payroll in Mexico.</span></span>                                                             |
| <span data-ttu-id="13958-371">Ágazati szám (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-371">Branch number (required)</span></span>       |                                                                                                             |
| <span data-ttu-id="13958-372">Bankszámla típusa (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-372">Bank account type (required)</span></span>   | <span data-ttu-id="13958-373">**Számlatípus** ez a mező Mexikóban történő bérlistafeldolgozáskor használatos.</span><span class="sxs-lookup"><span data-stu-id="13958-373">**Account type** field used when processing payroll in Mexico.</span></span> <span data-ttu-id="13958-374">Támogatott értékek: **Folyószámla** és **Bérlista**</span><span class="sxs-lookup"><span data-stu-id="13958-374">Supported values include **Checking** and **Payroll**.</span></span> |

> [!NOTE]
> <span data-ttu-id="13958-375">Alkalmazottak, akik úgy döntenek, hogy a banki átutaláson keresztülkérik fizetésük, meg kell adniuk egy hivatkozást egy jogi személyhez tartozó egyenlegszámlához, melynek elsődleges címének Mexikóban kell lennie és egy Mexikói bank érvényes bankszámlájához van társítva.</span><span class="sxs-lookup"><span data-stu-id="13958-375">Employees who choose to be paid via bank account transfers must provide a link to a remainder account that is under a legal entity that has its primary address in Mexico and associated with a valid bank account from a Mexican bank.</span></span> <span data-ttu-id="13958-376">Minden egyéb nem egyenlegszámla figyelmen kívül lesz hagyva.</span><span class="sxs-lookup"><span data-stu-id="13958-376">All other non-remainder accounts are ignored.</span></span>

#### <a name="address-information"></a><span data-ttu-id="13958-377">Címadatok</span><span class="sxs-lookup"><span data-stu-id="13958-377">Address information</span></span>

<span data-ttu-id="13958-378">Minden alkalmazottnak kell egy elsődleges hellyel rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="13958-378">Every employee must have one primary location.</span></span> <span data-ttu-id="13958-379">A Dayforce-ban ezen hely alapján van meghatározva az alkalmazott elsődleges tartózkodási helye adózási célokból.</span><span class="sxs-lookup"><span data-stu-id="13958-379">In Dayforce, this location is used to determine the employee's primary residence for tax purposes.</span></span>

- <span data-ttu-id="13958-380">Elsődleges (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-380">Primary (required)</span></span>
- <span data-ttu-id="13958-381">Ország/régiót (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-381">Country/region (required)</span></span>
- <span data-ttu-id="13958-382">Irányítószám/postai kód (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-382">Zip/postal code (required)</span></span>
- <span data-ttu-id="13958-383">Utca (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-383">Street (required)</span></span>
- <span data-ttu-id="13958-384">Házszám (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-384">Street Number (required)</span></span>
- <span data-ttu-id="13958-385">Épületblokk</span><span class="sxs-lookup"><span data-stu-id="13958-385">Building Complement</span></span>
- <span data-ttu-id="13958-386">Város (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-386">City (required)</span></span>
- <span data-ttu-id="13958-387">Állam (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-387">State (required)</span></span>
- <span data-ttu-id="13958-388">Megye (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-388">County (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a><span data-ttu-id="13958-389">Az adatok konfigurálása bérlista létrehozásához az Egyesült Államokban és Kanadában</span><span class="sxs-lookup"><span data-stu-id="13958-389">Configure your data to generate payroll in United States and Canada</span></span>

<span data-ttu-id="13958-390">Ha a fizetést generálása alkalmazottaknak az Egyesült Államokban és Kanadában, a következő elemeket kell beállítani:</span><span class="sxs-lookup"><span data-stu-id="13958-390">If you're generating pay for employees in the United States and Canada, the following elements must be configured:</span></span>

- <span data-ttu-id="13958-391">Részlegek szükségesek beosztásokhoz.</span><span class="sxs-lookup"><span data-stu-id="13958-391">Departments are required on positions.</span></span>
- <span data-ttu-id="13958-392">Költséghelyek pénzügyi dimenziókként kell beállítani, és az alapértelmezett pénzügyi dimenzió karakterlánc első elemének kell lennie.</span><span class="sxs-lookup"><span data-stu-id="13958-392">Cost centers must be set as financial dimensions and must be the first element in the default financial dimension string.</span></span>

> [!NOTE] 
> <span data-ttu-id="13958-393">Konfigurálhatja a Human Resources alkalmazást úgy, hogy a beosztásokhoz kötelező legyen beállítani részleget.</span><span class="sxs-lookup"><span data-stu-id="13958-393">You can configure Human Resources to require that Positions specify a Department.</span></span> <span data-ttu-id="13958-394">Ehhez kattintson a **Emberi erőforrások megosztott beosztásai > Beosztások > Részlegek szükségesek beosztásokhoz.** elemre.</span><span class="sxs-lookup"><span data-stu-id="13958-394">To do this, go to **Human Resources Shared Positions > Positions > Require departments on positions**.</span></span> <span data-ttu-id="13958-395">Azt ajánljuk, hogy ezt a beállítást tartassa be az integráció során.</span><span class="sxs-lookup"><span data-stu-id="13958-395">We recommend that this setting be enforced for the integration.</span></span>

### <a name="job-types"></a><span data-ttu-id="13958-396">Feladattípusok</span><span class="sxs-lookup"><span data-stu-id="13958-396">Job types</span></span>

<span data-ttu-id="13958-397">Beosztástípusok használatával a hasonló feladatok kategóriákba sorolhatók.</span><span class="sxs-lookup"><span data-stu-id="13958-397">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="13958-398">A beosztástípusok szükségesek az Egyesült Államokban és Kanadában a bérlisták feldolgozásához.</span><span class="sxs-lookup"><span data-stu-id="13958-398">Job types are required in order to process payroll in the United States and Canada.</span></span> <span data-ttu-id="13958-399">Beosztástípusok többek között a teljes és részmunkaidős, illetve a munkabéres és az órabéres.</span><span class="sxs-lookup"><span data-stu-id="13958-399">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="13958-400">A beosztástípusok a fizetéstípusokként vannak hozzárendelve a Dayforce-hoz, melyek jelzik, hogy a munkavállaló órás vagy bérezéses.</span><span class="sxs-lookup"><span data-stu-id="13958-400">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="13958-401">A következő feladattípusok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="13958-401">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="13958-402">Feladattípus</span><span class="sxs-lookup"><span data-stu-id="13958-402">Job type</span></span>   | <span data-ttu-id="13958-403">Leírás</span><span class="sxs-lookup"><span data-stu-id="13958-403">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="13958-404">Óránként</span><span class="sxs-lookup"><span data-stu-id="13958-404">Hourly</span></span>     | <span data-ttu-id="13958-405">Óránként</span><span class="sxs-lookup"><span data-stu-id="13958-405">Hourly</span></span>      |
| <span data-ttu-id="13958-406">Bérezéses</span><span class="sxs-lookup"><span data-stu-id="13958-406">Salaried</span></span>   | <span data-ttu-id="13958-407">Bérezéses</span><span class="sxs-lookup"><span data-stu-id="13958-407">Salaried</span></span>    |

### <a name="position-types"></a><span data-ttu-id="13958-408">Beosztási típusok</span><span class="sxs-lookup"><span data-stu-id="13958-408">Position types</span></span> 

<span data-ttu-id="13958-409">Ne használjon beosztástípusokat annak leírására, hogy a beosztás teljes munkaidős, részmunkaidős vagy más.</span><span class="sxs-lookup"><span data-stu-id="13958-409">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="13958-410">A feladattípusok a fizetésosztályokként vannak hozzárendelve a Dayforce-hoz, melyek jelzik, hogy a munkavállaló teljes- vagy részmunkaidős.</span><span class="sxs-lookup"><span data-stu-id="13958-410">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="13958-411">A következő beosztástípusok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="13958-411">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="13958-412">Beosztás típusa</span><span class="sxs-lookup"><span data-stu-id="13958-412">Position type</span></span>   | <span data-ttu-id="13958-413">Leírás</span><span class="sxs-lookup"><span data-stu-id="13958-413">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="13958-414">Teljes munkaidős</span><span class="sxs-lookup"><span data-stu-id="13958-414">Full-time</span></span>       | <span data-ttu-id="13958-415">Teljes munkaidős alkalmazott</span><span class="sxs-lookup"><span data-stu-id="13958-415">Full time employee</span></span> |
| <span data-ttu-id="13958-416">Részmunkaidős</span><span class="sxs-lookup"><span data-stu-id="13958-416">Part-time</span></span>       | <span data-ttu-id="13958-417">Részmunkaidős alkalmazott</span><span class="sxs-lookup"><span data-stu-id="13958-417">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="13958-418">Okkódok</span><span class="sxs-lookup"><span data-stu-id="13958-418">Reason codes</span></span>

<span data-ttu-id="13958-419">Az alkalmazottak állapotával kapcsolatos okkódok tájékoztatnak.</span><span class="sxs-lookup"><span data-stu-id="13958-419">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="13958-420">Okkódok a Dayforce-hoz állapot okaként vannak hozzárendelve, melyek jelzik egy alkalmazott beosztásában vagy alkalmazotti státuszában bekövetkezett változások okát.</span><span class="sxs-lookup"><span data-stu-id="13958-420">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="13958-421">A következő okkódok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="13958-421">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="13958-422">Okkód</span><span class="sxs-lookup"><span data-stu-id="13958-422">Reason code</span></span>    | <span data-ttu-id="13958-423">Leírás</span><span class="sxs-lookup"><span data-stu-id="13958-423">Description</span></span>      | <span data-ttu-id="13958-424">Alkalmazandó forgatókönyvek</span><span class="sxs-lookup"><span data-stu-id="13958-424">Applicable scenarios</span></span> |
|----------------|------------------|----------------------|
| <span data-ttu-id="13958-425">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="13958-425">RESIGNATION</span></span>    | <span data-ttu-id="13958-426">Felmondás</span><span class="sxs-lookup"><span data-stu-id="13958-426">Resignation</span></span>      | <span data-ttu-id="13958-427">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="13958-427">Terminate worker</span></span>     |
| <span data-ttu-id="13958-428">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="13958-428">TERMINATION</span></span>    | <span data-ttu-id="13958-429">Befejezés</span><span class="sxs-lookup"><span data-stu-id="13958-429">Termination</span></span>      | <span data-ttu-id="13958-430">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="13958-430">Terminate worker</span></span>     |
| <span data-ttu-id="13958-431">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="13958-431">RETIREMENT</span></span>     | <span data-ttu-id="13958-432">Megszüntetés</span><span class="sxs-lookup"><span data-stu-id="13958-432">Retirement</span></span>       | <span data-ttu-id="13958-433">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="13958-433">Terminate worker</span></span>     |
| <span data-ttu-id="13958-434">EGYÉB</span><span class="sxs-lookup"><span data-stu-id="13958-434">OTHER</span></span>          | <span data-ttu-id="13958-435">Egyéb okok</span><span class="sxs-lookup"><span data-stu-id="13958-435">Other Reasons</span></span>    | <span data-ttu-id="13958-436">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="13958-436">Terminate worker</span></span>     |
| <span data-ttu-id="13958-437">DEATH</span><span class="sxs-lookup"><span data-stu-id="13958-437">DEATH</span></span>          | <span data-ttu-id="13958-438">Elhalálozás</span><span class="sxs-lookup"><span data-stu-id="13958-438">Death</span></span>            | <span data-ttu-id="13958-439">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="13958-439">Terminate worker</span></span>     |
| <span data-ttu-id="13958-440">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="13958-440">LEAVEOFABSENCE</span></span> | <span data-ttu-id="13958-441">Szabadság</span><span class="sxs-lookup"><span data-stu-id="13958-441">Leave of Absence</span></span> | <span data-ttu-id="13958-442">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="13958-442">Terminate worker</span></span>     |
| <span data-ttu-id="13958-443">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="13958-443">CONTRACTEND</span></span>    | <span data-ttu-id="13958-444">Szerződés vége</span><span class="sxs-lookup"><span data-stu-id="13958-444">End of Contract</span></span>  | <span data-ttu-id="13958-445">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="13958-445">Terminate worker</span></span>     |
| <span data-ttu-id="13958-446">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="13958-446">SALARYCHANGE</span></span>   | <span data-ttu-id="13958-447">Munkabér módosítása</span><span class="sxs-lookup"><span data-stu-id="13958-447">Change of Salary</span></span> | <span data-ttu-id="13958-448">Kompenzáció</span><span class="sxs-lookup"><span data-stu-id="13958-448">Compensation</span></span>         |

### <a name="marital-status"></a><span data-ttu-id="13958-449">Családi állapot</span><span class="sxs-lookup"><span data-stu-id="13958-449">Marital status</span></span>

<span data-ttu-id="13958-450">Családi állapot értékei Dayforce-hoz vannak rendelve és konvertálva szükség esetén az elfogadható értékekre az integráció során.</span><span class="sxs-lookup"><span data-stu-id="13958-450">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="13958-451">Az alábbi táblázat bemutatja, hogy családi állapot értékek hogyan vannak leképezve a Dayforce -ban.</span><span class="sxs-lookup"><span data-stu-id="13958-451">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="13958-452">Emberi erőforrások</span><span class="sxs-lookup"><span data-stu-id="13958-452">Human Resources</span></span>                 | <span data-ttu-id="13958-453">Dayforce</span><span class="sxs-lookup"><span data-stu-id="13958-453">Dayforce</span></span>             |
|------------------------|----------------------|
| <span data-ttu-id="13958-454">Nős/férjezett</span><span class="sxs-lookup"><span data-stu-id="13958-454">Married</span></span>                | <span data-ttu-id="13958-455">Nős/férjezett</span><span class="sxs-lookup"><span data-stu-id="13958-455">Married</span></span>              |
| <span data-ttu-id="13958-456">Egy</span><span class="sxs-lookup"><span data-stu-id="13958-456">Single</span></span>                 | <span data-ttu-id="13958-457">Egy</span><span class="sxs-lookup"><span data-stu-id="13958-457">Single</span></span>               |
| <span data-ttu-id="13958-458">Özvegy</span><span class="sxs-lookup"><span data-stu-id="13958-458">Widowed</span></span>                | <span data-ttu-id="13958-459">Özvegy</span><span class="sxs-lookup"><span data-stu-id="13958-459">Widowed</span></span>              |
| <span data-ttu-id="13958-460">Elvált</span><span class="sxs-lookup"><span data-stu-id="13958-460">Divorced</span></span>               | <span data-ttu-id="13958-461">Elvált</span><span class="sxs-lookup"><span data-stu-id="13958-461">Divorced</span></span>             |
| <span data-ttu-id="13958-462">Bejegyzett élettársi kapcsolat</span><span class="sxs-lookup"><span data-stu-id="13958-462">Registered Partnership</span></span> | <span data-ttu-id="13958-463">Élettársi viszony</span><span class="sxs-lookup"><span data-stu-id="13958-463">Domestic Partnership</span></span> |
| <span data-ttu-id="13958-464">Nincs</span><span class="sxs-lookup"><span data-stu-id="13958-464">None</span></span>                   | <span data-ttu-id="13958-465">Nincs</span><span class="sxs-lookup"><span data-stu-id="13958-465">None</span></span>                 |
| <span data-ttu-id="13958-466">Együttélés</span><span class="sxs-lookup"><span data-stu-id="13958-466">Cohabiting</span></span>             | <span data-ttu-id="13958-467">Együttélés</span><span class="sxs-lookup"><span data-stu-id="13958-467">Cohabiting</span></span>           |

### <a name="gender"></a><span data-ttu-id="13958-468">Nem</span><span class="sxs-lookup"><span data-stu-id="13958-468">Gender</span></span>

<span data-ttu-id="13958-469">A nemek a Dayforce-hoz vannak rendelve és konvertálva szükség esetén az elfogadható értékekre az integráció során.</span><span class="sxs-lookup"><span data-stu-id="13958-469">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="13958-470">Az alábbi táblázat bemutatja, hogy a nemek hogyan vannak leképezve a Dayforce-ban.</span><span class="sxs-lookup"><span data-stu-id="13958-470">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="13958-471">Emberi erőforrások</span><span class="sxs-lookup"><span data-stu-id="13958-471">Human Resources</span></span>       | <span data-ttu-id="13958-472">Dayforce</span><span class="sxs-lookup"><span data-stu-id="13958-472">Dayforce</span></span>        |
|--------------|-----------------|
| <span data-ttu-id="13958-473">Férfi</span><span class="sxs-lookup"><span data-stu-id="13958-473">Male</span></span>         | <span data-ttu-id="13958-474">Férfi</span><span class="sxs-lookup"><span data-stu-id="13958-474">Male</span></span>            |
| <span data-ttu-id="13958-475">Nő</span><span class="sxs-lookup"><span data-stu-id="13958-475">Female</span></span>       | <span data-ttu-id="13958-476">Nő</span><span class="sxs-lookup"><span data-stu-id="13958-476">Female</span></span>          |
| <span data-ttu-id="13958-477">Nem meghatározott</span><span class="sxs-lookup"><span data-stu-id="13958-477">Non-specific</span></span> | <span data-ttu-id="13958-478">*Nem támogatott*</span><span class="sxs-lookup"><span data-stu-id="13958-478">*Not supported*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="13958-479">Bevételkódok</span><span class="sxs-lookup"><span data-stu-id="13958-479">Earning codes</span></span>

<span data-ttu-id="13958-480">A bevételkódok egyedi módon azonosítják a dolgozók által kapott fizetéstípusokat.</span><span class="sxs-lookup"><span data-stu-id="13958-480">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="13958-481">A kódoknak különböző paramétereket fednek le, amelyek a bevételekhez kapcsolódnak, például könyvelési szabályok, jelentési követelmények és bruttósítási lehetőségek.</span><span class="sxs-lookup"><span data-stu-id="13958-481">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="13958-482">Ha egy nem támogatott gyakoriság van használatban, a **Minden fizetés** gyakorisága van alapértelmezés szerint használva a kiszámításhoz.</span><span class="sxs-lookup"><span data-stu-id="13958-482">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="13958-483">Támogatott gyakoriságok</span><span class="sxs-lookup"><span data-stu-id="13958-483">Supported frequencies</span></span>

- <span data-ttu-id="13958-484">Összes</span><span class="sxs-lookup"><span data-stu-id="13958-484">All</span></span>
- <span data-ttu-id="13958-485">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="13958-485">EVERYPAY</span></span>
- <span data-ttu-id="13958-486">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="13958-486">EACHPAYPERIOD</span></span>
- <span data-ttu-id="13958-487">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="13958-487">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="13958-488">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="13958-488">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="13958-489">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="13958-489">1OFMTH</span></span>
- <span data-ttu-id="13958-490">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="13958-490">LASTOFMTH</span></span>
- <span data-ttu-id="13958-491">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="13958-491">2OFMTH</span></span>
- <span data-ttu-id="13958-492">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="13958-492">3OFMTH</span></span>
- <span data-ttu-id="13958-493">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="13958-493">4OFMTH</span></span>
- <span data-ttu-id="13958-494">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="13958-494">5OFMTH</span></span>
- <span data-ttu-id="13958-495">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="13958-495">1N2OFMTH</span></span>
- <span data-ttu-id="13958-496">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="13958-496">3N4OFMTH</span></span>
- <span data-ttu-id="13958-497">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="13958-497">1N3OFMTH</span></span>
- <span data-ttu-id="13958-498">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="13958-498">1N4OFMTH</span></span>
- <span data-ttu-id="13958-499">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="13958-499">2N3OFMTH</span></span>
- <span data-ttu-id="13958-500">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="13958-500">2N4OFMTH</span></span>
- <span data-ttu-id="13958-501">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="13958-501">1N2N3OFMTH</span></span>
- <span data-ttu-id="13958-502">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="13958-502">1N2N4OFMTH</span></span>
- <span data-ttu-id="13958-503">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="13958-503">1N3N4OFMTH</span></span>
- <span data-ttu-id="13958-504">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="13958-504">2N3N4OFMTH</span></span>
- <span data-ttu-id="13958-505">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="13958-505">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="13958-506">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="13958-506">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="13958-507">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="13958-507">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="13958-508">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="13958-508">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="13958-509">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="13958-509">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="13958-510">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="13958-510">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="13958-511">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="13958-511">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="13958-512">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="13958-512">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="13958-513">Címek</span><span class="sxs-lookup"><span data-stu-id="13958-513">Addresses</span></span>

<span data-ttu-id="13958-514">Az adott ország vagy régió, állam és megye (település) kódok specifikus formátumokat követelnek, hogy Dayforce és az országos és regionális szolgáltatók felismerjék azokat.</span><span class="sxs-lookup"><span data-stu-id="13958-514">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="13958-515">Annak ellenére, hogy a városok formátuma rugalmas, minden városnak társítva kell lennie egy államhoz.</span><span class="sxs-lookup"><span data-stu-id="13958-515">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="13958-516">Emberi erőforrások</span><span class="sxs-lookup"><span data-stu-id="13958-516">Human Resources</span></span>          | <span data-ttu-id="13958-517">Dayforce</span><span class="sxs-lookup"><span data-stu-id="13958-517">Dayforce</span></span>              |
|-----------------|-----------------------|
| <span data-ttu-id="13958-518">Ország/régió</span><span class="sxs-lookup"><span data-stu-id="13958-518">Country/Region</span></span>  | <span data-ttu-id="13958-519">Országkód</span><span class="sxs-lookup"><span data-stu-id="13958-519">Country Code</span></span>          |
| <span data-ttu-id="13958-520">Irányítószám / postai kód</span><span class="sxs-lookup"><span data-stu-id="13958-520">Zip/Postal Code</span></span> | <span data-ttu-id="13958-521">Irányítószám</span><span class="sxs-lookup"><span data-stu-id="13958-521">Postal Code</span></span>           |
| <span data-ttu-id="13958-522">Állami</span><span class="sxs-lookup"><span data-stu-id="13958-522">State</span></span>           | <span data-ttu-id="13958-523">Államkód</span><span class="sxs-lookup"><span data-stu-id="13958-523">State Code</span></span>            |
| <span data-ttu-id="13958-524">Város</span><span class="sxs-lookup"><span data-stu-id="13958-524">City</span></span>            | <span data-ttu-id="13958-525">Város</span><span class="sxs-lookup"><span data-stu-id="13958-525">City</span></span>                  |
| <span data-ttu-id="13958-526">Megye</span><span class="sxs-lookup"><span data-stu-id="13958-526">County</span></span>          | <span data-ttu-id="13958-527">Megye (Helyhatóság)</span><span class="sxs-lookup"><span data-stu-id="13958-527">County (Municipality)</span></span> |
| <span data-ttu-id="13958-528">Utca</span><span class="sxs-lookup"><span data-stu-id="13958-528">Street</span></span>          | <span data-ttu-id="13958-529">Cím 1. sora</span><span class="sxs-lookup"><span data-stu-id="13958-529">Address Line 1</span></span>        |

### <a name="tax-regions"></a><span data-ttu-id="13958-530">Adórégiók</span><span class="sxs-lookup"><span data-stu-id="13958-530">Tax regions</span></span>

<span data-ttu-id="13958-531">Az adórégiók a megfelelő adó megállapítására szolgálnak, amelyet a bérlista létrehozásakor kell alkalmazni.</span><span class="sxs-lookup"><span data-stu-id="13958-531">Tax regions are used to determine the appropriate tax that should be applied during payroll generation.</span></span> <span data-ttu-id="13958-532">Az adórégiók helycímként vannak a Dayforce-hoz rendelve.</span><span class="sxs-lookup"><span data-stu-id="13958-532">Tax regions are mapped to Dayforce as location addresses.</span></span> <span data-ttu-id="13958-533">Az alapértelmezett adórégiót a dolgozó aktív beosztásával kell társítani.</span><span class="sxs-lookup"><span data-stu-id="13958-533">The default tax region must be associated with the worker's active position.</span></span> 

- <span data-ttu-id="13958-534">Adórégió (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-534">Tax region (required)</span></span>
- <span data-ttu-id="13958-535">Ország/régió (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-535">Country/Region (required)</span></span>
- <span data-ttu-id="13958-536">Állam (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-536">State (required)</span></span>
- <span data-ttu-id="13958-537">Megye</span><span class="sxs-lookup"><span data-stu-id="13958-537">County</span></span> 
- <span data-ttu-id="13958-538">Város (kötelező)</span><span class="sxs-lookup"><span data-stu-id="13958-538">City (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a><span data-ttu-id="13958-539">Adatok konfigurálása bérlista létrehozásához Mexikóban</span><span class="sxs-lookup"><span data-stu-id="13958-539">Configure your data to generate payroll in Mexico</span></span>

<span data-ttu-id="13958-540">Ha a fizetést generál alkalmazottaknak Mexikóban, a következő elemeket kell beállítani:</span><span class="sxs-lookup"><span data-stu-id="13958-540">If you're generating pay for employees in Mexico, the following elements must be configured:</span></span>

- <span data-ttu-id="13958-541">Részlegek szükségesek beosztásokhoz.</span><span class="sxs-lookup"><span data-stu-id="13958-541">Departments are required on positions.</span></span>
- <span data-ttu-id="13958-542">Költséghelyek pénzügyi dimenziókként kell beállítani, és az Alapértelmezett pénzügyi dimenzió karakterlánc első elemének kell lennie.</span><span class="sxs-lookup"><span data-stu-id="13958-542">Cost centers must be set as financial dimensions and must be the first element in the Default Financial Dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="13958-543">Beosztástípusok</span><span class="sxs-lookup"><span data-stu-id="13958-543">Job types</span></span>

<span data-ttu-id="13958-544">Beosztástípusok használatával a hasonló feladatok kategóriákba sorolhatók.</span><span class="sxs-lookup"><span data-stu-id="13958-544">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="13958-545">Mexikóban a Bérlista feldolgozásához feladattípusok szükségesek.</span><span class="sxs-lookup"><span data-stu-id="13958-545">Job types are required in order to process payroll in Mexico.</span></span> <span data-ttu-id="13958-546">Beosztástípusok többek között a teljes és részmunkaidős, illetve a munkabéres és az órabéres.</span><span class="sxs-lookup"><span data-stu-id="13958-546">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="13958-547">A beosztástípusok a fizetéstípusokként vannak hozzárendelve a Dayforce-hoz, melyek jelzik, hogy a munkavállaló órás vagy bérezéses.</span><span class="sxs-lookup"><span data-stu-id="13958-547">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="13958-548">A következő feladattípusok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="13958-548">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="13958-549">Feladattípus</span><span class="sxs-lookup"><span data-stu-id="13958-549">Job type</span></span>   | <span data-ttu-id="13958-550">Leírás</span><span class="sxs-lookup"><span data-stu-id="13958-550">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="13958-551">Óránként</span><span class="sxs-lookup"><span data-stu-id="13958-551">Hourly</span></span>     | <span data-ttu-id="13958-552">MX Órabér</span><span class="sxs-lookup"><span data-stu-id="13958-552">MX Hourly</span></span>   |
| <span data-ttu-id="13958-553">Bérezéses</span><span class="sxs-lookup"><span data-stu-id="13958-553">Salaried</span></span>   | <span data-ttu-id="13958-554">MX Bérezéses</span><span class="sxs-lookup"><span data-stu-id="13958-554">MX Salaried</span></span> |

### <a name="position-types"></a><span data-ttu-id="13958-555">Beosztási típusok</span><span class="sxs-lookup"><span data-stu-id="13958-555">Position types</span></span> 

<span data-ttu-id="13958-556">Ne használjon beosztástípusokat annak leírására, hogy a beosztás teljes munkaidős, részmunkaidős vagy más.</span><span class="sxs-lookup"><span data-stu-id="13958-556">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="13958-557">A feladattípusok a fizetésosztályokként vannak hozzárendelve a Dayforce-hoz, melyek jelzik, hogy a munkavállaló teljes- vagy részmunkaidős.</span><span class="sxs-lookup"><span data-stu-id="13958-557">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="13958-558">A következő beosztástípusok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="13958-558">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="13958-559">Beosztás típusa</span><span class="sxs-lookup"><span data-stu-id="13958-559">Position type</span></span>   | <span data-ttu-id="13958-560">Leírás</span><span class="sxs-lookup"><span data-stu-id="13958-560">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="13958-561">Teljes munkaidős</span><span class="sxs-lookup"><span data-stu-id="13958-561">Full-time</span></span>       | <span data-ttu-id="13958-562">Teljes munkaidős alkalmazott</span><span class="sxs-lookup"><span data-stu-id="13958-562">Full time employee</span></span> |
| <span data-ttu-id="13958-563">Részmunkaidős</span><span class="sxs-lookup"><span data-stu-id="13958-563">Part-time</span></span>       | <span data-ttu-id="13958-564">Részmunkaidős alkalmazott</span><span class="sxs-lookup"><span data-stu-id="13958-564">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="13958-565">Okkódok</span><span class="sxs-lookup"><span data-stu-id="13958-565">Reason codes</span></span>

<span data-ttu-id="13958-566">Az alkalmazottak állapotával kapcsolatos okkódok tájékoztatnak.</span><span class="sxs-lookup"><span data-stu-id="13958-566">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="13958-567">Okkódok a Dayforce-hoz állapot okaként vannak hozzárendelve, melyek jelzik egy alkalmazott beosztásában vagy alkalmazotti státuszában bekövetkezett változások okát.</span><span class="sxs-lookup"><span data-stu-id="13958-567">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="13958-568">A következő okkódok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="13958-568">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="13958-569">Okkód</span><span class="sxs-lookup"><span data-stu-id="13958-569">Reason code</span></span>            | <span data-ttu-id="13958-570">Leírás</span><span class="sxs-lookup"><span data-stu-id="13958-570">Description</span></span>                    | <span data-ttu-id="13958-571">Alkalmazandó forgatókönyvek</span><span class="sxs-lookup"><span data-stu-id="13958-571">Applicable scenarios</span></span> |
|------------------------|--------------------------------|----------------------|
| <span data-ttu-id="13958-572">DEPARTUREBEFOREPAYMENT</span><span class="sxs-lookup"><span data-stu-id="13958-572">DEPARTUREBEFOREPAYMENT</span></span> | <span data-ttu-id="13958-573">Indulás első bérlista előtt</span><span class="sxs-lookup"><span data-stu-id="13958-573">Departure before first payroll</span></span> | <span data-ttu-id="13958-574">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="13958-574">Terminate worker</span></span>     |
| <span data-ttu-id="13958-575">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="13958-575">RESIGNATION</span></span>            | <span data-ttu-id="13958-576">Felmondás</span><span class="sxs-lookup"><span data-stu-id="13958-576">Resignation</span></span>                    | <span data-ttu-id="13958-577">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="13958-577">Terminate worker</span></span>     |
| <span data-ttu-id="13958-578">PENSION</span><span class="sxs-lookup"><span data-stu-id="13958-578">PENSION</span></span>                | <span data-ttu-id="13958-579">Nyugdíj</span><span class="sxs-lookup"><span data-stu-id="13958-579">Pension</span></span>                        | <span data-ttu-id="13958-580">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="13958-580">Terminate worker</span></span>     |
| <span data-ttu-id="13958-581">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="13958-581">TERMINATION</span></span>            | <span data-ttu-id="13958-582">Befejezés</span><span class="sxs-lookup"><span data-stu-id="13958-582">Termination</span></span>                    | <span data-ttu-id="13958-583">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="13958-583">Terminate worker</span></span>     |
| <span data-ttu-id="13958-584">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="13958-584">RETIREMENT</span></span>             | <span data-ttu-id="13958-585">Megszüntetés</span><span class="sxs-lookup"><span data-stu-id="13958-585">Retirement</span></span>                     | <span data-ttu-id="13958-586">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="13958-586">Terminate worker</span></span>     |
| <span data-ttu-id="13958-587">ABSENTEE</span><span class="sxs-lookup"><span data-stu-id="13958-587">ABSENTEE</span></span>               | <span data-ttu-id="13958-588">Távollevő</span><span class="sxs-lookup"><span data-stu-id="13958-588">Absentee</span></span>                       | <span data-ttu-id="13958-589">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="13958-589">Terminate worker</span></span>     |
| <span data-ttu-id="13958-590">EGYÉB</span><span class="sxs-lookup"><span data-stu-id="13958-590">OTHER</span></span>                  | <span data-ttu-id="13958-591">Egyéb okok</span><span class="sxs-lookup"><span data-stu-id="13958-591">Other Reasons</span></span>                  | <span data-ttu-id="13958-592">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="13958-592">Terminate worker</span></span>     |
| <span data-ttu-id="13958-593">CLOSURE</span><span class="sxs-lookup"><span data-stu-id="13958-593">CLOSURE</span></span>                | <span data-ttu-id="13958-594">Üzletzárás</span><span class="sxs-lookup"><span data-stu-id="13958-594">Business Closure</span></span>               | <span data-ttu-id="13958-595">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="13958-595">Terminate worker</span></span>     |
| <span data-ttu-id="13958-596">DEATH</span><span class="sxs-lookup"><span data-stu-id="13958-596">DEATH</span></span>                  | <span data-ttu-id="13958-597">Elhalálozás</span><span class="sxs-lookup"><span data-stu-id="13958-597">Death</span></span>                          | <span data-ttu-id="13958-598">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="13958-598">Terminate worker</span></span>     |
| <span data-ttu-id="13958-599">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="13958-599">LEAVEOFABSENCE</span></span>         | <span data-ttu-id="13958-600">Szabadság</span><span class="sxs-lookup"><span data-stu-id="13958-600">Leave of Absence</span></span>               | <span data-ttu-id="13958-601">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="13958-601">Terminate worker</span></span>     |
| <span data-ttu-id="13958-602">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="13958-602">CONTRACTEND</span></span>            | <span data-ttu-id="13958-603">Szerződés vége</span><span class="sxs-lookup"><span data-stu-id="13958-603">End of Contract</span></span>                | <span data-ttu-id="13958-604">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="13958-604">Terminate worker</span></span>     |
| <span data-ttu-id="13958-605">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="13958-605">SALARYCHANGE</span></span>           | <span data-ttu-id="13958-606">Munkabér módosítása</span><span class="sxs-lookup"><span data-stu-id="13958-606">Change of Salary</span></span>               | <span data-ttu-id="13958-607">Kompenzáció</span><span class="sxs-lookup"><span data-stu-id="13958-607">Compensation</span></span>         |

### <a name="terms-of-employment"></a><span data-ttu-id="13958-608">Foglalkoztatási feltételek</span><span class="sxs-lookup"><span data-stu-id="13958-608">Terms of employment</span></span>

<span data-ttu-id="13958-609">A Foglalkoztatási feltételek foglalkoztatási feltételkategóriák létrehozására használatosak.</span><span class="sxs-lookup"><span data-stu-id="13958-609">Terms of employment are used to create categories of employment terms.</span></span> <span data-ttu-id="13958-610">A feltételek alkalmazási mutató értékekként vannak a Dayforce-hoz rendelve.</span><span class="sxs-lookup"><span data-stu-id="13958-610">The terms are mapped to Dayforce as employment indicator values.</span></span>

<span data-ttu-id="13958-611">A következő alkalmazási feltételek és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="13958-611">The following terms of employment and descriptions are required.</span></span>

| <span data-ttu-id="13958-612">Foglalkoztatási feltételek</span><span class="sxs-lookup"><span data-stu-id="13958-612">Terms of employment</span></span>   | <span data-ttu-id="13958-613">Leírás</span><span class="sxs-lookup"><span data-stu-id="13958-613">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="13958-614">Szabályos</span><span class="sxs-lookup"><span data-stu-id="13958-614">Regular</span></span>               | <span data-ttu-id="13958-615">Szabályos</span><span class="sxs-lookup"><span data-stu-id="13958-615">Regular</span></span>     |
| <span data-ttu-id="13958-616">Közvetlen</span><span class="sxs-lookup"><span data-stu-id="13958-616">Direct</span></span>                | <span data-ttu-id="13958-617">Közvetlen</span><span class="sxs-lookup"><span data-stu-id="13958-617">Direct</span></span>      |
| <span data-ttu-id="13958-618">Szakmai gyakorlat</span><span class="sxs-lookup"><span data-stu-id="13958-618">Internship</span></span>            | <span data-ttu-id="13958-619">Szakmai gyakorlat</span><span class="sxs-lookup"><span data-stu-id="13958-619">Internship</span></span>  |
| <span data-ttu-id="13958-620">Állandó</span><span class="sxs-lookup"><span data-stu-id="13958-620">Permanent</span></span>             | <span data-ttu-id="13958-621">Állandó</span><span class="sxs-lookup"><span data-stu-id="13958-621">Permanent</span></span>   |

### <a name="marital-status"></a><span data-ttu-id="13958-622">Családi állapot</span><span class="sxs-lookup"><span data-stu-id="13958-622">Marital status</span></span>

<span data-ttu-id="13958-623">Családi állapot értékei Dayforce-hoz vannak rendelve és konvertálva szükség esetén az elfogadható értékekre az integráció során.</span><span class="sxs-lookup"><span data-stu-id="13958-623">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="13958-624">Az alábbi táblázat bemutatja, hogy családi állapot értékek hogyan vannak leképezve a Dayforce -ban.</span><span class="sxs-lookup"><span data-stu-id="13958-624">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="13958-625">Emberi erőforrások</span><span class="sxs-lookup"><span data-stu-id="13958-625">Human Resources</span></span>                 | <span data-ttu-id="13958-626">Dayforce</span><span class="sxs-lookup"><span data-stu-id="13958-626">Dayforce</span></span>                  |
|------------------------|---------------------------|
| <span data-ttu-id="13958-627">Nős/férjezett</span><span class="sxs-lookup"><span data-stu-id="13958-627">Married</span></span>                | <span data-ttu-id="13958-628">Nős/férjezett</span><span class="sxs-lookup"><span data-stu-id="13958-628">Married</span></span>                   |
| <span data-ttu-id="13958-629">Egy</span><span class="sxs-lookup"><span data-stu-id="13958-629">Single</span></span>                 | <span data-ttu-id="13958-630">Egy</span><span class="sxs-lookup"><span data-stu-id="13958-630">Single</span></span>                    |
| <span data-ttu-id="13958-631">Özvegy</span><span class="sxs-lookup"><span data-stu-id="13958-631">Widowed</span></span>                | <span data-ttu-id="13958-632">Özvegy</span><span class="sxs-lookup"><span data-stu-id="13958-632">Widowed</span></span>                   |
| <span data-ttu-id="13958-633">Elvált</span><span class="sxs-lookup"><span data-stu-id="13958-633">Divorced</span></span>               | <span data-ttu-id="13958-634">Elvált</span><span class="sxs-lookup"><span data-stu-id="13958-634">Divorced</span></span>                  |
| <span data-ttu-id="13958-635">Bejegyzett élettársi kapcsolat</span><span class="sxs-lookup"><span data-stu-id="13958-635">Registered Partnership</span></span> | <span data-ttu-id="13958-636">Élettársi viszony</span><span class="sxs-lookup"><span data-stu-id="13958-636">Domestic Partnership</span></span>      |
| <span data-ttu-id="13958-637">Nincs</span><span class="sxs-lookup"><span data-stu-id="13958-637">None</span></span>                   | <span data-ttu-id="13958-638">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="13958-638">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="13958-639">Együttélés</span><span class="sxs-lookup"><span data-stu-id="13958-639">Cohabiting</span></span>             | <span data-ttu-id="13958-640">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="13958-640">*Not supported by Mexico*</span></span> |

### <a name="gender"></a><span data-ttu-id="13958-641">Nem</span><span class="sxs-lookup"><span data-stu-id="13958-641">Gender</span></span>

<span data-ttu-id="13958-642">A nemek a Dayforce-hoz vannak rendelve és konvertálva szükség esetén az elfogadható értékekre az integráció során.</span><span class="sxs-lookup"><span data-stu-id="13958-642">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="13958-643">Az alábbi táblázat bemutatja, hogy a nemek hogyan vannak leképezve a Dayforce-ban.</span><span class="sxs-lookup"><span data-stu-id="13958-643">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="13958-644">Emberi erőforrások</span><span class="sxs-lookup"><span data-stu-id="13958-644">Human Resources</span></span>       | <span data-ttu-id="13958-645">Dayforce</span><span class="sxs-lookup"><span data-stu-id="13958-645">Dayforce</span></span>                  |
|--------------|---------------------------|
| <span data-ttu-id="13958-646">Férfi</span><span class="sxs-lookup"><span data-stu-id="13958-646">Male</span></span>         | <span data-ttu-id="13958-647">Férfi</span><span class="sxs-lookup"><span data-stu-id="13958-647">Male</span></span>                      |
| <span data-ttu-id="13958-648">Nő</span><span class="sxs-lookup"><span data-stu-id="13958-648">Female</span></span>       | <span data-ttu-id="13958-649">Nő</span><span class="sxs-lookup"><span data-stu-id="13958-649">Female</span></span>                    |
| <span data-ttu-id="13958-650">Nem meghatározott</span><span class="sxs-lookup"><span data-stu-id="13958-650">Non-specific</span></span> | <span data-ttu-id="13958-651">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="13958-651">*Not supported by Mexico*</span></span> |

### <a name="payment-method"></a><span data-ttu-id="13958-652">Kifizetési mód</span><span class="sxs-lookup"><span data-stu-id="13958-652">Payment method</span></span>

<span data-ttu-id="13958-653">A Fizetési módok adják meg az alkalmazott és a vállalat számára az alkalmazott kifizetésének módja leírásának lehetőségét.</span><span class="sxs-lookup"><span data-stu-id="13958-653">Payment methods give the employee and the company a way to describe how employees will be paid.</span></span> <span data-ttu-id="13958-654">A Fizetési módok a Dayforce-hoz vannak rendelve és konvertálva szükség esetén az elfogadható értékekre az integráció során.</span><span class="sxs-lookup"><span data-stu-id="13958-654">Payment methods are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="13958-655">Az alábbi táblázat bemutatja, hogy a fizetés módok hogyan vannak leképezve a Dayforce-ban.</span><span class="sxs-lookup"><span data-stu-id="13958-655">The following table shows how payment methods are mapped to Dayforce.</span></span>

| <span data-ttu-id="13958-656">Emberi erőforrások</span><span class="sxs-lookup"><span data-stu-id="13958-656">Human Resources</span></span>             | <span data-ttu-id="13958-657">Dayforce</span><span class="sxs-lookup"><span data-stu-id="13958-657">Dayforce</span></span>                  |
|--------------------|---------------------------|
| <span data-ttu-id="13958-658">Készpénz</span><span class="sxs-lookup"><span data-stu-id="13958-658">Cash</span></span>               | <span data-ttu-id="13958-659">Készpénz</span><span class="sxs-lookup"><span data-stu-id="13958-659">Cash</span></span>                      |
| <span data-ttu-id="13958-660">Elektronikus fizetés</span><span class="sxs-lookup"><span data-stu-id="13958-660">Electronic Payment</span></span> | <span data-ttu-id="13958-661">Átvitel</span><span class="sxs-lookup"><span data-stu-id="13958-661">Transfer</span></span>                  |
| <span data-ttu-id="13958-662">Csekkes</span><span class="sxs-lookup"><span data-stu-id="13958-662">Check</span></span>              | <span data-ttu-id="13958-663">Csekk</span><span class="sxs-lookup"><span data-stu-id="13958-663">Cheque</span></span>                    |
| <span data-ttu-id="13958-664">Váltó</span><span class="sxs-lookup"><span data-stu-id="13958-664">Bank Draft</span></span>         | <span data-ttu-id="13958-665">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="13958-665">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="13958-666">Egyéb</span><span class="sxs-lookup"><span data-stu-id="13958-666">Other</span></span>              | <span data-ttu-id="13958-667">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="13958-667">*Not supported by Mexico*</span></span> |

### <a name="bank-account-type"></a><span data-ttu-id="13958-668">Bankszámla típusa</span><span class="sxs-lookup"><span data-stu-id="13958-668">Bank account type</span></span>

<span data-ttu-id="13958-669">Bankszámla-típusok az alkalmazottaknak történő elektronikus kifizetésekhez szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="13958-669">Bank account types are used for electronic payments to employees.</span></span> <span data-ttu-id="13958-670">Bankszámla típusa a Dayforce-ba átutalási számlaadatként van rendelve.</span><span class="sxs-lookup"><span data-stu-id="13958-670">Bank account types are mapped to Dayforce as transfer account information.</span></span> <span data-ttu-id="13958-671">A bankszámlatípusok szükség esetén konvertálva vannak az elfogadható értékekké az integráció során.</span><span class="sxs-lookup"><span data-stu-id="13958-671">The bank account types are translated, as appropriate, to the accepted values upon integration.</span></span>

| <span data-ttu-id="13958-672">Emberi erőforrások</span><span class="sxs-lookup"><span data-stu-id="13958-672">Human Resources</span></span>            | <span data-ttu-id="13958-673">Dayforce</span><span class="sxs-lookup"><span data-stu-id="13958-673">Dayforce</span></span>                  |
|-------------------|---------------------------|
| <span data-ttu-id="13958-674">Folyószámla</span><span class="sxs-lookup"><span data-stu-id="13958-674">Checking Account</span></span>  | <span data-ttu-id="13958-675">CheckingAccount</span><span class="sxs-lookup"><span data-stu-id="13958-675">CheckingAccount</span></span>           |
| <span data-ttu-id="13958-676">Bérlista elszámolási számlája</span><span class="sxs-lookup"><span data-stu-id="13958-676">Payroll Account</span></span>   | <span data-ttu-id="13958-677">PayrollAccount</span><span class="sxs-lookup"><span data-stu-id="13958-677">PayrollAccount</span></span>            |
| <span data-ttu-id="13958-678">Megtakarítási számla</span><span class="sxs-lookup"><span data-stu-id="13958-678">Savings Account</span></span>   | <span data-ttu-id="13958-679">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="13958-679">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="13958-680">BankGirot-számla</span><span class="sxs-lookup"><span data-stu-id="13958-680">BankGirot account</span></span> | <span data-ttu-id="13958-681">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="13958-681">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="13958-682">PlusGirot-számla</span><span class="sxs-lookup"><span data-stu-id="13958-682">PlusGirot account</span></span> | <span data-ttu-id="13958-683">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="13958-683">*Not supported by Mexico*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="13958-684">Bevételkódok</span><span class="sxs-lookup"><span data-stu-id="13958-684">Earning codes</span></span>

<span data-ttu-id="13958-685">A bevételkódok egyedi módon azonosítják a dolgozók által kapott fizetéstípusokat.</span><span class="sxs-lookup"><span data-stu-id="13958-685">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="13958-686">A kódoknak különböző paramétereket fednek le, amelyek a bevételekhez kapcsolódnak, például könyvelési szabályok, jelentési követelmények és bruttósítási lehetőségek.</span><span class="sxs-lookup"><span data-stu-id="13958-686">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="13958-687">Ha egy nem támogatott gyakoriság van használatban, a **Minden fizetés** gyakorisága van alapértelmezés szerint használva a kiszámításhoz.</span><span class="sxs-lookup"><span data-stu-id="13958-687">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="13958-688">Támogatott gyakoriságok</span><span class="sxs-lookup"><span data-stu-id="13958-688">Supported frequencies</span></span>

- <span data-ttu-id="13958-689">Összes</span><span class="sxs-lookup"><span data-stu-id="13958-689">All</span></span>
- <span data-ttu-id="13958-690">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="13958-690">EVERYPAY</span></span>
- <span data-ttu-id="13958-691">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="13958-691">EACHPAYPERIOD</span></span>
- <span data-ttu-id="13958-692">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="13958-692">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="13958-693">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="13958-693">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="13958-694">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="13958-694">1OFMTH</span></span>
- <span data-ttu-id="13958-695">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="13958-695">LASTOFMTH</span></span>
- <span data-ttu-id="13958-696">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="13958-696">2OFMTH</span></span>
- <span data-ttu-id="13958-697">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="13958-697">3OFMTH</span></span>
- <span data-ttu-id="13958-698">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="13958-698">4OFMTH</span></span>
- <span data-ttu-id="13958-699">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="13958-699">5OFMTH</span></span>
- <span data-ttu-id="13958-700">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="13958-700">1N2OFMTH</span></span>
- <span data-ttu-id="13958-701">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="13958-701">3N4OFMTH</span></span>
- <span data-ttu-id="13958-702">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="13958-702">1N3OFMTH</span></span>
- <span data-ttu-id="13958-703">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="13958-703">1N4OFMTH</span></span>
- <span data-ttu-id="13958-704">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="13958-704">2N3OFMTH</span></span>
- <span data-ttu-id="13958-705">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="13958-705">2N4OFMTH</span></span>
- <span data-ttu-id="13958-706">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="13958-706">1N2N3OFMTH</span></span>
- <span data-ttu-id="13958-707">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="13958-707">1N2N4OFMTH</span></span>
- <span data-ttu-id="13958-708">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="13958-708">1N3N4OFMTH</span></span>
- <span data-ttu-id="13958-709">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="13958-709">2N3N4OFMTH</span></span>
- <span data-ttu-id="13958-710">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="13958-710">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="13958-711">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="13958-711">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="13958-712">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="13958-712">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="13958-713">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="13958-713">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="13958-714">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="13958-714">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="13958-715">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="13958-715">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="13958-716">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="13958-716">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="13958-717">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="13958-717">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="13958-718">Címek</span><span class="sxs-lookup"><span data-stu-id="13958-718">Addresses</span></span>

<span data-ttu-id="13958-719">Az adott ország vagy régió, állam és megye (település) kódok specifikus formátumokat követelnek, hogy Dayforce és az országos és regionális szolgáltatók felismerjék azokat.</span><span class="sxs-lookup"><span data-stu-id="13958-719">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="13958-720">Annak ellenére, hogy a városok formátuma rugalmas, minden városnak társítva kell lennie egy államhoz.</span><span class="sxs-lookup"><span data-stu-id="13958-720">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="13958-721">Emberi erőforrások</span><span class="sxs-lookup"><span data-stu-id="13958-721">Human Resources</span></span>              | <span data-ttu-id="13958-722">Dayforce</span><span class="sxs-lookup"><span data-stu-id="13958-722">Dayforce</span></span>              |
|---------------------|-----------------------|
| <span data-ttu-id="13958-723">Ország/régió</span><span class="sxs-lookup"><span data-stu-id="13958-723">Country/Region</span></span>      | <span data-ttu-id="13958-724">Országkód</span><span class="sxs-lookup"><span data-stu-id="13958-724">Country Code</span></span>          |
| <span data-ttu-id="13958-725">Irányítószám / postai kód</span><span class="sxs-lookup"><span data-stu-id="13958-725">Zip/Postal Code</span></span>     | <span data-ttu-id="13958-726">Irányítószám</span><span class="sxs-lookup"><span data-stu-id="13958-726">Postal Code</span></span>           |
| <span data-ttu-id="13958-727">Állami</span><span class="sxs-lookup"><span data-stu-id="13958-727">State</span></span>               | <span data-ttu-id="13958-728">Államkód</span><span class="sxs-lookup"><span data-stu-id="13958-728">State Code</span></span>            |
| <span data-ttu-id="13958-729">Város</span><span class="sxs-lookup"><span data-stu-id="13958-729">City</span></span>                | <span data-ttu-id="13958-730">Város</span><span class="sxs-lookup"><span data-stu-id="13958-730">City</span></span>                  |
| <span data-ttu-id="13958-731">Megye</span><span class="sxs-lookup"><span data-stu-id="13958-731">County</span></span>              | <span data-ttu-id="13958-732">Megye (Helyhatóság)</span><span class="sxs-lookup"><span data-stu-id="13958-732">County (Municipality)</span></span> |
| <span data-ttu-id="13958-733">Utca</span><span class="sxs-lookup"><span data-stu-id="13958-733">Street</span></span>              | <span data-ttu-id="13958-734">Cím 1. sora</span><span class="sxs-lookup"><span data-stu-id="13958-734">Address Line 1</span></span>        |
| <span data-ttu-id="13958-735">Utca, házszám</span><span class="sxs-lookup"><span data-stu-id="13958-735">Street Number</span></span>       | <span data-ttu-id="13958-736">Cím 2. sora</span><span class="sxs-lookup"><span data-stu-id="13958-736">Address Line 2</span></span>        |
| <span data-ttu-id="13958-737">Épületblokk</span><span class="sxs-lookup"><span data-stu-id="13958-737">Building Complement</span></span> | <span data-ttu-id="13958-738">Cím 5. sora</span><span class="sxs-lookup"><span data-stu-id="13958-738">Address Line 5</span></span>        |

### <a name="passport-number"></a><span data-ttu-id="13958-739">Útlevél száma</span><span class="sxs-lookup"><span data-stu-id="13958-739">Passport number</span></span>

<span data-ttu-id="13958-740">Az alkalmazottak útlevél adatokat is nyilatkozhatnak.</span><span class="sxs-lookup"><span data-stu-id="13958-740">Employees can declare passport information.</span></span> <span data-ttu-id="13958-741">Az információ a **Útlevél** azonosítótípusra vonatkozik, és az alkalmazott Mexikó-specifikus adataiként van a Dayforce-ba integrálva.</span><span class="sxs-lookup"><span data-stu-id="13958-741">This information is of the **Passport** identification type and is integrated into Dayforce as part of an employee's Mexico-specific information.</span></span>

- <span data-ttu-id="13958-742">Azonosító típusa = „Útlevél”</span><span class="sxs-lookup"><span data-stu-id="13958-742">Identification Type = "Passport"</span></span>
- <span data-ttu-id="13958-743">Kibocsátás dátuma</span><span class="sxs-lookup"><span data-stu-id="13958-743">Issued Date</span></span>
- <span data-ttu-id="13958-744">Lejárat dátuma</span><span class="sxs-lookup"><span data-stu-id="13958-744">Expiration Date</span></span>

<span data-ttu-id="13958-745">Az alkalmazottak több azonosítószámot is megadhatnak az **Útlevél** azonosítótípushoz.</span><span class="sxs-lookup"><span data-stu-id="13958-745">Employees can declare multiple identification numbers of the **Passport** identification type.</span></span> <span data-ttu-id="13958-746">Azonban csak az aktuális aktív útlevélbejegyzés van integrálva a Dayforce-ba.</span><span class="sxs-lookup"><span data-stu-id="13958-746">However, only the current active passport entry is integrated into Dayforce.</span></span> <span data-ttu-id="13958-747">Ha az összes útlevélbejegyzés lejárt, a legutóbb kiállított lesz integrálva a Dayforce-ba.</span><span class="sxs-lookup"><span data-stu-id="13958-747">If all passport entries are expired, the passport that was most recently issued is integrated into Dayforce.</span></span>

