---
title: Vonalkód létrehozása termékhez
description: Ez az eljárás bemutatja, hogyan hozható létre manuálisan vonalkód, példaként az M0001 cikkszám használatával.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, EcoResProductDetailsExtended, InventItemBarcode, InventItemBarcodeLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2ae2765a125045d60566267d01e380069d5d527c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1568604"
---
# <a name="create-a-bar-code-for-a-product"></a><span data-ttu-id="b27f4-103">Vonalkód létrehozása termékhez</span><span class="sxs-lookup"><span data-stu-id="b27f4-103">Create a bar code for a product</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b27f4-104">Ez az eljárás bemutatja, hogyan hozható létre manuálisan vonalkód, példaként az M0001 cikkszám használatával.</span><span class="sxs-lookup"><span data-stu-id="b27f4-104">This procedure shows how to manually create a bar code using the item number M0001 as an example.</span></span> <span data-ttu-id="b27f4-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="b27f4-105">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="b27f4-106">Kattintson a Kiadott termék karbantartása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b27f4-106">Click Released product maintenance.</span></span>
2. <span data-ttu-id="b27f4-107">Kattintson a Kibocsátott termék lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b27f4-107">Click Released products.</span></span>
3. <span data-ttu-id="b27f4-108">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="b27f4-108">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="b27f4-109">A Művelet panelen kattintson a Készletkezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="b27f4-109">On the Action Pane, click Manage inventory.</span></span>
5. <span data-ttu-id="b27f4-110">Kattintson a Vonalkódok elemre.</span><span class="sxs-lookup"><span data-stu-id="b27f4-110">Click Bar codes.</span></span>
6. <span data-ttu-id="b27f4-111">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="b27f4-111">Click New.</span></span>
7. <span data-ttu-id="b27f4-112">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="b27f4-112">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="b27f4-113">A Vonalkódbeállítás mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="b27f4-113">In the Barcode setup field, enter or select a value.</span></span>
9. <span data-ttu-id="b27f4-114">A Vonalkód mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="b27f4-114">In the Bar code field, enter or select a value.</span></span>
10. <span data-ttu-id="b27f4-115">A Vonalkód mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="b27f4-115">In the Bar code field, type a value.</span></span>
    * <span data-ttu-id="b27f4-116">Nyomja le a Tab gombot.</span><span class="sxs-lookup"><span data-stu-id="b27f4-116">Press the Tab key.</span></span>  
11. <span data-ttu-id="b27f4-117">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b27f4-117">Close the page.</span></span>
12. <span data-ttu-id="b27f4-118">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="b27f4-118">In the Quantity field, enter a number.</span></span>
13. <span data-ttu-id="b27f4-119">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="b27f4-119">Click Save.</span></span>
    * <span data-ttu-id="b27f4-120">Amikor a Mentés gombra kattint, lefut a vonalkód-ellenőrzés, és ebben az esetben megjelenik egy hibaüzenet, miszerint a várt ellenőrző számjegy 8, de az értékben 3 szerepel.</span><span class="sxs-lookup"><span data-stu-id="b27f4-120">When you click Save, the barcode check is run, and in this case it will display an error stating that the expected check digit is 8, but that 3 was found.</span></span> <span data-ttu-id="b27f4-121">A vonalkód számát manuálisan frissítse úgy, hogy 8 legyen a vége.</span><span class="sxs-lookup"><span data-stu-id="b27f4-121">Manually update the barcode number so that 8 is at the end.</span></span>  
14. <span data-ttu-id="b27f4-122">A Vonalkód mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="b27f4-122">In the Bar code field, enter or select a value.</span></span>
15. <span data-ttu-id="b27f4-123">A Vonalkód mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="b27f4-123">In the Bar code field, type a value.</span></span>
    * <span data-ttu-id="b27f4-124">Nyomja le a Tab gombot.</span><span class="sxs-lookup"><span data-stu-id="b27f4-124">Press the Tab key.</span></span>  
16. <span data-ttu-id="b27f4-125">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b27f4-125">Close the page.</span></span>
17. <span data-ttu-id="b27f4-126">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="b27f4-126">Click Save.</span></span>
18. <span data-ttu-id="b27f4-127">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b27f4-127">Close the page.</span></span>

