---
title: A termék várakoztatva van a tranzakcióknál
description: A tervezési rendelések megerősítése után olyan hibaüzenet jelenik meg, amely szerint egy cikk várakoztatva van a tranzakcióknál.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 6654e6437a088218db116b955631be4c7e62de5f
ms.sourcegitcommit: f9b145ef4a81cec81f420871b4130b05db4f4500
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2021
ms.locfileid: "6301279"
---
# <a name="product-is-on-hold-for-transactions"></a><span data-ttu-id="58ba7-103">A termék várakoztatva van a tranzakcióknál</span><span class="sxs-lookup"><span data-stu-id="58ba7-103">Product is on hold for transactions</span></span>

<span data-ttu-id="58ba7-104">Hibakód: SYS13295</span><span class="sxs-lookup"><span data-stu-id="58ba7-104">Error code: SYS13295</span></span>

## <a name="symptoms"></a><span data-ttu-id="58ba7-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="58ba7-105">Symptoms</span></span>

<span data-ttu-id="58ba7-106">A tervezett rendelés megerősítése után a következő hibaüzenetet kapja:</span><span class="sxs-lookup"><span data-stu-id="58ba7-106">After you firm planned orders, you receive the following error message:</span></span>

> <span data-ttu-id="58ba7-107">A(z) %1 cikk zárolva van a(z) %2 tranzakcióiban.</span><span class="sxs-lookup"><span data-stu-id="58ba7-107">Item %1 is on hold for transactions in %2.</span></span>

## <a name="cause"></a><span data-ttu-id="58ba7-108">Ok</span><span class="sxs-lookup"><span data-stu-id="58ba7-108">Cause</span></span>

<span data-ttu-id="58ba7-109">A zárolt cikkek leírásában a *zárolt*, a *leállított* és a *várakoztatott* szó ugyanazt jelenti.</span><span class="sxs-lookup"><span data-stu-id="58ba7-109">When describing blocked items, system uses the terms *blocked*, *stopped*, and *on hold* interchangeably.</span></span> <span data-ttu-id="58ba7-110">Ez a hiba azt jelenti, hogy a cikk **Leállítottként** van beállítva az alapértelmezett rendelési beállításaiban.</span><span class="sxs-lookup"><span data-stu-id="58ba7-110">This error means that the item is set as **Stopped** in its default order settings.</span></span>

<span data-ttu-id="58ba7-111">Ha egy cikk zárolva van, de Ön felveszi egy beszerzési rendelésre vagy egy értékesítési rendelési sorba, figyelmeztető üzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="58ba7-111">If an item is blocked, and you add it to a purchase order or sales order line, you receive a warning message.</span></span> <span data-ttu-id="58ba7-112">Ha egy cikk zárolva van, akkor a beszerzési rendeléshez vagy az értékesítési rendelés sorához kapcsolódó készlettranzakciókat nem lehet módosítani (például szállítólevél vagy számla feladásakor).</span><span class="sxs-lookup"><span data-stu-id="58ba7-112">When an item is blocked, inventory transactions that are related to the purchase order or sales order line can't be modified (for example, when you post a packing slip or an invoice).</span></span> <span data-ttu-id="58ba7-113">Lehetőség van arra, hogy egy beszerzett cikket zároljon, ugyanakkor mégis értékesítse.</span><span class="sxs-lookup"><span data-stu-id="58ba7-113">You can block a purchased item, and, at the same time, sell the item.</span></span> <span data-ttu-id="58ba7-114">Ebben az esetben a **Leállítva** jelölőnégyzet be van jelölve a beszerzési rendelésen, de a cikk nincs zárolva van a készletben vagy egy értékesítési rendelésen.</span><span class="sxs-lookup"><span data-stu-id="58ba7-114">In this case, the **Stopped** check box is selected on a purchase order, but the item isn't blocked in inventory or on a sales order.</span></span>

<span data-ttu-id="58ba7-115">Néhány olyan feltétel, amely egy adott számúa cikk eladásának zárolását okozhatja:</span><span class="sxs-lookup"><span data-stu-id="58ba7-115">Here are some of the conditions that can cause an item number to be blocked from being sold:</span></span>

- <span data-ttu-id="58ba7-116">A cikk még fejlesztés vagy gyártás alatt áll.</span><span class="sxs-lookup"><span data-stu-id="58ba7-116">The item is still under development or manufacture.</span></span> <span data-ttu-id="58ba7-117">Ezért nem szeretné, hogy eladják vagy lefoglalják.</span><span class="sxs-lookup"><span data-stu-id="58ba7-117">Therefore, you don't want it to be sold or reserved.</span></span>
- <span data-ttu-id="58ba7-118">Több hibás cikket kapott, és a hibákat ki kell javítani, mielőtt a cikk eladható lenne.</span><span class="sxs-lookup"><span data-stu-id="58ba7-118">You've received many defective items, and the defects must be corrected before the item can be sold.</span></span>

<span data-ttu-id="58ba7-119">Az ilyen típusú esetekben a cikkeket zárolni lehet a probléma megoldásáig.</span><span class="sxs-lookup"><span data-stu-id="58ba7-119">In cases of this type, you can block the item until the issue is resolved.</span></span>

<span data-ttu-id="58ba7-120">Ha egy cikk zárolva van, és visszáru-rendelési sort hoz létre, akkor a rendszer üzenetet küld.</span><span class="sxs-lookup"><span data-stu-id="58ba7-120">If an item is blocked, and you create a return order line, you receive a message.</span></span> <span data-ttu-id="58ba7-121">A cikkek sorozatai és adagjai nem blokkolhatók.</span><span class="sxs-lookup"><span data-stu-id="58ba7-121">You can't block a series or a lot of an item.</span></span> <span data-ttu-id="58ba7-122">Ha egy cikk egy adott részét kell blokkolni, akkor blokkolhatja őket egy készletbe helyezve, vagy úgy, hogy az adott időszakra a cikk teljes készletét blokkolja.</span><span class="sxs-lookup"><span data-stu-id="58ba7-122">If parts of an item must be blocked, you can block them by moving inventory or by blocking the full stock of the item for that period.</span></span>

## <a name="resolution"></a><span data-ttu-id="58ba7-123">Megoldás</span><span class="sxs-lookup"><span data-stu-id="58ba7-123">Resolution</span></span>

- <span data-ttu-id="58ba7-124">Nyissa meg az **Alapértelmezett rendelésbeállítások** oldalt a cikknél, és törölje a jelet a **Leállítva** jelölőnégyzetből.</span><span class="sxs-lookup"><span data-stu-id="58ba7-124">Open the **Default order settings** page for the item, and clear the **Stopped** checkbox.</span></span>
