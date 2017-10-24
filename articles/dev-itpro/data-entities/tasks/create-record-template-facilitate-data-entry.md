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
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 6f8d804133f8e9c6f47420d41df8d9430381e2fe
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-record-template-to-facilitate-data-entry"></a><span data-ttu-id="04971-103">Adatbevitel megkönnyítése érdekében rekordsablon létrehozása</span><span class="sxs-lookup"><span data-stu-id="04971-103">Create a record template to facilitate data entry</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="04971-104">Ez az eljárás bemutatja, hogyan hozható létre rekordsablon azért, hogy a gyakran használt mezőértékeket ne kelljen minden új rekordhoz explicit módon megadni.</span><span class="sxs-lookup"><span data-stu-id="04971-104">This procedure demonstrates how to create a record template so that field values that are used often do not have to be entered explicitly for each new record.</span></span> <span data-ttu-id="04971-105">Ezzel a műveletsorral létrehoz egy új rekordot az új laptokhoz, amelyeket fel kell venni a tárgyi eszközök közé.</span><span class="sxs-lookup"><span data-stu-id="04971-105">In this procedure, you’ll create a new record for new laptops that should be added to your fixed assets.</span></span> <span data-ttu-id="04971-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="04971-106">This procedure uses the USMF sample company.</span></span>

1. <span data-ttu-id="04971-107">Nyissa meg a következőt: Tárgyi eszközök > Tárgyi eszközök > Tárgyi eszközök.</span><span class="sxs-lookup"><span data-stu-id="04971-107">Go to Fixed assets > Fixed assets > Fixed assets.</span></span>
2. <span data-ttu-id="04971-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="04971-108">Click New.</span></span>
3. <span data-ttu-id="04971-109">A Tárgyieszköz-csoport mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="04971-109">In the Fixed asset group field, enter or select a value.</span></span>
4. <span data-ttu-id="04971-110">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="04971-110">In the Name field, type a value.</span></span>
    * <span data-ttu-id="04971-111">Adja meg például a következőt: „Vállalati vezetői laptop”.</span><span class="sxs-lookup"><span data-stu-id="04971-111">For example, enter 'Corporate lead laptop'.</span></span>  
5. <span data-ttu-id="04971-112">Írjon be egy értéket a Keresési név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="04971-112">In the Search name field, type a value.</span></span>
    * <span data-ttu-id="04971-113">Adja meg például a következőt: „laptop”.</span><span class="sxs-lookup"><span data-stu-id="04971-113">For example, enter 'laptop.'</span></span>  
6. <span data-ttu-id="04971-114">Bontsa ki a Technikai információ szakaszt.</span><span class="sxs-lookup"><span data-stu-id="04971-114">Expand the Technical information section.</span></span>
7. <span data-ttu-id="04971-115">A Gyártmány mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="04971-115">In the Make field, type a value.</span></span>
8. <span data-ttu-id="04971-116">A Modell mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="04971-116">In the Model field, type a value.</span></span>
9. <span data-ttu-id="04971-117">A Modellév mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="04971-117">In the Model year field, type a value.</span></span>
10. <span data-ttu-id="04971-118">A Művelet ablaktáblában kattintson a Beállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="04971-118">On the Action Pane, click Options.</span></span>
11. <span data-ttu-id="04971-119">Kattintson a Rekord adatai lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="04971-119">Click Record info.</span></span>
12. <span data-ttu-id="04971-120">Kattintson a Felhasználói sablon lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="04971-120">Click User template.</span></span>
13. <span data-ttu-id="04971-121">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="04971-121">In the Name field, type a value.</span></span>
    * <span data-ttu-id="04971-122">Adja meg például a következőt: „Vállalati laptop”.</span><span class="sxs-lookup"><span data-stu-id="04971-122">For example, enter 'Corporate laptop.'</span></span>  
14. <span data-ttu-id="04971-123">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="04971-123">In the Description field, type a value.</span></span>
    * <span data-ttu-id="04971-124">Adja meg például a következőt: „Vállalati laptop”.</span><span class="sxs-lookup"><span data-stu-id="04971-124">For example, enter 'Corporate laptop'.</span></span>  
15. <span data-ttu-id="04971-125">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="04971-125">Click OK.</span></span>
16. <span data-ttu-id="04971-126">Kattintson a Bezárás gombra.</span><span class="sxs-lookup"><span data-stu-id="04971-126">Click Close.</span></span>


