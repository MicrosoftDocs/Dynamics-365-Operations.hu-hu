---
title: Vevői munkafolyamat
description: Ez a témakör a vevői munkafolyamattal kapcsolatban tartalmaz információkat. A munkafolyamat segítségével módosíthat a vevőre vonatkozó specifikus mezőket, és jóváhagyásra küldheti ezeket a módosításokat, mielőtt hozzáadásra kerülnének a vevőhöz.
author: mikefalkner
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: c769d225ee0f7b35719c37d9b9bc690a20060911
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5817269"
---
# <a name="customer-workflow"></a><span data-ttu-id="12e64-104">Vevői munkafolyamat</span><span class="sxs-lookup"><span data-stu-id="12e64-104">Customer workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="12e64-105">A vevői munkafolyamatot hozzáadtuk a 8.0.4-es verzióhoz.</span><span class="sxs-lookup"><span data-stu-id="12e64-105">The customer workflow has been added to version 8.0.4.</span></span> <span data-ttu-id="12e64-106">A munkafolyamat segítségével módosíthatja a vevőre vonatkozó specifikus mezőket, és jóváhagyásra küldheti ezeket a módosításokat, mielőtt hozzáadásra kerülnének a vevőhöz.</span><span class="sxs-lookup"><span data-stu-id="12e64-106">You can change specific fields for a customer and then send those changes for approval by using the workflow before they are added to the customer.</span></span>

## <a name="set-up-the-customer-workflow"></a><span data-ttu-id="12e64-107">Vevői munkafolyamat beállítása</span><span class="sxs-lookup"><span data-stu-id="12e64-107">Set up the customer workflow</span></span>

<span data-ttu-id="12e64-108">A vevői munkafolyamat funkció használata előtt engedélyeznie kell azt.</span><span class="sxs-lookup"><span data-stu-id="12e64-108">Before you can use the customer workflow feature, you must enable it.</span></span>

1. <span data-ttu-id="12e64-109">Lépjen a **Kinnlevőségek \> Beállítások \> Kinnlevőségek paraméterei** pontra.</span><span class="sxs-lookup"><span data-stu-id="12e64-109">Go to **Accounts receivable \> Setup \> Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="12e64-110">A funkció engedélyezéséhez állítsa az **Általános** lapon belül a **Vevői jóváhagyás** gyorslapon a **Vevői jóváhagyások engedélyezése** beállítást **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="12e64-110">On the **General** tab, on the **Customer approval** FastTab, set the **Enable customer approvals** option to **Yes** to enable the feature.</span></span>
3. <span data-ttu-id="12e64-111">Az **Adatentitás viselkedése** mezőben válassza azt a viselkedést, amelyet az adatentitás az adatok importálásakor alkalmazzon:</span><span class="sxs-lookup"><span data-stu-id="12e64-111">In the **Data entity behavior** field, select the behavior that the data entities should use when data is imported:</span></span>

    - <span data-ttu-id="12e64-112">**Módosítások engedélyezése jóváhagyás nélkül** – Egy entitás módosíthatja a vevői rekordot anélkül, hogy a munkafolyamaton keresztül kellene vinnie.</span><span class="sxs-lookup"><span data-stu-id="12e64-112">**Allow changes without approval** – An entity can update the customer record without processing it through the workflow.</span></span>
    - <span data-ttu-id="12e64-113">**Módosítások elutasítása** – A vevő rekordot nem lehet módosítani.</span><span class="sxs-lookup"><span data-stu-id="12e64-113">**Reject changes** – Changes can't be made to the customer record.</span></span> <span data-ttu-id="12e64-114">Az importálás sikertelen lesz a munkafolyamat számára engedélyezett mezőkre vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="12e64-114">The import will fail for the fields that are enabled for the workflow.</span></span>
    - <span data-ttu-id="12e64-115">**Módosítási javaslatok létrehozása** – Minden mező módosítható, kivéve azok, amelyek a munkafolyamat számára engedélyezve vannak.</span><span class="sxs-lookup"><span data-stu-id="12e64-115">**Create change proposals** – All fields will be changed except the fields that are enabled for the workflow.</span></span> <span data-ttu-id="12e64-116">Az ilyen mezőkbe bevitt értékek javasolt módosításként kerülnek hozzáadásra a vevőhöz, a munkafolyamat pedig automatikus elindul.</span><span class="sxs-lookup"><span data-stu-id="12e64-116">The new values for those fields will be added to the customer as proposed changes, and the workflow will be started automatically.</span></span>

4. <span data-ttu-id="12e64-117">A vevői mezők listájában jelölje be az **Engedélyezés** jelölőnégyzetet minden olyan mező esetében, amelyeket jóvá kell hagyni, mielőtt véglegesíteni lehet a módosításokat.</span><span class="sxs-lookup"><span data-stu-id="12e64-117">In the list of customer fields, select then **Enable** check box for every field that must be approved before the changes can be made.</span></span>
5. <span data-ttu-id="12e64-118">Lépjen a **Kinnlevőségek \> Beállítások \> Kinnlevőségek munkafolyamatai** pontra.</span><span class="sxs-lookup"><span data-stu-id="12e64-118">Go to **Accounts receivable \> Setup \> Accounts receivable workflows**.</span></span>
6. <span data-ttu-id="12e64-119">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="12e64-119">Select **New**.</span></span>
7. <span data-ttu-id="12e64-120">Válassza a **Javasolt vevői módosítások munkafolyamata** elemet.</span><span class="sxs-lookup"><span data-stu-id="12e64-120">Select **Proposed customer change workflow**.</span></span> 
8. <span data-ttu-id="12e64-121">Állítsa be a munkafolyamatot úgy, hogy megfeleljen a jóváhagyási folyamatnak.</span><span class="sxs-lookup"><span data-stu-id="12e64-121">Set up the workflow so that it matches your approval process.</span></span> <span data-ttu-id="12e64-122">A **Munkafolyamat-jóváhagyás javasolt vevői módosítások esetén** munkafolyamat jóváhagyási eleme alkalmazza a módosításokat a vevőre vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="12e64-122">The **Workflow approval for proposed customer change** workflow approval element will apply the changes to the customer.</span></span>

