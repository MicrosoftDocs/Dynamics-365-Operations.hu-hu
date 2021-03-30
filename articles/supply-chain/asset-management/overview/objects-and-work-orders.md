---
title: Eszközök és munkarendelések
description: Ez a témakör bemutatja az eszközöket és munkarendeléseket az Eszközkezelés modulban.
author: josaw1
manager: tfehr
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6fd5aa8914437fb77ea25ec229c94cfb0bb12def
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5253062"
---
# <a name="assets-and-work-orders"></a><span data-ttu-id="ba5a2-103">Eszközök és munkarendelések</span><span class="sxs-lookup"><span data-stu-id="ba5a2-103">Assets and work orders</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="ba5a2-104">Ez a témakör bemutatja az eszközöket és munkarendeléseket az Eszközkezelés modulban.</span><span class="sxs-lookup"><span data-stu-id="ba5a2-104">This topic describes assets and work orders in Asset Management.</span></span> <span data-ttu-id="ba5a2-105">Az eszközök és a munkarendelések az Eszközkezelés központi részei.</span><span class="sxs-lookup"><span data-stu-id="ba5a2-105">Assets and work orders are the central parts of Asset Management.</span></span> <span data-ttu-id="ba5a2-106">Az *eszköz* olyan gép vagy gépalkatrész, amely folyamatos karbantartást és szervizt igényel.</span><span class="sxs-lookup"><span data-stu-id="ba5a2-106">An *asset* is a machine or machine part that requires continuous maintenance and service.</span></span> <span data-ttu-id="ba5a2-107">Az eszközöket hierarchikus szerkezetben lehet létrehozni, és a munkavégzési helyszínekhez kapcsolódhatnak.</span><span class="sxs-lookup"><span data-stu-id="ba5a2-107">Assets can be created in a hierarchical structure, and they can be related to functional locations.</span></span> <span data-ttu-id="ba5a2-108">A karbantartási munkákat az eszközstruktúra minden szintjéhez lehet tervezni.</span><span class="sxs-lookup"><span data-stu-id="ba5a2-108">Maintenance jobs can be planned at all levels in the asset structure.</span></span>

<span data-ttu-id="ba5a2-109">Különböző adatok, például termékadatok és eszközspecifikációk, valamint a szükséges karbantartási tervek vannak beállítva az egyes eszközökhöz.</span><span class="sxs-lookup"><span data-stu-id="ba5a2-109">Various data, such as product information and asset specification, and required maintenance plans are set up on each asset.</span></span> <span data-ttu-id="ba5a2-110">A következő ábrán az eszközadatok áttekintése és az eszközök feladattípusokhoz való viszonya látható.</span><span class="sxs-lookup"><span data-stu-id="ba5a2-110">The following illustration shows an overview of asset data and the affiliation of assets to job types.</span></span> <span data-ttu-id="ba5a2-111">Az öröklést és a függőségeket mutató példák vörös betűkkel jelzettek.</span><span class="sxs-lookup"><span data-stu-id="ba5a2-111">Red text is used for examples that show inheritance and dependencies.</span></span>

![A feladattípusokkal kapcsolatos eszközadatokat megjelenítő ábra](media/05-overview-image.png)

<span data-ttu-id="ba5a2-113">Minden munkrendeléshez tartozik egy munkarendelés-típus, például megelőző karbantartás, javító karbantartás vagy vizsgálat.</span><span class="sxs-lookup"><span data-stu-id="ba5a2-113">Every work order has a work order type, such preventive maintenance, corrective maintenance, or inspection.</span></span> <span data-ttu-id="ba5a2-114">A munkarendelés egy vagy több munkarendelési feladatot tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="ba5a2-114">The work order contains one or more work order jobs.</span></span> <span data-ttu-id="ba5a2-115">Minden munkrendelési feladat meghatároz egy feladatot, amelyet el kell végezni egy eszközön és egy kapcsolódó feladattípuson.</span><span class="sxs-lookup"><span data-stu-id="ba5a2-115">Every work order job defines a job that must be performed on an asset and a related job type.</span></span> <span data-ttu-id="ba5a2-116">A kapcsolódó feladattípusok lehetnek például 10 000 km, 50 000 km, éves nagyjavítás és biztonsági ellenőrzés.</span><span class="sxs-lookup"><span data-stu-id="ba5a2-116">Examples of related job types include 10,000 km, 50,000 km, 1-year overhaul, and safety inspection.</span></span> <span data-ttu-id="ba5a2-117">Egy munkarendelés több eszközhöz is tartozhat.</span><span class="sxs-lookup"><span data-stu-id="ba5a2-117">One work order can be related to multiple assets.</span></span>

