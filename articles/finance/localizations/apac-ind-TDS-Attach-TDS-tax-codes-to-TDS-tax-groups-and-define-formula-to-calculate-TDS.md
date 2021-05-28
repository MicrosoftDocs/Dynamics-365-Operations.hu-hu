---
title: TDS-adókódok csatolása a TDS-adócsoportokhoz, és a TDS kiszámításának képletének meghatározása
description: Ez a témakör elmagyarázza, hogyan lehet beállítani a levont adót a Forrás (TDS) adócsoportokban, és csatolni kell a TDS adókódokat a TDS adócsoportokhoz. A TDS-adócsoport TDS-ének kiszámításához meg kell határoznia a hozzá csatolt TDS-adókódok képletét.
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
ms.openlocfilehash: ec0d683153bd5ab731035159d32881fbdb352d70
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023307"
---
# <a name="attach-tds-tax-codes-to-tds-tax-groups-and-define-the-formula-for-calculating-tds"></a><span data-ttu-id="e39fd-104">TDS-adókódok csatolása a TDS-adócsoportokhoz, és a TDS kiszámításának képletének meghatározása</span><span class="sxs-lookup"><span data-stu-id="e39fd-104">Attach TDS tax codes to TDS tax groups and define the formula for calculating TDS</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e39fd-105">Ez a témakör elmagyarázza, hogyan lehet beállítani a levont adót a Forrás (TDS) adócsoportokban, és csatolni kell a TDS adókódokat a TDS adócsoportokhoz.</span><span class="sxs-lookup"><span data-stu-id="e39fd-105">This topic explains how to set up Tax Deducted at Source (TDS) tax groups and attach TDS tax codes to TDS tax groups.</span></span> <span data-ttu-id="e39fd-106">A TDS-adócsoport TDS-ének kiszámításához meg kell határoznia a hozzá csatolt TDS-adókódok képletét.</span><span class="sxs-lookup"><span data-stu-id="e39fd-106">To calculate TDS for a TDS tax group, you must define the formula for TDS tax codes that are attached to it.</span></span>

<span data-ttu-id="e39fd-107">Kövesse ezeket a lépéseket a TDS-adócsoport beállításához, csatolja hozzá a TDS-adókódokat, és határozza meg a TDS kiszámításának képletét.</span><span class="sxs-lookup"><span data-stu-id="e39fd-107">Follow these steps to set up a TDS tax group, attach TDS tax codes to it, and define the formula for calculating TDS.</span></span>

1. <span data-ttu-id="e39fd-108">Ugorjon az **Adó \> Közvetett adók \> Adóelőleg \> Adóelőlegcsoportok** elemre.</span><span class="sxs-lookup"><span data-stu-id="e39fd-108">Go to **Tax \> Indirect taxes \> Withholding tax \> Withholding tax groups**.</span></span>

    <span data-ttu-id="e39fd-109">[![Adóelőleg-csoportok oldal](./media/apac-ind-TDS-29.png)](./media/apac-ind-TDS-29.png)</span><span class="sxs-lookup"><span data-stu-id="e39fd-109">[![Withholding tax groups page](./media/apac-ind-TDS-29.png)](./media/apac-ind-TDS-29.png)</span></span>

