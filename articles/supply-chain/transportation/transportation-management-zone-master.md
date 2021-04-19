---
title: Szállításkezelés zónaalapja
description: Ez a témakör azt mutatja be, hogy a szállításkezelés hogyan segít zónákra oszthatja a földrajzi helyeket.
author: Henrikan
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TMSZoneMaster
audience: Application User
ms.reviewer: kamaybac
ms.custom: 12234
ms.assetid: b878478c-0e04-4a1e-a037-6fdbb345a9a3
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-01-09
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: aec1c17d32d1469f3a452084138404de3d498b71
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5807584"
---
# <a name="transportation-management-zone-master"></a><span data-ttu-id="e0905-103">Szállításkezelés zónaalapja</span><span class="sxs-lookup"><span data-stu-id="e0905-103">Transportation management zone master</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e0905-104">A szállításkezelés segít zónákra osztani a földrajzi helyeket.</span><span class="sxs-lookup"><span data-stu-id="e0905-104">Transport management lets you divide geographic locations into zones.</span></span> <span data-ttu-id="e0905-105">A helyek zónákra történő felosztása a következőkben segíthet:</span><span class="sxs-lookup"><span data-stu-id="e0905-105">Dividing locations into zones can help to:</span></span>

- <span data-ttu-id="e0905-106">**Szállítási árak egyszerűsítése** – Zónaalapú árak egyszerűbbek az egyes helyalapú árképzéseknél, különösen akkor, ha a szállítási helyek elszórtak.</span><span class="sxs-lookup"><span data-stu-id="e0905-106">**Simplify transportation pricing** – Zone-wise pricing can be simpler than individual location-based pricing, especially when transportation locations are scattered.</span></span>
- <span data-ttu-id="e0905-107">**Rakománytervezés optimalizálása** – A rakományok zónák szerinti konszolidálása.</span><span class="sxs-lookup"><span data-stu-id="e0905-107">**Optimize load planning** – By consolidating loads by zones.</span></span>
- <span data-ttu-id="e0905-108">**Útvonaltervezés optimalizálása** – Meghatározott útvonalak hozzárendelése meghatározott zónákhoz.</span><span class="sxs-lookup"><span data-stu-id="e0905-108">**Optimize route planning** – By assigning specific route plans to specific zones.</span></span>

<span data-ttu-id="e0905-109">A zónák a metaadat-mezőértékek (például ország, irányítószám vagy szállítmányozói szolgáltatás) alapján definiálhatók, amelyek az egyes zónákra érvényesek.</span><span class="sxs-lookup"><span data-stu-id="e0905-109">You define zones based on the metadata field values (such as country, zip code range, or carrier service) that qualify each zone.</span></span> <span data-ttu-id="e0905-110">A zónák definícióit nem szükséges megadni, ha a szállítási árak nem alkalmaznak zónakoncepciót.</span><span class="sxs-lookup"><span data-stu-id="e0905-110">Zone definitions aren't required if your transportation pricing doesn't employ a zone concept.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]