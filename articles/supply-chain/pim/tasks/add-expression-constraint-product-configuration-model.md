---
title: Kifejezésmegszorítás hozzáadása a termékkonfigurációs modellhez
description: Ez az eljárás bemutatja, hogyan lehet hozzáadni egy új megszorítási kifejezést egy termékkonfigurációs modellhez.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, SysClientPolymorphicCreateSelector, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9cd5475e48cbcd8dcee6b228297f58e364ac503d
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920881"
---
# <a name="add-an-expression-constraint-to-a-product-configuration-model"></a><span data-ttu-id="beb7a-103">Kifejezésmegszorítás hozzáadása a termékkonfigurációs modellhez</span><span class="sxs-lookup"><span data-stu-id="beb7a-103">Add an expression constraint to a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="beb7a-104">Ez az eljárás bemutatja, hogyan lehet hozzáadni egy új megszorítási kifejezést egy termékkonfigurációs modellhez.</span><span class="sxs-lookup"><span data-stu-id="beb7a-104">This procedure shows how you can add a new constraint expression to a product configuration model.</span></span> <span data-ttu-id="beb7a-105">Azt mutatja, hogyan írható elő kötelezővé sarokvédelem alkalmazása a hangszórón, ha a felhasználó fém elülső rácsot választott.</span><span class="sxs-lookup"><span data-stu-id="beb7a-105">It shows how you can mandate that corner protection must be applied to a speaker if the user has selected a front grill in metal.</span></span> <span data-ttu-id="beb7a-106">Az eljárás a Felső kategóriás hangszóró összetevőt használja az USMF bemutatócégben.</span><span class="sxs-lookup"><span data-stu-id="beb7a-106">The procedure uses the High end speaker component in the demo company USMF.</span></span>

## <a name="create-an-expression-constraint"></a><span data-ttu-id="beb7a-107">Kifejezésmegszorítás szerkesztője</span><span class="sxs-lookup"><span data-stu-id="beb7a-107">Create an expression constraint</span></span>

1. <span data-ttu-id="beb7a-108">Lépjen a **Termékinformáció-kezelés \> Termékek \> Termékkonfigurációs modellek** elemre.</span><span class="sxs-lookup"><span data-stu-id="beb7a-108">Go to **Product information management \> Products \> Product configuration models**.</span></span>
3. <span data-ttu-id="beb7a-109">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="beb7a-109">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="beb7a-110">Ez a példa a felső kategóriás hangszóró modellt használja.</span><span class="sxs-lookup"><span data-stu-id="beb7a-110">This example uses the high end speaker model.</span></span>  
4. <span data-ttu-id="beb7a-111">A listában válassza ki a kiválasztott sorból a hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="beb7a-111">In the list, select the link in the selected row.</span></span>
5. <span data-ttu-id="beb7a-112">Bontsa ki **Megszorítások** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="beb7a-112">Expand the **Constraints** section.</span></span>
6. <span data-ttu-id="beb7a-113">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="beb7a-113">Select **Add**.</span></span>
7. <span data-ttu-id="beb7a-114">Válassza a **Létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="beb7a-114">Select **Create**.</span></span>
8. <span data-ttu-id="beb7a-115">Írjon be egy értéket a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="beb7a-115">In the **Name** field, type a value.</span></span>

## <a name="enter-expression"></a><span data-ttu-id="beb7a-116">Kifejezés megadása</span><span class="sxs-lookup"><span data-stu-id="beb7a-116">Enter expression</span></span>

1. <span data-ttu-id="beb7a-117">Válassza a **Kifejezés szerkesztése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="beb7a-117">Select **Edit expression**.</span></span>
    * <span data-ttu-id="beb7a-118">Ha a feladatrögzítésben feloldja a felhasználói felületet ebben a fázisban, akkor az IntelliSense és a szimbólumlista segítségével felépítheti a megszorítási kifejezést.</span><span class="sxs-lookup"><span data-stu-id="beb7a-118">If you unlock the user interface in the task recording at this stage, you can use IntelliSense and the list of symbols to build the constraint expression .</span></span>  
2. <span data-ttu-id="beb7a-119">A **ConstraintBody** mezőben írja be „Implies [FrontGrill =="Metal", CornerProtection]”.</span><span class="sxs-lookup"><span data-stu-id="beb7a-119">In the **ConstraintBody** field, enter 'Implies[FrontGrill=="Metal", CornerProtection] '.</span></span>
    * <span data-ttu-id="beb7a-120">Ez a kifejezéslogika a következőt állítja: Ha az előlapi rács fém, akkor ki kell választani a sarokvédő lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="beb7a-120">This expression logic states: If the Front grill is  metal, then the corner protection option must be selected.</span></span>  
3. <span data-ttu-id="beb7a-121">A **Validálás** kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="beb7a-121">Select **Validate**.</span></span>
    * <span data-ttu-id="beb7a-122">Az érvényesítési funkció ellenőrzi a megszorítási kifejezést, és szintaktikai hibákat keres.</span><span class="sxs-lookup"><span data-stu-id="beb7a-122">The validate function runs through the constraint expression and checks for syntax errors.</span></span>  
4. <span data-ttu-id="beb7a-123">Válassza **Bezárás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="beb7a-123">Select **Close**.</span></span>
5. <span data-ttu-id="beb7a-124">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="beb7a-124">Select **OK**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]