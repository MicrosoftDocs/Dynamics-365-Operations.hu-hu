---
title: Parancsfájl hozzáadása a webhely oldalaihoz a telemetria támogatásához
description: Ez a témakör azt mutatja be, hogyan lehet ügyféloldali parancsfájlt hozzáadni a webhely lapjaihoz, hogy támogassa az ügyfél-oldali telemetria gyűjtését.
author: bicyclingfool
manager: annbe
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: a88f4f920154aafaa15a48af67365152e21111f7
ms.sourcegitcommit: 420b9e538f706178f8e1f2786e02f4f400bf2336
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/02/2020
ms.locfileid: "3761249"
---
# <a name="add-script-code-to-site-pages-to-support-telemetry"></a><span data-ttu-id="f1406-103">Parancsfájl hozzáadása a webhely oldalaihoz a telemetria támogatásához</span><span class="sxs-lookup"><span data-stu-id="f1406-103">Add script code to site pages to support telemetry</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f1406-104">Ez a témakör azt mutatja be, hogyan lehet ügyféloldali parancsfájlt hozzáadni a webhely lapjaihoz, hogy támogassa az ügyfél-oldali telemetria gyűjtését.</span><span class="sxs-lookup"><span data-stu-id="f1406-104">This topic describes how to add client-side script code to your site pages to support the collection of client-side telemetry.</span></span>

## <a name="overview"></a><span data-ttu-id="f1406-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="f1406-105">Overview</span></span>

<span data-ttu-id="f1406-106">A webanalitika fontos eszköz, ha meg szeretné tudni, hogyan lépnek interakcióba a vevők a webhellyel, és amelyek alapján a felhasználói élmény maximális konverzió érdekében történő optimalizálására szolgáló döntéseket hozhat.</span><span class="sxs-lookup"><span data-stu-id="f1406-106">Web analytics are an essential tool when you want to understand how your customers interact with your site and make decisions that will help optimize the experience for maximum conversion.</span></span> <span data-ttu-id="f1406-107">Számos webes elemzési csomag érhető el, amely segít elérni ezeket a célokat, például a Google Analytics, a Clicky, a Moz Analytics és a KISSMetrics.</span><span class="sxs-lookup"><span data-stu-id="f1406-107">Many web analytics packages are available to help you achieve these goals, such as Google Analytics, Clicky, Moz Analytics, and KISSMetrics.</span></span> <span data-ttu-id="f1406-108">A legtöbb webanalitikai csomag megköveteli, hogy ügyféloldali parancsfájlt adjon meg a HTML **\<head\>**  elemében a weboldala minden oldalán.</span><span class="sxs-lookup"><span data-stu-id="f1406-108">Most web analytics packages require that you add client-side script code in the **\<head\>** element of the HTML for all pages of your site.</span></span>

> [!NOTE]
> <span data-ttu-id="f1406-109">Az ebben a témakörben található utasítások a Microsoft Dynamics 365 Commerce által natív módon nem kínált egyéni ügyféloldali funkciókra is vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="f1406-109">The instructions in this topic also apply to other custom client-side functionality that Microsoft Dynamics 365 Commerce doesn't natively offer.</span></span>

## <a name="create-a-reusable-fragment-for-your-script-code"></a><span data-ttu-id="f1406-110">Újra felhasználható töredék létrehozása a parancsfájl kódjához</span><span class="sxs-lookup"><span data-stu-id="f1406-110">Create a reusable fragment for your script code</span></span>

<span data-ttu-id="f1406-111">A töredékek lehetővé teszik a belső és a külső parancsfájlkódok használatát a webhely összes lapján, függetlenül attól, hogy milyen sablont használnak.</span><span class="sxs-lookup"><span data-stu-id="f1406-111">A fragment allows you to reuse inline or external script code across all pages on your site, regardless of the template they use.</span></span>

