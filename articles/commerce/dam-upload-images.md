---
title: Képek feltöltése
description: Ez a témakör azt mutatja be, hogyan tölthet fel képeket a Microsoft Dynamics 365 Commerce webhelykészítőben.
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
ms.openlocfilehash: 2a0a2fdb275cbeb65c06c01128e90ba660f98c9b
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799229"
---
# <a name="upload-images"></a><span data-ttu-id="a0fb7-103">Képek feltöltése</span><span class="sxs-lookup"><span data-stu-id="a0fb7-103">Upload images</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a0fb7-104">Ez a témakör azt mutatja be, hogyan tölthet fel képeket a Microsoft Dynamics 365 Commerce webhelykészítőben.</span><span class="sxs-lookup"><span data-stu-id="a0fb7-104">This topic describes how to upload images in Microsoft Dynamics 365 Commerce site builder.</span></span>

<span data-ttu-id="a0fb7-105">A Commerce webhelykészítő médiatára segítségével képeket tölthet fel, egyesével vagy tömegesen mappákkal.</span><span class="sxs-lookup"><span data-stu-id="a0fb7-105">The Commerce site builder Media Library allows you to upload images, either singly or in bulk using folders.</span></span> <span data-ttu-id="a0fb7-106">Mindig a legnagyobb felbontással és minőséggel töltse fel a képet, mert a képátméretező összetevő automatikusan optimalizálja a képet különböző nézetablakok és töréspontok számára.</span><span class="sxs-lookup"><span data-stu-id="a0fb7-106">You should always upload the version of the image with highest resolution and quality, because the image resizer component will automatically optimize the image for different viewports and their breakpoints.</span></span>

### <a name="image-information-specified-during-upload"></a><span data-ttu-id="a0fb7-107">A feltöltéskor megadott képinformáció</span><span class="sxs-lookup"><span data-stu-id="a0fb7-107">Image information specified during upload</span></span>

<span data-ttu-id="a0fb7-108">Kép feltöltésekor meg lehet adni a következő adatokat.</span><span class="sxs-lookup"><span data-stu-id="a0fb7-108">When uploading an image, the following information can be specified.</span></span>

- <span data-ttu-id="a0fb7-109">**Cím, helyettesítő szöveg, leírás, kulcsszavak**: a kép vagy a képek metaadatai.</span><span class="sxs-lookup"><span data-stu-id="a0fb7-109">**Title, Alt Text, Description, Keywords**: Metadata of the image or images.</span></span> <span data-ttu-id="a0fb7-110">A cím és a helyettesítő szöveg kötelező értékek.</span><span class="sxs-lookup"><span data-stu-id="a0fb7-110">Title and alt text are required values.</span></span>
- <span data-ttu-id="a0fb7-111">**Kategóriaválasztás**:</span><span class="sxs-lookup"><span data-stu-id="a0fb7-111">**Select category**:</span></span>
    - <span data-ttu-id="a0fb7-112">**Nincs**: az e-kereskedelmi leírás képéhez vagy képekhez használatos.</span><span class="sxs-lookup"><span data-stu-id="a0fb7-112">**None**: Used for an e-Commerce storytelling image or images.</span></span>
    - <span data-ttu-id="a0fb7-113">**Termék, kategória, vevő, alkalmazott, katalógus**: Dynamics 365 Commerce omnicsatornás képhez vagy képekhez használatos.</span><span class="sxs-lookup"><span data-stu-id="a0fb7-113">**Product, Category, Customer, Employee, Catalog**: Used for Dynamics 365 Commerce omni-channel image or images.</span></span>
- <span data-ttu-id="a0fb7-114">**Eszközök közzététele feltöltés után**: Ha ez a jelölőnégyzet be van jelölve, akkor a képet vagy a képeket a feltöltés után azonnal közzéteszi a program.</span><span class="sxs-lookup"><span data-stu-id="a0fb7-114">**Publish assets after upload**: When this check box is selected, the image or images are published immediately after upload.</span></span>

> [!NOTE]
> <span data-ttu-id="a0fb7-115">A kiválasztott kategóriába tartozó képeszközöket is automatikusan címkézik a kategóriával, hogy egy adott kategóriába tartozó eszközök keresésekor támogassa a keresést.</span><span class="sxs-lookup"><span data-stu-id="a0fb7-115">Image assets with a category assigned are also automatically tagged with the category as a keyword to aid searching for assets of a specific category.</span></span>

