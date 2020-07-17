---
title: Folyamatok automatizálása
description: Ez a témakör részletesen bemutatja, hogy hogyan lehet a folyamatok automatizálásával egyszerű ütemezést végezni a kötegelt kiszolgálón futtatott folyamatok között.
author: RyanCCarlson2
manager: tonyafehr
ms.date: 06/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProcessScheduleSeries
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2020-06-30
ms.dyn365.ops.version: AX 10.0.11
ms.openlocfilehash: 2ab4e7510ff98b9fbf0223096b905e9de47f52e1
ms.sourcegitcommit: 1833c1e07a32c8ad41e4a1516e78100ae04a2156
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/26/2020
ms.locfileid: "3508185"
---
# <a name="process-automation"></a><span data-ttu-id="9e778-103">Folyamatok automatizálása</span><span class="sxs-lookup"><span data-stu-id="9e778-103">Process automation</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="9e778-104">A folyamatok automatizálásával egyszerű ütemezést lehet végezni a kötegelt kiszolgálón futtatott folyamatok között.</span><span class="sxs-lookup"><span data-stu-id="9e778-104">Process automation allows simple scheduling of processes that will be run by the batch server.</span></span> <span data-ttu-id="9e778-105">Az ütemezett munka frissített naptár nézete lehetővé teszi a végfelhasználók számára, hogy megtekintsék és végrehajtsák az ütemezett és befejezett munkát.</span><span class="sxs-lookup"><span data-stu-id="9e778-105">The updated calendar view of the scheduled work allows end users to view and take action on scheduled and completed work.</span></span>

## <a name="administration"></a><span data-ttu-id="9e778-106">Adminisztráció</span><span class="sxs-lookup"><span data-stu-id="9e778-106">Administration</span></span>

<span data-ttu-id="9e778-107">A rendszer a **Beállítás** menü Rendszeradminisztráció moduljában található összes folyamatautomatizálás központi felügyeleti lapja.</span><span class="sxs-lookup"><span data-stu-id="9e778-107">The central administration page for all process automations is found in the System Administration module under the **Setup** menu.</span></span> <span data-ttu-id="9e778-108">Ez a lap felsorolja a rendszerben beállított összes automatizált folyamatot (sorozatot).</span><span class="sxs-lookup"><span data-stu-id="9e778-108">This page will list all automated processes (series) that are set up in the system.</span></span> <span data-ttu-id="9e778-109">Ez lehetővé teszi az új folyamatautomatizálások közvetlen hozzáadását ezen a lapon.</span><span class="sxs-lookup"><span data-stu-id="9e778-109">It will also allow you to add new process automations directly from this page.</span></span> <span data-ttu-id="9e778-110">Ha be van állítva a sorozat, akkor az egyes sorozatok ebből a listából kezelhetők.</span><span class="sxs-lookup"><span data-stu-id="9e778-110">After a series is set up, you can manage each series from this list.</span></span> <span data-ttu-id="9e778-111">Választhatja, hogy a teljes sorozatot szerkeszti, törli, egy lista nézetben megtekinti az összes előfordulását, vagy letiltja a sorozatot, ha szüneteltetni szeretné az ütemezett munkát egy adott időszakra.</span><span class="sxs-lookup"><span data-stu-id="9e778-111">You can chose to edit the entire series, delete it, view all occurrences in a list view, or disable the series if you would like to pause the scheduled work for a period of time.</span></span> 

