---
title: Jövőbeli életesemények konfigurálása
description: 'A jövőbeli életesemények ütemezése a következőben végezhető el: Dynamics 365 Human Resources.'
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
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
ms.openlocfilehash: 655070e52e3d1f43ca6904ce3218582868f193fe
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009293"
---
# <a name="configure-future-life-events"></a><span data-ttu-id="bd00c-103">Jövőbeli életesemények konfigurálása</span><span class="sxs-lookup"><span data-stu-id="bd00c-103">Configure future life events</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="bd00c-104">A jövőbeli életesemények ütemezése a következőben végezhető el: Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="bd00c-104">You can schedule future life events in Dynamics 365 Human Resources.</span></span>

1. <span data-ttu-id="bd00c-105">A **Juttatások kezelése** munkaterületen, amely a **Beállítás** menüpontban található, válassza a **Jövőbeli életesemények** elemet.</span><span class="sxs-lookup"><span data-stu-id="bd00c-105">In the **Benefits management** workspace, under **Setup**, select **Future life events**.</span></span>

2. <span data-ttu-id="bd00c-106">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="bd00c-106">Select **New**.</span></span>

3. <span data-ttu-id="bd00c-107">Adjon meg értékeket a következő mezőkben:</span><span class="sxs-lookup"><span data-stu-id="bd00c-107">Specify values for the following fields:</span></span>

   | <span data-ttu-id="bd00c-108">Mező</span><span class="sxs-lookup"><span data-stu-id="bd00c-108">Field</span></span> | <span data-ttu-id="bd00c-109">Leírás</span><span class="sxs-lookup"><span data-stu-id="bd00c-109">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="bd00c-110">Életesemény dátuma</span><span class="sxs-lookup"><span data-stu-id="bd00c-110">Life event date</span></span> | <span data-ttu-id="bd00c-111">A rendszer feldolgozza az összes mai napig esedékes eseményt a belépési időszakban.</span><span class="sxs-lookup"><span data-stu-id="bd00c-111">The system processes all events during the enrollment period that occur up until this date.</span></span> |
   | <span data-ttu-id="bd00c-112">Életesemény naplózva</span><span class="sxs-lookup"><span data-stu-id="bd00c-112">Life event logged</span></span> | <span data-ttu-id="bd00c-113">Az esemény naplózásának dátuma és ideje.</span><span class="sxs-lookup"><span data-stu-id="bd00c-113">Date and time when the life event is logged.</span></span> |
   | <span data-ttu-id="bd00c-114">Eseménynapló típusa</span><span class="sxs-lookup"><span data-stu-id="bd00c-114">Log type</span></span> | <span data-ttu-id="bd00c-115">Azt jelzi, hogy a művelet a következők egyike-e:</span><span class="sxs-lookup"><span data-stu-id="bd00c-115">Shows whether the action is one of the following:</span></span></br></br><span data-ttu-id="bd00c-116">- **Frissítés** – olyan meglévő rekord módosítása, amely életeseményeket követ</span><span class="sxs-lookup"><span data-stu-id="bd00c-116">- **Update** – a change to an existing record that is tracking life events</span></span></br></br><span data-ttu-id="bd00c-117">- **Beszúrás** – új életesemény rekordjának létrehozása</span><span class="sxs-lookup"><span data-stu-id="bd00c-117">- **Insert** – the creation of a new life event record</span></span> |
   | <span data-ttu-id="bd00c-118">Életesemény-típus azonosítója</span><span class="sxs-lookup"><span data-stu-id="bd00c-118">Life event type ID</span></span> | <span data-ttu-id="bd00c-119">Az életesemény típusának egyedi azonosítója.</span><span class="sxs-lookup"><span data-stu-id="bd00c-119">The life event type unique identifier.</span></span> |
   | <span data-ttu-id="bd00c-120">Életesemény-típus</span><span class="sxs-lookup"><span data-stu-id="bd00c-120">Life event type</span></span> | <span data-ttu-id="bd00c-121">Katalizátor az alkalmazotti juttatások regisztrálásának frissítéséhez.</span><span class="sxs-lookup"><span data-stu-id="bd00c-121">A catalyst to updating an employee’s benefits enrollment.</span></span> <span data-ttu-id="bd00c-122">A további tudnivalókért lásd az Életesemény-indítók szakaszt.</span><span class="sxs-lookup"><span data-stu-id="bd00c-122">For more details, see the Life event triggers section.</span></span> |
   | <span data-ttu-id="bd00c-123">Állapot</span><span class="sxs-lookup"><span data-stu-id="bd00c-123">Status</span></span> | <span data-ttu-id="bd00c-124">Annak megjelenítése, hogy feldolgozták-e az életeseményt vagy sem.</span><span class="sxs-lookup"><span data-stu-id="bd00c-124">Whether the life event has been processed or not.</span></span> |
   | <span data-ttu-id="bd00c-125">Vonal</span><span class="sxs-lookup"><span data-stu-id="bd00c-125">Line</span></span> | <span data-ttu-id="bd00c-126">A jövőbeli életesemény sorának száma.</span><span class="sxs-lookup"><span data-stu-id="bd00c-126">The line number of the future life event.</span></span> |

4. <span data-ttu-id="bd00c-127">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="bd00c-127">Select **Save**.</span></span> 
