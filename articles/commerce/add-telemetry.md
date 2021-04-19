---
title: Parancsfájl hozzáadása a webhely oldalaihoz a telemetria támogatásához
description: Ez a témakör azt mutatja be, hogyan lehet ügyféloldali parancsfájlt hozzáadni a webhely lapjaihoz, hogy támogassa az ügyfél-oldali telemetria gyűjtését.
author: bicyclingfool
ms.date: 09/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: fb1773ab10b23a586eb6a8286f145181818585b9
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797431"
---
# <a name="add-script-code-to-site-pages-to-support-telemetry"></a><span data-ttu-id="cb324-103">Parancsfájl hozzáadása a webhely oldalaihoz a telemetria támogatásához</span><span class="sxs-lookup"><span data-stu-id="cb324-103">Add script code to site pages to support telemetry</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="cb324-104">Ez a témakör azt mutatja be, hogyan lehet ügyféloldali parancsfájlt hozzáadni a webhely lapjaihoz, hogy támogassa az ügyfél-oldali telemetria gyűjtését.</span><span class="sxs-lookup"><span data-stu-id="cb324-104">This topic describes how to add client-side script code to your site pages to support the collection of client-side telemetry.</span></span>

<span data-ttu-id="cb324-105">A webanalitika fontos eszköz, ha meg szeretné tudni, hogyan lépnek interakcióba a vevők a webhellyel, és amelyek alapján a felhasználói élmény maximális konverzió érdekében történő optimalizálására szolgáló döntéseket hozhat.</span><span class="sxs-lookup"><span data-stu-id="cb324-105">Web analytics are an essential tool when you want to understand how your customers interact with your site and make decisions that will help optimize the experience for maximum conversion.</span></span> <span data-ttu-id="cb324-106">Számos webes elemzési csomag érhető el, amely segít elérni ezeket a célokat, például a Google Analytics, a Clicky, a Moz Analytics és a KISSMetrics.</span><span class="sxs-lookup"><span data-stu-id="cb324-106">Many web analytics packages are available to help you achieve these goals, such as Google Analytics, Clicky, Moz Analytics, and KISSMetrics.</span></span> <span data-ttu-id="cb324-107">A legtöbb webanalitikai csomag megköveteli, hogy ügyféloldali parancsfájlt adjon meg a HTML **\<head\>**  elemében a weboldala minden oldalán.</span><span class="sxs-lookup"><span data-stu-id="cb324-107">Most web analytics packages require that you add client-side script code in the **\<head\>** element of the HTML for all pages of your site.</span></span>

> [!NOTE]
> <span data-ttu-id="cb324-108">Az ebben a témakörben található utasítások a Microsoft Dynamics 365 Commerce által natív módon nem kínált egyéni ügyféloldali funkciókra is vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="cb324-108">The instructions in this topic also apply to other custom client-side functionality that Microsoft Dynamics 365 Commerce doesn't natively offer.</span></span>

## <a name="create-a-reusable-fragment-for-your-script-code"></a><span data-ttu-id="cb324-109">Újra felhasználható töredék létrehozása a parancsfájl kódjához</span><span class="sxs-lookup"><span data-stu-id="cb324-109">Create a reusable fragment for your script code</span></span>

<span data-ttu-id="cb324-110">A töredékek lehetővé teszik a belső és a külső parancsfájlkódok használatát a webhely összes lapján, függetlenül attól, hogy milyen sablont használnak.</span><span class="sxs-lookup"><span data-stu-id="cb324-110">A fragment allows you to reuse inline or external script code across all pages on your site, regardless of the template they use.</span></span>

### <a name="create-a-reusable-fragment-for-your-inline-script-code"></a><span data-ttu-id="cb324-111">Újra felhasználható töredék létrehozása a szövegközi parancsfájl kódjához</span><span class="sxs-lookup"><span data-stu-id="cb324-111">Create a reusable fragment for your inline script code</span></span>

<span data-ttu-id="cb324-112">A webhelykészítőben a szövegközi parancsfájlkódhoz tartozó újrahasználható töredék létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="cb324-112">To create a reusable fragment for your inline script code in site builder, follow these steps.</span></span>

