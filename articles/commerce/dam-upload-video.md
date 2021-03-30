---
title: Videók feltöltése
description: Ez a témakör azt mutatja be, hogyan tölthet fel videókat a Microsoft Dynamics 365 Commerce webhelykészítőben.
author: psimolin
manager: annbe
ms.date: 03/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
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
ms.openlocfilehash: d74e7116d68074bfc917784a8f51f85d5682c5d6
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5213842"
---
# <a name="upload-videos"></a><span data-ttu-id="6a0f9-103">Videók feltöltése</span><span class="sxs-lookup"><span data-stu-id="6a0f9-103">Upload videos</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="6a0f9-104">Ez a témakör azt mutatja be, hogyan tölthet fel videókat a Microsoft Dynamics 365 Commerce webhelykészítőben.</span><span class="sxs-lookup"><span data-stu-id="6a0f9-104">This topic describes how to upload videos in Microsoft Dynamics 365 Commerce site builder.</span></span>

## <a name="overview"></a><span data-ttu-id="6a0f9-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="6a0f9-105">Overview</span></span>

<span data-ttu-id="6a0f9-106">A Commerce webhelykészítő médiatára segítségével videókat tölthet fel.</span><span class="sxs-lookup"><span data-stu-id="6a0f9-106">The Commerce site builder Media Library allows you to upload videos.</span></span> <span data-ttu-id="6a0f9-107">Mindig a legnagyobb bitrátával és felbontással töltse fel a videót, mert a videót a program automatikusan átváltja különböző nézetablakok és töréspontok számára.</span><span class="sxs-lookup"><span data-stu-id="6a0f9-107">You should always upload the version of a video with the highest bitrate and resolution, because the video will be automatically converted to be suitable for different viewports and their breakpoints.</span></span>

### <a name="video-information-specified-during-upload"></a><span data-ttu-id="6a0f9-108">A feltöltéskor megadott videóinformáció</span><span class="sxs-lookup"><span data-stu-id="6a0f9-108">Video information specified during upload</span></span>

<span data-ttu-id="6a0f9-109">Videó feltöltésekor meg lehet adni a következő adatokat.</span><span class="sxs-lookup"><span data-stu-id="6a0f9-109">When uploading a video, the following information can be specified.</span></span>

- <span data-ttu-id="6a0f9-110">**Cím, leírás, kulcsszavak**: a videó metaadatai.</span><span class="sxs-lookup"><span data-stu-id="6a0f9-110">**Title, Description, Keywords**: Metadata of the video.</span></span>
- <span data-ttu-id="6a0f9-111">**Feliratok automatikus létrehozása**: meghatározza, hogy a rendszer automatikusan generálja-e a feliratokat a videóhoz.</span><span class="sxs-lookup"><span data-stu-id="6a0f9-111">**Automatically generate closed captions**: Specifies whether closed captions should be automatically generated for the video.</span></span>
- <span data-ttu-id="6a0f9-112">**Felirat**: meghatározza a használandó feliratokat.</span><span class="sxs-lookup"><span data-stu-id="6a0f9-112">**Closed Caption**: Specifies the closed captions to be used.</span></span>
- <span data-ttu-id="6a0f9-113">**Normál hang**: meghatározza a normál hangsáv használatát.</span><span class="sxs-lookup"><span data-stu-id="6a0f9-113">**Regular Audio**: Specifies the regular audio track to be used.</span></span>
- <span data-ttu-id="6a0f9-114">**Miniatűr**: meghatározza a videoklip mintaképét.</span><span class="sxs-lookup"><span data-stu-id="6a0f9-114">**Thumbnail**: Specifies the thumbnail for the video.</span></span> <span data-ttu-id="6a0f9-115">Ha nincs megadva, a rendszer automatikusan létrehozza.</span><span class="sxs-lookup"><span data-stu-id="6a0f9-115">If not specified, it will be generated automatically.</span></span>
- <span data-ttu-id="6a0f9-116">**Leíró hang**: meghatározza a leíró hangsáv használatát.</span><span class="sxs-lookup"><span data-stu-id="6a0f9-116">**Descriptive Audio**: Specifies the descriptive audio track to be used.</span></span>

## <a name="upload-a-video"></a><span data-ttu-id="6a0f9-117">Videó feltöltése</span><span class="sxs-lookup"><span data-stu-id="6a0f9-117">Upload a video</span></span>

