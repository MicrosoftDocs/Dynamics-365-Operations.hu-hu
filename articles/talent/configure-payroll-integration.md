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
ms.openlocfilehash: ec1d14cb14ab709dfc1bead4be0785904efcce4e
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/30/2019
ms.locfileid: "2251039"
---
# <a name="configure-the-payroll-integration-between-talent-and-dayforce"></a><span data-ttu-id="6d88c-103">Bérlista-integráció konfigurálása a Talent és a Dayforce között</span><span class="sxs-lookup"><span data-stu-id="6d88c-103">Configure the payroll integration between Talent and Dayforce</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="6d88c-104">A Microsoft Dynamics 365 Talent és Ceridian Dayforce integrálásához több konfigurációs lépést szükséges elvégezni, melyek ebben a témakörben vannak ismertetve.</span><span class="sxs-lookup"><span data-stu-id="6d88c-104">The integration between Microsoft Dynamics 365 Talent and Ceridian Dayforce relies on several configuration steps that are described in this topic.</span></span> <span data-ttu-id="6d88c-105">Be kell állítania az integrációt a Talent a Dayforce alkalmazásokban is a fizetési időszak feldolgozása előtt.</span><span class="sxs-lookup"><span data-stu-id="6d88c-105">You must configure the integration in both Talent and Dayforce before you can process a pay run.</span></span>

<span data-ttu-id="6d88c-106">Ha olyan szolgáltatást használ a fizetési időszakokhoz, mint a Dayforce, engedélyeznie kell az integrációt a Talentben.</span><span class="sxs-lookup"><span data-stu-id="6d88c-106">When you use a service such as Dayforce to complete pay runs, you must enable the integration in Talent.</span></span> <span data-ttu-id="6d88c-107">Az integrációhoz meghatározott adatok szükségesek a Talentből.</span><span class="sxs-lookup"><span data-stu-id="6d88c-107">The integration requires specific data from Talent.</span></span> <span data-ttu-id="6d88c-108">Ezért ellenőriznie kell, hogy a Dayforce-ban hozzárendelt adatok olyan módon vannak konfigurálva a Talentben, hogy az támogassa az integrációt.</span><span class="sxs-lookup"><span data-stu-id="6d88c-108">Therefore, you must verify that data that is mapped to Dayforce is configured in Talent in a manner that supports the integration.</span></span> <span data-ttu-id="6d88c-109">Az integráció a következő szélesebb adatkategóriákat használja:</span><span class="sxs-lookup"><span data-stu-id="6d88c-109">The integration uses the following broad categories of data:</span></span>

- <span data-ttu-id="6d88c-110">Emberierőforrás-adatok</span><span class="sxs-lookup"><span data-stu-id="6d88c-110">Human resources data</span></span>
- <span data-ttu-id="6d88c-111">Kompenzációadatok</span><span class="sxs-lookup"><span data-stu-id="6d88c-111">Compensation data</span></span>
- <span data-ttu-id="6d88c-112">Bérlistaadatok, mint kifizetési ciklus, fizetési időszakok és bevételkódok</span><span class="sxs-lookup"><span data-stu-id="6d88c-112">Payroll data, such as pay cycles, pay periods, and earning codes</span></span>
- <span data-ttu-id="6d88c-113">Dolgozóadatok</span><span class="sxs-lookup"><span data-stu-id="6d88c-113">Worker data</span></span>

<span data-ttu-id="6d88c-114">Ez a témakör leírja a lépéseket, amelyeket követni kell az integráció engedélyezéséhez.</span><span class="sxs-lookup"><span data-stu-id="6d88c-114">This topic describes the steps that you must follow to enable the integration.</span></span> <span data-ttu-id="6d88c-115">Azt is bemutatja, hogy milyen típusú adatok és konfiguráció szükséges az integrációhoz.</span><span class="sxs-lookup"><span data-stu-id="6d88c-115">It also explains the types of data and the configuration details that the integration requires.</span></span>

## <a name="enable-the-integration"></a><span data-ttu-id="6d88c-116">Engedélyezze az integrációt</span><span class="sxs-lookup"><span data-stu-id="6d88c-116">Enable the integration</span></span>

<span data-ttu-id="6d88c-117">A Talentben be kell kapcsolja a műveletek integrációját, meg kell adnia a konfiguráció adatait, hogy tudjon a Dayforcehoz csatlakozni.</span><span class="sxs-lookup"><span data-stu-id="6d88c-117">In Talent, you must turn on the integration and enter the configuration information to connect to Dayforce.</span></span> <span data-ttu-id="6d88c-118">Ha azt szeretné, hogy a létrehozott általános főkönyvi tranzakció importálva legyen a Microsoft Dynamics 365 Finance alkalmazásba, be kell állítania egy Microsoft Azure tárolási fiókot, majd adja meg, majd Azure tárolási kapcsolat karakterláncát a Finance alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="6d88c-118">If you want the general ledger transaction that is produced to be imported into Microsoft Dynamics 365 Finance, you must also set up a Microsoft Azure storage account and enter the Azure Storage connection string in Finance.</span></span>

<span data-ttu-id="6d88c-119">Az integráció engedélyezéséhez a Talentben kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="6d88c-119">To turn on the integration in Talent, follow these steps.</span></span>

1. <span data-ttu-id="6d88c-120">A **Rendszerfelügyelet** oldalon válassza az **Integrációkonfiguráció** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6d88c-120">On the **System administration** page, select **Integration configuration**.</span></span>
2. <span data-ttu-id="6d88c-121">Adja meg a biztonságos fájl átviteli protokollt (FTP) végpontot és a biztonságos FTP-mappa elérési útja.</span><span class="sxs-lookup"><span data-stu-id="6d88c-121">Enter the secure File Transfer Protocol (FTP) endpoint and the secure FTP folder path.</span></span>
3. <span data-ttu-id="6d88c-122">Adja meg azon felhasználó felhasználónevét és jelszavát, aki hozzáfér a biztonságos FTP végponthoz és a mappa elérési útjához.</span><span class="sxs-lookup"><span data-stu-id="6d88c-122">Enter the user name and password of the user who will access the secure FTP endpoint and folder path.</span></span>
4. <span data-ttu-id="6d88c-123">Tesztelje a kapcsolatot szükség szerint, és állítsa a **Bérlista-integráció engedélyezése** lehetőséggel **Igenre**.</span><span class="sxs-lookup"><span data-stu-id="6d88c-123">Test the connection, as required, and set the **Enable payroll integration** option to **Yes**.</span></span>

<span data-ttu-id="6d88c-124">Ha az integráció engedélyezve van, adatexport adatcsomagok és fájlok jönnek létre, valamint a gyakoriság is be van állítva.</span><span class="sxs-lookup"><span data-stu-id="6d88c-124">When the integration is turned on, the data export package and files are created, and the frequency is set.</span></span> <span data-ttu-id="6d88c-125">Igény szerint módosíthatja a gyakoriságot.</span><span class="sxs-lookup"><span data-stu-id="6d88c-125">You can change this frequency as you require.</span></span>

<span data-ttu-id="6d88c-126">Azure tárolási fiókokkal és Azure tárolási kapcsolati karakterláncokat kapcsolatos további információt az alábbi Azure-témakörökben találja:</span><span class="sxs-lookup"><span data-stu-id="6d88c-126">For more information about Azure storage accounts and Azure Storage connection strings, see the following Azure topics:</span></span>

