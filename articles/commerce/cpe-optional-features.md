---
title: A Dynamics 365 Commerce előzetes verziós környezet választható funkcióinak konfigurálása
description: Ez a témakör bemutatja, hogyan lehet opcionális funkciókat konfigurálni egy Microsoft Dynamics 365 Commerce előzetes környezethez.
author: psimolin
manager: annbe
ms.date: 12/10/2019
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
ms.author: psimolin
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 4b17f8e9b0d8a9a62714d0073561e66642b2eaf9
ms.sourcegitcommit: 12b9d6f2dd24e52e46487748c848864909af6967
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/14/2020
ms.locfileid: "3057740"
---
# <a name="configure-optional-features-for-a-dynamics-365-commerce-preview-environment"></a><span data-ttu-id="a8b14-103">A Dynamics 365 Commerce előzetes verziós környezet választható funkcióinak konfigurálása</span><span class="sxs-lookup"><span data-stu-id="a8b14-103">Configure optional features for a Dynamics 365 Commerce preview environment</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="a8b14-104">Ez a témakör bemutatja, hogyan lehet opcionális funkciókat konfigurálni egy Microsoft Dynamics 365 Commerce előzetes környezethez.</span><span class="sxs-lookup"><span data-stu-id="a8b14-104">This topic explains how to configure optional features for a Microsoft Dynamics 365 Commerce preview environment.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a8b14-105">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="a8b14-105">Prerequisites</span></span>

<span data-ttu-id="a8b14-106">Ha ki szeretné próbálni tranzakciós e-mail funkciókat, akkor az alábbi előfeltételeknek kell teljesülniük:</span><span class="sxs-lookup"><span data-stu-id="a8b14-106">If you want to evaluate the transactional email features, the following prerequisites must be met:</span></span>

- <span data-ttu-id="a8b14-107">Rendelkezik egy e-mail kiszolgálóval (Egyszerű üzenetátviteli protokoll \[SMTP\] kiszolgáló), amelyet abból a Microsoft Azure-előfizetésből lehet használni, ahol az előzetes környezetet létesítette.</span><span class="sxs-lookup"><span data-stu-id="a8b14-107">You have an available email server (Simple Mail Transfer Protocol \[SMTP\] server) that can be used from the Microsoft Azure subscription where you provisioned the preview environment.</span></span>
- <span data-ttu-id="a8b14-108">A kiszolgáló teljes képzésű tartományneve (FQDN)/IP-címe, SMTP-portszáma és a hitelesítési adatok rendelkezésre állnak.</span><span class="sxs-lookup"><span data-stu-id="a8b14-108">You have the server's fully qualified domain name (FQDN)/IP address, SMTP port number, and authentication details available.</span></span>

<span data-ttu-id="a8b14-109">Ha az új omnicsatornás képek fogyasztásával szeretné értékelni a Digitális eszközkezelés funkciókat, akkor rendelkezésre kell állnia a tartalomkezelő rendszer (CMS) bérlőnevének.</span><span class="sxs-lookup"><span data-stu-id="a8b14-109">If you want to evaluate Digital Asset Management features by ingesting new omni-channel images, you must have the name of your content management system (CMS) tenant available.</span></span> <span data-ttu-id="a8b14-110">A név megtalálásához a jelen témakör későbbi részében talál útmutatást.</span><span class="sxs-lookup"><span data-stu-id="a8b14-110">Instructions for finding this name are provided later in this topic.</span></span> <span data-ttu-id="a8b14-111">>>>(Q: Hol vannak az utasítások?)</span><span class="sxs-lookup"><span data-stu-id="a8b14-111">>>>(Q: where are the instructions?)</span></span>

## <a name="configure-the-image-back-end"></a><span data-ttu-id="a8b14-112">A képháttér konfigurálása</span><span class="sxs-lookup"><span data-stu-id="a8b14-112">Configure the image back end</span></span>

### <a name="find-your-media-base-url"></a><span data-ttu-id="a8b14-113">A média alap URL-címének megkeresése</span><span class="sxs-lookup"><span data-stu-id="a8b14-113">Find your media base URL</span></span>

