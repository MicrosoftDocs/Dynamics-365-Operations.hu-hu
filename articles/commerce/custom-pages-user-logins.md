---
title: Felhasználói bejelentkezéshez használt egyéni lapok beállítása
description: Ez a témakör azt mutatja be, hogyan lehet egyéni lapokat létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban, amelyek az Azure Active Directory (Azure AD) cég és ügyfél (B2C) közötti bérlők felhasználóinak személyre szabott bejelentkezésit kezelik.
author: brianshook
manager: annbe
ms.date: 12/05/2019
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
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: fe2a716d370c350c0c7e034835ff755f1ec9c6a1
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2020
ms.locfileid: "3001944"
---
# <a name="set-up-custom-pages-for-user-logins"></a><span data-ttu-id="a2661-103">Felhasználói bejelentkezéshez használt egyéni lapok beállítása</span><span class="sxs-lookup"><span data-stu-id="a2661-103">Set up custom pages for user logins</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="a2661-104">Ez a témakör azt mutatja be, hogyan lehet egyéni lapokat létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban, amelyek az Azure Active Directory (Azure AD) cég és ügyfél (B2C) közötti bérlők felhasználóinak személyre szabott bejelentkezésit kezelik.</span><span class="sxs-lookup"><span data-stu-id="a2661-104">This topic describes how to build custom pages in Microsoft Dynamics 365 Commerce that handle customized sign-ins for users of Azure Active Directory (Azure AD) business-to-consumer (B2C) tenants.</span></span>

## <a name="overview"></a><span data-ttu-id="a2661-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="a2661-105">Overview</span></span>

<span data-ttu-id="a2661-106">A Dynamics 365 Commerce alkalmazásban létrehozott egyéni lapok felhasználói bejelentkezési folyamatok kezelésére való beállításához be kell állítania azokat a Azure AD-szabályokat, amelyekre a Commerce-környezetben hivatkozni fognak.</span><span class="sxs-lookup"><span data-stu-id="a2661-106">To use custom pages that are authored in Dynamics 365 Commerce to handle user sign-in flows, you must set up the Azure AD policies that will be referenced in the Commerce environment.</span></span> <span data-ttu-id="a2661-107">A „Regisztráció és bejelentkezés”, „Profilszerkesztés” és „Új jelszó létrehozása” Azure AD B2C irányelveket az Azure AD B2C alkalmazás használatával állíthatja be.</span><span class="sxs-lookup"><span data-stu-id="a2661-107">You can configure the "Sign up and sign in," "Profile editing," and "Password reset" Azure AD B2C policies by using the Azure AD B2C application.</span></span> <span data-ttu-id="a2661-108">Az Azure AD B2C bérlő és az irányelvnevek később hivatkozhatók a létesítési folyamat során, amelyet a Commerce-környezetben, Microsoft Dynamics Lifecycle Services (LCS) használatával végeznek.</span><span class="sxs-lookup"><span data-stu-id="a2661-108">The Azure AD B2C tenant and policy names can then be referenced during the provisioning process that is done for the Commerce environment by using Microsoft Dynamics Lifecycle Services (LCS).</span></span>

<span data-ttu-id="a2661-109">Az egyéni Commerce-lapok a bejelentkezés, a regisztráció, a számlaprofil szerkesztése vagy az új jelszó beállítására szolgáló modul használatával hozhatók létre.</span><span class="sxs-lookup"><span data-stu-id="a2661-109">The custom Commerce pages can be built by using the sign in, sign up, account profile edit, or password reset module.</span></span> <span data-ttu-id="a2661-110">Az ilyen egyéni lapokhoz közzétett lap URL-címeit az Azure AD B2C házirend-konfigurációi között kell megadni az Azure-portálon.</span><span class="sxs-lookup"><span data-stu-id="a2661-110">The page URLs that are published for these custom pages should then be referenced in Azure AD B2C policy configurations in the Azure portal.</span></span>

## <a name="set-up-b2c-policies"></a><span data-ttu-id="a2661-111">B2C irányelvek beállítása</span><span class="sxs-lookup"><span data-stu-id="a2661-111">Set up B2C policies</span></span>

<span data-ttu-id="a2661-112">Miután beállította az Azure AD B2C-bérlőt, és társította a Commerce-környezethez, kattintson az **Azure AD B2C**-lapra az Azure-portálon, majd a menüben az **Irányelvek** alatt válassza a **Felhasználói folyamatok (házirendek)** parancsot.</span><span class="sxs-lookup"><span data-stu-id="a2661-112">After you set up your Azure AD B2C tenant and associate it with your Commerce environment, go to the **Azure AD B2C** page in the Azure portal, and then, on the menu, under **Policies**, select **User flows (policies)**.</span></span>

![Felhasználói folyamatok (irányelvek) parancs a menüben](./media/B2C_CustomPage_PoliciesMenu.png)

