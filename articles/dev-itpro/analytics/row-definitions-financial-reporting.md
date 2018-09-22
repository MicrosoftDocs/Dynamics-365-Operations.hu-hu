---
title: "Sordefiníciók a pénzügyi jelentéstervezőben"
description: "Egy sordefiníció egy jelentés-összetevő vagy építőelem, amely megadja az egyes sorok tartalmait egy pénzügyi jelentésben. A sordefiníciók kombinálhatóak oszlop,- jelentési fa- és jelentési definíciókkal, építőelem-csoportok létrehozásához, amelyek több vállalat által használhatóak."
author: aprilolson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 68873
ms.assetid: 2fd7b5da-700f-48cb-9003-90c0d82f818f
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 821d8927211d7ac3e479848c7e7bef9f650d4340
ms.openlocfilehash: c829af1da1b3109f4687c9a2536dd156339d5c76
ms.contentlocale: hu-hu
ms.lasthandoff: 08/13/2018

---

# <a name="row-definitions-in-financial-report-designer"></a><span data-ttu-id="6ccc6-104">Sordefiníciók a pénzügyi jelentéstervezőben</span><span class="sxs-lookup"><span data-stu-id="6ccc6-104">Row definitions in financial report designer</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6ccc6-105">Egy sordefiníció egy jelentés-összetevő vagy építőelem, amely megadja az egyes sorok tartalmait egy pénzügyi jelentésben.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-105">A row definition is a report component, or building block, that specifies the contents of each row on a financial report.</span></span> <span data-ttu-id="6ccc6-106">A sordefiníciók kombinálhatóak oszlop,- jelentési fa- és jelentési definíciókkal, építőelem-csoportok létrehozásához, amelyek több vállalat által használhatóak.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-106">A row definition can be combined with column definitions, reporting tree definitions, and report definitions to create a building block group that can be used by multiple companies.</span></span>

## <a name="create-a-row-definition"></a><span data-ttu-id="6ccc6-107">Sordefiníció létrehozása</span><span class="sxs-lookup"><span data-stu-id="6ccc6-107">Create a row definition</span></span>

1. <span data-ttu-id="6ccc6-108">A Jelentéstervezőben kattintson a navigációs panelen található **Sordefiníciók** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-108">In Report Designer, in the navigation pane, click **Row Definitions**.</span></span>
2. <span data-ttu-id="6ccc6-109">A **Fájl** menüben kattintson az **Új** elemre, majd a **Sordefiníciók** pontra.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-109">On the **File** menu, click **New**, and then click **Row Definition**.</span></span> <span data-ttu-id="6ccc6-110">Az egyes cellák tartalmával kapcsolatos további tudnivalókat lásd: [Sordefiníció cellák módosítása](modify-row-definition-cells-financial-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="6ccc6-110">For more information about the content of each cell, see [Modify row definition cells](modify-row-definition-cells-financial-reporting.md).</span></span>

## <a name="open-a-row-definition"></a><span data-ttu-id="6ccc6-111">Sordefiníció megnyitása</span><span class="sxs-lookup"><span data-stu-id="6ccc6-111">Open a row definition</span></span>
1. <span data-ttu-id="6ccc6-112">A Jelentéstervezőben kattintson a navigációs panelen található **Sordefiníciók** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-112">In Report Designer, in the navigation pane, click **Row Definitions**.</span></span>
2. <span data-ttu-id="6ccc6-113">Kattintson duplán a sordefiníció nevére, hogy megnyissa.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-113">Double-click the name of the row definition to open.</span></span>
3. <span data-ttu-id="6ccc6-114">A sordefinícióhoz társított bármely építőelem megtekintéséhez kattintson a jobb gombbal a sordefinícióra, és válassza ki a **Társítások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-114">To view any building blocks that are associated with the row definition, right-click the row definition, and then select **Associations**.</span></span>

## <a name="contents-of-a-row-definition"></a><span data-ttu-id="6ccc6-115"> Sordefiníció tartalma</span><span class="sxs-lookup"><span data-stu-id="6ccc6-115">Contents of a row definition</span></span>
<span data-ttu-id="6ccc6-116">Egy sordefiníció legfeljebb 20 000 pénzügyidimenzió-sort és a következő információkat tartalmazhatja:</span><span class="sxs-lookup"><span data-stu-id="6ccc6-116">A row definition can contain up to 20,000 financial dimension rows and can include the following information:</span></span>

