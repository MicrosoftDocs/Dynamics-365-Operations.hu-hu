---
title: Egy elemre vonatkozó szállítási megszorítások beállítása
description: Ez az eljárás állítja be a szállítási megszorításokat annak érdekében, hogy megakadályozza a kiválasztott cikk egy kijelölt központon keresztül történő szállítását.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSConstraint, InventLocationIdLookup, InventItemIdLookupSimple
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4ccd7d79fbcdd600f78dbff98ce39c04865afe37
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3146146"
---
# <a name="set-up-transportation-constraints-for-an-item"></a><span data-ttu-id="79481-103">Egy elemre vonatkozó szállítási megszorítások beállítása</span><span class="sxs-lookup"><span data-stu-id="79481-103">Set up transportation constraints for an item</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="79481-104">Ez az eljárás állítja be a szállítási megszorításokat annak érdekében, hogy megakadályozza a kiválasztott cikk egy kijelölt központon keresztül történő szállítását.</span><span class="sxs-lookup"><span data-stu-id="79481-104">This procedure will set up a transportation constraint to prevent a selected item from being transported through a selected hub.</span></span> <span data-ttu-id="79481-105">Általában ezt a feladatot egy Szállítási koordinátor végzi el.</span><span class="sxs-lookup"><span data-stu-id="79481-105">This task would typically be carried out by a Transportation coordinator.</span></span> <span data-ttu-id="79481-106">Ezt a folyamatot az USMF bemutatócégnél vagy a saját adataiban is használhatja.</span><span class="sxs-lookup"><span data-stu-id="79481-106">You can use this procedure in the USMF demo data company or on your own data.</span></span>


## <a name="create-an-item-constaint"></a><span data-ttu-id="79481-107">Cikkmegszorítás létrehozása</span><span class="sxs-lookup"><span data-stu-id="79481-107">Create an item constaint</span></span>
1. <span data-ttu-id="79481-108">Ugorjon a Megszorítások pontra.</span><span class="sxs-lookup"><span data-stu-id="79481-108">Go to Constraints.</span></span>
2. <span data-ttu-id="79481-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="79481-109">Click New.</span></span>
3. <span data-ttu-id="79481-110">Írjon be egy értéket a megszorítás mezőbe.</span><span class="sxs-lookup"><span data-stu-id="79481-110">In the Item constraint field, type a value.</span></span>
4. <span data-ttu-id="79481-111">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="79481-111">In the Name field, type a value.</span></span>
5. <span data-ttu-id="79481-112">A Hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="79481-112">In the Site field, enter or select a value.</span></span>
6. <span data-ttu-id="79481-113">A Raktár mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="79481-113">In the Warehouse field, enter or select a value.</span></span>
7. <span data-ttu-id="79481-114">Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="79481-114">In the Item number field, enter or select a value.</span></span>
8. <span data-ttu-id="79481-115">A Központ mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="79481-115">In the Hub field, enter or select a value.</span></span>
9. <span data-ttu-id="79481-116">Válasszon ki egy lehetőséget a Megszorítás művelet mezőben.</span><span class="sxs-lookup"><span data-stu-id="79481-116">In the Constraint action field, select an option.</span></span>
10. <span data-ttu-id="79481-117">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="79481-117">Click Save.</span></span>
11. <span data-ttu-id="79481-118">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="79481-118">Close the page.</span></span>

