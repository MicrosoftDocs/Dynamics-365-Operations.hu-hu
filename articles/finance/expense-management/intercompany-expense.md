---
title: Vállalatközi költségek
description: Egy dolgozó, aki a szervezeten belüli egy jogi személy alkalmazottja, esetenként végezhet munkát az adott szervezeten belüli másik jogi személy számára. Ebben az esetben a vállalatközi költségek funkciót használhatja ahhoz, hogy a dolgozói költségeket hozzárendelje ahhoz a jogi személyhez, amelynek számára a munka el lett végezve.
author: ShylaThompson
manager: AnnBe
ms.date: 05/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TrvParameters
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0967f23e4e1f8e0431c55d4d54554e7e90e2451c
ms.sourcegitcommit: 07e425707eb20730f10246a27799f4deeef93f97
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/21/2020
ms.locfileid: "3390884"
---
# <a name="intercompany-expenses"></a><span data-ttu-id="58d00-104">Vállalatközi költségek</span><span class="sxs-lookup"><span data-stu-id="58d00-104">Intercompany expenses</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="58d00-105">Egy dolgozó, aki a szervezeten belüli egy jogi személy alkalmazottja, esetenként végezhet munkát az adott szervezeten belüli másik jogi személy számára.</span><span class="sxs-lookup"><span data-stu-id="58d00-105">A worker who is employed by one legal entity in an organization might perform work for another legal entity in the same organization.</span></span> <span data-ttu-id="58d00-106">Ebben az esetben a vállalatközi költségek funkciót használhatja ahhoz, hogy a dolgozói költségeket hozzárendelje ahhoz a jogi személyhez, amelynek számára a munka el lett végezve.</span><span class="sxs-lookup"><span data-stu-id="58d00-106">In this situation, you can use the intercompany expense feature to assign the worker’s expenses to the legal entity for which the work was performed.</span></span> <span data-ttu-id="58d00-107">A dolgozót foglalkoztató jogi személy neve kölcsönbe adó jogi személy.</span><span class="sxs-lookup"><span data-stu-id="58d00-107">The legal entity that employs the worker is called the loaning legal entity.</span></span> <span data-ttu-id="58d00-108">A jogi személy, amelynél a dolgozóval kapcsolatos költségek felmerülnek, a kölcsönbe vevő jogi személy.</span><span class="sxs-lookup"><span data-stu-id="58d00-108">The legal entity for which the worker incurs expenses is called the borrowing legal entity.</span></span> 

<span data-ttu-id="58d00-109">Mielőtt a dolgozó létrehozhatna és benyújthatna költségeket egy másik jogi személynek végrehajtott munkához, a kölcsönbe adó jogi személynél a **Költséggazdálkodási paraméterek** oldalon ki kell válasszalasztani a **Vállalatközi költségsorok engedélyezése** paramétert.</span><span class="sxs-lookup"><span data-stu-id="58d00-109">Before a worker can create and submit expenses for work that is performed for a different legal entity, in the loaning legal entity, on the **Expense management parameters** page, select the **Allow intercompany expense lines** option.</span></span> 

## <a name="tax-posting-for-intercompany-expenses"></a><span data-ttu-id="58d00-110">Vállalatközi költségek adójának feladása</span><span class="sxs-lookup"><span data-stu-id="58d00-110">Tax posting for intercompany expenses</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="58d00-111">Ha a kölcsönadó (forrás) jogi személyhez társított adócsoportokat szeretné használni a kölcsönfelvevő (cél) jogi személyé helyett a költségjelentésben, akkor ezt be kell állítania a Főkönyvi forgalmi adójának beállításában.</span><span class="sxs-lookup"><span data-stu-id="58d00-111">If you want to use tax groups that are associated with the loaning (source) legal entity instead of the borrowing (destination) legal entity in your expense report, you will need to configure this in the General ledger sales tax set up.</span></span> <span data-ttu-id="58d00-112">Amikor a Főkönyv **Vállalatközi adó feladásának jogi személye** paramétere a **Forrás** értékre van beállítva és az **Áfaadózási szabályok alkalmazása** beállítás számára a **Nem** érték van megadva, akkor a kölcsönadó jogi személyhez tartozó adózási kombinációt fogja használni a rendszer.</span><span class="sxs-lookup"><span data-stu-id="58d00-112">When the General ledger parameter, **Legal entity for intercompany tax posting** is set to **Source** and **Apply sales tax taxation rules** is set to **No**, the tax combination for the loaning legal entity will be used.</span></span> <span data-ttu-id="58d00-113">Ha ugyanaz a paraméter a **Cél** értékre van állítva, akkor a rendszer a kölcsönfelvevő jogi személyhez tartozó adózási kombinációt fogja használni.</span><span class="sxs-lookup"><span data-stu-id="58d00-113">When the same parameter is set to **Destination**, the tax combination for borrowing legal entity will be used.</span></span> <span data-ttu-id="58d00-114">Az Egyesült Államokban bejegyzett jogi személyek esetében, ha a paraméter **Forrás** értékre van beállítva, akkor a **Visszaigényelhető áfa** mezőt is az új **Főkönyvi feladási csoportok** lapon kell beállítani.</span><span class="sxs-lookup"><span data-stu-id="58d00-114">For legal entities in the United States, when the parameter is set to **Source**, the **Sales tax receivable** field must also be configured on the new **Ledger posting groups** page.</span></span> <span data-ttu-id="58d00-115">A könyvelési motor az ebből a mezőből származó adatokat fogja használni az adóval kapcsolatos könyvelési bejegyzésekhez.</span><span class="sxs-lookup"><span data-stu-id="58d00-115">The accounting engine will use the information from this field for tax related accounting entry.</span></span>   
<span data-ttu-id="58d00-116">A viselkedés összhangban van a projekttel vagy anélkül feladott kiadási sorokkal.</span><span class="sxs-lookup"><span data-stu-id="58d00-116">The behavior is consistent for expense lines posted with or without a project.</span></span>  
