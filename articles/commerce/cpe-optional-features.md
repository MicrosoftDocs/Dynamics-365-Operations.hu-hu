---
title: A Commerce előzetes verziós környezet választható funkcióinak konfigurálása
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
ms.openlocfilehash: 2c4872cdebc414eaa865af025237bd9e1d14bfd2
ms.sourcegitcommit: 610d5c3efadbaf11752b46f24680af619bcd70a6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/10/2019
ms.locfileid: "2906116"
---
# <a name="configure-optional-features-for-a-commerce-preview-environment"></a><span data-ttu-id="07e95-103">A Commerce előzetes verziós környezet választható funkcióinak konfigurálása</span><span class="sxs-lookup"><span data-stu-id="07e95-103">Configure optional features for a Commerce preview environment</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="07e95-104">Ez a témakör bemutatja, hogyan lehet opcionális funkciókat konfigurálni egy Microsoft Dynamics 365 Commerce előzetes környezethez.</span><span class="sxs-lookup"><span data-stu-id="07e95-104">This topic explains how to configure optional features for a Microsoft Dynamics 365 Commerce preview environment.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="07e95-105">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="07e95-105">Prerequisites</span></span>

<span data-ttu-id="07e95-106">Ha ki szeretné próbálni tranzakciós e-mail funkciókat, akkor az alábbi előfeltételeknek kell teljesülniük:</span><span class="sxs-lookup"><span data-stu-id="07e95-106">If you want to evaluate the transactional email features, the following prerequisites must be met:</span></span>

- <span data-ttu-id="07e95-107">Rendelkezik egy e-mail kiszolgálóval (Egyszerű üzenetátviteli protokoll \[SMTP\] kiszolgáló), amelyet abból a Microsoft Azure-előfizetésből lehet használni, ahol az előzetes környezetet létesítette.</span><span class="sxs-lookup"><span data-stu-id="07e95-107">You have an available email server (Simple Mail Transfer Protocol \[SMTP\] server) that can be used from the Microsoft Azure subscription where you provisioned the preview environment.</span></span>
- <span data-ttu-id="07e95-108">A kiszolgáló teljes képzésű tartományneve (FQDN)/IP-címe, SMTP-portszáma és a hitelesítési adatok rendelkezésre állnak.</span><span class="sxs-lookup"><span data-stu-id="07e95-108">You have the server's fully qualified domain name (FQDN)/IP address, SMTP port number, and authentication details available.</span></span>

<span data-ttu-id="07e95-109">Ha az új omnicsatornás képek fogyasztásával szeretné értékelni a Digitális eszközkezelés funkciókat, akkor rendelkezésre kell állnia a tartalomkezelő rendszer (CMS) bérlőnevének.</span><span class="sxs-lookup"><span data-stu-id="07e95-109">If you want to evaluate Digital Asset Management features by ingesting new omni-channel images, you must have the name of your content management system (CMS) tenant available.</span></span> <span data-ttu-id="07e95-110">A név megtalálásához a jelen témakör későbbi részében talál útmutatást.</span><span class="sxs-lookup"><span data-stu-id="07e95-110">Instructions for finding this name are provided later in this topic.</span></span> <span data-ttu-id="07e95-111">>>>(Q: Hol vannak az utasítások?)</span><span class="sxs-lookup"><span data-stu-id="07e95-111">>>>(Q: where are the instructions?)</span></span>

## <a name="configure-the-image-back-end"></a><span data-ttu-id="07e95-112">A képháttér konfigurálása</span><span class="sxs-lookup"><span data-stu-id="07e95-112">Configure the image back end</span></span>

### <a name="find-your-media-base-url"></a><span data-ttu-id="07e95-113">A média alap URL-címének megkeresése</span><span class="sxs-lookup"><span data-stu-id="07e95-113">Find your media base URL</span></span>

