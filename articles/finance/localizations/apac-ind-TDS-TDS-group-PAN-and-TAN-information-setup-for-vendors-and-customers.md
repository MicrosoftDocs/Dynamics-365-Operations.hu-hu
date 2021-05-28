---
title: TDS-csoport, PAN és TAN-információk beállítása a vevők és szállítók számára
description: Ez a témakör bemutatja a forrásnál levont adó (TDS) csoport, az állandó számlaszám (PAN) és az adószámlaszám (TAN) beállítását szállítókhoz.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: fd33b1775afefed798f1e9bb7601f4112222c430
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023299"
---
# <a name="tds-group-pan-and-tan-information-setup-for-vendors-and-customers"></a><span data-ttu-id="a6566-103">TDS-csoport, PAN és TAN-információk beállítása a vevők és szállítók számára</span><span class="sxs-lookup"><span data-stu-id="a6566-103">TDS group, PAN, and TAN information setup for vendors and customers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a6566-104">Ez a témakör bemutatja a forrásnál levont adó (TDS) csoport, az állandó számlaszám (PAN) és az adószámlaszám (TAN) beállítását szállítókhoz.</span><span class="sxs-lookup"><span data-stu-id="a6566-104">This topic explains how to set up information about the Tax Deducted at Source (TDS) group, permanent account number (PAN), and tax account number (TAN) for vendors and customers.</span></span>

1. <span data-ttu-id="a6566-105">Ugrás a **Kötelezettségek \> Szállítók: \> Minden szállító** vagy **Kinnlevőségek \> Vevők \> Minden vevő** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a6566-105">Go to **Accounts payable \> Vendors \> All vendors** or **Accounts receivable \> Customers \> All customers**.</span></span>

    <span data-ttu-id="a6566-106">[![Minden szállító lap](./media/apac-ind-TDS-55.png)](./media/apac-ind-TDS-55.png)</span><span class="sxs-lookup"><span data-stu-id="a6566-106">[![All vendors page](./media/apac-ind-TDS-55.png)](./media/apac-ind-TDS-55.png)</span></span>

2. <span data-ttu-id="a6566-107">A Műveletablakban válassza az **Új** lehetőséget a szállító vagy vevő létrehozásához, és adja meg a szükséges adatokat.</span><span class="sxs-lookup"><span data-stu-id="a6566-107">On the Action Pane, select **New** to create a vendor or customer, and enter the required details.</span></span> <span data-ttu-id="a6566-108">Másik lehetőségként válasszon ki egy meglévő szállítót vagy vevőt.</span><span class="sxs-lookup"><span data-stu-id="a6566-108">Alternatively, select an existing vendor or customer.</span></span>
3. <span data-ttu-id="a6566-109">A **Számla és szállítás** gyorslapon az **Adóelőleg** szakaszban állítsa be az **Adóelőleg számítása** lehetőséget **Igen** értékre adóelőleg, TDS, forrásnál beszedett adó (TCS) számításához a szállítóhoz vagy ügyfélhez.</span><span class="sxs-lookup"><span data-stu-id="a6566-109">On the **Invoice and delivery** FastTab, in the **Withholding tax** section, set the **Calculate withholding tax** option to **Yes** to calculate withholding tax, TDS, or Tax Collected at Source (TCS) for the vendor or customer.</span></span>
4. <span data-ttu-id="a6566-110">A beszerzési számla TDS-ének számítása a szállítóhoz vagy vevőhöz megadott alapértelmezett TDS-csoport alapján történik.</span><span class="sxs-lookup"><span data-stu-id="a6566-110">TDS for a purchase invoice is calculated based on the default TDS group that is defined for the vendor or customer.</span></span> <span data-ttu-id="a6566-111">A **TDS-csoport** mezőben válassza ki az alapértelmezett TDS-csoportot.</span><span class="sxs-lookup"><span data-stu-id="a6566-111">In the **TDS group** field, select the default TDS group.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a6566-112">Az **Adóelőleg-csoport** mező és a **TCS-csoport** mező nem lesz elérhető, ha a **TDS-csoport** mezőben egy TDS-csoportot választ.</span><span class="sxs-lookup"><span data-stu-id="a6566-112">When you select a TDS group in the **TDS group** field, the **Withholding tax group** and **TCS group** fields become unavailable.</span></span>

5. <span data-ttu-id="a6566-113">Válassza ki a szállító vagy vevő állandó számlaszámának állapotát az **Adóinformáció** gyorslapon a **PAN-információk** szakaszban, az **Állapot** mezőben:</span><span class="sxs-lookup"><span data-stu-id="a6566-113">On the **Tax information** FastTab, in the **PAN information** section, in the **Status** field, select the status of the permanent account number for the vendor or customer:</span></span>

    - <span data-ttu-id="a6566-114">**Nem érhető el** – A szállítónak vagy a vevőnek nincs PAN-ja.</span><span class="sxs-lookup"><span data-stu-id="a6566-114">**Not available** – The vendor or customer doesn't have a PAN.</span></span>
    - <span data-ttu-id="a6566-115">**Beérkezett** – A szállítónak vagy a vevőnek van PAN-ja.</span><span class="sxs-lookup"><span data-stu-id="a6566-115">**Received** – The vendor or customer has a PAN.</span></span>
    - <span data-ttu-id="a6566-116">**Jelentkezett** – a szállító vagy a vevő PAN-ért jelentkezett.</span><span class="sxs-lookup"><span data-stu-id="a6566-116">**Applied** – The vendor or customer has applied for a PAN.</span></span>
    - <span data-ttu-id="a6566-117">**Érvénytelen** – A szállítónak vagy a vevőnek van PAN-ja, de nem érvényes.</span><span class="sxs-lookup"><span data-stu-id="a6566-117">**Invalid** – The vendor or customer has a PAN, but it isn't valid.</span></span>

