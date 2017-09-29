--- 
title: "Költségösszetevő-dimenzió feltérképezése"
description: "A költségellenőr ezzel az eljárással hozzárendelhet egy költségösszetevő-dimenziót egy költségösszetevő-dimenzióhoz az MXMF jogi személyen belül."
author: YuyuScheller
manager: AnnBe
ms.date: 06/28/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 3ff31db3dbb6da9570bb85bbcaa3b444852d91d7
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---
# <a name="map-a-cost-element-dimension"></a><span data-ttu-id="f8509-103">Költségösszetevő-dimenzió feltérképezése</span><span class="sxs-lookup"><span data-stu-id="f8509-103">Map a cost element dimension</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f8509-104">A költségellenőr ezzel az eljárással hozzárendelhet egy költségösszetevő-dimenziót egy költségösszetevő-dimenzióhoz az MXMF jogi személyen belül.</span><span class="sxs-lookup"><span data-stu-id="f8509-104">A cost controller can use this procedure to map a cost element dimension to a cost element dimension in the MXMF legal entity.</span></span> <span data-ttu-id="f8509-105">Ez a felvétel az USP2 bemutató vállalati adatait használja.</span><span class="sxs-lookup"><span data-stu-id="f8509-105">This recording uses the USP2 demo data company.</span></span>

1. <span data-ttu-id="f8509-106">Ugrás a Költségkönyvelés > Dimenziók > Költségösszetevő-dimenziók elemre.</span><span class="sxs-lookup"><span data-stu-id="f8509-106">Go to Cost accounting > Dimensions > Cost element dimensions.</span></span>
2. <span data-ttu-id="f8509-107">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="f8509-107">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="f8509-108">Ehhez a példához válassza ki a Költségösszetevők lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f8509-108">For this example, select Cost elements.</span></span>  
3. <span data-ttu-id="f8509-109">Kattintson a Dimenzióleképezések lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f8509-109">Click Dimension mappings.</span></span>
4. <span data-ttu-id="f8509-110">Kattintson az Ezen dimenzióról való leképezések konfigurálása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f8509-110">Click Configure mappings from this dimension.</span></span>
5. <span data-ttu-id="f8509-111">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f8509-111">Click New.</span></span>
6. <span data-ttu-id="f8509-112">A Céldimenzió mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="f8509-112">In the To dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="f8509-113">Ehhez a példához válassza ki az MXMF költségösszetevők lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f8509-113">For this example, select MXMF Cost elements.</span></span>  
7. <span data-ttu-id="f8509-114">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f8509-114">Click New.</span></span>
8. <span data-ttu-id="f8509-115">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="f8509-115">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="f8509-116">A Forrásdimenzió-tag mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="f8509-116">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="f8509-117">Ebben a példában válassza ki a 606400 telefon- és faxköltség dimenziótagot.</span><span class="sxs-lookup"><span data-stu-id="f8509-117">For this example, select dimension member 606400 Telephone & Fax Expense.</span></span>  
10. <span data-ttu-id="f8509-118">A Céldimenziótag mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="f8509-118">In the To dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="f8509-119">Ebben a példában válassza ki a 6001004 Telefono dimenziótagot.</span><span class="sxs-lookup"><span data-stu-id="f8509-119">For this example, select dimension member 6001004 Telefono.</span></span>  
11. <span data-ttu-id="f8509-120">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="f8509-120">Click Save.</span></span>


