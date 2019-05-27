---
title: Konfigurációs szabályok létrehozása
description: Ez az eljárás olyan konfigurációs szabályokat hoz létre, amelyeket a dimenzión alapuló konfigurációkhoz használhat fel az anyagjegyzék bizonyos kombinációinak betartására vagy megakadályozására.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMTable, BOMConfigRule, ConfigItemIdLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a315ddecd2e10f508b86ac8ea18a36df71616963
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1568466"
---
# <a name="create-configuration-rules"></a><span data-ttu-id="e1ae1-103">Konfigurációs szabályok létrehozása</span><span class="sxs-lookup"><span data-stu-id="e1ae1-103">Create configuration rules</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e1ae1-104">Ez az eljárás olyan konfigurációs szabályokat hoz létre, amelyeket a dimenzión alapuló konfigurációkhoz használhat fel az anyagjegyzék bizonyos kombinációinak betartására vagy megakadályozására.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-104">This procedure creates configuration rules that can be used for dimension-based configuration to enforce or prevent certain combinations of BOM lines.</span></span> <span data-ttu-id="e1ae1-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="e1ae1-106">Ez az hetedik eljárás a nyolcból, amely a dimenzión alapuló konfiguráció-kombinációk létrehozását ismerteti.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-106">This is the seventh procedure out of eight that explains how to build combinations for dimension-based configuration.</span></span>

1. <span data-ttu-id="e1ae1-107">Ugorjon a Termékinformációk kezelése > Anyagjegyzékek és képletek > Anyagjegyzékek pontra.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-107">Go to Product information management > Bills of materials and formulas > Bills of materials.</span></span>
2. <span data-ttu-id="e1ae1-108">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="e1ae1-109">Keresse meg és válassza ki a Dimenzión alapuló konfiguráció BOM-ját.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-109">Find and select the BOM for the dimension-based configuration.</span></span>  
3. <span data-ttu-id="e1ae1-110">A Művelet ablaktáblában kattintson a Beállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-110">On the Action Pane, click Options.</span></span>
4. <span data-ttu-id="e1ae1-111">Kattintson a Nézetváltás elemre.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-111">Click Change view.</span></span>
5. <span data-ttu-id="e1ae1-112">Kattintson a Fejlécnézet gombra.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-112">Click Header view.</span></span>
    * <span data-ttu-id="e1ae1-113">A konfigurációs útvonal gyorslapjának eléréséhez nyissa meg a fejléc nézetet.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-113">Open the header view to access the Configuration route FastTab.</span></span>  
6. <span data-ttu-id="e1ae1-114">Bontsa ki vagy csukja össze a Konfigurációs útvonal szakaszát.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-114">Expand or collapse the Configuration route section.</span></span>
    * <span data-ttu-id="e1ae1-115">A konfigurációs útvonal gyorslapjának bővített módban kell lennie.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-115">The Configuration route FastTab must be in the expanded mode.</span></span>  
7. <span data-ttu-id="e1ae1-116">Kattintson a Konfigurációs szabályok elemre.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-116">Click Configuration rules.</span></span>
8. <span data-ttu-id="e1ae1-117">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-117">Click New.</span></span>
9. <span data-ttu-id="e1ae1-118">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-118">In the list, mark the selected row.</span></span>
10. <span data-ttu-id="e1ae1-119">A Cikkszám mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-119">In the Item number field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="e1ae1-120">Az aktuális konfigurációs csoport cikkei jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-120">The items in the current configuration group are displayed.</span></span> <span data-ttu-id="e1ae1-121">Jelölje ki azt, amely megjeleníti a szabály feltételét.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-121">Select the one that represents the condition in the rule.</span></span>  
11. <span data-ttu-id="e1ae1-122">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-122">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="e1ae1-123">Válassza ki valamelyik lehetőséget a Módszer mezőben.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-123">In the Method field, select an option.</span></span>
    * <span data-ttu-id="e1ae1-124">Lehetősége van egy másik konfigurációs csoportban szereplő cikk kijelölésének vagy a kijelölés visszavonásának az érvényesítésére.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-124">It is possible to enforce either a selection or a deselection of an item from another configuration group.</span></span>  
13. <span data-ttu-id="e1ae1-125">A Származtatott csoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-125">In the Derived group field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="e1ae1-126">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-126">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="e1ae1-127">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-127">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="e1ae1-128">Válassza ki a kívánt konfigurációs csoportot.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-128">Select the desired configuration group.</span></span>  
16. <span data-ttu-id="e1ae1-129">A Származtatott cikkszám mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-129">In the Derived item number field, click the drop-down button to open the lookup.</span></span>
17. <span data-ttu-id="e1ae1-130">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-130">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="e1ae1-131">Válassza ki azt a cikkszámot, amelyet a megadott módszertől függően kijelöl vagy eltávolít.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-131">Select the item number that will be either selected or deselected depending on the chosen method.</span></span>  
18. <span data-ttu-id="e1ae1-132">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-132">Close the page.</span></span>

