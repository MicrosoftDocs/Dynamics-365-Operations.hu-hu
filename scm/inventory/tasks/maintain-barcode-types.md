---
title: "Vonalkódtípusok kezelése"
description: "Ez az eljárás bemutatja, hogyan állíthat be egy új vonalkód-definíciót, amelyet a kitárolási lista jelentés részeként fel lehet használni."
author: perlynne
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0e7f66cccd76e5326fce75d1a13aff294c16fb9b
ms.openlocfilehash: 45323206550d1b0ed66d89f4be7b995c60af63fc
ms.contentlocale: hu-hu
ms.lasthandoff: 09/12/2017

---
# <a name="maintain-bar-code-types"></a><span data-ttu-id="430bd-103">Vonalkódtípusok kezelése</span><span class="sxs-lookup"><span data-stu-id="430bd-103">Maintain bar code types</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="430bd-104">Ez az eljárás bemutatja, hogyan állíthat be egy új vonalkód-definíciót, amelyet a kitárolási lista jelentés részeként fel lehet használni.</span><span class="sxs-lookup"><span data-stu-id="430bd-104">This procedure shows you how to set up a new barcode definition which can then be used as part of the picking list report.</span></span> <span data-ttu-id="430bd-105">Ezt a folyamatot az USMF bemutatócégen vagy saját adata használatával is elvégezheti.</span><span class="sxs-lookup"><span data-stu-id="430bd-105">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="430bd-106">A USMF használata esetén alkalmazhatja az itt megjelenő, példa jellegű értékeket.</span><span class="sxs-lookup"><span data-stu-id="430bd-106">If you are using USMF you can use the example values that are shown.</span></span> <span data-ttu-id="430bd-107">Ezeket a feladatokat jellemzően egy raktári vezető végzi el.</span><span class="sxs-lookup"><span data-stu-id="430bd-107">These tasks would typically be carried out by a warehouse manager.</span></span>

1. <span data-ttu-id="430bd-108">Ugrás a vonalkódokhoz.</span><span class="sxs-lookup"><span data-stu-id="430bd-108">Go to Bar codes.</span></span>
2. <span data-ttu-id="430bd-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="430bd-109">Click New.</span></span>
3. <span data-ttu-id="430bd-110">Érték beírása a Vonalkód beállítása mezőbe.</span><span class="sxs-lookup"><span data-stu-id="430bd-110">In the Barcode setup field, type a value.</span></span>
4. <span data-ttu-id="430bd-111">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="430bd-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="430bd-112">A Vonalkódtípus mezőben válasszon ki egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="430bd-112">In the Bar code type field, select an option.</span></span>
    * <span data-ttu-id="430bd-113">Az USMF használata esetén választhatja az „39-es kódot”.</span><span class="sxs-lookup"><span data-stu-id="430bd-113">If you're using USMF, you can select 'Code 39'.</span></span>  
6. <span data-ttu-id="430bd-114">Adjon meg egy számot a Méret mezőben.</span><span class="sxs-lookup"><span data-stu-id="430bd-114">In the Size field, enter a number.</span></span>
7. <span data-ttu-id="430bd-115">Adjon meg egy számot a Maximális hossz mezőben.</span><span class="sxs-lookup"><span data-stu-id="430bd-115">In the Maximum length field, enter a number.</span></span>
8. <span data-ttu-id="430bd-116">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="430bd-116">Click Save.</span></span>
9. <span data-ttu-id="430bd-117">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="430bd-117">Close the page.</span></span>
10. <span data-ttu-id="430bd-118">Ugrás a készlet- és raktárkezelési paraméterekhez.</span><span class="sxs-lookup"><span data-stu-id="430bd-118">Go to Inventory and warehouse management parameters.</span></span>
11. <span data-ttu-id="430bd-119">A Vonalkódbeállítás mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="430bd-119">In the Barcode setup field, enter or select a value.</span></span>
    * <span data-ttu-id="430bd-120">Válassza ki a korábban létrehozott vonalkód beállítást, de figyeljen arra, hogy a vonalkód formátumnak egyeznie kell a folyamatban használt rekord egyedi azonosítójával.</span><span class="sxs-lookup"><span data-stu-id="430bd-120">Select the barcode setup that you created before, but be aware that the bar code format must match the format of the unique identifier for the record type used in the process.</span></span> <span data-ttu-id="430bd-121">Például a kitárolási útvonalakhoz, a vonalkód formátumnak egyeznie kell a kitárolási útvonal hivatkozásával, amely általában egy számsorozat.</span><span class="sxs-lookup"><span data-stu-id="430bd-121">For example, for picking routes, the bar code format should match the format of the picking route reference, which is typically a number sequence.</span></span>  
12. <span data-ttu-id="430bd-122">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="430bd-122">Click Save.</span></span>
13. <span data-ttu-id="430bd-123">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="430bd-123">Close the page.</span></span>

