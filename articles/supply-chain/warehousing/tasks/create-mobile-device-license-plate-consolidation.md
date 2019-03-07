---
title: Menüelem létrehozása mobileszközhöz azonosítótábla-konszolidáláshoz
description: Ez az eljárás bemutatja, hogyan lehet létrehozni egy mobileszköz menüpontot az azonosítótábla-konszolidálási munkához.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bfe07426e9ff11c60c5f703b810ba09d6c863399
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "343650"
---
# <a name="create-a-mobile-device-menu-item-for-license-plate-consolidation"></a><span data-ttu-id="b7484-103">Menüelem létrehozása mobileszközhöz azonosítótábla-konszolidáláshoz</span><span class="sxs-lookup"><span data-stu-id="b7484-103">Create a mobile device menu item for license plate consolidation</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b7484-104">Ez az eljárás bemutatja, hogyan lehet létrehozni egy mobileszköz menüpontot az azonosítótábla-konszolidálási munkához.</span><span class="sxs-lookup"><span data-stu-id="b7484-104">This procedure shows you how to create a mobile device menu item for license plate consolidation work.</span></span> <span data-ttu-id="b7484-105">Ez lehetővé teszi, hogy a raktárosok konszolidálják az azonosítótáblán levő cikkeket egy másik azonosítótábla elemeivel ugyanazon a helyen belül.</span><span class="sxs-lookup"><span data-stu-id="b7484-105">This enables warehouse workers to consolidate items on one license plate with items on another license place within the same location.</span></span> <span data-ttu-id="b7484-106">Ezt például akkor használhatják, ha a következő előkészítési lépések azonosok mindkét munkamegrendelés esetében, és így a munkát csak egyszer kell elvégezni az egyesített cikkeken.</span><span class="sxs-lookup"><span data-stu-id="b7484-106">For example, they might use this if subsequent staging steps were the same on both work orders, so that the work only needs to be performed once for the merged items.</span></span> <span data-ttu-id="b7484-107">Az USMF bemutatócég adataiban használhatja ezt az eljárást.</span><span class="sxs-lookup"><span data-stu-id="b7484-107">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="b7484-108">A feladatot jellemzően egy raktári vezető végzi el.</span><span class="sxs-lookup"><span data-stu-id="b7484-108">The task would typically be carried out by a warehouse manager.</span></span> <span data-ttu-id="b7484-109">Ez az eljárás egy olyan funkcióra vonatkozik, amely a Dynamics 365 for Operations 1611-es verziójába került be.</span><span class="sxs-lookup"><span data-stu-id="b7484-109">This procedure is for a feature that was added in Dynamics 365 for Operations, version 1611.</span></span>

1. <span data-ttu-id="b7484-110">Ugrás a Raktárkezelés > Beállítás > Mobileszköz > Mobileszköz menü elemekre.</span><span class="sxs-lookup"><span data-stu-id="b7484-110">Go to Warehouse management > Setup > Mobile device > Mobile device menu items.</span></span>
2. <span data-ttu-id="b7484-111">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b7484-111">Click New.</span></span>
3. <span data-ttu-id="b7484-112">Írjon be egy értéket a Menüelem neve mezőbe.</span><span class="sxs-lookup"><span data-stu-id="b7484-112">In the Menu item name field, type a value.</span></span>
4. <span data-ttu-id="b7484-113">Érték beírása a Címmezőbe.</span><span class="sxs-lookup"><span data-stu-id="b7484-113">In the Title field, type a value.</span></span>
5. <span data-ttu-id="b7484-114">A Mód mezőben válassza ki a „Közvetett” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b7484-114">In the Mode field, select 'Indirect'.</span></span>
6. <span data-ttu-id="b7484-115">A Tevékenységkód mezőben válassza ki az „Azonosítótáblák egyesítése” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b7484-115">In the Activity code field, select 'Consolidate license plates'.</span></span>