> [!NOTE]
> <span data-ttu-id="07e95-114">A művelet végrehajtása előtt be kell fejeznie a [Webhely beállítása a Commerce alkalmazásban](cpe-post-provisioning.md#set-up-your-site-in-commerce) témakör lépéseit.</span><span class="sxs-lookup"><span data-stu-id="07e95-114">Before you can complete this procedure, you must complete the steps in [Set up your site in Commerce](cpe-post-provisioning.md#set-up-your-site-in-commerce).</span></span>

1. <span data-ttu-id="07e95-115">Jelentkezzen be a Commerce webhelykezelő eszközébe azzal az URL-címmel, amelyet az e-kereskedelem inicializálásakor a létesítés során megadott (lásd: [E-kereskedelem inicializálása](provisioning-guide.md#initialize-e-commerce)).</span><span class="sxs-lookup"><span data-stu-id="07e95-115">Sign in to the Commerce site management tool by using the URL you made a note of when you initialized e-Commerce during provisioning (see [Initialize e-Commerce](provisioning-guide.md#initialize-e-commerce)).</span></span>
1. <span data-ttu-id="07e95-116">Nyissa meg a **Gyár** webhelyet.</span><span class="sxs-lookup"><span data-stu-id="07e95-116">Open the **Fabrikam** site.</span></span>
1. <span data-ttu-id="07e95-117">A bal oldali menüben válassza az **Eszközök** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="07e95-117">On the menu on the left, select **Assets**.</span></span>
1. <span data-ttu-id="07e95-118">Válasszon ki egyetlen képeszközt.</span><span class="sxs-lookup"><span data-stu-id="07e95-118">Select any single image asset.</span></span>
1. <span data-ttu-id="07e95-119">A jobb oldali tulajdonságvizsgálóban keresse meg a **Nyilvános URL** tulajdonságot.</span><span class="sxs-lookup"><span data-stu-id="07e95-119">In the property inspector on the right, find the **Public URL** property.</span></span> <span data-ttu-id="07e95-120">Az érték egy URL.</span><span class="sxs-lookup"><span data-stu-id="07e95-120">The value is a URL.</span></span> <span data-ttu-id="07e95-121">Egy példa:</span><span class="sxs-lookup"><span data-stu-id="07e95-121">Here is an example:</span></span>

    <span data-ttu-id="07e95-122">`https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/MA1nQC`.</span><span class="sxs-lookup"><span data-stu-id="07e95-122">`https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/MA1nQC`.</span></span>

1. <span data-ttu-id="07e95-123">Cserélje le az URL-címben szereplő utolsó azonosítót (az előző példában **MA1nQC**) a következő karakterlánccal: **search?fileName=**.</span><span class="sxs-lookup"><span data-stu-id="07e95-123">Replace the last identifier in the URL (**MA1nQC** in the preceding example) with the string **search?fileName=**.</span></span> <span data-ttu-id="07e95-124">A csere után így néz ki a példa URL:</span><span class="sxs-lookup"><span data-stu-id="07e95-124">Here is what the example URL looks like after this change is made:</span></span>

    `https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/search?fileName=`

    <span data-ttu-id="07e95-125">Ez az URL-cím a média alap URL-je.</span><span class="sxs-lookup"><span data-stu-id="07e95-125">This URL is your media base URL.</span></span> <span data-ttu-id="07e95-126">Jegyezze fel.</span><span class="sxs-lookup"><span data-stu-id="07e95-126">Make a note of it.</span></span>

### <a name="update-the-media-base-url"></a><span data-ttu-id="07e95-127">A média alap URL-cím frissítése</span><span class="sxs-lookup"><span data-stu-id="07e95-127">Update the media base URL</span></span>

1. <span data-ttu-id="07e95-128">Jelentkezzen be a Dynamics 365 Retail alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="07e95-128">Sign in to Dynamics 365 Retail.</span></span>
1. <span data-ttu-id="07e95-129">A bal oldali menü használatával nyissa meg a **Modulok \> Kereskedelem \> Csatorna beállítása \> Csatornaprofilok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="07e95-129">Use the menu on the left to go to **Modules \> Retail \> Channel setup \> Channel profiles**.</span></span>
1. <span data-ttu-id="07e95-130">Válassza ki a **Szerkesztés** opciót.</span><span class="sxs-lookup"><span data-stu-id="07e95-130">Select **Edit**.</span></span>
1. <span data-ttu-id="07e95-131">A **Profil tulajdonságai** alatt cserélje le a **Médiakiszolgáló alap URL-címe** tulajdonságot a korábban létrehozott média alap URL-címre.</span><span class="sxs-lookup"><span data-stu-id="07e95-131">Under **Profile properties**, replace the value for the **Media Server Base URL** property with the media base URL that you created earlier.</span></span>
1. <span data-ttu-id="07e95-132">Válassza ki a másik csatornát a bal oldali listából az **Alapértelmezett** csatorna alatt.</span><span class="sxs-lookup"><span data-stu-id="07e95-132">In the list on the left, under the **Default** channel, select the other channel.</span></span>
1. <span data-ttu-id="07e95-133">A **Profil tulajdonságai** területen kattintson a **Hozzáadás** gombra.</span><span class="sxs-lookup"><span data-stu-id="07e95-133">Under **Profile properties**, select **Add**.</span></span>
1. <span data-ttu-id="07e95-134">A hozzáadott tulajdonság esetében válassza a **Médiakiszolgáló alap URL-címe** lehetőséget tulajdonságkulcsként.</span><span class="sxs-lookup"><span data-stu-id="07e95-134">For the property that was added, select **Media Server Base URL** as the property key.</span></span> <span data-ttu-id="07e95-135">A tulajdonságértékként adja meg a korábban létrehozott média alap URL-címét.</span><span class="sxs-lookup"><span data-stu-id="07e95-135">As the property value, enter the media base URL that you created earlier.</span></span>
1. <span data-ttu-id="07e95-136">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="07e95-136">Select **Save**.</span></span>

## <a name="configure-the-email-server"></a><span data-ttu-id="07e95-137">E-mail-kiszolgáló konfigurálása</span><span class="sxs-lookup"><span data-stu-id="07e95-137">Configure the email server</span></span>

> [!NOTE]
> <span data-ttu-id="07e95-138">Az itt megadott SMTP-kiszolgálónak vagy e-mail szolgáltatásnak elérhetőnek kell lennie a környezethez használt Azure-előfizetésből.</span><span class="sxs-lookup"><span data-stu-id="07e95-138">The SMTP server or email service that you enter here must be accessible from the Azure subscription that you're using for the environment.</span></span>

1. <span data-ttu-id="07e95-139">Jelentkezzen be a Retail alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="07e95-139">Sign in to Retail.</span></span>
1. <span data-ttu-id="07e95-140">A bal oldali menü használatával nyissa meg a **Modulok \> Rendszerfelügyelet \> Beállítás \> E-mail \> E-mail-paraméterek** elemet.</span><span class="sxs-lookup"><span data-stu-id="07e95-140">Use the menu on the left to go to **Modules \> System administration \> Setup \> Email \> Email parameters**.</span></span>
1. <span data-ttu-id="07e95-141">Az **SMTP-beállítások** lapon a **Kimenő levelek kiszolgálója** mezőjébe írja be az SMTP-kiszolgáló vagy e-mail-szolgáltatás FQDN-nevét vagy IP-címét.</span><span class="sxs-lookup"><span data-stu-id="07e95-141">On the **SMTP settings** tab, in the **Outgoing mail server** field, enter the FQDN or IP address of your SMTP server or email service.</span></span>
1. <span data-ttu-id="07e95-142">Írja be az **SMTP portszáma** mezőbe a port számát.</span><span class="sxs-lookup"><span data-stu-id="07e95-142">In the **SMTP port number** field, enter the port number.</span></span> <span data-ttu-id="07e95-143">(Ha nem a Secure Sockets Layer \[SSL\] protokollt használja, az alapértelmezett portszám **25**.)</span><span class="sxs-lookup"><span data-stu-id="07e95-143">(If you aren't using Secure Sockets Layer \[SSL\], the default port number is **25**.)</span></span>
1. <span data-ttu-id="07e95-144">Ha hitelesítés szükséges, írja be az értékeket a **Felhasználónév** és a **Jelszó** mezőkbe.</span><span class="sxs-lookup"><span data-stu-id="07e95-144">If authentication is required, enter values in the **User name** and **Password** fields.</span></span>
1. <span data-ttu-id="07e95-145">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="07e95-145">Select **Save**.</span></span>
1. <span data-ttu-id="07e95-146">Válassza a **Frissítés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="07e95-146">Select **Refresh**.</span></span>
1. <span data-ttu-id="07e95-147">A **Teszt-e-mail** lapon az **E-mail-szolgáltató** mezőben válassza ki az **SMTP** elemet.</span><span class="sxs-lookup"><span data-stu-id="07e95-147">On the **Test email** tab, in the **Email provider** field, select **SMTP**.</span></span>
1. <span data-ttu-id="07e95-148">A **Címzett** mezőbe írja be azt az e-mail címet, amelyre a teszt-e-mailt kézbesíteni kívánja.</span><span class="sxs-lookup"><span data-stu-id="07e95-148">In the **Send to** field, enter the email address that the test email should be delivered to.</span></span>
1. <span data-ttu-id="07e95-149">Válassza a **Teszt-e-mail küldése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="07e95-149">Select **Send test email**.</span></span>

## <a name="configure-email-templates"></a><span data-ttu-id="07e95-150">E-mail-sablonok konfigurálása</span><span class="sxs-lookup"><span data-stu-id="07e95-150">Configure email templates</span></span>

<span data-ttu-id="07e95-151">Az e-mail-sablont minden olyan tranzakciós eseményhez, amelyre e-maileket szeretne küldeni, frissíteni kell egy érvényes feladói e-mail-címmel.</span><span class="sxs-lookup"><span data-stu-id="07e95-151">For each transactional event that you want to send emails for, you must update the email template with a valid sender email address.</span></span>

1. <span data-ttu-id="07e95-152">Jelentkezzen be a Retail alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="07e95-152">Sign in to Retail.</span></span>
1. <span data-ttu-id="07e95-153">A bal oldali menü használatával nyissa meg a **Modulok \> Szervezet felügyelete \> Beállítás \> Szervezeti e-mail-sablonok** elemet.</span><span class="sxs-lookup"><span data-stu-id="07e95-153">Use the menu on the left to go to **Modules \> Organization administration \> Setup \> Organization email templates**.</span></span>
1. <span data-ttu-id="07e95-154">Válassza ki a **Lista megjelenítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="07e95-154">Select **Show list**.</span></span>
1. <span data-ttu-id="07e95-155">A lista minden sablonja esetén hajtsa végre az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="07e95-155">For each template in the list, follow these steps:</span></span>

    1. <span data-ttu-id="07e95-156">A **Feladó e-mail címe** mezőbe írja be a feladó e-mail címét.</span><span class="sxs-lookup"><span data-stu-id="07e95-156">In the **Sender email** field, enter the sender email address.</span></span>
    1. <span data-ttu-id="07e95-157">Nem kötelező: A **Feladó neve** mezőben adja meg a feladó neveként használandó nevet.</span><span class="sxs-lookup"><span data-stu-id="07e95-157">Optional: In the **Sender name** field, enter the name that should be used as the sender name.</span></span>

1. <span data-ttu-id="07e95-158">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="07e95-158">Select **Save**.</span></span>

## <a name="customize-email-templates"></a><span data-ttu-id="07e95-159">E-mail-sablonok testreszabása</span><span class="sxs-lookup"><span data-stu-id="07e95-159">Customize email templates</span></span>

<span data-ttu-id="07e95-160">Célszerű lehet testreszabni az e-mail sablonokat, hogy azok különböző képeket használhassanak.</span><span class="sxs-lookup"><span data-stu-id="07e95-160">You might want to customize the email templates so that they use different images.</span></span> <span data-ttu-id="07e95-161">Előfordulhat az is, hogy frissíteni szeretné a sablonokban lévő hivatkozásokat, hogy azok az előzetes környezetbe kerüljenek.</span><span class="sxs-lookup"><span data-stu-id="07e95-161">Or you might want to update the links in the templates so that they go to your preview environment.</span></span> <span data-ttu-id="07e95-162">Ez az eljárás leírja, hogyan lehet letölteni az alapértelmezett sablonokat, illetve hogyan szabhatja testre és frissítheti a sablonokat a rendszerben.</span><span class="sxs-lookup"><span data-stu-id="07e95-162">This procedure explains how to download the default templates, customize them, and update the templates in the system.</span></span>

1. <span data-ttu-id="07e95-163">A böngésző használatával letöltheti a [Microsoft Dynamics 365 Commerce Preview default email templates .zip fájlt](https://download.microsoft.com/download/d/7/b/d7b6c4d4-fe09-4922-9551-46bbb29d202d/Commerce.Preview.Default.Email.Templates.zip) a számítógépére.</span><span class="sxs-lookup"><span data-stu-id="07e95-163">In a web browser, download the [Microsoft Dynamics 365 Commerce Preview default email templates zip file](https://download.microsoft.com/download/d/7/b/d7b6c4d4-fe09-4922-9551-46bbb29d202d/Commerce.Preview.Default.Email.Templates.zip) to your local computer.</span></span> <span data-ttu-id="07e95-164">Ez a fájl a következő HTML-dokumentumokat tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="07e95-164">This file contains the following HTML documents:</span></span>

    - <span data-ttu-id="07e95-165">Rendelés megerősítési sablon</span><span class="sxs-lookup"><span data-stu-id="07e95-165">Order confirmation template</span></span>
    - <span data-ttu-id="07e95-166">Ajándékutalvány-sablon kiadása</span><span class="sxs-lookup"><span data-stu-id="07e95-166">Issue gift card template</span></span>
    - <span data-ttu-id="07e95-167">Új rendeléssablon</span><span class="sxs-lookup"><span data-stu-id="07e95-167">New order template</span></span>
    - <span data-ttu-id="07e95-168">Csomagrendelési sablon</span><span class="sxs-lookup"><span data-stu-id="07e95-168">Pack order template</span></span>
    - <span data-ttu-id="07e95-169">Kitárolás rendelési sablon</span><span class="sxs-lookup"><span data-stu-id="07e95-169">Pick order template</span></span>

1. <span data-ttu-id="07e95-170">A sablonokat a szöveg- vagy HTML-szerkesztő segítségével szabhatja testre.</span><span class="sxs-lookup"><span data-stu-id="07e95-170">Customize the templates by using a text or HTML editor.</span></span> <span data-ttu-id="07e95-171">A [támogatott tokenek](#supported-tokens-in-the-email-template) listája a jelen témakör későbbi részében található.</span><span class="sxs-lookup"><span data-stu-id="07e95-171">See the list of [supported tokens](#supported-tokens-in-the-email-template) later in this topic.</span></span>
1. <span data-ttu-id="07e95-172">Jelentkezzen be a Retail alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="07e95-172">Sign in to Retail.</span></span>
1. <span data-ttu-id="07e95-173">A bal oldali menü használatával nyissa meg a **Modulok \> Szervezet felügyelete \> Beállítás \> Szervezeti e-mail-sablonok** elemet.</span><span class="sxs-lookup"><span data-stu-id="07e95-173">Use the menu on the left to go to **Modules \> Organization administration \> Setup \> Organization email templates**.</span></span>
1. <span data-ttu-id="07e95-174">A bal oldali lista kibontásával megjelenítheti az összes sablont.</span><span class="sxs-lookup"><span data-stu-id="07e95-174">Expand the list on the left to see all the templates.</span></span>
1. <span data-ttu-id="07e95-175">Minden testreszabni kívánt sablonhoz hajtsa végre az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="07e95-175">For each template that you want to customize, follow these steps:</span></span>

    1. <span data-ttu-id="07e95-176">Válassza ki a sablont a listából.</span><span class="sxs-lookup"><span data-stu-id="07e95-176">Select the template in the list.</span></span>
    1. <span data-ttu-id="07e95-177">Az **E-mail-üzenet tartalma** területen válassza ki a megfelelő nyelvi verziót a listából.</span><span class="sxs-lookup"><span data-stu-id="07e95-177">Under **Email message content**, select the appropriate language version in the list.</span></span> <span data-ttu-id="07e95-178">(Az alapértelmezett nyelv az **en-us**.)</span><span class="sxs-lookup"><span data-stu-id="07e95-178">(The default language is **en-us**.)</span></span>
    1. <span data-ttu-id="07e95-179">Az **E-mail-üzenet tartalma** alatt válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="07e95-179">Under **Email message content**, select **Edit**.</span></span> <span data-ttu-id="07e95-180">Megjelenik az **E-mail-sablon feltöltése** ablaktábla.</span><span class="sxs-lookup"><span data-stu-id="07e95-180">The **Upload email template** pane appears.</span></span>
    1. <span data-ttu-id="07e95-181">Válassza a **Tallózás** lehetőséget, és keresse meg azt a HTML-fájlt, amely a testreszabott tartalommal rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="07e95-181">Select **Browse**, and find the HTML file that has the customized content.</span></span>
    1. <span data-ttu-id="07e95-182">Válassza a **Feltöltés** elemet.</span><span class="sxs-lookup"><span data-stu-id="07e95-182">Select **Upload**.</span></span> <span data-ttu-id="07e95-183">A sablon fel lesz töltve a rendszerbe, és megjelenik egy előnézet.</span><span class="sxs-lookup"><span data-stu-id="07e95-183">The template is uploaded into the system, and a preview is shown.</span></span>
    1. <span data-ttu-id="07e95-184">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="07e95-184">Select **OK**.</span></span>
    1. <span data-ttu-id="07e95-185">Opcionális: A sablon **Tárgy** tulajdonságának testreszabása.</span><span class="sxs-lookup"><span data-stu-id="07e95-185">Optional: Customize the **Subject** property of the template.</span></span>
    1. <span data-ttu-id="07e95-186">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="07e95-186">Select **Save**.</span></span>

### <a name="supported-tokens-in-the-email-template"></a><span data-ttu-id="07e95-187">Az e-mail-sablonban támogatott tokenek</span><span class="sxs-lookup"><span data-stu-id="07e95-187">Supported tokens in the email template</span></span>

<span data-ttu-id="07e95-188">Ezeket a tokeneket az e-mail renderelése során a program lecseréli a vevőkre és a rendelésre vonatkozó tényleges értékekre.</span><span class="sxs-lookup"><span data-stu-id="07e95-188">When the email is rendered, these tokens are replaced with actual values that apply to the customer and the customer's order.</span></span>

#### <a name="sales-order"></a><span data-ttu-id="07e95-189">Értékesítési rendelés</span><span class="sxs-lookup"><span data-stu-id="07e95-189">Sales order</span></span>

<span data-ttu-id="07e95-190">A következő tokenek érvényesek a teljes értékesítési rendelésre.</span><span class="sxs-lookup"><span data-stu-id="07e95-190">The following tokens apply to the overall sales order.</span></span>

| <span data-ttu-id="07e95-191">A token neve</span><span class="sxs-lookup"><span data-stu-id="07e95-191">Name of the token</span></span> | <span data-ttu-id="07e95-192">Jogkivonat</span><span class="sxs-lookup"><span data-stu-id="07e95-192">Token</span></span> |
|-------------------|-------|
| <span data-ttu-id="07e95-193">Rendelés száma</span><span class="sxs-lookup"><span data-stu-id="07e95-193">Order number</span></span>      | <span data-ttu-id="07e95-194">%salesid%</span><span class="sxs-lookup"><span data-stu-id="07e95-194">%salesid%</span></span> |
| <span data-ttu-id="07e95-195">Vevő neve</span><span class="sxs-lookup"><span data-stu-id="07e95-195">Customer's name</span></span>   | <span data-ttu-id="07e95-196">%customername%</span><span class="sxs-lookup"><span data-stu-id="07e95-196">%customername%</span></span> |
| <span data-ttu-id="07e95-197">Szállítási cím</span><span class="sxs-lookup"><span data-stu-id="07e95-197">Delivery address</span></span>  | <span data-ttu-id="07e95-198">%deliveryaddress%</span><span class="sxs-lookup"><span data-stu-id="07e95-198">%deliveryaddress%</span></span> |
| <span data-ttu-id="07e95-199">Számlázási cím</span><span class="sxs-lookup"><span data-stu-id="07e95-199">Billing address</span></span>   | <span data-ttu-id="07e95-200">%customeraddress%</span><span class="sxs-lookup"><span data-stu-id="07e95-200">%customeraddress%</span></span> |
| <span data-ttu-id="07e95-201">Megrendelési dátum</span><span class="sxs-lookup"><span data-stu-id="07e95-201">Order date</span></span>        | <span data-ttu-id="07e95-202">%shipdate%</span><span class="sxs-lookup"><span data-stu-id="07e95-202">%shipdate%</span></span> |
| <span data-ttu-id="07e95-203">Kézbesítés módja</span><span class="sxs-lookup"><span data-stu-id="07e95-203">Delivery mode</span></span>     | <span data-ttu-id="07e95-204">%modeofdelivery%</span><span class="sxs-lookup"><span data-stu-id="07e95-204">%modeofdelivery%</span></span> |
| <span data-ttu-id="07e95-205">Engedmény</span><span class="sxs-lookup"><span data-stu-id="07e95-205">Discount</span></span>          | <span data-ttu-id="07e95-206">%discount%</span><span class="sxs-lookup"><span data-stu-id="07e95-206">%discount%</span></span> |
| <span data-ttu-id="07e95-207">Áfa</span><span class="sxs-lookup"><span data-stu-id="07e95-207">Sales tax</span></span>         | <span data-ttu-id="07e95-208">%tax%</span><span class="sxs-lookup"><span data-stu-id="07e95-208">%tax%</span></span> |
| <span data-ttu-id="07e95-209">Rendelés végösszege</span><span class="sxs-lookup"><span data-stu-id="07e95-209">Order total</span></span>       | <span data-ttu-id="07e95-210">%total%</span><span class="sxs-lookup"><span data-stu-id="07e95-210">%total%</span></span> |

#### <a name="sales-line"></a><span data-ttu-id="07e95-211">Értékesítési sor</span><span class="sxs-lookup"><span data-stu-id="07e95-211">Sales line</span></span>

<span data-ttu-id="07e95-212">A következő tokeneket cseréli ki a rendszer értékekre az egyes termékek esetében.</span><span class="sxs-lookup"><span data-stu-id="07e95-212">The following tokens are replaced with values for each product in the order.</span></span>

> [!NOTE]
> <span data-ttu-id="07e95-213">Tegye a **Terméklista – kezdés** tokent a HTML-blokk elejére, amely minden termékre megismétlődik, majd a blokk végén helyezze el a **Terméklista – befejezés** tokent.</span><span class="sxs-lookup"><span data-stu-id="07e95-213">Put the **Product list - start** token at the beginning of the HTML block that is repeated for every product, and put the **Product list - end** token at the end of the block.</span></span>

| <span data-ttu-id="07e95-214">A token neve</span><span class="sxs-lookup"><span data-stu-id="07e95-214">Name of the token</span></span>      | <span data-ttu-id="07e95-215">Jogkivonat</span><span class="sxs-lookup"><span data-stu-id="07e95-215">Token</span></span> |
|------------------------|-------|
| <span data-ttu-id="07e95-216">Terméklista – kezdés</span><span class="sxs-lookup"><span data-stu-id="07e95-216">Product list - start</span></span>   | <span data-ttu-id="07e95-217">\<!--%tablebegin.salesline% --\></span><span class="sxs-lookup"><span data-stu-id="07e95-217">\<!--%tablebegin.salesline% --\></span></span> |
| <span data-ttu-id="07e95-218">Terméklista – befejezés</span><span class="sxs-lookup"><span data-stu-id="07e95-218">Product list - end</span></span>     | <span data-ttu-id="07e95-219">\<!--%tableend.salesline%--\></span><span class="sxs-lookup"><span data-stu-id="07e95-219">\<!--%tableend.salesline%--\></span></span> |
| <span data-ttu-id="07e95-220">Termék neve</span><span class="sxs-lookup"><span data-stu-id="07e95-220">Product name</span></span>           | <span data-ttu-id="07e95-221">%lineproductname%</span><span class="sxs-lookup"><span data-stu-id="07e95-221">%lineproductname%</span></span> |
| <span data-ttu-id="07e95-222">Leírás</span><span class="sxs-lookup"><span data-stu-id="07e95-222">Description</span></span>            | <span data-ttu-id="07e95-223">%lineproductdescription%</span><span class="sxs-lookup"><span data-stu-id="07e95-223">%lineproductdescription%</span></span> |
| <span data-ttu-id="07e95-224">Mennyiség</span><span class="sxs-lookup"><span data-stu-id="07e95-224">Quantity</span></span>               | <span data-ttu-id="07e95-225">%linequantity%</span><span class="sxs-lookup"><span data-stu-id="07e95-225">%linequantity%</span></span> |
| <span data-ttu-id="07e95-226">Sor egységára</span><span class="sxs-lookup"><span data-stu-id="07e95-226">Line unit price</span></span>        | <span data-ttu-id="07e95-227">%lineprice% (verify)</span><span class="sxs-lookup"><span data-stu-id="07e95-227">%lineprice% (verify)</span></span> |
| <span data-ttu-id="07e95-228">sortétel összege</span><span class="sxs-lookup"><span data-stu-id="07e95-228">line item total</span></span>        | <span data-ttu-id="07e95-229">%linenetamount%</span><span class="sxs-lookup"><span data-stu-id="07e95-229">%linenetamount%</span></span> |
| <span data-ttu-id="07e95-230">sorkedvezmény</span><span class="sxs-lookup"><span data-stu-id="07e95-230">line discount</span></span>          | <span data-ttu-id="07e95-231">%linediscount%</span><span class="sxs-lookup"><span data-stu-id="07e95-231">%linediscount%</span></span> |
| <span data-ttu-id="07e95-232">Szállítási dátum</span><span class="sxs-lookup"><span data-stu-id="07e95-232">Ship date</span></span>              | <span data-ttu-id="07e95-233">%lineshipdate%</span><span class="sxs-lookup"><span data-stu-id="07e95-233">%lineshipdate%</span></span> |
| <span data-ttu-id="07e95-234">Beszerzési mód</span><span class="sxs-lookup"><span data-stu-id="07e95-234">Procurement method</span></span>     | <span data-ttu-id="07e95-235">%linedeliverymode%</span><span class="sxs-lookup"><span data-stu-id="07e95-235">%linedeliverymode%</span></span> |
| <span data-ttu-id="07e95-236">szállítási cím</span><span class="sxs-lookup"><span data-stu-id="07e95-236">delivery address</span></span>       | <span data-ttu-id="07e95-237">%linedeliveryaddress%</span><span class="sxs-lookup"><span data-stu-id="07e95-237">%linedeliveryaddress%</span></span> |
| <span data-ttu-id="07e95-238">A sor értékesítési egysége</span><span class="sxs-lookup"><span data-stu-id="07e95-238">Sales unit of the line</span></span> | <span data-ttu-id="07e95-239">%lineunit%</span><span class="sxs-lookup"><span data-stu-id="07e95-239">%lineunit%</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="07e95-240">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="07e95-240">Additional resources</span></span>

[<span data-ttu-id="07e95-241">Commerce előzetes verziós környezet áttekintése</span><span class="sxs-lookup"><span data-stu-id="07e95-241">Commerce preview environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="07e95-242">Commerce előzetes verziós környezet kiépítése</span><span class="sxs-lookup"><span data-stu-id="07e95-242">Provision a Commerce preview environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="07e95-243">Commerce előzetes verziós környezet konfigurálása</span><span class="sxs-lookup"><span data-stu-id="07e95-243">Configure a Commerce preview environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="07e95-244">Commerce előzetes verziós környezet GYIK</span><span class="sxs-lookup"><span data-stu-id="07e95-244">Commerce preview environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="07e95-245">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="07e95-245">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="07e95-246">Retail Cloud Scale Unit (RCSU)</span><span class="sxs-lookup"><span data-stu-id="07e95-246">Retail Cloud Scale Unit (RCSU)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="07e95-247">Microsoft Azure-portál</span><span class="sxs-lookup"><span data-stu-id="07e95-247">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="07e95-248">Dynamics 365 Commerce-webhely</span><span class="sxs-lookup"><span data-stu-id="07e95-248">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)

[<span data-ttu-id="07e95-249">Súgóerőforrások: Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="07e95-249">Help resources for Dynamics 365 Retail</span></span>](../retail/index.md)
