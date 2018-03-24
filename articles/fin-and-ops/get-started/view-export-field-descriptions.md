---
title: "Mezőleírások megtekintése és exportálása"
description: "Ez a cikk leírja, hogy hogyan tekinthetőek a mezőleírások, illetve hogy hogyan exportálhatóak a leírások a Mezőleírások oldal segítségével."
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: FieldDescriptions
audience: Application User, Developer, IT Pro
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.custom: 11534
ms.assetid: e2795f51-a8a7-4c74-bdb9-b1be93bdd358
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 812db9f1d319e4d16f83700a7153a0a3b318963e
ms.openlocfilehash: cfe5126841905248d0ab04ed9a718098c11bbd22
ms.contentlocale: hu-hu
ms.lasthandoff: 03/23/2018

---

# <a name="view-and-export-field-descriptions"></a><span data-ttu-id="3bd15-103">Mezőleírások megtekintése és exportálása</span><span class="sxs-lookup"><span data-stu-id="3bd15-103">View and export field descriptions</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="3bd15-104">Ez a cikk leírja, hogy hogyan tekinthetőek a mezőleírások, illetve hogy hogyan exportálhatóak a leírások a Mezőleírások oldal segítségével.</span><span class="sxs-lookup"><span data-stu-id="3bd15-104">This article describes how to view field descriptions and how to use the Field descriptions page to export descriptions.</span></span>

<span data-ttu-id="3bd15-105">A Microsoft Dynamics 365 for Finance and Operations rendszer tartalmazza néhány bonyolultabb mező leírását.</span><span class="sxs-lookup"><span data-stu-id="3bd15-105">Microsoft Dynamics 365 for Finance and Operations has descriptions for some of the more complex fields.</span></span> <span data-ttu-id="3bd15-106">Ezek a leírások akkor jelennek meg, ha az adott mező fölé húzza az egérmutatót.</span><span class="sxs-lookup"><span data-stu-id="3bd15-106">These descriptions appear when you hover over a field.</span></span> <span data-ttu-id="3bd15-107">Ezenkívül a **Mezőleírások** oldalon megtekintheti és exportálhatja a leírásokat.</span><span class="sxs-lookup"><span data-stu-id="3bd15-107">You can also view and export descriptions on the **Field descriptions** page.</span></span> 

<span data-ttu-id="3bd15-108">Nem minden lap rendelkezik mezőleírásokkal.</span><span class="sxs-lookup"><span data-stu-id="3bd15-108">Not all pages have field descriptions.</span></span> <span data-ttu-id="3bd15-109">Csak az összetettebb mezőkhöz kívánunk leírásokat nyújtani, azokhoz nem, amelyek használata nyilvánvaló.</span><span class="sxs-lookup"><span data-stu-id="3bd15-109">We want to provide descriptions only for the more complex fields, not where the use of the field is obvious.</span></span> <span data-ttu-id="3bd15-110">Ezért néhány oldalon egyáltalán nem található mezőleírás, egyes oldalakon csak néhány leírás jelenik meg, néhány összetettebb oldalon (ilyen például a legtöbb paraméteroldal) pedig sok leírás érhető el.</span><span class="sxs-lookup"><span data-stu-id="3bd15-110">Therefore, some pages don't have any field descriptions, some pages have a few descriptions, and some of the more complex pages, such as many of the parameters pages, have many descriptions.</span></span> 

<span data-ttu-id="3bd15-111">Amennyiben ön hozzáfér a Finance and Operations rendszer fejlesztői környezetéhez, új mezőleírásokat adhat meg, illetve módosíthatja a meglévő leírásokat.</span><span class="sxs-lookup"><span data-stu-id="3bd15-111">If you have access to the Finance and Operations development environment, you can add new field descriptions and customize existing descriptions.</span></span> <span data-ttu-id="3bd15-112">Például cégspecifikus információt tehet hozzá egy mezőleíráshoz.</span><span class="sxs-lookup"><span data-stu-id="3bd15-112">For example, you can add company-specific information to a field description.</span></span> <span data-ttu-id="3bd15-113">További tájékoztatást a [Mező testreszabása – súgó](../../dev-itpro/user-interface/customize-field-help.md) pontnál talál.</span><span class="sxs-lookup"><span data-stu-id="3bd15-113">For more information, see [Customize field help](../../dev-itpro/user-interface/customize-field-help.md).</span></span>

