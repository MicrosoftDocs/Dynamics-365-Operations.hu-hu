---
title: Sablonanyagjegyzék létrehozása
description: Különböző módszerek segítségével hozhat létre sablonanyagjegyzéket.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMATemplateBOMTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5afcb8171b674281faf8100d5c01fdff8d6ff764
ms.sourcegitcommit: 34b8f6f5c6134b7b97a9fb41d0b2e63215c67062
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/17/2021
ms.locfileid: "5470785"
---
# <a name="create-a-template-bom"></a><span data-ttu-id="f57bf-103">Sablonanyagjegyzék létrehozása</span><span class="sxs-lookup"><span data-stu-id="f57bf-103">Create a template BOM</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="f57bf-104">Az alábbi módszerek bármelyikével létrehozhat sablonanyagjegyzéket.</span><span class="sxs-lookup"><span data-stu-id="f57bf-104">You can create a template BOM by using any of the following methods.</span></span> <span data-ttu-id="f57bf-105">A **Kezdő dátum** és a **Záró dátum** mezők használata egyik esetben sem kötelező, csak tájékoztatásra szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="f57bf-105">For all methods, the **From date** and **To date** fields are optional and for information only.</span></span>

## <a name="create-a-template-bom-manually"></a><span data-ttu-id="f57bf-106">Sablonanyagjegyzék létrehozása manuálisan</span><span class="sxs-lookup"><span data-stu-id="f57bf-106">Create a template BOM manually</span></span>

1.  <span data-ttu-id="f57bf-107">Lépjen a **Szolgáltatáskezelés** \> **Beállítás** \> **A szolgáltatás tárgyai** \> **Sablonanyagjegyzékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f57bf-107">Go to **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="f57bf-108">Válassza az **Új** elemet, hogy megnyissa a **Sablonanyagjegyzék létrehozása** képernyőt.</span><span class="sxs-lookup"><span data-stu-id="f57bf-108">Select **New** to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="f57bf-109">Az **Anyagjegyzéksorok másolása hivatkozásból** elemnél jelölje be a **Kézi** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f57bf-109">Under **Copy BOM lines from reference**, select the **Manual** option.</span></span>

4.  <span data-ttu-id="f57bf-110">A **Cikkszám** mezőben adjon meg egy **Anyagjegyzék** típusú cikket.</span><span class="sxs-lookup"><span data-stu-id="f57bf-110">In the **Item number** field, enter an item of the type **BOM**.</span></span>

5.  <span data-ttu-id="f57bf-111">Adjon nevet a sablonnak a **Név** mezőben.</span><span class="sxs-lookup"><span data-stu-id="f57bf-111">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="f57bf-112">Adja meg a **Kezdő dátum** és a **Záró dátum** mezőben azt a dátumintervallumot, amelyben aktív a sablonanyagjegyzék.</span><span class="sxs-lookup"><span data-stu-id="f57bf-112">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="f57bf-113">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f57bf-113">Select **OK**.</span></span>

<span data-ttu-id="f57bf-114">Létrejön egy új, üres sablonanyagjegyzék.</span><span class="sxs-lookup"><span data-stu-id="f57bf-114">A new, blank template BOM is created.</span></span>

## <a name="create-a-template-bom-based-on-another-template-bom"></a><span data-ttu-id="f57bf-115">Sablonanyagjegyzék létrehozása másik sablonanyagjegyzék alapján</span><span class="sxs-lookup"><span data-stu-id="f57bf-115">Create a template BOM based on another template BOM</span></span>

1.  <span data-ttu-id="f57bf-116">Válassza a **Szolgáltatáskezelés** \> **Beállítás** \> **A szolgáltatás tárgyai** \> **Sablonanyagjegyzékek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f57bf-116">Select **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="f57bf-117">Válassza az **Új** elemet, hogy megnyissa a **Sablonanyagjegyzék létrehozása** képernyőt.</span><span class="sxs-lookup"><span data-stu-id="f57bf-117">Select **New** to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="f57bf-118">Az **Anyagjegyzéksorok másolása hivatkozásból** elemnél jelölje be az **Anyagjegyzék-sablon** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f57bf-118">Under **Copy BOM lines from reference**, select the **Template BOM** option.</span></span>

4.  <span data-ttu-id="f57bf-119">A **Hivatkozási szám** mezőben válasszon egy létező sablonanyagjegyzéket, amelyet átmásol az új sablonanyagjegyzékbe.</span><span class="sxs-lookup"><span data-stu-id="f57bf-119">In the **Reference number** field, select an existing template BOM to copy to your new template BOM.</span></span>

5.  <span data-ttu-id="f57bf-120">Adjon nevet a sablonnak a **Név** mezőben.</span><span class="sxs-lookup"><span data-stu-id="f57bf-120">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="f57bf-121">Adja meg a **Kezdő dátum** és a **Záró dátum** mezőben azt a dátumintervallumot, amelyben aktív a sablonanyagjegyzék.</span><span class="sxs-lookup"><span data-stu-id="f57bf-121">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="f57bf-122">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f57bf-122">Select **OK**.</span></span>

