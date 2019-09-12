---
title: Munkarendelés típusai
description: Ez a témakör a munkarendelés-típusokat mutatja be az Eszközkezelésben.
author: josaw1
manager: AnnBe
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 57120b51c069e49697f8ec4357265974a0d3afb4
ms.sourcegitcommit: 802dbf0a744d70f9e546632d419415b0993331ab
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/13/2019
ms.locfileid: "1874578"
---
# <a name="work-order-types"></a><span data-ttu-id="b0b04-103">Munkarendelés típusai</span><span class="sxs-lookup"><span data-stu-id="b0b04-103">Work order types</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="b0b04-104">A munkarendelés-típusok a munkarendelések kategorizálására szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="b0b04-104">Work order types are used to categorize work orders.</span></span> <span data-ttu-id="b0b04-105">A munkarendelések kapcsolódhatnak például megelőző karbantartáshoz vagy hibaelhárító karbantartáshoz.</span><span class="sxs-lookup"><span data-stu-id="b0b04-105">For example, you might have work orders that are related to preventive maintenance or corrective maintenance.</span></span>

<span data-ttu-id="b0b04-106">A munkarendelés-típus határozza meg egy munkarendelés életciklusmodelljéhez fűződő kapcsolatot.</span><span class="sxs-lookup"><span data-stu-id="b0b04-106">A work order type defines an affiliation with a work order lifecycle model.</span></span> <span data-ttu-id="b0b04-107">A munkarendelés életciklusmodellje határozza meg a munkarendelésen beállítható munkarendelés életciklus-állapotát.</span><span class="sxs-lookup"><span data-stu-id="b0b04-107">A work order lifecycle model defines the work order lifecycle states that can be set on a work order.</span></span> <span data-ttu-id="b0b04-108">(A munkarendelés életciklus-állapota lehet például: **Létrehozva**, **Folyamatban** és **Befejezve**.)</span><span class="sxs-lookup"><span data-stu-id="b0b04-108">(Examples of work order lifecycle states include **Created**, **In Process**, and **Finished**.)</span></span>

<span data-ttu-id="b0b04-109">A munkarendelés életciklus-állapotaival és projektfázisaival kapcsolatos további információért lásd: [Munkarendelés életciklus-állapotai](work-order-lifecycle-states.md).</span><span class="sxs-lookup"><span data-stu-id="b0b04-109">For more information about work order lifecycle states and project stages, see [Work order lifecycle states](work-order-lifecycle-states.md).</span></span>

1. <span data-ttu-id="b0b04-110">Válassza ki az **Eszközkezelés** \> **Beállítás** \> **Munkarendelések** \> **Munkarendelés-típusai** elemet.</span><span class="sxs-lookup"><span data-stu-id="b0b04-110">Select **Asset management** \> **Setup** \> **Work orders** \> **Work order types**.</span></span>
2. <span data-ttu-id="b0b04-111">Válassza az **Új** lehetőséget egy új munkarendelés-típus létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="b0b04-111">Select **New** to create a work order type.</span></span>
3. <span data-ttu-id="b0b04-112">A **Munkarendelés-típus** mezőben adja meg a munkarendelés típusának azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="b0b04-112">In the **Work order type** field, enter an ID for the work order type.</span></span>
4. <span data-ttu-id="b0b04-113">A **Név** mezőben adjon meg egy nevet.</span><span class="sxs-lookup"><span data-stu-id="b0b04-113">In the **Name** field, enter a name.</span></span>
5. <span data-ttu-id="b0b04-114">Válasszon ki egy életciklusmodellt a **Munkarendelés életciklusmodellje** mezőben.</span><span class="sxs-lookup"><span data-stu-id="b0b04-114">In the **Work order lifecycle model** field, select a lifecycle model.</span></span>
5. <span data-ttu-id="b0b04-115">Állítsa az **Egy karbantartási dolgozó** beállítást **Igen** értékre, ha az adott típusú munkarendeléshez kapcsolódó összes munkarendelési feladatot ugyanahhoz a karbantartási dolgozóhoz kell ütemezni.</span><span class="sxs-lookup"><span data-stu-id="b0b04-115">Set the **One maintenance worker** option to **Yes** if all work order jobs that are related to a work order of this type should be scheduled to the same maintenance worker.</span></span>
6. <span data-ttu-id="b0b04-116">A **Költségtípus** mezőben válassza ki a megfelelőt: **Helyesbítő**, **Megelőző** vagy **Befektetés**.</span><span class="sxs-lookup"><span data-stu-id="b0b04-116">In the **Cost type** field, select **Corrective**, **Preventive**, or **Investment**, as appropriate.</span></span> <span data-ttu-id="b0b04-117">A munkarendelésen szereplő összes munkarendelési feladatnak ugyanolyan költségtípusúnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="b0b04-117">All work order jobs on a work order must have the same cost type.</span></span>
7. <span data-ttu-id="b0b04-118">A **Kötelező** szakaszban állítsa a megfelelő beállításokat **Igen** értékre, amellyel megadhatja, hogy az ilyen típusú munkarendeléshez milyen, a hibával vagy karbantartás miatti üzemkimaradással kapcsolatos információt adjon hozzá a rendszer.</span><span class="sxs-lookup"><span data-stu-id="b0b04-118">In the **Mandatory** section, set the relevant options to **Yes** to specify which fault-related or maintenance downtime–related information is added to a work order of this type.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b0b04-119">A **Kötelező** szakasz beállításai a **Munkarendelés életciklus-állapotai** oldal **Ellenőrzés** gyorslapján található beállításokhoz kapcsolódnak (**Eszközkezelés** \> **Beállítás** \> **Munkarendelések** \> **Életciklus-állapotok**).</span><span class="sxs-lookup"><span data-stu-id="b0b04-119">The options in the **Mandatory** section are related to the options on the **Validate** FastTab of the **Work order lifecycle states** page (**Asset management** \> **Setup** \> **Work orders** \> **Lifecycle states**).</span></span>

8. <span data-ttu-id="b0b04-120">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b0b04-120">Select **Save**.</span></span>

![1. ábra](media/16-setup-for-work-orders.png)
