---
title: Parancsfájl hozzáadása a webhely oldalaihoz a telemetria támogatásához
description: Ez a témakör azt mutatja be, hogyan lehet ügyféloldali parancsfájlt hozzáadni a webhely lapjaihoz, hogy támogassa az ügyfél-oldali telemetria gyűjtését.
author: bicyclingfool
manager: annbe
ms.date: 09/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e035c767474cba19c3a31eafdefb08b422b564ba
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5209203"
---
# <a name="add-script-code-to-site-pages-to-support-telemetry"></a><span data-ttu-id="35b08-103">Parancsfájl hozzáadása a webhely oldalaihoz a telemetria támogatásához</span><span class="sxs-lookup"><span data-stu-id="35b08-103">Add script code to site pages to support telemetry</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="35b08-104">Ez a témakör azt mutatja be, hogyan lehet ügyféloldali parancsfájlt hozzáadni a webhely lapjaihoz, hogy támogassa az ügyfél-oldali telemetria gyűjtését.</span><span class="sxs-lookup"><span data-stu-id="35b08-104">This topic describes how to add client-side script code to your site pages to support the collection of client-side telemetry.</span></span>

## <a name="overview"></a><span data-ttu-id="35b08-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="35b08-105">Overview</span></span>

<span data-ttu-id="35b08-106">A webanalitika fontos eszköz, ha meg szeretné tudni, hogyan lépnek interakcióba a vevők a webhellyel, és amelyek alapján a felhasználói élmény maximális konverzió érdekében történő optimalizálására szolgáló döntéseket hozhat.</span><span class="sxs-lookup"><span data-stu-id="35b08-106">Web analytics are an essential tool when you want to understand how your customers interact with your site and make decisions that will help optimize the experience for maximum conversion.</span></span> <span data-ttu-id="35b08-107">Számos webes elemzési csomag érhető el, amely segít elérni ezeket a célokat, például a Google Analytics, a Clicky, a Moz Analytics és a KISSMetrics.</span><span class="sxs-lookup"><span data-stu-id="35b08-107">Many web analytics packages are available to help you achieve these goals, such as Google Analytics, Clicky, Moz Analytics, and KISSMetrics.</span></span> <span data-ttu-id="35b08-108">A legtöbb webanalitikai csomag megköveteli, hogy ügyféloldali parancsfájlt adjon meg a HTML **\<head\>**  elemében a weboldala minden oldalán.</span><span class="sxs-lookup"><span data-stu-id="35b08-108">Most web analytics packages require that you add client-side script code in the **\<head\>** element of the HTML for all pages of your site.</span></span>

> [!NOTE]
> <span data-ttu-id="35b08-109">Az ebben a témakörben található utasítások a Microsoft Dynamics 365 Commerce által natív módon nem kínált egyéni ügyféloldali funkciókra is vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="35b08-109">The instructions in this topic also apply to other custom client-side functionality that Microsoft Dynamics 365 Commerce doesn't natively offer.</span></span>

## <a name="create-a-reusable-fragment-for-your-script-code"></a><span data-ttu-id="35b08-110">Újra felhasználható töredék létrehozása a parancsfájl kódjához</span><span class="sxs-lookup"><span data-stu-id="35b08-110">Create a reusable fragment for your script code</span></span>

<span data-ttu-id="35b08-111">A töredékek lehetővé teszik a belső és a külső parancsfájlkódok használatát a webhely összes lapján, függetlenül attól, hogy milyen sablont használnak.</span><span class="sxs-lookup"><span data-stu-id="35b08-111">A fragment allows you to reuse inline or external script code across all pages on your site, regardless of the template they use.</span></span>

### <a name="create-a-reusable-fragment-for-your-inline-script-code"></a><span data-ttu-id="35b08-112">Újra felhasználható töredék létrehozása a szövegközi parancsfájl kódjához</span><span class="sxs-lookup"><span data-stu-id="35b08-112">Create a reusable fragment for your inline script code</span></span>

<span data-ttu-id="35b08-113">A webhelykészítőben a szövegközi parancsfájlkódhoz tartozó újrahasználható töredék létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="35b08-113">To create a reusable fragment for your inline script code in site builder, follow these steps.</span></span>

