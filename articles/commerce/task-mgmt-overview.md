---
title: Feladatkezelés – áttekintés
description: Ez a témakör áttekintést nyújt a feladatkezelésről Microsoft Dynamics 365 Commerce vezetői és dolgozói számára.
author: gvrmohanreddy
manager: annbe
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 3891d846f51b5335809876a6557dfb5a031272c8
ms.sourcegitcommit: 80cbb7d22267aa6a0ae0568d0063fb95556958a5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/11/2020
ms.locfileid: "3036763"
---
# <a name="task-management-overview"></a><span data-ttu-id="1d9f8-103">Feladatkezelés – áttekintés</span><span class="sxs-lookup"><span data-stu-id="1d9f8-103">Task management overview</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="1d9f8-104">Ez a témakör áttekintést nyújt a feladatkezelésről Microsoft Dynamics 365 Commerce vezetői és dolgozói számára.</span><span class="sxs-lookup"><span data-stu-id="1d9f8-104">This topic provides an overview of task management for managers and workers in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="1d9f8-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="1d9f8-105">Overview</span></span>

<span data-ttu-id="1d9f8-106">Kiskereskedelmi környezetben mindig nehéz biztosítani azt, hogy a megfelelő személy, a megfelelő időben hajtsa végre a feladatokat.</span><span class="sxs-lookup"><span data-stu-id="1d9f8-106">In a retail environment, it's always difficult to make sure that tasks are performed by the right person at the right time.</span></span> <span data-ttu-id="1d9f8-107">A kiskereskedőknek tájékoztatni kell a dolgozókat a közelgő feladatokról és a kapcsolódó üzleti kontextusról, hogy a feladatokat megfelelően és időben végre lehessen hajtani.</span><span class="sxs-lookup"><span data-stu-id="1d9f8-107">Retailers must be able to notify workers about upcoming tasks and provide related business context, so that the tasks can be completed correctly and on time.</span></span>

<span data-ttu-id="1d9f8-108">A Feladatkezelő egy termelékenységi funkció, Dynamics 365 Commerce alkalmazásban amellyel a vezetők és a dolgozók feladatlistát hozhatnak létre, kezelhetik a hozzárendelés feltételeit, nyomon követhetik a feladat állapotát, és integrálják ezeket a műveleteket a Commerce háttériroda és a pénztár (POS) alkalmazások között.</span><span class="sxs-lookup"><span data-stu-id="1d9f8-108">Task management is a productivity feature in Dynamics 365 Commerce that lets managers and workers create task lists, manage assignment criteria, track task status, and integrate these operations between Commerce back office and point of sale (POS) applications.</span></span>

<span data-ttu-id="1d9f8-109">A Központbeli szeméyek a Feladatkezelő segítségével hozhatják létre a feladatokat a kiskereskedelmi üzleteket számára, valamint nyomon követheti az állapotot üzlet vagy dolgozó szerint.</span><span class="sxs-lookup"><span data-stu-id="1d9f8-109">Headquarters personas can use task management to create task lists for retail stores, and to track status by store or worker.</span></span> <span data-ttu-id="1d9f8-110">Ismétlődő feladatokat is létrehozhatnak (például „Csütörtök estei zárás ellenőrzőlista”).</span><span class="sxs-lookup"><span data-stu-id="1d9f8-110">They can also create recurrent tasks (for example, "Thursday night closing checklist").</span></span>

<span data-ttu-id="1d9f8-111">Az üzletvezetők használhatják a feladatkezelést feladatok egyéni dolgozókhoz való hozzárendelésére, az esedékes feladatokkal kapcsolatos értesítések küldésére, a feladat állapotának módosítására, valamint a pénztár alkalmazásban egycélű feladatok létrehozására.</span><span class="sxs-lookup"><span data-stu-id="1d9f8-111">Store managers can use task management to assign tasks to individual workers, send notifications about upcoming tasks or tasks that are past due, update task status, and create single-purpose tasks in the POS application.</span></span> <span data-ttu-id="1d9f8-112">A dolgozók ezt követően megtekinthetik az értesítéseket, megtekinthetik a feladatok adatait, és frissíthetik a feladat állapotát a pénztárnál.</span><span class="sxs-lookup"><span data-stu-id="1d9f8-112">Workers can then see notifications, view task details, and update task status at the POS.</span></span>

<span data-ttu-id="1d9f8-113">A következő ábra a feladatok kezelésének fogalmi felépítését mutatja be a Commerce modulban.</span><span class="sxs-lookup"><span data-stu-id="1d9f8-113">The following illustration shows the conceptual architecture of task management in Commerce.</span></span>

![A feladatkezelés koncepcionális szerkezete](media/Tasks-management-conceptual-architecture.png)

## <a name="additional-resources"></a><span data-ttu-id="1d9f8-115">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="1d9f8-115">Additional resources</span></span>

[<span data-ttu-id="1d9f8-116">Feladatkezelés konfigurálása</span><span class="sxs-lookup"><span data-stu-id="1d9f8-116">Configure task management</span></span>](task-mgmt-configure.md)

[<span data-ttu-id="1d9f8-117">Feladatlisták létrehozása és feladatok hozzáadása</span><span class="sxs-lookup"><span data-stu-id="1d9f8-117">Create task lists and add tasks</span></span>](task-mgmt-create-lists.md)

[<span data-ttu-id="1d9f8-118">Feladatlisták hozzárendelése áruházakhoz vagy alkalmazottakhoz</span><span class="sxs-lookup"><span data-stu-id="1d9f8-118">Assign task lists to stores or employees</span></span>](task-mgmt-assign-lists.md)

[<span data-ttu-id="1d9f8-119">Feladatkezelés a pénztárban</span><span class="sxs-lookup"><span data-stu-id="1d9f8-119">Task management in POS</span></span>](task-mgmt-POS.md)