### <a name="create-a-reusable-fragment-for-your-inline-script-code"></a><span data-ttu-id="f1406-112">Újra felhasználható töredék létrehozása a szövegközi parancsfájl kódjához</span><span class="sxs-lookup"><span data-stu-id="f1406-112">Create a reusable fragment for your inline script code</span></span>

<span data-ttu-id="f1406-113">A webhelykészítőben a szövegközi parancsfájlkódhoz tartozó újrahasználható töredék létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="f1406-113">To create a reusable fragment for your inline script code in site builder, follow these steps.</span></span>

1. <span data-ttu-id="f1406-114">Lépjen a **Töredékek** pontra, majd válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1406-114">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="f1406-115">Az **Új töredék** párbeszédpanelen válassza ki a **Szövegközi parancsfájl** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1406-115">In the **New fragment** dialog box, select **Inline script**.</span></span>
1. <span data-ttu-id="f1406-116">A **Töredék neve** pontban adja meg a töredék nevét, majd válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1406-116">Under **Fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="f1406-117">Válassza ki az **alapértelmezett szövegközi parancsfájl** modult a létrehozott töredék alatt.</span><span class="sxs-lookup"><span data-stu-id="f1406-117">Under the fragment that you created, select the **Default inline script** module.</span></span>
1. <span data-ttu-id="f1406-118">A jobb oldali ablaktáblában a **Szövegközi parancsfájl** területen adja meg a kliensoldali parancsfájlt.</span><span class="sxs-lookup"><span data-stu-id="f1406-118">In the property pane on the right, under **Inline script**, enter your client-side script.</span></span> <span data-ttu-id="f1406-119">Ezt követően konfigurálja a szükséges egyéb beállításokat.</span><span class="sxs-lookup"><span data-stu-id="f1406-119">Then configure other options as you require.</span></span>
1. <span data-ttu-id="f1406-120">Válassza a **Mentés** parancsot, majd válassza a **Szerkesztés befejezése** elemet.</span><span class="sxs-lookup"><span data-stu-id="f1406-120">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="f1406-121">Válassza a **Közzététel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1406-121">Select **Publish**.</span></span>

### <a name="create-a-reusable-fragment-for-your-external-script-code"></a><span data-ttu-id="f1406-122">Újra felhasználható töredék létrehozása a külső parancsfájl kódjához</span><span class="sxs-lookup"><span data-stu-id="f1406-122">Create a reusable fragment for your external script code</span></span>

<span data-ttu-id="f1406-123">A webhelykészítőben a külső parancsfájlkódhoz tartozó újrahasználható töredék létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="f1406-123">To create a reusable fragment for your external script code in site builder, follow these steps.</span></span>

1. <span data-ttu-id="f1406-124">Lépjen a **Töredékek** pontra, majd válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1406-124">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="f1406-125">Az **Új töredék** párbeszédpanelen válassza ki a **Külső parancsfájl** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1406-125">In the **New fragment** dialog box, select **External script**.</span></span>
1. <span data-ttu-id="f1406-126">A **Töredék neve** pontban adja meg a töredék nevét, majd válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1406-126">Under **Fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="f1406-127">Válassza ki az **alapértelmezett külső parancsfájl** modult a létrehozott töredék alatt.</span><span class="sxs-lookup"><span data-stu-id="f1406-127">Under the fragment that you created, select the **Default external script** module.</span></span>
1. <span data-ttu-id="f1406-128">A jobb oldali ablaktáblában a **Parancsfájl forrása** területen adja meg a külső parancsfájlhoz tartozó külső vagy kapcsolódó URL-címet.</span><span class="sxs-lookup"><span data-stu-id="f1406-128">In the property pane on the right, under **Script source**, add an external or relative URL for the external script source.</span></span> <span data-ttu-id="f1406-129">Ezt követően konfigurálja a szükséges egyéb beállításokat.</span><span class="sxs-lookup"><span data-stu-id="f1406-129">Then configure other options as you require.</span></span>
1. <span data-ttu-id="f1406-130">Válassza a **Mentés** parancsot, majd válassza a **Szerkesztés befejezése** elemet.</span><span class="sxs-lookup"><span data-stu-id="f1406-130">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="f1406-131">Válassza a **Közzététel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1406-131">Select **Publish**.</span></span>

