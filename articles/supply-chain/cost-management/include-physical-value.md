---
title: Tényleges értékkel együtt
description: A Cikkmodell csoportok oldal készletmodell gyorslapján található tényleges értékkel együtt jelölőnégyzetet arra használhatja, hogy meghatározza a ténylegesen frissített tranzakciók vajon számításba vannak-e véve egy cikk mozgóátlagon alapuló önköltségi árának kiszámításakor.
author: AndersGirke
manager: tfehr
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventModelGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 79033
ms.assetid: 1928c145-bf82-436d-87ca-e7a173e31923
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5685fd384e240c1bc6236dbddf678c8d6d9c8c66
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5005502"
---
# <a name="include-physical-value"></a><span data-ttu-id="cfbbf-103">Tényleges értékkel együtt</span><span class="sxs-lookup"><span data-stu-id="cfbbf-103">Include physical value</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cfbbf-104">A Cikkmodell csoportok oldal készletmodell gyorslapján található tényleges értékkel együtt jelölőnégyzetet arra használhatja, hogy meghatározza a ténylegesen frissített tranzakciók vajon számításba vannak-e véve egy cikk mozgóátlagon alapuló önköltségi árának kiszámításakor.</span><span class="sxs-lookup"><span data-stu-id="cfbbf-104">You use the Include physical value check box on the Inventory model FastTab of the Item model groups page to specify whether physically updated transactions are considered when the running average cost price is calculated for an item.</span></span>

<span data-ttu-id="cfbbf-105">A **tényleges értékkel együtt** jelölőnégyzet a következő értékekkel rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="cfbbf-105">The **Include physical value** check box has the following values.</span></span>

| <span data-ttu-id="cfbbf-106">Érték</span><span class="sxs-lookup"><span data-stu-id="cfbbf-106">Value</span></span>    | <span data-ttu-id="cfbbf-107">Eredmény</span><span class="sxs-lookup"><span data-stu-id="cfbbf-107">Result</span></span>                                                                                                                          |
|----------|---------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="cfbbf-108">Kijelölve</span><span class="sxs-lookup"><span data-stu-id="cfbbf-108">Selected</span></span> | <span data-ttu-id="cfbbf-109">A mozgóátlagon alapuló önköltségi ár kiszámításához a ténylegesen frissített és a pénzügyileg frissített tranzakciók is felhasználásra kerülnek.</span><span class="sxs-lookup"><span data-stu-id="cfbbf-109">Both physically updated transactions and financially updated transactions are used to calculate the running average cost price.</span></span> |
| <span data-ttu-id="cfbbf-110">Törölve</span><span class="sxs-lookup"><span data-stu-id="cfbbf-110">Cleared</span></span>  | <span data-ttu-id="cfbbf-111">Csak a pénzügyileg frissített tranzakciók kerülnek felhasználásra a mozgóátlagon alapuló önköltségi ár kiszámításakor.</span><span class="sxs-lookup"><span data-stu-id="cfbbf-111">Only financially updated transactions are used to calculate the running average cost price.</span></span>                                     |

<span data-ttu-id="cfbbf-112">A jelölőnégyzeteknek némileg eltérő hatásuk van, attól függően, hogy milyen készletmodellt alkalmaz.</span><span class="sxs-lookup"><span data-stu-id="cfbbf-112">The check box has slightly different effects, depending on the inventory model that you use.</span></span>

