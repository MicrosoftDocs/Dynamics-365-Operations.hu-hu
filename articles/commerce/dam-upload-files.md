---
title: Képek és videók kivételével a fájlok feltöltése
description: Ez a témakör azt mutatja be, hogyan lehet a Microsoft Dynamics 365 Commerce webhelyszerkesztő alkalmazásban képek és videók kivételével bináris fájlokat feltölteni.
author: psimolin
ms.date: 03/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 380bcccd1053cbcc276e964ce97f16d1d39ea75a
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799253"
---
# <a name="upload-files-other-than-images-and-videos"></a><span data-ttu-id="a2425-103">Fájlok feltöltése képek és videók kivételével</span><span class="sxs-lookup"><span data-stu-id="a2425-103">Upload files other than images and videos</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a2425-104">Ez a témakör azt mutatja be, hogyan lehet a Microsoft Dynamics 365 Commerce webhelyszerkesztő alkalmazásban képek és videók kivételével fájlokat feltölteni.</span><span class="sxs-lookup"><span data-stu-id="a2425-104">This topic describes how to upload files other than images and videos in Microsoft Dynamics 365 Commerce site builder.</span></span>

<span data-ttu-id="a2425-105">A Commerce webhelykészítő médiatárja támogatja a képeket vagy videókat nem tartalmazó bináris eszközök feltöltését.</span><span class="sxs-lookup"><span data-stu-id="a2425-105">The Commerce site builder Media Library supports the uploading of binary assets other than images or videos.</span></span> <span data-ttu-id="a2425-106">Előfordulhat például, hogy fel szeretné tölteni Microsoft Excel, Microsoft Word, Microsoft PowerPoint vagy PDF formátumú fájlokat.</span><span class="sxs-lookup"><span data-stu-id="a2425-106">For example, you might want to upload Microsoft Excel, Microsoft Word, Microsoft PowerPoint, or PDF files.</span></span>

<span data-ttu-id="a2425-107">A következő dokumentumtípusok támogatottak:</span><span class="sxs-lookup"><span data-stu-id="a2425-107">The following document types are supported:</span></span>
- <span data-ttu-id="a2425-108">7Z</span><span class="sxs-lookup"><span data-stu-id="a2425-108">7Z</span></span>
- <span data-ttu-id="a2425-109">AVI</span><span class="sxs-lookup"><span data-stu-id="a2425-109">AVI</span></span>
- <span data-ttu-id="a2425-110">CS</span><span class="sxs-lookup"><span data-stu-id="a2425-110">CS</span></span>
- <span data-ttu-id="a2425-111">CSS</span><span class="sxs-lookup"><span data-stu-id="a2425-111">CSS</span></span>
- <span data-ttu-id="a2425-112">DOC</span><span class="sxs-lookup"><span data-stu-id="a2425-112">DOC</span></span>
- <span data-ttu-id="a2425-113">DOCX</span><span class="sxs-lookup"><span data-stu-id="a2425-113">DOCX</span></span>
- <span data-ttu-id="a2425-114">EPUB</span><span class="sxs-lookup"><span data-stu-id="a2425-114">EPUB</span></span>
- <span data-ttu-id="a2425-115">GIF</span><span class="sxs-lookup"><span data-stu-id="a2425-115">GIF</span></span>
- <span data-ttu-id="a2425-116">INDD</span><span class="sxs-lookup"><span data-stu-id="a2425-116">INDD</span></span>
- <span data-ttu-id="a2425-117">JAR</span><span class="sxs-lookup"><span data-stu-id="a2425-117">JAR</span></span>
- <span data-ttu-id="a2425-118">JPG</span><span class="sxs-lookup"><span data-stu-id="a2425-118">JPG</span></span>
- <span data-ttu-id="a2425-119">JPEG</span><span class="sxs-lookup"><span data-stu-id="a2425-119">JPEG</span></span>
- <span data-ttu-id="a2425-120">JS</span><span class="sxs-lookup"><span data-stu-id="a2425-120">JS</span></span>
- <span data-ttu-id="a2425-121">MP3</span><span class="sxs-lookup"><span data-stu-id="a2425-121">MP3</span></span>
- <span data-ttu-id="a2425-122">MP4</span><span class="sxs-lookup"><span data-stu-id="a2425-122">MP4</span></span>
- <span data-ttu-id="a2425-123">MPEG</span><span class="sxs-lookup"><span data-stu-id="a2425-123">MPEG</span></span>
- <span data-ttu-id="a2425-124">MPG</span><span class="sxs-lookup"><span data-stu-id="a2425-124">MPG</span></span>
- <span data-ttu-id="a2425-125">ODP</span><span class="sxs-lookup"><span data-stu-id="a2425-125">ODP</span></span>
- <span data-ttu-id="a2425-126">ODS</span><span class="sxs-lookup"><span data-stu-id="a2425-126">ODS</span></span>
- <span data-ttu-id="a2425-127">ODT</span><span class="sxs-lookup"><span data-stu-id="a2425-127">ODT</span></span>
- <span data-ttu-id="a2425-128">PDF</span><span class="sxs-lookup"><span data-stu-id="a2425-128">PDF</span></span>
- <span data-ttu-id="a2425-129">PNG</span><span class="sxs-lookup"><span data-stu-id="a2425-129">PNG</span></span>
- <span data-ttu-id="a2425-130">PPT</span><span class="sxs-lookup"><span data-stu-id="a2425-130">PPT</span></span>
- <span data-ttu-id="a2425-131">PPTX</span><span class="sxs-lookup"><span data-stu-id="a2425-131">PPTX</span></span>
- <span data-ttu-id="a2425-132">PS</span><span class="sxs-lookup"><span data-stu-id="a2425-132">PS</span></span>
- <span data-ttu-id="a2425-133">QXP</span><span class="sxs-lookup"><span data-stu-id="a2425-133">QXP</span></span>
- <span data-ttu-id="a2425-134">RAR</span><span class="sxs-lookup"><span data-stu-id="a2425-134">RAR</span></span>
- <span data-ttu-id="a2425-135">RTF</span><span class="sxs-lookup"><span data-stu-id="a2425-135">RTF</span></span>
- <span data-ttu-id="a2425-136">SVG</span><span class="sxs-lookup"><span data-stu-id="a2425-136">SVG</span></span>
- <span data-ttu-id="a2425-137">TAR</span><span class="sxs-lookup"><span data-stu-id="a2425-137">TAR</span></span>
- <span data-ttu-id="a2425-138">TGZ</span><span class="sxs-lookup"><span data-stu-id="a2425-138">TGZ</span></span>
- <span data-ttu-id="a2425-139">TXT</span><span class="sxs-lookup"><span data-stu-id="a2425-139">TXT</span></span>
- <span data-ttu-id="a2425-140">WMV</span><span class="sxs-lookup"><span data-stu-id="a2425-140">WMV</span></span>
- <span data-ttu-id="a2425-141">XLS</span><span class="sxs-lookup"><span data-stu-id="a2425-141">XLS</span></span>
- <span data-ttu-id="a2425-142">XLSX</span><span class="sxs-lookup"><span data-stu-id="a2425-142">XLSX</span></span>
- <span data-ttu-id="a2425-143">XML</span><span class="sxs-lookup"><span data-stu-id="a2425-143">XML</span></span>
- <span data-ttu-id="a2425-144">ZIP</span><span class="sxs-lookup"><span data-stu-id="a2425-144">ZIP</span></span>

