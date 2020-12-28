---
title: Képek és videók kivételével a fájlok feltöltése
description: Ez a témakör azt mutatja be, hogyan lehet a Microsoft Dynamics 365 Commerce webhelyszerkesztő alkalmazásban képek és videók kivételével bináris fájlokat feltölteni.
author: psimolin
manager: annbe
ms.date: 03/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 4acd3bec32cdfe627f6eb33dd5dc652f7cff74a8
ms.sourcegitcommit: 597476103bb695e3cbe6d9ffcd7a466400346636
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/20/2020
ms.locfileid: "4594212"
---
# <a name="upload-files-other-than-images-and-videos"></a><span data-ttu-id="7b62e-103">Képek és videók kivételével a fájlok feltöltése</span><span class="sxs-lookup"><span data-stu-id="7b62e-103">Upload files other than images and videos</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="7b62e-104">Ez a témakör azt mutatja be, hogyan lehet a Microsoft Dynamics 365 Commerce webhelyszerkesztő alkalmazásban képek és videók kivételével fájlokat feltölteni.</span><span class="sxs-lookup"><span data-stu-id="7b62e-104">This topic describes how to upload files other than images and videos in Microsoft Dynamics 365 Commerce site builder.</span></span>

## <a name="overview"></a><span data-ttu-id="7b62e-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="7b62e-105">Overview</span></span>

<span data-ttu-id="7b62e-106">A Commerce webhelykészítő médiatárja támogatja a képeket vagy videókat nem tartalmazó bináris eszközök feltöltését.</span><span class="sxs-lookup"><span data-stu-id="7b62e-106">The Commerce site builder Media Library supports the uploading of binary assets other than images or videos.</span></span> <span data-ttu-id="7b62e-107">Előfordulhat például, hogy fel szeretné tölteni Microsoft Excel, Microsoft Word, Microsoft PowerPoint vagy PDF formátumú fájlokat.</span><span class="sxs-lookup"><span data-stu-id="7b62e-107">For example, you might want to upload Microsoft Excel, Microsoft Word, Microsoft PowerPoint, or PDF files.</span></span>

<span data-ttu-id="7b62e-108">A következő dokumentumtípusok támogatottak:</span><span class="sxs-lookup"><span data-stu-id="7b62e-108">The following document types are supported:</span></span>
- <span data-ttu-id="7b62e-109">7Z</span><span class="sxs-lookup"><span data-stu-id="7b62e-109">7Z</span></span>
- <span data-ttu-id="7b62e-110">AVI</span><span class="sxs-lookup"><span data-stu-id="7b62e-110">AVI</span></span>
- <span data-ttu-id="7b62e-111">CS</span><span class="sxs-lookup"><span data-stu-id="7b62e-111">CS</span></span>
- <span data-ttu-id="7b62e-112">CSS</span><span class="sxs-lookup"><span data-stu-id="7b62e-112">CSS</span></span>
- <span data-ttu-id="7b62e-113">DOC</span><span class="sxs-lookup"><span data-stu-id="7b62e-113">DOC</span></span>
- <span data-ttu-id="7b62e-114">DOCX</span><span class="sxs-lookup"><span data-stu-id="7b62e-114">DOCX</span></span>
- <span data-ttu-id="7b62e-115">EPUB</span><span class="sxs-lookup"><span data-stu-id="7b62e-115">EPUB</span></span>
- <span data-ttu-id="7b62e-116">GIF</span><span class="sxs-lookup"><span data-stu-id="7b62e-116">GIF</span></span>
- <span data-ttu-id="7b62e-117">INDD</span><span class="sxs-lookup"><span data-stu-id="7b62e-117">INDD</span></span>
- <span data-ttu-id="7b62e-118">JAR</span><span class="sxs-lookup"><span data-stu-id="7b62e-118">JAR</span></span>
- <span data-ttu-id="7b62e-119">JPG</span><span class="sxs-lookup"><span data-stu-id="7b62e-119">JPG</span></span>
- <span data-ttu-id="7b62e-120">JPEG</span><span class="sxs-lookup"><span data-stu-id="7b62e-120">JPEG</span></span>
- <span data-ttu-id="7b62e-121">JS</span><span class="sxs-lookup"><span data-stu-id="7b62e-121">JS</span></span>
- <span data-ttu-id="7b62e-122">MP3</span><span class="sxs-lookup"><span data-stu-id="7b62e-122">MP3</span></span>
- <span data-ttu-id="7b62e-123">MP4</span><span class="sxs-lookup"><span data-stu-id="7b62e-123">MP4</span></span>
- <span data-ttu-id="7b62e-124">MPEG</span><span class="sxs-lookup"><span data-stu-id="7b62e-124">MPEG</span></span>
- <span data-ttu-id="7b62e-125">MPG</span><span class="sxs-lookup"><span data-stu-id="7b62e-125">MPG</span></span>
- <span data-ttu-id="7b62e-126">ODP</span><span class="sxs-lookup"><span data-stu-id="7b62e-126">ODP</span></span>
- <span data-ttu-id="7b62e-127">ODS</span><span class="sxs-lookup"><span data-stu-id="7b62e-127">ODS</span></span>
- <span data-ttu-id="7b62e-128">ODT</span><span class="sxs-lookup"><span data-stu-id="7b62e-128">ODT</span></span>
- <span data-ttu-id="7b62e-129">PDF</span><span class="sxs-lookup"><span data-stu-id="7b62e-129">PDF</span></span>
- <span data-ttu-id="7b62e-130">PNG</span><span class="sxs-lookup"><span data-stu-id="7b62e-130">PNG</span></span>
- <span data-ttu-id="7b62e-131">PPT</span><span class="sxs-lookup"><span data-stu-id="7b62e-131">PPT</span></span>
- <span data-ttu-id="7b62e-132">PPTX</span><span class="sxs-lookup"><span data-stu-id="7b62e-132">PPTX</span></span>
- <span data-ttu-id="7b62e-133">PS</span><span class="sxs-lookup"><span data-stu-id="7b62e-133">PS</span></span>
- <span data-ttu-id="7b62e-134">QXP</span><span class="sxs-lookup"><span data-stu-id="7b62e-134">QXP</span></span>
- <span data-ttu-id="7b62e-135">RAR</span><span class="sxs-lookup"><span data-stu-id="7b62e-135">RAR</span></span>
- <span data-ttu-id="7b62e-136">RTF</span><span class="sxs-lookup"><span data-stu-id="7b62e-136">RTF</span></span>
- <span data-ttu-id="7b62e-137">SVG</span><span class="sxs-lookup"><span data-stu-id="7b62e-137">SVG</span></span>
- <span data-ttu-id="7b62e-138">TAR</span><span class="sxs-lookup"><span data-stu-id="7b62e-138">TAR</span></span>
- <span data-ttu-id="7b62e-139">TGZ</span><span class="sxs-lookup"><span data-stu-id="7b62e-139">TGZ</span></span>
- <span data-ttu-id="7b62e-140">TXT</span><span class="sxs-lookup"><span data-stu-id="7b62e-140">TXT</span></span>
- <span data-ttu-id="7b62e-141">WMV</span><span class="sxs-lookup"><span data-stu-id="7b62e-141">WMV</span></span>
- <span data-ttu-id="7b62e-142">XLS</span><span class="sxs-lookup"><span data-stu-id="7b62e-142">XLS</span></span>
- <span data-ttu-id="7b62e-143">XLSX</span><span class="sxs-lookup"><span data-stu-id="7b62e-143">XLSX</span></span>
- <span data-ttu-id="7b62e-144">XML</span><span class="sxs-lookup"><span data-stu-id="7b62e-144">XML</span></span>
- <span data-ttu-id="7b62e-145">ZIP</span><span class="sxs-lookup"><span data-stu-id="7b62e-145">ZIP</span></span>

