---
title: Jövőbeli életesemények konfigurálása
description: 'A jövőbeli életesemények ütemezése a következőben végezhető el: Dynamics 365 Human Resources.'
author: andreabichsel
manager: tfehr
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitFutureLifeEvents, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f10d7b6c9b45f6cedc16972fb157e43b7e0c40b3
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2021
ms.locfileid: "5112857"
---
# <a name="configure-future-life-events"></a><span data-ttu-id="5aee9-103">Jövőbeli életesemények konfigurálása</span><span class="sxs-lookup"><span data-stu-id="5aee9-103">Configure future life events</span></span>

<span data-ttu-id="5aee9-104">A jövőbeli életesemények ütemezése a következőben végezhető el: Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="5aee9-104">You can schedule future life events in Dynamics 365 Human Resources.</span></span>

1. <span data-ttu-id="5aee9-105">A **Juttatások kezelése** munkaterületen, amely a **Beállítás** menüpontban található, válassza a **Jövőbeli életesemények** elemet.</span><span class="sxs-lookup"><span data-stu-id="5aee9-105">In the **Benefits management** workspace, under **Setup**, select **Future life events**.</span></span>

2. <span data-ttu-id="5aee9-106">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5aee9-106">Select **New**.</span></span>

3. <span data-ttu-id="5aee9-107">Adjon meg értékeket a következő mezőkben:</span><span class="sxs-lookup"><span data-stu-id="5aee9-107">Specify values for the following fields:</span></span>

   | <span data-ttu-id="5aee9-108">Mező</span><span class="sxs-lookup"><span data-stu-id="5aee9-108">Field</span></span> | <span data-ttu-id="5aee9-109">Leírás</span><span class="sxs-lookup"><span data-stu-id="5aee9-109">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="5aee9-110">Életesemény dátuma</span><span class="sxs-lookup"><span data-stu-id="5aee9-110">Life event date</span></span> | <span data-ttu-id="5aee9-111">A rendszer feldolgozza az összes mai napig esedékes eseményt a belépési időszakban.</span><span class="sxs-lookup"><span data-stu-id="5aee9-111">The system processes all events during the enrollment period that occur up until this date.</span></span> |
   | <span data-ttu-id="5aee9-112">Életesemény naplózva</span><span class="sxs-lookup"><span data-stu-id="5aee9-112">Life event logged</span></span> | <span data-ttu-id="5aee9-113">Az esemény naplózásának dátuma és ideje.</span><span class="sxs-lookup"><span data-stu-id="5aee9-113">Date and time when the life event is logged.</span></span> |
   | <span data-ttu-id="5aee9-114">Eseménynapló típusa</span><span class="sxs-lookup"><span data-stu-id="5aee9-114">Log type</span></span> | <span data-ttu-id="5aee9-115">Azt jelzi, hogy a művelet a következők egyike-e:</span><span class="sxs-lookup"><span data-stu-id="5aee9-115">Shows whether the action is one of the following:</span></span></br></br><span data-ttu-id="5aee9-116">- **Frissítés** – olyan meglévő rekord módosítása, amely életeseményeket követ</span><span class="sxs-lookup"><span data-stu-id="5aee9-116">- **Update** – a change to an existing record that is tracking life events</span></span></br></br><span data-ttu-id="5aee9-117">- **Beszúrás** – új életesemény rekordjának létrehozása</span><span class="sxs-lookup"><span data-stu-id="5aee9-117">- **Insert** – the creation of a new life event record</span></span> |
   | <span data-ttu-id="5aee9-118">Életesemény-típus azonosítója</span><span class="sxs-lookup"><span data-stu-id="5aee9-118">Life event type ID</span></span> | <span data-ttu-id="5aee9-119">Az életesemény típusának egyedi azonosítója.</span><span class="sxs-lookup"><span data-stu-id="5aee9-119">The life event type unique identifier.</span></span> |
   | <span data-ttu-id="5aee9-120">Életesemény-típus</span><span class="sxs-lookup"><span data-stu-id="5aee9-120">Life event type</span></span> | <span data-ttu-id="5aee9-121">Katalizátor az alkalmazotti juttatások regisztrálásának frissítéséhez.</span><span class="sxs-lookup"><span data-stu-id="5aee9-121">A catalyst to updating an employee’s benefits enrollment.</span></span> <span data-ttu-id="5aee9-122">A további tudnivalókért lásd az Életesemény-indítók szakaszt.</span><span class="sxs-lookup"><span data-stu-id="5aee9-122">For more details, see the Life event triggers section.</span></span> |
   | <span data-ttu-id="5aee9-123">Állapot</span><span class="sxs-lookup"><span data-stu-id="5aee9-123">Status</span></span> | <span data-ttu-id="5aee9-124">Annak megjelenítése, hogy feldolgozták-e az életeseményt vagy sem.</span><span class="sxs-lookup"><span data-stu-id="5aee9-124">Whether the life event has been processed or not.</span></span> |
   | <span data-ttu-id="5aee9-125">Vonal</span><span class="sxs-lookup"><span data-stu-id="5aee9-125">Line</span></span> | <span data-ttu-id="5aee9-126">A jövőbeli életesemény sorának száma.</span><span class="sxs-lookup"><span data-stu-id="5aee9-126">The line number of the future life event.</span></span> |

4. <span data-ttu-id="5aee9-127">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5aee9-127">Select **Save**.</span></span> 
