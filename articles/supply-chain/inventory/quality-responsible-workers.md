---
title: A szabálytalanságok jóváhagyásáért felelős dolgozók
description: Ez a témakör leírja, hogyan kell konfigurálni a szabálytalanságok jóváhagyásáért felelős dolgozókat.
author: rachel-profitt
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5979cb33146a00c3ea49ada9577140b24c07928f
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956687"
---
# <a name="workers-responsible-for-approving-nonconformances"></a><span data-ttu-id="d2e84-103">A szabálytalanságok jóváhagyásáért felelős dolgozók</span><span class="sxs-lookup"><span data-stu-id="d2e84-103">Workers responsible for approving nonconformances</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d2e84-104">Ez a témakör leírja, hogyan kell konfigurálni a szabálytalanságok jóváhagyásáért felelős dolgozókat.</span><span class="sxs-lookup"><span data-stu-id="d2e84-104">This topic describes how to configure workers that are responsible for approving nonconformances.</span></span>

<span data-ttu-id="d2e84-105">A szabálytalanságokat jóvá kell hagyni, mielőtt a felhasználók elkezdhetnék megadni a részleteket, például a javításokat vagy a műveleteket.</span><span class="sxs-lookup"><span data-stu-id="d2e84-105">Nonconformances must be approved before users can start to enter details such as corrections or operations.</span></span> <span data-ttu-id="d2e84-106">Ahhoz, hogy a felhasználók jóváhagyhassák vagy elutasíthassák a szabálytalanságokat, a felhasználói azonosítójukat (felhasználói rekordjukat) hozzá kell kapcsolni egy dolgozói rekordhoz.</span><span class="sxs-lookup"><span data-stu-id="d2e84-106">Before users can approve or reject nonconformances, their user ID (user record) must be linked to a worker record.</span></span> <span data-ttu-id="d2e84-107">A minőségért felelős dolgozókat opcionálisan beállíthatja, majd egy dolgozó számára engedélyezheti, hogy egy másik dolgozó nevében jóváhagyja a munkát.</span><span class="sxs-lookup"><span data-stu-id="d2e84-107">You can optionally configure workers that are responsible for quality and then allow one worker to approve work on behalf of another worker.</span></span>

## <a name="enable-a-user-for-nonconformance-processing"></a><span data-ttu-id="d2e84-108">Engedélyezzen a szabálytalanságok feldolgozására egy felhasználót</span><span class="sxs-lookup"><span data-stu-id="d2e84-108">Enable a user for nonconformance processing</span></span>

<span data-ttu-id="d2e84-109">Ahhoz, hogy egy falhasználó jóváhagyhasson vagy elutasíthasson a szabálytalanságokat, a felhasználói azonosítóját (felhasználói rekordját) hozzá kell kapcsolni egy dolgozói rekordhoz.</span><span class="sxs-lookup"><span data-stu-id="d2e84-109">Before a user can approve or reject nonconformances, you must link their user record to a worker record.</span></span> <span data-ttu-id="d2e84-110">Ezt követően automatikusan be lehet állítani a jóváhagyási mezőket, és az aktuális felhasználó automatikusan kitölthető az időnyilvántartáshoz.</span><span class="sxs-lookup"><span data-stu-id="d2e84-110">The approval fields can then be automatically set, and the current user can be automatically filled in for the timesheet.</span></span> <span data-ttu-id="d2e84-111">Mielőtt a felhasználó használhatná a dokumentummegjegyzéseket, aktiválnia kell a dokumentumkezelése a felhasználói beállításaiban.</span><span class="sxs-lookup"><span data-stu-id="d2e84-111">Before the user can use the document notes, you must activate document handling in their user options.</span></span>

