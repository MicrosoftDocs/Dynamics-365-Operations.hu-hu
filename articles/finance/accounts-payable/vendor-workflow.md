---
title: Szállítói munkafolyamat
description: Módosítsa a szállító adatait és egy munkafolyamattal hagyja jóvá.
author: mikefalkner
manager: annbe
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Vendor
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: fb89b54b2f9377c216c447590a9434e3ff2d9bac
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5248135"
---
# <a name="vendor-workflow"></a><span data-ttu-id="0b153-103">Szállítói munkafolyamat</span><span class="sxs-lookup"><span data-stu-id="0b153-103">Vendor workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0b153-104">A szállító munkafolyamat használata esetén az egyes mezőkön végrehajtott módosítások el lesznek küldve a munkafolyamathoz jóváhagyásra, mielőtt hozzáadásra kerülnek a szállítóhoz.</span><span class="sxs-lookup"><span data-stu-id="0b153-104">When the vendor workflow is used, changes that are made to specific fields are sent to the workflow for approval before they are added to the vendor.</span></span>

## <a name="set-up-the-vendor-workflow"></a><span data-ttu-id="0b153-105">Szállítói munkafolyamat beállítása</span><span class="sxs-lookup"><span data-stu-id="0b153-105">Set up the vendor workflow</span></span>

<span data-ttu-id="0b153-106">A munkafolyamat használatához előbb aktiválni kell azt.</span><span class="sxs-lookup"><span data-stu-id="0b153-106">Before you can use the workflow feature, you must enable it.</span></span>

1. <span data-ttu-id="0b153-107">Ugorjon a **Kötelezettségek \> Beállítás \> Kötelezettségek paraméterei pontra**.</span><span class="sxs-lookup"><span data-stu-id="0b153-107">Go to **Accounts payable \> Setup \> Accounts payable parameters**.</span></span>
2. <span data-ttu-id="0b153-108">Az **Általános** lapon, a **Szállítói jóváhagyás** gyorslapon állítsa a **Feladatrögzítés engedélyezése** beállítást **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="0b153-108">On the **General** tab, on the **Vendor approval** FastTab, set the **Enable vendor approvals** option to **Yes**.</span></span>
3. <span data-ttu-id="0b153-109">Az **Adatentitás működése** mezőben, válassza ki az adatok importálásakor használandó viselkedést:</span><span class="sxs-lookup"><span data-stu-id="0b153-109">In the **Data entity behavior** field, select the behavior that should be used when data is imported:</span></span>

    - <span data-ttu-id="0b153-110">**Módosítások engedélyezése jóváhagyás nélkül** – Az adatentitás lehet frissítheti a szállítórekordot a munkafolyamat-feldolgozása nélkül.</span><span class="sxs-lookup"><span data-stu-id="0b153-110">**Allow changes without approval** – The data entity can update the vendor record without processing it through the workflow.</span></span>
    - <span data-ttu-id="0b153-111">**Módosítások elvetése** – Nem módosíthatók a szállítói rekordok.</span><span class="sxs-lookup"><span data-stu-id="0b153-111">**Reject changes** – Changes can't be made to the vendor record.</span></span> <span data-ttu-id="0b153-112">Az importálás sikertelen lesz azokhoz a mezőkhöz, amelyek engedélyezve vannak ehhez a munkafolyamathoz.</span><span class="sxs-lookup"><span data-stu-id="0b153-112">The import will fail for the fields that are enabled for the workflow.</span></span>
    - <span data-ttu-id="0b153-113">**Módosítási javaslatok létrehozása** – Minden mező meg fog változni a munkafolyamathoz engedélyezett mezők kivételével.</span><span class="sxs-lookup"><span data-stu-id="0b153-113">**Create change proposals** – All fields will be changed except the fields that are enabled for the workflow.</span></span> <span data-ttu-id="0b153-114">Ezen a mezők új értékei hozzá lesznek adva a szállítóhoz javasolt módosításokként, és a munkafolyamat automatikusan elindul.</span><span class="sxs-lookup"><span data-stu-id="0b153-114">The new values for those fields will be added to the vendor as proposed changes, and the workflow will be started automatically.</span></span>

4. <span data-ttu-id="0b153-115">A szállítói mezők listájában jelölje be az **Engedélyezése** jelölőnégyzetet minden mezőhöz, amelyet a módosítás előtt jóvá kell hagyni.</span><span class="sxs-lookup"><span data-stu-id="0b153-115">In the list of vendor fields, select the **Enable** check box for every field that must be approved before the changes can be made.</span></span>
5. <span data-ttu-id="0b153-116">Ugorjon a **Kötelezettségek \> Beállítás \> Kötelezettségekkel kapcsolatos munkafolyamatok** pontra.</span><span class="sxs-lookup"><span data-stu-id="0b153-116">Go to **Accounts payable \> Setup \> Accounts payable workflows**.</span></span>
6. <span data-ttu-id="0b153-117">**Új** kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="0b153-117">Select **New**.</span></span>
7. <span data-ttu-id="0b153-118">Válassza a **A javasolt szállítói módosítások munkafolyamata** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0b153-118">Select **Proposed vendor changes workflow**.</span></span> 
8. <span data-ttu-id="0b153-119">A munkafolyamatot állítsa be úgy, hogy megfeleljen a jóváhagyási folyamatának.</span><span class="sxs-lookup"><span data-stu-id="0b153-119">Set up the workflow so that it matches your approval process.</span></span> <span data-ttu-id="0b153-120">A **Javasolt szállítói módosításhoz tartozó munkafolyamat-jóváhagyás** munkafolyamat-jóváhagyási elem alkalmazza a módosításokat szállítóhoz.</span><span class="sxs-lookup"><span data-stu-id="0b153-120">The **Workflow approval for proposed vendor change** workflow approval element will apply the changes to the vendor.</span></span>