## <a name="upload-a-file"></a><span data-ttu-id="7b62e-146">Fájl feltöltése</span><span class="sxs-lookup"><span data-stu-id="7b62e-146">Upload a file</span></span>

<span data-ttu-id="7b62e-147">Ha fel szeretne tölteni egy fájlt a Commerce webhelyszerkesztőben, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="7b62e-147">To upload a file to Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="7b62e-148">A bal oldali navigációs ablakban válassza ki a **Médiatár** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7b62e-148">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="7b62e-149">A parancssávon válassza a **Feltöltés \> Médiaelemek feltöltése**.</span><span class="sxs-lookup"><span data-stu-id="7b62e-149">On the command bar, select **Upload \> Upload Media Items**.</span></span>
1. <span data-ttu-id="7b62e-150">A Fájlkezelő területen jelöljön ki egy vagy több fájlt, majd válassza a **Megnyitás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7b62e-150">In File Explorer, select one or more files and then select **Open**.</span></span>
1. <span data-ttu-id="7b62e-151">A **Médiaelem feltöltése** párbeszédpanelen szükség szerint adja meg a cím, a leírás és a kulcsszavas metaadatokat.</span><span class="sxs-lookup"><span data-stu-id="7b62e-151">In the **Upload Media Item** dialog box, enter title, description, and keyword metadata as needed.</span></span>
1. <span data-ttu-id="7b62e-152">Ha azonnal közzétenné a fájl(oka)t a feltöltés után, jelölje be a **Médiatartalom közzététele a feltöltés után** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="7b62e-152">To publish the file(s) immediately after upload, select the **Publish media items after upload** check box.</span></span>
1. <span data-ttu-id="7b62e-153">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7b62e-153">Select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7b62e-154">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="7b62e-154">Additional resources</span></span>

[<span data-ttu-id="7b62e-155">Digitális eszközkezelés – áttekintés</span><span class="sxs-lookup"><span data-stu-id="7b62e-155">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="7b62e-156">Képek feltöltése</span><span class="sxs-lookup"><span data-stu-id="7b62e-156">Upload images</span></span>](dam-upload-images.md)

[<span data-ttu-id="7b62e-157">Videó feltöltése</span><span class="sxs-lookup"><span data-stu-id="7b62e-157">Upload video</span></span>](dam-upload-video.md)

[<span data-ttu-id="7b62e-158">Képek körülvágása</span><span class="sxs-lookup"><span data-stu-id="7b62e-158">Crop images</span></span>](dam-crop-images.md)

[<span data-ttu-id="7b62e-159">Képfókuszpontok testreszabása</span><span class="sxs-lookup"><span data-stu-id="7b62e-159">Customize image focal points</span></span>](dam-custom-focal-point.md)

[<span data-ttu-id="7b62e-160">Statikus fájlok feltöltése és kiszolgálása</span><span class="sxs-lookup"><span data-stu-id="7b62e-160">Upload and serve static files</span></span>](upload-serve-static-files.md)
