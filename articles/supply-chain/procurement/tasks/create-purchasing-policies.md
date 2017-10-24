--- 
title: "Beszerzési irányelvek létrehozása"
description: "Ez az eljárás bemutatja, hogy hogyan lehet olyan beszerzési irányelveket létrehozni, amelyeket egyeztetni kíván az üzleti folyamattal a beszerzéshez."
author: mkirknel
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: c2b3a66443394f5bfbe51b6685513281025d68fd
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="create-purchasing-policies"></a><span data-ttu-id="325b8-103">Beszerzési irányelvek létrehozása</span><span class="sxs-lookup"><span data-stu-id="325b8-103">Create purchasing policies</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="325b8-104">Ez az eljárás bemutatja, hogy hogyan lehet olyan beszerzési irányelveket létrehozni, amelyeket egyeztetni kíván az üzleti folyamattal a beszerzéshez.</span><span class="sxs-lookup"><span data-stu-id="325b8-104">This procedure shows you how to create purchasing policies to align with your business processes for purchasing.</span></span> <span data-ttu-id="325b8-105">A beszerzési irányelvek létrehozása előtt, be kell állítania a beszerzési irányelvek paramétereit.</span><span class="sxs-lookup"><span data-stu-id="325b8-105">Before you can create purchasing policies, you must set up the purchasing policy parameters.</span></span> <span data-ttu-id="325b8-106">Lehetőség van a beszerzési irányelvek létrehozására, módosítására és visszavonására, azonban nem törölheti a beszerzési irányelvet.</span><span class="sxs-lookup"><span data-stu-id="325b8-106">It’s possible to create, modify, and retire a purchasing policy, but you can’t delete a purchasing policy.</span></span> <span data-ttu-id="325b8-107">Ezt a folyamatot általában egy beszerzési vezető végzi el.</span><span class="sxs-lookup"><span data-stu-id="325b8-107">This procedure would typically be carried out by a purchasing manager.</span></span> <span data-ttu-id="325b8-108">Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is használhatja.</span><span class="sxs-lookup"><span data-stu-id="325b8-108">You can use this procedure in demo data company USMF or on your own data.</span></span>


## <a name="set-up-policy-parameters"></a><span data-ttu-id="325b8-109">Irányelv-paraméterek beállítása</span><span class="sxs-lookup"><span data-stu-id="325b8-109">Set up policy parameters</span></span>
1. <span data-ttu-id="325b8-110">Ugorjon a Beszerzési irányelvek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="325b8-110">Go to Purchasing policies.</span></span>
2. <span data-ttu-id="325b8-111">Kattintson a Paraméterek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="325b8-111">Click Parameters.</span></span>
    * <span data-ttu-id="325b8-112">Az irányelvszabályok a szervezet különböző szintjeire vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="325b8-112">Policy precedence rules apply to different levels in your organization.</span></span> <span data-ttu-id="325b8-113">A szervezeti egységek a szervezeti hierarchiától függően jelennek meg, és a hierarchia azon szintjein, amelyek hozzá vannak rendelve a beszerzés belső ellenőrzésének céljaihoz.</span><span class="sxs-lookup"><span data-stu-id="325b8-113">The organizational units that are shown depend on your organizational hierarchy, and on which levels in the hierarchy have been assigned the purpose of Procurement internal control.</span></span> <span data-ttu-id="325b8-114">Például előfordulhat, hogy a szervezet rendelkezik jogi személyekkel, költséghelyekkel, és részlegekkel, azonban lehet, hogy ezek közül csak néhány rendelkezik a beszerzés belső ellenőrzés hierarchiájának céljával.</span><span class="sxs-lookup"><span data-stu-id="325b8-114">For example, your organization might have legal entities, cost centers, regions, and departments, but it may be that only some of these have a hierarchy purpose of Procurement internal control.</span></span> <span data-ttu-id="325b8-115">Alapértelmezés szerint a Vállalat típus szervezete érhető el.</span><span class="sxs-lookup"><span data-stu-id="325b8-115">As a default, the organization of type Company is available.</span></span>  
3. <span data-ttu-id="325b8-116">Kattintson az Irányelvszabály-típus paraméterei fülre.</span><span class="sxs-lookup"><span data-stu-id="325b8-116">Click the Policy rule type parameters tab.</span></span>
4. <span data-ttu-id="325b8-117">Válassza ki a „Beszerzés irányelv\Beszerzési igénylés-ellenőrzési szabály” lehetőséget a fa struktúrában.</span><span class="sxs-lookup"><span data-stu-id="325b8-117">In the tree, select 'Purchasing policy\Purchase requisition control rule'.</span></span>
    * <span data-ttu-id="325b8-118">Az irányelvek feldolgozásának elsőbbségi sorrendje az irányelvek szintjén határozható meg.</span><span class="sxs-lookup"><span data-stu-id="325b8-118">You define the order of precedence for policy resolution at the policy level.</span></span> <span data-ttu-id="325b8-119">Egyes irányelvtípusok esetén azonban az egyes irányelvszabály-típusok elsőbbségi sorrendje felülbírálható.</span><span class="sxs-lookup"><span data-stu-id="325b8-119">However, for some policy types, you can override the order of precedence for individual policy rule types.</span></span> <span data-ttu-id="325b8-120">Például a következőképpen határozhatja meg a beszerzési szabályok elsőbbségi sorrend rendelését: költséghely, részleg, vállalat.</span><span class="sxs-lookup"><span data-stu-id="325b8-120">For example, you might define the order of precedence for purchasing policies to be: cost center, department, company.</span></span> <span data-ttu-id="325b8-121">A katalógus irányelvszabálya esetén a következő sorrendet kell használnia: részleg, költséghely, vállalat.</span><span class="sxs-lookup"><span data-stu-id="325b8-121">For the catalog policy rule, you might want the order of precedence to be: department, cost center, company.</span></span> <span data-ttu-id="325b8-122">A Katalógus irányelvszabálynál módosíthatja az elsőbbségi sorrendet.</span><span class="sxs-lookup"><span data-stu-id="325b8-122">You can change the order of precedence for the Catalog policy rule.</span></span> <span data-ttu-id="325b8-123">Amikor a dolgozó igénylést hoz létre, a megjelenített katalógust azon irányelvek határozzák meg, amelyeket a rendszer a dolgozó részlegéhez, majd a költséghelyhez, és a vállalathoz rendelt.</span><span class="sxs-lookup"><span data-stu-id="325b8-123">When a worker creates a requisition, the catalog that is displayed is determined by the policies that are associated with the worker’s department, then their cost center, and then their company.</span></span>  
    * <span data-ttu-id="325b8-124">Ha a rendszer egynél több szervezeti szintet listázott, akkor a felfelé vagy lefelé nyíl használatával beállíthatja a beszerzési igénylés ellenőrzési szabályának elsőbbségi sorrendjét.</span><span class="sxs-lookup"><span data-stu-id="325b8-124">If there’s more than one organizational level listed, you can use the Up/Down arrows to set the order of precedence for the Purchase requisition control rule.</span></span>  
