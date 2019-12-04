---
title: Talent rendszerkövetelményei
description: Ez a témakör felsorolja a Dynamics 365 Talent követelményeit.
author: andreabichsel
manager: AnnBe
ms.date: 10/21/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 63213
ms.assetid: 5dbc62fc-0184-4c0e-9856-e735fc68799e
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 0bd7d7051dd01834f306e165af55d740192b99e0
ms.sourcegitcommit: caeb24027831efccbc316ff8e7f9e62b42010d65
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/19/2019
ms.locfileid: "2818479"
---
# <a name="talent-system-requirements"></a><span data-ttu-id="52108-103">Talent rendszerkövetelményei</span><span class="sxs-lookup"><span data-stu-id="52108-103">Talent system requirements</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="52108-104">Ez a témakör a Microsoft Dynamics 365 Talent, beleértve az Attract, Onboard, és Core HR alkalmazások követelményeit írja le.</span><span class="sxs-lookup"><span data-stu-id="52108-104">This topic describes requirements for Microsoft Dynamics 365 Talent, including Attract, Onboard, and Core HR.</span></span> <span data-ttu-id="52108-105">Ezenkívül kiemeli azokat az országokat és régiókat, ahol a Talent elérhető, valamint a Talent adatainak lokalizációjával és a nyelvekkel kapcsolatos információkat.</span><span class="sxs-lookup"><span data-stu-id="52108-105">It also outlines the countries and regions where Talent is available, plus information about languages and localization for Talent data.</span></span> <span data-ttu-id="52108-106">Mindemellett ez a témakör a Talent frissítési irányelveit is tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="52108-106">In additions, this topic provides the update policy for Talent.</span></span>

## <a name="supported-web-browsers"></a><span data-ttu-id="52108-107">Támogatott böngészők</span><span class="sxs-lookup"><span data-stu-id="52108-107">Supported web browsers</span></span>

<span data-ttu-id="52108-108">A Microsoft Dynamics 365 Talent az alábbi böngészők bármelyikében működik, ha azok a megadott operációs rendszer alatt futnak:</span><span class="sxs-lookup"><span data-stu-id="52108-108">Microsoft Dynamics 365 Talent can run in any of the following web browsers that run on the specified operating systems:</span></span> 

*   <span data-ttu-id="52108-109">Microsoft Edge (legfrissebb elérhető verziója) a Windows 10 rendszeren</span><span class="sxs-lookup"><span data-stu-id="52108-109">Microsoft Edge (latest publicly available version) on Windows 10</span></span>
*   <span data-ttu-id="52108-110">Internet Explorer 11, Windows 10, Windows 8.1 vagy Windows 7 rendszereken</span><span class="sxs-lookup"><span data-stu-id="52108-110">Internet Explorer 11 on Windows 10, Windows 8.1, or Windows 7</span></span>
*   <span data-ttu-id="52108-111">Google Chrome (legfrissebb elérhető verzió)</span><span class="sxs-lookup"><span data-stu-id="52108-111">Google Chrome (latest publicly available version)</span></span>
*   <span data-ttu-id="52108-112">Apple Safari (legfrissebb elérhető verzió)</span><span class="sxs-lookup"><span data-stu-id="52108-112">Apple Safari (latest publicly available version)</span></span>

<span data-ttu-id="52108-113">A böngésző legfrissebb változatáért látogasson el a szoftver gyártójának webhelyére.</span><span class="sxs-lookup"><span data-stu-id="52108-113">To find the latest release for each web browser, go to the software manufacturer’s website.</span></span> 

