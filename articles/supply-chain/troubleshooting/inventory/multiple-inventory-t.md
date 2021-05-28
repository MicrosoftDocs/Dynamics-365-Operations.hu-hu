---
title: Több készlettranzakció kötegszámokhoz, ha a Tényleges frissítéskor nincs engedélyezve
description: Több készlettranzakció jön létre, miután módosította a beszerzésirendelés-sort az olyan cikkekhez, amelyeknél a kötegszámcsoport Tényleges frissítésekor beállításának értéke Nem.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventNumGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 1fa54cdfdbc5608fb6c7114dced0f96bab47253e
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026589"
---
# <a name="multiple-inventory-transactions-for-batch-numbers-when-on-physical-update-is-disabled"></a><span data-ttu-id="f4aad-103">Több készlettranzakció kötegszámokhoz, ha a Tényleges frissítéskor nincs engedélyezve</span><span class="sxs-lookup"><span data-stu-id="f4aad-103">Multiple inventory transactions for batch numbers when On physical update is disabled</span></span>

<span data-ttu-id="f4aad-104">Tudásbáziscikk száma: 4613390</span><span class="sxs-lookup"><span data-stu-id="f4aad-104">KB number: 4613390</span></span>

## <a name="symptoms"></a><span data-ttu-id="f4aad-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="f4aad-105">Symptoms</span></span>

<span data-ttu-id="f4aad-106">Több készlettranzakció jön létre, miután módosította a beszerzésirendelés-sort az olyan cikkekhez, amelyeknél a kötegszámcsoport **Tényleges frissítésekor** beállításának értéke *Nem*.</span><span class="sxs-lookup"><span data-stu-id="f4aad-106">Multiple inventory transactions are created after you adjust a purchase order line for items where the **On physical update** option of the batch number group is set to *No*.</span></span>

<span data-ttu-id="f4aad-107">Ha olyan cikket hoz létre, ahol a kötegszámcsoport **Tényleges frissítéskor** beállítási beállítása *Nem*, a rendszer automatikusan létrehoz egy új kötegszámot, ha módosítja egy beszerzési sor mennyiségét, és menti a beszerzési rendelés lapját.</span><span class="sxs-lookup"><span data-stu-id="f4aad-107">When you create an item where the **On physical update** option of the batch number group is set to *No*, the system automatically creates a new batch number if you modify a purchase line quantity and save the purchase order page.</span></span>

## <a name="resolution"></a><span data-ttu-id="f4aad-108">Felbontás</span><span class="sxs-lookup"><span data-stu-id="f4aad-108">Resolution</span></span>

<span data-ttu-id="f4aad-109">A kötegszámcsoportok **Tényleges frissítéskor** beállítása a következő módon működik:</span><span class="sxs-lookup"><span data-stu-id="f4aad-109">The **On physical update** setting for batch number groups works in the following way:</span></span>

- <span data-ttu-id="f4aad-110">Ha a beállítás *Igen*, az új kötegszámok csak a tényleges frissítés után (például a cikkek kiszállításakor vagy fogadásakor jönnek létre).</span><span class="sxs-lookup"><span data-stu-id="f4aad-110">When the option is set to *Yes*, new batch numbers are created only after a physical update (for example, when items are shipped or received).</span></span>
- <span data-ttu-id="f4aad-111">Ha a beállítás *Nem*, egy új kötegszám jön létre minden alkalommal, amikor egy vonatkozó frissítés történik (például amikor új mennyiséget adnak hozzá egy beszerzési rendeléshez).</span><span class="sxs-lookup"><span data-stu-id="f4aad-111">When the option is set to *No*, a new batch number is created every time that an applicable update occurs (for example, when a new quantity is added to a purchase order).</span></span>