<span data-ttu-id="a2661-114">Most konfigurálhatja a „Regisztráció és bejelentkezés”, „Profilszerkesztés” és „Új jelszó létrehozása” felhasználói bejelentkezési folyamatokat.</span><span class="sxs-lookup"><span data-stu-id="a2661-114">You can now configure the "Sign up and sign in," "Profile editing," and "Password reset" user sign-in flows.</span></span>

### <a name="configure-the-sign-up-and-sign-in-policy"></a><span data-ttu-id="a2661-115">A „Regisztráció és bejelentkezés” irányelv konfigurálása</span><span class="sxs-lookup"><span data-stu-id="a2661-115">Configure the "Sign up and sign in" policy</span></span>

<span data-ttu-id="a2661-116">A „Regisztráció és bejelentkezés” irányelv konfigurálásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="a2661-116">To configure the "Sign up and sign in" policy, follow these steps.</span></span>

1. <span data-ttu-id="a2661-117">Válassza ki az **Új felhasználói folyamat** lehetőséget, majd az **Ajánlott** lapon válassza ki a **Regisztráció és bejelentkezés** irányelvet.</span><span class="sxs-lookup"><span data-stu-id="a2661-117">Select **New user flow**, and then, on the **Recommended** tab, select the **Sign up and sign in** policy.</span></span>
1. <span data-ttu-id="a2661-118">Adja meg az irányelv nevét (például **B2C\_1\_SignInSignUp**).</span><span class="sxs-lookup"><span data-stu-id="a2661-118">Enter a name for the policy (for example, **B2C\_1\_SignInSignUp**).</span></span>
1. <span data-ttu-id="a2661-119">Az **Identitásszolgáltatók** szakaszban válassza ki az irányelvhez használandó identitásszolgáltatókat.</span><span class="sxs-lookup"><span data-stu-id="a2661-119">In the **Identity Providers** section, select the identity providers to use for the policy.</span></span> <span data-ttu-id="a2661-120">Legalább az **E-mailes feliratkozás** lehetőséget be kell jelölni.</span><span class="sxs-lookup"><span data-stu-id="a2661-120">At a minimum, **Email signup** must be selected.</span></span>
1. <span data-ttu-id="a2661-121">Az **Attribútum összegyűjtése** oszlopban jelölje be az **E-mail-cím**, az **Utónév** és a **Vezetéknév** jelölőnégyzetét.</span><span class="sxs-lookup"><span data-stu-id="a2661-121">In the **Collect attribute** column, select the check boxes for **Email Address**, **Given Name**, and **Surname**.</span></span>
1. <span data-ttu-id="a2661-122">A **Visszatérítési igény** oszlopban válassza ki az **E-mail-címek**, **Utónév**, **Identitásszolgáltató**, **Vezetéknév** és **Felhasználó objektumazonosítója** jelölőnégyzeteket.</span><span class="sxs-lookup"><span data-stu-id="a2661-122">In the **Return claim** column, select the check boxes for **Email Addresses**, **Given Name**, **Identity Provider**, **Surname**, and **User's Object ID**.</span></span>

    ![Kiválasztott attribútumok és igények](./media/B2C_SignInSignUp_Attributes.png)

1. <span data-ttu-id="a2661-124">Az irányelv létrehozásához kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a2661-124">Select **OK** to create the policy.</span></span>
1. <span data-ttu-id="a2661-125">Kattintson duplán az új irányelv nevére, majd a navigációs ablakban válassza ki a **Tulajdonságok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a2661-125">Double-click the new policy name, and then, in the navigation pane, select **Properties**.</span></span>
1. <span data-ttu-id="a2661-126">Adja meg a **Oldalelrendezés JavaScript általi érvényesítésének engedélyezése (előnézet)** lehetőség esetében a **Be** értéket.</span><span class="sxs-lookup"><span data-stu-id="a2661-126">Set the **Enable JavaScript enforcing page layout (preview)** option to **On**.</span></span>

    ![Az új irányelv Tulajdonságok lapja](./media/B2C_SignInSignUp_EnableJavascript.png)

> [!NOTE]
> <span data-ttu-id="a2661-128">Az irányelv neve teljes hivatkozással jelenik meg a Commerce-környezetben.</span><span class="sxs-lookup"><span data-stu-id="a2661-128">The policy name will be fully referenced in the Commerce environment.</span></span> <span data-ttu-id="a2661-129">(A **B2C\_1\_** előtag szerepelni fog a hivatkozásban.) Az irányelveket a létrehozásuk után nem lehet átnevezni.</span><span class="sxs-lookup"><span data-stu-id="a2661-129">(The **B2C\_1\_** prefix will be included in the reference.) Policies can't be renamed after they are created.</span></span> <span data-ttu-id="a2661-130">Ha a Commerce-környezet egy meglévő irányelvét cseréli le, akkor törölheti az eredeti irányelvet, és összeállíthat egy azonos nevű új irányelvet.</span><span class="sxs-lookup"><span data-stu-id="a2661-130">If you're replacing an existing policy for your Commerce environment, you can delete the original policy and build a new policy that has the same name.</span></span> <span data-ttu-id="a2661-131">Ha a környezetet már létre lett hozva, akkor alternatív megoldásként egy szolgáltatási kérelem útján elküldheti az új irányelv nevét.</span><span class="sxs-lookup"><span data-stu-id="a2661-131">Alternatively, if the environment has already been provisioned, you can submit the new policy name through a service request.</span></span>