## <a name="upload-a-file"></a><span data-ttu-id="a2425-145">Fájl feltöltése</span><span class="sxs-lookup"><span data-stu-id="a2425-145">Upload a file</span></span>

<span data-ttu-id="a2425-146">Ha fel szeretne tölteni egy fájlt a Commerce webhelyszerkesztőben, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="a2425-146">To upload a file to Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="a2425-147">A bal oldali navigációs ablakban válassza ki a **Médiatár** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a2425-147">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="a2425-148">A parancssávon válassza a **Feltöltés \> Médiaelemek feltöltése**.</span><span class="sxs-lookup"><span data-stu-id="a2425-148">On the command bar, select **Upload \> Upload Media Items**.</span></span>
1. <span data-ttu-id="a2425-149">A Fájlkezelő területen jelöljön ki egy vagy több fájlt, majd válassza a **Megnyitás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a2425-149">In File Explorer, select one or more files and then select **Open**.</span></span>
1. <span data-ttu-id="a2425-150">A **Médiaelem feltöltése** párbeszédpanelen szükség szerint adja meg a cím, a leírás és a kulcsszavas metaadatokat.</span><span class="sxs-lookup"><span data-stu-id="a2425-150">In the **Upload Media Item** dialog box, enter title, description, and keyword metadata as needed.</span></span>
1. <span data-ttu-id="a2425-151">Ha azonnal közzétenné a fájl(oka)t a feltöltés után, jelölje be a **Médiatartalom közzététele a feltöltés után** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="a2425-151">To publish the file(s) immediately after upload, select the **Publish media items after upload** check box.</span></span>
1. <span data-ttu-id="a2425-152">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a2425-152">Select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a2425-153">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="a2425-153">Additional resources</span></span>

[<span data-ttu-id="a2425-154">Digitális eszközkezelés – áttekintés</span><span class="sxs-lookup"><span data-stu-id="a2425-154">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="a2425-155">Képek feltöltése</span><span class="sxs-lookup"><span data-stu-id="a2425-155">Upload images</span></span>](dam-upload-images.md)

[<span data-ttu-id="a2425-156">Videó feltöltése</span><span class="sxs-lookup"><span data-stu-id="a2425-156">Upload video</span></span>](dam-upload-video.md)

[<span data-ttu-id="a2425-157">Képek körülvágása</span><span class="sxs-lookup"><span data-stu-id="a2425-157">Crop images</span></span>](dam-crop-images.md)

[<span data-ttu-id="a2425-158">Képfókuszpontok testreszabása</span><span class="sxs-lookup"><span data-stu-id="a2425-158">Customize image focal points</span></span>](dam-custom-focal-point.md)

[<span data-ttu-id="a2425-159">Statikus fájlok feltöltése és kiszolgálása</span><span class="sxs-lookup"><span data-stu-id="a2425-159">Upload and serve static files</span></span>](upload-serve-static-files.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
