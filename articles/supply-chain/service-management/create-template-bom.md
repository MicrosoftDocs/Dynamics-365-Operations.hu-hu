---
title: Sablonanyagjegyzék létrehozása
description: Különböző módszerek segítségével hozhat létre sablonanyagjegyzéket.
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMATemplateBOMTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 89c5d45ac27a8678c51fb63c0326c2802a094596
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "320995"
---
# <a name="create-a-template-bom"></a><span data-ttu-id="57739-103">Sablonanyagjegyzék létrehozása</span><span class="sxs-lookup"><span data-stu-id="57739-103">Create a template BOM</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="57739-104">Az alábbi módszerek bármelyikével létrehozhat sablonanyagjegyzéket.</span><span class="sxs-lookup"><span data-stu-id="57739-104">You can create a template BOM by using any of the following methods.</span></span> <span data-ttu-id="57739-105">A **Kezdő dátum** és a **Záró dátum** mezők használata egyik esetben sem kötelező, csak tájékoztatásra szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="57739-105">For all methods, the **From date** and **To date** fields are optional and for information only.</span></span>

## <a name="create-a-template-bom-manually"></a><span data-ttu-id="57739-106">Sablonanyagjegyzék létrehozása manuálisan</span><span class="sxs-lookup"><span data-stu-id="57739-106">Create a template BOM manually</span></span>

1.  <span data-ttu-id="57739-107">Kattintson a **Szolgáltatáskezelés** \> **Beállítás** \> **A szolgáltatás tárgyai** \> **Sablonanyagjegyzékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="57739-107">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="57739-108">Nyomja le a CTRL+N billentyűkombinációt, hogy megnyissa a **Sablonanyagjegyzék létrehozása** képernyőt.</span><span class="sxs-lookup"><span data-stu-id="57739-108">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="57739-109">Az **Anyagjegyzéksorok másolása hivatkozásból** elemnél jelölje be a **Kézi** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="57739-109">Under **Copy BOM lines from reference**, select the **Manual** option.</span></span>

4.  <span data-ttu-id="57739-110">A **Cikkszám** mezőben adjon meg egy **Anyagjegyzék** típusú cikket.</span><span class="sxs-lookup"><span data-stu-id="57739-110">In the **Item number** field, enter an item of the type **BOM**.</span></span>

5.  <span data-ttu-id="57739-111">Adjon nevet a sablonnak a **Név** mezőben.</span><span class="sxs-lookup"><span data-stu-id="57739-111">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="57739-112">Adja meg a **Kezdő dátum** és a **Záró dátum** mezőben azt a dátumintervallumot, amelyben aktív a sablonanyagjegyzék.</span><span class="sxs-lookup"><span data-stu-id="57739-112">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="57739-113">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="57739-113">Click **OK**.</span></span>

<span data-ttu-id="57739-114">Létrejön egy új, üres sablonanyagjegyzék.</span><span class="sxs-lookup"><span data-stu-id="57739-114">A new, blank template BOM is created.</span></span>

## <a name="create-a-template-bom-based-on-another-template-bom"></a><span data-ttu-id="57739-115">Sablonanyagjegyzék létrehozása másik sablonanyagjegyzék alapján</span><span class="sxs-lookup"><span data-stu-id="57739-115">Create a template BOM based on another template BOM</span></span>

1.  <span data-ttu-id="57739-116">Kattintson a **Szolgáltatáskezelés** \> **Beállítás** \> **A szolgáltatás tárgyai** \> **Sablonanyagjegyzékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="57739-116">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="57739-117">Nyomja le a CTRL+N billentyűkombinációt, hogy megnyissa a **Sablonanyagjegyzék létrehozása** képernyőt.</span><span class="sxs-lookup"><span data-stu-id="57739-117">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="57739-118">Az **Anyagjegyzéksorok másolása hivatkozásból** elemnél jelölje be az **Anyagjegyzék-sablon** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="57739-118">Under **Copy BOM lines from reference**, select the **Template BOM** option.</span></span>

4.  <span data-ttu-id="57739-119">A **Hivatkozási szám** mezőben válasszon egy létező sablonanyagjegyzéket, amelyet átmásol az új sablonanyagjegyzékbe.</span><span class="sxs-lookup"><span data-stu-id="57739-119">In the **Reference number** field, select an existing template BOM to copy to your new template BOM.</span></span>

5.  <span data-ttu-id="57739-120">Adjon nevet a sablonnak a **Név** mezőben.</span><span class="sxs-lookup"><span data-stu-id="57739-120">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="57739-121">Adja meg a **Kezdő dátum** és a **Záró dátum** mezőben azt a dátumintervallumot, amelyben aktív a sablonanyagjegyzék.</span><span class="sxs-lookup"><span data-stu-id="57739-121">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="57739-122">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="57739-122">Click **OK**.</span></span>

