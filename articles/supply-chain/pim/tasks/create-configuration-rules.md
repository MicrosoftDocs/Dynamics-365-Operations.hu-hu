--- 
title: "Konfigurációs szabályok létrehozása"
description: "Ez az eljárás olyan konfigurációs szabályokat hoz létre, amelyeket a dimenzión alapuló konfigurációkhoz használhat fel az anyagjegyzék bizonyos kombinációinak betartására vagy megakadályozására."
author: YuyuScheller
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 0abe7a8ef1c8d4053b341f6c0117f400492a3808
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---
# <a name="create-configuration-rules"></a><span data-ttu-id="d06bd-103">Konfigurációs szabályok létrehozása</span><span class="sxs-lookup"><span data-stu-id="d06bd-103">Create configuration rules</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d06bd-104">Ez az eljárás olyan konfigurációs szabályokat hoz létre, amelyeket a dimenzión alapuló konfigurációkhoz használhat fel az anyagjegyzék bizonyos kombinációinak betartására vagy megakadályozására.</span><span class="sxs-lookup"><span data-stu-id="d06bd-104">This procedure creates configuration rules that can be used for dimension-based configuration to enforce or prevent certain combinations of BOM lines.</span></span> <span data-ttu-id="d06bd-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="d06bd-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="d06bd-106">Ez az hetedik eljárás a nyolcból, amely a dimenzión alapuló konfiguráció-kombinációk létrehozását ismerteti.</span><span class="sxs-lookup"><span data-stu-id="d06bd-106">This is the seventh procedure out of eight that explains how to build combinations for dimension-based configuration.</span></span>

1. <span data-ttu-id="d06bd-107">Ugorjon a Termékinformációk kezelése > Anyagjegyzékek és képletek > Anyagjegyzékek pontra.</span><span class="sxs-lookup"><span data-stu-id="d06bd-107">Go to Product information management > Bills of materials and formulas > Bills of materials.</span></span>
2. <span data-ttu-id="d06bd-108">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="d06bd-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="d06bd-109">Keresse meg és válassza ki a Dimenzión alapuló konfiguráció BOM-ját.</span><span class="sxs-lookup"><span data-stu-id="d06bd-109">Find and select the BOM for the dimension-based configuration.</span></span>  
3. <span data-ttu-id="d06bd-110">A Művelet ablaktáblában kattintson a Beállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="d06bd-110">On the Action Pane, click Options.</span></span>
4. <span data-ttu-id="d06bd-111">Kattintson a Nézetváltás elemre.</span><span class="sxs-lookup"><span data-stu-id="d06bd-111">Click Change view.</span></span>
5. <span data-ttu-id="d06bd-112">Kattintson a Fejlécnézet gombra.</span><span class="sxs-lookup"><span data-stu-id="d06bd-112">Click Header view.</span></span>
    * <span data-ttu-id="d06bd-113">A konfigurációs útvonal gyorslapjának eléréséhez nyissa meg a fejléc nézetet.</span><span class="sxs-lookup"><span data-stu-id="d06bd-113">Open the header view to access the Configuration route FastTab.</span></span>  
6. <span data-ttu-id="d06bd-114">Bontsa ki vagy csukja össze a Konfigurációs útvonal szakaszát.</span><span class="sxs-lookup"><span data-stu-id="d06bd-114">Expand or collapse the Configuration route section.</span></span>
    * <span data-ttu-id="d06bd-115">A konfigurációs útvonal gyorslapjának bővített módban kell lennie.</span><span class="sxs-lookup"><span data-stu-id="d06bd-115">The Configuration route FastTab must be in the expanded mode.</span></span>  
7. <span data-ttu-id="d06bd-116">Kattintson a Konfigurációs szabályok elemre.</span><span class="sxs-lookup"><span data-stu-id="d06bd-116">Click Configuration rules.</span></span>
8. <span data-ttu-id="d06bd-117">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d06bd-117">Click New.</span></span>
9. <span data-ttu-id="d06bd-118">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="d06bd-118">In the list, mark the selected row.</span></span>
10. <span data-ttu-id="d06bd-119">A Cikkszám mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d06bd-119">In the Item number field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="d06bd-120">Az aktuális konfigurációs csoport cikkei jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="d06bd-120">The items in the current configuration group are displayed.</span></span> <span data-ttu-id="d06bd-121">Jelölje ki azt, amely megjeleníti a szabály feltételét.</span><span class="sxs-lookup"><span data-stu-id="d06bd-121">Select the one that represents the condition in the rule.</span></span>  
11. <span data-ttu-id="d06bd-122">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="d06bd-122">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="d06bd-123">Válassza ki valamelyik lehetőséget a Módszer mezőben.</span><span class="sxs-lookup"><span data-stu-id="d06bd-123">In the Method field, select an option.</span></span>
    * <span data-ttu-id="d06bd-124">Lehetősége van egy másik konfigurációs csoportban szereplő cikk kijelölésének vagy a kijelölés visszavonásának az érvényesítésére.</span><span class="sxs-lookup"><span data-stu-id="d06bd-124">It is possible to enforce either a selection or a deselection of an item from another configuration group.</span></span>  
13. <span data-ttu-id="d06bd-125">A Származtatott csoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d06bd-125">In the Derived group field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="d06bd-126">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="d06bd-126">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="d06bd-127">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="d06bd-127">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="d06bd-128">Válassza ki a kívánt konfigurációs csoportot.</span><span class="sxs-lookup"><span data-stu-id="d06bd-128">Select the desired configuration group.</span></span>  
16. <span data-ttu-id="d06bd-129">A Származtatott cikkszám mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d06bd-129">In the Derived item number field, click the drop-down button to open the lookup.</span></span>
17. <span data-ttu-id="d06bd-130">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="d06bd-130">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="d06bd-131">Válassza ki azt a cikkszámot, amelyet a megadott módszertől függően kijelöl vagy eltávolít.</span><span class="sxs-lookup"><span data-stu-id="d06bd-131">Select the item number that will be either selected or deselected depending on the chosen method.</span></span>  
18. <span data-ttu-id="d06bd-132">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d06bd-132">Close the page.</span></span>


