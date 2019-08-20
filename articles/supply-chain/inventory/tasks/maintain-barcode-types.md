---
title: Vonalkódtípusok karbantartása
description: Ez az eljárás bemutatja, hogyan állíthat be egy új vonalkód-definíciót, amelyet a kitárolási lista jelentés részeként fel lehet használni.
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BarcodeSetup, InventParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0551784ff55f5dc05fbe92ee354316eb04d755cb
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845445"
---
# <a name="maintain-barcode-types"></a><span data-ttu-id="5dd79-103">Vonalkódtípusok karbantartása</span><span class="sxs-lookup"><span data-stu-id="5dd79-103">Maintain barcode types</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5dd79-104">Ez az eljárás bemutatja, hogyan állíthat be egy új vonalkód-definíciót, amelyet a kitárolási lista jelentés részeként fel lehet használni.</span><span class="sxs-lookup"><span data-stu-id="5dd79-104">This procedure shows you how to set up a new barcode definition which can then be used as part of the picking list report.</span></span> <span data-ttu-id="5dd79-105">Ezt a folyamatot az USMF bemutatócégen vagy saját adata használatával is elvégezheti.</span><span class="sxs-lookup"><span data-stu-id="5dd79-105">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="5dd79-106">A USMF használata esetén alkalmazhatja az itt megjelenő, példa jellegű értékeket.</span><span class="sxs-lookup"><span data-stu-id="5dd79-106">If you are using USMF you can use the example values that are shown.</span></span> <span data-ttu-id="5dd79-107">Ezeket a feladatokat jellemzően egy raktári vezető végzi el.</span><span class="sxs-lookup"><span data-stu-id="5dd79-107">These tasks would typically be carried out by a warehouse manager.</span></span>

1. <span data-ttu-id="5dd79-108">Ugrás a vonalkódokhoz.</span><span class="sxs-lookup"><span data-stu-id="5dd79-108">Go to Bar codes.</span></span>
2. <span data-ttu-id="5dd79-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5dd79-109">Click New.</span></span>
3. <span data-ttu-id="5dd79-110">Érték beírása a Vonalkód beállítása mezőbe.</span><span class="sxs-lookup"><span data-stu-id="5dd79-110">In the Barcode setup field, type a value.</span></span>
4. <span data-ttu-id="5dd79-111">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5dd79-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="5dd79-112">A Vonalkódtípus mezőben válasszon ki egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5dd79-112">In the Bar code type field, select an option.</span></span>
    * <span data-ttu-id="5dd79-113">Az USMF használata esetén választhatja az „39-es kódot”.</span><span class="sxs-lookup"><span data-stu-id="5dd79-113">If you're using USMF, you can select 'Code 39'.</span></span>  
6. <span data-ttu-id="5dd79-114">Adjon meg egy számot a Méret mezőben.</span><span class="sxs-lookup"><span data-stu-id="5dd79-114">In the Size field, enter a number.</span></span>
7. <span data-ttu-id="5dd79-115">Adjon meg egy számot a Maximális hossz mezőben.</span><span class="sxs-lookup"><span data-stu-id="5dd79-115">In the Maximum length field, enter a number.</span></span>
8. <span data-ttu-id="5dd79-116">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="5dd79-116">Click Save.</span></span>
9. <span data-ttu-id="5dd79-117">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5dd79-117">Close the page.</span></span>
10. <span data-ttu-id="5dd79-118">Ugrás a készlet- és raktárkezelési paraméterekhez.</span><span class="sxs-lookup"><span data-stu-id="5dd79-118">Go to Inventory and warehouse management parameters.</span></span>
11. <span data-ttu-id="5dd79-119">A Vonalkódbeállítás mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5dd79-119">In the Barcode setup field, enter or select a value.</span></span>
    * <span data-ttu-id="5dd79-120">Válassza ki a korábban létrehozott vonalkód beállítást, de figyeljen arra, hogy a vonalkód formátumnak egyeznie kell a folyamatban használt rekord egyedi azonosítójával.</span><span class="sxs-lookup"><span data-stu-id="5dd79-120">Select the barcode setup that you created before, but be aware that the bar code format must match the format of the unique identifier for the record type used in the process.</span></span> <span data-ttu-id="5dd79-121">Például a kitárolási útvonalakhoz, a vonalkód formátumnak egyeznie kell a kitárolási útvonal hivatkozásával, amely általában egy számsorozat.</span><span class="sxs-lookup"><span data-stu-id="5dd79-121">For example, for picking routes, the bar code format should match the format of the picking route reference, which is typically a number sequence.</span></span>  
12. <span data-ttu-id="5dd79-122">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="5dd79-122">Click Save.</span></span>
13. <span data-ttu-id="5dd79-123">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5dd79-123">Close the page.</span></span>

