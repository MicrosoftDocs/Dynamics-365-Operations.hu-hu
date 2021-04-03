---
title: Kalkuláció hozzáadása termékkonfigurációs modellhez
description: Ez az eljárás bemutatja, hogyan lehet hozzáadni egy új számítást egy termékkonfigurációs modellhez.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6e23d33c6911310cca6aac0df4589e909568a86a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5258071"
---
# <a name="add-a-calculation-to-a-product-configuration-model"></a><span data-ttu-id="45da4-103">Kalkuláció hozzáadása termékkonfigurációs modellhez</span><span class="sxs-lookup"><span data-stu-id="45da4-103">Add a calculation to a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="45da4-104">Ez az eljárás bemutatja, hogyan lehet hozzáadni egy új számítást egy termékkonfigurációs modellhez.</span><span class="sxs-lookup"><span data-stu-id="45da4-104">This procedure shows how to add a new calculation to a product configuration model.</span></span> <span data-ttu-id="45da4-105">Azt mutatja, hogyan lehet létrehozni egy logikai kifejezést az „if” operátorral, hogy a fehér hangszórók magassága 10 az egyéb felületekkel rendelkezőké pedig 15 legyen.</span><span class="sxs-lookup"><span data-stu-id="45da4-105">It shows how you can create a logical expression using the "If" operator to set a speaker height to 10 for white speakers and 15 for all other cabinet finishes.</span></span> <span data-ttu-id="45da4-106">Az eljárás a Felső kategóriás hangszóró összetevőt használja az USMF bemutatócégben.</span><span class="sxs-lookup"><span data-stu-id="45da4-106">The procedure uses the High end speaker component in the demo company USMF.</span></span>


## <a name="add-a-calculation"></a><span data-ttu-id="45da4-107">Számítás hozzáadása</span><span class="sxs-lookup"><span data-stu-id="45da4-107">Add a calculation</span></span>

## <a name="create-calculation-expression"></a><span data-ttu-id="45da4-108">Számításkifejezés létrehozása</span><span class="sxs-lookup"><span data-stu-id="45da4-108">Create calculation expression</span></span>
1. <span data-ttu-id="45da4-109">Kattintson a Kifejezés szerkesztése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="45da4-109">Click Edit expression.</span></span>
2. <span data-ttu-id="45da4-110">A ConstraintBody mezőben írja be, hogy „If[CabinetFinish =="White", 10, 15]”.</span><span class="sxs-lookup"><span data-stu-id="45da4-110">In the ConstraintBody field, enter 'If[CabinetFinish=="White", 10, 15]'.</span></span>
3. <span data-ttu-id="45da4-111">Kattintson az Érvényesítés gombra.</span><span class="sxs-lookup"><span data-stu-id="45da4-111">Click Validate.</span></span>
4. <span data-ttu-id="45da4-112">Kattintson a Bezárás gombra.</span><span class="sxs-lookup"><span data-stu-id="45da4-112">Click Close.</span></span>
5. <span data-ttu-id="45da4-113">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="45da4-113">Click OK.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]