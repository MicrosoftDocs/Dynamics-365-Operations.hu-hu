---
title: Videók feltöltése
description: Ez a témakör azt mutatja be, hogyan tölthet fel videókat a Microsoft Dynamics 365 Commerce webhelykészítőben.
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
ms.openlocfilehash: 5ec20f8caee2f5a62230be05923dfd52600c1e35
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799205"
---
# <a name="upload-videos"></a><span data-ttu-id="42328-103">Videók feltöltése</span><span class="sxs-lookup"><span data-stu-id="42328-103">Upload videos</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="42328-104">Ez a témakör azt mutatja be, hogyan tölthet fel videókat a Microsoft Dynamics 365 Commerce webhelykészítőben.</span><span class="sxs-lookup"><span data-stu-id="42328-104">This topic describes how to upload videos in Microsoft Dynamics 365 Commerce site builder.</span></span>

<span data-ttu-id="42328-105">A Commerce webhelykészítő médiatára segítségével videókat tölthet fel.</span><span class="sxs-lookup"><span data-stu-id="42328-105">The Commerce site builder Media Library allows you to upload videos.</span></span> <span data-ttu-id="42328-106">Mindig a legnagyobb bitrátával és felbontással töltse fel a videót, mert a videót a program automatikusan átváltja különböző nézetablakok és töréspontok számára.</span><span class="sxs-lookup"><span data-stu-id="42328-106">You should always upload the version of a video with the highest bitrate and resolution, because the video will be automatically converted to be suitable for different viewports and their breakpoints.</span></span>

### <a name="video-information-specified-during-upload"></a><span data-ttu-id="42328-107">A feltöltéskor megadott videóinformáció</span><span class="sxs-lookup"><span data-stu-id="42328-107">Video information specified during upload</span></span>

<span data-ttu-id="42328-108">Videó feltöltésekor meg lehet adni a következő adatokat.</span><span class="sxs-lookup"><span data-stu-id="42328-108">When uploading a video, the following information can be specified.</span></span>

- <span data-ttu-id="42328-109">**Cím, leírás, kulcsszavak**: a videó metaadatai.</span><span class="sxs-lookup"><span data-stu-id="42328-109">**Title, Description, Keywords**: Metadata of the video.</span></span>
- <span data-ttu-id="42328-110">**Feliratok automatikus létrehozása**: meghatározza, hogy a rendszer automatikusan generálja-e a feliratokat a videóhoz.</span><span class="sxs-lookup"><span data-stu-id="42328-110">**Automatically generate closed captions**: Specifies whether closed captions should be automatically generated for the video.</span></span>
- <span data-ttu-id="42328-111">**Felirat**: meghatározza a használandó feliratokat.</span><span class="sxs-lookup"><span data-stu-id="42328-111">**Closed Caption**: Specifies the closed captions to be used.</span></span>
- <span data-ttu-id="42328-112">**Normál hang**: meghatározza a normál hangsáv használatát.</span><span class="sxs-lookup"><span data-stu-id="42328-112">**Regular Audio**: Specifies the regular audio track to be used.</span></span>
- <span data-ttu-id="42328-113">**Miniatűr**: meghatározza a videoklip mintaképét.</span><span class="sxs-lookup"><span data-stu-id="42328-113">**Thumbnail**: Specifies the thumbnail for the video.</span></span> <span data-ttu-id="42328-114">Ha nincs megadva, a rendszer automatikusan létrehozza.</span><span class="sxs-lookup"><span data-stu-id="42328-114">If not specified, it will be generated automatically.</span></span>
- <span data-ttu-id="42328-115">**Leíró hang**: meghatározza a leíró hangsáv használatát.</span><span class="sxs-lookup"><span data-stu-id="42328-115">**Descriptive Audio**: Specifies the descriptive audio track to be used.</span></span>

## <a name="upload-a-video"></a><span data-ttu-id="42328-116">Videó feltöltése</span><span class="sxs-lookup"><span data-stu-id="42328-116">Upload a video</span></span>