## <a name="add-a-fragment-that-includes-script-code-to-a-template"></a><span data-ttu-id="f1406-132">Parancsfájlkódot tartalmazó töredék hozzáadása sablonhoz</span><span class="sxs-lookup"><span data-stu-id="f1406-132">Add a fragment that includes script code to a template</span></span>

<span data-ttu-id="f1406-133">A webhelykészítőben egy sablonhoz egy parancsfájlkódot tartalmazó töredék hozzáadásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="f1406-133">To add a fragment that includes script code to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="f1406-134">Nyissa mega **Sablonok** pontot, majd nyissa meg azon oldalakhoz tartozó sablont, amelyhez hozzá szeretné adni a parancsfájlkódot.</span><span class="sxs-lookup"><span data-stu-id="f1406-134">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="f1406-135">A bal oldali panelen bontsa ki a sablon hierarchiáját a **HTML-fejléc** helyének megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="f1406-135">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="f1406-136">A **HTML-fejléc** helyben válassza a három pont (**…**) gombot, majd válassza a **Töredék hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="f1406-136">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add fragment**.</span></span>
1. <span data-ttu-id="f1406-137">Válassza ki a parancsfájl kódjához létrehozott töredéket.</span><span class="sxs-lookup"><span data-stu-id="f1406-137">Select the fragment that you created for your script code.</span></span>
1. <span data-ttu-id="f1406-138">Válassza a **Mentés** parancsot, majd válassza a **Szerkesztés befejezése** elemet.</span><span class="sxs-lookup"><span data-stu-id="f1406-138">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="f1406-139">Válassza a **Közzététel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1406-139">Select **Publish**.</span></span>

## <a name="add-an-external-script-or-inline-script-directly-to-a-template"></a><span data-ttu-id="f1406-140">Külső parancsfájl vagy szövegközi parancsfájl hozzáadása sablonhoz közvetlenül</span><span class="sxs-lookup"><span data-stu-id="f1406-140">Add an external script or inline script directly to a template</span></span>

<span data-ttu-id="f1406-141">Ha azt szeretné, hogy egy szövegközi vagy külső parancsfájlt közvetlenül egyetlen sablon által vezérelt oldalak csoportjába szúrjunk be, akkor előbb nem kell létrehoznia a töredéket.</span><span class="sxs-lookup"><span data-stu-id="f1406-141">If you want to insert an inline or external script directly into a set of pages that are controlled by a single template, you don't have to create a fragment first.</span></span>

### <a name="add-an-inline-script-directly-to-a-template"></a><span data-ttu-id="f1406-142">Szövegközi parancsfájl hozzáadása sablonhoz közvetlenül</span><span class="sxs-lookup"><span data-stu-id="f1406-142">Add an inline script directly to a template</span></span>

<span data-ttu-id="f1406-143">Ha egy szövegközi parancsfájlt közvetlenül egy sablonhoz szeretne hozzáadni a webhelykészítőben, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="f1406-143">To add an inline script directly to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="f1406-144">Nyissa mega **Sablonok** pontot, majd nyissa meg azon oldalakhoz tartozó sablont, amelyhez hozzá szeretné adni a parancsfájlkódot.</span><span class="sxs-lookup"><span data-stu-id="f1406-144">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="f1406-145">A bal oldali panelen bontsa ki a sablon hierarchiáját a **HTML-fejléc** helyének megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="f1406-145">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="f1406-146">A **HTML-fejléc** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="f1406-146">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="f1406-147">A **Modul hozzáadása** párbeszédablakban válassza a **Szövegközi parancsfájl** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1406-147">In the **Add Module** dialog box, select **Inline script**.</span></span>
1. <span data-ttu-id="f1406-148">A jobb oldali ablaktáblában a **Szövegközi parancsfájl** területen adja meg a kliensoldali parancsfájlt.</span><span class="sxs-lookup"><span data-stu-id="f1406-148">In the property pane on the right, under **Inline script**, enter your client-side script.</span></span> <span data-ttu-id="f1406-149">Ezt követően konfigurálja a szükséges egyéb beállításokat.</span><span class="sxs-lookup"><span data-stu-id="f1406-149">Then configure other options as you require.</span></span>
1. <span data-ttu-id="f1406-150">Válassza a **Mentés** parancsot, majd válassza a **Szerkesztés befejezése** elemet.</span><span class="sxs-lookup"><span data-stu-id="f1406-150">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="f1406-151">Válassza a **Közzététel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1406-151">Select **Publish**.</span></span>

