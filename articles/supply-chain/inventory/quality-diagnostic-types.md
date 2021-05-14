---
title: A szabálytalanságok diagnosztikai típusai
description: Ez a témakör azt ismerteti, hogyan lehet a szabálytalanságokkal használható diagnosztikai típusokat használni és létrehozni.
author: rachel-profitt
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestDiagnosticType, InventTestCorrection
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 19fcd57e28efabd6ca32c444ab961b876bde424d
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956678"
---
# <a name="diagnostic-types-for-nonconformances"></a><span data-ttu-id="550d6-103">A szabálytalanságok diagnosztikai típusai</span><span class="sxs-lookup"><span data-stu-id="550d6-103">Diagnostic types for nonconformances</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="550d6-104">Ez a témakör azt ismerteti, hogyan lehet a szabálytalanságokkal használható diagnosztikai típusokat használni és létrehozni.</span><span class="sxs-lookup"><span data-stu-id="550d6-104">This topic describes how to use and create diagnostic types that can be used with nonconformances.</span></span>

<span data-ttu-id="550d6-105">A **Diagnosztikai típusok** oldal használatával határozhatja meg a diagnosztikai műveletek osztályozását.</span><span class="sxs-lookup"><span data-stu-id="550d6-105">You use the **Diagnostic types** page to define a classification of diagnostic actions.</span></span> <span data-ttu-id="550d6-106">Ezután a szabálytalanság korrekciójának létrehozásakor ki kell választani egy diagnosztikai vizsgálatot.</span><span class="sxs-lookup"><span data-stu-id="550d6-106">Then, when you create a correction for a nonconformance, you select a diagnostic.</span></span> <span data-ttu-id="550d6-107">A javítás meghatározza, hogy milyen típusú diagnosztikai műveletet kell végrehajtani a jóváhagyott szabálytalanságon, valamint hogy kinek kell elvégeznie.</span><span class="sxs-lookup"><span data-stu-id="550d6-107">A correction specifies what type of diagnostic action should be taken for an approved nonconformance, and who should take that action.</span></span> <span data-ttu-id="550d6-108">Azt is meghatározza, melyik napra kérték és mikorra tervezik a végrehajtást.</span><span class="sxs-lookup"><span data-stu-id="550d6-108">It also specifies the requested completion date and the planned completion date.</span></span>

## <a name="examples-of-diagnostic-types"></a><span data-ttu-id="550d6-109">Néhány példa a diagnosztikai típusokra</span><span class="sxs-lookup"><span data-stu-id="550d6-109">Examples of diagnostic types</span></span>

<span data-ttu-id="550d6-110">Egy gyártó cégnél dolgozik, és több cikknél nem sikerült a minőségi teszt.</span><span class="sxs-lookup"><span data-stu-id="550d6-110">You work for a manufacturing company, and several items have failed quality tests.</span></span> <span data-ttu-id="550d6-111">Ezeket a cikkeket karanténterületre helyezik át, és nem megfelelő termékként jelölik meg.</span><span class="sxs-lookup"><span data-stu-id="550d6-111">Those items are moved into a quarantine area and marked as nonconforming products.</span></span> <span data-ttu-id="550d6-112">Szabálytalanságrekordot hoz létre a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban, hogy a probléma megoldása közben nyomon kövesse a részleteket.</span><span class="sxs-lookup"><span data-stu-id="550d6-112">A nonconformance record is created in Microsoft Dynamics 365 Supply Chain Management to track the details through issue resolution.</span></span>

<span data-ttu-id="550d6-113">Ebben az esetben a minőségbiztosítási problémák azért fordulnak elő, mert a csomagológépben található olyan csapágyak elromlottak és túlmelegedtek.</span><span class="sxs-lookup"><span data-stu-id="550d6-113">In this case, the quality issues are occurring because bearings in the machine that packages the items have gone bad and are overheating.</span></span> <span data-ttu-id="550d6-114">A problémát úgy tudják megszűntetni, ha kicserélik az alkatrészt.</span><span class="sxs-lookup"><span data-stu-id="550d6-114">The correction for this problem is to replace the parts in the machine.</span></span>

