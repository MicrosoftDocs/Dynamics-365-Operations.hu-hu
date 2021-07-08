---
title: A kijelölt receptúraszám nincs jóváhagyva kötegrendeléshez
description: Egy tervezett rendelés meghatározásakor olyan hibaüzenet jelenik meg, amely szerint a kiválasztott receptúraszám nincs jóváhagyva kötegrendeléshez.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 4f993c92ca0a2f8f79e4b0e0eda43904529163f8
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294088"
---
# <a name="selected-formula-number-isnt-approved-for-a-batch-order"></a><span data-ttu-id="5e3d7-103">A kijelölt receptúraszám nincs jóváhagyva kötegrendeléshez</span><span class="sxs-lookup"><span data-stu-id="5e3d7-103">Selected formula number isn't approved for a batch order</span></span>

<span data-ttu-id="5e3d7-104">Hibakód: PRO2614</span><span class="sxs-lookup"><span data-stu-id="5e3d7-104">Error code: PRO2614</span></span>

## <a name="symptoms"></a><span data-ttu-id="5e3d7-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="5e3d7-105">Symptoms</span></span>

<span data-ttu-id="5e3d7-106">Amikor tervezett rendelést próbál megerősíteni, a következő hibaüzenetet kapja:</span><span class="sxs-lookup"><span data-stu-id="5e3d7-106">When you try to firm a planned order, you receive the following error message:</span></span>

> <span data-ttu-id="5e3d7-107">A választott receptúraszám nincs jóváhagyva kötegrendeléshez.</span><span class="sxs-lookup"><span data-stu-id="5e3d7-107">The selected formula number is not approved for a batch order.</span></span>

## <a name="cause"></a><span data-ttu-id="5e3d7-108">Ok</span><span class="sxs-lookup"><span data-stu-id="5e3d7-108">Cause</span></span>

<span data-ttu-id="5e3d7-109">A rendszer ellenőrzi a meghatározási műveletet, hogy áll-e rendelkezésre jóváhagyott receptúra az aktív cikkhez.</span><span class="sxs-lookup"><span data-stu-id="5e3d7-109">The system validates the firming operation to make sure that an approved formula is available for the active item.</span></span> <span data-ttu-id="5e3d7-110">Önnek valószínűleg jóvá kell hagynia a receptúrát.</span><span class="sxs-lookup"><span data-stu-id="5e3d7-110">You must probably approve the formula.</span></span>

## <a name="resolution"></a><span data-ttu-id="5e3d7-111">Megoldás</span><span class="sxs-lookup"><span data-stu-id="5e3d7-111">Resolution</span></span>

<span data-ttu-id="5e3d7-112">A receptúra jóváhagyásához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="5e3d7-112">To approve a formula, follow these steps.</span></span>

1. <span data-ttu-id="5e3d7-113">Lépjen a **Termékinformációk kezelése \> Anyagjegyzékek és receptúrák \> Receptúrák** részre.</span><span class="sxs-lookup"><span data-stu-id="5e3d7-113">Go to **Product information management \> Bills of materials and formulas \> Formulas**.</span></span>
1. <span data-ttu-id="5e3d7-114">Válassza ki a kívánt receptúrát.</span><span class="sxs-lookup"><span data-stu-id="5e3d7-114">Select the relevant formula.</span></span>
1. <span data-ttu-id="5e3d7-115">A Művelet ablaktábla **Receptúra** lapján lévő **Karbantartás** csoportban válassza a **Receptúra jóváhagyása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5e3d7-115">On the Action Pane, on the **Formula** tab, in the **Maintain** group, select **Approve formula**.</span></span>
1. <span data-ttu-id="5e3d7-116">A **DBJ vagy receptúra jóváhagyása** párbeszédpanelen válassza ki a jóváhagyót, és kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="5e3d7-116">In the **Approve BOM or formula** dialog box, select an approver, and then select **OK**.</span></span>
