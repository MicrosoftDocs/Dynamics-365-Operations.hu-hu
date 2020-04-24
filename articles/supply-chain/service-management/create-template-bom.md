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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 815b6b726e9a76a9294995bc5689b030cf623ec0
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3202583"
---
# <a name="create-a-template-bom"></a><span data-ttu-id="e4a55-103">Sablonanyagjegyzék létrehozása</span><span class="sxs-lookup"><span data-stu-id="e4a55-103">Create a template BOM</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="e4a55-104">Az alábbi módszerek bármelyikével létrehozhat sablonanyagjegyzéket.</span><span class="sxs-lookup"><span data-stu-id="e4a55-104">You can create a template BOM by using any of the following methods.</span></span> <span data-ttu-id="e4a55-105">A **Kezdő dátum** és a **Záró dátum** mezők használata egyik esetben sem kötelező, csak tájékoztatásra szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="e4a55-105">For all methods, the **From date** and **To date** fields are optional and for information only.</span></span>

## <a name="create-a-template-bom-manually"></a><span data-ttu-id="e4a55-106">Sablonanyagjegyzék létrehozása manuálisan</span><span class="sxs-lookup"><span data-stu-id="e4a55-106">Create a template BOM manually</span></span>

1.  <span data-ttu-id="e4a55-107">Kattintson a **Szolgáltatáskezelés** \> **Beállítás** \> **A szolgáltatás tárgyai** \> **Sablonanyagjegyzékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e4a55-107">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="e4a55-108">Nyomja le a CTRL+N billentyűkombinációt, hogy megnyissa a **Sablonanyagjegyzék létrehozása** képernyőt.</span><span class="sxs-lookup"><span data-stu-id="e4a55-108">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="e4a55-109">Az **Anyagjegyzéksorok másolása hivatkozásból** elemnél jelölje be a **Kézi** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e4a55-109">Under **Copy BOM lines from reference**, select the **Manual** option.</span></span>

4.  <span data-ttu-id="e4a55-110">A **Cikkszám** mezőben adjon meg egy **Anyagjegyzék** típusú cikket.</span><span class="sxs-lookup"><span data-stu-id="e4a55-110">In the **Item number** field, enter an item of the type **BOM**.</span></span>

5.  <span data-ttu-id="e4a55-111">Adjon nevet a sablonnak a **Név** mezőben.</span><span class="sxs-lookup"><span data-stu-id="e4a55-111">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="e4a55-112">Adja meg a **Kezdő dátum** és a **Záró dátum** mezőben azt a dátumintervallumot, amelyben aktív a sablonanyagjegyzék.</span><span class="sxs-lookup"><span data-stu-id="e4a55-112">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="e4a55-113">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="e4a55-113">Click **OK**.</span></span>

<span data-ttu-id="e4a55-114">Létrejön egy új, üres sablonanyagjegyzék.</span><span class="sxs-lookup"><span data-stu-id="e4a55-114">A new, blank template BOM is created.</span></span>

## <a name="create-a-template-bom-based-on-another-template-bom"></a><span data-ttu-id="e4a55-115">Sablonanyagjegyzék létrehozása másik sablonanyagjegyzék alapján</span><span class="sxs-lookup"><span data-stu-id="e4a55-115">Create a template BOM based on another template BOM</span></span>

1.  <span data-ttu-id="e4a55-116">Kattintson a **Szolgáltatáskezelés** \> **Beállítás** \> **A szolgáltatás tárgyai** \> **Sablonanyagjegyzékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e4a55-116">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="e4a55-117">Nyomja le a CTRL+N billentyűkombinációt, hogy megnyissa a **Sablonanyagjegyzék létrehozása** képernyőt.</span><span class="sxs-lookup"><span data-stu-id="e4a55-117">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="e4a55-118">Az **Anyagjegyzéksorok másolása hivatkozásból** elemnél jelölje be az **Anyagjegyzék-sablon** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e4a55-118">Under **Copy BOM lines from reference**, select the **Template BOM** option.</span></span>

4.  <span data-ttu-id="e4a55-119">A **Hivatkozási szám** mezőben válasszon egy létező sablonanyagjegyzéket, amelyet átmásol az új sablonanyagjegyzékbe.</span><span class="sxs-lookup"><span data-stu-id="e4a55-119">In the **Reference number** field, select an existing template BOM to copy to your new template BOM.</span></span>

5.  <span data-ttu-id="e4a55-120">Adjon nevet a sablonnak a **Név** mezőben.</span><span class="sxs-lookup"><span data-stu-id="e4a55-120">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="e4a55-121">Adja meg a **Kezdő dátum** és a **Záró dátum** mezőben azt a dátumintervallumot, amelyben aktív a sablonanyagjegyzék.</span><span class="sxs-lookup"><span data-stu-id="e4a55-121">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="e4a55-122">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="e4a55-122">Click **OK**.</span></span>

<span data-ttu-id="e4a55-123">Egy új sablonanyagjegyzék jön létre az eredeti sablonanyagjegyzék soraival megegyező sorokkal.</span><span class="sxs-lookup"><span data-stu-id="e4a55-123">A new template BOM is created by using lines that correspond to the lines in the original template BOM.</span></span>