## <a name="see-field-descriptions-in-the-user-interface"></a><span data-ttu-id="3bd15-114">Mezőleírások megtekintése a felhasználói felületen</span><span class="sxs-lookup"><span data-stu-id="3bd15-114">See field descriptions in the user interface</span></span>
<span data-ttu-id="3bd15-115">A mezőleírásokat az egérmutató adott mező fölé navigálásával tekintheti meg.</span><span class="sxs-lookup"><span data-stu-id="3bd15-115">You can view field descriptions by hovering over a field.</span></span> <span data-ttu-id="3bd15-116">Ha nem tartozik leírás az adott mezőhöz, az egérmutató mező fölé vitelekor a mező neve jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="3bd15-116">If no description is available, you see the field name when you hover over the field.</span></span> <span data-ttu-id="3bd15-117">(Megjegyzés: a Dynamics AX 7.0 (2016. február) verzióban a mezők leírásai csak a **Mezőleírások** page.) Az alábbi ábrán az a mezőleírás látható, amely az egérmutató **Cikkek zárolása leltár közben** mező fölé vitelekor jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="3bd15-117">(Note: In Dynamics AX 7.0 (February 2016), field descriptions can be viewed only on the **Field descriptions** page.) The following illustration shows the field description that appears when you hover over the **Lock items during count** field.</span></span> 

<span data-ttu-id="3bd15-118">[![Példa egy mezőleírásra](./media/field-description.png)](./media/field-description.png)</span><span class="sxs-lookup"><span data-stu-id="3bd15-118">[![Example of a field description](./media/field-description.png)](./media/field-description.png)</span></span>

## <a name="use-the-field-descriptions-page-to-view-and-export-field-help"></a><span data-ttu-id="3bd15-119">A Mezőleírások oldal segítségével megtekintheti és exportálhatja a mezőkhöz tartozó súgót</span><span class="sxs-lookup"><span data-stu-id="3bd15-119">Use the Field descriptions page to view and export field help</span></span>
<span data-ttu-id="3bd15-120">A **Mezőleírások** oldal segítségével megtekintheti és exportálhatja a mezőleírásokat.</span><span class="sxs-lookup"><span data-stu-id="3bd15-120">The **Field descriptions** page lets you view and export field descriptions.</span></span> <span data-ttu-id="3bd15-121">Egyszerre csak egy lap leírásai tekinthetők meg.</span><span class="sxs-lookup"><span data-stu-id="3bd15-121">You can see the descriptions that are available for one page at a time.</span></span>

### <a name="view-the-descriptions-for-a-page"></a><span data-ttu-id="3bd15-122">Egy lap leírásainak megtekintése:</span><span class="sxs-lookup"><span data-stu-id="3bd15-122">View the descriptions for a page</span></span>

<span data-ttu-id="3bd15-123">Egy lap leírásainak megtekintéséhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="3bd15-123">To view the descriptions for a page, follow this step.</span></span>

-   <span data-ttu-id="3bd15-124">A **Lap kijelölése** mezőbe írja be a lap nevét.</span><span class="sxs-lookup"><span data-stu-id="3bd15-124">In the **Select a page** field, type the name of the page.</span></span> <span data-ttu-id="3bd15-125">Másik lehetőségként a nyílra kattintva nyissa meg az összes lapot tartalmazó listát; keresse ki a kívánt lapot, vagy szűrje a listát.</span><span class="sxs-lookup"><span data-stu-id="3bd15-125">Alternatively, click the arrow to open a list of all the pages, and then browse or filter the list.</span></span>

<span data-ttu-id="3bd15-126">Használhatja a felhasználói felületen megjelenő lapnevet (például: **Vevők**) vagy a lap kódnevét (AOT nevét), amely úgy érhető el, hogy jobb gombbal a lapra kattint (például: **CustTable**).</span><span class="sxs-lookup"><span data-stu-id="3bd15-126">You can use either the name of the page that is shown in the user interface (UI) (for example, **Customers**) or the code name (AOT name) that's available when you right-click a page (for example, **CustTable**).</span></span> 

