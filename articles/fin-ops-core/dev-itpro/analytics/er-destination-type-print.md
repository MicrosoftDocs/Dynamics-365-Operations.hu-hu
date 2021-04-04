---
title: Nyomtató ER céltípusa
description: Ez a témakör bemutatja, hogyan kell konfigurálni egy nyomtatási célt az Elektronikus jelentéskészítési (ER) formátumok egyes MAPPA vagy FÁJL összetevőihez.
author: NickSelin
manager: AnnBe
ms.date: 02/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 19613d9dfba21d591d96a2df45bedb80c043b3a7
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561950"
---
# <a name="printer-destination"></a><a name="PrinterDestinationType"></a><span data-ttu-id="b0b0c-103">Nyomtatási cél</span><span class="sxs-lookup"><span data-stu-id="b0b0c-103">Printer destination</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b0b0c-104">A létrejövő dokumentumokat közvetlenül egy hálózati nyomtatóra lehet küldeni közvetlen nyomtatásra.</span><span class="sxs-lookup"><span data-stu-id="b0b0c-104">You can send a generated document directly to a network printer for direct printing.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b0b0c-105">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="b0b0c-105">Prerequisites</span></span>

<span data-ttu-id="b0b0c-106">Először telepítenie és konfigurálnia kell a dokumentumirányítási ügynököt, majd regisztrálnia kell a hálózati nyomtatókat.</span><span class="sxs-lookup"><span data-stu-id="b0b0c-106">Before you begin, you must install and configure the Document Routing Agent, and then register the network printers.</span></span> <span data-ttu-id="b0b0c-107">További információkért lásd: [A Dokumentumirányítási ügynök telepítése a hálózati nyomtatás engedélyezéséhez](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/install-document-routing-agent).</span><span class="sxs-lookup"><span data-stu-id="b0b0c-107">For more information, see [Install the Document Routing Agent to enable network printing](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/install-document-routing-agent).</span></span>

## <a name="make-the-printer-destination-available"></a><span data-ttu-id="b0b0c-108">A nyomtató célhelyének elérhetővé tétele</span><span class="sxs-lookup"><span data-stu-id="b0b0c-108">Make the Printer destination available</span></span>

<span data-ttu-id="b0b0c-109">Ahhoz, hogy a **Nyomtató** célhelyet elérhetővé tegye a Microsoft Dynamics 365 Finance aktuális példányában, lépjen a **Funkció kezelése** munkaterületre, majd kapcsolja be az alábbi funkciókat, ebben a sorrendben:</span><span class="sxs-lookup"><span data-stu-id="b0b0c-109">To make the **Printer** destination available in the current instance of Microsoft Dynamics 365 Finance, go to the **Feature management** workspace, and turn on the following features, in this order:</span></span>

1. <span data-ttu-id="b0b0c-110">A kimenő Elektronikus jelentéskészítési dokumentumok konvertálásának engedélyezése Microsoft Office formátumokról PDF-fájllá</span><span class="sxs-lookup"><span data-stu-id="b0b0c-110">Convert Electronic Reporting outbound documents from Microsoft Office formats to PDF</span></span>
2. <span data-ttu-id="b0b0c-111">Dokumentumirányítási ügynök az Elektronikus jelentéskészítés céljaként a kimenő dokumentumok esetében</span><span class="sxs-lookup"><span data-stu-id="b0b0c-111">Document Routing Agent as Electronic Reporting destination for outbound documents</span></span>

<span data-ttu-id="b0b0c-112">[![Az ER nyomtatócélhely funkció beállítása a Funkció kezelése munkaterületen](./media/ER_Destinations-EnablePrinterDestinationFeature.png)](./media/ER_Destinations-EnablePrinterDestinationFeature.png)</span><span class="sxs-lookup"><span data-stu-id="b0b0c-112">[![Turning on the ER printer destination feature in Feature management](./media/ER_Destinations-EnablePrinterDestinationFeature.png)](./media/ER_Destinations-EnablePrinterDestinationFeature.png)</span></span>

### <a name="applicability"></a><span data-ttu-id="b0b0c-113">Alkalmazhatóság</span><span class="sxs-lookup"><span data-stu-id="b0b0c-113">Applicability</span></span>

<span data-ttu-id="b0b0c-114">A **Nyomtató** célhely csak olyan fájlösszetevőkhöz konfigurálható, amelyek nyomtatható PDF-formátumban (PDF Merger vagy PDF fájlformátumú elemekben) vagy Microsoft Office Excel/Word formátumban (Excel-fájl) generálják a kimenetet.</span><span class="sxs-lookup"><span data-stu-id="b0b0c-114">The **Printer** destination can be configured only for file components that are used to generate output in either printable PDF format (PDF Merger or PDF file format elements) or Microsoft Office Excel/Word format (Excel file).</span></span> <span data-ttu-id="b0b0c-115">Amikor a rendszer létrehozza a PDF formátumú kimenetet, elküldi azt a nyomtatónak.</span><span class="sxs-lookup"><span data-stu-id="b0b0c-115">When output is generated in PDF format, it's sent to a printer.</span></span> <span data-ttu-id="b0b0c-116">Amikor Microsoft Office-formátumú kimenetet generál, a rendszer azt automatikusan PDF-formátumba konvertálja, majd elküldi a nyomtatónak.</span><span class="sxs-lookup"><span data-stu-id="b0b0c-116">When output is generated in Microsoft Office format, it's automatically converted to PDF format and then sent to a printer.</span></span>