## <a name="change-customer-information-and-submit-the-changes-to-the-workflow"></a><span data-ttu-id="12e64-123">Vevőadatok módosítása és a módosítások elküldése a munkafolyamatba</span><span class="sxs-lookup"><span data-stu-id="12e64-123">Change customer information and submit the changes to the workflow</span></span>

<span data-ttu-id="12e64-124">Ha egy olyan mezőt változtat, amely engedélyezve van a munkafolyamat számára, a **Javasolt módosítások** oldal jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="12e64-124">When you change a field that is enabled for the workflow, the **Proposed changes** page appears.</span></span> <span data-ttu-id="12e64-125">Ez az oldal megmutatja a mező eredeti értékét és az újonnan megadott értéket.</span><span class="sxs-lookup"><span data-stu-id="12e64-125">This page shows the original value of the field and the new value that you entered.</span></span> <span data-ttu-id="12e64-126">A megváltoztatott mező értéke visszaáll az eredeti értékre.</span><span class="sxs-lookup"><span data-stu-id="12e64-126">The field that you changed is reverted to its original value.</span></span> <span data-ttu-id="12e64-127">Az oldalon egy állapotüzenet tájékoztatja arról, hogy a módosításokat még nem küldte el.</span><span class="sxs-lookup"><span data-stu-id="12e64-127">A status message on the page informs you that your changes haven't been submitted.</span></span>

<span data-ttu-id="12e64-128">Minden alkalommal, amikor olyan mezőt módosít, amely a munkafolyamat számára engedélyezve van, a mező hozzáadásra kerül a javasolt módosítások listájához.</span><span class="sxs-lookup"><span data-stu-id="12e64-128">Every time that you change a field that is enabled for the workflow, that field is added to the list of proposed changes.</span></span> <span data-ttu-id="12e64-129">Egy mező javasolt értékének elvetése érdekében használja a listában a mező mellett található **Elvetés** gombot.</span><span class="sxs-lookup"><span data-stu-id="12e64-129">To discard the proposed value for a field, use the **Discard** button next to the field in the list.</span></span> <span data-ttu-id="12e64-130">Az összes módosítás elvetése érdekében válassza az oldal alján található **Összes elvetése** gombot.</span><span class="sxs-lookup"><span data-stu-id="12e64-130">To discard all changes, use the **Discard all change** button at the bottom of the page.</span></span> <span data-ttu-id="12e64-131">Az oldal bezárásához kattintson az **Ok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="12e64-131">Select **OK** to close the page.</span></span>

<span data-ttu-id="12e64-132">Amennyiben legalább egy javasolt módosítással rendelkezik, két további menü jelenik meg a Műveletpanelen: a **Javasolt módosítások** és a **Munkafolyamat**.</span><span class="sxs-lookup"><span data-stu-id="12e64-132">After you have at least one proposed change, two additional menus appear on the Action Pane: **Proposed changes** and **Workflow**.</span></span>

1. <span data-ttu-id="12e64-133">A **Javasolt módosítások** oldal megnyitásához válassza a **Javasolt módosítások** menüt, és tekintse át a módosításokat.</span><span class="sxs-lookup"><span data-stu-id="12e64-133">Select **Proposed changes** to open the **Proposed changes** page and review your changes.</span></span>
2. <span data-ttu-id="12e64-134">A módosítások munkafolyamatba történő elküldéséhez válassza a **Munkafolyamat \> Elküldés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="12e64-134">Select **Workflow \> Submit** to submit the changes to the workflow.</span></span>

    <span data-ttu-id="12e64-135">Az oldalon látható állapot a következőre változik: **Jóváhagyásra váró módosítások**.</span><span class="sxs-lookup"><span data-stu-id="12e64-135">The status on the page is changed to **Changes pending approval**.</span></span>

<span data-ttu-id="12e64-136">A munkafolyamat az alkalmazás szokásos munkafolyamata.</span><span class="sxs-lookup"><span data-stu-id="12e64-136">The workflow follows the standard workflow process in the application.</span></span> <span data-ttu-id="12e64-137">A jóváhagyót a rendszer a **Vevő** oldalra irányítja, ahol áttekintheti a **Javasolt módosítások** oldalon található módosításokat, majd a munkafolyamat jóváhagyásához kiválaszthatja a **Munkafolyamat \> Jóváhagyás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="12e64-137">The approver is directed to the **Customer** page where the changes can be reviewed on the **Proposed changes** page and then select **Workflow \> Approve** to approve the workflow.</span></span> <span data-ttu-id="12e64-138">Miután minden jóváhagyás befejeződött, a mezők a javasolt értékekre frissülnek.</span><span class="sxs-lookup"><span data-stu-id="12e64-138">After all approvals are completed, the fields are updated with the values that you proposed.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]