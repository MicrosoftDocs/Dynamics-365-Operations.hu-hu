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
ms.openlocfilehash: fc0490e3532dcbb9c1e91101009b2d4605315416
ms.sourcegitcommit: 567132f4e4f7a1d76dccf762068209a42c788b52
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/03/2020
ms.locfileid: "3097024"
---
# <a name="upload-files-other-than-images-and-videos"></a><span data-ttu-id="8803a-103">Képek és videók kivételével a fájlok feltöltése</span><span class="sxs-lookup"><span data-stu-id="8803a-103">Upload files other than images and videos</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="8803a-104">Ez a témakör azt mutatja be, hogyan lehet a Microsoft Dynamics 365 Commerce webhelyszerkesztő alkalmazásban képek és videók kivételével fájlokat feltölteni.</span><span class="sxs-lookup"><span data-stu-id="8803a-104">This topic describes how to upload files other than images and videos in Microsoft Dynamics 365 Commerce site builder.</span></span>

## <a name="overview"></a><span data-ttu-id="8803a-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="8803a-105">Overview</span></span>

<span data-ttu-id="8803a-106">A Commerce webhelykészítő médiatárja támogatja a képeket vagy videókat nem tartalmazó bináris eszközök feltöltését.</span><span class="sxs-lookup"><span data-stu-id="8803a-106">The Commerce site builder Media Library supports the uploading of binary assets other than images or videos.</span></span> <span data-ttu-id="8803a-107">Előfordulhat például, hogy fel szeretné tölteni Microsoft Excel, Microsoft Word, Microsoft PowerPoint vagy PDF formátumú fájlokat.</span><span class="sxs-lookup"><span data-stu-id="8803a-107">For example, you might want to upload Microsoft Excel, Microsoft Word, Microsoft PowerPoint, or PDF files.</span></span>

<span data-ttu-id="8803a-108">A következő dokumentumtípusok támogatottak:</span><span class="sxs-lookup"><span data-stu-id="8803a-108">The following document types are supported:</span></span>
- <span data-ttu-id="8803a-109">7Z</span><span class="sxs-lookup"><span data-stu-id="8803a-109">7Z</span></span>
- <span data-ttu-id="8803a-110">AVI</span><span class="sxs-lookup"><span data-stu-id="8803a-110">AVI</span></span>
- <span data-ttu-id="8803a-111">CS</span><span class="sxs-lookup"><span data-stu-id="8803a-111">CS</span></span>
- <span data-ttu-id="8803a-112">CSS</span><span class="sxs-lookup"><span data-stu-id="8803a-112">CSS</span></span>
- <span data-ttu-id="8803a-113">DOC</span><span class="sxs-lookup"><span data-stu-id="8803a-113">DOC</span></span>
- <span data-ttu-id="8803a-114">DOCX</span><span class="sxs-lookup"><span data-stu-id="8803a-114">DOCX</span></span>
- <span data-ttu-id="8803a-115">EPUB</span><span class="sxs-lookup"><span data-stu-id="8803a-115">EPUB</span></span>
- <span data-ttu-id="8803a-116">GIF</span><span class="sxs-lookup"><span data-stu-id="8803a-116">GIF</span></span>
- <span data-ttu-id="8803a-117">INDD</span><span class="sxs-lookup"><span data-stu-id="8803a-117">INDD</span></span>
- <span data-ttu-id="8803a-118">JAR</span><span class="sxs-lookup"><span data-stu-id="8803a-118">JAR</span></span>
- <span data-ttu-id="8803a-119">JPG</span><span class="sxs-lookup"><span data-stu-id="8803a-119">JPG</span></span>
- <span data-ttu-id="8803a-120">JPEG</span><span class="sxs-lookup"><span data-stu-id="8803a-120">JPEG</span></span>
- <span data-ttu-id="8803a-121">JS</span><span class="sxs-lookup"><span data-stu-id="8803a-121">JS</span></span>
- <span data-ttu-id="8803a-122">MP3</span><span class="sxs-lookup"><span data-stu-id="8803a-122">MP3</span></span>
- <span data-ttu-id="8803a-123">MP4</span><span class="sxs-lookup"><span data-stu-id="8803a-123">MP4</span></span>
- <span data-ttu-id="8803a-124">MPEG</span><span class="sxs-lookup"><span data-stu-id="8803a-124">MPEG</span></span>
- <span data-ttu-id="8803a-125">MPG</span><span class="sxs-lookup"><span data-stu-id="8803a-125">MPG</span></span>
- <span data-ttu-id="8803a-126">ODP</span><span class="sxs-lookup"><span data-stu-id="8803a-126">ODP</span></span>
- <span data-ttu-id="8803a-127">ODS</span><span class="sxs-lookup"><span data-stu-id="8803a-127">ODS</span></span>
- <span data-ttu-id="8803a-128">ODT</span><span class="sxs-lookup"><span data-stu-id="8803a-128">ODT</span></span>
- <span data-ttu-id="8803a-129">PDF</span><span class="sxs-lookup"><span data-stu-id="8803a-129">PDF</span></span>
- <span data-ttu-id="8803a-130">PNG</span><span class="sxs-lookup"><span data-stu-id="8803a-130">PNG</span></span>
- <span data-ttu-id="8803a-131">PPT</span><span class="sxs-lookup"><span data-stu-id="8803a-131">PPT</span></span>
- <span data-ttu-id="8803a-132">PPTX</span><span class="sxs-lookup"><span data-stu-id="8803a-132">PPTX</span></span>
- <span data-ttu-id="8803a-133">PS</span><span class="sxs-lookup"><span data-stu-id="8803a-133">PS</span></span>
- <span data-ttu-id="8803a-134">QXP</span><span class="sxs-lookup"><span data-stu-id="8803a-134">QXP</span></span>
- <span data-ttu-id="8803a-135">RAR</span><span class="sxs-lookup"><span data-stu-id="8803a-135">RAR</span></span>
- <span data-ttu-id="8803a-136">RTF</span><span class="sxs-lookup"><span data-stu-id="8803a-136">RTF</span></span>
- <span data-ttu-id="8803a-137">SVG</span><span class="sxs-lookup"><span data-stu-id="8803a-137">SVG</span></span>
- <span data-ttu-id="8803a-138">TAR</span><span class="sxs-lookup"><span data-stu-id="8803a-138">TAR</span></span>
- <span data-ttu-id="8803a-139">TGZ</span><span class="sxs-lookup"><span data-stu-id="8803a-139">TGZ</span></span>
- <span data-ttu-id="8803a-140">TXT</span><span class="sxs-lookup"><span data-stu-id="8803a-140">TXT</span></span>
- <span data-ttu-id="8803a-141">WMV</span><span class="sxs-lookup"><span data-stu-id="8803a-141">WMV</span></span>
- <span data-ttu-id="8803a-142">XLS</span><span class="sxs-lookup"><span data-stu-id="8803a-142">XLS</span></span>
- <span data-ttu-id="8803a-143">XLSX</span><span class="sxs-lookup"><span data-stu-id="8803a-143">XLSX</span></span>
- <span data-ttu-id="8803a-144">XML</span><span class="sxs-lookup"><span data-stu-id="8803a-144">XML</span></span>
- <span data-ttu-id="8803a-145">ZIP</span><span class="sxs-lookup"><span data-stu-id="8803a-145">ZIP</span></span>

