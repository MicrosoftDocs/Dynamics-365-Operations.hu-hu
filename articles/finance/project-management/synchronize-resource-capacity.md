---
title: Erőforrás-kapacitás szinkronizálása
description: Ez a témakör azt mutatja be, hogyan lehet szinkronizálni az erőforrás kapacitását a naptárak és a projektek között.
author: Yowelle
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 27b6fde91a72e37bb2712daba765032322cbd4e9
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760562"
---
# <a name="synchronize-resource-capacity"></a><span data-ttu-id="94d4b-103">Erőforrás-kapacitás szinkronizálása</span><span class="sxs-lookup"><span data-stu-id="94d4b-103">Synchronize resource capacity</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="94d4b-104">Az erőforrás-szinkronizálási folyamatok segítségével garantálható, hogy a naptár- és alapnaptáradatok a projekterőforrás-ütemezéssel összhangba kerülnek.</span><span class="sxs-lookup"><span data-stu-id="94d4b-104">The processes for resource synchronization help guarantee that information for the calendar and base calendar trickles down into project resource scheduling.</span></span> <span data-ttu-id="94d4b-105">Ha a naptár módosult, a folyamatok elvégzik a szükséges frissítéseket a projekterőforrások ütemezéséhez.</span><span class="sxs-lookup"><span data-stu-id="94d4b-105">If the calendar is changed, the processes make the required updates to the scheduling of project resources.</span></span> <span data-ttu-id="94d4b-106">A folyamatok a teljesítmény javításában is segítenek, mivel a naptár-erőforrásadatok szinkronizálása előre megtörténik.</span><span class="sxs-lookup"><span data-stu-id="94d4b-106">The processes also help improve performance, because the calendar's resource information is synchronized in advance.</span></span> <span data-ttu-id="94d4b-107">Ezért az erőforrás-ütemezési információk módosításai gyorsabban megtörténnek.</span><span class="sxs-lookup"><span data-stu-id="94d4b-107">Therefore, updates to resource scheduling information occur more quickly.</span></span> <span data-ttu-id="94d4b-108">Javasoljuk, hogy ne egyesével, hanem kötegként ütemezze a folyamatokat.</span><span class="sxs-lookup"><span data-stu-id="94d4b-108">We recommend that you schedule the processes as a batch instead of one at a time.</span></span> <span data-ttu-id="94d4b-109">Ellenkező esetben fennáll a kockázata annak, hogy valaki elfelejti az utolsó adatszinkronizálás inkluzív időpontját.</span><span class="sxs-lookup"><span data-stu-id="94d4b-109">Otherwise, there is a risk that someone will forget the inclusive dates when the information was last synchronized.</span></span> <span data-ttu-id="94d4b-110">Ha az inkluzív időpontokat nem használták, szünetek fordulhatnak elő a dátumszinkronizálás során.</span><span class="sxs-lookup"><span data-stu-id="94d4b-110">If inclusive dates aren't used, gaps can occur during date synchronization.</span></span>

![Naptár szinkronizálása](./media/projectresourcing04-1024x471.jpg)

## <a name="synchronize-resource-capacity-roll-ups"></a><span data-ttu-id="94d4b-112">Erőforrás kapacitás-összesítéseinek szinkronizálása</span><span class="sxs-lookup"><span data-stu-id="94d4b-112">Synchronize resource capacity roll-ups</span></span>

<span data-ttu-id="94d4b-113">A szinkronizálási folyamat arra szolgál, hogy az összes naptári erőforrásadatot szinkronizálja.</span><span class="sxs-lookup"><span data-stu-id="94d4b-113">The synchronization process is designed to synchronize all resource calendar information.</span></span> <span data-ttu-id="94d4b-114">Ez az információ alapnaptár adatokat tartalmaz a projekt Erőforrásnaptár kapacitás tábláját ért bármely módosításról.</span><span class="sxs-lookup"><span data-stu-id="94d4b-114">This information includes base calendar information about any changes to the project's Resource calendar capacity table.</span></span> <span data-ttu-id="94d4b-115">Ha új erőforrások kerülnek a projekthez, a szinkronizálás biztosítja a frissített naptáradatok elérhetőségét.</span><span class="sxs-lookup"><span data-stu-id="94d4b-115">If new resources are added in the project, synchronization helps guarantee that the updated calendar information is available.</span></span> <span data-ttu-id="94d4b-116">Ez a szinkronizálás bármikor megtehető.</span><span class="sxs-lookup"><span data-stu-id="94d4b-116">This synchronization can be done at any time.</span></span>

