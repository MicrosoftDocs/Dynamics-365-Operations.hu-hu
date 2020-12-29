---
title: Elkülönített gyártási erőforráscsoport meghatározása
description: Egy erőforráscsoport üzemi erőforrások csoportja, amelyek általában megfelelnek a munkacellák fizikai elrendezésének, amelyet a termelésben a padlón lévő sárga vonalak jelölnek.
author: sorenva
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WrkCtrResourceGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: eaccb566c04d6d4b91ea8cb046931e750a4c6eed
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429222"
---
# <a name="define-discrete-manufacturing-resource-group"></a><span data-ttu-id="3f328-103">Elkülönített gyártási erőforráscsoport meghatározása</span><span class="sxs-lookup"><span data-stu-id="3f328-103">Define discrete manufacturing resource group</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3f328-104">Egy erőforráscsoport üzemi erőforrások csoportja, amelyek általában megfelelnek a munkacellák fizikai elrendezésének, amelyet a termelésben a padlón lévő sárga vonalak jelölnek.</span><span class="sxs-lookup"><span data-stu-id="3f328-104">A resource group is a set of operations resources that typically correspond to the physical organization of work cells, defined by yellow lines on the production shop floor.</span></span> <span data-ttu-id="3f328-105">Ez az eljárás bemutatja, hogyan adjon meg egy erőforráscsoportot különálló termelésben való használathoz..</span><span class="sxs-lookup"><span data-stu-id="3f328-105">This procedure shows you how to define a ressource group for use in discrete production.</span></span> <span data-ttu-id="3f328-106">Ezt a folyamatot az USMF bemutatócégen vagy saját adatai használatával is elvégezheti.</span><span class="sxs-lookup"><span data-stu-id="3f328-106">You can walk through this procedure in demo data company USMF, or use your own data.</span></span>

1. <span data-ttu-id="3f328-107">Ugrás az erőforráscsoportokra.</span><span class="sxs-lookup"><span data-stu-id="3f328-107">Go to Resource groups.</span></span>
2. <span data-ttu-id="3f328-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3f328-108">Click New.</span></span>
3. <span data-ttu-id="3f328-109">Írjon be egy értéket az Erőforráscsoport mezőbe.</span><span class="sxs-lookup"><span data-stu-id="3f328-109">In the Resource group field, type a value.</span></span>
4. <span data-ttu-id="3f328-110">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="3f328-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="3f328-111">A Hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="3f328-111">In the Site field, enter or select a value.</span></span>
6. <span data-ttu-id="3f328-112">A Termelési egység mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="3f328-112">In the Production unit field, enter or select a value.</span></span>

## <a name="define-default-operational-parameters"></a><span data-ttu-id="3f328-113">Alapértelmezett működési paraméterek meghatározása</span><span class="sxs-lookup"><span data-stu-id="3f328-113">Define default operational parameters</span></span>
1. <span data-ttu-id="3f328-114">Bontsa ki a Művelet szakaszt.</span><span class="sxs-lookup"><span data-stu-id="3f328-114">Expand the Operation section.</span></span>
2. <span data-ttu-id="3f328-115">Adjon meg egy számot a Selejtszázalék mezőben.</span><span class="sxs-lookup"><span data-stu-id="3f328-115">In the Scrap percentage field, enter a number.</span></span>
3. <span data-ttu-id="3f328-116">A Beállítási kategória mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="3f328-116">In the Setup category field, enter or select a value.</span></span>
4. <span data-ttu-id="3f328-117">A Lefutásiidő-kategória mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="3f328-117">In the Run time category field, enter or select a value.</span></span>
5. <span data-ttu-id="3f328-118">A Műveletütemezés százalék mezőjében adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="3f328-118">In the Operations scheduling percentage field, enter a number.</span></span>

## <a name="define-operating-hours"></a><span data-ttu-id="3f328-119">Működési óraszám megadása</span><span class="sxs-lookup"><span data-stu-id="3f328-119">Define operating hours</span></span>
1. <span data-ttu-id="3f328-120">Bontsa ki a Naptárak szakaszt.</span><span class="sxs-lookup"><span data-stu-id="3f328-120">Expand the Calendars section.</span></span>
2. <span data-ttu-id="3f328-121">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="3f328-121">Click Add.</span></span>
3. <span data-ttu-id="3f328-122">A Naptárak mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="3f328-122">In the Calendar field, enter or select a value.</span></span>

## <a name="add-operations-resources"></a><span data-ttu-id="3f328-123">Üzemi erőforrások hozzáadása</span><span class="sxs-lookup"><span data-stu-id="3f328-123">Add operations resources</span></span>
1. <span data-ttu-id="3f328-124">Bontsa ki az Erőforrások szakaszt.</span><span class="sxs-lookup"><span data-stu-id="3f328-124">Expand the Resources section.</span></span>
2. <span data-ttu-id="3f328-125">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="3f328-125">Click Add.</span></span>
3. <span data-ttu-id="3f328-126">Az Erőforrások mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="3f328-126">In the Resource field, enter or select a value.</span></span>
4. <span data-ttu-id="3f328-127">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="3f328-127">Click Add.</span></span>
5. <span data-ttu-id="3f328-128">Az Erőforrások mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="3f328-128">In the Resource field, enter or select a value.</span></span>
6. <span data-ttu-id="3f328-129">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="3f328-129">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="3f328-130">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="3f328-130">In the list, click the link in the selected row.</span></span>