### <a name="naming-conventions-for-omni-channel-images"></a><span data-ttu-id="a0fb7-116">Az omnicsatornás képek elnevezési konvenciói</span><span class="sxs-lookup"><span data-stu-id="a0fb7-116">Naming conventions for omni-channel images</span></span> 

<span data-ttu-id="a0fb7-117">Ha a médiatárat állította be az omnicsatornás képek háttereként, akkor képkategóriákkal jelezheti, melyik kategóriához tartozik a feltöltött kép.</span><span class="sxs-lookup"><span data-stu-id="a0fb7-117">If you have configured the Media Library as the omni-channel image backend, you can use image categories to indicate which category the uploaded image belongs to.</span></span> <span data-ttu-id="a0fb7-118">A követendő elnevezési szabállyal biztosítható, hogy a képeket más csatornák megfelelően kérik le, pl. pénztár (POS).</span><span class="sxs-lookup"><span data-stu-id="a0fb7-118">There is also a naming convention that should be followed to ensure that images are retrieved correctly by other channels, such as point of sale (POS).</span></span>

<span data-ttu-id="a0fb7-119">Az alapértelmezett elnevezési konvenció a kategória alapján változik:</span><span class="sxs-lookup"><span data-stu-id="a0fb7-119">The default naming convention varies based on the category:</span></span>
- <span data-ttu-id="a0fb7-120">Katalóguskép: "**/Catalogs/\{LanguageId\}/\{CatalogName\}.jpg**"</span><span class="sxs-lookup"><span data-stu-id="a0fb7-120">Catalog images should be named "**/Catalogs/\{LanguageId\}/\{CatalogName\}.jpg**"</span></span>
- <span data-ttu-id="a0fb7-121">Kategóriaképek: "**/Categories/\{CategoryName\}.png**"</span><span class="sxs-lookup"><span data-stu-id="a0fb7-121">Category images should be named "**/Categories/\{CategoryName\}.png**"</span></span>
- <span data-ttu-id="a0fb7-122">Vevői képek: "**/Customers/\{CustomerNumber\}.jpg**"</span><span class="sxs-lookup"><span data-stu-id="a0fb7-122">Customer images should be named "**/Customers/\{CustomerNumber\}.jpg**"</span></span>
- <span data-ttu-id="a0fb7-123">Alkalmazotti képek: "**/Workers/\{WorkerNumber\}.jpg**"</span><span class="sxs-lookup"><span data-stu-id="a0fb7-123">Employee images should be named "**/Workers/\{WorkerNumber\}.jpg**"</span></span>
- <span data-ttu-id="a0fb7-124">Termékképek: "**/Products/\{ProductNumber\}_000_001.png**"</span><span class="sxs-lookup"><span data-stu-id="a0fb7-124">Product images should be named "**/Products/\{ProductNumber\}_000_001.png**"</span></span>
    - <span data-ttu-id="a0fb7-125">A 001 a kép sorszáma, amely lehet 001, 002, 003, 004 vagy 005</span><span class="sxs-lookup"><span data-stu-id="a0fb7-125">001 is the sequence of the image and it can be 001, 002, 003, 004 or 005</span></span>
- <span data-ttu-id="a0fb7-126">Termékváltozat-képek: „**/Products/\{ProductNumber\} \^ \{Style\} \^ \{Size\} \^ \{Color\} \^\_000_001.png**”</span><span class="sxs-lookup"><span data-stu-id="a0fb7-126">Product variant images should be named "**/Products/\{ProductNumber\} \^ \{Style\} \^ \{Size\} \^ \{Color\} \^\_000_001.png**"</span></span>
    - <span data-ttu-id="a0fb7-127">Például: 93039 \^ \^ 2 \^ Fekete \^_000_001.png</span><span class="sxs-lookup"><span data-stu-id="a0fb7-127">For example: 93039 \^ \^ 2 \^ Black \^_000_001.png</span></span>

## <a name="upload-an-image"></a><span data-ttu-id="a0fb7-128">Kép feltöltése</span><span class="sxs-lookup"><span data-stu-id="a0fb7-128">Upload an image</span></span>

<span data-ttu-id="a0fb7-129">Ha képet szeretne feltölteni a webhelykészítőbe, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="a0fb7-129">To upload an image in site builder, follow these steps.</span></span>

