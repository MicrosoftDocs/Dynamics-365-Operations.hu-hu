---
title: Új kanbanszabály létrehozása egy meglévő kanbanszabály másolásával
description: Ez az eljárás egy létező kanbanszabály másolatának létrehozásával foglalkozik.
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanRules, KanbanRuleDuplicate, InventItemIdLookupSimple
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d80bf0318234f858e51fb461894238894e01717c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829066"
---
# <a name="create-a-new-kanban-rule-by-duplicating-an-existing-kanban-rule"></a><span data-ttu-id="580fd-103">Új kanbanszabály létrehozása egy meglévő kanbanszabály másolásával</span><span class="sxs-lookup"><span data-stu-id="580fd-103">Create a new kanban rule by duplicating an existing kanban rule</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="580fd-104">Ez az eljárás egy létező kanbanszabály másolatának létrehozásával foglalkozik.</span><span class="sxs-lookup"><span data-stu-id="580fd-104">This procedure focuses on creating a duplicate of an existing kanban rule.</span></span> <span data-ttu-id="580fd-105">Ez akkor hasznos, ha már létező kanbanszabályok alapján szeretne új kanbanszabályt létrehozni.</span><span class="sxs-lookup"><span data-stu-id="580fd-105">This is useful if you want to create new kanban rules based on existing kanban rules.</span></span> <span data-ttu-id="580fd-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="580fd-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="580fd-107">Ez az eljárás a folyamatmérnök vagy az érték-előállítási vezető munkáját segíti, mert ők készítik elő a termelést a módosított termelési folyamathoz vagy az új feltöltési szabályhoz.</span><span class="sxs-lookup"><span data-stu-id="580fd-107">This procedure is intended for the process engineer or the value stream manager as they prepare production for a changed production flow or a new replenishment rule.</span></span>


## <a name="select-a-kanban-rule"></a><span data-ttu-id="580fd-108">Válasszon ki egy kanbanszabályt</span><span class="sxs-lookup"><span data-stu-id="580fd-108">Select a kanban rule</span></span>
1. <span data-ttu-id="580fd-109">Ugorjon a Kanbanszabályokhoz.</span><span class="sxs-lookup"><span data-stu-id="580fd-109">Go to Kanban rules.</span></span>
2. <span data-ttu-id="580fd-110">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="580fd-110">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="580fd-111">Válassza ki a 000017 kanbanszabályt az M0006 termékhez.</span><span class="sxs-lookup"><span data-stu-id="580fd-111">Select kanban rule 000017 for Product M0006.</span></span>  

## <a name="duplicate-a-kanban-rule"></a><span data-ttu-id="580fd-112">Másolja a kanbanszabályt</span><span class="sxs-lookup"><span data-stu-id="580fd-112">Duplicate a kanban rule</span></span>
1. <span data-ttu-id="580fd-113">Kattintson a Kanbanszabály másolása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="580fd-113">Click Duplicate kanban rule.</span></span>
    * <span data-ttu-id="580fd-114">Egy kanbanszabály másolásakor lehetősége van módosítani a típust, a dátumokat, a tevékenységeket és a termékkiválasztást.</span><span class="sxs-lookup"><span data-stu-id="580fd-114">When duplicating a kanban rule, it is possible to change type, dates, activities, and the product selection.</span></span> <span data-ttu-id="580fd-115">A következő lépésben módosítsa a terméket ehhez az eljáráshoz.</span><span class="sxs-lookup"><span data-stu-id="580fd-115">Change the product for this procedure in the next step.</span></span>  
2. <span data-ttu-id="580fd-116">A Termék mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="580fd-116">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="580fd-117">Válassza az M0007 lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="580fd-117">Select M0007.</span></span>  
3. <span data-ttu-id="580fd-118">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="580fd-118">Click OK.</span></span>
    * <span data-ttu-id="580fd-119">Vegye figyelembe, hogy a 000017 kanbanszabályról létrejön egy másolat.</span><span class="sxs-lookup"><span data-stu-id="580fd-119">Note that a duplicate of kanban rule 000017 is created.</span></span>    



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]