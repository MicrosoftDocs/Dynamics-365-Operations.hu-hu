---
title: "Felhőbeli telepítések rendszerkövetelményei"
description: "Ez a témakör a Microsoft Dynamics 365 for Finance and Operations Enterprise edition aktuális verziójára vonatkozó rendszerkövetelményeket sorolja fel felhőalapú telepítés esetén."
author: sericks007
manager: AnnBe
ms.date: 08/02/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 55651
ms.assetid: e564d51d-42d3-47c5-b388-93b8219c692a
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 8
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 83637b4b2ccc01950e68569b3b8bee1a7cd69855
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="system-requirements-for-cloud-deployments"></a><span data-ttu-id="caaa5-103">Felhőbeli telepítések rendszerkövetelményei</span><span class="sxs-lookup"><span data-stu-id="caaa5-103">System requirements for cloud deployments</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="caaa5-104">Ez a témakör a Microsoft Dynamics 365 for Finance and Operations Enterprise edition aktuális verziójára vonatkozó rendszerkövetelményeket sorolja fel felhőalapú telepítés esetén.</span><span class="sxs-lookup"><span data-stu-id="caaa5-104">This topic lists the system requirements for the current version of Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, for cloud deployments.</span></span> <span data-ttu-id="caaa5-105">Mielőtt telepíti a Finance and Operations szoftvert, amennyiben ez a lépés szükséges, biztosítsa, hogy az ön által használt rendszer eléri vagy meghaladja a minimális hálózati, hardver és szoftver követelményeket.</span><span class="sxs-lookup"><span data-stu-id="caaa5-105">Before you install Finance and Operations, when this step is appropriate, verify that the system that you're working with meets or exceeds the minimum network, hardware, and software requirements.</span></span>

## <a name="supported-web-browsers"></a><span data-ttu-id="caaa5-106">Támogatott böngészők</span><span class="sxs-lookup"><span data-stu-id="caaa5-106">Supported web browsers</span></span>
<span data-ttu-id="caaa5-107">A webes alkalmazás az alábbi böngészők bármelyikében működik, ha azok a megadott operációs rendszer alatt futnak:</span><span class="sxs-lookup"><span data-stu-id="caaa5-107">The web application can run in any of the following web browsers that run on the specified operating systems:</span></span>

-   <span data-ttu-id="caaa5-108">Microsoft Edge (legfrissebb elérhető verziója) a Windows 10 rendszeren</span><span class="sxs-lookup"><span data-stu-id="caaa5-108">Microsoft Edge (latest publicly available version) on Windows 10</span></span>
-   <span data-ttu-id="caaa5-109">Internet Explorer 11, Windows 10, Windows 8.1 vagy Windows 7 rendszereken</span><span class="sxs-lookup"><span data-stu-id="caaa5-109">Internet Explorer 11 on Windows 10, Windows 8.1, or Windows 7</span></span>
-   <span data-ttu-id="caaa5-110">Google Chrome (legfrissebb elérhető verziója) Windows 10, Windows 8.1, Windows 8, Windows 7 rendszereken, vagy Google Nexus 10 táblagépen</span><span class="sxs-lookup"><span data-stu-id="caaa5-110">Google Chrome (latest publicly available version) on Windows 10, Windows 8.1, Windows 8, Windows 7, or Google Nexus 10 tablet</span></span>
-   <span data-ttu-id="caaa5-111">Apple Safari (legfrissebb elérhető verziója) Mac OS X 10.10 (Yosemite), 10.11 (El Capitan), 10.12 (Sierra) rendszereken, vagy Apple iPad gépen</span><span class="sxs-lookup"><span data-stu-id="caaa5-111">Apple Safari (latest publicly available version) on Mac OS X 10.10 (Yosemite), 10.11 (El Capitan) or 10.12 (Sierra), or Apple iPad</span></span>

<span data-ttu-id="caaa5-112">A böngésző legfrissebb változatáért látogasson el a szoftver gyártójának webhelyére.</span><span class="sxs-lookup"><span data-stu-id="caaa5-112">To find the latest release for each web browser, go to the software manufacturer’s website.</span></span> 

