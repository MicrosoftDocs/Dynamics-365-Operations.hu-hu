---
title: Képek körülvágása
description: Ez a témakör azt mutatja be, hogyan vághat körül képeket a Microsoft Dynamics 365 Commerce webhelykészítőben.
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
ms.openlocfilehash: 771f98ef11355ad30ededcb310e9794ce792b7f0
ms.sourcegitcommit: 567132f4e4f7a1d76dccf762068209a42c788b52
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/03/2020
ms.locfileid: "3097022"
---
# <a name="crop-images"></a><span data-ttu-id="312a6-103">Képek körülvágása</span><span class="sxs-lookup"><span data-stu-id="312a6-103">Crop images</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="312a6-104">Ez a témakör azt mutatja be, hogyan vághat körül képeket a Microsoft Dynamics 365 Commerce webhelykészítőben.</span><span class="sxs-lookup"><span data-stu-id="312a6-104">This topic describes how to crop images in Microsoft Dynamics 365 Commerce site builder.</span></span>

## <a name="overview"></a><span data-ttu-id="312a6-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="312a6-105">Overview</span></span>

<span data-ttu-id="312a6-106">A Commerce webhelykészítő médiatára segítségével képeket vághat körül, hogy optimalizálja őket különböző modultípusokhoz és nézetportokhoz.</span><span class="sxs-lookup"><span data-stu-id="312a6-106">The Commerce site builder Media Library allows you to crop images to optimize them for different module types and viewports.</span></span>

## <a name="crop-an-image"></a><span data-ttu-id="312a6-107">Kép körülvágása</span><span class="sxs-lookup"><span data-stu-id="312a6-107">Crop an image</span></span>

<span data-ttu-id="312a6-108">Ha képet szeretne körülvágni a webhelykészítőben, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="312a6-108">To crop an image in site builder, follow these steps.</span></span>

1. <span data-ttu-id="312a6-109">A Commerce webhelykészítő bal oldali navigációs paneljében válassza a **Médiatárat**.</span><span class="sxs-lookup"><span data-stu-id="312a6-109">In the left navigation pane of Commerce site builder, select **Media Library**.</span></span>
1. <span data-ttu-id="312a6-110">A fő ablakban válassza ki a módosítani kívánt képet.</span><span class="sxs-lookup"><span data-stu-id="312a6-110">In the main window, select the image you want to modify.</span></span>
1. <span data-ttu-id="312a6-111">A parancssorban válassza a **Szerkesztés** parancsot a fájl kivételéhez.</span><span class="sxs-lookup"><span data-stu-id="312a6-111">On the command bar, select **Edit** to check out the file.</span></span>
1. <span data-ttu-id="312a6-112">Válassza ki a képet a **Szerkesztési mód** megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="312a6-112">Select the image to enter **Edit Mode**.</span></span>
1. <span data-ttu-id="312a6-113">A **Szerkesztési mód** területen válassza a **Nézet szerkesztése modul alapján** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="312a6-113">Under **Edit Mode**, select **Edit View by Module**.</span></span>
1. <span data-ttu-id="312a6-114">A **modul** legördülő menüjében válassza ki a modul típusát.</span><span class="sxs-lookup"><span data-stu-id="312a6-114">From the **Module** drop-down menu, select the module type.</span></span>
1. <span data-ttu-id="312a6-115">A **nézettípus** legördülő menüjében válassza ki a nézet típusát.</span><span class="sxs-lookup"><span data-stu-id="312a6-115">From the **View type** drop-down menu, select the view type.</span></span>
1. <span data-ttu-id="312a6-116">Az **Elhelyezés** legördülő menüben válassza ki a kép elhelyezését.</span><span class="sxs-lookup"><span data-stu-id="312a6-116">From the **Placement** drop-down menu, select the image placement.</span></span>
1. <span data-ttu-id="312a6-117">A **nézettípus** legördülő menüjében válassza ki a nézetport méretét.</span><span class="sxs-lookup"><span data-stu-id="312a6-117">From the **Viewport** drop-down menu, select the viewport size.</span></span>
1. <span data-ttu-id="312a6-118">A kép átfedésben van a körülvágási területet képviselő területtel.</span><span class="sxs-lookup"><span data-stu-id="312a6-118">The image is overlaid with the area representing the crop region.</span></span> <span data-ttu-id="312a6-119">Szükség szerint helyezze át és méretezze át a körülvágási területet.</span><span class="sxs-lookup"><span data-stu-id="312a6-119">Move and resize the crop region as needed.</span></span> <span data-ttu-id="312a6-120">A méretarány karbantartása automatikusan történik.</span><span class="sxs-lookup"><span data-stu-id="312a6-120">The aspect ratio will be maintained automatically.</span></span>
1. <span data-ttu-id="312a6-121">Ha végzett, kattintson a parancssáv **Mentés** gombjára, majd válassza a **Szerkesztés befejezését**.</span><span class="sxs-lookup"><span data-stu-id="312a6-121">When you're done, on the command bar, select **Save**, and then select **Finish editing**.</span></span> 

<span data-ttu-id="312a6-122">Az egyéni körülvágás befejezése után a képmódosítások szinte azonnal érvénybe lépnek.</span><span class="sxs-lookup"><span data-stu-id="312a6-122">After custom cropping is completed, image modifications will take effect almost immediately.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="312a6-123">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="312a6-123">Additional resources</span></span>

[<span data-ttu-id="312a6-124">Digitális eszközkezelés – áttekintés</span><span class="sxs-lookup"><span data-stu-id="312a6-124">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="312a6-125">Képek feltöltése</span><span class="sxs-lookup"><span data-stu-id="312a6-125">Upload images</span></span>](dam-upload-images.md)

[<span data-ttu-id="312a6-126">Videó feltöltése</span><span class="sxs-lookup"><span data-stu-id="312a6-126">Upload video</span></span>](dam-upload-video.md)

[<span data-ttu-id="312a6-127">Fájlok feltöltése</span><span class="sxs-lookup"><span data-stu-id="312a6-127">Upload files</span></span>](dam-upload-files.md)

[<span data-ttu-id="312a6-128">Kép fókuszpontok testreszabása</span><span class="sxs-lookup"><span data-stu-id="312a6-128">Customize image focal points</span></span>](dam-custom-focal-point.md)