<span data-ttu-id="a2661-132">Az egyéni lapok összeállítását követően visszatérhet az irányelvhez, és befejezheti a beállítását.</span><span class="sxs-lookup"><span data-stu-id="a2661-132">You will return to this policy to finish the setup after you've built the custom pages.</span></span> <span data-ttu-id="a2661-133">Most zárja be az irányelvet, hogy visszatérjen az Azure-portál **Felhasználói folyamatok (irányelvek)** lapjára.</span><span class="sxs-lookup"><span data-stu-id="a2661-133">For now, close the policy to return to the **User flows (policies)** page in the Azure portal.</span></span>

### <a name="configure-the-profile-editing-policy"></a><span data-ttu-id="a2661-134">A „Profilszerkesztés” irányelv konfigurálása</span><span class="sxs-lookup"><span data-stu-id="a2661-134">Configure the "Profile editing" policy</span></span>

<span data-ttu-id="a2661-135">A „Profilszerkesztés” irányelv konfigurálásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="a2661-135">To configure the "Profile editing" policy, follow these steps.</span></span>

1. <span data-ttu-id="a2661-136">Válassza ki az **Új felhasználói folyamat** lehetőséget, majd az **Ajánlott** lapon válassza ki a **Profilszerkesztés** irányelvet.</span><span class="sxs-lookup"><span data-stu-id="a2661-136">Select **New user flow**, and then, on the **Recommended** tab, select the **Profile editing** policy.</span></span>
1. <span data-ttu-id="a2661-137">Adja meg az irányelv nevét (például **B2C\_1\_EditProfile**).</span><span class="sxs-lookup"><span data-stu-id="a2661-137">Enter a name for the policy (for example, **B2C\_1\_EditProfile**).</span></span>
1. <span data-ttu-id="a2661-138">Az **Identitásszolgáltatók** szakaszban válassza ki az irányelvhez használandó identitásszolgáltatókat.</span><span class="sxs-lookup"><span data-stu-id="a2661-138">In the **Identity Providers** section, select the identity providers to use for the policy.</span></span> <span data-ttu-id="a2661-139">Legalább a **Bejelentkezés helyi fiókkal** lehetőséget ki kell választani.</span><span class="sxs-lookup"><span data-stu-id="a2661-139">At a minimum, **Local Account SignIn** must be selected.</span></span>
1. <span data-ttu-id="a2661-140">Az **Attribútum összegyűjtése** oszlopban jelölje be az **E-mail-címek** és a **Vezetéknév** jelölőnégyzetét.</span><span class="sxs-lookup"><span data-stu-id="a2661-140">In the **Collect attribute** column, select the check boxes for **Email Addresses** and **Surname**.</span></span>
1. <span data-ttu-id="a2661-141">A **Visszatérítési igény** oszlopban válassza ki az **E-mail-címek**, **Utónév**, **Identitásszolgáltató**, **Vezetéknév** és **Felhasználó objektumazonosítója** jelölőnégyzeteket.</span><span class="sxs-lookup"><span data-stu-id="a2661-141">In the **Return claim** column, select the check boxes for **Email Addresses**, **Given Name**, **Identity Provider**, **Surname**, and **User's Object ID**.</span></span>
1. <span data-ttu-id="a2661-142">Az irányelv létrehozásához kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a2661-142">Select **OK** to create the policy.</span></span>
1. <span data-ttu-id="a2661-143">Kattintson duplán az új irányelv nevére, majd a navigációs ablakban válassza ki a **Tulajdonságok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a2661-143">Double-click the new policy name, and then, in the navigation pane, select **Properties**.</span></span>
1. <span data-ttu-id="a2661-144">Adja meg a **Oldalelrendezés JavaScript általi érvényesítésének engedélyezése (előnézet)** lehetőség esetében a **Be** értéket.</span><span class="sxs-lookup"><span data-stu-id="a2661-144">Set the **Enable JavaScript enforcing page layout (preview)** option to **On**.</span></span>