<span data-ttu-id="f57bf-123">Egy új sablonanyagjegyzék jön létre az eredeti sablonanyagjegyzék soraival megegyező sorokkal.</span><span class="sxs-lookup"><span data-stu-id="f57bf-123">A new template BOM is created by using lines that correspond to the lines in the original template BOM.</span></span>

## <a name="create-a-template-bom-based-on-an-item-bom"></a><span data-ttu-id="f57bf-124">Sablonanyagjegyzék létrehozása cikkanyagjegyzék alapján</span><span class="sxs-lookup"><span data-stu-id="f57bf-124">Create a template BOM based on an item BOM</span></span>

1.  <span data-ttu-id="f57bf-125">Válassza a **Szolgáltatáskezelés** \> **Beállítás** \> **A szolgáltatás tárgyai** \> **Sablonanyagjegyzékek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f57bf-125">Select **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="f57bf-126">Válassza az **Új** elemet, hogy megnyissa a **Sablonanyagjegyzék létrehozása** képernyőt.</span><span class="sxs-lookup"><span data-stu-id="f57bf-126">Select **New** to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="f57bf-127">Az **Anyagjegyzéksorok másolása hivatkozásból** elemnél jelölje be az **Anyagjegyzék** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f57bf-127">Under **Copy BOM lines from reference**, select **BOM**.</span></span>

4.  <span data-ttu-id="f57bf-128">A **Hivatkozási szám** mezőben, válasszon ki egy anyagjegyzék-verziót.</span><span class="sxs-lookup"><span data-stu-id="f57bf-128">In the **Reference number** field, select a BOM version.</span></span> <span data-ttu-id="f57bf-129">Egy anyagjegyzék típusú cikket másol a program a **Cikkszám** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="f57bf-129">An item of the type BOM is copied to the **Item number**.</span></span>

5.  <span data-ttu-id="f57bf-130">Adjon nevet a sablonnak a **Név** mezőben.</span><span class="sxs-lookup"><span data-stu-id="f57bf-130">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="f57bf-131">Adja meg a **Kezdő dátum** és a **Záró dátum** mezőben azt a dátumintervallumot, amelyben aktív a sablonanyagjegyzék.</span><span class="sxs-lookup"><span data-stu-id="f57bf-131">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="f57bf-132">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f57bf-132">Select **OK**.</span></span>

<span data-ttu-id="f57bf-133">Létrejön egy új sablonanyagjegyzék azoknak a soroknak a felhasználásával, amelyek megfelelnek az **Anyagjegyzékek** mezőben szereplő anyagjegyzéknek.</span><span class="sxs-lookup"><span data-stu-id="f57bf-133">A new template BOM is created by using lines that correspond to the lines of the BOM listed in **Bills of materials**.</span></span>

## <a name="create-a-template-bom-based-on-a-production-bom"></a><span data-ttu-id="f57bf-134">Sablonanyagjegyzék létrehozása termelési anyagjegyzék alapján</span><span class="sxs-lookup"><span data-stu-id="f57bf-134">Create a template BOM based on a production BOM</span></span>

1.  <span data-ttu-id="f57bf-135">Válassza a **Szolgáltatáskezelés** \> **Beállítás** \> **A szolgáltatás tárgyai** \> **Sablonanyagjegyzékek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f57bf-135">Select **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="f57bf-136">Válassza az **Új** elemet, hogy megnyissa a **Sablonanyagjegyzék létrehozása** képernyőt.</span><span class="sxs-lookup"><span data-stu-id="f57bf-136">Select **New** to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="f57bf-137">Az **Anyagjegyzéksorok másolása hivatkozásból** elemnél jelölje be a **Termelés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f57bf-137">Under **Copy BOM lines from reference**, select **Production**.</span></span>

4.  <span data-ttu-id="f57bf-138">A **Hivatkozási szám** mezőben, válasszon ki egy termelési anyagjegyzéket.</span><span class="sxs-lookup"><span data-stu-id="f57bf-138">In the **Reference number** field, select a production BOM.</span></span>

5.  <span data-ttu-id="f57bf-139">Adjon nevet a sablonnak a **Név** mezőben.</span><span class="sxs-lookup"><span data-stu-id="f57bf-139">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="f57bf-140">Adja meg a **Kezdő dátum** és a **Záró dátum** mezőben azt a dátumintervallumot, amelyben aktív a sablonanyagjegyzék.</span><span class="sxs-lookup"><span data-stu-id="f57bf-140">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="f57bf-141">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f57bf-141">Select **OK**.</span></span>

<span data-ttu-id="f57bf-142">Létrejön egy új sablonanyagjegyzék azoknak a soroknak a felhasználásával, amelyek megfelelnek az **AJ** mezőben szereplő anyagjegyzéknek.</span><span class="sxs-lookup"><span data-stu-id="f57bf-142">A new template BOM is created by using lines that correspond to the lines of the BOM listed in **BOM**.</span></span>

## <a name="see-also"></a><span data-ttu-id="f57bf-143">Lásd még</span><span class="sxs-lookup"><span data-stu-id="f57bf-143">See also</span></span>

[<span data-ttu-id="f57bf-144">Sablonanyagjegyzékek</span><span class="sxs-lookup"><span data-stu-id="f57bf-144">Template BOMs</span></span>](template-boms.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]