## <a name="create-a-template-bom-based-on-an-item-bom"></a><span data-ttu-id="e4a55-124">Sablonanyagjegyzék létrehozása cikkanyagjegyzék alapján</span><span class="sxs-lookup"><span data-stu-id="e4a55-124">Create a template BOM based on an item BOM</span></span>

1.  <span data-ttu-id="e4a55-125">Kattintson a **Szolgáltatáskezelés** \> **Beállítás** \> **A szolgáltatás tárgyai** \> **Sablonanyagjegyzékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e4a55-125">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="e4a55-126">Nyomja le a CTRL+N billentyűkombinációt, hogy megnyissa a **Sablonanyagjegyzék létrehozása** képernyőt.</span><span class="sxs-lookup"><span data-stu-id="e4a55-126">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="e4a55-127">Az **Anyagjegyzéksorok másolása hivatkozásból** elemnél jelölje be az **Anyagjegyzék** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e4a55-127">Under **Copy BOM lines from reference**, select **BOM**.</span></span>

4.  <span data-ttu-id="e4a55-128">A **Hivatkozási szám** mezőben, válasszon ki egy anyagjegyzék-verziót.</span><span class="sxs-lookup"><span data-stu-id="e4a55-128">In the **Reference number** field, select a BOM version.</span></span> <span data-ttu-id="e4a55-129">Egy anyagjegyzék típusú cikket másol a program a **Cikkszám** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="e4a55-129">An item of the type BOM is copied to the **Item number**.</span></span>

5.  <span data-ttu-id="e4a55-130">Adjon nevet a sablonnak a **Név** mezőben.</span><span class="sxs-lookup"><span data-stu-id="e4a55-130">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="e4a55-131">Adja meg a **Kezdő dátum** és a **Záró dátum** mezőben azt a dátumintervallumot, amelyben aktív a sablonanyagjegyzék.</span><span class="sxs-lookup"><span data-stu-id="e4a55-131">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="e4a55-132">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="e4a55-132">Click **OK**.</span></span>

<span data-ttu-id="e4a55-133">Létrejön egy új sablonanyagjegyzék azoknak a soroknak a felhasználásával, amelyek megfelelnek az **Anyagjegyzékek** mezőben szereplő anyagjegyzéknek.</span><span class="sxs-lookup"><span data-stu-id="e4a55-133">A new template BOM is created by using lines that correspond to the lines of the BOM listed in **Bills of materials**.</span></span>

## <a name="create-a-template-bom-based-on-a-production-bom"></a><span data-ttu-id="e4a55-134">Sablonanyagjegyzék létrehozása termelési anyagjegyzék alapján</span><span class="sxs-lookup"><span data-stu-id="e4a55-134">Create a template BOM based on a production BOM</span></span>

1.  <span data-ttu-id="e4a55-135">Kattintson a **Szolgáltatáskezelés** \> **Beállítás** \> **A szolgáltatás tárgyai** \> **Sablonanyagjegyzékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e4a55-135">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="e4a55-136">Nyomja le a CTRL+N billentyűkombinációt, hogy megnyissa a **Sablonanyagjegyzék létrehozása** képernyőt.</span><span class="sxs-lookup"><span data-stu-id="e4a55-136">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="e4a55-137">Az **Anyagjegyzéksorok másolása hivatkozásból** elemnél jelölje be a **Termelés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e4a55-137">Under **Copy BOM lines from reference**, select **Production**.</span></span>

4.  <span data-ttu-id="e4a55-138">A **Hivatkozási szám** mezőben, válasszon ki egy termelési anyagjegyzéket.</span><span class="sxs-lookup"><span data-stu-id="e4a55-138">In the **Reference number** field, select a production BOM.</span></span>

5.  <span data-ttu-id="e4a55-139">Adjon nevet a sablonnak a **Név** mezőben.</span><span class="sxs-lookup"><span data-stu-id="e4a55-139">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="e4a55-140">Adja meg a **Kezdő dátum** és a **Záró dátum** mezőben azt a dátumintervallumot, amelyben aktív a sablonanyagjegyzék.</span><span class="sxs-lookup"><span data-stu-id="e4a55-140">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="e4a55-141">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="e4a55-141">Click **OK**.</span></span>

<span data-ttu-id="e4a55-142">Létrejön egy új sablonanyagjegyzék azoknak a soroknak a felhasználásával, amelyek megfelelnek az **AJ** mezőben szereplő anyagjegyzéknek.</span><span class="sxs-lookup"><span data-stu-id="e4a55-142">A new template BOM is created by using lines that correspond to the lines of the BOM listed in **BOM**.</span></span>

## <a name="see-also"></a><span data-ttu-id="e4a55-143">Lásd még</span><span class="sxs-lookup"><span data-stu-id="e4a55-143">See also</span></span>

[<span data-ttu-id="e4a55-144">Sablonanyagjegyzékek</span><span class="sxs-lookup"><span data-stu-id="e4a55-144">Template BOMs</span></span>](template-boms.md)

  