1. <span data-ttu-id="35b08-114">Lépjen a **Töredékek** pontra, majd válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="35b08-114">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="35b08-115">Az **Új töredék** párbeszédpanelen válassza ki a **Szövegközi parancsfájl** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="35b08-115">In the **New fragment** dialog box, select **Inline script**.</span></span>
1. <span data-ttu-id="35b08-116">A **Töredék neve** pontban adja meg a töredék nevét, majd válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="35b08-116">Under **Fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="35b08-117">Válassza ki az **alapértelmezett szövegközi parancsfájl** modult a létrehozott töredék alatt.</span><span class="sxs-lookup"><span data-stu-id="35b08-117">Under the fragment that you created, select the **Default inline script** module.</span></span>
1. <span data-ttu-id="35b08-118">A jobb oldali ablaktáblában a **Szövegközi parancsfájl** területen adja meg a kliensoldali parancsfájlt.</span><span class="sxs-lookup"><span data-stu-id="35b08-118">In the property pane on the right, under **Inline script**, enter your client-side script.</span></span> <span data-ttu-id="35b08-119">Ezt követően konfigurálja a szükséges egyéb beállításokat.</span><span class="sxs-lookup"><span data-stu-id="35b08-119">Then configure other options as you require.</span></span>
1. <span data-ttu-id="35b08-120">Válassza a **Mentés** parancsot, majd válassza a **Szerkesztés befejezése** elemet.</span><span class="sxs-lookup"><span data-stu-id="35b08-120">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="35b08-121">Válassza a **Közzététel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="35b08-121">Select **Publish**.</span></span>

### <a name="create-a-reusable-fragment-for-your-external-script-code"></a><span data-ttu-id="35b08-122">Újra felhasználható töredék létrehozása a külső parancsfájl kódjához</span><span class="sxs-lookup"><span data-stu-id="35b08-122">Create a reusable fragment for your external script code</span></span>

<span data-ttu-id="35b08-123">A webhelykészítőben a külső parancsfájlkódhoz tartozó újrahasználható töredék létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="35b08-123">To create a reusable fragment for your external script code in site builder, follow these steps.</span></span>

1. <span data-ttu-id="35b08-124">Lépjen a **Töredékek** pontra, majd válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="35b08-124">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="35b08-125">Az **Új töredék** párbeszédpanelen válassza ki a **Külső parancsfájl** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="35b08-125">In the **New fragment** dialog box, select **External script**.</span></span>
1. <span data-ttu-id="35b08-126">A **Töredék neve** pontban adja meg a töredék nevét, majd válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="35b08-126">Under **Fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="35b08-127">Válassza ki az **alapértelmezett külső parancsfájl** modult a létrehozott töredék alatt.</span><span class="sxs-lookup"><span data-stu-id="35b08-127">Under the fragment that you created, select the **Default external script** module.</span></span>
1. <span data-ttu-id="35b08-128">A jobb oldali ablaktáblában a **Parancsfájl forrása** területen adja meg a külső parancsfájlhoz tartozó külső vagy kapcsolódó URL-címet.</span><span class="sxs-lookup"><span data-stu-id="35b08-128">In the property pane on the right, under **Script source**, add an external or relative URL for the external script source.</span></span> <span data-ttu-id="35b08-129">Ezt követően konfigurálja a szükséges egyéb beállításokat.</span><span class="sxs-lookup"><span data-stu-id="35b08-129">Then configure other options as you require.</span></span>
1. <span data-ttu-id="35b08-130">Válassza a **Mentés** parancsot, majd válassza a **Szerkesztés befejezése** elemet.</span><span class="sxs-lookup"><span data-stu-id="35b08-130">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="35b08-131">Válassza a **Közzététel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="35b08-131">Select **Publish**.</span></span>

