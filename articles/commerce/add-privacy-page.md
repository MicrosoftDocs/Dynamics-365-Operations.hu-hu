---
title: Adatvédelmi irányelv oldalának hozzáadása
description: Ez a témakör azt mutatja be, hogyan lehet egy adatvédelmi irányelv oldalt hozzáadni a webhelyéhez a Microsoft Dynamics 365 Commerce alkalmazásban.
author: v-chgri
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 12cd0358279684ce1d3050348c37209ba3d29140
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797527"
---
# <a name="add-a-privacy-policy-page"></a><span data-ttu-id="67942-103">Adatvédelmi irányelv oldalának hozzáadása</span><span class="sxs-lookup"><span data-stu-id="67942-103">Add a privacy policy page</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="67942-104">Ez a témakör azt mutatja be, hogyan lehet egy adatvédelmi irányelv oldalt hozzáadni a webhelyéhez a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="67942-104">This topic describes how to add a privacy policy page to your site in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="67942-105">Az adatvédelmi előírásoknak való megfelelés olyan szervezeti intézkedéseket is tartalmaz, amelyek tájékoztatják a webhely felhasználóit az adatok gyűjtésének és kezelésének módjáról.</span><span class="sxs-lookup"><span data-stu-id="67942-105">Privacy compliance includes organizational measures that inform site users about how their data is collected and handled.</span></span> <span data-ttu-id="67942-106">A felhasználók ezután eldönthetik, hogyan kívánják személyes adataikat kezelni, és megfelelő lépéseket tehetnek.</span><span class="sxs-lookup"><span data-stu-id="67942-106">Users can then decide how they want their personal data to be handled and can take appropriate action.</span></span>

## <a name="review-the-microsoft-privacy-statement-in-dynamics-365-commerce"></a><span data-ttu-id="67942-107">A Microsoft adatvédelmi nyilatkozatának áttekintése a Dynamics 365 Commerce alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="67942-107">Review the Microsoft privacy statement in Dynamics 365 Commerce</span></span>

<span data-ttu-id="67942-108">Ha szeretné áttekinteni a Microsoft adatvédelmi nyilatkozatát, amikor be van jelentkezve a Dynamics 365 Commerce szerkesztőeszközökre, válassza a jobb felső sarokban található **Súgó** (**?**) gombot, majd válassza az **Adatvédelem és cookie-k** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="67942-108">To review the Microsoft privacy statement while you're signed in to the Dynamics 365 Commerce authoring tools, select the **Help** button (**?**) in the upper-right corner, and then select **Privacy and cookies**.</span></span> <span data-ttu-id="67942-109">Megnyílik egy új lap, amely hivatkozást tartalmaz a [Microsoft adatvédelmi nyilatkozatra](https://privacy.microsoft.com/privacystatement).</span><span class="sxs-lookup"><span data-stu-id="67942-109">A new tab is opened that has a link to the [Microsoft privacy statement](https://privacy.microsoft.com/privacystatement).</span></span>

## <a name="build-a-privacy-policy-page-for-your-site"></a><span data-ttu-id="67942-110">Adatvédelmi irányelv oldal összeállítása a webhelyéhez</span><span class="sxs-lookup"><span data-stu-id="67942-110">Build a privacy policy page for your site</span></span>

<span data-ttu-id="67942-111">A Dynamics 365 Commerce alkalmazásban többféle módon adhat hozzáférést a webhelye felhasználóinak az adatvédelmi irányelveihez.</span><span class="sxs-lookup"><span data-stu-id="67942-111">In Dynamics 365 Commerce, there are several ways to give users of your site access to your privacy policy.</span></span> <span data-ttu-id="67942-112">Ez a szakasz bemutatja, hogyan lehet egy adatvédelmi irányelv oldalt létrehozni, majd egy élőlábtöredék segítségével hivatkozni a lapra.</span><span class="sxs-lookup"><span data-stu-id="67942-112">This section shows how to build a privacy policy page and then reference the page by using a footer fragment.</span></span>

<span data-ttu-id="67942-113">Az alábbi útmutatás bemutatja, hogyan lehet egy Commerce-webhely általános adatvédelmi irányelv oldalát létrehozni.</span><span class="sxs-lookup"><span data-stu-id="67942-113">The guidance that follows is an example that shows how to build a generic privacy policy page for a Commerce site.</span></span> <span data-ttu-id="67942-114">Ön felelős az olyan adatvédelmi irányelv oldal tervezéséért és megvalósításáért, amely a legjobban megfelel vállalata jogi követelményeinek.</span><span class="sxs-lookup"><span data-stu-id="67942-114">You're responsible for designing and implementing a privacy policy page solution that best meets your company's legal requirements.</span></span>

