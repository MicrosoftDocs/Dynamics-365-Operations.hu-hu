---
title: Szabadság kezelése
description: Ez az eljárás végigvezeti az alkalmazotti szabadságrekordok létrehozásán.
author: ShielaSogge
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmWorker, HcmEmploymentLeave
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7687d31fbf73a02b1b924d092e77ac28b573e694
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "337969"
---
# <a name="manage-leave-of-absence"></a><span data-ttu-id="30b69-103">Szabadság kezelése</span><span class="sxs-lookup"><span data-stu-id="30b69-103">Manage leave of absence</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="30b69-104">Ez az eljárás végigvezeti az alkalmazotti szabadságrekordok létrehozásán.</span><span class="sxs-lookup"><span data-stu-id="30b69-104">This procedure walks through the creation of employee leave records.</span></span> <span data-ttu-id="30b69-105">Nyomon követheti többek között az egészségügyi, oktatási vagy szülői tevékenység miatt szabadságok idejét.</span><span class="sxs-lookup"><span data-stu-id="30b69-105">You can track leave time for reasons that include medical, educational, or parental activities.</span></span> <span data-ttu-id="30b69-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="30b69-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="30b69-107">Ugrás az Emberi erőforrások > Dolgozók > Alkalmazottak lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="30b69-107">Go to Human resources > Workers > Employees.</span></span>
2. <span data-ttu-id="30b69-108">A listából válasszon egy alkalmazottat.</span><span class="sxs-lookup"><span data-stu-id="30b69-108">In the list, select an employee.</span></span>
3. <span data-ttu-id="30b69-109">A kiválasztott alkalmazott részletes adatainak megjelenítése az alkalmazott nevének kiválasztásával.</span><span class="sxs-lookup"><span data-stu-id="30b69-109">Display detailed information for the selected employee by selecting the employee's name.</span></span>
4. <span data-ttu-id="30b69-110">Kattintson a Foglalkoztatás lapra.</span><span class="sxs-lookup"><span data-stu-id="30b69-110">Click the Employment tab.</span></span>
5. <span data-ttu-id="30b69-111">Kattintson a Szabadság elemre.</span><span class="sxs-lookup"><span data-stu-id="30b69-111">Click Leave.</span></span>
6. <span data-ttu-id="30b69-112">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="30b69-112">Click New.</span></span>
7. <span data-ttu-id="30b69-113">A Szabadságtípus mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="30b69-113">In the Leave type field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="30b69-114">A Szabadságtípusok képernyőn egy szabadságtípust társíthat egy kereseti kódhoz.</span><span class="sxs-lookup"><span data-stu-id="30b69-114">You can associate a leave type to an earning code in the Leave types form.</span></span> <span data-ttu-id="30b69-115">Ha egy szabadságtípus egy kereseti kóddal van társítva, egy kereseti sor fog létrejönni a társított kereseti kóddal a beírt szabadság időszakban.</span><span class="sxs-lookup"><span data-stu-id="30b69-115">If a leave type is associated with an earning code, an earning line will be generated with the associated earning code during the leave period that you enter.</span></span>  
8. <span data-ttu-id="30b69-116">Ebből a listából válassza ki a szabadság típusát.</span><span class="sxs-lookup"><span data-stu-id="30b69-116">In the list, select a leave type.</span></span> 
    * <span data-ttu-id="30b69-117">Például: Örökbefogadás</span><span class="sxs-lookup"><span data-stu-id="30b69-117">For example: Adoption</span></span>  
9. <span data-ttu-id="30b69-118">Adja meg szabadság kezdetének időpontját.</span><span class="sxs-lookup"><span data-stu-id="30b69-118">Enter the date that the leave will start.</span></span> <span data-ttu-id="30b69-119">Példa: 2015-10-26</span><span class="sxs-lookup"><span data-stu-id="30b69-119">Example: '2015-10-26'</span></span>
    * <span data-ttu-id="30b69-120">Példa: 2015-10-26</span><span class="sxs-lookup"><span data-stu-id="30b69-120">For example:  2015-10-26</span></span>  
10. <span data-ttu-id="30b69-121">Adja meg szabadság kezdetének időpontját.</span><span class="sxs-lookup"><span data-stu-id="30b69-121">Enter the date that the leave will start.</span></span> 
    * <span data-ttu-id="30b69-122">Példa: 2015-11-20</span><span class="sxs-lookup"><span data-stu-id="30b69-122">For example:  2015-11-20</span></span>  
11. <span data-ttu-id="30b69-123">Adjon meg egy leírást a jegyzet mezőben.</span><span class="sxs-lookup"><span data-stu-id="30b69-123">In the note field, enter a description.</span></span>
    * <span data-ttu-id="30b69-124">Például: örökbefogdás miatti szabadság</span><span class="sxs-lookup"><span data-stu-id="30b69-124">For example: Leave for adoption</span></span>  
12. <span data-ttu-id="30b69-125">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="30b69-125">Click Save.</span></span>

