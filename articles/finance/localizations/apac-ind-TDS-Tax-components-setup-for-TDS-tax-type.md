---
title: Adó-összetevők beállítása a TDS-adótípusra
description: Ez a témakör elmagyarázza, hogyan állíthatja be az adóelőleg-összetevőket a Forrásnál levont adó (TDS) adótípushoz. Azt is elmagyarázza, hogyan kell meghatározni az egyes TDS-összetevők TDS-ének kiszámításához használt küszöbértéket.
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
ms.openlocfilehash: 6e0a6a05fcb4afb8c8965e25c3089bc1b3d98431
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023293"
---
# <a name="set-up-tax-components-for-the-tds-tax-type"></a><span data-ttu-id="42eb1-104">Adó-összetevők beállítása a TDS-adótípusra</span><span class="sxs-lookup"><span data-stu-id="42eb1-104">Set up tax components for the TDS tax type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="42eb1-105">Ez a témakör elmagyarázza, hogyan állíthatja be az adóelőleg-összetevőket a Forrásnál levont adó (TDS) adótípushoz.</span><span class="sxs-lookup"><span data-stu-id="42eb1-105">This topic explains how to set up withholding tax components for the Tax Deducted at Source (TDS) tax type.</span></span> <span data-ttu-id="42eb1-106">A TDS komponensek a TDS, felár, PE-Cess, és SHE Cess.</span><span class="sxs-lookup"><span data-stu-id="42eb1-106">The TDS components are TDS, surcharge, PE-Cess, and SHE Cess.</span></span> <span data-ttu-id="42eb1-107">Ez a témakör elmagyarázza, hogyan kell meghatározni az egyes TDS-összetevők TDS-ének kiszámításához használt küszöbértéket.</span><span class="sxs-lookup"><span data-stu-id="42eb1-107">This topic also explains how to define the threshold that is used to calculate TDS for each TDS component.</span></span> <span data-ttu-id="42eb1-108">Ezenkívül meghatározhat egy kivételi küszöbértéket, amelyet az egyes TDS-összetevők TDS-ének kiszámítására használhat.</span><span class="sxs-lookup"><span data-stu-id="42eb1-108">Additionally, you can define an exception threshold that is used to calculate TDS for each TDS component.</span></span>

<span data-ttu-id="42eb1-109">A TDS-összetevők beállításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="42eb1-109">Follow these steps to set up TDS components.</span></span>

1. <span data-ttu-id="42eb1-110">Lépjen az **Adó \> Beállítás \> Adóelőleg \> Adóelőleg-összetevők** részhez.</span><span class="sxs-lookup"><span data-stu-id="42eb1-110">Go to **Tax \> Setup \> Withholding tax \> Withholding tax components**.</span></span>

    <span data-ttu-id="42eb1-111">[![Adóelőleg-összetevők oldal](./media/apac-ind-TDS-9.png)](./media/apac-ind-TDS-9.png)</span><span class="sxs-lookup"><span data-stu-id="42eb1-111">[![Withholding tax components page](./media/apac-ind-TDS-9.png)](./media/apac-ind-TDS-9.png)</span></span>