<span data-ttu-id="67942-115">Kezdésként a szerkesztőeszközökben keresse meg azt a webhelyet, amelyhez fel kívánja építeni az adatvédelmi irányelv oldalát.</span><span class="sxs-lookup"><span data-stu-id="67942-115">To start, in the authoring tools, go to the site that you want to build a privacy policy page for.</span></span>

### <a name="create-a-template"></a><span data-ttu-id="67942-116">Sablon létrehozása</span><span class="sxs-lookup"><span data-stu-id="67942-116">Create a template</span></span>

> [!NOTE]
> <span data-ttu-id="67942-117">Ha már létrehoztak olyan sablont, ami használható az adatvédelmi irányelv oldal létrehozásához, ugorjon előre az [Adatvédelmi irányelv oldal összeállítása](#build-a-privacy-policy-page) szakaszra.</span><span class="sxs-lookup"><span data-stu-id="67942-117">If a template that can be used for the privacy policy page has already been created, skip ahead to the [Build a privacy policy page](#build-a-privacy-policy-page) section.</span></span>

<span data-ttu-id="67942-118">Sablon létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="67942-118">To create a template, follow these steps.</span></span>

1. <span data-ttu-id="67942-119">Lépjen a **Sablonok** pontra, majd oldalsablon készítéséhez válassza az **Új** elemet.</span><span class="sxs-lookup"><span data-stu-id="67942-119">Go to **Templates**, and then select **New** to create a page template.</span></span>
1. <span data-ttu-id="67942-120">Az **Új sablon** párbeszédablakban a **Sablon neve** alatt adja meg a **promóciós szalagcím sablon** elemet, majd válassza az **OK** gombot.</span><span class="sxs-lookup"><span data-stu-id="67942-120">In the **New Template** dialog box, under **Template Name**, enter **Promo banner template**, and then select **OK**.</span></span>
1. <span data-ttu-id="67942-121">A sablonban adja hozzá a szükséges modulokat a megfelelő oldalhelyekhez.</span><span class="sxs-lookup"><span data-stu-id="67942-121">In the template, add any required modules to the required page slots.</span></span> <span data-ttu-id="67942-122">Útmutatásért vigye az egérmutatót a piros felkiáltójelek fölé.</span><span class="sxs-lookup"><span data-stu-id="67942-122">For guidance, hover over the red exclamation marks.</span></span> <span data-ttu-id="67942-123">(A **HTML-fejléc** tárolóhelyen például szükség lehet az **Alapértelmezett külső parancsfájl** modulra.)</span><span class="sxs-lookup"><span data-stu-id="67942-123">(For example, the **HTML Head** slot might require a **Default External Script** module.)</span></span>
1. <span data-ttu-id="67942-124">Adja hozzá a **Törzs** tárolóhelyen az **Alapértelmezett lap** modult.</span><span class="sxs-lookup"><span data-stu-id="67942-124">In the **Body** slot, add a **Default Page** module.</span></span>
1. <span data-ttu-id="67942-125">Az **Alapértelmezett lap** modul **Fő** helyén adjon hozzá egy **Tartalomgazdag blokk** modult.</span><span class="sxs-lookup"><span data-stu-id="67942-125">In the **Default Page** module, in the **Main** slot, add a **Content Rich Block** module.</span></span>
1. <span data-ttu-id="67942-126">A **Tartalomgazdag blokk** modulban adja hozzá a **Tartalomgazdag blokkelem** modult.</span><span class="sxs-lookup"><span data-stu-id="67942-126">In the **Content Rich Block** module, add a **Content rich block item** module.</span></span>
1. <span data-ttu-id="67942-127">Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="67942-127">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

### <a name="build-a-privacy-policy-page"></a><span data-ttu-id="67942-128">Adatvédelmi irányelv oldalának összeállítása</span><span class="sxs-lookup"><span data-stu-id="67942-128">Build a privacy policy page</span></span>

<span data-ttu-id="67942-129">Az adatvédelmi irányelvek oldalának létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="67942-129">To build a privacy policy page, follow these steps.</span></span>

1. <span data-ttu-id="67942-130">Lépjen az **Oldalak** pontra, majd válassza az **Új** lehetőséget az oldal létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="67942-130">Go to **Pages**, and then select **New** to create a page.</span></span>
1. <span data-ttu-id="67942-131">A **Sablon kiválasztása** párbeszédablakban válassza ki az adatvédelmi irányelv oldalának sablonját.</span><span class="sxs-lookup"><span data-stu-id="67942-131">In the **Choose a template** dialog box, select the template for the privacy policy page.</span></span>
1. <span data-ttu-id="67942-132">Adja meg az oldal nevét és az oldal URL-t, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="67942-132">Enter a page name and page URL, and then select **OK**.</span></span> 
1. <span data-ttu-id="67942-133">Az új lap **Fő** helyén adjon hozzá egy **Tartalomgazdag blokk** modult.</span><span class="sxs-lookup"><span data-stu-id="67942-133">In the **Main** slot of the page, add a **Content Rich Block** module.</span></span>
1. <span data-ttu-id="67942-134">A **Tartalomgazdag blokk** modulban adja hozzá a **Tartalomgazdag blokkelem** modult.</span><span class="sxs-lookup"><span data-stu-id="67942-134">In the **Content Rich Block** module, add a **Content rich block item** module.</span></span>
1. <span data-ttu-id="67942-135">A **Tartalomgazdag blokk** modul tulajdonságpanelén válassza az **Adatforrás hozzáadása** parancsot, majd válassza a **Rich Text tartalom** menüpontot.</span><span class="sxs-lookup"><span data-stu-id="67942-135">In the properties pane for the **Content Rich Block** module, select **Add Data Source**, and then select **Rich Text Content**.</span></span>
1. <span data-ttu-id="67942-136">A rich text szerkesztőben adja meg az adatvédelmi irányelvek oldal tartalmát.</span><span class="sxs-lookup"><span data-stu-id="67942-136">In the rich text editor, enter the content for the privacy policy page.</span></span> <span data-ttu-id="67942-137">Szükség esetén bontsa ki a rich text szerkesztőt teljes képernyős módra.</span><span class="sxs-lookup"><span data-stu-id="67942-137">Expand the rich text editor to full-screen mode as you require.</span></span>
1. <span data-ttu-id="67942-138">Miután befejezte a tartalom bevitelével, az **Előnézet** lehetőséget kiválasztva tekintheti meg az oldal előnézetét a webböngészőben.</span><span class="sxs-lookup"><span data-stu-id="67942-138">When you've finished entering content, select **Preview** to preview the page in the web browser.</span></span>
1. <span data-ttu-id="67942-139">Végezze el az oldal és a modul tulajdonságainak minden hátralévő kiegészítését.</span><span class="sxs-lookup"><span data-stu-id="67942-139">Complete any remaining additions to the page and module properties.</span></span>
1. <span data-ttu-id="67942-140">Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="67942-140">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="67942-141">Az adatvédelmi irányelvek oldal URL-címének közzétételéhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="67942-141">To publish the URL for the privacy policy page, follow these steps.</span></span>

1. <span data-ttu-id="67942-142">Lépjen az **URL-címek** részhez, és válassza ki az adatvédelmi irányelv oldal URL-címét.</span><span class="sxs-lookup"><span data-stu-id="67942-142">Go to **URLs**, and select the URL for the privacy policy page.</span></span>
1. <span data-ttu-id="67942-143">A kiválasztott URL-cím közzétételéhez válassza a **közzététel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="67942-143">Select **Publish** to publish the selected URL.</span></span>

### <a name="create-a-link-to-the-privacy-policy-page-in-a-footer"></a><span data-ttu-id="67942-144">Az adatvédelmi irányelv oldalra mutató hivatkozás létrehozása láblécben</span><span class="sxs-lookup"><span data-stu-id="67942-144">Create a link to the privacy policy page in a footer</span></span>

<span data-ttu-id="67942-145">Az adatvédelmi irányelvek oldalra mutató hivatkozást hozzáadhatja egy töredékhez.</span><span class="sxs-lookup"><span data-stu-id="67942-145">You can add a link to the privacy policy page to a fragment.</span></span> <span data-ttu-id="67942-146">Ezzel a módszerrel megoszthatja a hivatkozást, és a töredékre hivatkozva több webhelyoldalon is frissítheti azt.</span><span class="sxs-lookup"><span data-stu-id="67942-146">In this way, you can share the link and update it across multiple site pages by referencing the fragment.</span></span> <span data-ttu-id="67942-147">Ez a példa bemutatja, hogyan lehet az adatvédelmi irányelv oldalra mutató hivatkozást hozzáadni egy lábléctöredékhez.</span><span class="sxs-lookup"><span data-stu-id="67942-147">This example shows how to add a link to the privacy policy page to a footer fragment.</span></span>

<span data-ttu-id="67942-148">A hivatkozás hozzáadásához egy lábléctöredékhez tegye a következőket.</span><span class="sxs-lookup"><span data-stu-id="67942-148">To add a link to a footer fragment, follow these steps.</span></span>

1. <span data-ttu-id="67942-149">Lépjen a **Töredékek** pontra, majd válassza az **Új** lehetőséget az oldaltöredék létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="67942-149">Go to **Fragments**, and then select **New** to create a page fragment.</span></span>
1. <span data-ttu-id="67942-150">Az **Új töredék** párbeszédpanelen válassza ki a **Lábléc** modult.</span><span class="sxs-lookup"><span data-stu-id="67942-150">In the **New fragment** dialog box, select the **Footer** module.</span></span>
1. <span data-ttu-id="67942-151">A **Töredék neve** pontban adja meg a töredék nevét, majd válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="67942-151">Under **Fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="67942-152">A **Lábléc-kategória** bővítőhelyen adja hozzá a **Láblécelem** modult.</span><span class="sxs-lookup"><span data-stu-id="67942-152">In the **Footer category** slot, add a **Footer item** module.</span></span>
1. <span data-ttu-id="67942-153">A jobb oldali tulajdonságok panelen válassza a **Hivatkozás szövege** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="67942-153">In the properties pane on the right, select **Link text**.</span></span>
1. <span data-ttu-id="67942-154">A **Hivatkozás szövege** párbeszédpanelen adja meg az adatvédelmi irányelv oldal hivatkozásszövegét és hivatkozási célját, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="67942-154">In the **Link text** dialog box, enter the link text and link target of the privacy policy page, and then click **OK**.</span></span>
1. <span data-ttu-id="67942-155">Az adatvédelmi irányelv URL-címének lekéréséhez lépjen az **Oldalak** részre, nyissa meg az adatvédelmi irányelv oldalát, és másolja az URL-címet a tulajdonságok ablaktáblából.</span><span class="sxs-lookup"><span data-stu-id="67942-155">To get the URL of the privacy policy page, go to **Pages**, go to the privacy policy page, and copy the URL from the properties pane.</span></span>
1. <span data-ttu-id="67942-156">Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a töredék ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="67942-156">Select **Save**, select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="67942-157">Megtekintheti a töredék előnézetét, és tesztelheti az adatvédelmi irányelvek oldalra mutató hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="67942-157">Preview the fragment, and test the link to the privacy policy page.</span></span>

<span data-ttu-id="67942-158">A töredék már hivatkozható más webhelyoldalak sablonjaiban.</span><span class="sxs-lookup"><span data-stu-id="67942-158">The fragment can now be referenced in the template for other site pages.</span></span> <span data-ttu-id="67942-159">Ha erre a töredékre egy sablon **Lábléc** moduljában hivatkoznak, akkor a hivatkozás minden olyan oldalon megjelenik, amely az adott sablon használatával készült.</span><span class="sxs-lookup"><span data-stu-id="67942-159">When this fragment is referenced in the **Footer** module of a template, the link reference will appear on any pages that are built by using that template.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="67942-160">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="67942-160">Additional resources</span></span>

[<span data-ttu-id="67942-161">Megfelelőség áttekintése</span><span class="sxs-lookup"><span data-stu-id="67942-161">Compliance overview</span></span>](compliance-overview.md)

[<span data-ttu-id="67942-162">Kisegítő funkciók és lehetőségek</span><span class="sxs-lookup"><span data-stu-id="67942-162">Accessibility features and capabilities</span></span>](accessibility.md)

[<span data-ttu-id="67942-163">Cookie-k megfelelősége</span><span class="sxs-lookup"><span data-stu-id="67942-163">Cookie compliance</span></span>](cookie-compliance.md)

[<span data-ttu-id="67942-164">Nyomon követett tartalmi változásokhoz társított felhasználói azonosítók kicserélése</span><span class="sxs-lookup"><span data-stu-id="67942-164">Replace user IDs associated with tracked content changes</span></span>](replace-IDs-tracked-changes.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