1. <span data-ttu-id="cb324-113">Lépjen a **Töredékek** pontra, majd válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cb324-113">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="cb324-114">Az **Új töredék** párbeszédpanelen válassza ki a **Szövegközi parancsfájl** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cb324-114">In the **New fragment** dialog box, select **Inline script**.</span></span>
1. <span data-ttu-id="cb324-115">A **Töredék neve** pontban adja meg a töredék nevét, majd válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cb324-115">Under **Fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="cb324-116">Válassza ki az **alapértelmezett szövegközi parancsfájl** modult a létrehozott töredék alatt.</span><span class="sxs-lookup"><span data-stu-id="cb324-116">Under the fragment that you created, select the **Default inline script** module.</span></span>
1. <span data-ttu-id="cb324-117">A jobb oldali ablaktáblában a **Szövegközi parancsfájl** területen adja meg a kliensoldali parancsfájlt.</span><span class="sxs-lookup"><span data-stu-id="cb324-117">In the property pane on the right, under **Inline script**, enter your client-side script.</span></span> <span data-ttu-id="cb324-118">Ezt követően konfigurálja a szükséges egyéb beállításokat.</span><span class="sxs-lookup"><span data-stu-id="cb324-118">Then configure other options as you require.</span></span>
1. <span data-ttu-id="cb324-119">Válassza a **Mentés** parancsot, majd válassza a **Szerkesztés befejezése** elemet.</span><span class="sxs-lookup"><span data-stu-id="cb324-119">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="cb324-120">Válassza a **Közzététel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cb324-120">Select **Publish**.</span></span>

### <a name="create-a-reusable-fragment-for-your-external-script-code"></a><span data-ttu-id="cb324-121">Újra felhasználható töredék létrehozása a külső parancsfájl kódjához</span><span class="sxs-lookup"><span data-stu-id="cb324-121">Create a reusable fragment for your external script code</span></span>

<span data-ttu-id="cb324-122">A webhelykészítőben a külső parancsfájlkódhoz tartozó újrahasználható töredék létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="cb324-122">To create a reusable fragment for your external script code in site builder, follow these steps.</span></span>

1. <span data-ttu-id="cb324-123">Lépjen a **Töredékek** pontra, majd válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cb324-123">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="cb324-124">Az **Új töredék** párbeszédpanelen válassza ki a **Külső parancsfájl** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cb324-124">In the **New fragment** dialog box, select **External script**.</span></span>
1. <span data-ttu-id="cb324-125">A **Töredék neve** pontban adja meg a töredék nevét, majd válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cb324-125">Under **Fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="cb324-126">Válassza ki az **alapértelmezett külső parancsfájl** modult a létrehozott töredék alatt.</span><span class="sxs-lookup"><span data-stu-id="cb324-126">Under the fragment that you created, select the **Default external script** module.</span></span>
1. <span data-ttu-id="cb324-127">A jobb oldali ablaktáblában a **Parancsfájl forrása** területen adja meg a külső parancsfájlhoz tartozó külső vagy kapcsolódó URL-címet.</span><span class="sxs-lookup"><span data-stu-id="cb324-127">In the property pane on the right, under **Script source**, add an external or relative URL for the external script source.</span></span> <span data-ttu-id="cb324-128">Ezt követően konfigurálja a szükséges egyéb beállításokat.</span><span class="sxs-lookup"><span data-stu-id="cb324-128">Then configure other options as you require.</span></span>
1. <span data-ttu-id="cb324-129">Válassza a **Mentés** parancsot, majd válassza a **Szerkesztés befejezése** elemet.</span><span class="sxs-lookup"><span data-stu-id="cb324-129">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="cb324-130">Válassza a **Közzététel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cb324-130">Select **Publish**.</span></span>

