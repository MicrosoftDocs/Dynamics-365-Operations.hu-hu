--- 
title: "Adatbevitel megkönnyítése érdekében rekordsablon létrehozása"
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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 6f8d804133f8e9c6f47420d41df8d9430381e2fe
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-record-template-to-facilitate-data-entry"></a><span data-ttu-id="702cd-103">Adatbevitel megkönnyítése érdekében rekordsablon létrehozása</span><span class="sxs-lookup"><span data-stu-id="702cd-103">Create a record template to facilitate data entry</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="702cd-104">Ez az eljárás bemutatja, hogyan hozható létre rekordsablon azért, hogy a gyakran használt mezőértékeket ne kelljen minden új rekordhoz explicit módon megadni.</span><span class="sxs-lookup"><span data-stu-id="702cd-104">This procedure demonstrates how to create a record template so that field values that are used often do not have to be entered explicitly for each new record.</span></span> <span data-ttu-id="702cd-105">Ezzel a műveletsorral létrehoz egy új rekordot az új laptokhoz, amelyeket fel kell venni a tárgyi eszközök közé.</span><span class="sxs-lookup"><span data-stu-id="702cd-105">In this procedure, you’ll create a new record for new laptops that should be added to your fixed assets.</span></span> <span data-ttu-id="702cd-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="702cd-106">This procedure uses the USMF sample company.</span></span>

1. <span data-ttu-id="702cd-107">Nyissa meg a következőt: Tárgyi eszközök > Tárgyi eszközök > Tárgyi eszközök.</span><span class="sxs-lookup"><span data-stu-id="702cd-107">Go to Fixed assets > Fixed assets > Fixed assets.</span></span>
2. <span data-ttu-id="702cd-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="702cd-108">Click New.</span></span>
3. <span data-ttu-id="702cd-109">A Tárgyieszköz-csoport mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="702cd-109">In the Fixed asset group field, enter or select a value.</span></span>
4. <span data-ttu-id="702cd-110">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="702cd-110">In the Name field, type a value.</span></span>
    * <span data-ttu-id="702cd-111">Adja meg például a következőt: „Vállalati vezetői laptop”.</span><span class="sxs-lookup"><span data-stu-id="702cd-111">For example, enter 'Corporate lead laptop'.</span></span>  
5. <span data-ttu-id="702cd-112">Írjon be egy értéket a Keresési név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="702cd-112">In the Search name field, type a value.</span></span>
    * <span data-ttu-id="702cd-113">Adja meg például a következőt: „laptop”.</span><span class="sxs-lookup"><span data-stu-id="702cd-113">For example, enter 'laptop.'</span></span>  
6. <span data-ttu-id="702cd-114">Bontsa ki a Technikai információ szakaszt.</span><span class="sxs-lookup"><span data-stu-id="702cd-114">Expand the Technical information section.</span></span>
7. <span data-ttu-id="702cd-115">A Gyártmány mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="702cd-115">In the Make field, type a value.</span></span>
8. <span data-ttu-id="702cd-116">A Modell mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="702cd-116">In the Model field, type a value.</span></span>
9. <span data-ttu-id="702cd-117">A Modellév mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="702cd-117">In the Model year field, type a value.</span></span>
10. <span data-ttu-id="702cd-118">A Művelet ablaktáblában kattintson a Beállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="702cd-118">On the Action Pane, click Options.</span></span>
11. <span data-ttu-id="702cd-119">Kattintson a Rekord adatai lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="702cd-119">Click Record info.</span></span>
12. <span data-ttu-id="702cd-120">Kattintson a Felhasználói sablon lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="702cd-120">Click User template.</span></span>
13. <span data-ttu-id="702cd-121">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="702cd-121">In the Name field, type a value.</span></span>
    * <span data-ttu-id="702cd-122">Adja meg például a következőt: „Vállalati laptop”.</span><span class="sxs-lookup"><span data-stu-id="702cd-122">For example, enter 'Corporate laptop.'</span></span>  
14. <span data-ttu-id="702cd-123">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="702cd-123">In the Description field, type a value.</span></span>
    * <span data-ttu-id="702cd-124">Adja meg például a következőt: „Vállalati laptop”.</span><span class="sxs-lookup"><span data-stu-id="702cd-124">For example, enter 'Corporate laptop'.</span></span>  
15. <span data-ttu-id="702cd-125">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="702cd-125">Click OK.</span></span>
16. <span data-ttu-id="702cd-126">Kattintson a Bezárás gombra.</span><span class="sxs-lookup"><span data-stu-id="702cd-126">Click Close.</span></span>


