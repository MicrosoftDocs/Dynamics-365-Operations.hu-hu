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
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a0d7092228f078f528ec1cb9ac56d7034c44bccf
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1567883"
---
# <a name="maintain-barcode-types"></a><span data-ttu-id="5dbcd-103">Vonalkódtípusok karbantartása</span><span class="sxs-lookup"><span data-stu-id="5dbcd-103">Maintain barcode types</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5dbcd-104">Ez az eljárás bemutatja, hogyan állíthat be egy új vonalkód-definíciót, amelyet a kitárolási lista jelentés részeként fel lehet használni.</span><span class="sxs-lookup"><span data-stu-id="5dbcd-104">This procedure shows you how to set up a new barcode definition which can then be used as part of the picking list report.</span></span> <span data-ttu-id="5dbcd-105">Ezt a folyamatot az USMF bemutatócégen vagy saját adata használatával is elvégezheti.</span><span class="sxs-lookup"><span data-stu-id="5dbcd-105">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="5dbcd-106">A USMF használata esetén alkalmazhatja az itt megjelenő, példa jellegű értékeket.</span><span class="sxs-lookup"><span data-stu-id="5dbcd-106">If you are using USMF you can use the example values that are shown.</span></span> <span data-ttu-id="5dbcd-107">Ezeket a feladatokat jellemzően egy raktári vezető végzi el.</span><span class="sxs-lookup"><span data-stu-id="5dbcd-107">These tasks would typically be carried out by a warehouse manager.</span></span>

1. <span data-ttu-id="5dbcd-108">Ugrás a vonalkódokhoz.</span><span class="sxs-lookup"><span data-stu-id="5dbcd-108">Go to Bar codes.</span></span>
2. <span data-ttu-id="5dbcd-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5dbcd-109">Click New.</span></span>
3. <span data-ttu-id="5dbcd-110">Érték beírása a Vonalkód beállítása mezőbe.</span><span class="sxs-lookup"><span data-stu-id="5dbcd-110">In the Barcode setup field, type a value.</span></span>
4. <span data-ttu-id="5dbcd-111">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5dbcd-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="5dbcd-112">A Vonalkódtípus mezőben válasszon ki egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5dbcd-112">In the Bar code type field, select an option.</span></span>
    * <span data-ttu-id="5dbcd-113">Az USMF használata esetén választhatja az „39-es kódot”.</span><span class="sxs-lookup"><span data-stu-id="5dbcd-113">If you're using USMF, you can select 'Code 39'.</span></span>  
6. <span data-ttu-id="5dbcd-114">Adjon meg egy számot a Méret mezőben.</span><span class="sxs-lookup"><span data-stu-id="5dbcd-114">In the Size field, enter a number.</span></span>
7. <span data-ttu-id="5dbcd-115">Adjon meg egy számot a Maximális hossz mezőben.</span><span class="sxs-lookup"><span data-stu-id="5dbcd-115">In the Maximum length field, enter a number.</span></span>
8. <span data-ttu-id="5dbcd-116">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="5dbcd-116">Click Save.</span></span>
9. <span data-ttu-id="5dbcd-117">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5dbcd-117">Close the page.</span></span>
10. <span data-ttu-id="5dbcd-118">Ugrás a készlet- és raktárkezelési paraméterekhez.</span><span class="sxs-lookup"><span data-stu-id="5dbcd-118">Go to Inventory and warehouse management parameters.</span></span>
11. <span data-ttu-id="5dbcd-119">A Vonalkódbeállítás mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5dbcd-119">In the Barcode setup field, enter or select a value.</span></span>
    * <span data-ttu-id="5dbcd-120">Válassza ki a korábban létrehozott vonalkód beállítást, de figyeljen arra, hogy a vonalkód formátumnak egyeznie kell a folyamatban használt rekord egyedi azonosítójával.</span><span class="sxs-lookup"><span data-stu-id="5dbcd-120">Select the barcode setup that you created before, but be aware that the bar code format must match the format of the unique identifier for the record type used in the process.</span></span> <span data-ttu-id="5dbcd-121">Például a kitárolási útvonalakhoz, a vonalkód formátumnak egyeznie kell a kitárolási útvonal hivatkozásával, amely általában egy számsorozat.</span><span class="sxs-lookup"><span data-stu-id="5dbcd-121">For example, for picking routes, the bar code format should match the format of the picking route reference, which is typically a number sequence.</span></span>  
12. <span data-ttu-id="5dbcd-122">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="5dbcd-122">Click Save.</span></span>
13. <span data-ttu-id="5dbcd-123">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5dbcd-123">Close the page.</span></span>