<span data-ttu-id="3bd15-127">A lapok listájának különféle módon megvalósítható szűréséről bővebben a cikk „Lap keresése” szakaszában olvashat.</span><span class="sxs-lookup"><span data-stu-id="3bd15-127">For information about the various ways to filter the list of pages, see the "Searching for a page" section later in this article.</span></span> 

<span data-ttu-id="3bd15-128">Ha a **Leírás nélküli mezőkkel együtt** beállításnál az **Igen** lehetőséget választja, az oldalon minden mező megjelenik, függetlenül attól, hogy rendelkezik-e mezőleírással.</span><span class="sxs-lookup"><span data-stu-id="3bd15-128">If you set the **Include fields without a description** option to **Yes**, all the fields on the page are shown, even if they don't have a field description.</span></span>

### <a name="export-the-descriptions-for-a-page"></a><span data-ttu-id="3bd15-129">Egy lap leírásainak exportálása</span><span class="sxs-lookup"><span data-stu-id="3bd15-129">Export the descriptions for a page</span></span>

<span data-ttu-id="3bd15-130">Egy lap leírásainak exportálásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="3bd15-130">To export the descriptions for a page, follow these steps.</span></span>

1.  <span data-ttu-id="3bd15-131">Válasszon egy lapot a **Lap kijelölése** mezőben.</span><span class="sxs-lookup"><span data-stu-id="3bd15-131">In the **Select a page** field, select a page.</span></span>
2.  <span data-ttu-id="3bd15-132">Kattintson a jobb felső sarokban lévő **Megnyitás Microsoft Office programban** gombra, majd válassza a **FieldDescriptionTmp** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3bd15-132">Click the **Open in Microsoft Office** button in the upper-right corner, and then click **FieldDescriptionTmp**.</span></span>

### <a name="searching-for-a-page"></a><span data-ttu-id="3bd15-133">Egy lap keresése</span><span class="sxs-lookup"><span data-stu-id="3bd15-133">Searching for a page</span></span>

<span data-ttu-id="3bd15-134">Egy adott lap több módon is megkereshető a **Lap kijelölése** mezőben.</span><span class="sxs-lookup"><span data-stu-id="3bd15-134">There are several ways to search for a page in the **Select a page** field.</span></span> <span data-ttu-id="3bd15-135">Sok esetben a **Lap kijelölése** mezőben található nyílra kell kattintania a legördülő menü kinyitásához; ekkor egy szűrt laplistáról választhat.</span><span class="sxs-lookup"><span data-stu-id="3bd15-135">In many cases, you must click the arrow in the **Select a page** field to open the drop-down list, and then select from a filtered list of pages.</span></span>

