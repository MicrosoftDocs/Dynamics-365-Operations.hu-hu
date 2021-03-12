---
title: Dynamics 365 Commerce értékelési környezet választható funkcióinak konfigurálása
description: Ez a témakör bemutatja, hogyan lehet opcionális funkciókat konfigurálni egy Microsoft Dynamics 365 Commerce értékelési környezethez.
author: psimolin
manager: annbe
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6639de250557ce9a25fc2cde3807abf64b0ddc18
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993450"
---
# <a name="configure-optional-features-for-a-dynamics-365-commerce-evaluation-environment"></a><span data-ttu-id="a9bc6-103">Dynamics 365 Commerce értékelési környezet választható funkcióinak konfigurálása</span><span class="sxs-lookup"><span data-stu-id="a9bc6-103">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a9bc6-104">Ez a témakör bemutatja, hogyan lehet opcionális funkciókat konfigurálni egy Microsoft Dynamics 365 Commerce értékelési környezethez.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-104">This topic explains how to configure optional features for a Microsoft Dynamics 365 Commerce evaluation environment.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a9bc6-105">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="a9bc6-105">Prerequisites</span></span>

<span data-ttu-id="a9bc6-106">Ha ki szeretné próbálni tranzakciós e-mail funkciókat, akkor az alábbi előfeltételeknek kell teljesülniük:</span><span class="sxs-lookup"><span data-stu-id="a9bc6-106">If you want to evaluate the transactional email features, the following prerequisites must be met:</span></span>

- <span data-ttu-id="a9bc6-107">Rendelkezik egy e-mail kiszolgálóval (Egyszerű üzenetátviteli protokoll \[SMTP\] kiszolgáló), amelyet abból a Microsoft Azure-előfizetésből lehet használni, ahol az értékelési környezetet létesítette.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-107">You have an available email server (Simple Mail Transfer Protocol \[SMTP\] server) that can be used from the Microsoft Azure subscription where you provisioned the evaluation environment.</span></span>
- <span data-ttu-id="a9bc6-108">A kiszolgáló teljes képzésű tartományneve (FQDN)/IP-címe, SMTP-portszáma és a hitelesítési adatok rendelkezésre állnak.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-108">You have the server's fully qualified domain name (FQDN)/IP address, SMTP port number, and authentication details available.</span></span>

## <a name="configure-the-image-back-end"></a><span data-ttu-id="a9bc6-109">A képháttér konfigurálása</span><span class="sxs-lookup"><span data-stu-id="a9bc6-109">Configure the image back end</span></span>

### <a name="find-your-media-base-url"></a><span data-ttu-id="a9bc6-110">A média alap URL-címének megkeresése</span><span class="sxs-lookup"><span data-stu-id="a9bc6-110">Find your media base URL</span></span>