2. <span data-ttu-id="42eb1-112">Az **Adótípus** mezőben válassza ki a **TDS** lehetőséget a TDS adótípus adóelőleg-komponenseinek beállításához.</span><span class="sxs-lookup"><span data-stu-id="42eb1-112">In the **Tax type** field, select **TDS** to set up withholding tax components for the TDS tax type.</span></span>
3. <span data-ttu-id="42eb1-113">Jelölje be a műveleti ablakban az **Új** lehetőséget az új sor létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="42eb1-113">On the Action Pane, select **New** to create a line.</span></span>
4. <span data-ttu-id="42eb1-114">Az **Adóelőleg összetevő** mezőben adjon nevet a TDS összetevőnek.</span><span class="sxs-lookup"><span data-stu-id="42eb1-114">In the **Withholding tax component** field, enter a name for the TDS component.</span></span>
5. <span data-ttu-id="42eb1-115">Az **Adóelőleg-összetevő csoport** mezőben válassza ki azt a TDS-adóelőleg-összetevő csoportot, amelyhez a TDS összetevőt csatolja.</span><span class="sxs-lookup"><span data-stu-id="42eb1-115">In the **Withholding tax component group** field, select the TDS withholding tax component group to attach the TDS component to.</span></span>
6. <span data-ttu-id="42eb1-116">Az **Általános** gyorslapon a **Leírás** mezőben adja meg a TDS-összetevő leírását.</span><span class="sxs-lookup"><span data-stu-id="42eb1-116">On the **General** FastTab, in the **Description** field, enter a description of  the TDS component.</span></span>
7. <span data-ttu-id="42eb1-117">A műveletpanelen válassza ki a **Küszöbérték** lehetőséget a **Küszöbérték** oldal megnyitásához, hogy meghatározza azt a küszöbértéket, amely a TDS-összetevő TDS--ének számításához használatos.</span><span class="sxs-lookup"><span data-stu-id="42eb1-117">On the Action Pane, select **Threshold** to open **Threshold** page, so that you can define the threshold that is used to calculate TDS for the TDS component.</span></span>
8. <span data-ttu-id="42eb1-118">A **Kzedő dátum** és a **Befejező dátum** mezők segítségével határozza meg azt az időszakot, amelyre a küszöbérték vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="42eb1-118">Use the **From date** and **To date** fields to define the period that the threshold is applicable to.</span></span>
9. <span data-ttu-id="42eb1-119">Adja meg az **Általános** gyorslapon a **Küszöbérték** mezőben azt a küszöbérték-összeget, amely a TDS összetevő TDS-ének számításához használatos.</span><span class="sxs-lookup"><span data-stu-id="42eb1-119">On the **General** FastTab, in the **Threshold** field, enter the threshold amount that is used to calculate TDS for the TDS component.</span></span> <span data-ttu-id="42eb1-120">Az adó levonása csak akkor történik meg a forrásnál, ha a számla halmozott összege túllépi a küszöbértéket.</span><span class="sxs-lookup"><span data-stu-id="42eb1-120">The tax will be deducted at the source only when the cumulative invoice amount crosses the threshold.</span></span>

    <span data-ttu-id="42eb1-121">Ha például a küszöbérték összege 10 000, akkor a TDS számítása az összesített számlaösszeg után történik, amely meghaladja a 10 000-et (tehát10 001 vagy több).</span><span class="sxs-lookup"><span data-stu-id="42eb1-121">For example, if the threshold amount is 10,000, TDS is calculated after the cumulative invoice amount exceeds 10,000 (in other words, when it's 10,001 or more).</span></span>

10. <span data-ttu-id="42eb1-122">A **Kivételi Küszöbérték** mezőben azt a kivételi küszöbérték-összeget adja meg, amely a TDS összetevő TDS-ének számításához használatos.</span><span class="sxs-lookup"><span data-stu-id="42eb1-122">In the **Exception threshold** field, enter the exception threshold amount that is used to calculate TDS for the TDS component.</span></span> <span data-ttu-id="42eb1-123">A számlasor adójának levonása csak akkor történik meg a forrásnál, ha a számla halmozott összege túllépi a kivételi küszöbértéket.</span><span class="sxs-lookup"><span data-stu-id="42eb1-123">The tax on an invoice line will be deducted at the source only when the amount crosses the exception threshold.</span></span>

    <span data-ttu-id="42eb1-124">Ha például a kivétel küszöbérték összege 5000, akkor a TDS számítása egy adott számlasor alapján történik, ha a számlasor összege meghaladja az 5000-et (vagyis, ha 5001 vagy több).</span><span class="sxs-lookup"><span data-stu-id="42eb1-124">For example, if the exception threshold amount is 5,000, TDS is calculated on a specific invoice line if the invoice line amount exceeds 5,000 (in other words, if it's 5,001 or more).</span></span>

    <span data-ttu-id="42eb1-125">[![Küszöbérték oldal](./media/apac-ind-TDS-10.png)](./media/apac-ind-TDS-10.png)</span><span class="sxs-lookup"><span data-stu-id="42eb1-125">[![Threshold page](./media/apac-ind-TDS-10.png)](./media/apac-ind-TDS-10.png)</span></span>

    > [!NOTE]
    > <span data-ttu-id="42eb1-126">A kivételi küszöbérték összegének kisebbnek vagy egyenlőnek kell lennie a küszöbérték összegével.</span><span class="sxs-lookup"><span data-stu-id="42eb1-126">The exception threshold amount must be less than or equal to the threshold amount.</span></span>
    >
    > <span data-ttu-id="42eb1-127">A rendszer akkor is levonja a tranzakció adóját, ha a tranzakció összege túllépi a kivételi küszöbértéket, még akkor is, ha a számla halmozott összege nem lépi túl a **Küszöbérték** mezőben megadott küszöbértéket.</span><span class="sxs-lookup"><span data-stu-id="42eb1-127">The tax is deducted for a transaction if the transaction amount crosses the exception threshold, even if the cumulative invoice amount doesn't cross the threshold that is specified in the **Threshold** field.</span></span>

11. <span data-ttu-id="42eb1-128">A **Küszöbérték** lap bezárásával térjen vissza **Adóelőleg-összetevők** lapra.</span><span class="sxs-lookup"><span data-stu-id="42eb1-128">Close the **Threshold** page to return to the **Withholding tax components** page.</span></span>
12. <span data-ttu-id="42eb1-129">A Műveleti panelen a **Másolás** gombra kattintva nyissa meg az **Adóelőleg-összetevők másolása** párbeszédpanelt, hogy átmásolhassa az egyik TDS-összetevő csoporthoz beállított TDS-összetevőket egy másik TDS-összetevő csoportba.</span><span class="sxs-lookup"><span data-stu-id="42eb1-129">On the Action Pane, select **Copy** to open the **Copy withholding tax components** dialog box, so that you can copy the TDS components that were set up for one TDS component group to another TDS component group.</span></span>
13. <span data-ttu-id="42eb1-130">A **Forrás** mezőben válassza ki azt a TDS-összetevő csoportot, amelyből másolni kell a TDS-összetevőket.</span><span class="sxs-lookup"><span data-stu-id="42eb1-130">In the **From** field, select the TDS component group to copy the TDS components from.</span></span> <span data-ttu-id="42eb1-131">A **Cél** mezőben válassza ki az adóelőleg összetevő csoportot, amelybe másolni kell a TDS-összetevőket.</span><span class="sxs-lookup"><span data-stu-id="42eb1-131">In the **To** field, select the withholding tax component group to copy the TDS components to.</span></span>

    > [!NOTE]
    > <span data-ttu-id="42eb1-132">A TDS-összetevőcsoportokhoz csatolt általános TDS-összetevők másolása nem történt meg.</span><span class="sxs-lookup"><span data-stu-id="42eb1-132">Common TDS components that are attached to both TDS component groups aren't copied.</span></span>

14. <span data-ttu-id="42eb1-133">Ha az **Adóelőleg-összetevők** lapon válassza az **OK lehetőséget a TDS-összetevők másolásához a másik TDS-összetevő csoportra az Adóelőleg-összetevők** oldalon.</span><span class="sxs-lookup"><span data-stu-id="42eb1-133">Select **OK** to copy and create TDS components for the other TDS component group on the **Withholding tax components** page.</span></span>

    <span data-ttu-id="42eb1-134">[![Adóelőleg-összetevők másolása párbeszédpanel](./media/apac-ind-TDS-11.png)](./media/apac-ind-TDS-11.png)</span><span class="sxs-lookup"><span data-stu-id="42eb1-134">[![Copy withholding tax components dialog box](./media/apac-ind-TDS-11.png)](./media/apac-ind-TDS-11.png)</span></span>

15. <span data-ttu-id="42eb1-135">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="42eb1-135">Close the page.</span></span>
