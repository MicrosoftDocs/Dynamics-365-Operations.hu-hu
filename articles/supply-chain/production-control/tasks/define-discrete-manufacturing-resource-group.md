---
title: Elkülönített gyártási erőforráscsoport meghatározása
description: Egy erőforráscsoport üzemi erőforrások csoportja, amelyek általában megfelelnek a munkacellák fizikai elrendezésének, amelyet a termelésben a padlón lévő sárga vonalak jelölnek.
author: sorenva
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WrkCtrResourceGroup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 01b797aa97e73cbe112c37a1efcd1e759730bc24
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3149113"
---
# <a name="define-discrete-manufacturing-resource-group"></a><span data-ttu-id="00418-103">Elkülönített gyártási erőforráscsoport meghatározása</span><span class="sxs-lookup"><span data-stu-id="00418-103">Define discrete manufacturing resource group</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="00418-104">Egy erőforráscsoport üzemi erőforrások csoportja, amelyek általában megfelelnek a munkacellák fizikai elrendezésének, amelyet a termelésben a padlón lévő sárga vonalak jelölnek.</span><span class="sxs-lookup"><span data-stu-id="00418-104">A resource group is a set of operations resources that typically correspond to the physical organization of work cells, defined by yellow lines on the production shop floor.</span></span> <span data-ttu-id="00418-105">Ez az eljárás bemutatja, hogyan adjon meg egy erőforráscsoportot különálló termelésben való használathoz..</span><span class="sxs-lookup"><span data-stu-id="00418-105">This procedure shows you how to define a ressource group for use in discrete production.</span></span> <span data-ttu-id="00418-106">Ezt a folyamatot az USMF bemutatócégen vagy saját adatai használatával is elvégezheti.</span><span class="sxs-lookup"><span data-stu-id="00418-106">You can walk through this procedure in demo data company USMF, or use your own data.</span></span>

1. <span data-ttu-id="00418-107">Ugrás az erőforráscsoportokra.</span><span class="sxs-lookup"><span data-stu-id="00418-107">Go to Resource groups.</span></span>
2. <span data-ttu-id="00418-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="00418-108">Click New.</span></span>
3. <span data-ttu-id="00418-109">Írjon be egy értéket az Erőforráscsoport mezőbe.</span><span class="sxs-lookup"><span data-stu-id="00418-109">In the Resource group field, type a value.</span></span>
4. <span data-ttu-id="00418-110">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="00418-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="00418-111">A Hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="00418-111">In the Site field, enter or select a value.</span></span>
6. <span data-ttu-id="00418-112">A Termelési egység mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="00418-112">In the Production unit field, enter or select a value.</span></span>

## <a name="define-default-operational-parameters"></a><span data-ttu-id="00418-113">Alapértelmezett működési paraméterek meghatározása</span><span class="sxs-lookup"><span data-stu-id="00418-113">Define default operational parameters</span></span>
1. <span data-ttu-id="00418-114">Bontsa ki a Művelet szakaszt.</span><span class="sxs-lookup"><span data-stu-id="00418-114">Expand the Operation section.</span></span>
2. <span data-ttu-id="00418-115">Adjon meg egy számot a Selejtszázalék mezőben.</span><span class="sxs-lookup"><span data-stu-id="00418-115">In the Scrap percentage field, enter a number.</span></span>
3. <span data-ttu-id="00418-116">A Beállítási kategória mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="00418-116">In the Setup category field, enter or select a value.</span></span>
4. <span data-ttu-id="00418-117">A Lefutásiidő-kategória mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="00418-117">In the Run time category field, enter or select a value.</span></span>
5. <span data-ttu-id="00418-118">A Műveletütemezés százalék mezőjében adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="00418-118">In the Operations scheduling percentage field, enter a number.</span></span>

## <a name="define-operating-hours"></a><span data-ttu-id="00418-119">Működési óraszám megadása</span><span class="sxs-lookup"><span data-stu-id="00418-119">Define operating hours</span></span>
1. <span data-ttu-id="00418-120">Bontsa ki a Naptárak szakaszt.</span><span class="sxs-lookup"><span data-stu-id="00418-120">Expand the Calendars section.</span></span>
2. <span data-ttu-id="00418-121">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="00418-121">Click Add.</span></span>
3. <span data-ttu-id="00418-122">A Naptárak mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="00418-122">In the Calendar field, enter or select a value.</span></span>

## <a name="add-operations-resources"></a><span data-ttu-id="00418-123">Üzemi erőforrások hozzáadása</span><span class="sxs-lookup"><span data-stu-id="00418-123">Add operations resources</span></span>
1. <span data-ttu-id="00418-124">Bontsa ki az Erőforrások szakaszt.</span><span class="sxs-lookup"><span data-stu-id="00418-124">Expand the Resources section.</span></span>
2. <span data-ttu-id="00418-125">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="00418-125">Click Add.</span></span>
3. <span data-ttu-id="00418-126">Az Erőforrások mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="00418-126">In the Resource field, enter or select a value.</span></span>
4. <span data-ttu-id="00418-127">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="00418-127">Click Add.</span></span>
5. <span data-ttu-id="00418-128">Az Erőforrások mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="00418-128">In the Resource field, enter or select a value.</span></span>
6. <span data-ttu-id="00418-129">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="00418-129">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="00418-130">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="00418-130">In the list, click the link in the selected row.</span></span>

