---
title: Rendszerkövetelmények
description: Ez a cikk leírja a Microsoft Dynamics 365 Human Resources rendszer követelményeit.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1e7d7389c1bcf0f6024464e37b36d39efae5b832
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2021
ms.locfileid: "5112790"
---
# <a name="system-requirements"></a><span data-ttu-id="5b31c-103">Rendszerkövetelmények</span><span class="sxs-lookup"><span data-stu-id="5b31c-103">System requirements</span></span>

<span data-ttu-id="5b31c-104">Ez a cikk leírja a Microsoft Dynamics 365 Human Resources rendszer követelményeit.</span><span class="sxs-lookup"><span data-stu-id="5b31c-104">This article describes requirements for Microsoft Dynamics 365 Human Resources.</span></span> <span data-ttu-id="5b31c-105">Ezenkívül ismerteti azokat az országokat és régiókat, ahol a Human Resources alkalmazás elérhető, valamint a nyelvekkel és a Human Resources adatainak lokalizációjával kapcsolatban tartalmaz információkat.</span><span class="sxs-lookup"><span data-stu-id="5b31c-105">It also outlines the countries and regions where Human Resources is available, and information about languages and localization for Human Resources data.</span></span>

## <a name="supported-web-browsers"></a><span data-ttu-id="5b31c-106">Támogatott böngészők</span><span class="sxs-lookup"><span data-stu-id="5b31c-106">Supported web browsers</span></span>

<span data-ttu-id="5b31c-107">A Human Resources alkalmazás az alábbi böngészők bármelyikében működik, ha azok a megadott operációs rendszer alatt futnak:</span><span class="sxs-lookup"><span data-stu-id="5b31c-107">Human Resources can run in any of the following web browsers that run on the specified operating systems:</span></span> 

*   <span data-ttu-id="5b31c-108">Microsoft Edge (legfrissebb elérhető verziója) a Windows 10 rendszeren</span><span class="sxs-lookup"><span data-stu-id="5b31c-108">Microsoft Edge (latest publicly available version) on Windows 10</span></span>
*   <span data-ttu-id="5b31c-109">Internet Explorer 11, Windows 10, Windows 8.1 vagy Windows 7 rendszereken</span><span class="sxs-lookup"><span data-stu-id="5b31c-109">Internet Explorer 11 on Windows 10, Windows 8.1, or Windows 7</span></span>
*   <span data-ttu-id="5b31c-110">Google Chrome (legfrissebb elérhető verzió)</span><span class="sxs-lookup"><span data-stu-id="5b31c-110">Google Chrome (latest publicly available version)</span></span>
*   <span data-ttu-id="5b31c-111">Apple Safari (legfrissebb elérhető verzió)</span><span class="sxs-lookup"><span data-stu-id="5b31c-111">Apple Safari (latest publicly available version)</span></span>

<span data-ttu-id="5b31c-112">A böngésző legfrissebb változatáért látogasson el a szoftver gyártójának webhelyére.</span><span class="sxs-lookup"><span data-stu-id="5b31c-112">To find the latest release for each web browser, go to the software manufacturer’s website.</span></span> 

