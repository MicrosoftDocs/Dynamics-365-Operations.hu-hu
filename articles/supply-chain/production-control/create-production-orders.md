---
title: Termelési rendelés életciklusának áttekintése
description: A termelési rendelés létrehozása egy kérést kezdeményez egy cikk gyártásának az elindítására. A termelési rendelés tartalmazza azokat az információkat, hogy mit fognak gyártani, milyen mennyiségben és a mi a tervezett befejezési dátum. Azokat az információkat is tartalmazza, hogy mely anyagokat használják fel és hogy mely folyamatot kell követni a cikk előállításához.
author: johanhoffmann
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTable, ProdTableCreate
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19741
ms.assetid: bbb6e69d-479c-45fc-a0a8-66da5df16c7f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 68758f4ddf39b4b8f7f0758f9e59e17c3411723a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5246309"
---
# <a name="production-order-lifecycle-overview"></a><span data-ttu-id="9a697-105">Termelési rendelés életciklusának áttekintése</span><span class="sxs-lookup"><span data-stu-id="9a697-105">Production order lifecycle overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9a697-106">A termelési rendelés létrehozása egy kérést kezdeményez egy cikk gyártásának az elindítására.</span><span class="sxs-lookup"><span data-stu-id="9a697-106">When a production order is created, a request is initiated to start producing an item.</span></span> <span data-ttu-id="9a697-107">A termelési rendelés tartalmazza azokat az információkat, hogy mit fognak gyártani, milyen mennyiségben és a mi a tervezett befejezési dátum.</span><span class="sxs-lookup"><span data-stu-id="9a697-107">The production order contains information about what will be produced, the quantity to produce, and the planned finish date.</span></span> <span data-ttu-id="9a697-108">Azokat az információkat is tartalmazza, hogy mely anyagokat használják fel és hogy mely folyamatot kell követni a cikk előállításához.</span><span class="sxs-lookup"><span data-stu-id="9a697-108">It also contains information about which materials to consume and which process to follow to produce the item.</span></span>

<span data-ttu-id="9a697-109">A termelési megrendelés végighalad a termék életciklus-szakaszain.</span><span class="sxs-lookup"><span data-stu-id="9a697-109">A production order passes through stages of the production life cycle.</span></span> <span data-ttu-id="9a697-110">Amikor egy megrendelés létrejön hozzárendelődik a **Létrehozva** állapot.</span><span class="sxs-lookup"><span data-stu-id="9a697-110">When an order is created, it is assigned the status **Created**.</span></span> <span data-ttu-id="9a697-111">Amikor egy megrendelés befejeződik hozzárendelődik a **Befejezett** állapot.</span><span class="sxs-lookup"><span data-stu-id="9a697-111">When an order is finished, it is assigned the status **Ended**.</span></span> <span data-ttu-id="9a697-112">Minden szakaszban egy paraméter-beállítás engedélyei a felhasználónak, hogy konfigurálja az egyes lépéseket.</span><span class="sxs-lookup"><span data-stu-id="9a697-112">A parameter setting in each stage allows a user to configure each step.</span></span> <span data-ttu-id="9a697-113">A beállítás alkalmazható egy felhasználónak vagy az összes felhasználónak.</span><span class="sxs-lookup"><span data-stu-id="9a697-113">The setting can be set up for a single user or for all users.</span></span>

<span data-ttu-id="9a697-114">A termelési anyagjegyzék és a termelési útvonal a termelési megrendelés fő entitásai.</span><span class="sxs-lookup"><span data-stu-id="9a697-114">The production bill of material and the production route are the main entities of the production order.</span></span> <span data-ttu-id="9a697-115">A termelési megrendelésbe másolódnak a kiválasztott termelésre kerülő cikk és mennyisség alapján.</span><span class="sxs-lookup"><span data-stu-id="9a697-115">They are copied to the production order based on the selected item and quantity that are going to be produced.</span></span> <span data-ttu-id="9a697-116">Mielőtt a termelési megrendelés megkezdődik a termelési anyagjegyzék és útvonal szerkeszthető.</span><span class="sxs-lookup"><span data-stu-id="9a697-116">Before the production order is started, the production bill of material and route can be edited.</span></span>

<span data-ttu-id="9a697-117">Egy termelési megrendelés a következő esetekben hozható létre:</span><span class="sxs-lookup"><span data-stu-id="9a697-117">A production order can be created in the following scenarios:</span></span>

-   <span data-ttu-id="9a697-118">Az alaptermelés végrehajtásával anyagi igény alapján létrehozva.</span><span class="sxs-lookup"><span data-stu-id="9a697-118">Created by master planning execution based on material demand.</span></span>
-   <span data-ttu-id="9a697-119">Közvetlenül az értékesítési megrendelés sorból vagy magasabb szintű termelési megrendelés létrejöttekor és becslésekor (rögzített készletek) létrehozva.</span><span class="sxs-lookup"><span data-stu-id="9a697-119">Created directly from a sales order line or when a higher-level production order is created and estimated (pegged supply).</span></span>
-   <span data-ttu-id="9a697-120">Manuálisan létrehozva.</span><span class="sxs-lookup"><span data-stu-id="9a697-120">Created manually.</span></span>






[!INCLUDE[footer-include](../../includes/footer-banner.md)]