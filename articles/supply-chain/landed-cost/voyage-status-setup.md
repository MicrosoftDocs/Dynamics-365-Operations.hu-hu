---
title: Hajóút állapotának beállítása
description: Ez a témakör leírja, hogyan lehet megállapítani a felhasználók által hajóutakhoz rendelhető állapotértékeket.
author: sherry-zheng
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMStatusTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 80433c17ed9d790d88b20ecc253c8e4459ffea10
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829788"
---
# <a name="voyage-status-setup"></a><span data-ttu-id="15881-103">Hajóút állapotának beállítása</span><span class="sxs-lookup"><span data-stu-id="15881-103">Voyage status setup</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="15881-104">A **Hajóút állapota** oldalon meghatározza a felhasználók által a hajóutakhoz rendelhető állapotértékeket.</span><span class="sxs-lookup"><span data-stu-id="15881-104">On the **Voyage statuses** page, you establish the set of status values that users can assign to voyages.</span></span> <span data-ttu-id="15881-105">A felhasználók a hajóút minden szintjéhez hozzárendelhetnek egy állapotot: hajóút, szállítókonténer, árulevél, beszerzési rendelés és cikk (vásárlási sorok és átmozgatási rendelési sorok).</span><span class="sxs-lookup"><span data-stu-id="15881-105">Users can assign voyage status values to all levels of a voyage: voyage, shipping container, folio, purchase order, and item (purchase lines and transfer order lines).</span></span> <span data-ttu-id="15881-106">Ezeknek két céljuk van:</span><span class="sxs-lookup"><span data-stu-id="15881-106">They are used for two purposes:</span></span>

- <span data-ttu-id="15881-107">A felhasználó tájékoztatása a hajóút, a szállítókonténer, az árulevél, a beszerzési rendelés vagy a cikk állapotáról (beszerzési sorok és átmozgatási rendelési sorok).</span><span class="sxs-lookup"><span data-stu-id="15881-107">Inform the user about the status of the voyage, shipping container, folio, purchase order, or item (purchase lines and transfer order lines).</span></span>
- <span data-ttu-id="15881-108">A költségterület használatának korlátozása a módosítás vagy törlés megakadályozásával.</span><span class="sxs-lookup"><span data-stu-id="15881-108">Limit the use of the cost area by preventing modification or deletion.</span></span>

<span data-ttu-id="15881-109">A hajóút állapotának beállításához lépjen a **Partraszállítási költség \> Hajóút beállítása \> Hajóút állapota** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="15881-109">To set up your voyage statuses, go to **Landed cost \> Setup \> Voyage statuses**.</span></span> <span data-ttu-id="15881-110">A műveleti ablaktábla gombjaival lehet állapotokat hozzáadni, eltávolítani és szerkeszteni.</span><span class="sxs-lookup"><span data-stu-id="15881-110">There, you can add, remove, and edit statuses by using the buttons on the Action Pane.</span></span>

<span data-ttu-id="15881-111">Minden költségterületnek saját hajóállapot-hierarchiája és készlete van.</span><span class="sxs-lookup"><span data-stu-id="15881-111">Each cost area has its own set and hierarchy of voyage statuses.</span></span> <span data-ttu-id="15881-112">Ezért a **Hajóút állapota** oldalon a **Költségterület** mezőben ki kell választania azt a költségterületet, amelyhez kapcsolódóan hajóút-állapotokat szeretne megtekinteni vagy létrehozni.</span><span class="sxs-lookup"><span data-stu-id="15881-112">Therefore, on the **Voyage statuses** page, in the **Cost area** field, you must first select the cost area that you want to view or create voyage statuses for.</span></span> <span data-ttu-id="15881-113">Ezután szükség szerint minden hajóút állapota esetén állítsa be a következő táblázatban leírt mezőket.</span><span class="sxs-lookup"><span data-stu-id="15881-113">Then, for each voyage status, set the fields that are described in the following table, as required.</span></span> <span data-ttu-id="15881-114">Ne feledje, hogy a hajóút állapotát a rendszeresemények automatikusan módosíthatják, például a követési központ használatával meghatározott szabályok.</span><span class="sxs-lookup"><span data-stu-id="15881-114">Note that the status of a voyage can also be automatically changed by system events, such as rules that have been established by using the tracking control center.</span></span>