-   <span data-ttu-id="3bd15-136">Írja be a név egy részét, majd a nyissa meg a legördülő listát, és válasszon a szűrt lapok listájából.</span><span class="sxs-lookup"><span data-stu-id="3bd15-136">Type part of the name, and then open the drop-down list to select from a filtered list of pages.</span></span>
-   <span data-ttu-id="3bd15-137">Nyissa meg a legördülő listát, majd kattintson a lista tetején lévő **Lapnév** fejlécre vagy a **Lap AOT-neve** fejlécre.</span><span class="sxs-lookup"><span data-stu-id="3bd15-137">Open the drop-down list, and then click either the **Page name** heading at the top of the list or the **Page AOT name** heading.</span></span> <span data-ttu-id="3bd15-138">Ekkor megjelenik egy párbeszédpanel, ahol speciális szűrési lehetőségeket használhat, például **A lapnév kezdete**.</span><span class="sxs-lookup"><span data-stu-id="3bd15-138">A dialog box appears, where you can use advanced filtering options, such as **Page name begins with**.</span></span>
-   <span data-ttu-id="3bd15-139">Írja be a lap teljes nevét.</span><span class="sxs-lookup"><span data-stu-id="3bd15-139">Type the full name of the page.</span></span> <span data-ttu-id="3bd15-140">Ha ezt a beállítást használja, célszerű megnyitni a legördülő listát, és megnézni, hogy mi szerepel még a listán, még akkor is, ha a mezőleírások megjelennek.</span><span class="sxs-lookup"><span data-stu-id="3bd15-140">When you use this option, it's best to open the drop-down list and see what else is in the list, even if field descriptions are shown.</span></span>
    -   <span data-ttu-id="3bd15-141">Ha egyetlen pontos egyezés található a névhez, akkor annak megfelelő lap mezőleírásai fognak megjelenni.</span><span class="sxs-lookup"><span data-stu-id="3bd15-141">If there is a single exact match to the name, the field descriptions for that page are shown.</span></span>
    -   <span data-ttu-id="3bd15-142">Ha egynél több pontos egyezés található, nem jelennek meg leírások.</span><span class="sxs-lookup"><span data-stu-id="3bd15-142">If there is more than one exact match, no descriptions are shown.</span></span> <span data-ttu-id="3bd15-143">Ez esetben nyissa meg a legördülő listát és jelölje ki a kívánt lapot.</span><span class="sxs-lookup"><span data-stu-id="3bd15-143">You must open the drop-down list and select the page that you want.</span></span>
    -   <span data-ttu-id="3bd15-144">A beírt névnek megfelelő lap leírásai jelennek meg akkor is, ha a beírt név egy másik lap nevének részét képezi.</span><span class="sxs-lookup"><span data-stu-id="3bd15-144">If the name that you typed is part of the name of another page, you see the descriptions for your page.</span></span> <span data-ttu-id="3bd15-145">Azonban ha megnyitja a legördülő listát, abban láthatóak lesznek az adott nevet tartalmazó lapok.</span><span class="sxs-lookup"><span data-stu-id="3bd15-145">However, if you open the drop-down list, you see additional pages that contain that name.</span></span>

<span data-ttu-id="3bd15-146">Például ha a **Leltár** kifejezést írja be a ****Lap kijelölése**** mezőbe, nem jelenik meg leírás.</span><span class="sxs-lookup"><span data-stu-id="3bd15-146">For example, no descriptions are shown when you type **Counting** in the ****Select a page**** field.</span></span> <span data-ttu-id="3bd15-147">Ha rákattint a legördülő listára, két **Leltár** nevű lapot fog látni, valamint több olyan lapot, amelynek nevében szerepel a „Leltár” szó.</span><span class="sxs-lookup"><span data-stu-id="3bd15-147">You open the drop-down list, and see that there are two pages that have the name **Counting** and several pages that contain the word "Counting" in the name.</span></span> <span data-ttu-id="3bd15-148">Ha az **InventJournalCount** AOT-névvel rendelkező lapot választja, akkor megjelennek az adott laphoz tartozó mezőleírások.</span><span class="sxs-lookup"><span data-stu-id="3bd15-148">If you select the page that has the AOT name **InventJournalCount**, the field descriptions are shown for that page.</span></span> <span data-ttu-id="3bd15-149">Azonban ha újra megnyitja a legördülő listát, látni fogja, hogy a lista most már tartalmaz minden olyan lapot, amelynél az AOT-lapnév része az „InventJournalCount”.</span><span class="sxs-lookup"><span data-stu-id="3bd15-149">However, if you open the drop-down list again, you will see that the list now contains all pages that have "InventJournalCount" as part of their AOT name.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="3bd15-150">Hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="3bd15-150">Troubleshooting</span></span>
<span data-ttu-id="3bd15-151">Ez a szakasz a mezőleírások használata során felmerülő lehetséges problémák elhárításához nyújt segítséget.</span><span class="sxs-lookup"><span data-stu-id="3bd15-151">This section provides information to help you troubleshoot issues that you might encounter when you use field descriptions.</span></span>

### <a name="i-cant-find-a-field-description"></a><span data-ttu-id="3bd15-152">Nem található mezőleírás</span><span class="sxs-lookup"><span data-stu-id="3bd15-152">I can't find a field description</span></span>