> [!NOTE]
> <span data-ttu-id="cb324-131">Ha a webhelyhez engedélyezve van a tartalmi biztonsági irányelv (CSP), győződjön meg arról, hogy a Commerce webhelykészítőben a **script-src** CSP direktívához minden külső URL-cím hozzá van-e rendelve.</span><span class="sxs-lookup"><span data-stu-id="cb324-131">If content security policy (CSP) is enabled for your site, ensure that all external URLs are added to the **script-src** CSP directive in Commerce site builder.</span></span> <span data-ttu-id="cb324-132">További információ: [Tartalomra vonatkozó biztonsági irányelv (CSP) kezelése](manage-csp.md).</span><span class="sxs-lookup"><span data-stu-id="cb324-132">For more information, see [Manage Content Security Policy (CSP)](manage-csp.md).</span></span>

## <a name="add-a-fragment-that-includes-script-code-to-a-template"></a><span data-ttu-id="cb324-133">Parancsfájlkódot tartalmazó töredék hozzáadása sablonhoz</span><span class="sxs-lookup"><span data-stu-id="cb324-133">Add a fragment that includes script code to a template</span></span>

<span data-ttu-id="cb324-134">A webhelykészítőben egy sablonhoz egy parancsfájlkódot tartalmazó töredék hozzáadásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="cb324-134">To add a fragment that includes script code to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="cb324-135">Nyissa mega **Sablonok** pontot, majd nyissa meg azon oldalakhoz tartozó sablont, amelyhez hozzá szeretné adni a parancsfájlkódot.</span><span class="sxs-lookup"><span data-stu-id="cb324-135">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="cb324-136">A bal oldali panelen bontsa ki a sablon hierarchiáját a **HTML-fejléc** helyének megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="cb324-136">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="cb324-137">A **HTML-fejléc** helyben válassza a három pont (**…**) gombot, majd válassza a **Töredék hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="cb324-137">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add fragment**.</span></span>
1. <span data-ttu-id="cb324-138">Válassza ki a parancsfájl kódjához létrehozott töredéket.</span><span class="sxs-lookup"><span data-stu-id="cb324-138">Select the fragment that you created for your script code.</span></span>
1. <span data-ttu-id="cb324-139">Válassza a **Mentés** parancsot, majd válassza a **Szerkesztés befejezése** elemet.</span><span class="sxs-lookup"><span data-stu-id="cb324-139">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="cb324-140">Válassza a **Közzététel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cb324-140">Select **Publish**.</span></span>

## <a name="add-an-external-script-or-inline-script-directly-to-a-template"></a><span data-ttu-id="cb324-141">Külső parancsfájl vagy szövegközi parancsfájl hozzáadása sablonhoz közvetlenül</span><span class="sxs-lookup"><span data-stu-id="cb324-141">Add an external script or inline script directly to a template</span></span>

<span data-ttu-id="cb324-142">Ha azt szeretné, hogy egy szövegközi vagy külső parancsfájlt közvetlenül egyetlen sablon által vezérelt oldalak csoportjába szúrjunk be, akkor előbb nem kell létrehoznia a töredéket.</span><span class="sxs-lookup"><span data-stu-id="cb324-142">If you want to insert an inline or external script directly into a set of pages that are controlled by a single template, you don't have to create a fragment first.</span></span>

### <a name="add-an-inline-script-directly-to-a-template"></a><span data-ttu-id="cb324-143">Szövegközi parancsfájl hozzáadása sablonhoz közvetlenül</span><span class="sxs-lookup"><span data-stu-id="cb324-143">Add an inline script directly to a template</span></span>

