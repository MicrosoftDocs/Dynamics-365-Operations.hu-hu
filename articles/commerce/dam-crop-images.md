---
title: Képek körülvágása
description: Ez a témakör azt mutatja be, hogyan vághat körül képeket a Microsoft Dynamics 365 Commerce webhelykészítőben.
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
ms.openlocfilehash: 2cf8d43062ec527755fdf1a28f0ea3ceac1fbc15
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5003828"
---
# <a name="crop-images"></a><span data-ttu-id="0210d-103">Képek körülvágása</span><span class="sxs-lookup"><span data-stu-id="0210d-103">Crop images</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="0210d-104">Ez a témakör azt mutatja be, hogyan vághat körül képeket a Microsoft Dynamics 365 Commerce webhelykészítőben.</span><span class="sxs-lookup"><span data-stu-id="0210d-104">This topic describes how to crop images in Microsoft Dynamics 365 Commerce site builder.</span></span>

## <a name="overview"></a><span data-ttu-id="0210d-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="0210d-105">Overview</span></span>

<span data-ttu-id="0210d-106">A Commerce webhelykészítő médiatára segítségével képeket vághat körül, hogy optimalizálja őket különböző modultípusokhoz és nézetportokhoz.</span><span class="sxs-lookup"><span data-stu-id="0210d-106">The Commerce site builder Media Library allows you to crop images to optimize them for different module types and viewports.</span></span>

## <a name="crop-an-image"></a><span data-ttu-id="0210d-107">Kép körülvágása</span><span class="sxs-lookup"><span data-stu-id="0210d-107">Crop an image</span></span>

<span data-ttu-id="0210d-108">Ha képet szeretne körülvágni a webhelykészítőben, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="0210d-108">To crop an image in site builder, follow these steps.</span></span>

1. <span data-ttu-id="0210d-109">A Commerce webhelykészítő bal oldali navigációs paneljében válassza a **Médiatárat**.</span><span class="sxs-lookup"><span data-stu-id="0210d-109">In the left navigation pane of Commerce site builder, select **Media Library**.</span></span>
1. <span data-ttu-id="0210d-110">A fő ablakban válassza ki a módosítani kívánt képet.</span><span class="sxs-lookup"><span data-stu-id="0210d-110">In the main window, select the image you want to modify.</span></span>
1. <span data-ttu-id="0210d-111">Válassza a parancssáv **Szerkesztés** elemét.</span><span class="sxs-lookup"><span data-stu-id="0210d-111">On the command bar, select **Edit**.</span></span>
1. <span data-ttu-id="0210d-112">Válassza ki a képet a **Szerkesztési mód** megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="0210d-112">Select the image to enter **Edit Mode**.</span></span>
1. <span data-ttu-id="0210d-113">A **Szerkesztési mód** területen válassza a **Nézet szerkesztése modul alapján** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0210d-113">Under **Edit Mode**, select **Edit View by Module**.</span></span>
1. <span data-ttu-id="0210d-114">A **modul** legördülő menüjében válassza ki a modul típusát.</span><span class="sxs-lookup"><span data-stu-id="0210d-114">From the **Module** drop-down menu, select the module type.</span></span>
1. <span data-ttu-id="0210d-115">A **nézettípus** legördülő menüjében válassza ki a nézet típusát.</span><span class="sxs-lookup"><span data-stu-id="0210d-115">From the **View type** drop-down menu, select the view type.</span></span>
1. <span data-ttu-id="0210d-116">Az **Elhelyezés** legördülő menüben válassza ki a kép elhelyezését.</span><span class="sxs-lookup"><span data-stu-id="0210d-116">From the **Placement** drop-down menu, select the image placement.</span></span>
1. <span data-ttu-id="0210d-117">A **nézettípus** legördülő menüjében válassza ki a nézetport méretét.</span><span class="sxs-lookup"><span data-stu-id="0210d-117">From the **Viewport** drop-down menu, select the viewport size.</span></span>
1. <span data-ttu-id="0210d-118">A kép átfedésben van a körülvágási területet képviselő területtel.</span><span class="sxs-lookup"><span data-stu-id="0210d-118">The image is overlaid with the area representing the crop region.</span></span> <span data-ttu-id="0210d-119">Szükség szerint helyezze át és méretezze át a körülvágási területet.</span><span class="sxs-lookup"><span data-stu-id="0210d-119">Move and resize the crop region as needed.</span></span> <span data-ttu-id="0210d-120">A méretarány karbantartása automatikusan történik.</span><span class="sxs-lookup"><span data-stu-id="0210d-120">The aspect ratio will be maintained automatically.</span></span>
1. <span data-ttu-id="0210d-121">Ha végzett, kattintson a parancssáv **Mentés** gombjára, majd válassza a **Szerkesztés befejezését**.</span><span class="sxs-lookup"><span data-stu-id="0210d-121">When you're done, on the command bar, select **Save**, and then select **Finish editing**.</span></span> 

<span data-ttu-id="0210d-122">Az egyéni körülvágás befejezése után a képmódosítások szinte azonnal érvénybe lépnek.</span><span class="sxs-lookup"><span data-stu-id="0210d-122">After custom cropping is completed, image modifications will take effect almost immediately.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0210d-123">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="0210d-123">Additional resources</span></span>

[<span data-ttu-id="0210d-124">Digitális eszközkezelés – áttekintés</span><span class="sxs-lookup"><span data-stu-id="0210d-124">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="0210d-125">Képek feltöltése</span><span class="sxs-lookup"><span data-stu-id="0210d-125">Upload images</span></span>](dam-upload-images.md)

[<span data-ttu-id="0210d-126">Videó feltöltése</span><span class="sxs-lookup"><span data-stu-id="0210d-126">Upload video</span></span>](dam-upload-video.md)

[<span data-ttu-id="0210d-127">Fájlok feltöltése</span><span class="sxs-lookup"><span data-stu-id="0210d-127">Upload files</span></span>](dam-upload-files.md)

[<span data-ttu-id="0210d-128">Képfókuszpontok testreszabása</span><span class="sxs-lookup"><span data-stu-id="0210d-128">Customize image focal points</span></span>](dam-custom-focal-point.md)

[<span data-ttu-id="0210d-129">Statikus fájlok feltöltése és kiszolgálása</span><span class="sxs-lookup"><span data-stu-id="0210d-129">Upload and serve static files</span></span>](upload-serve-static-files.md)
