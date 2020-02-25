---
title: Nyomtató ER céltípusa
description: Ez a témakör azt mutatja be, hogyan lehet beállítani egy nyomtatót célhelyként a kimenő dokumentumok létrehozásához konfigurált elektronikus jelentési (ER) formátumú fájlok MAPPA vagy FÁJL összetevőihez PDF vagy Microsoft Office-formátumokban (Excel/Word).
author: NickSelin
manager: AnnBe
ms.date: 01/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 58e067baa130458e3a8e788d978604f208140a03
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019807"
---
# <a name="PrinterDestinationType"></a><span data-ttu-id="f3f45-103">Nyomtató célhely</span><span class="sxs-lookup"><span data-stu-id="f3f45-103">Printer destination</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f3f45-104">A létrejövő dokumentumokat közvetlenül egy hálózati nyomtatóra lehet küldeni közvetlen nyomtatásra.</span><span class="sxs-lookup"><span data-stu-id="f3f45-104">You can send a generated document directly to a network printer for direct printing.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f3f45-105">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="f3f45-105">Prerequisites</span></span>

<span data-ttu-id="f3f45-106">Először telepítenie és konfigurálnia kell a dokumentumirányítási ügynököt, majd regisztrálnia kell a hálózati nyomtatókat.</span><span class="sxs-lookup"><span data-stu-id="f3f45-106">Before you begin, you must install and configure the Document Routing Agent, and then register the network printers.</span></span> <span data-ttu-id="f3f45-107">További információkért lásd: [A Dokumentumirányítási ügynök telepítése a hálózati nyomtatás engedélyezéséhez](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/install-document-routing-agent).</span><span class="sxs-lookup"><span data-stu-id="f3f45-107">For more information, see [Install the Document Routing Agent to enable network printing](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/install-document-routing-agent).</span></span>

## <a name="make-the-printer-destination-available"></a><span data-ttu-id="f3f45-108">A nyomtató célhelyének elérhetővé tétele</span><span class="sxs-lookup"><span data-stu-id="f3f45-108">Make the Printer destination available</span></span>

<span data-ttu-id="f3f45-109">Ahhoz, hogy a **Nyomtató** célhelyet elérhetővé tegye a Microsoft Dynamics 365 Finance aktuális példányában, lépjen a **Funkció kezelése** munkaterületre, majd kapcsolja be az alábbi funkciókat, ebben a sorrendben:</span><span class="sxs-lookup"><span data-stu-id="f3f45-109">To make the **Printer** destination available in the current instance of Microsoft Dynamics 365 Finance, go to the **Feature management** workspace, and turn on the following features, in this order:</span></span>

1. <span data-ttu-id="f3f45-110">A kimenő Elektronikus jelentéskészítési dokumentumok konvertálásának engedélyezése Microsoft Office formátumokról PDF-fájllá</span><span class="sxs-lookup"><span data-stu-id="f3f45-110">Convert Electronic Reporting outbound documents from Microsoft Office formats to PDF</span></span>
2. <span data-ttu-id="f3f45-111">Dokumentumirányítási ügynök az Elektronikus jelentéskészítés céljaként a kimenő dokumentumok esetében</span><span class="sxs-lookup"><span data-stu-id="f3f45-111">Document Routing Agent as Electronic Reporting destination for outbound documents</span></span>

<span data-ttu-id="f3f45-112">[![Az ER nyomtatócélhely funkció beállítása a Funkció kezelése munkaterületen](./media/ER_Destinations-EnablePrinterDestinationFeature.png)](./media/ER_Destinations-EnablePrinterDestinationFeature.png)</span><span class="sxs-lookup"><span data-stu-id="f3f45-112">[![Turning on the ER printer destination feature in Feature management](./media/ER_Destinations-EnablePrinterDestinationFeature.png)](./media/ER_Destinations-EnablePrinterDestinationFeature.png)</span></span>

### <a name="applicability"></a><span data-ttu-id="f3f45-113">Alkalmazhatóság</span><span class="sxs-lookup"><span data-stu-id="f3f45-113">Applicability</span></span>

<span data-ttu-id="f3f45-114">A **Nyomtató** célhely csak olyan fájlösszetevőkhöz konfigurálható, amelyek nyomtatható PDF-formátumban (PDF Merger vagy PDF fájlformátumú elemekben) vagy Microsoft Office Excel/Word formátumban (Excel-fájl) generálják a kimenetet.</span><span class="sxs-lookup"><span data-stu-id="f3f45-114">The **Printer** destination can be configured only for file components that are used to generate output in either printable PDF format (PDF Merger or PDF file format elements) or Microsoft Office Excel/Word format (Excel file).</span></span> <span data-ttu-id="f3f45-115">Amikor a rendszer létrehozza a PDF formátumú kimenetet, elküldi azt a nyomtatónak.</span><span class="sxs-lookup"><span data-stu-id="f3f45-115">When output is generated in PDF format, it's sent to a printer.</span></span> <span data-ttu-id="f3f45-116">Amikor Microsoft Office-formátumú kimenetet generál, a rendszer azt automatikusan PDF-formátumba konvertálja, majd elküldi a nyomtatónak.</span><span class="sxs-lookup"><span data-stu-id="f3f45-116">When output is generated in Microsoft Office format, it's automatically converted to PDF format and then sent to a printer.</span></span>