5. <span data-ttu-id="325b8-125">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="325b8-125">Close the page.</span></span>

## <a name="create-a-new-policy"></a><span data-ttu-id="325b8-126">Új irányelv létrehozása</span><span class="sxs-lookup"><span data-stu-id="325b8-126">Create a new policy</span></span>
1. <span data-ttu-id="325b8-127">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="325b8-127">Click New.</span></span>
2. <span data-ttu-id="325b8-128">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="325b8-128">In the Name field, type a value.</span></span>
3. <span data-ttu-id="325b8-129">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="325b8-129">In the Description field, type a value.</span></span>
    * <span data-ttu-id="325b8-130">Egyetlen beszerzési irányelv csak vonatkozhat egy szervezeti hierarchiára.</span><span class="sxs-lookup"><span data-stu-id="325b8-130">A single purchasing policy can only apply to one organization hierarchy.</span></span> <span data-ttu-id="325b8-131">Például rendelkezhet egy „Földrajzi” és egy „Részleg” elnevezésű hierarchiával, illetve a két hierarchiára vonatkozó, különböző beszerzési irányelvvel.</span><span class="sxs-lookup"><span data-stu-id="325b8-131">For example, you could have one hierarchy called “Geographic” and one called “Department”, and have a different purchasing policy for each.</span></span>  
    * <span data-ttu-id="325b8-132">Válasszon ki egy olyan szervezetet, amelyre vonatkozóan alkalmazni kell az irányelvet.</span><span class="sxs-lookup"><span data-stu-id="325b8-132">Select an organization that the policy should apply to.</span></span>  
4. <span data-ttu-id="325b8-133">Kattintson a nyílra a kijelölt szervezet hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="325b8-133">Click the arrow to add the selected organization.</span></span>
    * <span data-ttu-id="325b8-134">Ezen folyamat megismétlésével több szervezetet is hozzáadhat.</span><span class="sxs-lookup"><span data-stu-id="325b8-134">You can repeat this process to add more organizations.</span></span>  

## <a name="add-a-policy-rule"></a><span data-ttu-id="325b8-135">Irányelvszabály hozzáadása</span><span class="sxs-lookup"><span data-stu-id="325b8-135">Add a policy rule</span></span>
1. <span data-ttu-id="325b8-136">Válassza ki az Igénylésicél-szabály lehetőséget az Irányelvszabály típusa listában.</span><span class="sxs-lookup"><span data-stu-id="325b8-136">In the Policy rule type list, select Requisition purpose rule.</span></span>
    * <span data-ttu-id="325b8-137">Egy olyan szabályt is létrehozhat, amely az alapértelmezett igénylési célt Felhasználás típusra állítja be, de helyette lehetővé válik a Feltöltés típusa lehetőség kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="325b8-137">You’ll create a rule that sets the default requisition purpose to type Consumption but allows the Replenishment type to be selected instead.</span></span>  
2. <span data-ttu-id="325b8-138">Kattintson az Irányelvszabályra.</span><span class="sxs-lookup"><span data-stu-id="325b8-138">Click Create policy rule.</span></span>
3. <span data-ttu-id="325b8-139">Válassza ki az Igen lehetőséget a Kézi felülbírálás engedélyezése mezőben.</span><span class="sxs-lookup"><span data-stu-id="325b8-139">Select Yes in the Allow manual override field.</span></span>
4. <span data-ttu-id="325b8-140">Kattintson a Bezárás gombra.</span><span class="sxs-lookup"><span data-stu-id="325b8-140">Click Close.</span></span>
    * <span data-ttu-id="325b8-141">Most beállíthatja az egyéb irányelveket a beszerzési irányelvekhez.</span><span class="sxs-lookup"><span data-stu-id="325b8-141">Now you can set up other policy rules for the purchasing policy.</span></span>   <span data-ttu-id="325b8-142">Jegyezze meg, hogy egy irányelvszabály-típus nem rendelkezhet olyan átfedő szabályokkal, amelyek egyaránt aktív állapotban vannak az egyetlen beszerzési webhelyen.</span><span class="sxs-lookup"><span data-stu-id="325b8-142">Note that a Policy rule type cannot have overlapping rules that are active at the same time within a single procurement policy.</span></span>  
5. <span data-ttu-id="325b8-143">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="325b8-143">Close the page.</span></span>
6. <span data-ttu-id="325b8-144">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="325b8-144">Close the page.</span></span>


