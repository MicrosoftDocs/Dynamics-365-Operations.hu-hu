---
title: Szolgáltatási anyagjegyzék módosítása
description: Szolgáltatási anyagjegyzék módosítása.
author: ShylaThompson
manager: tfehr
ms.date: 05/03/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 11017cf239c55bde5f90a0d48783740a1b3e0591
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3202261"
---
# <a name="modify-a-service-bom"></a><span data-ttu-id="cf281-103">Szolgáltatási anyagjegyzék módosítása</span><span class="sxs-lookup"><span data-stu-id="cf281-103">Modify a Service BOM</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="cf281-104">A szolgáltatási anyagjegyzékben rögzítheti egy elem előzményeit.</span><span class="sxs-lookup"><span data-stu-id="cf281-104">You can record the history of an element in a service BOM.</span></span> <span data-ttu-id="cf281-105">Minden alkalommal, amikor frissít egy anyagjegyzéksort, egy előzménysor jön létre az **Előzmények** ablakban.</span><span class="sxs-lookup"><span data-stu-id="cf281-105">Every time that you update a BOM line, a history line is created in the **History** pane.</span></span> <span data-ttu-id="cf281-106">Az előzménysor az anyagjegyzéksor aktuális állapotát mutatja.</span><span class="sxs-lookup"><span data-stu-id="cf281-106">The history line shows the current state of the BOM line.</span></span>

## <a name="update-a-service-bom-element"></a><span data-ttu-id="cf281-107">Szolgáltatási anyagjegyzék elemének frissítése</span><span class="sxs-lookup"><span data-stu-id="cf281-107">Update a service BOM element</span></span>

1.  <span data-ttu-id="cf281-108">Kattintson a **Szolgáltatáskezelés** \> **Közös** \> **Szolgáltatási szerződések** \> **Szolgáltatási szerződések** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cf281-108">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>

2.  <span data-ttu-id="cf281-109">Kattintson a **Szerkesztés** elemre a **Szolgáltatási szerződések** részleteit tartalmazó képernyő megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="cf281-109">Click **Edit** to open the **Service agreements** details form.</span></span>

3.  <span data-ttu-id="cf281-110">A **Műveleti panelen** kattintson a **Szolgáltatás tárgyai** elemre a **Szolgáltatás tárgyai** képernyő megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="cf281-110">On the **Action Pane**, click **Service objects** to open the **Service objects** form.</span></span>

4.  <span data-ttu-id="cf281-111">Válassza ki azt az tárgyat, amelynél frissíteni szeretne egy anyagjegyzéksort, majd kattintson a **Tervező** parancsra.</span><span class="sxs-lookup"><span data-stu-id="cf281-111">Select the object to update a BOM line for, and then click **Designer**.</span></span>

5.  <span data-ttu-id="cf281-112">A **Tervező** képernyőn válassza ki azt az anyagjegyzéksort, amelyet frissíteni szeretne, majd kattintson az **Anyagjegyzéksor módosítása** elemre.</span><span class="sxs-lookup"><span data-stu-id="cf281-112">In the **Designer** form, select the BOM line to update, and then click **Edit BOM line**.</span></span>
    
    > [!NOTE]
    > <P><span data-ttu-id="cf281-113">A <STRONG>Beállítás</STRONG> lapon válassza ki a <STRONG>Módosítás hozzáadáskor</STRONG> jelölőnégyzetet, ha meg akarja nyitni az <STRONG>Anyagjegyzéksor módosítása</STRONG> képernyőt, amikor egy sort húzással visz át a szolgáltatási anyagjegyzékbe.</span><span class="sxs-lookup"><span data-stu-id="cf281-113">On the <STRONG>Setup</STRONG> tab, select the <STRONG>Edit when adding</STRONG> check box if you want the <STRONG>Edit BOM line</STRONG> form to open when you drag a line into the service BOM.</span></span></P>

6.  <span data-ttu-id="cf281-114">A **Mennyiség** mezőben Írja be a mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="cf281-114">In the **Quantity** field, enter the quantity.</span></span>

7.  <span data-ttu-id="cf281-115">Jelölje be a **Szervizrendeléssor létrehozása** jelölőnégyzetet, ha létre kíván hozni egy szervizrendeléssort a helyettesítő cikk számára, amely ezek után számlázható lesz.</span><span class="sxs-lookup"><span data-stu-id="cf281-115">If you want to create a service order line for the replacement item, which can then be invoiced, select the **Create service order line** check box.</span></span>

8.  <span data-ttu-id="cf281-116">Zárja be a párbeszédpanelt az **OK** gombra kattintva.</span><span class="sxs-lookup"><span data-stu-id="cf281-116">Click **OK** to close the form.</span></span>

## <a name="delete-a-service-bom-line"></a><span data-ttu-id="cf281-117">Szolgáltatási anyagjegyzéksor törlése</span><span class="sxs-lookup"><span data-stu-id="cf281-117">Delete a service BOM line</span></span>

1.  <span data-ttu-id="cf281-118">Kattintson a **Szolgáltatáskezelés** \> **Közös** \> **Szolgáltatási szerződések** \> **Szolgáltatási szerződések** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cf281-118">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>

2.  <span data-ttu-id="cf281-119">Kattintson a **Szerkesztés** elemre a **Szolgáltatási szerződések** részleteit tartalmazó képernyő megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="cf281-119">Click **Edit** to open the **Service agreements** details form.</span></span>

3.  <span data-ttu-id="cf281-120">A **Műveleti panelen** kattintson a **Szolgáltatás tárgyai** elemre a **Szolgáltatás tárgyai** képernyő megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="cf281-120">On the **Action Pane**, click **Service objects** to open the **Service objects** form.</span></span>

4.  <span data-ttu-id="cf281-121">Válassza ki azt a tárgyat, amelyből törölni szeretne egy anyagjegyzéksort, majd kattintson a **Tervező** parancsra.</span><span class="sxs-lookup"><span data-stu-id="cf281-121">Select the object to delete a service BOM line from, and then click **Designer**.</span></span>

5.  <span data-ttu-id="cf281-122">A **Tervező** képernyőn válassza ki azt az anyagjegyzéksort, amelyet törölni szeretne, majd kattintson az **Anyagjegyzéksor törlése** elemre.</span><span class="sxs-lookup"><span data-stu-id="cf281-122">In the **Designer** form, select the BOM line to delete, and then click **Delete BOM line**.</span></span>

## <a name="see-also"></a><span data-ttu-id="cf281-123">Lásd még</span><span class="sxs-lookup"><span data-stu-id="cf281-123">See also</span></span>

[<span data-ttu-id="cf281-124">Sablonanyagjegyzékek</span><span class="sxs-lookup"><span data-stu-id="cf281-124">Template BOMs</span></span>](template-boms.md)

  


