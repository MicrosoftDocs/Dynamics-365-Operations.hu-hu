---
title: Beosztás jelentési kapcsolatainak módosítása
description: Ez az eljárás bemutatja, hogyan módosíthatja a jelentési kapcsolatot egy alkalmazott esetében.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmPosition, HcmPositionReportsToDialog, HcmPositionLookup
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3285222b11905999f0eadb846ac785342c16aa38
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009308"
---
# <a name="modify-reporting-relationships-for-a-position"></a><span data-ttu-id="7b822-103">Beosztás jelentési kapcsolatainak módosítása</span><span class="sxs-lookup"><span data-stu-id="7b822-103">Modify reporting relationships for a position</span></span>



<span data-ttu-id="7b822-104">Ez az eljárás bemutatja, hogyan módosíthatja a jelentési kapcsolatot egy alkalmazott esetében.</span><span class="sxs-lookup"><span data-stu-id="7b822-104">This procedure shows how to change the reporting relationship for an employee.</span></span> <span data-ttu-id="7b822-105">A jelentési kapcsolat egy munkafolyamathoz kapcsolódó dokumentumok útjának meghatározására is használható.</span><span class="sxs-lookup"><span data-stu-id="7b822-105">The reporting relationship can be used for routing documents through workflow.</span></span> <span data-ttu-id="7b822-106">Az eljárás bemutatja, hogyan rendelhet hozzá egy alkalmazottat további hierarchiákhoz.</span><span class="sxs-lookup"><span data-stu-id="7b822-106">The procedure also shows how to assign the employee to additional hierarchies.</span></span> <span data-ttu-id="7b822-107">Például egy alkalmazott egy projektcsapat tagjai is lehet, miközben nem hivatalos jelentési kapcsolata van a projektcsapat vezetőjével.</span><span class="sxs-lookup"><span data-stu-id="7b822-107">For example, an employee might be a part of a project team with an informal reporting relationship to a project supervisor.</span></span> <span data-ttu-id="7b822-108">Annak érdekében, hogy különböző projekt vagy mátrix forgatókönyvek is megvalósíthatók legyenek, további jelentési kapcsolatok is hozzáadhatók egy beosztáshoz.</span><span class="sxs-lookup"><span data-stu-id="7b822-108">Additional reporting relationships can be defined on the position to accommodate various project or matrix scenarios.</span></span> <span data-ttu-id="7b822-109">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="7b822-109">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="7b822-110">Ugorjon az Emberi erőforrások > Pozíciók > Pozíciók pontra.</span><span class="sxs-lookup"><span data-stu-id="7b822-110">Go to Human resources > Positions > Positions.</span></span>
2. <span data-ttu-id="7b822-111">Rekordok kereséséhez használja a gyorsszűrőt.</span><span class="sxs-lookup"><span data-stu-id="7b822-111">Use the Quick Filter to find records.</span></span> <span data-ttu-id="7b822-112">Például szűkítse a Pozíció mezőt a „000091” értéket beírva.</span><span class="sxs-lookup"><span data-stu-id="7b822-112">For example, filter on the Position field with a value of '000091'.</span></span>
3. <span data-ttu-id="7b822-113">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="7b822-113">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="7b822-114">Bontsa ki a Jelentés a beosztásnak szakaszt.</span><span class="sxs-lookup"><span data-stu-id="7b822-114">Expand the Reports to position section.</span></span>
5. <span data-ttu-id="7b822-115">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="7b822-115">Click New to open the drop dialog.</span></span>
6. <span data-ttu-id="7b822-116">A Jelentés a következőnek mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="7b822-116">In the Reports to field, enter or select a value.</span></span>
7. <span data-ttu-id="7b822-117">Kattintson a Létrehozás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7b822-117">Click Create.</span></span>
8. <span data-ttu-id="7b822-118">Bontsa ki a Kapcsolatok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="7b822-118">Expand the Relationships section.</span></span>
9. <span data-ttu-id="7b822-119">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="7b822-119">Click Add.</span></span>
10. <span data-ttu-id="7b822-120">Jelölje be a rács bal oldalán található jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="7b822-120">Select the check box on the left of the grid.</span></span>
11. <span data-ttu-id="7b822-121">A Hierarchia neve mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="7b822-121">In the Hierarchy name field, enter or select a value.</span></span>
    * <span data-ttu-id="7b822-122">Példa: Projekt</span><span class="sxs-lookup"><span data-stu-id="7b822-122">Example: Project</span></span>  
12. <span data-ttu-id="7b822-123">A Jelentés beosztás szerint mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="7b822-123">In the Reports to position field, enter or select a value.</span></span>  <span data-ttu-id="7b822-124">Példa: 000437</span><span class="sxs-lookup"><span data-stu-id="7b822-124">Example:  000437</span></span>
13. <span data-ttu-id="7b822-125">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="7b822-125">Click Save.</span></span>