6. <span data-ttu-id="a6566-118">Ha a **Beérkezett** beállítást választotta az **Állapot** mezőben annak jelzésére, hogy a szállítónak vagy a vevőnek van PAN-ja, írja be a PAN számot a **Szám** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="a6566-118">If you selected **Received** in the **Status** field to indicate that the vendor or customer has a PAN, enter the PAN in the **Number** field.</span></span> <span data-ttu-id="a6566-119">A PAN-nak öt betűből, majd négy numerikus karakterből, majd egy betűből kell állnia.</span><span class="sxs-lookup"><span data-stu-id="a6566-119">The PAN must consist of five alphabetic characters, then four numeric characters, and then one alphabetic character.</span></span> <span data-ttu-id="a6566-120">Egy példa: **ABCDE1260A**.</span><span class="sxs-lookup"><span data-stu-id="a6566-120">Here is an example: **ABCDE1260A**.</span></span>
7. <span data-ttu-id="a6566-121">Ha a **Jelentkezett** beállítást választotta az **Állapot** mezőben annak jelzésére, hogy a szállító vagy a vevő igényelt PAN-t, írja be a hivatkozási számot a **Referenciaszám** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="a6566-121">If you selected **Applied** in the **Status** field to indicate that the vendor or customer has applied for PAN, enter the reference number in the **Reference number** field.</span></span>
8. <span data-ttu-id="a6566-122">Az **Értékelő** jellege mezőben válassza ki az értékelő kategória jellegét a szállítóhoz vagy ügyfélhez.</span><span class="sxs-lookup"><span data-stu-id="a6566-122">In the **Nature of assessee** field, select the nature of assessee category that the vendor or customer belongs to:</span></span>

    - <span data-ttu-id="a6566-123">Cég</span><span class="sxs-lookup"><span data-stu-id="a6566-123">Company</span></span>
    - <span data-ttu-id="a6566-124">HUF</span><span class="sxs-lookup"><span data-stu-id="a6566-124">HUF</span></span>
    - <span data-ttu-id="a6566-125">Megerősítve</span><span class="sxs-lookup"><span data-stu-id="a6566-125">Firm</span></span>
    - <span data-ttu-id="a6566-126">Individual</span><span class="sxs-lookup"><span data-stu-id="a6566-126">Individual</span></span>
    - <span data-ttu-id="a6566-127">AOP</span><span class="sxs-lookup"><span data-stu-id="a6566-127">AOP</span></span>
    - <span data-ttu-id="a6566-128">BOI</span><span class="sxs-lookup"><span data-stu-id="a6566-128">BOI</span></span>
    - <span data-ttu-id="a6566-129">Önkormányzat</span><span class="sxs-lookup"><span data-stu-id="a6566-129">Local authority</span></span>
    - <span data-ttu-id="a6566-130">Egyebek</span><span class="sxs-lookup"><span data-stu-id="a6566-130">Others</span></span>

    <span data-ttu-id="a6566-131">[![Adóinformációk gyorslap](./media/apac-ind-TDS-56.png)](./media/apac-ind-TDS-56.png)</span><span class="sxs-lookup"><span data-stu-id="a6566-131">[![Tax information FastTab](./media/apac-ind-TDS-56.png)](./media/apac-ind-TDS-56.png)</span></span>

9. <span data-ttu-id="a6566-132">Ezután a Műveleti panelen a **Szállító** lap **Regisztráció** csoportjában válassza a **Regisztrációs azonosítók** lehetőséget a **Címek kezelése** lap megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="a6566-132">On the Action Pane, on the **Vendor** tab, in the **Registration** group, select **Registration IDs** to open the **Manage addresses** page.</span></span>
10. <span data-ttu-id="a6566-133">A **Címek kezelése** lapon, az **Adóinformációk** gyorslapon válassza a **Hozzáadás** vagy a **Szerkesztés** lehetőséget, hogy megnyíljon az **Adóinformációk kezelése** lap, ahol karbantarthatja az adóregisztrációs bejegyzést.</span><span class="sxs-lookup"><span data-stu-id="a6566-133">On the **Manage addresses** page, on the **Tax information** FastTab, select **Add** or **Edit** to open the **Manage tax information** page, where you can maintain the tax registration entry.</span></span>
11. <span data-ttu-id="a6566-134">Az **Adóinformációk kezelése** lapon, az **Adóelőleg** gyorslap **Adószámla száma (TAN)** mezőjében adja meg a TAN-t.</span><span class="sxs-lookup"><span data-stu-id="a6566-134">On the **Manage tax information** page, on the **Withholding tax** FastTab, in the **Tax Account Number (TAN)** field, enter the TAN.</span></span> <span data-ttu-id="a6566-135">A TAN-nak négy betűből, majd öt numerikus karakterből, majd egy betűből kell állnia.</span><span class="sxs-lookup"><span data-stu-id="a6566-135">The TAN must consist of four alphabetic characters, then five numeric characters, and then one alphabetic character.</span></span> <span data-ttu-id="a6566-136">Egy példa: **AFGH54821T**.</span><span class="sxs-lookup"><span data-stu-id="a6566-136">Here is an example: **AFGH54821T**.</span></span>
12. <span data-ttu-id="a6566-137">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="a6566-137">Close the page.</span></span>