## <a name="change-vendor-information-and-submit-the-changes-to-the-workflow"></a><span data-ttu-id="0b153-121">A szállító adatainak módosítása és a módosításokat elküldése a munkafolyamatnak</span><span class="sxs-lookup"><span data-stu-id="0b153-121">Change vendor information and submit the changes to the workflow</span></span>

<span data-ttu-id="0b153-122">Ha módosít egy mezőt, amely engedélyezve van, a munkafolyamathoz, a **Javasolt módosítások** lap jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="0b153-122">When you change a field that is enabled for the workflow, the **Proposed changes** page appears.</span></span> <span data-ttu-id="0b153-123">Ez az oldal megmutatja a mező eredeti értékét és az újonnan megadott értéket.</span><span class="sxs-lookup"><span data-stu-id="0b153-123">This page shows the original value of the field and the new value that you entered.</span></span> <span data-ttu-id="0b153-124">A mezőt, amely a módosított vissza lett állítva az eredeti értékre.</span><span class="sxs-lookup"><span data-stu-id="0b153-124">The field that you changed is reverted to its original value.</span></span> <span data-ttu-id="0b153-125">Egy állapotüzenet is mutatja, hogy a módosítások még nem lettek beküldve.</span><span class="sxs-lookup"><span data-stu-id="0b153-125">A status message also informs you that your changes haven't been submitted.</span></span> 

<span data-ttu-id="0b153-126">Minden alkalommal, amikor módosít egy mezőt, amely engedélyezve van a munkafolyamathoz, az a mező hozzáadódik **Javasolt módosítások** oldalon található listához.</span><span class="sxs-lookup"><span data-stu-id="0b153-126">Every time that you change a field that is enabled for the workflow, that field is added to the list on the **Proposed changes** page.</span></span> <span data-ttu-id="0b153-127">A mezőhöz a javasolt érték elvetéséhez, használja az **Elvetés** gombot a listában található mező mellett.</span><span class="sxs-lookup"><span data-stu-id="0b153-127">To discard the proposed value for a field, use the **Discard** button next to the field in the list.</span></span> <span data-ttu-id="0b153-128">Az összes változtatás elvetéséhez használja az **Összes változtatás elvetése** gombot az oldal alján.</span><span class="sxs-lookup"><span data-stu-id="0b153-128">To discard all changes, use the **Discard all changes** button at the bottom of the page.</span></span> <span data-ttu-id="0b153-129">Válassza az **OK** lehetőséget az oldal bezárásához.</span><span class="sxs-lookup"><span data-stu-id="0b153-129">Select **OK** to close the page.</span></span>

<span data-ttu-id="0b153-130">Legalább egy javasolt módosítás után, két további lap jelenik meg a műveleti panelen: **Javasolt módosítások** és **Munkafolyamat**.</span><span class="sxs-lookup"><span data-stu-id="0b153-130">After you have at least one proposed change, two additional tabs appear on the action pane: **Proposed changes** and **Workflow**.</span></span>

1. <span data-ttu-id="0b153-131">Válassza a **Javasolt módosítások** elemet a **Javasolt módosítások** lap megnyitásához, és ellenőrizze a módosításait.</span><span class="sxs-lookup"><span data-stu-id="0b153-131">Select **Proposed changes** to open the **Proposed changes** page and review your changes.</span></span>
2. <span data-ttu-id="0b153-132">Válassza a **Munkafolyamat \> Beküldés lehetőséget, hogy beküldje a módosításokat a munkafolyamathoz**.</span><span class="sxs-lookup"><span data-stu-id="0b153-132">Select **Workflow \> Submit to submit the changes to workflow**.</span></span>

    <span data-ttu-id="0b153-133">Az oldalon látható állapot a következőre változik: **Jóváhagyásra váró módosítások**.</span><span class="sxs-lookup"><span data-stu-id="0b153-133">The status on the page is changed to **Changes pending approval**.</span></span>

<span data-ttu-id="0b153-134">A munkafolyamat a normál munkafolyamatot követi.</span><span class="sxs-lookup"><span data-stu-id="0b153-134">The workflow follows the standard workflow process.</span></span> <span data-ttu-id="0b153-135">A jóváhagyót a rendszer a **Szállító** oldalra irányítja, ahol áttekintheti a **Javasolt módosítások** oldalon található módosításokat, majd a munkafolyamat jóváhagyásához kiválaszthatja a **Munkafolyamat \> Jóváhagyás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0b153-135">The approver is directed to the **Vendor** page where the changes can be reviewed on the **Proposed changes** page and then select **Workflow \> Approve** to approve the workflow.</span></span> <span data-ttu-id="0b153-136">Miután minden jóváhagyás befejeződött, a mezők a javasolt értékekre frissülnek.</span><span class="sxs-lookup"><span data-stu-id="0b153-136">After all approvals are completed, the fields are updated with the values that you proposed.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]