---
title: A program akkor is kéri, hogy mentse a cikkfedezeti beállításokat, ha nem hajtott végre módosításokat
description: A program akkor is kéri, hogy mentse a cikkfedezeti beállításokat, ha nem hajtott végre módosításokat.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: DataManagementWorkspace_
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: angarmas
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 3dfa974740420433af1e1b37630b22509510c91b
ms.sourcegitcommit: 3c15a26e9708adc9a75082dc551f0a3a0a7d89f4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049470"
---
# <a name="youre-prompted-to-save-item-coverage-settings-even-though-you-made-no-changes"></a><span data-ttu-id="468fe-103">A program akkor is kéri, hogy mentse a cikkfedezeti beállításokat, ha nem hajtott végre módosításokat</span><span class="sxs-lookup"><span data-stu-id="468fe-103">You're prompted to save item coverage settings even though you made no changes</span></span>

<span data-ttu-id="468fe-104">Tudásbáziscikk száma: 4615588</span><span class="sxs-lookup"><span data-stu-id="468fe-104">KB number: 4615588</span></span>

## <a name="symptoms"></a><span data-ttu-id="468fe-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="468fe-105">Symptoms</span></span>

<span data-ttu-id="468fe-106">Bizonyos helyzetekben előfordulhat, hogy a **Cikkfedezet** oldal megnyitásakor a következő üzenet jelenik meg, miután importálta a cikkeket a *Cikkfedezet V2* entitáson keresztül:</span><span class="sxs-lookup"><span data-stu-id="468fe-106">In some scenarios, you might receive the following message when you open the **Item coverage** page after you import items through the *Item coverage V2* entity:</span></span>

> <span data-ttu-id="468fe-107">Menti a módosításokat a bezárás előtt?</span><span class="sxs-lookup"><span data-stu-id="468fe-107">Do you want to save your changes before closing?</span></span>

<span data-ttu-id="468fe-108">Ez az üzenet akkor is megjelenik, ha nem hajtott végre módosításokat.</span><span class="sxs-lookup"><span data-stu-id="468fe-108">You receive this message even though you haven't made any changes.</span></span>

## <a name="resolution"></a><span data-ttu-id="468fe-109">Megoldás</span><span class="sxs-lookup"><span data-stu-id="468fe-109">Resolution</span></span>

<span data-ttu-id="468fe-110">A **Cikkfedezet** oldal olyan összetett alapértelmezési logikát használ, ami azt okozhatja, hogy az üzenet megjelenik az adatbázisban a közelmúltban végrehajtott közvetlen módosítások (például entitások importálása) után.</span><span class="sxs-lookup"><span data-stu-id="468fe-110">The **Item coverage** page includes complex defaulting logic that might cause the message to be shown after direct changes have recently been made in the database, such as through entity import.</span></span> <span data-ttu-id="468fe-111">Ha az `AREGENERALSETTINGSOVERRIDDEN` entitásmező értéke például *Nem*, de új vagy módosított értékeket adó fájlt importál a mezőkhöz (például `PRODUCTCOVERAGEGROUPID` és/vagy `VENDORACCOUNTNUMBER`).</span><span class="sxs-lookup"><span data-stu-id="468fe-111">For example, the `AREGENERALSETTINGSOVERRIDDEN` entity field is set to *No*, but you import a file that provides new or modified values for fields such as `PRODUCTCOVERAGEGROUPID` and/or `VENDORACCOUNTNUMBER`.</span></span> <span data-ttu-id="468fe-112">Mivel ebben az esetben az `AREGENERALSETTINGSOVERRIDDEN` mező értéke *Nem*, az értékek automatikusan törlődnek a **Cikkfedezet** oldal importálás utáni első megnyitásakor.</span><span class="sxs-lookup"><span data-stu-id="468fe-112">In this case, because the `AREGENERALSETTINGSOVERRIDDEN` field is set to *No*, the values are automatically cleared from the fields when you open the **Item coverage** page for the first time after the import.</span></span> <span data-ttu-id="468fe-113">Ha az üzenetmező megjelenésekor menti a módosításokat, azok az adatbázisban tárolódnak.</span><span class="sxs-lookup"><span data-stu-id="468fe-113">If you save the changes as the message box prompts, they are stored in the database.</span></span> <span data-ttu-id="468fe-114">Ellenkező esetben az oldal következő megnyitásakor ugyanez az üzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="468fe-114">Otherwise, you will receive the same message the next time that you open the page.</span></span>

<span data-ttu-id="468fe-115">Ha meg szeretné akadályozni ezt a viselkedést, de szerepeltetni szeretné az értékeket a mezőkhöz (például `PRODUCTCOVERAGEGROUPID`) az entitásimportáláson keresztül, akkor az importáláskor az `AREGENERALSETTINGSOVERRIDDEN` értékeként az *Igent* adja meg.</span><span class="sxs-lookup"><span data-stu-id="468fe-115">To prevent this behavior but also include values for fields such as `PRODUCTCOVERAGEGROUPID` through entity import, set `AREGENERALSETTINGSOVERRIDDEN` to *Yes* when you import.</span></span>