<span data-ttu-id="a2661-145">Az egyéni lapok összeállítását követően visszatérhet az irányelvhez, és befejezheti a beállítását.</span><span class="sxs-lookup"><span data-stu-id="a2661-145">You will return to this policy to finish the setup after you've built the custom pages.</span></span> <span data-ttu-id="a2661-146">Most zárja be az irányelvet, hogy visszatérjen az Azure-portál **Felhasználói folyamatok (irányelvek)** lapjára.</span><span class="sxs-lookup"><span data-stu-id="a2661-146">For now, close the policy to return to the **User flows (policies)** page in the Azure portal.</span></span>

### <a name="configure-the-password-reset-policy"></a><span data-ttu-id="a2661-147">Az „Új jelszó létrehozása” irányelv konfigurálása</span><span class="sxs-lookup"><span data-stu-id="a2661-147">Configure the "Password reset" policy</span></span>

<span data-ttu-id="a2661-148">Az „Új jelszó létrehozása” irányelv konfigurálásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="a2661-148">To configure the "Password reset" policy, follow these steps.</span></span>

1. <span data-ttu-id="a2661-149">Válassza ki az **Új felhasználói folyamat** lehetőséget, majd az **Előnézet** lapon válassza ki az **Új jelszó létrehozása v1.1** irányelvet.</span><span class="sxs-lookup"><span data-stu-id="a2661-149">Select **New user flow**, and then, on the **Preview** tab, select the **Password reset v1.1** policy.</span></span>

    ![Az Előnézet lapon kiválasztott Új jelszó létrehozása v1.1 irányelv](./media/B2C_ForgetPassword_Menu.png)

1. <span data-ttu-id="a2661-151">Adja meg az irányelv nevét (például **B2C\_1\_ForgetPassword**).</span><span class="sxs-lookup"><span data-stu-id="a2661-151">Enter a name for the policy (for example, **B2C\_1\_ForgetPassword**).</span></span>
1. <span data-ttu-id="a2661-152">Az **Identitásszolgáltatók** szakaszban válassza az **Új jelszó beállítása e-mail-cím használatával** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a2661-152">In the **Identity Providers** section, select **Reset password using email address**.</span></span>
1. <span data-ttu-id="a2661-153">A **Visszatérítési igény** oszlopban válassza ki az **E-mail-címek**, **Utónév**, **Vezetéknév** és **Felhasználó objektumazonosítója** jelölőnégyzeteket.</span><span class="sxs-lookup"><span data-stu-id="a2661-153">In the **Return claim** column, select the check boxes for **Email Addresses**, **Given Name**, **Surname**, and **User's Object ID**.</span></span>

    ![Kijelölt igények](./media/B2C_ForgetPassword_Attributes.png)

1. <span data-ttu-id="a2661-155">Az irányelv létrehozásához kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a2661-155">Select **OK** to create the policy.</span></span>
1. <span data-ttu-id="a2661-156">Kattintson duplán az új irányelv nevére, majd a navigációs ablakban válassza ki a **Tulajdonságok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a2661-156">Double-click the new policy name, and then, in the navigation pane, select **Properties**.</span></span>
1. <span data-ttu-id="a2661-157">Adja meg a **Oldalelrendezés JavaScript általi érvényesítésének engedélyezése (előnézet)** lehetőség esetében a **Be** értéket.</span><span class="sxs-lookup"><span data-stu-id="a2661-157">Set the **Enable JavaScript enforcing page layout (preview)** option to **On**.</span></span>

<span data-ttu-id="a2661-158">Az egyéni lapok összeállítását követően visszatérhet az irányelvhez, és befejezheti a beállítását.</span><span class="sxs-lookup"><span data-stu-id="a2661-158">You will return to this policy to finish the setup after you've built the custom pages.</span></span> <span data-ttu-id="a2661-159">Most zárja be az irányelvet, hogy visszatérjen az Azure-portál **Felhasználói folyamatok (irányelvek)** lapjára.</span><span class="sxs-lookup"><span data-stu-id="a2661-159">For now, close the policy to return to the **User flows (policies)** page in the Azure portal.</span></span>

## <a name="build-the-custom-pages"></a><span data-ttu-id="a2661-160">Egyéni lapok létrehozása</span><span class="sxs-lookup"><span data-stu-id="a2661-160">Build the custom pages</span></span>

<span data-ttu-id="a2661-161">Az egyéni lapoknak a felhasználói bejelentkezések kezelésére történő létrehozásához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="a2661-161">To build the custom pages to handle user sign-ins, follow these steps.</span></span>

