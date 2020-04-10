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
ms.openlocfilehash: 93742819f492c0c169a6ca8dc2d486fe35ec4a5c
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3149343"
---
# <a name="copy-co-products-from-an-existing-formula-version"></a><span data-ttu-id="fe7c2-103">Társtermékek másolása meglévő receptúraverzióból</span><span class="sxs-lookup"><span data-stu-id="fe7c2-103">Copy co-products from an existing formula version</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fe7c2-104">Ez az eljárás bemutatja, hogy hogyan másolhat társtermékeket egy már meglévő receptúraverzióból egy másik receptúraverzióba egy kiadott termékre vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="fe7c2-104">This procedure shows how to copy co-products from an existing formula version to a different formula version for a released product.</span></span> <span data-ttu-id="fe7c2-105">Az az előfeltétele, hogy legalább egy receptúraverziót társítani kell a társtermékekkel.</span><span class="sxs-lookup"><span data-stu-id="fe7c2-105">It is a prerequisite that there is at least one formula version associated with co-products.</span></span> <span data-ttu-id="fe7c2-106">Ez az eljárás az USP2 bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="fe7c2-106">The demo data company USP2 is used to create this procedure.</span></span>


## <a name="find-a-released-product"></a><span data-ttu-id="fe7c2-107">Keressen egy kiadott terméket.</span><span class="sxs-lookup"><span data-stu-id="fe7c2-107">Find a released product</span></span>
1. <span data-ttu-id="fe7c2-108">Ugrás a Kiadott termékek elemre.</span><span class="sxs-lookup"><span data-stu-id="fe7c2-108">Go to Released products.</span></span>
2. <span data-ttu-id="fe7c2-109">Kattintson a Szűrők megjelenítése pontra.</span><span class="sxs-lookup"><span data-stu-id="fe7c2-109">Click Show filters.</span></span>
    * <span data-ttu-id="fe7c2-110">A termelési mezőtípust készül hozzáadni a szűrő párbeszédpanelen.</span><span class="sxs-lookup"><span data-stu-id="fe7c2-110">You are about to add the field Production type in the filter dialog box.</span></span>  
3. <span data-ttu-id="fe7c2-111">Kattintson a Szűrőmező hozzáadása gombra a Termelés típusa mező hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="fe7c2-111">Click Add a filter field to add the field Production type.</span></span>
    * <span data-ttu-id="fe7c2-112">A következő lépésben manuálisan kell megadni a Receptúrát a Termelés típusa mezőben, mielőtt kiválasztja az Alkalmazás lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="fe7c2-112">In the next step, you need to manually enter Formula in the Production type field before you select Apply.</span></span> <span data-ttu-id="fe7c2-113">Ez a lehetőség beállítja a kiadott termékek listáján szereplő szűrőt.</span><span class="sxs-lookup"><span data-stu-id="fe7c2-113">This sets the filter on the list of released products.</span></span>  
4. <span data-ttu-id="fe7c2-114">Adja meg manuálisan a Receptúrát a Termelés típusa mezőben.</span><span class="sxs-lookup"><span data-stu-id="fe7c2-114">Manually enter Formula in the Production type field.</span></span>
5. <span data-ttu-id="fe7c2-115">Kattintson az Alkalmaz gombra.</span><span class="sxs-lookup"><span data-stu-id="fe7c2-115">Click Apply.</span></span>

## <a name="select-a-released-product"></a><span data-ttu-id="fe7c2-116">Válasszon ki egy kiadott terméket.</span><span class="sxs-lookup"><span data-stu-id="fe7c2-116">Select a released product</span></span>
1. <span data-ttu-id="fe7c2-117">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="fe7c2-117">In the list, find and select the desired record.</span></span>
2. <span data-ttu-id="fe7c2-118">Kattintson a Receptúraverziók elemre.</span><span class="sxs-lookup"><span data-stu-id="fe7c2-118">Click Formula versions.</span></span>
    * <span data-ttu-id="fe7c2-119">Kattintson a Műszaki műveletpanelen a receptúraverziókra.</span><span class="sxs-lookup"><span data-stu-id="fe7c2-119">On the Engineering Action Pane, click Formula versions.</span></span>  

## <a name="copy-co-products"></a><span data-ttu-id="fe7c2-120">Társtermékek másolása</span><span class="sxs-lookup"><span data-stu-id="fe7c2-120">Copy co-products</span></span>
1. <span data-ttu-id="fe7c2-121">A Művelet panelen kattintson a Receptúraverzió elemre.</span><span class="sxs-lookup"><span data-stu-id="fe7c2-121">On the Action Pane, click Formula version.</span></span>
2. <span data-ttu-id="fe7c2-122">Kattintson a Társtermékek elemre.</span><span class="sxs-lookup"><span data-stu-id="fe7c2-122">Click Co-products.</span></span>
3. <span data-ttu-id="fe7c2-123">Kattintson a Másolás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="fe7c2-123">Click Copy.</span></span>
4. <span data-ttu-id="fe7c2-124">Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="fe7c2-124">In the Item number field, enter or select a value.</span></span>
5. <span data-ttu-id="fe7c2-125">A Képletverzió mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="fe7c2-125">In the Formula version field, enter or select a value.</span></span>
6. <span data-ttu-id="fe7c2-126">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="fe7c2-126">Click OK.</span></span>
7. <span data-ttu-id="fe7c2-127">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="fe7c2-127">Close the page.</span></span>

