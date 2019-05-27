---
title: Helyprofil létrehozása
description: A raktárban minden helyhez társítani kell egy helyprofilt, amely leírja a hely tulajdonságait, például azt, hogy a hely engedélyezi-e a vegyes cikkeket.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationProfile
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8bc7705b7db46af8fbe8bf9e78a878a53249b452
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1560906"
---
# <a name="create-a-location-profile"></a><span data-ttu-id="46c72-103">Helyprofil létrehozása</span><span class="sxs-lookup"><span data-stu-id="46c72-103">Create a location profile</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="46c72-104">A raktárban minden helyhez társítani kell egy helyprofilt, amely leírja a hely tulajdonságait, például azt, hogy a hely engedélyezi-e a vegyes cikkeket.</span><span class="sxs-lookup"><span data-stu-id="46c72-104">Every location in the warehouse needs to have a location profile associated with it that describes the properties of the location, for example, whether the location allows mixed items.</span></span> <span data-ttu-id="46c72-105">Ebben az eljárásban olyan helyprofilt hozunk létre, amely nem igényel azonosítótáblás szabályozást.</span><span class="sxs-lookup"><span data-stu-id="46c72-105">In this procedure we’ll create a profile for a location that doesn’t require license plate control.</span></span> <span data-ttu-id="46c72-106">Engedélyezzük a vegyes cikkeket és a kevert készlet állapotokat, és engedélyezzük a ciklus leltározást.</span><span class="sxs-lookup"><span data-stu-id="46c72-106">We’ll enable mixed items, and mixed inventory statuses, and allow cycle counting.</span></span> <span data-ttu-id="46c72-107">Az USMF bemutatócég adataiban használhatja ezt az eljárást.</span><span class="sxs-lookup"><span data-stu-id="46c72-107">You can use this procedure in the USMF demo data company.</span></span>

1. <span data-ttu-id="46c72-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="46c72-108">Click New.</span></span>
2. <span data-ttu-id="46c72-109">Írjon egy értéket a Helyprofil azonosítója mezőbe.</span><span class="sxs-lookup"><span data-stu-id="46c72-109">In the Location profile ID field, type a value.</span></span>
3. <span data-ttu-id="46c72-110">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="46c72-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="46c72-111">A Helyformátum mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="46c72-111">In the Location format field, enter or select a value.</span></span>
5. <span data-ttu-id="46c72-112">A Hely típusa mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="46c72-112">In the Location type field, enter or select a value.</span></span>
6. <span data-ttu-id="46c72-113">Adjon meg vagy válasszon ki egy értéket a Kikötőkezelési profil azonosítója mezőben.</span><span class="sxs-lookup"><span data-stu-id="46c72-113">In the Dock management profile ID field, enter or select a value.</span></span>
7. <span data-ttu-id="46c72-114">Válassza ki az Igen lehetőséget a Vegyes cikkek engedélyezése mezőben.</span><span class="sxs-lookup"><span data-stu-id="46c72-114">Select Yes in the Allow mixed items field.</span></span>
8. <span data-ttu-id="46c72-115">Válassza ki az Igen lehetőséget a Vegyes készletállapotok engedélyezése mezőben.</span><span class="sxs-lookup"><span data-stu-id="46c72-115">Select Yes in the Allow mixed  inventory statuses field.</span></span>
9. <span data-ttu-id="46c72-116">Válassza ki az Igen lehetőséget a Ciklikus leltározás engedélyezése mezőben.</span><span class="sxs-lookup"><span data-stu-id="46c72-116">Select Yes in the Allow cycle counting field.</span></span>
10. <span data-ttu-id="46c72-117">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="46c72-117">Click Save.</span></span>
11. <span data-ttu-id="46c72-118">Ugorjon a Raktárkezelés > Beállítás > Raktárkezelési > Helyprofilok pontra.</span><span class="sxs-lookup"><span data-stu-id="46c72-118">Go to Warehouse management > Setup > Warehouse > Location profiles.</span></span>