- [<span data-ttu-id="6d88c-127">Az Azure Storage-fiókokról</span><span class="sxs-lookup"><span data-stu-id="6d88c-127">About Azure storage accounts</span></span>](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [<span data-ttu-id="6d88c-128">Azure Storage kapcsolati karakterláncok konfigurálása</span><span class="sxs-lookup"><span data-stu-id="6d88c-128">Configure Azure Storage connection strings</span></span>](https://docs.microsoft.com/azure/storage/common/storage-configure-connection-string)

### <a name="technical-details-when-payroll-integration-is-enabled"></a><span data-ttu-id="6d88c-129">Technikai részletek a bérlista integrációjának engedélyezésekor</span><span class="sxs-lookup"><span data-stu-id="6d88c-129">Technical details when payroll integration is enabled</span></span>

<span data-ttu-id="6d88c-130">A bérlista-integráció bekapcsolása két elsődleges hatással jár:</span><span class="sxs-lookup"><span data-stu-id="6d88c-130">Turning on the payroll integration has two primary effects:</span></span>

- <span data-ttu-id="6d88c-131">Létrejön egy „bérlista-integráció exportálása” nevű adatexportálási projekt.</span><span class="sxs-lookup"><span data-stu-id="6d88c-131">A data export project named "Payroll integration export" is created.</span></span> <span data-ttu-id="6d88c-132">Ez a projekt a bérlista-integrációhoz szükséges entitásokat és mezőket tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="6d88c-132">This project contains the entities and fields required for the payroll integration.</span></span> <span data-ttu-id="6d88c-133">A projekt vizsgálatához nyissa meg a **Rendszerfelügyeletet**, válassza ki az **Adatkezelési** csempét, majd nyissa meg az adatprojektet a projektek listájából.</span><span class="sxs-lookup"><span data-stu-id="6d88c-133">To examine the project, go to **System administration**, select the **Data management** tile, and then open the data project from the list of projects.</span></span>
- <span data-ttu-id="6d88c-134">Ez a kötegelt feladat végrehajtja az adatexportálási projektet, titkosítja a létrejövő adatcsomagot, és átviszi az adatcsomag-fájlt az **Integráció konfigurációja** képernyőjén beállított SFTP végpontba.</span><span class="sxs-lookup"><span data-stu-id="6d88c-134">This batch job executes the data export project, encrypts the resulting data package, and transfers the data package file to the SFTP endpoint configured on the **Integration configuration** screen.</span></span>

> [!NOTE]
> <span data-ttu-id="6d88c-135">Az SFTP végpontra átvitt adatcsomag titkosítva van a csomag egyedi kulcsával.</span><span class="sxs-lookup"><span data-stu-id="6d88c-135">The data package transferred to the SFTP endpoint is encrypted using a key that is unique to the package.</span></span> <span data-ttu-id="6d88c-136">A kulcs egy Azure kulcstárolóban van, amely csak Ceridian számára érhető el.</span><span class="sxs-lookup"><span data-stu-id="6d88c-136">The key is in an Azure Key Vault that is accessible only by Ceridian.</span></span> <span data-ttu-id="6d88c-137">Az adatcsomag tartalmát nem lehet dekódolni és megvizsgálni.</span><span class="sxs-lookup"><span data-stu-id="6d88c-137">It is not possible to decrypt and examine the data package contents.</span></span> <span data-ttu-id="6d88c-138">Ha meg kell vizsgálnia az adatcsomag tartalmát, akkor manuálisan kell exportálnia a „Bérlista-integráció exportálása” adatprojektet, le kell töltenie, majd meg kell nyitnia.</span><span class="sxs-lookup"><span data-stu-id="6d88c-138">If you need to examine the contents of the data package, you need to export the "Payroll integration export" data project manually, download it, and then open it.</span></span> <span data-ttu-id="6d88c-139">A manuális exportálás nem alkalmazza a titkosítást, és nem viszi át a csomagot.</span><span class="sxs-lookup"><span data-stu-id="6d88c-139">Manual export will not apply encryption or transfer the package.</span></span>

## <a name="configure-your-data"></a><span data-ttu-id="6d88c-140">Adatai konfigurálása</span><span class="sxs-lookup"><span data-stu-id="6d88c-140">Configure your data</span></span> 

<span data-ttu-id="6d88c-141">A bérlista feldolgozásához konfigurálnia kell az emberi erőforrás adatokat a Talentben.</span><span class="sxs-lookup"><span data-stu-id="6d88c-141">To process payroll, you must configure human resource data in Talent.</span></span> <span data-ttu-id="6d88c-142">Be kell állítani a szervezeti adatokat, például a feladatokat és beosztásokat, valamint juttatásokra és a kompenzációra vonatkozó adatokat.</span><span class="sxs-lookup"><span data-stu-id="6d88c-142">You must set up organizational data, such as jobs and positions, together with benefits and compensation information.</span></span> <span data-ttu-id="6d88c-143">Ez az információ megadja a foglalkoztatásra, fizetésre és levonásokra vonatkozó információkat, melyek szükségesek az alkalmazott fizetések generálásához.</span><span class="sxs-lookup"><span data-stu-id="6d88c-143">This information provides the employment, pay, and deduction information that is required in order to generate employee pay.</span></span>

### <a name="human-resource-data"></a><span data-ttu-id="6d88c-144">Emberierőforrás-adatok</span><span class="sxs-lookup"><span data-stu-id="6d88c-144">Human resource data</span></span>

#### <a name="benefits"></a><span data-ttu-id="6d88c-145">Juttatások</span><span class="sxs-lookup"><span data-stu-id="6d88c-145">Benefits</span></span> 

<span data-ttu-id="6d88c-146">Az emberi erőforrások számos beállítási és karbantartási eszközt biztosít, amelyek segítségével beállíthatja és karbantarthatja a szervezet által a dolgozónak biztosított juttatásokat, levonásokat és dolgozói kompenzációs terveket.</span><span class="sxs-lookup"><span data-stu-id="6d88c-146">Human resources provides tools for the setup and maintenance of the benefits, deductions, and worker compensation plans that an organization offers or processes for its workers.</span></span>

<span data-ttu-id="6d88c-147">Juttatások létrehozása esetén ne felejtse el a következő adatokat és beállításokat, amelyeket a Dayforce használ.</span><span class="sxs-lookup"><span data-stu-id="6d88c-147">When you create benefits, keep in mind the following data and configurations that are used in Dayforce.</span></span>

##### <a name="benefit-plans"></a><span data-ttu-id="6d88c-148">Juttatási tervek</span><span class="sxs-lookup"><span data-stu-id="6d88c-148">Benefit plans</span></span>

- <span data-ttu-id="6d88c-149">Terv (szükséges)</span><span class="sxs-lookup"><span data-stu-id="6d88c-149">Plan (required)</span></span>
- <span data-ttu-id="6d88c-150">Típus (szükséges)</span><span class="sxs-lookup"><span data-stu-id="6d88c-150">Type (required)</span></span>
- <span data-ttu-id="6d88c-151">Bérlista hatása (szükséges)</span><span class="sxs-lookup"><span data-stu-id="6d88c-151">Payroll impact (required)</span></span>
- <span data-ttu-id="6d88c-152">Hátralékok helyreállítása</span><span class="sxs-lookup"><span data-stu-id="6d88c-152">Recover arrears</span></span>
- <span data-ttu-id="6d88c-153">Levonási módszer</span><span class="sxs-lookup"><span data-stu-id="6d88c-153">Deduction method</span></span>
- <span data-ttu-id="6d88c-154">Levonás prioritása</span><span class="sxs-lookup"><span data-stu-id="6d88c-154">Deduction priority</span></span>
- <span data-ttu-id="6d88c-155">Időszak korlátozása</span><span class="sxs-lookup"><span data-stu-id="6d88c-155">Limit period</span></span>
- <span data-ttu-id="6d88c-156">Összeghatár</span><span class="sxs-lookup"><span data-stu-id="6d88c-156">Limit amount</span></span>

##### <a name="benefits"></a><span data-ttu-id="6d88c-157">Juttatások</span><span class="sxs-lookup"><span data-stu-id="6d88c-157">Benefits</span></span>

- <span data-ttu-id="6d88c-158">Terv (szükséges)</span><span class="sxs-lookup"><span data-stu-id="6d88c-158">Plan (required)</span></span>
- <span data-ttu-id="6d88c-159">Típus (szükséges)</span><span class="sxs-lookup"><span data-stu-id="6d88c-159">Type (required)</span></span>
- <span data-ttu-id="6d88c-160">Lehetőség (szükséges)</span><span class="sxs-lookup"><span data-stu-id="6d88c-160">Option (required)</span></span>
- <span data-ttu-id="6d88c-161">Juttatás azonosítója (szükséges)</span><span class="sxs-lookup"><span data-stu-id="6d88c-161">Benefit ID (required)</span></span>
- <span data-ttu-id="6d88c-162">Gyakoriság</span><span class="sxs-lookup"><span data-stu-id="6d88c-162">Frequency</span></span>
- <span data-ttu-id="6d88c-163">Alap</span><span class="sxs-lookup"><span data-stu-id="6d88c-163">Basis</span></span>
- <span data-ttu-id="6d88c-164">Összeg vagy mérték</span><span class="sxs-lookup"><span data-stu-id="6d88c-164">Amount or rate</span></span>
- <span data-ttu-id="6d88c-165">Bevételkód</span><span class="sxs-lookup"><span data-stu-id="6d88c-165">Earning code</span></span>

##### <a name="supported-frequencies"></a><span data-ttu-id="6d88c-166">Támogatott gyakoriságok</span><span class="sxs-lookup"><span data-stu-id="6d88c-166">Supported frequencies</span></span> 

- <span data-ttu-id="6d88c-167">Heti</span><span class="sxs-lookup"><span data-stu-id="6d88c-167">Weekly</span></span>
- <span data-ttu-id="6d88c-168">Kétheti</span><span class="sxs-lookup"><span data-stu-id="6d88c-168">Bi-weekly</span></span>
- <span data-ttu-id="6d88c-169">Félhavi</span><span class="sxs-lookup"><span data-stu-id="6d88c-169">Semi-monthly</span></span>
- <span data-ttu-id="6d88c-170">Havi</span><span class="sxs-lookup"><span data-stu-id="6d88c-170">Monthly</span></span>

##### <a name="supported-bases"></a><span data-ttu-id="6d88c-171">Támogatott alapok</span><span class="sxs-lookup"><span data-stu-id="6d88c-171">Supported bases</span></span> 

- <span data-ttu-id="6d88c-172">Rögzített összeg</span><span class="sxs-lookup"><span data-stu-id="6d88c-172">Fixed amount</span></span>
- <span data-ttu-id="6d88c-173">Bevételek százaléka</span><span class="sxs-lookup"><span data-stu-id="6d88c-173">Percent of earnings</span></span>
- <span data-ttu-id="6d88c-174">Produktív órák</span><span class="sxs-lookup"><span data-stu-id="6d88c-174">Productive hours</span></span>

<span data-ttu-id="6d88c-175">A Dayforce létrehozza a következő levonásokat, a juttatási tervben definiált bérlistahatás alapján.</span><span class="sxs-lookup"><span data-stu-id="6d88c-175">Dayforce creates the following deductions, based on the payroll impact that is defined on the benefit plan.</span></span>

| <span data-ttu-id="6d88c-176">Kiválasztás a Talentben</span><span class="sxs-lookup"><span data-stu-id="6d88c-176">Selection in Talent</span></span>        | <span data-ttu-id="6d88c-177">Eredmény a Dayforce-ban</span><span class="sxs-lookup"><span data-stu-id="6d88c-177">Result in Dayforce</span></span>                            |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="6d88c-178">Nincs</span><span class="sxs-lookup"><span data-stu-id="6d88c-178">None</span></span>                       | <span data-ttu-id="6d88c-179">Nincs létrehozva levonás.</span><span class="sxs-lookup"><span data-stu-id="6d88c-179">No deduction is created.</span></span>                      |
| <span data-ttu-id="6d88c-180">Csak levonás</span><span class="sxs-lookup"><span data-stu-id="6d88c-180">Deduction only</span></span>             | <span data-ttu-id="6d88c-181">Alkalmazotti levonás jön létre.</span><span class="sxs-lookup"><span data-stu-id="6d88c-181">An employee deduction is created.</span></span>             |
| <span data-ttu-id="6d88c-182">Csak hozzájárulás</span><span class="sxs-lookup"><span data-stu-id="6d88c-182">Contribution only</span></span>          | <span data-ttu-id="6d88c-183">Egy alkalmazotti levonás jön létre.</span><span class="sxs-lookup"><span data-stu-id="6d88c-183">An employer deduction is created.</span></span>             |
| <span data-ttu-id="6d88c-184">Levonás és hozzájárulás</span><span class="sxs-lookup"><span data-stu-id="6d88c-184">Deduction and contribution</span></span> | <span data-ttu-id="6d88c-185">Alkalmazotti és a munkáltatói levonások jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="6d88c-185">Employee and employer deductions are created.</span></span> |

<span data-ttu-id="6d88c-186">A juttatási programok definiálásával és kezelésével kapcsolatosan további tájékoztatás a következő témakörökben talál:</span><span class="sxs-lookup"><span data-stu-id="6d88c-186">For more information about how to define and manage a benefits program, see the following topics:</span></span>

- [<span data-ttu-id="6d88c-187">Alkalmazotti juttatási program megvalósítása</span><span class="sxs-lookup"><span data-stu-id="6d88c-187">Deliver an employee benefits program</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [<span data-ttu-id="6d88c-188">Új juttatás létrehozása</span><span class="sxs-lookup"><span data-stu-id="6d88c-188">Create a new benefit</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [<span data-ttu-id="6d88c-189">Juttatásra való jogosultsági szabályok és irányelvek meghatározása</span><span class="sxs-lookup"><span data-stu-id="6d88c-189">Define benefit eligibility rules and policies</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [<span data-ttu-id="6d88c-190">Dolgozók juttatásainak felvétele és eltávolítása</span><span class="sxs-lookup"><span data-stu-id="6d88c-190">Enroll and remove benefits from workers</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a><span data-ttu-id="6d88c-191">Kompenzáció</span><span class="sxs-lookup"><span data-stu-id="6d88c-191">Compensation</span></span> 

<span data-ttu-id="6d88c-192">A kompenzációkezeléssel szabályozható az alapfizetés és a jutalmak kifizetése.</span><span class="sxs-lookup"><span data-stu-id="6d88c-192">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="6d88c-193">Egy alkalmazott fix fizetési díjalapja és érdemeken alapuló fizetése kezelhető a fix kompenzációs tervekkel.</span><span class="sxs-lookup"><span data-stu-id="6d88c-193">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="6d88c-194">Az ösztönző díjak kifizetése, például bónuszok, teljesítménydíjak, részvényopciók és kölcsönök, továbbá az egyszeri jutalmak a változó kompenzációs tervekben szabályozhatók.</span><span class="sxs-lookup"><span data-stu-id="6d88c-194">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span>

<span data-ttu-id="6d88c-195">A Dayforce a kompenzációs adatok segítségével kiszámítja az alkalmazott óradíját vagy éves díját.</span><span class="sxs-lookup"><span data-stu-id="6d88c-195">Dayforce uses compensation information to calculate an employee's hourly or annual rate.</span></span> <span data-ttu-id="6d88c-196">Fix kompenzációs tervek és a fizetési díjalap átalakítások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="6d88c-196">Fixed compensation plans and pay rate conversions are required.</span></span> <span data-ttu-id="6d88c-197">Az alkalmazottakat hozzá kell rendelni a fix kompenzációs tervhez.</span><span class="sxs-lookup"><span data-stu-id="6d88c-197">Employees must be associated with a fixed compensation plan.</span></span>

<span data-ttu-id="6d88c-198">A következő témakörökben bővebben olvashat a kompenzációs tervekről:</span><span class="sxs-lookup"><span data-stu-id="6d88c-198">For more information about compensation plans, see the following topics:</span></span>

- [<span data-ttu-id="6d88c-199">Fix kompenzációs konstrukciók létrehozása</span><span class="sxs-lookup"><span data-stu-id="6d88c-199">Create fixed compensation plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [<span data-ttu-id="6d88c-200">Változó kompenzációs konstrukciók létrehozása</span><span class="sxs-lookup"><span data-stu-id="6d88c-200">Create variable compensation plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [<span data-ttu-id="6d88c-201">Munkabér-/kompenzációs struktúra és tervek kialakítása</span><span class="sxs-lookup"><span data-stu-id="6d88c-201">Develop salary/compensation structure and plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [<span data-ttu-id="6d88c-202">Folyamatkompenzáció</span><span class="sxs-lookup"><span data-stu-id="6d88c-202">Process compensation</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/process-compensation)
- [<span data-ttu-id="6d88c-203">Kompenzációs folyamat meghatározása és eredmények kiszámítása</span><span class="sxs-lookup"><span data-stu-id="6d88c-203">Define compensation process and calculate results</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [<span data-ttu-id="6d88c-204">Alkalmazottak felvétele fix kompenzációs konstrukcióba</span><span class="sxs-lookup"><span data-stu-id="6d88c-204">Enroll an employee in a fixed compensation plan</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [<span data-ttu-id="6d88c-205">Alkalmazottak felvétele változó kompenzációs konstrukcióba</span><span class="sxs-lookup"><span data-stu-id="6d88c-205">Enroll an employee in a variable compensation plan</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a><span data-ttu-id="6d88c-206">Beosztások</span><span class="sxs-lookup"><span data-stu-id="6d88c-206">Jobs</span></span> 

<span data-ttu-id="6d88c-207">A munkakör azon feladatok és felelősségek gyűjteménye, amelyek egy adott munkát végrehajtó személytől elvártak.</span><span class="sxs-lookup"><span data-stu-id="6d88c-207">A job is a collection of the tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="6d88c-208">További információ a következő témakörökben olvasható:</span><span class="sxs-lookup"><span data-stu-id="6d88c-208">For more information, see the following topics:</span></span>

- [<span data-ttu-id="6d88c-209">Feladat összetevőinek beállítása</span><span class="sxs-lookup"><span data-stu-id="6d88c-209">Setting up the components of a job</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-job)
- [<span data-ttu-id="6d88c-210">Új feladatok meghatározása</span><span class="sxs-lookup"><span data-stu-id="6d88c-210">Define new jobs</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a><span data-ttu-id="6d88c-211">Beosztások</span><span class="sxs-lookup"><span data-stu-id="6d88c-211">Positions</span></span>

<span data-ttu-id="6d88c-212">Egy beosztás egy feladat egyedi példánya.</span><span class="sxs-lookup"><span data-stu-id="6d88c-212">A position is an individual instance of a job.</span></span> <span data-ttu-id="6d88c-213">Például az „Értékesítési igazgató (Kelet)” pozíció egyike azon beosztásoknak, amelyek társíthatók az „Értékesítési igazgató” feladathoz.</span><span class="sxs-lookup"><span data-stu-id="6d88c-213">For example, the "Sales manager (East)" position is one of the positions that are associated with the "Sales manager" job.</span></span> <span data-ttu-id="6d88c-214">A beosztás létezik a részlegben.</span><span class="sxs-lookup"><span data-stu-id="6d88c-214">A position exists in a department.</span></span> <span data-ttu-id="6d88c-215">Egy beosztáshoz csak egy dolgozó rendelhető.</span><span class="sxs-lookup"><span data-stu-id="6d88c-215">Only one worker can be associated with each position.</span></span>

<span data-ttu-id="6d88c-216">A következő adatokat és konfigurációkat szem előtt tartani beosztások beállításakor:</span><span class="sxs-lookup"><span data-stu-id="6d88c-216">Keep the following data and configuration in mind when you set up positions:</span></span>

- <span data-ttu-id="6d88c-217">Beosztás (szükséges)</span><span class="sxs-lookup"><span data-stu-id="6d88c-217">Position (required)</span></span>
- <span data-ttu-id="6d88c-218">Leírás (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-218">Description (required)</span></span>
- <span data-ttu-id="6d88c-219">Munka (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-219">Job (required)</span></span>
- <span data-ttu-id="6d88c-220">Részleg (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-220">Department (required)</span></span>
- <span data-ttu-id="6d88c-221">Beosztás típusa (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-221">Position type (required)</span></span>
- <span data-ttu-id="6d88c-222">Teljes munkaidőssel egyenértékű</span><span class="sxs-lookup"><span data-stu-id="6d88c-222">Full-time equivalent</span></span>
- <span data-ttu-id="6d88c-223">Éves rendes munkaidő (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-223">Annual regular hours (required)</span></span>
- <span data-ttu-id="6d88c-224">Jogi személy által fizetett (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-224">Paid by legal entity (required)</span></span>
- <span data-ttu-id="6d88c-225">Fizetési ciklus (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-225">Pay cycle (required)</span></span>
- <span data-ttu-id="6d88c-226">Alapértelmezett pénzügyi dimenzió – Költséghely (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-226">Default financial dimension – Cost center (required)</span></span>
- <span data-ttu-id="6d88c-227">Dolgozó-hozzárendelés – dolgozó-hozzárendelés kezdete, hozzárendelés vége és okkód</span><span class="sxs-lookup"><span data-stu-id="6d88c-227">Worker assignment – Worker, assignment start, assignment end, reason code</span></span>

<span data-ttu-id="6d88c-228">A azonos osztály több beosztása társítva van az ugyanazon a feladathoz, azok össze lesznek vonva a Dayforce egyetlen pozíciójába.</span><span class="sxs-lookup"><span data-stu-id="6d88c-228">If multiple positions in the same department are associated with the same job, they are consolidated into a single position in Dayforce.</span></span>

<span data-ttu-id="6d88c-229">További információ a következő témakörökben olvasható:</span><span class="sxs-lookup"><span data-stu-id="6d88c-229">For more information, see the following topics:</span></span>

- [<span data-ttu-id="6d88c-230">Munkaerő szervezése részlegek, munkák és beosztások szerint</span><span class="sxs-lookup"><span data-stu-id="6d88c-230">Organize your workforce using departments, jobs, and positions</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [<span data-ttu-id="6d88c-231">Beosztások beállítása</span><span class="sxs-lookup"><span data-stu-id="6d88c-231">Set up positions</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a><span data-ttu-id="6d88c-232">Osztályok</span><span class="sxs-lookup"><span data-stu-id="6d88c-232">Departments</span></span>

<span data-ttu-id="6d88c-233">A részleg egy működési egység, amely a szervezet egy kategóriáját vagy működési területét képviseli.</span><span class="sxs-lookup"><span data-stu-id="6d88c-233">A department is an operating unit that represents a category or functional area of an organization.</span></span> <span data-ttu-id="6d88c-234">Egy részleg a szervezet egy konkrét területen végzett tevékenységeiért felel (például értékesítés, könyvelés, emberi erőforrások).</span><span class="sxs-lookup"><span data-stu-id="6d88c-234">A department is responsible for a specific area of the organization, such as sales, accounting, or human resources.</span></span> <span data-ttu-id="6d88c-235">A részlegek segítségével hozhatók létre jelentések a működési területekről.</span><span class="sxs-lookup"><span data-stu-id="6d88c-235">You can use departments to report on functional areas.</span></span> <span data-ttu-id="6d88c-236">A részlegeknek lehet eredménykimutatási felelőssége.</span><span class="sxs-lookup"><span data-stu-id="6d88c-236">Departments might have profit and loss responsibility.</span></span>

<span data-ttu-id="6d88c-237">További információ a következő témakörökben olvasható:</span><span class="sxs-lookup"><span data-stu-id="6d88c-237">For more information, see the following topics:</span></span>

- [<span data-ttu-id="6d88c-238">Részleg létrehozása és társítása a szervezeti hierarchiához</span><span class="sxs-lookup"><span data-stu-id="6d88c-238">Create a department and associate it with the department hierarchy</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [<span data-ttu-id="6d88c-239">Új részlegek meghatározása</span><span class="sxs-lookup"><span data-stu-id="6d88c-239">Define new departments</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a><span data-ttu-id="6d88c-240">Fizetési ciklusok és fizetési időszakok</span><span class="sxs-lookup"><span data-stu-id="6d88c-240">Pay cycles and pay periods</span></span>

<span data-ttu-id="6d88c-241">A fizetési ciklus meghatározza, hogy milyen gyakran történik a bérlista folyósítása, és a dolgozók mely napokon kapnak fizetést,.</span><span class="sxs-lookup"><span data-stu-id="6d88c-241">A pay cycle determines how often payroll is run and the specific days when workers are paid.</span></span> <span data-ttu-id="6d88c-242">Például a kifizetési ciklus lehet, havi, és az alkalmazottak kaphatják a hónap utolsó napján a fizetésüket.</span><span class="sxs-lookup"><span data-stu-id="6d88c-242">For example, a pay cycle might be monthly, and employees might be paid on the last day of the month.</span></span> <span data-ttu-id="6d88c-243">Vagy a kifizetési ciklus lehet heti, és az alkalmazottak a fizetési időszak utáni kedden kaphatják fizetésüket.</span><span class="sxs-lookup"><span data-stu-id="6d88c-243">Alternatively, a pay cycle might be weekly, and employees might be paid on the Tuesday after the end of the pay period.</span></span> <span data-ttu-id="6d88c-244">Kifizetési ciklusok beosztásokhoz vannak rendelve, és szabályozzák, hogy az ebben a beosztásban lévő dolgozók mikor kapnak fizetést.</span><span class="sxs-lookup"><span data-stu-id="6d88c-244">Pay cycles are assigned to positions to control when workers in those positions are paid.</span></span>

<span data-ttu-id="6d88c-245">Miután létrehozott fizetési ciklusokat, minden egyes ciklushoz fizetési időszakot hozhat létre.</span><span class="sxs-lookup"><span data-stu-id="6d88c-245">After you create pay cycles, you can generate pay periods for each cycle.</span></span> <span data-ttu-id="6d88c-246">Minden fizetési időszakban egy alapértelmezett fizetési dátum van, amely a megadott adatokon alapul.</span><span class="sxs-lookup"><span data-stu-id="6d88c-246">Each pay period includes a default payment date that is based on information that you provide.</span></span> <span data-ttu-id="6d88c-247">Ugyanakkor az alapértelmezett fizetési dátumot a fizetési időszakban módosíthatja kivételekhez például amikor egy kifizetési dátum ünnepnapra esik.</span><span class="sxs-lookup"><span data-stu-id="6d88c-247">However, you can modify the default payment date in a pay period to allow for exceptions, such as when the payment date falls on a holiday.</span></span>

<span data-ttu-id="6d88c-248">A következő adatokat használja a Dayforce:</span><span class="sxs-lookup"><span data-stu-id="6d88c-248">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="6d88c-249">Fizetési ciklus (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-249">Pay cycle (required)</span></span>
- <span data-ttu-id="6d88c-250">Fizetési ciklus gyakorisága (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-250">Pay cycle frequency (required)</span></span>
- <span data-ttu-id="6d88c-251">Az időszak kezdő dátuma (az első fizetési időszak szükséges)</span><span class="sxs-lookup"><span data-stu-id="6d88c-251">Period start date (first pay period required)</span></span>
- <span data-ttu-id="6d88c-252">Alapértelmezett fizetési dátum (az első fizetési időszak szükséges)</span><span class="sxs-lookup"><span data-stu-id="6d88c-252">Default payment date (first pay period required)</span></span>

<span data-ttu-id="6d88c-253">Ez az információ Dayforceba fizetési csoportokként van integrálva országonként vagy régiónként le van választva egyes kifizetési ciklusokhoz.</span><span class="sxs-lookup"><span data-stu-id="6d88c-253">This information is integrated with Dayforce as pay groups, and is separated by country or region for each pay cycle.</span></span> <span data-ttu-id="6d88c-254">Legalább egy fizetési időszakot kell létrehozni az integráció előtt.</span><span class="sxs-lookup"><span data-stu-id="6d88c-254">At least one pay period must be generated before integration.</span></span> <span data-ttu-id="6d88c-255">Dayforce létrehoz fizetési csoport naptárakat és a kifizetési dátumokat, az első fizetési időszak kezdő dátuma és az alapértelmezett fizetési dátum alapján, melyek a Talentben vannak beállítva.</span><span class="sxs-lookup"><span data-stu-id="6d88c-255">Dayforce generates pay group calendars and payment dates, based on the start date of the first pay period and the default payment date that is set up in Talent.</span></span>

#### <a name="earning-codes"></a><span data-ttu-id="6d88c-256">Bevételkódok</span><span class="sxs-lookup"><span data-stu-id="6d88c-256">Earning codes</span></span>

<span data-ttu-id="6d88c-257">A bevételkódok egyedi módon azonosítják a dolgozók által kapott fizetéstípusokat.</span><span class="sxs-lookup"><span data-stu-id="6d88c-257">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="6d88c-258">A kódoknak különböző paraméterei vannak, amelyek a bevételekhez kapcsolódnak, például könyvelési szabályok, jelentési követelmények és bruttósítási lehetőségek.</span><span class="sxs-lookup"><span data-stu-id="6d88c-258">The codes have various parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span>

<span data-ttu-id="6d88c-259">A következő adatokat használja a Dayforce:</span><span class="sxs-lookup"><span data-stu-id="6d88c-259">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="6d88c-260">Bevételkód (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-260">Earning Code (required)</span></span>
- <span data-ttu-id="6d88c-261">Leírás</span><span class="sxs-lookup"><span data-stu-id="6d88c-261">Description</span></span>
- <span data-ttu-id="6d88c-262">Mértékegység</span><span class="sxs-lookup"><span data-stu-id="6d88c-262">Unit of measure</span></span>
- <span data-ttu-id="6d88c-263">Produktív</span><span class="sxs-lookup"><span data-stu-id="6d88c-263">Productive</span></span>

### <a name="worker-data"></a><span data-ttu-id="6d88c-264">Dolgozóadatok</span><span class="sxs-lookup"><span data-stu-id="6d88c-264">Worker data</span></span>

<span data-ttu-id="6d88c-265">A dolgozók különböző típusaihoz tartozó rekordok, melyek fontosak az emberi erőforrásoknak és a bérlistarendszerekhez.</span><span class="sxs-lookup"><span data-stu-id="6d88c-265">Records for the various types of workers that you have are important to your human resources and payroll systems.</span></span> <span data-ttu-id="6d88c-266">A bevitt információk felhasználhatók az dolgozói és személyes adatok nyilvántartására.</span><span class="sxs-lookup"><span data-stu-id="6d88c-266">The information that you enter can be used to track workers and personal information.</span></span>

<span data-ttu-id="6d88c-267">A dolgozók következő adatait tarthatja karban:</span><span class="sxs-lookup"><span data-stu-id="6d88c-267">You can maintain the following information for workers:</span></span>

- <span data-ttu-id="6d88c-268">**Alapvető** – A dolgozók alapvető információi, például a kapcsolattartási adatok, demográfiai adatok azonosító adatok, családi adatok, a katonai szolgálat állapota, kiküldetésekre vonatkozó adatok, illetve személyes és rendkívüli kapcsolattartók.</span><span class="sxs-lookup"><span data-stu-id="6d88c-268">**Basic** – Maintain basic information about a worker, such as contact information, demographic information, identification information, family information, military service status, expatriate information, and personal and emergency contacts.</span></span>
- <span data-ttu-id="6d88c-269">**Foglalkoztatás** – Információk a dolgozó munkaviszonyáról, például a vállalati vagy szervezeti kapcsolat, hozzárendelt pozíció, kezdő és záró dátumok, munkajogosultság, foglalkoztatás feltételei, nyugdíj, szabadság és áthelyezéssel kapcsolatos információk.</span><span class="sxs-lookup"><span data-stu-id="6d88c-269">**Employment** – Maintain information about a worker's employment, such as company or organization affiliation, position assignment, start and end dates, work eligibility, terms of employment, pension, vacation, and relocation information.</span></span>
- <span data-ttu-id="6d88c-270">**Szabadság és a távollét** – A dolgozó távolléteinek kezelése, például a munkaidő-naptárak, a távolléti tranzakciók és távollét beállítása.</span><span class="sxs-lookup"><span data-stu-id="6d88c-270">**Leave and absence** – Maintain information about a worker's absences, such as working calendars, absence transactions, and absence setup.</span></span>
- <span data-ttu-id="6d88c-271">**Kompenzáció és bérlista** – dolgozói kompenzációs tervek és bérlistainformációk kezelése, például felvétel konstrukciója, jutalmak, teljesítmény, jutalék, adózási információk, nyugdíj és fizetéslevonások.</span><span class="sxs-lookup"><span data-stu-id="6d88c-271">**Compensation and payroll** – Maintain information about a worker's compensation plans and payroll information, such as plan enrollment, awards, performance, commission, tax information, retirement, and salary deductions.</span></span>

<span data-ttu-id="6d88c-272">A dolgozóinformációk létrehozása esetén ne felejtse el a következő adatokat és beállításokat, amelyeket a Dayforce használ.</span><span class="sxs-lookup"><span data-stu-id="6d88c-272">When you enter worker information, keep in mind the following data and configurations that are used in Dayforce.</span></span>

#### <a name="general-information"></a><span data-ttu-id="6d88c-273">Általános információk</span><span class="sxs-lookup"><span data-stu-id="6d88c-273">General information</span></span>

- <span data-ttu-id="6d88c-274">Személyzeti szám (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-274">Personnel number (required)</span></span>
- <span data-ttu-id="6d88c-275">Utónév (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-275">First name (required)</span></span>
- <span data-ttu-id="6d88c-276">Vezetéknév (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-276">Last name (required)</span></span>
- <span data-ttu-id="6d88c-277">Második keresztnév</span><span class="sxs-lookup"><span data-stu-id="6d88c-277">Middle name</span></span>
- <span data-ttu-id="6d88c-278">Szolgálati idő dátuma</span><span class="sxs-lookup"><span data-stu-id="6d88c-278">Seniority date</span></span>
- <span data-ttu-id="6d88c-279">Más néven</span><span class="sxs-lookup"><span data-stu-id="6d88c-279">Known as</span></span>

#### <a name="personal-information"></a><span data-ttu-id="6d88c-280">Személyes információ</span><span class="sxs-lookup"><span data-stu-id="6d88c-280">Personal information</span></span>

- <span data-ttu-id="6d88c-281">Családi állapot (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-281">Marital status (required)</span></span>
- <span data-ttu-id="6d88c-282">Születési dátum (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-282">Birth date (required)</span></span>
- <span data-ttu-id="6d88c-283">Nem (szükséges)</span><span class="sxs-lookup"><span data-stu-id="6d88c-283">Gender (required)</span></span>
- <span data-ttu-id="6d88c-284">Fogyatékkal élő személy</span><span class="sxs-lookup"><span data-stu-id="6d88c-284">Person with disabilities</span></span>
- <span data-ttu-id="6d88c-285">Állampolgárság ország régió (csak a Mexikó)</span><span class="sxs-lookup"><span data-stu-id="6d88c-285">Nationality country region (only for Mexico)</span></span>

#### <a name="address-information"></a><span data-ttu-id="6d88c-286">Címadatok</span><span class="sxs-lookup"><span data-stu-id="6d88c-286">Address information</span></span>

- <span data-ttu-id="6d88c-287">Elsődleges (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-287">Primary (required)</span></span>
- <span data-ttu-id="6d88c-288">Ország/régiót (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-288">Country/region (required)</span></span>
- <span data-ttu-id="6d88c-289">Irányítószámot (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-289">Postal code (required)</span></span>
- <span data-ttu-id="6d88c-290">Utca, házszám (kötelező) (csak Mexikó esetén)</span><span class="sxs-lookup"><span data-stu-id="6d88c-290">Street Number (required) (Only for Mexico)</span></span>
- <span data-ttu-id="6d88c-291">Épületblokk (csak a Mexikó)</span><span class="sxs-lookup"><span data-stu-id="6d88c-291">Building Complement (Only for Mexico)</span></span>
- <span data-ttu-id="6d88c-292">Város (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-292">City (required)</span></span>
- <span data-ttu-id="6d88c-293">Állam (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-293">State (required)</span></span>
- <span data-ttu-id="6d88c-294">Megye (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-294">County (required)</span></span>

#### <a name="contact-information"></a><span data-ttu-id="6d88c-295">Névjegy adatai</span><span class="sxs-lookup"><span data-stu-id="6d88c-295">Contact information</span></span> 

- <span data-ttu-id="6d88c-296">Elsődleges (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-296">Primary (required)</span></span>
- <span data-ttu-id="6d88c-297">Kapcsolattartó száma (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-297">Contact number (required)</span></span>
- <span data-ttu-id="6d88c-298">Mellék</span><span class="sxs-lookup"><span data-stu-id="6d88c-298">Extension</span></span>

#### <a name="payroll-information-and-earning-codes"></a><span data-ttu-id="6d88c-299">Bérlistaadatok és bevételkódok</span><span class="sxs-lookup"><span data-stu-id="6d88c-299">Payroll information and earning codes</span></span>

<span data-ttu-id="6d88c-300">Alkalmazottak hozzárendelhetők meghatározott bevételekhez adott fizetési gyakorisággal, és magadható elsődleges fizetési mód.</span><span class="sxs-lookup"><span data-stu-id="6d88c-300">Employees may be assigned specific earnings at a given frequency of payment and have a preferred payment method.</span></span> <span data-ttu-id="6d88c-301">A következő mezőket a Dayforce arra használja, hogy garantálja, hogy ezeket a preferenciákat és beállításokat használja.</span><span class="sxs-lookup"><span data-stu-id="6d88c-301">The following fields are used in Dayforce to help guarantee that those preferences and settings are used.</span></span>

##### <a name="earning-codes"></a><span data-ttu-id="6d88c-302">Bevételkódok</span><span class="sxs-lookup"><span data-stu-id="6d88c-302">Earning codes</span></span>

- <span data-ttu-id="6d88c-303">Beosztás (szükséges)</span><span class="sxs-lookup"><span data-stu-id="6d88c-303">Position (required)</span></span>
- <span data-ttu-id="6d88c-304">Bevételkód (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-304">Earning Code (required)</span></span>
- <span data-ttu-id="6d88c-305">Gyakoriság (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-305">Frequency (required)</span></span>
- <span data-ttu-id="6d88c-306">Összeg (szükséges)</span><span class="sxs-lookup"><span data-stu-id="6d88c-306">Amount (required)</span></span>

##### <a name="payroll-information"></a><span data-ttu-id="6d88c-307">Bérlistaadatok</span><span class="sxs-lookup"><span data-stu-id="6d88c-307">Payroll information</span></span>

- <span data-ttu-id="6d88c-308">Kifizetési mód</span><span class="sxs-lookup"><span data-stu-id="6d88c-308">Payment Method</span></span>
- <span data-ttu-id="6d88c-309">Gazdasági régió (szükséges)</span><span class="sxs-lookup"><span data-stu-id="6d88c-309">Economic Region (required)</span></span>
- <span data-ttu-id="6d88c-310">Alkalmazott juttatásainak azonosítója</span><span class="sxs-lookup"><span data-stu-id="6d88c-310">Employee Benefits ID</span></span>
- <span data-ttu-id="6d88c-311">Nemzeti azonosító (szükséges)</span><span class="sxs-lookup"><span data-stu-id="6d88c-311">National ID Number (required)</span></span>
- <span data-ttu-id="6d88c-312">Katonai szolgálat száma</span><span class="sxs-lookup"><span data-stu-id="6d88c-312">Military Service Number</span></span>
- <span data-ttu-id="6d88c-313">Műszakazonosító (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-313">Shift ID (required)</span></span>
- <span data-ttu-id="6d88c-314">Adószám (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-314">Tax Number (required)</span></span>
- <span data-ttu-id="6d88c-315">Szakszervezeti azonosító (szükséges)</span><span class="sxs-lookup"><span data-stu-id="6d88c-315">Union ID (required)</span></span>
- <span data-ttu-id="6d88c-316">Munkanap azonosítója (szükséges)</span><span class="sxs-lookup"><span data-stu-id="6d88c-316">Work Day ID (required)</span></span>
- <span data-ttu-id="6d88c-317">Munkavállalási engedély száma</span><span class="sxs-lookup"><span data-stu-id="6d88c-317">Work Permit Number</span></span>

> [!NOTE]
> <span data-ttu-id="6d88c-318">A fizetési módhoz Mexikó támogatja a **Készpénzt**, **Csekket** (a vállalat fizikai csekkjét és az **Elektronikus fizetést**.</span><span class="sxs-lookup"><span data-stu-id="6d88c-318">For the payment method, Mexico supports **Cash**, **Check** (the company's physical check), and **Electronic Payment**.</span></span> <span data-ttu-id="6d88c-319">Ha nincs fizetési mód van megadva, alapértelmezés szerint a **Csekk** használt.</span><span class="sxs-lookup"><span data-stu-id="6d88c-319">If np payment method is specified, **Check** is used by default.</span></span>

#### <a name="employment-details"></a><span data-ttu-id="6d88c-320">Foglalkoztatás részletei</span><span class="sxs-lookup"><span data-stu-id="6d88c-320">Employment details</span></span>

<span data-ttu-id="6d88c-321">Foglalkoztatási előzményei kulcsfontosságú információkat tartalmaznak a munkavállaók felvételi, elbocsátási, és újbóli felvétele állapotával kapcsolatosan a Dayforce-ban.</span><span class="sxs-lookup"><span data-stu-id="6d88c-321">Employment detail history is used as key information to derive an employee's hire, termination, and rehire statuses in Dayforce.</span></span> <span data-ttu-id="6d88c-322">Dayforce egyszerre csak egy aktív foglalkoztatásrekordot tesz lehetővé.</span><span class="sxs-lookup"><span data-stu-id="6d88c-322">Dayforce supports only one active employment record at a time.</span></span>

- <span data-ttu-id="6d88c-323">Foglalkoztatás kezdődátuma (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-323">Employment start date (required)</span></span>
- <span data-ttu-id="6d88c-324">Munkaviszony záró dátuma</span><span class="sxs-lookup"><span data-stu-id="6d88c-324">Employment end date</span></span>
- <span data-ttu-id="6d88c-325">Kezdő dátum</span><span class="sxs-lookup"><span data-stu-id="6d88c-325">Start date</span></span>
- <span data-ttu-id="6d88c-326">Módosított kezdési időpont</span><span class="sxs-lookup"><span data-stu-id="6d88c-326">Adjusted start date</span></span>
- <span data-ttu-id="6d88c-327">Munkaviszony megszűnésének dátuma (megszűntetéskor kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-327">Termination date (required upon termination)</span></span>
- <span data-ttu-id="6d88c-328">Felmondás oka (megszűntetéskor kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-328">Termination reason (required upon termination)</span></span>

<span data-ttu-id="6d88c-329">Az alkalmazott legfontosabb dátumai a következő adatokból vannak származtatva.</span><span class="sxs-lookup"><span data-stu-id="6d88c-329">An employee's key dates are derived by using the following information.</span></span>

| <span data-ttu-id="6d88c-330">Talent</span><span class="sxs-lookup"><span data-stu-id="6d88c-330">Talent</span></span>                | <span data-ttu-id="6d88c-331">Dayforce</span><span class="sxs-lookup"><span data-stu-id="6d88c-331">Dayforce</span></span>                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="6d88c-332">Legutóbbi felvételi dátum</span><span class="sxs-lookup"><span data-stu-id="6d88c-332">Most recent hire date</span></span> | <span data-ttu-id="6d88c-333">Foglalkoztatás kezdete az aktuális nem megszűntetett előzményrekordra</span><span class="sxs-lookup"><span data-stu-id="6d88c-333">Employment start of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="6d88c-334">Munkaviszony megszűnésének dátuma</span><span class="sxs-lookup"><span data-stu-id="6d88c-334">Termination date</span></span>      | <span data-ttu-id="6d88c-335">Foglalkoztatás befejezése az aktuális nem megszűntetett előzményrekordra</span><span class="sxs-lookup"><span data-stu-id="6d88c-335">Termination date of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="6d88c-336">Kezdő dátum</span><span class="sxs-lookup"><span data-stu-id="6d88c-336">Start date</span></span>            | <span data-ttu-id="6d88c-337">Módosított kezdési időpont, kezdődátum vagy foglalkoztatás kezdete az aktuális nem aktív előzményrekordra</span><span class="sxs-lookup"><span data-stu-id="6d88c-337">Adjusted start date, start date, or employment start of current non-active employment history record</span></span> |
| <span data-ttu-id="6d88c-338">Eredeti felvételi dátum</span><span class="sxs-lookup"><span data-stu-id="6d88c-338">Original hire date</span></span>    | <span data-ttu-id="6d88c-339">Foglalkoztatás kezdete legkorábbi foglalkoztatási előzményrekordra</span><span class="sxs-lookup"><span data-stu-id="6d88c-339">Employment start of earliest employment history record</span></span>                                               |

#### <a name="compensation"></a><span data-ttu-id="6d88c-340">Kompenzáció</span><span class="sxs-lookup"><span data-stu-id="6d88c-340">Compensation</span></span>

<span data-ttu-id="6d88c-341">Egy fix kompenzációs tervet kell társítani minden alkalmazott elsődleges pozíciójához az alkalmazási időszak alatt.</span><span class="sxs-lookup"><span data-stu-id="6d88c-341">A fixed compensation plan must be associated with every employee's primary position throughout an employment period.</span></span> <span data-ttu-id="6d88c-342">Az időszak a belépés dátumával (vagy a foglalkoztatás kezdő dátumával) kezdődik, és a munkaviszony megszűnéséig tart .</span><span class="sxs-lookup"><span data-stu-id="6d88c-342">This period starts on the date that the employee was hired (or the employment start date) and continues until termination.</span></span>

- <span data-ttu-id="6d88c-343">Érvényesség dátuma (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-343">Effective Date (required)</span></span>
- <span data-ttu-id="6d88c-344">Lejárati dátum</span><span class="sxs-lookup"><span data-stu-id="6d88c-344">Expiration date</span></span>
- <span data-ttu-id="6d88c-345">Fizetési díjalap (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-345">Pay Rate (required)</span></span>
- <span data-ttu-id="6d88c-346">Fizetési díjalapok átalakításai (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-346">Pay Rate Conversions (required)</span></span>
- <span data-ttu-id="6d88c-347">Évi egyenérték (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-347">Annual equivalent (required)</span></span>
- <span data-ttu-id="6d88c-348">Óránkénti egyenérték (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-348">Hourly equivalent (required)</span></span>

<span data-ttu-id="6d88c-349">Ha az óránkénti alkalmazottnak több beosztása van, az elsődleges beosztásához tartozó fix kompenzációja importálva lesz a Dayforce-ba, alkalmazott szintű alapdíj/-fizetés.</span><span class="sxs-lookup"><span data-stu-id="6d88c-349">If an hourly employee has multiple positions, the fixed compensation of the primary position is imported into Dayforce as the employee-level base rate/salary.</span></span> <span data-ttu-id="6d88c-350">A nem elsődleges beosztások esetén, az óránkénti díj a megfelelő pozícióba lesz mentve Dayforce-ban.</span><span class="sxs-lookup"><span data-stu-id="6d88c-350">For non-primary positions, the hourly rate is saved to the corresponding position in Dayforce.</span></span>

<span data-ttu-id="6d88c-351">Ha a fizetett alkalmazott több beosztással rendelkezik, a összesített óradíj és éves fizetés származtatva lesz az összes aktív beosztásból mint az alkalmazotti szintű alapdíj/-fizetés.</span><span class="sxs-lookup"><span data-stu-id="6d88c-351">If a salaried employee has multiple positions, the cumulative hour rate and annual salary across all active positions are derived and used as the employee-level base rate/salary.</span></span>

#### <a name="identification-numbers"></a><span data-ttu-id="6d88c-352">Azonosítószámok</span><span class="sxs-lookup"><span data-stu-id="6d88c-352">Identification numbers</span></span>

##### <a name="social-security-identifier"></a><span data-ttu-id="6d88c-353">Társadalombiztosítási azonosító</span><span class="sxs-lookup"><span data-stu-id="6d88c-353">Social Security identifier</span></span> 

<span data-ttu-id="6d88c-354">Minden alkalmazottnak kell egy elsődleges azonosítóval rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="6d88c-354">Every employee must have one primary identifier.</span></span> <span data-ttu-id="6d88c-355">Ez az azonosító legyen **TAJ-szám** azonosítótípus kell legyen.</span><span class="sxs-lookup"><span data-stu-id="6d88c-355">This identifier must be of **SSN** identification type.</span></span> <span data-ttu-id="6d88c-356">A Dayforce-ban automatikusan van származtatva az alkalmazott társadalombiztosítási azonosítójából, mely a felvételhez szükséges.</span><span class="sxs-lookup"><span data-stu-id="6d88c-356">In Dayforce, it's automatically derived as the employee's Social Security identifier that is required for hire.</span></span>

- <span data-ttu-id="6d88c-357">Elsődleges (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-357">Primary (required)</span></span>
- <span data-ttu-id="6d88c-358">Azonosító típusa = „TAJ-szám”</span><span class="sxs-lookup"><span data-stu-id="6d88c-358">Identification Type = "SSN"</span></span>
- <span data-ttu-id="6d88c-359">Kibocsátás dátuma</span><span class="sxs-lookup"><span data-stu-id="6d88c-359">Issued Date</span></span>
- <span data-ttu-id="6d88c-360">Lejárat dátuma</span><span class="sxs-lookup"><span data-stu-id="6d88c-360">Expiration Date</span></span>

<span data-ttu-id="6d88c-361">Az alkalmazottak több azonosítószámot is megadhatnak **TAJ-szám** azonosítótípushoz.</span><span class="sxs-lookup"><span data-stu-id="6d88c-361">Employees can declare multiple identification numbers of the **SSN** identification type.</span></span> <span data-ttu-id="6d88c-362">Azonban csak az **Elsődlegesként** megjelölt rekord van integrálva Dayforce-ba, függetlenül attól, hogy a szám aktív vagy lejárt.</span><span class="sxs-lookup"><span data-stu-id="6d88c-362">However, only the record that is marked as **Primary** is integrated into Dayforce, regardless of whether the number is active or expired.</span></span>

#### <a name="bank-accounts-and-disbursements"></a><span data-ttu-id="6d88c-363">Bankszámlák és kifizetések</span><span class="sxs-lookup"><span data-stu-id="6d88c-363">Bank accounts and disbursements</span></span>

<span data-ttu-id="6d88c-364">Érvényes bankszámlaadatokat meg kell adni minden olyan alkalmazotthoz, aki úgy dönt, hogy a banki átutalással kéri fizetését.</span><span class="sxs-lookup"><span data-stu-id="6d88c-364">Valid bank account information must be entered for any employee who chooses to be paid via bank account transfers.</span></span>

| <span data-ttu-id="6d88c-365">Talent</span><span class="sxs-lookup"><span data-stu-id="6d88c-365">Talent</span></span>                         | <span data-ttu-id="6d88c-366">Dayforce</span><span class="sxs-lookup"><span data-stu-id="6d88c-366">Dayforce</span></span>                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="6d88c-367">Bankszámlaszám (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-367">Bank account number (required)</span></span> |                                                                                                             |
| <span data-ttu-id="6d88c-368">SWIFT-kód (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-368">SWIFT code (required)</span></span>          | <span data-ttu-id="6d88c-369">**Bankazonosító** ez a mező Mexikóban történő bérlistafeldolgozáskor használatos.</span><span class="sxs-lookup"><span data-stu-id="6d88c-369">**Bank ID** field used when processing payroll in Mexico.</span></span>                                                             |
| <span data-ttu-id="6d88c-370">Ágazati szám (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-370">Branch number (required)</span></span>       |                                                                                                             |
| <span data-ttu-id="6d88c-371">Bankszámla típusa (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-371">Bank account type (required)</span></span>   | <span data-ttu-id="6d88c-372">**Számlatípus** ez a mező Mexikóban történő bérlistafeldolgozáskor használatos.</span><span class="sxs-lookup"><span data-stu-id="6d88c-372">**Account type** field used when processing payroll in Mexico.</span></span> <span data-ttu-id="6d88c-373">Támogatott értékek: **Folyószámla** és **Bérlista**</span><span class="sxs-lookup"><span data-stu-id="6d88c-373">Supported values include **Checking** and **Payroll**.</span></span> |

> [!NOTE]
> <span data-ttu-id="6d88c-374">Alkalmazottak, akik úgy döntenek, hogy a banki átutaláson keresztülkérik fizetésük, meg kell adniuk egy hivatkozást egy jogi személyhez tartozó egyenlegszámlához, melynek elsődleges címének Mexikóban kell lennie és egy Mexikói bank érvényes bankszámlájához van társítva.</span><span class="sxs-lookup"><span data-stu-id="6d88c-374">Employees who choose to be paid via bank account transfers must provide a link to a remainder account that is under a legal entity that has its primary address in Mexico and associated with a valid bank account from a Mexican bank.</span></span> <span data-ttu-id="6d88c-375">Minden egyéb nem egyenlegszámla figyelmen kívül lesz hagyva.</span><span class="sxs-lookup"><span data-stu-id="6d88c-375">All other non-remainder accounts are ignored.</span></span>

#### <a name="address-information"></a><span data-ttu-id="6d88c-376">Címadatok</span><span class="sxs-lookup"><span data-stu-id="6d88c-376">Address information</span></span>

<span data-ttu-id="6d88c-377">Minden alkalmazottnak kell egy elsődleges hellyel rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="6d88c-377">Every employee must have one primary location.</span></span> <span data-ttu-id="6d88c-378">A Dayforce-ban ezen hely alapján van meghatározva az alkalmazott elsődleges tartózkodási helye adózási célokból.</span><span class="sxs-lookup"><span data-stu-id="6d88c-378">In Dayforce, this location is used to determine the employee's primary residence for tax purposes.</span></span>

- <span data-ttu-id="6d88c-379">Elsődleges (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-379">Primary (required)</span></span>
- <span data-ttu-id="6d88c-380">Ország/régiót (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-380">Country/region (required)</span></span>
- <span data-ttu-id="6d88c-381">Irányítószám/postai kód (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-381">Zip/postal code (required)</span></span>
- <span data-ttu-id="6d88c-382">Utca (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-382">Street (required)</span></span>
- <span data-ttu-id="6d88c-383">Házszám (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-383">Street Number (required)</span></span>
- <span data-ttu-id="6d88c-384">Épületblokk</span><span class="sxs-lookup"><span data-stu-id="6d88c-384">Building Complement</span></span>
- <span data-ttu-id="6d88c-385">Város (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-385">City (required)</span></span>
- <span data-ttu-id="6d88c-386">Állam (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-386">State (required)</span></span>
- <span data-ttu-id="6d88c-387">Megye (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-387">County (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a><span data-ttu-id="6d88c-388">Az adatok konfigurálása bérlista létrehozásához az Egyesült Államokban és Kanadában</span><span class="sxs-lookup"><span data-stu-id="6d88c-388">Configure your data to generate payroll in United States and Canada</span></span>

<span data-ttu-id="6d88c-389">Ha a fizetést generálása alkalmazottaknak az Egyesült Államokban és Kanadában, a következő elemeket kell beállítani:</span><span class="sxs-lookup"><span data-stu-id="6d88c-389">If you're generating pay for employees in the United States and Canada, the following elements must be configured:</span></span>

- <span data-ttu-id="6d88c-390">Részlegek szükségesek beosztásokhoz.</span><span class="sxs-lookup"><span data-stu-id="6d88c-390">Departments are required on positions.</span></span>
- <span data-ttu-id="6d88c-391">Költséghelyek pénzügyi dimenziókként kell beállítani, és az alapértelmezett pénzügyi dimenzió karakterlánc első elemének kell lennie.</span><span class="sxs-lookup"><span data-stu-id="6d88c-391">Cost centers must be set as financial dimensions and must be the first element in the default financial dimension string.</span></span>

> [!NOTE] 
> <span data-ttu-id="6d88c-392">Beállíthatja a Talent szolgáltatást úgy, hogy a Beosztásokhoz kötelező legyen beállítani Részleget.</span><span class="sxs-lookup"><span data-stu-id="6d88c-392">You can configure Talent to require that Positions specify a Department.</span></span> <span data-ttu-id="6d88c-393">Ehhez kattintson a **Emberi erőforrások megosztott beosztásai > Beosztások > Részlegek szükségesek beosztásokhoz.** elemre.</span><span class="sxs-lookup"><span data-stu-id="6d88c-393">To do this, go to **Human Resources Shared Positions > Positions > Require departments on positions**.</span></span> <span data-ttu-id="6d88c-394">Azt ajánljuk, hogy ezt a beállítást tartassa be az integráció során.</span><span class="sxs-lookup"><span data-stu-id="6d88c-394">We recommend that this setting be enforced for the integration.</span></span>

### <a name="job-types"></a><span data-ttu-id="6d88c-395">Feladattípusok</span><span class="sxs-lookup"><span data-stu-id="6d88c-395">Job types</span></span>

<span data-ttu-id="6d88c-396">Beosztástípusok használatával a hasonló feladatok kategóriákba sorolhatók.</span><span class="sxs-lookup"><span data-stu-id="6d88c-396">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="6d88c-397">A beosztástípusok szükségesek az Egyesült Államokban és Kanadában a bérlisták feldolgozásához.</span><span class="sxs-lookup"><span data-stu-id="6d88c-397">Job types are required in order to process payroll in the United States and Canada.</span></span> <span data-ttu-id="6d88c-398">Beosztástípusok többek között a teljes és részmunkaidős, illetve a munkabéres és az órabéres.</span><span class="sxs-lookup"><span data-stu-id="6d88c-398">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="6d88c-399">A beosztástípusok a fizetéstípusokként vannak hozzárendelve a Dayforce-hoz, melyek jelzik, hogy a munkavállaló órás vagy bérezéses.</span><span class="sxs-lookup"><span data-stu-id="6d88c-399">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="6d88c-400">A következő feladattípusok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="6d88c-400">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="6d88c-401">Feladattípus</span><span class="sxs-lookup"><span data-stu-id="6d88c-401">Job type</span></span>   | <span data-ttu-id="6d88c-402">Leírás</span><span class="sxs-lookup"><span data-stu-id="6d88c-402">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="6d88c-403">Óránként</span><span class="sxs-lookup"><span data-stu-id="6d88c-403">Hourly</span></span>     | <span data-ttu-id="6d88c-404">Óránként</span><span class="sxs-lookup"><span data-stu-id="6d88c-404">Hourly</span></span>      |
| <span data-ttu-id="6d88c-405">Bérezéses</span><span class="sxs-lookup"><span data-stu-id="6d88c-405">Salaried</span></span>   | <span data-ttu-id="6d88c-406">Bérezéses</span><span class="sxs-lookup"><span data-stu-id="6d88c-406">Salaried</span></span>    |

### <a name="position-types"></a><span data-ttu-id="6d88c-407">Beosztási típusok</span><span class="sxs-lookup"><span data-stu-id="6d88c-407">Position types</span></span> 

<span data-ttu-id="6d88c-408">Ne használjon beosztástípusokat annak leírására, hogy a beosztás teljes munkaidős, részmunkaidős vagy más.</span><span class="sxs-lookup"><span data-stu-id="6d88c-408">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="6d88c-409">A feladattípusok a fizetésosztályokként vannak hozzárendelve a Dayforce-hoz, melyek jelzik, hogy a munkavállaló teljes- vagy részmunkaidős.</span><span class="sxs-lookup"><span data-stu-id="6d88c-409">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="6d88c-410">A következő beosztástípusok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="6d88c-410">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="6d88c-411">Beosztás típusa</span><span class="sxs-lookup"><span data-stu-id="6d88c-411">Position type</span></span>   | <span data-ttu-id="6d88c-412">Leírás</span><span class="sxs-lookup"><span data-stu-id="6d88c-412">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="6d88c-413">Teljes munkaidős</span><span class="sxs-lookup"><span data-stu-id="6d88c-413">Full-time</span></span>       | <span data-ttu-id="6d88c-414">Teljes munkaidős alkalmazott</span><span class="sxs-lookup"><span data-stu-id="6d88c-414">Full time employee</span></span> |
| <span data-ttu-id="6d88c-415">Részmunkaidős</span><span class="sxs-lookup"><span data-stu-id="6d88c-415">Part-time</span></span>       | <span data-ttu-id="6d88c-416">Részmunkaidős alkalmazott</span><span class="sxs-lookup"><span data-stu-id="6d88c-416">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="6d88c-417">Okkódok</span><span class="sxs-lookup"><span data-stu-id="6d88c-417">Reason codes</span></span>

<span data-ttu-id="6d88c-418">Az alkalmazottak állapotával kapcsolatos okkódok tájékoztatnak.</span><span class="sxs-lookup"><span data-stu-id="6d88c-418">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="6d88c-419">Okkódok a Dayforce-hoz állapot okaként vannak hozzárendelve, melyek jelzik egy alkalmazott beosztásában vagy alkalmazotti státuszában bekövetkezett változások okát.</span><span class="sxs-lookup"><span data-stu-id="6d88c-419">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="6d88c-420">A következő okkódok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="6d88c-420">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="6d88c-421">Okkód</span><span class="sxs-lookup"><span data-stu-id="6d88c-421">Reason code</span></span>    | <span data-ttu-id="6d88c-422">Leírás</span><span class="sxs-lookup"><span data-stu-id="6d88c-422">Description</span></span>      | <span data-ttu-id="6d88c-423">Alkalmazandó forgatókönyvek</span><span class="sxs-lookup"><span data-stu-id="6d88c-423">Applicable scenarios</span></span> |
|----------------|------------------|----------------------|
| <span data-ttu-id="6d88c-424">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="6d88c-424">RESIGNATION</span></span>    | <span data-ttu-id="6d88c-425">Felmondás</span><span class="sxs-lookup"><span data-stu-id="6d88c-425">Resignation</span></span>      | <span data-ttu-id="6d88c-426">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="6d88c-426">Terminate worker</span></span>     |
| <span data-ttu-id="6d88c-427">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="6d88c-427">TERMINATION</span></span>    | <span data-ttu-id="6d88c-428">Befejezés</span><span class="sxs-lookup"><span data-stu-id="6d88c-428">Termination</span></span>      | <span data-ttu-id="6d88c-429">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="6d88c-429">Terminate worker</span></span>     |
| <span data-ttu-id="6d88c-430">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="6d88c-430">RETIREMENT</span></span>     | <span data-ttu-id="6d88c-431">Megszüntetés</span><span class="sxs-lookup"><span data-stu-id="6d88c-431">Retirement</span></span>       | <span data-ttu-id="6d88c-432">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="6d88c-432">Terminate worker</span></span>     |
| <span data-ttu-id="6d88c-433">EGYÉB</span><span class="sxs-lookup"><span data-stu-id="6d88c-433">OTHER</span></span>          | <span data-ttu-id="6d88c-434">Egyéb okok</span><span class="sxs-lookup"><span data-stu-id="6d88c-434">Other Reasons</span></span>    | <span data-ttu-id="6d88c-435">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="6d88c-435">Terminate worker</span></span>     |
| <span data-ttu-id="6d88c-436">DEATH</span><span class="sxs-lookup"><span data-stu-id="6d88c-436">DEATH</span></span>          | <span data-ttu-id="6d88c-437">Elhalálozás</span><span class="sxs-lookup"><span data-stu-id="6d88c-437">Death</span></span>            | <span data-ttu-id="6d88c-438">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="6d88c-438">Terminate worker</span></span>     |
| <span data-ttu-id="6d88c-439">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="6d88c-439">LEAVEOFABSENCE</span></span> | <span data-ttu-id="6d88c-440">Szabadság</span><span class="sxs-lookup"><span data-stu-id="6d88c-440">Leave of Absence</span></span> | <span data-ttu-id="6d88c-441">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="6d88c-441">Terminate worker</span></span>     |
| <span data-ttu-id="6d88c-442">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="6d88c-442">CONTRACTEND</span></span>    | <span data-ttu-id="6d88c-443">Szerződés vége</span><span class="sxs-lookup"><span data-stu-id="6d88c-443">End of Contract</span></span>  | <span data-ttu-id="6d88c-444">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="6d88c-444">Terminate worker</span></span>     |
| <span data-ttu-id="6d88c-445">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="6d88c-445">SALARYCHANGE</span></span>   | <span data-ttu-id="6d88c-446">Munkabér módosítása</span><span class="sxs-lookup"><span data-stu-id="6d88c-446">Change of Salary</span></span> | <span data-ttu-id="6d88c-447">Kompenzáció</span><span class="sxs-lookup"><span data-stu-id="6d88c-447">Compensation</span></span>         |

### <a name="marital-status"></a><span data-ttu-id="6d88c-448">Családi állapot</span><span class="sxs-lookup"><span data-stu-id="6d88c-448">Marital status</span></span>

<span data-ttu-id="6d88c-449">Családi állapot értékei Dayforce-hoz vannak rendelve és konvertálva szükség esetén az elfogadható értékekre az integráció során.</span><span class="sxs-lookup"><span data-stu-id="6d88c-449">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="6d88c-450">Az alábbi táblázat bemutatja, hogy családi állapot értékek hogyan vannak leképezve a Dayforce -ban.</span><span class="sxs-lookup"><span data-stu-id="6d88c-450">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="6d88c-451">Talent</span><span class="sxs-lookup"><span data-stu-id="6d88c-451">Talent</span></span>                 | <span data-ttu-id="6d88c-452">Dayforce</span><span class="sxs-lookup"><span data-stu-id="6d88c-452">Dayforce</span></span>             |
|------------------------|----------------------|
| <span data-ttu-id="6d88c-453">Házas</span><span class="sxs-lookup"><span data-stu-id="6d88c-453">Married</span></span>                | <span data-ttu-id="6d88c-454">Házas</span><span class="sxs-lookup"><span data-stu-id="6d88c-454">Married</span></span>              |
| <span data-ttu-id="6d88c-455">Egy</span><span class="sxs-lookup"><span data-stu-id="6d88c-455">Single</span></span>                 | <span data-ttu-id="6d88c-456">Egy</span><span class="sxs-lookup"><span data-stu-id="6d88c-456">Single</span></span>               |
| <span data-ttu-id="6d88c-457">Özvegy</span><span class="sxs-lookup"><span data-stu-id="6d88c-457">Widowed</span></span>                | <span data-ttu-id="6d88c-458">Özvegy</span><span class="sxs-lookup"><span data-stu-id="6d88c-458">Widowed</span></span>              |
| <span data-ttu-id="6d88c-459">Elvált</span><span class="sxs-lookup"><span data-stu-id="6d88c-459">Divorced</span></span>               | <span data-ttu-id="6d88c-460">Elvált</span><span class="sxs-lookup"><span data-stu-id="6d88c-460">Divorced</span></span>             |
| <span data-ttu-id="6d88c-461">Bejegyzett élettársi kapcsolat</span><span class="sxs-lookup"><span data-stu-id="6d88c-461">Registered Partnership</span></span> | <span data-ttu-id="6d88c-462">Élettársi viszony</span><span class="sxs-lookup"><span data-stu-id="6d88c-462">Domestic Partnership</span></span> |
| <span data-ttu-id="6d88c-463">Nincs</span><span class="sxs-lookup"><span data-stu-id="6d88c-463">None</span></span>                   | <span data-ttu-id="6d88c-464">Nincs</span><span class="sxs-lookup"><span data-stu-id="6d88c-464">None</span></span>                 |
| <span data-ttu-id="6d88c-465">Együttélés</span><span class="sxs-lookup"><span data-stu-id="6d88c-465">Cohabiting</span></span>             | <span data-ttu-id="6d88c-466">Együttélés</span><span class="sxs-lookup"><span data-stu-id="6d88c-466">Cohabiting</span></span>           |

### <a name="gender"></a><span data-ttu-id="6d88c-467">Nem</span><span class="sxs-lookup"><span data-stu-id="6d88c-467">Gender</span></span>

<span data-ttu-id="6d88c-468">A nemek a Dayforce-hoz vannak rendelve és konvertálva szükség esetén az elfogadható értékekre az integráció során.</span><span class="sxs-lookup"><span data-stu-id="6d88c-468">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="6d88c-469">Az alábbi táblázat bemutatja, hogy a nemek hogyan vannak leképezve a Dayforce-ban.</span><span class="sxs-lookup"><span data-stu-id="6d88c-469">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="6d88c-470">Talent</span><span class="sxs-lookup"><span data-stu-id="6d88c-470">Talent</span></span>       | <span data-ttu-id="6d88c-471">Dayforce</span><span class="sxs-lookup"><span data-stu-id="6d88c-471">Dayforce</span></span>        |
|--------------|-----------------|
| <span data-ttu-id="6d88c-472">Férfi</span><span class="sxs-lookup"><span data-stu-id="6d88c-472">Male</span></span>         | <span data-ttu-id="6d88c-473">Férfi</span><span class="sxs-lookup"><span data-stu-id="6d88c-473">Male</span></span>            |
| <span data-ttu-id="6d88c-474">Nő</span><span class="sxs-lookup"><span data-stu-id="6d88c-474">Female</span></span>       | <span data-ttu-id="6d88c-475">Nő</span><span class="sxs-lookup"><span data-stu-id="6d88c-475">Female</span></span>          |
| <span data-ttu-id="6d88c-476">Nem meghatározott</span><span class="sxs-lookup"><span data-stu-id="6d88c-476">Non-specific</span></span> | <span data-ttu-id="6d88c-477">*Nem támogatott*</span><span class="sxs-lookup"><span data-stu-id="6d88c-477">*Not supported*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="6d88c-478">Bevételkódok</span><span class="sxs-lookup"><span data-stu-id="6d88c-478">Earning codes</span></span>

<span data-ttu-id="6d88c-479">A bevételkódok egyedi módon azonosítják a dolgozók által kapott fizetéstípusokat.</span><span class="sxs-lookup"><span data-stu-id="6d88c-479">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="6d88c-480">A kódoknak különböző paramétereket fednek le, amelyek a bevételekhez kapcsolódnak, például könyvelési szabályok, jelentési követelmények és bruttósítási lehetőségek.</span><span class="sxs-lookup"><span data-stu-id="6d88c-480">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="6d88c-481">Ha egy nem támogatott gyakoriság van használatban, a **Minden fizetés** gyakorisága van alapértelmezés szerint használva a kiszámításhoz.</span><span class="sxs-lookup"><span data-stu-id="6d88c-481">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="6d88c-482">Támogatott gyakoriságok</span><span class="sxs-lookup"><span data-stu-id="6d88c-482">Supported frequencies</span></span>

- <span data-ttu-id="6d88c-483">Összes</span><span class="sxs-lookup"><span data-stu-id="6d88c-483">All</span></span>
- <span data-ttu-id="6d88c-484">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="6d88c-484">EVERYPAY</span></span>
- <span data-ttu-id="6d88c-485">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="6d88c-485">EACHPAYPERIOD</span></span>
- <span data-ttu-id="6d88c-486">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="6d88c-486">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="6d88c-487">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="6d88c-487">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="6d88c-488">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="6d88c-488">1OFMTH</span></span>
- <span data-ttu-id="6d88c-489">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="6d88c-489">LASTOFMTH</span></span>
- <span data-ttu-id="6d88c-490">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="6d88c-490">2OFMTH</span></span>
- <span data-ttu-id="6d88c-491">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="6d88c-491">3OFMTH</span></span>
- <span data-ttu-id="6d88c-492">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6d88c-492">4OFMTH</span></span>
- <span data-ttu-id="6d88c-493">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="6d88c-493">5OFMTH</span></span>
- <span data-ttu-id="6d88c-494">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="6d88c-494">1N2OFMTH</span></span>
- <span data-ttu-id="6d88c-495">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6d88c-495">3N4OFMTH</span></span>
- <span data-ttu-id="6d88c-496">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="6d88c-496">1N3OFMTH</span></span>
- <span data-ttu-id="6d88c-497">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6d88c-497">1N4OFMTH</span></span>
- <span data-ttu-id="6d88c-498">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="6d88c-498">2N3OFMTH</span></span>
- <span data-ttu-id="6d88c-499">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6d88c-499">2N4OFMTH</span></span>
- <span data-ttu-id="6d88c-500">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="6d88c-500">1N2N3OFMTH</span></span>
- <span data-ttu-id="6d88c-501">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6d88c-501">1N2N4OFMTH</span></span>
- <span data-ttu-id="6d88c-502">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6d88c-502">1N3N4OFMTH</span></span>
- <span data-ttu-id="6d88c-503">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6d88c-503">2N3N4OFMTH</span></span>
- <span data-ttu-id="6d88c-504">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6d88c-504">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="6d88c-505">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="6d88c-505">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="6d88c-506">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="6d88c-506">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="6d88c-507">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="6d88c-507">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="6d88c-508">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="6d88c-508">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="6d88c-509">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="6d88c-509">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="6d88c-510">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="6d88c-510">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="6d88c-511">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="6d88c-511">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="6d88c-512">Címek</span><span class="sxs-lookup"><span data-stu-id="6d88c-512">Addresses</span></span>

<span data-ttu-id="6d88c-513">Az adott ország vagy régió, állam és megye (település) kódok specifikus formátumokat követelnek, hogy Dayforce és az országos és regionális szolgáltatók felismerjék azokat.</span><span class="sxs-lookup"><span data-stu-id="6d88c-513">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="6d88c-514">Annak ellenére, hogy a városok formátuma rugalmas, minden városnak társítva kell lennie egy államhoz.</span><span class="sxs-lookup"><span data-stu-id="6d88c-514">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="6d88c-515">Talent</span><span class="sxs-lookup"><span data-stu-id="6d88c-515">Talent</span></span>          | <span data-ttu-id="6d88c-516">Dayforce</span><span class="sxs-lookup"><span data-stu-id="6d88c-516">Dayforce</span></span>              |
|-----------------|-----------------------|
| <span data-ttu-id="6d88c-517">Ország/régió</span><span class="sxs-lookup"><span data-stu-id="6d88c-517">Country/Region</span></span>  | <span data-ttu-id="6d88c-518">Országkód</span><span class="sxs-lookup"><span data-stu-id="6d88c-518">Country Code</span></span>          |
| <span data-ttu-id="6d88c-519">Irányítószám / postai kód</span><span class="sxs-lookup"><span data-stu-id="6d88c-519">Zip/Postal Code</span></span> | <span data-ttu-id="6d88c-520">Irányítószám</span><span class="sxs-lookup"><span data-stu-id="6d88c-520">Postal Code</span></span>           |
| <span data-ttu-id="6d88c-521">Állami</span><span class="sxs-lookup"><span data-stu-id="6d88c-521">State</span></span>           | <span data-ttu-id="6d88c-522">Államkód</span><span class="sxs-lookup"><span data-stu-id="6d88c-522">State Code</span></span>            |
| <span data-ttu-id="6d88c-523">Város</span><span class="sxs-lookup"><span data-stu-id="6d88c-523">City</span></span>            | <span data-ttu-id="6d88c-524">Város</span><span class="sxs-lookup"><span data-stu-id="6d88c-524">City</span></span>                  |
| <span data-ttu-id="6d88c-525">Megye</span><span class="sxs-lookup"><span data-stu-id="6d88c-525">County</span></span>          | <span data-ttu-id="6d88c-526">Megye (Helyhatóság)</span><span class="sxs-lookup"><span data-stu-id="6d88c-526">County (Municipality)</span></span> |
| <span data-ttu-id="6d88c-527">Utca</span><span class="sxs-lookup"><span data-stu-id="6d88c-527">Street</span></span>          | <span data-ttu-id="6d88c-528">Cím 1. sora</span><span class="sxs-lookup"><span data-stu-id="6d88c-528">Address Line 1</span></span>        |

### <a name="tax-regions"></a><span data-ttu-id="6d88c-529">Adórégiók</span><span class="sxs-lookup"><span data-stu-id="6d88c-529">Tax regions</span></span>

<span data-ttu-id="6d88c-530">Az adórégiók a megfelelő adó megállapítására szolgálnak, amelyet a bérlista létrehozásakor kell alkalmazni.</span><span class="sxs-lookup"><span data-stu-id="6d88c-530">Tax regions are used to determine the appropriate tax that should be applied during payroll generation.</span></span> <span data-ttu-id="6d88c-531">Az adórégiók helycímként vannak a Dayforce-hoz rendelve.</span><span class="sxs-lookup"><span data-stu-id="6d88c-531">Tax regions are mapped to Dayforce as location addresses.</span></span> <span data-ttu-id="6d88c-532">Az alapértelmezett adórégiót a dolgozó aktív beosztásával kell társítani.</span><span class="sxs-lookup"><span data-stu-id="6d88c-532">The default tax region must be associated with the worker's active position.</span></span> 

- <span data-ttu-id="6d88c-533">Adórégió (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-533">Tax region (required)</span></span>
- <span data-ttu-id="6d88c-534">Ország/régió (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-534">Country/Region (required)</span></span>
- <span data-ttu-id="6d88c-535">Állam (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-535">State (required)</span></span>
- <span data-ttu-id="6d88c-536">Megye</span><span class="sxs-lookup"><span data-stu-id="6d88c-536">County</span></span> 
- <span data-ttu-id="6d88c-537">Város (kötelező)</span><span class="sxs-lookup"><span data-stu-id="6d88c-537">City (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a><span data-ttu-id="6d88c-538">Adatok konfigurálása bérlista létrehozásához Mexikóban</span><span class="sxs-lookup"><span data-stu-id="6d88c-538">Configure your data to generate payroll in Mexico</span></span>

<span data-ttu-id="6d88c-539">Ha a fizetést generál alkalmazottaknak Mexikóban, a következő elemeket kell beállítani:</span><span class="sxs-lookup"><span data-stu-id="6d88c-539">If you're generating pay for employees in Mexico, the following elements must be configured:</span></span>

- <span data-ttu-id="6d88c-540">Részlegek szükségesek beosztásokhoz.</span><span class="sxs-lookup"><span data-stu-id="6d88c-540">Departments are required on positions.</span></span>
- <span data-ttu-id="6d88c-541">Költséghelyek pénzügyi dimenziókként kell beállítani, és az Alapértelmezett pénzügyi dimenzió karakterlánc első elemének kell lennie.</span><span class="sxs-lookup"><span data-stu-id="6d88c-541">Cost centers must be set as financial dimensions and must be the first element in the Default Financial Dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="6d88c-542">Beosztástípusok</span><span class="sxs-lookup"><span data-stu-id="6d88c-542">Job types</span></span>

<span data-ttu-id="6d88c-543">Beosztástípusok használatával a hasonló feladatok kategóriákba sorolhatók.</span><span class="sxs-lookup"><span data-stu-id="6d88c-543">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="6d88c-544">Mexikóban a Bérlista feldolgozásához feladattípusok szükségesek.</span><span class="sxs-lookup"><span data-stu-id="6d88c-544">Job types are required in order to process payroll in Mexico.</span></span> <span data-ttu-id="6d88c-545">Beosztástípusok többek között a teljes és részmunkaidős, illetve a munkabéres és az órabéres.</span><span class="sxs-lookup"><span data-stu-id="6d88c-545">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="6d88c-546">A beosztástípusok a fizetéstípusokként vannak hozzárendelve a Dayforce-hoz, melyek jelzik, hogy a munkavállaló órás vagy bérezéses.</span><span class="sxs-lookup"><span data-stu-id="6d88c-546">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="6d88c-547">A következő feladattípusok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="6d88c-547">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="6d88c-548">Feladattípus</span><span class="sxs-lookup"><span data-stu-id="6d88c-548">Job type</span></span>   | <span data-ttu-id="6d88c-549">Leírás</span><span class="sxs-lookup"><span data-stu-id="6d88c-549">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="6d88c-550">Óránként</span><span class="sxs-lookup"><span data-stu-id="6d88c-550">Hourly</span></span>     | <span data-ttu-id="6d88c-551">MX Órabér</span><span class="sxs-lookup"><span data-stu-id="6d88c-551">MX Hourly</span></span>   |
| <span data-ttu-id="6d88c-552">Bérezéses</span><span class="sxs-lookup"><span data-stu-id="6d88c-552">Salaried</span></span>   | <span data-ttu-id="6d88c-553">MX Bérezéses</span><span class="sxs-lookup"><span data-stu-id="6d88c-553">MX Salaried</span></span> |

### <a name="position-types"></a><span data-ttu-id="6d88c-554">Beosztási típusok</span><span class="sxs-lookup"><span data-stu-id="6d88c-554">Position types</span></span> 

<span data-ttu-id="6d88c-555">Ne használjon beosztástípusokat annak leírására, hogy a beosztás teljes munkaidős, részmunkaidős vagy más.</span><span class="sxs-lookup"><span data-stu-id="6d88c-555">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="6d88c-556">A feladattípusok a fizetésosztályokként vannak hozzárendelve a Dayforce-hoz, melyek jelzik, hogy a munkavállaló teljes- vagy részmunkaidős.</span><span class="sxs-lookup"><span data-stu-id="6d88c-556">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="6d88c-557">A következő beosztástípusok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="6d88c-557">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="6d88c-558">Beosztás típusa</span><span class="sxs-lookup"><span data-stu-id="6d88c-558">Position type</span></span>   | <span data-ttu-id="6d88c-559">Leírás</span><span class="sxs-lookup"><span data-stu-id="6d88c-559">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="6d88c-560">Teljes munkaidős</span><span class="sxs-lookup"><span data-stu-id="6d88c-560">Full-time</span></span>       | <span data-ttu-id="6d88c-561">Teljes munkaidős alkalmazott</span><span class="sxs-lookup"><span data-stu-id="6d88c-561">Full time employee</span></span> |
| <span data-ttu-id="6d88c-562">Részmunkaidős</span><span class="sxs-lookup"><span data-stu-id="6d88c-562">Part-time</span></span>       | <span data-ttu-id="6d88c-563">Részmunkaidős alkalmazott</span><span class="sxs-lookup"><span data-stu-id="6d88c-563">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="6d88c-564">Okkódok</span><span class="sxs-lookup"><span data-stu-id="6d88c-564">Reason codes</span></span>

<span data-ttu-id="6d88c-565">Az alkalmazottak állapotával kapcsolatos okkódok tájékoztatnak.</span><span class="sxs-lookup"><span data-stu-id="6d88c-565">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="6d88c-566">Okkódok a Dayforce-hoz állapot okaként vannak hozzárendelve, melyek jelzik egy alkalmazott beosztásában vagy alkalmazotti státuszában bekövetkezett változások okát.</span><span class="sxs-lookup"><span data-stu-id="6d88c-566">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="6d88c-567">A következő okkódok és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="6d88c-567">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="6d88c-568">Okkód</span><span class="sxs-lookup"><span data-stu-id="6d88c-568">Reason code</span></span>            | <span data-ttu-id="6d88c-569">Leírás</span><span class="sxs-lookup"><span data-stu-id="6d88c-569">Description</span></span>                    | <span data-ttu-id="6d88c-570">Alkalmazandó forgatókönyvek</span><span class="sxs-lookup"><span data-stu-id="6d88c-570">Applicable scenarios</span></span> |
|------------------------|--------------------------------|----------------------|
| <span data-ttu-id="6d88c-571">DEPARTUREBEFOREPAYMENT</span><span class="sxs-lookup"><span data-stu-id="6d88c-571">DEPARTUREBEFOREPAYMENT</span></span> | <span data-ttu-id="6d88c-572">Indulás első bérlista előtt</span><span class="sxs-lookup"><span data-stu-id="6d88c-572">Departure before first payroll</span></span> | <span data-ttu-id="6d88c-573">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="6d88c-573">Terminate worker</span></span>     |
| <span data-ttu-id="6d88c-574">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="6d88c-574">RESIGNATION</span></span>            | <span data-ttu-id="6d88c-575">Felmondás</span><span class="sxs-lookup"><span data-stu-id="6d88c-575">Resignation</span></span>                    | <span data-ttu-id="6d88c-576">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="6d88c-576">Terminate worker</span></span>     |
| <span data-ttu-id="6d88c-577">PENSION</span><span class="sxs-lookup"><span data-stu-id="6d88c-577">PENSION</span></span>                | <span data-ttu-id="6d88c-578">Nyugdíj</span><span class="sxs-lookup"><span data-stu-id="6d88c-578">Pension</span></span>                        | <span data-ttu-id="6d88c-579">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="6d88c-579">Terminate worker</span></span>     |
| <span data-ttu-id="6d88c-580">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="6d88c-580">TERMINATION</span></span>            | <span data-ttu-id="6d88c-581">Befejezés</span><span class="sxs-lookup"><span data-stu-id="6d88c-581">Termination</span></span>                    | <span data-ttu-id="6d88c-582">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="6d88c-582">Terminate worker</span></span>     |
| <span data-ttu-id="6d88c-583">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="6d88c-583">RETIREMENT</span></span>             | <span data-ttu-id="6d88c-584">Megszüntetés</span><span class="sxs-lookup"><span data-stu-id="6d88c-584">Retirement</span></span>                     | <span data-ttu-id="6d88c-585">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="6d88c-585">Terminate worker</span></span>     |
| <span data-ttu-id="6d88c-586">ABSENTEE</span><span class="sxs-lookup"><span data-stu-id="6d88c-586">ABSENTEE</span></span>               | <span data-ttu-id="6d88c-587">Távollevő</span><span class="sxs-lookup"><span data-stu-id="6d88c-587">Absentee</span></span>                       | <span data-ttu-id="6d88c-588">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="6d88c-588">Terminate worker</span></span>     |
| <span data-ttu-id="6d88c-589">EGYÉB</span><span class="sxs-lookup"><span data-stu-id="6d88c-589">OTHER</span></span>                  | <span data-ttu-id="6d88c-590">Egyéb okok</span><span class="sxs-lookup"><span data-stu-id="6d88c-590">Other Reasons</span></span>                  | <span data-ttu-id="6d88c-591">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="6d88c-591">Terminate worker</span></span>     |
| <span data-ttu-id="6d88c-592">CLOSURE</span><span class="sxs-lookup"><span data-stu-id="6d88c-592">CLOSURE</span></span>                | <span data-ttu-id="6d88c-593">Üzletzárás</span><span class="sxs-lookup"><span data-stu-id="6d88c-593">Business Closure</span></span>               | <span data-ttu-id="6d88c-594">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="6d88c-594">Terminate worker</span></span>     |
| <span data-ttu-id="6d88c-595">DEATH</span><span class="sxs-lookup"><span data-stu-id="6d88c-595">DEATH</span></span>                  | <span data-ttu-id="6d88c-596">Elhalálozás</span><span class="sxs-lookup"><span data-stu-id="6d88c-596">Death</span></span>                          | <span data-ttu-id="6d88c-597">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="6d88c-597">Terminate worker</span></span>     |
| <span data-ttu-id="6d88c-598">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="6d88c-598">LEAVEOFABSENCE</span></span>         | <span data-ttu-id="6d88c-599">Szabadság</span><span class="sxs-lookup"><span data-stu-id="6d88c-599">Leave of Absence</span></span>               | <span data-ttu-id="6d88c-600">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="6d88c-600">Terminate worker</span></span>     |
| <span data-ttu-id="6d88c-601">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="6d88c-601">CONTRACTEND</span></span>            | <span data-ttu-id="6d88c-602">Szerződés vége</span><span class="sxs-lookup"><span data-stu-id="6d88c-602">End of Contract</span></span>                | <span data-ttu-id="6d88c-603">Felmondás a dolgozónak</span><span class="sxs-lookup"><span data-stu-id="6d88c-603">Terminate worker</span></span>     |
| <span data-ttu-id="6d88c-604">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="6d88c-604">SALARYCHANGE</span></span>           | <span data-ttu-id="6d88c-605">Munkabér módosítása</span><span class="sxs-lookup"><span data-stu-id="6d88c-605">Change of Salary</span></span>               | <span data-ttu-id="6d88c-606">Kompenzáció</span><span class="sxs-lookup"><span data-stu-id="6d88c-606">Compensation</span></span>         |

### <a name="terms-of-employment"></a><span data-ttu-id="6d88c-607">Foglalkoztatási feltételek</span><span class="sxs-lookup"><span data-stu-id="6d88c-607">Terms of employment</span></span>

<span data-ttu-id="6d88c-608">A Foglalkoztatási feltételek foglalkoztatási feltételkategóriák létrehozására használatosak.</span><span class="sxs-lookup"><span data-stu-id="6d88c-608">Terms of employment are used to create categories of employment terms.</span></span> <span data-ttu-id="6d88c-609">A feltételek alkalmazási mutató értékekként vannak a Dayforce-hoz rendelve.</span><span class="sxs-lookup"><span data-stu-id="6d88c-609">The terms are mapped to Dayforce as employment indicator values.</span></span>

<span data-ttu-id="6d88c-610">A következő alkalmazási feltételek és leírások szükségesek.</span><span class="sxs-lookup"><span data-stu-id="6d88c-610">The following terms of employment and descriptions are required.</span></span>

| <span data-ttu-id="6d88c-611">Foglalkoztatási feltételek</span><span class="sxs-lookup"><span data-stu-id="6d88c-611">Terms of employment</span></span>   | <span data-ttu-id="6d88c-612">Leírás</span><span class="sxs-lookup"><span data-stu-id="6d88c-612">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="6d88c-613">Szabályos</span><span class="sxs-lookup"><span data-stu-id="6d88c-613">Regular</span></span>               | <span data-ttu-id="6d88c-614">Szabályos</span><span class="sxs-lookup"><span data-stu-id="6d88c-614">Regular</span></span>     |
| <span data-ttu-id="6d88c-615">Közvetlen</span><span class="sxs-lookup"><span data-stu-id="6d88c-615">Direct</span></span>                | <span data-ttu-id="6d88c-616">Közvetlen</span><span class="sxs-lookup"><span data-stu-id="6d88c-616">Direct</span></span>      |
| <span data-ttu-id="6d88c-617">Szakmai gyakorlat</span><span class="sxs-lookup"><span data-stu-id="6d88c-617">Internship</span></span>            | <span data-ttu-id="6d88c-618">Szakmai gyakorlat</span><span class="sxs-lookup"><span data-stu-id="6d88c-618">Internship</span></span>  |
| <span data-ttu-id="6d88c-619">Állandó</span><span class="sxs-lookup"><span data-stu-id="6d88c-619">Permanent</span></span>             | <span data-ttu-id="6d88c-620">Állandó</span><span class="sxs-lookup"><span data-stu-id="6d88c-620">Permanent</span></span>   |

### <a name="marital-status"></a><span data-ttu-id="6d88c-621">Családi állapot</span><span class="sxs-lookup"><span data-stu-id="6d88c-621">Marital status</span></span>

<span data-ttu-id="6d88c-622">Családi állapot értékei Dayforce-hoz vannak rendelve és konvertálva szükség esetén az elfogadható értékekre az integráció során.</span><span class="sxs-lookup"><span data-stu-id="6d88c-622">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="6d88c-623">Az alábbi táblázat bemutatja, hogy családi állapot értékek hogyan vannak leképezve a Dayforce -ban.</span><span class="sxs-lookup"><span data-stu-id="6d88c-623">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="6d88c-624">Talent</span><span class="sxs-lookup"><span data-stu-id="6d88c-624">Talent</span></span>                 | <span data-ttu-id="6d88c-625">Dayforce</span><span class="sxs-lookup"><span data-stu-id="6d88c-625">Dayforce</span></span>                  |
|------------------------|---------------------------|
| <span data-ttu-id="6d88c-626">Házas</span><span class="sxs-lookup"><span data-stu-id="6d88c-626">Married</span></span>                | <span data-ttu-id="6d88c-627">Házas</span><span class="sxs-lookup"><span data-stu-id="6d88c-627">Married</span></span>                   |
| <span data-ttu-id="6d88c-628">Egy</span><span class="sxs-lookup"><span data-stu-id="6d88c-628">Single</span></span>                 | <span data-ttu-id="6d88c-629">Egy</span><span class="sxs-lookup"><span data-stu-id="6d88c-629">Single</span></span>                    |
| <span data-ttu-id="6d88c-630">Özvegy</span><span class="sxs-lookup"><span data-stu-id="6d88c-630">Widowed</span></span>                | <span data-ttu-id="6d88c-631">Özvegy</span><span class="sxs-lookup"><span data-stu-id="6d88c-631">Widowed</span></span>                   |
| <span data-ttu-id="6d88c-632">Elvált</span><span class="sxs-lookup"><span data-stu-id="6d88c-632">Divorced</span></span>               | <span data-ttu-id="6d88c-633">Elvált</span><span class="sxs-lookup"><span data-stu-id="6d88c-633">Divorced</span></span>                  |
| <span data-ttu-id="6d88c-634">Bejegyzett élettársi kapcsolat</span><span class="sxs-lookup"><span data-stu-id="6d88c-634">Registered Partnership</span></span> | <span data-ttu-id="6d88c-635">Élettársi viszony</span><span class="sxs-lookup"><span data-stu-id="6d88c-635">Domestic Partnership</span></span>      |
| <span data-ttu-id="6d88c-636">Nincs</span><span class="sxs-lookup"><span data-stu-id="6d88c-636">None</span></span>                   | <span data-ttu-id="6d88c-637">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="6d88c-637">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="6d88c-638">Együttélés</span><span class="sxs-lookup"><span data-stu-id="6d88c-638">Cohabiting</span></span>             | <span data-ttu-id="6d88c-639">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="6d88c-639">*Not supported by Mexico*</span></span> |

### <a name="gender"></a><span data-ttu-id="6d88c-640">Nem</span><span class="sxs-lookup"><span data-stu-id="6d88c-640">Gender</span></span>

<span data-ttu-id="6d88c-641">A nemek a Dayforce-hoz vannak rendelve és konvertálva szükség esetén az elfogadható értékekre az integráció során.</span><span class="sxs-lookup"><span data-stu-id="6d88c-641">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="6d88c-642">Az alábbi táblázat bemutatja, hogy a nemek hogyan vannak leképezve a Dayforce-ban.</span><span class="sxs-lookup"><span data-stu-id="6d88c-642">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="6d88c-643">Talent</span><span class="sxs-lookup"><span data-stu-id="6d88c-643">Talent</span></span>       | <span data-ttu-id="6d88c-644">Dayforce</span><span class="sxs-lookup"><span data-stu-id="6d88c-644">Dayforce</span></span>                  |
|--------------|---------------------------|
| <span data-ttu-id="6d88c-645">Férfi</span><span class="sxs-lookup"><span data-stu-id="6d88c-645">Male</span></span>         | <span data-ttu-id="6d88c-646">Férfi</span><span class="sxs-lookup"><span data-stu-id="6d88c-646">Male</span></span>                      |
| <span data-ttu-id="6d88c-647">Nő</span><span class="sxs-lookup"><span data-stu-id="6d88c-647">Female</span></span>       | <span data-ttu-id="6d88c-648">Nő</span><span class="sxs-lookup"><span data-stu-id="6d88c-648">Female</span></span>                    |
| <span data-ttu-id="6d88c-649">Nem meghatározott</span><span class="sxs-lookup"><span data-stu-id="6d88c-649">Non-specific</span></span> | <span data-ttu-id="6d88c-650">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="6d88c-650">*Not supported by Mexico*</span></span> |

### <a name="payment-method"></a><span data-ttu-id="6d88c-651">Kifizetési mód</span><span class="sxs-lookup"><span data-stu-id="6d88c-651">Payment method</span></span>

<span data-ttu-id="6d88c-652">A Fizetési módok adják meg az alkalmazott és a vállalat számára az alkalmazott kifizetésének módja leírásának lehetőségét.</span><span class="sxs-lookup"><span data-stu-id="6d88c-652">Payment methods give the employee and the company a way to describe how employees will be paid.</span></span> <span data-ttu-id="6d88c-653">A Fizetési módok a Dayforce-hoz vannak rendelve és konvertálva szükség esetén az elfogadható értékekre az integráció során.</span><span class="sxs-lookup"><span data-stu-id="6d88c-653">Payment methods are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="6d88c-654">Az alábbi táblázat bemutatja, hogy a fizetés módok hogyan vannak leképezve a Dayforce-ban.</span><span class="sxs-lookup"><span data-stu-id="6d88c-654">The following table shows how payment methods are mapped to Dayforce.</span></span>

| <span data-ttu-id="6d88c-655">Talent</span><span class="sxs-lookup"><span data-stu-id="6d88c-655">Talent</span></span>             | <span data-ttu-id="6d88c-656">Dayforce</span><span class="sxs-lookup"><span data-stu-id="6d88c-656">Dayforce</span></span>                  |
|--------------------|---------------------------|
| <span data-ttu-id="6d88c-657">Készpénz</span><span class="sxs-lookup"><span data-stu-id="6d88c-657">Cash</span></span>               | <span data-ttu-id="6d88c-658">Készpénz</span><span class="sxs-lookup"><span data-stu-id="6d88c-658">Cash</span></span>                      |
| <span data-ttu-id="6d88c-659">Elektronikus fizetés</span><span class="sxs-lookup"><span data-stu-id="6d88c-659">Electronic Payment</span></span> | <span data-ttu-id="6d88c-660">Átvitel</span><span class="sxs-lookup"><span data-stu-id="6d88c-660">Transfer</span></span>                  |
| <span data-ttu-id="6d88c-661">Csekkes</span><span class="sxs-lookup"><span data-stu-id="6d88c-661">Check</span></span>              | <span data-ttu-id="6d88c-662">Csekk</span><span class="sxs-lookup"><span data-stu-id="6d88c-662">Cheque</span></span>                    |
| <span data-ttu-id="6d88c-663">Váltó</span><span class="sxs-lookup"><span data-stu-id="6d88c-663">Bank Draft</span></span>         | <span data-ttu-id="6d88c-664">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="6d88c-664">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="6d88c-665">Egyéb</span><span class="sxs-lookup"><span data-stu-id="6d88c-665">Other</span></span>              | <span data-ttu-id="6d88c-666">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="6d88c-666">*Not supported by Mexico*</span></span> |

### <a name="bank-account-type"></a><span data-ttu-id="6d88c-667">Bankszámla típusa</span><span class="sxs-lookup"><span data-stu-id="6d88c-667">Bank account type</span></span>

<span data-ttu-id="6d88c-668">Bankszámla-típusok az alkalmazottaknak történő elektronikus kifizetésekhez szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="6d88c-668">Bank account types are used for electronic payments to employees.</span></span> <span data-ttu-id="6d88c-669">Bankszámla típusa a Dayforce-ba átutalási számlaadatként van rendelve.</span><span class="sxs-lookup"><span data-stu-id="6d88c-669">Bank account types are mapped to Dayforce as transfer account information.</span></span> <span data-ttu-id="6d88c-670">A bankszámlatípusok szükség esetén konvertálva vannak az elfogadható értékekké az integráció során.</span><span class="sxs-lookup"><span data-stu-id="6d88c-670">The bank account types are translated, as appropriate, to the accepted values upon integration.</span></span>

| <span data-ttu-id="6d88c-671">Talent</span><span class="sxs-lookup"><span data-stu-id="6d88c-671">Talent</span></span>            | <span data-ttu-id="6d88c-672">Dayforce</span><span class="sxs-lookup"><span data-stu-id="6d88c-672">Dayforce</span></span>                  |
|-------------------|---------------------------|
| <span data-ttu-id="6d88c-673">Folyószámla</span><span class="sxs-lookup"><span data-stu-id="6d88c-673">Checking Account</span></span>  | <span data-ttu-id="6d88c-674">CheckingAccount</span><span class="sxs-lookup"><span data-stu-id="6d88c-674">CheckingAccount</span></span>           |
| <span data-ttu-id="6d88c-675">Bérlista elszámolási számlája</span><span class="sxs-lookup"><span data-stu-id="6d88c-675">Payroll Account</span></span>   | <span data-ttu-id="6d88c-676">PayrollAccount</span><span class="sxs-lookup"><span data-stu-id="6d88c-676">PayrollAccount</span></span>            |
| <span data-ttu-id="6d88c-677">Megtakarítási számla</span><span class="sxs-lookup"><span data-stu-id="6d88c-677">Savings Account</span></span>   | <span data-ttu-id="6d88c-678">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="6d88c-678">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="6d88c-679">BankGirot-számla</span><span class="sxs-lookup"><span data-stu-id="6d88c-679">BankGirot account</span></span> | <span data-ttu-id="6d88c-680">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="6d88c-680">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="6d88c-681">PlusGirot-számla</span><span class="sxs-lookup"><span data-stu-id="6d88c-681">PlusGirot account</span></span> | <span data-ttu-id="6d88c-682">*Mexikó nem támogatja*</span><span class="sxs-lookup"><span data-stu-id="6d88c-682">*Not supported by Mexico*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="6d88c-683">Bevételkódok</span><span class="sxs-lookup"><span data-stu-id="6d88c-683">Earning codes</span></span>

<span data-ttu-id="6d88c-684">A bevételkódok egyedi módon azonosítják a dolgozók által kapott fizetéstípusokat.</span><span class="sxs-lookup"><span data-stu-id="6d88c-684">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="6d88c-685">A kódoknak különböző paramétereket fednek le, amelyek a bevételekhez kapcsolódnak, például könyvelési szabályok, jelentési követelmények és bruttósítási lehetőségek.</span><span class="sxs-lookup"><span data-stu-id="6d88c-685">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="6d88c-686">Ha egy nem támogatott gyakoriság van használatban, a **Minden fizetés** gyakorisága van alapértelmezés szerint használva a kiszámításhoz.</span><span class="sxs-lookup"><span data-stu-id="6d88c-686">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="6d88c-687">Támogatott gyakoriságok</span><span class="sxs-lookup"><span data-stu-id="6d88c-687">Supported frequencies</span></span>

- <span data-ttu-id="6d88c-688">Összes</span><span class="sxs-lookup"><span data-stu-id="6d88c-688">All</span></span>
- <span data-ttu-id="6d88c-689">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="6d88c-689">EVERYPAY</span></span>
- <span data-ttu-id="6d88c-690">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="6d88c-690">EACHPAYPERIOD</span></span>
- <span data-ttu-id="6d88c-691">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="6d88c-691">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="6d88c-692">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="6d88c-692">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="6d88c-693">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="6d88c-693">1OFMTH</span></span>
- <span data-ttu-id="6d88c-694">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="6d88c-694">LASTOFMTH</span></span>
- <span data-ttu-id="6d88c-695">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="6d88c-695">2OFMTH</span></span>
- <span data-ttu-id="6d88c-696">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="6d88c-696">3OFMTH</span></span>
- <span data-ttu-id="6d88c-697">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6d88c-697">4OFMTH</span></span>
- <span data-ttu-id="6d88c-698">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="6d88c-698">5OFMTH</span></span>
- <span data-ttu-id="6d88c-699">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="6d88c-699">1N2OFMTH</span></span>
- <span data-ttu-id="6d88c-700">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6d88c-700">3N4OFMTH</span></span>
- <span data-ttu-id="6d88c-701">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="6d88c-701">1N3OFMTH</span></span>
- <span data-ttu-id="6d88c-702">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6d88c-702">1N4OFMTH</span></span>
- <span data-ttu-id="6d88c-703">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="6d88c-703">2N3OFMTH</span></span>
- <span data-ttu-id="6d88c-704">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6d88c-704">2N4OFMTH</span></span>
- <span data-ttu-id="6d88c-705">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="6d88c-705">1N2N3OFMTH</span></span>
- <span data-ttu-id="6d88c-706">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6d88c-706">1N2N4OFMTH</span></span>
- <span data-ttu-id="6d88c-707">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6d88c-707">1N3N4OFMTH</span></span>
- <span data-ttu-id="6d88c-708">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6d88c-708">2N3N4OFMTH</span></span>
- <span data-ttu-id="6d88c-709">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6d88c-709">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="6d88c-710">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="6d88c-710">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="6d88c-711">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="6d88c-711">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="6d88c-712">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="6d88c-712">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="6d88c-713">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="6d88c-713">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="6d88c-714">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="6d88c-714">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="6d88c-715">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="6d88c-715">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="6d88c-716">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="6d88c-716">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="6d88c-717">Címek</span><span class="sxs-lookup"><span data-stu-id="6d88c-717">Addresses</span></span>

<span data-ttu-id="6d88c-718">Az adott ország vagy régió, állam és megye (település) kódok specifikus formátumokat követelnek, hogy Dayforce és az országos és regionális szolgáltatók felismerjék azokat.</span><span class="sxs-lookup"><span data-stu-id="6d88c-718">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="6d88c-719">Annak ellenére, hogy a városok formátuma rugalmas, minden városnak társítva kell lennie egy államhoz.</span><span class="sxs-lookup"><span data-stu-id="6d88c-719">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="6d88c-720">Talent</span><span class="sxs-lookup"><span data-stu-id="6d88c-720">Talent</span></span>              | <span data-ttu-id="6d88c-721">Dayforce</span><span class="sxs-lookup"><span data-stu-id="6d88c-721">Dayforce</span></span>              |
|---------------------|-----------------------|
| <span data-ttu-id="6d88c-722">Ország/régió</span><span class="sxs-lookup"><span data-stu-id="6d88c-722">Country/Region</span></span>      | <span data-ttu-id="6d88c-723">Országkód</span><span class="sxs-lookup"><span data-stu-id="6d88c-723">Country Code</span></span>          |
| <span data-ttu-id="6d88c-724">Irányítószám / postai kód</span><span class="sxs-lookup"><span data-stu-id="6d88c-724">Zip/Postal Code</span></span>     | <span data-ttu-id="6d88c-725">Irányítószám</span><span class="sxs-lookup"><span data-stu-id="6d88c-725">Postal Code</span></span>           |
| <span data-ttu-id="6d88c-726">Állami</span><span class="sxs-lookup"><span data-stu-id="6d88c-726">State</span></span>               | <span data-ttu-id="6d88c-727">Államkód</span><span class="sxs-lookup"><span data-stu-id="6d88c-727">State Code</span></span>            |
| <span data-ttu-id="6d88c-728">Város</span><span class="sxs-lookup"><span data-stu-id="6d88c-728">City</span></span>                | <span data-ttu-id="6d88c-729">Város</span><span class="sxs-lookup"><span data-stu-id="6d88c-729">City</span></span>                  |
| <span data-ttu-id="6d88c-730">Megye</span><span class="sxs-lookup"><span data-stu-id="6d88c-730">County</span></span>              | <span data-ttu-id="6d88c-731">Megye (Helyhatóság)</span><span class="sxs-lookup"><span data-stu-id="6d88c-731">County (Municipality)</span></span> |
| <span data-ttu-id="6d88c-732">Utca</span><span class="sxs-lookup"><span data-stu-id="6d88c-732">Street</span></span>              | <span data-ttu-id="6d88c-733">Cím 1. sora</span><span class="sxs-lookup"><span data-stu-id="6d88c-733">Address Line 1</span></span>        |
| <span data-ttu-id="6d88c-734">Utca, házszám</span><span class="sxs-lookup"><span data-stu-id="6d88c-734">Street Number</span></span>       | <span data-ttu-id="6d88c-735">Cím 2. sora</span><span class="sxs-lookup"><span data-stu-id="6d88c-735">Address Line 2</span></span>        |
| <span data-ttu-id="6d88c-736">Épületblokk</span><span class="sxs-lookup"><span data-stu-id="6d88c-736">Building Complement</span></span> | <span data-ttu-id="6d88c-737">Cím 5. sora</span><span class="sxs-lookup"><span data-stu-id="6d88c-737">Address Line 5</span></span>        |

### <a name="passport-number"></a><span data-ttu-id="6d88c-738">Útlevél száma</span><span class="sxs-lookup"><span data-stu-id="6d88c-738">Passport number</span></span>

<span data-ttu-id="6d88c-739">Az alkalmazottak útlevél adatokat is nyilatkozhatnak.</span><span class="sxs-lookup"><span data-stu-id="6d88c-739">Employees can declare passport information.</span></span> <span data-ttu-id="6d88c-740">Az információ a **Útlevél** azonosítótípusra vonatkozik, és az alkalmazott Mexikó-specifikus adataiként van a Dayforce-ba integrálva.</span><span class="sxs-lookup"><span data-stu-id="6d88c-740">This information is of the **Passport** identification type and is integrated into Dayforce as part of an employee's Mexico-specific information.</span></span>

- <span data-ttu-id="6d88c-741">Azonosító típusa = „Útlevél”</span><span class="sxs-lookup"><span data-stu-id="6d88c-741">Identification Type = "Passport"</span></span>
- <span data-ttu-id="6d88c-742">Kibocsátás dátuma</span><span class="sxs-lookup"><span data-stu-id="6d88c-742">Issued Date</span></span>
- <span data-ttu-id="6d88c-743">Lejárat dátuma</span><span class="sxs-lookup"><span data-stu-id="6d88c-743">Expiration Date</span></span>

<span data-ttu-id="6d88c-744">Az alkalmazottak több azonosítószámot is megadhatnak az **Útlevél** azonosítótípushoz.</span><span class="sxs-lookup"><span data-stu-id="6d88c-744">Employees can declare multiple identification numbers of the **Passport** identification type.</span></span> <span data-ttu-id="6d88c-745">Azonban csak az aktuális aktív útlevélbejegyzés van integrálva a Dayforce-ba.</span><span class="sxs-lookup"><span data-stu-id="6d88c-745">However, only the current active passport entry is integrated into Dayforce.</span></span> <span data-ttu-id="6d88c-746">Ha az összes útlevélbejegyzés lejárt, a legutóbb kiállított lesz integrálva a Dayforce-ba.</span><span class="sxs-lookup"><span data-stu-id="6d88c-746">If all passport entries are expired, the passport that was most recently issued is integrated into Dayforce.</span></span>