1. <span data-ttu-id="a0fb7-130">A bal oldali navigációs ablakban válassza ki a **Médiatár** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a0fb7-130">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="a0fb7-131">A parancssávon válassza a **Feltöltés \> Médiaelemek feltöltése**.</span><span class="sxs-lookup"><span data-stu-id="a0fb7-131">On the command bar, select **Upload \> Upload Media Items**.</span></span>
1. <span data-ttu-id="a0fb7-132">A fájlkezelő ablakban navigáljon a lapra, és válasszon ki egy vagy több képfájlt, majd válassza a **Megnyitás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a0fb7-132">In the File Explorer window, navigate to and select one or more image files to upload, and then select **Open**.</span></span>
1. <span data-ttu-id="a0fb7-133">A **médiaelem feltöltése** párbeszédpanelen írja be a szükséges címet és a helyettesítő szöveget.</span><span class="sxs-lookup"><span data-stu-id="a0fb7-133">In the **Upload Media Item** dialog box, enter the required title and alt text.</span></span>
1. <span data-ttu-id="a0fb7-134">Írja be a választható leírást és kulcsszavakat, és ha szükséges, válasszon ki egy kategóriát.</span><span class="sxs-lookup"><span data-stu-id="a0fb7-134">Enter optional description and keywords and select a category if desired.</span></span> 
1. <span data-ttu-id="a0fb7-135">Ha azonnal közzétenné a képeket a feltöltés után, jelölje be a **Médiatartalom közzététele a feltöltés után** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="a0fb7-135">If you want to publish the image(s) immediately after upload, select the **Publish media items after upload** check box.</span></span>
1. <span data-ttu-id="a0fb7-136">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a0fb7-136">Select **OK**.</span></span>

## <a name="upload-a-folder-of-images"></a><span data-ttu-id="a0fb7-137">Képek mappa feltöltése</span><span class="sxs-lookup"><span data-stu-id="a0fb7-137">Upload a folder of images</span></span>

<span data-ttu-id="a0fb7-138">Ha tömegesen szeretne feltölteni egy képmappát a webhelykészítőbe, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="a0fb7-138">To bulk upload a folder of images in site builder, follow these steps.</span></span>

1. <span data-ttu-id="a0fb7-139">A bal oldali navigációs ablakban válassza ki a **Médiatár** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a0fb7-139">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="a0fb7-140">A parancssávon válassza a **Feltöltés \> Mappa feltöltése**.</span><span class="sxs-lookup"><span data-stu-id="a0fb7-140">On the command bar, select **Upload \> Upload Folder**.</span></span>
1. <span data-ttu-id="a0fb7-141">A fájlkezelő ablakban navigáljon a feltöltendő mappára, és válasszon ki, majd válassza a **Megnyitás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a0fb7-141">In the File Explorer window, navigate to and select a folder to upload, and then select **Open**.</span></span>
1. <span data-ttu-id="a0fb7-142">A **médiatartalom feltöltése** párbeszédpanelen írja be a választható kulcsszavakat, és ha szükséges, válasszon ki egy kategóriát.</span><span class="sxs-lookup"><span data-stu-id="a0fb7-142">In the **Upload Media Items** dialog box, enter optional keywords and select a category if desired.</span></span> 
1. <span data-ttu-id="a0fb7-143">Ha azonnal közzétenné a mappaképeket a feltöltés után, jelölje be a **Médiatartalom közzététele a feltöltés után** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="a0fb7-143">If you want to publish the images in the folder immediately after upload, select the **Publish media items after upload** check box.</span></span>
1. <span data-ttu-id="a0fb7-144">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a0fb7-144">Select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a0fb7-145">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="a0fb7-145">Additional resources</span></span>

[<span data-ttu-id="a0fb7-146">Digitális eszközkezelés – áttekintés</span><span class="sxs-lookup"><span data-stu-id="a0fb7-146">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="a0fb7-147">Videó feltöltése</span><span class="sxs-lookup"><span data-stu-id="a0fb7-147">Upload video</span></span>](dam-upload-video.md)

[<span data-ttu-id="a0fb7-148">Fájlok feltöltése</span><span class="sxs-lookup"><span data-stu-id="a0fb7-148">Upload files</span></span>](dam-upload-files.md)

[<span data-ttu-id="a0fb7-149">Képek körülvágása</span><span class="sxs-lookup"><span data-stu-id="a0fb7-149">Crop images</span></span>](dam-crop-images.md)

[<span data-ttu-id="a0fb7-150">Képfókuszpontok testreszabása</span><span class="sxs-lookup"><span data-stu-id="a0fb7-150">Customize image focal points</span></span>](dam-custom-focal-point.md)

[<span data-ttu-id="a0fb7-151">Statikus fájlok feltöltése és kiszolgálása</span><span class="sxs-lookup"><span data-stu-id="a0fb7-151">Upload and serve static files</span></span>](upload-serve-static-files.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