> [!NOTE]
> <span data-ttu-id="35b08-132">Ha a webhelyhez engedélyezve van a tartalmi biztonsági irányelv (CSP), győződjön meg arról, hogy a Commerce webhelykészítőben a **script-src** CSP direktívához minden külső URL-cím hozzá van-e rendelve.</span><span class="sxs-lookup"><span data-stu-id="35b08-132">If content security policy (CSP) is enabled for your site, ensure that all external URLs are added to the **script-src** CSP directive in Commerce site builder.</span></span> <span data-ttu-id="35b08-133">További információ: [Tartalomra vonatkozó biztonsági irányelv (CSP) kezelése](manage-csp.md).</span><span class="sxs-lookup"><span data-stu-id="35b08-133">For more information, see [Manage Content Security Policy (CSP)](manage-csp.md).</span></span>

## <a name="add-a-fragment-that-includes-script-code-to-a-template"></a><span data-ttu-id="35b08-134">Parancsfájlkódot tartalmazó töredék hozzáadása sablonhoz</span><span class="sxs-lookup"><span data-stu-id="35b08-134">Add a fragment that includes script code to a template</span></span>

<span data-ttu-id="35b08-135">A webhelykészítőben egy sablonhoz egy parancsfájlkódot tartalmazó töredék hozzáadásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="35b08-135">To add a fragment that includes script code to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="35b08-136">Nyissa mega **Sablonok** pontot, majd nyissa meg azon oldalakhoz tartozó sablont, amelyhez hozzá szeretné adni a parancsfájlkódot.</span><span class="sxs-lookup"><span data-stu-id="35b08-136">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="35b08-137">A bal oldali panelen bontsa ki a sablon hierarchiáját a **HTML-fejléc** helyének megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="35b08-137">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="35b08-138">A **HTML-fejléc** helyben válassza a három pont (**…**) gombot, majd válassza a **Töredék hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="35b08-138">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add fragment**.</span></span>
1. <span data-ttu-id="35b08-139">Válassza ki a parancsfájl kódjához létrehozott töredéket.</span><span class="sxs-lookup"><span data-stu-id="35b08-139">Select the fragment that you created for your script code.</span></span>
1. <span data-ttu-id="35b08-140">Válassza a **Mentés** parancsot, majd válassza a **Szerkesztés befejezése** elemet.</span><span class="sxs-lookup"><span data-stu-id="35b08-140">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="35b08-141">Válassza a **Közzététel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="35b08-141">Select **Publish**.</span></span>

## <a name="add-an-external-script-or-inline-script-directly-to-a-template"></a><span data-ttu-id="35b08-142">Külső parancsfájl vagy szövegközi parancsfájl hozzáadása sablonhoz közvetlenül</span><span class="sxs-lookup"><span data-stu-id="35b08-142">Add an external script or inline script directly to a template</span></span>

<span data-ttu-id="35b08-143">Ha azt szeretné, hogy egy szövegközi vagy külső parancsfájlt közvetlenül egyetlen sablon által vezérelt oldalak csoportjába szúrjunk be, akkor előbb nem kell létrehoznia a töredéket.</span><span class="sxs-lookup"><span data-stu-id="35b08-143">If you want to insert an inline or external script directly into a set of pages that are controlled by a single template, you don't have to create a fragment first.</span></span>

### <a name="add-an-inline-script-directly-to-a-template"></a><span data-ttu-id="35b08-144">Szövegközi parancsfájl hozzáadása sablonhoz közvetlenül</span><span class="sxs-lookup"><span data-stu-id="35b08-144">Add an inline script directly to a template</span></span>