## <a name="upload-a-file"></a><span data-ttu-id="8803a-146">Fájl feltöltése</span><span class="sxs-lookup"><span data-stu-id="8803a-146">Upload a file</span></span>

<span data-ttu-id="8803a-147">Ha fel szeretne tölteni egy fájlt a Commerce webhelyszerkesztőben, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="8803a-147">To upload a file to Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="8803a-148">A bal oldali navigációs ablakban válassza ki a **Médiatár** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8803a-148">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="8803a-149">A parancssávon válassza a **Feltöltés \> Médiaelemek feltöltése**.</span><span class="sxs-lookup"><span data-stu-id="8803a-149">On the command bar, select **Upload \> Upload Media Items**.</span></span>
1. <span data-ttu-id="8803a-150">A Fájlkezelő területen jelöljön ki egy vagy több fájlt, majd válassza a **Megnyitás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8803a-150">In File Explorer, select one or more files and then select **Open**.</span></span>
1. <span data-ttu-id="8803a-151">A **Médiaelem feltöltése** párbeszédpanelen szükség szerint adja meg a cím, a leírás és a kulcsszavas metaadatokat.</span><span class="sxs-lookup"><span data-stu-id="8803a-151">In the **Upload Media Item** dialog box, enter title, description, and keyword metadata as needed.</span></span>
1. <span data-ttu-id="8803a-152">Ha azonnal közzétenné a fájl(oka)t a feltöltés után, jelölje be a **Médiatartalom közzététele a feltöltés után** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="8803a-152">To publish the file(s) immediately after upload, select the **Publish media items after upload** check box.</span></span>
1. <span data-ttu-id="8803a-153">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8803a-153">Select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8803a-154">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="8803a-154">Additional resources</span></span>

[<span data-ttu-id="8803a-155">Digitális eszközkezelés – áttekintés</span><span class="sxs-lookup"><span data-stu-id="8803a-155">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="8803a-156">Képek feltöltése</span><span class="sxs-lookup"><span data-stu-id="8803a-156">Upload images</span></span>](dam-upload-images.md)

[<span data-ttu-id="8803a-157">Videó feltöltése</span><span class="sxs-lookup"><span data-stu-id="8803a-157">Upload video</span></span>](dam-upload-video.md)

[<span data-ttu-id="8803a-158">Képek körülvágása</span><span class="sxs-lookup"><span data-stu-id="8803a-158">Crop images</span></span>](dam-crop-images.md)

[<span data-ttu-id="8803a-159">Kép fókuszpontok testreszabása</span><span class="sxs-lookup"><span data-stu-id="8803a-159">Customize image focal points</span></span>](dam-custom-focal-point.md)