1. <span data-ttu-id="d2e84-112">Ugrás a **Rendszerfelügyelet \> Felhasználók \> Felhasználók** elemre.</span><span class="sxs-lookup"><span data-stu-id="d2e84-112">Go to **System administration \> Users \> Users**.</span></span>
1. <span data-ttu-id="d2e84-113">Keresse meg és nyissa meg azt a felhasználót, akinek képesnek kell lennie szabálytalanságok jóváhagyására vagy elutasítására.</span><span class="sxs-lookup"><span data-stu-id="d2e84-113">Find and open the user who should be able to approve or reject nonconformances.</span></span>
1. <span data-ttu-id="d2e84-114">A **Személy** mezőt állítsa be az aktuális felhasználói rekordhoz kapcsolódó dolgozó nevére.</span><span class="sxs-lookup"><span data-stu-id="d2e84-114">Set the **Person** field to the name of the worker that is related to the current user record.</span></span>
1. <span data-ttu-id="d2e84-115">A műveleti ablaktáblán válassza ki a **Felhasználói beállítások** elemet.</span><span class="sxs-lookup"><span data-stu-id="d2e84-115">On the Action Pane, select **User options**.</span></span>
1. <span data-ttu-id="d2e84-116">Az aktuális felhasználói rekord **Beállítások** lapján, a **Beállítások** lapon állítsa a **Dokumentumkezelés engedélyezése** lehetőséget *Igen* beállításra.</span><span class="sxs-lookup"><span data-stu-id="d2e84-116">On the **Options** page for the current user record, on the **Preferences** tab, set the **Enable document handling** option to *Yes*.</span></span>
1. <span data-ttu-id="d2e84-117">Zárja be a lapokat.</span><span class="sxs-lookup"><span data-stu-id="d2e84-117">Close the pages.</span></span>

## <a name="define-workers-that-are-responsible-for-quality"></a><span data-ttu-id="d2e84-118">Határozza meg a minőségért felelős dolgozókat</span><span class="sxs-lookup"><span data-stu-id="d2e84-118">Define workers that are responsible for quality</span></span>

1. <span data-ttu-id="d2e84-119">Ugorjon a következőhöz: **Készletkezelés \> Beállítás \> Minőség-ellenőrzés \> Minőségért felelős dolgozók**.</span><span class="sxs-lookup"><span data-stu-id="d2e84-119">Go to **Inventory management \> Setup \> Quality control \> Workers responsible for quality**.</span></span>
2. <span data-ttu-id="d2e84-120">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="d2e84-120">On the Action Pane, select **New**.</span></span>
3. <span data-ttu-id="d2e84-121">A **Dolgozó** mezőben válassza ki azt a dolgozót, aki a minőségi adatokat megadja.</span><span class="sxs-lookup"><span data-stu-id="d2e84-121">In the **Worker** field, select the worker that enters quality data.</span></span>
4. <span data-ttu-id="d2e84-122">A **Felelős dolgozó** mezőben válassza ki azt a dolgozót, aki helyett a kiválasztott dolgozó munkát ad meg.</span><span class="sxs-lookup"><span data-stu-id="d2e84-122">In the **Worker responsible** field, select the worker that the selected worker enters work on behalf of.</span></span> <span data-ttu-id="d2e84-123">A szabálytalanságok létrehozásakor és frissítésekor a dolgozó alapértelmezés szerint meg lesz adva a **Dolgozó** mezőkben.</span><span class="sxs-lookup"><span data-stu-id="d2e84-123">When nonconformances are created and updated, this worker will be entered by default in **Worker** fields.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d2e84-124">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="d2e84-124">Additional resources</span></span>

- [<span data-ttu-id="d2e84-125">Minőségkezelés áttekintése</span><span class="sxs-lookup"><span data-stu-id="d2e84-125">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="d2e84-126">A minőség- és a szabálytalanságkezelés engedélyezése</span><span class="sxs-lookup"><span data-stu-id="d2e84-126">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="d2e84-127">Minőségbiztosítási költségek</span><span class="sxs-lookup"><span data-stu-id="d2e84-127">Quality charges</span></span>](quality-charges.md)
- [<span data-ttu-id="d2e84-128">A szabálytalanságok karanténzónái</span><span class="sxs-lookup"><span data-stu-id="d2e84-128">Quarantine zones for nonconformances</span></span>](quality-quarantine-zones.md)
- [<span data-ttu-id="d2e84-129">A szabálytalanságok diagnosztikai típusai</span><span class="sxs-lookup"><span data-stu-id="d2e84-129">Diagnostic types for nonconformances</span></span>](quality-diagnostic-types.md)
- [<span data-ttu-id="d2e84-130">Szabálytalanságok minőségi költségei</span><span class="sxs-lookup"><span data-stu-id="d2e84-130">Quality charges for nonconformances</span></span>](quality-charges.md)
- [<span data-ttu-id="d2e84-131">Műveletek szabálytalanságokhoz kapcsolódóan</span><span class="sxs-lookup"><span data-stu-id="d2e84-131">Operations for nonconformances</span></span>](quality-operations.md)
- [<span data-ttu-id="d2e84-132">Raktári folyamatok minőségkezelése</span><span class="sxs-lookup"><span data-stu-id="d2e84-132">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
