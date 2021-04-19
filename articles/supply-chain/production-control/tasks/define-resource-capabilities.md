---
title: Erőforrás-képességek meghatározása
description: Az erőforrás-képességek azt mutatják, hogy az erőforrások milyen műveleteket képesek elvégezni.
author: sorenva
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WrkCtrCapability
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 072991e7b3844ad3583b7d0c575d426299f74e9f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828706"
---
# <a name="define-resource-capabilities"></a><span data-ttu-id="9fb20-103">Erőforrás-képességek meghatározása</span><span class="sxs-lookup"><span data-stu-id="9fb20-103">Define resource capabilities</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9fb20-104">Az erőforrás-képességek azt mutatják, hogy az erőforrások milyen műveleteket képesek elvégezni.</span><span class="sxs-lookup"><span data-stu-id="9fb20-104">Resource capabilities describe what operations resources can do.</span></span> <span data-ttu-id="9fb20-105">Az ütemezés során a feladat és a művelet követelményeihez hozzárendelődnek a rendelkezésre álló erőforrások képességei.</span><span class="sxs-lookup"><span data-stu-id="9fb20-105">During scheduling, the requirements of each job and operation are matched against the capabilities of the available resources.</span></span> <span data-ttu-id="9fb20-106">Ez az útmutató segít létrehozni egy erőforrás-képességet, és azt hozzárendelni egy erőforráshoz.</span><span class="sxs-lookup"><span data-stu-id="9fb20-106">This task guide will help you create a resource capability and assign it to a resource.</span></span> <span data-ttu-id="9fb20-107">A feladat létrehozásához az USMF bemutató vállalatot használtuk példaként.</span><span class="sxs-lookup"><span data-stu-id="9fb20-107">The demo data company used to create this task is USMF.</span></span>


## <a name="create-a-resource-capability"></a><span data-ttu-id="9fb20-108">Új erőforrás-képesség létrehozása</span><span class="sxs-lookup"><span data-stu-id="9fb20-108">Create a resource capability</span></span>
1. <span data-ttu-id="9fb20-109">Menjen rá az erőforrás-képességekre.</span><span class="sxs-lookup"><span data-stu-id="9fb20-109">Go to Resource capabilities.</span></span>
2. <span data-ttu-id="9fb20-110">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="9fb20-110">Click New.</span></span>
3. <span data-ttu-id="9fb20-111">A Képesség mezőbe írja be az erőforrás képességének azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="9fb20-111">In the Capability field, type the ID of the resource capability.</span></span>
    * <span data-ttu-id="9fb20-112">Egy adott művelethez a képesség azonosítóját adja meg, hogy meghatározza, hogy az erőforrásoknak ezzel a képességgel kell rendelkezniük a művelet végrehajtásához.</span><span class="sxs-lookup"><span data-stu-id="9fb20-112">For a given operation, you use the capability ID to specify that resources must have this capability to perform the operation.</span></span>  
4. <span data-ttu-id="9fb20-113">Adja meg a képesség leírását a Leírás mezőben.</span><span class="sxs-lookup"><span data-stu-id="9fb20-113">In the Description field, enter a description of the capability.</span></span>

## <a name="assign-capability-to-a-resource"></a><span data-ttu-id="9fb20-114">Képesség hozzárendelése egy erőforráshoz.</span><span class="sxs-lookup"><span data-stu-id="9fb20-114">Assign capability to a resource</span></span>
1. <span data-ttu-id="9fb20-115">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="9fb20-115">Click Add.</span></span>
2. <span data-ttu-id="9fb20-116">Az Erőforrás mezőbe írja be az erőforrás azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="9fb20-116">In the Resource field, type the ID of the resource.</span></span>
    * <span data-ttu-id="9fb20-117">Egy erőforrás-képesség hozzárendelhető egy vagy több erőforráshoz.</span><span class="sxs-lookup"><span data-stu-id="9fb20-117">A resource capability can be assigned to one or more resources.</span></span>  
3. <span data-ttu-id="9fb20-118">A Lejárat ideje mezőben adjon meg egy dátumot.</span><span class="sxs-lookup"><span data-stu-id="9fb20-118">In the Expiration field, enter a date.</span></span>
    * <span data-ttu-id="9fb20-119">A mező segítségével adhatja meg, hogy az erőforrás képessége csak korlátozott időtartamra adott.</span><span class="sxs-lookup"><span data-stu-id="9fb20-119">You can use this field to specify that a resource has the capability for only a limited time.</span></span>  
4. <span data-ttu-id="9fb20-120">Adjon meg egy számot a Prioritás mezőben.</span><span class="sxs-lookup"><span data-stu-id="9fb20-120">In the Priority field, enter a number.</span></span>
    * <span data-ttu-id="9fb20-121">Feladatok és műveletek ütemezésekor meg lehet adni, hogy prioritás szerint kívánja-e kijelölni az erőforrásokat.</span><span class="sxs-lookup"><span data-stu-id="9fb20-121">When you schedule jobs and operations, you can specify whether to select resources by priority.</span></span> <span data-ttu-id="9fb20-122">Ha ezt választja, és egynél több erőforrás tudja elvégezni feladatot vagy műveletet a kért dátumig, a szükséges képesség tekintetében legalacsonyabb prioritású erőforrás lesz jelölve.</span><span class="sxs-lookup"><span data-stu-id="9fb20-122">If you choose to do this, and more than one resource can perform the job or operation by the requested date, the resource that has the lowest priority with respect to the required capability is selected.</span></span>  
5. <span data-ttu-id="9fb20-123">Adjon meg egy számot a Szint mezőben.</span><span class="sxs-lookup"><span data-stu-id="9fb20-123">In the Level field, enter a number.</span></span>
    * <span data-ttu-id="9fb20-124">Amikor Ön határozza meg, hogy a feladat vagy a művelet egy adott képességet igényel, meghatározhatja a szükséges minimális szintet is.</span><span class="sxs-lookup"><span data-stu-id="9fb20-124">When you specify that a job or operation requires a particular capability, you can also specify the minimum level that is required.</span></span> <span data-ttu-id="9fb20-125">A képesség szint segítségével különbséget tehet azon erőforrások között, amelyek ugyanazt a feladatot hajthatják végre, de eltérő sebességgel, méretben, és stb.</span><span class="sxs-lookup"><span data-stu-id="9fb20-125">Use the capability level to differentiate resources that can perform the same job, but at different speeds, strengths, sizes, and so on.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]