<span data-ttu-id="cb324-144">Ha egy szövegközi parancsfájlt közvetlenül egy sablonhoz szeretne hozzáadni a webhelykészítőben, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="cb324-144">To add an inline script directly to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="cb324-145">Nyissa mega **Sablonok** pontot, majd nyissa meg azon oldalakhoz tartozó sablont, amelyhez hozzá szeretné adni a parancsfájlkódot.</span><span class="sxs-lookup"><span data-stu-id="cb324-145">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="cb324-146">A bal oldali panelen bontsa ki a sablon hierarchiáját a **HTML-fejléc** helyének megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="cb324-146">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="cb324-147">A **HTML-fejléc** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="cb324-147">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="cb324-148">A **Modul hozzáadása** párbeszédablakban válassza a **Szövegközi parancsfájl** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cb324-148">In the **Add Module** dialog box, select **Inline script**.</span></span>
1. <span data-ttu-id="cb324-149">A jobb oldali ablaktáblában a **Szövegközi parancsfájl** területen adja meg a kliensoldali parancsfájlt.</span><span class="sxs-lookup"><span data-stu-id="cb324-149">In the property pane on the right, under **Inline script**, enter your client-side script.</span></span> <span data-ttu-id="cb324-150">Ezt követően konfigurálja a szükséges egyéb beállításokat.</span><span class="sxs-lookup"><span data-stu-id="cb324-150">Then configure other options as you require.</span></span>
1. <span data-ttu-id="cb324-151">Válassza a **Mentés** parancsot, majd válassza a **Szerkesztés befejezése** elemet.</span><span class="sxs-lookup"><span data-stu-id="cb324-151">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="cb324-152">Válassza a **Közzététel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cb324-152">Select **Publish**.</span></span>

### <a name="add-an-external-script-directly-to-a-template"></a><span data-ttu-id="cb324-153">Külső parancsfájl hozzáadása sablonhoz közvetlenül</span><span class="sxs-lookup"><span data-stu-id="cb324-153">Add an external script directly to a template</span></span>

<span data-ttu-id="cb324-154">Ha egy külső parancsfájlt közvetlenül egy sablonhoz szeretne hozzáadni a webhelykészítőben, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="cb324-154">To add an external script directly to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="cb324-155">Nyissa mega **Sablonok** pontot, majd nyissa meg azon oldalakhoz tartozó sablont, amelyhez hozzá szeretné adni a parancsfájlkódot.</span><span class="sxs-lookup"><span data-stu-id="cb324-155">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="cb324-156">A bal oldali panelen bontsa ki a sablon hierarchiáját a **HTML-fejléc** helyének megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="cb324-156">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="cb324-157">A **HTML-fejléc** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="cb324-157">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="cb324-158">A **Modul hozzáadása** párbeszédablakban válassza a **Külső parancsfájl** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cb324-158">In the **Add Module** dialog box, select **External script**.</span></span>
1. <span data-ttu-id="cb324-159">A jobb oldali ablaktáblában a **Parancsfájl forrása** területen adja meg a külső parancsfájlhoz tartozó külső vagy kapcsolódó URL-címet.</span><span class="sxs-lookup"><span data-stu-id="cb324-159">In the property pane on the right, under **Script source**, add an external or relative URL for the external script source.</span></span> <span data-ttu-id="cb324-160">Ezt követően konfigurálja a szükséges egyéb beállításokat.</span><span class="sxs-lookup"><span data-stu-id="cb324-160">Then configure other options as you require.</span></span>
1. <span data-ttu-id="cb324-161">Válassza a **Mentés** parancsot, majd válassza a **Szerkesztés befejezése** elemet.</span><span class="sxs-lookup"><span data-stu-id="cb324-161">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="cb324-162">Válassza a **Közzététel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cb324-162">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cb324-163">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="cb324-163">Additional resources</span></span>

[<span data-ttu-id="cb324-164">Embléma hozzáadása</span><span class="sxs-lookup"><span data-stu-id="cb324-164">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="cb324-165">Webhely témájának kiválasztása</span><span class="sxs-lookup"><span data-stu-id="cb324-165">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="cb324-166">A CSS felülíró fájljainak használata</span><span class="sxs-lookup"><span data-stu-id="cb324-166">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="cb324-167">Kedvencek ikon hozzáadása</span><span class="sxs-lookup"><span data-stu-id="cb324-167">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="cb324-168">Üdvözlő üzenet hozzáadása</span><span class="sxs-lookup"><span data-stu-id="cb324-168">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="cb324-169">Szerzői jogi értesítés hozzáadása</span><span class="sxs-lookup"><span data-stu-id="cb324-169">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="cb324-170">Nyelvek hozzáadása a webhelyhez</span><span class="sxs-lookup"><span data-stu-id="cb324-170">Add languages to your site</span></span>](add-languages-to-site.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
