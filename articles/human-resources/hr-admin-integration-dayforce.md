---
title: A Dayforce szolgáltatással való integráció konfigurálása
description: A Microsoft Dynamics 365 Human Resources és a Ceridian Dayforce között végbemenő integrálás több olyan konfigurációs lépésre támaszkodik, amelyeket ebben a cikkben ismertünk. A fizetési időszak feldolgozása előtt konfigurálnia kell az integrációt a Human Resources alkalmazásban és a Dayforce alkalmazásban is.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 1647b7fbf84a78051e745e918954df32a2e7e1dd
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2021
ms.locfileid: "5890004"
---
# <a name="configure-integration-with-dayforce"></a><span data-ttu-id="dbf88-104">A Dayforce szolgáltatással való integráció konfigurálása</span><span class="sxs-lookup"><span data-stu-id="dbf88-104">Configure integration with Dayforce</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="dbf88-105">A Microsoft Dynamics 365 Human Resources és a Ceridian Dayforce között végbemenő integrálás több olyan konfigurációs lépésre támaszkodik, amelyeket ebben a cikkben ismertünk.</span><span class="sxs-lookup"><span data-stu-id="dbf88-105">The integration between Microsoft Dynamics 365 Human Resources and Ceridian Dayforce relies on several configuration steps that are described in this article.</span></span> <span data-ttu-id="dbf88-106">A fizetési időszak feldolgozása előtt konfigurálnia kell az integrációt a Human Resources alkalmazásban és a Dayforce alkalmazásban is.</span><span class="sxs-lookup"><span data-stu-id="dbf88-106">You must configure the integration in both Human Resources and Dayforce before you can process a pay run.</span></span>

<span data-ttu-id="dbf88-107">Ha olyan szolgáltatást használ a fizetési időszak teljesítéséhez, mint a Dayforce, engedélyeznie kell az integrációt a Human Resources alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="dbf88-107">When you use a service such as Dayforce to complete pay runs, you must enable the integration in Human Resources.</span></span> <span data-ttu-id="dbf88-108">Az integrációhoz szükségesek bizonyos adatok a Human Resources alkalmazásból.</span><span class="sxs-lookup"><span data-stu-id="dbf88-108">The integration requires specific data from Human Resources.</span></span> <span data-ttu-id="dbf88-109">Ezért ellenőriznie kell, hogy a Dayforce alkalmazáshoz hozzárendelt adatok olyan módon legyenek konfigurálva a Human Resources alkalmazásban, hogy az támogassa az integrációt.</span><span class="sxs-lookup"><span data-stu-id="dbf88-109">Therefore, you must verify that data that is mapped to Dayforce is configured in Human Resources in a manner that supports the integration.</span></span> <span data-ttu-id="dbf88-110">Az integráció a következő szélesebb adatkategóriákat használja:</span><span class="sxs-lookup"><span data-stu-id="dbf88-110">The integration uses the following broad categories of data:</span></span>

- <span data-ttu-id="dbf88-111">Emberierőforrás-adatok</span><span class="sxs-lookup"><span data-stu-id="dbf88-111">Human resources data</span></span>
- <span data-ttu-id="dbf88-112">Kompenzációadatok</span><span class="sxs-lookup"><span data-stu-id="dbf88-112">Compensation data</span></span>
- <span data-ttu-id="dbf88-113">Bérlistaadatok, mint kifizetési ciklus, fizetési időszakok és bevételkódok</span><span class="sxs-lookup"><span data-stu-id="dbf88-113">Payroll data, such as pay cycles, pay periods, and earning codes</span></span>
- <span data-ttu-id="dbf88-114">Dolgozóadatok</span><span class="sxs-lookup"><span data-stu-id="dbf88-114">Worker data</span></span>

<span data-ttu-id="dbf88-115">Ez a cikk leírja a lépéseket, amelyeket követni kell az integráció engedélyezéséhez.</span><span class="sxs-lookup"><span data-stu-id="dbf88-115">This article describes the steps that you must follow to enable the integration.</span></span> <span data-ttu-id="dbf88-116">Azt is bemutatja, hogy milyen típusú adatok és konfiguráció szükséges az integrációhoz.</span><span class="sxs-lookup"><span data-stu-id="dbf88-116">It also explains the types of data and the configuration details that the integration requires.</span></span>

## <a name="enable-the-integration"></a><span data-ttu-id="dbf88-117">Engedélyezze az integrációt</span><span class="sxs-lookup"><span data-stu-id="dbf88-117">Enable the integration</span></span>

<span data-ttu-id="dbf88-118">A Dayforce alkalmazáshoz való csatlakozáshoz a Human Resources alkalmazásban be kell kapcsolnia az integrációt és meg kell adnia a konfiguráció adatait.</span><span class="sxs-lookup"><span data-stu-id="dbf88-118">In Human Resources, you must turn on the integration and enter the configuration information to connect to Dayforce.</span></span> <span data-ttu-id="dbf88-119">Ha azt szeretné, hogy a létrehozott általános főkönyvi tranzakció importálva legyen a Microsoft Dynamics 365 Finance alkalmazásba, be kell állítania egy Microsoft Azure tárolási fiókot, majd adja meg, majd Azure tárolási kapcsolat karakterláncát a Finance alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="dbf88-119">If you want the general ledger transaction that is produced to be imported into Microsoft Dynamics 365 Finance, you must also set up a Microsoft Azure storage account and enter the Azure Storage connection string in Finance.</span></span>

<span data-ttu-id="dbf88-120">A Human Resources alkalmazásban lévő integráció bekapcsolásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="dbf88-120">To turn on the integration in Human Resources, follow these steps.</span></span>

1. <span data-ttu-id="dbf88-121">A **Rendszerfelügyelet** oldalon válassza az **Integrációkonfiguráció** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dbf88-121">On the **System administration** page, select **Integration configuration**.</span></span>
2. <span data-ttu-id="dbf88-122">Adja meg a biztonságos fájl átviteli protokollt (FTP) végpontot és a biztonságos FTP-mappa elérési útja.</span><span class="sxs-lookup"><span data-stu-id="dbf88-122">Enter the secure File Transfer Protocol (FTP) endpoint and the secure FTP folder path.</span></span>
3. <span data-ttu-id="dbf88-123">Adja meg azon felhasználó felhasználónevét és jelszavát, aki hozzáfér a biztonságos FTP végponthoz és a mappa elérési útjához.</span><span class="sxs-lookup"><span data-stu-id="dbf88-123">Enter the user name and password of the user who will access the secure FTP endpoint and folder path.</span></span>
4. <span data-ttu-id="dbf88-124">Tesztelje a kapcsolatot szükség szerint, és állítsa a **Bérlista-integráció engedélyezése** lehetőséggel **Igenre**.</span><span class="sxs-lookup"><span data-stu-id="dbf88-124">Test the connection, as required, and set the **Enable payroll integration** option to **Yes**.</span></span>

<span data-ttu-id="dbf88-125">Ha az integráció engedélyezve van, adatexport adatcsomagok és fájlok jönnek létre, valamint a gyakoriság is be van állítva.</span><span class="sxs-lookup"><span data-stu-id="dbf88-125">When the integration is turned on, the data export package and files are created, and the frequency is set.</span></span> <span data-ttu-id="dbf88-126">Igény szerint módosíthatja a gyakoriságot.</span><span class="sxs-lookup"><span data-stu-id="dbf88-126">You can change this frequency as you require.</span></span>

<span data-ttu-id="dbf88-127">Az Azure tárolási fiókokkal és az Azure tárolási kapcsolati karakterláncokkal kapcsolatos további információkat az alábbi Azure-cikkben találja:</span><span class="sxs-lookup"><span data-stu-id="dbf88-127">For more information about Azure storage accounts and Azure Storage connection strings, see the following Azure articles:</span></span>