- <span data-ttu-id="6ccc6-117">Leíró szöveget, amely értelmet ad a jelentésnek szakaszcímek, sorok és terek létrehozásával, például **Készpénz** vagy **Teljes bevétel**</span><span class="sxs-lookup"><span data-stu-id="6ccc6-117">Descriptive text that adds meaning to the report by creating section headings, lines, and spaces, such as **Cash** or **Total Revenue**</span></span>
- <span data-ttu-id="6ccc6-118">Pénzügyi adatokra mutató hivatkozásokat, amelyek tartalmazhatnak a Microsoft Dynamics 365 for Finance and Operations alkalmazásban szereplő dimenzióértékeket</span><span class="sxs-lookup"><span data-stu-id="6ccc6-118">Links to financial data, which can include dimension values in the Microsoft Dynamics 365 for Finance and Operations</span></span>

    > [!NOTE]
    > <span data-ttu-id="6ccc6-119">A sordefiníciót beállíthatja úgy, hogy minden alkalommal lekérje az adatokat a pénzügyi dimenziók rendszeréből, amikor a jelentést elkészítik.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-119">You can set up a row definition to pull data from the financial dimensions system every time that the report is generated.</span></span>

- <span data-ttu-id="6ccc6-120">Sorösszegeket és képleteket, amik a hivatkozott pénzügyi adatokon alapulnak.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-120">Row totals and formulas that are based on the linked financial data</span></span>

<span data-ttu-id="6ccc6-121">Általában minden sordefiníció tartalmaz egyet a következő információtípusok közül:</span><span class="sxs-lookup"><span data-stu-id="6ccc6-121">Usually, each row in a row definition contains one of the following types of information:</span></span>

- <span data-ttu-id="6ccc6-122">Hivatkozásokat a pénzügyi dimenziók rendszerére</span><span class="sxs-lookup"><span data-stu-id="6ccc6-122">References to the financial dimensions system</span></span>
- <span data-ttu-id="6ccc6-123">Összegeket vagy számításokat az adatok alapján</span><span class="sxs-lookup"><span data-stu-id="6ccc6-123">Totals or calculations that are based on the data</span></span>
- <span data-ttu-id="6ccc6-124">Formázás</span><span class="sxs-lookup"><span data-stu-id="6ccc6-124">Formatting</span></span>

<span data-ttu-id="6ccc6-125">A sordefiníció információk megadására két módja van:</span><span class="sxs-lookup"><span data-stu-id="6ccc6-125">There are two methods for entering information in a row definition:</span></span>

- <span data-ttu-id="6ccc6-126">A sorinformáció megadása manuálisan, egy új sordefinícióba.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-126">Manually enter row information in a new row definition.</span></span> <span data-ttu-id="6ccc6-127">További tudnivalókért lásd: [Sordefiníció cellák módosítása](modify-row-definition-cells-financial-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="6ccc6-127">For more information, see [Modify row definition cells](modify-row-definition-cells-financial-reporting.md).</span></span>
- <span data-ttu-id="6ccc6-128">Használja a jelentéstervezőt, hogy közvetlenül kinyerje a sorinformációkat a pénzügyi dimenziókból.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-128">Use report designer to pull row information directly from the financial dimensions.</span></span> <span data-ttu-id="6ccc6-129">További információért lásd a „Kapcsolódó képletek/sorok/egységek" részt a [Sordefiniáló cellák módosítása](modify-row-definition-cells-financial-reporting.md) fejezetben.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-129">For more information, see the "Related formulas/rows/units" section in [Modify row definition cells](modify-row-definition-cells-financial-reporting.md).</span></span>