> [!NOTE]
> <span data-ttu-id="a8b14-114">A művelet végrehajtása előtt be kell fejeznie a [Webhely beállítása a Commerce alkalmazásban](cpe-post-provisioning.md#set-up-your-site-in-commerce) témakör lépéseit.</span><span class="sxs-lookup"><span data-stu-id="a8b14-114">Before you can complete this procedure, you must complete the steps in [Set up your site in Commerce](cpe-post-provisioning.md#set-up-your-site-in-commerce).</span></span>

1. <span data-ttu-id="a8b14-115">Jelentkezzen be a Commerce webhelykezelő eszközébe azzal az URL-címmel, amelyet az e-kereskedelem inicializálásakor a létesítés során megadott (lásd: [E-kereskedelem inicializálása](provisioning-guide.md#initialize-e-commerce)).</span><span class="sxs-lookup"><span data-stu-id="a8b14-115">Sign in to the Commerce site management tool by using the URL you made a note of when you initialized e-Commerce during provisioning (see [Initialize e-Commerce](provisioning-guide.md#initialize-e-commerce)).</span></span>
1. <span data-ttu-id="a8b14-116">Nyissa meg a **Gyár** webhelyet.</span><span class="sxs-lookup"><span data-stu-id="a8b14-116">Open the **Fabrikam** site.</span></span>
1. <span data-ttu-id="a8b14-117">A bal oldali menüben válassza az **Eszközök** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a8b14-117">On the menu on the left, select **Assets**.</span></span>
1. <span data-ttu-id="a8b14-118">Válasszon ki egyetlen képeszközt.</span><span class="sxs-lookup"><span data-stu-id="a8b14-118">Select any single image asset.</span></span>
1. <span data-ttu-id="a8b14-119">A jobb oldali tulajdonságvizsgálóban keresse meg a **Nyilvános URL** tulajdonságot.</span><span class="sxs-lookup"><span data-stu-id="a8b14-119">In the property inspector on the right, find the **Public URL** property.</span></span> <span data-ttu-id="a8b14-120">Az érték egy URL.</span><span class="sxs-lookup"><span data-stu-id="a8b14-120">The value is a URL.</span></span> <span data-ttu-id="a8b14-121">Egy példa:</span><span class="sxs-lookup"><span data-stu-id="a8b14-121">Here is an example:</span></span>

    <span data-ttu-id="a8b14-122">`https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/MA1nQC`.</span><span class="sxs-lookup"><span data-stu-id="a8b14-122">`https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/MA1nQC`.</span></span>

1. <span data-ttu-id="a8b14-123">Cserélje le az URL-címben szereplő utolsó azonosítót (az előző példában **MA1nQC**) a következő karakterlánccal: **search?fileName=**.</span><span class="sxs-lookup"><span data-stu-id="a8b14-123">Replace the last identifier in the URL (**MA1nQC** in the preceding example) with the string **search?fileName=**.</span></span> <span data-ttu-id="a8b14-124">A csere után így néz ki a példa URL:</span><span class="sxs-lookup"><span data-stu-id="a8b14-124">Here is what the example URL looks like after this change is made:</span></span>

    `https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/search?fileName=`

    <span data-ttu-id="a8b14-125">Ez az URL-cím a média alap URL-je.</span><span class="sxs-lookup"><span data-stu-id="a8b14-125">This URL is your media base URL.</span></span> <span data-ttu-id="a8b14-126">Jegyezze fel.</span><span class="sxs-lookup"><span data-stu-id="a8b14-126">Make a note of it.</span></span>

### <a name="update-the-media-base-url"></a><span data-ttu-id="a8b14-127">A média alap URL-cím frissítése</span><span class="sxs-lookup"><span data-stu-id="a8b14-127">Update the media base URL</span></span>

1. <span data-ttu-id="a8b14-128">Jelentkezzen be a Dynamics 365 Commerce alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="a8b14-128">Sign in to Dynamics 365 Commerce.</span></span>
1. <span data-ttu-id="a8b14-129">A bal oldali menü használatával nyissa meg a **Modulok \> Kiskereskedelem és kereskedelem \> Csatorna beállítása \> Csatornaprofilok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a8b14-129">Use the menu on the left to go to **Modules \> Retail and commerce \> Channel setup \> Channel profiles**.</span></span>
1. <span data-ttu-id="a8b14-130">Válassza ki a **Szerkesztés** opciót.</span><span class="sxs-lookup"><span data-stu-id="a8b14-130">Select **Edit**.</span></span>
1. <span data-ttu-id="a8b14-131">A **Profil tulajdonságai** alatt cserélje le a **Médiakiszolgáló alap URL-címe** tulajdonságot a korábban létrehozott média alap URL-címre.</span><span class="sxs-lookup"><span data-stu-id="a8b14-131">Under **Profile properties**, replace the value for the **Media Server Base URL** property with the media base URL that you created earlier.</span></span>
1. <span data-ttu-id="a8b14-132">Válassza ki a másik csatornát a bal oldali listából az **Alapértelmezett** csatorna alatt.</span><span class="sxs-lookup"><span data-stu-id="a8b14-132">In the list on the left, under the **Default** channel, select the other channel.</span></span>
1. <span data-ttu-id="a8b14-133">A **Profil tulajdonságai** területen kattintson a **Hozzáadás** gombra.</span><span class="sxs-lookup"><span data-stu-id="a8b14-133">Under **Profile properties**, select **Add**.</span></span>
1. <span data-ttu-id="a8b14-134">A hozzáadott tulajdonság esetében válassza a **Médiakiszolgáló alap URL-címe** lehetőséget tulajdonságkulcsként.</span><span class="sxs-lookup"><span data-stu-id="a8b14-134">For the property that was added, select **Media Server Base URL** as the property key.</span></span> <span data-ttu-id="a8b14-135">A tulajdonságértékként adja meg a korábban létrehozott média alap URL-címét.</span><span class="sxs-lookup"><span data-stu-id="a8b14-135">As the property value, enter the media base URL that you created earlier.</span></span>
1. <span data-ttu-id="a8b14-136">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a8b14-136">Select **Save**.</span></span>

## <a name="configure-the-email-server"></a><span data-ttu-id="a8b14-137">E-mail-kiszolgáló konfigurálása</span><span class="sxs-lookup"><span data-stu-id="a8b14-137">Configure the email server</span></span>

> [!NOTE]
> <span data-ttu-id="a8b14-138">Az itt megadott SMTP-kiszolgálónak vagy e-mail szolgáltatásnak elérhetőnek kell lennie a környezethez használt Azure-előfizetésből.</span><span class="sxs-lookup"><span data-stu-id="a8b14-138">The SMTP server or email service that you enter here must be accessible from the Azure subscription that you're using for the environment.</span></span>

1. <span data-ttu-id="a8b14-139">Bejelentkezés a Commerce alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="a8b14-139">Sign in to Commerce.</span></span>
1. <span data-ttu-id="a8b14-140">A bal oldali menü használatával nyissa meg a **Modulok \> Rendszerfelügyelet \> Beállítás \> E-mail \> E-mail-paraméterek** elemet.</span><span class="sxs-lookup"><span data-stu-id="a8b14-140">Use the menu on the left to go to **Modules \> System administration \> Setup \> Email \> Email parameters**.</span></span>
1. <span data-ttu-id="a8b14-141">Az **SMTP-beállítások** lapon a **Kimenő levelek kiszolgálója** mezőjébe írja be az SMTP-kiszolgáló vagy e-mail-szolgáltatás FQDN-nevét vagy IP-címét.</span><span class="sxs-lookup"><span data-stu-id="a8b14-141">On the **SMTP settings** tab, in the **Outgoing mail server** field, enter the FQDN or IP address of your SMTP server or email service.</span></span>
1. <span data-ttu-id="a8b14-142">Írja be az **SMTP portszáma** mezőbe a port számát.</span><span class="sxs-lookup"><span data-stu-id="a8b14-142">In the **SMTP port number** field, enter the port number.</span></span> <span data-ttu-id="a8b14-143">(Ha nem a Secure Sockets Layer \[SSL\] protokollt használja, az alapértelmezett portszám **25**.)</span><span class="sxs-lookup"><span data-stu-id="a8b14-143">(If you aren't using Secure Sockets Layer \[SSL\], the default port number is **25**.)</span></span>
1. <span data-ttu-id="a8b14-144">Ha hitelesítés szükséges, írja be az értékeket a **Felhasználónév** és a **Jelszó** mezőkbe.</span><span class="sxs-lookup"><span data-stu-id="a8b14-144">If authentication is required, enter values in the **User name** and **Password** fields.</span></span>
1. <span data-ttu-id="a8b14-145">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a8b14-145">Select **Save**.</span></span>
1. <span data-ttu-id="a8b14-146">Válassza a **Frissítés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a8b14-146">Select **Refresh**.</span></span>
1. <span data-ttu-id="a8b14-147">A **Teszt-e-mail** lapon az **E-mail-szolgáltató** mezőben válassza ki az **SMTP** elemet.</span><span class="sxs-lookup"><span data-stu-id="a8b14-147">On the **Test email** tab, in the **Email provider** field, select **SMTP**.</span></span>
1. <span data-ttu-id="a8b14-148">A **Címzett** mezőbe írja be azt az e-mail címet, amelyre a teszt-e-mailt kézbesíteni kívánja.</span><span class="sxs-lookup"><span data-stu-id="a8b14-148">In the **Send to** field, enter the email address that the test email should be delivered to.</span></span>
1. <span data-ttu-id="a8b14-149">Válassza a **Teszt-e-mail küldése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a8b14-149">Select **Send test email**.</span></span>

## <a name="configure-email-templates"></a><span data-ttu-id="a8b14-150">E-mail-sablonok konfigurálása</span><span class="sxs-lookup"><span data-stu-id="a8b14-150">Configure email templates</span></span>

<span data-ttu-id="a8b14-151">Az e-mail-sablont minden olyan tranzakciós eseményhez, amelyre e-maileket szeretne küldeni, frissíteni kell egy érvényes feladói e-mail-címmel.</span><span class="sxs-lookup"><span data-stu-id="a8b14-151">For each transactional event that you want to send emails for, you must update the email template with a valid sender email address.</span></span>

1. <span data-ttu-id="a8b14-152">Bejelentkezés a Commerce alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="a8b14-152">Sign in to Commerce.</span></span>
1. <span data-ttu-id="a8b14-153">A bal oldali menü használatával nyissa meg a **Modulok \> Szervezet felügyelete \> Beállítás \> Szervezeti e-mail-sablonok** elemet.</span><span class="sxs-lookup"><span data-stu-id="a8b14-153">Use the menu on the left to go to **Modules \> Organization administration \> Setup \> Organization email templates**.</span></span>
1. <span data-ttu-id="a8b14-154">Válassza ki a **Lista megjelenítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a8b14-154">Select **Show list**.</span></span>
1. <span data-ttu-id="a8b14-155">A lista minden sablonja esetén hajtsa végre az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="a8b14-155">For each template in the list, follow these steps:</span></span>

    1. <span data-ttu-id="a8b14-156">A **Feladó e-mail címe** mezőbe írja be a feladó e-mail címét.</span><span class="sxs-lookup"><span data-stu-id="a8b14-156">In the **Sender email** field, enter the sender email address.</span></span>
    1. <span data-ttu-id="a8b14-157">Nem kötelező: A **Feladó neve** mezőben adja meg a feladó neveként használandó nevet.</span><span class="sxs-lookup"><span data-stu-id="a8b14-157">Optional: In the **Sender name** field, enter the name that should be used as the sender name.</span></span>

1. <span data-ttu-id="a8b14-158">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a8b14-158">Select **Save**.</span></span>

## <a name="customize-email-templates"></a><span data-ttu-id="a8b14-159">E-mail-sablonok testreszabása</span><span class="sxs-lookup"><span data-stu-id="a8b14-159">Customize email templates</span></span>

<span data-ttu-id="a8b14-160">Célszerű lehet testreszabni az e-mail sablonokat, hogy azok különböző képeket használhassanak.</span><span class="sxs-lookup"><span data-stu-id="a8b14-160">You might want to customize the email templates so that they use different images.</span></span> <span data-ttu-id="a8b14-161">Előfordulhat az is, hogy frissíteni szeretné a sablonokban lévő hivatkozásokat, hogy azok az előzetes környezetbe kerüljenek.</span><span class="sxs-lookup"><span data-stu-id="a8b14-161">Or you might want to update the links in the templates so that they go to your preview environment.</span></span> <span data-ttu-id="a8b14-162">Ez az eljárás leírja, hogyan lehet letölteni az alapértelmezett sablonokat, illetve hogyan szabhatja testre és frissítheti a sablonokat a rendszerben.</span><span class="sxs-lookup"><span data-stu-id="a8b14-162">This procedure explains how to download the default templates, customize them, and update the templates in the system.</span></span>

1. <span data-ttu-id="a8b14-163">A böngésző használatával letöltheti a [Microsoft Dynamics 365 Commerce Preview default email templates .zip fájlt](https://download.microsoft.com/download/d/7/b/d7b6c4d4-fe09-4922-9551-46bbb29d202d/Commerce.Preview.Default.Email.Templates.zip) a számítógépére.</span><span class="sxs-lookup"><span data-stu-id="a8b14-163">In a web browser, download the [Microsoft Dynamics 365 Commerce Preview default email templates zip file](https://download.microsoft.com/download/d/7/b/d7b6c4d4-fe09-4922-9551-46bbb29d202d/Commerce.Preview.Default.Email.Templates.zip) to your local computer.</span></span> <span data-ttu-id="a8b14-164">Ez a fájl a következő HTML-dokumentumokat tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="a8b14-164">This file contains the following HTML documents:</span></span>

    - <span data-ttu-id="a8b14-165">Rendelés megerősítési sablon</span><span class="sxs-lookup"><span data-stu-id="a8b14-165">Order confirmation template</span></span>
    - <span data-ttu-id="a8b14-166">Ajándékutalvány-sablon kiadása</span><span class="sxs-lookup"><span data-stu-id="a8b14-166">Issue gift card template</span></span>
    - <span data-ttu-id="a8b14-167">Új rendeléssablon</span><span class="sxs-lookup"><span data-stu-id="a8b14-167">New order template</span></span>
    - <span data-ttu-id="a8b14-168">Csomagrendelési sablon</span><span class="sxs-lookup"><span data-stu-id="a8b14-168">Pack order template</span></span>
    - <span data-ttu-id="a8b14-169">Kitárolás rendelési sablon</span><span class="sxs-lookup"><span data-stu-id="a8b14-169">Pick order template</span></span>

1. <span data-ttu-id="a8b14-170">A sablonokat a szöveg- vagy HTML-szerkesztő segítségével szabhatja testre.</span><span class="sxs-lookup"><span data-stu-id="a8b14-170">Customize the templates by using a text or HTML editor.</span></span> <span data-ttu-id="a8b14-171">A [támogatott tokenek](#supported-tokens-in-the-email-template) listája a jelen témakör későbbi részében található.</span><span class="sxs-lookup"><span data-stu-id="a8b14-171">See the list of [supported tokens](#supported-tokens-in-the-email-template) later in this topic.</span></span>
1. <span data-ttu-id="a8b14-172">Bejelentkezés a Commerce alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="a8b14-172">Sign in to Commerce.</span></span>
1. <span data-ttu-id="a8b14-173">A bal oldali menü használatával nyissa meg a **Modulok \> Szervezet felügyelete \> Beállítás \> Szervezeti e-mail-sablonok** elemet.</span><span class="sxs-lookup"><span data-stu-id="a8b14-173">Use the menu on the left to go to **Modules \> Organization administration \> Setup \> Organization email templates**.</span></span>
1. <span data-ttu-id="a8b14-174">A bal oldali lista kibontásával megjelenítheti az összes sablont.</span><span class="sxs-lookup"><span data-stu-id="a8b14-174">Expand the list on the left to see all the templates.</span></span>
1. <span data-ttu-id="a8b14-175">Minden testreszabni kívánt sablonhoz hajtsa végre az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="a8b14-175">For each template that you want to customize, follow these steps:</span></span>

    1. <span data-ttu-id="a8b14-176">Válassza ki a sablont a listából.</span><span class="sxs-lookup"><span data-stu-id="a8b14-176">Select the template in the list.</span></span>
    1. <span data-ttu-id="a8b14-177">Az **E-mail-üzenet tartalma** területen válassza ki a megfelelő nyelvi verziót a listából.</span><span class="sxs-lookup"><span data-stu-id="a8b14-177">Under **Email message content**, select the appropriate language version in the list.</span></span> <span data-ttu-id="a8b14-178">(Az alapértelmezett nyelv az **en-us**.)</span><span class="sxs-lookup"><span data-stu-id="a8b14-178">(The default language is **en-us**.)</span></span>
    1. <span data-ttu-id="a8b14-179">Az **E-mail-üzenet tartalma** alatt válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a8b14-179">Under **Email message content**, select **Edit**.</span></span> <span data-ttu-id="a8b14-180">Megjelenik az **E-mail-sablon feltöltése** ablaktábla.</span><span class="sxs-lookup"><span data-stu-id="a8b14-180">The **Upload email template** pane appears.</span></span>
    1. <span data-ttu-id="a8b14-181">Válassza a **Tallózás** lehetőséget, és keresse meg azt a HTML-fájlt, amely a testreszabott tartalommal rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="a8b14-181">Select **Browse**, and find the HTML file that has the customized content.</span></span>
    1. <span data-ttu-id="a8b14-182">Válassza a **Feltöltés** elemet.</span><span class="sxs-lookup"><span data-stu-id="a8b14-182">Select **Upload**.</span></span> <span data-ttu-id="a8b14-183">A sablon fel lesz töltve a rendszerbe, és megjelenik egy előnézet.</span><span class="sxs-lookup"><span data-stu-id="a8b14-183">The template is uploaded into the system, and a preview is shown.</span></span>
    1. <span data-ttu-id="a8b14-184">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a8b14-184">Select **OK**.</span></span>
    1. <span data-ttu-id="a8b14-185">Opcionális: A sablon **Tárgy** tulajdonságának testreszabása.</span><span class="sxs-lookup"><span data-stu-id="a8b14-185">Optional: Customize the **Subject** property of the template.</span></span>
    1. <span data-ttu-id="a8b14-186">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a8b14-186">Select **Save**.</span></span>

### <a name="supported-tokens-in-the-email-template"></a><span data-ttu-id="a8b14-187">Az e-mail-sablonban támogatott tokenek</span><span class="sxs-lookup"><span data-stu-id="a8b14-187">Supported tokens in the email template</span></span>

<span data-ttu-id="a8b14-188">Ezeket a tokeneket az e-mail renderelése során a program lecseréli a vevőkre és a rendelésre vonatkozó tényleges értékekre.</span><span class="sxs-lookup"><span data-stu-id="a8b14-188">When the email is rendered, these tokens are replaced with actual values that apply to the customer and the customer's order.</span></span>

#### <a name="sales-order"></a><span data-ttu-id="a8b14-189">Értékesítési rendelés</span><span class="sxs-lookup"><span data-stu-id="a8b14-189">Sales order</span></span>

<span data-ttu-id="a8b14-190">A következő tokenek érvényesek a teljes értékesítési rendelésre.</span><span class="sxs-lookup"><span data-stu-id="a8b14-190">The following tokens apply to the overall sales order.</span></span>

| <span data-ttu-id="a8b14-191">A token neve</span><span class="sxs-lookup"><span data-stu-id="a8b14-191">Name of the token</span></span> | <span data-ttu-id="a8b14-192">Jogkivonat</span><span class="sxs-lookup"><span data-stu-id="a8b14-192">Token</span></span> |
|-------------------|-------|
| <span data-ttu-id="a8b14-193">Rendelés száma</span><span class="sxs-lookup"><span data-stu-id="a8b14-193">Order number</span></span>      | <span data-ttu-id="a8b14-194">%salesid%</span><span class="sxs-lookup"><span data-stu-id="a8b14-194">%salesid%</span></span> |
| <span data-ttu-id="a8b14-195">Vevő neve</span><span class="sxs-lookup"><span data-stu-id="a8b14-195">Customer's name</span></span>   | <span data-ttu-id="a8b14-196">%customername%</span><span class="sxs-lookup"><span data-stu-id="a8b14-196">%customername%</span></span> |
| <span data-ttu-id="a8b14-197">Szállítási cím</span><span class="sxs-lookup"><span data-stu-id="a8b14-197">Delivery address</span></span>  | <span data-ttu-id="a8b14-198">%deliveryaddress%</span><span class="sxs-lookup"><span data-stu-id="a8b14-198">%deliveryaddress%</span></span> |
| <span data-ttu-id="a8b14-199">Számlázási cím</span><span class="sxs-lookup"><span data-stu-id="a8b14-199">Billing address</span></span>   | <span data-ttu-id="a8b14-200">%customeraddress%</span><span class="sxs-lookup"><span data-stu-id="a8b14-200">%customeraddress%</span></span> |
| <span data-ttu-id="a8b14-201">Megrendelési dátum</span><span class="sxs-lookup"><span data-stu-id="a8b14-201">Order date</span></span>        | <span data-ttu-id="a8b14-202">%shipdate%</span><span class="sxs-lookup"><span data-stu-id="a8b14-202">%shipdate%</span></span> |
| <span data-ttu-id="a8b14-203">Kézbesítés módja</span><span class="sxs-lookup"><span data-stu-id="a8b14-203">Delivery mode</span></span>     | <span data-ttu-id="a8b14-204">%modeofdelivery%</span><span class="sxs-lookup"><span data-stu-id="a8b14-204">%modeofdelivery%</span></span> |
| <span data-ttu-id="a8b14-205">Engedmény</span><span class="sxs-lookup"><span data-stu-id="a8b14-205">Discount</span></span>          | <span data-ttu-id="a8b14-206">%discount%</span><span class="sxs-lookup"><span data-stu-id="a8b14-206">%discount%</span></span> |
| <span data-ttu-id="a8b14-207">Áfa</span><span class="sxs-lookup"><span data-stu-id="a8b14-207">Sales tax</span></span>         | <span data-ttu-id="a8b14-208">%tax%</span><span class="sxs-lookup"><span data-stu-id="a8b14-208">%tax%</span></span> |
| <span data-ttu-id="a8b14-209">Rendelés végösszege</span><span class="sxs-lookup"><span data-stu-id="a8b14-209">Order total</span></span>       | <span data-ttu-id="a8b14-210">%total%</span><span class="sxs-lookup"><span data-stu-id="a8b14-210">%total%</span></span> |

#### <a name="sales-line"></a><span data-ttu-id="a8b14-211">Értékesítési sor</span><span class="sxs-lookup"><span data-stu-id="a8b14-211">Sales line</span></span>

<span data-ttu-id="a8b14-212">A következő tokeneket cseréli ki a rendszer értékekre az egyes termékek esetében.</span><span class="sxs-lookup"><span data-stu-id="a8b14-212">The following tokens are replaced with values for each product in the order.</span></span>

> [!NOTE]
> <span data-ttu-id="a8b14-213">Tegye a **Terméklista – kezdés** tokent a HTML-blokk elejére, amely minden termékre megismétlődik, majd a blokk végén helyezze el a **Terméklista – befejezés** tokent.</span><span class="sxs-lookup"><span data-stu-id="a8b14-213">Put the **Product list - start** token at the beginning of the HTML block that is repeated for every product, and put the **Product list - end** token at the end of the block.</span></span>

| <span data-ttu-id="a8b14-214">A token neve</span><span class="sxs-lookup"><span data-stu-id="a8b14-214">Name of the token</span></span>      | <span data-ttu-id="a8b14-215">Jogkivonat</span><span class="sxs-lookup"><span data-stu-id="a8b14-215">Token</span></span> |
|------------------------|-------|
| <span data-ttu-id="a8b14-216">Terméklista – kezdés</span><span class="sxs-lookup"><span data-stu-id="a8b14-216">Product list - start</span></span>   | <span data-ttu-id="a8b14-217">\<!--%tablebegin.salesline% --\></span><span class="sxs-lookup"><span data-stu-id="a8b14-217">\<!--%tablebegin.salesline% --\></span></span> |
| <span data-ttu-id="a8b14-218">Terméklista – befejezés</span><span class="sxs-lookup"><span data-stu-id="a8b14-218">Product list - end</span></span>     | <span data-ttu-id="a8b14-219">\<!--%tableend.salesline%--\></span><span class="sxs-lookup"><span data-stu-id="a8b14-219">\<!--%tableend.salesline%--\></span></span> |
| <span data-ttu-id="a8b14-220">Termék neve</span><span class="sxs-lookup"><span data-stu-id="a8b14-220">Product name</span></span>           | <span data-ttu-id="a8b14-221">%lineproductname%</span><span class="sxs-lookup"><span data-stu-id="a8b14-221">%lineproductname%</span></span> |
| <span data-ttu-id="a8b14-222">Leírás</span><span class="sxs-lookup"><span data-stu-id="a8b14-222">Description</span></span>            | <span data-ttu-id="a8b14-223">%lineproductdescription%</span><span class="sxs-lookup"><span data-stu-id="a8b14-223">%lineproductdescription%</span></span> |
| <span data-ttu-id="a8b14-224">Mennyiség</span><span class="sxs-lookup"><span data-stu-id="a8b14-224">Quantity</span></span>               | <span data-ttu-id="a8b14-225">%linequantity%</span><span class="sxs-lookup"><span data-stu-id="a8b14-225">%linequantity%</span></span> |
| <span data-ttu-id="a8b14-226">Sor egységára</span><span class="sxs-lookup"><span data-stu-id="a8b14-226">Line unit price</span></span>        | <span data-ttu-id="a8b14-227">%lineprice% (verify)</span><span class="sxs-lookup"><span data-stu-id="a8b14-227">%lineprice% (verify)</span></span> |
| <span data-ttu-id="a8b14-228">sortétel összege</span><span class="sxs-lookup"><span data-stu-id="a8b14-228">line item total</span></span>        | <span data-ttu-id="a8b14-229">%linenetamount%</span><span class="sxs-lookup"><span data-stu-id="a8b14-229">%linenetamount%</span></span> |
| <span data-ttu-id="a8b14-230">sorkedvezmény</span><span class="sxs-lookup"><span data-stu-id="a8b14-230">line discount</span></span>          | <span data-ttu-id="a8b14-231">%linediscount%</span><span class="sxs-lookup"><span data-stu-id="a8b14-231">%linediscount%</span></span> |
| <span data-ttu-id="a8b14-232">Szállítási dátum</span><span class="sxs-lookup"><span data-stu-id="a8b14-232">Ship date</span></span>              | <span data-ttu-id="a8b14-233">%lineshipdate%</span><span class="sxs-lookup"><span data-stu-id="a8b14-233">%lineshipdate%</span></span> |
| <span data-ttu-id="a8b14-234">Beszerzési mód</span><span class="sxs-lookup"><span data-stu-id="a8b14-234">Procurement method</span></span>     | <span data-ttu-id="a8b14-235">%linedeliverymode%</span><span class="sxs-lookup"><span data-stu-id="a8b14-235">%linedeliverymode%</span></span> |
| <span data-ttu-id="a8b14-236">szállítási cím</span><span class="sxs-lookup"><span data-stu-id="a8b14-236">delivery address</span></span>       | <span data-ttu-id="a8b14-237">%linedeliveryaddress%</span><span class="sxs-lookup"><span data-stu-id="a8b14-237">%linedeliveryaddress%</span></span> |
| <span data-ttu-id="a8b14-238">A sor értékesítési egysége</span><span class="sxs-lookup"><span data-stu-id="a8b14-238">Sales unit of the line</span></span> | <span data-ttu-id="a8b14-239">%lineunit%</span><span class="sxs-lookup"><span data-stu-id="a8b14-239">%lineunit%</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="a8b14-240">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="a8b14-240">Additional resources</span></span>

[<span data-ttu-id="a8b14-241">Dynamics 365 Commerce előzetes verziós környezet áttekintése</span><span class="sxs-lookup"><span data-stu-id="a8b14-241">Dynamics 365 Commerce preview environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="a8b14-242">Egy Dynamics 365 Commerce előnézeti környezet létesítése</span><span class="sxs-lookup"><span data-stu-id="a8b14-242">Provision a Dynamics 365 Commerce preview environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="a8b14-243">Dynamics 365 Commerce előzetes verziós környezet konfigurálása</span><span class="sxs-lookup"><span data-stu-id="a8b14-243">Configure a Dynamics 365 Commerce preview environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="a8b14-244">Dynamics 365 Commerce előzetes verziós környezet GYIK</span><span class="sxs-lookup"><span data-stu-id="a8b14-244">Dynamics 365 Commerce preview environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="a8b14-245">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="a8b14-245">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="a8b14-246">Retail Cloud Scale Unit (RCSU)</span><span class="sxs-lookup"><span data-stu-id="a8b14-246">Retail Cloud Scale Unit (RCSU)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="a8b14-247">Microsoft Azure-portál</span><span class="sxs-lookup"><span data-stu-id="a8b14-247">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="a8b14-248">Dynamics 365 Commerce-webhely</span><span class="sxs-lookup"><span data-stu-id="a8b14-248">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)