<span data-ttu-id="94d4b-117">Köteg használatát javasoljuk.</span><span class="sxs-lookup"><span data-stu-id="94d4b-117">We recommend that you use a batch.</span></span> <span data-ttu-id="94d4b-118">A beállítások a kapacitásfoglalások szinkronizálása során érhető el.</span><span class="sxs-lookup"><span data-stu-id="94d4b-118">The options are available during synchronization of capacity reservations.</span></span>

1. <span data-ttu-id="94d4b-119">Válassza a **Projektvezetés és könyvelés** &gt; **Időszakos** &gt; **Kapacitásszinkronizálás** &gt; **Erőforrás kapacitás-összesítéseinek szinkronizálása** lehetőségeket.</span><span class="sxs-lookup"><span data-stu-id="94d4b-119">Select **Project management and accounting** &gt; **Periodic** &gt; **Capacity synchronization** &gt; **Synchronize resources capacity roll-ups**.</span></span>
2. <span data-ttu-id="94d4b-120">Állítsa be az alábbi táblázatban található lehetőségeket.</span><span class="sxs-lookup"><span data-stu-id="94d4b-120">Set the options in the following table.</span></span>

    | <span data-ttu-id="94d4b-121">Lehetőség</span><span class="sxs-lookup"><span data-stu-id="94d4b-121">Option</span></span>      | <span data-ttu-id="94d4b-122">Leírás</span><span class="sxs-lookup"><span data-stu-id="94d4b-122">Description</span></span> |
    |-------------|-------------|
    | <span data-ttu-id="94d4b-123">Időszak kódja</span><span class="sxs-lookup"><span data-stu-id="94d4b-123">Period code</span></span> | <span data-ttu-id="94d4b-124">Bejelölheti a Főkönyvi dátumtartomány kódját, és beállíthatja a szinkronizálási folyamat kezdő és záró dátumát erőforráskapacitás-összesítésekhez.</span><span class="sxs-lookup"><span data-stu-id="94d4b-124">Optionally select the General ledger date interval code to set the start and end dates for the synchronization process for resource capacity roll-ups.</span></span> |
    | <span data-ttu-id="94d4b-125">Kezdő dátum</span><span class="sxs-lookup"><span data-stu-id="94d4b-125">Start date</span></span>  | <span data-ttu-id="94d4b-126">Adja meg a szinkronizálási folyamat kezdő dátumát erőforráskapacitás-összesítésekhez.</span><span class="sxs-lookup"><span data-stu-id="94d4b-126">Enter the start date for the synchronization process for resource capacity roll-ups.</span></span> |
    | <span data-ttu-id="94d4b-127">Befejezés</span><span class="sxs-lookup"><span data-stu-id="94d4b-127">End date</span></span>    | <span data-ttu-id="94d4b-128">Adja meg a szinkronizálási folyamat záró dátumát erőforráskapacitás-összesítésekhez.</span><span class="sxs-lookup"><span data-stu-id="94d4b-128">Enter the end date for the synchronization process for resource capacity roll-ups.</span></span> |

<span data-ttu-id="94d4b-129">[![Szinkronizálási folyamat](./media/projectresourcing09.jpg)](./media/projectresourcing09.jpg)</span><span class="sxs-lookup"><span data-stu-id="94d4b-129">[![Synchronization process](./media/projectresourcing09.jpg)](./media/projectresourcing09.jpg)</span></span>
