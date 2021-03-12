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
ms.openlocfilehash: 8b34cc2e9921df6e3ef619e2b2adaf8d2069fbac
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4974560"
---
# <a name="create-a-template-bom"></a><span data-ttu-id="f8a94-103">Sablonanyagjegyzék létrehozása</span><span class="sxs-lookup"><span data-stu-id="f8a94-103">Create a template BOM</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="f8a94-104">Az alábbi módszerek bármelyikével létrehozhat sablonanyagjegyzéket.</span><span class="sxs-lookup"><span data-stu-id="f8a94-104">You can create a template BOM by using any of the following methods.</span></span> <span data-ttu-id="f8a94-105">A **Kezdő dátum** és a **Záró dátum** mezők használata egyik esetben sem kötelező, csak tájékoztatásra szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="f8a94-105">For all methods, the **From date** and **To date** fields are optional and for information only.</span></span>

## <a name="create-a-template-bom-manually"></a><span data-ttu-id="f8a94-106">Sablonanyagjegyzék létrehozása manuálisan</span><span class="sxs-lookup"><span data-stu-id="f8a94-106">Create a template BOM manually</span></span>

1.  <span data-ttu-id="f8a94-107">Kattintson a **Szolgáltatáskezelés** \> **Beállítás** \> **A szolgáltatás tárgyai** \> **Sablonanyagjegyzékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f8a94-107">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="f8a94-108">Nyomja le a CTRL+N billentyűkombinációt, hogy megnyissa a **Sablonanyagjegyzék létrehozása** képernyőt.</span><span class="sxs-lookup"><span data-stu-id="f8a94-108">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="f8a94-109">Az **Anyagjegyzéksorok másolása hivatkozásból** elemnél jelölje be a **Kézi** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f8a94-109">Under **Copy BOM lines from reference**, select the **Manual** option.</span></span>

4.  <span data-ttu-id="f8a94-110">A **Cikkszám** mezőben adjon meg egy **Anyagjegyzék** típusú cikket.</span><span class="sxs-lookup"><span data-stu-id="f8a94-110">In the **Item number** field, enter an item of the type **BOM**.</span></span>

5.  <span data-ttu-id="f8a94-111">Adjon nevet a sablonnak a **Név** mezőben.</span><span class="sxs-lookup"><span data-stu-id="f8a94-111">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="f8a94-112">Adja meg a **Kezdő dátum** és a **Záró dátum** mezőben azt a dátumintervallumot, amelyben aktív a sablonanyagjegyzék.</span><span class="sxs-lookup"><span data-stu-id="f8a94-112">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="f8a94-113">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="f8a94-113">Click **OK**.</span></span>

<span data-ttu-id="f8a94-114">Létrejön egy új, üres sablonanyagjegyzék.</span><span class="sxs-lookup"><span data-stu-id="f8a94-114">A new, blank template BOM is created.</span></span>

## <a name="create-a-template-bom-based-on-another-template-bom"></a><span data-ttu-id="f8a94-115">Sablonanyagjegyzék létrehozása másik sablonanyagjegyzék alapján</span><span class="sxs-lookup"><span data-stu-id="f8a94-115">Create a template BOM based on another template BOM</span></span>

1.  <span data-ttu-id="f8a94-116">Kattintson a **Szolgáltatáskezelés** \> **Beállítás** \> **A szolgáltatás tárgyai** \> **Sablonanyagjegyzékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f8a94-116">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="f8a94-117">Nyomja le a CTRL+N billentyűkombinációt, hogy megnyissa a **Sablonanyagjegyzék létrehozása** képernyőt.</span><span class="sxs-lookup"><span data-stu-id="f8a94-117">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="f8a94-118">Az **Anyagjegyzéksorok másolása hivatkozásból** elemnél jelölje be az **Anyagjegyzék-sablon** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f8a94-118">Under **Copy BOM lines from reference**, select the **Template BOM** option.</span></span>

4.  <span data-ttu-id="f8a94-119">A **Hivatkozási szám** mezőben válasszon egy létező sablonanyagjegyzéket, amelyet átmásol az új sablonanyagjegyzékbe.</span><span class="sxs-lookup"><span data-stu-id="f8a94-119">In the **Reference number** field, select an existing template BOM to copy to your new template BOM.</span></span>

5.  <span data-ttu-id="f8a94-120">Adjon nevet a sablonnak a **Név** mezőben.</span><span class="sxs-lookup"><span data-stu-id="f8a94-120">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="f8a94-121">Adja meg a **Kezdő dátum** és a **Záró dátum** mezőben azt a dátumintervallumot, amelyben aktív a sablonanyagjegyzék.</span><span class="sxs-lookup"><span data-stu-id="f8a94-121">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="f8a94-122">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="f8a94-122">Click **OK**.</span></span>

<span data-ttu-id="f8a94-123">Egy új sablonanyagjegyzék jön létre az eredeti sablonanyagjegyzék soraival megegyező sorokkal.</span><span class="sxs-lookup"><span data-stu-id="f8a94-123">A new template BOM is created by using lines that correspond to the lines in the original template BOM.</span></span>