<span data-ttu-id="42328-117">Ha videót szeretne feltölteni a webhelykészítőbe, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="42328-117">To upload a video in site builder, follow these steps.</span></span>

1. <span data-ttu-id="42328-118">A bal oldali navigációs ablakban válassza ki a **Médiatár** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="42328-118">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="42328-119">A parancssávon válassza a **Feltöltés \> Médiaelemek feltöltése**.</span><span class="sxs-lookup"><span data-stu-id="42328-119">On the command bar, select **Upload \> Upload Media Items**.</span></span>
1. <span data-ttu-id="42328-120">A fájlkezelő ablakban navigáljon a lapra, és válasszon ki egy vagy több videofájlot, majd válassza a **Megnyitás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="42328-120">In the File Explorer window, navigate to and select one or more video files to upload, and then select **Open**.</span></span>
1. <span data-ttu-id="42328-121">A **médiaelem feltöltése** párbeszédpanelen írja be a szükséges címet és a helyettesítő szöveget.</span><span class="sxs-lookup"><span data-stu-id="42328-121">In the **Upload Media Item** dialog box, enter the required title and alt text.</span></span>
1. <span data-ttu-id="42328-122">Írja be a választható leírást és kulcsszavakat, és ha szükséges, válasszon ki egy kategóriát.</span><span class="sxs-lookup"><span data-stu-id="42328-122">Enter optional description and keywords and select a category if desired.</span></span> 
1. <span data-ttu-id="42328-123">Ha azonnal közzétenné a képeket a feltöltés után, jelölje be a **Médiatartalom közzététele a feltöltés után** jelölőnégyzetet</span><span class="sxs-lookup"><span data-stu-id="42328-123">If you want to publish the image(s) after immediately upload, select the **Publish media items after upload** check box</span></span>
1. <span data-ttu-id="42328-124">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="42328-124">Select **OK**.</span></span>

<span data-ttu-id="42328-125">Ha egyszerre több típusú eszközt (például képeket és videókat) tölt fel, akkor a **Médiaelem feltöltése** párbeszédpanelen csak a kulcsszavakat lehet megadni, hogy a fájlok közzététele a feltöltés után azonnal történjen-e, és hogy a feliratok automatikusan megjelenjenek-e a videofájlok esetében.</span><span class="sxs-lookup"><span data-stu-id="42328-125">If you are uploading multiple types of assets simultaneously (for example, images and videos), in the **Upload Media Item** dialog box you will only be able to specify keywords, whether the files should be published immediately after upload, and whether closed captions should be automatically generated for video files.</span></span> <span data-ttu-id="42328-126">Minden eszköz ugyanazokat a kulcsszavakkal fog rendelkezni.</span><span class="sxs-lookup"><span data-stu-id="42328-126">All the assets will share the same keywords.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="42328-127">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="42328-127">Additional resources</span></span>

[<span data-ttu-id="42328-128">Digitális eszközkezelés – áttekintés</span><span class="sxs-lookup"><span data-stu-id="42328-128">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="42328-129">Képek feltöltése</span><span class="sxs-lookup"><span data-stu-id="42328-129">Upload images</span></span>](dam-upload-images.md)

[<span data-ttu-id="42328-130">Fájlok feltöltése</span><span class="sxs-lookup"><span data-stu-id="42328-130">Upload files</span></span>](dam-upload-files.md)

[<span data-ttu-id="42328-131">Képek körülvágása</span><span class="sxs-lookup"><span data-stu-id="42328-131">Crop images</span></span>](dam-crop-images.md)

[<span data-ttu-id="42328-132">Képfókuszpontok testreszabása</span><span class="sxs-lookup"><span data-stu-id="42328-132">Customize image focal points</span></span>](dam-custom-focal-point.md)

[<span data-ttu-id="42328-133">Statikus fájlok feltöltése és kiszolgálása</span><span class="sxs-lookup"><span data-stu-id="42328-133">Upload and serve static files</span></span>](upload-serve-static-files.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
