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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d0c3656f765ea3c53c38679a1709a02fba36a848
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5204230"
---
# <a name="modify-a-service-bom"></a><span data-ttu-id="c33c3-103">Szolgáltatási anyagjegyzék módosítása</span><span class="sxs-lookup"><span data-stu-id="c33c3-103">Modify a Service BOM</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="c33c3-104">A szolgáltatási anyagjegyzékben rögzítheti egy elem előzményeit.</span><span class="sxs-lookup"><span data-stu-id="c33c3-104">You can record the history of an element in a service BOM.</span></span> <span data-ttu-id="c33c3-105">Minden alkalommal, amikor frissít egy anyagjegyzéksort, egy előzménysor jön létre az **Előzmények** ablakban.</span><span class="sxs-lookup"><span data-stu-id="c33c3-105">Every time that you update a BOM line, a history line is created in the **History** pane.</span></span> <span data-ttu-id="c33c3-106">Az előzménysor az anyagjegyzéksor aktuális állapotát mutatja.</span><span class="sxs-lookup"><span data-stu-id="c33c3-106">The history line shows the current state of the BOM line.</span></span>

## <a name="update-a-service-bom-element"></a><span data-ttu-id="c33c3-107">Szolgáltatási anyagjegyzék elemének frissítése</span><span class="sxs-lookup"><span data-stu-id="c33c3-107">Update a service BOM element</span></span>

1.  <span data-ttu-id="c33c3-108">Kattintson a **Szolgáltatáskezelés** \> **Közös** \> **Szolgáltatási szerződések** \> **Szolgáltatási szerződések** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c33c3-108">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>

2.  <span data-ttu-id="c33c3-109">Kattintson a **Szerkesztés** elemre a **Szolgáltatási szerződések** részleteit tartalmazó képernyő megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="c33c3-109">Click **Edit** to open the **Service agreements** details form.</span></span>

3.  <span data-ttu-id="c33c3-110">A **Műveleti panelen** kattintson a **Szolgáltatás tárgyai** elemre a **Szolgáltatás tárgyai** képernyő megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="c33c3-110">On the **Action Pane**, click **Service objects** to open the **Service objects** form.</span></span>

4.  <span data-ttu-id="c33c3-111">Válassza ki azt az tárgyat, amelynél frissíteni szeretne egy anyagjegyzéksort, majd kattintson a **Tervező** parancsra.</span><span class="sxs-lookup"><span data-stu-id="c33c3-111">Select the object to update a BOM line for, and then click **Designer**.</span></span>

5.  <span data-ttu-id="c33c3-112">A **Tervező** képernyőn válassza ki azt az anyagjegyzéksort, amelyet frissíteni szeretne, majd kattintson az **Anyagjegyzéksor módosítása** elemre.</span><span class="sxs-lookup"><span data-stu-id="c33c3-112">In the **Designer** form, select the BOM line to update, and then click **Edit BOM line**.</span></span>
    
    > [!NOTE]
    > <P><span data-ttu-id="c33c3-113">A <STRONG>Beállítás</STRONG> lapon válassza ki a <STRONG>Módosítás hozzáadáskor</STRONG> jelölőnégyzetet, ha meg akarja nyitni az <STRONG>Anyagjegyzéksor módosítása</STRONG> képernyőt, amikor egy sort húzással visz át a szolgáltatási anyagjegyzékbe.</span><span class="sxs-lookup"><span data-stu-id="c33c3-113">On the <STRONG>Setup</STRONG> tab, select the <STRONG>Edit when adding</STRONG> check box if you want the <STRONG>Edit BOM line</STRONG> form to open when you drag a line into the service BOM.</span></span></P>

6.  <span data-ttu-id="c33c3-114">A **Mennyiség** mezőben Írja be a mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="c33c3-114">In the **Quantity** field, enter the quantity.</span></span>

7.  <span data-ttu-id="c33c3-115">Jelölje be a **Szervizrendeléssor létrehozása** jelölőnégyzetet, ha létre kíván hozni egy szervizrendeléssort a helyettesítő cikk számára, amely ezek után számlázható lesz.</span><span class="sxs-lookup"><span data-stu-id="c33c3-115">If you want to create a service order line for the replacement item, which can then be invoiced, select the **Create service order line** check box.</span></span>

8.  <span data-ttu-id="c33c3-116">Zárja be a párbeszédpanelt az **OK** gombra kattintva.</span><span class="sxs-lookup"><span data-stu-id="c33c3-116">Click **OK** to close the form.</span></span>

## <a name="delete-a-service-bom-line"></a><span data-ttu-id="c33c3-117">Szolgáltatási anyagjegyzéksor törlése</span><span class="sxs-lookup"><span data-stu-id="c33c3-117">Delete a service BOM line</span></span>

1.  <span data-ttu-id="c33c3-118">Kattintson a **Szolgáltatáskezelés** \> **Közös** \> **Szolgáltatási szerződések** \> **Szolgáltatási szerződések** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c33c3-118">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>

2.  <span data-ttu-id="c33c3-119">Kattintson a **Szerkesztés** elemre a **Szolgáltatási szerződések** részleteit tartalmazó képernyő megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="c33c3-119">Click **Edit** to open the **Service agreements** details form.</span></span>

3.  <span data-ttu-id="c33c3-120">A **Műveleti panelen** kattintson a **Szolgáltatás tárgyai** elemre a **Szolgáltatás tárgyai** képernyő megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="c33c3-120">On the **Action Pane**, click **Service objects** to open the **Service objects** form.</span></span>

4.  <span data-ttu-id="c33c3-121">Válassza ki azt a tárgyat, amelyből törölni szeretne egy anyagjegyzéksort, majd kattintson a **Tervező** parancsra.</span><span class="sxs-lookup"><span data-stu-id="c33c3-121">Select the object to delete a service BOM line from, and then click **Designer**.</span></span>

5.  <span data-ttu-id="c33c3-122">A **Tervező** képernyőn válassza ki azt az anyagjegyzéksort, amelyet törölni szeretne, majd kattintson az **Anyagjegyzéksor törlése** elemre.</span><span class="sxs-lookup"><span data-stu-id="c33c3-122">In the **Designer** form, select the BOM line to delete, and then click **Delete BOM line**.</span></span>

## <a name="see-also"></a><span data-ttu-id="c33c3-123">Lásd még</span><span class="sxs-lookup"><span data-stu-id="c33c3-123">See also</span></span>

[<span data-ttu-id="c33c3-124">Sablonanyagjegyzékek</span><span class="sxs-lookup"><span data-stu-id="c33c3-124">Template BOMs</span></span>](template-boms.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]