> [!NOTE]
> -   <span data-ttu-id="caaa5-113">A Task Recorder által generált képek rögzítéséhez és Microsoft Word-dokumentumba való ágyazásához telepítenie kell egy előzetes verziójú Chrome-bővítményt.</span><span class="sxs-lookup"><span data-stu-id="caaa5-113">You must install a pre-release Chrome extension to enable Task Recorder to capture screenshots and include them in Microsoft Word documents that are generated.</span></span> <!---For instructions about how to install the extension, see [Screenshot Extension setup](../../dev-itpro/user-interface/task-recorder).-->
> -   <span data-ttu-id="caaa5-114">A munkafolyamat-szerkesztő ClickOnce-alkalmazásként indul el.</span><span class="sxs-lookup"><span data-stu-id="caaa5-114">The Workflow Editor is started as a ClickOnce application.</span></span> <span data-ttu-id="caaa5-115">Csak a Microsoft Edge és az Internet Explorer (a Microsoft Windows egy támogatott verziójának használata esetén) támogatja a ClickOnce-alkalmazásokat.</span><span class="sxs-lookup"><span data-stu-id="caaa5-115">Only Microsoft Edge and Internet Explorer (on a supported version of Microsoft Windows) support ClickOnce applications.</span></span> <span data-ttu-id="caaa5-116">A Workflow Editor ClickOnce alkalmazáshoz 64 bit-kompatibilis operációs rendszer szükséges.</span><span class="sxs-lookup"><span data-stu-id="caaa5-116">The Workflow Editor ClickOnce application requires a 64-bit-compatible operating system.</span></span>
> -   <span data-ttu-id="caaa5-117">A Report Designer for Financial reporting ClickOnce alkalmazásként indul el.</span><span class="sxs-lookup"><span data-stu-id="caaa5-117">The Report Designer for Financial reporting is started as a ClickOnce application.</span></span> <span data-ttu-id="caaa5-118">64 bit-kompatibilis operációs rendszert igényel.</span><span class="sxs-lookup"><span data-stu-id="caaa5-118">It requires a 64-bit-compatible operating system.</span></span> <span data-ttu-id="caaa5-119">Chrome használata esetén, telepítenie kell a ClickOnce kiterjesztést a jelentéstervező kliens letöltéséhez.</span><span class="sxs-lookup"><span data-stu-id="caaa5-119">If you’re using Chrome, you must install a ClickOnce extension to download the Report Designer client.</span></span> <span data-ttu-id="caaa5-120">Ha a Chrome böngészőt Inkognitó módban futtatja, győződjön meg arról, a ClickOnce kiterjesztés engedélyezve van-e az Inkognitó módban.</span><span class="sxs-lookup"><span data-stu-id="caaa5-120">If you use Chrome in Incognito mode, make sure that the ClickOnce extension is also enabled for Incognito mode.</span></span>
> -   <span data-ttu-id="caaa5-121">A PDF-fájlok előnézetének megtekintéséhez olyan böngészők használatát javasoljuk, mint a Microsoft Edge (a legújabb nyilvánosan elérhető verzió) Windows 10 rendszeren, illetve a Google Chrome (a legújabb nyilvánosan elérhető verzió) Windows 10, Windows 8.1, Windows 8 vagy Windows 7 rendszeren vagy Google Nexus 10 táblagépeken.</span><span class="sxs-lookup"><span data-stu-id="caaa5-121">To preview PDF files, we recommend that you use browsers such as Microsoft Edge (latest publicly available version) on Windows 10, or Google Chrome (latest publicly available version) on Windows 10, Windows 8.1, Windows 8, Windows 7, or Google Nexus 10 tablet.</span></span>

### <a name="supported-web-browsers-for-retail-cloud-pos"></a><span data-ttu-id="caaa5-122">A kiskereskedelmi felhő-POS pénztárgép által támogatott böngészők</span><span class="sxs-lookup"><span data-stu-id="caaa5-122">Supported web browsers for Retail Cloud POS</span></span>

