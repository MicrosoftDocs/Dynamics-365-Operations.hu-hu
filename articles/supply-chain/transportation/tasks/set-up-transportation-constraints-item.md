---
title: Egy elemre vonatkozó szállítási megszorítások beállítása
description: Ez az eljárás állítja be a szállítási megszorításokat annak érdekében, hogy megakadályozza a kiválasztott cikk egy kijelölt központon keresztül történő szállítását.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSConstraint, InventLocationIdLookup, InventItemIdLookupSimple
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8eb9873f0ad6f404dc88d27ed5feedfc71fd62b5
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3201410"
---
# <a name="set-up-transportation-constraints-for-an-item"></a><span data-ttu-id="1f6df-103">Egy elemre vonatkozó szállítási megszorítások beállítása</span><span class="sxs-lookup"><span data-stu-id="1f6df-103">Set up transportation constraints for an item</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1f6df-104">Ez az eljárás állítja be a szállítási megszorításokat annak érdekében, hogy megakadályozza a kiválasztott cikk egy kijelölt központon keresztül történő szállítását.</span><span class="sxs-lookup"><span data-stu-id="1f6df-104">This procedure will set up a transportation constraint to prevent a selected item from being transported through a selected hub.</span></span> <span data-ttu-id="1f6df-105">Általában ezt a feladatot egy Szállítási koordinátor végzi el.</span><span class="sxs-lookup"><span data-stu-id="1f6df-105">This task would typically be carried out by a Transportation coordinator.</span></span> <span data-ttu-id="1f6df-106">Ezt a folyamatot az USMF bemutatócégnél vagy a saját adataiban is használhatja.</span><span class="sxs-lookup"><span data-stu-id="1f6df-106">You can use this procedure in the USMF demo data company or on your own data.</span></span>


## <a name="create-an-item-constaint"></a><span data-ttu-id="1f6df-107">Cikkmegszorítás létrehozása</span><span class="sxs-lookup"><span data-stu-id="1f6df-107">Create an item constaint</span></span>
1. <span data-ttu-id="1f6df-108">Ugorjon a Megszorítások pontra.</span><span class="sxs-lookup"><span data-stu-id="1f6df-108">Go to Constraints.</span></span>
2. <span data-ttu-id="1f6df-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1f6df-109">Click New.</span></span>
3. <span data-ttu-id="1f6df-110">Írjon be egy értéket a megszorítás mezőbe.</span><span class="sxs-lookup"><span data-stu-id="1f6df-110">In the Item constraint field, type a value.</span></span>
4. <span data-ttu-id="1f6df-111">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="1f6df-111">In the Name field, type a value.</span></span>
5. <span data-ttu-id="1f6df-112">A Hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1f6df-112">In the Site field, enter or select a value.</span></span>
6. <span data-ttu-id="1f6df-113">A Raktár mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1f6df-113">In the Warehouse field, enter or select a value.</span></span>
7. <span data-ttu-id="1f6df-114">Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1f6df-114">In the Item number field, enter or select a value.</span></span>
8. <span data-ttu-id="1f6df-115">A Központ mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1f6df-115">In the Hub field, enter or select a value.</span></span>
9. <span data-ttu-id="1f6df-116">Válasszon ki egy lehetőséget a Megszorítás művelet mezőben.</span><span class="sxs-lookup"><span data-stu-id="1f6df-116">In the Constraint action field, select an option.</span></span>
10. <span data-ttu-id="1f6df-117">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="1f6df-117">Click Save.</span></span>
11. <span data-ttu-id="1f6df-118">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="1f6df-118">Close the page.</span></span>