2. <span data-ttu-id="e39fd-110">A Műveletablakban válassza az **Új** lehetőséget a TDS adóelőleg-csoportjának létrehozásához, és adja meg a szükséges adatokat.</span><span class="sxs-lookup"><span data-stu-id="e39fd-110">On the Action Pane, select **New** to create a withholding tax group for TDS, and enter the required details.</span></span>
3. <span data-ttu-id="e39fd-111">Az **Adó típusa** mezőben válassza ki a **TDS** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e39fd-111">In the **Tax type** field, select **TDS**.</span></span>
4. <span data-ttu-id="e39fd-112">A **Beállítás** gyorsfülön válassza a **Hozzáadás** lehetőséget egy új sor létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="e39fd-112">On the **Setup** FastTab, select **Add** to create a line.</span></span>
5. <span data-ttu-id="e39fd-113">Az **Adóelőlegkód** mezőben válassza ki a TDS-adócsoport TDS-adóelőlegkódját.</span><span class="sxs-lookup"><span data-stu-id="e39fd-113">In the **Withholding tax code** field, select the TDS tax code for the TDS tax group.</span></span> <span data-ttu-id="e39fd-114">Az **Adóelőlegnév** mező a TDS adókód nevét mutatja, az **Érték** mező pedig az értéket.</span><span class="sxs-lookup"><span data-stu-id="e39fd-114">The **Withholding tax name** field shows the name of the TDS tax code, and the **Value** field shows the value.</span></span>
6. <span data-ttu-id="e39fd-115">Ha figyelmen kívül szeretné hagyni a TDS-tranzakciók TDS-adókódjához csatolt TDS-adóösszetevőre meghatározott küszöbértéket és kivételküszöb-értéket, válassza a **Küszöbérték figyelmen kívül hagyása** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="e39fd-115">To ignore the threshold limit and exception threshold limit that are defined for the TDS tax component that is attached to the TDS tax code in TDS transactions, select the **Overlook threshold** check box.</span></span>
7. <span data-ttu-id="e39fd-116">Jelölje be a **Mentesít** jelölőnégyzetet, ha meg akarja előzni, hogy az adócsoport a tranzakciókban kiszámításra kerüljön.</span><span class="sxs-lookup"><span data-stu-id="e39fd-116">To prevent the tax group from being calculated in transactions, select the **Exempt** check box.</span></span>
8. <span data-ttu-id="e39fd-117">A Műveletablakban válassza a **Tervező** lehetőséget a képlettervező megnyitásához, így meghatározhatja a TDS-adócsoport TDS-kiszámításának képletét.</span><span class="sxs-lookup"><span data-stu-id="e39fd-117">On the Action Pane, select **Designer** to open the formula designer, so that you can define the formula for calculating TDS for the TDS tax group.</span></span> <span data-ttu-id="e39fd-118">A **Tervező** lapon az **Adók** fülön láthatók a TDS-adócsoporthoz kiválasztott TDS-adókódok.</span><span class="sxs-lookup"><span data-stu-id="e39fd-118">On the **Designer** page, the **Taxes** tab shows the TDS tax codes that have been selected for the TDS tax group.</span></span>

    <span data-ttu-id="e39fd-119">[![Tervező oldal](./media/apac-ind-TDS-30.png)](./media/apac-ind-TDS-30.png)</span><span class="sxs-lookup"><span data-stu-id="e39fd-119">[![Designer page](./media/apac-ind-TDS-30.png)](./media/apac-ind-TDS-30.png)</span></span>

9. <span data-ttu-id="e39fd-120">A **Számítás** fülön válassza az **Alt+N** lehetőséget egy sor létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="e39fd-120">On the **Calculation** tab, select **Alt+N** to create a line.</span></span> <span data-ttu-id="e39fd-121">Az **azonosítómező** a TDS-számítás automatikusan generált prioritásazonosítóját mutatja.</span><span class="sxs-lookup"><span data-stu-id="e39fd-121">The **ID** field shows the automatically generated priority ID for TDS calculation.</span></span>
10. <span data-ttu-id="e39fd-122">Az **Adókód** mezőben válassza ki a TDS-adókódját a képlet meghatározásához.</span><span class="sxs-lookup"><span data-stu-id="e39fd-122">In the **Tax code** field, select the TDS tax code to define the formula for.</span></span> <span data-ttu-id="e39fd-123">A TDS-adócsoporthoz kiválasztott összes TDS-adókód választható ebben a mezőben.</span><span class="sxs-lookup"><span data-stu-id="e39fd-123">All the TDS tax codes that have been selected for the TDS tax group are available for selection in this field.</span></span>
11. <span data-ttu-id="e39fd-124">Az **Adóköteles összeg** mezőben válassza ki a TDS kiszámításának alapját:</span><span class="sxs-lookup"><span data-stu-id="e39fd-124">In the **Taxable basis** field, select the basis for calculating TDS:</span></span>

    - <span data-ttu-id="e39fd-125">**Bruttó összeg** – Számítsa ki a TDS-t a bruttó tranzakciós összeg (azaz a számla összege) alapján az adókódhoz definiált számítási kifejezéssel.</span><span class="sxs-lookup"><span data-stu-id="e39fd-125">**Gross amount** – Calculate TDS based on the gross transaction amount (that is, the invoice amount) by using the calculation expression that is defined for the tax code.</span></span>
    - <span data-ttu-id="e39fd-126">**Kiz. bruttó összeg** – Számítsa ki a TDS-t az adókódhoz definiált számítási kifejezés alapján.</span><span class="sxs-lookup"><span data-stu-id="e39fd-126">**Excl Gross amount** – Calculate TDS based on the calculation expression that is defined for the tax code.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e39fd-127">Az **Adóköteles összeg** mező nem állítható be prioritásazonosítóval rendelkező TDS adókód **Kiz. bruttó összegére** **1**.</span><span class="sxs-lookup"><span data-stu-id="e39fd-127">The **Taxable basis** field can't be set to **Excl Gross amount** for the TDS tax code that has a priority ID of **1**.</span></span>

