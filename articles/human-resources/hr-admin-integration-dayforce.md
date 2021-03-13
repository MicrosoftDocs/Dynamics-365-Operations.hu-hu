---
title: A Dayforce szolgáltatással való integráció konfigurálása
description: A Microsoft Dynamics 365 Human Resources és a Ceridian Dayforce között végbemenő integrálás több olyan konfigurációs lépésre támaszkodik, amelyeket ebben a cikkben ismertünk. A fizetési időszak feldolgozása előtt konfigurálnia kell az integrációt a Human Resources alkalmazásban és a Dayforce alkalmazásban is.
author: andreabichsel
manager: tfehr
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
ms.openlocfilehash: 044a2d2f632b2c98ce94b6d61c2582a861640b68
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2021
ms.locfileid: "5112808"
---
# <a name="configure-integration-with-dayforce"></a><span data-ttu-id="ed63e-104">A Dayforce szolgáltatással való integráció konfigurálása</span><span class="sxs-lookup"><span data-stu-id="ed63e-104">Configure integration with Dayforce</span></span>

<span data-ttu-id="ed63e-105">A Microsoft Dynamics 365 Human Resources és a Ceridian Dayforce között végbemenő integrálás több olyan konfigurációs lépésre támaszkodik, amelyeket ebben a cikkben ismertünk.</span><span class="sxs-lookup"><span data-stu-id="ed63e-105">The integration between Microsoft Dynamics 365 Human Resources and Ceridian Dayforce relies on several configuration steps that are described in this article.</span></span> <span data-ttu-id="ed63e-106">A fizetési időszak feldolgozása előtt konfigurálnia kell az integrációt a Human Resources alkalmazásban és a Dayforce alkalmazásban is.</span><span class="sxs-lookup"><span data-stu-id="ed63e-106">You must configure the integration in both Human Resources and Dayforce before you can process a pay run.</span></span>

<span data-ttu-id="ed63e-107">Ha olyan szolgáltatást használ a fizetési időszak teljesítéséhez, mint a Dayforce, engedélyeznie kell az integrációt a Human Resources alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="ed63e-107">When you use a service such as Dayforce to complete pay runs, you must enable the integration in Human Resources.</span></span> <span data-ttu-id="ed63e-108">Az integrációhoz szükségesek bizonyos adatok a Human Resources alkalmazásból.</span><span class="sxs-lookup"><span data-stu-id="ed63e-108">The integration requires specific data from Human Resources.</span></span> <span data-ttu-id="ed63e-109">Ezért ellenőriznie kell, hogy a Dayforce alkalmazáshoz hozzárendelt adatok olyan módon legyenek konfigurálva a Human Resources alkalmazásban, hogy az támogassa az integrációt.</span><span class="sxs-lookup"><span data-stu-id="ed63e-109">Therefore, you must verify that data that is mapped to Dayforce is configured in Human Resources in a manner that supports the integration.</span></span> <span data-ttu-id="ed63e-110">Az integráció a következő szélesebb adatkategóriákat használja:</span><span class="sxs-lookup"><span data-stu-id="ed63e-110">The integration uses the following broad categories of data:</span></span>

- <span data-ttu-id="ed63e-111">Emberierőforrás-adatok</span><span class="sxs-lookup"><span data-stu-id="ed63e-111">Human resources data</span></span>
- <span data-ttu-id="ed63e-112">Kompenzációadatok</span><span class="sxs-lookup"><span data-stu-id="ed63e-112">Compensation data</span></span>
- <span data-ttu-id="ed63e-113">Bérlistaadatok, mint kifizetési ciklus, fizetési időszakok és bevételkódok</span><span class="sxs-lookup"><span data-stu-id="ed63e-113">Payroll data, such as pay cycles, pay periods, and earning codes</span></span>
- <span data-ttu-id="ed63e-114">Dolgozóadatok</span><span class="sxs-lookup"><span data-stu-id="ed63e-114">Worker data</span></span>

<span data-ttu-id="ed63e-115">Ez a cikk leírja a lépéseket, amelyeket követni kell az integráció engedélyezéséhez.</span><span class="sxs-lookup"><span data-stu-id="ed63e-115">This article describes the steps that you must follow to enable the integration.</span></span> <span data-ttu-id="ed63e-116">Azt is bemutatja, hogy milyen típusú adatok és konfiguráció szükséges az integrációhoz.</span><span class="sxs-lookup"><span data-stu-id="ed63e-116">It also explains the types of data and the configuration details that the integration requires.</span></span>

## <a name="enable-the-integration"></a><span data-ttu-id="ed63e-117">Engedélyezze az integrációt</span><span class="sxs-lookup"><span data-stu-id="ed63e-117">Enable the integration</span></span>

<span data-ttu-id="ed63e-118">A Dayforce alkalmazáshoz való csatlakozáshoz a Human Resources alkalmazásban be kell kapcsolnia az integrációt és meg kell adnia a konfiguráció adatait.</span><span class="sxs-lookup"><span data-stu-id="ed63e-118">In Human Resources, you must turn on the integration and enter the configuration information to connect to Dayforce.</span></span> <span data-ttu-id="ed63e-119">Ha azt szeretné, hogy a létrehozott általános főkönyvi tranzakció importálva legyen a Microsoft Dynamics 365 Finance alkalmazásba, be kell állítania egy Microsoft Azure tárolási fiókot, majd adja meg, majd Azure tárolási kapcsolat karakterláncát a Finance alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="ed63e-119">If you want the general ledger transaction that is produced to be imported into Microsoft Dynamics 365 Finance, you must also set up a Microsoft Azure storage account and enter the Azure Storage connection string in Finance.</span></span>

<span data-ttu-id="ed63e-120">A Human Resources alkalmazásban lévő integráció bekapcsolásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="ed63e-120">To turn on the integration in Human Resources, follow these steps.</span></span>

1. <span data-ttu-id="ed63e-121">A **Rendszerfelügyelet** oldalon válassza az **Integrációkonfiguráció** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ed63e-121">On the **System administration** page, select **Integration configuration**.</span></span>
2. <span data-ttu-id="ed63e-122">Adja meg a biztonságos fájl átviteli protokollt (FTP) végpontot és a biztonságos FTP-mappa elérési útja.</span><span class="sxs-lookup"><span data-stu-id="ed63e-122">Enter the secure File Transfer Protocol (FTP) endpoint and the secure FTP folder path.</span></span>
3. <span data-ttu-id="ed63e-123">Adja meg azon felhasználó felhasználónevét és jelszavát, aki hozzáfér a biztonságos FTP végponthoz és a mappa elérési útjához.</span><span class="sxs-lookup"><span data-stu-id="ed63e-123">Enter the user name and password of the user who will access the secure FTP endpoint and folder path.</span></span>
4. <span data-ttu-id="ed63e-124">Tesztelje a kapcsolatot szükség szerint, és állítsa a **Bérlista-integráció engedélyezése** lehetőséggel **Igenre**.</span><span class="sxs-lookup"><span data-stu-id="ed63e-124">Test the connection, as required, and set the **Enable payroll integration** option to **Yes**.</span></span>

<span data-ttu-id="ed63e-125">Ha az integráció engedélyezve van, adatexport adatcsomagok és fájlok jönnek létre, valamint a gyakoriság is be van állítva.</span><span class="sxs-lookup"><span data-stu-id="ed63e-125">When the integration is turned on, the data export package and files are created, and the frequency is set.</span></span> <span data-ttu-id="ed63e-126">Igény szerint módosíthatja a gyakoriságot.</span><span class="sxs-lookup"><span data-stu-id="ed63e-126">You can change this frequency as you require.</span></span>

<span data-ttu-id="ed63e-127">Az Azure tárolási fiókokkal és az Azure tárolási kapcsolati karakterláncokkal kapcsolatos további információkat az alábbi Azure-cikkben találja:</span><span class="sxs-lookup"><span data-stu-id="ed63e-127">For more information about Azure storage accounts and Azure Storage connection strings, see the following Azure articles:</span></span>