<span data-ttu-id="ba5a2-118">A következő ábrán egy munkarendelés legfontosabb adatainak áttekintése látható.</span><span class="sxs-lookup"><span data-stu-id="ba5a2-118">The following illustration shows an overview of the key data in a work order.</span></span>

![A munkarendelésen szereplő kulcsfontosságú adatokat megjelenítő ábra](media/06-overview-image.png)

<span data-ttu-id="ba5a2-120">Egy munkarendelés kapcsolódhat másik munkarendeléshez, a feladattípusok pedig tartalmazhatnak követőfeladatokat, amelyek munkarendelést hoznak létre.</span><span class="sxs-lookup"><span data-stu-id="ba5a2-120">A work order can be related to another work order, and job types can contain succeeding jobs that create a work order.</span></span> <span data-ttu-id="ba5a2-121">Általában nincsenek függőségek a munkarendelések között.</span><span class="sxs-lookup"><span data-stu-id="ba5a2-121">In general, there are no dependencies between work orders.</span></span> <span data-ttu-id="ba5a2-122">Így megváltoztathatók a munkarendelések életciklus-állapota, és egymástól függetlenül ütemezhetők.</span><span class="sxs-lookup"><span data-stu-id="ba5a2-122">Therefore, they can change their work order lifecycle state and can be scheduled independently of each other.</span></span>

<span data-ttu-id="ba5a2-123">A munkarendeléseket többféle módon lehet létrehozni a javító, megelőző vagy reaktív karbantartással kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="ba5a2-123">Work orders can be created in various ways that are related to corrective, preventive, or reactive maintenance.</span></span> <span data-ttu-id="ba5a2-124">A munkarendelések manuálisan is létrehozhatók.</span><span class="sxs-lookup"><span data-stu-id="ba5a2-124">You can also create work orders manually.</span></span> <span data-ttu-id="ba5a2-125">A következő ábrán a munkarendelések automatikus vagy manuális létrehozására vonatkozó folyamat áttekintése látható.</span><span class="sxs-lookup"><span data-stu-id="ba5a2-125">The following illustration shows an overview of the process for automatic or manual creation of work orders.</span></span>

![Munkarendelések automatikus vagy manuális létrehozását megjelenítő ábra](media/07-overview-image.png)

<span data-ttu-id="ba5a2-127">Több lépést is el kell végezni egy karbantartási feladat munkarendelésen való ütemezéséhez és futtatásához.</span><span class="sxs-lookup"><span data-stu-id="ba5a2-127">Several steps must be completed when you want to schedule and run a maintenance job on a work order.</span></span> <span data-ttu-id="ba5a2-128">A következő ábrán egy munkarendeléshez tartozó feldolgozás áttekintése látható.</span><span class="sxs-lookup"><span data-stu-id="ba5a2-128">The following illustration shows an overview of the processing for a work order.</span></span>

![A munkarendelés feldolgozásának áttekintését bemutató ábra](media/08-overview-image.png)

> [!NOTE]
> <span data-ttu-id="ba5a2-130">Általánosságban a Dynamics 365 Supply Chain Management szolgáltatással és az **Eszközkezelés** modullal történő munkavégzés során válassza az **Új** lehetőséget új rekord létrehozásához, a **Szerkesztés** lehetőséget a meglévő rekord frissítéséhez, és a **Mentés** lehetőséget az új vagy szerkesztett adatok elmentéséhez.</span><span class="sxs-lookup"><span data-stu-id="ba5a2-130">In general, when you work in Dynamics 365 Supply Chain Management and the **Asset Management** module, you select **New** to create a new record, you select **Edit** to update an existing record, and you select **Save** to save new or edited data.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]