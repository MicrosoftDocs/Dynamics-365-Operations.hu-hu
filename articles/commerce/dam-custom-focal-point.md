---
title: Kép fókuszpontok testreszabása
description: Ez a témakör azt mutatja be, hogyan szabhat testre képfókuszpontokat a Microsoft Dynamics 365 Commerce webhelykészítőben.
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
ms.openlocfilehash: 2c9bbd51f1fe9a19198a455eedd3ba744d54a165
ms.sourcegitcommit: 567132f4e4f7a1d76dccf762068209a42c788b52
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/03/2020
ms.locfileid: "3097023"
---
# <a name="customize-image-focal-points"></a><span data-ttu-id="174b0-103">Kép fókuszpontok testreszabása</span><span class="sxs-lookup"><span data-stu-id="174b0-103">Customize image focal points</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="174b0-104">Ez a témakör azt mutatja be, hogyan szabhat testre képfókuszpontokat a Microsoft Dynamics 365 Commerce webhelykészítőben.</span><span class="sxs-lookup"><span data-stu-id="174b0-104">This topic describes how to customize image focal points in Microsoft Dynamics 365 Commerce site builder.</span></span>

## <a name="overview"></a><span data-ttu-id="174b0-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="174b0-105">Overview</span></span>

<span data-ttu-id="174b0-106">Amikor képet tölt fel a Commerce webhelykészítő médiatárba, a rendszer megpróbálja meghatározni a kép fókuszpontját.</span><span class="sxs-lookup"><span data-stu-id="174b0-106">When an image is uploaded to the Commerce site builder Media Library, the system attempts to determine the focal point of the image.</span></span> <span data-ttu-id="174b0-107">Ha például a képen van egy személy, a rendszer alapértelmezés szerint beállítja a fókuszpontot a személy arcára.</span><span class="sxs-lookup"><span data-stu-id="174b0-107">For example, if the image has a person on it, the system will set the focal point to the face of the person by default.</span></span> <span data-ttu-id="174b0-108">A legtöbb esetben az automatikusan beállítható a fókuszpont minden nézetablaknál jól működik, de előfordulhat, hogy a fókuszpontot is módosítani szeretné annak érdekében, hogy a kép egy bizonyos része mindig látható legyen.</span><span class="sxs-lookup"><span data-stu-id="174b0-108">In most cases the automatically set focal point works well for all viewports, but sometimes you may want to adjust the focal point to ensure that a specific part of the image is always visible.</span></span>

### <a name="define-a-custom-focal-point-for-an-image"></a><span data-ttu-id="174b0-109">Egyéni fókuszpont definiálása a képhez</span><span class="sxs-lookup"><span data-stu-id="174b0-109">Define a custom focal point for an image</span></span>

<span data-ttu-id="174b0-110">Ha egyéni fókuszpontot szeretne definiálni egy képhez, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="174b0-110">To define a custom focal point for an image, follow these steps.</span></span>

1. <span data-ttu-id="174b0-111">A Commerce webhelykészítő bal oldali navigációs paneljében válassza a **Médiatárat**.</span><span class="sxs-lookup"><span data-stu-id="174b0-111">In the left navigation pane of Commerce site builder, select **Media Library**.</span></span>
1. <span data-ttu-id="174b0-112">A fő ablakban válassza ki a módosítani kívánt képet.</span><span class="sxs-lookup"><span data-stu-id="174b0-112">In the main window, select the image you want to modify.</span></span>
1. <span data-ttu-id="174b0-113">A parancssorban válassza a **Szerkesztés** parancsot a fájl kivételéhez.</span><span class="sxs-lookup"><span data-stu-id="174b0-113">On the command bar, select **Edit** to check out the file.</span></span>
1. <span data-ttu-id="174b0-114">Válassza ki a képet a **Szerkesztési mód** megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="174b0-114">Select the image to enter **Edit Mode**.</span></span>
1. <span data-ttu-id="174b0-115">A **szerkesztési mód** területen válassza a **fókuszpont módosítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="174b0-115">Under **Edit Mode**, select **Change Focal Point**.</span></span> <span data-ttu-id="174b0-116">A kép fölött egy körkörös fókuszpont-vezérlőelem jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="174b0-116">A circular focal point control appears over the image.</span></span>
1. <span data-ttu-id="174b0-117">A fókuszpont-vezérlőelem kiválasztása a kívánt fókuszpont fölé történő áthelyezéshez.</span><span class="sxs-lookup"><span data-stu-id="174b0-117">Select the focal point control to move it over the desired focal point.</span></span>
1. <span data-ttu-id="174b0-118">Ha végzett, kattintson a parancssáv **Mentés** gombjára, majd válassza a **Szerkesztés befejezését**.</span><span class="sxs-lookup"><span data-stu-id="174b0-118">When you're done, on the command bar select **Save**, and then select **Finish editing**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="174b0-119">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="174b0-119">Additional resources</span></span>

[<span data-ttu-id="174b0-120">Digitális eszközkezelés – áttekintés</span><span class="sxs-lookup"><span data-stu-id="174b0-120">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="174b0-121">Képek feltöltése</span><span class="sxs-lookup"><span data-stu-id="174b0-121">Upload images</span></span>](dam-upload-images.md)

[<span data-ttu-id="174b0-122">Videó feltöltése</span><span class="sxs-lookup"><span data-stu-id="174b0-122">Upload video</span></span>](dam-upload-video.md)

[<span data-ttu-id="174b0-123">Fájlok feltöltése</span><span class="sxs-lookup"><span data-stu-id="174b0-123">Upload files</span></span>](dam-upload-files.md)

[<span data-ttu-id="174b0-124">Képek körülvágása</span><span class="sxs-lookup"><span data-stu-id="174b0-124">Crop images</span></span>](dam-crop-images.md)