## <a name="create-a-template-bom-based-on-an-item-bom"></a><span data-ttu-id="f8a94-124">Sablonanyagjegyzék létrehozása cikkanyagjegyzék alapján</span><span class="sxs-lookup"><span data-stu-id="f8a94-124">Create a template BOM based on an item BOM</span></span>

1.  <span data-ttu-id="f8a94-125">Kattintson a **Szolgáltatáskezelés** \> **Beállítás** \> **A szolgáltatás tárgyai** \> **Sablonanyagjegyzékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f8a94-125">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="f8a94-126">Nyomja le a CTRL+N billentyűkombinációt, hogy megnyissa a **Sablonanyagjegyzék létrehozása** képernyőt.</span><span class="sxs-lookup"><span data-stu-id="f8a94-126">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="f8a94-127">Az **Anyagjegyzéksorok másolása hivatkozásból** elemnél jelölje be az **Anyagjegyzék** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f8a94-127">Under **Copy BOM lines from reference**, select **BOM**.</span></span>

4.  <span data-ttu-id="f8a94-128">A **Hivatkozási szám** mezőben, válasszon ki egy anyagjegyzék-verziót.</span><span class="sxs-lookup"><span data-stu-id="f8a94-128">In the **Reference number** field, select a BOM version.</span></span> <span data-ttu-id="f8a94-129">Egy anyagjegyzék típusú cikket másol a program a **Cikkszám** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="f8a94-129">An item of the type BOM is copied to the **Item number**.</span></span>

5.  <span data-ttu-id="f8a94-130">Adjon nevet a sablonnak a **Név** mezőben.</span><span class="sxs-lookup"><span data-stu-id="f8a94-130">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="f8a94-131">Adja meg a **Kezdő dátum** és a **Záró dátum** mezőben azt a dátumintervallumot, amelyben aktív a sablonanyagjegyzék.</span><span class="sxs-lookup"><span data-stu-id="f8a94-131">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="f8a94-132">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="f8a94-132">Click **OK**.</span></span>

<span data-ttu-id="f8a94-133">Létrejön egy új sablonanyagjegyzék azoknak a soroknak a felhasználásával, amelyek megfelelnek az **Anyagjegyzékek** mezőben szereplő anyagjegyzéknek.</span><span class="sxs-lookup"><span data-stu-id="f8a94-133">A new template BOM is created by using lines that correspond to the lines of the BOM listed in **Bills of materials**.</span></span>

## <a name="create-a-template-bom-based-on-a-production-bom"></a><span data-ttu-id="f8a94-134">Sablonanyagjegyzék létrehozása termelési anyagjegyzék alapján</span><span class="sxs-lookup"><span data-stu-id="f8a94-134">Create a template BOM based on a production BOM</span></span>

1.  <span data-ttu-id="f8a94-135">Kattintson a **Szolgáltatáskezelés** \> **Beállítás** \> **A szolgáltatás tárgyai** \> **Sablonanyagjegyzékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f8a94-135">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="f8a94-136">Nyomja le a CTRL+N billentyűkombinációt, hogy megnyissa a **Sablonanyagjegyzék létrehozása** képernyőt.</span><span class="sxs-lookup"><span data-stu-id="f8a94-136">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="f8a94-137">Az **Anyagjegyzéksorok másolása hivatkozásból** elemnél jelölje be a **Termelés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f8a94-137">Under **Copy BOM lines from reference**, select **Production**.</span></span>

4.  <span data-ttu-id="f8a94-138">A **Hivatkozási szám** mezőben, válasszon ki egy termelési anyagjegyzéket.</span><span class="sxs-lookup"><span data-stu-id="f8a94-138">In the **Reference number** field, select a production BOM.</span></span>

5.  <span data-ttu-id="f8a94-139">Adjon nevet a sablonnak a **Név** mezőben.</span><span class="sxs-lookup"><span data-stu-id="f8a94-139">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="f8a94-140">Adja meg a **Kezdő dátum** és a **Záró dátum** mezőben azt a dátumintervallumot, amelyben aktív a sablonanyagjegyzék.</span><span class="sxs-lookup"><span data-stu-id="f8a94-140">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="f8a94-141">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="f8a94-141">Click **OK**.</span></span>

<span data-ttu-id="f8a94-142">Létrejön egy új sablonanyagjegyzék azoknak a soroknak a felhasználásával, amelyek megfelelnek az **AJ** mezőben szereplő anyagjegyzéknek.</span><span class="sxs-lookup"><span data-stu-id="f8a94-142">A new template BOM is created by using lines that correspond to the lines of the BOM listed in **BOM**.</span></span>

## <a name="see-also"></a><span data-ttu-id="f8a94-143">Lásd még</span><span class="sxs-lookup"><span data-stu-id="f8a94-143">See also</span></span>

[<span data-ttu-id="f8a94-144">Sablonanyagjegyzékek</span><span class="sxs-lookup"><span data-stu-id="f8a94-144">Template BOMs</span></span>](template-boms.md)

  


