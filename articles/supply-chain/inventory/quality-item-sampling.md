---
title: Minőségkezelési cikkmintavétel
description: Ez a témakör a cikkmintavételek beállítását ismerteti.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventItemSampling
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ae8bfd329ca0d7c30adcd93a759ee6bea7b76278
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022228"
---
# <a name="quality-management-item-sampling"></a><span data-ttu-id="a93d5-103">Minőségkezelési cikkmintavétel</span><span class="sxs-lookup"><span data-stu-id="a93d5-103">Quality management item sampling</span></span>

<span data-ttu-id="a93d5-104">A cikkmintavétel a minőségi társítás részeként használatos.</span><span class="sxs-lookup"><span data-stu-id="a93d5-104">Item sampling is used as part of a quality association.</span></span> <span data-ttu-id="a93d5-105">Meghatározza az aktuális fizikai készlet vizsgálandó mennyiségét.</span><span class="sxs-lookup"><span data-stu-id="a93d5-105">It defines the amount of current physical inventory that must be inspected.</span></span> <span data-ttu-id="a93d5-106">A mintavétel történhet rögzített mennyiség, százalékos érték vagy teljes azonosítótábla alapján.</span><span class="sxs-lookup"><span data-stu-id="a93d5-106">Sampling can be based on fixed quantities, a percentage, or a full license plate.</span></span>

## <a name="set-up-item-sampling"></a><span data-ttu-id="a93d5-107">Cikk-mintavétel beállítása</span><span class="sxs-lookup"><span data-stu-id="a93d5-107">Set up item sampling</span></span>

<span data-ttu-id="a93d5-108">A cikkmintavétel beállításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="a93d5-108">Follow these steps to set up item sampling.</span></span>

1. <span data-ttu-id="a93d5-109">Ugorjon a következőhöz: **Készletkezelés \> Beállítás \> Minőség-ellenőrzés \> Cikkmintavétel**.</span><span class="sxs-lookup"><span data-stu-id="a93d5-109">Go to **Inventory management \> Setup \> Quality control \> Item sampling**.</span></span>
1. <span data-ttu-id="a93d5-110">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a93d5-110">Select **New**.</span></span>
1. <span data-ttu-id="a93d5-111">Adjon meg egy értéket a **Cikkmintavétel** mezőben.</span><span class="sxs-lookup"><span data-stu-id="a93d5-111">In the **Item sampling** field, enter a value.</span></span>
1. <span data-ttu-id="a93d5-112">A **Leírás** mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="a93d5-112">In the **Description** field, enter a value.</span></span>
1. <span data-ttu-id="a93d5-113">Adjon meg egy számot az **Érték** mezőben.</span><span class="sxs-lookup"><span data-stu-id="a93d5-113">In the **Value** field, enter a number.</span></span> <span data-ttu-id="a93d5-114">Ez az érték a szomszédos mezőben kiválasztott megadott mennyiségre vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="a93d5-114">This value is related to the quantity specification value that is selected in the adjacent field.</span></span>
1. <span data-ttu-id="a93d5-115">A **Folyamat** szakaszban jelölje be a **Teljes zárolás** jelölőnégyzetet, ha a teszt sikertelensége esetén a teljes tétel- vagy rendeléssormennyiséget le kell tiltani.</span><span class="sxs-lookup"><span data-stu-id="a93d5-115">In the **Process** section, select the **Full blocking** check box if the whole lot or order line quantity should be blocked if a test is failed.</span></span> <span data-ttu-id="a93d5-116">Ha a jelölőnégyzet nincs bejelölve, akkor ha a teszt sikertelen, csak a minőségi rendelés cikkeket tiltja le a rendszer.</span><span class="sxs-lookup"><span data-stu-id="a93d5-116">If this check box is cleared, only the items in the quality order will be blocked if a test is failed.</span></span>
1. <span data-ttu-id="a93d5-117">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a93d5-117">Select **Save**.</span></span>
1. <span data-ttu-id="a93d5-118">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="a93d5-118">Close the page.</span></span>

> [!NOTE]
> <span data-ttu-id="a93d5-119">A *Raktári folyamatok minőségkezelése* funkció további cikkmintavételi képességeket ad hozzá.</span><span class="sxs-lookup"><span data-stu-id="a93d5-119">The *Quality management for warehouse processes* feature provides additional item sampling capabilities.</span></span> <span data-ttu-id="a93d5-120">Bevezeti a *Cikkmintaétel hatókörének* fogalmát, és lehetővé teszi egy teljes azonosítótábla meghatározását mennyiségi specifikációnak.</span><span class="sxs-lookup"><span data-stu-id="a93d5-120">It adds the concept of *item sampling scope* and lets you define a full license plate as the quantity specification.</span></span> <span data-ttu-id="a93d5-121">Ha bekapcsolta ezt a funkciót, lásd: [Raktári folyamatok minőségkezelése](quality-management-for-warehouses-processes.md).</span><span class="sxs-lookup"><span data-stu-id="a93d5-121">If you've turned on this feature, see [Quality management for warehouse processes](quality-management-for-warehouses-processes.md).</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