12. <span data-ttu-id="e39fd-128">A TDS-számítás a TDS-adócsoporthoz csatolt minden egyes adókód **Számítási kifejezés** mezőjében meghatározott képleten alapul.</span><span class="sxs-lookup"><span data-stu-id="e39fd-128">The TDS calculation is based on the formula that is defined in the **Calculation expression** field for each tax code that is attached to the TDS tax group.</span></span> <span data-ttu-id="e39fd-129">Válassza ki a pluszjelet (**+**), a mínuszjel (**-**), a szorzásjel (**\**_), vagy az osztásjel (_*/**) gombot a kiválasztott TDS-adókód számítási kifejezésének megadásához a **Számítási kifejezés** mezőben.</span><span class="sxs-lookup"><span data-stu-id="e39fd-129">Select the plus sign (**+**), minus sign (**-**), multiplication sign (**\**_), or division sign (_*/**) button to enter the calculation expression for the selected TDS tax code in the **Calculation expression** field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e39fd-130">Nem határozható meg számítási kifejezés az **1** prioritási azonosítóval rendelkező TDS-adókódhoz.</span><span class="sxs-lookup"><span data-stu-id="e39fd-130">No calculation expression can be defined for the TDS tax code that has a priority ID of **1**.</span></span>

13. <span data-ttu-id="e39fd-131">A **Számítási** kifejezés mezőben a TDS-adókód számítási kifejezésének meghatározásához adjon hozzá TDS-adókódokat, amelyek az **Adók** fülön érhetők el. A TDS-adókódok **Számítási kifejezés** mezőbe történő hozzáadásához az alábbi módszerek bármelyikét használhatja:</span><span class="sxs-lookup"><span data-stu-id="e39fd-131">To define the calculation expression for the TDS tax code in the **Calculation expression** field, add TDS tax codes that are available on the **Taxes** tab. To add TDS tax codes in the **Calculation expression** field, you can use any of the following methods:</span></span>

    - <span data-ttu-id="e39fd-132">Húzza a szükséges adókódot az **Adók** fülről a **Számítási kifejezés** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="e39fd-132">Drag the required tax code from the **Taxes** tab to the **Calculation expression** field.</span></span>
    - <span data-ttu-id="e39fd-133">Koppintson duplán (vagy kattintson duplán) a szükséges adókódra az **Adók** fülön.</span><span class="sxs-lookup"><span data-stu-id="e39fd-133">Double-tap (or double-click) the required tax code on the **Taxes** tab.</span></span>
    - <span data-ttu-id="e39fd-134">Válassza ki és tartsa lenyomva (vagy kattintson a jobb gombbal) a szükséges adókódot az **Adók** fülön, majd válassza az **Adókód hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e39fd-134">Select and hold (or right-click) the required tax code on the **Taxes** tab, and then select **Add tax code**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e39fd-135">Számítási kifejezés beszúrása minden TDS-adókód előtt.</span><span class="sxs-lookup"><span data-stu-id="e39fd-135">Insert a calculation expression before each TDS tax code.</span></span> <span data-ttu-id="e39fd-136">A számítási kifejezéshez hozzáadott TDS-adókódok zárójelben (\[...\]) jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="e39fd-136">The TDS tax codes that have been added to the calculation expression appear in brackets (\[...\]).</span></span>

14. <span data-ttu-id="e39fd-137">A **Számítási kifejezés** mezőben található adókódhoz definiált számítási kifejezés törléséhez válassza a **C** gombot.</span><span class="sxs-lookup"><span data-stu-id="e39fd-137">To clear the calculation expression that is defined for a tax code in the **Calculation expression** field, select the **C** button.</span></span>
15. <span data-ttu-id="e39fd-138">A **Számítás** fülön lévő rekord törléséhez válassza a **Törlés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e39fd-138">To delete a record on the **Calculation** tab, select **Delete**.</span></span>
16. <span data-ttu-id="e39fd-139">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="e39fd-139">Close the page.</span></span>