<span data-ttu-id="3bd15-153">Jelenleg zajlik az összetettebb mezők leírásának folyamata.</span><span class="sxs-lookup"><span data-stu-id="3bd15-153">We’re in the process of adding descriptions for the more complex fields.</span></span> <span data-ttu-id="3bd15-154">Ha segítségre van szüksége egy adott mezőhöz, kérjük tudassa velünk azzal, hogy hozzászól ehhez a témakörhöz.</span><span class="sxs-lookup"><span data-stu-id="3bd15-154">If you require help for a particular field, let us know by adding a comment for this topic.</span></span>

### <a name="the-field-description-isnt-helpful"></a><span data-ttu-id="3bd15-155">A mezőleírás nem ad segítséget</span><span class="sxs-lookup"><span data-stu-id="3bd15-155">The field description isn't helpful</span></span>

<span data-ttu-id="3bd15-156">Kérjük, tudassa ezt velünk azzal, hogy hozzászól ehhez a témakörhöz.</span><span class="sxs-lookup"><span data-stu-id="3bd15-156">Let us know by adding a comment for this topic.</span></span> <span data-ttu-id="3bd15-157">Ha lehetséges, írja le azokat a kiegészítő információkat, amelyekre szüksége van.</span><span class="sxs-lookup"><span data-stu-id="3bd15-157">If you can, describe the additional information that you require.</span></span>

### <a name="i-cant-find-a-field-on-the-field-descriptions-page"></a><span data-ttu-id="3bd15-158">Nem találok egy mezőt a Mezőleírások oldalon</span><span class="sxs-lookup"><span data-stu-id="3bd15-158">I can't find a field on the Field descriptions page</span></span>

<span data-ttu-id="3bd15-159">Az egy lapon lévő összes mező megjelenítéséhez, állítsa a **Tartalmazza a leírás nélküli mezőket** lehetőséget az **Igen** opcióra.</span><span class="sxs-lookup"><span data-stu-id="3bd15-159">To show all the fields on a page, set the **Include fields without a description** option to **Yes**.</span></span> <span data-ttu-id="3bd15-160">A **Lap kijelölése** mezőre való kattintással ellenőrizze, hogy a megfelelő lapot választotta-e ki.</span><span class="sxs-lookup"><span data-stu-id="3bd15-160">Click the **Select a page** field to verify that you've selected the correct page.</span></span> <span data-ttu-id="3bd15-161">Ha a beírt név egy másik lapnév része, előfordulhat, hogy a hosszabb nevű lapot választotta ki.</span><span class="sxs-lookup"><span data-stu-id="3bd15-161">If the name that you typed is part of another field name, you might have selected the page that has the longer name.</span></span>

### <a name="i-cant-find-a-page-on-the-field-descriptions-page"></a><span data-ttu-id="3bd15-162">Nem találok egy lapot a Mezőleírások oldalon</span><span class="sxs-lookup"><span data-stu-id="3bd15-162">I can't find a page on the Field descriptions page</span></span>

<span data-ttu-id="3bd15-163">A lapok különféle módon megvalósítható megkereséséről bővebben feljebb, a cikk „Lapok keresése” szakaszában olvashat.</span><span class="sxs-lookup"><span data-stu-id="3bd15-163">For information about the various way to find pages, see the "Searching for pages" section earlier in this article.</span></span> <span data-ttu-id="3bd15-164">Ha a lap pontos nevét írta be, a mezőleírások lehet, hogy azért nem jelennek meg, mert egynél több azonos nevű lap létezik.</span><span class="sxs-lookup"><span data-stu-id="3bd15-164">If you've typed the exact name of the page, the field descriptions might not be shown if more than one page has the same name.</span></span> <span data-ttu-id="3bd15-165">Kattintson a nyílra a **Lap kijelölése** mezőben az elérhető lapok szűrt listájának megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="3bd15-165">Click the arrow in the **Select a page** field to open a filtered list of the pages that are available.</span></span>

<a name="see-also"></a><span data-ttu-id="3bd15-166">Lásd még</span><span class="sxs-lookup"><span data-stu-id="3bd15-166">See also</span></span>
--------

[<span data-ttu-id="3bd15-167">Mező testreszabása – súgó</span><span class="sxs-lookup"><span data-stu-id="3bd15-167">Customize field help</span></span>](../../dev-itpro/user-interface/customize-field-help.md)





