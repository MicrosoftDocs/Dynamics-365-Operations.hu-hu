---
title: Menüelem létrehozása mobileszközhöz azonosítótábla-konszolidáláshoz
description: Ez az eljárás bemutatja, hogyan lehet létrehozni egy mobileszköz menüpontot az azonosítótábla-konszolidálási munkához.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b3f5f572461de007f137ffa7ea05c535371f95b7
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977238"
---
# <a name="create-a-mobile-device-menu-item-for-license-plate-consolidation"></a><span data-ttu-id="25a43-103">Menüelem létrehozása mobileszközhöz azonosítótábla-konszolidáláshoz</span><span class="sxs-lookup"><span data-stu-id="25a43-103">Create a mobile device menu item for license plate consolidation</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="25a43-104">Ez az eljárás bemutatja, hogyan lehet létrehozni egy mobileszköz menüpontot az azonosítótábla-konszolidálási munkához.</span><span class="sxs-lookup"><span data-stu-id="25a43-104">This procedure shows you how to create a mobile device menu item for license plate consolidation work.</span></span> <span data-ttu-id="25a43-105">Ez lehetővé teszi, hogy a raktárosok konszolidálják az azonosítótáblán levő cikkeket egy másik azonosítótábla elemeivel ugyanazon a helyen belül.</span><span class="sxs-lookup"><span data-stu-id="25a43-105">This enables warehouse workers to consolidate items on one license plate with items on another license place within the same location.</span></span> <span data-ttu-id="25a43-106">Ezt például akkor használhatják, ha a következő előkészítési lépések azonosok mindkét munkamegrendelés esetében, és így a munkát csak egyszer kell elvégezni az egyesített cikkeken.</span><span class="sxs-lookup"><span data-stu-id="25a43-106">For example, they might use this if subsequent staging steps were the same on both work orders, so that the work only needs to be performed once for the merged items.</span></span> <span data-ttu-id="25a43-107">Az USMF bemutatócég adataiban használhatja ezt az eljárást.</span><span class="sxs-lookup"><span data-stu-id="25a43-107">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="25a43-108">A feladatot jellemzően egy raktári vezető végzi el.</span><span class="sxs-lookup"><span data-stu-id="25a43-108">The task would typically be carried out by a warehouse manager.</span></span> <span data-ttu-id="25a43-109">Ez az eljárás egy olyan funkcióra vonatkozik, amely a Dynamics 365 for Operations 1611-es verziójába került be.</span><span class="sxs-lookup"><span data-stu-id="25a43-109">This procedure is for a feature that was added in Dynamics 365 for Operations, version 1611.</span></span>

1. <span data-ttu-id="25a43-110">Ugrás a Raktárkezelés > Beállítás > Mobileszköz > Mobileszköz menü elemekre.</span><span class="sxs-lookup"><span data-stu-id="25a43-110">Go to Warehouse management > Setup > Mobile device > Mobile device menu items.</span></span>
2. <span data-ttu-id="25a43-111">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="25a43-111">Click New.</span></span>
3. <span data-ttu-id="25a43-112">Írjon be egy értéket a Menüelem neve mezőbe.</span><span class="sxs-lookup"><span data-stu-id="25a43-112">In the Menu item name field, type a value.</span></span>
4. <span data-ttu-id="25a43-113">Érték beírása a Címmezőbe.</span><span class="sxs-lookup"><span data-stu-id="25a43-113">In the Title field, type a value.</span></span>
5. <span data-ttu-id="25a43-114">A Mód mezőben válassza ki a „Közvetett” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="25a43-114">In the Mode field, select 'Indirect'.</span></span>
6. <span data-ttu-id="25a43-115">A Tevékenységkód mezőben válassza ki az „Azonosítótáblák egyesítése” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="25a43-115">In the Activity code field, select 'Consolidate license plates'.</span></span>