- [<span data-ttu-id="ed63e-128">Az Azure Storage-fiókokról</span><span class="sxs-lookup"><span data-stu-id="ed63e-128">About Azure storage accounts</span></span>](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [<span data-ttu-id="ed63e-129">Azure Storage kapcsolati karakterláncok konfigurálása</span><span class="sxs-lookup"><span data-stu-id="ed63e-129">Configure Azure Storage connection strings</span></span>](https://docs.microsoft.com/azure/storage/common/storage-configure-connection-string)

### <a name="technical-details-when-payroll-integration-is-enabled"></a><span data-ttu-id="ed63e-130">Technikai részletek a bérlista integrációjának engedélyezésekor</span><span class="sxs-lookup"><span data-stu-id="ed63e-130">Technical details when payroll integration is enabled</span></span>

<span data-ttu-id="ed63e-131">A bérlista-integráció bekapcsolása két elsődleges hatással jár:</span><span class="sxs-lookup"><span data-stu-id="ed63e-131">Turning on the payroll integration has two primary effects:</span></span>

- <span data-ttu-id="ed63e-132">Létrejön egy „bérlista-integráció exportálása” nevű adatexportálási projekt.</span><span class="sxs-lookup"><span data-stu-id="ed63e-132">A data export project named "Payroll integration export" is created.</span></span> <span data-ttu-id="ed63e-133">Ez a projekt a bérlista-integrációhoz szükséges entitásokat és mezőket tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="ed63e-133">This project contains the entities and fields required for the payroll integration.</span></span> <span data-ttu-id="ed63e-134">A projekt vizsgálatához nyissa meg a **Rendszerfelügyeletet**, válassza ki az **Adatkezelési** csempét, majd nyissa meg az adatprojektet a projektek listájából.</span><span class="sxs-lookup"><span data-stu-id="ed63e-134">To examine the project, go to **System administration**, select the **Data management** tile, and then open the data project from the list of projects.</span></span>
- <span data-ttu-id="ed63e-135">Ez a kötegelt feladat végrehajtja az adatexportálási projektet, titkosítja a létrejövő adatcsomagot, és átviszi az adatcsomag-fájlt az **Integráció konfigurációja** képernyőjén beállított SFTP végpontba.</span><span class="sxs-lookup"><span data-stu-id="ed63e-135">This batch job executes the data export project, encrypts the resulting data package, and transfers the data package file to the SFTP endpoint configured on the **Integration configuration** screen.</span></span>

> [!NOTE]
> <span data-ttu-id="ed63e-136">Az SFTP végpontra átvitt adatcsomag titkosítva van a csomag egyedi kulcsával.</span><span class="sxs-lookup"><span data-stu-id="ed63e-136">The data package transferred to the SFTP endpoint is encrypted using a key that is unique to the package.</span></span> <span data-ttu-id="ed63e-137">A kulcs egy Azure kulcstárolóban van, amely csak Ceridian számára érhető el.</span><span class="sxs-lookup"><span data-stu-id="ed63e-137">The key is in an Azure Key Vault that is accessible only by Ceridian.</span></span> <span data-ttu-id="ed63e-138">Az adatcsomag tartalmát nem lehet dekódolni és megvizsgálni.</span><span class="sxs-lookup"><span data-stu-id="ed63e-138">It is not possible to decrypt and examine the data package contents.</span></span> <span data-ttu-id="ed63e-139">Ha meg kell vizsgálnia az adatcsomag tartalmát, akkor manuálisan kell exportálnia a „Bérlista-integráció exportálása” adatprojektet, le kell töltenie, majd meg kell nyitnia.</span><span class="sxs-lookup"><span data-stu-id="ed63e-139">If you need to examine the contents of the data package, you need to export the "Payroll integration export" data project manually, download it, and then open it.</span></span> <span data-ttu-id="ed63e-140">A manuális exportálás nem alkalmazza a titkosítást, és nem viszi át a csomagot.</span><span class="sxs-lookup"><span data-stu-id="ed63e-140">Manual export will not apply encryption or transfer the package.</span></span>

## <a name="configure-your-data"></a><span data-ttu-id="ed63e-141">Adatai konfigurálása</span><span class="sxs-lookup"><span data-stu-id="ed63e-141">Configure your data</span></span> 

<span data-ttu-id="ed63e-142">A bérlista feldolgozásához konfigurálnia kell az emberierőforrás-adatokat a Human Resources alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="ed63e-142">To process payroll, you must configure human resource data in Human Resources.</span></span> <span data-ttu-id="ed63e-143">Be kell állítani a szervezeti adatokat, például a feladatokat és beosztásokat, valamint juttatásokra és a kompenzációra vonatkozó adatokat.</span><span class="sxs-lookup"><span data-stu-id="ed63e-143">You must set up organizational data, such as jobs and positions, together with benefits and compensation information.</span></span> <span data-ttu-id="ed63e-144">Ez az információ megadja a foglalkoztatásra, fizetésre és levonásokra vonatkozó információkat, melyek szükségesek az alkalmazott fizetések generálásához.</span><span class="sxs-lookup"><span data-stu-id="ed63e-144">This information provides the employment, pay, and deduction information that is required in order to generate employee pay.</span></span>

### <a name="human-resource-data"></a><span data-ttu-id="ed63e-145">Emberierőforrás-adatok</span><span class="sxs-lookup"><span data-stu-id="ed63e-145">Human resource data</span></span>

#### <a name="benefits"></a><span data-ttu-id="ed63e-146">Juttatások</span><span class="sxs-lookup"><span data-stu-id="ed63e-146">Benefits</span></span> 

<span data-ttu-id="ed63e-147">Az emberi erőforrások számos beállítási és karbantartási eszközt biztosít, amelyek segítségével beállíthatja és karbantarthatja a szervezet által a dolgozónak biztosított juttatásokat, levonásokat és dolgozói kompenzációs terveket.</span><span class="sxs-lookup"><span data-stu-id="ed63e-147">Human resources provides tools for the setup and maintenance of the benefits, deductions, and worker compensation plans that an organization offers or processes for its workers.</span></span>

<span data-ttu-id="ed63e-148">Juttatások létrehozása esetén ne felejtse el a következő adatokat és beállításokat, amelyeket a Dayforce használ.</span><span class="sxs-lookup"><span data-stu-id="ed63e-148">When you create benefits, keep in mind the following data and configurations that are used in Dayforce.</span></span>

##### <a name="benefit-plans"></a><span data-ttu-id="ed63e-149">Juttatási tervek</span><span class="sxs-lookup"><span data-stu-id="ed63e-149">Benefit plans</span></span>

- <span data-ttu-id="ed63e-150">Terv (szükséges)</span><span class="sxs-lookup"><span data-stu-id="ed63e-150">Plan (required)</span></span>
- <span data-ttu-id="ed63e-151">Típus (szükséges)</span><span class="sxs-lookup"><span data-stu-id="ed63e-151">Type (required)</span></span>
- <span data-ttu-id="ed63e-152">Bérlista hatása (szükséges)</span><span class="sxs-lookup"><span data-stu-id="ed63e-152">Payroll impact (required)</span></span>
- <span data-ttu-id="ed63e-153">Hátralékok helyreállítása</span><span class="sxs-lookup"><span data-stu-id="ed63e-153">Recover arrears</span></span>
- <span data-ttu-id="ed63e-154">Levonási módszer</span><span class="sxs-lookup"><span data-stu-id="ed63e-154">Deduction method</span></span>
- <span data-ttu-id="ed63e-155">Levonás prioritása</span><span class="sxs-lookup"><span data-stu-id="ed63e-155">Deduction priority</span></span>
- <span data-ttu-id="ed63e-156">Időszak korlátozása</span><span class="sxs-lookup"><span data-stu-id="ed63e-156">Limit period</span></span>
- <span data-ttu-id="ed63e-157">Összeghatár</span><span class="sxs-lookup"><span data-stu-id="ed63e-157">Limit amount</span></span>

##### <a name="benefits"></a><span data-ttu-id="ed63e-158">Juttatások</span><span class="sxs-lookup"><span data-stu-id="ed63e-158">Benefits</span></span>

- <span data-ttu-id="ed63e-159">Terv (szükséges)</span><span class="sxs-lookup"><span data-stu-id="ed63e-159">Plan (required)</span></span>
- <span data-ttu-id="ed63e-160">Típus (szükséges)</span><span class="sxs-lookup"><span data-stu-id="ed63e-160">Type (required)</span></span>
- <span data-ttu-id="ed63e-161">Lehetőség (szükséges)</span><span class="sxs-lookup"><span data-stu-id="ed63e-161">Option (required)</span></span>
- <span data-ttu-id="ed63e-162">Juttatás azonosítója (szükséges)</span><span class="sxs-lookup"><span data-stu-id="ed63e-162">Benefit ID (required)</span></span>
- <span data-ttu-id="ed63e-163">Gyakoriság</span><span class="sxs-lookup"><span data-stu-id="ed63e-163">Frequency</span></span>
- <span data-ttu-id="ed63e-164">Alap</span><span class="sxs-lookup"><span data-stu-id="ed63e-164">Basis</span></span>
- <span data-ttu-id="ed63e-165">Összeg vagy mérték</span><span class="sxs-lookup"><span data-stu-id="ed63e-165">Amount or rate</span></span>
- <span data-ttu-id="ed63e-166">Bevételkód</span><span class="sxs-lookup"><span data-stu-id="ed63e-166">Earning code</span></span>

##### <a name="supported-frequencies"></a><span data-ttu-id="ed63e-167">Támogatott gyakoriságok</span><span class="sxs-lookup"><span data-stu-id="ed63e-167">Supported frequencies</span></span> 

- <span data-ttu-id="ed63e-168">Heti</span><span class="sxs-lookup"><span data-stu-id="ed63e-168">Weekly</span></span>
- <span data-ttu-id="ed63e-169">Kétheti</span><span class="sxs-lookup"><span data-stu-id="ed63e-169">Bi-weekly</span></span>
- <span data-ttu-id="ed63e-170">Félhavi</span><span class="sxs-lookup"><span data-stu-id="ed63e-170">Semi-monthly</span></span>
- <span data-ttu-id="ed63e-171">Havi</span><span class="sxs-lookup"><span data-stu-id="ed63e-171">Monthly</span></span>

##### <a name="supported-bases"></a><span data-ttu-id="ed63e-172">Támogatott alapok</span><span class="sxs-lookup"><span data-stu-id="ed63e-172">Supported bases</span></span> 

- <span data-ttu-id="ed63e-173">Rögzített összeg</span><span class="sxs-lookup"><span data-stu-id="ed63e-173">Fixed amount</span></span>
- <span data-ttu-id="ed63e-174">Bevételek százaléka</span><span class="sxs-lookup"><span data-stu-id="ed63e-174">Percent of earnings</span></span>
- <span data-ttu-id="ed63e-175">Produktív órák</span><span class="sxs-lookup"><span data-stu-id="ed63e-175">Productive hours</span></span>

<span data-ttu-id="ed63e-176">A Dayforce létrehozza a következő levonásokat, a juttatási tervben definiált bérlistahatás alapján.</span><span class="sxs-lookup"><span data-stu-id="ed63e-176">Dayforce creates the following deductions, based on the payroll impact that is defined on the benefit plan.</span></span>

| <span data-ttu-id="ed63e-177">Kiválasztás a Human Resources alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="ed63e-177">Selection in Human Resources</span></span>        | <span data-ttu-id="ed63e-178">Eredmény a Dayforce-ban</span><span class="sxs-lookup"><span data-stu-id="ed63e-178">Result in Dayforce</span></span>                            |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="ed63e-179">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="ed63e-179">None</span></span>                       | <span data-ttu-id="ed63e-180">Nincs létrehozva levonás.</span><span class="sxs-lookup"><span data-stu-id="ed63e-180">No deduction is created.</span></span>                      |
| <span data-ttu-id="ed63e-181">Csak levonás</span><span class="sxs-lookup"><span data-stu-id="ed63e-181">Deduction only</span></span>             | <span data-ttu-id="ed63e-182">Alkalmazotti levonás jön létre.</span><span class="sxs-lookup"><span data-stu-id="ed63e-182">An employee deduction is created.</span></span>             |
| <span data-ttu-id="ed63e-183">Csak hozzájárulás</span><span class="sxs-lookup"><span data-stu-id="ed63e-183">Contribution only</span></span>          | <span data-ttu-id="ed63e-184">Egy alkalmazotti levonás jön létre.</span><span class="sxs-lookup"><span data-stu-id="ed63e-184">An employer deduction is created.</span></span>             |
| <span data-ttu-id="ed63e-185">Levonás és hozzájárulás</span><span class="sxs-lookup"><span data-stu-id="ed63e-185">Deduction and contribution</span></span> | <span data-ttu-id="ed63e-186">Alkalmazotti és a munkáltatói levonások jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="ed63e-186">Employee and employer deductions are created.</span></span> |

<span data-ttu-id="ed63e-187">A juttatási programok meghatározásával és kezelésével kapcsolatos további tájékoztatást a következő cikkekben találja:</span><span class="sxs-lookup"><span data-stu-id="ed63e-187">For more information about how to define and manage a benefits program, see the following articles:</span></span>

- [<span data-ttu-id="ed63e-188">Alkalmazotti juttatási program végrehajtása</span><span class="sxs-lookup"><span data-stu-id="ed63e-188">Deliver an employee benefits program</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [<span data-ttu-id="ed63e-189">Új juttatás létrehozása</span><span class="sxs-lookup"><span data-stu-id="ed63e-189">Create a new benefit</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [<span data-ttu-id="ed63e-190">Juttatásra való jogosultsági szabályok és irányelvek meghatározása</span><span class="sxs-lookup"><span data-stu-id="ed63e-190">Define benefit eligibility rules and policies</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [<span data-ttu-id="ed63e-191">Dolgozók juttatásainak felvétele és eltávolítása</span><span class="sxs-lookup"><span data-stu-id="ed63e-191">Enroll and remove benefits from workers</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a><span data-ttu-id="ed63e-192">Kompenzáció</span><span class="sxs-lookup"><span data-stu-id="ed63e-192">Compensation</span></span> 

<span data-ttu-id="ed63e-193">A kompenzációkezeléssel szabályozható az alapfizetés és a jutalmak kifizetése.</span><span class="sxs-lookup"><span data-stu-id="ed63e-193">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="ed63e-194">Egy alkalmazott fix fizetési díjalapja és érdemeken alapuló fizetése kezelhető a fix kompenzációs tervekkel.</span><span class="sxs-lookup"><span data-stu-id="ed63e-194">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="ed63e-195">Az ösztönző díjak kifizetése, például bónuszok, teljesítménydíjak, részvényopciók és kölcsönök, továbbá az egyszeri jutalmak a változó kompenzációs tervekben szabályozhatók.</span><span class="sxs-lookup"><span data-stu-id="ed63e-195">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span>

<span data-ttu-id="ed63e-196">A Dayforce a kompenzációs adatok segítségével kiszámítja az alkalmazott óradíját vagy éves díját.</span><span class="sxs-lookup"><span data-stu-id="ed63e-196">Dayforce uses compensation information to calculate an employee's hourly or annual rate.</span></span> <span data-ttu-id="ed63e-197">Fix kompenzációs tervek és a fizetési díjalap átalakítások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="ed63e-197">Fixed compensation plans and pay rate conversions are required.</span></span> <span data-ttu-id="ed63e-198">Az alkalmazottakat hozzá kell rendelni a fix kompenzációs tervhez.</span><span class="sxs-lookup"><span data-stu-id="ed63e-198">Employees must be associated with a fixed compensation plan.</span></span>

<span data-ttu-id="ed63e-199">A következő cikkekben bővebben olvashat a kompenzációs tervekről:</span><span class="sxs-lookup"><span data-stu-id="ed63e-199">For more information about compensation plans, see the following articles:</span></span>

- [<span data-ttu-id="ed63e-200">Fix kompenzációs konstrukciók létrehozása</span><span class="sxs-lookup"><span data-stu-id="ed63e-200">Create fixed compensation plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [<span data-ttu-id="ed63e-201">Változó kompenzációs konstrukciók létrehozása</span><span class="sxs-lookup"><span data-stu-id="ed63e-201">Create variable compensation plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [<span data-ttu-id="ed63e-202">Munkabér-/kompenzációs struktúra és tervek kialakítása</span><span class="sxs-lookup"><span data-stu-id="ed63e-202">Develop salary/compensation structure and plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [<span data-ttu-id="ed63e-203">Folyamatkompenzáció</span><span class="sxs-lookup"><span data-stu-id="ed63e-203">Process compensation</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/process-compensation)
- [<span data-ttu-id="ed63e-204">Kompenzációs folyamat meghatározása és eredmények kiszámítása</span><span class="sxs-lookup"><span data-stu-id="ed63e-204">Define compensation process and calculate results</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [<span data-ttu-id="ed63e-205">Alkalmazottak felvétele fix kompenzációs konstrukcióba</span><span class="sxs-lookup"><span data-stu-id="ed63e-205">Enroll an employee in a fixed compensation plan</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [<span data-ttu-id="ed63e-206">Alkalmazottak felvétele változó kompenzációs konstrukcióba</span><span class="sxs-lookup"><span data-stu-id="ed63e-206">Enroll an employee in a variable compensation plan</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a><span data-ttu-id="ed63e-207">Beosztások</span><span class="sxs-lookup"><span data-stu-id="ed63e-207">Jobs</span></span> 

<span data-ttu-id="ed63e-208">A munkakör azon feladatok és felelősségek gyűjteménye, amelyek egy adott munkát végrehajtó személytől elvártak.</span><span class="sxs-lookup"><span data-stu-id="ed63e-208">A job is a collection of the tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="ed63e-209">További információért tekintse át az alábbi cikkeket:</span><span class="sxs-lookup"><span data-stu-id="ed63e-209">For more information, see the following articles:</span></span>

- [<span data-ttu-id="ed63e-210">Feladat összetevőinek beállítása</span><span class="sxs-lookup"><span data-stu-id="ed63e-210">Setting up the components of a job</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-job)
- [<span data-ttu-id="ed63e-211">Új feladatok meghatározása</span><span class="sxs-lookup"><span data-stu-id="ed63e-211">Define new jobs</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a><span data-ttu-id="ed63e-212">Beosztások</span><span class="sxs-lookup"><span data-stu-id="ed63e-212">Positions</span></span>

<span data-ttu-id="ed63e-213">Egy beosztás egy feladat egyedi példánya.</span><span class="sxs-lookup"><span data-stu-id="ed63e-213">A position is an individual instance of a job.</span></span> <span data-ttu-id="ed63e-214">Például az „Értékesítési igazgató (Kelet)” pozíció egyike azon beosztásoknak, amelyek társíthatók az „Értékesítési igazgató” feladathoz.</span><span class="sxs-lookup"><span data-stu-id="ed63e-214">For example, the "Sales manager (East)" position is one of the positions that are associated with the "Sales manager" job.</span></span> <span data-ttu-id="ed63e-215">A beosztás létezik a részlegben.</span><span class="sxs-lookup"><span data-stu-id="ed63e-215">A position exists in a department.</span></span> <span data-ttu-id="ed63e-216">Egy beosztáshoz csak egy dolgozó rendelhető.</span><span class="sxs-lookup"><span data-stu-id="ed63e-216">Only one worker can be associated with each position.</span></span>

<span data-ttu-id="ed63e-217">A következő adatokat és konfigurációkat szem előtt tartani beosztások beállításakor:</span><span class="sxs-lookup"><span data-stu-id="ed63e-217">Keep the following data and configuration in mind when you set up positions:</span></span>

- <span data-ttu-id="ed63e-218">Beosztás (szükséges)</span><span class="sxs-lookup"><span data-stu-id="ed63e-218">Position (required)</span></span>
- <span data-ttu-id="ed63e-219">Leírás (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-219">Description (required)</span></span>
- <span data-ttu-id="ed63e-220">Munka (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-220">Job (required)</span></span>
- <span data-ttu-id="ed63e-221">Részleg (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-221">Department (required)</span></span>
- <span data-ttu-id="ed63e-222">Beosztás típusa (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-222">Position type (required)</span></span>
- <span data-ttu-id="ed63e-223">Teljes munkaidőssel egyenértékű</span><span class="sxs-lookup"><span data-stu-id="ed63e-223">Full-time equivalent</span></span>
- <span data-ttu-id="ed63e-224">Éves rendes munkaidő (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-224">Annual regular hours (required)</span></span>
- <span data-ttu-id="ed63e-225">Jogi személy által fizetett (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-225">Paid by legal entity (required)</span></span>
- <span data-ttu-id="ed63e-226">Fizetési ciklus (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-226">Pay cycle (required)</span></span>
- <span data-ttu-id="ed63e-227">Alapértelmezett pénzügyi dimenzió – Költséghely (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-227">Default financial dimension – Cost center (required)</span></span>
- <span data-ttu-id="ed63e-228">Dolgozó-hozzárendelés – dolgozó-hozzárendelés kezdete, hozzárendelés vége és okkód</span><span class="sxs-lookup"><span data-stu-id="ed63e-228">Worker assignment – Worker, assignment start, assignment end, reason code</span></span>

<span data-ttu-id="ed63e-229">A azonos osztály több beosztása társítva van az ugyanazon a feladathoz, azok össze lesznek vonva a Dayforce egyetlen pozíciójába.</span><span class="sxs-lookup"><span data-stu-id="ed63e-229">If multiple positions in the same department are associated with the same job, they are consolidated into a single position in Dayforce.</span></span>

<span data-ttu-id="ed63e-230">További információért tekintse át az alábbi cikkeket:</span><span class="sxs-lookup"><span data-stu-id="ed63e-230">For more information, see the following articles:</span></span>

- [<span data-ttu-id="ed63e-231">Munkaerő szervezése részlegek, feladatok és beosztások szerint</span><span class="sxs-lookup"><span data-stu-id="ed63e-231">Organize your workforce using departments, jobs, and positions</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [<span data-ttu-id="ed63e-232">Beosztások beállítása</span><span class="sxs-lookup"><span data-stu-id="ed63e-232">Set up positions</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a><span data-ttu-id="ed63e-233">Osztályok</span><span class="sxs-lookup"><span data-stu-id="ed63e-233">Departments</span></span>

<span data-ttu-id="ed63e-234">A részleg egy működési egység, amely a szervezet egy kategóriáját vagy működési területét képviseli.</span><span class="sxs-lookup"><span data-stu-id="ed63e-234">A department is an operating unit that represents a category or functional area of an organization.</span></span> <span data-ttu-id="ed63e-235">Egy részleg a szervezet egy konkrét területen végzett tevékenységeiért felel (például értékesítés, könyvelés, emberi erőforrások).</span><span class="sxs-lookup"><span data-stu-id="ed63e-235">A department is responsible for a specific area of the organization, such as sales, accounting, or human resources.</span></span> <span data-ttu-id="ed63e-236">A részlegek segítségével hozhatók létre jelentések a működési területekről.</span><span class="sxs-lookup"><span data-stu-id="ed63e-236">You can use departments to report on functional areas.</span></span> <span data-ttu-id="ed63e-237">A részlegeknek lehet eredménykimutatási felelőssége.</span><span class="sxs-lookup"><span data-stu-id="ed63e-237">Departments might have profit and loss responsibility.</span></span>

<span data-ttu-id="ed63e-238">További információért tekintse át az alábbi cikkeket:</span><span class="sxs-lookup"><span data-stu-id="ed63e-238">For more information, see the following articles:</span></span>

- [<span data-ttu-id="ed63e-239">Részleg létrehozása és társítása a szervezeti hierarchiához</span><span class="sxs-lookup"><span data-stu-id="ed63e-239">Create a department and associate it with the department hierarchy</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [<span data-ttu-id="ed63e-240">Új részlegek meghatározása</span><span class="sxs-lookup"><span data-stu-id="ed63e-240">Define new departments</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a><span data-ttu-id="ed63e-241">Fizetési ciklusok és fizetési időszakok</span><span class="sxs-lookup"><span data-stu-id="ed63e-241">Pay cycles and pay periods</span></span>

<span data-ttu-id="ed63e-242">A fizetési ciklus meghatározza, hogy milyen gyakran történik a bérlista folyósítása, és a dolgozók mely napokon kapnak fizetést,.</span><span class="sxs-lookup"><span data-stu-id="ed63e-242">A pay cycle determines how often payroll is run and the specific days when workers are paid.</span></span> <span data-ttu-id="ed63e-243">Például a kifizetési ciklus lehet, havi, és az alkalmazottak kaphatják a hónap utolsó napján a fizetésüket.</span><span class="sxs-lookup"><span data-stu-id="ed63e-243">For example, a pay cycle might be monthly, and employees might be paid on the last day of the month.</span></span> <span data-ttu-id="ed63e-244">Vagy a kifizetési ciklus lehet heti, és az alkalmazottak a fizetési időszak utáni kedden kaphatják fizetésüket.</span><span class="sxs-lookup"><span data-stu-id="ed63e-244">Alternatively, a pay cycle might be weekly, and employees might be paid on the Tuesday after the end of the pay period.</span></span> <span data-ttu-id="ed63e-245">Kifizetési ciklusok beosztásokhoz vannak rendelve, és szabályozzák, hogy az ebben a beosztásban lévő dolgozók mikor kapnak fizetést.</span><span class="sxs-lookup"><span data-stu-id="ed63e-245">Pay cycles are assigned to positions to control when workers in those positions are paid.</span></span>

<span data-ttu-id="ed63e-246">Miután létrehozott fizetési ciklusokat, minden egyes ciklushoz fizetési időszakot hozhat létre.</span><span class="sxs-lookup"><span data-stu-id="ed63e-246">After you create pay cycles, you can generate pay periods for each cycle.</span></span> <span data-ttu-id="ed63e-247">Minden fizetési időszakban egy alapértelmezett fizetési dátum van, amely a megadott adatokon alapul.</span><span class="sxs-lookup"><span data-stu-id="ed63e-247">Each pay period includes a default payment date that is based on information that you provide.</span></span> <span data-ttu-id="ed63e-248">Ugyanakkor az alapértelmezett fizetési dátumot a fizetési időszakban módosíthatja kivételekhez például amikor egy kifizetési dátum ünnepnapra esik.</span><span class="sxs-lookup"><span data-stu-id="ed63e-248">However, you can modify the default payment date in a pay period to allow for exceptions, such as when the payment date falls on a holiday.</span></span>

<span data-ttu-id="ed63e-249">A következő adatokat használja a Dayforce:</span><span class="sxs-lookup"><span data-stu-id="ed63e-249">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="ed63e-250">Fizetési ciklus (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-250">Pay cycle (required)</span></span>
- <span data-ttu-id="ed63e-251">Fizetési ciklus gyakorisága (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-251">Pay cycle frequency (required)</span></span>
- <span data-ttu-id="ed63e-252">Az időszak kezdő dátuma (az első fizetési időszak szükséges)</span><span class="sxs-lookup"><span data-stu-id="ed63e-252">Period start date (first pay period required)</span></span>
- <span data-ttu-id="ed63e-253">Alapértelmezett fizetési dátum (az első fizetési időszak szükséges)</span><span class="sxs-lookup"><span data-stu-id="ed63e-253">Default payment date (first pay period required)</span></span>

<span data-ttu-id="ed63e-254">Ez az információ Dayforceba fizetési csoportokként van integrálva országonként vagy régiónként le van választva egyes kifizetési ciklusokhoz.</span><span class="sxs-lookup"><span data-stu-id="ed63e-254">This information is integrated with Dayforce as pay groups, and is separated by country or region for each pay cycle.</span></span> <span data-ttu-id="ed63e-255">Legalább egy fizetési időszakot kell létrehozni az integráció előtt.</span><span class="sxs-lookup"><span data-stu-id="ed63e-255">At least one pay period must be generated before integration.</span></span> <span data-ttu-id="ed63e-256">A Dayforce fizetési csoportnaptárakat és kifizetési dátumokat hoz létre az első fizetési időszak kezdő dátuma és az alapértelmezett fizetési dátum alapján, amelyek a Human Resources alkalmazásban vannak beállítva.</span><span class="sxs-lookup"><span data-stu-id="ed63e-256">Dayforce generates pay group calendars and payment dates, based on the start date of the first pay period and the default payment date that is set up in Human Resources.</span></span>

#### <a name="earning-codes"></a><span data-ttu-id="ed63e-257">Bevételkódok</span><span class="sxs-lookup"><span data-stu-id="ed63e-257">Earning codes</span></span>

<span data-ttu-id="ed63e-258">A bevételkódok egyedi módon azonosítják a dolgozók által kapott fizetéstípusokat.</span><span class="sxs-lookup"><span data-stu-id="ed63e-258">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="ed63e-259">A kódoknak különböző paraméterei vannak, amelyek a bevételekhez kapcsolódnak, például könyvelési szabályok, jelentési követelmények és bruttósítási lehetőségek.</span><span class="sxs-lookup"><span data-stu-id="ed63e-259">The codes have various parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span>

<span data-ttu-id="ed63e-260">A következő adatokat használja a Dayforce:</span><span class="sxs-lookup"><span data-stu-id="ed63e-260">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="ed63e-261">Bevételkód (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-261">Earning Code (required)</span></span>
- <span data-ttu-id="ed63e-262">Leírás</span><span class="sxs-lookup"><span data-stu-id="ed63e-262">Description</span></span>
- <span data-ttu-id="ed63e-263">Mértékegység</span><span class="sxs-lookup"><span data-stu-id="ed63e-263">Unit of measure</span></span>
- <span data-ttu-id="ed63e-264">Produktív</span><span class="sxs-lookup"><span data-stu-id="ed63e-264">Productive</span></span>

### <a name="worker-data"></a><span data-ttu-id="ed63e-265">Dolgozóadatok</span><span class="sxs-lookup"><span data-stu-id="ed63e-265">Worker data</span></span>

<span data-ttu-id="ed63e-266">A dolgozók különböző típusaihoz tartozó rekordok, melyek fontosak az emberi erőforrásoknak és a bérlistarendszerekhez.</span><span class="sxs-lookup"><span data-stu-id="ed63e-266">Records for the various types of workers that you have are important to your human resources and payroll systems.</span></span> <span data-ttu-id="ed63e-267">A bevitt információk felhasználhatók az dolgozói és személyes adatok nyilvántartására.</span><span class="sxs-lookup"><span data-stu-id="ed63e-267">The information that you enter can be used to track workers and personal information.</span></span>

<span data-ttu-id="ed63e-268">A dolgozók következő adatait tarthatja karban:</span><span class="sxs-lookup"><span data-stu-id="ed63e-268">You can maintain the following information for workers:</span></span>

- <span data-ttu-id="ed63e-269">**Alapvető** – A dolgozók alapvető információi, például a kapcsolattartási adatok, demográfiai adatok azonosító adatok, családi adatok, a katonai szolgálat állapota, kiküldetésekre vonatkozó adatok, illetve személyes és rendkívüli kapcsolattartók.</span><span class="sxs-lookup"><span data-stu-id="ed63e-269">**Basic** – Maintain basic information about a worker, such as contact information, demographic information, identification information, family information, military service status, expatriate information, and personal and emergency contacts.</span></span>
- <span data-ttu-id="ed63e-270">**Foglalkoztatás** – Információk a dolgozó munkaviszonyáról, például a vállalati vagy szervezeti kapcsolat, hozzárendelt pozíció, kezdő és záró dátumok, munkajogosultság, foglalkoztatás feltételei, nyugdíj, szabadság és áthelyezéssel kapcsolatos információk.</span><span class="sxs-lookup"><span data-stu-id="ed63e-270">**Employment** – Maintain information about a worker's employment, such as company or organization affiliation, position assignment, start and end dates, work eligibility, terms of employment, pension, vacation, and relocation information.</span></span>
- <span data-ttu-id="ed63e-271">**Szabadság és a távollét** – A dolgozó távolléteinek kezelése, például a munkaidő-naptárak, a távolléti tranzakciók és távollét beállítása.</span><span class="sxs-lookup"><span data-stu-id="ed63e-271">**Leave and absence** – Maintain information about a worker's absences, such as working calendars, absence transactions, and absence setup.</span></span>
- <span data-ttu-id="ed63e-272">**Kompenzáció és bérlista** – dolgozói kompenzációs tervek és bérlistainformációk kezelése, például felvétel konstrukciója, jutalmak, teljesítmény, jutalék, adózási információk, nyugdíj és fizetéslevonások.</span><span class="sxs-lookup"><span data-stu-id="ed63e-272">**Compensation and payroll** – Maintain information about a worker's compensation plans and payroll information, such as plan enrollment, awards, performance, commission, tax information, retirement, and salary deductions.</span></span>

<span data-ttu-id="ed63e-273">A dolgozóinformációk létrehozása esetén ne felejtse el a következő adatokat és beállításokat, amelyeket a Dayforce használ.</span><span class="sxs-lookup"><span data-stu-id="ed63e-273">When you enter worker information, keep in mind the following data and configurations that are used in Dayforce.</span></span>

#### <a name="general-information"></a><span data-ttu-id="ed63e-274">Általános információk</span><span class="sxs-lookup"><span data-stu-id="ed63e-274">General information</span></span>

- <span data-ttu-id="ed63e-275">Személyzeti szám (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-275">Personnel number (required)</span></span>
- <span data-ttu-id="ed63e-276">Utónév (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-276">First name (required)</span></span>
- <span data-ttu-id="ed63e-277">Vezetéknév (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-277">Last name (required)</span></span>
- <span data-ttu-id="ed63e-278">Második keresztnév</span><span class="sxs-lookup"><span data-stu-id="ed63e-278">Middle name</span></span>
- <span data-ttu-id="ed63e-279">Szolgálati idő dátuma</span><span class="sxs-lookup"><span data-stu-id="ed63e-279">Seniority date</span></span>
- <span data-ttu-id="ed63e-280">Más néven</span><span class="sxs-lookup"><span data-stu-id="ed63e-280">Known as</span></span>

#### <a name="personal-information"></a><span data-ttu-id="ed63e-281">Személyes információ</span><span class="sxs-lookup"><span data-stu-id="ed63e-281">Personal information</span></span>

- <span data-ttu-id="ed63e-282">Családi állapot (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-282">Marital status (required)</span></span>
- <span data-ttu-id="ed63e-283">Születési dátum (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-283">Birth date (required)</span></span>
- <span data-ttu-id="ed63e-284">Nem (szükséges)</span><span class="sxs-lookup"><span data-stu-id="ed63e-284">Gender (required)</span></span>
- <span data-ttu-id="ed63e-285">Fogyatékkal élő személy</span><span class="sxs-lookup"><span data-stu-id="ed63e-285">Person with disabilities</span></span>
- <span data-ttu-id="ed63e-286">Állampolgárság ország régió (csak a Mexikó)</span><span class="sxs-lookup"><span data-stu-id="ed63e-286">Nationality country region (only for Mexico)</span></span>

#### <a name="address-information"></a><span data-ttu-id="ed63e-287">Címadatok</span><span class="sxs-lookup"><span data-stu-id="ed63e-287">Address information</span></span>

- <span data-ttu-id="ed63e-288">Elsődleges (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-288">Primary (required)</span></span>
- <span data-ttu-id="ed63e-289">Ország/régiót (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-289">Country/region (required)</span></span>
- <span data-ttu-id="ed63e-290">Irányítószámot (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-290">Postal code (required)</span></span>
- <span data-ttu-id="ed63e-291">Utca, házszám (kötelező) (csak Mexikó esetén)</span><span class="sxs-lookup"><span data-stu-id="ed63e-291">Street Number (required) (Only for Mexico)</span></span>
- <span data-ttu-id="ed63e-292">Épületblokk (csak a Mexikó)</span><span class="sxs-lookup"><span data-stu-id="ed63e-292">Building Complement (Only for Mexico)</span></span>
- <span data-ttu-id="ed63e-293">Város (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-293">City (required)</span></span>
- <span data-ttu-id="ed63e-294">Állam (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-294">State (required)</span></span>
- <span data-ttu-id="ed63e-295">Megye (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-295">County (required)</span></span>

#### <a name="contact-information"></a><span data-ttu-id="ed63e-296">Névjegy adatai</span><span class="sxs-lookup"><span data-stu-id="ed63e-296">Contact information</span></span> 

- <span data-ttu-id="ed63e-297">Elsődleges (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-297">Primary (required)</span></span>
- <span data-ttu-id="ed63e-298">Kapcsolattartó száma (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-298">Contact number (required)</span></span>
- <span data-ttu-id="ed63e-299">Mellék</span><span class="sxs-lookup"><span data-stu-id="ed63e-299">Extension</span></span>

#### <a name="payroll-information-and-earning-codes"></a><span data-ttu-id="ed63e-300">Bérlistaadatok és bevételkódok</span><span class="sxs-lookup"><span data-stu-id="ed63e-300">Payroll information and earning codes</span></span>

<span data-ttu-id="ed63e-301">Alkalmazottak hozzárendelhetők meghatározott bevételekhez adott fizetési gyakorisággal, és magadható elsődleges fizetési mód.</span><span class="sxs-lookup"><span data-stu-id="ed63e-301">Employees may be assigned specific earnings at a given frequency of payment and have a preferred payment method.</span></span> <span data-ttu-id="ed63e-302">A következő mezőket a Dayforce arra használja, hogy garantálja, hogy ezeket a preferenciákat és beállításokat használja.</span><span class="sxs-lookup"><span data-stu-id="ed63e-302">The following fields are used in Dayforce to help guarantee that those preferences and settings are used.</span></span>

##### <a name="earning-codes"></a><span data-ttu-id="ed63e-303">Bevételkódok</span><span class="sxs-lookup"><span data-stu-id="ed63e-303">Earning codes</span></span>

- <span data-ttu-id="ed63e-304">Beosztás (szükséges)</span><span class="sxs-lookup"><span data-stu-id="ed63e-304">Position (required)</span></span>
- <span data-ttu-id="ed63e-305">Bevételkód (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-305">Earning Code (required)</span></span>
- <span data-ttu-id="ed63e-306">Gyakoriság (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-306">Frequency (required)</span></span>
- <span data-ttu-id="ed63e-307">Összeg (szükséges)</span><span class="sxs-lookup"><span data-stu-id="ed63e-307">Amount (required)</span></span>

##### <a name="payroll-information"></a><span data-ttu-id="ed63e-308">Bérlistaadatok</span><span class="sxs-lookup"><span data-stu-id="ed63e-308">Payroll information</span></span>

- <span data-ttu-id="ed63e-309">Kifizetési mód</span><span class="sxs-lookup"><span data-stu-id="ed63e-309">Payment Method</span></span>
- <span data-ttu-id="ed63e-310">Gazdasági régió (szükséges)</span><span class="sxs-lookup"><span data-stu-id="ed63e-310">Economic Region (required)</span></span>
- <span data-ttu-id="ed63e-311">Alkalmazott juttatásainak azonosítója</span><span class="sxs-lookup"><span data-stu-id="ed63e-311">Employee Benefits ID</span></span>
- <span data-ttu-id="ed63e-312">Nemzeti azonosító (szükséges)</span><span class="sxs-lookup"><span data-stu-id="ed63e-312">National ID Number (required)</span></span>
- <span data-ttu-id="ed63e-313">Katonai szolgálat száma</span><span class="sxs-lookup"><span data-stu-id="ed63e-313">Military Service Number</span></span>
- <span data-ttu-id="ed63e-314">Műszakazonosító (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-314">Shift ID (required)</span></span>
- <span data-ttu-id="ed63e-315">Adószám (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-315">Tax Number (required)</span></span>
- <span data-ttu-id="ed63e-316">Szakszervezeti azonosító (szükséges)</span><span class="sxs-lookup"><span data-stu-id="ed63e-316">Union ID (required)</span></span>
- <span data-ttu-id="ed63e-317">Munkanap azonosítója (szükséges)</span><span class="sxs-lookup"><span data-stu-id="ed63e-317">Work Day ID (required)</span></span>
- <span data-ttu-id="ed63e-318">Munkavállalási engedély száma</span><span class="sxs-lookup"><span data-stu-id="ed63e-318">Work Permit Number</span></span>

> [!NOTE]
> <span data-ttu-id="ed63e-319">A fizetési módhoz Mexikó támogatja a **Készpénzt**, **Csekket** (a vállalat fizikai csekkjét) és az **Elektronikus fizetést**.</span><span class="sxs-lookup"><span data-stu-id="ed63e-319">For the payment method, Mexico supports **Cash**, **Check** (the company's physical check), and **Electronic Payment**.</span></span> <span data-ttu-id="ed63e-320">Ha nincs fizetési mód van megadva, alapértelmezés szerint a **Csekk** használt.</span><span class="sxs-lookup"><span data-stu-id="ed63e-320">If np payment method is specified, **Check** is used by default.</span></span>

#### <a name="employment-details"></a><span data-ttu-id="ed63e-321">Foglalkoztatás részletei</span><span class="sxs-lookup"><span data-stu-id="ed63e-321">Employment details</span></span>

<span data-ttu-id="ed63e-322">Foglalkoztatási előzményei kulcsfontosságú információkat tartalmaznak a munkavállaók felvételi, elbocsátási, és újbóli felvétele állapotával kapcsolatosan a Dayforce-ban.</span><span class="sxs-lookup"><span data-stu-id="ed63e-322">Employment detail history is used as key information to derive an employee's hire, termination, and rehire statuses in Dayforce.</span></span> <span data-ttu-id="ed63e-323">Dayforce egyszerre csak egy aktív foglalkoztatásrekordot tesz lehetővé.</span><span class="sxs-lookup"><span data-stu-id="ed63e-323">Dayforce supports only one active employment record at a time.</span></span>

- <span data-ttu-id="ed63e-324">Foglalkoztatás kezdődátuma (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-324">Employment start date (required)</span></span>
- <span data-ttu-id="ed63e-325">Munkaviszony záró dátuma</span><span class="sxs-lookup"><span data-stu-id="ed63e-325">Employment end date</span></span>
- <span data-ttu-id="ed63e-326">Kezdő dátum</span><span class="sxs-lookup"><span data-stu-id="ed63e-326">Start date</span></span>
- <span data-ttu-id="ed63e-327">Módosított kezdési időpont</span><span class="sxs-lookup"><span data-stu-id="ed63e-327">Adjusted start date</span></span>
- <span data-ttu-id="ed63e-328">Munkaviszony megszűnésének dátuma (megszűntetéskor kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-328">Termination date (required upon termination)</span></span>
- <span data-ttu-id="ed63e-329">Felmondás oka (megszűntetéskor kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-329">Termination reason (required upon termination)</span></span>

<span data-ttu-id="ed63e-330">Az alkalmazott legfontosabb dátumai a következő adatokból vannak származtatva.</span><span class="sxs-lookup"><span data-stu-id="ed63e-330">An employee's key dates are derived by using the following information.</span></span>

| <span data-ttu-id="ed63e-331">Emberi erőforrások</span><span class="sxs-lookup"><span data-stu-id="ed63e-331">Human Resources</span></span>                | <span data-ttu-id="ed63e-332">Dayforce</span><span class="sxs-lookup"><span data-stu-id="ed63e-332">Dayforce</span></span>                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="ed63e-333">Legutóbbi felvételi dátum</span><span class="sxs-lookup"><span data-stu-id="ed63e-333">Most recent hire date</span></span> | <span data-ttu-id="ed63e-334">Foglalkoztatás kezdete az aktuális nem megszűntetett előzményrekordra</span><span class="sxs-lookup"><span data-stu-id="ed63e-334">Employment start of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="ed63e-335">Munkaviszony megszűnésének dátuma</span><span class="sxs-lookup"><span data-stu-id="ed63e-335">Termination date</span></span>      | <span data-ttu-id="ed63e-336">Foglalkoztatás befejezése az aktuális nem megszűntetett előzményrekordra</span><span class="sxs-lookup"><span data-stu-id="ed63e-336">Termination date of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="ed63e-337">Kezdő dátum</span><span class="sxs-lookup"><span data-stu-id="ed63e-337">Start date</span></span>            | <span data-ttu-id="ed63e-338">Módosított kezdési időpont, kezdődátum vagy foglalkoztatás kezdete az aktuális nem aktív előzményrekordra</span><span class="sxs-lookup"><span data-stu-id="ed63e-338">Adjusted start date, start date, or employment start of current non-active employment history record</span></span> |
| <span data-ttu-id="ed63e-339">Eredeti felvételi dátum</span><span class="sxs-lookup"><span data-stu-id="ed63e-339">Original hire date</span></span>    | <span data-ttu-id="ed63e-340">Foglalkoztatás kezdete legkorábbi foglalkoztatási előzményrekordra</span><span class="sxs-lookup"><span data-stu-id="ed63e-340">Employment start of earliest employment history record</span></span>                                               |

#### <a name="compensation"></a><span data-ttu-id="ed63e-341">Kompenzáció</span><span class="sxs-lookup"><span data-stu-id="ed63e-341">Compensation</span></span>

<span data-ttu-id="ed63e-342">Egy fix kompenzációs tervet kell társítani minden alkalmazott elsődleges pozíciójához az alkalmazási időszak alatt.</span><span class="sxs-lookup"><span data-stu-id="ed63e-342">A fixed compensation plan must be associated with every employee's primary position throughout an employment period.</span></span> <span data-ttu-id="ed63e-343">Az időszak a belépés dátumával (vagy a foglalkoztatás kezdő dátumával) kezdődik, és a munkaviszony megszűnéséig tart .</span><span class="sxs-lookup"><span data-stu-id="ed63e-343">This period starts on the date that the employee was hired (or the employment start date) and continues until termination.</span></span>

- <span data-ttu-id="ed63e-344">Érvényesség dátuma (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-344">Effective Date (required)</span></span>
- <span data-ttu-id="ed63e-345">Lejárati dátum</span><span class="sxs-lookup"><span data-stu-id="ed63e-345">Expiration date</span></span>
- <span data-ttu-id="ed63e-346">Fizetési díjalap (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-346">Pay Rate (required)</span></span>
- <span data-ttu-id="ed63e-347">Fizetési díjalapok átalakításai (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-347">Pay Rate Conversions (required)</span></span>
- <span data-ttu-id="ed63e-348">Évi egyenérték (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-348">Annual equivalent (required)</span></span>
- <span data-ttu-id="ed63e-349">Óránkénti egyenérték (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-349">Hourly equivalent (required)</span></span>

<span data-ttu-id="ed63e-350">Ha az óránkénti alkalmazottnak több beosztása van, az elsődleges beosztásához tartozó fix kompenzációja importálva lesz a Dayforce-ba, alkalmazott szintű alapdíj/-fizetés.</span><span class="sxs-lookup"><span data-stu-id="ed63e-350">If an hourly employee has multiple positions, the fixed compensation of the primary position is imported into Dayforce as the employee-level base rate/salary.</span></span> <span data-ttu-id="ed63e-351">A nem elsődleges beosztások esetén, az óránkénti díj a megfelelő pozícióba lesz mentve Dayforce-ban.</span><span class="sxs-lookup"><span data-stu-id="ed63e-351">For non-primary positions, the hourly rate is saved to the corresponding position in Dayforce.</span></span>

<span data-ttu-id="ed63e-352">Ha a fizetett alkalmazott több beosztással rendelkezik, a összesített óradíj és éves fizetés származtatva lesz az összes aktív beosztásból mint az alkalmazotti szintű alapdíj/-fizetés.</span><span class="sxs-lookup"><span data-stu-id="ed63e-352">If a salaried employee has multiple positions, the cumulative hour rate and annual salary across all active positions are derived and used as the employee-level base rate/salary.</span></span>

#### <a name="identification-numbers"></a><span data-ttu-id="ed63e-353">Azonosítószámok</span><span class="sxs-lookup"><span data-stu-id="ed63e-353">Identification numbers</span></span>

##### <a name="social-security-identifier"></a><span data-ttu-id="ed63e-354">Társadalombiztosítási azonosító</span><span class="sxs-lookup"><span data-stu-id="ed63e-354">Social Security identifier</span></span> 

<span data-ttu-id="ed63e-355">Minden alkalmazottnak kell egy elsődleges azonosítóval rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="ed63e-355">Every employee must have one primary identifier.</span></span> <span data-ttu-id="ed63e-356">Ez az azonosító legyen **TAJ-szám** azonosítótípus kell legyen.</span><span class="sxs-lookup"><span data-stu-id="ed63e-356">This identifier must be of **SSN** identification type.</span></span> <span data-ttu-id="ed63e-357">A Dayforce-ban automatikusan van származtatva az alkalmazott társadalombiztosítási azonosítójából, mely a felvételhez szükséges.</span><span class="sxs-lookup"><span data-stu-id="ed63e-357">In Dayforce, it's automatically derived as the employee's Social Security identifier that is required for hire.</span></span>

- <span data-ttu-id="ed63e-358">Elsődleges (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-358">Primary (required)</span></span>
- <span data-ttu-id="ed63e-359">Azonosító típusa = „TAJ-szám”</span><span class="sxs-lookup"><span data-stu-id="ed63e-359">Identification Type = "SSN"</span></span>
- <span data-ttu-id="ed63e-360">Kibocsátás dátuma</span><span class="sxs-lookup"><span data-stu-id="ed63e-360">Issued Date</span></span>
- <span data-ttu-id="ed63e-361">Lejárat dátuma</span><span class="sxs-lookup"><span data-stu-id="ed63e-361">Expiration Date</span></span>

<span data-ttu-id="ed63e-362">Az alkalmazottak több azonosítószámot is megadhatnak **TAJ-szám** azonosítótípushoz.</span><span class="sxs-lookup"><span data-stu-id="ed63e-362">Employees can declare multiple identification numbers of the **SSN** identification type.</span></span> <span data-ttu-id="ed63e-363">Azonban csak az **Elsődlegesként** megjelölt rekord van integrálva Dayforce-ba, függetlenül attól, hogy a szám aktív vagy lejárt.</span><span class="sxs-lookup"><span data-stu-id="ed63e-363">However, only the record that is marked as **Primary** is integrated into Dayforce, regardless of whether the number is active or expired.</span></span>

#### <a name="bank-accounts-and-disbursements"></a><span data-ttu-id="ed63e-364">Bankszámlák és kifizetések</span><span class="sxs-lookup"><span data-stu-id="ed63e-364">Bank accounts and disbursements</span></span>

<span data-ttu-id="ed63e-365">Érvényes bankszámlaadatokat meg kell adni minden olyan alkalmazotthoz, aki úgy dönt, hogy a banki átutalással kéri fizetését.</span><span class="sxs-lookup"><span data-stu-id="ed63e-365">Valid bank account information must be entered for any employee who chooses to be paid via bank account transfers.</span></span>

| <span data-ttu-id="ed63e-366">Emberi erőforrások</span><span class="sxs-lookup"><span data-stu-id="ed63e-366">Human Resources</span></span>                         | <span data-ttu-id="ed63e-367">Dayforce</span><span class="sxs-lookup"><span data-stu-id="ed63e-367">Dayforce</span></span>                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="ed63e-368">Bankszámlaszám (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-368">Bank account number (required)</span></span> |                                                                                                             |
| <span data-ttu-id="ed63e-369">SWIFT-kód (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-369">SWIFT code (required)</span></span>          | <span data-ttu-id="ed63e-370">**Bankazonosító** ez a mező Mexikóban történő bérlistafeldolgozáskor használatos.</span><span class="sxs-lookup"><span data-stu-id="ed63e-370">**Bank ID** field used when processing payroll in Mexico.</span></span>                                                             |
| <span data-ttu-id="ed63e-371">Ágazati szám (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-371">Branch number (required)</span></span>       |                                                                                                             |
| <span data-ttu-id="ed63e-372">Bankszámla típusa (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-372">Bank account type (required)</span></span>   | <span data-ttu-id="ed63e-373">**Számlatípus** ez a mező Mexikóban történő bérlistafeldolgozáskor használatos.</span><span class="sxs-lookup"><span data-stu-id="ed63e-373">**Account type** field used when processing payroll in Mexico.</span></span> <span data-ttu-id="ed63e-374">Támogatott értékek: **Folyószámla** és **Bérlista**</span><span class="sxs-lookup"><span data-stu-id="ed63e-374">Supported values include **Checking** and **Payroll**.</span></span> |

> [!NOTE]
> <span data-ttu-id="ed63e-375">Alkalmazottak, akik úgy döntenek, hogy a banki átutaláson keresztülkérik fizetésük, meg kell adniuk egy hivatkozást egy jogi személyhez tartozó egyenlegszámlához, melynek elsődleges címének Mexikóban kell lennie és egy Mexikói bank érvényes bankszámlájához van társítva.</span><span class="sxs-lookup"><span data-stu-id="ed63e-375">Employees who choose to be paid via bank account transfers must provide a link to a remainder account that is under a legal entity that has its primary address in Mexico and associated with a valid bank account from a Mexican bank.</span></span> <span data-ttu-id="ed63e-376">Minden egyéb nem egyenlegszámla figyelmen kívül lesz hagyva.</span><span class="sxs-lookup"><span data-stu-id="ed63e-376">All other non-remainder accounts are ignored.</span></span>

#### <a name="address-information"></a><span data-ttu-id="ed63e-377">Címadatok</span><span class="sxs-lookup"><span data-stu-id="ed63e-377">Address information</span></span>

<span data-ttu-id="ed63e-378">Minden alkalmazottnak kell egy elsődleges hellyel rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="ed63e-378">Every employee must have one primary location.</span></span> <span data-ttu-id="ed63e-379">A Dayforce-ban ezen hely alapján van meghatározva az alkalmazott elsődleges tartózkodási helye adózási célokból.</span><span class="sxs-lookup"><span data-stu-id="ed63e-379">In Dayforce, this location is used to determine the employee's primary residence for tax purposes.</span></span>

- <span data-ttu-id="ed63e-380">Elsődleges (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-380">Primary (required)</span></span>
- <span data-ttu-id="ed63e-381">Ország/régiót (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-381">Country/region (required)</span></span>
- <span data-ttu-id="ed63e-382">Irányítószám/postai kód (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-382">Zip/postal code (required)</span></span>
- <span data-ttu-id="ed63e-383">Utca (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-383">Street (required)</span></span>
- <span data-ttu-id="ed63e-384">Házszám (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-384">Street Number (required)</span></span>
- <span data-ttu-id="ed63e-385">Épületblokk</span><span class="sxs-lookup"><span data-stu-id="ed63e-385">Building Complement</span></span>
- <span data-ttu-id="ed63e-386">Város (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-386">City (required)</span></span>
- <span data-ttu-id="ed63e-387">Állam (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-387">State (required)</span></span>
- <span data-ttu-id="ed63e-388">Megye (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-388">County (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a><span data-ttu-id="ed63e-389">Az adatok konfigurálása bérlista létrehozásához az Egyesült Államokban és Kanadában</span><span class="sxs-lookup"><span data-stu-id="ed63e-389">Configure your data to generate payroll in United States and Canada</span></span>

<span data-ttu-id="ed63e-390">Ha a fizetést generálása alkalmazottaknak az Egyesült Államokban és Kanadában, a következő elemeket kell beállítani:</span><span class="sxs-lookup"><span data-stu-id="ed63e-390">If you're generating pay for employees in the United States and Canada, the following elements must be configured:</span></span>

- <span data-ttu-id="ed63e-391">Részlegek szükségesek beosztásokhoz.</span><span class="sxs-lookup"><span data-stu-id="ed63e-391">Departments are required on positions.</span></span>
- <span data-ttu-id="ed63e-392">Költséghelyek pénzügyi dimenziókként kell beállítani, és az alapértelmezett pénzügyi dimenzió karakterlánc első elemének kell lennie.</span><span class="sxs-lookup"><span data-stu-id="ed63e-392">Cost centers must be set as financial dimensions and must be the first element in the default financial dimension string.</span></span>

> [!NOTE] 
> <span data-ttu-id="ed63e-393">Konfigurálhatja a Human Resources alkalmazást úgy, hogy a beosztásokhoz kötelező legyen beállítani részleget.</span><span class="sxs-lookup"><span data-stu-id="ed63e-393">You can configure Human Resources to require that Positions specify a Department.</span></span> <span data-ttu-id="ed63e-394">Ehhez kattintson a **Emberi erőforrások megosztott beosztásai > Beosztások > Részlegek szükségesek beosztásokhoz.** elemre.</span><span class="sxs-lookup"><span data-stu-id="ed63e-394">To do this, go to **Human Resources Shared Positions > Positions > Require departments on positions**.</span></span> <span data-ttu-id="ed63e-395">Azt ajánljuk, hogy ezt a beállítást tartassa be az integráció során.</span><span class="sxs-lookup"><span data-stu-id="ed63e-395">We recommend that this setting be enforced for the integration.</span></span>

### <a name="job-types"></a><span data-ttu-id="ed63e-396">Feladattípusok</span><span class="sxs-lookup"><span data-stu-id="ed63e-396">Job types</span></span>

<span data-ttu-id="ed63e-397">Beosztástípusok használatával a hasonló feladatok kategóriákba sorolhatók.</span><span class="sxs-lookup"><span data-stu-id="ed63e-397">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="ed63e-398">A beosztástípusok szükségesek az Egyesült Államokban és Kanadában a bérlisták feldolgozásához.</span><span class="sxs-lookup"><span data-stu-id="ed63e-398">Job types are required in order to process payroll in the United States and Canada.</span></span> <span data-ttu-id="ed63e-399">Beosztástípusok többek között a teljes és részmunkaidős, illetve a munkabéres és az órabéres.</span><span class="sxs-lookup"><span data-stu-id="ed63e-399">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="ed63e-400">A beosztástípusok a fizetéstípusokként vannak hozzárendelve a Dayforce-hoz, melyek jelzik, hogy a munkavállaló órás vagy bérezéses.</span><span class="sxs-lookup"><span data-stu-id="ed63e-400">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="ed63e-401">A következő feladattípusok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="ed63e-401">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="ed63e-402">Feladattípus</span><span class="sxs-lookup"><span data-stu-id="ed63e-402">Job type</span></span>   | <span data-ttu-id="ed63e-403">Leírás</span><span class="sxs-lookup"><span data-stu-id="ed63e-403">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="ed63e-404">Óránként</span><span class="sxs-lookup"><span data-stu-id="ed63e-404">Hourly</span></span>     | <span data-ttu-id="ed63e-405">Óránként</span><span class="sxs-lookup"><span data-stu-id="ed63e-405">Hourly</span></span>      |
| <span data-ttu-id="ed63e-406">Bérezéses</span><span class="sxs-lookup"><span data-stu-id="ed63e-406">Salaried</span></span>   | <span data-ttu-id="ed63e-407">Bérezéses</span><span class="sxs-lookup"><span data-stu-id="ed63e-407">Salaried</span></span>    |

### <a name="position-types"></a><span data-ttu-id="ed63e-408">Beosztási típusok</span><span class="sxs-lookup"><span data-stu-id="ed63e-408">Position types</span></span> 

<span data-ttu-id="ed63e-409">Ne használjon beosztástípusokat annak leírására, hogy a beosztás teljes munkaidős, részmunkaidős vagy más.</span><span class="sxs-lookup"><span data-stu-id="ed63e-409">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="ed63e-410">A feladattípusok a fizetésosztályokként vannak hozzárendelve a Dayforce-hoz, melyek jelzik, hogy a munkavállaló teljes- vagy részmunkaidős.</span><span class="sxs-lookup"><span data-stu-id="ed63e-410">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="ed63e-411">A következő beosztástípusok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="ed63e-411">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="ed63e-412">Beosztás típusa</span><span class="sxs-lookup"><span data-stu-id="ed63e-412">Position type</span></span>   | <span data-ttu-id="ed63e-413">Leírás</span><span class="sxs-lookup"><span data-stu-id="ed63e-413">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="ed63e-414">Teljes munkaidős</span><span class="sxs-lookup"><span data-stu-id="ed63e-414">Full-time</span></span>       | <span data-ttu-id="ed63e-415">Teljes munkaidős alkalmazott</span><span class="sxs-lookup"><span data-stu-id="ed63e-415">Full time employee</span></span> |
| <span data-ttu-id="ed63e-416">Részmunkaidős</span><span class="sxs-lookup"><span data-stu-id="ed63e-416">Part-time</span></span>       | <span data-ttu-id="ed63e-417">Részmunkaidős alkalmazott</span><span class="sxs-lookup"><span data-stu-id="ed63e-417">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="ed63e-418">Okkódok</span><span class="sxs-lookup"><span data-stu-id="ed63e-418">Reason codes</span></span>

<span data-ttu-id="ed63e-419">Az alkalmazottak állapotával kapcsolatos okkódok tájékoztatnak.</span><span class="sxs-lookup"><span data-stu-id="ed63e-419">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="ed63e-420">Okkódok a Dayforce-hoz állapot okaként vannak hozzárendelve, melyek jelzik egy alkalmazott beosztásában vagy alkalmazotti státuszában bekövetkezett változások okát.</span><span class="sxs-lookup"><span data-stu-id="ed63e-420">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="ed63e-421">A következő okkódok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="ed63e-421">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="ed63e-422">Okkód</span><span class="sxs-lookup"><span data-stu-id="ed63e-422">Reason code</span></span>    | <span data-ttu-id="ed63e-423">Leírás</span><span class="sxs-lookup"><span data-stu-id="ed63e-423">Description</span></span>      | <span data-ttu-id="ed63e-424">Alkalmazandó forgatókönyvek</span><span class="sxs-lookup"><span data-stu-id="ed63e-424">Applicable scenarios</span></span> |
|----------------|------------------|----------------------|
| <span data-ttu-id="ed63e-425">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="ed63e-425">RESIGNATION</span></span>    | <span data-ttu-id="ed63e-426">Felmondás</span><span class="sxs-lookup"><span data-stu-id="ed63e-426">Resignation</span></span>      | <span data-ttu-id="ed63e-427">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="ed63e-427">Terminate worker</span></span>     |
| <span data-ttu-id="ed63e-428">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="ed63e-428">TERMINATION</span></span>    | <span data-ttu-id="ed63e-429">Befejezés</span><span class="sxs-lookup"><span data-stu-id="ed63e-429">Termination</span></span>      | <span data-ttu-id="ed63e-430">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="ed63e-430">Terminate worker</span></span>     |
| <span data-ttu-id="ed63e-431">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="ed63e-431">RETIREMENT</span></span>     | <span data-ttu-id="ed63e-432">Megszüntetés</span><span class="sxs-lookup"><span data-stu-id="ed63e-432">Retirement</span></span>       | <span data-ttu-id="ed63e-433">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="ed63e-433">Terminate worker</span></span>     |
| <span data-ttu-id="ed63e-434">EGYÉB</span><span class="sxs-lookup"><span data-stu-id="ed63e-434">OTHER</span></span>          | <span data-ttu-id="ed63e-435">Egyéb okok</span><span class="sxs-lookup"><span data-stu-id="ed63e-435">Other Reasons</span></span>    | <span data-ttu-id="ed63e-436">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="ed63e-436">Terminate worker</span></span>     |
| <span data-ttu-id="ed63e-437">DEATH</span><span class="sxs-lookup"><span data-stu-id="ed63e-437">DEATH</span></span>          | <span data-ttu-id="ed63e-438">Elhalálozás</span><span class="sxs-lookup"><span data-stu-id="ed63e-438">Death</span></span>            | <span data-ttu-id="ed63e-439">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="ed63e-439">Terminate worker</span></span>     |
| <span data-ttu-id="ed63e-440">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="ed63e-440">LEAVEOFABSENCE</span></span> | <span data-ttu-id="ed63e-441">Szabadság</span><span class="sxs-lookup"><span data-stu-id="ed63e-441">Leave of Absence</span></span> | <span data-ttu-id="ed63e-442">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="ed63e-442">Terminate worker</span></span>     |
| <span data-ttu-id="ed63e-443">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="ed63e-443">CONTRACTEND</span></span>    | <span data-ttu-id="ed63e-444">Szerződés vége</span><span class="sxs-lookup"><span data-stu-id="ed63e-444">End of Contract</span></span>  | <span data-ttu-id="ed63e-445">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="ed63e-445">Terminate worker</span></span>     |
| <span data-ttu-id="ed63e-446">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="ed63e-446">SALARYCHANGE</span></span>   | <span data-ttu-id="ed63e-447">Munkabér módosítása</span><span class="sxs-lookup"><span data-stu-id="ed63e-447">Change of Salary</span></span> | <span data-ttu-id="ed63e-448">Kompenzáció</span><span class="sxs-lookup"><span data-stu-id="ed63e-448">Compensation</span></span>         |

### <a name="marital-status"></a><span data-ttu-id="ed63e-449">Családi állapot</span><span class="sxs-lookup"><span data-stu-id="ed63e-449">Marital status</span></span>

<span data-ttu-id="ed63e-450">Családi állapot értékei Dayforce-hoz vannak rendelve és konvertálva szükség esetén az elfogadható értékekre az integráció során.</span><span class="sxs-lookup"><span data-stu-id="ed63e-450">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="ed63e-451">Az alábbi táblázat bemutatja, hogy családi állapot értékek hogyan vannak leképezve a Dayforce -ban.</span><span class="sxs-lookup"><span data-stu-id="ed63e-451">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="ed63e-452">Emberi erőforrások</span><span class="sxs-lookup"><span data-stu-id="ed63e-452">Human Resources</span></span>                 | <span data-ttu-id="ed63e-453">Dayforce</span><span class="sxs-lookup"><span data-stu-id="ed63e-453">Dayforce</span></span>             |
|------------------------|----------------------|
| <span data-ttu-id="ed63e-454">Nős/férjezett</span><span class="sxs-lookup"><span data-stu-id="ed63e-454">Married</span></span>                | <span data-ttu-id="ed63e-455">Nős/férjezett</span><span class="sxs-lookup"><span data-stu-id="ed63e-455">Married</span></span>              |
| <span data-ttu-id="ed63e-456">Egy</span><span class="sxs-lookup"><span data-stu-id="ed63e-456">Single</span></span>                 | <span data-ttu-id="ed63e-457">Egy</span><span class="sxs-lookup"><span data-stu-id="ed63e-457">Single</span></span>               |
| <span data-ttu-id="ed63e-458">Özvegy</span><span class="sxs-lookup"><span data-stu-id="ed63e-458">Widowed</span></span>                | <span data-ttu-id="ed63e-459">Özvegy</span><span class="sxs-lookup"><span data-stu-id="ed63e-459">Widowed</span></span>              |
| <span data-ttu-id="ed63e-460">Elvált</span><span class="sxs-lookup"><span data-stu-id="ed63e-460">Divorced</span></span>               | <span data-ttu-id="ed63e-461">Elvált</span><span class="sxs-lookup"><span data-stu-id="ed63e-461">Divorced</span></span>             |
| <span data-ttu-id="ed63e-462">Bejegyzett élettársi kapcsolat</span><span class="sxs-lookup"><span data-stu-id="ed63e-462">Registered Partnership</span></span> | <span data-ttu-id="ed63e-463">Élettársi viszony</span><span class="sxs-lookup"><span data-stu-id="ed63e-463">Domestic Partnership</span></span> |
| <span data-ttu-id="ed63e-464">Nincs</span><span class="sxs-lookup"><span data-stu-id="ed63e-464">None</span></span>                   | <span data-ttu-id="ed63e-465">Nincs</span><span class="sxs-lookup"><span data-stu-id="ed63e-465">None</span></span>                 |
| <span data-ttu-id="ed63e-466">Együttélés</span><span class="sxs-lookup"><span data-stu-id="ed63e-466">Cohabiting</span></span>             | <span data-ttu-id="ed63e-467">Együttélés</span><span class="sxs-lookup"><span data-stu-id="ed63e-467">Cohabiting</span></span>           |

### <a name="gender"></a><span data-ttu-id="ed63e-468">Nem</span><span class="sxs-lookup"><span data-stu-id="ed63e-468">Gender</span></span>

<span data-ttu-id="ed63e-469">A nemek a Dayforce-hoz vannak rendelve és konvertálva szükség esetén az elfogadható értékekre az integráció során.</span><span class="sxs-lookup"><span data-stu-id="ed63e-469">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="ed63e-470">Az alábbi táblázat bemutatja, hogy a nemek hogyan vannak leképezve a Dayforce-ban.</span><span class="sxs-lookup"><span data-stu-id="ed63e-470">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="ed63e-471">Emberi erőforrások</span><span class="sxs-lookup"><span data-stu-id="ed63e-471">Human Resources</span></span>       | <span data-ttu-id="ed63e-472">Dayforce</span><span class="sxs-lookup"><span data-stu-id="ed63e-472">Dayforce</span></span>        |
|--------------|-----------------|
| <span data-ttu-id="ed63e-473">Férfi</span><span class="sxs-lookup"><span data-stu-id="ed63e-473">Male</span></span>         | <span data-ttu-id="ed63e-474">Férfi</span><span class="sxs-lookup"><span data-stu-id="ed63e-474">Male</span></span>            |
| <span data-ttu-id="ed63e-475">Nő</span><span class="sxs-lookup"><span data-stu-id="ed63e-475">Female</span></span>       | <span data-ttu-id="ed63e-476">Nő</span><span class="sxs-lookup"><span data-stu-id="ed63e-476">Female</span></span>          |
| <span data-ttu-id="ed63e-477">Nem meghatározott</span><span class="sxs-lookup"><span data-stu-id="ed63e-477">Non-specific</span></span> | <span data-ttu-id="ed63e-478">*Nem támogatott*</span><span class="sxs-lookup"><span data-stu-id="ed63e-478">*Not supported*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="ed63e-479">Bevételkódok</span><span class="sxs-lookup"><span data-stu-id="ed63e-479">Earning codes</span></span>

<span data-ttu-id="ed63e-480">A bevételkódok egyedi módon azonosítják a dolgozók által kapott fizetéstípusokat.</span><span class="sxs-lookup"><span data-stu-id="ed63e-480">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="ed63e-481">A kódoknak különböző paramétereket fednek le, amelyek a bevételekhez kapcsolódnak, például könyvelési szabályok, jelentési követelmények és bruttósítási lehetőségek.</span><span class="sxs-lookup"><span data-stu-id="ed63e-481">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="ed63e-482">Ha egy nem támogatott gyakoriság van használatban, a **Minden fizetés** gyakorisága van alapértelmezés szerint használva a kiszámításhoz.</span><span class="sxs-lookup"><span data-stu-id="ed63e-482">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="ed63e-483">Támogatott gyakoriságok</span><span class="sxs-lookup"><span data-stu-id="ed63e-483">Supported frequencies</span></span>

- <span data-ttu-id="ed63e-484">Összes</span><span class="sxs-lookup"><span data-stu-id="ed63e-484">All</span></span>
- <span data-ttu-id="ed63e-485">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="ed63e-485">EVERYPAY</span></span>
- <span data-ttu-id="ed63e-486">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="ed63e-486">EACHPAYPERIOD</span></span>
- <span data-ttu-id="ed63e-487">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="ed63e-487">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="ed63e-488">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="ed63e-488">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="ed63e-489">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="ed63e-489">1OFMTH</span></span>
- <span data-ttu-id="ed63e-490">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="ed63e-490">LASTOFMTH</span></span>
- <span data-ttu-id="ed63e-491">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="ed63e-491">2OFMTH</span></span>
- <span data-ttu-id="ed63e-492">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="ed63e-492">3OFMTH</span></span>
- <span data-ttu-id="ed63e-493">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="ed63e-493">4OFMTH</span></span>
- <span data-ttu-id="ed63e-494">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="ed63e-494">5OFMTH</span></span>
- <span data-ttu-id="ed63e-495">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="ed63e-495">1N2OFMTH</span></span>
- <span data-ttu-id="ed63e-496">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="ed63e-496">3N4OFMTH</span></span>
- <span data-ttu-id="ed63e-497">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="ed63e-497">1N3OFMTH</span></span>
- <span data-ttu-id="ed63e-498">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="ed63e-498">1N4OFMTH</span></span>
- <span data-ttu-id="ed63e-499">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="ed63e-499">2N3OFMTH</span></span>
- <span data-ttu-id="ed63e-500">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="ed63e-500">2N4OFMTH</span></span>
- <span data-ttu-id="ed63e-501">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="ed63e-501">1N2N3OFMTH</span></span>
- <span data-ttu-id="ed63e-502">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="ed63e-502">1N2N4OFMTH</span></span>
- <span data-ttu-id="ed63e-503">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="ed63e-503">1N3N4OFMTH</span></span>
- <span data-ttu-id="ed63e-504">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="ed63e-504">2N3N4OFMTH</span></span>
- <span data-ttu-id="ed63e-505">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="ed63e-505">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="ed63e-506">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="ed63e-506">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="ed63e-507">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="ed63e-507">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="ed63e-508">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="ed63e-508">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="ed63e-509">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="ed63e-509">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="ed63e-510">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="ed63e-510">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="ed63e-511">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="ed63e-511">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="ed63e-512">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="ed63e-512">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="ed63e-513">Címek</span><span class="sxs-lookup"><span data-stu-id="ed63e-513">Addresses</span></span>

<span data-ttu-id="ed63e-514">Az adott ország vagy régió, állam és megye (település) kódok specifikus formátumokat követelnek, hogy Dayforce és az országos és regionális szolgáltatók felismerjék azokat.</span><span class="sxs-lookup"><span data-stu-id="ed63e-514">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="ed63e-515">Annak ellenére, hogy a városok formátuma rugalmas, minden városnak társítva kell lennie egy államhoz.</span><span class="sxs-lookup"><span data-stu-id="ed63e-515">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="ed63e-516">Emberi erőforrások</span><span class="sxs-lookup"><span data-stu-id="ed63e-516">Human Resources</span></span>          | <span data-ttu-id="ed63e-517">Dayforce</span><span class="sxs-lookup"><span data-stu-id="ed63e-517">Dayforce</span></span>              |
|-----------------|-----------------------|
| <span data-ttu-id="ed63e-518">Ország/régió</span><span class="sxs-lookup"><span data-stu-id="ed63e-518">Country/Region</span></span>  | <span data-ttu-id="ed63e-519">Országkód</span><span class="sxs-lookup"><span data-stu-id="ed63e-519">Country Code</span></span>          |
| <span data-ttu-id="ed63e-520">Irányítószám / postai kód</span><span class="sxs-lookup"><span data-stu-id="ed63e-520">Zip/Postal Code</span></span> | <span data-ttu-id="ed63e-521">Irányítószám</span><span class="sxs-lookup"><span data-stu-id="ed63e-521">Postal Code</span></span>           |
| <span data-ttu-id="ed63e-522">Állami</span><span class="sxs-lookup"><span data-stu-id="ed63e-522">State</span></span>           | <span data-ttu-id="ed63e-523">Államkód</span><span class="sxs-lookup"><span data-stu-id="ed63e-523">State Code</span></span>            |
| <span data-ttu-id="ed63e-524">Város</span><span class="sxs-lookup"><span data-stu-id="ed63e-524">City</span></span>            | <span data-ttu-id="ed63e-525">Város</span><span class="sxs-lookup"><span data-stu-id="ed63e-525">City</span></span>                  |
| <span data-ttu-id="ed63e-526">Megye</span><span class="sxs-lookup"><span data-stu-id="ed63e-526">County</span></span>          | <span data-ttu-id="ed63e-527">Megye (Helyhatóság)</span><span class="sxs-lookup"><span data-stu-id="ed63e-527">County (Municipality)</span></span> |
| <span data-ttu-id="ed63e-528">Utca</span><span class="sxs-lookup"><span data-stu-id="ed63e-528">Street</span></span>          | <span data-ttu-id="ed63e-529">Cím 1. sora</span><span class="sxs-lookup"><span data-stu-id="ed63e-529">Address Line 1</span></span>        |

### <a name="tax-regions"></a><span data-ttu-id="ed63e-530">Adórégiók</span><span class="sxs-lookup"><span data-stu-id="ed63e-530">Tax regions</span></span>

<span data-ttu-id="ed63e-531">Az adórégiók a megfelelő adó megállapítására szolgálnak, amelyet a bérlista létrehozásakor kell alkalmazni.</span><span class="sxs-lookup"><span data-stu-id="ed63e-531">Tax regions are used to determine the appropriate tax that should be applied during payroll generation.</span></span> <span data-ttu-id="ed63e-532">Az adórégiók helycímként vannak a Dayforce-hoz rendelve.</span><span class="sxs-lookup"><span data-stu-id="ed63e-532">Tax regions are mapped to Dayforce as location addresses.</span></span> <span data-ttu-id="ed63e-533">Az alapértelmezett adórégiót a dolgozó aktív beosztásával kell társítani.</span><span class="sxs-lookup"><span data-stu-id="ed63e-533">The default tax region must be associated with the worker's active position.</span></span> 

- <span data-ttu-id="ed63e-534">Adórégió (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-534">Tax region (required)</span></span>
- <span data-ttu-id="ed63e-535">Ország/régió (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-535">Country/Region (required)</span></span>
- <span data-ttu-id="ed63e-536">Állam (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-536">State (required)</span></span>
- <span data-ttu-id="ed63e-537">Megye</span><span class="sxs-lookup"><span data-stu-id="ed63e-537">County</span></span> 
- <span data-ttu-id="ed63e-538">Város (kötelező)</span><span class="sxs-lookup"><span data-stu-id="ed63e-538">City (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a><span data-ttu-id="ed63e-539">Adatok konfigurálása bérlista létrehozásához Mexikóban</span><span class="sxs-lookup"><span data-stu-id="ed63e-539">Configure your data to generate payroll in Mexico</span></span>

<span data-ttu-id="ed63e-540">Ha a fizetést generál alkalmazottaknak Mexikóban, a következő elemeket kell beállítani:</span><span class="sxs-lookup"><span data-stu-id="ed63e-540">If you're generating pay for employees in Mexico, the following elements must be configured:</span></span>

- <span data-ttu-id="ed63e-541">Részlegek szükségesek beosztásokhoz.</span><span class="sxs-lookup"><span data-stu-id="ed63e-541">Departments are required on positions.</span></span>
- <span data-ttu-id="ed63e-542">Költséghelyek pénzügyi dimenziókként kell beállítani, és az Alapértelmezett pénzügyi dimenzió karakterlánc első elemének kell lennie.</span><span class="sxs-lookup"><span data-stu-id="ed63e-542">Cost centers must be set as financial dimensions and must be the first element in the Default Financial Dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="ed63e-543">Beosztástípusok</span><span class="sxs-lookup"><span data-stu-id="ed63e-543">Job types</span></span>

<span data-ttu-id="ed63e-544">Beosztástípusok használatával a hasonló feladatok kategóriákba sorolhatók.</span><span class="sxs-lookup"><span data-stu-id="ed63e-544">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="ed63e-545">Mexikóban a Bérlista feldolgozásához feladattípusok szükségesek.</span><span class="sxs-lookup"><span data-stu-id="ed63e-545">Job types are required in order to process payroll in Mexico.</span></span> <span data-ttu-id="ed63e-546">Beosztástípusok többek között a teljes és részmunkaidős, illetve a munkabéres és az órabéres.</span><span class="sxs-lookup"><span data-stu-id="ed63e-546">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="ed63e-547">A beosztástípusok a fizetéstípusokként vannak hozzárendelve a Dayforce-hoz, melyek jelzik, hogy a munkavállaló órás vagy bérezéses.</span><span class="sxs-lookup"><span data-stu-id="ed63e-547">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="ed63e-548">A következő feladattípusok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="ed63e-548">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="ed63e-549">Feladattípus</span><span class="sxs-lookup"><span data-stu-id="ed63e-549">Job type</span></span>   | <span data-ttu-id="ed63e-550">Leírás</span><span class="sxs-lookup"><span data-stu-id="ed63e-550">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="ed63e-551">Óránként</span><span class="sxs-lookup"><span data-stu-id="ed63e-551">Hourly</span></span>     | <span data-ttu-id="ed63e-552">MX Órabér</span><span class="sxs-lookup"><span data-stu-id="ed63e-552">MX Hourly</span></span>   |
| <span data-ttu-id="ed63e-553">Bérezéses</span><span class="sxs-lookup"><span data-stu-id="ed63e-553">Salaried</span></span>   | <span data-ttu-id="ed63e-554">MX Bérezéses</span><span class="sxs-lookup"><span data-stu-id="ed63e-554">MX Salaried</span></span> |

### <a name="position-types"></a><span data-ttu-id="ed63e-555">Beosztási típusok</span><span class="sxs-lookup"><span data-stu-id="ed63e-555">Position types</span></span> 

<span data-ttu-id="ed63e-556">Ne használjon beosztástípusokat annak leírására, hogy a beosztás teljes munkaidős, részmunkaidős vagy más.</span><span class="sxs-lookup"><span data-stu-id="ed63e-556">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="ed63e-557">A feladattípusok a fizetésosztályokként vannak hozzárendelve a Dayforce-hoz, melyek jelzik, hogy a munkavállaló teljes- vagy részmunkaidős.</span><span class="sxs-lookup"><span data-stu-id="ed63e-557">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="ed63e-558">A következő beosztástípusok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="ed63e-558">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="ed63e-559">Beosztás típusa</span><span class="sxs-lookup"><span data-stu-id="ed63e-559">Position type</span></span>   | <span data-ttu-id="ed63e-560">Leírás</span><span class="sxs-lookup"><span data-stu-id="ed63e-560">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="ed63e-561">Teljes munkaidős</span><span class="sxs-lookup"><span data-stu-id="ed63e-561">Full-time</span></span>       | <span data-ttu-id="ed63e-562">Teljes munkaidős alkalmazott</span><span class="sxs-lookup"><span data-stu-id="ed63e-562">Full time employee</span></span> |
| <span data-ttu-id="ed63e-563">Részmunkaidős</span><span class="sxs-lookup"><span data-stu-id="ed63e-563">Part-time</span></span>       | <span data-ttu-id="ed63e-564">Részmunkaidős alkalmazott</span><span class="sxs-lookup"><span data-stu-id="ed63e-564">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="ed63e-565">Okkódok</span><span class="sxs-lookup"><span data-stu-id="ed63e-565">Reason codes</span></span>

<span data-ttu-id="ed63e-566">Az alkalmazottak állapotával kapcsolatos okkódok tájékoztatnak.</span><span class="sxs-lookup"><span data-stu-id="ed63e-566">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="ed63e-567">Okkódok a Dayforce-hoz állapot okaként vannak hozzárendelve, melyek jelzik egy alkalmazott beosztásában vagy alkalmazotti státuszában bekövetkezett változások okát.</span><span class="sxs-lookup"><span data-stu-id="ed63e-567">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="ed63e-568">A következő okkódok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="ed63e-568">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="ed63e-569">Okkód</span><span class="sxs-lookup"><span data-stu-id="ed63e-569">Reason code</span></span>            | <span data-ttu-id="ed63e-570">Leírás</span><span class="sxs-lookup"><span data-stu-id="ed63e-570">Description</span></span>                    | <span data-ttu-id="ed63e-571">Alkalmazandó forgatókönyvek</span><span class="sxs-lookup"><span data-stu-id="ed63e-571">Applicable scenarios</span></span> |
|------------------------|--------------------------------|----------------------|
| <span data-ttu-id="ed63e-572">DEPARTUREBEFOREPAYMENT</span><span class="sxs-lookup"><span data-stu-id="ed63e-572">DEPARTUREBEFOREPAYMENT</span></span> | <span data-ttu-id="ed63e-573">Indulás első bérlista előtt</span><span class="sxs-lookup"><span data-stu-id="ed63e-573">Departure before first payroll</span></span> | <span data-ttu-id="ed63e-574">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="ed63e-574">Terminate worker</span></span>     |
| <span data-ttu-id="ed63e-575">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="ed63e-575">RESIGNATION</span></span>            | <span data-ttu-id="ed63e-576">Felmondás</span><span class="sxs-lookup"><span data-stu-id="ed63e-576">Resignation</span></span>                    | <span data-ttu-id="ed63e-577">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="ed63e-577">Terminate worker</span></span>     |
| <span data-ttu-id="ed63e-578">PENSION</span><span class="sxs-lookup"><span data-stu-id="ed63e-578">PENSION</span></span>                | <span data-ttu-id="ed63e-579">Nyugdíj</span><span class="sxs-lookup"><span data-stu-id="ed63e-579">Pension</span></span>                        | <span data-ttu-id="ed63e-580">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="ed63e-580">Terminate worker</span></span>     |
| <span data-ttu-id="ed63e-581">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="ed63e-581">TERMINATION</span></span>            | <span data-ttu-id="ed63e-582">Befejezés</span><span class="sxs-lookup"><span data-stu-id="ed63e-582">Termination</span></span>                    | <span data-ttu-id="ed63e-583">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="ed63e-583">Terminate worker</span></span>     |
| <span data-ttu-id="ed63e-584">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="ed63e-584">RETIREMENT</span></span>             | <span data-ttu-id="ed63e-585">Megszüntetés</span><span class="sxs-lookup"><span data-stu-id="ed63e-585">Retirement</span></span>                     | <span data-ttu-id="ed63e-586">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="ed63e-586">Terminate worker</span></span>     |
| <span data-ttu-id="ed63e-587">ABSENTEE</span><span class="sxs-lookup"><span data-stu-id="ed63e-587">ABSENTEE</span></span>               | <span data-ttu-id="ed63e-588">Távollevő</span><span class="sxs-lookup"><span data-stu-id="ed63e-588">Absentee</span></span>                       | <span data-ttu-id="ed63e-589">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="ed63e-589">Terminate worker</span></span>     |
| <span data-ttu-id="ed63e-590">EGYÉB</span><span class="sxs-lookup"><span data-stu-id="ed63e-590">OTHER</span></span>                  | <span data-ttu-id="ed63e-591">Egyéb okok</span><span class="sxs-lookup"><span data-stu-id="ed63e-591">Other Reasons</span></span>                  | <span data-ttu-id="ed63e-592">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="ed63e-592">Terminate worker</span></span>     |
| <span data-ttu-id="ed63e-593">CLOSURE</span><span class="sxs-lookup"><span data-stu-id="ed63e-593">CLOSURE</span></span>                | <span data-ttu-id="ed63e-594">Üzletzárás</span><span class="sxs-lookup"><span data-stu-id="ed63e-594">Business Closure</span></span>               | <span data-ttu-id="ed63e-595">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="ed63e-595">Terminate worker</span></span>     |
| <span data-ttu-id="ed63e-596">DEATH</span><span class="sxs-lookup"><span data-stu-id="ed63e-596">DEATH</span></span>                  | <span data-ttu-id="ed63e-597">Elhalálozás</span><span class="sxs-lookup"><span data-stu-id="ed63e-597">Death</span></span>                          | <span data-ttu-id="ed63e-598">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="ed63e-598">Terminate worker</span></span>     |
| <span data-ttu-id="ed63e-599">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="ed63e-599">LEAVEOFABSENCE</span></span>         | <span data-ttu-id="ed63e-600">Szabadság</span><span class="sxs-lookup"><span data-stu-id="ed63e-600">Leave of Absence</span></span>               | <span data-ttu-id="ed63e-601">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="ed63e-601">Terminate worker</span></span>     |
| <span data-ttu-id="ed63e-602">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="ed63e-602">CONTRACTEND</span></span>            | <span data-ttu-id="ed63e-603">Szerződés vége</span><span class="sxs-lookup"><span data-stu-id="ed63e-603">End of Contract</span></span>                | <span data-ttu-id="ed63e-604">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="ed63e-604">Terminate worker</span></span>     |
| <span data-ttu-id="ed63e-605">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="ed63e-605">SALARYCHANGE</span></span>           | <span data-ttu-id="ed63e-606">Munkabér módosítása</span><span class="sxs-lookup"><span data-stu-id="ed63e-606">Change of Salary</span></span>               | <span data-ttu-id="ed63e-607">Kompenzáció</span><span class="sxs-lookup"><span data-stu-id="ed63e-607">Compensation</span></span>         |

### <a name="terms-of-employment"></a><span data-ttu-id="ed63e-608">Foglalkoztatási feltételek</span><span class="sxs-lookup"><span data-stu-id="ed63e-608">Terms of employment</span></span>

<span data-ttu-id="ed63e-609">A Foglalkoztatási feltételek foglalkoztatási feltételkategóriák létrehozására használatosak.</span><span class="sxs-lookup"><span data-stu-id="ed63e-609">Terms of employment are used to create categories of employment terms.</span></span> <span data-ttu-id="ed63e-610">A feltételek alkalmazási mutató értékekként vannak a Dayforce-hoz rendelve.</span><span class="sxs-lookup"><span data-stu-id="ed63e-610">The terms are mapped to Dayforce as employment indicator values.</span></span>

<span data-ttu-id="ed63e-611">A következő alkalmazási feltételek és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="ed63e-611">The following terms of employment and descriptions are required.</span></span>

| <span data-ttu-id="ed63e-612">Foglalkoztatási feltételek</span><span class="sxs-lookup"><span data-stu-id="ed63e-612">Terms of employment</span></span>   | <span data-ttu-id="ed63e-613">Leírás</span><span class="sxs-lookup"><span data-stu-id="ed63e-613">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="ed63e-614">Szabályos</span><span class="sxs-lookup"><span data-stu-id="ed63e-614">Regular</span></span>               | <span data-ttu-id="ed63e-615">Szabályos</span><span class="sxs-lookup"><span data-stu-id="ed63e-615">Regular</span></span>     |
| <span data-ttu-id="ed63e-616">Közvetlen</span><span class="sxs-lookup"><span data-stu-id="ed63e-616">Direct</span></span>                | <span data-ttu-id="ed63e-617">Közvetlen</span><span class="sxs-lookup"><span data-stu-id="ed63e-617">Direct</span></span>      |
| <span data-ttu-id="ed63e-618">Szakmai gyakorlat</span><span class="sxs-lookup"><span data-stu-id="ed63e-618">Internship</span></span>            | <span data-ttu-id="ed63e-619">Szakmai gyakorlat</span><span class="sxs-lookup"><span data-stu-id="ed63e-619">Internship</span></span>  |
| <span data-ttu-id="ed63e-620">Állandó</span><span class="sxs-lookup"><span data-stu-id="ed63e-620">Permanent</span></span>             | <span data-ttu-id="ed63e-621">Állandó</span><span class="sxs-lookup"><span data-stu-id="ed63e-621">Permanent</span></span>   |

### <a name="marital-status"></a><span data-ttu-id="ed63e-622">Családi állapot</span><span class="sxs-lookup"><span data-stu-id="ed63e-622">Marital status</span></span>

<span data-ttu-id="ed63e-623">Családi állapot értékei Dayforce-hoz vannak rendelve és konvertálva szükség esetén az elfogadható értékekre az integráció során.</span><span class="sxs-lookup"><span data-stu-id="ed63e-623">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="ed63e-624">Az alábbi táblázat bemutatja, hogy családi állapot értékek hogyan vannak leképezve a Dayforce -ban.</span><span class="sxs-lookup"><span data-stu-id="ed63e-624">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="ed63e-625">Emberi erőforrások</span><span class="sxs-lookup"><span data-stu-id="ed63e-625">Human Resources</span></span>                 | <span data-ttu-id="ed63e-626">Dayforce</span><span class="sxs-lookup"><span data-stu-id="ed63e-626">Dayforce</span></span>                  |
|------------------------|---------------------------|
| <span data-ttu-id="ed63e-627">Nős/férjezett</span><span class="sxs-lookup"><span data-stu-id="ed63e-627">Married</span></span>                | <span data-ttu-id="ed63e-628">Nős/férjezett</span><span class="sxs-lookup"><span data-stu-id="ed63e-628">Married</span></span>                   |
| <span data-ttu-id="ed63e-629">Egy</span><span class="sxs-lookup"><span data-stu-id="ed63e-629">Single</span></span>                 | <span data-ttu-id="ed63e-630">Egy</span><span class="sxs-lookup"><span data-stu-id="ed63e-630">Single</span></span>                    |
| <span data-ttu-id="ed63e-631">Özvegy</span><span class="sxs-lookup"><span data-stu-id="ed63e-631">Widowed</span></span>                | <span data-ttu-id="ed63e-632">Özvegy</span><span class="sxs-lookup"><span data-stu-id="ed63e-632">Widowed</span></span>                   |
| <span data-ttu-id="ed63e-633">Elvált</span><span class="sxs-lookup"><span data-stu-id="ed63e-633">Divorced</span></span>               | <span data-ttu-id="ed63e-634">Elvált</span><span class="sxs-lookup"><span data-stu-id="ed63e-634">Divorced</span></span>                  |
| <span data-ttu-id="ed63e-635">Bejegyzett élettársi kapcsolat</span><span class="sxs-lookup"><span data-stu-id="ed63e-635">Registered Partnership</span></span> | <span data-ttu-id="ed63e-636">Élettársi viszony</span><span class="sxs-lookup"><span data-stu-id="ed63e-636">Domestic Partnership</span></span>      |
| <span data-ttu-id="ed63e-637">Nincs</span><span class="sxs-lookup"><span data-stu-id="ed63e-637">None</span></span>                   | <span data-ttu-id="ed63e-638">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="ed63e-638">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="ed63e-639">Együttélés</span><span class="sxs-lookup"><span data-stu-id="ed63e-639">Cohabiting</span></span>             | <span data-ttu-id="ed63e-640">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="ed63e-640">*Not supported by Mexico*</span></span> |

### <a name="gender"></a><span data-ttu-id="ed63e-641">Nem</span><span class="sxs-lookup"><span data-stu-id="ed63e-641">Gender</span></span>

<span data-ttu-id="ed63e-642">A nemek a Dayforce-hoz vannak rendelve és konvertálva szükség esetén az elfogadható értékekre az integráció során.</span><span class="sxs-lookup"><span data-stu-id="ed63e-642">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="ed63e-643">Az alábbi táblázat bemutatja, hogy a nemek hogyan vannak leképezve a Dayforce-ban.</span><span class="sxs-lookup"><span data-stu-id="ed63e-643">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="ed63e-644">Emberi erőforrások</span><span class="sxs-lookup"><span data-stu-id="ed63e-644">Human Resources</span></span>       | <span data-ttu-id="ed63e-645">Dayforce</span><span class="sxs-lookup"><span data-stu-id="ed63e-645">Dayforce</span></span>                  |
|--------------|---------------------------|
| <span data-ttu-id="ed63e-646">Férfi</span><span class="sxs-lookup"><span data-stu-id="ed63e-646">Male</span></span>         | <span data-ttu-id="ed63e-647">Férfi</span><span class="sxs-lookup"><span data-stu-id="ed63e-647">Male</span></span>                      |
| <span data-ttu-id="ed63e-648">Nő</span><span class="sxs-lookup"><span data-stu-id="ed63e-648">Female</span></span>       | <span data-ttu-id="ed63e-649">Nő</span><span class="sxs-lookup"><span data-stu-id="ed63e-649">Female</span></span>                    |
| <span data-ttu-id="ed63e-650">Nem meghatározott</span><span class="sxs-lookup"><span data-stu-id="ed63e-650">Non-specific</span></span> | <span data-ttu-id="ed63e-651">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="ed63e-651">*Not supported by Mexico*</span></span> |

### <a name="payment-method"></a><span data-ttu-id="ed63e-652">Kifizetési mód</span><span class="sxs-lookup"><span data-stu-id="ed63e-652">Payment method</span></span>

<span data-ttu-id="ed63e-653">A Fizetési módok adják meg az alkalmazott és a vállalat számára az alkalmazott kifizetésének módja leírásának lehetőségét.</span><span class="sxs-lookup"><span data-stu-id="ed63e-653">Payment methods give the employee and the company a way to describe how employees will be paid.</span></span> <span data-ttu-id="ed63e-654">A Fizetési módok a Dayforce-hoz vannak rendelve és konvertálva szükség esetén az elfogadható értékekre az integráció során.</span><span class="sxs-lookup"><span data-stu-id="ed63e-654">Payment methods are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="ed63e-655">Az alábbi táblázat bemutatja, hogy a fizetés módok hogyan vannak leképezve a Dayforce-ban.</span><span class="sxs-lookup"><span data-stu-id="ed63e-655">The following table shows how payment methods are mapped to Dayforce.</span></span>

| <span data-ttu-id="ed63e-656">Emberi erőforrások</span><span class="sxs-lookup"><span data-stu-id="ed63e-656">Human Resources</span></span>             | <span data-ttu-id="ed63e-657">Dayforce</span><span class="sxs-lookup"><span data-stu-id="ed63e-657">Dayforce</span></span>                  |
|--------------------|---------------------------|
| <span data-ttu-id="ed63e-658">Készpénz</span><span class="sxs-lookup"><span data-stu-id="ed63e-658">Cash</span></span>               | <span data-ttu-id="ed63e-659">Készpénz</span><span class="sxs-lookup"><span data-stu-id="ed63e-659">Cash</span></span>                      |
| <span data-ttu-id="ed63e-660">Elektronikus fizetés</span><span class="sxs-lookup"><span data-stu-id="ed63e-660">Electronic Payment</span></span> | <span data-ttu-id="ed63e-661">Átvitel</span><span class="sxs-lookup"><span data-stu-id="ed63e-661">Transfer</span></span>                  |
| <span data-ttu-id="ed63e-662">Csekkes</span><span class="sxs-lookup"><span data-stu-id="ed63e-662">Check</span></span>              | <span data-ttu-id="ed63e-663">Csekk</span><span class="sxs-lookup"><span data-stu-id="ed63e-663">Cheque</span></span>                    |
| <span data-ttu-id="ed63e-664">Váltó</span><span class="sxs-lookup"><span data-stu-id="ed63e-664">Bank Draft</span></span>         | <span data-ttu-id="ed63e-665">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="ed63e-665">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="ed63e-666">Egyéb</span><span class="sxs-lookup"><span data-stu-id="ed63e-666">Other</span></span>              | <span data-ttu-id="ed63e-667">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="ed63e-667">*Not supported by Mexico*</span></span> |

### <a name="bank-account-type"></a><span data-ttu-id="ed63e-668">Bankszámla típusa</span><span class="sxs-lookup"><span data-stu-id="ed63e-668">Bank account type</span></span>

<span data-ttu-id="ed63e-669">Bankszámla-típusok az alkalmazottaknak történő elektronikus kifizetésekhez szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="ed63e-669">Bank account types are used for electronic payments to employees.</span></span> <span data-ttu-id="ed63e-670">Bankszámla típusa a Dayforce-ba átutalási számlaadatként van rendelve.</span><span class="sxs-lookup"><span data-stu-id="ed63e-670">Bank account types are mapped to Dayforce as transfer account information.</span></span> <span data-ttu-id="ed63e-671">A bankszámlatípusok szükség esetén konvertálva vannak az elfogadható értékekké az integráció során.</span><span class="sxs-lookup"><span data-stu-id="ed63e-671">The bank account types are translated, as appropriate, to the accepted values upon integration.</span></span>

| <span data-ttu-id="ed63e-672">Emberi erőforrások</span><span class="sxs-lookup"><span data-stu-id="ed63e-672">Human Resources</span></span>            | <span data-ttu-id="ed63e-673">Dayforce</span><span class="sxs-lookup"><span data-stu-id="ed63e-673">Dayforce</span></span>                  |
|-------------------|---------------------------|
| <span data-ttu-id="ed63e-674">Folyószámla</span><span class="sxs-lookup"><span data-stu-id="ed63e-674">Checking Account</span></span>  | <span data-ttu-id="ed63e-675">CheckingAccount</span><span class="sxs-lookup"><span data-stu-id="ed63e-675">CheckingAccount</span></span>           |
| <span data-ttu-id="ed63e-676">Bérlista elszámolási számlája</span><span class="sxs-lookup"><span data-stu-id="ed63e-676">Payroll Account</span></span>   | <span data-ttu-id="ed63e-677">PayrollAccount</span><span class="sxs-lookup"><span data-stu-id="ed63e-677">PayrollAccount</span></span>            |
| <span data-ttu-id="ed63e-678">Megtakarítási számla</span><span class="sxs-lookup"><span data-stu-id="ed63e-678">Savings Account</span></span>   | <span data-ttu-id="ed63e-679">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="ed63e-679">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="ed63e-680">BankGirot-számla</span><span class="sxs-lookup"><span data-stu-id="ed63e-680">BankGirot account</span></span> | <span data-ttu-id="ed63e-681">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="ed63e-681">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="ed63e-682">PlusGirot-számla</span><span class="sxs-lookup"><span data-stu-id="ed63e-682">PlusGirot account</span></span> | <span data-ttu-id="ed63e-683">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="ed63e-683">*Not supported by Mexico*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="ed63e-684">Bevételkódok</span><span class="sxs-lookup"><span data-stu-id="ed63e-684">Earning codes</span></span>

<span data-ttu-id="ed63e-685">A bevételkódok egyedi módon azonosítják a dolgozók által kapott fizetéstípusokat.</span><span class="sxs-lookup"><span data-stu-id="ed63e-685">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="ed63e-686">A kódoknak különböző paramétereket fednek le, amelyek a bevételekhez kapcsolódnak, például könyvelési szabályok, jelentési követelmények és bruttósítási lehetőségek.</span><span class="sxs-lookup"><span data-stu-id="ed63e-686">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="ed63e-687">Ha egy nem támogatott gyakoriság van használatban, a **Minden fizetés** gyakorisága van alapértelmezés szerint használva a kiszámításhoz.</span><span class="sxs-lookup"><span data-stu-id="ed63e-687">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="ed63e-688">Támogatott gyakoriságok</span><span class="sxs-lookup"><span data-stu-id="ed63e-688">Supported frequencies</span></span>

- <span data-ttu-id="ed63e-689">Összes</span><span class="sxs-lookup"><span data-stu-id="ed63e-689">All</span></span>
- <span data-ttu-id="ed63e-690">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="ed63e-690">EVERYPAY</span></span>
- <span data-ttu-id="ed63e-691">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="ed63e-691">EACHPAYPERIOD</span></span>
- <span data-ttu-id="ed63e-692">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="ed63e-692">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="ed63e-693">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="ed63e-693">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="ed63e-694">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="ed63e-694">1OFMTH</span></span>
- <span data-ttu-id="ed63e-695">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="ed63e-695">LASTOFMTH</span></span>
- <span data-ttu-id="ed63e-696">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="ed63e-696">2OFMTH</span></span>
- <span data-ttu-id="ed63e-697">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="ed63e-697">3OFMTH</span></span>
- <span data-ttu-id="ed63e-698">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="ed63e-698">4OFMTH</span></span>
- <span data-ttu-id="ed63e-699">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="ed63e-699">5OFMTH</span></span>
- <span data-ttu-id="ed63e-700">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="ed63e-700">1N2OFMTH</span></span>
- <span data-ttu-id="ed63e-701">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="ed63e-701">3N4OFMTH</span></span>
- <span data-ttu-id="ed63e-702">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="ed63e-702">1N3OFMTH</span></span>
- <span data-ttu-id="ed63e-703">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="ed63e-703">1N4OFMTH</span></span>
- <span data-ttu-id="ed63e-704">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="ed63e-704">2N3OFMTH</span></span>
- <span data-ttu-id="ed63e-705">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="ed63e-705">2N4OFMTH</span></span>
- <span data-ttu-id="ed63e-706">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="ed63e-706">1N2N3OFMTH</span></span>
- <span data-ttu-id="ed63e-707">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="ed63e-707">1N2N4OFMTH</span></span>
- <span data-ttu-id="ed63e-708">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="ed63e-708">1N3N4OFMTH</span></span>
- <span data-ttu-id="ed63e-709">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="ed63e-709">2N3N4OFMTH</span></span>
- <span data-ttu-id="ed63e-710">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="ed63e-710">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="ed63e-711">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="ed63e-711">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="ed63e-712">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="ed63e-712">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="ed63e-713">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="ed63e-713">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="ed63e-714">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="ed63e-714">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="ed63e-715">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="ed63e-715">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="ed63e-716">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="ed63e-716">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="ed63e-717">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="ed63e-717">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="ed63e-718">Címek</span><span class="sxs-lookup"><span data-stu-id="ed63e-718">Addresses</span></span>

<span data-ttu-id="ed63e-719">Az adott ország vagy régió, állam és megye (település) kódok specifikus formátumokat követelnek, hogy Dayforce és az országos és regionális szolgáltatók felismerjék azokat.</span><span class="sxs-lookup"><span data-stu-id="ed63e-719">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="ed63e-720">Annak ellenére, hogy a városok formátuma rugalmas, minden városnak társítva kell lennie egy államhoz.</span><span class="sxs-lookup"><span data-stu-id="ed63e-720">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="ed63e-721">Emberi erőforrások</span><span class="sxs-lookup"><span data-stu-id="ed63e-721">Human Resources</span></span>              | <span data-ttu-id="ed63e-722">Dayforce</span><span class="sxs-lookup"><span data-stu-id="ed63e-722">Dayforce</span></span>              |
|---------------------|-----------------------|
| <span data-ttu-id="ed63e-723">Ország/régió</span><span class="sxs-lookup"><span data-stu-id="ed63e-723">Country/Region</span></span>      | <span data-ttu-id="ed63e-724">Országkód</span><span class="sxs-lookup"><span data-stu-id="ed63e-724">Country Code</span></span>          |
| <span data-ttu-id="ed63e-725">Irányítószám / postai kód</span><span class="sxs-lookup"><span data-stu-id="ed63e-725">Zip/Postal Code</span></span>     | <span data-ttu-id="ed63e-726">Irányítószám</span><span class="sxs-lookup"><span data-stu-id="ed63e-726">Postal Code</span></span>           |
| <span data-ttu-id="ed63e-727">Állami</span><span class="sxs-lookup"><span data-stu-id="ed63e-727">State</span></span>               | <span data-ttu-id="ed63e-728">Államkód</span><span class="sxs-lookup"><span data-stu-id="ed63e-728">State Code</span></span>            |
| <span data-ttu-id="ed63e-729">Város</span><span class="sxs-lookup"><span data-stu-id="ed63e-729">City</span></span>                | <span data-ttu-id="ed63e-730">Város</span><span class="sxs-lookup"><span data-stu-id="ed63e-730">City</span></span>                  |
| <span data-ttu-id="ed63e-731">Megye</span><span class="sxs-lookup"><span data-stu-id="ed63e-731">County</span></span>              | <span data-ttu-id="ed63e-732">Megye (Helyhatóság)</span><span class="sxs-lookup"><span data-stu-id="ed63e-732">County (Municipality)</span></span> |
| <span data-ttu-id="ed63e-733">Utca</span><span class="sxs-lookup"><span data-stu-id="ed63e-733">Street</span></span>              | <span data-ttu-id="ed63e-734">Cím 1. sora</span><span class="sxs-lookup"><span data-stu-id="ed63e-734">Address Line 1</span></span>        |
| <span data-ttu-id="ed63e-735">Utca, házszám</span><span class="sxs-lookup"><span data-stu-id="ed63e-735">Street Number</span></span>       | <span data-ttu-id="ed63e-736">Cím 2. sora</span><span class="sxs-lookup"><span data-stu-id="ed63e-736">Address Line 2</span></span>        |
| <span data-ttu-id="ed63e-737">Épületblokk</span><span class="sxs-lookup"><span data-stu-id="ed63e-737">Building Complement</span></span> | <span data-ttu-id="ed63e-738">Cím 5. sora</span><span class="sxs-lookup"><span data-stu-id="ed63e-738">Address Line 5</span></span>        |

### <a name="passport-number"></a><span data-ttu-id="ed63e-739">Útlevél száma</span><span class="sxs-lookup"><span data-stu-id="ed63e-739">Passport number</span></span>

<span data-ttu-id="ed63e-740">Az alkalmazottak útlevél adatokat is nyilatkozhatnak.</span><span class="sxs-lookup"><span data-stu-id="ed63e-740">Employees can declare passport information.</span></span> <span data-ttu-id="ed63e-741">Az információ a **Útlevél** azonosítótípusra vonatkozik, és az alkalmazott Mexikó-specifikus adataiként van a Dayforce-ba integrálva.</span><span class="sxs-lookup"><span data-stu-id="ed63e-741">This information is of the **Passport** identification type and is integrated into Dayforce as part of an employee's Mexico-specific information.</span></span>

- <span data-ttu-id="ed63e-742">Azonosító típusa = „Útlevél”</span><span class="sxs-lookup"><span data-stu-id="ed63e-742">Identification Type = "Passport"</span></span>
- <span data-ttu-id="ed63e-743">Kibocsátás dátuma</span><span class="sxs-lookup"><span data-stu-id="ed63e-743">Issued Date</span></span>
- <span data-ttu-id="ed63e-744">Lejárat dátuma</span><span class="sxs-lookup"><span data-stu-id="ed63e-744">Expiration Date</span></span>

<span data-ttu-id="ed63e-745">Az alkalmazottak több azonosítószámot is megadhatnak az **Útlevél** azonosítótípushoz.</span><span class="sxs-lookup"><span data-stu-id="ed63e-745">Employees can declare multiple identification numbers of the **Passport** identification type.</span></span> <span data-ttu-id="ed63e-746">Azonban csak az aktuális aktív útlevélbejegyzés van integrálva a Dayforce-ba.</span><span class="sxs-lookup"><span data-stu-id="ed63e-746">However, only the current active passport entry is integrated into Dayforce.</span></span> <span data-ttu-id="ed63e-747">Ha az összes útlevélbejegyzés lejárt, a legutóbb kiállított lesz integrálva a Dayforce-ba.</span><span class="sxs-lookup"><span data-stu-id="ed63e-747">If all passport entries are expired, the passport that was most recently issued is integrated into Dayforce.</span></span>