## <a name="add-dimensions-in-a-row-definition"></a><span data-ttu-id="6ccc6-130"> Dimenziók hozzáadása egy sordefinícióhoz</span><span class="sxs-lookup"><span data-stu-id="6ccc6-130">Add dimensions in a row definition</span></span>
<span data-ttu-id="6ccc6-131">Egy dimenzió az adatok és értékek egy metszete.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-131">A dimension is an intersection of data and values.</span></span> <span data-ttu-id="6ccc6-132">Adat- és jelentéstervező értékeket csoportosíthat a jelentéstervezőben.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-132">You can group data and values in report designer.</span></span> <span data-ttu-id="6ccc6-133">Ezután részletesebben osztályozhatja és elemezheti a tranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-133">You can then classify and analyze transactions in more detail.</span></span> <span data-ttu-id="6ccc6-134">Használhatja a **Sorok beszúrása dimenziókból** párbeszédpanelt, hogy egy időben több sort adjon hozzá egy sordefinícióhoz.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-134">You can use the **Insert Rows from Dimensions** dialog box to add multiple rows to a row definition at the same time.</span></span> <span data-ttu-id="6ccc6-135">A párbeszédpanel minden dimenzióhoz egy oszlopot jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-135">The dialog box displays one column for each dimension.</span></span> <span data-ttu-id="6ccc6-136">A következő táblázat tartalmazza az egyes dimenziókhoz megadható információk leírását.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-136">The following table describes the information that you can specify for each dimension.</span></span>

