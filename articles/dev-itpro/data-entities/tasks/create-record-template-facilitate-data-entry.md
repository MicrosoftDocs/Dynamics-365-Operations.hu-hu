--- 
title: "Adatbevitel megkönnyítése érdekében rekordsablonok létrehozása"
description: "Ez az eljárás bemutatja, hogyan hozható létre rekordsablon azért, hogy a gyakran használt mezőértékeket ne kelljen minden új rekordhoz explicit módon megadni."
author: sericks007
manager: AnnBe
ms.date: 02/21/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: afe2da72ef6a6451e797ed6098df164e765e503e
ms.contentlocale: hu-hu
ms.lasthandoff: 08/09/2018

---
# <a name="create-record-templates-to-facilitate-data-entry"></a><span data-ttu-id="75e1b-103">Adatbevitel megkönnyítése érdekében rekordsablonok létrehozása</span><span class="sxs-lookup"><span data-stu-id="75e1b-103">Create record templates to facilitate data entry</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="75e1b-104">Ez az eljárás bemutatja, hogyan hozható létre rekordsablon azért, hogy a gyakran használt mezőértékeket ne kelljen minden új rekordhoz explicit módon megadni.</span><span class="sxs-lookup"><span data-stu-id="75e1b-104">This procedure demonstrates how to create a record template so that field values that are used often do not have to be entered explicitly for each new record.</span></span> <span data-ttu-id="75e1b-105">Ezzel a műveletsorral létrehoz egy új rekordot az új laptokhoz, amelyeket fel kell venni a tárgyi eszközök közé.</span><span class="sxs-lookup"><span data-stu-id="75e1b-105">In this procedure, you’ll create a new record for new laptops that should be added to your fixed assets.</span></span> <span data-ttu-id="75e1b-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="75e1b-106">This procedure uses the USMF sample company.</span></span>

1. <span data-ttu-id="75e1b-107">Nyissa meg a következőt: Tárgyi eszközök > Tárgyi eszközök > Tárgyi eszközök.</span><span class="sxs-lookup"><span data-stu-id="75e1b-107">Go to Fixed assets > Fixed assets > Fixed assets.</span></span>
2. <span data-ttu-id="75e1b-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="75e1b-108">Click New.</span></span>
3. <span data-ttu-id="75e1b-109">A Tárgyieszköz-csoport mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="75e1b-109">In the Fixed asset group field, enter or select a value.</span></span>
4. <span data-ttu-id="75e1b-110">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="75e1b-110">In the Name field, type a value.</span></span>
    * <span data-ttu-id="75e1b-111">Adja meg például a következőt: „Vállalati vezetői laptop”.</span><span class="sxs-lookup"><span data-stu-id="75e1b-111">For example, enter 'Corporate lead laptop'.</span></span>  
5. <span data-ttu-id="75e1b-112">Írjon be egy értéket a Keresési név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="75e1b-112">In the Search name field, type a value.</span></span>
    * <span data-ttu-id="75e1b-113">Adja meg például a következőt: „laptop”.</span><span class="sxs-lookup"><span data-stu-id="75e1b-113">For example, enter 'laptop.'</span></span>  
6. <span data-ttu-id="75e1b-114">Bontsa ki a Technikai információ szakaszt.</span><span class="sxs-lookup"><span data-stu-id="75e1b-114">Expand the Technical information section.</span></span>
7. <span data-ttu-id="75e1b-115">A Gyártmány mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="75e1b-115">In the Make field, type a value.</span></span>
8. <span data-ttu-id="75e1b-116">A Modell mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="75e1b-116">In the Model field, type a value.</span></span>
9. <span data-ttu-id="75e1b-117">A Modellév mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="75e1b-117">In the Model year field, type a value.</span></span>
10. <span data-ttu-id="75e1b-118">A Művelet ablaktáblában kattintson a Beállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="75e1b-118">On the Action Pane, click Options.</span></span>
11. <span data-ttu-id="75e1b-119">Kattintson a Rekord adatai lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="75e1b-119">Click Record info.</span></span>
12. <span data-ttu-id="75e1b-120">Kattintson a Felhasználói sablon lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="75e1b-120">Click User template.</span></span>
13. <span data-ttu-id="75e1b-121">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="75e1b-121">In the Name field, type a value.</span></span>
    * <span data-ttu-id="75e1b-122">Adja meg például a következőt: „Vállalati laptop”.</span><span class="sxs-lookup"><span data-stu-id="75e1b-122">For example, enter 'Corporate laptop.'</span></span>  
14. <span data-ttu-id="75e1b-123">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="75e1b-123">In the Description field, type a value.</span></span>
    * <span data-ttu-id="75e1b-124">Adja meg például a következőt: „Vállalati laptop”.</span><span class="sxs-lookup"><span data-stu-id="75e1b-124">For example, enter 'Corporate laptop'.</span></span>  
15. <span data-ttu-id="75e1b-125">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="75e1b-125">Click OK.</span></span>
16. <span data-ttu-id="75e1b-126">Kattintson a Bezárás gombra.</span><span class="sxs-lookup"><span data-stu-id="75e1b-126">Click Close.</span></span>