> [!NOTE]
> * <span data-ttu-id="5b31c-113">A Task Recorder által generált képek rögzítéséhez és Microsoft Word-dokumentumba való ágyazásához telepítenie kell egy Chrome-bővítményt.</span><span class="sxs-lookup"><span data-stu-id="5b31c-113">To capture images that are generated from Task Recorder and include them in Microsoft Word documents, you must have a Chrome extension installed.</span></span> 
> * <span data-ttu-id="5b31c-114">A munkafolyamat-szerkesztő ClickOnce-alkalmazásként indul el.</span><span class="sxs-lookup"><span data-stu-id="5b31c-114">The Workflow Editor is started as a ClickOnce application.</span></span> <span data-ttu-id="5b31c-115">Csak Microsoft Edge és Internet Explorer (a Microsoft Windows támogatott verzióin) ClickOnce alkalmazások támogatása.</span><span class="sxs-lookup"><span data-stu-id="5b31c-115">Only Microsoft Edge and Internet Explorer (on a supported version of Microsoft Windows) support ClickOnce applications.</span></span> <span data-ttu-id="5b31c-116">A Workflow Editor ClickOnce alkalmazáshoz 64 bit-kompatibilis operációs rendszer szükséges.</span><span class="sxs-lookup"><span data-stu-id="5b31c-116">The Workflow Editor ClickOnce application requires a 64-bit compatible operating system.</span></span>
> * <span data-ttu-id="5b31c-117">A PDF-fájlok előnézetének megtekintéséhez olyan modern böngészők használatát javasoljuk, mint a Microsoft Edge (a legújabb nyilvánosan elérhető verzió) Windows 10 rendszeren, illetve a Google Chrome (a legújabb nyilvánosan elérhető verzió) Windows 10, Windows 8.1, Windows 8 vagy Windows 7 rendszeren vagy Google Nexus 10 táblagépeken.</span><span class="sxs-lookup"><span data-stu-id="5b31c-117">To preview PDF files, we recommend that you use modern browsers like Microsoft Edge (latest publicly available version) on Windows 10, or Google Chrome (latest publicly available version) on Windows 10, Windows 8.1, Windows 8, Windows 7, or Google Nexus 10 tablet.</span></span>
>   <span data-ttu-id="5b31c-118">Hálózati követelmények</span><span class="sxs-lookup"><span data-stu-id="5b31c-118">Network requirements</span></span>
> * <span data-ttu-id="5b31c-119">A Human Resources alkalmazást olyan hálózatokhoz tervezték, amelyek késleltetési ideje 250-300 milliszekund (ms) vagy kevesebb.</span><span class="sxs-lookup"><span data-stu-id="5b31c-119">Human Resources is designed for networks with latency of 250-300 milliseconds (ms) or less.</span></span> <span data-ttu-id="5b31c-120">Ez a késleltetés a böngészőklienstől a Microsoft Azure adatközpontig, amely tárolja a Human Resources szolgáltatást.</span><span class="sxs-lookup"><span data-stu-id="5b31c-120">This is the latency from a browser client to the Microsoft Azure data center that hosts Human Resources.</span></span> <span data-ttu-id="5b31c-121">Javasoljuk, hogy tesztelje a hálózati késleltetést a következő helyen: [www.azurespeed.com](https://www.azurespeed.com "Azure késleltetési teszt").</span><span class="sxs-lookup"><span data-stu-id="5b31c-121">We recommend that you test network latency at [www.azurespeed.com](https://www.azurespeed.com "Azure Latency Test").</span></span>
> * <span data-ttu-id="5b31c-122">A Human Resources alkalmazás sávszélesség-követelményei a forgatókönyvtől függnek.</span><span class="sxs-lookup"><span data-stu-id="5b31c-122">Bandwidth requirements for Human Resources depend on your scenario.</span></span> <span data-ttu-id="5b31c-123">A legtöbb jellemző forgatókönyv másodpercenként több mint 50 kilobájt sávszélességet igényel (KBps).</span><span class="sxs-lookup"><span data-stu-id="5b31c-123">Most typical scenarios require a bandwidth of more than 50 kilobytes per second (KBps).</span></span>
> 
> [!WARNING]
> <span data-ttu-id="5b31c-124">Ne úgy számítsa ki a sávszélesség követelményeit az ügyfél helyéről, hogy megszorozza a felhasználók számát a minimális sávszélességi követelményekkel.</span><span class="sxs-lookup"><span data-stu-id="5b31c-124">Don't compute bandwidth requirements from a client location by multiplying the number of users by the minimum bandwidth requirements.</span></span> <span data-ttu-id="5b31c-125">Adott hely egyidejű használatát nagyon nehéz kiszámítani.</span><span class="sxs-lookup"><span data-stu-id="5b31c-125">The concurrent usage of a given location is very difficult to calculate.</span></span> <span data-ttu-id="5b31c-126">A sávszélesség miatt aggódó ügyfelek számára a Human Resources próbaverziójának használata ajánlott.</span><span class="sxs-lookup"><span data-stu-id="5b31c-126">For customers who are concerned about bandwidth requirements, use a trial version of Human Resources.</span></span>

## <a name="supported-microsoft-office-applications"></a><span data-ttu-id="5b31c-127">Támogatott Microsoft Office-alkalmazások</span><span class="sxs-lookup"><span data-stu-id="5b31c-127">Supported Microsoft Office applications</span></span>

* <span data-ttu-id="5b31c-128">A Microsoft Excel és Word bővítmények futtatásához telepítve kell lennie a Microsoft Office 2016 programnak Windows vagy Mac rendszeren.</span><span class="sxs-lookup"><span data-stu-id="5b31c-128">To run the Microsoft Excel and Word add-ins, you must have Microsoft Office 2016 for Windows or Mac installed.</span></span> <span data-ttu-id="5b31c-129">Verziójának követelményeivel kapcsolatos további részletekért lásd: [Office-integráció hibáinak elhárítása](../dev-itpro/office-integration/office-integration-troubleshooting.md "Office-integráció – hibaelhárítás").</span><span class="sxs-lookup"><span data-stu-id="5b31c-129">For more details about version requirements, see [Office integration troubleshooting](../dev-itpro/office-integration/office-integration-troubleshooting.md "Office integration troubleshooting").</span></span>
* <span data-ttu-id="5b31c-130">Az Exportálás Excel-be vagy az Exportálás a Word programba funkcióval létrehozott dokumentumok megtekintéséhez telepíteni kell a Microsoft Office 2007 vagy újabb verzióját.</span><span class="sxs-lookup"><span data-stu-id="5b31c-130">To view documents that are generated by the Export to Excel or Export to Word functionality, you must have Microsoft Office 2007 or later installed.</span></span>

## <a name="regional-availability-languages-and-localization"></a><span data-ttu-id="5b31c-131">Regionális elérhetőség, nyelvek és lokalizáció</span><span class="sxs-lookup"><span data-stu-id="5b31c-131">Regional availability, languages, and localization</span></span>

<span data-ttu-id="5b31c-132">A Human Resources által támogatott országok, régiók és nyelvek listáját tartalmazó PDF-fájlt a következő helyen töltheti le: [A Microsoft Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability) nemzetközi elérhetősége.</span><span class="sxs-lookup"><span data-stu-id="5b31c-132">You can download a PDF file of the countries, regions, and languages Human Resources supports at [International availability of Microsoft Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability).</span></span> 

> [!NOTE]
> <span data-ttu-id="5b31c-133">A felhasználói felület más nyelvekre való lokalizálása esetén az összes felhasználói adat a megadott nyelven van tárolva.</span><span class="sxs-lookup"><span data-stu-id="5b31c-133">While the user interface is localized into other languages, all user data is stored in the language in which it was entered.</span></span> <span data-ttu-id="5b31c-134">E-maileket és sablonokat más nyelveken is létre lehet hozni, de az adatok, például az ütemezési adatok csak angol nyelven érhetők el.</span><span class="sxs-lookup"><span data-stu-id="5b31c-134">You can create emails and templates in other languages, but data such as scheduling information is only available in English at this time.</span></span>

<span data-ttu-id="5b31c-135">Ha fejlesztőként érdekelt az ország-vagy régióspecifikus testreszabások létrehozásában, illetve a Microsoft által jelenleg támogatott országhoz vagy régióhoz kapcsolódó megoldások létrehozásában, lásd: [Globalizáció](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lcs-solutions/country-region).</span><span class="sxs-lookup"><span data-stu-id="5b31c-135">If you're a developer interested in creating country- or region-specific customizations, or in creating a solution for a country or region not currently supported by Microsoft, see [Globalization](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lcs-solutions/country-region).</span></span>
