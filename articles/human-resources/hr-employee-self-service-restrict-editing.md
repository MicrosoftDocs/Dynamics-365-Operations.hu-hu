---
title: Személyes adatok szerkesztésének korlátozása
description: A kapcsolattartók részleteinek alkalmazottak általi szerkesztésének korlátozása a Dynamics 365 Human Resources alkalmazásban.
author: andreabichsel
ms.date: 03/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: EssWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 727e0d4dbc5b330045bc9f91abab4d43b09e4382
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5794805"
---
# <a name="restrict-editing-of-personal-information"></a><span data-ttu-id="7dea3-103">Személyes adatok szerkesztésének korlátozása</span><span class="sxs-lookup"><span data-stu-id="7dea3-103">Restrict editing of personal information</span></span>

[!include [applies to](../includes/applies-to-hr.md)]
[!include [preview feature](./includes/preview-feature.md)]

<span data-ttu-id="7dea3-104">Ez a témakör azt ismerteti, hogyan lehet korlátozni az alkalmazottak számára a kapcsolattartók részleteinek szerkesztését a Dynamics 365 Human Resources alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="7dea3-104">This topic describes how to restrict employees from editing contact details in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="7dea3-105">Előfordulhat, hogy meg szeretné akadályozni, hogy az alkalmazottak bizonyos kapcsolattartási adatokat, például az vállalati telephelyet vagy az e-mail-címet szerkeszthessenek.</span><span class="sxs-lookup"><span data-stu-id="7dea3-105">You might want to prevent employees from editing certain contact details, such as their business location or email address.</span></span>

> [!NOTE]
> <span data-ttu-id="7dea3-106">A funkció használatához először engedélyeznie kell az **(Előzetes verzió) Alkalmazottak korlátozása a cím és kapcsolatfelvételi adatok hozzáadásánál és szerkesztésénél adott célok esetén** beállítást a Funkciókezelésben.</span><span class="sxs-lookup"><span data-stu-id="7dea3-106">To use this feature, you must first enable **(Preview) Restrict employees from adding or editing address and contact information for select purposes** in Feature management.</span></span> <span data-ttu-id="7dea3-107">Az előzetes funkciók aktiválásával kapcsolatos további részletekért tekintse meg a [Szolgáltatások kezelése](hr-admin-manage-features.md) oldalt.</span><span class="sxs-lookup"><span data-stu-id="7dea3-107">For more information about enabling preview features, see [Manage features](hr-admin-manage-features.md).</span></span><br><br><span data-ttu-id="7dea3-108">![Előzetes funkció engedélyezése](./media/hr-employee-self-service-restrict-enable.png)</span><span class="sxs-lookup"><span data-stu-id="7dea3-108">![Enable preview feature](./media/hr-employee-self-service-restrict-enable.png)</span></span>

## <a name="choose-the-information-an-employee-can-add-or-edit"></a><span data-ttu-id="7dea3-109">Válassza ki az alkalmazott által hozzáadható vagy szerkeszthető információkat</span><span class="sxs-lookup"><span data-stu-id="7dea3-109">Choose the information an employee can add or edit</span></span>

1. <span data-ttu-id="7dea3-110">A Human Resources szolgáltatásban válassza ki a **Személyzetkezelés** elemet , válassza ki a **hivatkozások** elemet, majd válassza ki a **emberi erőforrás paramétereit**.</span><span class="sxs-lookup"><span data-stu-id="7dea3-110">In Human Resources, select **Personnel management**, select **Links**, and then select **Human resources parameters**.</span></span>

   ![Lépjen a Humar Resources paramétereihez](./media/hr-employee-self-service-human-resources-parameters.png)

2. <span data-ttu-id="7dea3-112">A **Human Resources paraméterei** oldalon válassza az **Alkalmazotti önkiszolgáló rendszer** lapot.</span><span class="sxs-lookup"><span data-stu-id="7dea3-112">On the **Human resources parameters** page, select the **Employee self service** tab.</span></span>

   ![Válassza az Alkalmazotti önkiszolgáló rendszer lehetőséget](./media/hr-employee-self-service-tab.png)

3. <span data-ttu-id="7dea3-114">Az **Alkalmazotti önkiszolgáló rendszer** lapon törölje a jelet a **Cím- és kapcsolattartási adatok** szakaszösszes olyan információjának jelölőnégyzetéből, amelyet nem szeretne, ha az alkalmazottak hozzáadhatnának vagy szerkeszthetnének.</span><span class="sxs-lookup"><span data-stu-id="7dea3-114">On the **Employee self service** tab, uncheck all information in the **Address and contact information** section that you don't want employees to add or edit.</span></span> <span data-ttu-id="7dea3-115">Ebben a példában töröltük a jelet az **Üzleti** kapcsolattartói adatok jelölőnégyzetéből.</span><span class="sxs-lookup"><span data-stu-id="7dea3-115">In this example, we've unchecked **Business** contact information.</span></span>

   ![Az üzleti kapcsolattartási adatok szerkesztésének korlátozása](./media/hr-employee-self-service-restrict-business.png)