-   <span data-ttu-id="cfbbf-113">Ha bejelöli a **tényleges értékkel együtt** jelölőnégyzetet a FIFO (elsőként be, elsőként ki), a LIFO (utolsóként be, elsőként ki) vagy a LIFO dátum készletmodellek esetében, akkor a készletzárás a ténylegesen frissített tranzakciókat is kiigazítja.</span><span class="sxs-lookup"><span data-stu-id="cfbbf-113">If you select the **Include physical value** check box when you use the FIFO (First in, first out), LIFO (Last in, first out), or LIFO date inventory model, inventory close also makes adjustments to physically updated transactions.</span></span>
-   <span data-ttu-id="cfbbf-114">Ha a **Tényleges értékkel együtt** jelölőnégyzet nincs bejelölve a készletmodellek használatakor, akkor a készletzárás csak a pénzügyileg frissített tranzakciókat rendezi.</span><span class="sxs-lookup"><span data-stu-id="cfbbf-114">If you don't select the **Include physical value** check box when you use these inventory models, inventory close makes settlements only to financially updated transactions.</span></span>
-   <span data-ttu-id="cfbbf-115">Amikor súlyozott átlagon vagy súlyozott átlagon és dátumon alapuló készletmodellt alkalmaz, a készletzárás csak a pénzügyileg frissített tranzakciókat fogja rendezni attól függetlenül, hogy be van-e jelölve a **Tényleges értékkel együtt** négyzet, vagy sem.</span><span class="sxs-lookup"><span data-stu-id="cfbbf-115">When you use the weighted average or weighted average date inventory model, inventory close settles only financially updated transactions, regardless of whether you select the **Include physical value** check box.</span></span>

<span data-ttu-id="cfbbf-116">**1. példa** Ön a **tényleges értékkel együtt** jelölőnégyzetet választotta, majd a következő beszerzési rendeléseket kapta:</span><span class="sxs-lookup"><span data-stu-id="cfbbf-116">**Example 1** You've selected the **Include physical value** check box and receive the following purchase orders:</span></span>

-   <span data-ttu-id="cfbbf-117">2-es mennyiségű beszerzési rendelés 10,00 USD önköltségi árral, melynek szállítólevele frissítve lett.</span><span class="sxs-lookup"><span data-stu-id="cfbbf-117">A purchase order for a quantity of 2 and a cost price of USD 10.00 that has been packing slip–updated.</span></span>
-   <span data-ttu-id="cfbbf-118">3-es mennyiségű beszerzési rendelés 12,00 USD önköltségi árral, melynek számlája frissítve lett.</span><span class="sxs-lookup"><span data-stu-id="cfbbf-118">A purchase order for a quantity of 3 and a cost price of USD 12.00 that has been invoice-updated.</span></span>

<span data-ttu-id="cfbbf-119">Ebben az esetben a mozgóátlagon alapuló önköltségi ár 11,20 USD = (2x10+3x12)/(2+3), mivel mind a tényleges, mind a pénzügyileg frissített tranzakciók fel lettek használva az önköltség kiszámításakor.</span><span class="sxs-lookup"><span data-stu-id="cfbbf-119">In this case, the running average cost price will be USD 11.20 = (2x10+3x12)/(2+3), because both physically updated transactions and financially updated transactions are used to calculate the cost price.</span></span> 

<span data-ttu-id="cfbbf-120">**2. példa** Ön nem jelölte be a **tényleges értékkel együtt** jelölőnégyzetet és a cikkbeállításoknál szereplő önköltségi ár 10,00 USD.</span><span class="sxs-lookup"><span data-stu-id="cfbbf-120">**Example 2** You haven't selected the **Include physical value** check box, and the cost price on the item setup is USD 10.00.</span></span> 

-   <span data-ttu-id="cfbbf-121">Kap egy 20-as mennyiségű beszerzési rendelést 12,00 USD önköltségi árral, melynek szállítólevele frissítve lett.</span><span class="sxs-lookup"><span data-stu-id="cfbbf-121">You receive a purchase order for a quantity of 20 and a cost price of USD 12.00 that has been packing slip–updated.</span></span>

<span data-ttu-id="cfbbf-122">Egy értékesítési rendelés feladásakor, a feladott költségösszeg 10,00 USD, mivel a mozgóátlagon alapuló önköltségi ár nem fogja tartalmazni a ténylegesen feladott tranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="cfbbf-122">When a sales order is posted, the posted cost amount is USD 10.00, because the running average cost price won't include physically posted transactions.</span></span> 

> [!NOTE]
> <span data-ttu-id="cfbbf-123">Összehasonlításképpen: Ha bejelöli a **Tényleges értékkel együtt** jelölőnégyzetet egy értékesítési rendelés feladásakor, akkor a feladott költség összege 12,00 USD lesz.</span><span class="sxs-lookup"><span data-stu-id="cfbbf-123">For comparison, if you select the **Include physical value** check box for this item, when a sales order is posted, the posted cost amount will be USD 12.00.</span></span>