<span data-ttu-id="caaa5-123">A Retail Cloud POS az alábbi böngészők bármelyikében működik, ha azok a megadott operációs rendszer alatt futnak:</span><span class="sxs-lookup"><span data-stu-id="caaa5-123">Retail Cloud POS can run in any of the following web browsers that run on the specified operating systems:</span></span>

-   <span data-ttu-id="caaa5-124">Microsoft Edge (legfrissebb elérhető verziója) a Windows 10 rendszeren</span><span class="sxs-lookup"><span data-stu-id="caaa5-124">Microsoft Edge (latest publicly available version) on Windows 10</span></span>
-   <span data-ttu-id="caaa5-125">Internet Explorer 11, Windows 10, Windows 8.1 vagy Windows 7 rendszereken</span><span class="sxs-lookup"><span data-stu-id="caaa5-125">Internet Explorer 11 on Windows 10, Windows 8.1, or Windows 7</span></span>
-   <span data-ttu-id="caaa5-126">Chrome (legutóbbi nyilvánosan elérhető verzió) Windows 10, Windows 8.1 vagy Windows 7 rendszeren</span><span class="sxs-lookup"><span data-stu-id="caaa5-126">Chrome (latest publicly available version) on Windows 10, Windows 8.1, or Windows 7</span></span>

## <a name="network-requirements"></a><span data-ttu-id="caaa5-127">Hálózati követelmények</span><span class="sxs-lookup"><span data-stu-id="caaa5-127">Network requirements</span></span>
-   <span data-ttu-id="caaa5-128">A Finance and Operations szoftvert olyan hálózatokhoz tervezték, amelyek várakozási ideje 250-300 milliszekund (ms) vagy kevesebb.</span><span class="sxs-lookup"><span data-stu-id="caaa5-128">Finance and Operations is designed for networks that have a latency of 250–300 milliseconds (ms) or less.</span></span> <span data-ttu-id="caaa5-129">Ez a latencia a böngészőklienstől a Microsoft Azure adatközpontig, amely tárolja a Finance and Operationst.</span><span class="sxs-lookup"><span data-stu-id="caaa5-129">This latency is the latency from a browser client to the Microsoft Azure datacenter that hosts Finance and Operations.</span></span> <span data-ttu-id="caaa5-130">Javasoljuk, hogy tesztelje a hálózati késleltetést a következő helyen: <http://www.azurespeed.com>.</span><span class="sxs-lookup"><span data-stu-id="caaa5-130">We recommend that you test network latency at <http://www.azurespeed.com>.</span></span>
-   <span data-ttu-id="caaa5-131">A Finance and Operations sávszélességi követelményei az ön körülményeitől függenek.</span><span class="sxs-lookup"><span data-stu-id="caaa5-131">Bandwidth requirements for Finance and Operations depend on your scenario.</span></span> <span data-ttu-id="caaa5-132">A legtöbb jellemző forgatókönyv másodpercenként több mint 50 kilobájt sávszélességet igényel (KBps).</span><span class="sxs-lookup"><span data-stu-id="caaa5-132">Most typical scenarios require a bandwidth of more than 50 kilobytes per second (KBps).</span></span> <span data-ttu-id="caaa5-133">Azonban olyan nagyteljesítményű forgatókönyvek esetében, mint például a munkaterületek vagy a kiterjedt testreszabást igénylő forgatókönyvek, nagyobb sávszélességet ajánlunk.</span><span class="sxs-lookup"><span data-stu-id="caaa5-133">However, we recommend more bandwidth for scenarios that have high payload requirements, such as scenarios that involve workspaces or extensive customization.</span></span>

<span data-ttu-id="caaa5-134">Általánosságban elmondható, hogy a Finance and Operations az internetre optimalizált.</span><span class="sxs-lookup"><span data-stu-id="caaa5-134">In general, Finance and Operations is optimized for the internet.</span></span> <span data-ttu-id="caaa5-135">A böngésző kliensből az Azure adatközpontba történő oda-vissza utak száma nagyon kicsi, és a teljes hasznos tartalom tömörítve van.</span><span class="sxs-lookup"><span data-stu-id="caaa5-135">The number of round trips from a browser client to the Azure datacenter is very small, and the whole payload is compressed.</span></span> 