4. <span data-ttu-id="7dea3-117">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7dea3-117">Select **Save**.</span></span>

   ![Módosítások mentése](./media/hr-employee-self-service-restrict-save.png)

## <a name="employee-experience"></a><span data-ttu-id="7dea3-119">Alkalmazotti felhasználói élmény</span><span class="sxs-lookup"><span data-stu-id="7dea3-119">Employee experience</span></span>

<span data-ttu-id="7dea3-120">Miután korlátozta az alkalmazottak számára a kapcsolattartók részleteinek hozzáadását vagy szerkesztését, láthatják az adatokat, de nem módosíthatja őket.</span><span class="sxs-lookup"><span data-stu-id="7dea3-120">After you've restricted employees from adding or editing contact details, they can see the information, but can't change it.</span></span>

<span data-ttu-id="7dea3-121">Ebben a példában, ahol az alkalmazottak nem szerkeszthetik az **Üzleti** kapcsolattartási adatokat, továbbra is láthatják az adatokat az Alkalmazotti önkiszolgáló rendszerben:</span><span class="sxs-lookup"><span data-stu-id="7dea3-121">In this example, where employees are restricted from editing **Business** contact details, they can still see the information in Employee self service:</span></span>

![Üzleti kapcsolattartói részletek megtekintése](./media/hr-employee-self-service-restrict-view.png)

<span data-ttu-id="7dea3-123">Amikor azonban kiválasztják az üzleti kapcsolattartó adatait, a **Cím szerkesztése** ablaktábla csak olvashatóként jelenik meg, és egyik mező sem módosítható.</span><span class="sxs-lookup"><span data-stu-id="7dea3-123">However, when they select the business contact details, the **Edit address** pane appears as read-only, and they can't change any of the fields.</span></span>

![Az üzleti kapcsolattartó adatai csak olvashatóként jelennek meg](./media/hr-employee-self-service-restrict-read-only.png)

<span data-ttu-id="7dea3-125">Emellett, ha a **Hozzáadás** gombot választják új cím hozzáadásához, akkor a **Cél** legördülő listában nem választhatják ki az **Üzleti** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7dea3-125">In addition, if they select **Add** to add a new address, they can't select **Business** from the **Purpose** dropdown box.</span></span>

![Az alkalmazott nem tud Üzleti címet hozzáadni.](./media/hr-employee-self-service-restrict-add.png)

<span data-ttu-id="7dea3-127">Az alkalmazottak ugyanezzel a viselkedéssel találkoznak, amikor kiválasztják a **Kapcsolattartó adatai** elemet a **Személyes adatok** lapon, és új címet adnak meg.</span><span class="sxs-lookup"><span data-stu-id="7dea3-127">Employees get the same experience when they select **Contact details** on the **Personal information** page and add a new address.</span></span> <span data-ttu-id="7dea3-128">A **Cél** legördülő lista csak azokat az információtípusokat jeleníti meg, amelyekhez hozzáadhatnak.</span><span class="sxs-lookup"><span data-stu-id="7dea3-128">The **Purpose** dropdown box only displays the types of information they can add.</span></span> 

![Az alkalmazott nem választhatja ki a Vállalkozás lehetőséget a Cél legördülő mezőben](./media/hr-employee-self-service-restrict-purpose.png)

<span data-ttu-id="7dea3-130">A **Kapcsolattartó adatai** most a **Cél** értéket jeleníti meg a rácsban.</span><span class="sxs-lookup"><span data-stu-id="7dea3-130">**Contact details** now shows **Purpose** in the grid.</span></span>

![A Cél jelenik meg a Kapcsolattartó adatai rácsban](./media/hr-employee-self-service-restrict-purpose-grid.png)

## <a name="see-also"></a><span data-ttu-id="7dea3-132">Lásd még</span><span class="sxs-lookup"><span data-stu-id="7dea3-132">See also</span></span>

[<span data-ttu-id="7dea3-133">Alkalmazotti és vezetői önkiszolgáló rendszer áttekintése</span><span class="sxs-lookup"><span data-stu-id="7dea3-133">Employee and Manager self service overview</span></span>](hr-employee-manager-self-service-overview.md)<br>
[<span data-ttu-id="7dea3-134">A Human Resources paramétereinek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="7dea3-134">Configure Human resources parameters</span></span>](hr-setup-parameters.md)<br>
[<span data-ttu-id="7dea3-135">Személyes információk szerkesztése</span><span class="sxs-lookup"><span data-stu-id="7dea3-135">Edit personal information</span></span>](hr-employee-manager-self-service-edit-personal-information.md)