### <a name="add-an-external-script-directly-to-a-template"></a><span data-ttu-id="f1406-152">Külső parancsfájl hozzáadása sablonhoz közvetlenül</span><span class="sxs-lookup"><span data-stu-id="f1406-152">Add an external script directly to a template</span></span>

<span data-ttu-id="f1406-153">Ha egy külső parancsfájlt közvetlenül egy sablonhoz szeretne hozzáadni a webhelykészítőben, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="f1406-153">To add an external script directly to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="f1406-154">Nyissa mega **Sablonok** pontot, majd nyissa meg azon oldalakhoz tartozó sablont, amelyhez hozzá szeretné adni a parancsfájlkódot.</span><span class="sxs-lookup"><span data-stu-id="f1406-154">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="f1406-155">A bal oldali panelen bontsa ki a sablon hierarchiáját a **HTML-fejléc** helyének megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="f1406-155">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="f1406-156">A **HTML-fejléc** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="f1406-156">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="f1406-157">A **Modul hozzáadása** párbeszédablakban válassza a **Külső parancsfájl** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1406-157">In the **Add Module** dialog box, select **External script**.</span></span>
1. <span data-ttu-id="f1406-158">A jobb oldali ablaktáblában a **Parancsfájl forrása** területen adja meg a külső parancsfájlhoz tartozó külső vagy kapcsolódó URL-címet.</span><span class="sxs-lookup"><span data-stu-id="f1406-158">In the property pane on the right, under **Script source**, add an external or relative URL for the external script source.</span></span> <span data-ttu-id="f1406-159">Ezt követően konfigurálja a szükséges egyéb beállításokat.</span><span class="sxs-lookup"><span data-stu-id="f1406-159">Then configure other options as you require.</span></span>
1. <span data-ttu-id="f1406-160">Válassza a **Mentés** parancsot, majd válassza a **Szerkesztés befejezése** elemet.</span><span class="sxs-lookup"><span data-stu-id="f1406-160">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="f1406-161">Válassza a **Közzététel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1406-161">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f1406-162">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="f1406-162">Additional resources</span></span>

[<span data-ttu-id="f1406-163">Embléma hozzáadása</span><span class="sxs-lookup"><span data-stu-id="f1406-163">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="f1406-164">Webhely témájának kiválasztása</span><span class="sxs-lookup"><span data-stu-id="f1406-164">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="f1406-165">A CSS felülíró fájljainak használata</span><span class="sxs-lookup"><span data-stu-id="f1406-165">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="f1406-166">Kedvencek ikon hozzáadása</span><span class="sxs-lookup"><span data-stu-id="f1406-166">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="f1406-167">Üdvözlő üzenet hozzáadása</span><span class="sxs-lookup"><span data-stu-id="f1406-167">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="f1406-168">Szerzői jogi értesítés hozzáadása</span><span class="sxs-lookup"><span data-stu-id="f1406-168">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="f1406-169">Nyelvek hozzáadása a webhelyhez</span><span class="sxs-lookup"><span data-stu-id="f1406-169">Add languages to your site</span></span>](add-languages-to-site.md)
