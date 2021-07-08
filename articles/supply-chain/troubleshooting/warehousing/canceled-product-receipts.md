---
title: A visszavont termékbevételezések nem frissítik a tranzakció állapotát Regisztrálva állapotra
description: Miután visszavonta a bejövő rakomány termékbevételezéseit, a rendszer automatikusan Beérkezett állapotról Megrendelve állapotra frissíti a készlettranzakció állapotát.
author: GalynaFedorova
ms.date: 06/11/2021
ms.topic: troubleshooting
ms.search.form: WMSPickingRegistration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-06-11
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 9c86457d50a7a9ac2a699a0e0a9c7bdf4cd7c67b
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294090"
---
# <a name="canceled-product-receipts-dont-update-transaction-status-to-registered"></a><span data-ttu-id="b04b6-103">A visszavont termékbevételezések nem frissítik a tranzakció állapotát Regisztrálva állapotra</span><span class="sxs-lookup"><span data-stu-id="b04b6-103">Canceled product receipts don't update transaction status to Registered</span></span>

## <a name="symptoms"></a><span data-ttu-id="b04b6-104">Tünetek</span><span class="sxs-lookup"><span data-stu-id="b04b6-104">Symptoms</span></span>

<span data-ttu-id="b04b6-105">Miután a beérkező terhelésen futtatta a **Termékbevételek törlése** műveletet, a rendszer automatikusan frissíti a készlettranzakciók állapotát a *Fogadottról* a *Rendeltre*.</span><span class="sxs-lookup"><span data-stu-id="b04b6-105">After you run the **Cancel product receipts** action on an inbound load, the system automatically updates the status of inventory transactions from *Received* to *Ordered*.</span></span>

## <a name="resolution"></a><span data-ttu-id="b04b6-106">Megoldás</span><span class="sxs-lookup"><span data-stu-id="b04b6-106">Resolution</span></span>

<span data-ttu-id="b04b6-107">Amikor a kimenő rakományok csomagjegyzékét törlik, a készlettranzakciók állapota *Kitárolt* marad.</span><span class="sxs-lookup"><span data-stu-id="b04b6-107">When packing slips are canceled for outbound loads, the status of inventory transactions remains *Picked*.</span></span> <span data-ttu-id="b04b6-108">Amikor azonban a bejövő rakományból származó termékbevételezéseket visszavonják, a készlettranzakciók állapota nem áll vissza a *Regisztrálva* állapotra.</span><span class="sxs-lookup"><span data-stu-id="b04b6-108">However, when product receipts from an inbound load are canceled, the status of inventory transactions isn't restored to *Registered*.</span></span> <span data-ttu-id="b04b6-109">Ennek megfelelően a bejövő rakományból származó termékbevételezés visszavonása után a raktári dolgozónak újra regisztrálnia kell a cikkmennyiségeket a rakományok számára.</span><span class="sxs-lookup"><span data-stu-id="b04b6-109">Therefore, after a product receipt from an inbound load is canceled, the warehouse worker must re-register item quantities for the loads.</span></span>

<span data-ttu-id="b04b6-110">További információ a bejövő rakományba [Bejövő rakománnyal érkező cikkmennyiség regisztrálása](/dynamics365/supply-chain/warehousing/inbound-load-handling#register-item-quantities-arriving).</span><span class="sxs-lookup"><span data-stu-id="b04b6-110">For more information, see [Register item quantities that arrive on an inbound load](/dynamics365/supply-chain/warehousing/inbound-load-handling#register-item-quantities-arriving).</span></span>
