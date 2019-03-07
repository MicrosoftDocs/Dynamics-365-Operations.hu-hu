---
title: Pénzügyi dimenziók meghatározása
description: Ez a feladat-útmutató bemutatja az entitás által támogatott pénzügyi dimenzió és egyéni pénzügyi dimenzió hozzáadását.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionDetails,  DimensionAttributeTableExtensionActivate, DimensionValueDetails
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 20a7781486c6e0612c27af02a1bccbc48c55a932
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "353793"
---
# <a name="define-financial-dimensions"></a><span data-ttu-id="8756e-103">Pénzügyi dimenziók meghatározása</span><span class="sxs-lookup"><span data-stu-id="8756e-103">Define financial dimensions</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8756e-104">Ez a feladat-útmutató bemutatja az entitás által támogatott pénzügyi dimenzió és egyéni pénzügyi dimenzió hozzáadását.</span><span class="sxs-lookup"><span data-stu-id="8756e-104">This task guide demonstrates adding an entity backed financial dimension and a custom financial dimension.</span></span>  <span data-ttu-id="8756e-105">Az útmutató az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="8756e-105">The guide uses the USMF demo company.</span></span>


## <a name="create-an-entity-backed-financial-dimension"></a><span data-ttu-id="8756e-106">Entitás által biztosított pénzügyi dimenzió létrehozása</span><span class="sxs-lookup"><span data-stu-id="8756e-106">Create an entity backed financial dimension</span></span>
1. <span data-ttu-id="8756e-107">Ugrás a következő útvonalra: Főkönyv > Számlatükör > Dimenziók > Pénzügyi dimenziók.</span><span class="sxs-lookup"><span data-stu-id="8756e-107">Go to General ledger > Chart of accounts > Dimensions > Financial dimensions.</span></span>
2. <span data-ttu-id="8756e-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8756e-108">Click New.</span></span>
3. <span data-ttu-id="8756e-109">A pénzügyi dimenzió alapjául a Felhasználói értékek forrása mezőben jelöljön ki egy rendszer által definiált entitást.</span><span class="sxs-lookup"><span data-stu-id="8756e-109">In the User values from field, select a system-defined entity to base the financial dimension on.</span></span> 
4. <span data-ttu-id="8756e-110">A Dimenzió neve mezőbe írjon be egy értéket a pénzügyi dimenzió leírásához.</span><span class="sxs-lookup"><span data-stu-id="8756e-110">In the Dimension name field, type a value to describe the financial dimension.</span></span>
    * <span data-ttu-id="8756e-111">A név eltérhet a rendszer által meghatározott entitástól, de nem tartalmazhat szóközt vagy különleges karaktert.</span><span class="sxs-lookup"><span data-stu-id="8756e-111">The name can be different than the system-defined entity but cannot contain spaces or special characters.</span></span>  
5. <span data-ttu-id="8756e-112">Kattintson az Aktiválás gombra.</span><span class="sxs-lookup"><span data-stu-id="8756e-112">Click Activate.</span></span>
    * <span data-ttu-id="8756e-113">A pénzügyi dimenzió aktiválásával frissítheti a pénzügyi dimenzió nevét tartalmazó táblázatot, és eltávolíthatja a törölt dimenziókat.</span><span class="sxs-lookup"><span data-stu-id="8756e-113">Activating the financial dimension updates the table with the financial dimension name and removes deleted dimensions.</span></span> <span data-ttu-id="8756e-114">A pénzügyi dimenziók aktiválása előtt megadhat dimenzióértékeket, de a pénzügyi dimenzió nem használható, amíg nincs aktiválva.</span><span class="sxs-lookup"><span data-stu-id="8756e-114">You can enter dimension values before you activate a financial dimension, but a financial dimension cannot be used until it is activated.</span></span>  
6. <span data-ttu-id="8756e-115">Kattintson a Bezárás gombra az aktiváló üzeneten.</span><span class="sxs-lookup"><span data-stu-id="8756e-115">Click Close on the activation message.</span></span>
7. <span data-ttu-id="8756e-116">Kattintson az Aktiválás gombra.</span><span class="sxs-lookup"><span data-stu-id="8756e-116">Click Activate.</span></span>
    * <span data-ttu-id="8756e-117">Megadhatja, hogy a dimenzió aktiválását egy adott napon és időpontban szeretné futtatni, kötegelt módon.</span><span class="sxs-lookup"><span data-stu-id="8756e-117">Dimension activation can be scheduled to run by batch at a specific date and time.</span></span>  
8. <span data-ttu-id="8756e-118">Kattintson a Dimenzióértékek elemre.</span><span class="sxs-lookup"><span data-stu-id="8756e-118">Click Dimension values.</span></span>
    * <span data-ttu-id="8756e-119">Néhány dimenzióérték vállalatspecifikus érték.</span><span class="sxs-lookup"><span data-stu-id="8756e-119">Some dimension values are company specific.</span></span> <span data-ttu-id="8756e-120">Ellenőrizheti, hogy vállalatspecifikusak-e, ha a vállalat neve megjelenik a dimenzióértékek listájában.</span><span class="sxs-lookup"><span data-stu-id="8756e-120">You can verify if they are company specific by if the company name is showing in the dimension values list.</span></span>  

