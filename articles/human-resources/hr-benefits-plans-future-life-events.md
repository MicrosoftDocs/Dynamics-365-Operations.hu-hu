---
title: Jövőbeli életesemények konfigurálása
description: 'A jövőbeli életesemények ütemezése a következőben végezhető el: Dynamics 365 Human Resources.'
author: andreabichsel
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitFutureLifeEvents, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d52e91e7b050027485b3536f40f6ad80afd90de8
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6056732"
---
# <a name="configure-future-life-events"></a><span data-ttu-id="37d07-103">Jövőbeli életesemények konfigurálása</span><span class="sxs-lookup"><span data-stu-id="37d07-103">Configure future life events</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="37d07-104">A jövőbeli életesemények ütemezése a következőben végezhető el: Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="37d07-104">You can schedule future life events in Dynamics 365 Human Resources.</span></span>

1. <span data-ttu-id="37d07-105">A **Juttatások kezelése** munkaterületen, amely a **Beállítás** menüpontban található, válassza a **Jövőbeli életesemények** elemet.</span><span class="sxs-lookup"><span data-stu-id="37d07-105">In the **Benefits management** workspace, under **Setup**, select **Future life events**.</span></span>

2. <span data-ttu-id="37d07-106">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="37d07-106">Select **New**.</span></span>

3. <span data-ttu-id="37d07-107">Adjon meg értékeket a következő mezőkben:</span><span class="sxs-lookup"><span data-stu-id="37d07-107">Specify values for the following fields:</span></span>

   | <span data-ttu-id="37d07-108">Mező</span><span class="sxs-lookup"><span data-stu-id="37d07-108">Field</span></span> | <span data-ttu-id="37d07-109">Leírás</span><span class="sxs-lookup"><span data-stu-id="37d07-109">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="37d07-110">Életesemény dátuma</span><span class="sxs-lookup"><span data-stu-id="37d07-110">Life event date</span></span> | <span data-ttu-id="37d07-111">A rendszer feldolgozza az összes mai napig esedékes eseményt a belépési időszakban.</span><span class="sxs-lookup"><span data-stu-id="37d07-111">The system processes all events during the enrollment period that occur up until this date.</span></span> |
   | <span data-ttu-id="37d07-112">Életesemény naplózva</span><span class="sxs-lookup"><span data-stu-id="37d07-112">Life event logged</span></span> | <span data-ttu-id="37d07-113">Az esemény naplózásának dátuma és ideje.</span><span class="sxs-lookup"><span data-stu-id="37d07-113">Date and time when the life event is logged.</span></span> |
   | <span data-ttu-id="37d07-114">Eseménynapló típusa</span><span class="sxs-lookup"><span data-stu-id="37d07-114">Log type</span></span> | <span data-ttu-id="37d07-115">Azt jelzi, hogy a művelet a következők egyike-e:</span><span class="sxs-lookup"><span data-stu-id="37d07-115">Shows whether the action is one of the following:</span></span></br></br><span data-ttu-id="37d07-116">- **Frissítés** – olyan meglévő rekord módosítása, amely életeseményeket követ</span><span class="sxs-lookup"><span data-stu-id="37d07-116">- **Update** – a change to an existing record that is tracking life events</span></span></br></br><span data-ttu-id="37d07-117">- **Beszúrás** – új életesemény rekordjának létrehozása</span><span class="sxs-lookup"><span data-stu-id="37d07-117">- **Insert** – the creation of a new life event record</span></span> |
   | <span data-ttu-id="37d07-118">Életesemény-típus azonosítója</span><span class="sxs-lookup"><span data-stu-id="37d07-118">Life event type ID</span></span> | <span data-ttu-id="37d07-119">Az életesemény típusának egyedi azonosítója.</span><span class="sxs-lookup"><span data-stu-id="37d07-119">The life event type unique identifier.</span></span> |
   | <span data-ttu-id="37d07-120">Életesemény-típus</span><span class="sxs-lookup"><span data-stu-id="37d07-120">Life event type</span></span> | <span data-ttu-id="37d07-121">Katalizátor az alkalmazotti juttatások regisztrálásának frissítéséhez.</span><span class="sxs-lookup"><span data-stu-id="37d07-121">A catalyst to updating an employee’s benefits enrollment.</span></span> <span data-ttu-id="37d07-122">A további tudnivalókért lásd az Életesemény-indítók szakaszt.</span><span class="sxs-lookup"><span data-stu-id="37d07-122">For more details, see the Life event triggers section.</span></span> |
   | <span data-ttu-id="37d07-123">Állapot</span><span class="sxs-lookup"><span data-stu-id="37d07-123">Status</span></span> | <span data-ttu-id="37d07-124">Annak megjelenítése, hogy feldolgozták-e az életeseményt vagy sem.</span><span class="sxs-lookup"><span data-stu-id="37d07-124">Whether the life event has been processed or not.</span></span> |
   | <span data-ttu-id="37d07-125">Vonal</span><span class="sxs-lookup"><span data-stu-id="37d07-125">Line</span></span> | <span data-ttu-id="37d07-126">A jövőbeli életesemény sorának száma.</span><span class="sxs-lookup"><span data-stu-id="37d07-126">The line number of the future life event.</span></span> |

4. <span data-ttu-id="37d07-127">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="37d07-127">Select **Save**.</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]