1. <span data-ttu-id="a2661-162">Nyissa meg a webhelyét a Commerce létrehozási eszközökben.</span><span class="sxs-lookup"><span data-stu-id="a2661-162">In the Commerce authoring tools, go to your site.</span></span>
1. <span data-ttu-id="a2661-163">Állítsa össze a következő öt sablont és öt lapot:</span><span class="sxs-lookup"><span data-stu-id="a2661-163">Build the following five templates and five pages:</span></span>

    - <span data-ttu-id="a2661-164">A **Bejelentkezés** sablont és a bejelentkezési modult használó lapot.</span><span class="sxs-lookup"><span data-stu-id="a2661-164">A **Sign In** template and page that use the sign in module.</span></span>
    - <span data-ttu-id="a2661-165">A **Regisztráció** sablont és a regisztrációs modult használó lapot.</span><span class="sxs-lookup"><span data-stu-id="a2661-165">A **Sign Up** template and page that use the sign up module.</span></span>
    - <span data-ttu-id="a2661-166">Az **Új jelszó beállítása** sablont és az új jelszó beállítás modult használó lapot.</span><span class="sxs-lookup"><span data-stu-id="a2661-166">A **Password Reset** template and page that use the password reset module.</span></span>
    - <span data-ttu-id="a2661-167">Az **Új jelszó megerősítése** sablont és az új jelszó megerősítése modult használó lapot.</span><span class="sxs-lookup"><span data-stu-id="a2661-167">A **Password Reset verification** template and page that use the password reset verification module.</span></span>
    - <span data-ttu-id="a2661-168">A **Profilszerkesztés** sablont és a fiókprofil-szerkesztő modult használó lapot</span><span class="sxs-lookup"><span data-stu-id="a2661-168">A **Profile Edit** template and page that use the account profile edit module</span></span>

<span data-ttu-id="a2661-169">A lapok összeállítása során kövesse az alábbi irányelveket:</span><span class="sxs-lookup"><span data-stu-id="a2661-169">When you build the pages, follow these guidelines:</span></span>

- <span data-ttu-id="a2661-170">Minden lap vagy modul esetében használja az üzleti szükségleteinek legmegfelelőbb elrendezést és stílust.</span><span class="sxs-lookup"><span data-stu-id="a2661-170">For each page or module, use the layout and style that best suit your business requirements.</span></span>
- <span data-ttu-id="a2661-171">Tegye közzé az összes lapot és URL-t, amelyet az Azure AD B2C beállításban használni kell.</span><span class="sxs-lookup"><span data-stu-id="a2661-171">Publish all pages and URLs that must be used in the Azure AD B2C setup.</span></span>
- <span data-ttu-id="a2661-172">Miután közzétette a lapokat és az URL-címeket, gyűjtse össze az URL-eket, amelyeket az Azure AD B2C irányelv-konfigurációkhoz használni kell.</span><span class="sxs-lookup"><span data-stu-id="a2661-172">After the pages and URLs are published, collect the URLs that must be used for the Azure AD B2C policy configurations.</span></span> <span data-ttu-id="a2661-173">A **?preloadscripts=true** utótagot a program minden URL-címhez hozzáadja, amikor használatban van.</span><span class="sxs-lookup"><span data-stu-id="a2661-173">A **?preloadscripts=true** suffix will be added to every URL when it's used.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a2661-174">Ne használja újra az olyan univerzális fejléceket és lábléceket, amelyek relatív hivatkozásokkal rendelkeznek.</span><span class="sxs-lookup"><span data-stu-id="a2661-174">Don't reuse universal headers and footers that have relative links.</span></span> <span data-ttu-id="a2661-175">Ezeket a lapokat a rendszer az Azure AD B2C tartományban tárolja, amikor használatban vannak, ezért csak abszolút URL-címeket szabad használni minden hivatkozáshoz.</span><span class="sxs-lookup"><span data-stu-id="a2661-175">Because these pages will be hosted in the Azure AD B2C domain when they are used, only absolute URLs should be used for all links.</span></span>

## <a name="configure-azure-ad-b2c-policies-with-custom-page-information"></a><span data-ttu-id="a2661-176">Az Azure AD B2C irányelvek beállítása egyénilap-információkkal</span><span class="sxs-lookup"><span data-stu-id="a2661-176">Configure Azure AD B2C policies with custom page information</span></span> 

<span data-ttu-id="a2661-177">Az Azure-portálon térjen vissza az **Azure AD B2C** lapra, majd a menüben az **Irányelvek** alatt válassza a **Felhasználói folyamatok (irányelvek)** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a2661-177">In the Azure portal, return to the **Azure AD B2C** page, and then, on the menu, under **Policies**, select **User flows (policies)**.</span></span>

### <a name="update-the-sign-up-and-sign-in-policy-with-custom-page-information"></a><span data-ttu-id="a2661-178">A „Regisztráció és bejelentkezés” irányelv frissítése az egyéni lap információival</span><span class="sxs-lookup"><span data-stu-id="a2661-178">Update the "Sign up and sign in" policy with custom page information</span></span>

<span data-ttu-id="a2661-179">A „Regisztráció és bejelentkezés” irányelvnek az egyéni lap információival való frissítéséhez tegye a következőket.</span><span class="sxs-lookup"><span data-stu-id="a2661-179">To update the "Sign up and sign in" policy with custom page information, follow these steps.</span></span>

