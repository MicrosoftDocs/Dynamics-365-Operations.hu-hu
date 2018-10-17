--- 
title: "Szabadság kezelése"
description: "Ez az eljárás végigvezeti az alkalmazotti szabadságrekordok létrehozásán."
author: ShielaSogge
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: HcmWorker, HcmEmploymentLeave
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 7687d31fbf73a02b1b924d092e77ac28b573e694
ms.contentlocale: hu-hu
ms.lasthandoff: 09/14/2018

---
# <a name="manage-leave-of-absence"></a><span data-ttu-id="cffc8-103">Szabadság kezelése</span><span class="sxs-lookup"><span data-stu-id="cffc8-103">Manage leave of absence</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="cffc8-104">Ez az eljárás végigvezeti az alkalmazotti szabadságrekordok létrehozásán.</span><span class="sxs-lookup"><span data-stu-id="cffc8-104">This procedure walks through the creation of employee leave records.</span></span> <span data-ttu-id="cffc8-105">Nyomon követheti többek között az egészségügyi, oktatási vagy szülői tevékenység miatt szabadságok idejét.</span><span class="sxs-lookup"><span data-stu-id="cffc8-105">You can track leave time for reasons that include medical, educational, or parental activities.</span></span> <span data-ttu-id="cffc8-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="cffc8-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="cffc8-107">Ugrás az Emberi erőforrások > Dolgozók > Alkalmazottak lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cffc8-107">Go to Human resources > Workers > Employees.</span></span>
2. <span data-ttu-id="cffc8-108">A listából válasszon egy alkalmazottat.</span><span class="sxs-lookup"><span data-stu-id="cffc8-108">In the list, select an employee.</span></span>
3. <span data-ttu-id="cffc8-109">A kiválasztott alkalmazott részletes adatainak megjelenítése az alkalmazott nevének kiválasztásával.</span><span class="sxs-lookup"><span data-stu-id="cffc8-109">Display detailed information for the selected employee by selecting the employee's name.</span></span>
4. <span data-ttu-id="cffc8-110">Kattintson a Foglalkoztatás lapra.</span><span class="sxs-lookup"><span data-stu-id="cffc8-110">Click the Employment tab.</span></span>
5. <span data-ttu-id="cffc8-111">Kattintson a Szabadság elemre.</span><span class="sxs-lookup"><span data-stu-id="cffc8-111">Click Leave.</span></span>
6. <span data-ttu-id="cffc8-112">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cffc8-112">Click New.</span></span>
7. <span data-ttu-id="cffc8-113">A Szabadságtípus mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="cffc8-113">In the Leave type field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="cffc8-114">A Szabadságtípusok képernyőn egy szabadságtípust társíthat egy kereseti kódhoz.</span><span class="sxs-lookup"><span data-stu-id="cffc8-114">You can associate a leave type to an earning code in the Leave types form.</span></span> <span data-ttu-id="cffc8-115">Ha egy szabadságtípus egy kereseti kóddal van társítva, egy kereseti sor fog létrejönni a társított kereseti kóddal a beírt szabadság időszakban.</span><span class="sxs-lookup"><span data-stu-id="cffc8-115">If a leave type is associated with an earning code, an earning line will be generated with the associated earning code during the leave period that you enter.</span></span>  
8. <span data-ttu-id="cffc8-116">Ebből a listából válassza ki a szabadság típusát.</span><span class="sxs-lookup"><span data-stu-id="cffc8-116">In the list, select a leave type.</span></span> 
    * <span data-ttu-id="cffc8-117">Például: Örökbefogadás</span><span class="sxs-lookup"><span data-stu-id="cffc8-117">For example: Adoption</span></span>  
9. <span data-ttu-id="cffc8-118">Adja meg szabadság kezdetének időpontját.</span><span class="sxs-lookup"><span data-stu-id="cffc8-118">Enter the date that the leave will start.</span></span> <span data-ttu-id="cffc8-119">Példa: 2015-10-26</span><span class="sxs-lookup"><span data-stu-id="cffc8-119">Example: '2015-10-26'</span></span>
    * <span data-ttu-id="cffc8-120">Példa: 2015-10-26</span><span class="sxs-lookup"><span data-stu-id="cffc8-120">For example:  2015-10-26</span></span>  
10. <span data-ttu-id="cffc8-121">Adja meg szabadság kezdetének időpontját.</span><span class="sxs-lookup"><span data-stu-id="cffc8-121">Enter the date that the leave will start.</span></span> 
    * <span data-ttu-id="cffc8-122">Példa: 2015-11-20</span><span class="sxs-lookup"><span data-stu-id="cffc8-122">For example:  2015-11-20</span></span>  
11. <span data-ttu-id="cffc8-123">Adjon meg egy leírást a jegyzet mezőben.</span><span class="sxs-lookup"><span data-stu-id="cffc8-123">In the note field, enter a description.</span></span>
    * <span data-ttu-id="cffc8-124">Például: örökbefogdás miatti szabadság</span><span class="sxs-lookup"><span data-stu-id="cffc8-124">For example: Leave for adoption</span></span>  
12. <span data-ttu-id="cffc8-125">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="cffc8-125">Click Save.</span></span>