<span data-ttu-id="550d6-115">A diagnosztikai típusok konfigurálása során több rekordot is létre lehet hozni, amelyek a gép számára eltérő típusú problémát képviselnek.</span><span class="sxs-lookup"><span data-stu-id="550d6-115">When you configure the diagnostic types, you can create multiple records, each of which represents a different type of problem that the machine might have.</span></span> <span data-ttu-id="550d6-116">Másik lehetőségként létrehozhat egy általános diagnosztikai típust, amely a gép javítását jelzi.</span><span class="sxs-lookup"><span data-stu-id="550d6-116">Alternatively, you can create one generic diagnostic type that represents machine repair.</span></span>

## <a name="create-a-diagnostic-type"></a><span data-ttu-id="550d6-117">Diagnosztikai típus létrehozása</span><span class="sxs-lookup"><span data-stu-id="550d6-117">Create a diagnostic type</span></span>

1. <span data-ttu-id="550d6-118">Ugorjon a **Készletgazdálkodás \> Beállítás \> Minőségkezelés \> Diagnosztikai típusok** pontra.</span><span class="sxs-lookup"><span data-stu-id="550d6-118">Go to **Inventory management \> Setup \> Quality management \> Diagnostic types**.</span></span>
1. <span data-ttu-id="550d6-119">A műveleti ablakpanelen válassza ki az **Új** lehetőséget, ha hozzá szeretne adni egy sort a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="550d6-119">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="550d6-120">Ezután új sorhoz állítsa be a következő mezőket:</span><span class="sxs-lookup"><span data-stu-id="550d6-120">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="550d6-121">**Diagnosztika** – A diagnosztikai típus egyedi azonosítójának vagy nevének megadása.</span><span class="sxs-lookup"><span data-stu-id="550d6-121">**Diagnostic** – Enter a unique ID or name for the diagnostic type.</span></span>
    - <span data-ttu-id="550d6-122">**Leírás** – Adja meg a diagnosztikai típus részletes leírását.</span><span class="sxs-lookup"><span data-stu-id="550d6-122">**Description** – Enter a detailed description of the diagnostic type.</span></span>

1. <span data-ttu-id="550d6-123">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="550d6-123">Close the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="550d6-124">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="550d6-124">Additional resources</span></span>

- [<span data-ttu-id="550d6-125">Minőségkezelés áttekintése</span><span class="sxs-lookup"><span data-stu-id="550d6-125">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="550d6-126">A minőség- és a szabálytalanságkezelés engedélyezése</span><span class="sxs-lookup"><span data-stu-id="550d6-126">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="550d6-127">A szabálytalanságok jóváhagyásáért felelős dolgozók</span><span class="sxs-lookup"><span data-stu-id="550d6-127">Workers responsible for approving nonconformances</span></span>](quality-responsible-workers.md)
- [<span data-ttu-id="550d6-128">A szabálytalanságok karanténzónái</span><span class="sxs-lookup"><span data-stu-id="550d6-128">Quarantine zones for nonconformances</span></span>](quality-quarantine-zones.md)
- [<span data-ttu-id="550d6-129">A szabálytalanságok problématípusai</span><span class="sxs-lookup"><span data-stu-id="550d6-129">Problem types for nonconformances</span></span>](quality-problem-types.md)
- [<span data-ttu-id="550d6-130">Szabálytalanságok minőségi költségei</span><span class="sxs-lookup"><span data-stu-id="550d6-130">Quality charges for nonconformances</span></span>](quality-charges.md)
- [<span data-ttu-id="550d6-131">Műveletek szabálytalanságokhoz kapcsolódóan</span><span class="sxs-lookup"><span data-stu-id="550d6-131">Operations for nonconformances</span></span>](quality-operations.md)
- [<span data-ttu-id="550d6-132">Raktári folyamatok minőségkezelése</span><span class="sxs-lookup"><span data-stu-id="550d6-132">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
