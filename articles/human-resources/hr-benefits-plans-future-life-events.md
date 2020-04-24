---
title: Jövőbeli életesemények konfigurálása
description: 'A jövőbeli életesemények ütemezése a következőben végezhető el: Dynamics 365 Human Resources.'
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitFutureLifeEvents
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 134152bb8ae2b9f42b59cc9202e244435a607eba
ms.sourcegitcommit: a9461650d11d6845e1942865ebf7e35f75f61ad3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/06/2020
ms.locfileid: "3230085"
---
# <a name="configure-future-life-events"></a><span data-ttu-id="713cc-103">Jövőbeli életesemények konfigurálása</span><span class="sxs-lookup"><span data-stu-id="713cc-103">Configure future life events</span></span>

<span data-ttu-id="713cc-104">A jövőbeli életesemények ütemezése a következőben végezhető el: Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="713cc-104">You can schedule future life events in Dynamics 365 Human Resources.</span></span>

1. <span data-ttu-id="713cc-105">A **Juttatások kezelése** munkaterületen, amely a **Beállítás** menüpontban található, válassza a **Jövőbeli életesemények** elemet.</span><span class="sxs-lookup"><span data-stu-id="713cc-105">In the **Benefits management** workspace, under **Setup**, select **Future life events**.</span></span>

2. <span data-ttu-id="713cc-106">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="713cc-106">Select **New**.</span></span>

3. <span data-ttu-id="713cc-107">Adjon meg értékeket a következő mezőkben:</span><span class="sxs-lookup"><span data-stu-id="713cc-107">Specify values for the following fields:</span></span>

   | <span data-ttu-id="713cc-108">Mező</span><span class="sxs-lookup"><span data-stu-id="713cc-108">Field</span></span> | <span data-ttu-id="713cc-109">Leírás</span><span class="sxs-lookup"><span data-stu-id="713cc-109">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="713cc-110">Életesemény dátuma</span><span class="sxs-lookup"><span data-stu-id="713cc-110">Life event date</span></span> | <span data-ttu-id="713cc-111">A rendszer feldolgozza az összes mai napig esedékes eseményt a belépési időszakban.</span><span class="sxs-lookup"><span data-stu-id="713cc-111">The system processes all events during the enrollment period that occur up until this date.</span></span> |
   | <span data-ttu-id="713cc-112">Életesemény naplózva</span><span class="sxs-lookup"><span data-stu-id="713cc-112">Life event logged</span></span> | <span data-ttu-id="713cc-113">Az esemény naplózásának dátuma és ideje.</span><span class="sxs-lookup"><span data-stu-id="713cc-113">Date and time when the life event is logged.</span></span> |
   | <span data-ttu-id="713cc-114">Eseménynapló típusa</span><span class="sxs-lookup"><span data-stu-id="713cc-114">Log type</span></span> | <span data-ttu-id="713cc-115">Azt jelzi, hogy a művelet a következők egyike-e:</span><span class="sxs-lookup"><span data-stu-id="713cc-115">Shows whether the action is one of the following:</span></span></br></br><span data-ttu-id="713cc-116">- **Frissítés** – olyan meglévő rekord módosítása, amely életeseményeket követ</span><span class="sxs-lookup"><span data-stu-id="713cc-116">- **Update** – a change to an existing record that is tracking life events</span></span></br></br><span data-ttu-id="713cc-117">- **Beszúrás** – új életesemény rekordjának létrehozása</span><span class="sxs-lookup"><span data-stu-id="713cc-117">- **Insert** – the creation of a new life event record</span></span> |
   | <span data-ttu-id="713cc-118">Életesemény-típus azonosítója</span><span class="sxs-lookup"><span data-stu-id="713cc-118">Life event type ID</span></span> | <span data-ttu-id="713cc-119">Az életesemény típusának egyedi azonosítója.</span><span class="sxs-lookup"><span data-stu-id="713cc-119">The life event type unique identifier.</span></span> |
   | <span data-ttu-id="713cc-120">Életesemény-típus</span><span class="sxs-lookup"><span data-stu-id="713cc-120">Life event type</span></span> | <span data-ttu-id="713cc-121">Katalizátor az alkalmazotti juttatások regisztrálásának frissítéséhez.</span><span class="sxs-lookup"><span data-stu-id="713cc-121">A catalyst to updating an employee’s benefits enrollment.</span></span> <span data-ttu-id="713cc-122">A további tudnivalókért lásd az Életesemény-indítók szakaszt.</span><span class="sxs-lookup"><span data-stu-id="713cc-122">For more details, see the Life event triggers section.</span></span> |
   | <span data-ttu-id="713cc-123">Állapot</span><span class="sxs-lookup"><span data-stu-id="713cc-123">Status</span></span> | <span data-ttu-id="713cc-124">Annak megjelenítése, hogy feldolgozták-e az életeseményt vagy sem.</span><span class="sxs-lookup"><span data-stu-id="713cc-124">Whether the life event has been processed or not.</span></span> |
   | <span data-ttu-id="713cc-125">Vonal</span><span class="sxs-lookup"><span data-stu-id="713cc-125">Line</span></span> | <span data-ttu-id="713cc-126">A jövőbeli életesemény sorának száma.</span><span class="sxs-lookup"><span data-stu-id="713cc-126">The line number of the future life event.</span></span> |

4. <span data-ttu-id="713cc-127">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="713cc-127">Select **Save**.</span></span> 