## <a name="calendar-view"></a><span data-ttu-id="9e778-112">Naptár nézet</span><span class="sxs-lookup"><span data-stu-id="9e778-112">Calendar view</span></span> 
<span data-ttu-id="9e778-113">A folyamatok automatizálásának egyik kulcselőnye az a képessége, hogy az ütemezett munka egyszerű naptári nézetben látható legyen.</span><span class="sxs-lookup"><span data-stu-id="9e778-113">One of the key benefits of process automation is the ability to see the scheduled work in a simple calendar view.</span></span>  <span data-ttu-id="9e778-114">Ez a nézet lehetővé teszi, hogy egyszerre egy heti munkát jelenítsen meg.</span><span class="sxs-lookup"><span data-stu-id="9e778-114">This view allows you to see work for a week at a time.</span></span> <span data-ttu-id="9e778-115">Ez a nézet a **Folyamatautomatizálás** lap jobb oldalán jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="9e778-115">You will see this view on the right side of the **Process automation** page.</span></span> <span data-ttu-id="9e778-116">A program kitölti a kiválasztott sorozathoz ütemezett munkát.</span><span class="sxs-lookup"><span data-stu-id="9e778-116">It will be populated with the scheduled work for the selected series.</span></span> 

<span data-ttu-id="9e778-117">[![Folyamatautomatizálási naptár](./media/CalendarView2.png)](./media/CalendarView2.png)</span><span class="sxs-lookup"><span data-stu-id="9e778-117">[![Process automation calendar](./media/CalendarView2.png)](./media/CalendarView2.png)</span></span>

## <a name="occurrence-changes"></a><span data-ttu-id="9e778-118">Előfordulás módosításai</span><span class="sxs-lookup"><span data-stu-id="9e778-118">Occurrence changes</span></span>
<span data-ttu-id="9e778-119">Minden előfordulás módosítható anélkül, hogy hatással lenne az azt létrehozó sorozatok által meghatározott egyéb előfordulásokra.</span><span class="sxs-lookup"><span data-stu-id="9e778-119">Each occurrence can be modified without impacting other occurrences defined by the series that originated them.</span></span> <span data-ttu-id="9e778-120">Az ütemezett munka előfordulásai szerkeszthetők a naptár nézetből a **Nézet/Szerkesztés** gombra kattintva, majd az **Előfordulás** lehetőséget választva.</span><span class="sxs-lookup"><span data-stu-id="9e778-120">Occurrences of scheduled work can be edited from the calendar view by selecting the **View/Edit** button and selecting **Occurrence**.</span></span> <span data-ttu-id="9e778-121">Ez lehetővé teszi a sorozat beállítási varázslója által eredetileg megjelenített összes beállítás elérését, és lehetőséget nyújt arra, hogy egyszeri módosítást hajtson végre a kiválasztott előforduláshoz.</span><span class="sxs-lookup"><span data-stu-id="9e778-121">This allows you access to all the settings originally shown in the series setup wizard and provides the ability to make a one-off change for the selected occurrence.</span></span> <span data-ttu-id="9e778-122">Az ütemezett munka előfordulását a naptár nézetből a **Letiltás** gomb választásával ki is lehet kapcsolni.</span><span class="sxs-lookup"><span data-stu-id="9e778-122">An occurrence of scheduled work can also be turned off by selecting the **Disable** button from the calendar view.</span></span> 

## <a name="developer-documentation"></a><span data-ttu-id="9e778-123">Fejlesztői dokumentáció</span><span class="sxs-lookup"><span data-stu-id="9e778-123">Developer documentation</span></span> 
<span data-ttu-id="9e778-124">A fejlesztői dokumentáció jelenleg írás alatt áll, hogy lehetővé tegye a fejlesztők számára a folyamatautomatizálási keretrendszer kiterjesztését.</span><span class="sxs-lookup"><span data-stu-id="9e778-124">Developer documentation is currently being written to allow developers to extend the process automation framework.</span></span> <span data-ttu-id="9e778-125">Ez a dokumentáció tájékoztatást ad arról, hogy hogyan lehet egyéni folyamatokat létrehozni, amelyeket a kötegelt kiszolgálón kell futtatni a folyamatautomatizálási varázslóval ütemezve, és a naptár nézetben automatikusan megjelennek.</span><span class="sxs-lookup"><span data-stu-id="9e778-125">This documentation will provide information about how you can create custom processes that you require to be run by the batch server scheduled with the process automation wizard and appear in the calendar view automatically.</span></span>