1. <span data-ttu-id="a2661-180">A korábban konfigurált **Regisztráció és bejelentkezés** irányelv navigációs ablakában válassza ki a **Lapelrendezések** elemet.</span><span class="sxs-lookup"><span data-stu-id="a2661-180">In the **Sign in and sign up** policy that you configured earlier, in the navigation pane, select **Page layouts**.</span></span>
1. <span data-ttu-id="a2661-181">Válassza ki az **Egyesített bejelentkezési vagy regisztrációs lap** elrendezést.</span><span class="sxs-lookup"><span data-stu-id="a2661-181">Select the **Unified sign up or sign in page** layout.</span></span>
1. <span data-ttu-id="a2661-182">Az **Egyéni laptartalom használata** lehetőséget állítsa be **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="a2661-182">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="a2661-183">Írja be a teljes bejelentkezési URL-t az **Egyéni lap URI** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="a2661-183">In the **Custom page URI** field, enter the full sign-in URL.</span></span> <span data-ttu-id="a2661-184">Foglalja bele a **?preloadscripts=true** utótagot.</span><span class="sxs-lookup"><span data-stu-id="a2661-184">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="a2661-185">Például írja be, hogy ``www.<my domain>.com/sign-in?preloadscripts=true``.</span><span class="sxs-lookup"><span data-stu-id="a2661-185">For example, enter ``www.<my domain>.com/sign-in?preloadscripts=true``.</span></span>
1. <span data-ttu-id="a2661-186">A **Lapelrendezés verziója (előnézet)** mezőben válassza ki a **1.2.0** értéket.</span><span class="sxs-lookup"><span data-stu-id="a2661-186">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>
1. <span data-ttu-id="a2661-187">Válassza ki a **Helyi fiók regisztrációs lapja** elrendezést.</span><span class="sxs-lookup"><span data-stu-id="a2661-187">Select the **Local account sign up page** layout.</span></span>
1. <span data-ttu-id="a2661-188">Az **Egyéni laptartalom használata** lehetőséget állítsa be **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="a2661-188">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="a2661-189">Írja be a teljes bejelentkezési URL-t az **Egyéni lap URI** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="a2661-189">In the **Custom page URI** field, enter the full sign-up URL.</span></span> <span data-ttu-id="a2661-190">Foglalja bele a **?preloadscripts=true** utótagot.</span><span class="sxs-lookup"><span data-stu-id="a2661-190">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="a2661-191">Például írja be, hogy ``www.<my domain>.com/sign-up?preloadscripts=true``.</span><span class="sxs-lookup"><span data-stu-id="a2661-191">For example, enter ``www.<my domain>.com/sign-up?preloadscripts=true``.</span></span>
1. <span data-ttu-id="a2661-192">A **Lapelrendezés verziója (előnézet)** mezőben válassza ki a **1.2.0** értéket.</span><span class="sxs-lookup"><span data-stu-id="a2661-192">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>
1. <span data-ttu-id="a2661-193">A **Felhasználói attribútumok** szakaszban hajtsa végre a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="a2661-193">In the **User attributes** section, follow these steps:</span></span>

    1. <span data-ttu-id="a2661-194">Az **E-mail-cím**, **Utónév** és **Vezetéknév** attribútumok esetében válassza a **Nem** értéket az **Ellenőrzés szükséges** mezőben.</span><span class="sxs-lookup"><span data-stu-id="a2661-194">For the **Email Address**, **Given Name**, and **Surname** attributes, select **No** in the **Requires Verification** field.</span></span>
    1. <span data-ttu-id="a2661-195">Az **Utónév** és **Vezetéknév** attribútumok esetében válassza a **Nem** értéket az **Opcionális** mezőben.</span><span class="sxs-lookup"><span data-stu-id="a2661-195">For the **Given Name** and **Surname** attributes, select **No** in the **Optional** field.</span></span>

    ![A Helyi fiók regisztrációs lap irányelvének konfigurálása](./media/B2C_SignUp_PageURLConfig.png)

### <a name="update-the-profile-editing-policy-with-custom-page-information"></a><span data-ttu-id="a2661-197">A „Profilszerkesztés” irányelv frissítése az egyéni lap információival</span><span class="sxs-lookup"><span data-stu-id="a2661-197">Update the "Profile editing" policy with custom page information</span></span>

<span data-ttu-id="a2661-198">A „Profilszerkesztés” irányelvnek az egyéni lap információival való frissítéséhez tegye a következőket.</span><span class="sxs-lookup"><span data-stu-id="a2661-198">To update the "Profile editing" policy with custom page information, follow these steps.</span></span>