<span data-ttu-id="6a0f9-118">Ha videót szeretne feltölteni a webhelykészítőbe, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="6a0f9-118">To upload a video in site builder, follow these steps.</span></span>

1. <span data-ttu-id="6a0f9-119">A bal oldali navigációs ablakban válassza ki a **Médiatár** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6a0f9-119">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="6a0f9-120">A parancssávon válassza a **Feltöltés \> Médiaelemek feltöltése**.</span><span class="sxs-lookup"><span data-stu-id="6a0f9-120">On the command bar, select **Upload \> Upload Media Items**.</span></span>
1. <span data-ttu-id="6a0f9-121">A fájlkezelő ablakban navigáljon a lapra, és válasszon ki egy vagy több videofájlot, majd válassza a **Megnyitás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6a0f9-121">In the File Explorer window, navigate to and select one or more video files to upload, and then select **Open**.</span></span>
1. <span data-ttu-id="6a0f9-122">A **médiaelem feltöltése** párbeszédpanelen írja be a szükséges címet és a helyettesítő szöveget.</span><span class="sxs-lookup"><span data-stu-id="6a0f9-122">In the **Upload Media Item** dialog box, enter the required title and alt text.</span></span>
1. <span data-ttu-id="6a0f9-123">Írja be a választható leírást és kulcsszavakat, és ha szükséges, válasszon ki egy kategóriát.</span><span class="sxs-lookup"><span data-stu-id="6a0f9-123">Enter optional description and keywords and select a category if desired.</span></span> 
1. <span data-ttu-id="6a0f9-124">Ha azonnal közzétenné a képeket a feltöltés után, jelölje be a **Médiatartalom közzététele a feltöltés után** jelölőnégyzetet</span><span class="sxs-lookup"><span data-stu-id="6a0f9-124">If you want to publish the image(s) after immediately upload, select the **Publish media items after upload** check box</span></span>
1. <span data-ttu-id="6a0f9-125">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6a0f9-125">Select **OK**.</span></span>

<span data-ttu-id="6a0f9-126">Ha egyszerre több típusú eszközt (például képeket és videókat) tölt fel, akkor a **Médiaelem feltöltése** párbeszédpanelen csak a kulcsszavakat lehet megadni, hogy a fájlok közzététele a feltöltés után azonnal történjen-e, és hogy a feliratok automatikusan megjelenjenek-e a videofájlok esetében.</span><span class="sxs-lookup"><span data-stu-id="6a0f9-126">If you are uploading multiple types of assets simultaneously (for example, images and videos), in the **Upload Media Item** dialog box you will only be able to specify keywords, whether the files should be published immediately after upload, and whether closed captions should be automatically generated for video files.</span></span> <span data-ttu-id="6a0f9-127">Minden eszköz ugyanazokat a kulcsszavakkal fog rendelkezni.</span><span class="sxs-lookup"><span data-stu-id="6a0f9-127">All the assets will share the same keywords.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6a0f9-128">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="6a0f9-128">Additional resources</span></span>

[<span data-ttu-id="6a0f9-129">Digitális eszközkezelés – áttekintés</span><span class="sxs-lookup"><span data-stu-id="6a0f9-129">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="6a0f9-130">Képek feltöltése</span><span class="sxs-lookup"><span data-stu-id="6a0f9-130">Upload images</span></span>](dam-upload-images.md)

[<span data-ttu-id="6a0f9-131">Fájlok feltöltése</span><span class="sxs-lookup"><span data-stu-id="6a0f9-131">Upload files</span></span>](dam-upload-files.md)

[<span data-ttu-id="6a0f9-132">Képek körülvágása</span><span class="sxs-lookup"><span data-stu-id="6a0f9-132">Crop images</span></span>](dam-crop-images.md)

[<span data-ttu-id="6a0f9-133">Képfókuszpontok testreszabása</span><span class="sxs-lookup"><span data-stu-id="6a0f9-133">Customize image focal points</span></span>](dam-custom-focal-point.md)

[<span data-ttu-id="6a0f9-134">Statikus fájlok feltöltése és kiszolgálása</span><span class="sxs-lookup"><span data-stu-id="6a0f9-134">Upload and serve static files</span></span>](upload-serve-static-files.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]