| <span data-ttu-id="15881-115">Mező</span><span class="sxs-lookup"><span data-stu-id="15881-115">Field</span></span> | <span data-ttu-id="15881-116">Leírás</span><span class="sxs-lookup"><span data-stu-id="15881-116">Description</span></span> |
|---|---|
| <span data-ttu-id="15881-117">Út állapota</span><span class="sxs-lookup"><span data-stu-id="15881-117">Voyage status</span></span> | <span data-ttu-id="15881-118">Adja meg a hajóút állapotának nevét.</span><span class="sxs-lookup"><span data-stu-id="15881-118">Enter the name of the voyage status.</span></span> |
| <span data-ttu-id="15881-119">Leírás</span><span class="sxs-lookup"><span data-stu-id="15881-119">Description</span></span> | <span data-ttu-id="15881-120">Adja meg a hajóút állapotának leírását.</span><span class="sxs-lookup"><span data-stu-id="15881-120">Enter a description of the voyage status.</span></span> |
| <span data-ttu-id="15881-121">Módosítás</span><span class="sxs-lookup"><span data-stu-id="15881-121">Modify</span></span> | <span data-ttu-id="15881-122">Jelölje be ezt a jelölőnégyzetet, ha a felhasználók módosíthatják az ilyen állapotú hajóutakat.</span><span class="sxs-lookup"><span data-stu-id="15881-122">Select this check box if users are allowed to modify voyages that have this status.</span></span> |
| <span data-ttu-id="15881-123">Eltávolítás</span><span class="sxs-lookup"><span data-stu-id="15881-123">Delete</span></span> | <span data-ttu-id="15881-124">Jelölje be ezt a jelölőnégyzetet, ha a felhasználók törölhetik az ilyen állapotú hajóutakat.</span><span class="sxs-lookup"><span data-stu-id="15881-124">Select this check box if users are allowed to delete voyages that have this status.</span></span> |
| <span data-ttu-id="15881-125">Kötelező</span><span class="sxs-lookup"><span data-stu-id="15881-125">Mandatory</span></span> | <span data-ttu-id="15881-126">Jelölje be ezt a jelölőnégyzetet, ha kötelezővé teszi a hajóút állapotát, hogy ne legyen átugorható.</span><span class="sxs-lookup"><span data-stu-id="15881-126">Select this check box to make the voyage status mandatory, so that it can't be skipped.</span></span> |
| <span data-ttu-id="15881-127">Szülő</span><span class="sxs-lookup"><span data-stu-id="15881-127">Parent</span></span> | <span data-ttu-id="15881-128">Ezzel a mezővel hierarchiát hozhat létre az állapotértékek között.</span><span class="sxs-lookup"><span data-stu-id="15881-128">Use this field to establish a hierarchy among the status values.</span></span> <span data-ttu-id="15881-129">A hajóút-állapotok (manuálisan vagy automatikusan) csak lefelé módosíthatók a hierarchiában szülőállapotról az egyik gyermekállapotra.</span><span class="sxs-lookup"><span data-stu-id="15881-129">Voyage statuses can be changed (either manually or automatically) only downward in the hierarchy, from a parent status to one of its child statuses.</span></span>

> [!NOTE]
> <span data-ttu-id="15881-130">Csak a szervezete által használt hajóút-állapotokat kell beállítani.</span><span class="sxs-lookup"><span data-stu-id="15881-130">You have to set up only the specific voyage statuses that your organization uses.</span></span> <span data-ttu-id="15881-131">A jellemző hajóút-állapotok a következők: *Visszaigazolva*, *Úton lévő áruk*, *Beérkezett*, *Költségszámításra kész* és *Költség elszámolva*.</span><span class="sxs-lookup"><span data-stu-id="15881-131">Typical voyage statuses include *Confirmed*, *Goods in transit*, *Received*, *Ready for costing*, and *Costed*.</span></span> <span data-ttu-id="15881-132">Előfordulhatnak azonban más állapotok is.</span><span class="sxs-lookup"><span data-stu-id="15881-132">However, other statuses might be present.</span></span>
