---
title: Nincs Kezdő dátum érték a Cikkár lap Aktív árak lapján
description: Nincs Kezdő dátum érték a Cikkár lap Aktív árak lapján.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventItemPrice
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 3dd13f6a3e5ce3c894e96f420358d337f2e43dba
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026590"
---
# <a name="there-is-no-from-date-value-on-the-active-prices-tab-of-the-item-price-page"></a><span data-ttu-id="9c544-103">Nincs Kezdő dátum érték a Cikkár lap Aktív árak lapján</span><span class="sxs-lookup"><span data-stu-id="9c544-103">There is no From date value on the Active prices tab of the Item price page</span></span>

<span data-ttu-id="9c544-104">Tudásbáziscikk száma: 4613548</span><span class="sxs-lookup"><span data-stu-id="9c544-104">KB number: 4613548</span></span>

## <a name="symptoms"></a><span data-ttu-id="9c544-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="9c544-105">Symptoms</span></span>

<span data-ttu-id="9c544-106">Nincs **Kezdő dátum** érték a **Cikkár lap** **Aktív árak** lapján.</span><span class="sxs-lookup"><span data-stu-id="9c544-106">There is no **From date** value on the **Active prices** tab of the **Item price** page.</span></span>

## <a name="resolution"></a><span data-ttu-id="9c544-107">Felbontás</span><span class="sxs-lookup"><span data-stu-id="9c544-107">Resolution</span></span>

<span data-ttu-id="9c544-108">A függő árhoz beállított **Kezdő dátum** (érvénybe lépés dátuma) nem kerül át az aktív árba.</span><span class="sxs-lookup"><span data-stu-id="9c544-108">The **From date** value (effective date) that is set on the pending price isn't transferred to the active price.</span></span>

<span data-ttu-id="9c544-109">A cikk-költségrekordok a legelső bevitelkor *Függőbben* állapottal és egy tervezett érvénybelépési dátummal rendelkeznek.</span><span class="sxs-lookup"><span data-stu-id="9c544-109">When an item cost record is first entered, it has a status of *Pending* and an intended effective date.</span></span> <span data-ttu-id="9c544-110">A cikk-költség rekord aktiválásakor az állapot *Aktív* lesz, továbbá az érvénybelépési dátum az aktiválási dátumra módosul.</span><span class="sxs-lookup"><span data-stu-id="9c544-110">When you activate the item cost record, the status is updated to *Active*, and the effective date is updated to the activation date.</span></span> <span data-ttu-id="9c544-111">Ennek megfelelően az aktív ár aktiválási dátuma mindig az aktiválás tényleges dátuma.</span><span class="sxs-lookup"><span data-stu-id="9c544-111">Therefore, the active price's activation date is always the actual date of the activation.</span></span>

<span data-ttu-id="9c544-112">További információ: [Költségszámítási verziók áttekintése](../../cost-management/costing-versions.md).</span><span class="sxs-lookup"><span data-stu-id="9c544-112">For more information, see [Costing versions overview](../../cost-management/costing-versions.md).</span></span>
