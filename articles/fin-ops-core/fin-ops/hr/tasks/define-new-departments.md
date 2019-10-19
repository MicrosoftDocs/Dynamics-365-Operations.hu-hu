---
title: Új részlegek meghatározása
description: 'A részlegek olyan működési egységek, amelyek egy vállalat funkcionális területeként működnek, például: értékesítés vagy könyvelés.'
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: OMOperatingUnit, HierarchyDesigner, OMNodeSelection, HierarchyPublishAndCloseForm
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a20b98e755cf5269b72d245156bbd44fd71a3185
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2190580"
---
# <a name="define-new-departments"></a><span data-ttu-id="4c303-103">Új részlegek meghatározása</span><span class="sxs-lookup"><span data-stu-id="4c303-103">Define new departments</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4c303-104">A részlegek olyan működési egységek, amelyek egy vállalat funkcionális területeként működnek, például: értékesítés vagy könyvelés.</span><span class="sxs-lookup"><span data-stu-id="4c303-104">Departments are operating units that represent a functional area of a business, such as sales or accounting.</span></span> <span data-ttu-id="4c303-105">Számos vállalat olyan szervezeti hierarchiával rendelkezik, amelyben a vállalaton belüli különböző részlegek is megjelennek.</span><span class="sxs-lookup"><span data-stu-id="4c303-105">Many companies have organizational hierarchies that display the various departments within a business.</span></span> <span data-ttu-id="4c303-106">Ez az eljárás végigvezeti a részlegek létrehozásával, valamint a részlegeknek a szervezeti hierarchiához való hozzáadásával kapcsolatos folyamatokon.</span><span class="sxs-lookup"><span data-stu-id="4c303-106">This procedure walks through the process of creating departments, and adding those departments to an organizations departmental hierarchy.</span></span> <span data-ttu-id="4c303-107">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="4c303-107">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="4c303-108">Ugrás az Emberi erőforrások > Részlegek > Részlegek menüpontra.</span><span class="sxs-lookup"><span data-stu-id="4c303-108">Go to Human resources > Departments > Departments.</span></span>
2. <span data-ttu-id="4c303-109">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="4c303-109">Click New to open the drop dialog.</span></span>
3. <span data-ttu-id="4c303-110">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="4c303-110">In the Name field, type a value.</span></span>
    * <span data-ttu-id="4c303-111">Példa: Projekt számlázása</span><span class="sxs-lookup"><span data-stu-id="4c303-111">Example: Project billing</span></span>  
4. <span data-ttu-id="4c303-112">A Memo mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="4c303-112">In the Memo field, type a value.</span></span>
    * <span data-ttu-id="4c303-113">Példa: Projekt számlázása</span><span class="sxs-lookup"><span data-stu-id="4c303-113">Example: Project billing</span></span>  
5. <span data-ttu-id="4c303-114">A Kezelő mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="4c303-114">In the Manager field, enter or select a value.</span></span>
    * <span data-ttu-id="4c303-115">Példa: Jodi Christiansen</span><span class="sxs-lookup"><span data-stu-id="4c303-115">Example: Jodi Christiansen</span></span>  
6. <span data-ttu-id="4c303-116">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="4c303-116">Click Save.</span></span>
7. <span data-ttu-id="4c303-117">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="4c303-117">Close the page.</span></span>
8. <span data-ttu-id="4c303-118">Ugrás az Emberi erőforrások > Részlegek > Részlegek hierarchiája menüpontra.</span><span class="sxs-lookup"><span data-stu-id="4c303-118">Go to Human resources > Departments > Department hierarchy.</span></span>
9. <span data-ttu-id="4c303-119">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4c303-119">Click Edit.</span></span>
10. <span data-ttu-id="4c303-120">Kattintson a Beszúrás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4c303-120">Click Insert.</span></span>
11. <span data-ttu-id="4c303-121">Kattintson a részleg lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4c303-121">Click Department.</span></span>
12. <span data-ttu-id="4c303-122">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="4c303-122">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="4c303-123">Példa: Projekt számlázása</span><span class="sxs-lookup"><span data-stu-id="4c303-123">Example: Project billing</span></span>  
13. <span data-ttu-id="4c303-124">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="4c303-124">Click OK.</span></span>
14. <span data-ttu-id="4c303-125">A Közzététel gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="4c303-125">Click Publish to open the drop dialog.</span></span>
15. <span data-ttu-id="4c303-126">Az Érvényesség dátuma mezőben adjon meg egy dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="4c303-126">In the Effective date field, enter a date and time.</span></span>
    * <span data-ttu-id="4c303-127">A szervezeti hierarchia közzétételekor kiválaszthatja, hogy a módosítások mikor lépjenek érvénybe.</span><span class="sxs-lookup"><span data-stu-id="4c303-127">When publishing the department hierarchy, you can select when to make the changes effective.</span></span> <span data-ttu-id="4c303-128">A módosítások jövőbeni dátummal is rendelkezhetnek.</span><span class="sxs-lookup"><span data-stu-id="4c303-128">Changes can be future dated.</span></span> <span data-ttu-id="4c303-129">Például előfordulhat, hogy a pénzügyi év kezdetén tudni fogja, hogy fel szeretne venni egy további osztályt.</span><span class="sxs-lookup"><span data-stu-id="4c303-129">For example, you may know that at the beginning of your fiscal year you will be adding an additional department.</span></span> <span data-ttu-id="4c303-130">A hatályos dátumot a pénzügyi év elejére is beállíthatja, és akkor a hierarchiára vonatkozó módosítások azon a napon lépnek érvénybe.</span><span class="sxs-lookup"><span data-stu-id="4c303-130">You can set your effective date to the beginning of the fiscal year, and the changes to the hierarchy will be effective on that date.</span></span>  
16. <span data-ttu-id="4c303-131">Írjon be egy értéket a Változások leírása mezőbe.</span><span class="sxs-lookup"><span data-stu-id="4c303-131">In the Describe changes field, type a value.</span></span>
17. <span data-ttu-id="4c303-132">Kattintson a Közzététel parancsra.</span><span class="sxs-lookup"><span data-stu-id="4c303-132">Click Publish.</span></span>