> [!WARNING]
> <span data-ttu-id="caaa5-136">Ne úgy számítsa ki a sávszélesség követelményeit az ügyfél helyéről, hogy megszorozza a felhasználók számát a minimális sávszélességi követelményekkel.</span><span class="sxs-lookup"><span data-stu-id="caaa5-136">Don't calculate bandwidth requirements from a client location by multiplying the number of users by the minimum bandwidth requirements.</span></span> <span data-ttu-id="caaa5-137">Adott hely egyidejű használatát nagyon nehéz kiszámítani.</span><span class="sxs-lookup"><span data-stu-id="caaa5-137">The concurrent usage of a given location is very difficult to calculate.</span></span> <span data-ttu-id="caaa5-138">A sávszélesség miatt aggódó ügyfelek számára a Finance and Operations előzetes verziójának használata ajánlott.</span><span class="sxs-lookup"><span data-stu-id="caaa5-138">Customers who are concerned about bandwidth requirements should use a preview version of Finance and Operations.</span></span>

## <a name="net-framework-requirements"></a><span data-ttu-id="caaa5-139">A .NET keretrendszer követelményei</span><span class="sxs-lookup"><span data-stu-id="caaa5-139">.NET Framework requirements</span></span>
<span data-ttu-id="caaa5-140">A Finance and Operations esetében a Microsoft .NET-keretrendszer 4.6.2-es verziója szükséges az összes ClickOnce alkalmazáshoz, például a dokumentumátirányító ügynökhöz.</span><span class="sxs-lookup"><span data-stu-id="caaa5-140">Finance and Operations requires the Microsoft .NET Framework version 4.6.2 for all ClickOnce applications, such as the document routing agent.</span></span> <span data-ttu-id="caaa5-141">További tájékoztatás: [A .NET keretrendszer telepítése](https://msdn.microsoft.com/en-us/library/5a4x27ek(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="caaa5-141">For installation instructions, see [Installing the .NET Framework](https://msdn.microsoft.com/en-us/library/5a4x27ek(v=vs.110).aspx).</span></span>

## <a name="supported-microsoft-office-applications"></a><span data-ttu-id="caaa5-142">Támogatott Microsoft Office-alkalmazások</span><span class="sxs-lookup"><span data-stu-id="caaa5-142">Supported Microsoft Office applications</span></span>
<span data-ttu-id="caaa5-143">A következő Microsoft Office-alkalmazások a Finance and Operations felhő alapú vagy helyszíni telepítései esetén használhatók:</span><span class="sxs-lookup"><span data-stu-id="caaa5-143">The following Microsoft Office applications are supported in cloud and on-premises deployments of Finance and Operations:</span></span>

-   <span data-ttu-id="caaa5-144">A Microsoft Excel és Word bővítmények futtatásához telepítve kell lennie a Microsoft Office 2016 programnak Windows vagy Mac rendszeren.</span><span class="sxs-lookup"><span data-stu-id="caaa5-144">To run the Microsoft Excel and Word add-ins, you must have Microsoft Office 2016 for Windows or Mac installed.</span></span> <span data-ttu-id="caaa5-145">Verziójának követelményeivel kapcsolatos további részletekért lásd: [Office-integráció hibáinak elhárítása](../../dev-itpro/office-integration/office-integration-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="caaa5-145">For more information about version requirements, see [Office integration troubleshooting](../../dev-itpro/office-integration/office-integration-troubleshooting.md).</span></span>
-   <span data-ttu-id="caaa5-146">Az Exportálás Excel-be vagy az Exportálás a Word programba funkcióval létrehozott dokumentumok megtekintéséhez telepíteni kell a Microsoft Office 2007 vagy újabb verzióját.</span><span class="sxs-lookup"><span data-stu-id="caaa5-146">To view documents that are generated by the Export to Excel or Export to Word functionality, you must have Microsoft Office 2007 or later installed.</span></span>

## <a name="retail-modern-pos-requirements"></a><span data-ttu-id="caaa5-147">Retail Modern POS követelményei</span><span class="sxs-lookup"><span data-stu-id="caaa5-147">Retail Modern POS requirements</span></span>

> [!NOTE]
> <span data-ttu-id="caaa5-148">Ha a Retail Modern POS offline adatbázist fog használni, a számítógépnek teljesítenie kell a Microsoft SQL Server minden rendszerkövetelményét.</span><span class="sxs-lookup"><span data-stu-id="caaa5-148">If Retail Modern POS will use an offline database, the computer must meet all system requirements for Microsoft SQL Server.</span></span> <span data-ttu-id="caaa5-149">A Retail Modern POS offline adatbázis a következőkön működik: Microsoft SQL Server 2012, Service Pack 3 vagy későbbi, Microsoft SQL Server 2014, Service Pack 2 vagy későbbi, valamint Microsoft SQL Server 2016.</span><span class="sxs-lookup"><span data-stu-id="caaa5-149">A Retail Modern POS offline database will work on Microsoft SQL Server 2012 with Service Pack 3 or later, Microsoft SQL Server 2014 with Service Pack 2 or later, and Microsoft SQL Server 2016.</span></span> <span data-ttu-id="caaa5-150">Javasoljuk, hogy mindig a rendelkezésre álló legújabb verziót használja, és telepítse az összes legújabb szervizcsomagot.</span><span class="sxs-lookup"><span data-stu-id="caaa5-150">We recommend that you always use the latest version that is available, and that you install all the latest service packs.</span></span>

### <a name="supported-operating-systems"></a><span data-ttu-id="caaa5-151">Támogatott operációs rendszerek</span><span class="sxs-lookup"><span data-stu-id="caaa5-151">Supported operating systems</span></span>

-   <span data-ttu-id="caaa5-152">A Retail Modern POS egy 32 bites alkalmazás, de egyaránt fut az x86 és az x64 architektúrán is.</span><span class="sxs-lookup"><span data-stu-id="caaa5-152">Retail Modern POS is a 32-bit application, but it will run on both x86 and x64 architectures.</span></span>
-   <span data-ttu-id="caaa5-153">A Retail Modern POS csak Windows 10 Pro, Enterprise, valamint Enterprise Long Term Servicing Branch (LTSB) kiadások esetén támogatott.</span><span class="sxs-lookup"><span data-stu-id="caaa5-153">Retail Modern POS is supported only on Windows 10 Pro, Enterprise, and Enterprise Long Term Servicing Branch (LTSB) editions.</span></span>

### <a name="minimum-system-requirements"></a><span data-ttu-id="caaa5-154">Minimális rendszerkövetelmények</span><span class="sxs-lookup"><span data-stu-id="caaa5-154">Minimum system requirements</span></span>

-   <span data-ttu-id="caaa5-155">A minimális támogatott felbontás az 1280×1024.</span><span class="sxs-lookup"><span data-stu-id="caaa5-155">The minimum supported resolution is 1,280 × 1,024.</span></span>
-   <span data-ttu-id="caaa5-156">A Retail Modern POS rendszert futtató számítógépnek meg kell felelnie ezeknek a követelményeknek:</span><span class="sxs-lookup"><span data-stu-id="caaa5-156">The computer that Retail Modern POS runs on must meet these requirements:</span></span>

    -   <span data-ttu-id="caaa5-157">Legalább kétmagos processzorral kell rendelkeznie, melynek legalább 2 GHz az órajele.</span><span class="sxs-lookup"><span data-stu-id="caaa5-157">It must have, at a minimum, a dual-core processor that runs at no less than 2 gigahertz (GHz).</span></span>
    -   <span data-ttu-id="caaa5-158">Legalább 3 GB RAM-mal (véletlen hozzáférésű memória) kell rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="caaa5-158">It must have, at a minimum, 3 gigabytes (GB) of random-access memory (RAM).</span></span>
    -   <span data-ttu-id="caaa5-159">Internet-hozzáféréssel kell rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="caaa5-159">It must have internet access.</span></span>

## <a name="retail-hardware-station-requirements"></a><span data-ttu-id="caaa5-160">Retail hardware station követelményei</span><span class="sxs-lookup"><span data-stu-id="caaa5-160">Retail hardware station requirements</span></span>
### <a name="supported-operating-systems"></a><span data-ttu-id="caaa5-161">Támogatott operációs rendszerek</span><span class="sxs-lookup"><span data-stu-id="caaa5-161">Supported operating systems</span></span>

-   <span data-ttu-id="caaa5-162">A Retail hardware station egy 32 bites alkalmazás, de egyaránt fut az x86 és az x64 architektúrán is.</span><span class="sxs-lookup"><span data-stu-id="caaa5-162">Retail hardware station is a 32-bit application, but it will run on both x86 and x64 architectures.</span></span>
-   <span data-ttu-id="caaa5-163">A Retail hardware station a következő operációs rendszereken támogatott:</span><span class="sxs-lookup"><span data-stu-id="caaa5-163">Retail hardware station is supported on the following operating systems:</span></span>

    -   <span data-ttu-id="caaa5-164">Windows 7 Professional, Enterprise és Ultimate verzió</span><span class="sxs-lookup"><span data-stu-id="caaa5-164">Windows 7 Professional, Enterprise, and Ultimate editions</span></span> 
    
        > [!NOTE]
        > <span data-ttu-id="caaa5-165">A Windows 7 operációs rendszer csak akkor támogatott, ha ön manuálisan telepíti az Internet Explorer 11-et.</span><span class="sxs-lookup"><span data-stu-id="caaa5-165">Windows 7 is supported only if Internet Explorer 11 is manually installed on the system.</span></span>

    -   <span data-ttu-id="caaa5-166">Windows 8.1 Update 1 Professional, Enterprise és Embedded verzió</span><span class="sxs-lookup"><span data-stu-id="caaa5-166">Windows 8.1 Update 1 Professional, Enterprise, and Embedded editions</span></span>
    -   <span data-ttu-id="caaa5-167">Windows 10 Pro, Enterprise és Enterprise LTSB verzió</span><span class="sxs-lookup"><span data-stu-id="caaa5-167">Windows 10 Pro, Enterprise, and Enterprise LTSB editions</span></span>

### <a name="minimum-system-requirements"></a><span data-ttu-id="caaa5-168">Minimális rendszerkövetelmények</span><span class="sxs-lookup"><span data-stu-id="caaa5-168">Minimum system requirements</span></span>

<span data-ttu-id="caaa5-169">A számítógépnek teljesítenie kell a rendszerkövetelményeket a következő elemek telepítéséhez és használatához:</span><span class="sxs-lookup"><span data-stu-id="caaa5-169">The computer must meet all system requirements for installing and using the following items:</span></span>

-   <span data-ttu-id="caaa5-170">Internet Information Services (IIS)</span><span class="sxs-lookup"><span data-stu-id="caaa5-170">Internet Information Services (IIS)</span></span>
-   <span data-ttu-id="caaa5-171">Harmadik fél által biztosított hardver</span><span class="sxs-lookup"><span data-stu-id="caaa5-171">Third-party hardware</span></span>

## <a name="retail-store-scale-unit-requirements"></a><span data-ttu-id="caaa5-172">Core Retail Store Scale Unit követelményei</span><span class="sxs-lookup"><span data-stu-id="caaa5-172">Retail Store Scale Unit requirements</span></span>
### <a name="supported-operating-systems"></a><span data-ttu-id="caaa5-173">Támogatott operációs rendszerek</span><span class="sxs-lookup"><span data-stu-id="caaa5-173">Supported operating systems</span></span>

-   <span data-ttu-id="caaa5-174">A Retail Store Scale Unit egy 32 bites alkalmazás, de egyaránt fut az x86 és az x64 architektúrán is.</span><span class="sxs-lookup"><span data-stu-id="caaa5-174">Retail Store Scale Unit is a 32-bit application, but it will run on both x86 and x64 architectures.</span></span>
-   <span data-ttu-id="caaa5-175">A Retail Store Scale Unit a következő operációs rendszereken támogatott:</span><span class="sxs-lookup"><span data-stu-id="caaa5-175">Retail Store Scale Unit is supported on the following operating systems:</span></span>

    -   <span data-ttu-id="caaa5-176">Windows 7 Professional, Enterprise és Ultimate verzió</span><span class="sxs-lookup"><span data-stu-id="caaa5-176">Windows 7 Professional, Enterprise, and Ultimate editions</span></span>
    -   <span data-ttu-id="caaa5-177">Windows 8.1 Update 1 Professional, Enterprise és Embedded verzió</span><span class="sxs-lookup"><span data-stu-id="caaa5-177">Windows 8.1 Update 1 Professional, Enterprise, and Embedded editions</span></span>
    -   <span data-ttu-id="caaa5-178">Windows 10 Pro, Enterprise és Enterprise LTSB verzió</span><span class="sxs-lookup"><span data-stu-id="caaa5-178">Windows 10 Pro, Enterprise, and Enterprise LTSB editions</span></span>

### <a name="minimum-system-requirements"></a><span data-ttu-id="caaa5-179">Minimális rendszerkövetelmények</span><span class="sxs-lookup"><span data-stu-id="caaa5-179">Minimum system requirements</span></span>

-   <span data-ttu-id="caaa5-180">4 GB RAM</span><span class="sxs-lookup"><span data-stu-id="caaa5-180">4 GB of RAM</span></span>
-   <span data-ttu-id="caaa5-181">Maximális processzorsebesség 1,6 GHz magonként (legalább kétmagos)</span><span class="sxs-lookup"><span data-stu-id="caaa5-181">1.6 GHz peak CPU speed per core (Two cores are the minimum.)</span></span>
-   <span data-ttu-id="caaa5-182">Legalább 10 GB szabad lemezterület (a csatorna-adatbázis használatához sok helyre lehet szükség).</span><span class="sxs-lookup"><span data-stu-id="caaa5-182">At least 10 GB of free space (The channel database can require a large amount of space.)</span></span>

### <a name="recommended-system-requirements"></a><span data-ttu-id="caaa5-183">Ajánlott rendszerkövetelmények</span><span class="sxs-lookup"><span data-stu-id="caaa5-183">Recommended system requirements</span></span>

-   <span data-ttu-id="caaa5-184">6 GB RAM</span><span class="sxs-lookup"><span data-stu-id="caaa5-184">6 GB of RAM</span></span>
-   <span data-ttu-id="caaa5-185">2.4 GHz i7 (vagy ezzel egyenértékű) magonkénti CPU-sebesség / (négymagos processzor ajánlott).</span><span class="sxs-lookup"><span data-stu-id="caaa5-185">2.4 GHz i7 (or equivalent) peak CPU speed per core (Four cores are recommended.)</span></span>
-   <span data-ttu-id="caaa5-186">Legalább 10 GB szabad lemezterület (a csatorna-adatbázis használatához sok helyre lehet szükség).</span><span class="sxs-lookup"><span data-stu-id="caaa5-186">At least 10 GB of free space (The channel database can require a large amount of space.)</span></span>

## <a name="connector-requirements"></a><span data-ttu-id="caaa5-187">A Connector követelményei</span><span class="sxs-lookup"><span data-stu-id="caaa5-187">Connector requirements</span></span>
### <a name="supported-operating-systems"></a><span data-ttu-id="caaa5-188">Támogatott operációs rendszerek</span><span class="sxs-lookup"><span data-stu-id="caaa5-188">Supported operating systems</span></span>

-   <span data-ttu-id="caaa5-189">A Connector for Microsoft Dynamics AX két külön telepítőprogramot tartalmaz: az Async Server Connector service és a Real-time service for Dynamics AX 2012 R3 telepítőprogramokat.</span><span class="sxs-lookup"><span data-stu-id="caaa5-189">The Connector for Microsoft Dynamics AX has two separate installers, one for Async Server Connector service and one for Real-time service for Dynamics AX 2012 R3.</span></span>
-   <span data-ttu-id="caaa5-190">Mindkét összetevő 32 bites alkalmazás, de egyaránt futnak az x86 és az x64 architektúrán is.</span><span class="sxs-lookup"><span data-stu-id="caaa5-190">Both components are 32-bit applications, but they will run on both x86 and x64 architectures.</span></span>
-   <span data-ttu-id="caaa5-191">Mindkét összetevőt támogatják a következő operációs rendszerek:</span><span class="sxs-lookup"><span data-stu-id="caaa5-191">Both components are supported on the following operating systems:</span></span>

    -   <span data-ttu-id="caaa5-192">Windows 7 Professional, Enterprise és Ultimate verzió</span><span class="sxs-lookup"><span data-stu-id="caaa5-192">Windows 7 Professional, Enterprise, and Ultimate editions</span></span>
    -   <span data-ttu-id="caaa5-193">Windows 8.1 Update 1 Professional, Enterprise és Embedded verzió</span><span class="sxs-lookup"><span data-stu-id="caaa5-193">Windows 8.1 Update 1 Professional, Enterprise, and Embedded editions</span></span>
    -   <span data-ttu-id="caaa5-194">Windows 10 Pro, Enterprise és Enterprise LTSB verzió</span><span class="sxs-lookup"><span data-stu-id="caaa5-194">Windows 10 Pro, Enterprise, and Enterprise LTSB editions</span></span>
    -   <span data-ttu-id="caaa5-195">Microsoft Windows Server 2012 R2 és Microsoft Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="caaa5-195">Microsoft Windows Server 2012 R2 and Microsoft Windows Server 2016</span></span>

### <a name="minimum-system-requirements"></a><span data-ttu-id="caaa5-196">Minimális rendszerkövetelmények</span><span class="sxs-lookup"><span data-stu-id="caaa5-196">Minimum system requirements</span></span>
-   <span data-ttu-id="caaa5-197">2 GB memóriával (4 GB RAM ajánlott.)</span><span class="sxs-lookup"><span data-stu-id="caaa5-197">2 GB of RAM (4 GB of RAM are recommended.)</span></span>
-   <span data-ttu-id="caaa5-198">Maximális processzorsebesség 1,6 GHz magonként (legalább kétmagos)</span><span class="sxs-lookup"><span data-stu-id="caaa5-198">1.6 GHz peak CPU speed per core (Two cores are the minimum.)</span></span>
-   <span data-ttu-id="caaa5-199">Legalább 10 GB szabad lemezterület (a csatorna-adatbázis használatához sok helyre lehet szükség).</span><span class="sxs-lookup"><span data-stu-id="caaa5-199">At least 10 GB of free space (The channel database can require a large amount of space.)</span></span>

## <a name="requirements-for-development-on-local-vms"></a><span data-ttu-id="caaa5-200">A helyi virtuális gépek fejlesztési követelményei</span><span class="sxs-lookup"><span data-stu-id="caaa5-200">Requirements for development on local VMs</span></span>
<span data-ttu-id="caaa5-201">A helyi virtuális gépek fejlesztési követelményeiről lásd: [helyszínen futó virtuális gép](../../dev-itpro/dev-tools/access-instances.md).</span><span class="sxs-lookup"><span data-stu-id="caaa5-201">For information about the requirements for development on local virtual machines (VMs), see [VM running on-premises](../../dev-itpro/dev-tools/access-instances.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="caaa5-202">Lásd még</span><span class="sxs-lookup"><span data-stu-id="caaa5-202">See also</span></span>

[<span data-ttu-id="caaa5-203">Szerezze be a Dynamics 365 for Finance and Operations Enterprise Edition bétaverzióját</span><span class="sxs-lookup"><span data-stu-id="caaa5-203">Get an evaluation copy of Dynamics 365 for Finance and Operations, Enterprise edition</span></span>](../../dev-itpro/dev-tools/get-evaluation-copy.md)

