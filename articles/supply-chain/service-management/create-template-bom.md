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
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b2e06283f3b95c5ff6b4376bba63cf5a42d5feeb
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2020
ms.locfileid: "3981817"
---
# <a name="create-a-template-bom"></a><span data-ttu-id="09b8d-103">Sablonanyagjegyzék létrehozása</span><span class="sxs-lookup"><span data-stu-id="09b8d-103">Create a template BOM</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="09b8d-104">Az alábbi módszerek bármelyikével létrehozhat sablonanyagjegyzéket.</span><span class="sxs-lookup"><span data-stu-id="09b8d-104">You can create a template BOM by using any of the following methods.</span></span> <span data-ttu-id="09b8d-105">A **Kezdő dátum** és a **Záró dátum** mezők használata egyik esetben sem kötelező, csak tájékoztatásra szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="09b8d-105">For all methods, the **From date** and **To date** fields are optional and for information only.</span></span>

## <a name="create-a-template-bom-manually"></a><span data-ttu-id="09b8d-106">Sablonanyagjegyzék létrehozása manuálisan</span><span class="sxs-lookup"><span data-stu-id="09b8d-106">Create a template BOM manually</span></span>

1.  <span data-ttu-id="09b8d-107">Kattintson a **Szolgáltatáskezelés** \> **Beállítás** \> **A szolgáltatás tárgyai** \> **Sablonanyagjegyzékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="09b8d-107">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs** .</span></span>

2.  <span data-ttu-id="09b8d-108">Nyomja le a CTRL+N billentyűkombinációt, hogy megnyissa a **Sablonanyagjegyzék létrehozása** képernyőt.</span><span class="sxs-lookup"><span data-stu-id="09b8d-108">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="09b8d-109">Az **Anyagjegyzéksorok másolása hivatkozásból** elemnél jelölje be a **Kézi** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="09b8d-109">Under **Copy BOM lines from reference** , select the **Manual** option.</span></span>

4.  <span data-ttu-id="09b8d-110">A **Cikkszám** mezőben adjon meg egy **Anyagjegyzék** típusú cikket.</span><span class="sxs-lookup"><span data-stu-id="09b8d-110">In the **Item number** field, enter an item of the type **BOM** .</span></span>

5.  <span data-ttu-id="09b8d-111">Adjon nevet a sablonnak a **Név** mezőben.</span><span class="sxs-lookup"><span data-stu-id="09b8d-111">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="09b8d-112">Adja meg a **Kezdő dátum** és a **Záró dátum** mezőben azt a dátumintervallumot, amelyben aktív a sablonanyagjegyzék.</span><span class="sxs-lookup"><span data-stu-id="09b8d-112">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="09b8d-113">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="09b8d-113">Click **OK** .</span></span>

<span data-ttu-id="09b8d-114">Létrejön egy új, üres sablonanyagjegyzék.</span><span class="sxs-lookup"><span data-stu-id="09b8d-114">A new, blank template BOM is created.</span></span>

## <a name="create-a-template-bom-based-on-another-template-bom"></a><span data-ttu-id="09b8d-115">Sablonanyagjegyzék létrehozása másik sablonanyagjegyzék alapján</span><span class="sxs-lookup"><span data-stu-id="09b8d-115">Create a template BOM based on another template BOM</span></span>

1.  <span data-ttu-id="09b8d-116">Kattintson a **Szolgáltatáskezelés** \> **Beállítás** \> **A szolgáltatás tárgyai** \> **Sablonanyagjegyzékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="09b8d-116">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs** .</span></span>

2.  <span data-ttu-id="09b8d-117">Nyomja le a CTRL+N billentyűkombinációt, hogy megnyissa a **Sablonanyagjegyzék létrehozása** képernyőt.</span><span class="sxs-lookup"><span data-stu-id="09b8d-117">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="09b8d-118">Az **Anyagjegyzéksorok másolása hivatkozásból** elemnél jelölje be az **Anyagjegyzék-sablon** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="09b8d-118">Under **Copy BOM lines from reference** , select the **Template BOM** option.</span></span>

4.  <span data-ttu-id="09b8d-119">A **Hivatkozási szám** mezőben válasszon egy létező sablonanyagjegyzéket, amelyet átmásol az új sablonanyagjegyzékbe.</span><span class="sxs-lookup"><span data-stu-id="09b8d-119">In the **Reference number** field, select an existing template BOM to copy to your new template BOM.</span></span>

5.  <span data-ttu-id="09b8d-120">Adjon nevet a sablonnak a **Név** mezőben.</span><span class="sxs-lookup"><span data-stu-id="09b8d-120">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="09b8d-121">Adja meg a **Kezdő dátum** és a **Záró dátum** mezőben azt a dátumintervallumot, amelyben aktív a sablonanyagjegyzék.</span><span class="sxs-lookup"><span data-stu-id="09b8d-121">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="09b8d-122">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="09b8d-122">Click **OK** .</span></span>

<span data-ttu-id="09b8d-123">Egy új sablonanyagjegyzék jön létre az eredeti sablonanyagjegyzék soraival megegyező sorokkal.</span><span class="sxs-lookup"><span data-stu-id="09b8d-123">A new template BOM is created by using lines that correspond to the lines in the original template BOM.</span></span>

