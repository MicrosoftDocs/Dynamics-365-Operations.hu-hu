---
title: A Talent rendszerkövetelményei és frissítési irányelvei
description: Ez a témakör felsorolja a Dynamics 365 for Talent követelményeit. Ezenkívül ismerteti a frissítési irányelvet is.
author: andreabichsel
manager: AnnBe
ms.date: 04/04/2017
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
ms.openlocfilehash: 2389f00b22ec3b5284eeffb2c015533b7a3d13e0
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/19/2019
ms.locfileid: "856301"
---
# <a name="talent-system-requirements-and-update-policy"></a><span data-ttu-id="2e0ad-104">A Talent rendszerkövetelményei és frissítési irányelvei</span><span class="sxs-lookup"><span data-stu-id="2e0ad-104">Talent system requirements and update policy</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="2e0ad-105">Ez a témakör felsorolja a Microsoft Dynamics 365 for Talent követelményeit.</span><span class="sxs-lookup"><span data-stu-id="2e0ad-105">This topic lists requirements for Microsoft Dynamics 365 for Talent.</span></span> <span data-ttu-id="2e0ad-106">Ezenkívül ismerteti a frissítési irányelvet is.</span><span class="sxs-lookup"><span data-stu-id="2e0ad-106">The update policy is outlined, as well.</span></span>

## <a name="supported-web-browsers"></a><span data-ttu-id="2e0ad-107">Támogatott böngészők</span><span class="sxs-lookup"><span data-stu-id="2e0ad-107">Supported web browsers</span></span>

<span data-ttu-id="2e0ad-108">A Microsoft Dynamics 365 for Talent webes alkalmazás az alábbi böngészők bármelyikében működik, ha azok a megadott operációs rendszer alatt futnak:</span><span class="sxs-lookup"><span data-stu-id="2e0ad-108">The Microsoft Dynamics 365 for Talent web application can run in any of the following web browsers that run on the specified operating systems:</span></span> 

*   <span data-ttu-id="2e0ad-109">Microsoft Edge (legfrissebb elérhető verziója) a Windows 10 rendszeren</span><span class="sxs-lookup"><span data-stu-id="2e0ad-109">Microsoft Edge (latest publicly available version) on Windows 10</span></span>
*   <span data-ttu-id="2e0ad-110">Internet Explorer 11, Windows 10, Windows 8.1 vagy Windows 7 rendszereken</span><span class="sxs-lookup"><span data-stu-id="2e0ad-110">Internet Explorer 11 on Windows 10, Windows 8.1, or Windows 7</span></span>
*   <span data-ttu-id="2e0ad-111">Google Chrome (legfrissebb elérhető verzió)</span><span class="sxs-lookup"><span data-stu-id="2e0ad-111">Google Chrome (latest publicly available version)</span></span>
*   <span data-ttu-id="2e0ad-112">Apple Safari (legfrissebb elérhető verzió)</span><span class="sxs-lookup"><span data-stu-id="2e0ad-112">Apple Safari (latest publicly available version)</span></span>

<span data-ttu-id="2e0ad-113">A böngésző legfrissebb változatáért látogasson el a szoftver gyártójának webhelyére.</span><span class="sxs-lookup"><span data-stu-id="2e0ad-113">To find the latest release for each web browser, go to the software manufacturer’s website.</span></span> 