### <a name="limitations"></a><span data-ttu-id="f3f45-117">Korlátozások</span><span class="sxs-lookup"><span data-stu-id="f3f45-117">Limitations</span></span>

<span data-ttu-id="f3f45-118">Ez a funkció egy előnézeti funkció, azok a felhasználási feltételek vonatkoznak rá, amelyek itt olvashatók: [Kiegészítő felhasználási feltételek a Microsoft Dynamics 365 előnézetek esetén](https://go.microsoft.com/fwlink/?linkid=2105274).</span><span class="sxs-lookup"><span data-stu-id="f3f45-118">This feature is a preview feature and is subject to the terms of use that are described in [Supplemental Terms of Use for Microsoft Dynamics 365 Previews](https://go.microsoft.com/fwlink/?linkid=2105274).</span></span>

<span data-ttu-id="f3f45-119">A **Nyomtató** célhely csak felhőalapú telepítések esetén van a rendszerben.</span><span class="sxs-lookup"><span data-stu-id="f3f45-119">The **Printer** destination is implemented only for cloud deployments.</span></span>

### <a name="use-the-printer-destination"></a><span data-ttu-id="f3f45-120">A Nyomtató célhely használata</span><span class="sxs-lookup"><span data-stu-id="f3f45-120">Use the Printer destination</span></span>

1. <span data-ttu-id="f3f45-121">Az **Engedélyezve** beállítást az **Igen** értékre állítva a létrejövő dokumentumokat elküldi a nyomtatónak.</span><span class="sxs-lookup"><span data-stu-id="f3f45-121">Set the **Enabled** option to **Yes** to send a generated document to a printer.</span></span>
2. <span data-ttu-id="f3f45-122">A **Nyomtató neve** mezőben válassza ki a kívánt hálózati nyomtatót.</span><span class="sxs-lookup"><span data-stu-id="f3f45-122">In the **Printer name** field, select the required network printer.</span></span>
3. <span data-ttu-id="f3f45-123">Állítsa **Menti a nyomtatási archívumba?** lehetőséget **Igen** értékre, és a létrejövő kimenetet a nyomtatási archívumban tárolhatja, így az további nyomtatás céljából elérhetővé válik.</span><span class="sxs-lookup"><span data-stu-id="f3f45-123">Set the **Save in print archive?** option to **Yes** to store the generated output in the print archive, so that it's available for further printing.</span></span> <span data-ttu-id="f3f45-124">Ha később szeretné elérni az archivált kimenetet, nyissa meg a **Szervezeti adminisztráció** \> **Lekérdezések és jelentések** \> **Jelentésarchívum** elemét.</span><span class="sxs-lookup"><span data-stu-id="f3f45-124">To access archived output later, go to **Organization administration** \> **Inquiries and reports** \> **Report archive**.</span></span>

<span data-ttu-id="f3f45-125">[![A Nyomtató célhely használata](./media/ER_Destinations-PrinterDestination.png)](./media/ER_Destinations-PrinterDestination.png)</span><span class="sxs-lookup"><span data-stu-id="f3f45-125">[![Using the Printer destination](./media/ER_Destinations-PrinterDestination.png)](./media/ER_Destinations-PrinterDestination.png)</span></span>

> [!NOTE]
> <span data-ttu-id="f3f45-126">A **Nyomtató** célhely konfigurálása során nem kell bekapcsolni a **Konvertálás PDF-fájllá** beállítást.</span><span class="sxs-lookup"><span data-stu-id="f3f45-126">The **Convert to PDF** option doesn't have to be turned on when you configure the **Printer** destination.</span></span> <span data-ttu-id="f3f45-127">A PDF-konverzió nyomtatás céljából akkor is megtörténhet, ha a beállítás ki van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="f3f45-127">The PDF conversion for printing purposes will occur even if the option is turned off.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f3f45-128">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="f3f45-128">Additional resources</span></span>

- [<span data-ttu-id="f3f45-129">Elektronikus jelentéskészítés (ER) áttekintése</span><span class="sxs-lookup"><span data-stu-id="f3f45-129">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="f3f45-130">Elektronikus jelentéskészítés (ER) céljai</span><span class="sxs-lookup"><span data-stu-id="f3f45-130">Electronic reporting (ER) destinations</span></span>](electronic-reporting-destinations.md)
