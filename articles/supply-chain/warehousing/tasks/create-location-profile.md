---
title: Helyprofil létrehozása
description: Ez a témakör bemutatja, hogyan lehet helyprofilokat létrehozni a Dynamics 365 for Finance and Operations megoldásban.
author: ShylaThompson
manager: AnnBe
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationProfile
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 46aa1001c21ae39c158062444303ca02c0f41a45
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/08/2019
ms.locfileid: "1866979"
---
# <a name="create-a-location-profile"></a><span data-ttu-id="4872e-103">Helyprofil létrehozása</span><span class="sxs-lookup"><span data-stu-id="4872e-103">Create a location profile</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4872e-104">Ez a témakör bemutatja, hogyan lehet helyprofilokat létrehozni a Dynamics 365 for Finance and Operations megoldásban.</span><span class="sxs-lookup"><span data-stu-id="4872e-104">This topic explains how to create a location profile in Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="4872e-105">A raktárban minden helyhez társítani kell egy helyprofilt, amely leírja a hely tulajdonságait, például azt, hogy a hely engedélyezi-e a vegyes cikkeket.</span><span class="sxs-lookup"><span data-stu-id="4872e-105">Every location in the warehouse needs to have a location profile associated with it that describes the properties of the location, for example, whether the location allows mixed items.</span></span> <span data-ttu-id="4872e-106">Ebben az eljárásban olyan helyprofilt hozunk létre, amely nem igényel azonosítótáblás szabályozást.</span><span class="sxs-lookup"><span data-stu-id="4872e-106">In this procedure we’ll create a profile for a location that doesn’t require license plate control.</span></span> <span data-ttu-id="4872e-107">Engedélyezzük a vegyes cikkeket és a kevert készlet állapotokat, és engedélyezzük a ciklus leltározást.</span><span class="sxs-lookup"><span data-stu-id="4872e-107">We’ll enable mixed items, and mixed inventory statuses, and allow cycle counting.</span></span> <span data-ttu-id="4872e-108">Az USMF bemutatócég adataiban használhatja ezt az eljárást.</span><span class="sxs-lookup"><span data-stu-id="4872e-108">You can use this procedure in the USMF demo data company.</span></span>


1. <span data-ttu-id="4872e-109">A navigációs ablaktáblán ugorjon a **Modulok > Raktárkezelés > Beállítás > Raktár > Helyprofilok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4872e-109">In the navigation pane, go to **Modules > Warehouse management > Setup > Warehouse > Location profiles**.</span></span>
2. <span data-ttu-id="4872e-110">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4872e-110">Select **New**.</span></span>
3. <span data-ttu-id="4872e-111">Írjon egy értéket a **Helyprofil azonosítója** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="4872e-111">In the **Location profile ID** field, type a value.</span></span>
4. <span data-ttu-id="4872e-112">Írjon be egy értéket a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="4872e-112">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="4872e-113">A **Helyformátum** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="4872e-113">In the **Location format** field, enter or select a value.</span></span>
6. <span data-ttu-id="4872e-114">A **Hely típusa** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="4872e-114">In the **Location type** field, enter or select a value.</span></span>
7. <span data-ttu-id="4872e-115">Adjon meg vagy válasszon ki egy értéket a **Kikötőkezelési profil azonosítója** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4872e-115">In the **Dock management profile ID** field, enter or select a value.</span></span>
8. <span data-ttu-id="4872e-116">Válassza ki az **Igen** lehetőséget a **Vegyes cikkek engedélyezése** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4872e-116">Select **Yes** in the **Allow mixed items** field.</span></span>
9. <span data-ttu-id="4872e-117">Válassza ki az **Igen** lehetőséget a **Vegyes készletállapotok engedélyezése** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4872e-117">Select **Yes** in the **Allow mixed inventory statuses** field.</span></span>
10. <span data-ttu-id="4872e-118">Válassza ki az **Igen** lehetőséget a **Ciklikus leltározás engedélyezése** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4872e-118">Select **Yes** in the **Allow cycle counting** field.</span></span>
11. <span data-ttu-id="4872e-119">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4872e-119">Select **Save**.</span></span>