| <span data-ttu-id="6ccc6-137">Lehetőség</span><span class="sxs-lookup"><span data-stu-id="6ccc6-137">Option</span></span>                | <span data-ttu-id="6ccc6-138">Leírás</span><span class="sxs-lookup"><span data-stu-id="6ccc6-138">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="6ccc6-139">Dimenzió</span><span class="sxs-lookup"><span data-stu-id="6ccc6-139">Dimension</span></span>             | <span data-ttu-id="6ccc6-140">A szabály, amely azonosítja a sordimenzióhoz adandó dimenziót.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-140">The pattern that identifies the dimension to add to the row definition.</span></span> <span data-ttu-id="6ccc6-141">Ez a szabály tartalmaz egy és-jelet (&), vagy egy kettős kereszt jelet (\#), minden pozícióhoz a dimenziókban.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-141">This pattern contains one ampersand (&) or number sign (\#) for each position in the dimensions.</span></span> <span data-ttu-id="6ccc6-142">Általában használjon kizárólag jeleket a Fő számlához és kizárólag számokat a többi dimenzióhoz.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-142">Generally, use all ampersands for the Main Account dimension and all number signs for other dimensions.</span></span> |
| <span data-ttu-id="6ccc6-143">Dimenziótartomány kezdete</span><span class="sxs-lookup"><span data-stu-id="6ccc6-143">Dimension Range Start</span></span> | <span data-ttu-id="6ccc6-144">A sordefinícióhoz hozzáadni kívánt dimenzió első értéke.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-144">The first value for this dimension to add to the row definition.</span></span> |
| <span data-ttu-id="6ccc6-145">Dimenziótartomány vége</span><span class="sxs-lookup"><span data-stu-id="6ccc6-145">Dimension Range End</span></span>   | <span data-ttu-id="6ccc6-146">Az utolsó érték, amely ebből a dimenzióból a sordefinícióhoz adandó.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-146">The last value for this dimension to add to the row definition.</span></span> |

<span data-ttu-id="6ccc6-147">Dimenziók hozzáadásához a sordefiníciókhoz végezze el a következő lépéseket.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-147">To add dimensions to a row definition, follow these steps.</span></span>

1. <span data-ttu-id="6ccc6-148">A Jelentéstervezőben kattintson a **Sordefiníciók** lehetőségre, majd nyissa meg a sordefiníciót, hogy módosítsa.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-148">In Report Designer, click **Row Definitions**, and then open the row definition to modify.</span></span>
2. <span data-ttu-id="6ccc6-149">A **Szerkesztés** menüben kattintson a **Sorok beszúrása dimenziókból** elemre.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-149">On the **Edit** menu, click **Insert Rows from Dimensions**.</span></span>
3. <span data-ttu-id="6ccc6-150">A **Sorok beszúrása dimenziókból** párbeszédpanelen a **Dimenziók** sorban, jelölje ki a dimenzióból a sordefinícióba átvinni kívánt cellát, majd kattintson az **Összes &&&** elemre.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-150">In the **Insert Rows from Dimensions** dialog box, in the **Dimensions** row, select the cell for the dimension to transfer to the row definition, and then click **All &&&**.</span></span>
4. <span data-ttu-id="6ccc6-151">Hogy korlátozza a sordefiníciót a dimenzióértékek egy adott tartományára, adja meg a kezdő dimenzióértéket a **Dimenziótartomány kezdete** cellában, majd adja meg a záró dimenzióértéket a **Dimenziótartomány vége** cellában.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-151">To limit the row definition to a specific range of dimension values, enter the starting dimension value in the **Dimension Range Start** cell, and then enter the ending dimension value in the **Dimension Range End** cell.</span></span> <span data-ttu-id="6ccc6-152">Ha az összes értéket szerepeltetni kívánja a kiválasztott dimenzió esetén, hagyja üresen ezeket a cellákat.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-152">To include all values for the selected dimension, leave these cells empty.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6ccc6-153">Az ERP-adatbázis adatleválogatási módszerétől függően előfordulhat, hogy a helyettesítő karakterek (\* vagy ?) a dimenziótartományokban nem adják vissza az összes kívánt eredményt.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-153">Wildcard characters (\* or ?) in dimension ranges might not return all the results that you want, depending on how the ERP database collates data.</span></span>

5. <span data-ttu-id="6ccc6-154">Adjon meg egy értéket a **Kezdő sorkód** mezőben, hogy megadja a sordefinícióhoz adandó, első dimenzióértékhez tartozó sorkódot.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-154">In the **Starting row code** field, specify the row code for the first dimension value to add to the row definition.</span></span>
6. <span data-ttu-id="6ccc6-155">Adjon meg egy értéket a **Sorok növekménye** mezőben, hogy megadja az egymást követő sorkódok közötti rést.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-155">In the **Increment each row by** field, specify the gap between consecutive row codes.</span></span> <span data-ttu-id="6ccc6-156">Például, ha az első sorkódot 100, és a növekményértéke 30, akkor az első új sorok kódjai rendre 100, 130, 160, 190 és 220. Használjon olyan növekményértéket, amely elég helyet biztosít új formátum és receptúra sorok beszúrásához.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-156">For example, if the first row code is 100, and the increment value is 30, the first new rows have the codes 100, 130, 160, 190, and 220.</span></span> <span data-ttu-id="6ccc6-157">Használjon olyan növekményértéket, amely elég helyet biztosít új formátum és receptúra sorok beszúrásához.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-157">Use an increment value that provides enough space to insert new format and formula rows.</span></span>
7. <span data-ttu-id="6ccc6-158">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-158">Click **OK**.</span></span> <span data-ttu-id="6ccc6-159">Minden kijelölt dimenzióérték után egy sor adódik a sordefinícióhoz.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-159">For each of the selected dimension values, one line is added to the row definition.</span></span>

## <a name="adjust-rounding-in-a-row-definition"></a><span data-ttu-id="6ccc6-160"> Kerekítés beállítása egy sordefinícióban</span><span class="sxs-lookup"><span data-stu-id="6ccc6-160">Adjust rounding in a row definition</span></span>
<span data-ttu-id="6ccc6-161">Egy olyan mérleg esetén, amelyben az összegek kerekítve vannak az összesítések eltérhetnek az egyensúlytól.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-161">If you have a balance sheet where the amounts are rounded, the totals might not balance.</span></span> <span data-ttu-id="6ccc6-162">Ez a probléma akkor fordulhat elő, ha például a kerekítési lehetőséget választja a mérlegkimutatáson, és a jelentésdefiníció is határoz meg kerekítést.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-162">This issue can occur if, for example, you use the rounding option on a balance sheet report and the report definition also specifies rounding.</span></span> <span data-ttu-id="6ccc6-163">Használhatja a **Kerekítés helyesbítés** lehetőséget a sordefinícióban, hogy kiegyenlítse a mérlegben szereplő összegeket.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-163">You can use the **Rounding adjustment** option in the row definition to balance the amounts in the balance sheets.</span></span> <span data-ttu-id="6ccc6-164">A kerekítést kikapcsolhatja vagy módosíthatja a jelentésdefiníció **Beállítások** lapján.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-164">You can turn rounding off or modify it on the **Settings** tab of the report definition.</span></span> <span data-ttu-id="6ccc6-165">A következő táblázat bemutatja az összegek kerekítését.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-165">The following table shows how amounts are rounded.</span></span> <span data-ttu-id="6ccc6-166">Ebben a táblázatban a 100-as és 200-as sorok összesítései eltérnek, ha a kerekítés be van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-166">In this table, the totals of rows 100 and 200 differ when rounding is turned on.</span></span>

| <span data-ttu-id="6ccc6-167">Sorkód</span><span class="sxs-lookup"><span data-stu-id="6ccc6-167">Row code</span></span> | <span data-ttu-id="6ccc6-168">Összegek kerekítés nélkül</span><span class="sxs-lookup"><span data-stu-id="6ccc6-168">Amounts without rounding</span></span> | <span data-ttu-id="6ccc6-169">Összeg teljes ezrekre kerekítéssel</span><span class="sxs-lookup"><span data-stu-id="6ccc6-169">Amount with rounding to whole thousands</span></span> |
|----------|--------------------------|-----------------------------------------|
| <span data-ttu-id="6ccc6-170">100</span><span class="sxs-lookup"><span data-stu-id="6ccc6-170">100</span></span>      | <span data-ttu-id="6ccc6-171">3600</span><span class="sxs-lookup"><span data-stu-id="6ccc6-171">3,600</span></span>                    | <span data-ttu-id="6ccc6-172">4</span><span class="sxs-lookup"><span data-stu-id="6ccc6-172">4</span></span>                                       |
| <span data-ttu-id="6ccc6-173">200</span><span class="sxs-lookup"><span data-stu-id="6ccc6-173">200</span></span>      | <span data-ttu-id="6ccc6-174">3700</span><span class="sxs-lookup"><span data-stu-id="6ccc6-174">3,700</span></span>                    | <span data-ttu-id="6ccc6-175">4</span><span class="sxs-lookup"><span data-stu-id="6ccc6-175">4</span></span>                                       |
| <span data-ttu-id="6ccc6-176">Összesen</span><span class="sxs-lookup"><span data-stu-id="6ccc6-176">Total</span></span>    | <span data-ttu-id="6ccc6-177">7300</span><span class="sxs-lookup"><span data-stu-id="6ccc6-177">7,300</span></span>                    | <span data-ttu-id="6ccc6-178">8</span><span class="sxs-lookup"><span data-stu-id="6ccc6-178">8</span></span>                                       |

<span data-ttu-id="6ccc6-179">Hogy beállítsa a kerekítést egy mérlegben, kövesse a következő lépéseket.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-179">To adjust rounding in a balance sheet, follow these steps.</span></span>

1. <span data-ttu-id="6ccc6-180">A Jelentés Tervező eszközben, kattintson **Sor Definíciók**, majd nyissa meg a sor definíciót, hogy módosítsa.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-180">In Report Designer, click **Row Definitions**, and then open the row definition to modify.</span></span>
2. <span data-ttu-id="6ccc6-181">Válassza a **Szerkesztés** menü **Kerekítési kiigazítás** parancsát.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-181">On the **Edit** menu, click **Rounding Adjustment**.</span></span>
3. <span data-ttu-id="6ccc6-182">A **Kerekítési helyesbítés** párbeszédpanelen írja be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="6ccc6-182">In the **Rounding Adjustments** dialog box, enter the following values:</span></span>

    - <span data-ttu-id="6ccc6-183">**Sorkerekítési helyesbítés** – Az adott sorhoz tartozó sorkód helyesbítve lesz, hogy kiegyenlítse a mérleget.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-183">**Rounding adjustment row** – The row code for the row that should be adjusted to balance the balance sheet.</span></span>
    - <span data-ttu-id="6ccc6-184">**Összes eszköz sor** – A sorkód, amely ahhoz a sorhoz tartozik a mérlegben, amely tartalmazza az összes eszközt.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-184">**Total assets row** – The row code for the row in the balance sheet that contains the total assets.</span></span>
    - <span data-ttu-id="6ccc6-185">**Összes kötelezettség– és részvénysor** – A sorkód, amely ahhoz a sorhoz tartozik a mérlegben, amely tartalmazza az összes kötelezettséget és részvényt.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-185">**Total liabilities and equity row** – The row code for the row in the balance sheet that contains the total liabilities and equity.</span></span>
    - <span data-ttu-id="6ccc6-186">**Helyesbítési összeghatár** – egy pozitív egész szám, amely megadja az automatikus helyesbítések korlátját.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-186">**Adjustment amount limit** – A positive whole number that specifies the limit on automatic adjustments.</span></span> <span data-ttu-id="6ccc6-187">A rendszer ezt a összeget hasonlítja össze a tényleges kerekítési különbség abszolút értékével.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-187">This amount is compared with the absolute value of the actual rounding difference.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6ccc6-188">Ezeket a sorkódokat a pénzügyi adatokhoz kell kapcsolni.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-188">These row codes must be linked to your financial data.</span></span> <span data-ttu-id="6ccc6-189">Más megfogalmazásban: a sor **Kapcsolás a pénzügyi dimenziókhoz** cellájában szerepelnie kell egy dimenzióértéknek.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-189">In other words, the row must have a dimension value in its **Link to Financial Dimensions** cell.</span></span> <span data-ttu-id="6ccc6-190">Leírás (**DESC**), számított (**CALC**), vagy összesített (**TOT**) sorra **ne** hivatkozzon.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-190">Do **not** reference a description (**DESC**), calculated (**CALC**), or totaled (**TOT**) row.</span></span>

<span data-ttu-id="6ccc6-191">A mérlegben szereplő összegek most már kiegyenlítődnek, ha a kerekítés be van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-191">The amounts in your balance sheet will now balance evenly when rounding is turned on.</span></span>

> [!NOTE]
> <span data-ttu-id="6ccc6-192">A kerekítési korlátozás alkalmazása a jelentésdefinícióhoz megadott **Kerekítés pontossága** beállítás alapján történik.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-192">The adjustment limit is applied based on the **Rounding precision** option that is specified for the report definition.</span></span> <span data-ttu-id="6ccc6-193">Például, ha kijelöli, hogy ezrekre kerekíti a jelentését és beírja a **2** értéket a **Helyesbítési összeghatár** mezőbe, akkor egy figyelmeztető üzenetet kap, amikor a **Kerekítés helyesbítő sor** mezőben azonosításra került érték több mint 2000-rel növekszik, vagy nő.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-193">For example, if you round your report to thousands and enter **2** in the **Adjustment amount limit** field, you receive a warning message when the value in the **Rounding adjustment row** field increases or decreases by more than 2,000.</span></span>

## <a name="format-row-and-column-text"></a><span data-ttu-id="6ccc6-194">Sor– és oszlopszöveg formázása</span><span class="sxs-lookup"><span data-stu-id="6ccc6-194">Format row and column text</span></span>
<span data-ttu-id="6ccc6-195">Személyre szabhatja a jelentései megjelenését szövegtípusok változtatásával és szövegszerkesztéssel.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-195">You can customize the appearance of your reports by changing fonts and formatting text.</span></span> <span data-ttu-id="6ccc6-196">A következő bekezdések elmagyarázzák, hogyan szerkessze a sorok és oszlopok megjelenését a jelentésekben.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-196">The following sections explain how to format the appearance of rows and columns on reports.</span></span>

### <a name="manage-font-styles"></a><span data-ttu-id="6ccc6-197">Betűstílusok kezelése</span><span class="sxs-lookup"><span data-stu-id="6ccc6-197">Manage font styles</span></span>

<span data-ttu-id="6ccc6-198">Létrehozhat, és módosíthat betűtípusokat a jelentéséhez.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-198">You can create and modify font styles for your report.</span></span> <span data-ttu-id="6ccc6-199">Ezeket a stílusokat alkalmazhatja a dokumentumban, vagy a jelentés egy adott sorában vagy oszlopában.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-199">You can then apply those styles to the document, or to a specific row or column on a report.</span></span>

<table>
<tbody>
<tr>
<td><span data-ttu-id="6ccc6-200"><strong>Új betűstílus létrehozása</strong></span><span class="sxs-lookup"><span data-stu-id="6ccc6-200"><strong>Create a font style</strong></span></span></td>
<td>
<ol>
<li><span data-ttu-id="6ccc6-201">A jelentéstervezőben a <strong>Formátum</strong> menüben kattintson a <strong>Stílusok és formázás</strong> elemre.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-201">In Report Designer, on the <strong>Format</strong> menu, click <strong>Styles and Formatting</strong>.</span></span></li>
<li><span data-ttu-id="6ccc6-202">A <strong>Stílusok és formázás</strong> párbeszédpanelen kattintson az <strong>Új</strong> gombra, és írjon be egy egyedi nevet az új stílus számára.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-202">In the <strong>Styles and Formatting</strong> dialog box, click <strong>New</strong>, and then enter a unique name for the new style.</span></span></li>
<li><span data-ttu-id="6ccc6-203">Válassza ki a kívánt betűtípus-beállításokat, majd kattintson az <strong>OK</strong> gombra.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-203">Make your font selections, and then click <strong>OK</strong>.</span></span></li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="6ccc6-204"><strong>Betűstílus módosítása</strong></span><span class="sxs-lookup"><span data-stu-id="6ccc6-204"><strong>Modify a font style</strong></span></span></td>
<td>
<ol>
<li><span data-ttu-id="6ccc6-205">A jelentéstervezőben a <strong>Formátum</strong> menüben kattintson a <strong>Stílusok és formázás</strong> elemre.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-205">In Report Designer, on the <strong>Format</strong> menu, click <strong>Styles and Formatting</strong>.</span></span></li>
<li><span data-ttu-id="6ccc6-206">Válassza ki a módosítani kívánt stílust a <strong>Stílusok és formázás</strong> párbeszédpanelen, majd kattintson a <strong>Módosítás</strong> gombra.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-206">In the <strong>Styles and Formatting</strong> dialog box, select a style to modify, and then click <strong>Modify</strong>.</span></span></li>
<li><span data-ttu-id="6ccc6-207">Válassza ki a kívánt betűtípus-beállításokat, majd kattintson az <strong>OK</strong> gombra.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-207">Make your font selections, and then click <strong>OK</strong>.</span></span></li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="6ccc6-208"><strong>Új betűstílus alkalmazása</strong></span><span class="sxs-lookup"><span data-stu-id="6ccc6-208"><strong>Apply a font style</strong></span></span></td>
<td>
<ol>
<li><span data-ttu-id="6ccc6-209">A Jelentéstervezőben, egy definícióban vagy oszlopdefinícióban, vagy fejlécekben és láblécben jelöljön ki egy vagy több cellát.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-209">In Report Designer, in a definition or column definition, or in headers and footers, select one or more cells.</span></span></li>
<li><span data-ttu-id="6ccc6-210">Válasszon ki egy betűstílust az eszköztár <strong>Stílus</strong> listájáról.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-210">In the <strong>Style</strong> list on the toolbar, select a font style.</span></span></li>
</ol>
</td>
</tr>
</tbody>
</table>

### <a name="format-row-text"></a><span data-ttu-id="6ccc6-211">Sorszöveg formázása</span><span class="sxs-lookup"><span data-stu-id="6ccc6-211">Format row text</span></span>

<span data-ttu-id="6ccc6-212">A sordefinícióban meghatározott formázás felülír minden formázást, amely az oszlop- és jelentésdefinícióban van meghatározva.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-212">The formatting that is specified in the row definition overrides any formatting that is specified in the column definition and the report definition.</span></span> <span data-ttu-id="6ccc6-213">A Formázás eszköztár vezérlőelemei segítségével módosíthatja a szöveg formátumot.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-213">You can modify the text format by using the controls on the formatting toolbar.</span></span> <span data-ttu-id="6ccc6-214">Ezek a vezérlők szabványos Microsoft Windows vezérlők.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-214">These controls are standard Microsoft Windows controls.</span></span>

1. <span data-ttu-id="6ccc6-215">Nyissa meg a módosítandó sordefiníciót a jelentéstervezőben.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-215">In Report Designer, open the row definition to modify.</span></span>
2. <span data-ttu-id="6ccc6-216">Válassza ki a formázandó cellákat.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-216">Select the cells to format.</span></span> <span data-ttu-id="6ccc6-217">Több cella kijelöléséhez tartsa lenyomva a Ctrl gombot, amíg kijelöli a cellát.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-217">To select multiple cells, hold down the Ctrl key while you select the cell.</span></span>
3. <span data-ttu-id="6ccc6-218">Kattintson a formátum eszköztári gombjára, hogy alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-218">Click the toolbar button of the format to apply.</span></span> <span data-ttu-id="6ccc6-219">Például, egy sor behúzásához jelölje ki a sort, és kattintson a Behúzás növelése **Behúzás növelése** ![Behúzás növelése](https://i-technet.sec.s-msft.com/dynimg/IC679497.gif "Behúzás növelése") elemre az eszköztárban.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-219">For example, to indent a row, select the row, and then click **Increase Indent** ![Increase Indent](https://i-technet.sec.s-msft.com/dynimg/IC679497.gif "Increase Indent") on the toolbar.</span></span>

### <a name="adjust-columns-while-you-design-reports"></a><span data-ttu-id="6ccc6-220">Oszlopok beállítása a jelentések tervezése közben</span><span class="sxs-lookup"><span data-stu-id="6ccc6-220">Adjust columns while you design reports</span></span>

<span data-ttu-id="6ccc6-221">Hogy megkönnyítse azon oszlopok áttekintését, amelyeken a sordefinícióban dolgozik beállíthatja az oszlopszélességet és elrejtheti (minimalizálhatja) vagy megjelenítheti az oszlopokat a nézet oldalon.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-221">To make it easier to view the columns that you're working on in the row definition, you can adjust the width of a column, and can also hide (minimize) or show columns in the view pane.</span></span> <span data-ttu-id="6ccc6-222">A végrehajtott módosítások csak az oszlopok képernyőn való megjelenésére vannak hatással.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-222">The modifications that you make affect only the on-screen appearance of the columns.</span></span> <span data-ttu-id="6ccc6-223">Nincsenek hatással a jelentések oszlopformázásra.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-223">They don't affect the column formatting on reports.</span></span>

### <a name="change-the-width-of-a-column-in-the-view-pane"></a><span data-ttu-id="6ccc6-224">Oszlopszélesség megváltoztatása a nézet ablakban</span><span class="sxs-lookup"><span data-stu-id="6ccc6-224">Change the width of a column in the view pane</span></span>

1. <span data-ttu-id="6ccc6-225">Nyissa meg a módosítandó sordefiníciót a jelentéstervezőben.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-225">In Report Designer, open the row definition to modify.</span></span>
2. <span data-ttu-id="6ccc6-226">A **Formátum** menüben válassza ki az **Oszlopszélesség** elemet.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-226">On the **Format** menu, select **Column Width**.</span></span>
3. <span data-ttu-id="6ccc6-227">Az **Oszlopszélesség** párbeszédpanelen adjon meg egy értéket, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-227">In the **Column Width** dialog box, enter a value, and then click **OK**.</span></span> <span data-ttu-id="6ccc6-228">Másik lehetőségként elhúzhatja az oszlop fejléccellájának jobb határát, hogy megváltoztassa az oszlopszélességet.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-228">Alternatively, you can drag the right boundary of a column heading cell to change the width of the column.</span></span>

### <a name="hide-columns-in-the-view-pane"></a><span data-ttu-id="6ccc6-229">Oszlopok elrejtése a nézet ablakban</span><span class="sxs-lookup"><span data-stu-id="6ccc6-229">Hide columns in the view pane</span></span>

1. <span data-ttu-id="6ccc6-230">Nyissa meg a módosítandó sordefiníciót a jelentéstervezőben.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-230">In Report Designer, open the row definition to modify.</span></span>
2. <span data-ttu-id="6ccc6-231">Válassza ki azokat az oszlopokat, amelyeket kis méretűvé kíván tenni.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-231">Select the column or columns to minimize.</span></span>
3. <span data-ttu-id="6ccc6-232">Kattintson jobb gombbal, majd kattintson az **Elrejtés** gombra.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-232">Right-click, and then click **Hide**.</span></span>

### <a name="show-all-hidden-columns-in-the-view-pane"></a><span data-ttu-id="6ccc6-233">Minden rejtett oszlop megjelenítése a nézet ablakban</span><span class="sxs-lookup"><span data-stu-id="6ccc6-233">Show all hidden columns in the view pane</span></span>

1. <span data-ttu-id="6ccc6-234">Nyissa meg a módosítandó sordefiníciót a jelentéstervezőben.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-234">In Report Designer, open the row definition to modify.</span></span>
2. <span data-ttu-id="6ccc6-235">Kattintson jobb gombbal a megjelenítendő minimalizált oszlopra, majd kattintson a **Megjelenítés** elemre.</span><span class="sxs-lookup"><span data-stu-id="6ccc6-235">Right-click the minimized column to display, and then click **Unhide**.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="6ccc6-236">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="6ccc6-236">Additional resources</span></span>

[<span data-ttu-id="6ccc6-237">Pénzügyi jelentéskészítés</span><span class="sxs-lookup"><span data-stu-id="6ccc6-237">Financial reporting</span></span>](financial-reporting-intro.md)

