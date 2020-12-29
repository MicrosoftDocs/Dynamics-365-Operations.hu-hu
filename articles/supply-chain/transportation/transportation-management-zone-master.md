---
title: Szállításkezelés zónaalapja
description: Ez a témakör azt mutatja be, hogy a szállításkezelés hogyan segít zónákra oszthatja a földrajzi helyeket.
author: Henrikan
manager: ''
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSZoneMaster
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 12234
ms.assetid: b878478c-0e04-4a1e-a037-6fdbb345a9a3
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-01-09
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 2112e7131281cd485b580fd71536981c1ba4aefd
ms.sourcegitcommit: fe7ac653efcb1ac6318083f482394b96ed82b4c7
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/29/2020
ms.locfileid: "4429985"
---
# <a name="transportation-management-zone-master"></a><span data-ttu-id="24587-103">Szállításkezelés zónaalapja</span><span class="sxs-lookup"><span data-stu-id="24587-103">Transportation management zone master</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="24587-104">A szállításkezelés segít zónákra osztani a földrajzi helyeket.</span><span class="sxs-lookup"><span data-stu-id="24587-104">Transport management lets you divide geographic locations into zones.</span></span> <span data-ttu-id="24587-105">A helyek zónákra történő felosztása a következőkben segíthet:</span><span class="sxs-lookup"><span data-stu-id="24587-105">Dividing locations into zones can help to:</span></span>

- <span data-ttu-id="24587-106">**Szállítási árak egyszerűsítése** – Zónaalapú árak egyszerűbbek az egyes helyalapú árképzéseknél, különösen akkor, ha a szállítási helyek elszórtak.</span><span class="sxs-lookup"><span data-stu-id="24587-106">**Simplify transportation pricing** – Zone-wise pricing can be simpler than individual location-based pricing, especially when transportation locations are scattered.</span></span>
- <span data-ttu-id="24587-107">**Rakománytervezés optimalizálása** – A rakományok zónák szerinti konszolidálása.</span><span class="sxs-lookup"><span data-stu-id="24587-107">**Optimize load planning** – By consolidating loads by zones.</span></span>
- <span data-ttu-id="24587-108">**Útvonaltervezés optimalizálása** – Meghatározott útvonalak hozzárendelése meghatározott zónákhoz.</span><span class="sxs-lookup"><span data-stu-id="24587-108">**Optimize route planning** – By assigning specific route plans to specific zones.</span></span>

<span data-ttu-id="24587-109">A zónák a metaadat-mezőértékek (például ország, irányítószám vagy szállítmányozói szolgáltatás) alapján definiálhatók, amelyek az egyes zónákra érvényesek.</span><span class="sxs-lookup"><span data-stu-id="24587-109">You define zones based on the metadata field values (such as country, zip code range, or carrier service) that qualify each zone.</span></span> <span data-ttu-id="24587-110">A zónák definícióit nem szükséges megadni, ha a szállítási árak nem alkalmaznak zónakoncepciót.</span><span class="sxs-lookup"><span data-stu-id="24587-110">Zone definitions aren't required if your transportation pricing doesn't employ a zone concept.</span></span>