- [<span data-ttu-id="dbf88-128">Az Azure Storage-fiókokról</span><span class="sxs-lookup"><span data-stu-id="dbf88-128">About Azure storage accounts</span></span>](/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [<span data-ttu-id="dbf88-129">Azure Storage kapcsolati karakterláncok konfigurálása</span><span class="sxs-lookup"><span data-stu-id="dbf88-129">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)

### <a name="technical-details-when-payroll-integration-is-enabled"></a><span data-ttu-id="dbf88-130">Technikai részletek a bérlista integrációjának engedélyezésekor</span><span class="sxs-lookup"><span data-stu-id="dbf88-130">Technical details when payroll integration is enabled</span></span>

<span data-ttu-id="dbf88-131">A bérlista-integráció bekapcsolása két elsődleges hatással jár:</span><span class="sxs-lookup"><span data-stu-id="dbf88-131">Turning on the payroll integration has two primary effects:</span></span>

- <span data-ttu-id="dbf88-132">Létrejön egy „bérlista-integráció exportálása” nevű adatexportálási projekt.</span><span class="sxs-lookup"><span data-stu-id="dbf88-132">A data export project named "Payroll integration export" is created.</span></span> <span data-ttu-id="dbf88-133">Ez a projekt a bérlista-integrációhoz szükséges entitásokat és mezőket tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="dbf88-133">This project contains the entities and fields required for the payroll integration.</span></span> <span data-ttu-id="dbf88-134">A projekt vizsgálatához nyissa meg a **Rendszerfelügyeletet**, válassza ki az **Adatkezelési** csempét, majd nyissa meg az adatprojektet a projektek listájából.</span><span class="sxs-lookup"><span data-stu-id="dbf88-134">To examine the project, go to **System administration**, select the **Data management** tile, and then open the data project from the list of projects.</span></span>
- <span data-ttu-id="dbf88-135">Ez a kötegelt feladat végrehajtja az adatexportálási projektet, titkosítja a létrejövő adatcsomagot, és átviszi az adatcsomag-fájlt az **Integráció konfigurációja** képernyőjén beállított SFTP végpontba.</span><span class="sxs-lookup"><span data-stu-id="dbf88-135">This batch job executes the data export project, encrypts the resulting data package, and transfers the data package file to the SFTP endpoint configured on the **Integration configuration** screen.</span></span>

> [!NOTE]
> <span data-ttu-id="dbf88-136">Az SFTP végpontra átvitt adatcsomag titkosítva van a csomag egyedi kulcsával.</span><span class="sxs-lookup"><span data-stu-id="dbf88-136">The data package transferred to the SFTP endpoint is encrypted using a key that is unique to the package.</span></span> <span data-ttu-id="dbf88-137">A kulcs egy Azure kulcstárolóban van, amely csak Ceridian számára érhető el.</span><span class="sxs-lookup"><span data-stu-id="dbf88-137">The key is in an Azure Key Vault that is accessible only by Ceridian.</span></span> <span data-ttu-id="dbf88-138">Az adatcsomag tartalmát nem lehet dekódolni és megvizsgálni.</span><span class="sxs-lookup"><span data-stu-id="dbf88-138">It is not possible to decrypt and examine the data package contents.</span></span> <span data-ttu-id="dbf88-139">Ha meg kell vizsgálnia az adatcsomag tartalmát, akkor manuálisan kell exportálnia a „Bérlista-integráció exportálása” adatprojektet, le kell töltenie, majd meg kell nyitnia.</span><span class="sxs-lookup"><span data-stu-id="dbf88-139">If you need to examine the contents of the data package, you need to export the "Payroll integration export" data project manually, download it, and then open it.</span></span> <span data-ttu-id="dbf88-140">A manuális exportálás nem alkalmazza a titkosítást, és nem viszi át a csomagot.</span><span class="sxs-lookup"><span data-stu-id="dbf88-140">Manual export will not apply encryption or transfer the package.</span></span>
> <span data-ttu-id="dbf88-141">Olyan esetekben, amikor az integrációs fájlokat egy Dynamics 365 Human Resources UAT- vagy teszkörnyezetből egy Ceridian Dayforce Test környezetbe küldik, a következő kulcstartó URL-cím használható: https://payrollintegrationprod.vault.azure.net.</span><span class="sxs-lookup"><span data-stu-id="dbf88-141">For instances where the integration files are sent from a Dynamics 365 Human Resources UAT or Sandbox environment to a Ceridian Dayforce Test environment, you can use the following key vault URL: https://payrollintegrationprod.vault.azure.net.</span></span>

## <a name="configure-your-data"></a><span data-ttu-id="dbf88-142">Adatai konfigurálása</span><span class="sxs-lookup"><span data-stu-id="dbf88-142">Configure your data</span></span> 

<span data-ttu-id="dbf88-143">A bérlista feldolgozásához konfigurálnia kell az emberierőforrás-adatokat a Human Resources alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="dbf88-143">To process payroll, you must configure human resource data in Human Resources.</span></span> <span data-ttu-id="dbf88-144">Be kell állítani a szervezeti adatokat, például a feladatokat és beosztásokat, valamint juttatásokra és a kompenzációra vonatkozó adatokat.</span><span class="sxs-lookup"><span data-stu-id="dbf88-144">You must set up organizational data, such as jobs and positions, together with benefits and compensation information.</span></span> <span data-ttu-id="dbf88-145">Ez az információ megadja a foglalkoztatásra, fizetésre és levonásokra vonatkozó információkat, melyek szükségesek az alkalmazott fizetések generálásához.</span><span class="sxs-lookup"><span data-stu-id="dbf88-145">This information provides the employment, pay, and deduction information that is required in order to generate employee pay.</span></span>

### <a name="human-resource-data"></a><span data-ttu-id="dbf88-146">Emberierőforrás-adatok</span><span class="sxs-lookup"><span data-stu-id="dbf88-146">Human resource data</span></span>

#### <a name="benefits"></a><span data-ttu-id="dbf88-147">Juttatások</span><span class="sxs-lookup"><span data-stu-id="dbf88-147">Benefits</span></span> 

<span data-ttu-id="dbf88-148">Az emberi erőforrások számos beállítási és karbantartási eszközt biztosít, amelyek segítségével beállíthatja és karbantarthatja a szervezet által a dolgozónak biztosított juttatásokat, levonásokat és dolgozói kompenzációs terveket.</span><span class="sxs-lookup"><span data-stu-id="dbf88-148">Human resources provides tools for the setup and maintenance of the benefits, deductions, and worker compensation plans that an organization offers or processes for its workers.</span></span>

<span data-ttu-id="dbf88-149">Juttatások létrehozása esetén ne felejtse el a következő adatokat és beállításokat, amelyeket a Dayforce használ.</span><span class="sxs-lookup"><span data-stu-id="dbf88-149">When you create benefits, keep in mind the following data and configurations that are used in Dayforce.</span></span>

##### <a name="benefit-plans"></a><span data-ttu-id="dbf88-150">Juttatási tervek</span><span class="sxs-lookup"><span data-stu-id="dbf88-150">Benefit plans</span></span>

- <span data-ttu-id="dbf88-151">Terv (szükséges)</span><span class="sxs-lookup"><span data-stu-id="dbf88-151">Plan (required)</span></span>
- <span data-ttu-id="dbf88-152">Típus (szükséges)</span><span class="sxs-lookup"><span data-stu-id="dbf88-152">Type (required)</span></span>
- <span data-ttu-id="dbf88-153">Bérlista hatása (szükséges)</span><span class="sxs-lookup"><span data-stu-id="dbf88-153">Payroll impact (required)</span></span>
- <span data-ttu-id="dbf88-154">Hátralékok helyreállítása</span><span class="sxs-lookup"><span data-stu-id="dbf88-154">Recover arrears</span></span>
- <span data-ttu-id="dbf88-155">Levonási módszer</span><span class="sxs-lookup"><span data-stu-id="dbf88-155">Deduction method</span></span>
- <span data-ttu-id="dbf88-156">Levonás prioritása</span><span class="sxs-lookup"><span data-stu-id="dbf88-156">Deduction priority</span></span>
- <span data-ttu-id="dbf88-157">Időszak korlátozása</span><span class="sxs-lookup"><span data-stu-id="dbf88-157">Limit period</span></span>
- <span data-ttu-id="dbf88-158">Összeghatár</span><span class="sxs-lookup"><span data-stu-id="dbf88-158">Limit amount</span></span>

##### <a name="benefits"></a><span data-ttu-id="dbf88-159">Juttatások</span><span class="sxs-lookup"><span data-stu-id="dbf88-159">Benefits</span></span>

- <span data-ttu-id="dbf88-160">Terv (szükséges)</span><span class="sxs-lookup"><span data-stu-id="dbf88-160">Plan (required)</span></span>
- <span data-ttu-id="dbf88-161">Típus (szükséges)</span><span class="sxs-lookup"><span data-stu-id="dbf88-161">Type (required)</span></span>
- <span data-ttu-id="dbf88-162">Lehetőség (szükséges)</span><span class="sxs-lookup"><span data-stu-id="dbf88-162">Option (required)</span></span>
- <span data-ttu-id="dbf88-163">Juttatás azonosítója (szükséges)</span><span class="sxs-lookup"><span data-stu-id="dbf88-163">Benefit ID (required)</span></span>
- <span data-ttu-id="dbf88-164">Gyakoriság</span><span class="sxs-lookup"><span data-stu-id="dbf88-164">Frequency</span></span>
- <span data-ttu-id="dbf88-165">Alap</span><span class="sxs-lookup"><span data-stu-id="dbf88-165">Basis</span></span>
- <span data-ttu-id="dbf88-166">Összeg vagy mérték</span><span class="sxs-lookup"><span data-stu-id="dbf88-166">Amount or rate</span></span>
- <span data-ttu-id="dbf88-167">Bevételkód</span><span class="sxs-lookup"><span data-stu-id="dbf88-167">Earning code</span></span>

##### <a name="supported-frequencies"></a><span data-ttu-id="dbf88-168">Támogatott gyakoriságok</span><span class="sxs-lookup"><span data-stu-id="dbf88-168">Supported frequencies</span></span> 

- <span data-ttu-id="dbf88-169">Heti</span><span class="sxs-lookup"><span data-stu-id="dbf88-169">Weekly</span></span>
- <span data-ttu-id="dbf88-170">Kétheti</span><span class="sxs-lookup"><span data-stu-id="dbf88-170">Bi-weekly</span></span>
- <span data-ttu-id="dbf88-171">Félhavi</span><span class="sxs-lookup"><span data-stu-id="dbf88-171">Semi-monthly</span></span>
- <span data-ttu-id="dbf88-172">Havi</span><span class="sxs-lookup"><span data-stu-id="dbf88-172">Monthly</span></span>

##### <a name="supported-bases"></a><span data-ttu-id="dbf88-173">Támogatott alapok</span><span class="sxs-lookup"><span data-stu-id="dbf88-173">Supported bases</span></span> 

- <span data-ttu-id="dbf88-174">Rögzített összeg</span><span class="sxs-lookup"><span data-stu-id="dbf88-174">Fixed amount</span></span>
- <span data-ttu-id="dbf88-175">Bevételek százaléka</span><span class="sxs-lookup"><span data-stu-id="dbf88-175">Percent of earnings</span></span>
- <span data-ttu-id="dbf88-176">Produktív órák</span><span class="sxs-lookup"><span data-stu-id="dbf88-176">Productive hours</span></span>

<span data-ttu-id="dbf88-177">A Dayforce létrehozza a következő levonásokat, a juttatási tervben definiált bérlistahatás alapján.</span><span class="sxs-lookup"><span data-stu-id="dbf88-177">Dayforce creates the following deductions, based on the payroll impact that is defined on the benefit plan.</span></span>

| <span data-ttu-id="dbf88-178">Kiválasztás a Human Resources alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="dbf88-178">Selection in Human Resources</span></span>        | <span data-ttu-id="dbf88-179">Eredmény a Dayforce-ban</span><span class="sxs-lookup"><span data-stu-id="dbf88-179">Result in Dayforce</span></span>                            |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="dbf88-180">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="dbf88-180">None</span></span>                       | <span data-ttu-id="dbf88-181">Nincs létrehozva levonás.</span><span class="sxs-lookup"><span data-stu-id="dbf88-181">No deduction is created.</span></span>                      |
| <span data-ttu-id="dbf88-182">Csak levonás</span><span class="sxs-lookup"><span data-stu-id="dbf88-182">Deduction only</span></span>             | <span data-ttu-id="dbf88-183">Alkalmazotti levonás jön létre.</span><span class="sxs-lookup"><span data-stu-id="dbf88-183">An employee deduction is created.</span></span>             |
| <span data-ttu-id="dbf88-184">Csak hozzájárulás</span><span class="sxs-lookup"><span data-stu-id="dbf88-184">Contribution only</span></span>          | <span data-ttu-id="dbf88-185">Egy alkalmazotti levonás jön létre.</span><span class="sxs-lookup"><span data-stu-id="dbf88-185">An employer deduction is created.</span></span>             |
| <span data-ttu-id="dbf88-186">Levonás és hozzájárulás</span><span class="sxs-lookup"><span data-stu-id="dbf88-186">Deduction and contribution</span></span> | <span data-ttu-id="dbf88-187">Alkalmazotti és a munkáltatói levonások jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="dbf88-187">Employee and employer deductions are created.</span></span> |

<span data-ttu-id="dbf88-188">A juttatási programok meghatározásával és kezelésével kapcsolatos további tájékoztatást a következő cikkekben találja:</span><span class="sxs-lookup"><span data-stu-id="dbf88-188">For more information about how to define and manage a benefits program, see the following articles:</span></span>

- [<span data-ttu-id="dbf88-189">Alkalmazotti juttatási program végrehajtása</span><span class="sxs-lookup"><span data-stu-id="dbf88-189">Deliver an employee benefits program</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [<span data-ttu-id="dbf88-190">Új juttatás létrehozása</span><span class="sxs-lookup"><span data-stu-id="dbf88-190">Create a new benefit</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [<span data-ttu-id="dbf88-191">Juttatásra való jogosultsági szabályok és irányelvek meghatározása</span><span class="sxs-lookup"><span data-stu-id="dbf88-191">Define benefit eligibility rules and policies</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [<span data-ttu-id="dbf88-192">Dolgozók juttatásainak felvétele és eltávolítása</span><span class="sxs-lookup"><span data-stu-id="dbf88-192">Enroll and remove benefits from workers</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a><span data-ttu-id="dbf88-193">Kompenzáció</span><span class="sxs-lookup"><span data-stu-id="dbf88-193">Compensation</span></span> 

<span data-ttu-id="dbf88-194">A kompenzációkezeléssel szabályozható az alapfizetés és a jutalmak kifizetése.</span><span class="sxs-lookup"><span data-stu-id="dbf88-194">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="dbf88-195">Egy alkalmazott fix fizetési díjalapja és érdemeken alapuló fizetése kezelhető a fix kompenzációs tervekkel.</span><span class="sxs-lookup"><span data-stu-id="dbf88-195">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="dbf88-196">Az ösztönző díjak kifizetése, például bónuszok, teljesítménydíjak, részvényopciók és kölcsönök, továbbá az egyszeri jutalmak a változó kompenzációs tervekben szabályozhatók.</span><span class="sxs-lookup"><span data-stu-id="dbf88-196">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span>

<span data-ttu-id="dbf88-197">A Dayforce a kompenzációs adatok segítségével kiszámítja az alkalmazott óradíját vagy éves díját.</span><span class="sxs-lookup"><span data-stu-id="dbf88-197">Dayforce uses compensation information to calculate an employee's hourly or annual rate.</span></span> <span data-ttu-id="dbf88-198">Fix kompenzációs tervek és a fizetési díjalap átalakítások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="dbf88-198">Fixed compensation plans and pay rate conversions are required.</span></span> <span data-ttu-id="dbf88-199">Az alkalmazottakat hozzá kell rendelni a fix kompenzációs tervhez.</span><span class="sxs-lookup"><span data-stu-id="dbf88-199">Employees must be associated with a fixed compensation plan.</span></span>

<span data-ttu-id="dbf88-200">A következő cikkekben bővebben olvashat a kompenzációs tervekről:</span><span class="sxs-lookup"><span data-stu-id="dbf88-200">For more information about compensation plans, see the following articles:</span></span>

- [<span data-ttu-id="dbf88-201">Fix kompenzációs konstrukciók létrehozása</span><span class="sxs-lookup"><span data-stu-id="dbf88-201">Create fixed compensation plans</span></span>](/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [<span data-ttu-id="dbf88-202">Változó kompenzációs konstrukciók létrehozása</span><span class="sxs-lookup"><span data-stu-id="dbf88-202">Create variable compensation plans</span></span>](/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [<span data-ttu-id="dbf88-203">Munkabér-/kompenzációs struktúra és tervek kialakítása</span><span class="sxs-lookup"><span data-stu-id="dbf88-203">Develop salary/compensation structure and plans</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [<span data-ttu-id="dbf88-204">Folyamatkompenzáció</span><span class="sxs-lookup"><span data-stu-id="dbf88-204">Process compensation</span></span>](/dynamics365/unified-operations/talent/process-compensation)
- [<span data-ttu-id="dbf88-205">Kompenzációs folyamat meghatározása és eredmények kiszámítása</span><span class="sxs-lookup"><span data-stu-id="dbf88-205">Define compensation process and calculate results</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [<span data-ttu-id="dbf88-206">Alkalmazottak felvétele fix kompenzációs konstrukcióba</span><span class="sxs-lookup"><span data-stu-id="dbf88-206">Enroll an employee in a fixed compensation plan</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [<span data-ttu-id="dbf88-207">Alkalmazottak felvétele változó kompenzációs konstrukcióba</span><span class="sxs-lookup"><span data-stu-id="dbf88-207">Enroll an employee in a variable compensation plan</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a><span data-ttu-id="dbf88-208">Beosztások</span><span class="sxs-lookup"><span data-stu-id="dbf88-208">Jobs</span></span> 

<span data-ttu-id="dbf88-209">A munkakör azon feladatok és felelősségek gyűjteménye, amelyek egy adott munkát végrehajtó személytől elvártak.</span><span class="sxs-lookup"><span data-stu-id="dbf88-209">A job is a collection of the tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="dbf88-210">További információért tekintse át az alábbi cikkeket:</span><span class="sxs-lookup"><span data-stu-id="dbf88-210">For more information, see the following articles:</span></span>

- [<span data-ttu-id="dbf88-211">Feladat összetevőinek beállítása</span><span class="sxs-lookup"><span data-stu-id="dbf88-211">Setting up the components of a job</span></span>](/dynamics365/unified-operations/talent/create-job)
- [<span data-ttu-id="dbf88-212">Új feladatok meghatározása</span><span class="sxs-lookup"><span data-stu-id="dbf88-212">Define new jobs</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a><span data-ttu-id="dbf88-213">Beosztások</span><span class="sxs-lookup"><span data-stu-id="dbf88-213">Positions</span></span>

<span data-ttu-id="dbf88-214">Egy beosztás egy feladat egyedi példánya.</span><span class="sxs-lookup"><span data-stu-id="dbf88-214">A position is an individual instance of a job.</span></span> <span data-ttu-id="dbf88-215">Például az „Értékesítési igazgató (Kelet)” pozíció egyike azon beosztásoknak, amelyek társíthatók az „Értékesítési igazgató” feladathoz.</span><span class="sxs-lookup"><span data-stu-id="dbf88-215">For example, the "Sales manager (East)" position is one of the positions that are associated with the "Sales manager" job.</span></span> <span data-ttu-id="dbf88-216">A beosztás létezik a részlegben.</span><span class="sxs-lookup"><span data-stu-id="dbf88-216">A position exists in a department.</span></span> <span data-ttu-id="dbf88-217">Egy beosztáshoz csak egy dolgozó rendelhető.</span><span class="sxs-lookup"><span data-stu-id="dbf88-217">Only one worker can be associated with each position.</span></span>

<span data-ttu-id="dbf88-218">A következő adatokat és konfigurációkat szem előtt tartani beosztások beállításakor:</span><span class="sxs-lookup"><span data-stu-id="dbf88-218">Keep the following data and configuration in mind when you set up positions:</span></span>

- <span data-ttu-id="dbf88-219">Beosztás (szükséges)</span><span class="sxs-lookup"><span data-stu-id="dbf88-219">Position (required)</span></span>
- <span data-ttu-id="dbf88-220">Leírás (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-220">Description (required)</span></span>
- <span data-ttu-id="dbf88-221">Munka (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-221">Job (required)</span></span>
- <span data-ttu-id="dbf88-222">Részleg (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-222">Department (required)</span></span>
- <span data-ttu-id="dbf88-223">Beosztás típusa (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-223">Position type (required)</span></span>
- <span data-ttu-id="dbf88-224">Teljes munkaidőssel egyenértékű</span><span class="sxs-lookup"><span data-stu-id="dbf88-224">Full-time equivalent</span></span>
- <span data-ttu-id="dbf88-225">Éves rendes munkaidő (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-225">Annual regular hours (required)</span></span>
- <span data-ttu-id="dbf88-226">Jogi személy által fizetett (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-226">Paid by legal entity (required)</span></span>
- <span data-ttu-id="dbf88-227">Fizetési ciklus (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-227">Pay cycle (required)</span></span>
- <span data-ttu-id="dbf88-228">Alapértelmezett pénzügyi dimenzió – Költséghely (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-228">Default financial dimension – Cost center (required)</span></span>
- <span data-ttu-id="dbf88-229">Dolgozó-hozzárendelés – dolgozó-hozzárendelés kezdete, hozzárendelés vége és okkód</span><span class="sxs-lookup"><span data-stu-id="dbf88-229">Worker assignment – Worker, assignment start, assignment end, reason code</span></span>

<span data-ttu-id="dbf88-230">A azonos osztály több beosztása társítva van az ugyanazon a feladathoz, azok össze lesznek vonva a Dayforce egyetlen pozíciójába.</span><span class="sxs-lookup"><span data-stu-id="dbf88-230">If multiple positions in the same department are associated with the same job, they are consolidated into a single position in Dayforce.</span></span>

<span data-ttu-id="dbf88-231">További információért tekintse át az alábbi cikkeket:</span><span class="sxs-lookup"><span data-stu-id="dbf88-231">For more information, see the following articles:</span></span>

- [<span data-ttu-id="dbf88-232">Munkaerő szervezése részlegek, feladatok és beosztások szerint</span><span class="sxs-lookup"><span data-stu-id="dbf88-232">Organize your workforce using departments, jobs, and positions</span></span>](/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [<span data-ttu-id="dbf88-233">Beosztások beállítása</span><span class="sxs-lookup"><span data-stu-id="dbf88-233">Set up positions</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a><span data-ttu-id="dbf88-234">Osztályok</span><span class="sxs-lookup"><span data-stu-id="dbf88-234">Departments</span></span>

<span data-ttu-id="dbf88-235">A részleg egy működési egység, amely a szervezet egy kategóriáját vagy működési területét képviseli.</span><span class="sxs-lookup"><span data-stu-id="dbf88-235">A department is an operating unit that represents a category or functional area of an organization.</span></span> <span data-ttu-id="dbf88-236">Egy részleg a szervezet egy konkrét területen végzett tevékenységeiért felel (például értékesítés, könyvelés, emberi erőforrások).</span><span class="sxs-lookup"><span data-stu-id="dbf88-236">A department is responsible for a specific area of the organization, such as sales, accounting, or human resources.</span></span> <span data-ttu-id="dbf88-237">A részlegek segítségével hozhatók létre jelentések a működési területekről.</span><span class="sxs-lookup"><span data-stu-id="dbf88-237">You can use departments to report on functional areas.</span></span> <span data-ttu-id="dbf88-238">A részlegeknek lehet eredménykimutatási felelőssége.</span><span class="sxs-lookup"><span data-stu-id="dbf88-238">Departments might have profit and loss responsibility.</span></span>

<span data-ttu-id="dbf88-239">További információért tekintse át az alábbi cikkeket:</span><span class="sxs-lookup"><span data-stu-id="dbf88-239">For more information, see the following articles:</span></span>

- [<span data-ttu-id="dbf88-240">Részleg létrehozása és társítása a szervezeti hierarchiához</span><span class="sxs-lookup"><span data-stu-id="dbf88-240">Create a department and associate it with the department hierarchy</span></span>](/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [<span data-ttu-id="dbf88-241">Új részlegek meghatározása</span><span class="sxs-lookup"><span data-stu-id="dbf88-241">Define new departments</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a><span data-ttu-id="dbf88-242">Fizetési ciklusok és fizetési időszakok</span><span class="sxs-lookup"><span data-stu-id="dbf88-242">Pay cycles and pay periods</span></span>

<span data-ttu-id="dbf88-243">A fizetési ciklus meghatározza, hogy milyen gyakran történik a bérlista folyósítása, és a dolgozók mely napokon kapnak fizetést,.</span><span class="sxs-lookup"><span data-stu-id="dbf88-243">A pay cycle determines how often payroll is run and the specific days when workers are paid.</span></span> <span data-ttu-id="dbf88-244">Például a kifizetési ciklus lehet, havi, és az alkalmazottak kaphatják a hónap utolsó napján a fizetésüket.</span><span class="sxs-lookup"><span data-stu-id="dbf88-244">For example, a pay cycle might be monthly, and employees might be paid on the last day of the month.</span></span> <span data-ttu-id="dbf88-245">Vagy a kifizetési ciklus lehet heti, és az alkalmazottak a fizetési időszak utáni kedden kaphatják fizetésüket.</span><span class="sxs-lookup"><span data-stu-id="dbf88-245">Alternatively, a pay cycle might be weekly, and employees might be paid on the Tuesday after the end of the pay period.</span></span> <span data-ttu-id="dbf88-246">Kifizetési ciklusok beosztásokhoz vannak rendelve, és szabályozzák, hogy az ebben a beosztásban lévő dolgozók mikor kapnak fizetést.</span><span class="sxs-lookup"><span data-stu-id="dbf88-246">Pay cycles are assigned to positions to control when workers in those positions are paid.</span></span>

<span data-ttu-id="dbf88-247">Miután létrehozott fizetési ciklusokat, minden egyes ciklushoz fizetési időszakot hozhat létre.</span><span class="sxs-lookup"><span data-stu-id="dbf88-247">After you create pay cycles, you can generate pay periods for each cycle.</span></span> <span data-ttu-id="dbf88-248">Minden fizetési időszakban egy alapértelmezett fizetési dátum van, amely a megadott adatokon alapul.</span><span class="sxs-lookup"><span data-stu-id="dbf88-248">Each pay period includes a default payment date that is based on information that you provide.</span></span> <span data-ttu-id="dbf88-249">Ugyanakkor az alapértelmezett fizetési dátumot a fizetési időszakban módosíthatja kivételekhez például amikor egy kifizetési dátum ünnepnapra esik.</span><span class="sxs-lookup"><span data-stu-id="dbf88-249">However, you can modify the default payment date in a pay period to allow for exceptions, such as when the payment date falls on a holiday.</span></span>

<span data-ttu-id="dbf88-250">A következő adatokat használja a Dayforce:</span><span class="sxs-lookup"><span data-stu-id="dbf88-250">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="dbf88-251">Fizetési ciklus (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-251">Pay cycle (required)</span></span>
- <span data-ttu-id="dbf88-252">Fizetési ciklus gyakorisága (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-252">Pay cycle frequency (required)</span></span>
- <span data-ttu-id="dbf88-253">Az időszak kezdő dátuma (az első fizetési időszak szükséges)</span><span class="sxs-lookup"><span data-stu-id="dbf88-253">Period start date (first pay period required)</span></span>
- <span data-ttu-id="dbf88-254">Alapértelmezett fizetési dátum (az első fizetési időszak szükséges)</span><span class="sxs-lookup"><span data-stu-id="dbf88-254">Default payment date (first pay period required)</span></span>

<span data-ttu-id="dbf88-255">Ez az információ Dayforceba fizetési csoportokként van integrálva országonként vagy régiónként le van választva egyes kifizetési ciklusokhoz.</span><span class="sxs-lookup"><span data-stu-id="dbf88-255">This information is integrated with Dayforce as pay groups, and is separated by country or region for each pay cycle.</span></span> <span data-ttu-id="dbf88-256">Legalább egy fizetési időszakot kell létrehozni az integráció előtt.</span><span class="sxs-lookup"><span data-stu-id="dbf88-256">At least one pay period must be generated before integration.</span></span> <span data-ttu-id="dbf88-257">A Dayforce fizetési csoportnaptárakat és kifizetési dátumokat hoz létre az első fizetési időszak kezdő dátuma és az alapértelmezett fizetési dátum alapján, amelyek a Human Resources alkalmazásban vannak beállítva.</span><span class="sxs-lookup"><span data-stu-id="dbf88-257">Dayforce generates pay group calendars and payment dates, based on the start date of the first pay period and the default payment date that is set up in Human Resources.</span></span>

#### <a name="earning-codes"></a><span data-ttu-id="dbf88-258">Bevételkódok</span><span class="sxs-lookup"><span data-stu-id="dbf88-258">Earning codes</span></span>

<span data-ttu-id="dbf88-259">A bevételkódok egyedi módon azonosítják a dolgozók által kapott fizetéstípusokat.</span><span class="sxs-lookup"><span data-stu-id="dbf88-259">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="dbf88-260">A kódoknak különböző paraméterei vannak, amelyek a bevételekhez kapcsolódnak, például könyvelési szabályok, jelentési követelmények és bruttósítási lehetőségek.</span><span class="sxs-lookup"><span data-stu-id="dbf88-260">The codes have various parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span>

<span data-ttu-id="dbf88-261">A következő adatokat használja a Dayforce:</span><span class="sxs-lookup"><span data-stu-id="dbf88-261">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="dbf88-262">Bevételkód (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-262">Earning Code (required)</span></span>
- <span data-ttu-id="dbf88-263">Leírás</span><span class="sxs-lookup"><span data-stu-id="dbf88-263">Description</span></span>
- <span data-ttu-id="dbf88-264">Mértékegység</span><span class="sxs-lookup"><span data-stu-id="dbf88-264">Unit of measure</span></span>
- <span data-ttu-id="dbf88-265">Produktív</span><span class="sxs-lookup"><span data-stu-id="dbf88-265">Productive</span></span>

### <a name="worker-data"></a><span data-ttu-id="dbf88-266">Dolgozóadatok</span><span class="sxs-lookup"><span data-stu-id="dbf88-266">Worker data</span></span>

<span data-ttu-id="dbf88-267">A dolgozók különböző típusaihoz tartozó rekordok, melyek fontosak az emberi erőforrásoknak és a bérlistarendszerekhez.</span><span class="sxs-lookup"><span data-stu-id="dbf88-267">Records for the various types of workers that you have are important to your human resources and payroll systems.</span></span> <span data-ttu-id="dbf88-268">A bevitt információk felhasználhatók az dolgozói és személyes adatok nyilvántartására.</span><span class="sxs-lookup"><span data-stu-id="dbf88-268">The information that you enter can be used to track workers and personal information.</span></span>

<span data-ttu-id="dbf88-269">A dolgozók következő adatait tarthatja karban:</span><span class="sxs-lookup"><span data-stu-id="dbf88-269">You can maintain the following information for workers:</span></span>

- <span data-ttu-id="dbf88-270">**Alapvető** – A dolgozók alapvető információi, például a kapcsolattartási adatok, demográfiai adatok azonosító adatok, családi adatok, a katonai szolgálat állapota, kiküldetésekre vonatkozó adatok, illetve személyes és rendkívüli kapcsolattartók.</span><span class="sxs-lookup"><span data-stu-id="dbf88-270">**Basic** – Maintain basic information about a worker, such as contact information, demographic information, identification information, family information, military service status, expatriate information, and personal and emergency contacts.</span></span>
- <span data-ttu-id="dbf88-271">**Foglalkoztatás** – Információk a dolgozó munkaviszonyáról, például a vállalati vagy szervezeti kapcsolat, hozzárendelt pozíció, kezdő és záró dátumok, munkajogosultság, foglalkoztatás feltételei, nyugdíj, szabadság és áthelyezéssel kapcsolatos információk.</span><span class="sxs-lookup"><span data-stu-id="dbf88-271">**Employment** – Maintain information about a worker's employment, such as company or organization affiliation, position assignment, start and end dates, work eligibility, terms of employment, pension, vacation, and relocation information.</span></span>
- <span data-ttu-id="dbf88-272">**Szabadság és a távollét** – A dolgozó távolléteinek kezelése, például a munkaidő-naptárak, a távolléti tranzakciók és távollét beállítása.</span><span class="sxs-lookup"><span data-stu-id="dbf88-272">**Leave and absence** – Maintain information about a worker's absences, such as working calendars, absence transactions, and absence setup.</span></span>
- <span data-ttu-id="dbf88-273">**Kompenzáció és bérlista** – dolgozói kompenzációs tervek és bérlistainformációk kezelése, például felvétel konstrukciója, jutalmak, teljesítmény, jutalék, adózási információk, nyugdíj és fizetéslevonások.</span><span class="sxs-lookup"><span data-stu-id="dbf88-273">**Compensation and payroll** – Maintain information about a worker's compensation plans and payroll information, such as plan enrollment, awards, performance, commission, tax information, retirement, and salary deductions.</span></span>

<span data-ttu-id="dbf88-274">A dolgozóinformációk létrehozása esetén ne felejtse el a következő adatokat és beállításokat, amelyeket a Dayforce használ.</span><span class="sxs-lookup"><span data-stu-id="dbf88-274">When you enter worker information, keep in mind the following data and configurations that are used in Dayforce.</span></span>

#### <a name="general-information"></a><span data-ttu-id="dbf88-275">Általános információk</span><span class="sxs-lookup"><span data-stu-id="dbf88-275">General information</span></span>

- <span data-ttu-id="dbf88-276">Személyzeti szám (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-276">Personnel number (required)</span></span>
- <span data-ttu-id="dbf88-277">Utónév (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-277">First name (required)</span></span>
- <span data-ttu-id="dbf88-278">Vezetéknév (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-278">Last name (required)</span></span>
- <span data-ttu-id="dbf88-279">Második keresztnév</span><span class="sxs-lookup"><span data-stu-id="dbf88-279">Middle name</span></span>
- <span data-ttu-id="dbf88-280">Szolgálati idő dátuma</span><span class="sxs-lookup"><span data-stu-id="dbf88-280">Seniority date</span></span>
- <span data-ttu-id="dbf88-281">Más néven</span><span class="sxs-lookup"><span data-stu-id="dbf88-281">Known as</span></span>

#### <a name="personal-information"></a><span data-ttu-id="dbf88-282">Személyes információ</span><span class="sxs-lookup"><span data-stu-id="dbf88-282">Personal information</span></span>

- <span data-ttu-id="dbf88-283">Családi állapot (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-283">Marital status (required)</span></span>
- <span data-ttu-id="dbf88-284">Születési dátum (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-284">Birth date (required)</span></span>
- <span data-ttu-id="dbf88-285">Nem (szükséges)</span><span class="sxs-lookup"><span data-stu-id="dbf88-285">Gender (required)</span></span>
- <span data-ttu-id="dbf88-286">Fogyatékkal élő személy</span><span class="sxs-lookup"><span data-stu-id="dbf88-286">Person with disabilities</span></span>
- <span data-ttu-id="dbf88-287">Állampolgárság ország régió (csak a Mexikó)</span><span class="sxs-lookup"><span data-stu-id="dbf88-287">Nationality country region (only for Mexico)</span></span>

#### <a name="address-information"></a><span data-ttu-id="dbf88-288">Címadatok</span><span class="sxs-lookup"><span data-stu-id="dbf88-288">Address information</span></span>

- <span data-ttu-id="dbf88-289">Elsődleges (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-289">Primary (required)</span></span>
- <span data-ttu-id="dbf88-290">Ország/régiót (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-290">Country/region (required)</span></span>
- <span data-ttu-id="dbf88-291">Irányítószámot (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-291">Postal code (required)</span></span>
- <span data-ttu-id="dbf88-292">Utca, házszám (kötelező) (csak Mexikó esetén)</span><span class="sxs-lookup"><span data-stu-id="dbf88-292">Street Number (required) (Only for Mexico)</span></span>
- <span data-ttu-id="dbf88-293">Épületblokk (csak a Mexikó)</span><span class="sxs-lookup"><span data-stu-id="dbf88-293">Building Complement (Only for Mexico)</span></span>
- <span data-ttu-id="dbf88-294">Város (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-294">City (required)</span></span>
- <span data-ttu-id="dbf88-295">Állam (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-295">State (required)</span></span>
- <span data-ttu-id="dbf88-296">Megye (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-296">County (required)</span></span>

#### <a name="contact-information"></a><span data-ttu-id="dbf88-297">Névjegy adatai</span><span class="sxs-lookup"><span data-stu-id="dbf88-297">Contact information</span></span> 

- <span data-ttu-id="dbf88-298">Elsődleges (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-298">Primary (required)</span></span>
- <span data-ttu-id="dbf88-299">Kapcsolattartó száma (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-299">Contact number (required)</span></span>
- <span data-ttu-id="dbf88-300">Mellék</span><span class="sxs-lookup"><span data-stu-id="dbf88-300">Extension</span></span>

#### <a name="payroll-information-and-earning-codes"></a><span data-ttu-id="dbf88-301">Bérlistaadatok és bevételkódok</span><span class="sxs-lookup"><span data-stu-id="dbf88-301">Payroll information and earning codes</span></span>

<span data-ttu-id="dbf88-302">Alkalmazottak hozzárendelhetők meghatározott bevételekhez adott fizetési gyakorisággal, és magadható elsődleges fizetési mód.</span><span class="sxs-lookup"><span data-stu-id="dbf88-302">Employees may be assigned specific earnings at a given frequency of payment and have a preferred payment method.</span></span> <span data-ttu-id="dbf88-303">A következő mezőket a Dayforce arra használja, hogy garantálja, hogy ezeket a preferenciákat és beállításokat használja.</span><span class="sxs-lookup"><span data-stu-id="dbf88-303">The following fields are used in Dayforce to help guarantee that those preferences and settings are used.</span></span>

##### <a name="earning-codes"></a><span data-ttu-id="dbf88-304">Bevételkódok</span><span class="sxs-lookup"><span data-stu-id="dbf88-304">Earning codes</span></span>

- <span data-ttu-id="dbf88-305">Beosztás (szükséges)</span><span class="sxs-lookup"><span data-stu-id="dbf88-305">Position (required)</span></span>
- <span data-ttu-id="dbf88-306">Bevételkód (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-306">Earning Code (required)</span></span>
- <span data-ttu-id="dbf88-307">Gyakoriság (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-307">Frequency (required)</span></span>
- <span data-ttu-id="dbf88-308">Összeg (szükséges)</span><span class="sxs-lookup"><span data-stu-id="dbf88-308">Amount (required)</span></span>

##### <a name="payroll-information"></a><span data-ttu-id="dbf88-309">Bérlistaadatok</span><span class="sxs-lookup"><span data-stu-id="dbf88-309">Payroll information</span></span>

- <span data-ttu-id="dbf88-310">Kifizetési mód</span><span class="sxs-lookup"><span data-stu-id="dbf88-310">Payment Method</span></span>
- <span data-ttu-id="dbf88-311">Gazdasági régió (szükséges)</span><span class="sxs-lookup"><span data-stu-id="dbf88-311">Economic Region (required)</span></span>
- <span data-ttu-id="dbf88-312">Alkalmazott juttatásainak azonosítója</span><span class="sxs-lookup"><span data-stu-id="dbf88-312">Employee Benefits ID</span></span>
- <span data-ttu-id="dbf88-313">Nemzeti azonosító (szükséges)</span><span class="sxs-lookup"><span data-stu-id="dbf88-313">National ID Number (required)</span></span>
- <span data-ttu-id="dbf88-314">Katonai szolgálat száma</span><span class="sxs-lookup"><span data-stu-id="dbf88-314">Military Service Number</span></span>
- <span data-ttu-id="dbf88-315">Műszakazonosító (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-315">Shift ID (required)</span></span>
- <span data-ttu-id="dbf88-316">Adószám (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-316">Tax Number (required)</span></span>
- <span data-ttu-id="dbf88-317">Szakszervezeti azonosító (szükséges)</span><span class="sxs-lookup"><span data-stu-id="dbf88-317">Union ID (required)</span></span>
- <span data-ttu-id="dbf88-318">Munkanap azonosítója (szükséges)</span><span class="sxs-lookup"><span data-stu-id="dbf88-318">Work Day ID (required)</span></span>
- <span data-ttu-id="dbf88-319">Munkavállalási engedély száma</span><span class="sxs-lookup"><span data-stu-id="dbf88-319">Work Permit Number</span></span>

> [!NOTE]
> <span data-ttu-id="dbf88-320">A fizetési módhoz Mexikó támogatja a **Készpénzt**, **Csekket** (a vállalat fizikai csekkjét) és az **Elektronikus fizetést**.</span><span class="sxs-lookup"><span data-stu-id="dbf88-320">For the payment method, Mexico supports **Cash**, **Check** (the company's physical check), and **Electronic Payment**.</span></span> <span data-ttu-id="dbf88-321">Ha nincs fizetési mód van megadva, alapértelmezés szerint a **Csekk** használt.</span><span class="sxs-lookup"><span data-stu-id="dbf88-321">If np payment method is specified, **Check** is used by default.</span></span>

#### <a name="employment-details"></a><span data-ttu-id="dbf88-322">Foglalkoztatás részletei</span><span class="sxs-lookup"><span data-stu-id="dbf88-322">Employment details</span></span>

<span data-ttu-id="dbf88-323">Foglalkoztatási előzményei kulcsfontosságú információkat tartalmaznak a munkavállaók felvételi, elbocsátási, és újbóli felvétele állapotával kapcsolatosan a Dayforce-ban.</span><span class="sxs-lookup"><span data-stu-id="dbf88-323">Employment detail history is used as key information to derive an employee's hire, termination, and rehire statuses in Dayforce.</span></span> <span data-ttu-id="dbf88-324">Dayforce egyszerre csak egy aktív foglalkoztatásrekordot tesz lehetővé.</span><span class="sxs-lookup"><span data-stu-id="dbf88-324">Dayforce supports only one active employment record at a time.</span></span>

- <span data-ttu-id="dbf88-325">Foglalkoztatás kezdődátuma (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-325">Employment start date (required)</span></span>
- <span data-ttu-id="dbf88-326">Munkaviszony záró dátuma</span><span class="sxs-lookup"><span data-stu-id="dbf88-326">Employment end date</span></span>
- <span data-ttu-id="dbf88-327">Kezdő dátum</span><span class="sxs-lookup"><span data-stu-id="dbf88-327">Start date</span></span>
- <span data-ttu-id="dbf88-328">Módosított kezdési időpont</span><span class="sxs-lookup"><span data-stu-id="dbf88-328">Adjusted start date</span></span>
- <span data-ttu-id="dbf88-329">Munkaviszony megszűnésének dátuma (megszűntetéskor kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-329">Termination date (required upon termination)</span></span>
- <span data-ttu-id="dbf88-330">Felmondás oka (megszűntetéskor kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-330">Termination reason (required upon termination)</span></span>

<span data-ttu-id="dbf88-331">Az alkalmazott legfontosabb dátumai a következő adatokból vannak származtatva.</span><span class="sxs-lookup"><span data-stu-id="dbf88-331">An employee's key dates are derived by using the following information.</span></span>

| <span data-ttu-id="dbf88-332">Emberi erőforrások</span><span class="sxs-lookup"><span data-stu-id="dbf88-332">Human Resources</span></span>                | <span data-ttu-id="dbf88-333">Dayforce</span><span class="sxs-lookup"><span data-stu-id="dbf88-333">Dayforce</span></span>                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="dbf88-334">Legutóbbi felvételi dátum</span><span class="sxs-lookup"><span data-stu-id="dbf88-334">Most recent hire date</span></span> | <span data-ttu-id="dbf88-335">Foglalkoztatás kezdete az aktuális nem megszűntetett előzményrekordra</span><span class="sxs-lookup"><span data-stu-id="dbf88-335">Employment start of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="dbf88-336">Munkaviszony megszűnésének dátuma</span><span class="sxs-lookup"><span data-stu-id="dbf88-336">Termination date</span></span>      | <span data-ttu-id="dbf88-337">Foglalkoztatás befejezése az aktuális nem megszűntetett előzményrekordra</span><span class="sxs-lookup"><span data-stu-id="dbf88-337">Termination date of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="dbf88-338">Kezdő dátum</span><span class="sxs-lookup"><span data-stu-id="dbf88-338">Start date</span></span>            | <span data-ttu-id="dbf88-339">Módosított kezdési időpont, kezdődátum vagy foglalkoztatás kezdete az aktuális nem aktív előzményrekordra</span><span class="sxs-lookup"><span data-stu-id="dbf88-339">Adjusted start date, start date, or employment start of current non-active employment history record</span></span> |
| <span data-ttu-id="dbf88-340">Eredeti felvételi dátum</span><span class="sxs-lookup"><span data-stu-id="dbf88-340">Original hire date</span></span>    | <span data-ttu-id="dbf88-341">Foglalkoztatás kezdete legkorábbi foglalkoztatási előzményrekordra</span><span class="sxs-lookup"><span data-stu-id="dbf88-341">Employment start of earliest employment history record</span></span>                                               |

#### <a name="compensation"></a><span data-ttu-id="dbf88-342">Kompenzáció</span><span class="sxs-lookup"><span data-stu-id="dbf88-342">Compensation</span></span>

<span data-ttu-id="dbf88-343">Egy fix kompenzációs tervet kell társítani minden alkalmazott elsődleges pozíciójához az alkalmazási időszak alatt.</span><span class="sxs-lookup"><span data-stu-id="dbf88-343">A fixed compensation plan must be associated with every employee's primary position throughout an employment period.</span></span> <span data-ttu-id="dbf88-344">Az időszak a belépés dátumával (vagy a foglalkoztatás kezdő dátumával) kezdődik, és a munkaviszony megszűnéséig tart .</span><span class="sxs-lookup"><span data-stu-id="dbf88-344">This period starts on the date that the employee was hired (or the employment start date) and continues until termination.</span></span>

- <span data-ttu-id="dbf88-345">Érvényesség dátuma (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-345">Effective Date (required)</span></span>
- <span data-ttu-id="dbf88-346">Lejárati dátum</span><span class="sxs-lookup"><span data-stu-id="dbf88-346">Expiration date</span></span>
- <span data-ttu-id="dbf88-347">Fizetési díjalap (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-347">Pay Rate (required)</span></span>
- <span data-ttu-id="dbf88-348">Fizetési díjalapok átalakításai (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-348">Pay Rate Conversions (required)</span></span>
- <span data-ttu-id="dbf88-349">Évi egyenérték (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-349">Annual equivalent (required)</span></span>
- <span data-ttu-id="dbf88-350">Óránkénti egyenérték (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-350">Hourly equivalent (required)</span></span>

<span data-ttu-id="dbf88-351">Ha az óránkénti alkalmazottnak több beosztása van, az elsődleges beosztásához tartozó fix kompenzációja importálva lesz a Dayforce-ba, alkalmazott szintű alapdíj/-fizetés.</span><span class="sxs-lookup"><span data-stu-id="dbf88-351">If an hourly employee has multiple positions, the fixed compensation of the primary position is imported into Dayforce as the employee-level base rate/salary.</span></span> <span data-ttu-id="dbf88-352">A nem elsődleges beosztások esetén, az óránkénti díj a megfelelő pozícióba lesz mentve Dayforce-ban.</span><span class="sxs-lookup"><span data-stu-id="dbf88-352">For non-primary positions, the hourly rate is saved to the corresponding position in Dayforce.</span></span>

<span data-ttu-id="dbf88-353">Ha a fizetett alkalmazott több beosztással rendelkezik, a összesített óradíj és éves fizetés származtatva lesz az összes aktív beosztásból mint az alkalmazotti szintű alapdíj/-fizetés.</span><span class="sxs-lookup"><span data-stu-id="dbf88-353">If a salaried employee has multiple positions, the cumulative hour rate and annual salary across all active positions are derived and used as the employee-level base rate/salary.</span></span>

#### <a name="identification-numbers"></a><span data-ttu-id="dbf88-354">Azonosítószámok</span><span class="sxs-lookup"><span data-stu-id="dbf88-354">Identification numbers</span></span>

##### <a name="social-security-identifier"></a><span data-ttu-id="dbf88-355">Társadalombiztosítási azonosító</span><span class="sxs-lookup"><span data-stu-id="dbf88-355">Social Security identifier</span></span> 

<span data-ttu-id="dbf88-356">Minden alkalmazottnak kell egy elsődleges azonosítóval rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="dbf88-356">Every employee must have one primary identifier.</span></span> <span data-ttu-id="dbf88-357">Ez az azonosító legyen **TAJ-szám** azonosítótípus kell legyen.</span><span class="sxs-lookup"><span data-stu-id="dbf88-357">This identifier must be of **SSN** identification type.</span></span> <span data-ttu-id="dbf88-358">A Dayforce-ban automatikusan van származtatva az alkalmazott társadalombiztosítási azonosítójából, mely a felvételhez szükséges.</span><span class="sxs-lookup"><span data-stu-id="dbf88-358">In Dayforce, it's automatically derived as the employee's Social Security identifier that is required for hire.</span></span>

- <span data-ttu-id="dbf88-359">Elsődleges (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-359">Primary (required)</span></span>
- <span data-ttu-id="dbf88-360">Azonosító típusa = „TAJ-szám”</span><span class="sxs-lookup"><span data-stu-id="dbf88-360">Identification Type = "SSN"</span></span>
- <span data-ttu-id="dbf88-361">Kibocsátás dátuma</span><span class="sxs-lookup"><span data-stu-id="dbf88-361">Issued Date</span></span>
- <span data-ttu-id="dbf88-362">Lejárat dátuma</span><span class="sxs-lookup"><span data-stu-id="dbf88-362">Expiration Date</span></span>

<span data-ttu-id="dbf88-363">Az alkalmazottak több azonosítószámot is megadhatnak **TAJ-szám** azonosítótípushoz.</span><span class="sxs-lookup"><span data-stu-id="dbf88-363">Employees can declare multiple identification numbers of the **SSN** identification type.</span></span> <span data-ttu-id="dbf88-364">Azonban csak az **Elsődlegesként** megjelölt rekord van integrálva Dayforce-ba, függetlenül attól, hogy a szám aktív vagy lejárt.</span><span class="sxs-lookup"><span data-stu-id="dbf88-364">However, only the record that is marked as **Primary** is integrated into Dayforce, regardless of whether the number is active or expired.</span></span>

#### <a name="bank-accounts-and-disbursements"></a><span data-ttu-id="dbf88-365">Bankszámlák és kifizetések</span><span class="sxs-lookup"><span data-stu-id="dbf88-365">Bank accounts and disbursements</span></span>

<span data-ttu-id="dbf88-366">Érvényes bankszámlaadatokat meg kell adni minden olyan alkalmazotthoz, aki úgy dönt, hogy a banki átutalással kéri fizetését.</span><span class="sxs-lookup"><span data-stu-id="dbf88-366">Valid bank account information must be entered for any employee who chooses to be paid via bank account transfers.</span></span>

| <span data-ttu-id="dbf88-367">Emberi erőforrások</span><span class="sxs-lookup"><span data-stu-id="dbf88-367">Human Resources</span></span>                         | <span data-ttu-id="dbf88-368">Dayforce</span><span class="sxs-lookup"><span data-stu-id="dbf88-368">Dayforce</span></span>                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="dbf88-369">Bankszámlaszám (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-369">Bank account number (required)</span></span> |                                                                                                             |
| <span data-ttu-id="dbf88-370">SWIFT-kód (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-370">SWIFT code (required)</span></span>          | <span data-ttu-id="dbf88-371">**Bankazonosító** ez a mező Mexikóban történő bérlistafeldolgozáskor használatos.</span><span class="sxs-lookup"><span data-stu-id="dbf88-371">**Bank ID** field used when processing payroll in Mexico.</span></span>                                                             |
| <span data-ttu-id="dbf88-372">Ágazati szám (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-372">Branch number (required)</span></span>       |                                                                                                             |
| <span data-ttu-id="dbf88-373">Bankszámla típusa (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-373">Bank account type (required)</span></span>   | <span data-ttu-id="dbf88-374">**Számlatípus** ez a mező Mexikóban történő bérlistafeldolgozáskor használatos.</span><span class="sxs-lookup"><span data-stu-id="dbf88-374">**Account type** field used when processing payroll in Mexico.</span></span> <span data-ttu-id="dbf88-375">Támogatott értékek: **Folyószámla** és **Bérlista**</span><span class="sxs-lookup"><span data-stu-id="dbf88-375">Supported values include **Checking** and **Payroll**.</span></span> |

> [!NOTE]
> <span data-ttu-id="dbf88-376">Alkalmazottak, akik úgy döntenek, hogy a banki átutaláson keresztülkérik fizetésük, meg kell adniuk egy hivatkozást egy jogi személyhez tartozó egyenlegszámlához, melynek elsődleges címének Mexikóban kell lennie és egy Mexikói bank érvényes bankszámlájához van társítva.</span><span class="sxs-lookup"><span data-stu-id="dbf88-376">Employees who choose to be paid via bank account transfers must provide a link to a remainder account that is under a legal entity that has its primary address in Mexico and associated with a valid bank account from a Mexican bank.</span></span> <span data-ttu-id="dbf88-377">Minden egyéb nem egyenlegszámla figyelmen kívül lesz hagyva.</span><span class="sxs-lookup"><span data-stu-id="dbf88-377">All other non-remainder accounts are ignored.</span></span>

#### <a name="address-information"></a><span data-ttu-id="dbf88-378">Címadatok</span><span class="sxs-lookup"><span data-stu-id="dbf88-378">Address information</span></span>

<span data-ttu-id="dbf88-379">Minden alkalmazottnak kell egy elsődleges hellyel rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="dbf88-379">Every employee must have one primary location.</span></span> <span data-ttu-id="dbf88-380">A Dayforce-ban ezen hely alapján van meghatározva az alkalmazott elsődleges tartózkodási helye adózási célokból.</span><span class="sxs-lookup"><span data-stu-id="dbf88-380">In Dayforce, this location is used to determine the employee's primary residence for tax purposes.</span></span>

- <span data-ttu-id="dbf88-381">Elsődleges (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-381">Primary (required)</span></span>
- <span data-ttu-id="dbf88-382">Ország/régiót (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-382">Country/region (required)</span></span>
- <span data-ttu-id="dbf88-383">Irányítószám/postai kód (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-383">Zip/postal code (required)</span></span>
- <span data-ttu-id="dbf88-384">Utca (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-384">Street (required)</span></span>
- <span data-ttu-id="dbf88-385">Házszám (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-385">Street Number (required)</span></span>
- <span data-ttu-id="dbf88-386">Épületblokk</span><span class="sxs-lookup"><span data-stu-id="dbf88-386">Building Complement</span></span>
- <span data-ttu-id="dbf88-387">Város (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-387">City (required)</span></span>
- <span data-ttu-id="dbf88-388">Állam (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-388">State (required)</span></span>
- <span data-ttu-id="dbf88-389">Megye (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-389">County (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a><span data-ttu-id="dbf88-390">Az adatok konfigurálása bérlista létrehozásához az Egyesült Államokban és Kanadában</span><span class="sxs-lookup"><span data-stu-id="dbf88-390">Configure your data to generate payroll in United States and Canada</span></span>

<span data-ttu-id="dbf88-391">Ha a fizetést generálása alkalmazottaknak az Egyesült Államokban és Kanadában, a következő elemeket kell beállítani:</span><span class="sxs-lookup"><span data-stu-id="dbf88-391">If you're generating pay for employees in the United States and Canada, the following elements must be configured:</span></span>

- <span data-ttu-id="dbf88-392">Részlegek szükségesek beosztásokhoz.</span><span class="sxs-lookup"><span data-stu-id="dbf88-392">Departments are required on positions.</span></span>
- <span data-ttu-id="dbf88-393">Költséghelyek pénzügyi dimenziókként kell beállítani, és az alapértelmezett pénzügyi dimenzió karakterlánc első elemének kell lennie.</span><span class="sxs-lookup"><span data-stu-id="dbf88-393">Cost centers must be set as financial dimensions and must be the first element in the default financial dimension string.</span></span>

> [!NOTE] 
> <span data-ttu-id="dbf88-394">Konfigurálhatja a Human Resources alkalmazást úgy, hogy a beosztásokhoz kötelező legyen beállítani részleget.</span><span class="sxs-lookup"><span data-stu-id="dbf88-394">You can configure Human Resources to require that Positions specify a Department.</span></span> <span data-ttu-id="dbf88-395">Ehhez kattintson a **Emberi erőforrások megosztott beosztásai > Beosztások > Részlegek szükségesek beosztásokhoz.** elemre.</span><span class="sxs-lookup"><span data-stu-id="dbf88-395">To do this, go to **Human Resources Shared Positions > Positions > Require departments on positions**.</span></span> <span data-ttu-id="dbf88-396">Azt ajánljuk, hogy ezt a beállítást tartassa be az integráció során.</span><span class="sxs-lookup"><span data-stu-id="dbf88-396">We recommend that this setting be enforced for the integration.</span></span>

### <a name="job-types"></a><span data-ttu-id="dbf88-397">Feladattípusok</span><span class="sxs-lookup"><span data-stu-id="dbf88-397">Job types</span></span>

<span data-ttu-id="dbf88-398">Beosztástípusok használatával a hasonló feladatok kategóriákba sorolhatók.</span><span class="sxs-lookup"><span data-stu-id="dbf88-398">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="dbf88-399">A beosztástípusok szükségesek az Egyesült Államokban és Kanadában a bérlisták feldolgozásához.</span><span class="sxs-lookup"><span data-stu-id="dbf88-399">Job types are required in order to process payroll in the United States and Canada.</span></span> <span data-ttu-id="dbf88-400">Beosztástípusok többek között a teljes és részmunkaidős, illetve a munkabéres és az órabéres.</span><span class="sxs-lookup"><span data-stu-id="dbf88-400">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="dbf88-401">A beosztástípusok a fizetéstípusokként vannak hozzárendelve a Dayforce-hoz, melyek jelzik, hogy a munkavállaló órás vagy bérezéses.</span><span class="sxs-lookup"><span data-stu-id="dbf88-401">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="dbf88-402">A következő feladattípusok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="dbf88-402">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="dbf88-403">Feladattípus</span><span class="sxs-lookup"><span data-stu-id="dbf88-403">Job type</span></span>   | <span data-ttu-id="dbf88-404">Leírás</span><span class="sxs-lookup"><span data-stu-id="dbf88-404">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="dbf88-405">Óránként</span><span class="sxs-lookup"><span data-stu-id="dbf88-405">Hourly</span></span>     | <span data-ttu-id="dbf88-406">Óránként</span><span class="sxs-lookup"><span data-stu-id="dbf88-406">Hourly</span></span>      |
| <span data-ttu-id="dbf88-407">Bérezéses</span><span class="sxs-lookup"><span data-stu-id="dbf88-407">Salaried</span></span>   | <span data-ttu-id="dbf88-408">Bérezéses</span><span class="sxs-lookup"><span data-stu-id="dbf88-408">Salaried</span></span>    |

### <a name="position-types"></a><span data-ttu-id="dbf88-409">Beosztási típusok</span><span class="sxs-lookup"><span data-stu-id="dbf88-409">Position types</span></span> 

<span data-ttu-id="dbf88-410">Ne használjon beosztástípusokat annak leírására, hogy a beosztás teljes munkaidős, részmunkaidős vagy más.</span><span class="sxs-lookup"><span data-stu-id="dbf88-410">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="dbf88-411">A feladattípusok a fizetésosztályokként vannak hozzárendelve a Dayforce-hoz, melyek jelzik, hogy a munkavállaló teljes- vagy részmunkaidős.</span><span class="sxs-lookup"><span data-stu-id="dbf88-411">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="dbf88-412">A következő beosztástípusok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="dbf88-412">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="dbf88-413">Beosztás típusa</span><span class="sxs-lookup"><span data-stu-id="dbf88-413">Position type</span></span>   | <span data-ttu-id="dbf88-414">Leírás</span><span class="sxs-lookup"><span data-stu-id="dbf88-414">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="dbf88-415">Teljes munkaidős</span><span class="sxs-lookup"><span data-stu-id="dbf88-415">Full-time</span></span>       | <span data-ttu-id="dbf88-416">Teljes munkaidős alkalmazott</span><span class="sxs-lookup"><span data-stu-id="dbf88-416">Full time employee</span></span> |
| <span data-ttu-id="dbf88-417">Részmunkaidős</span><span class="sxs-lookup"><span data-stu-id="dbf88-417">Part-time</span></span>       | <span data-ttu-id="dbf88-418">Részmunkaidős alkalmazott</span><span class="sxs-lookup"><span data-stu-id="dbf88-418">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="dbf88-419">Okkódok</span><span class="sxs-lookup"><span data-stu-id="dbf88-419">Reason codes</span></span>

<span data-ttu-id="dbf88-420">Az alkalmazottak állapotával kapcsolatos okkódok tájékoztatnak.</span><span class="sxs-lookup"><span data-stu-id="dbf88-420">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="dbf88-421">Okkódok a Dayforce-hoz állapot okaként vannak hozzárendelve, melyek jelzik egy alkalmazott beosztásában vagy alkalmazotti státuszában bekövetkezett változások okát.</span><span class="sxs-lookup"><span data-stu-id="dbf88-421">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="dbf88-422">A következő okkódok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="dbf88-422">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="dbf88-423">Okkód</span><span class="sxs-lookup"><span data-stu-id="dbf88-423">Reason code</span></span>    | <span data-ttu-id="dbf88-424">Leírás</span><span class="sxs-lookup"><span data-stu-id="dbf88-424">Description</span></span>      | <span data-ttu-id="dbf88-425">Alkalmazandó forgatókönyvek</span><span class="sxs-lookup"><span data-stu-id="dbf88-425">Applicable scenarios</span></span> |
|----------------|------------------|----------------------|
| <span data-ttu-id="dbf88-426">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="dbf88-426">RESIGNATION</span></span>    | <span data-ttu-id="dbf88-427">Felmondás</span><span class="sxs-lookup"><span data-stu-id="dbf88-427">Resignation</span></span>      | <span data-ttu-id="dbf88-428">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="dbf88-428">Terminate worker</span></span>     |
| <span data-ttu-id="dbf88-429">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="dbf88-429">TERMINATION</span></span>    | <span data-ttu-id="dbf88-430">Befejezés</span><span class="sxs-lookup"><span data-stu-id="dbf88-430">Termination</span></span>      | <span data-ttu-id="dbf88-431">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="dbf88-431">Terminate worker</span></span>     |
| <span data-ttu-id="dbf88-432">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="dbf88-432">RETIREMENT</span></span>     | <span data-ttu-id="dbf88-433">Megszüntetés</span><span class="sxs-lookup"><span data-stu-id="dbf88-433">Retirement</span></span>       | <span data-ttu-id="dbf88-434">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="dbf88-434">Terminate worker</span></span>     |
| <span data-ttu-id="dbf88-435">EGYÉB</span><span class="sxs-lookup"><span data-stu-id="dbf88-435">OTHER</span></span>          | <span data-ttu-id="dbf88-436">Egyéb okok</span><span class="sxs-lookup"><span data-stu-id="dbf88-436">Other Reasons</span></span>    | <span data-ttu-id="dbf88-437">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="dbf88-437">Terminate worker</span></span>     |
| <span data-ttu-id="dbf88-438">DEATH</span><span class="sxs-lookup"><span data-stu-id="dbf88-438">DEATH</span></span>          | <span data-ttu-id="dbf88-439">Elhalálozás</span><span class="sxs-lookup"><span data-stu-id="dbf88-439">Death</span></span>            | <span data-ttu-id="dbf88-440">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="dbf88-440">Terminate worker</span></span>     |
| <span data-ttu-id="dbf88-441">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="dbf88-441">LEAVEOFABSENCE</span></span> | <span data-ttu-id="dbf88-442">Szabadság</span><span class="sxs-lookup"><span data-stu-id="dbf88-442">Leave of Absence</span></span> | <span data-ttu-id="dbf88-443">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="dbf88-443">Terminate worker</span></span>     |
| <span data-ttu-id="dbf88-444">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="dbf88-444">CONTRACTEND</span></span>    | <span data-ttu-id="dbf88-445">Szerződés vége</span><span class="sxs-lookup"><span data-stu-id="dbf88-445">End of Contract</span></span>  | <span data-ttu-id="dbf88-446">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="dbf88-446">Terminate worker</span></span>     |
| <span data-ttu-id="dbf88-447">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="dbf88-447">SALARYCHANGE</span></span>   | <span data-ttu-id="dbf88-448">Munkabér módosítása</span><span class="sxs-lookup"><span data-stu-id="dbf88-448">Change of Salary</span></span> | <span data-ttu-id="dbf88-449">Kompenzáció</span><span class="sxs-lookup"><span data-stu-id="dbf88-449">Compensation</span></span>         |

### <a name="marital-status"></a><span data-ttu-id="dbf88-450">Családi állapot</span><span class="sxs-lookup"><span data-stu-id="dbf88-450">Marital status</span></span>

<span data-ttu-id="dbf88-451">Családi állapot értékei Dayforce-hoz vannak rendelve és konvertálva szükség esetén az elfogadható értékekre az integráció során.</span><span class="sxs-lookup"><span data-stu-id="dbf88-451">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="dbf88-452">Az alábbi táblázat bemutatja, hogy családi állapot értékek hogyan vannak leképezve a Dayforce -ban.</span><span class="sxs-lookup"><span data-stu-id="dbf88-452">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="dbf88-453">Emberi erőforrások</span><span class="sxs-lookup"><span data-stu-id="dbf88-453">Human Resources</span></span>                 | <span data-ttu-id="dbf88-454">Dayforce</span><span class="sxs-lookup"><span data-stu-id="dbf88-454">Dayforce</span></span>             |
|------------------------|----------------------|
| <span data-ttu-id="dbf88-455">Nős/férjezett</span><span class="sxs-lookup"><span data-stu-id="dbf88-455">Married</span></span>                | <span data-ttu-id="dbf88-456">Nős/férjezett</span><span class="sxs-lookup"><span data-stu-id="dbf88-456">Married</span></span>              |
| <span data-ttu-id="dbf88-457">Egy</span><span class="sxs-lookup"><span data-stu-id="dbf88-457">Single</span></span>                 | <span data-ttu-id="dbf88-458">Egy</span><span class="sxs-lookup"><span data-stu-id="dbf88-458">Single</span></span>               |
| <span data-ttu-id="dbf88-459">Özvegy</span><span class="sxs-lookup"><span data-stu-id="dbf88-459">Widowed</span></span>                | <span data-ttu-id="dbf88-460">Özvegy</span><span class="sxs-lookup"><span data-stu-id="dbf88-460">Widowed</span></span>              |
| <span data-ttu-id="dbf88-461">Elvált</span><span class="sxs-lookup"><span data-stu-id="dbf88-461">Divorced</span></span>               | <span data-ttu-id="dbf88-462">Elvált</span><span class="sxs-lookup"><span data-stu-id="dbf88-462">Divorced</span></span>             |
| <span data-ttu-id="dbf88-463">Bejegyzett élettársi kapcsolat</span><span class="sxs-lookup"><span data-stu-id="dbf88-463">Registered Partnership</span></span> | <span data-ttu-id="dbf88-464">Élettársi viszony</span><span class="sxs-lookup"><span data-stu-id="dbf88-464">Domestic Partnership</span></span> |
| <span data-ttu-id="dbf88-465">Nincs</span><span class="sxs-lookup"><span data-stu-id="dbf88-465">None</span></span>                   | <span data-ttu-id="dbf88-466">Nincs</span><span class="sxs-lookup"><span data-stu-id="dbf88-466">None</span></span>                 |
| <span data-ttu-id="dbf88-467">Együttélés</span><span class="sxs-lookup"><span data-stu-id="dbf88-467">Cohabiting</span></span>             | <span data-ttu-id="dbf88-468">Együttélés</span><span class="sxs-lookup"><span data-stu-id="dbf88-468">Cohabiting</span></span>           |

### <a name="gender"></a><span data-ttu-id="dbf88-469">Nem</span><span class="sxs-lookup"><span data-stu-id="dbf88-469">Gender</span></span>

<span data-ttu-id="dbf88-470">A nemek a Dayforce-hoz vannak rendelve és konvertálva szükség esetén az elfogadható értékekre az integráció során.</span><span class="sxs-lookup"><span data-stu-id="dbf88-470">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="dbf88-471">Az alábbi táblázat bemutatja, hogy a nemek hogyan vannak leképezve a Dayforce-ban.</span><span class="sxs-lookup"><span data-stu-id="dbf88-471">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="dbf88-472">Emberi erőforrások</span><span class="sxs-lookup"><span data-stu-id="dbf88-472">Human Resources</span></span>       | <span data-ttu-id="dbf88-473">Dayforce</span><span class="sxs-lookup"><span data-stu-id="dbf88-473">Dayforce</span></span>        |
|--------------|-----------------|
| <span data-ttu-id="dbf88-474">Férfi</span><span class="sxs-lookup"><span data-stu-id="dbf88-474">Male</span></span>         | <span data-ttu-id="dbf88-475">Férfi</span><span class="sxs-lookup"><span data-stu-id="dbf88-475">Male</span></span>            |
| <span data-ttu-id="dbf88-476">Nő</span><span class="sxs-lookup"><span data-stu-id="dbf88-476">Female</span></span>       | <span data-ttu-id="dbf88-477">Nő</span><span class="sxs-lookup"><span data-stu-id="dbf88-477">Female</span></span>          |
| <span data-ttu-id="dbf88-478">Nem meghatározott</span><span class="sxs-lookup"><span data-stu-id="dbf88-478">Non-specific</span></span> | <span data-ttu-id="dbf88-479">*Nem támogatott*</span><span class="sxs-lookup"><span data-stu-id="dbf88-479">*Not supported*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="dbf88-480">Bevételkódok</span><span class="sxs-lookup"><span data-stu-id="dbf88-480">Earning codes</span></span>

<span data-ttu-id="dbf88-481">A bevételkódok egyedi módon azonosítják a dolgozók által kapott fizetéstípusokat.</span><span class="sxs-lookup"><span data-stu-id="dbf88-481">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="dbf88-482">A kódoknak különböző paramétereket fednek le, amelyek a bevételekhez kapcsolódnak, például könyvelési szabályok, jelentési követelmények és bruttósítási lehetőségek.</span><span class="sxs-lookup"><span data-stu-id="dbf88-482">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="dbf88-483">Ha egy nem támogatott gyakoriság van használatban, a **Minden fizetés** gyakorisága van alapértelmezés szerint használva a kiszámításhoz.</span><span class="sxs-lookup"><span data-stu-id="dbf88-483">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="dbf88-484">Támogatott gyakoriságok</span><span class="sxs-lookup"><span data-stu-id="dbf88-484">Supported frequencies</span></span>

- <span data-ttu-id="dbf88-485">Összes</span><span class="sxs-lookup"><span data-stu-id="dbf88-485">All</span></span>
- <span data-ttu-id="dbf88-486">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="dbf88-486">EVERYPAY</span></span>
- <span data-ttu-id="dbf88-487">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="dbf88-487">EACHPAYPERIOD</span></span>
- <span data-ttu-id="dbf88-488">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="dbf88-488">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="dbf88-489">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="dbf88-489">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="dbf88-490">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbf88-490">1OFMTH</span></span>
- <span data-ttu-id="dbf88-491">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="dbf88-491">LASTOFMTH</span></span>
- <span data-ttu-id="dbf88-492">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbf88-492">2OFMTH</span></span>
- <span data-ttu-id="dbf88-493">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbf88-493">3OFMTH</span></span>
- <span data-ttu-id="dbf88-494">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbf88-494">4OFMTH</span></span>
- <span data-ttu-id="dbf88-495">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbf88-495">5OFMTH</span></span>
- <span data-ttu-id="dbf88-496">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbf88-496">1N2OFMTH</span></span>
- <span data-ttu-id="dbf88-497">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbf88-497">3N4OFMTH</span></span>
- <span data-ttu-id="dbf88-498">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbf88-498">1N3OFMTH</span></span>
- <span data-ttu-id="dbf88-499">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbf88-499">1N4OFMTH</span></span>
- <span data-ttu-id="dbf88-500">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbf88-500">2N3OFMTH</span></span>
- <span data-ttu-id="dbf88-501">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbf88-501">2N4OFMTH</span></span>
- <span data-ttu-id="dbf88-502">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbf88-502">1N2N3OFMTH</span></span>
- <span data-ttu-id="dbf88-503">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbf88-503">1N2N4OFMTH</span></span>
- <span data-ttu-id="dbf88-504">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbf88-504">1N3N4OFMTH</span></span>
- <span data-ttu-id="dbf88-505">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbf88-505">2N3N4OFMTH</span></span>
- <span data-ttu-id="dbf88-506">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbf88-506">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="dbf88-507">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="dbf88-507">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="dbf88-508">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="dbf88-508">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="dbf88-509">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="dbf88-509">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="dbf88-510">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="dbf88-510">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="dbf88-511">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="dbf88-511">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="dbf88-512">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="dbf88-512">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="dbf88-513">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="dbf88-513">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="dbf88-514">Címek</span><span class="sxs-lookup"><span data-stu-id="dbf88-514">Addresses</span></span>

<span data-ttu-id="dbf88-515">Az adott ország vagy régió, állam és megye (település) kódok specifikus formátumokat követelnek, hogy Dayforce és az országos és regionális szolgáltatók felismerjék azokat.</span><span class="sxs-lookup"><span data-stu-id="dbf88-515">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="dbf88-516">Annak ellenére, hogy a városok formátuma rugalmas, minden városnak társítva kell lennie egy államhoz.</span><span class="sxs-lookup"><span data-stu-id="dbf88-516">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="dbf88-517">Emberi erőforrások</span><span class="sxs-lookup"><span data-stu-id="dbf88-517">Human Resources</span></span>          | <span data-ttu-id="dbf88-518">Dayforce</span><span class="sxs-lookup"><span data-stu-id="dbf88-518">Dayforce</span></span>              |
|-----------------|-----------------------|
| <span data-ttu-id="dbf88-519">Ország/régió</span><span class="sxs-lookup"><span data-stu-id="dbf88-519">Country/Region</span></span>  | <span data-ttu-id="dbf88-520">Országkód</span><span class="sxs-lookup"><span data-stu-id="dbf88-520">Country Code</span></span>          |
| <span data-ttu-id="dbf88-521">Irányítószám / postai kód</span><span class="sxs-lookup"><span data-stu-id="dbf88-521">Zip/Postal Code</span></span> | <span data-ttu-id="dbf88-522">Irányítószám</span><span class="sxs-lookup"><span data-stu-id="dbf88-522">Postal Code</span></span>           |
| <span data-ttu-id="dbf88-523">Állami</span><span class="sxs-lookup"><span data-stu-id="dbf88-523">State</span></span>           | <span data-ttu-id="dbf88-524">Államkód</span><span class="sxs-lookup"><span data-stu-id="dbf88-524">State Code</span></span>            |
| <span data-ttu-id="dbf88-525">Város</span><span class="sxs-lookup"><span data-stu-id="dbf88-525">City</span></span>            | <span data-ttu-id="dbf88-526">Város</span><span class="sxs-lookup"><span data-stu-id="dbf88-526">City</span></span>                  |
| <span data-ttu-id="dbf88-527">Megye</span><span class="sxs-lookup"><span data-stu-id="dbf88-527">County</span></span>          | <span data-ttu-id="dbf88-528">Megye (Helyhatóság)</span><span class="sxs-lookup"><span data-stu-id="dbf88-528">County (Municipality)</span></span> |
| <span data-ttu-id="dbf88-529">Utca</span><span class="sxs-lookup"><span data-stu-id="dbf88-529">Street</span></span>          | <span data-ttu-id="dbf88-530">Cím 1. sora</span><span class="sxs-lookup"><span data-stu-id="dbf88-530">Address Line 1</span></span>        |

### <a name="tax-regions"></a><span data-ttu-id="dbf88-531">Adórégiók</span><span class="sxs-lookup"><span data-stu-id="dbf88-531">Tax regions</span></span>

<span data-ttu-id="dbf88-532">Az adórégiók a megfelelő adó megállapítására szolgálnak, amelyet a bérlista létrehozásakor kell alkalmazni.</span><span class="sxs-lookup"><span data-stu-id="dbf88-532">Tax regions are used to determine the appropriate tax that should be applied during payroll generation.</span></span> <span data-ttu-id="dbf88-533">Az adórégiók helycímként vannak a Dayforce-hoz rendelve.</span><span class="sxs-lookup"><span data-stu-id="dbf88-533">Tax regions are mapped to Dayforce as location addresses.</span></span> <span data-ttu-id="dbf88-534">Az alapértelmezett adórégiót a dolgozó aktív beosztásával kell társítani.</span><span class="sxs-lookup"><span data-stu-id="dbf88-534">The default tax region must be associated with the worker's active position.</span></span> 

- <span data-ttu-id="dbf88-535">Adórégió (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-535">Tax region (required)</span></span>
- <span data-ttu-id="dbf88-536">Ország/régió (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-536">Country/Region (required)</span></span>
- <span data-ttu-id="dbf88-537">Állam (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-537">State (required)</span></span>
- <span data-ttu-id="dbf88-538">Megye</span><span class="sxs-lookup"><span data-stu-id="dbf88-538">County</span></span> 
- <span data-ttu-id="dbf88-539">Város (kötelező)</span><span class="sxs-lookup"><span data-stu-id="dbf88-539">City (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a><span data-ttu-id="dbf88-540">Adatok konfigurálása bérlista létrehozásához Mexikóban</span><span class="sxs-lookup"><span data-stu-id="dbf88-540">Configure your data to generate payroll in Mexico</span></span>

<span data-ttu-id="dbf88-541">Ha a fizetést generál alkalmazottaknak Mexikóban, a következő elemeket kell beállítani:</span><span class="sxs-lookup"><span data-stu-id="dbf88-541">If you're generating pay for employees in Mexico, the following elements must be configured:</span></span>

- <span data-ttu-id="dbf88-542">Részlegek szükségesek beosztásokhoz.</span><span class="sxs-lookup"><span data-stu-id="dbf88-542">Departments are required on positions.</span></span>
- <span data-ttu-id="dbf88-543">Költséghelyek pénzügyi dimenziókként kell beállítani, és az Alapértelmezett pénzügyi dimenzió karakterlánc első elemének kell lennie.</span><span class="sxs-lookup"><span data-stu-id="dbf88-543">Cost centers must be set as financial dimensions and must be the first element in the Default Financial Dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="dbf88-544">Beosztástípusok</span><span class="sxs-lookup"><span data-stu-id="dbf88-544">Job types</span></span>

<span data-ttu-id="dbf88-545">Beosztástípusok használatával a hasonló feladatok kategóriákba sorolhatók.</span><span class="sxs-lookup"><span data-stu-id="dbf88-545">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="dbf88-546">Mexikóban a Bérlista feldolgozásához feladattípusok szükségesek.</span><span class="sxs-lookup"><span data-stu-id="dbf88-546">Job types are required in order to process payroll in Mexico.</span></span> <span data-ttu-id="dbf88-547">Beosztástípusok többek között a teljes és részmunkaidős, illetve a munkabéres és az órabéres.</span><span class="sxs-lookup"><span data-stu-id="dbf88-547">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="dbf88-548">A beosztástípusok a fizetéstípusokként vannak hozzárendelve a Dayforce-hoz, melyek jelzik, hogy a munkavállaló órás vagy bérezéses.</span><span class="sxs-lookup"><span data-stu-id="dbf88-548">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="dbf88-549">A következő feladattípusok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="dbf88-549">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="dbf88-550">Feladattípus</span><span class="sxs-lookup"><span data-stu-id="dbf88-550">Job type</span></span>   | <span data-ttu-id="dbf88-551">Leírás</span><span class="sxs-lookup"><span data-stu-id="dbf88-551">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="dbf88-552">Óránként</span><span class="sxs-lookup"><span data-stu-id="dbf88-552">Hourly</span></span>     | <span data-ttu-id="dbf88-553">MX Órabér</span><span class="sxs-lookup"><span data-stu-id="dbf88-553">MX Hourly</span></span>   |
| <span data-ttu-id="dbf88-554">Bérezéses</span><span class="sxs-lookup"><span data-stu-id="dbf88-554">Salaried</span></span>   | <span data-ttu-id="dbf88-555">MX Bérezéses</span><span class="sxs-lookup"><span data-stu-id="dbf88-555">MX Salaried</span></span> |

### <a name="position-types"></a><span data-ttu-id="dbf88-556">Beosztási típusok</span><span class="sxs-lookup"><span data-stu-id="dbf88-556">Position types</span></span> 

<span data-ttu-id="dbf88-557">Ne használjon beosztástípusokat annak leírására, hogy a beosztás teljes munkaidős, részmunkaidős vagy más.</span><span class="sxs-lookup"><span data-stu-id="dbf88-557">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="dbf88-558">A feladattípusok a fizetésosztályokként vannak hozzárendelve a Dayforce-hoz, melyek jelzik, hogy a munkavállaló teljes- vagy részmunkaidős.</span><span class="sxs-lookup"><span data-stu-id="dbf88-558">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="dbf88-559">A következő beosztástípusok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="dbf88-559">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="dbf88-560">Beosztás típusa</span><span class="sxs-lookup"><span data-stu-id="dbf88-560">Position type</span></span>   | <span data-ttu-id="dbf88-561">Leírás</span><span class="sxs-lookup"><span data-stu-id="dbf88-561">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="dbf88-562">Teljes munkaidős</span><span class="sxs-lookup"><span data-stu-id="dbf88-562">Full-time</span></span>       | <span data-ttu-id="dbf88-563">Teljes munkaidős alkalmazott</span><span class="sxs-lookup"><span data-stu-id="dbf88-563">Full time employee</span></span> |
| <span data-ttu-id="dbf88-564">Részmunkaidős</span><span class="sxs-lookup"><span data-stu-id="dbf88-564">Part-time</span></span>       | <span data-ttu-id="dbf88-565">Részmunkaidős alkalmazott</span><span class="sxs-lookup"><span data-stu-id="dbf88-565">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="dbf88-566">Okkódok</span><span class="sxs-lookup"><span data-stu-id="dbf88-566">Reason codes</span></span>

<span data-ttu-id="dbf88-567">Az alkalmazottak állapotával kapcsolatos okkódok tájékoztatnak.</span><span class="sxs-lookup"><span data-stu-id="dbf88-567">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="dbf88-568">Okkódok a Dayforce-hoz állapot okaként vannak hozzárendelve, melyek jelzik egy alkalmazott beosztásában vagy alkalmazotti státuszában bekövetkezett változások okát.</span><span class="sxs-lookup"><span data-stu-id="dbf88-568">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="dbf88-569">A következő okkódok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="dbf88-569">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="dbf88-570">Okkód</span><span class="sxs-lookup"><span data-stu-id="dbf88-570">Reason code</span></span>            | <span data-ttu-id="dbf88-571">Leírás</span><span class="sxs-lookup"><span data-stu-id="dbf88-571">Description</span></span>                    | <span data-ttu-id="dbf88-572">Alkalmazandó forgatókönyvek</span><span class="sxs-lookup"><span data-stu-id="dbf88-572">Applicable scenarios</span></span> |
|------------------------|--------------------------------|----------------------|
| <span data-ttu-id="dbf88-573">DEPARTUREBEFOREPAYMENT</span><span class="sxs-lookup"><span data-stu-id="dbf88-573">DEPARTUREBEFOREPAYMENT</span></span> | <span data-ttu-id="dbf88-574">Indulás első bérlista előtt</span><span class="sxs-lookup"><span data-stu-id="dbf88-574">Departure before first payroll</span></span> | <span data-ttu-id="dbf88-575">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="dbf88-575">Terminate worker</span></span>     |
| <span data-ttu-id="dbf88-576">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="dbf88-576">RESIGNATION</span></span>            | <span data-ttu-id="dbf88-577">Felmondás</span><span class="sxs-lookup"><span data-stu-id="dbf88-577">Resignation</span></span>                    | <span data-ttu-id="dbf88-578">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="dbf88-578">Terminate worker</span></span>     |
| <span data-ttu-id="dbf88-579">PENSION</span><span class="sxs-lookup"><span data-stu-id="dbf88-579">PENSION</span></span>                | <span data-ttu-id="dbf88-580">Nyugdíj</span><span class="sxs-lookup"><span data-stu-id="dbf88-580">Pension</span></span>                        | <span data-ttu-id="dbf88-581">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="dbf88-581">Terminate worker</span></span>     |
| <span data-ttu-id="dbf88-582">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="dbf88-582">TERMINATION</span></span>            | <span data-ttu-id="dbf88-583">Befejezés</span><span class="sxs-lookup"><span data-stu-id="dbf88-583">Termination</span></span>                    | <span data-ttu-id="dbf88-584">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="dbf88-584">Terminate worker</span></span>     |
| <span data-ttu-id="dbf88-585">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="dbf88-585">RETIREMENT</span></span>             | <span data-ttu-id="dbf88-586">Megszüntetés</span><span class="sxs-lookup"><span data-stu-id="dbf88-586">Retirement</span></span>                     | <span data-ttu-id="dbf88-587">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="dbf88-587">Terminate worker</span></span>     |
| <span data-ttu-id="dbf88-588">ABSENTEE</span><span class="sxs-lookup"><span data-stu-id="dbf88-588">ABSENTEE</span></span>               | <span data-ttu-id="dbf88-589">Távollevő</span><span class="sxs-lookup"><span data-stu-id="dbf88-589">Absentee</span></span>                       | <span data-ttu-id="dbf88-590">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="dbf88-590">Terminate worker</span></span>     |
| <span data-ttu-id="dbf88-591">EGYÉB</span><span class="sxs-lookup"><span data-stu-id="dbf88-591">OTHER</span></span>                  | <span data-ttu-id="dbf88-592">Egyéb okok</span><span class="sxs-lookup"><span data-stu-id="dbf88-592">Other Reasons</span></span>                  | <span data-ttu-id="dbf88-593">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="dbf88-593">Terminate worker</span></span>     |
| <span data-ttu-id="dbf88-594">CLOSURE</span><span class="sxs-lookup"><span data-stu-id="dbf88-594">CLOSURE</span></span>                | <span data-ttu-id="dbf88-595">Üzletzárás</span><span class="sxs-lookup"><span data-stu-id="dbf88-595">Business Closure</span></span>               | <span data-ttu-id="dbf88-596">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="dbf88-596">Terminate worker</span></span>     |
| <span data-ttu-id="dbf88-597">DEATH</span><span class="sxs-lookup"><span data-stu-id="dbf88-597">DEATH</span></span>                  | <span data-ttu-id="dbf88-598">Elhalálozás</span><span class="sxs-lookup"><span data-stu-id="dbf88-598">Death</span></span>                          | <span data-ttu-id="dbf88-599">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="dbf88-599">Terminate worker</span></span>     |
| <span data-ttu-id="dbf88-600">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="dbf88-600">LEAVEOFABSENCE</span></span>         | <span data-ttu-id="dbf88-601">Szabadság</span><span class="sxs-lookup"><span data-stu-id="dbf88-601">Leave of Absence</span></span>               | <span data-ttu-id="dbf88-602">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="dbf88-602">Terminate worker</span></span>     |
| <span data-ttu-id="dbf88-603">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="dbf88-603">CONTRACTEND</span></span>            | <span data-ttu-id="dbf88-604">Szerződés vége</span><span class="sxs-lookup"><span data-stu-id="dbf88-604">End of Contract</span></span>                | <span data-ttu-id="dbf88-605">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="dbf88-605">Terminate worker</span></span>     |
| <span data-ttu-id="dbf88-606">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="dbf88-606">SALARYCHANGE</span></span>           | <span data-ttu-id="dbf88-607">Munkabér módosítása</span><span class="sxs-lookup"><span data-stu-id="dbf88-607">Change of Salary</span></span>               | <span data-ttu-id="dbf88-608">Kompenzáció</span><span class="sxs-lookup"><span data-stu-id="dbf88-608">Compensation</span></span>         |

### <a name="terms-of-employment"></a><span data-ttu-id="dbf88-609">Foglalkoztatási feltételek</span><span class="sxs-lookup"><span data-stu-id="dbf88-609">Terms of employment</span></span>

<span data-ttu-id="dbf88-610">A Foglalkoztatási feltételek foglalkoztatási feltételkategóriák létrehozására használatosak.</span><span class="sxs-lookup"><span data-stu-id="dbf88-610">Terms of employment are used to create categories of employment terms.</span></span> <span data-ttu-id="dbf88-611">A feltételek alkalmazási mutató értékekként vannak a Dayforce-hoz rendelve.</span><span class="sxs-lookup"><span data-stu-id="dbf88-611">The terms are mapped to Dayforce as employment indicator values.</span></span>

<span data-ttu-id="dbf88-612">A következő alkalmazási feltételek és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="dbf88-612">The following terms of employment and descriptions are required.</span></span>

| <span data-ttu-id="dbf88-613">Foglalkoztatási feltételek</span><span class="sxs-lookup"><span data-stu-id="dbf88-613">Terms of employment</span></span>   | <span data-ttu-id="dbf88-614">Leírás</span><span class="sxs-lookup"><span data-stu-id="dbf88-614">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="dbf88-615">Szabályos</span><span class="sxs-lookup"><span data-stu-id="dbf88-615">Regular</span></span>               | <span data-ttu-id="dbf88-616">Szabályos</span><span class="sxs-lookup"><span data-stu-id="dbf88-616">Regular</span></span>     |
| <span data-ttu-id="dbf88-617">Közvetlen</span><span class="sxs-lookup"><span data-stu-id="dbf88-617">Direct</span></span>                | <span data-ttu-id="dbf88-618">Közvetlen</span><span class="sxs-lookup"><span data-stu-id="dbf88-618">Direct</span></span>      |
| <span data-ttu-id="dbf88-619">Szakmai gyakorlat</span><span class="sxs-lookup"><span data-stu-id="dbf88-619">Internship</span></span>            | <span data-ttu-id="dbf88-620">Szakmai gyakorlat</span><span class="sxs-lookup"><span data-stu-id="dbf88-620">Internship</span></span>  |
| <span data-ttu-id="dbf88-621">Állandó</span><span class="sxs-lookup"><span data-stu-id="dbf88-621">Permanent</span></span>             | <span data-ttu-id="dbf88-622">Állandó</span><span class="sxs-lookup"><span data-stu-id="dbf88-622">Permanent</span></span>   |

### <a name="marital-status"></a><span data-ttu-id="dbf88-623">Családi állapot</span><span class="sxs-lookup"><span data-stu-id="dbf88-623">Marital status</span></span>

<span data-ttu-id="dbf88-624">Családi állapot értékei Dayforce-hoz vannak rendelve és konvertálva szükség esetén az elfogadható értékekre az integráció során.</span><span class="sxs-lookup"><span data-stu-id="dbf88-624">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="dbf88-625">Az alábbi táblázat bemutatja, hogy családi állapot értékek hogyan vannak leképezve a Dayforce -ban.</span><span class="sxs-lookup"><span data-stu-id="dbf88-625">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="dbf88-626">Emberi erőforrások</span><span class="sxs-lookup"><span data-stu-id="dbf88-626">Human Resources</span></span>                 | <span data-ttu-id="dbf88-627">Dayforce</span><span class="sxs-lookup"><span data-stu-id="dbf88-627">Dayforce</span></span>                  |
|------------------------|---------------------------|
| <span data-ttu-id="dbf88-628">Nős/férjezett</span><span class="sxs-lookup"><span data-stu-id="dbf88-628">Married</span></span>                | <span data-ttu-id="dbf88-629">Nős/férjezett</span><span class="sxs-lookup"><span data-stu-id="dbf88-629">Married</span></span>                   |
| <span data-ttu-id="dbf88-630">Egy</span><span class="sxs-lookup"><span data-stu-id="dbf88-630">Single</span></span>                 | <span data-ttu-id="dbf88-631">Egy</span><span class="sxs-lookup"><span data-stu-id="dbf88-631">Single</span></span>                    |
| <span data-ttu-id="dbf88-632">Özvegy</span><span class="sxs-lookup"><span data-stu-id="dbf88-632">Widowed</span></span>                | <span data-ttu-id="dbf88-633">Özvegy</span><span class="sxs-lookup"><span data-stu-id="dbf88-633">Widowed</span></span>                   |
| <span data-ttu-id="dbf88-634">Elvált</span><span class="sxs-lookup"><span data-stu-id="dbf88-634">Divorced</span></span>               | <span data-ttu-id="dbf88-635">Elvált</span><span class="sxs-lookup"><span data-stu-id="dbf88-635">Divorced</span></span>                  |
| <span data-ttu-id="dbf88-636">Bejegyzett élettársi kapcsolat</span><span class="sxs-lookup"><span data-stu-id="dbf88-636">Registered Partnership</span></span> | <span data-ttu-id="dbf88-637">Élettársi viszony</span><span class="sxs-lookup"><span data-stu-id="dbf88-637">Domestic Partnership</span></span>      |
| <span data-ttu-id="dbf88-638">Nincs</span><span class="sxs-lookup"><span data-stu-id="dbf88-638">None</span></span>                   | <span data-ttu-id="dbf88-639">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="dbf88-639">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="dbf88-640">Együttélés</span><span class="sxs-lookup"><span data-stu-id="dbf88-640">Cohabiting</span></span>             | <span data-ttu-id="dbf88-641">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="dbf88-641">*Not supported by Mexico*</span></span> |

### <a name="gender"></a><span data-ttu-id="dbf88-642">Nem</span><span class="sxs-lookup"><span data-stu-id="dbf88-642">Gender</span></span>

<span data-ttu-id="dbf88-643">A nemek a Dayforce-hoz vannak rendelve és konvertálva szükség esetén az elfogadható értékekre az integráció során.</span><span class="sxs-lookup"><span data-stu-id="dbf88-643">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="dbf88-644">Az alábbi táblázat bemutatja, hogy a nemek hogyan vannak leképezve a Dayforce-ban.</span><span class="sxs-lookup"><span data-stu-id="dbf88-644">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="dbf88-645">Emberi erőforrások</span><span class="sxs-lookup"><span data-stu-id="dbf88-645">Human Resources</span></span>       | <span data-ttu-id="dbf88-646">Dayforce</span><span class="sxs-lookup"><span data-stu-id="dbf88-646">Dayforce</span></span>                  |
|--------------|---------------------------|
| <span data-ttu-id="dbf88-647">Férfi</span><span class="sxs-lookup"><span data-stu-id="dbf88-647">Male</span></span>         | <span data-ttu-id="dbf88-648">Férfi</span><span class="sxs-lookup"><span data-stu-id="dbf88-648">Male</span></span>                      |
| <span data-ttu-id="dbf88-649">Nő</span><span class="sxs-lookup"><span data-stu-id="dbf88-649">Female</span></span>       | <span data-ttu-id="dbf88-650">Nő</span><span class="sxs-lookup"><span data-stu-id="dbf88-650">Female</span></span>                    |
| <span data-ttu-id="dbf88-651">Nem meghatározott</span><span class="sxs-lookup"><span data-stu-id="dbf88-651">Non-specific</span></span> | <span data-ttu-id="dbf88-652">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="dbf88-652">*Not supported by Mexico*</span></span> |

### <a name="payment-method"></a><span data-ttu-id="dbf88-653">Kifizetési mód</span><span class="sxs-lookup"><span data-stu-id="dbf88-653">Payment method</span></span>

<span data-ttu-id="dbf88-654">A Fizetési módok adják meg az alkalmazott és a vállalat számára az alkalmazott kifizetésének módja leírásának lehetőségét.</span><span class="sxs-lookup"><span data-stu-id="dbf88-654">Payment methods give the employee and the company a way to describe how employees will be paid.</span></span> <span data-ttu-id="dbf88-655">A Fizetési módok a Dayforce-hoz vannak rendelve és konvertálva szükség esetén az elfogadható értékekre az integráció során.</span><span class="sxs-lookup"><span data-stu-id="dbf88-655">Payment methods are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="dbf88-656">Az alábbi táblázat bemutatja, hogy a fizetés módok hogyan vannak leképezve a Dayforce-ban.</span><span class="sxs-lookup"><span data-stu-id="dbf88-656">The following table shows how payment methods are mapped to Dayforce.</span></span>

| <span data-ttu-id="dbf88-657">Emberi erőforrások</span><span class="sxs-lookup"><span data-stu-id="dbf88-657">Human Resources</span></span>             | <span data-ttu-id="dbf88-658">Dayforce</span><span class="sxs-lookup"><span data-stu-id="dbf88-658">Dayforce</span></span>                  |
|--------------------|---------------------------|
| <span data-ttu-id="dbf88-659">Készpénz</span><span class="sxs-lookup"><span data-stu-id="dbf88-659">Cash</span></span>               | <span data-ttu-id="dbf88-660">Készpénz</span><span class="sxs-lookup"><span data-stu-id="dbf88-660">Cash</span></span>                      |
| <span data-ttu-id="dbf88-661">Elektronikus fizetés</span><span class="sxs-lookup"><span data-stu-id="dbf88-661">Electronic Payment</span></span> | <span data-ttu-id="dbf88-662">Átvitel</span><span class="sxs-lookup"><span data-stu-id="dbf88-662">Transfer</span></span>                  |
| <span data-ttu-id="dbf88-663">Csekkes</span><span class="sxs-lookup"><span data-stu-id="dbf88-663">Check</span></span>              | <span data-ttu-id="dbf88-664">Csekk</span><span class="sxs-lookup"><span data-stu-id="dbf88-664">Cheque</span></span>                    |
| <span data-ttu-id="dbf88-665">Váltó</span><span class="sxs-lookup"><span data-stu-id="dbf88-665">Bank Draft</span></span>         | <span data-ttu-id="dbf88-666">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="dbf88-666">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="dbf88-667">Egyéb</span><span class="sxs-lookup"><span data-stu-id="dbf88-667">Other</span></span>              | <span data-ttu-id="dbf88-668">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="dbf88-668">*Not supported by Mexico*</span></span> |

### <a name="bank-account-type"></a><span data-ttu-id="dbf88-669">Bankszámla típusa</span><span class="sxs-lookup"><span data-stu-id="dbf88-669">Bank account type</span></span>

<span data-ttu-id="dbf88-670">Bankszámla-típusok az alkalmazottaknak történő elektronikus kifizetésekhez szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="dbf88-670">Bank account types are used for electronic payments to employees.</span></span> <span data-ttu-id="dbf88-671">Bankszámla típusa a Dayforce-ba átutalási számlaadatként van rendelve.</span><span class="sxs-lookup"><span data-stu-id="dbf88-671">Bank account types are mapped to Dayforce as transfer account information.</span></span> <span data-ttu-id="dbf88-672">A bankszámlatípusok szükség esetén konvertálva vannak az elfogadható értékekké az integráció során.</span><span class="sxs-lookup"><span data-stu-id="dbf88-672">The bank account types are translated, as appropriate, to the accepted values upon integration.</span></span>

| <span data-ttu-id="dbf88-673">Emberi erőforrások</span><span class="sxs-lookup"><span data-stu-id="dbf88-673">Human Resources</span></span>            | <span data-ttu-id="dbf88-674">Dayforce</span><span class="sxs-lookup"><span data-stu-id="dbf88-674">Dayforce</span></span>                  |
|-------------------|---------------------------|
| <span data-ttu-id="dbf88-675">Folyószámla</span><span class="sxs-lookup"><span data-stu-id="dbf88-675">Checking Account</span></span>  | <span data-ttu-id="dbf88-676">CheckingAccount</span><span class="sxs-lookup"><span data-stu-id="dbf88-676">CheckingAccount</span></span>           |
| <span data-ttu-id="dbf88-677">Bérlista elszámolási számlája</span><span class="sxs-lookup"><span data-stu-id="dbf88-677">Payroll Account</span></span>   | <span data-ttu-id="dbf88-678">PayrollAccount</span><span class="sxs-lookup"><span data-stu-id="dbf88-678">PayrollAccount</span></span>            |
| <span data-ttu-id="dbf88-679">Megtakarítási számla</span><span class="sxs-lookup"><span data-stu-id="dbf88-679">Savings Account</span></span>   | <span data-ttu-id="dbf88-680">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="dbf88-680">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="dbf88-681">BankGirot-számla</span><span class="sxs-lookup"><span data-stu-id="dbf88-681">BankGirot account</span></span> | <span data-ttu-id="dbf88-682">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="dbf88-682">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="dbf88-683">PlusGirot-számla</span><span class="sxs-lookup"><span data-stu-id="dbf88-683">PlusGirot account</span></span> | <span data-ttu-id="dbf88-684">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="dbf88-684">*Not supported by Mexico*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="dbf88-685">Bevételkódok</span><span class="sxs-lookup"><span data-stu-id="dbf88-685">Earning codes</span></span>

<span data-ttu-id="dbf88-686">A bevételkódok egyedi módon azonosítják a dolgozók által kapott fizetéstípusokat.</span><span class="sxs-lookup"><span data-stu-id="dbf88-686">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="dbf88-687">A kódoknak különböző paramétereket fednek le, amelyek a bevételekhez kapcsolódnak, például könyvelési szabályok, jelentési követelmények és bruttósítási lehetőségek.</span><span class="sxs-lookup"><span data-stu-id="dbf88-687">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="dbf88-688">Ha egy nem támogatott gyakoriság van használatban, a **Minden fizetés** gyakorisága van alapértelmezés szerint használva a kiszámításhoz.</span><span class="sxs-lookup"><span data-stu-id="dbf88-688">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="dbf88-689">Támogatott gyakoriságok</span><span class="sxs-lookup"><span data-stu-id="dbf88-689">Supported frequencies</span></span>

- <span data-ttu-id="dbf88-690">Összes</span><span class="sxs-lookup"><span data-stu-id="dbf88-690">All</span></span>
- <span data-ttu-id="dbf88-691">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="dbf88-691">EVERYPAY</span></span>
- <span data-ttu-id="dbf88-692">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="dbf88-692">EACHPAYPERIOD</span></span>
- <span data-ttu-id="dbf88-693">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="dbf88-693">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="dbf88-694">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="dbf88-694">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="dbf88-695">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbf88-695">1OFMTH</span></span>
- <span data-ttu-id="dbf88-696">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="dbf88-696">LASTOFMTH</span></span>
- <span data-ttu-id="dbf88-697">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbf88-697">2OFMTH</span></span>
- <span data-ttu-id="dbf88-698">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbf88-698">3OFMTH</span></span>
- <span data-ttu-id="dbf88-699">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbf88-699">4OFMTH</span></span>
- <span data-ttu-id="dbf88-700">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbf88-700">5OFMTH</span></span>
- <span data-ttu-id="dbf88-701">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbf88-701">1N2OFMTH</span></span>
- <span data-ttu-id="dbf88-702">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbf88-702">3N4OFMTH</span></span>
- <span data-ttu-id="dbf88-703">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbf88-703">1N3OFMTH</span></span>
- <span data-ttu-id="dbf88-704">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbf88-704">1N4OFMTH</span></span>
- <span data-ttu-id="dbf88-705">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbf88-705">2N3OFMTH</span></span>
- <span data-ttu-id="dbf88-706">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbf88-706">2N4OFMTH</span></span>
- <span data-ttu-id="dbf88-707">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbf88-707">1N2N3OFMTH</span></span>
- <span data-ttu-id="dbf88-708">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbf88-708">1N2N4OFMTH</span></span>
- <span data-ttu-id="dbf88-709">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbf88-709">1N3N4OFMTH</span></span>
- <span data-ttu-id="dbf88-710">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbf88-710">2N3N4OFMTH</span></span>
- <span data-ttu-id="dbf88-711">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="dbf88-711">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="dbf88-712">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="dbf88-712">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="dbf88-713">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="dbf88-713">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="dbf88-714">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="dbf88-714">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="dbf88-715">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="dbf88-715">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="dbf88-716">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="dbf88-716">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="dbf88-717">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="dbf88-717">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="dbf88-718">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="dbf88-718">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="dbf88-719">Címek</span><span class="sxs-lookup"><span data-stu-id="dbf88-719">Addresses</span></span>

<span data-ttu-id="dbf88-720">Az adott ország vagy régió, állam és megye (település) kódok specifikus formátumokat követelnek, hogy Dayforce és az országos és regionális szolgáltatók felismerjék azokat.</span><span class="sxs-lookup"><span data-stu-id="dbf88-720">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="dbf88-721">Annak ellenére, hogy a városok formátuma rugalmas, minden városnak társítva kell lennie egy államhoz.</span><span class="sxs-lookup"><span data-stu-id="dbf88-721">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="dbf88-722">Emberi erőforrások</span><span class="sxs-lookup"><span data-stu-id="dbf88-722">Human Resources</span></span>              | <span data-ttu-id="dbf88-723">Dayforce</span><span class="sxs-lookup"><span data-stu-id="dbf88-723">Dayforce</span></span>              |
|---------------------|-----------------------|
| <span data-ttu-id="dbf88-724">Ország/régió</span><span class="sxs-lookup"><span data-stu-id="dbf88-724">Country/Region</span></span>      | <span data-ttu-id="dbf88-725">Országkód</span><span class="sxs-lookup"><span data-stu-id="dbf88-725">Country Code</span></span>          |
| <span data-ttu-id="dbf88-726">Irányítószám / postai kód</span><span class="sxs-lookup"><span data-stu-id="dbf88-726">Zip/Postal Code</span></span>     | <span data-ttu-id="dbf88-727">Irányítószám</span><span class="sxs-lookup"><span data-stu-id="dbf88-727">Postal Code</span></span>           |
| <span data-ttu-id="dbf88-728">Állami</span><span class="sxs-lookup"><span data-stu-id="dbf88-728">State</span></span>               | <span data-ttu-id="dbf88-729">Államkód</span><span class="sxs-lookup"><span data-stu-id="dbf88-729">State Code</span></span>            |
| <span data-ttu-id="dbf88-730">Város</span><span class="sxs-lookup"><span data-stu-id="dbf88-730">City</span></span>                | <span data-ttu-id="dbf88-731">Város</span><span class="sxs-lookup"><span data-stu-id="dbf88-731">City</span></span>                  |
| <span data-ttu-id="dbf88-732">Megye</span><span class="sxs-lookup"><span data-stu-id="dbf88-732">County</span></span>              | <span data-ttu-id="dbf88-733">Megye (Helyhatóság)</span><span class="sxs-lookup"><span data-stu-id="dbf88-733">County (Municipality)</span></span> |
| <span data-ttu-id="dbf88-734">Utca</span><span class="sxs-lookup"><span data-stu-id="dbf88-734">Street</span></span>              | <span data-ttu-id="dbf88-735">Cím 1. sora</span><span class="sxs-lookup"><span data-stu-id="dbf88-735">Address Line 1</span></span>        |
| <span data-ttu-id="dbf88-736">Utca, házszám</span><span class="sxs-lookup"><span data-stu-id="dbf88-736">Street Number</span></span>       | <span data-ttu-id="dbf88-737">Cím 2. sora</span><span class="sxs-lookup"><span data-stu-id="dbf88-737">Address Line 2</span></span>        |
| <span data-ttu-id="dbf88-738">Épületblokk</span><span class="sxs-lookup"><span data-stu-id="dbf88-738">Building Complement</span></span> | <span data-ttu-id="dbf88-739">Cím 5. sora</span><span class="sxs-lookup"><span data-stu-id="dbf88-739">Address Line 5</span></span>        |

### <a name="passport-number"></a><span data-ttu-id="dbf88-740">Útlevél száma</span><span class="sxs-lookup"><span data-stu-id="dbf88-740">Passport number</span></span>

<span data-ttu-id="dbf88-741">Az alkalmazottak útlevél adatokat is nyilatkozhatnak.</span><span class="sxs-lookup"><span data-stu-id="dbf88-741">Employees can declare passport information.</span></span> <span data-ttu-id="dbf88-742">Az információ a **Útlevél** azonosítótípusra vonatkozik, és az alkalmazott Mexikó-specifikus adataiként van a Dayforce-ba integrálva.</span><span class="sxs-lookup"><span data-stu-id="dbf88-742">This information is of the **Passport** identification type and is integrated into Dayforce as part of an employee's Mexico-specific information.</span></span>

- <span data-ttu-id="dbf88-743">Azonosító típusa = „Útlevél”</span><span class="sxs-lookup"><span data-stu-id="dbf88-743">Identification Type = "Passport"</span></span>
- <span data-ttu-id="dbf88-744">Kibocsátás dátuma</span><span class="sxs-lookup"><span data-stu-id="dbf88-744">Issued Date</span></span>
- <span data-ttu-id="dbf88-745">Lejárat dátuma</span><span class="sxs-lookup"><span data-stu-id="dbf88-745">Expiration Date</span></span>

<span data-ttu-id="dbf88-746">Az alkalmazottak több azonosítószámot is megadhatnak az **Útlevél** azonosítótípushoz.</span><span class="sxs-lookup"><span data-stu-id="dbf88-746">Employees can declare multiple identification numbers of the **Passport** identification type.</span></span> <span data-ttu-id="dbf88-747">Azonban csak az aktuális aktív útlevélbejegyzés van integrálva a Dayforce-ba.</span><span class="sxs-lookup"><span data-stu-id="dbf88-747">However, only the current active passport entry is integrated into Dayforce.</span></span> <span data-ttu-id="dbf88-748">Ha az összes útlevélbejegyzés lejárt, a legutóbb kiállított lesz integrálva a Dayforce-ba.</span><span class="sxs-lookup"><span data-stu-id="dbf88-748">If all passport entries are expired, the passport that was most recently issued is integrated into Dayforce.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]