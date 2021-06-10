---
title: Az alaptervezés cikkei nem szűrhetők a kapcsolódó fedezetcsoport értékei alapján
description: Az alaptervezés cikkei nem szűrhetők a kapcsolódó fedezetcsoport értékei alapján.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ilebedev
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: fa0b614b6710c65811add8725a0e255ce2c34b88
ms.sourcegitcommit: 3c15a26e9708adc9a75082dc551f0a3a0a7d89f4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049471"
---
# <a name="you-cant-filter-master-planning-items-by-their-related-coverage-group-values"></a><span data-ttu-id="996e3-103">Az alaptervezés cikkei nem szűrhetők a kapcsolódó fedezetcsoport értékei alapján</span><span class="sxs-lookup"><span data-stu-id="996e3-103">You can't filter master planning items by their related coverage group values</span></span>

<span data-ttu-id="996e3-104">Tudásbáziscikk száma: 4612572</span><span class="sxs-lookup"><span data-stu-id="996e3-104">KB number: 4612572</span></span>

## <a name="symptoms"></a><span data-ttu-id="996e3-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="996e3-105">Symptoms</span></span>

<span data-ttu-id="996e3-106">Az alaptervezés kötegelt feladatában szereplő cikkeket a cikkfedezeti tábla kapcsolódó rekordjainak értékei alapján szeretné szűrni.</span><span class="sxs-lookup"><span data-stu-id="996e3-106">You want to filter the items that will be included in a master planning batch job, based on the values of related records from the item coverage table.</span></span> <span data-ttu-id="996e3-107">(A cikkeket például a **Szállító** és/vagy a **Fedezeti csoport** értéke alapján lehet érdemes szűrni).</span><span class="sxs-lookup"><span data-stu-id="996e3-107">(For example, you want to filter items by their **Vendor** and/or **Coverage group** value).</span></span> <span data-ttu-id="996e3-108">A kötegelt feladat szűrőbeállítása lehetővé teszi, hogy összekapcsolást hozzon létre a **Cikkek** táblából a **Cikkfedezet** táblába, majd megadja a lekérdezésben lévő cikkfedezeti táblából származó mezőértékeket.</span><span class="sxs-lookup"><span data-stu-id="996e3-108">The filter setup for the batch job lets you create a join from the **Items** table to the **Item coverage** table, and then specify field values from the item coverage table in your query.</span></span> <span data-ttu-id="996e3-109">A beállítás befejezése után azonban a rendszer továbbra is a teljes cikkfedezethez hoz létre tervezett rendeléseket, nem csak a cikkfedezeti táblából származó magadott mezőértékeknek megfelelő cikkekhez.</span><span class="sxs-lookup"><span data-stu-id="996e3-109">However, after you complete this setup, the system still creates planned orders for the whole item coverage, not just for the items that match the specified field values from the item coverage table.</span></span>

## <a name="resolution"></a><span data-ttu-id="996e3-110">Megoldás</span><span class="sxs-lookup"><span data-stu-id="996e3-110">Resolution</span></span>

<span data-ttu-id="996e3-111">A kötegelt feladatok szűrője csak cikkekre tud szűrést végezni.</span><span class="sxs-lookup"><span data-stu-id="996e3-111">The batch job filter can filter only on items.</span></span> <span data-ttu-id="996e3-112">Bár lehet összekapcsolást hozzáadni a **Cikkfedezet** táblához, az adott táblánál megadott szűrőbeállítások nincsenek hatással a lekérdezés kimenetére.</span><span class="sxs-lookup"><span data-stu-id="996e3-112">Although you can add a join to the **Item coverage** table, filter settings that you make against that table won't affect the query output.</span></span> <span data-ttu-id="996e3-113">Futásidőben a rendszer minden fedezeti csoporthoz és a szűrt cikkek összes változatához futtat tervezést.</span><span class="sxs-lookup"><span data-stu-id="996e3-113">At runtime, the system runs planning for all the coverage groups and all the variations that the filtered items have.</span></span> <span data-ttu-id="996e3-114">Ha egy cikk már szerepel a futtatásban, a cikkszűrőben szereplő fedezeti csoportok nincsenek hatással a tervezés kimenetére.</span><span class="sxs-lookup"><span data-stu-id="996e3-114">After an item is already included in the run, any coverage groups that are included in the item filter a won't affect the planning output.</span></span>