> [!NOTE]
> * <span data-ttu-id="2e0ad-114">A Task Recorder által generált képek rögzítéséhez és Microsoft Word-dokumentumba való ágyazásához telepítenie kell egy Chrome-bővítményt.</span><span class="sxs-lookup"><span data-stu-id="2e0ad-114">To capture images that are generated from Task Recorder and include them in Microsoft Word documents, you must have a Chrome extension installed.</span></span> 
> * <span data-ttu-id="2e0ad-115">A munkafolyamat-szerkesztő ClickOnce-alkalmazásként indul el.</span><span class="sxs-lookup"><span data-stu-id="2e0ad-115">The Workflow Editor is started as a ClickOnce application.</span></span> <span data-ttu-id="2e0ad-116">Csak Microsoft Edge és Internet Explorer (a Microsoft Windows támogatott verzióin) ClickOnce alkalmazások támogatása.</span><span class="sxs-lookup"><span data-stu-id="2e0ad-116">Only Microsoft Edge and Internet Explorer (on a supported version of Microsoft Windows) support ClickOnce applications.</span></span> <span data-ttu-id="2e0ad-117">A Workflow Editor ClickOnce alkalmazáshoz 64 bit-kompatibilis operációs rendszer szükséges.</span><span class="sxs-lookup"><span data-stu-id="2e0ad-117">The Workflow Editor ClickOnce application requires a 64-bit compatible operating system.</span></span>
> * <span data-ttu-id="2e0ad-118">A PDF-fájlok előnézetének megtekintéséhez olyan modern böngészők használatát javasoljuk, mint a Microsoft Edge (a legújabb nyilvánosan elérhető verzió) Windows 10 rendszeren, illetve a Google Chrome (a legújabb nyilvánosan elérhető verzió) Windows 10, Windows 8.1, Windows 8 vagy Windows 7 rendszeren vagy Google Nexus 10 táblagépeken.</span><span class="sxs-lookup"><span data-stu-id="2e0ad-118">To preview PDF files, we recommend that you use modern browsers like Microsoft Edge (latest publicly available version) on Windows 10, or Google Chrome (latest publicly available version) on Windows 10, Windows 8.1, Windows 8, Windows 7, or Google Nexus 10 tablet.</span></span>
>   <span data-ttu-id="2e0ad-119">Hálózati követelmények</span><span class="sxs-lookup"><span data-stu-id="2e0ad-119">Network requirements</span></span>
> * <span data-ttu-id="2e0ad-120">Dynamics 365 for Talent szoftvert olyan hálózatokhoz tervezték, amelyek várakozási ideje 250-300 milliszekund (ms) vagy kevesebb.</span><span class="sxs-lookup"><span data-stu-id="2e0ad-120">Dynamics 365 for Talent is designed for networks with latency of 250-300 milliseconds (ms) or less.</span></span> <span data-ttu-id="2e0ad-121">Ez a késleltetés a böngészőklienstől a Microsoft Azure adatközpontig, amely tárolja a Dynamics 365 for Talent példányt.</span><span class="sxs-lookup"><span data-stu-id="2e0ad-121">This is the latency from a browser client to the Microsoft Azure data center that hosts Dynamics 365 for Talent.</span></span> <span data-ttu-id="2e0ad-122">Javasoljuk, hogy tesztelje a hálózati késleltetést a következő helyen: [www.azurespeed.com](https://www.azurespeed.com "Azure késleltetési teszt").</span><span class="sxs-lookup"><span data-stu-id="2e0ad-122">We recommend that you test network latency at [www.azurespeed.com](https://www.azurespeed.com "Azure Latency Test").</span></span>
> * <span data-ttu-id="2e0ad-123">A Dynamics 365 for Talent sávszélesség-követelményei a forgatókönyvtől függnek.</span><span class="sxs-lookup"><span data-stu-id="2e0ad-123">Bandwidth requirements for Dynamics 365 for Talent depend on your scenario.</span></span> <span data-ttu-id="2e0ad-124">A legtöbb jellemző forgatókönyv másodpercenként több mint 50 kilobájt sávszélességet igényel (KBps).</span><span class="sxs-lookup"><span data-stu-id="2e0ad-124">Most typical scenarios require a bandwidth of more than 50 kilobytes per second (KBps).</span></span>
> 
> [!WARNING]
> <span data-ttu-id="2e0ad-125">Ne úgy számítsa ki a sávszélesség követelményeit az ügyfél helyéről, hogy megszorozza a felhasználók számát a minimális sávszélességi követelményekkel.</span><span class="sxs-lookup"><span data-stu-id="2e0ad-125">Don't compute bandwidth requirements from a client location by multiplying the number of users by the minimum bandwidth requirements.</span></span> <span data-ttu-id="2e0ad-126">Adott hely egyidejű használatát nagyon nehéz kiszámítani.</span><span class="sxs-lookup"><span data-stu-id="2e0ad-126">The concurrent usage of a given location is very difficult to calculate.</span></span> <span data-ttu-id="2e0ad-127">A sávszélesség miatt aggódó ügyfelek számára a Dynamics 365 for Talent próbaverziójának használata ajánlott.</span><span class="sxs-lookup"><span data-stu-id="2e0ad-127">For customers who are concerned about bandwidth requirements, use a trial version of Dynamics 365 for Talent.</span></span>

## <a name="supported-microsoft-office-applications"></a><span data-ttu-id="2e0ad-128">Támogatott Microsoft Office-alkalmazások</span><span class="sxs-lookup"><span data-stu-id="2e0ad-128">Supported Microsoft Office applications</span></span>

* <span data-ttu-id="2e0ad-129">A Microsoft Excel és Word bővítmények futtatásához telepítve kell lennie a Microsoft Office 2016 programnak Windows vagy Mac rendszeren.</span><span class="sxs-lookup"><span data-stu-id="2e0ad-129">To run the Microsoft Excel and Word add-ins, you must have Microsoft Office 2016 for Windows or Mac installed.</span></span> <span data-ttu-id="2e0ad-130">Verziójának követelményeivel kapcsolatos további részletekért lásd: [Office-integráció hibáinak elhárítása](../dev-itpro/office-integration/office-integration-troubleshooting.md "Office-integráció hibáinak elhárítása").</span><span class="sxs-lookup"><span data-stu-id="2e0ad-130">For more details about version requirements, see [Office integration troubleshooting](../dev-itpro/office-integration/office-integration-troubleshooting.md "Office integration troubleshooting").</span></span>
* <span data-ttu-id="2e0ad-131">Az Exportálás Excel-be vagy az Exportálás a Word programba funkcióval létrehozott dokumentumok megtekintéséhez telepíteni kell a Microsoft Office 2007 vagy újabb verzióját.</span><span class="sxs-lookup"><span data-stu-id="2e0ad-131">To view documents that are generated by the Export to Excel or Export to Word functionality, you must have Microsoft Office 2007 or later installed.</span></span>

## <a name="update-policy"></a><span data-ttu-id="2e0ad-132">Frissítési irányelv</span><span class="sxs-lookup"><span data-stu-id="2e0ad-132">Update policy</span></span>

<span data-ttu-id="2e0ad-133">A Microsoft Dynamics 365 for Talent felhőajánlatként van szolgáltatva.</span><span class="sxs-lookup"><span data-stu-id="2e0ad-133">Microsoft Dynamics 365 for Talent is serviced as a cloud offering.</span></span> <span data-ttu-id="2e0ad-134">A Dynamics 365 for Talent frissítései folyamatosak, és a Microsoft automatikusan alkalmazza őket.</span><span class="sxs-lookup"><span data-stu-id="2e0ad-134">Updates to Dynamics 365 for Talent are continuous and applied automatically by Microsoft.</span></span>

<span data-ttu-id="2e0ad-135">A frissítések rendszeres ütemben jelennek meg, és a rendszer minden környezetben alkalmazza őket.</span><span class="sxs-lookup"><span data-stu-id="2e0ad-135">Updates are released on a regular cadence, updates will be made to all environments.</span></span>  <span data-ttu-id="2e0ad-136">A Dynamics 365 for Talent rendszert támogatja a [Microsoft Support Lifecycle policy](https://support.microsoft.com/en-us/gp/lifecycle#gp/OSSLpolicy "Microsoft Support Lifecycle"), amely egységes és kiszámítható irányelveket nyújt a termék elérhetőségével kapcsolatos támogatásról.</span><span class="sxs-lookup"><span data-stu-id="2e0ad-136">Dynamics 365 for Talent is supported according to the [Microsoft Support Lifecycle policy](https://support.microsoft.com/en-us/gp/lifecycle#gp/OSSLpolicy "Microsoft Support Lifecycle"), which provides consistent and predictable guidelines for product support availability.</span></span>