<span data-ttu-id="57739-123">Egy új sablonanyagjegyzék jön létre az eredeti sablonanyagjegyzék soraival megegyező sorokkal.</span><span class="sxs-lookup"><span data-stu-id="57739-123">A new template BOM is created by using lines that correspond to the lines in the original template BOM.</span></span>

## <a name="create-a-template-bom-based-on-an-item-bom"></a><span data-ttu-id="57739-124">Sablonanyagjegyzék létrehozása cikkanyagjegyzék alapján</span><span class="sxs-lookup"><span data-stu-id="57739-124">Create a template BOM based on an item BOM</span></span>

1.  <span data-ttu-id="57739-125">Kattintson a **Szolgáltatáskezelés** \> **Beállítás** \> **A szolgáltatás tárgyai** \> **Sablonanyagjegyzékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="57739-125">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="57739-126">Nyomja le a CTRL+N billentyűkombinációt, hogy megnyissa a **Sablonanyagjegyzék létrehozása** képernyőt.</span><span class="sxs-lookup"><span data-stu-id="57739-126">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="57739-127">Az **Anyagjegyzéksorok másolása hivatkozásból** elemnél jelölje be az **Anyagjegyzék** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="57739-127">Under **Copy BOM lines from reference**, select **BOM**.</span></span>

4.  <span data-ttu-id="57739-128">A **Hivatkozási szám** mezőben, válasszon ki egy anyagjegyzék-verziót.</span><span class="sxs-lookup"><span data-stu-id="57739-128">In the **Reference number** field, select a BOM version.</span></span> <span data-ttu-id="57739-129">Egy anyagjegyzék típusú cikket másol a program a **Cikkszám** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="57739-129">An item of the type BOM is copied to the **Item number**.</span></span>

5.  <span data-ttu-id="57739-130">Adjon nevet a sablonnak a **Név** mezőben.</span><span class="sxs-lookup"><span data-stu-id="57739-130">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="57739-131">Adja meg a **Kezdő dátum** és a **Záró dátum** mezőben azt a dátumintervallumot, amelyben aktív a sablonanyagjegyzék.</span><span class="sxs-lookup"><span data-stu-id="57739-131">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="57739-132">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="57739-132">Click **OK**.</span></span>

<span data-ttu-id="57739-133">Létrejön egy új sablonanyagjegyzék azoknak a soroknak a felhasználásával, amelyek megfelelnek az **Anyagjegyzékek** mezőben szereplő anyagjegyzéknek.</span><span class="sxs-lookup"><span data-stu-id="57739-133">A new template BOM is created by using lines that correspond to the lines of the BOM listed in **Bills of materials**.</span></span>

## <a name="create-a-template-bom-based-on-a-production-bom"></a><span data-ttu-id="57739-134">Sablonanyagjegyzék létrehozása termelési anyagjegyzék alapján</span><span class="sxs-lookup"><span data-stu-id="57739-134">Create a template BOM based on a production BOM</span></span>

1.  <span data-ttu-id="57739-135">Kattintson a **Szolgáltatáskezelés** \> **Beállítás** \> **A szolgáltatás tárgyai** \> **Sablonanyagjegyzékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="57739-135">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="57739-136">Nyomja le a CTRL+N billentyűkombinációt, hogy megnyissa a **Sablonanyagjegyzék létrehozása** képernyőt.</span><span class="sxs-lookup"><span data-stu-id="57739-136">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="57739-137">Az **Anyagjegyzéksorok másolása hivatkozásból** elemnél jelölje be a **Termelés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="57739-137">Under **Copy BOM lines from reference**, select **Production**.</span></span>

4.  <span data-ttu-id="57739-138">A **Hivatkozási szám** mezőben, válasszon ki egy termelési anyagjegyzéket.</span><span class="sxs-lookup"><span data-stu-id="57739-138">In the **Reference number** field, select a production BOM.</span></span>

5.  <span data-ttu-id="57739-139">Adjon nevet a sablonnak a **Név** mezőben.</span><span class="sxs-lookup"><span data-stu-id="57739-139">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="57739-140">Adja meg a **Kezdő dátum** és a **Záró dátum** mezőben azt a dátumintervallumot, amelyben aktív a sablonanyagjegyzék.</span><span class="sxs-lookup"><span data-stu-id="57739-140">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="57739-141">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="57739-141">Click **OK**.</span></span>

<span data-ttu-id="57739-142">Létrejön egy új sablonanyagjegyzék azoknak a soroknak a felhasználásával, amelyek megfelelnek az **AJ** mezőben szereplő anyagjegyzéknek.</span><span class="sxs-lookup"><span data-stu-id="57739-142">A new template BOM is created by using lines that correspond to the lines of the BOM listed in **BOM**.</span></span>

## <a name="see-also"></a><span data-ttu-id="57739-143">Lásd még</span><span class="sxs-lookup"><span data-stu-id="57739-143">See also</span></span>

[<span data-ttu-id="57739-144">Sablonanyagjegyzékek</span><span class="sxs-lookup"><span data-stu-id="57739-144">Template BOMs</span></span>](template-boms.md)

  