<span data-ttu-id="35b08-145">Ha egy szövegközi parancsfájlt közvetlenül egy sablonhoz szeretne hozzáadni a webhelykészítőben, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="35b08-145">To add an inline script directly to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="35b08-146">Nyissa mega **Sablonok** pontot, majd nyissa meg azon oldalakhoz tartozó sablont, amelyhez hozzá szeretné adni a parancsfájlkódot.</span><span class="sxs-lookup"><span data-stu-id="35b08-146">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="35b08-147">A bal oldali panelen bontsa ki a sablon hierarchiáját a **HTML-fejléc** helyének megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="35b08-147">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="35b08-148">A **HTML-fejléc** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="35b08-148">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="35b08-149">A **Modul hozzáadása** párbeszédablakban válassza a **Szövegközi parancsfájl** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="35b08-149">In the **Add Module** dialog box, select **Inline script**.</span></span>
1. <span data-ttu-id="35b08-150">A jobb oldali ablaktáblában a **Szövegközi parancsfájl** területen adja meg a kliensoldali parancsfájlt.</span><span class="sxs-lookup"><span data-stu-id="35b08-150">In the property pane on the right, under **Inline script**, enter your client-side script.</span></span> <span data-ttu-id="35b08-151">Ezt követően konfigurálja a szükséges egyéb beállításokat.</span><span class="sxs-lookup"><span data-stu-id="35b08-151">Then configure other options as you require.</span></span>
1. <span data-ttu-id="35b08-152">Válassza a **Mentés** parancsot, majd válassza a **Szerkesztés befejezése** elemet.</span><span class="sxs-lookup"><span data-stu-id="35b08-152">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="35b08-153">Válassza a **Közzététel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="35b08-153">Select **Publish**.</span></span>

### <a name="add-an-external-script-directly-to-a-template"></a><span data-ttu-id="35b08-154">Külső parancsfájl hozzáadása sablonhoz közvetlenül</span><span class="sxs-lookup"><span data-stu-id="35b08-154">Add an external script directly to a template</span></span>

<span data-ttu-id="35b08-155">Ha egy külső parancsfájlt közvetlenül egy sablonhoz szeretne hozzáadni a webhelykészítőben, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="35b08-155">To add an external script directly to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="35b08-156">Nyissa mega **Sablonok** pontot, majd nyissa meg azon oldalakhoz tartozó sablont, amelyhez hozzá szeretné adni a parancsfájlkódot.</span><span class="sxs-lookup"><span data-stu-id="35b08-156">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="35b08-157">A bal oldali panelen bontsa ki a sablon hierarchiáját a **HTML-fejléc** helyének megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="35b08-157">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="35b08-158">A **HTML-fejléc** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="35b08-158">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="35b08-159">A **Modul hozzáadása** párbeszédablakban válassza a **Külső parancsfájl** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="35b08-159">In the **Add Module** dialog box, select **External script**.</span></span>
1. <span data-ttu-id="35b08-160">A jobb oldali ablaktáblában a **Parancsfájl forrása** területen adja meg a külső parancsfájlhoz tartozó külső vagy kapcsolódó URL-címet.</span><span class="sxs-lookup"><span data-stu-id="35b08-160">In the property pane on the right, under **Script source**, add an external or relative URL for the external script source.</span></span> <span data-ttu-id="35b08-161">Ezt követően konfigurálja a szükséges egyéb beállításokat.</span><span class="sxs-lookup"><span data-stu-id="35b08-161">Then configure other options as you require.</span></span>
1. <span data-ttu-id="35b08-162">Válassza a **Mentés** parancsot, majd válassza a **Szerkesztés befejezése** elemet.</span><span class="sxs-lookup"><span data-stu-id="35b08-162">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="35b08-163">Válassza a **Közzététel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="35b08-163">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="35b08-164">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="35b08-164">Additional resources</span></span>

[<span data-ttu-id="35b08-165">Embléma hozzáadása</span><span class="sxs-lookup"><span data-stu-id="35b08-165">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="35b08-166">Webhely témájának kiválasztása</span><span class="sxs-lookup"><span data-stu-id="35b08-166">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="35b08-167">A CSS felülíró fájljainak használata</span><span class="sxs-lookup"><span data-stu-id="35b08-167">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="35b08-168">Kedvencek ikon hozzáadása</span><span class="sxs-lookup"><span data-stu-id="35b08-168">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="35b08-169">Üdvözlő üzenet hozzáadása</span><span class="sxs-lookup"><span data-stu-id="35b08-169">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="35b08-170">Szerzői jogi értesítés hozzáadása</span><span class="sxs-lookup"><span data-stu-id="35b08-170">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="35b08-171">Nyelvek hozzáadása a webhelyhez</span><span class="sxs-lookup"><span data-stu-id="35b08-171">Add languages to your site</span></span>](add-languages-to-site.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]