### <a name="limitations"></a><span data-ttu-id="b0b0c-117">Korlátozások</span><span class="sxs-lookup"><span data-stu-id="b0b0c-117">Limitations</span></span>

<span data-ttu-id="b0b0c-118">A **Nyomtató** célhely csak felhőalapú telepítések esetén van a rendszerben.</span><span class="sxs-lookup"><span data-stu-id="b0b0c-118">The **Printer** destination is implemented only for cloud deployments.</span></span>

### <a name="use-the-printer-destination"></a><span data-ttu-id="b0b0c-119">A Nyomtató célhely használata</span><span class="sxs-lookup"><span data-stu-id="b0b0c-119">Use the Printer destination</span></span>

1. <span data-ttu-id="b0b0c-120">Az **Engedélyezve** beállítást az **Igen** értékre állítva a létrejövő dokumentumokat elküldi a nyomtatónak.</span><span class="sxs-lookup"><span data-stu-id="b0b0c-120">Set the **Enabled** option to **Yes** to send a generated document to a printer.</span></span>
2. <span data-ttu-id="b0b0c-121">A **Nyomtató neve** mezőben válassza ki a kívánt hálózati nyomtatót.</span><span class="sxs-lookup"><span data-stu-id="b0b0c-121">In the **Printer name** field, select the required network printer.</span></span>
3. <span data-ttu-id="b0b0c-122">Állítsa **Menti a nyomtatási archívumba?** lehetőséget **Igen** értékre, és a létrejövő kimenetet a nyomtatási archívumban tárolhatja, így az további nyomtatás céljából elérhetővé válik.</span><span class="sxs-lookup"><span data-stu-id="b0b0c-122">Set the **Save in print archive?** option to **Yes** to store the generated output in the print archive, so that it's available for further printing.</span></span> <span data-ttu-id="b0b0c-123">Ha később szeretné elérni az archivált kimenetet, nyissa meg a **Szervezeti adminisztráció** \> **Lekérdezések és jelentések** \> **Jelentésarchívum** elemét.</span><span class="sxs-lookup"><span data-stu-id="b0b0c-123">To access archived output later, go to **Organization administration** \> **Inquiries and reports** \> **Report archive**.</span></span>

<span data-ttu-id="b0b0c-124">[![A Nyomtató célhely használata](./media/ER_Destinations-PrinterDestination.png)](./media/ER_Destinations-PrinterDestination.png)</span><span class="sxs-lookup"><span data-stu-id="b0b0c-124">[![Using the Printer destination](./media/ER_Destinations-PrinterDestination.png)](./media/ER_Destinations-PrinterDestination.png)</span></span>

> [!NOTE]
> <span data-ttu-id="b0b0c-125">A **Nyomtató** célhely konfigurálása során nem kell bekapcsolni a **Konvertálás PDF-fájllá** beállítást.</span><span class="sxs-lookup"><span data-stu-id="b0b0c-125">The **Convert to PDF** option doesn't have to be turned on when you configure the **Printer** destination.</span></span> <span data-ttu-id="b0b0c-126">A PDF-konverzió nyomtatás céljából akkor is megtörténhet, ha a beállítás ki van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="b0b0c-126">The PDF conversion for printing purposes will occur even if the option is turned off.</span></span>

<span data-ttu-id="b0b0c-127">Ha egy adott [oldaltájolást](electronic-reporting-destinations.md#SelectPdfPageOrientation) szeretne használni a kimenő dokumentumok Excel-formátumba történő nyomtatásakor, akkor be kell kapcsolnia a **Konvertálás PDF-fájllá** beállítást.</span><span class="sxs-lookup"><span data-stu-id="b0b0c-127">To use a specific [page orientation](electronic-reporting-destinations.md#SelectPdfPageOrientation) when you print an outbound document in Excel format, you must turn on the **Convert to PDF** option.</span></span> <span data-ttu-id="b0b0c-128">Ha a **Konvertálás PDF-fájllá** beállítást **Igen** értékre állítja az **Oldaltájolás** mező elérhetővé válik.</span><span class="sxs-lookup"><span data-stu-id="b0b0c-128">When you set the **Convert to PDF** option to **Yes**, the **Page orientation** field becomes available.</span></span> <span data-ttu-id="b0b0c-129">A **Lap tájolása** mezőben kiválaszthat egy oldaltájolást.</span><span class="sxs-lookup"><span data-stu-id="b0b0c-129">In the **Page orientation** field, you can select a page orientation.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b0b0c-130">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="b0b0c-130">Additional resources</span></span>

- [<span data-ttu-id="b0b0c-131">Elektronikus jelentéskészítés (ER) áttekintése</span><span class="sxs-lookup"><span data-stu-id="b0b0c-131">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="b0b0c-132">Elektronikus jelentéskészítés (ER) céljai</span><span class="sxs-lookup"><span data-stu-id="b0b0c-132">Electronic reporting (ER) destinations</span></span>](electronic-reporting-destinations.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
