--- 
title: "Új részlegek meghatározása"
description: "A részlegek olyan működési egységek, amelyek egy vállalat funkcionális területeként működnek, például: értékesítés vagy könyvelés."
author: kherr75
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: OMOperatingUnit, HierarchyDesigner, OMNodeSelection, HierarchyPublishAndCloseForm
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: 689d7d3fca4f48448b240b7561bbde26118bce54
ms.contentlocale: hu-hu
ms.lasthandoff: 09/11/2018

---
# <a name="define-new-departments"></a><span data-ttu-id="8bee6-103">Új részlegek meghatározása</span><span class="sxs-lookup"><span data-stu-id="8bee6-103">Define new departments</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8bee6-104">A részlegek olyan működési egységek, amelyek egy vállalat funkcionális területeként működnek, például: értékesítés vagy könyvelés.</span><span class="sxs-lookup"><span data-stu-id="8bee6-104">Departments are operating units that represent a functional area of a business, such as sales or accounting.</span></span> <span data-ttu-id="8bee6-105">Számos vállalat olyan szervezeti hierarchiával rendelkezik, amelyben a vállalaton belüli különböző részlegek is megjelennek.</span><span class="sxs-lookup"><span data-stu-id="8bee6-105">Many companies have organizational hierarchies that display the various departments within a business.</span></span> <span data-ttu-id="8bee6-106">Ez az eljárás végigvezeti a részlegek létrehozásával, valamint a részlegeknek a szervezeti hierarchiához való hozzáadásával kapcsolatos folyamatokon.</span><span class="sxs-lookup"><span data-stu-id="8bee6-106">This procedure walks through the process of creating departments, and adding those departments to an organizations departmental hierarchy.</span></span> <span data-ttu-id="8bee6-107">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="8bee6-107">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="8bee6-108">Ugrás az Emberi erőforrások > Részlegek > Részlegek menüpontra.</span><span class="sxs-lookup"><span data-stu-id="8bee6-108">Go to Human resources > Departments > Departments.</span></span>
2. <span data-ttu-id="8bee6-109">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="8bee6-109">Click New to open the drop dialog.</span></span>
3. <span data-ttu-id="8bee6-110">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="8bee6-110">In the Name field, type a value.</span></span>
    * <span data-ttu-id="8bee6-111">Példa: Projekt számlázása</span><span class="sxs-lookup"><span data-stu-id="8bee6-111">Example: Project billing</span></span>  
4. <span data-ttu-id="8bee6-112">A Memo mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="8bee6-112">In the Memo field, type a value.</span></span>
    * <span data-ttu-id="8bee6-113">Példa: Projekt számlázása</span><span class="sxs-lookup"><span data-stu-id="8bee6-113">Example: Project billing</span></span>  
5. <span data-ttu-id="8bee6-114">A Kezelő mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="8bee6-114">In the Manager field, enter or select a value.</span></span>
    * <span data-ttu-id="8bee6-115">Példa: Jodi Christiansen</span><span class="sxs-lookup"><span data-stu-id="8bee6-115">Example: Jodi Christiansen</span></span>  
6. <span data-ttu-id="8bee6-116">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="8bee6-116">Click Save.</span></span>
7. <span data-ttu-id="8bee6-117">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="8bee6-117">Close the page.</span></span>
8. <span data-ttu-id="8bee6-118">Ugrás az Emberi erőforrások > Részlegek > Részlegek hierarchiája menüpontra.</span><span class="sxs-lookup"><span data-stu-id="8bee6-118">Go to Human resources > Departments > Department hierarchy.</span></span>
9. <span data-ttu-id="8bee6-119">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8bee6-119">Click Edit.</span></span>
10. <span data-ttu-id="8bee6-120">Kattintson a Beszúrás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8bee6-120">Click Insert.</span></span>
11. <span data-ttu-id="8bee6-121">Kattintson a részleg lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8bee6-121">Click Department.</span></span>
12. <span data-ttu-id="8bee6-122">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="8bee6-122">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="8bee6-123">Példa: Projekt számlázása</span><span class="sxs-lookup"><span data-stu-id="8bee6-123">Example: Project billing</span></span>  
13. <span data-ttu-id="8bee6-124">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="8bee6-124">Click OK.</span></span>
14. <span data-ttu-id="8bee6-125">A Közzététel gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="8bee6-125">Click Publish to open the drop dialog.</span></span>
15. <span data-ttu-id="8bee6-126">Az Érvényesség dátuma mezőben adjon meg egy dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="8bee6-126">In the Effective date field, enter a date and time.</span></span>
    * <span data-ttu-id="8bee6-127">A szervezeti hierarchia közzétételekor kiválaszthatja, hogy a módosítások mikor lépjenek érvénybe.</span><span class="sxs-lookup"><span data-stu-id="8bee6-127">When publishing the department hierarchy, you can select when to make the changes effective.</span></span> <span data-ttu-id="8bee6-128">A módosítások jövőbeni dátummal is rendelkezhetnek.</span><span class="sxs-lookup"><span data-stu-id="8bee6-128">Changes can be future dated.</span></span> <span data-ttu-id="8bee6-129">Például előfordulhat, hogy a pénzügyi év kezdetén tudni fogja, hogy fel szeretne venni egy további osztályt.</span><span class="sxs-lookup"><span data-stu-id="8bee6-129">For example, you may know that at the beginning of your fiscal year you will be adding an additional department.</span></span> <span data-ttu-id="8bee6-130">A hatályos dátumot a pénzügyi év elejére is beállíthatja, és akkor a hierarchiára vonatkozó módosítások azon a napon lépnek érvénybe.</span><span class="sxs-lookup"><span data-stu-id="8bee6-130">You can set your effective date to the beginning of the fiscal year, and the changes to the hierarchy will be effective on that date.</span></span>  
16. <span data-ttu-id="8bee6-131">Írjon be egy értéket a Változások leírása mezőbe.</span><span class="sxs-lookup"><span data-stu-id="8bee6-131">In the Describe changes field, type a value.</span></span>
17. <span data-ttu-id="8bee6-132">Kattintson a Közzététel parancsra.</span><span class="sxs-lookup"><span data-stu-id="8bee6-132">Click Publish.</span></span>


