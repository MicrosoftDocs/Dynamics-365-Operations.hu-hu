---
title: Bérlista-integráció konfigurálása a Talnet és a Dayforce közötti
description: Ez a témakör bemutatja, hogyan kell konfigurálni az integrációt a Microsoft Dynamics 365 Talent és a Ceridian Dayforce között úgy, hogy fel lehessen dolgozni fizetési időszakot.
author: andreabichsel
manager: AnnBe
ms.date: 06/24/2019
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
ms.openlocfilehash: 075b2bdfa08bb190f66b6d60074e1263feedcf70
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/06/2019
ms.locfileid: "2898533"
---
# <a name="configure-payroll-integration-between-talent-and-dayforce"></a><span data-ttu-id="1cd68-103">Bérlista-integráció konfigurálása a Talent és a Dayforce között</span><span class="sxs-lookup"><span data-stu-id="1cd68-103">Configure payroll integration between Talent and Dayforce</span></span>

<span data-ttu-id="1cd68-104">A Microsoft Dynamics 365 Talent és Ceridian Dayforce integrálásához több konfigurációs lépést szükséges elvégezni, melyek ebben a témakörben vannak ismertetve.</span><span class="sxs-lookup"><span data-stu-id="1cd68-104">The integration between Microsoft Dynamics 365 Talent and Ceridian Dayforce relies on several configuration steps that are described in this topic.</span></span> <span data-ttu-id="1cd68-105">Be kell állítania az integrációt a Talent a Dayforce alkalmazásokban is a fizetési időszak feldolgozása előtt.</span><span class="sxs-lookup"><span data-stu-id="1cd68-105">You must configure the integration in both Talent and Dayforce before you can process a pay run.</span></span>

<span data-ttu-id="1cd68-106">Ha olyan szolgáltatást használ a fizetési időszakokhoz, mint a Dayforce, engedélyeznie kell az integrációt a Talentben.</span><span class="sxs-lookup"><span data-stu-id="1cd68-106">When you use a service such as Dayforce to complete pay runs, you must enable the integration in Talent.</span></span> <span data-ttu-id="1cd68-107">Az integrációhoz meghatározott adatok szükségesek a Talentből.</span><span class="sxs-lookup"><span data-stu-id="1cd68-107">The integration requires specific data from Talent.</span></span> <span data-ttu-id="1cd68-108">Ezért ellenőriznie kell, hogy a Dayforce-ban hozzárendelt adatok olyan módon vannak konfigurálva a Talentben, hogy az támogassa az integrációt.</span><span class="sxs-lookup"><span data-stu-id="1cd68-108">Therefore, you must verify that data that is mapped to Dayforce is configured in Talent in a manner that supports the integration.</span></span> <span data-ttu-id="1cd68-109">Az integráció a következő szélesebb adatkategóriákat használja:</span><span class="sxs-lookup"><span data-stu-id="1cd68-109">The integration uses the following broad categories of data:</span></span>

- <span data-ttu-id="1cd68-110">Emberierőforrás-adatok</span><span class="sxs-lookup"><span data-stu-id="1cd68-110">Human resources data</span></span>
- <span data-ttu-id="1cd68-111">Kompenzációadatok</span><span class="sxs-lookup"><span data-stu-id="1cd68-111">Compensation data</span></span>
- <span data-ttu-id="1cd68-112">Bérlistaadatok, mint kifizetési ciklus, fizetési időszakok és bevételkódok</span><span class="sxs-lookup"><span data-stu-id="1cd68-112">Payroll data, such as pay cycles, pay periods, and earning codes</span></span>
- <span data-ttu-id="1cd68-113">Dolgozóadatok</span><span class="sxs-lookup"><span data-stu-id="1cd68-113">Worker data</span></span>

<span data-ttu-id="1cd68-114">Ez a témakör leírja a lépéseket, amelyeket követni kell az integráció engedélyezéséhez.</span><span class="sxs-lookup"><span data-stu-id="1cd68-114">This topic describes the steps that you must follow to enable the integration.</span></span> <span data-ttu-id="1cd68-115">Azt is bemutatja, hogy milyen típusú adatok és konfiguráció szükséges az integrációhoz.</span><span class="sxs-lookup"><span data-stu-id="1cd68-115">It also explains the types of data and the configuration details that the integration requires.</span></span>

## <a name="enable-the-integration"></a><span data-ttu-id="1cd68-116">Engedélyezze az integrációt</span><span class="sxs-lookup"><span data-stu-id="1cd68-116">Enable the integration</span></span>

<span data-ttu-id="1cd68-117">A Talentben be kell kapcsolja a műveletek integrációját, meg kell adnia a konfiguráció adatait, hogy tudjon a Dayforcehoz csatlakozni.</span><span class="sxs-lookup"><span data-stu-id="1cd68-117">In Talent, you must turn on the integration and enter the configuration information to connect to Dayforce.</span></span> <span data-ttu-id="1cd68-118">Ha azt szeretné, hogy a létrehozott általános főkönyvi tranzakció importálva legyen a Microsoft Dynamics 365 Finance alkalmazásba, be kell állítania egy Microsoft Azure tárolási fiókot, majd adja meg, majd Azure tárolási kapcsolat karakterláncát a Finance alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="1cd68-118">If you want the general ledger transaction that is produced to be imported into Microsoft Dynamics 365 Finance, you must also set up a Microsoft Azure storage account and enter the Azure Storage connection string in Finance.</span></span>

<span data-ttu-id="1cd68-119">Az integráció engedélyezéséhez a Talentben kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="1cd68-119">To turn on the integration in Talent, follow these steps.</span></span>

1. <span data-ttu-id="1cd68-120">A **Rendszerfelügyelet** oldalon válassza az **Integrációkonfiguráció** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1cd68-120">On the **System administration** page, select **Integration configuration**.</span></span>
2. <span data-ttu-id="1cd68-121">Adja meg a biztonságos fájl átviteli protokollt (FTP) végpontot és a biztonságos FTP-mappa elérési útja.</span><span class="sxs-lookup"><span data-stu-id="1cd68-121">Enter the secure File Transfer Protocol (FTP) endpoint and the secure FTP folder path.</span></span>
3. <span data-ttu-id="1cd68-122">Adja meg azon felhasználó felhasználónevét és jelszavát, aki hozzáfér a biztonságos FTP végponthoz és a mappa elérési útjához.</span><span class="sxs-lookup"><span data-stu-id="1cd68-122">Enter the user name and password of the user who will access the secure FTP endpoint and folder path.</span></span>
4. <span data-ttu-id="1cd68-123">Tesztelje a kapcsolatot szükség szerint, és állítsa a **Bérlista-integráció engedélyezése** lehetőséggel **Igenre**.</span><span class="sxs-lookup"><span data-stu-id="1cd68-123">Test the connection, as required, and set the **Enable payroll integration** option to **Yes**.</span></span>

<span data-ttu-id="1cd68-124">Ha az integráció engedélyezve van, adatexport adatcsomagok és fájlok jönnek létre, valamint a gyakoriság is be van állítva.</span><span class="sxs-lookup"><span data-stu-id="1cd68-124">When the integration is turned on, the data export package and files are created, and the frequency is set.</span></span> <span data-ttu-id="1cd68-125">Igény szerint módosíthatja a gyakoriságot.</span><span class="sxs-lookup"><span data-stu-id="1cd68-125">You can change this frequency as you require.</span></span>

<span data-ttu-id="1cd68-126">Azure tárolási fiókokkal és Azure tárolási kapcsolati karakterláncokat kapcsolatos további információt az alábbi Azure-témakörökben találja:</span><span class="sxs-lookup"><span data-stu-id="1cd68-126">For more information about Azure storage accounts and Azure Storage connection strings, see the following Azure topics:</span></span>

