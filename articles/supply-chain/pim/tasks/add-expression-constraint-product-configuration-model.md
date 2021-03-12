---
title: Kifejezésmegszorítás hozzáadása a termékkonfigurációs modellhez
description: Ez az eljárás bemutatja, hogyan lehet hozzáadni egy új megszorítási kifejezést egy termékkonfigurációs modellhez.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, SysClientPolymorphicCreateSelector, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 411e20bd8631b70df981c5785f502693d5ba3705
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4987129"
---
# <a name="add-an-expression-constraint-to-a-product-configuration-model"></a><span data-ttu-id="717e1-103">Kifejezésmegszorítás hozzáadása a termékkonfigurációs modellhez</span><span class="sxs-lookup"><span data-stu-id="717e1-103">Add an expression constraint to a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="717e1-104">Ez az eljárás bemutatja, hogyan lehet hozzáadni egy új megszorítási kifejezést egy termékkonfigurációs modellhez.</span><span class="sxs-lookup"><span data-stu-id="717e1-104">This procedure shows how you can add a new constraint expression to a product configuration model.</span></span> <span data-ttu-id="717e1-105">Azt mutatja, hogyan írható elő kötelezővé sarokvédelem alkalmazása a hangszórón, ha a felhasználó fém elülső rácsot választott.</span><span class="sxs-lookup"><span data-stu-id="717e1-105">It shows how you can mandate that corner protection must be applied to a speaker if the user has selected a front grill in metal.</span></span> <span data-ttu-id="717e1-106">Az eljárás a Felső kategóriás hangszóró összetevőt használja az USMF bemutatócégben.</span><span class="sxs-lookup"><span data-stu-id="717e1-106">The procedure uses the High end speaker component in the demo company USMF.</span></span>


## <a name="create-an-expression-constraint"></a><span data-ttu-id="717e1-107">Kifejezésmegszorítás szerkesztője</span><span class="sxs-lookup"><span data-stu-id="717e1-107">Create an expression constraint</span></span>
1. <span data-ttu-id="717e1-108">Kattintson a Termékváltozat modelldefinícióra.</span><span class="sxs-lookup"><span data-stu-id="717e1-108">Click Product variant model definition.</span></span>
2. <span data-ttu-id="717e1-109">Kattintson a Termékkonfigurációs modellek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="717e1-109">Click Product configuration models.</span></span>
3. <span data-ttu-id="717e1-110">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="717e1-110">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="717e1-111">Ez a példa a felső kategóriás hangszóró modellt használja.</span><span class="sxs-lookup"><span data-stu-id="717e1-111">This example uses the high end speaker model.</span></span>  
4. <span data-ttu-id="717e1-112">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="717e1-112">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="717e1-113">Bontsa ki Megszorítások szakaszt.</span><span class="sxs-lookup"><span data-stu-id="717e1-113">Expand the Constraints section.</span></span>
6. <span data-ttu-id="717e1-114">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="717e1-114">Click Add.</span></span>
7. <span data-ttu-id="717e1-115">Kattintson a Létrehozás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="717e1-115">Click Create.</span></span>
8. <span data-ttu-id="717e1-116">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="717e1-116">In the Name field, type a value.</span></span>

## <a name="enter-expression"></a><span data-ttu-id="717e1-117">Kifejezés megadása</span><span class="sxs-lookup"><span data-stu-id="717e1-117">Enter expression</span></span>
1. <span data-ttu-id="717e1-118">Kattintson a Kifejezés szerkesztése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="717e1-118">Click Edit expression.</span></span>
    * <span data-ttu-id="717e1-119">Ha a feladatrögzítésben feloldja a felhasználói felületet ebben a fázisban, akkor az IntelliSense és a szimbólumlista segítségével felépítheti a megszorítási kifejezést.</span><span class="sxs-lookup"><span data-stu-id="717e1-119">If you unlock the user interface in the task recording at this stage, you can use IntelliSense and the list of symbols to build the constraint expression .</span></span>  
2. <span data-ttu-id="717e1-120">A ConstraintBody mezőben írja be „Implies [FrontGrill =="Metal", CornerProtection]”.</span><span class="sxs-lookup"><span data-stu-id="717e1-120">In the ConstraintBody field, enter 'Implies[FrontGrill=="Metal", CornerProtection] '.</span></span>
    * <span data-ttu-id="717e1-121">Ez a kifejezéslogika a következőt állítja: Ha az előlapi rács fém, akkor ki kell választani a sarokvédő lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="717e1-121">This expression logic states: If the Front grill is  metal, then the corner protection option must be selected.</span></span>  
3. <span data-ttu-id="717e1-122">Kattintson az Érvényesítés gombra.</span><span class="sxs-lookup"><span data-stu-id="717e1-122">Click Validate.</span></span>
    * <span data-ttu-id="717e1-123">Az érvényesítési funkció ellenőrzi a megszorítási kifejezést, és szintaktikai hibákat keres.</span><span class="sxs-lookup"><span data-stu-id="717e1-123">The validate function runs through the constraint expression and checks for syntax errors.</span></span>  
4. <span data-ttu-id="717e1-124">Kattintson a Bezárás gombra.</span><span class="sxs-lookup"><span data-stu-id="717e1-124">Click Close.</span></span>
5. <span data-ttu-id="717e1-125">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="717e1-125">Click OK.</span></span>