> [!NOTE]
> <span data-ttu-id="a9bc6-111">A művelet végrehajtása előtt be kell fejeznie a [Webhely beállítása a Commerce alkalmazásban](cpe-post-provisioning.md#set-up-your-site-in-commerce) témakör lépéseit.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-111">Before you can complete this procedure, you must complete the steps in [Set up your site in Commerce](cpe-post-provisioning.md#set-up-your-site-in-commerce).</span></span>

1. <span data-ttu-id="a9bc6-112">Jelentkezzen be a Commerce webhelykészítőbe azzal az URL-címmel, amelyet az e-kereskedelem inicializálásakor a létesítés során megadott (lásd: [E-kereskedelem inicializálása](provisioning-guide.md#initialize-e-commerce)).</span><span class="sxs-lookup"><span data-stu-id="a9bc6-112">Sign in to the Commerce site builder by using the URL you made a note of when you initialized e-Commerce during provisioning (see [Initialize e-Commerce](provisioning-guide.md#initialize-e-commerce)).</span></span>
1. <span data-ttu-id="a9bc6-113">Nyissa meg a **Gyár** webhelyet.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-113">Open the **Fabrikam** site.</span></span>
1. <span data-ttu-id="a9bc6-114">A bal oldali menüben válassza az **Médiatár** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-114">On the menu on the left, select **Media Library**.</span></span>
1. <span data-ttu-id="a9bc6-115">Válasszon ki egyetlen képeszközt.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-115">Select any single image asset.</span></span>
1. <span data-ttu-id="a9bc6-116">A jobb oldali tulajdonságvizsgálóban keresse meg a **Nyilvános URL** tulajdonságot.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-116">In the property inspector on the right, find the **Public URL** property.</span></span> <span data-ttu-id="a9bc6-117">Az érték egy URL.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-117">The value is a URL.</span></span> <span data-ttu-id="a9bc6-118">Egy példa:</span><span class="sxs-lookup"><span data-stu-id="a9bc6-118">Here is an example:</span></span>

    <span data-ttu-id="a9bc6-119">`https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/MA1nQC`.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-119">`https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/MA1nQC`.</span></span>

1. <span data-ttu-id="a9bc6-120">Cserélje le az URL-címben szereplő utolsó azonosítót (az előző példában **MA1nQC**) a következő karakterlánccal: **search?fileName=**.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-120">Replace the last identifier in the URL (**MA1nQC** in the preceding example) with the string **search?fileName=**.</span></span> <span data-ttu-id="a9bc6-121">A csere után így néz ki a példa URL:</span><span class="sxs-lookup"><span data-stu-id="a9bc6-121">Here is what the example URL looks like after this change is made:</span></span>

    `https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/search?fileName=`

    <span data-ttu-id="a9bc6-122">Ez az URL-cím a média alap URL-je.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-122">This URL is your media base URL.</span></span> <span data-ttu-id="a9bc6-123">Jegyezze fel.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-123">Make a note of it.</span></span>

### <a name="update-the-media-base-url"></a><span data-ttu-id="a9bc6-124">A média alap URL-cím frissítése</span><span class="sxs-lookup"><span data-stu-id="a9bc6-124">Update the media base URL</span></span>

1. <span data-ttu-id="a9bc6-125">Bejelentkezés a Commerce központba.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-125">Sign in to Commerce headquarters.</span></span>
1. <span data-ttu-id="a9bc6-126">A bal oldali menü használatával nyissa meg a **Modulok \> Kiskereskedelem és kereskedelem \> Csatorna beállítása \> Csatornaprofilok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-126">Use the menu on the left to go to **Modules \> Retail and commerce \> Channel setup \> Channel profiles**.</span></span>
1. <span data-ttu-id="a9bc6-127">Válassza ki a **Szerkesztés** opciót.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-127">Select **Edit**.</span></span>
1. <span data-ttu-id="a9bc6-128">A **Profil tulajdonságai** alatt cserélje le a **Médiakiszolgáló alap URL-címe** tulajdonságot a korábban létrehozott média alap URL-címre.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-128">Under **Profile properties**, replace the value for the **Media Server Base URL** property with the media base URL that you created earlier.</span></span>
1. <span data-ttu-id="a9bc6-129">Válassza ki a másik csatornát, az **scXXXXXXXXX** nevűt.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-129">Select the channel that is named **scXXXXXXXXX**.</span></span>
1. <span data-ttu-id="a9bc6-130">A **Profil tulajdonságai** területen kattintson a **Hozzáadás** gombra.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-130">Under **Profile properties**, select **Add**.</span></span>
1. <span data-ttu-id="a9bc6-131">A hozzáadott tulajdonság esetében válassza a **Médiakiszolgáló alap URL-címe** lehetőséget tulajdonságkulcsként.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-131">For the property that was added, select **Media Server Base URL** as the property key.</span></span> <span data-ttu-id="a9bc6-132">A tulajdonságértékként adja meg a korábban létrehozott média alap URL-címét.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-132">As the property value, enter the media base URL that you created earlier.</span></span>
1. <span data-ttu-id="a9bc6-133">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-133">Select **Save**.</span></span>

## <a name="configure-and-test-the-email-server"></a><span data-ttu-id="a9bc6-134">E-mail-kiszolgáló konfigurálása és tesztelése</span><span class="sxs-lookup"><span data-stu-id="a9bc6-134">Configure and test the email server</span></span>

> [!NOTE]
> <span data-ttu-id="a9bc6-135">Az itt megadott SMTP-kiszolgálónak vagy e-mail szolgáltatásnak elérhetőnek kell lennie a környezethez használt Azure-előfizetésből.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-135">The SMTP server or email service that you enter here must be accessible from the Azure subscription that you're using for the environment.</span></span>

1. <span data-ttu-id="a9bc6-136">Bejelentkezés a Commerce központba.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-136">Sign in to Commerce headquarters.</span></span>
1. <span data-ttu-id="a9bc6-137">A bal oldali menü használatával nyissa meg a **Modulok \> Kiskereskedelem és kereskedelem \> Központ beállítása \> Paraméterek \> E-mail-paraméterek**.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-137">Use the menu on the left to go to **Modules \> Retail and Commerce \> Headquarters setup \> Parameters \> Email parameters**.</span></span>
1. <span data-ttu-id="a9bc6-138">Az **SMTP-beállítások** lapon a **Kimenő levelek kiszolgálója** mezőjébe írja be az SMTP-kiszolgáló vagy e-mail-szolgáltatás FQDN-nevét vagy IP-címét.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-138">On the **SMTP settings** tab, in the **Outgoing mail server** field, enter the FQDN or IP address of your SMTP server or email service.</span></span>
1. <span data-ttu-id="a9bc6-139">Írja be az **SMTP portszáma** mezőbe a port számát.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-139">In the **SMTP port number** field, enter the port number.</span></span> <span data-ttu-id="a9bc6-140">(Ha nem a Secure Sockets Layer \[SSL\] protokollt használja, az alapértelmezett portszám **25**.)</span><span class="sxs-lookup"><span data-stu-id="a9bc6-140">(If you aren't using Secure Sockets Layer \[SSL\], the default port number is **25**.)</span></span>
1. <span data-ttu-id="a9bc6-141">Ha hitelesítés szükséges, írja be az értékeket a **Felhasználónév** és a **Jelszó** mezőkbe.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-141">If authentication is required, enter values in the **User name** and **Password** fields.</span></span>
1. <span data-ttu-id="a9bc6-142">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-142">Select **Save**.</span></span>
1. <span data-ttu-id="a9bc6-143">Válassza a **Frissítés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-143">Select **Refresh**.</span></span>
1. <span data-ttu-id="a9bc6-144">A **Teszt-e-mail** lapon az **E-mail-szolgáltató** mezőben válassza ki az **SMTP** elemet.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-144">On the **Test email** tab, in the **Email provider** field, select **SMTP**.</span></span>
1. <span data-ttu-id="a9bc6-145">A **Címzett** mezőbe írja be azt az e-mail címet, amelyre a teszt-e-mailt kézbesíteni kívánja.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-145">In the **Send to** field, enter the email address that the test email should be delivered to.</span></span>
1. <span data-ttu-id="a9bc6-146">Válassza a **Teszt-e-mail küldése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-146">Select **Send test email**.</span></span>

## <a name="configure-email-templates"></a><span data-ttu-id="a9bc6-147">E-mail-sablonok konfigurálása</span><span class="sxs-lookup"><span data-stu-id="a9bc6-147">Configure email templates</span></span>

<span data-ttu-id="a9bc6-148">Az e-mail-sablont minden olyan tranzakciós eseményhez, amelyre e-maileket szeretne küldeni, frissíteni kell egy érvényes feladói e-mail-címmel.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-148">For each transactional event that you want to send emails for, you must update the email template with a valid sender email address.</span></span>

1. <span data-ttu-id="a9bc6-149">Bejelentkezés a Commerce központba.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-149">Sign in to Commerce headquarters.</span></span>
1. <span data-ttu-id="a9bc6-150">A bal oldali menü használatával nyissa meg a **Modulok \> Kiskereskedelem és kereskedelem \> Központ beállítása \> Paraméterek \> Szervezeti e-mail-sablonok**.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-150">Use the menu on the left to go to **Modules \> Retail and Commerce \> Headquarters setup \> Parameters \> Organization email templates**.</span></span>
1. <span data-ttu-id="a9bc6-151">Válassza ki a **Lista megjelenítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-151">Select **Show list**.</span></span>
1. <span data-ttu-id="a9bc6-152">A lista minden sablonja esetén hajtsa végre az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="a9bc6-152">For each template in the list, follow these steps:</span></span>

    1. <span data-ttu-id="a9bc6-153">A **Feladó e-mail címe** mezőbe írja be a feladó e-mail címét.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-153">In the **Sender email** field, enter the sender email address.</span></span>
    1. <span data-ttu-id="a9bc6-154">Nem kötelező: A **Feladó neve** mezőben adja meg a feladó neveként használandó nevet.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-154">Optional: In the **Sender name** field, enter the name that should be used as the sender name.</span></span>

1. <span data-ttu-id="a9bc6-155">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-155">Select **Save**.</span></span>

## <a name="customize-email-templates"></a><span data-ttu-id="a9bc6-156">E-mail-sablonok testreszabása</span><span class="sxs-lookup"><span data-stu-id="a9bc6-156">Customize email templates</span></span>

<span data-ttu-id="a9bc6-157">Célszerű lehet testreszabni az e-mail sablonokat, hogy azok különböző képeket használhassanak.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-157">You might want to customize the email templates so that they use different images.</span></span> <span data-ttu-id="a9bc6-158">Előfordulhat az is, hogy frissíteni szeretné a sablonokban lévő hivatkozásokat, hogy azok az értékelési környezetbe kerüljenek.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-158">Or you might want to update the links in the templates so that they go to your evaluation environment.</span></span> <span data-ttu-id="a9bc6-159">Ez az eljárás leírja, hogyan lehet letölteni az alapértelmezett sablonokat, illetve hogyan szabhatja testre és frissítheti a sablonokat a rendszerben.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-159">This procedure explains how to download the default templates, customize them, and update the templates in the system.</span></span>

1. <span data-ttu-id="a9bc6-160">A böngésző használatával letöltheti a [Microsoft Dynamics 365 Commerce értékelés alapértelmezett e-mail-sablonok .zip fájlját](https://download.microsoft.com/download/d/7/b/d7b6c4d4-fe09-4922-9551-46bbb29d202d/Commerce.Preview.Default.Email.Templates.zip) a számítógépére.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-160">In a web browser, download the [Microsoft Dynamics 365 Commerce Evaluation default email templates zip file](https://download.microsoft.com/download/d/7/b/d7b6c4d4-fe09-4922-9551-46bbb29d202d/Commerce.Preview.Default.Email.Templates.zip) to your local computer.</span></span> <span data-ttu-id="a9bc6-161">Ez a fájl a következő HTML-dokumentumokat tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="a9bc6-161">This file contains the following HTML documents:</span></span>

    - <span data-ttu-id="a9bc6-162">Rendelés megerősítési sablon</span><span class="sxs-lookup"><span data-stu-id="a9bc6-162">Order confirmation template</span></span>
    - <span data-ttu-id="a9bc6-163">Ajándékutalvány-sablon kiadása</span><span class="sxs-lookup"><span data-stu-id="a9bc6-163">Issue gift card template</span></span>
    - <span data-ttu-id="a9bc6-164">Új rendeléssablon</span><span class="sxs-lookup"><span data-stu-id="a9bc6-164">New order template</span></span>
    - <span data-ttu-id="a9bc6-165">Csomagrendelési sablon</span><span class="sxs-lookup"><span data-stu-id="a9bc6-165">Pack order template</span></span>
    - <span data-ttu-id="a9bc6-166">Kitárolás rendelési sablon</span><span class="sxs-lookup"><span data-stu-id="a9bc6-166">Pick order template</span></span>

1. <span data-ttu-id="a9bc6-167">A sablonokat a szöveg- vagy HTML-szerkesztő segítségével szabhatja testre.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-167">Customize the templates by using a text or HTML editor.</span></span> <span data-ttu-id="a9bc6-168">A [támogatott tokenek](#supported-tokens-in-the-email-template) listája a jelen témakör későbbi részében található.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-168">See the list of [supported tokens](#supported-tokens-in-the-email-template) later in this topic.</span></span>
1. <span data-ttu-id="a9bc6-169">Bejelentkezés a Commerce alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-169">Sign in to Commerce.</span></span>
1. <span data-ttu-id="a9bc6-170">A bal oldali menü használatával nyissa meg a **Modulok \> Szervezet felügyelete \> Beállítás \> Szervezeti e-mail-sablonok** elemet.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-170">Use the menu on the left to go to **Modules \> Organization administration \> Setup \> Organization email templates**.</span></span>
1. <span data-ttu-id="a9bc6-171">A bal oldali lista kibontásával megjelenítheti az összes sablont.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-171">Expand the list on the left to see all the templates.</span></span>
1. <span data-ttu-id="a9bc6-172">Minden testreszabni kívánt sablonhoz hajtsa végre az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="a9bc6-172">For each template that you want to customize, follow these steps:</span></span>

    1. <span data-ttu-id="a9bc6-173">Válassza ki a sablont a listából.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-173">Select the template in the list.</span></span>
    1. <span data-ttu-id="a9bc6-174">Az **E-mail-üzenet tartalma** területen válassza ki a megfelelő nyelvi verziót a listából.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-174">Under **Email message content**, select the appropriate language version in the list.</span></span> <span data-ttu-id="a9bc6-175">(Az alapértelmezett nyelv az **en-us**.)</span><span class="sxs-lookup"><span data-stu-id="a9bc6-175">(The default language is **en-us**.)</span></span>
    1. <span data-ttu-id="a9bc6-176">Az **E-mail-üzenet tartalma** alatt válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-176">Under **Email message content**, select **Edit**.</span></span> <span data-ttu-id="a9bc6-177">Megjelenik az **E-mail-sablon feltöltése** ablaktábla.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-177">The **Upload email template** pane appears.</span></span>
    1. <span data-ttu-id="a9bc6-178">Válassza a **Tallózás** lehetőséget, és keresse meg azt a HTML-fájlt, amely a testreszabott tartalommal rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-178">Select **Browse**, and find the HTML file that has the customized content.</span></span>
    1. <span data-ttu-id="a9bc6-179">Válassza a **Feltöltés** elemet.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-179">Select **Upload**.</span></span> <span data-ttu-id="a9bc6-180">A sablon fel lesz töltve a rendszerbe, és megjelenik egy előnézet.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-180">The template is uploaded into the system, and a preview is shown.</span></span>
    1. <span data-ttu-id="a9bc6-181">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-181">Select **OK**.</span></span>
    1. <span data-ttu-id="a9bc6-182">Opcionális: A sablon **Tárgy** tulajdonságának testreszabása.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-182">Optional: Customize the **Subject** property of the template.</span></span>
    1. <span data-ttu-id="a9bc6-183">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-183">Select **Save**.</span></span>

### <a name="supported-tokens-in-the-email-template"></a><span data-ttu-id="a9bc6-184">Az e-mail-sablonban támogatott tokenek</span><span class="sxs-lookup"><span data-stu-id="a9bc6-184">Supported tokens in the email template</span></span>

<span data-ttu-id="a9bc6-185">Ezeket a tokeneket az e-mail renderelése során a program lecseréli a vevőkre és a rendelésre vonatkozó tényleges értékekre.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-185">When the email is rendered, these tokens are replaced with actual values that apply to the customer and the customer's order.</span></span>

#### <a name="sales-order"></a><span data-ttu-id="a9bc6-186">Értékesítési rendelés</span><span class="sxs-lookup"><span data-stu-id="a9bc6-186">Sales order</span></span>

<span data-ttu-id="a9bc6-187">A következő tokenek érvényesek a teljes értékesítési rendelésre.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-187">The following tokens apply to the overall sales order.</span></span>

| <span data-ttu-id="a9bc6-188">A token neve</span><span class="sxs-lookup"><span data-stu-id="a9bc6-188">Name of the token</span></span> | <span data-ttu-id="a9bc6-189">Jogkivonat</span><span class="sxs-lookup"><span data-stu-id="a9bc6-189">Token</span></span> |
|-------------------|-------|
| <span data-ttu-id="a9bc6-190">Rendelés száma</span><span class="sxs-lookup"><span data-stu-id="a9bc6-190">Order number</span></span>      | <span data-ttu-id="a9bc6-191">%salesid%</span><span class="sxs-lookup"><span data-stu-id="a9bc6-191">%salesid%</span></span> |
| <span data-ttu-id="a9bc6-192">Vevő neve</span><span class="sxs-lookup"><span data-stu-id="a9bc6-192">Customer's name</span></span>   | <span data-ttu-id="a9bc6-193">%customername%</span><span class="sxs-lookup"><span data-stu-id="a9bc6-193">%customername%</span></span> |
| <span data-ttu-id="a9bc6-194">Szállítási cím</span><span class="sxs-lookup"><span data-stu-id="a9bc6-194">Delivery address</span></span>  | <span data-ttu-id="a9bc6-195">%deliveryaddress%</span><span class="sxs-lookup"><span data-stu-id="a9bc6-195">%deliveryaddress%</span></span> |
| <span data-ttu-id="a9bc6-196">Számlázási cím</span><span class="sxs-lookup"><span data-stu-id="a9bc6-196">Billing address</span></span>   | <span data-ttu-id="a9bc6-197">%customeraddress%</span><span class="sxs-lookup"><span data-stu-id="a9bc6-197">%customeraddress%</span></span> |
| <span data-ttu-id="a9bc6-198">Megrendelési dátum</span><span class="sxs-lookup"><span data-stu-id="a9bc6-198">Order date</span></span>        | <span data-ttu-id="a9bc6-199">%shipdate%</span><span class="sxs-lookup"><span data-stu-id="a9bc6-199">%shipdate%</span></span> |
| <span data-ttu-id="a9bc6-200">Kézbesítés módja</span><span class="sxs-lookup"><span data-stu-id="a9bc6-200">Delivery mode</span></span>     | <span data-ttu-id="a9bc6-201">%modeofdelivery%</span><span class="sxs-lookup"><span data-stu-id="a9bc6-201">%modeofdelivery%</span></span> |
| <span data-ttu-id="a9bc6-202">Engedmény</span><span class="sxs-lookup"><span data-stu-id="a9bc6-202">Discount</span></span>          | <span data-ttu-id="a9bc6-203">%discount%</span><span class="sxs-lookup"><span data-stu-id="a9bc6-203">%discount%</span></span> |
| <span data-ttu-id="a9bc6-204">Áfa</span><span class="sxs-lookup"><span data-stu-id="a9bc6-204">Sales tax</span></span>         | <span data-ttu-id="a9bc6-205">%tax%</span><span class="sxs-lookup"><span data-stu-id="a9bc6-205">%tax%</span></span> |
| <span data-ttu-id="a9bc6-206">Rendelés végösszege</span><span class="sxs-lookup"><span data-stu-id="a9bc6-206">Order total</span></span>       | <span data-ttu-id="a9bc6-207">%total%</span><span class="sxs-lookup"><span data-stu-id="a9bc6-207">%total%</span></span> |

#### <a name="sales-line"></a><span data-ttu-id="a9bc6-208">Értékesítési sor</span><span class="sxs-lookup"><span data-stu-id="a9bc6-208">Sales line</span></span>

<span data-ttu-id="a9bc6-209">A következő tokeneket cseréli ki a rendszer értékekre az egyes termékek esetében.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-209">The following tokens are replaced with values for each product in the order.</span></span>

> [!NOTE]
> <span data-ttu-id="a9bc6-210">Tegye a **Terméklista – kezdés** tokent a HTML-blokk elejére, amely minden termékre megismétlődik, majd a blokk végén helyezze el a **Terméklista – befejezés** tokent.</span><span class="sxs-lookup"><span data-stu-id="a9bc6-210">Put the **Product list - start** token at the beginning of the HTML block that is repeated for every product, and put the **Product list - end** token at the end of the block.</span></span>

| <span data-ttu-id="a9bc6-211">A token neve</span><span class="sxs-lookup"><span data-stu-id="a9bc6-211">Name of the token</span></span>      | <span data-ttu-id="a9bc6-212">Token</span><span class="sxs-lookup"><span data-stu-id="a9bc6-212">Token</span></span> |
|------------------------|-------|
| <span data-ttu-id="a9bc6-213">Terméklista – kezdés</span><span class="sxs-lookup"><span data-stu-id="a9bc6-213">Product list - start</span></span>   | \<!--%tablebegin.salesline% --\> |
| <span data-ttu-id="a9bc6-214">Terméklista – befejezés</span><span class="sxs-lookup"><span data-stu-id="a9bc6-214">Product list - end</span></span>     | \<!--%tableend.salesline%--\> |
| <span data-ttu-id="a9bc6-215">Termék neve</span><span class="sxs-lookup"><span data-stu-id="a9bc6-215">Product name</span></span>           | <span data-ttu-id="a9bc6-216">%lineproductname%</span><span class="sxs-lookup"><span data-stu-id="a9bc6-216">%lineproductname%</span></span> |
| <span data-ttu-id="a9bc6-217">Leírás</span><span class="sxs-lookup"><span data-stu-id="a9bc6-217">Description</span></span>            | <span data-ttu-id="a9bc6-218">%lineproductdescription%</span><span class="sxs-lookup"><span data-stu-id="a9bc6-218">%lineproductdescription%</span></span> |
| <span data-ttu-id="a9bc6-219">Mennyiség</span><span class="sxs-lookup"><span data-stu-id="a9bc6-219">Quantity</span></span>               | <span data-ttu-id="a9bc6-220">%linequantity%</span><span class="sxs-lookup"><span data-stu-id="a9bc6-220">%linequantity%</span></span> |
| <span data-ttu-id="a9bc6-221">Sor egységára</span><span class="sxs-lookup"><span data-stu-id="a9bc6-221">Line unit price</span></span>        | <span data-ttu-id="a9bc6-222">%lineprice% (verify)</span><span class="sxs-lookup"><span data-stu-id="a9bc6-222">%lineprice% (verify)</span></span> |
| <span data-ttu-id="a9bc6-223">sortétel összege</span><span class="sxs-lookup"><span data-stu-id="a9bc6-223">line item total</span></span>        | <span data-ttu-id="a9bc6-224">%linenetamount%</span><span class="sxs-lookup"><span data-stu-id="a9bc6-224">%linenetamount%</span></span> |
| <span data-ttu-id="a9bc6-225">sorkedvezmény</span><span class="sxs-lookup"><span data-stu-id="a9bc6-225">line discount</span></span>          | <span data-ttu-id="a9bc6-226">%linediscount%</span><span class="sxs-lookup"><span data-stu-id="a9bc6-226">%linediscount%</span></span> |
| <span data-ttu-id="a9bc6-227">Szállítási dátum</span><span class="sxs-lookup"><span data-stu-id="a9bc6-227">Ship date</span></span>              | <span data-ttu-id="a9bc6-228">%lineshipdate%</span><span class="sxs-lookup"><span data-stu-id="a9bc6-228">%lineshipdate%</span></span> |
| <span data-ttu-id="a9bc6-229">Beszerzési mód</span><span class="sxs-lookup"><span data-stu-id="a9bc6-229">Procurement method</span></span>     | <span data-ttu-id="a9bc6-230">%linedeliverymode%</span><span class="sxs-lookup"><span data-stu-id="a9bc6-230">%linedeliverymode%</span></span> |
| <span data-ttu-id="a9bc6-231">szállítási cím</span><span class="sxs-lookup"><span data-stu-id="a9bc6-231">delivery address</span></span>       | <span data-ttu-id="a9bc6-232">%linedeliveryaddress%</span><span class="sxs-lookup"><span data-stu-id="a9bc6-232">%linedeliveryaddress%</span></span> |
| <span data-ttu-id="a9bc6-233">A sor értékesítési egysége</span><span class="sxs-lookup"><span data-stu-id="a9bc6-233">Sales unit of the line</span></span> | <span data-ttu-id="a9bc6-234">%lineunit%</span><span class="sxs-lookup"><span data-stu-id="a9bc6-234">%lineunit%</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="a9bc6-235">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="a9bc6-235">Additional resources</span></span>

[<span data-ttu-id="a9bc6-236">Dynamics 365 Commerce értékelési környezet áttekintése</span><span class="sxs-lookup"><span data-stu-id="a9bc6-236">Dynamics 365 Commerce evaluation environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="a9bc6-237">Dynamics 365 Commerce értékelési környezet kiépítése</span><span class="sxs-lookup"><span data-stu-id="a9bc6-237">Provision a Dynamics 365 Commerce evaluation environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="a9bc6-238">Dynamics 365 Commerce értékelési környezet konfigurálása</span><span class="sxs-lookup"><span data-stu-id="a9bc6-238">Configure a Dynamics 365 Commerce evaluation environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="a9bc6-239">BOPIS konfigurálása Dynamics 365 Commerce értékelési környezetben</span><span class="sxs-lookup"><span data-stu-id="a9bc6-239">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>](cpe-bopis.md)

[<span data-ttu-id="a9bc6-240">Dynamics 365 Commerce értékelési környezet GYIK</span><span class="sxs-lookup"><span data-stu-id="a9bc6-240">Dynamics 365 Commerce evaluation environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="a9bc6-241">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="a9bc6-241">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="a9bc6-242">Retail Cloud Scale Unit (RCSU)</span><span class="sxs-lookup"><span data-stu-id="a9bc6-242">Retail Cloud Scale Unit (RCSU)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="a9bc6-243">Microsoft Azure-portál</span><span class="sxs-lookup"><span data-stu-id="a9bc6-243">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="a9bc6-244">Dynamics 365 Commerce-webhely</span><span class="sxs-lookup"><span data-stu-id="a9bc6-244">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)