## <a name="create-a-template-bom-based-on-an-item-bom"></a><span data-ttu-id="09b8d-124">Sablonanyagjegyzék létrehozása cikkanyagjegyzék alapján</span><span class="sxs-lookup"><span data-stu-id="09b8d-124">Create a template BOM based on an item BOM</span></span>

1.  <span data-ttu-id="09b8d-125">Kattintson a **Szolgáltatáskezelés** \> **Beállítás** \> **A szolgáltatás tárgyai** \> **Sablonanyagjegyzékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="09b8d-125">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs** .</span></span>

2.  <span data-ttu-id="09b8d-126">Nyomja le a CTRL+N billentyűkombinációt, hogy megnyissa a **Sablonanyagjegyzék létrehozása** képernyőt.</span><span class="sxs-lookup"><span data-stu-id="09b8d-126">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="09b8d-127">Az **Anyagjegyzéksorok másolása hivatkozásból** elemnél jelölje be az **Anyagjegyzék** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="09b8d-127">Under **Copy BOM lines from reference** , select **BOM** .</span></span>

4.  <span data-ttu-id="09b8d-128">A **Hivatkozási szám** mezőben, válasszon ki egy anyagjegyzék-verziót.</span><span class="sxs-lookup"><span data-stu-id="09b8d-128">In the **Reference number** field, select a BOM version.</span></span> <span data-ttu-id="09b8d-129">Egy anyagjegyzék típusú cikket másol a program a **Cikkszám** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="09b8d-129">An item of the type BOM is copied to the **Item number** .</span></span>

5.  <span data-ttu-id="09b8d-130">Adjon nevet a sablonnak a **Név** mezőben.</span><span class="sxs-lookup"><span data-stu-id="09b8d-130">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="09b8d-131">Adja meg a **Kezdő dátum** és a **Záró dátum** mezőben azt a dátumintervallumot, amelyben aktív a sablonanyagjegyzék.</span><span class="sxs-lookup"><span data-stu-id="09b8d-131">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="09b8d-132">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="09b8d-132">Click **OK** .</span></span>

<span data-ttu-id="09b8d-133">Létrejön egy új sablonanyagjegyzék azoknak a soroknak a felhasználásával, amelyek megfelelnek az **Anyagjegyzékek** mezőben szereplő anyagjegyzéknek.</span><span class="sxs-lookup"><span data-stu-id="09b8d-133">A new template BOM is created by using lines that correspond to the lines of the BOM listed in **Bills of materials** .</span></span>

## <a name="create-a-template-bom-based-on-a-production-bom"></a><span data-ttu-id="09b8d-134">Sablonanyagjegyzék létrehozása termelési anyagjegyzék alapján</span><span class="sxs-lookup"><span data-stu-id="09b8d-134">Create a template BOM based on a production BOM</span></span>

1.  <span data-ttu-id="09b8d-135">Kattintson a **Szolgáltatáskezelés** \> **Beállítás** \> **A szolgáltatás tárgyai** \> **Sablonanyagjegyzékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="09b8d-135">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs** .</span></span>

2.  <span data-ttu-id="09b8d-136">Nyomja le a CTRL+N billentyűkombinációt, hogy megnyissa a **Sablonanyagjegyzék létrehozása** képernyőt.</span><span class="sxs-lookup"><span data-stu-id="09b8d-136">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="09b8d-137">Az **Anyagjegyzéksorok másolása hivatkozásból** elemnél jelölje be a **Termelés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="09b8d-137">Under **Copy BOM lines from reference** , select **Production** .</span></span>

4.  <span data-ttu-id="09b8d-138">A **Hivatkozási szám** mezőben, válasszon ki egy termelési anyagjegyzéket.</span><span class="sxs-lookup"><span data-stu-id="09b8d-138">In the **Reference number** field, select a production BOM.</span></span>

5.  <span data-ttu-id="09b8d-139">Adjon nevet a sablonnak a **Név** mezőben.</span><span class="sxs-lookup"><span data-stu-id="09b8d-139">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="09b8d-140">Adja meg a **Kezdő dátum** és a **Záró dátum** mezőben azt a dátumintervallumot, amelyben aktív a sablonanyagjegyzék.</span><span class="sxs-lookup"><span data-stu-id="09b8d-140">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="09b8d-141">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="09b8d-141">Click **OK** .</span></span>

<span data-ttu-id="09b8d-142">Létrejön egy új sablonanyagjegyzék azoknak a soroknak a felhasználásával, amelyek megfelelnek az **AJ** mezőben szereplő anyagjegyzéknek.</span><span class="sxs-lookup"><span data-stu-id="09b8d-142">A new template BOM is created by using lines that correspond to the lines of the BOM listed in **BOM** .</span></span>

## <a name="see-also"></a><span data-ttu-id="09b8d-143">Lásd még</span><span class="sxs-lookup"><span data-stu-id="09b8d-143">See also</span></span>

[<span data-ttu-id="09b8d-144">Sablonanyagjegyzékek</span><span class="sxs-lookup"><span data-stu-id="09b8d-144">Template BOMs</span></span>](template-boms.md)

  