1. <span data-ttu-id="a2661-199">A korábban konfigurált **Profilszerkesztés** irányelv navigációs ablakában válassza ki a **Lapelrendezések** elemet.</span><span class="sxs-lookup"><span data-stu-id="a2661-199">In the **Profile Editing** policy that you configured earlier, in the navigation pane, select **Page layouts**.</span></span>
1. <span data-ttu-id="a2661-200">Válassza ki **Profilszerkesztés lap** elrendezést.</span><span class="sxs-lookup"><span data-stu-id="a2661-200">Select the **Profile edit page** layout.</span></span>
1. <span data-ttu-id="a2661-201">Az **Egyéni laptartalom használata** lehetőséget állítsa be **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="a2661-201">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="a2661-202">Írja be a teljes profilszerkesztési URL-t az **Egyéni lap URI** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="a2661-202">In the **Custom page URI** field, enter the full profile edit URL.</span></span> <span data-ttu-id="a2661-203">Foglalja bele a **?preloadscripts=true** utótagot.</span><span class="sxs-lookup"><span data-stu-id="a2661-203">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="a2661-204">Például írja be, hogy ``www.<my domain>.com/profile-edit?preloadscripts=true``.</span><span class="sxs-lookup"><span data-stu-id="a2661-204">For example, enter ``www.<my domain>.com/profile-edit?preloadscripts=true``.</span></span>
1. <span data-ttu-id="a2661-205">A **Lapelrendezés verziója (előnézet)** mezőben válassza ki a **1.2.0** értéket.</span><span class="sxs-lookup"><span data-stu-id="a2661-205">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>
1. <span data-ttu-id="a2661-206">A **Felhasználói attribútumok** szakaszban hajtsa végre a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="a2661-206">In the **User attributes** section, follow these steps:</span></span>

    1. <span data-ttu-id="a2661-207">Az **E-mail-cím** és **Utónév** attribútumok esetében válassza a **Nem** értéket az **Ellenőrzés szükséges** mezőben.</span><span class="sxs-lookup"><span data-stu-id="a2661-207">For the **Email Address**, **Given Name** attributes, select **No** in the **Requires Verification** field.</span></span>
    1. <span data-ttu-id="a2661-208">Az **Utónév** és **Vezetéknév** attribútumok esetében válassza a **Nem** értéket az **Opcionális** mezőben.</span><span class="sxs-lookup"><span data-stu-id="a2661-208">For the **Given Name** and **Surname** attributes, select **No** in the **Optional** field.</span></span>

### <a name="update-the-password-reset-policy-with-custom-page-information"></a><span data-ttu-id="a2661-209">Az „Új jelszó létrehozása” irányelv frissítése az egyéni lap információival</span><span class="sxs-lookup"><span data-stu-id="a2661-209">Update the "Password reset" policy with custom page information</span></span>

<span data-ttu-id="a2661-210">Az „Új jelszó létrehozása” irányelvnek az egyéni lap információival való frissítéséhez tegye a következőket.</span><span class="sxs-lookup"><span data-stu-id="a2661-210">To update the "Password reset" policy with custom page information, follow these steps.</span></span>

1. <span data-ttu-id="a2661-211">A korábban konfigurált **Új jelszó létrehozása** irányelv navigációs ablakában válassza ki a **Lapelrendezések** elemet.</span><span class="sxs-lookup"><span data-stu-id="a2661-211">In the **Password Reset** policy that you configured earlier, in the navigation pane, select **Page layouts**.</span></span>
1. <span data-ttu-id="a2661-212">Válassza ki az **Új jelszó létrehozása lap** elrendezést.</span><span class="sxs-lookup"><span data-stu-id="a2661-212">Select the **New password page** layout.</span></span>
1. <span data-ttu-id="a2661-213">Az **Egyéni laptartalom használata** lehetőséget állítsa be **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="a2661-213">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="a2661-214">Írja be a teljes jelszóvisszaállítási URL-t az **Egyéni lap URI** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="a2661-214">In the **Custom page URI** field, enter the full password reset URL.</span></span> <span data-ttu-id="a2661-215">Foglalja bele a **?preloadscripts=true** utótagot.</span><span class="sxs-lookup"><span data-stu-id="a2661-215">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="a2661-216">Például írja be, hogy ``www.<my domain>.com/passwordreset?preloadscripts=true``.</span><span class="sxs-lookup"><span data-stu-id="a2661-216">For example, enter ``www.<my domain>.com/passwordreset?preloadscripts=true``.</span></span>
1. <span data-ttu-id="a2661-217">A **Lapelrendezés verziója (előnézet)** mezőben válassza ki a **1.2.0** értéket.</span><span class="sxs-lookup"><span data-stu-id="a2661-217">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>
1. <span data-ttu-id="a2661-218">Válassza ki a **Fiókellenőrzés lap** elrendezést.</span><span class="sxs-lookup"><span data-stu-id="a2661-218">Select the **Account verification page** layout.</span></span>
1. <span data-ttu-id="a2661-219">Az **Egyéni laptartalom használata** lehetőséget állítsa be **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="a2661-219">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="a2661-220">Írja be a teljes jelszóvisszaállítás-érvényesítési URL-t az **Egyéni lap URI** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="a2661-220">In the **Custom page URI** field, enter the full password reset verification URL.</span></span> <span data-ttu-id="a2661-221">Foglalja bele a **?preloadscripts=true** utótagot.</span><span class="sxs-lookup"><span data-stu-id="a2661-221">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="a2661-222">Például írja be, hogy ``www.<my domain>.com/passwordreset-verification?preloadscripts=true``.</span><span class="sxs-lookup"><span data-stu-id="a2661-222">For example, enter ``www.<my domain>.com/passwordreset-verification?preloadscripts=true``.</span></span>
1. <span data-ttu-id="a2661-223">A **Lapelrendezés verziója (előnézet)** mezőben válassza ki a **1.2.0** értéket.</span><span class="sxs-lookup"><span data-stu-id="a2661-223">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>



