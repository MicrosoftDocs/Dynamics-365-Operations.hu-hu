---
title: Kép fókuszpontok testreszabása
description: Ez a témakör azt mutatja be, hogyan szabhat testre képfókuszpontokat a Microsoft Dynamics 365 Commerce webhelykészítőben.
author: psimolin
manager: annbe
ms.date: 04/14/2020
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
ms.openlocfilehash: 9c8fc9a1f944d24aff3ab2923ca2715209a674e4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4972932"
---
# <a name="customize-image-focal-points"></a><span data-ttu-id="c3b58-103">Kép fókuszpontok testreszabása</span><span class="sxs-lookup"><span data-stu-id="c3b58-103">Customize image focal points</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c3b58-104">Ez a témakör azt mutatja be, hogyan szabhat testre képfókuszpontokat a Microsoft Dynamics 365 Commerce webhelykészítőben.</span><span class="sxs-lookup"><span data-stu-id="c3b58-104">This topic describes how to customize image focal points in Microsoft Dynamics 365 Commerce site builder.</span></span>

## <a name="overview"></a><span data-ttu-id="c3b58-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="c3b58-105">Overview</span></span>

<span data-ttu-id="c3b58-106">Amikor képet tölt fel a Commerce webhelykészítő médiatárba, a rendszer megpróbálja meghatározni a kép fókuszpontját.</span><span class="sxs-lookup"><span data-stu-id="c3b58-106">When an image is uploaded to the Commerce site builder Media Library, the system attempts to determine the focal point of the image.</span></span> <span data-ttu-id="c3b58-107">Ha például a képen van egy személy, a rendszer alapértelmezés szerint beállítja a fókuszpontot a személy arcára.</span><span class="sxs-lookup"><span data-stu-id="c3b58-107">For example, if the image has a person on it, the system will set the focal point to the face of the person by default.</span></span> <span data-ttu-id="c3b58-108">A legtöbb esetben az automatikusan beállítható a fókuszpont minden nézetablaknál jól működik, de előfordulhat, hogy a fókuszpontot is módosítani szeretné annak érdekében, hogy a kép egy bizonyos része mindig látható legyen.</span><span class="sxs-lookup"><span data-stu-id="c3b58-108">In most cases the automatically set focal point works well for all viewports, but sometimes you may want to adjust the focal point to ensure that a specific part of the image is always visible.</span></span>

### <a name="define-a-custom-focal-point-for-an-image"></a><span data-ttu-id="c3b58-109">Egyéni fókuszpont definiálása a képhez</span><span class="sxs-lookup"><span data-stu-id="c3b58-109">Define a custom focal point for an image</span></span>

<span data-ttu-id="c3b58-110">Ha egyéni fókuszpontot szeretne definiálni egy képhez, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="c3b58-110">To define a custom focal point for an image, follow these steps.</span></span>

1. <span data-ttu-id="c3b58-111">A Commerce webhelykészítő bal oldali navigációs paneljében válassza a **Médiatárat**.</span><span class="sxs-lookup"><span data-stu-id="c3b58-111">In the left navigation pane of Commerce site builder, select **Media Library**.</span></span>
1. <span data-ttu-id="c3b58-112">A fő ablakban válassza ki a módosítani kívánt képet.</span><span class="sxs-lookup"><span data-stu-id="c3b58-112">In the main window, select the image you want to modify.</span></span>
1. <span data-ttu-id="c3b58-113">Válassza a parancssáv **Szerkesztés** elemét.</span><span class="sxs-lookup"><span data-stu-id="c3b58-113">On the command bar, select **Edit**.</span></span>
1. <span data-ttu-id="c3b58-114">Válassza ki a képet a **Szerkesztési mód** megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="c3b58-114">Select the image to enter **Edit Mode**.</span></span>
1. <span data-ttu-id="c3b58-115">A **szerkesztési mód** területen válassza a **fókuszpont módosítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c3b58-115">Under **Edit Mode**, select **Change Focal Point**.</span></span> <span data-ttu-id="c3b58-116">A kép fölött egy körkörös fókuszpont-vezérlőelem jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="c3b58-116">A circular focal point control appears over the image.</span></span>
1. <span data-ttu-id="c3b58-117">A fókuszpont-vezérlőelem kiválasztása a kívánt fókuszpont fölé történő áthelyezéshez.</span><span class="sxs-lookup"><span data-stu-id="c3b58-117">Select the focal point control to move it over the desired focal point.</span></span>
1. <span data-ttu-id="c3b58-118">Ha végzett, kattintson a parancssáv **Mentés** gombjára, majd válassza a **Szerkesztés befejezését**.</span><span class="sxs-lookup"><span data-stu-id="c3b58-118">When you're done, on the command bar select **Save**, and then select **Finish editing**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c3b58-119">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="c3b58-119">Additional resources</span></span>

[<span data-ttu-id="c3b58-120">Digitális eszközkezelés – áttekintés</span><span class="sxs-lookup"><span data-stu-id="c3b58-120">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="c3b58-121">Képek feltöltése</span><span class="sxs-lookup"><span data-stu-id="c3b58-121">Upload images</span></span>](dam-upload-images.md)

[<span data-ttu-id="c3b58-122">Videó feltöltése</span><span class="sxs-lookup"><span data-stu-id="c3b58-122">Upload video</span></span>](dam-upload-video.md)

[<span data-ttu-id="c3b58-123">Fájlok feltöltése</span><span class="sxs-lookup"><span data-stu-id="c3b58-123">Upload files</span></span>](dam-upload-files.md)

[<span data-ttu-id="c3b58-124">Képek körülvágása</span><span class="sxs-lookup"><span data-stu-id="c3b58-124">Crop images</span></span>](dam-crop-images.md)

[<span data-ttu-id="c3b58-125">Statikus fájlok feltöltése és kiszolgálása</span><span class="sxs-lookup"><span data-stu-id="c3b58-125">Upload and serve static files</span></span>](upload-serve-static-files.md)
