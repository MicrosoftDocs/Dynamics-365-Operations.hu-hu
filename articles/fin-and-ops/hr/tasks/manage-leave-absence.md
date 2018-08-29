--- 
title: "Szabadságok kezelése"
description: "Ez az eljárás végigvezeti az alkalmazotti szabadságrekordok létrehozásán."
author: ShielaSogge
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations, Talent
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 764d4c9049d94ebcd55c61654aa2f4133b35bae6
ms.openlocfilehash: fc16d2aefcb52493e72e78def5b86b9da9673914
ms.contentlocale: hu-hu
ms.lasthandoff: 08/09/2018

---
# <a name="manage-leaves-of-absence"></a><span data-ttu-id="ad6af-103">Szabadságok kezelése</span><span class="sxs-lookup"><span data-stu-id="ad6af-103">Manage leaves of absence</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ad6af-104">Ez az eljárás végigvezeti az alkalmazotti szabadságrekordok létrehozásán.</span><span class="sxs-lookup"><span data-stu-id="ad6af-104">This procedure walks through the creation of employee leave records.</span></span> <span data-ttu-id="ad6af-105">Nyomon követheti többek között az egészségügyi, oktatási vagy szülői tevékenység miatt szabadságok idejét.</span><span class="sxs-lookup"><span data-stu-id="ad6af-105">You can track leave time for reasons that include medical, educational, or parental activities.</span></span> <span data-ttu-id="ad6af-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="ad6af-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="ad6af-107">Ugrás az Emberi erőforrások > Dolgozók > Alkalmazottak lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ad6af-107">Go to Human resources > Workers > Employees.</span></span>
2. <span data-ttu-id="ad6af-108">A listából válasszon egy alkalmazottat.</span><span class="sxs-lookup"><span data-stu-id="ad6af-108">In the list, select an employee.</span></span>
3. <span data-ttu-id="ad6af-109">A kiválasztott alkalmazott részletes adatainak megjelenítése az alkalmazott nevének kiválasztásával.</span><span class="sxs-lookup"><span data-stu-id="ad6af-109">Display detailed information for the selected employee by selecting the employee's name.</span></span>
4. <span data-ttu-id="ad6af-110">Kattintson a Foglalkoztatás lapra.</span><span class="sxs-lookup"><span data-stu-id="ad6af-110">Click the Employment tab.</span></span>
5. <span data-ttu-id="ad6af-111">Kattintson a Szabadság elemre.</span><span class="sxs-lookup"><span data-stu-id="ad6af-111">Click Leave.</span></span>
6. <span data-ttu-id="ad6af-112">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ad6af-112">Click New.</span></span>
7. <span data-ttu-id="ad6af-113">A Szabadságtípus mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="ad6af-113">In the Leave type field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="ad6af-114">A Szabadságtípusok képernyőn egy szabadságtípust társíthat egy kereseti kódhoz.</span><span class="sxs-lookup"><span data-stu-id="ad6af-114">You can associate a leave type to an earning code in the Leave types form.</span></span> <span data-ttu-id="ad6af-115">Ha egy szabadságtípus egy kereseti kóddal van társítva, egy kereseti sor fog létrejönni a társított kereseti kóddal a beírt szabadság időszakban.</span><span class="sxs-lookup"><span data-stu-id="ad6af-115">If a leave type is associated with an earning code, an earning line will be generated with the associated earning code during the leave period that you enter.</span></span>  
8. <span data-ttu-id="ad6af-116">Ebből a listából válassza ki a szabadság típusát.</span><span class="sxs-lookup"><span data-stu-id="ad6af-116">In the list, select a leave type.</span></span> 
    * <span data-ttu-id="ad6af-117">Például: Örökbefogadás</span><span class="sxs-lookup"><span data-stu-id="ad6af-117">For example: Adoption</span></span>  
9. <span data-ttu-id="ad6af-118">Adja meg szabadság kezdetének időpontját.</span><span class="sxs-lookup"><span data-stu-id="ad6af-118">Enter the date that the leave will start.</span></span> <span data-ttu-id="ad6af-119">Példa: 2015-10-26</span><span class="sxs-lookup"><span data-stu-id="ad6af-119">Example: '2015-10-26'</span></span>
    * <span data-ttu-id="ad6af-120">Példa: 2015-10-26</span><span class="sxs-lookup"><span data-stu-id="ad6af-120">For example:  2015-10-26</span></span>  
10. <span data-ttu-id="ad6af-121">Adja meg szabadság kezdetének időpontját.</span><span class="sxs-lookup"><span data-stu-id="ad6af-121">Enter the date that the leave will start.</span></span> 
    * <span data-ttu-id="ad6af-122">Példa: 2015-11-20</span><span class="sxs-lookup"><span data-stu-id="ad6af-122">For example:  2015-11-20</span></span>  
11. <span data-ttu-id="ad6af-123">Adjon meg egy leírást a jegyzet mezőben.</span><span class="sxs-lookup"><span data-stu-id="ad6af-123">In the note field, enter a description.</span></span>
    * <span data-ttu-id="ad6af-124">Például: örökbefogdás miatti szabadság</span><span class="sxs-lookup"><span data-stu-id="ad6af-124">For example: Leave for adoption</span></span>  
12. <span data-ttu-id="ad6af-125">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="ad6af-125">Click Save.</span></span>