## <a name="customize-default-text-strings-for-labels-and-descriptions"></a><span data-ttu-id="a2661-224">Címkék és leírások alapértelmezett szöveges karakterláncainak testreszabása</span><span class="sxs-lookup"><span data-stu-id="a2661-224">Customize default text strings for labels and descriptions</span></span>

<span data-ttu-id="a2661-225">A kezdő csomagban a bejelentkezési modulok a címkék és leírások alapértelmezett szövegével kerülnek előre kitöltésre.</span><span class="sxs-lookup"><span data-stu-id="a2661-225">In the starter kit, sign in modules are prefilled with default text strings for the labels and descriptions.</span></span> <span data-ttu-id="a2661-226">Ezeket a karakterláncokat testreszabhatja a szoftverfejlesztői készletben (SDK) a bejelentkezési modul global.json fájljában található értékek frissítésével.</span><span class="sxs-lookup"><span data-stu-id="a2661-226">You can customize these strings in the software development kit (SDK) by updating the values in the global.json file for the sign in module.</span></span>

<span data-ttu-id="a2661-227">Az elfelejtett jelszó hivatkozásának alapértelmezett szövege például **Elfelejtette a jelszót?**.</span><span class="sxs-lookup"><span data-stu-id="a2661-227">For example, the default text for the forgotten password link is **Forgotten password?**.</span></span> <span data-ttu-id="a2661-228">A következőkben látható ez az alapértelmezett szöveg a bejelentkezési oldalon.</span><span class="sxs-lookup"><span data-stu-id="a2661-228">The following shows this default text on the sign-in page.</span></span>

![Alapértelmezett szöveg a bejelentkezési oldalon található elfelejtett jelszó hivatkozáshoz](./media/B2C_SignUp_ModuleFace.png)

<span data-ttu-id="a2661-230">A kezdőkészlet bejelentkezési moduljának global.json fájljában azonban szerkesztheti a szöveget az **Elfelejtett jelszó?** értékre, ahogy az a következő ábrán látható.</span><span class="sxs-lookup"><span data-stu-id="a2661-230">However, in the global.json file for the starter kit sign in module, you can edit the text to **Forgot Password?**, as shown in the following illustration.</span></span>

![Frissített hivatkozásszöveg a bejelentkezési modul global.json fájljában](./media/B2C_CustomizingStringsForModule.png)

<span data-ttu-id="a2661-232">A global.json fájl frissítése és a módosítások közzététele után az új hivatkozásszöveg megjelenik a bejelentkezési modulban, mind a Commerce, mind az éles bejelentkezési lapon.</span><span class="sxs-lookup"><span data-stu-id="a2661-232">After you update the global.json file and publish your changes, the new link text appears in the sign in module in both Commerce and on the live sign-in page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a2661-233">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="a2661-233">Additional resources</span></span>

[<span data-ttu-id="a2661-234">A tartománynév konfigurálása</span><span class="sxs-lookup"><span data-stu-id="a2661-234">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="a2661-235">Új e-commerce webhely telepítése</span><span class="sxs-lookup"><span data-stu-id="a2661-235">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="a2661-236">E-kereskedelmi webhely létrehozása</span><span class="sxs-lookup"><span data-stu-id="a2661-236">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="a2661-237">Online webhely társítása csatornával</span><span class="sxs-lookup"><span data-stu-id="a2661-237">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="a2661-238">Robots.txt fájlok kezelése</span><span class="sxs-lookup"><span data-stu-id="a2661-238">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="a2661-239">Tartalomkézbesítési hálózat (CDN) támogatásának hozzáadása</span><span class="sxs-lookup"><span data-stu-id="a2661-239">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="a2661-240">Helyalapú áruházészlelés engedélyezése</span><span class="sxs-lookup"><span data-stu-id="a2661-240">Enable location-based store detection</span></span>](enable-store-detection.md)