## <a name="create-a-custom-financial-dimension"></a><span data-ttu-id="8756e-121">Egyéni pénzügyi dimenzió létrehozása</span><span class="sxs-lookup"><span data-stu-id="8756e-121">Create a custom financial dimension</span></span>
1. <span data-ttu-id="8756e-122">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="8756e-122">Close the page.</span></span>
2. <span data-ttu-id="8756e-123">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8756e-123">Click New.</span></span>
3. <span data-ttu-id="8756e-124">Az Értékek forrása mezőben válassza a(z) <Custom dimension> lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8756e-124">In the Use values from field, select <Custom dimension>.</span></span>
4. <span data-ttu-id="8756e-125">A Dimenzió neve mezőbe írjon be egy értéket a pénzügyi dimenzió leírásához.</span><span class="sxs-lookup"><span data-stu-id="8756e-125">In the Dimension name field, type a value to describe the financial dimension.</span></span>
    * <span data-ttu-id="8756e-126">A név nem tartalmazhat szóközt vagy különleges karaktert.</span><span class="sxs-lookup"><span data-stu-id="8756e-126">The name cannot contain spaces or special characters.</span></span>  
    * <span data-ttu-id="8756e-127">A formátummaszk megadásával továbbá korlátozhatja a dimenzióértékekhez megadható adatok mennyiségét és típusát.</span><span class="sxs-lookup"><span data-stu-id="8756e-127">You can also specify an account mask to limit the amount and type of information that you can enter for dimension values.</span></span>   
    * <span data-ttu-id="8756e-128">Megadhat olyan karaktereket, például betűket vagy kötőjelet, amelyek minden egyes dimenzióértéknél változatlanok maradnak.</span><span class="sxs-lookup"><span data-stu-id="8756e-128">You can enter characters that remain the same for each dimension value, such as letters or a hyphen.</span></span> <span data-ttu-id="8756e-129">Emellett megadhat kettős kereszt (#) vagy és-jel (&) karaktereket számok és betűk helyőrzőjeként, amelyek változni fognak a dimenzióértékek minden létrehozásakor.</span><span class="sxs-lookup"><span data-stu-id="8756e-129">You can also enter number signs (#) and ampersands (&) as placeholders for letters and numbers that will change every time that a dimension value is created.</span></span> <span data-ttu-id="8756e-130">A kettős kereszt (#) a számok, míg az és-jel (&) a betűk helyőrzője.</span><span class="sxs-lookup"><span data-stu-id="8756e-130">Use a number sign (#) as a placeholder for a number and an ampersand (&) as a placeholder for a letter.</span></span>  <span data-ttu-id="8756e-131">Példa: Ha például a dimenzióértéket két C betűre és három számra szeretné korlátozni, formátummaszkként a CC-### értéket adja meg.</span><span class="sxs-lookup"><span data-stu-id="8756e-131">Example: To limit the dimension value to the letters CC and three numbers, you enter CC-### as the format mask.</span></span>  
5. <span data-ttu-id="8756e-132">Kattintson az Aktiválás gombra.</span><span class="sxs-lookup"><span data-stu-id="8756e-132">Click Activate.</span></span>
    * <span data-ttu-id="8756e-133">A pénzügyi dimenzió aktiválásával frissítheti a pénzügyi dimenzió nevét tartalmazó táblázatot, és eltávolíthatja a törölt dimenziókat.</span><span class="sxs-lookup"><span data-stu-id="8756e-133">Activating the financial dimension updates the table with the financial dimension name and removes deleted dimensions.</span></span> <span data-ttu-id="8756e-134">A pénzügyi dimenziók aktiválása előtt megadhat dimenzióértékeket, de a pénzügyi dimenzió nem használható, amíg nincs aktiválva.</span><span class="sxs-lookup"><span data-stu-id="8756e-134">You can enter dimension values before you activate a financial dimension, but a financial dimension cannot be used until it is activated.</span></span>  
6. <span data-ttu-id="8756e-135">Kattintson az Aktiválás gombra.</span><span class="sxs-lookup"><span data-stu-id="8756e-135">Click Activate.</span></span>
    * <span data-ttu-id="8756e-136">Megadhatja, hogy a dimenzió aktiválását egy adott napon és időpontban szeretné futtatni, kötegelt módon.</span><span class="sxs-lookup"><span data-stu-id="8756e-136">Dimension activation can be scheduled to run by batch at a specific date and time.</span></span>  
7. <span data-ttu-id="8756e-137">Kattintson a Dimenzióértékek elemre.</span><span class="sxs-lookup"><span data-stu-id="8756e-137">Click Dimension values.</span></span>
8. <span data-ttu-id="8756e-138">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8756e-138">Click New.</span></span>
9. <span data-ttu-id="8756e-139">A Dimenzió értéke mezőbe írjon be egy nevet a pénzügyi dimenzióérték leírásához.</span><span class="sxs-lookup"><span data-stu-id="8756e-139">In the Dimension value field, type a name to describe your financial dimension value.</span></span>
10. <span data-ttu-id="8756e-140">A Leírás mezőben írja be egy leírást, amely leírja a pénzügyi dimenzió értékét.</span><span class="sxs-lookup"><span data-stu-id="8756e-140">In the Description field, type a description that describes your financial dimension value.</span></span>