> [!NOTE]
> * <span data-ttu-id="52108-114">A Task Recorder által generált képek rögzítéséhez és Microsoft Word-dokumentumba való ágyazásához telepítenie kell egy Chrome-bővítményt.</span><span class="sxs-lookup"><span data-stu-id="52108-114">To capture images that are generated from Task Recorder and include them in Microsoft Word documents, you must have a Chrome extension installed.</span></span> 
> * <span data-ttu-id="52108-115">A munkafolyamat-szerkesztő ClickOnce-alkalmazásként indul el.</span><span class="sxs-lookup"><span data-stu-id="52108-115">The Workflow Editor is started as a ClickOnce application.</span></span> <span data-ttu-id="52108-116">Csak Microsoft Edge és Internet Explorer (a Microsoft Windows támogatott verzióin) ClickOnce alkalmazások támogatása.</span><span class="sxs-lookup"><span data-stu-id="52108-116">Only Microsoft Edge and Internet Explorer (on a supported version of Microsoft Windows) support ClickOnce applications.</span></span> <span data-ttu-id="52108-117">A Workflow Editor ClickOnce alkalmazáshoz 64 bit-kompatibilis operációs rendszer szükséges.</span><span class="sxs-lookup"><span data-stu-id="52108-117">The Workflow Editor ClickOnce application requires a 64-bit compatible operating system.</span></span>
> * <span data-ttu-id="52108-118">A PDF-fájlok előnézetének megtekintéséhez olyan modern böngészők használatát javasoljuk, mint a Microsoft Edge (a legújabb nyilvánosan elérhető verzió) Windows 10 rendszeren, illetve a Google Chrome (a legújabb nyilvánosan elérhető verzió) Windows 10, Windows 8.1, Windows 8 vagy Windows 7 rendszeren vagy Google Nexus 10 táblagépeken.</span><span class="sxs-lookup"><span data-stu-id="52108-118">To preview PDF files, we recommend that you use modern browsers like Microsoft Edge (latest publicly available version) on Windows 10, or Google Chrome (latest publicly available version) on Windows 10, Windows 8.1, Windows 8, Windows 7, or Google Nexus 10 tablet.</span></span>
>   <span data-ttu-id="52108-119">Hálózati követelmények</span><span class="sxs-lookup"><span data-stu-id="52108-119">Network requirements</span></span>
> * <span data-ttu-id="52108-120">Dynamics 365 Talent szoftvert olyan hálózatokhoz tervezték, amelyek várakozási ideje 250-300 milliszekund (ms) vagy kevesebb.</span><span class="sxs-lookup"><span data-stu-id="52108-120">Dynamics 365 Talent is designed for networks with latency of 250-300 milliseconds (ms) or less.</span></span> <span data-ttu-id="52108-121">Ez a késleltetés a böngészőklienstől a Microsoft Azure adatközpontig, amely tárolja a Talent szolgáltatást.</span><span class="sxs-lookup"><span data-stu-id="52108-121">This is the latency from a browser client to the Microsoft Azure data center that hosts Talent.</span></span> <span data-ttu-id="52108-122">Javasoljuk, hogy tesztelje a hálózati késleltetést a következő helyen: [www.azurespeed.com](https://www.azurespeed.com "Azure késleltetési teszt").</span><span class="sxs-lookup"><span data-stu-id="52108-122">We recommend that you test network latency at [www.azurespeed.com](https://www.azurespeed.com "Azure Latency Test").</span></span>
> * <span data-ttu-id="52108-123">A Talent sávszélesség-követelményei a forgatókönyvtől függnek.</span><span class="sxs-lookup"><span data-stu-id="52108-123">Bandwidth requirements for Talent depend on your scenario.</span></span> <span data-ttu-id="52108-124">A legtöbb jellemző forgatókönyv másodpercenként több mint 50 kilobájt sávszélességet igényel (KBps).</span><span class="sxs-lookup"><span data-stu-id="52108-124">Most typical scenarios require a bandwidth of more than 50 kilobytes per second (KBps).</span></span>
> 
> [!WARNING]
> <span data-ttu-id="52108-125">Ne úgy számítsa ki a sávszélesség követelményeit az ügyfél helyéről, hogy megszorozza a felhasználók számát a minimális sávszélességi követelményekkel.</span><span class="sxs-lookup"><span data-stu-id="52108-125">Don't compute bandwidth requirements from a client location by multiplying the number of users by the minimum bandwidth requirements.</span></span> <span data-ttu-id="52108-126">Adott hely egyidejű használatát nagyon nehéz kiszámítani.</span><span class="sxs-lookup"><span data-stu-id="52108-126">The concurrent usage of a given location is very difficult to calculate.</span></span> <span data-ttu-id="52108-127">A sávszélesség miatt aggódó ügyfelek számára a Talent próbaverziójának használata ajánlott.</span><span class="sxs-lookup"><span data-stu-id="52108-127">For customers who are concerned about bandwidth requirements, use a trial version of Talent.</span></span>

## <a name="supported-microsoft-office-applications"></a><span data-ttu-id="52108-128">Támogatott Microsoft Office-alkalmazások</span><span class="sxs-lookup"><span data-stu-id="52108-128">Supported Microsoft Office applications</span></span>

* <span data-ttu-id="52108-129">A Microsoft Excel és Word bővítmények futtatásához telepítve kell lennie a Microsoft Office 2016 programnak Windows vagy Mac rendszeren.</span><span class="sxs-lookup"><span data-stu-id="52108-129">To run the Microsoft Excel and Word add-ins, you must have Microsoft Office 2016 for Windows or Mac installed.</span></span> <span data-ttu-id="52108-130">Verziójának követelményeivel kapcsolatos további részletekért lásd: [Office-integráció hibáinak elhárítása](../dev-itpro/office-integration/office-integration-troubleshooting.md "Office-integráció – hibaelhárítás").</span><span class="sxs-lookup"><span data-stu-id="52108-130">For more details about version requirements, see [Office integration troubleshooting](../dev-itpro/office-integration/office-integration-troubleshooting.md "Office integration troubleshooting").</span></span>
* <span data-ttu-id="52108-131">Az Exportálás Excel-be vagy az Exportálás a Word programba funkcióval létrehozott dokumentumok megtekintéséhez telepíteni kell a Microsoft Office 2007 vagy újabb verzióját.</span><span class="sxs-lookup"><span data-stu-id="52108-131">To view documents that are generated by the Export to Excel or Export to Word functionality, you must have Microsoft Office 2007 or later installed.</span></span>

## <a name="regional-availability-languages-and-localization"></a><span data-ttu-id="52108-132">Regionális elérhetőség, nyelvek és lokalizáció</span><span class="sxs-lookup"><span data-stu-id="52108-132">Regional availability, languages, and localization</span></span>

<span data-ttu-id="52108-133">A Talent által támogatott országok, régiók és nyelvek listáját tartalmazó PDF-fájlt a következő helyen töltheti le: [A Microsoft Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability) nemzetközi elérhetősége.</span><span class="sxs-lookup"><span data-stu-id="52108-133">You can download a PDF file of the countries, regions, and languages Talent supports at [International availability of Microsoft Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability).</span></span> 

> [!NOTE]
> <span data-ttu-id="52108-134">A felhasználói felület más nyelvekre való lokalizálása esetén az összes felhasználói adat a megadott nyelven van tárolva.</span><span class="sxs-lookup"><span data-stu-id="52108-134">While the user interface is localized into other languages, all user data is stored in the language in which it was entered.</span></span> <span data-ttu-id="52108-135">E-maileket és sablonokat más nyelveken is létre lehet hozni, de az adatok, például az ütemezési adatok csak angol nyelven érhetők el.</span><span class="sxs-lookup"><span data-stu-id="52108-135">You can create emails and templates in other languages, but data such as scheduling information is only available in English at this time.</span></span>

<span data-ttu-id="52108-136">Ha fejlesztőként érdekelt az ország-vagy régióspecifikus testreszabások létrehozásában, illetve a Microsoft által jelenleg támogatott országhoz vagy régióhoz kapcsolódó megoldások létrehozásában, lásd: [Globalizáció](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lcs-solutions/country-region).</span><span class="sxs-lookup"><span data-stu-id="52108-136">If you're a developer interested in creating country- or region-specific customizations, or in creating a solution for a country or region not currently supported by Microsoft, see [Globalization](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lcs-solutions/country-region).</span></span>

