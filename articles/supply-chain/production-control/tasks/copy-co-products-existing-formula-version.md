---
title: Társtermékek másolása meglévő receptúraverzióból
description: Ez az eljárás bemutatja, hogy hogyan másolhat társtermékeket egy már meglévő receptúraverzióból egy másik receptúraverzióba egy kiadott termékre vonatkozóan.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, BOMConsistOf, PmfFormulaCoBy, BOMRouteCopyDialog
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 626c0fc8a60eeb84060d7279833de583d55a95a2
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1838751"
---
# <a name="copy-co-products-from-an-existing-formula-version"></a><span data-ttu-id="4a5cf-103">Társtermékek másolása meglévő receptúraverzióból</span><span class="sxs-lookup"><span data-stu-id="4a5cf-103">Copy co-products from an existing formula version</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4a5cf-104">Ez az eljárás bemutatja, hogy hogyan másolhat társtermékeket egy már meglévő receptúraverzióból egy másik receptúraverzióba egy kiadott termékre vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="4a5cf-104">This procedure shows how to copy co-products from an existing formula version to a different formula version for a released product.</span></span> <span data-ttu-id="4a5cf-105">Az az előfeltétele, hogy legalább egy receptúraverziót társítani kell a társtermékekkel.</span><span class="sxs-lookup"><span data-stu-id="4a5cf-105">It is a prerequisite that there is at least one formula version associated with co-products.</span></span> <span data-ttu-id="4a5cf-106">Ez az eljárás az USP2 bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="4a5cf-106">The demo data company USP2 is used to create this procedure.</span></span>


## <a name="find-a-released-product"></a><span data-ttu-id="4a5cf-107">Keressen egy kiadott terméket.</span><span class="sxs-lookup"><span data-stu-id="4a5cf-107">Find a released product</span></span>
1. <span data-ttu-id="4a5cf-108">Ugrás a Kiadott termékek elemre.</span><span class="sxs-lookup"><span data-stu-id="4a5cf-108">Go to Released products.</span></span>
2. <span data-ttu-id="4a5cf-109">Kattintson a Szűrők megjelenítése pontra.</span><span class="sxs-lookup"><span data-stu-id="4a5cf-109">Click Show filters.</span></span>
    * <span data-ttu-id="4a5cf-110">A termelési mezőtípust készül hozzáadni a szűrő párbeszédpanelen.</span><span class="sxs-lookup"><span data-stu-id="4a5cf-110">You are about to add the field Production type in the filter dialog box.</span></span>  
3. <span data-ttu-id="4a5cf-111">Kattintson a Szűrőmező hozzáadása gombra a Termelés típusa mező hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="4a5cf-111">Click Add a filter field to add the field Production type.</span></span>
    * <span data-ttu-id="4a5cf-112">A következő lépésben manuálisan kell megadni a Receptúrát a Termelés típusa mezőben, mielőtt kiválasztja az Alkalmazás lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4a5cf-112">In the next step, you need to manually enter Formula in the Production type field before you select Apply.</span></span> <span data-ttu-id="4a5cf-113">Ez a lehetőség beállítja a kiadott termékek listáján szereplő szűrőt.</span><span class="sxs-lookup"><span data-stu-id="4a5cf-113">This sets the filter on the list of released products.</span></span>  
4. <span data-ttu-id="4a5cf-114">Adja meg manuálisan a Receptúrát a Termelés típusa mezőben.</span><span class="sxs-lookup"><span data-stu-id="4a5cf-114">Manually enter Formula in the Production type field.</span></span>
5. <span data-ttu-id="4a5cf-115">Kattintson az Alkalmaz gombra.</span><span class="sxs-lookup"><span data-stu-id="4a5cf-115">Click Apply.</span></span>

## <a name="select-a-released-product"></a><span data-ttu-id="4a5cf-116">Válasszon ki egy kiadott terméket.</span><span class="sxs-lookup"><span data-stu-id="4a5cf-116">Select a released product</span></span>
1. <span data-ttu-id="4a5cf-117">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="4a5cf-117">In the list, find and select the desired record.</span></span>
2. <span data-ttu-id="4a5cf-118">Kattintson a Receptúraverziók elemre.</span><span class="sxs-lookup"><span data-stu-id="4a5cf-118">Click Formula versions.</span></span>
    * <span data-ttu-id="4a5cf-119">Kattintson a Műszaki műveletpanelen a receptúraverziókra.</span><span class="sxs-lookup"><span data-stu-id="4a5cf-119">On the Engineering Action Pane, click Formula versions.</span></span>  

## <a name="copy-co-products"></a><span data-ttu-id="4a5cf-120">Társtermékek másolása</span><span class="sxs-lookup"><span data-stu-id="4a5cf-120">Copy co-products</span></span>
1. <span data-ttu-id="4a5cf-121">A Művelet panelen kattintson a Receptúraverzió elemre.</span><span class="sxs-lookup"><span data-stu-id="4a5cf-121">On the Action Pane, click Formula version.</span></span>
2. <span data-ttu-id="4a5cf-122">Kattintson a Társtermékek elemre.</span><span class="sxs-lookup"><span data-stu-id="4a5cf-122">Click Co-products.</span></span>
3. <span data-ttu-id="4a5cf-123">Kattintson a Másolás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4a5cf-123">Click Copy.</span></span>
4. <span data-ttu-id="4a5cf-124">Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="4a5cf-124">In the Item number field, enter or select a value.</span></span>
5. <span data-ttu-id="4a5cf-125">A Képletverzió mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="4a5cf-125">In the Formula version field, enter or select a value.</span></span>
6. <span data-ttu-id="4a5cf-126">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="4a5cf-126">Click OK.</span></span>
7. <span data-ttu-id="4a5cf-127">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="4a5cf-127">Close the page.</span></span>