- [<span data-ttu-id="1cd68-127">Az Azure Storage-fiókokról</span><span class="sxs-lookup"><span data-stu-id="1cd68-127">About Azure storage accounts</span></span>](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [<span data-ttu-id="1cd68-128">Azure Storage kapcsolati karakterláncok konfigurálása</span><span class="sxs-lookup"><span data-stu-id="1cd68-128">Configure Azure Storage connection strings</span></span>](https://docs.microsoft.com/azure/storage/common/storage-configure-connection-string)

### <a name="technical-details-when-payroll-integration-is-enabled"></a><span data-ttu-id="1cd68-129">Technikai részletek a bérlista integrációjának engedélyezésekor</span><span class="sxs-lookup"><span data-stu-id="1cd68-129">Technical details when payroll integration is enabled</span></span>

<span data-ttu-id="1cd68-130">A bérlista-integráció bekapcsolása két elsődleges hatással jár:</span><span class="sxs-lookup"><span data-stu-id="1cd68-130">Turning on the payroll integration has two primary effects:</span></span>

- <span data-ttu-id="1cd68-131">Létrejön egy „bérlista-integráció exportálása” nevű adatexportálási projekt.</span><span class="sxs-lookup"><span data-stu-id="1cd68-131">A data export project named "Payroll integration export" is created.</span></span> <span data-ttu-id="1cd68-132">Ez a projekt a bérlista-integrációhoz szükséges entitásokat és mezőket tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="1cd68-132">This project contains the entities and fields required for the payroll integration.</span></span> <span data-ttu-id="1cd68-133">A projekt vizsgálatához nyissa meg a **Rendszerfelügyeletet**, válassza ki az **Adatkezelési** csempét, majd nyissa meg az adatprojektet a projektek listájából.</span><span class="sxs-lookup"><span data-stu-id="1cd68-133">To examine the project, go to **System administration**, select the **Data management** tile, and then open the data project from the list of projects.</span></span>
- <span data-ttu-id="1cd68-134">Ez a kötegelt feladat végrehajtja az adatexportálási projektet, titkosítja a létrejövő adatcsomagot, és átviszi az adatcsomag-fájlt az **Integráció konfigurációja** képernyőjén beállított SFTP végpontba.</span><span class="sxs-lookup"><span data-stu-id="1cd68-134">This batch job executes the data export project, encrypts the resulting data package, and transfers the data package file to the SFTP endpoint configured on the **Integration configuration** screen.</span></span>

> [!NOTE]
> <span data-ttu-id="1cd68-135">Az SFTP végpontra átvitt adatcsomag titkosítva van a csomag egyedi kulcsával.</span><span class="sxs-lookup"><span data-stu-id="1cd68-135">The data package transferred to the SFTP endpoint is encrypted using a key that is unique to the package.</span></span> <span data-ttu-id="1cd68-136">A kulcs egy Azure kulcstárolóban van, amely csak Ceridian számára érhető el.</span><span class="sxs-lookup"><span data-stu-id="1cd68-136">The key is in an Azure Key Vault that is accessible only by Ceridian.</span></span> <span data-ttu-id="1cd68-137">Az adatcsomag tartalmát nem lehet dekódolni és megvizsgálni.</span><span class="sxs-lookup"><span data-stu-id="1cd68-137">It is not possible to decrypt and examine the data package contents.</span></span> <span data-ttu-id="1cd68-138">Ha meg kell vizsgálnia az adatcsomag tartalmát, akkor manuálisan kell exportálnia a „Bérlista-integráció exportálása” adatprojektet, le kell töltenie, majd meg kell nyitnia.</span><span class="sxs-lookup"><span data-stu-id="1cd68-138">If you need to examine the contents of the data package, you need to export the "Payroll integration export" data project manually, download it, and then open it.</span></span> <span data-ttu-id="1cd68-139">A manuális exportálás nem alkalmazza a titkosítást, és nem viszi át a csomagot.</span><span class="sxs-lookup"><span data-stu-id="1cd68-139">Manual export will not apply encryption or transfer the package.</span></span>

## <a name="configure-your-data"></a><span data-ttu-id="1cd68-140">Adatai konfigurálása</span><span class="sxs-lookup"><span data-stu-id="1cd68-140">Configure your data</span></span> 

<span data-ttu-id="1cd68-141">A bérlista feldolgozásához konfigurálnia kell az emberi erőforrás adatokat a Talentben.</span><span class="sxs-lookup"><span data-stu-id="1cd68-141">To process payroll, you must configure human resource data in Talent.</span></span> <span data-ttu-id="1cd68-142">Be kell állítani a szervezeti adatokat, például a feladatokat és beosztásokat, valamint juttatásokra és a kompenzációra vonatkozó adatokat.</span><span class="sxs-lookup"><span data-stu-id="1cd68-142">You must set up organizational data, such as jobs and positions, together with benefits and compensation information.</span></span> <span data-ttu-id="1cd68-143">Ez az információ megadja a foglalkoztatásra, fizetésre és levonásokra vonatkozó információkat, melyek szükségesek az alkalmazott fizetések generálásához.</span><span class="sxs-lookup"><span data-stu-id="1cd68-143">This information provides the employment, pay, and deduction information that is required in order to generate employee pay.</span></span>

### <a name="human-resource-data"></a><span data-ttu-id="1cd68-144">Emberierőforrás-adatok</span><span class="sxs-lookup"><span data-stu-id="1cd68-144">Human resource data</span></span>

#### <a name="benefits"></a><span data-ttu-id="1cd68-145">Juttatások</span><span class="sxs-lookup"><span data-stu-id="1cd68-145">Benefits</span></span> 

<span data-ttu-id="1cd68-146">Az emberi erőforrások számos beállítási és karbantartási eszközt biztosít, amelyek segítségével beállíthatja és karbantarthatja a szervezet által a dolgozónak biztosított juttatásokat, levonásokat és dolgozói kompenzációs terveket.</span><span class="sxs-lookup"><span data-stu-id="1cd68-146">Human resources provides tools for the setup and maintenance of the benefits, deductions, and worker compensation plans that an organization offers or processes for its workers.</span></span>

<span data-ttu-id="1cd68-147">Juttatások létrehozása esetén ne felejtse el a következő adatokat és beállításokat, amelyeket a Dayforce használ.</span><span class="sxs-lookup"><span data-stu-id="1cd68-147">When you create benefits, keep in mind the following data and configurations that are used in Dayforce.</span></span>

##### <a name="benefit-plans"></a><span data-ttu-id="1cd68-148">Juttatási tervek</span><span class="sxs-lookup"><span data-stu-id="1cd68-148">Benefit plans</span></span>

- <span data-ttu-id="1cd68-149">Terv (szükséges)</span><span class="sxs-lookup"><span data-stu-id="1cd68-149">Plan (required)</span></span>
- <span data-ttu-id="1cd68-150">Típus (szükséges)</span><span class="sxs-lookup"><span data-stu-id="1cd68-150">Type (required)</span></span>
- <span data-ttu-id="1cd68-151">Bérlista hatása (szükséges)</span><span class="sxs-lookup"><span data-stu-id="1cd68-151">Payroll impact (required)</span></span>
- <span data-ttu-id="1cd68-152">Hátralékok helyreállítása</span><span class="sxs-lookup"><span data-stu-id="1cd68-152">Recover arrears</span></span>
- <span data-ttu-id="1cd68-153">Levonási módszer</span><span class="sxs-lookup"><span data-stu-id="1cd68-153">Deduction method</span></span>
- <span data-ttu-id="1cd68-154">Levonás prioritása</span><span class="sxs-lookup"><span data-stu-id="1cd68-154">Deduction priority</span></span>
- <span data-ttu-id="1cd68-155">Időszak korlátozása</span><span class="sxs-lookup"><span data-stu-id="1cd68-155">Limit period</span></span>
- <span data-ttu-id="1cd68-156">Összeghatár</span><span class="sxs-lookup"><span data-stu-id="1cd68-156">Limit amount</span></span>

##### <a name="benefits"></a><span data-ttu-id="1cd68-157">Juttatások</span><span class="sxs-lookup"><span data-stu-id="1cd68-157">Benefits</span></span>

- <span data-ttu-id="1cd68-158">Terv (szükséges)</span><span class="sxs-lookup"><span data-stu-id="1cd68-158">Plan (required)</span></span>
- <span data-ttu-id="1cd68-159">Típus (szükséges)</span><span class="sxs-lookup"><span data-stu-id="1cd68-159">Type (required)</span></span>
- <span data-ttu-id="1cd68-160">Lehetőség (szükséges)</span><span class="sxs-lookup"><span data-stu-id="1cd68-160">Option (required)</span></span>
- <span data-ttu-id="1cd68-161">Juttatás azonosítója (szükséges)</span><span class="sxs-lookup"><span data-stu-id="1cd68-161">Benefit ID (required)</span></span>
- <span data-ttu-id="1cd68-162">Gyakoriság</span><span class="sxs-lookup"><span data-stu-id="1cd68-162">Frequency</span></span>
- <span data-ttu-id="1cd68-163">Alap</span><span class="sxs-lookup"><span data-stu-id="1cd68-163">Basis</span></span>
- <span data-ttu-id="1cd68-164">Összeg vagy mérték</span><span class="sxs-lookup"><span data-stu-id="1cd68-164">Amount or rate</span></span>
- <span data-ttu-id="1cd68-165">Bevételkód</span><span class="sxs-lookup"><span data-stu-id="1cd68-165">Earning code</span></span>

##### <a name="supported-frequencies"></a><span data-ttu-id="1cd68-166">Támogatott gyakoriságok</span><span class="sxs-lookup"><span data-stu-id="1cd68-166">Supported frequencies</span></span> 

- <span data-ttu-id="1cd68-167">Heti</span><span class="sxs-lookup"><span data-stu-id="1cd68-167">Weekly</span></span>
- <span data-ttu-id="1cd68-168">Kétheti</span><span class="sxs-lookup"><span data-stu-id="1cd68-168">Bi-weekly</span></span>
- <span data-ttu-id="1cd68-169">Félhavi</span><span class="sxs-lookup"><span data-stu-id="1cd68-169">Semi-monthly</span></span>
- <span data-ttu-id="1cd68-170">Havi</span><span class="sxs-lookup"><span data-stu-id="1cd68-170">Monthly</span></span>

##### <a name="supported-bases"></a><span data-ttu-id="1cd68-171">Támogatott alapok</span><span class="sxs-lookup"><span data-stu-id="1cd68-171">Supported bases</span></span> 

- <span data-ttu-id="1cd68-172">Rögzített összeg</span><span class="sxs-lookup"><span data-stu-id="1cd68-172">Fixed amount</span></span>
- <span data-ttu-id="1cd68-173">Bevételek százaléka</span><span class="sxs-lookup"><span data-stu-id="1cd68-173">Percent of earnings</span></span>
- <span data-ttu-id="1cd68-174">Produktív órák</span><span class="sxs-lookup"><span data-stu-id="1cd68-174">Productive hours</span></span>

<span data-ttu-id="1cd68-175">A Dayforce létrehozza a következő levonásokat, a juttatási tervben definiált bérlistahatás alapján.</span><span class="sxs-lookup"><span data-stu-id="1cd68-175">Dayforce creates the following deductions, based on the payroll impact that is defined on the benefit plan.</span></span>

| <span data-ttu-id="1cd68-176">Kiválasztás a Talentben</span><span class="sxs-lookup"><span data-stu-id="1cd68-176">Selection in Talent</span></span>        | <span data-ttu-id="1cd68-177">Eredmény a Dayforce-ban</span><span class="sxs-lookup"><span data-stu-id="1cd68-177">Result in Dayforce</span></span>                            |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="1cd68-178">Nincs</span><span class="sxs-lookup"><span data-stu-id="1cd68-178">None</span></span>                       | <span data-ttu-id="1cd68-179">Nincs létrehozva levonás.</span><span class="sxs-lookup"><span data-stu-id="1cd68-179">No deduction is created.</span></span>                      |
| <span data-ttu-id="1cd68-180">Csak levonás</span><span class="sxs-lookup"><span data-stu-id="1cd68-180">Deduction only</span></span>             | <span data-ttu-id="1cd68-181">Alkalmazotti levonás jön létre.</span><span class="sxs-lookup"><span data-stu-id="1cd68-181">An employee deduction is created.</span></span>             |
| <span data-ttu-id="1cd68-182">Csak hozzájárulás</span><span class="sxs-lookup"><span data-stu-id="1cd68-182">Contribution only</span></span>          | <span data-ttu-id="1cd68-183">Egy alkalmazotti levonás jön létre.</span><span class="sxs-lookup"><span data-stu-id="1cd68-183">An employer deduction is created.</span></span>             |
| <span data-ttu-id="1cd68-184">Levonás és hozzájárulás</span><span class="sxs-lookup"><span data-stu-id="1cd68-184">Deduction and contribution</span></span> | <span data-ttu-id="1cd68-185">Alkalmazotti és a munkáltatói levonások jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="1cd68-185">Employee and employer deductions are created.</span></span> |

<span data-ttu-id="1cd68-186">A juttatási programok definiálásával és kezelésével kapcsolatosan további tájékoztatás a következő témakörökben talál:</span><span class="sxs-lookup"><span data-stu-id="1cd68-186">For more information about how to define and manage a benefits program, see the following topics:</span></span>

- [<span data-ttu-id="1cd68-187">Alkalmazotti juttatási program megvalósítása</span><span class="sxs-lookup"><span data-stu-id="1cd68-187">Deliver an employee benefits program</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [<span data-ttu-id="1cd68-188">Új juttatás létrehozása</span><span class="sxs-lookup"><span data-stu-id="1cd68-188">Create a new benefit</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [<span data-ttu-id="1cd68-189">Juttatásra való jogosultsági szabályok és irányelvek meghatározása</span><span class="sxs-lookup"><span data-stu-id="1cd68-189">Define benefit eligibility rules and policies</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [<span data-ttu-id="1cd68-190">Dolgozók juttatásainak felvétele és eltávolítása</span><span class="sxs-lookup"><span data-stu-id="1cd68-190">Enroll and remove benefits from workers</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a><span data-ttu-id="1cd68-191">Kompenzáció</span><span class="sxs-lookup"><span data-stu-id="1cd68-191">Compensation</span></span> 

<span data-ttu-id="1cd68-192">A kompenzációkezeléssel szabályozható az alapfizetés és a jutalmak kifizetése.</span><span class="sxs-lookup"><span data-stu-id="1cd68-192">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="1cd68-193">Egy alkalmazott fix fizetési díjalapja és érdemeken alapuló fizetése kezelhető a fix kompenzációs tervekkel.</span><span class="sxs-lookup"><span data-stu-id="1cd68-193">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="1cd68-194">Az ösztönző díjak kifizetése, például bónuszok, teljesítménydíjak, részvényopciók és kölcsönök, továbbá az egyszeri jutalmak a változó kompenzációs tervekben szabályozhatók.</span><span class="sxs-lookup"><span data-stu-id="1cd68-194">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span>

<span data-ttu-id="1cd68-195">A Dayforce a kompenzációs adatok segítségével kiszámítja az alkalmazott óradíját vagy éves díját.</span><span class="sxs-lookup"><span data-stu-id="1cd68-195">Dayforce uses compensation information to calculate an employee's hourly or annual rate.</span></span> <span data-ttu-id="1cd68-196">Fix kompenzációs tervek és a fizetési díjalap átalakítások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="1cd68-196">Fixed compensation plans and pay rate conversions are required.</span></span> <span data-ttu-id="1cd68-197">Az alkalmazottakat hozzá kell rendelni a fix kompenzációs tervhez.</span><span class="sxs-lookup"><span data-stu-id="1cd68-197">Employees must be associated with a fixed compensation plan.</span></span>

<span data-ttu-id="1cd68-198">A következő témakörökben bővebben olvashat a kompenzációs tervekről:</span><span class="sxs-lookup"><span data-stu-id="1cd68-198">For more information about compensation plans, see the following topics:</span></span>

- [<span data-ttu-id="1cd68-199">Fix kompenzációs konstrukciók létrehozása</span><span class="sxs-lookup"><span data-stu-id="1cd68-199">Create fixed compensation plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [<span data-ttu-id="1cd68-200">Változó kompenzációs konstrukciók létrehozása</span><span class="sxs-lookup"><span data-stu-id="1cd68-200">Create variable compensation plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [<span data-ttu-id="1cd68-201">Munkabér-/kompenzációs struktúra és tervek kialakítása</span><span class="sxs-lookup"><span data-stu-id="1cd68-201">Develop salary/compensation structure and plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [<span data-ttu-id="1cd68-202">Folyamatkompenzáció</span><span class="sxs-lookup"><span data-stu-id="1cd68-202">Process compensation</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/process-compensation)
- [<span data-ttu-id="1cd68-203">Kompenzációs folyamat meghatározása és eredmények kiszámítása</span><span class="sxs-lookup"><span data-stu-id="1cd68-203">Define compensation process and calculate results</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [<span data-ttu-id="1cd68-204">Alkalmazottak felvétele fix kompenzációs konstrukcióba</span><span class="sxs-lookup"><span data-stu-id="1cd68-204">Enroll an employee in a fixed compensation plan</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [<span data-ttu-id="1cd68-205">Alkalmazottak felvétele változó kompenzációs konstrukcióba</span><span class="sxs-lookup"><span data-stu-id="1cd68-205">Enroll an employee in a variable compensation plan</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a><span data-ttu-id="1cd68-206">Beosztások</span><span class="sxs-lookup"><span data-stu-id="1cd68-206">Jobs</span></span> 

<span data-ttu-id="1cd68-207">A munkakör azon feladatok és felelősségek gyűjteménye, amelyek egy adott munkát végrehajtó személytől elvártak.</span><span class="sxs-lookup"><span data-stu-id="1cd68-207">A job is a collection of the tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="1cd68-208">További információ a következő témakörökben olvasható:</span><span class="sxs-lookup"><span data-stu-id="1cd68-208">For more information, see the following topics:</span></span>

- [<span data-ttu-id="1cd68-209">Feladat összetevőinek beállítása</span><span class="sxs-lookup"><span data-stu-id="1cd68-209">Setting up the components of a job</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-job)
- [<span data-ttu-id="1cd68-210">Új feladatok meghatározása</span><span class="sxs-lookup"><span data-stu-id="1cd68-210">Define new jobs</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a><span data-ttu-id="1cd68-211">Beosztások</span><span class="sxs-lookup"><span data-stu-id="1cd68-211">Positions</span></span>

<span data-ttu-id="1cd68-212">Egy beosztás egy feladat egyedi példánya.</span><span class="sxs-lookup"><span data-stu-id="1cd68-212">A position is an individual instance of a job.</span></span> <span data-ttu-id="1cd68-213">Például az „Értékesítési igazgató (Kelet)” pozíció egyike azon beosztásoknak, amelyek társíthatók az „Értékesítési igazgató” feladathoz.</span><span class="sxs-lookup"><span data-stu-id="1cd68-213">For example, the "Sales manager (East)" position is one of the positions that are associated with the "Sales manager" job.</span></span> <span data-ttu-id="1cd68-214">A beosztás létezik a részlegben.</span><span class="sxs-lookup"><span data-stu-id="1cd68-214">A position exists in a department.</span></span> <span data-ttu-id="1cd68-215">Egy beosztáshoz csak egy dolgozó rendelhető.</span><span class="sxs-lookup"><span data-stu-id="1cd68-215">Only one worker can be associated with each position.</span></span>

<span data-ttu-id="1cd68-216">A következő adatokat és konfigurációkat szem előtt tartani beosztások beállításakor:</span><span class="sxs-lookup"><span data-stu-id="1cd68-216">Keep the following data and configuration in mind when you set up positions:</span></span>

- <span data-ttu-id="1cd68-217">Beosztás (szükséges)</span><span class="sxs-lookup"><span data-stu-id="1cd68-217">Position (required)</span></span>
- <span data-ttu-id="1cd68-218">Leírás (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-218">Description (required)</span></span>
- <span data-ttu-id="1cd68-219">Munka (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-219">Job (required)</span></span>
- <span data-ttu-id="1cd68-220">Részleg (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-220">Department (required)</span></span>
- <span data-ttu-id="1cd68-221">Beosztás típusa (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-221">Position type (required)</span></span>
- <span data-ttu-id="1cd68-222">Teljes munkaidőssel egyenértékű</span><span class="sxs-lookup"><span data-stu-id="1cd68-222">Full-time equivalent</span></span>
- <span data-ttu-id="1cd68-223">Éves rendes munkaidő (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-223">Annual regular hours (required)</span></span>
- <span data-ttu-id="1cd68-224">Jogi személy által fizetett (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-224">Paid by legal entity (required)</span></span>
- <span data-ttu-id="1cd68-225">Fizetési ciklus (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-225">Pay cycle (required)</span></span>
- <span data-ttu-id="1cd68-226">Alapértelmezett pénzügyi dimenzió – Költséghely (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-226">Default financial dimension – Cost center (required)</span></span>
- <span data-ttu-id="1cd68-227">Dolgozó-hozzárendelés – dolgozó-hozzárendelés kezdete, hozzárendelés vége és okkód</span><span class="sxs-lookup"><span data-stu-id="1cd68-227">Worker assignment – Worker, assignment start, assignment end, reason code</span></span>

<span data-ttu-id="1cd68-228">A azonos osztály több beosztása társítva van az ugyanazon a feladathoz, azok össze lesznek vonva a Dayforce egyetlen pozíciójába.</span><span class="sxs-lookup"><span data-stu-id="1cd68-228">If multiple positions in the same department are associated with the same job, they are consolidated into a single position in Dayforce.</span></span>

<span data-ttu-id="1cd68-229">További információ a következő témakörökben olvasható:</span><span class="sxs-lookup"><span data-stu-id="1cd68-229">For more information, see the following topics:</span></span>

- [<span data-ttu-id="1cd68-230">Munkaerő szervezése részlegek, munkák és beosztások szerint</span><span class="sxs-lookup"><span data-stu-id="1cd68-230">Organize your workforce using departments, jobs, and positions</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [<span data-ttu-id="1cd68-231">Beosztások beállítása</span><span class="sxs-lookup"><span data-stu-id="1cd68-231">Set up positions</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a><span data-ttu-id="1cd68-232">Osztályok</span><span class="sxs-lookup"><span data-stu-id="1cd68-232">Departments</span></span>

<span data-ttu-id="1cd68-233">A részleg egy működési egység, amely a szervezet egy kategóriáját vagy működési területét képviseli.</span><span class="sxs-lookup"><span data-stu-id="1cd68-233">A department is an operating unit that represents a category or functional area of an organization.</span></span> <span data-ttu-id="1cd68-234">Egy részleg a szervezet egy konkrét területen végzett tevékenységeiért felel (például értékesítés, könyvelés, emberi erőforrások).</span><span class="sxs-lookup"><span data-stu-id="1cd68-234">A department is responsible for a specific area of the organization, such as sales, accounting, or human resources.</span></span> <span data-ttu-id="1cd68-235">A részlegek segítségével hozhatók létre jelentések a működési területekről.</span><span class="sxs-lookup"><span data-stu-id="1cd68-235">You can use departments to report on functional areas.</span></span> <span data-ttu-id="1cd68-236">A részlegeknek lehet eredménykimutatási felelőssége.</span><span class="sxs-lookup"><span data-stu-id="1cd68-236">Departments might have profit and loss responsibility.</span></span>

<span data-ttu-id="1cd68-237">További információ a következő témakörökben olvasható:</span><span class="sxs-lookup"><span data-stu-id="1cd68-237">For more information, see the following topics:</span></span>

- [<span data-ttu-id="1cd68-238">Részleg létrehozása és társítása a szervezeti hierarchiához</span><span class="sxs-lookup"><span data-stu-id="1cd68-238">Create a department and associate it with the department hierarchy</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [<span data-ttu-id="1cd68-239">Új részlegek meghatározása</span><span class="sxs-lookup"><span data-stu-id="1cd68-239">Define new departments</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a><span data-ttu-id="1cd68-240">Fizetési ciklusok és fizetési időszakok</span><span class="sxs-lookup"><span data-stu-id="1cd68-240">Pay cycles and pay periods</span></span>

<span data-ttu-id="1cd68-241">A fizetési ciklus meghatározza, hogy milyen gyakran történik a bérlista folyósítása, és a dolgozók mely napokon kapnak fizetést,.</span><span class="sxs-lookup"><span data-stu-id="1cd68-241">A pay cycle determines how often payroll is run and the specific days when workers are paid.</span></span> <span data-ttu-id="1cd68-242">Például a kifizetési ciklus lehet, havi, és az alkalmazottak kaphatják a hónap utolsó napján a fizetésüket.</span><span class="sxs-lookup"><span data-stu-id="1cd68-242">For example, a pay cycle might be monthly, and employees might be paid on the last day of the month.</span></span> <span data-ttu-id="1cd68-243">Vagy a kifizetési ciklus lehet heti, és az alkalmazottak a fizetési időszak utáni kedden kaphatják fizetésüket.</span><span class="sxs-lookup"><span data-stu-id="1cd68-243">Alternatively, a pay cycle might be weekly, and employees might be paid on the Tuesday after the end of the pay period.</span></span> <span data-ttu-id="1cd68-244">Kifizetési ciklusok beosztásokhoz vannak rendelve, és szabályozzák, hogy az ebben a beosztásban lévő dolgozók mikor kapnak fizetést.</span><span class="sxs-lookup"><span data-stu-id="1cd68-244">Pay cycles are assigned to positions to control when workers in those positions are paid.</span></span>

<span data-ttu-id="1cd68-245">Miután létrehozott fizetési ciklusokat, minden egyes ciklushoz fizetési időszakot hozhat létre.</span><span class="sxs-lookup"><span data-stu-id="1cd68-245">After you create pay cycles, you can generate pay periods for each cycle.</span></span> <span data-ttu-id="1cd68-246">Minden fizetési időszakban egy alapértelmezett fizetési dátum van, amely a megadott adatokon alapul.</span><span class="sxs-lookup"><span data-stu-id="1cd68-246">Each pay period includes a default payment date that is based on information that you provide.</span></span> <span data-ttu-id="1cd68-247">Ugyanakkor az alapértelmezett fizetési dátumot a fizetési időszakban módosíthatja kivételekhez például amikor egy kifizetési dátum ünnepnapra esik.</span><span class="sxs-lookup"><span data-stu-id="1cd68-247">However, you can modify the default payment date in a pay period to allow for exceptions, such as when the payment date falls on a holiday.</span></span>

<span data-ttu-id="1cd68-248">A következő adatokat használja a Dayforce:</span><span class="sxs-lookup"><span data-stu-id="1cd68-248">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="1cd68-249">Fizetési ciklus (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-249">Pay cycle (required)</span></span>
- <span data-ttu-id="1cd68-250">Fizetési ciklus gyakorisága (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-250">Pay cycle frequency (required)</span></span>
- <span data-ttu-id="1cd68-251">Az időszak kezdő dátuma (az első fizetési időszak szükséges)</span><span class="sxs-lookup"><span data-stu-id="1cd68-251">Period start date (first pay period required)</span></span>
- <span data-ttu-id="1cd68-252">Alapértelmezett fizetési dátum (az első fizetési időszak szükséges)</span><span class="sxs-lookup"><span data-stu-id="1cd68-252">Default payment date (first pay period required)</span></span>

<span data-ttu-id="1cd68-253">Ez az információ Dayforceba fizetési csoportokként van integrálva országonként vagy régiónként le van választva egyes kifizetési ciklusokhoz.</span><span class="sxs-lookup"><span data-stu-id="1cd68-253">This information is integrated with Dayforce as pay groups, and is separated by country or region for each pay cycle.</span></span> <span data-ttu-id="1cd68-254">Legalább egy fizetési időszakot kell létrehozni az integráció előtt.</span><span class="sxs-lookup"><span data-stu-id="1cd68-254">At least one pay period must be generated before integration.</span></span> <span data-ttu-id="1cd68-255">Dayforce létrehoz fizetési csoport naptárakat és a kifizetési dátumokat, az első fizetési időszak kezdő dátuma és az alapértelmezett fizetési dátum alapján, melyek a Talentben vannak beállítva.</span><span class="sxs-lookup"><span data-stu-id="1cd68-255">Dayforce generates pay group calendars and payment dates, based on the start date of the first pay period and the default payment date that is set up in Talent.</span></span>

#### <a name="earning-codes"></a><span data-ttu-id="1cd68-256">Bevételkódok</span><span class="sxs-lookup"><span data-stu-id="1cd68-256">Earning codes</span></span>

<span data-ttu-id="1cd68-257">A bevételkódok egyedi módon azonosítják a dolgozók által kapott fizetéstípusokat.</span><span class="sxs-lookup"><span data-stu-id="1cd68-257">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="1cd68-258">A kódoknak különböző paraméterei vannak, amelyek a bevételekhez kapcsolódnak, például könyvelési szabályok, jelentési követelmények és bruttósítási lehetőségek.</span><span class="sxs-lookup"><span data-stu-id="1cd68-258">The codes have various parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span>

<span data-ttu-id="1cd68-259">A következő adatokat használja a Dayforce:</span><span class="sxs-lookup"><span data-stu-id="1cd68-259">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="1cd68-260">Bevételkód (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-260">Earning Code (required)</span></span>
- <span data-ttu-id="1cd68-261">Leírás</span><span class="sxs-lookup"><span data-stu-id="1cd68-261">Description</span></span>
- <span data-ttu-id="1cd68-262">Mértékegység</span><span class="sxs-lookup"><span data-stu-id="1cd68-262">Unit of measure</span></span>
- <span data-ttu-id="1cd68-263">Produktív</span><span class="sxs-lookup"><span data-stu-id="1cd68-263">Productive</span></span>

### <a name="worker-data"></a><span data-ttu-id="1cd68-264">Dolgozóadatok</span><span class="sxs-lookup"><span data-stu-id="1cd68-264">Worker data</span></span>

<span data-ttu-id="1cd68-265">A dolgozók különböző típusaihoz tartozó rekordok, melyek fontosak az emberi erőforrásoknak és a bérlistarendszerekhez.</span><span class="sxs-lookup"><span data-stu-id="1cd68-265">Records for the various types of workers that you have are important to your human resources and payroll systems.</span></span> <span data-ttu-id="1cd68-266">A bevitt információk felhasználhatók az dolgozói és személyes adatok nyilvántartására.</span><span class="sxs-lookup"><span data-stu-id="1cd68-266">The information that you enter can be used to track workers and personal information.</span></span>

<span data-ttu-id="1cd68-267">A dolgozók következő adatait tarthatja karban:</span><span class="sxs-lookup"><span data-stu-id="1cd68-267">You can maintain the following information for workers:</span></span>

- <span data-ttu-id="1cd68-268">**Alapvető** – A dolgozók alapvető információi, például a kapcsolattartási adatok, demográfiai adatok azonosító adatok, családi adatok, a katonai szolgálat állapota, kiküldetésekre vonatkozó adatok, illetve személyes és rendkívüli kapcsolattartók.</span><span class="sxs-lookup"><span data-stu-id="1cd68-268">**Basic** – Maintain basic information about a worker, such as contact information, demographic information, identification information, family information, military service status, expatriate information, and personal and emergency contacts.</span></span>
- <span data-ttu-id="1cd68-269">**Foglalkoztatás** – Információk a dolgozó munkaviszonyáról, például a vállalati vagy szervezeti kapcsolat, hozzárendelt pozíció, kezdő és záró dátumok, munkajogosultság, foglalkoztatás feltételei, nyugdíj, szabadság és áthelyezéssel kapcsolatos információk.</span><span class="sxs-lookup"><span data-stu-id="1cd68-269">**Employment** – Maintain information about a worker's employment, such as company or organization affiliation, position assignment, start and end dates, work eligibility, terms of employment, pension, vacation, and relocation information.</span></span>
- <span data-ttu-id="1cd68-270">**Szabadság és a távollét** – A dolgozó távolléteinek kezelése, például a munkaidő-naptárak, a távolléti tranzakciók és távollét beállítása.</span><span class="sxs-lookup"><span data-stu-id="1cd68-270">**Leave and absence** – Maintain information about a worker's absences, such as working calendars, absence transactions, and absence setup.</span></span>
- <span data-ttu-id="1cd68-271">**Kompenzáció és bérlista** – dolgozói kompenzációs tervek és bérlistainformációk kezelése, például felvétel konstrukciója, jutalmak, teljesítmény, jutalék, adózási információk, nyugdíj és fizetéslevonások.</span><span class="sxs-lookup"><span data-stu-id="1cd68-271">**Compensation and payroll** – Maintain information about a worker's compensation plans and payroll information, such as plan enrollment, awards, performance, commission, tax information, retirement, and salary deductions.</span></span>

<span data-ttu-id="1cd68-272">A dolgozóinformációk létrehozása esetén ne felejtse el a következő adatokat és beállításokat, amelyeket a Dayforce használ.</span><span class="sxs-lookup"><span data-stu-id="1cd68-272">When you enter worker information, keep in mind the following data and configurations that are used in Dayforce.</span></span>

#### <a name="general-information"></a><span data-ttu-id="1cd68-273">Általános információk</span><span class="sxs-lookup"><span data-stu-id="1cd68-273">General information</span></span>

- <span data-ttu-id="1cd68-274">Személyzeti szám (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-274">Personnel number (required)</span></span>
- <span data-ttu-id="1cd68-275">Utónév (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-275">First name (required)</span></span>
- <span data-ttu-id="1cd68-276">Vezetéknév (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-276">Last name (required)</span></span>
- <span data-ttu-id="1cd68-277">Második keresztnév</span><span class="sxs-lookup"><span data-stu-id="1cd68-277">Middle name</span></span>
- <span data-ttu-id="1cd68-278">Szolgálati idő dátuma</span><span class="sxs-lookup"><span data-stu-id="1cd68-278">Seniority date</span></span>
- <span data-ttu-id="1cd68-279">Más néven</span><span class="sxs-lookup"><span data-stu-id="1cd68-279">Known as</span></span>

#### <a name="personal-information"></a><span data-ttu-id="1cd68-280">Személyes információ</span><span class="sxs-lookup"><span data-stu-id="1cd68-280">Personal information</span></span>

- <span data-ttu-id="1cd68-281">Családi állapot (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-281">Marital status (required)</span></span>
- <span data-ttu-id="1cd68-282">Születési dátum (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-282">Birth date (required)</span></span>
- <span data-ttu-id="1cd68-283">Nem (szükséges)</span><span class="sxs-lookup"><span data-stu-id="1cd68-283">Gender (required)</span></span>
- <span data-ttu-id="1cd68-284">Fogyatékkal élő személy</span><span class="sxs-lookup"><span data-stu-id="1cd68-284">Person with disabilities</span></span>
- <span data-ttu-id="1cd68-285">Állampolgárság ország régió (csak a Mexikó)</span><span class="sxs-lookup"><span data-stu-id="1cd68-285">Nationality country region (only for Mexico)</span></span>

#### <a name="address-information"></a><span data-ttu-id="1cd68-286">Címadatok</span><span class="sxs-lookup"><span data-stu-id="1cd68-286">Address information</span></span>

- <span data-ttu-id="1cd68-287">Elsődleges (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-287">Primary (required)</span></span>
- <span data-ttu-id="1cd68-288">Ország/régiót (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-288">Country/region (required)</span></span>
- <span data-ttu-id="1cd68-289">Irányítószámot (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-289">Postal code (required)</span></span>
- <span data-ttu-id="1cd68-290">Utca, házszám (kötelező) (csak Mexikó esetén)</span><span class="sxs-lookup"><span data-stu-id="1cd68-290">Street Number (required) (Only for Mexico)</span></span>
- <span data-ttu-id="1cd68-291">Épületblokk (csak a Mexikó)</span><span class="sxs-lookup"><span data-stu-id="1cd68-291">Building Complement (Only for Mexico)</span></span>
- <span data-ttu-id="1cd68-292">Város (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-292">City (required)</span></span>
- <span data-ttu-id="1cd68-293">Állam (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-293">State (required)</span></span>
- <span data-ttu-id="1cd68-294">Megye (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-294">County (required)</span></span>

#### <a name="contact-information"></a><span data-ttu-id="1cd68-295">Névjegy adatai</span><span class="sxs-lookup"><span data-stu-id="1cd68-295">Contact information</span></span> 

- <span data-ttu-id="1cd68-296">Elsődleges (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-296">Primary (required)</span></span>
- <span data-ttu-id="1cd68-297">Kapcsolattartó száma (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-297">Contact number (required)</span></span>
- <span data-ttu-id="1cd68-298">Mellék</span><span class="sxs-lookup"><span data-stu-id="1cd68-298">Extension</span></span>

#### <a name="payroll-information-and-earning-codes"></a><span data-ttu-id="1cd68-299">Bérlistaadatok és bevételkódok</span><span class="sxs-lookup"><span data-stu-id="1cd68-299">Payroll information and earning codes</span></span>

<span data-ttu-id="1cd68-300">Alkalmazottak hozzárendelhetők meghatározott bevételekhez adott fizetési gyakorisággal, és magadható elsődleges fizetési mód.</span><span class="sxs-lookup"><span data-stu-id="1cd68-300">Employees may be assigned specific earnings at a given frequency of payment and have a preferred payment method.</span></span> <span data-ttu-id="1cd68-301">A következő mezőket a Dayforce arra használja, hogy garantálja, hogy ezeket a preferenciákat és beállításokat használja.</span><span class="sxs-lookup"><span data-stu-id="1cd68-301">The following fields are used in Dayforce to help guarantee that those preferences and settings are used.</span></span>

##### <a name="earning-codes"></a><span data-ttu-id="1cd68-302">Bevételkódok</span><span class="sxs-lookup"><span data-stu-id="1cd68-302">Earning codes</span></span>

- <span data-ttu-id="1cd68-303">Beosztás (szükséges)</span><span class="sxs-lookup"><span data-stu-id="1cd68-303">Position (required)</span></span>
- <span data-ttu-id="1cd68-304">Bevételkód (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-304">Earning Code (required)</span></span>
- <span data-ttu-id="1cd68-305">Gyakoriság (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-305">Frequency (required)</span></span>
- <span data-ttu-id="1cd68-306">Összeg (szükséges)</span><span class="sxs-lookup"><span data-stu-id="1cd68-306">Amount (required)</span></span>

##### <a name="payroll-information"></a><span data-ttu-id="1cd68-307">Bérlistaadatok</span><span class="sxs-lookup"><span data-stu-id="1cd68-307">Payroll information</span></span>

- <span data-ttu-id="1cd68-308">Kifizetési mód</span><span class="sxs-lookup"><span data-stu-id="1cd68-308">Payment Method</span></span>
- <span data-ttu-id="1cd68-309">Gazdasági régió (szükséges)</span><span class="sxs-lookup"><span data-stu-id="1cd68-309">Economic Region (required)</span></span>
- <span data-ttu-id="1cd68-310">Alkalmazott juttatásainak azonosítója</span><span class="sxs-lookup"><span data-stu-id="1cd68-310">Employee Benefits ID</span></span>
- <span data-ttu-id="1cd68-311">Nemzeti azonosító (szükséges)</span><span class="sxs-lookup"><span data-stu-id="1cd68-311">National ID Number (required)</span></span>
- <span data-ttu-id="1cd68-312">Katonai szolgálat száma</span><span class="sxs-lookup"><span data-stu-id="1cd68-312">Military Service Number</span></span>
- <span data-ttu-id="1cd68-313">Műszakazonosító (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-313">Shift ID (required)</span></span>
- <span data-ttu-id="1cd68-314">Adószám (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-314">Tax Number (required)</span></span>
- <span data-ttu-id="1cd68-315">Szakszervezeti azonosító (szükséges)</span><span class="sxs-lookup"><span data-stu-id="1cd68-315">Union ID (required)</span></span>
- <span data-ttu-id="1cd68-316">Munkanap azonosítója (szükséges)</span><span class="sxs-lookup"><span data-stu-id="1cd68-316">Work Day ID (required)</span></span>
- <span data-ttu-id="1cd68-317">Munkavállalási engedély száma</span><span class="sxs-lookup"><span data-stu-id="1cd68-317">Work Permit Number</span></span>

> [!NOTE]
> <span data-ttu-id="1cd68-318">A fizetési módhoz Mexikó támogatja a **Készpénzt**, **Csekket** (a vállalat fizikai csekkjét és az **Elektronikus fizetést**.</span><span class="sxs-lookup"><span data-stu-id="1cd68-318">For the payment method, Mexico supports **Cash**, **Check** (the company's physical check), and **Electronic Payment**.</span></span> <span data-ttu-id="1cd68-319">Ha nincs fizetési mód van megadva, alapértelmezés szerint a **Csekk** használt.</span><span class="sxs-lookup"><span data-stu-id="1cd68-319">If np payment method is specified, **Check** is used by default.</span></span>

#### <a name="employment-details"></a><span data-ttu-id="1cd68-320">Foglalkoztatás részletei</span><span class="sxs-lookup"><span data-stu-id="1cd68-320">Employment details</span></span>

<span data-ttu-id="1cd68-321">Foglalkoztatási előzményei kulcsfontosságú információkat tartalmaznak a munkavállaók felvételi, elbocsátási, és újbóli felvétele állapotával kapcsolatosan a Dayforce-ban.</span><span class="sxs-lookup"><span data-stu-id="1cd68-321">Employment detail history is used as key information to derive an employee's hire, termination, and rehire statuses in Dayforce.</span></span> <span data-ttu-id="1cd68-322">Dayforce egyszerre csak egy aktív foglalkoztatásrekordot tesz lehetővé.</span><span class="sxs-lookup"><span data-stu-id="1cd68-322">Dayforce supports only one active employment record at a time.</span></span>

- <span data-ttu-id="1cd68-323">Foglalkoztatás kezdődátuma (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-323">Employment start date (required)</span></span>
- <span data-ttu-id="1cd68-324">Munkaviszony záró dátuma</span><span class="sxs-lookup"><span data-stu-id="1cd68-324">Employment end date</span></span>
- <span data-ttu-id="1cd68-325">Kezdő dátum</span><span class="sxs-lookup"><span data-stu-id="1cd68-325">Start date</span></span>
- <span data-ttu-id="1cd68-326">Módosított kezdési időpont</span><span class="sxs-lookup"><span data-stu-id="1cd68-326">Adjusted start date</span></span>
- <span data-ttu-id="1cd68-327">Munkaviszony megszűnésének dátuma (megszűntetéskor kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-327">Termination date (required upon termination)</span></span>
- <span data-ttu-id="1cd68-328">Felmondás oka (megszűntetéskor kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-328">Termination reason (required upon termination)</span></span>

<span data-ttu-id="1cd68-329">Az alkalmazott legfontosabb dátumai a következő adatokból vannak származtatva.</span><span class="sxs-lookup"><span data-stu-id="1cd68-329">An employee's key dates are derived by using the following information.</span></span>

| <span data-ttu-id="1cd68-330">Talent</span><span class="sxs-lookup"><span data-stu-id="1cd68-330">Talent</span></span>                | <span data-ttu-id="1cd68-331">Dayforce</span><span class="sxs-lookup"><span data-stu-id="1cd68-331">Dayforce</span></span>                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="1cd68-332">Legutóbbi felvételi dátum</span><span class="sxs-lookup"><span data-stu-id="1cd68-332">Most recent hire date</span></span> | <span data-ttu-id="1cd68-333">Foglalkoztatás kezdete az aktuális nem megszűntetett előzményrekordra</span><span class="sxs-lookup"><span data-stu-id="1cd68-333">Employment start of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="1cd68-334">Munkaviszony megszűnésének dátuma</span><span class="sxs-lookup"><span data-stu-id="1cd68-334">Termination date</span></span>      | <span data-ttu-id="1cd68-335">Foglalkoztatás befejezése az aktuális nem megszűntetett előzményrekordra</span><span class="sxs-lookup"><span data-stu-id="1cd68-335">Termination date of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="1cd68-336">Kezdő dátum</span><span class="sxs-lookup"><span data-stu-id="1cd68-336">Start date</span></span>            | <span data-ttu-id="1cd68-337">Módosított kezdési időpont, kezdődátum vagy foglalkoztatás kezdete az aktuális nem aktív előzményrekordra</span><span class="sxs-lookup"><span data-stu-id="1cd68-337">Adjusted start date, start date, or employment start of current non-active employment history record</span></span> |
| <span data-ttu-id="1cd68-338">Eredeti felvételi dátum</span><span class="sxs-lookup"><span data-stu-id="1cd68-338">Original hire date</span></span>    | <span data-ttu-id="1cd68-339">Foglalkoztatás kezdete legkorábbi foglalkoztatási előzményrekordra</span><span class="sxs-lookup"><span data-stu-id="1cd68-339">Employment start of earliest employment history record</span></span>                                               |

#### <a name="compensation"></a><span data-ttu-id="1cd68-340">Kompenzáció</span><span class="sxs-lookup"><span data-stu-id="1cd68-340">Compensation</span></span>

<span data-ttu-id="1cd68-341">Egy fix kompenzációs tervet kell társítani minden alkalmazott elsődleges pozíciójához az alkalmazási időszak alatt.</span><span class="sxs-lookup"><span data-stu-id="1cd68-341">A fixed compensation plan must be associated with every employee's primary position throughout an employment period.</span></span> <span data-ttu-id="1cd68-342">Az időszak a belépés dátumával (vagy a foglalkoztatás kezdő dátumával) kezdődik, és a munkaviszony megszűnéséig tart .</span><span class="sxs-lookup"><span data-stu-id="1cd68-342">This period starts on the date that the employee was hired (or the employment start date) and continues until termination.</span></span>

- <span data-ttu-id="1cd68-343">Érvényesség dátuma (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-343">Effective Date (required)</span></span>
- <span data-ttu-id="1cd68-344">Lejárati dátum</span><span class="sxs-lookup"><span data-stu-id="1cd68-344">Expiration date</span></span>
- <span data-ttu-id="1cd68-345">Fizetési díjalap (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-345">Pay Rate (required)</span></span>
- <span data-ttu-id="1cd68-346">Fizetési díjalapok átalakításai (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-346">Pay Rate Conversions (required)</span></span>
- <span data-ttu-id="1cd68-347">Évi egyenérték (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-347">Annual equivalent (required)</span></span>
- <span data-ttu-id="1cd68-348">Óránkénti egyenérték (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-348">Hourly equivalent (required)</span></span>

<span data-ttu-id="1cd68-349">Ha az óránkénti alkalmazottnak több beosztása van, az elsődleges beosztásához tartozó fix kompenzációja importálva lesz a Dayforce-ba, alkalmazott szintű alapdíj/-fizetés.</span><span class="sxs-lookup"><span data-stu-id="1cd68-349">If an hourly employee has multiple positions, the fixed compensation of the primary position is imported into Dayforce as the employee-level base rate/salary.</span></span> <span data-ttu-id="1cd68-350">A nem elsődleges beosztások esetén, az óránkénti díj a megfelelő pozícióba lesz mentve Dayforce-ban.</span><span class="sxs-lookup"><span data-stu-id="1cd68-350">For non-primary positions, the hourly rate is saved to the corresponding position in Dayforce.</span></span>

<span data-ttu-id="1cd68-351">Ha a fizetett alkalmazott több beosztással rendelkezik, a összesített óradíj és éves fizetés származtatva lesz az összes aktív beosztásból mint az alkalmazotti szintű alapdíj/-fizetés.</span><span class="sxs-lookup"><span data-stu-id="1cd68-351">If a salaried employee has multiple positions, the cumulative hour rate and annual salary across all active positions are derived and used as the employee-level base rate/salary.</span></span>

#### <a name="identification-numbers"></a><span data-ttu-id="1cd68-352">Azonosítószámok</span><span class="sxs-lookup"><span data-stu-id="1cd68-352">Identification numbers</span></span>

##### <a name="social-security-identifier"></a><span data-ttu-id="1cd68-353">Társadalombiztosítási azonosító</span><span class="sxs-lookup"><span data-stu-id="1cd68-353">Social Security identifier</span></span> 

<span data-ttu-id="1cd68-354">Minden alkalmazottnak kell egy elsődleges azonosítóval rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="1cd68-354">Every employee must have one primary identifier.</span></span> <span data-ttu-id="1cd68-355">Ez az azonosító legyen **TAJ-szám** azonosítótípus kell legyen.</span><span class="sxs-lookup"><span data-stu-id="1cd68-355">This identifier must be of **SSN** identification type.</span></span> <span data-ttu-id="1cd68-356">A Dayforce-ban automatikusan van származtatva az alkalmazott társadalombiztosítási azonosítójából, mely a felvételhez szükséges.</span><span class="sxs-lookup"><span data-stu-id="1cd68-356">In Dayforce, it's automatically derived as the employee's Social Security identifier that is required for hire.</span></span>

- <span data-ttu-id="1cd68-357">Elsődleges (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-357">Primary (required)</span></span>
- <span data-ttu-id="1cd68-358">Azonosító típusa = „TAJ-szám”</span><span class="sxs-lookup"><span data-stu-id="1cd68-358">Identification Type = "SSN"</span></span>
- <span data-ttu-id="1cd68-359">Kibocsátás dátuma</span><span class="sxs-lookup"><span data-stu-id="1cd68-359">Issued Date</span></span>
- <span data-ttu-id="1cd68-360">Lejárat dátuma</span><span class="sxs-lookup"><span data-stu-id="1cd68-360">Expiration Date</span></span>

<span data-ttu-id="1cd68-361">Az alkalmazottak több azonosítószámot is megadhatnak **TAJ-szám** azonosítótípushoz.</span><span class="sxs-lookup"><span data-stu-id="1cd68-361">Employees can declare multiple identification numbers of the **SSN** identification type.</span></span> <span data-ttu-id="1cd68-362">Azonban csak az **Elsődlegesként** megjelölt rekord van integrálva Dayforce-ba, függetlenül attól, hogy a szám aktív vagy lejárt.</span><span class="sxs-lookup"><span data-stu-id="1cd68-362">However, only the record that is marked as **Primary** is integrated into Dayforce, regardless of whether the number is active or expired.</span></span>

#### <a name="bank-accounts-and-disbursements"></a><span data-ttu-id="1cd68-363">Bankszámlák és kifizetések</span><span class="sxs-lookup"><span data-stu-id="1cd68-363">Bank accounts and disbursements</span></span>

<span data-ttu-id="1cd68-364">Érvényes bankszámlaadatokat meg kell adni minden olyan alkalmazotthoz, aki úgy dönt, hogy a banki átutalással kéri fizetését.</span><span class="sxs-lookup"><span data-stu-id="1cd68-364">Valid bank account information must be entered for any employee who chooses to be paid via bank account transfers.</span></span>

| <span data-ttu-id="1cd68-365">Talent</span><span class="sxs-lookup"><span data-stu-id="1cd68-365">Talent</span></span>                         | <span data-ttu-id="1cd68-366">Dayforce</span><span class="sxs-lookup"><span data-stu-id="1cd68-366">Dayforce</span></span>                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="1cd68-367">Bankszámlaszám (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-367">Bank account number (required)</span></span> |                                                                                                             |
| <span data-ttu-id="1cd68-368">SWIFT-kód (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-368">SWIFT code (required)</span></span>          | <span data-ttu-id="1cd68-369">**Bankazonosító** ez a mező Mexikóban történő bérlistafeldolgozáskor használatos.</span><span class="sxs-lookup"><span data-stu-id="1cd68-369">**Bank ID** field used when processing payroll in Mexico.</span></span>                                                             |
| <span data-ttu-id="1cd68-370">Ágazati szám (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-370">Branch number (required)</span></span>       |                                                                                                             |
| <span data-ttu-id="1cd68-371">Bankszámla típusa (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-371">Bank account type (required)</span></span>   | <span data-ttu-id="1cd68-372">**Számlatípus** ez a mező Mexikóban történő bérlistafeldolgozáskor használatos.</span><span class="sxs-lookup"><span data-stu-id="1cd68-372">**Account type** field used when processing payroll in Mexico.</span></span> <span data-ttu-id="1cd68-373">Támogatott értékek: **Folyószámla** és **Bérlista**</span><span class="sxs-lookup"><span data-stu-id="1cd68-373">Supported values include **Checking** and **Payroll**.</span></span> |

> [!NOTE]
> <span data-ttu-id="1cd68-374">Alkalmazottak, akik úgy döntenek, hogy a banki átutaláson keresztülkérik fizetésük, meg kell adniuk egy hivatkozást egy jogi személyhez tartozó egyenlegszámlához, melynek elsődleges címének Mexikóban kell lennie és egy Mexikói bank érvényes bankszámlájához van társítva.</span><span class="sxs-lookup"><span data-stu-id="1cd68-374">Employees who choose to be paid via bank account transfers must provide a link to a remainder account that is under a legal entity that has its primary address in Mexico and associated with a valid bank account from a Mexican bank.</span></span> <span data-ttu-id="1cd68-375">Minden egyéb nem egyenlegszámla figyelmen kívül lesz hagyva.</span><span class="sxs-lookup"><span data-stu-id="1cd68-375">All other non-remainder accounts are ignored.</span></span>

#### <a name="address-information"></a><span data-ttu-id="1cd68-376">Címadatok</span><span class="sxs-lookup"><span data-stu-id="1cd68-376">Address information</span></span>

<span data-ttu-id="1cd68-377">Minden alkalmazottnak kell egy elsődleges hellyel rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="1cd68-377">Every employee must have one primary location.</span></span> <span data-ttu-id="1cd68-378">A Dayforce-ban ezen hely alapján van meghatározva az alkalmazott elsődleges tartózkodási helye adózási célokból.</span><span class="sxs-lookup"><span data-stu-id="1cd68-378">In Dayforce, this location is used to determine the employee's primary residence for tax purposes.</span></span>

- <span data-ttu-id="1cd68-379">Elsődleges (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-379">Primary (required)</span></span>
- <span data-ttu-id="1cd68-380">Ország/régiót (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-380">Country/region (required)</span></span>
- <span data-ttu-id="1cd68-381">Irányítószám/postai kód (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-381">Zip/postal code (required)</span></span>
- <span data-ttu-id="1cd68-382">Utca (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-382">Street (required)</span></span>
- <span data-ttu-id="1cd68-383">Házszám (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-383">Street Number (required)</span></span>
- <span data-ttu-id="1cd68-384">Épületblokk</span><span class="sxs-lookup"><span data-stu-id="1cd68-384">Building Complement</span></span>
- <span data-ttu-id="1cd68-385">Város (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-385">City (required)</span></span>
- <span data-ttu-id="1cd68-386">Állam (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-386">State (required)</span></span>
- <span data-ttu-id="1cd68-387">Megye (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-387">County (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a><span data-ttu-id="1cd68-388">Az adatok konfigurálása bérlista létrehozásához az Egyesült Államokban és Kanadában</span><span class="sxs-lookup"><span data-stu-id="1cd68-388">Configure your data to generate payroll in United States and Canada</span></span>

<span data-ttu-id="1cd68-389">Ha a fizetést generálása alkalmazottaknak az Egyesült Államokban és Kanadában, a következő elemeket kell beállítani:</span><span class="sxs-lookup"><span data-stu-id="1cd68-389">If you're generating pay for employees in the United States and Canada, the following elements must be configured:</span></span>

- <span data-ttu-id="1cd68-390">Részlegek szükségesek beosztásokhoz.</span><span class="sxs-lookup"><span data-stu-id="1cd68-390">Departments are required on positions.</span></span>
- <span data-ttu-id="1cd68-391">Költséghelyek pénzügyi dimenziókként kell beállítani, és az alapértelmezett pénzügyi dimenzió karakterlánc első elemének kell lennie.</span><span class="sxs-lookup"><span data-stu-id="1cd68-391">Cost centers must be set as financial dimensions and must be the first element in the default financial dimension string.</span></span>

> [!NOTE] 
> <span data-ttu-id="1cd68-392">Beállíthatja a Talent szolgáltatást úgy, hogy a Beosztásokhoz kötelező legyen beállítani Részleget.</span><span class="sxs-lookup"><span data-stu-id="1cd68-392">You can configure Talent to require that Positions specify a Department.</span></span> <span data-ttu-id="1cd68-393">Ehhez kattintson a **Emberi erőforrások megosztott beosztásai > Beosztások > Részlegek szükségesek beosztásokhoz.** elemre.</span><span class="sxs-lookup"><span data-stu-id="1cd68-393">To do this, go to **Human Resources Shared Positions > Positions > Require departments on positions**.</span></span> <span data-ttu-id="1cd68-394">Azt ajánljuk, hogy ezt a beállítást tartassa be az integráció során.</span><span class="sxs-lookup"><span data-stu-id="1cd68-394">We recommend that this setting be enforced for the integration.</span></span>

### <a name="job-types"></a><span data-ttu-id="1cd68-395">Feladattípusok</span><span class="sxs-lookup"><span data-stu-id="1cd68-395">Job types</span></span>

<span data-ttu-id="1cd68-396">Beosztástípusok használatával a hasonló feladatok kategóriákba sorolhatók.</span><span class="sxs-lookup"><span data-stu-id="1cd68-396">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="1cd68-397">A beosztástípusok szükségesek az Egyesült Államokban és Kanadában a bérlisták feldolgozásához.</span><span class="sxs-lookup"><span data-stu-id="1cd68-397">Job types are required in order to process payroll in the United States and Canada.</span></span> <span data-ttu-id="1cd68-398">Beosztástípusok többek között a teljes és részmunkaidős, illetve a munkabéres és az órabéres.</span><span class="sxs-lookup"><span data-stu-id="1cd68-398">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="1cd68-399">A beosztástípusok a fizetéstípusokként vannak hozzárendelve a Dayforce-hoz, melyek jelzik, hogy a munkavállaló órás vagy bérezéses.</span><span class="sxs-lookup"><span data-stu-id="1cd68-399">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="1cd68-400">A következő feladattípusok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="1cd68-400">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="1cd68-401">Feladattípus</span><span class="sxs-lookup"><span data-stu-id="1cd68-401">Job type</span></span>   | <span data-ttu-id="1cd68-402">Leírás</span><span class="sxs-lookup"><span data-stu-id="1cd68-402">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="1cd68-403">Óránként</span><span class="sxs-lookup"><span data-stu-id="1cd68-403">Hourly</span></span>     | <span data-ttu-id="1cd68-404">Óránként</span><span class="sxs-lookup"><span data-stu-id="1cd68-404">Hourly</span></span>      |
| <span data-ttu-id="1cd68-405">Bérezéses</span><span class="sxs-lookup"><span data-stu-id="1cd68-405">Salaried</span></span>   | <span data-ttu-id="1cd68-406">Bérezéses</span><span class="sxs-lookup"><span data-stu-id="1cd68-406">Salaried</span></span>    |

### <a name="position-types"></a><span data-ttu-id="1cd68-407">Beosztási típusok</span><span class="sxs-lookup"><span data-stu-id="1cd68-407">Position types</span></span> 

<span data-ttu-id="1cd68-408">Ne használjon beosztástípusokat annak leírására, hogy a beosztás teljes munkaidős, részmunkaidős vagy más.</span><span class="sxs-lookup"><span data-stu-id="1cd68-408">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="1cd68-409">A feladattípusok a fizetésosztályokként vannak hozzárendelve a Dayforce-hoz, melyek jelzik, hogy a munkavállaló teljes- vagy részmunkaidős.</span><span class="sxs-lookup"><span data-stu-id="1cd68-409">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="1cd68-410">A következő beosztástípusok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="1cd68-410">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="1cd68-411">Beosztás típusa</span><span class="sxs-lookup"><span data-stu-id="1cd68-411">Position type</span></span>   | <span data-ttu-id="1cd68-412">Leírás</span><span class="sxs-lookup"><span data-stu-id="1cd68-412">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="1cd68-413">Teljes munkaidős</span><span class="sxs-lookup"><span data-stu-id="1cd68-413">Full-time</span></span>       | <span data-ttu-id="1cd68-414">Teljes munkaidős alkalmazott</span><span class="sxs-lookup"><span data-stu-id="1cd68-414">Full time employee</span></span> |
| <span data-ttu-id="1cd68-415">Részmunkaidős</span><span class="sxs-lookup"><span data-stu-id="1cd68-415">Part-time</span></span>       | <span data-ttu-id="1cd68-416">Részmunkaidős alkalmazott</span><span class="sxs-lookup"><span data-stu-id="1cd68-416">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="1cd68-417">Okkódok</span><span class="sxs-lookup"><span data-stu-id="1cd68-417">Reason codes</span></span>

<span data-ttu-id="1cd68-418">Az alkalmazottak állapotával kapcsolatos okkódok tájékoztatnak.</span><span class="sxs-lookup"><span data-stu-id="1cd68-418">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="1cd68-419">Okkódok a Dayforce-hoz állapot okaként vannak hozzárendelve, melyek jelzik egy alkalmazott beosztásában vagy alkalmazotti státuszában bekövetkezett változások okát.</span><span class="sxs-lookup"><span data-stu-id="1cd68-419">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="1cd68-420">A következő okkódok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="1cd68-420">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="1cd68-421">Okkód</span><span class="sxs-lookup"><span data-stu-id="1cd68-421">Reason code</span></span>    | <span data-ttu-id="1cd68-422">Leírás</span><span class="sxs-lookup"><span data-stu-id="1cd68-422">Description</span></span>      | <span data-ttu-id="1cd68-423">Alkalmazandó forgatókönyvek</span><span class="sxs-lookup"><span data-stu-id="1cd68-423">Applicable scenarios</span></span> |
|----------------|------------------|----------------------|
| <span data-ttu-id="1cd68-424">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="1cd68-424">RESIGNATION</span></span>    | <span data-ttu-id="1cd68-425">Felmondás</span><span class="sxs-lookup"><span data-stu-id="1cd68-425">Resignation</span></span>      | <span data-ttu-id="1cd68-426">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="1cd68-426">Terminate worker</span></span>     |
| <span data-ttu-id="1cd68-427">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="1cd68-427">TERMINATION</span></span>    | <span data-ttu-id="1cd68-428">Befejezés</span><span class="sxs-lookup"><span data-stu-id="1cd68-428">Termination</span></span>      | <span data-ttu-id="1cd68-429">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="1cd68-429">Terminate worker</span></span>     |
| <span data-ttu-id="1cd68-430">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="1cd68-430">RETIREMENT</span></span>     | <span data-ttu-id="1cd68-431">Megszüntetés</span><span class="sxs-lookup"><span data-stu-id="1cd68-431">Retirement</span></span>       | <span data-ttu-id="1cd68-432">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="1cd68-432">Terminate worker</span></span>     |
| <span data-ttu-id="1cd68-433">EGYÉB</span><span class="sxs-lookup"><span data-stu-id="1cd68-433">OTHER</span></span>          | <span data-ttu-id="1cd68-434">Egyéb okok</span><span class="sxs-lookup"><span data-stu-id="1cd68-434">Other Reasons</span></span>    | <span data-ttu-id="1cd68-435">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="1cd68-435">Terminate worker</span></span>     |
| <span data-ttu-id="1cd68-436">DEATH</span><span class="sxs-lookup"><span data-stu-id="1cd68-436">DEATH</span></span>          | <span data-ttu-id="1cd68-437">Elhalálozás</span><span class="sxs-lookup"><span data-stu-id="1cd68-437">Death</span></span>            | <span data-ttu-id="1cd68-438">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="1cd68-438">Terminate worker</span></span>     |
| <span data-ttu-id="1cd68-439">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="1cd68-439">LEAVEOFABSENCE</span></span> | <span data-ttu-id="1cd68-440">Szabadság</span><span class="sxs-lookup"><span data-stu-id="1cd68-440">Leave of Absence</span></span> | <span data-ttu-id="1cd68-441">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="1cd68-441">Terminate worker</span></span>     |
| <span data-ttu-id="1cd68-442">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="1cd68-442">CONTRACTEND</span></span>    | <span data-ttu-id="1cd68-443">Szerződés vége</span><span class="sxs-lookup"><span data-stu-id="1cd68-443">End of Contract</span></span>  | <span data-ttu-id="1cd68-444">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="1cd68-444">Terminate worker</span></span>     |
| <span data-ttu-id="1cd68-445">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="1cd68-445">SALARYCHANGE</span></span>   | <span data-ttu-id="1cd68-446">Munkabér módosítása</span><span class="sxs-lookup"><span data-stu-id="1cd68-446">Change of Salary</span></span> | <span data-ttu-id="1cd68-447">Kompenzáció</span><span class="sxs-lookup"><span data-stu-id="1cd68-447">Compensation</span></span>         |

### <a name="marital-status"></a><span data-ttu-id="1cd68-448">Családi állapot</span><span class="sxs-lookup"><span data-stu-id="1cd68-448">Marital status</span></span>

<span data-ttu-id="1cd68-449">Családi állapot értékei Dayforce-hoz vannak rendelve és konvertálva szükség esetén az elfogadható értékekre az integráció során.</span><span class="sxs-lookup"><span data-stu-id="1cd68-449">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="1cd68-450">Az alábbi táblázat bemutatja, hogy családi állapot értékek hogyan vannak leképezve a Dayforce -ban.</span><span class="sxs-lookup"><span data-stu-id="1cd68-450">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="1cd68-451">Talent</span><span class="sxs-lookup"><span data-stu-id="1cd68-451">Talent</span></span>                 | <span data-ttu-id="1cd68-452">Dayforce</span><span class="sxs-lookup"><span data-stu-id="1cd68-452">Dayforce</span></span>             |
|------------------------|----------------------|
| <span data-ttu-id="1cd68-453">Házas</span><span class="sxs-lookup"><span data-stu-id="1cd68-453">Married</span></span>                | <span data-ttu-id="1cd68-454">Házas</span><span class="sxs-lookup"><span data-stu-id="1cd68-454">Married</span></span>              |
| <span data-ttu-id="1cd68-455">Egy</span><span class="sxs-lookup"><span data-stu-id="1cd68-455">Single</span></span>                 | <span data-ttu-id="1cd68-456">Egy</span><span class="sxs-lookup"><span data-stu-id="1cd68-456">Single</span></span>               |
| <span data-ttu-id="1cd68-457">Özvegy</span><span class="sxs-lookup"><span data-stu-id="1cd68-457">Widowed</span></span>                | <span data-ttu-id="1cd68-458">Özvegy</span><span class="sxs-lookup"><span data-stu-id="1cd68-458">Widowed</span></span>              |
| <span data-ttu-id="1cd68-459">Elvált</span><span class="sxs-lookup"><span data-stu-id="1cd68-459">Divorced</span></span>               | <span data-ttu-id="1cd68-460">Elvált</span><span class="sxs-lookup"><span data-stu-id="1cd68-460">Divorced</span></span>             |
| <span data-ttu-id="1cd68-461">Bejegyzett élettársi kapcsolat</span><span class="sxs-lookup"><span data-stu-id="1cd68-461">Registered Partnership</span></span> | <span data-ttu-id="1cd68-462">Élettársi viszony</span><span class="sxs-lookup"><span data-stu-id="1cd68-462">Domestic Partnership</span></span> |
| <span data-ttu-id="1cd68-463">Nincs</span><span class="sxs-lookup"><span data-stu-id="1cd68-463">None</span></span>                   | <span data-ttu-id="1cd68-464">Nincs</span><span class="sxs-lookup"><span data-stu-id="1cd68-464">None</span></span>                 |
| <span data-ttu-id="1cd68-465">Együttélés</span><span class="sxs-lookup"><span data-stu-id="1cd68-465">Cohabiting</span></span>             | <span data-ttu-id="1cd68-466">Együttélés</span><span class="sxs-lookup"><span data-stu-id="1cd68-466">Cohabiting</span></span>           |

### <a name="gender"></a><span data-ttu-id="1cd68-467">Nem</span><span class="sxs-lookup"><span data-stu-id="1cd68-467">Gender</span></span>

<span data-ttu-id="1cd68-468">A nemek a Dayforce-hoz vannak rendelve és konvertálva szükség esetén az elfogadható értékekre az integráció során.</span><span class="sxs-lookup"><span data-stu-id="1cd68-468">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="1cd68-469">Az alábbi táblázat bemutatja, hogy a nemek hogyan vannak leképezve a Dayforce-ban.</span><span class="sxs-lookup"><span data-stu-id="1cd68-469">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="1cd68-470">Talent</span><span class="sxs-lookup"><span data-stu-id="1cd68-470">Talent</span></span>       | <span data-ttu-id="1cd68-471">Dayforce</span><span class="sxs-lookup"><span data-stu-id="1cd68-471">Dayforce</span></span>        |
|--------------|-----------------|
| <span data-ttu-id="1cd68-472">Férfi</span><span class="sxs-lookup"><span data-stu-id="1cd68-472">Male</span></span>         | <span data-ttu-id="1cd68-473">Férfi</span><span class="sxs-lookup"><span data-stu-id="1cd68-473">Male</span></span>            |
| <span data-ttu-id="1cd68-474">Nő</span><span class="sxs-lookup"><span data-stu-id="1cd68-474">Female</span></span>       | <span data-ttu-id="1cd68-475">Nő</span><span class="sxs-lookup"><span data-stu-id="1cd68-475">Female</span></span>          |
| <span data-ttu-id="1cd68-476">Nem meghatározott</span><span class="sxs-lookup"><span data-stu-id="1cd68-476">Non-specific</span></span> | <span data-ttu-id="1cd68-477">*Nem támogatott*</span><span class="sxs-lookup"><span data-stu-id="1cd68-477">*Not supported*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="1cd68-478">Bevételkódok</span><span class="sxs-lookup"><span data-stu-id="1cd68-478">Earning codes</span></span>

<span data-ttu-id="1cd68-479">A bevételkódok egyedi módon azonosítják a dolgozók által kapott fizetéstípusokat.</span><span class="sxs-lookup"><span data-stu-id="1cd68-479">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="1cd68-480">A kódoknak különböző paramétereket fednek le, amelyek a bevételekhez kapcsolódnak, például könyvelési szabályok, jelentési követelmények és bruttósítási lehetőségek.</span><span class="sxs-lookup"><span data-stu-id="1cd68-480">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="1cd68-481">Ha egy nem támogatott gyakoriság van használatban, a **Minden fizetés** gyakorisága van alapértelmezés szerint használva a kiszámításhoz.</span><span class="sxs-lookup"><span data-stu-id="1cd68-481">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="1cd68-482">Támogatott gyakoriságok</span><span class="sxs-lookup"><span data-stu-id="1cd68-482">Supported frequencies</span></span>

- <span data-ttu-id="1cd68-483">Összes</span><span class="sxs-lookup"><span data-stu-id="1cd68-483">All</span></span>
- <span data-ttu-id="1cd68-484">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="1cd68-484">EVERYPAY</span></span>
- <span data-ttu-id="1cd68-485">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="1cd68-485">EACHPAYPERIOD</span></span>
- <span data-ttu-id="1cd68-486">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="1cd68-486">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="1cd68-487">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="1cd68-487">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="1cd68-488">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="1cd68-488">1OFMTH</span></span>
- <span data-ttu-id="1cd68-489">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="1cd68-489">LASTOFMTH</span></span>
- <span data-ttu-id="1cd68-490">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="1cd68-490">2OFMTH</span></span>
- <span data-ttu-id="1cd68-491">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="1cd68-491">3OFMTH</span></span>
- <span data-ttu-id="1cd68-492">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="1cd68-492">4OFMTH</span></span>
- <span data-ttu-id="1cd68-493">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="1cd68-493">5OFMTH</span></span>
- <span data-ttu-id="1cd68-494">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="1cd68-494">1N2OFMTH</span></span>
- <span data-ttu-id="1cd68-495">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="1cd68-495">3N4OFMTH</span></span>
- <span data-ttu-id="1cd68-496">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="1cd68-496">1N3OFMTH</span></span>
- <span data-ttu-id="1cd68-497">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="1cd68-497">1N4OFMTH</span></span>
- <span data-ttu-id="1cd68-498">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="1cd68-498">2N3OFMTH</span></span>
- <span data-ttu-id="1cd68-499">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="1cd68-499">2N4OFMTH</span></span>
- <span data-ttu-id="1cd68-500">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="1cd68-500">1N2N3OFMTH</span></span>
- <span data-ttu-id="1cd68-501">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="1cd68-501">1N2N4OFMTH</span></span>
- <span data-ttu-id="1cd68-502">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="1cd68-502">1N3N4OFMTH</span></span>
- <span data-ttu-id="1cd68-503">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="1cd68-503">2N3N4OFMTH</span></span>
- <span data-ttu-id="1cd68-504">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="1cd68-504">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="1cd68-505">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="1cd68-505">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="1cd68-506">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="1cd68-506">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="1cd68-507">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="1cd68-507">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="1cd68-508">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="1cd68-508">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="1cd68-509">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="1cd68-509">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="1cd68-510">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="1cd68-510">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="1cd68-511">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="1cd68-511">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="1cd68-512">Címek</span><span class="sxs-lookup"><span data-stu-id="1cd68-512">Addresses</span></span>

<span data-ttu-id="1cd68-513">Az adott ország vagy régió, állam és megye (település) kódok specifikus formátumokat követelnek, hogy Dayforce és az országos és regionális szolgáltatók felismerjék azokat.</span><span class="sxs-lookup"><span data-stu-id="1cd68-513">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="1cd68-514">Annak ellenére, hogy a városok formátuma rugalmas, minden városnak társítva kell lennie egy államhoz.</span><span class="sxs-lookup"><span data-stu-id="1cd68-514">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="1cd68-515">Talent</span><span class="sxs-lookup"><span data-stu-id="1cd68-515">Talent</span></span>          | <span data-ttu-id="1cd68-516">Dayforce</span><span class="sxs-lookup"><span data-stu-id="1cd68-516">Dayforce</span></span>              |
|-----------------|-----------------------|
| <span data-ttu-id="1cd68-517">Ország/régió</span><span class="sxs-lookup"><span data-stu-id="1cd68-517">Country/Region</span></span>  | <span data-ttu-id="1cd68-518">Országkód</span><span class="sxs-lookup"><span data-stu-id="1cd68-518">Country Code</span></span>          |
| <span data-ttu-id="1cd68-519">Irányítószám / postai kód</span><span class="sxs-lookup"><span data-stu-id="1cd68-519">Zip/Postal Code</span></span> | <span data-ttu-id="1cd68-520">Irányítószám</span><span class="sxs-lookup"><span data-stu-id="1cd68-520">Postal Code</span></span>           |
| <span data-ttu-id="1cd68-521">Állami</span><span class="sxs-lookup"><span data-stu-id="1cd68-521">State</span></span>           | <span data-ttu-id="1cd68-522">Államkód</span><span class="sxs-lookup"><span data-stu-id="1cd68-522">State Code</span></span>            |
| <span data-ttu-id="1cd68-523">Város</span><span class="sxs-lookup"><span data-stu-id="1cd68-523">City</span></span>            | <span data-ttu-id="1cd68-524">Város</span><span class="sxs-lookup"><span data-stu-id="1cd68-524">City</span></span>                  |
| <span data-ttu-id="1cd68-525">Megye</span><span class="sxs-lookup"><span data-stu-id="1cd68-525">County</span></span>          | <span data-ttu-id="1cd68-526">Megye (Helyhatóság)</span><span class="sxs-lookup"><span data-stu-id="1cd68-526">County (Municipality)</span></span> |
| <span data-ttu-id="1cd68-527">Utca</span><span class="sxs-lookup"><span data-stu-id="1cd68-527">Street</span></span>          | <span data-ttu-id="1cd68-528">Cím 1. sora</span><span class="sxs-lookup"><span data-stu-id="1cd68-528">Address Line 1</span></span>        |

### <a name="tax-regions"></a><span data-ttu-id="1cd68-529">Adórégiók</span><span class="sxs-lookup"><span data-stu-id="1cd68-529">Tax regions</span></span>

<span data-ttu-id="1cd68-530">Az adórégiók a megfelelő adó megállapítására szolgálnak, amelyet a bérlista létrehozásakor kell alkalmazni.</span><span class="sxs-lookup"><span data-stu-id="1cd68-530">Tax regions are used to determine the appropriate tax that should be applied during payroll generation.</span></span> <span data-ttu-id="1cd68-531">Az adórégiók helycímként vannak a Dayforce-hoz rendelve.</span><span class="sxs-lookup"><span data-stu-id="1cd68-531">Tax regions are mapped to Dayforce as location addresses.</span></span> <span data-ttu-id="1cd68-532">Az alapértelmezett adórégiót a dolgozó aktív beosztásával kell társítani.</span><span class="sxs-lookup"><span data-stu-id="1cd68-532">The default tax region must be associated with the worker's active position.</span></span> 

- <span data-ttu-id="1cd68-533">Adórégió (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-533">Tax region (required)</span></span>
- <span data-ttu-id="1cd68-534">Ország/régió (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-534">Country/Region (required)</span></span>
- <span data-ttu-id="1cd68-535">Állam (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-535">State (required)</span></span>
- <span data-ttu-id="1cd68-536">Megye</span><span class="sxs-lookup"><span data-stu-id="1cd68-536">County</span></span> 
- <span data-ttu-id="1cd68-537">Város (kötelező)</span><span class="sxs-lookup"><span data-stu-id="1cd68-537">City (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a><span data-ttu-id="1cd68-538">Adatok konfigurálása bérlista létrehozásához Mexikóban</span><span class="sxs-lookup"><span data-stu-id="1cd68-538">Configure your data to generate payroll in Mexico</span></span>

<span data-ttu-id="1cd68-539">Ha a fizetést generál alkalmazottaknak Mexikóban, a következő elemeket kell beállítani:</span><span class="sxs-lookup"><span data-stu-id="1cd68-539">If you're generating pay for employees in Mexico, the following elements must be configured:</span></span>

- <span data-ttu-id="1cd68-540">Részlegek szükségesek beosztásokhoz.</span><span class="sxs-lookup"><span data-stu-id="1cd68-540">Departments are required on positions.</span></span>
- <span data-ttu-id="1cd68-541">Költséghelyek pénzügyi dimenziókként kell beállítani, és az Alapértelmezett pénzügyi dimenzió karakterlánc első elemének kell lennie.</span><span class="sxs-lookup"><span data-stu-id="1cd68-541">Cost centers must be set as financial dimensions and must be the first element in the Default Financial Dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="1cd68-542">Beosztástípusok</span><span class="sxs-lookup"><span data-stu-id="1cd68-542">Job types</span></span>

<span data-ttu-id="1cd68-543">Beosztástípusok használatával a hasonló feladatok kategóriákba sorolhatók.</span><span class="sxs-lookup"><span data-stu-id="1cd68-543">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="1cd68-544">Mexikóban a Bérlista feldolgozásához feladattípusok szükségesek.</span><span class="sxs-lookup"><span data-stu-id="1cd68-544">Job types are required in order to process payroll in Mexico.</span></span> <span data-ttu-id="1cd68-545">Beosztástípusok többek között a teljes és részmunkaidős, illetve a munkabéres és az órabéres.</span><span class="sxs-lookup"><span data-stu-id="1cd68-545">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="1cd68-546">A beosztástípusok a fizetéstípusokként vannak hozzárendelve a Dayforce-hoz, melyek jelzik, hogy a munkavállaló órás vagy bérezéses.</span><span class="sxs-lookup"><span data-stu-id="1cd68-546">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="1cd68-547">A következő feladattípusok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="1cd68-547">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="1cd68-548">Feladattípus</span><span class="sxs-lookup"><span data-stu-id="1cd68-548">Job type</span></span>   | <span data-ttu-id="1cd68-549">Leírás</span><span class="sxs-lookup"><span data-stu-id="1cd68-549">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="1cd68-550">Óránként</span><span class="sxs-lookup"><span data-stu-id="1cd68-550">Hourly</span></span>     | <span data-ttu-id="1cd68-551">MX Órabér</span><span class="sxs-lookup"><span data-stu-id="1cd68-551">MX Hourly</span></span>   |
| <span data-ttu-id="1cd68-552">Bérezéses</span><span class="sxs-lookup"><span data-stu-id="1cd68-552">Salaried</span></span>   | <span data-ttu-id="1cd68-553">MX Bérezéses</span><span class="sxs-lookup"><span data-stu-id="1cd68-553">MX Salaried</span></span> |

### <a name="position-types"></a><span data-ttu-id="1cd68-554">Beosztási típusok</span><span class="sxs-lookup"><span data-stu-id="1cd68-554">Position types</span></span> 

<span data-ttu-id="1cd68-555">Ne használjon beosztástípusokat annak leírására, hogy a beosztás teljes munkaidős, részmunkaidős vagy más.</span><span class="sxs-lookup"><span data-stu-id="1cd68-555">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="1cd68-556">A feladattípusok a fizetésosztályokként vannak hozzárendelve a Dayforce-hoz, melyek jelzik, hogy a munkavállaló teljes- vagy részmunkaidős.</span><span class="sxs-lookup"><span data-stu-id="1cd68-556">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="1cd68-557">A következő beosztástípusok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="1cd68-557">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="1cd68-558">Beosztás típusa</span><span class="sxs-lookup"><span data-stu-id="1cd68-558">Position type</span></span>   | <span data-ttu-id="1cd68-559">Leírás</span><span class="sxs-lookup"><span data-stu-id="1cd68-559">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="1cd68-560">Teljes munkaidős</span><span class="sxs-lookup"><span data-stu-id="1cd68-560">Full-time</span></span>       | <span data-ttu-id="1cd68-561">Teljes munkaidős alkalmazott</span><span class="sxs-lookup"><span data-stu-id="1cd68-561">Full time employee</span></span> |
| <span data-ttu-id="1cd68-562">Részmunkaidős</span><span class="sxs-lookup"><span data-stu-id="1cd68-562">Part-time</span></span>       | <span data-ttu-id="1cd68-563">Részmunkaidős alkalmazott</span><span class="sxs-lookup"><span data-stu-id="1cd68-563">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="1cd68-564">Okkódok</span><span class="sxs-lookup"><span data-stu-id="1cd68-564">Reason codes</span></span>

<span data-ttu-id="1cd68-565">Az alkalmazottak állapotával kapcsolatos okkódok tájékoztatnak.</span><span class="sxs-lookup"><span data-stu-id="1cd68-565">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="1cd68-566">Okkódok a Dayforce-hoz állapot okaként vannak hozzárendelve, melyek jelzik egy alkalmazott beosztásában vagy alkalmazotti státuszában bekövetkezett változások okát.</span><span class="sxs-lookup"><span data-stu-id="1cd68-566">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="1cd68-567">A következő okkódok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="1cd68-567">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="1cd68-568">Okkód</span><span class="sxs-lookup"><span data-stu-id="1cd68-568">Reason code</span></span>            | <span data-ttu-id="1cd68-569">Leírás</span><span class="sxs-lookup"><span data-stu-id="1cd68-569">Description</span></span>                    | <span data-ttu-id="1cd68-570">Alkalmazandó forgatókönyvek</span><span class="sxs-lookup"><span data-stu-id="1cd68-570">Applicable scenarios</span></span> |
|------------------------|--------------------------------|----------------------|
| <span data-ttu-id="1cd68-571">DEPARTUREBEFOREPAYMENT</span><span class="sxs-lookup"><span data-stu-id="1cd68-571">DEPARTUREBEFOREPAYMENT</span></span> | <span data-ttu-id="1cd68-572">Indulás első bérlista előtt</span><span class="sxs-lookup"><span data-stu-id="1cd68-572">Departure before first payroll</span></span> | <span data-ttu-id="1cd68-573">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="1cd68-573">Terminate worker</span></span>     |
| <span data-ttu-id="1cd68-574">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="1cd68-574">RESIGNATION</span></span>            | <span data-ttu-id="1cd68-575">Felmondás</span><span class="sxs-lookup"><span data-stu-id="1cd68-575">Resignation</span></span>                    | <span data-ttu-id="1cd68-576">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="1cd68-576">Terminate worker</span></span>     |
| <span data-ttu-id="1cd68-577">PENSION</span><span class="sxs-lookup"><span data-stu-id="1cd68-577">PENSION</span></span>                | <span data-ttu-id="1cd68-578">Nyugdíj</span><span class="sxs-lookup"><span data-stu-id="1cd68-578">Pension</span></span>                        | <span data-ttu-id="1cd68-579">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="1cd68-579">Terminate worker</span></span>     |
| <span data-ttu-id="1cd68-580">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="1cd68-580">TERMINATION</span></span>            | <span data-ttu-id="1cd68-581">Befejezés</span><span class="sxs-lookup"><span data-stu-id="1cd68-581">Termination</span></span>                    | <span data-ttu-id="1cd68-582">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="1cd68-582">Terminate worker</span></span>     |
| <span data-ttu-id="1cd68-583">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="1cd68-583">RETIREMENT</span></span>             | <span data-ttu-id="1cd68-584">Megszüntetés</span><span class="sxs-lookup"><span data-stu-id="1cd68-584">Retirement</span></span>                     | <span data-ttu-id="1cd68-585">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="1cd68-585">Terminate worker</span></span>     |
| <span data-ttu-id="1cd68-586">ABSENTEE</span><span class="sxs-lookup"><span data-stu-id="1cd68-586">ABSENTEE</span></span>               | <span data-ttu-id="1cd68-587">Távollevő</span><span class="sxs-lookup"><span data-stu-id="1cd68-587">Absentee</span></span>                       | <span data-ttu-id="1cd68-588">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="1cd68-588">Terminate worker</span></span>     |
| <span data-ttu-id="1cd68-589">EGYÉB</span><span class="sxs-lookup"><span data-stu-id="1cd68-589">OTHER</span></span>                  | <span data-ttu-id="1cd68-590">Egyéb okok</span><span class="sxs-lookup"><span data-stu-id="1cd68-590">Other Reasons</span></span>                  | <span data-ttu-id="1cd68-591">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="1cd68-591">Terminate worker</span></span>     |
| <span data-ttu-id="1cd68-592">CLOSURE</span><span class="sxs-lookup"><span data-stu-id="1cd68-592">CLOSURE</span></span>                | <span data-ttu-id="1cd68-593">Üzletzárás</span><span class="sxs-lookup"><span data-stu-id="1cd68-593">Business Closure</span></span>               | <span data-ttu-id="1cd68-594">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="1cd68-594">Terminate worker</span></span>     |
| <span data-ttu-id="1cd68-595">DEATH</span><span class="sxs-lookup"><span data-stu-id="1cd68-595">DEATH</span></span>                  | <span data-ttu-id="1cd68-596">Elhalálozás</span><span class="sxs-lookup"><span data-stu-id="1cd68-596">Death</span></span>                          | <span data-ttu-id="1cd68-597">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="1cd68-597">Terminate worker</span></span>     |
| <span data-ttu-id="1cd68-598">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="1cd68-598">LEAVEOFABSENCE</span></span>         | <span data-ttu-id="1cd68-599">Szabadság</span><span class="sxs-lookup"><span data-stu-id="1cd68-599">Leave of Absence</span></span>               | <span data-ttu-id="1cd68-600">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="1cd68-600">Terminate worker</span></span>     |
| <span data-ttu-id="1cd68-601">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="1cd68-601">CONTRACTEND</span></span>            | <span data-ttu-id="1cd68-602">Szerződés vége</span><span class="sxs-lookup"><span data-stu-id="1cd68-602">End of Contract</span></span>                | <span data-ttu-id="1cd68-603">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="1cd68-603">Terminate worker</span></span>     |
| <span data-ttu-id="1cd68-604">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="1cd68-604">SALARYCHANGE</span></span>           | <span data-ttu-id="1cd68-605">Munkabér módosítása</span><span class="sxs-lookup"><span data-stu-id="1cd68-605">Change of Salary</span></span>               | <span data-ttu-id="1cd68-606">Kompenzáció</span><span class="sxs-lookup"><span data-stu-id="1cd68-606">Compensation</span></span>         |

### <a name="terms-of-employment"></a><span data-ttu-id="1cd68-607">Foglalkoztatási feltételek</span><span class="sxs-lookup"><span data-stu-id="1cd68-607">Terms of employment</span></span>

<span data-ttu-id="1cd68-608">A Foglalkoztatási feltételek foglalkoztatási feltételkategóriák létrehozására használatosak.</span><span class="sxs-lookup"><span data-stu-id="1cd68-608">Terms of employment are used to create categories of employment terms.</span></span> <span data-ttu-id="1cd68-609">A feltételek alkalmazási mutató értékekként vannak a Dayforce-hoz rendelve.</span><span class="sxs-lookup"><span data-stu-id="1cd68-609">The terms are mapped to Dayforce as employment indicator values.</span></span>

<span data-ttu-id="1cd68-610">A következő alkalmazási feltételek és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="1cd68-610">The following terms of employment and descriptions are required.</span></span>

| <span data-ttu-id="1cd68-611">Foglalkoztatási feltételek</span><span class="sxs-lookup"><span data-stu-id="1cd68-611">Terms of employment</span></span>   | <span data-ttu-id="1cd68-612">Leírás</span><span class="sxs-lookup"><span data-stu-id="1cd68-612">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="1cd68-613">Szabályos</span><span class="sxs-lookup"><span data-stu-id="1cd68-613">Regular</span></span>               | <span data-ttu-id="1cd68-614">Szabályos</span><span class="sxs-lookup"><span data-stu-id="1cd68-614">Regular</span></span>     |
| <span data-ttu-id="1cd68-615">Közvetlen</span><span class="sxs-lookup"><span data-stu-id="1cd68-615">Direct</span></span>                | <span data-ttu-id="1cd68-616">Közvetlen</span><span class="sxs-lookup"><span data-stu-id="1cd68-616">Direct</span></span>      |
| <span data-ttu-id="1cd68-617">Szakmai gyakorlat</span><span class="sxs-lookup"><span data-stu-id="1cd68-617">Internship</span></span>            | <span data-ttu-id="1cd68-618">Szakmai gyakorlat</span><span class="sxs-lookup"><span data-stu-id="1cd68-618">Internship</span></span>  |
| <span data-ttu-id="1cd68-619">Állandó</span><span class="sxs-lookup"><span data-stu-id="1cd68-619">Permanent</span></span>             | <span data-ttu-id="1cd68-620">Állandó</span><span class="sxs-lookup"><span data-stu-id="1cd68-620">Permanent</span></span>   |

### <a name="marital-status"></a><span data-ttu-id="1cd68-621">Családi állapot</span><span class="sxs-lookup"><span data-stu-id="1cd68-621">Marital status</span></span>

<span data-ttu-id="1cd68-622">Családi állapot értékei Dayforce-hoz vannak rendelve és konvertálva szükség esetén az elfogadható értékekre az integráció során.</span><span class="sxs-lookup"><span data-stu-id="1cd68-622">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="1cd68-623">Az alábbi táblázat bemutatja, hogy családi állapot értékek hogyan vannak leképezve a Dayforce -ban.</span><span class="sxs-lookup"><span data-stu-id="1cd68-623">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="1cd68-624">Talent</span><span class="sxs-lookup"><span data-stu-id="1cd68-624">Talent</span></span>                 | <span data-ttu-id="1cd68-625">Dayforce</span><span class="sxs-lookup"><span data-stu-id="1cd68-625">Dayforce</span></span>                  |
|------------------------|---------------------------|
| <span data-ttu-id="1cd68-626">Házas</span><span class="sxs-lookup"><span data-stu-id="1cd68-626">Married</span></span>                | <span data-ttu-id="1cd68-627">Házas</span><span class="sxs-lookup"><span data-stu-id="1cd68-627">Married</span></span>                   |
| <span data-ttu-id="1cd68-628">Egy</span><span class="sxs-lookup"><span data-stu-id="1cd68-628">Single</span></span>                 | <span data-ttu-id="1cd68-629">Egy</span><span class="sxs-lookup"><span data-stu-id="1cd68-629">Single</span></span>                    |
| <span data-ttu-id="1cd68-630">Özvegy</span><span class="sxs-lookup"><span data-stu-id="1cd68-630">Widowed</span></span>                | <span data-ttu-id="1cd68-631">Özvegy</span><span class="sxs-lookup"><span data-stu-id="1cd68-631">Widowed</span></span>                   |
| <span data-ttu-id="1cd68-632">Elvált</span><span class="sxs-lookup"><span data-stu-id="1cd68-632">Divorced</span></span>               | <span data-ttu-id="1cd68-633">Elvált</span><span class="sxs-lookup"><span data-stu-id="1cd68-633">Divorced</span></span>                  |
| <span data-ttu-id="1cd68-634">Bejegyzett élettársi kapcsolat</span><span class="sxs-lookup"><span data-stu-id="1cd68-634">Registered Partnership</span></span> | <span data-ttu-id="1cd68-635">Élettársi viszony</span><span class="sxs-lookup"><span data-stu-id="1cd68-635">Domestic Partnership</span></span>      |
| <span data-ttu-id="1cd68-636">Nincs</span><span class="sxs-lookup"><span data-stu-id="1cd68-636">None</span></span>                   | <span data-ttu-id="1cd68-637">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="1cd68-637">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="1cd68-638">Együttélés</span><span class="sxs-lookup"><span data-stu-id="1cd68-638">Cohabiting</span></span>             | <span data-ttu-id="1cd68-639">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="1cd68-639">*Not supported by Mexico*</span></span> |

### <a name="gender"></a><span data-ttu-id="1cd68-640">Nem</span><span class="sxs-lookup"><span data-stu-id="1cd68-640">Gender</span></span>

<span data-ttu-id="1cd68-641">A nemek a Dayforce-hoz vannak rendelve és konvertálva szükség esetén az elfogadható értékekre az integráció során.</span><span class="sxs-lookup"><span data-stu-id="1cd68-641">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="1cd68-642">Az alábbi táblázat bemutatja, hogy a nemek hogyan vannak leképezve a Dayforce-ban.</span><span class="sxs-lookup"><span data-stu-id="1cd68-642">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="1cd68-643">Talent</span><span class="sxs-lookup"><span data-stu-id="1cd68-643">Talent</span></span>       | <span data-ttu-id="1cd68-644">Dayforce</span><span class="sxs-lookup"><span data-stu-id="1cd68-644">Dayforce</span></span>                  |
|--------------|---------------------------|
| <span data-ttu-id="1cd68-645">Férfi</span><span class="sxs-lookup"><span data-stu-id="1cd68-645">Male</span></span>         | <span data-ttu-id="1cd68-646">Férfi</span><span class="sxs-lookup"><span data-stu-id="1cd68-646">Male</span></span>                      |
| <span data-ttu-id="1cd68-647">Nő</span><span class="sxs-lookup"><span data-stu-id="1cd68-647">Female</span></span>       | <span data-ttu-id="1cd68-648">Nő</span><span class="sxs-lookup"><span data-stu-id="1cd68-648">Female</span></span>                    |
| <span data-ttu-id="1cd68-649">Nem meghatározott</span><span class="sxs-lookup"><span data-stu-id="1cd68-649">Non-specific</span></span> | <span data-ttu-id="1cd68-650">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="1cd68-650">*Not supported by Mexico*</span></span> |

### <a name="payment-method"></a><span data-ttu-id="1cd68-651">Kifizetési mód</span><span class="sxs-lookup"><span data-stu-id="1cd68-651">Payment method</span></span>

<span data-ttu-id="1cd68-652">A Fizetési módok adják meg az alkalmazott és a vállalat számára az alkalmazott kifizetésének módja leírásának lehetőségét.</span><span class="sxs-lookup"><span data-stu-id="1cd68-652">Payment methods give the employee and the company a way to describe how employees will be paid.</span></span> <span data-ttu-id="1cd68-653">A Fizetési módok a Dayforce-hoz vannak rendelve és konvertálva szükség esetén az elfogadható értékekre az integráció során.</span><span class="sxs-lookup"><span data-stu-id="1cd68-653">Payment methods are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="1cd68-654">Az alábbi táblázat bemutatja, hogy a fizetés módok hogyan vannak leképezve a Dayforce-ban.</span><span class="sxs-lookup"><span data-stu-id="1cd68-654">The following table shows how payment methods are mapped to Dayforce.</span></span>

| <span data-ttu-id="1cd68-655">Talent</span><span class="sxs-lookup"><span data-stu-id="1cd68-655">Talent</span></span>             | <span data-ttu-id="1cd68-656">Dayforce</span><span class="sxs-lookup"><span data-stu-id="1cd68-656">Dayforce</span></span>                  |
|--------------------|---------------------------|
| <span data-ttu-id="1cd68-657">Készpénz</span><span class="sxs-lookup"><span data-stu-id="1cd68-657">Cash</span></span>               | <span data-ttu-id="1cd68-658">Készpénz</span><span class="sxs-lookup"><span data-stu-id="1cd68-658">Cash</span></span>                      |
| <span data-ttu-id="1cd68-659">Elektronikus fizetés</span><span class="sxs-lookup"><span data-stu-id="1cd68-659">Electronic Payment</span></span> | <span data-ttu-id="1cd68-660">Átvitel</span><span class="sxs-lookup"><span data-stu-id="1cd68-660">Transfer</span></span>                  |
| <span data-ttu-id="1cd68-661">Csekkes</span><span class="sxs-lookup"><span data-stu-id="1cd68-661">Check</span></span>              | <span data-ttu-id="1cd68-662">Csekk</span><span class="sxs-lookup"><span data-stu-id="1cd68-662">Cheque</span></span>                    |
| <span data-ttu-id="1cd68-663">Váltó</span><span class="sxs-lookup"><span data-stu-id="1cd68-663">Bank Draft</span></span>         | <span data-ttu-id="1cd68-664">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="1cd68-664">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="1cd68-665">Egyéb</span><span class="sxs-lookup"><span data-stu-id="1cd68-665">Other</span></span>              | <span data-ttu-id="1cd68-666">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="1cd68-666">*Not supported by Mexico*</span></span> |

### <a name="bank-account-type"></a><span data-ttu-id="1cd68-667">Bankszámla típusa</span><span class="sxs-lookup"><span data-stu-id="1cd68-667">Bank account type</span></span>

<span data-ttu-id="1cd68-668">Bankszámla-típusok az alkalmazottaknak történő elektronikus kifizetésekhez szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="1cd68-668">Bank account types are used for electronic payments to employees.</span></span> <span data-ttu-id="1cd68-669">Bankszámla típusa a Dayforce-ba átutalási számlaadatként van rendelve.</span><span class="sxs-lookup"><span data-stu-id="1cd68-669">Bank account types are mapped to Dayforce as transfer account information.</span></span> <span data-ttu-id="1cd68-670">A bankszámlatípusok szükség esetén konvertálva vannak az elfogadható értékekké az integráció során.</span><span class="sxs-lookup"><span data-stu-id="1cd68-670">The bank account types are translated, as appropriate, to the accepted values upon integration.</span></span>

| <span data-ttu-id="1cd68-671">Talent</span><span class="sxs-lookup"><span data-stu-id="1cd68-671">Talent</span></span>            | <span data-ttu-id="1cd68-672">Dayforce</span><span class="sxs-lookup"><span data-stu-id="1cd68-672">Dayforce</span></span>                  |
|-------------------|---------------------------|
| <span data-ttu-id="1cd68-673">Folyószámla</span><span class="sxs-lookup"><span data-stu-id="1cd68-673">Checking Account</span></span>  | <span data-ttu-id="1cd68-674">CheckingAccount</span><span class="sxs-lookup"><span data-stu-id="1cd68-674">CheckingAccount</span></span>           |
| <span data-ttu-id="1cd68-675">Bérlista elszámolási számlája</span><span class="sxs-lookup"><span data-stu-id="1cd68-675">Payroll Account</span></span>   | <span data-ttu-id="1cd68-676">PayrollAccount</span><span class="sxs-lookup"><span data-stu-id="1cd68-676">PayrollAccount</span></span>            |
| <span data-ttu-id="1cd68-677">Megtakarítási számla</span><span class="sxs-lookup"><span data-stu-id="1cd68-677">Savings Account</span></span>   | <span data-ttu-id="1cd68-678">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="1cd68-678">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="1cd68-679">BankGirot-számla</span><span class="sxs-lookup"><span data-stu-id="1cd68-679">BankGirot account</span></span> | <span data-ttu-id="1cd68-680">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="1cd68-680">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="1cd68-681">PlusGirot-számla</span><span class="sxs-lookup"><span data-stu-id="1cd68-681">PlusGirot account</span></span> | <span data-ttu-id="1cd68-682">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="1cd68-682">*Not supported by Mexico*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="1cd68-683">Bevételkódok</span><span class="sxs-lookup"><span data-stu-id="1cd68-683">Earning codes</span></span>

<span data-ttu-id="1cd68-684">A bevételkódok egyedi módon azonosítják a dolgozók által kapott fizetéstípusokat.</span><span class="sxs-lookup"><span data-stu-id="1cd68-684">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="1cd68-685">A kódoknak különböző paramétereket fednek le, amelyek a bevételekhez kapcsolódnak, például könyvelési szabályok, jelentési követelmények és bruttósítási lehetőségek.</span><span class="sxs-lookup"><span data-stu-id="1cd68-685">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="1cd68-686">Ha egy nem támogatott gyakoriság van használatban, a **Minden fizetés** gyakorisága van alapértelmezés szerint használva a kiszámításhoz.</span><span class="sxs-lookup"><span data-stu-id="1cd68-686">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="1cd68-687">Támogatott gyakoriságok</span><span class="sxs-lookup"><span data-stu-id="1cd68-687">Supported frequencies</span></span>

- <span data-ttu-id="1cd68-688">Összes</span><span class="sxs-lookup"><span data-stu-id="1cd68-688">All</span></span>
- <span data-ttu-id="1cd68-689">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="1cd68-689">EVERYPAY</span></span>
- <span data-ttu-id="1cd68-690">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="1cd68-690">EACHPAYPERIOD</span></span>
- <span data-ttu-id="1cd68-691">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="1cd68-691">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="1cd68-692">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="1cd68-692">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="1cd68-693">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="1cd68-693">1OFMTH</span></span>
- <span data-ttu-id="1cd68-694">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="1cd68-694">LASTOFMTH</span></span>
- <span data-ttu-id="1cd68-695">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="1cd68-695">2OFMTH</span></span>
- <span data-ttu-id="1cd68-696">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="1cd68-696">3OFMTH</span></span>
- <span data-ttu-id="1cd68-697">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="1cd68-697">4OFMTH</span></span>
- <span data-ttu-id="1cd68-698">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="1cd68-698">5OFMTH</span></span>
- <span data-ttu-id="1cd68-699">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="1cd68-699">1N2OFMTH</span></span>
- <span data-ttu-id="1cd68-700">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="1cd68-700">3N4OFMTH</span></span>
- <span data-ttu-id="1cd68-701">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="1cd68-701">1N3OFMTH</span></span>
- <span data-ttu-id="1cd68-702">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="1cd68-702">1N4OFMTH</span></span>
- <span data-ttu-id="1cd68-703">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="1cd68-703">2N3OFMTH</span></span>
- <span data-ttu-id="1cd68-704">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="1cd68-704">2N4OFMTH</span></span>
- <span data-ttu-id="1cd68-705">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="1cd68-705">1N2N3OFMTH</span></span>
- <span data-ttu-id="1cd68-706">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="1cd68-706">1N2N4OFMTH</span></span>
- <span data-ttu-id="1cd68-707">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="1cd68-707">1N3N4OFMTH</span></span>
- <span data-ttu-id="1cd68-708">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="1cd68-708">2N3N4OFMTH</span></span>
- <span data-ttu-id="1cd68-709">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="1cd68-709">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="1cd68-710">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="1cd68-710">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="1cd68-711">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="1cd68-711">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="1cd68-712">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="1cd68-712">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="1cd68-713">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="1cd68-713">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="1cd68-714">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="1cd68-714">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="1cd68-715">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="1cd68-715">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="1cd68-716">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="1cd68-716">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="1cd68-717">Címek</span><span class="sxs-lookup"><span data-stu-id="1cd68-717">Addresses</span></span>

<span data-ttu-id="1cd68-718">Az adott ország vagy régió, állam és megye (település) kódok specifikus formátumokat követelnek, hogy Dayforce és az országos és regionális szolgáltatók felismerjék azokat.</span><span class="sxs-lookup"><span data-stu-id="1cd68-718">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="1cd68-719">Annak ellenére, hogy a városok formátuma rugalmas, minden városnak társítva kell lennie egy államhoz.</span><span class="sxs-lookup"><span data-stu-id="1cd68-719">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="1cd68-720">Talent</span><span class="sxs-lookup"><span data-stu-id="1cd68-720">Talent</span></span>              | <span data-ttu-id="1cd68-721">Dayforce</span><span class="sxs-lookup"><span data-stu-id="1cd68-721">Dayforce</span></span>              |
|---------------------|-----------------------|
| <span data-ttu-id="1cd68-722">Ország/régió</span><span class="sxs-lookup"><span data-stu-id="1cd68-722">Country/Region</span></span>      | <span data-ttu-id="1cd68-723">Országkód</span><span class="sxs-lookup"><span data-stu-id="1cd68-723">Country Code</span></span>          |
| <span data-ttu-id="1cd68-724">Irányítószám / postai kód</span><span class="sxs-lookup"><span data-stu-id="1cd68-724">Zip/Postal Code</span></span>     | <span data-ttu-id="1cd68-725">Irányítószám</span><span class="sxs-lookup"><span data-stu-id="1cd68-725">Postal Code</span></span>           |
| <span data-ttu-id="1cd68-726">Állami</span><span class="sxs-lookup"><span data-stu-id="1cd68-726">State</span></span>               | <span data-ttu-id="1cd68-727">Államkód</span><span class="sxs-lookup"><span data-stu-id="1cd68-727">State Code</span></span>            |
| <span data-ttu-id="1cd68-728">Város</span><span class="sxs-lookup"><span data-stu-id="1cd68-728">City</span></span>                | <span data-ttu-id="1cd68-729">Város</span><span class="sxs-lookup"><span data-stu-id="1cd68-729">City</span></span>                  |
| <span data-ttu-id="1cd68-730">Megye</span><span class="sxs-lookup"><span data-stu-id="1cd68-730">County</span></span>              | <span data-ttu-id="1cd68-731">Megye (Helyhatóság)</span><span class="sxs-lookup"><span data-stu-id="1cd68-731">County (Municipality)</span></span> |
| <span data-ttu-id="1cd68-732">Utca</span><span class="sxs-lookup"><span data-stu-id="1cd68-732">Street</span></span>              | <span data-ttu-id="1cd68-733">Cím 1. sora</span><span class="sxs-lookup"><span data-stu-id="1cd68-733">Address Line 1</span></span>        |
| <span data-ttu-id="1cd68-734">Utca, házszám</span><span class="sxs-lookup"><span data-stu-id="1cd68-734">Street Number</span></span>       | <span data-ttu-id="1cd68-735">Cím 2. sora</span><span class="sxs-lookup"><span data-stu-id="1cd68-735">Address Line 2</span></span>        |
| <span data-ttu-id="1cd68-736">Épületblokk</span><span class="sxs-lookup"><span data-stu-id="1cd68-736">Building Complement</span></span> | <span data-ttu-id="1cd68-737">Cím 5. sora</span><span class="sxs-lookup"><span data-stu-id="1cd68-737">Address Line 5</span></span>        |

### <a name="passport-number"></a><span data-ttu-id="1cd68-738">Útlevél száma</span><span class="sxs-lookup"><span data-stu-id="1cd68-738">Passport number</span></span>

<span data-ttu-id="1cd68-739">Az alkalmazottak útlevél adatokat is nyilatkozhatnak.</span><span class="sxs-lookup"><span data-stu-id="1cd68-739">Employees can declare passport information.</span></span> <span data-ttu-id="1cd68-740">Az információ a **Útlevél** azonosítótípusra vonatkozik, és az alkalmazott Mexikó-specifikus adataiként van a Dayforce-ba integrálva.</span><span class="sxs-lookup"><span data-stu-id="1cd68-740">This information is of the **Passport** identification type and is integrated into Dayforce as part of an employee's Mexico-specific information.</span></span>

- <span data-ttu-id="1cd68-741">Azonosító típusa = „Útlevél”</span><span class="sxs-lookup"><span data-stu-id="1cd68-741">Identification Type = "Passport"</span></span>
- <span data-ttu-id="1cd68-742">Kibocsátás dátuma</span><span class="sxs-lookup"><span data-stu-id="1cd68-742">Issued Date</span></span>
- <span data-ttu-id="1cd68-743">Lejárat dátuma</span><span class="sxs-lookup"><span data-stu-id="1cd68-743">Expiration Date</span></span>

<span data-ttu-id="1cd68-744">Az alkalmazottak több azonosítószámot is megadhatnak az **Útlevél** azonosítótípushoz.</span><span class="sxs-lookup"><span data-stu-id="1cd68-744">Employees can declare multiple identification numbers of the **Passport** identification type.</span></span> <span data-ttu-id="1cd68-745">Azonban csak az aktuális aktív útlevélbejegyzés van integrálva a Dayforce-ba.</span><span class="sxs-lookup"><span data-stu-id="1cd68-745">However, only the current active passport entry is integrated into Dayforce.</span></span> <span data-ttu-id="1cd68-746">Ha az összes útlevélbejegyzés lejárt, a legutóbb kiállított lesz integrálva a Dayforce-ba.</span><span class="sxs-lookup"><span data-stu-id="1cd68-746">If all passport entries are expired, the passport that was most recently issued is integrated into Dayforce.</span></span>
