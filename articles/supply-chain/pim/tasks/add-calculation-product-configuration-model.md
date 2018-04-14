--- 
title: "Kalkuláció hozzáadása termékkonfigurációs modellhez"
description: "Ez az eljárás bemutatja, hogyan lehet hozzáadni egy új számítást egy termékkonfigurációs modellhez."
author: YuyuScheller
manager: AnnBe
ms.date: 03/02/2016
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
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 01434e8dbd1e66ae04d0b7910ef2be582297ac84
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---
# <a name="add-a-calculation-to-a-product-configuration-model"></a><span data-ttu-id="f832d-103">Kalkuláció hozzáadása termékkonfigurációs modellhez</span><span class="sxs-lookup"><span data-stu-id="f832d-103">Add a calculation to a product configuration model</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f832d-104">Ez az eljárás bemutatja, hogyan lehet hozzáadni egy új számítást egy termékkonfigurációs modellhez.</span><span class="sxs-lookup"><span data-stu-id="f832d-104">This procedure shows how to add a new calculation to a product configuration model.</span></span> <span data-ttu-id="f832d-105">Azt mutatja, hogyan lehet létrehozni egy logikai kifejezést az „if” operátorral, hogy a fehér hangszórók magassága 10 az egyéb felületekkel rendelkezőké pedig 15 legyen.</span><span class="sxs-lookup"><span data-stu-id="f832d-105">It shows how you can create a logical expression using the "If" operator to set a speaker height to 10 for white speakers and 15 for all other cabinet finishes.</span></span> <span data-ttu-id="f832d-106">Az eljárás a Felső kategóriás hangszóró összetevőt használja az USMF bemutatócégben.</span><span class="sxs-lookup"><span data-stu-id="f832d-106">The procedure uses the High end speaker component in the demo company USMF.</span></span>


## <a name="add-a-calculation"></a><span data-ttu-id="f832d-107">Számítás hozzáadása</span><span class="sxs-lookup"><span data-stu-id="f832d-107">Add a calculation</span></span>

## <a name="create-calculation-expression"></a><span data-ttu-id="f832d-108">Számításkifejezés létrehozása</span><span class="sxs-lookup"><span data-stu-id="f832d-108">Create calculation expression</span></span>
1. <span data-ttu-id="f832d-109">Kattintson a Kifejezés szerkesztése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f832d-109">Click Edit expression.</span></span>
2. <span data-ttu-id="f832d-110">A ConstraintBody mezőben írja be, hogy „If[CabinetFinish =="White", 10, 15]”.</span><span class="sxs-lookup"><span data-stu-id="f832d-110">In the ConstraintBody field, enter 'If[CabinetFinish=="White", 10, 15]'.</span></span>
3. <span data-ttu-id="f832d-111">Kattintson az Érvényesítés gombra.</span><span class="sxs-lookup"><span data-stu-id="f832d-111">Click Validate.</span></span>
4. <span data-ttu-id="f832d-112">Kattintson a Bezárás gombra.</span><span class="sxs-lookup"><span data-stu-id="f832d-112">Click Close.</span></span>
5. <span data-ttu-id="f832d-113">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="f832d-113">Click OK.</span></span>


