---
title: Felhasználói bejelentkezéshez használt egyéni oldalak beállítása
description: Ez a témakör azt mutatja be, hogyan lehet egyéni lapokat létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban, amelyek az Azure Active Directory (Azure AD) cég és ügyfél (B2C) közötti bérlők felhasználóinak személyre szabott bejelentkezésit kezelik.
author: brianshook
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3328fad5328ae1954a6749f9a5eebcb71c723698
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/19/2021
ms.locfileid: "5477948"
---
# <a name="set-up-custom-pages-for-user-sign-ins"></a><span data-ttu-id="ce517-103">Felhasználói bejelentkezéshez használt egyéni oldalak beállítása</span><span class="sxs-lookup"><span data-stu-id="ce517-103">Set up custom pages for user sign-ins</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ce517-104">Ez a témakör azt mutatja be, hogyan lehet egyéni lapokat létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban, amelyek az Azure Active Directory (Azure AD) cég és ügyfél (B2C) közötti bérlők felhasználóinak személyre szabott bejelentkezésit kezelik.</span><span class="sxs-lookup"><span data-stu-id="ce517-104">This topic describes how to build custom pages in Microsoft Dynamics 365 Commerce that handle customized sign-ins for users of Azure Active Directory (Azure AD) business-to-consumer (B2C) tenants.</span></span>

<span data-ttu-id="ce517-105">A Dynamics 365 Commerce alkalmazásban létrehozott egyéni lapok felhasználói bejelentkezési folyamatok kezelésére való beállításához be kell állítania azokat a Azure AD-szabályokat, amelyekre a Commerce-környezetben hivatkozni fognak.</span><span class="sxs-lookup"><span data-stu-id="ce517-105">To use custom pages that are authored in Dynamics 365 Commerce to handle user sign-in flows, you must set up the Azure AD policies that will be referenced in the Commerce environment.</span></span> <span data-ttu-id="ce517-106">A „Regisztráció és bejelentkezés”, „Profilszerkesztés” és „Új jelszó létrehozása” Azure AD B2C irányelveket az Azure AD B2C alkalmazás használatával állíthatja be.</span><span class="sxs-lookup"><span data-stu-id="ce517-106">You can configure the "Sign up and sign in," "Profile editing," and "Password reset" Azure AD B2C policies by using the Azure AD B2C application.</span></span> <span data-ttu-id="ce517-107">Az Azure AD B2C bérlő és az irányelvnevek később hivatkozhatók a létesítési folyamat során, amelyet a Commerce-környezetben, Microsoft Dynamics Lifecycle Services (LCS) használatával végeznek.</span><span class="sxs-lookup"><span data-stu-id="ce517-107">The Azure AD B2C tenant and policy names can then be referenced during the provisioning process that is done for the Commerce environment by using Microsoft Dynamics Lifecycle Services (LCS).</span></span>

<span data-ttu-id="ce517-108">Az egyéni Commerce-lapok a bejelentkezés, a regisztráció, a számlaprofil szerkesztése vagy az új jelszó beállítására szolgáló modul használatával hozhatók létre.</span><span class="sxs-lookup"><span data-stu-id="ce517-108">The custom Commerce pages can be built by using the sign in, sign up, account profile edit, or password reset module.</span></span> <span data-ttu-id="ce517-109">Az ilyen egyéni lapokhoz közzétett lap URL-címeit az Azure AD B2C házirend-konfigurációi között kell megadni az Azure-portálon.</span><span class="sxs-lookup"><span data-stu-id="ce517-109">The page URLs that are published for these custom pages should then be referenced in Azure AD B2C policy configurations in the Azure portal.</span></span>

## <a name="set-up-b2c-policies"></a><span data-ttu-id="ce517-110">B2C irányelvek beállítása</span><span class="sxs-lookup"><span data-stu-id="ce517-110">Set up B2C policies</span></span>

<span data-ttu-id="ce517-111">Miután beállította az Azure AD B2C-bérlőt, és társította a Commerce-környezethez, kattintson az **Azure AD B2C**-lapra az Azure-portálon, majd a menüben az **Irányelvek** alatt válassza a **Felhasználói folyamatok (házirendek)** parancsot.</span><span class="sxs-lookup"><span data-stu-id="ce517-111">After you set up your Azure AD B2C tenant and associate it with your Commerce environment, go to the **Azure AD B2C** page in the Azure portal, and then, on the menu, under **Policies**, select **User flows (policies)**.</span></span>

![Felhasználói folyamatok (irányelvek) parancs a menüben](./media/B2C_CustomPage_PoliciesMenu.png)

<span data-ttu-id="ce517-113">Most konfigurálhatja a „Regisztráció és bejelentkezés”, „Profilszerkesztés” és „Új jelszó létrehozása” felhasználói bejelentkezési folyamatokat.</span><span class="sxs-lookup"><span data-stu-id="ce517-113">You can now configure the "Sign up and sign in," "Profile editing," and "Password reset" user sign-in flows.</span></span>

### <a name="configure-the-sign-up-and-sign-in-policy"></a><span data-ttu-id="ce517-114">A „Regisztráció és bejelentkezés” irányelv konfigurálása</span><span class="sxs-lookup"><span data-stu-id="ce517-114">Configure the "Sign up and sign in" policy</span></span>

<span data-ttu-id="ce517-115">A „Regisztráció és bejelentkezés” irányelv konfigurálásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="ce517-115">To configure the "Sign up and sign in" policy, follow these steps.</span></span>

1. <span data-ttu-id="ce517-116">Válassza ki az **Új felhasználói folyamat** lehetőséget, majd az **Ajánlott** lapon válassza ki a **Regisztráció és bejelentkezés** irányelvet.</span><span class="sxs-lookup"><span data-stu-id="ce517-116">Select **New user flow**, and then, on the **Recommended** tab, select the **Sign up and sign in** policy.</span></span>
1. <span data-ttu-id="ce517-117">Adja meg az irányelv nevét (például **B2C\_1\_SignInSignUp**).</span><span class="sxs-lookup"><span data-stu-id="ce517-117">Enter a name for the policy (for example, **B2C\_1\_SignInSignUp**).</span></span>
1. <span data-ttu-id="ce517-118">Az **Identitásszolgáltatók** szakaszban válassza ki az irányelvhez használandó identitásszolgáltatókat.</span><span class="sxs-lookup"><span data-stu-id="ce517-118">In the **Identity Providers** section, select the identity providers to use for the policy.</span></span> <span data-ttu-id="ce517-119">Legalább az **E-mailes feliratkozás** lehetőséget be kell jelölni.</span><span class="sxs-lookup"><span data-stu-id="ce517-119">At a minimum, **Email signup** must be selected.</span></span>
1. <span data-ttu-id="ce517-120">Az **Attribútum összegyűjtése** oszlopban jelölje be az **E-mail-cím**, az **Utónév** és a **Vezetéknév** jelölőnégyzetét.</span><span class="sxs-lookup"><span data-stu-id="ce517-120">In the **Collect attribute** column, select the check boxes for **Email Address**, **Given Name**, and **Surname**.</span></span>
1. <span data-ttu-id="ce517-121">A **Visszatérítési igény** oszlopban válassza ki az **E-mail-címek**, **Utónév**, **Identitásszolgáltató**, **Vezetéknév** és **Felhasználó objektumazonosítója** jelölőnégyzeteket.</span><span class="sxs-lookup"><span data-stu-id="ce517-121">In the **Return claim** column, select the check boxes for **Email Addresses**, **Given Name**, **Identity Provider**, **Surname**, and **User's Object ID**.</span></span>

    ![Kiválasztott attribútumok és igények](./media/B2C_SignInSignUp_Attributes.png)

1. <span data-ttu-id="ce517-123">Az irányelv létrehozásához kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ce517-123">Select **OK** to create the policy.</span></span>
1. <span data-ttu-id="ce517-124">Kattintson duplán az új irányelv nevére, majd a navigációs ablakban válassza ki a **Tulajdonságok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ce517-124">Double-click the new policy name, and then, in the navigation pane, select **Properties**.</span></span>
1. <span data-ttu-id="ce517-125">Adja meg a **Oldalelrendezés JavaScript általi érvényesítésének engedélyezése (előnézet)** lehetőség esetében a **Be** értéket.</span><span class="sxs-lookup"><span data-stu-id="ce517-125">Set the **Enable JavaScript enforcing page layout (preview)** option to **On**.</span></span>

    ![Az új irányelv Tulajdonságok lapja](./media/B2C_SignInSignUp_EnableJavascript.png)

> [!NOTE]
> <span data-ttu-id="ce517-127">Az irányelv neve teljes hivatkozással jelenik meg a Commerce-környezetben.</span><span class="sxs-lookup"><span data-stu-id="ce517-127">The policy name will be fully referenced in the Commerce environment.</span></span> <span data-ttu-id="ce517-128">(A **B2C\_1\_** előtag szerepelni fog a hivatkozásban.) Az irányelveket a létrehozásuk után nem lehet átnevezni.</span><span class="sxs-lookup"><span data-stu-id="ce517-128">(The **B2C\_1\_** prefix will be included in the reference.) Policies can't be renamed after they are created.</span></span> <span data-ttu-id="ce517-129">Ha a Commerce-környezet egy meglévő irányelvét cseréli le, akkor törölheti az eredeti irányelvet, és összeállíthat egy azonos nevű új irányelvet.</span><span class="sxs-lookup"><span data-stu-id="ce517-129">If you're replacing an existing policy for your Commerce environment, you can delete the original policy and build a new policy that has the same name.</span></span> <span data-ttu-id="ce517-130">Ha a környezetet már létre lett hozva, akkor alternatív megoldásként egy szolgáltatási kérelem útján elküldheti az új irányelv nevét.</span><span class="sxs-lookup"><span data-stu-id="ce517-130">Alternatively, if the environment has already been provisioned, you can submit the new policy name through a service request.</span></span>

<span data-ttu-id="ce517-131">Az egyéni lapok összeállítását követően visszatérhet az irányelvhez, és befejezheti a beállítását.</span><span class="sxs-lookup"><span data-stu-id="ce517-131">You will return to this policy to finish the setup after you've built the custom pages.</span></span> <span data-ttu-id="ce517-132">Most zárja be az irányelvet, hogy visszatérjen az Azure-portál **Felhasználói folyamatok (irányelvek)** lapjára.</span><span class="sxs-lookup"><span data-stu-id="ce517-132">For now, close the policy to return to the **User flows (policies)** page in the Azure portal.</span></span>

### <a name="configure-the-profile-editing-policy"></a><span data-ttu-id="ce517-133">A „Profilszerkesztés” irányelv konfigurálása</span><span class="sxs-lookup"><span data-stu-id="ce517-133">Configure the "Profile editing" policy</span></span>

<span data-ttu-id="ce517-134">A „Profilszerkesztés” irányelv konfigurálásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="ce517-134">To configure the "Profile editing" policy, follow these steps.</span></span>

1. <span data-ttu-id="ce517-135">Válassza ki az **Új felhasználói folyamat** lehetőséget, majd az **Ajánlott** lapon válassza ki a **Profilszerkesztés** irányelvet.</span><span class="sxs-lookup"><span data-stu-id="ce517-135">Select **New user flow**, and then, on the **Recommended** tab, select the **Profile editing** policy.</span></span>
1. <span data-ttu-id="ce517-136">Adja meg az irányelv nevét (például **B2C\_1\_EditProfile**).</span><span class="sxs-lookup"><span data-stu-id="ce517-136">Enter a name for the policy (for example, **B2C\_1\_EditProfile**).</span></span>
1. <span data-ttu-id="ce517-137">Az **Identitásszolgáltatók** szakaszban válassza ki az irányelvhez használandó identitásszolgáltatókat.</span><span class="sxs-lookup"><span data-stu-id="ce517-137">In the **Identity Providers** section, select the identity providers to use for the policy.</span></span> <span data-ttu-id="ce517-138">Legalább a **Bejelentkezés helyi fiókkal** lehetőséget ki kell választani.</span><span class="sxs-lookup"><span data-stu-id="ce517-138">At a minimum, **Local Account SignIn** must be selected.</span></span>
1. <span data-ttu-id="ce517-139">Az **Attribútum összegyűjtése** oszlopban jelölje be az **E-mail-címek** és a **Vezetéknév** jelölőnégyzetét.</span><span class="sxs-lookup"><span data-stu-id="ce517-139">In the **Collect attribute** column, select the check boxes for **Email Addresses** and **Surname**.</span></span>
1. <span data-ttu-id="ce517-140">A **Visszatérítési igény** oszlopban válassza ki az **E-mail-címek**, **Utónév**, **Identitásszolgáltató**, **Vezetéknév** és **Felhasználó objektumazonosítója** jelölőnégyzeteket.</span><span class="sxs-lookup"><span data-stu-id="ce517-140">In the **Return claim** column, select the check boxes for **Email Addresses**, **Given Name**, **Identity Provider**, **Surname**, and **User's Object ID**.</span></span>
1. <span data-ttu-id="ce517-141">Az irányelv létrehozásához kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ce517-141">Select **OK** to create the policy.</span></span>
1. <span data-ttu-id="ce517-142">Kattintson duplán az új irányelv nevére, majd a navigációs ablakban válassza ki a **Tulajdonságok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ce517-142">Double-click the new policy name, and then, in the navigation pane, select **Properties**.</span></span>
1. <span data-ttu-id="ce517-143">Adja meg a **Oldalelrendezés JavaScript általi érvényesítésének engedélyezése (előnézet)** lehetőség esetében a **Be** értéket.</span><span class="sxs-lookup"><span data-stu-id="ce517-143">Set the **Enable JavaScript enforcing page layout (preview)** option to **On**.</span></span>

<span data-ttu-id="ce517-144">Az egyéni lapok összeállítását követően visszatérhet az irányelvhez, és befejezheti a beállítását.</span><span class="sxs-lookup"><span data-stu-id="ce517-144">You will return to this policy to finish the setup after you've built the custom pages.</span></span> <span data-ttu-id="ce517-145">Most zárja be az irányelvet, hogy visszatérjen az Azure-portál **Felhasználói folyamatok (irányelvek)** lapjára.</span><span class="sxs-lookup"><span data-stu-id="ce517-145">For now, close the policy to return to the **User flows (policies)** page in the Azure portal.</span></span>

### <a name="configure-the-password-reset-policy"></a><span data-ttu-id="ce517-146">Az „Új jelszó létrehozása” irányelv konfigurálása</span><span class="sxs-lookup"><span data-stu-id="ce517-146">Configure the "Password reset" policy</span></span>

<span data-ttu-id="ce517-147">Az „Új jelszó létrehozása” irányelv konfigurálásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="ce517-147">To configure the "Password reset" policy, follow these steps.</span></span>

1. <span data-ttu-id="ce517-148">Válassza ki az **Új felhasználói folyamat** lehetőséget, majd az **Előnézet** lapon válassza ki az **Új jelszó létrehozása v1.1** irányelvet.</span><span class="sxs-lookup"><span data-stu-id="ce517-148">Select **New user flow**, and then, on the **Preview** tab, select the **Password reset v1.1** policy.</span></span>

    ![Az Előnézet lapon kiválasztott Új jelszó létrehozása v1.1 irányelv](./media/B2C_ForgetPassword_Menu.png)

1. <span data-ttu-id="ce517-150">Adja meg az irányelv nevét (például **B2C\_1\_ForgetPassword**).</span><span class="sxs-lookup"><span data-stu-id="ce517-150">Enter a name for the policy (for example, **B2C\_1\_ForgetPassword**).</span></span>
1. <span data-ttu-id="ce517-151">Az **Identitásszolgáltatók** szakaszban válassza az **Új jelszó beállítása e-mail-cím használatával** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ce517-151">In the **Identity Providers** section, select **Reset password using email address**.</span></span>
1. <span data-ttu-id="ce517-152">A **Visszatérítési igény** oszlopban válassza ki az **E-mail-címek**, **Utónév**, **Vezetéknév** és **Felhasználó objektumazonosítója** jelölőnégyzeteket.</span><span class="sxs-lookup"><span data-stu-id="ce517-152">In the **Return claim** column, select the check boxes for **Email Addresses**, **Given Name**, **Surname**, and **User's Object ID**.</span></span>

    ![Kijelölt igények](./media/B2C_ForgetPassword_Attributes.png)

1. <span data-ttu-id="ce517-154">Az irányelv létrehozásához kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ce517-154">Select **OK** to create the policy.</span></span>
1. <span data-ttu-id="ce517-155">Kattintson duplán az új irányelv nevére, majd a navigációs ablakban válassza ki a **Tulajdonságok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ce517-155">Double-click the new policy name, and then, in the navigation pane, select **Properties**.</span></span>
1. <span data-ttu-id="ce517-156">Adja meg a **Oldalelrendezés JavaScript általi érvényesítésének engedélyezése (előnézet)** lehetőség esetében a **Be** értéket.</span><span class="sxs-lookup"><span data-stu-id="ce517-156">Set the **Enable JavaScript enforcing page layout (preview)** option to **On**.</span></span>

<span data-ttu-id="ce517-157">Az egyéni lapok összeállítását követően visszatérhet az irányelvhez, és befejezheti a beállítását.</span><span class="sxs-lookup"><span data-stu-id="ce517-157">You will return to this policy to finish the setup after you've built the custom pages.</span></span> <span data-ttu-id="ce517-158">Most zárja be az irányelvet, hogy visszatérjen az Azure-portál **Felhasználói folyamatok (irányelvek)** lapjára.</span><span class="sxs-lookup"><span data-stu-id="ce517-158">For now, close the policy to return to the **User flows (policies)** page in the Azure portal.</span></span>

## <a name="build-the-custom-pages"></a><span data-ttu-id="ce517-159">Egyéni lapok létrehozása</span><span class="sxs-lookup"><span data-stu-id="ce517-159">Build the custom pages</span></span>

<span data-ttu-id="ce517-160">Az egyéni lapoknak a felhasználói bejelentkezések kezelésére történő létrehozásához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="ce517-160">To build the custom pages to handle user sign-ins, follow these steps.</span></span>

1. <span data-ttu-id="ce517-161">Nyissa meg a webhelyét a Commerce létrehozási eszközökben.</span><span class="sxs-lookup"><span data-stu-id="ce517-161">In the Commerce authoring tools, go to your site.</span></span>
1. <span data-ttu-id="ce517-162">Állítsa össze a következő öt sablont és öt lapot:</span><span class="sxs-lookup"><span data-stu-id="ce517-162">Build the following five templates and five pages:</span></span>

    - <span data-ttu-id="ce517-163">A **Bejelentkezés** sablont és a bejelentkezési modult használó lapot.</span><span class="sxs-lookup"><span data-stu-id="ce517-163">A **Sign In** template and page that use the sign in module.</span></span>
    - <span data-ttu-id="ce517-164">A **Regisztráció** sablont és a regisztrációs modult használó lapot.</span><span class="sxs-lookup"><span data-stu-id="ce517-164">A **Sign Up** template and page that use the sign up module.</span></span>
    - <span data-ttu-id="ce517-165">Az **Új jelszó beállítása** sablont és az új jelszó beállítás modult használó lapot.</span><span class="sxs-lookup"><span data-stu-id="ce517-165">A **Password Reset** template and page that use the password reset module.</span></span>
    - <span data-ttu-id="ce517-166">Az **Új jelszó megerősítése** sablont és az új jelszó megerősítése modult használó lapot.</span><span class="sxs-lookup"><span data-stu-id="ce517-166">A **Password Reset verification** template and page that use the password reset verification module.</span></span>
    - <span data-ttu-id="ce517-167">A **Profilszerkesztés** sablont és a fiókprofil-szerkesztő modult használó lapot</span><span class="sxs-lookup"><span data-stu-id="ce517-167">A **Profile Edit** template and page that use the account profile edit module</span></span>

<span data-ttu-id="ce517-168">A lapok összeállítása során kövesse az alábbi irányelveket:</span><span class="sxs-lookup"><span data-stu-id="ce517-168">When you build the pages, follow these guidelines:</span></span>

- <span data-ttu-id="ce517-169">Minden lap vagy modul esetében használja az üzleti szükségleteinek legmegfelelőbb elrendezést és stílust.</span><span class="sxs-lookup"><span data-stu-id="ce517-169">For each page or module, use the layout and style that best suit your business requirements.</span></span>
- <span data-ttu-id="ce517-170">Tegye közzé az összes lapot és URL-t, amelyet az Azure AD B2C beállításban használni kell.</span><span class="sxs-lookup"><span data-stu-id="ce517-170">Publish all pages and URLs that must be used in the Azure AD B2C setup.</span></span>
- <span data-ttu-id="ce517-171">Miután közzétette a lapokat és az URL-címeket, gyűjtse össze az URL-eket, amelyeket az Azure AD B2C irányelv-konfigurációkhoz használni kell.</span><span class="sxs-lookup"><span data-stu-id="ce517-171">After the pages and URLs are published, collect the URLs that must be used for the Azure AD B2C policy configurations.</span></span> <span data-ttu-id="ce517-172">A **?preloadscripts=true** utótagot a program minden URL-címhez hozzáadja, amikor használatban van.</span><span class="sxs-lookup"><span data-stu-id="ce517-172">A **?preloadscripts=true** suffix will be added to every URL when it's used.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ce517-173">Ne használja újra az olyan univerzális fejléceket és lábléceket, amelyek relatív hivatkozásokkal rendelkeznek.</span><span class="sxs-lookup"><span data-stu-id="ce517-173">Don't reuse universal headers and footers that have relative links.</span></span> <span data-ttu-id="ce517-174">Ezeket a lapokat a rendszer az Azure AD B2C tartományban tárolja, amikor használatban vannak, ezért csak abszolút URL-címeket szabad használni minden hivatkozáshoz.</span><span class="sxs-lookup"><span data-stu-id="ce517-174">Because these pages will be hosted in the Azure AD B2C domain when they are used, only absolute URLs should be used for all links.</span></span>

## <a name="configure-azure-ad-b2c-policies-with-custom-page-information"></a><span data-ttu-id="ce517-175">Az Azure AD B2C irányelvek beállítása egyénilap-információkkal</span><span class="sxs-lookup"><span data-stu-id="ce517-175">Configure Azure AD B2C policies with custom page information</span></span> 

<span data-ttu-id="ce517-176">Az Azure-portálon térjen vissza az **Azure AD B2C** lapra, majd a menüben az **Irányelvek** alatt válassza a **Felhasználói folyamatok (irányelvek)** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ce517-176">In the Azure portal, return to the **Azure AD B2C** page, and then, on the menu, under **Policies**, select **User flows (policies)**.</span></span>

### <a name="update-the-sign-up-and-sign-in-policy-with-custom-page-information"></a><span data-ttu-id="ce517-177">A „Regisztráció és bejelentkezés” irányelv frissítése az egyéni lap információival</span><span class="sxs-lookup"><span data-stu-id="ce517-177">Update the "Sign up and sign in" policy with custom page information</span></span>

<span data-ttu-id="ce517-178">A „Regisztráció és bejelentkezés” irányelvnek az egyéni lap információival való frissítéséhez tegye a következőket.</span><span class="sxs-lookup"><span data-stu-id="ce517-178">To update the "Sign up and sign in" policy with custom page information, follow these steps.</span></span>

1. <span data-ttu-id="ce517-179">A korábban konfigurált **Regisztráció és bejelentkezés** irányelv navigációs ablakában válassza ki a **Lapelrendezések** elemet.</span><span class="sxs-lookup"><span data-stu-id="ce517-179">In the **Sign in and sign up** policy that you configured earlier, in the navigation pane, select **Page layouts**.</span></span>
1. <span data-ttu-id="ce517-180">Válassza ki az **Egyesített bejelentkezési vagy regisztrációs lap** elrendezést.</span><span class="sxs-lookup"><span data-stu-id="ce517-180">Select the **Unified sign up or sign in page** layout.</span></span>
1. <span data-ttu-id="ce517-181">Az **Egyéni laptartalom használata** lehetőséget állítsa be **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="ce517-181">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="ce517-182">Írja be a teljes bejelentkezési URL-t az **Egyéni lap URI** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="ce517-182">In the **Custom page URI** field, enter the full sign-in URL.</span></span> <span data-ttu-id="ce517-183">Foglalja bele a **?preloadscripts=true** utótagot.</span><span class="sxs-lookup"><span data-stu-id="ce517-183">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="ce517-184">Például írja be, hogy ``www.<my domain>.com/sign-in?preloadscripts=true``.</span><span class="sxs-lookup"><span data-stu-id="ce517-184">For example, enter ``www.<my domain>.com/sign-in?preloadscripts=true``.</span></span>
1. <span data-ttu-id="ce517-185">A **Lapelrendezés verziója (előnézet)** mezőben válassza ki a **1.2.0** értéket.</span><span class="sxs-lookup"><span data-stu-id="ce517-185">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>
1. <span data-ttu-id="ce517-186">Válassza ki a **Helyi fiók regisztrációs lapja** elrendezést.</span><span class="sxs-lookup"><span data-stu-id="ce517-186">Select the **Local account sign up page** layout.</span></span>
1. <span data-ttu-id="ce517-187">Az **Egyéni laptartalom használata** lehetőséget állítsa be **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="ce517-187">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="ce517-188">Írja be a teljes bejelentkezési URL-t az **Egyéni lap URI** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="ce517-188">In the **Custom page URI** field, enter the full sign-up URL.</span></span> <span data-ttu-id="ce517-189">Foglalja bele a **?preloadscripts=true** utótagot.</span><span class="sxs-lookup"><span data-stu-id="ce517-189">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="ce517-190">Például írja be, hogy ``www.<my domain>.com/sign-up?preloadscripts=true``.</span><span class="sxs-lookup"><span data-stu-id="ce517-190">For example, enter ``www.<my domain>.com/sign-up?preloadscripts=true``.</span></span>
1. <span data-ttu-id="ce517-191">A **Lapelrendezés verziója (előnézet)** mezőben válassza ki a **1.2.0** értéket.</span><span class="sxs-lookup"><span data-stu-id="ce517-191">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>
1. <span data-ttu-id="ce517-192">A **Felhasználói attribútumok** szakaszban hajtsa végre a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="ce517-192">In the **User attributes** section, follow these steps:</span></span>

    1. <span data-ttu-id="ce517-193">Az **E-mail-cím**, **Utónév** és **Vezetéknév** attribútumok esetében válassza a **Nem** értéket az **Ellenőrzés szükséges** mezőben.</span><span class="sxs-lookup"><span data-stu-id="ce517-193">For the **Email Address**, **Given Name**, and **Surname** attributes, select **No** in the **Requires Verification** field.</span></span>
    1. <span data-ttu-id="ce517-194">Az **Utónév** és **Vezetéknév** attribútumok esetében válassza a **Nem** értéket az **Opcionális** mezőben.</span><span class="sxs-lookup"><span data-stu-id="ce517-194">For the **Given Name** and **Surname** attributes, select **No** in the **Optional** field.</span></span>

    ![A Helyi fiók regisztrációs lap irányelvének konfigurálása](./media/B2C_SignUp_PageURLConfig.png)

### <a name="update-the-profile-editing-policy-with-custom-page-information"></a><span data-ttu-id="ce517-196">A „Profilszerkesztés” irányelv frissítése az egyéni lap információival</span><span class="sxs-lookup"><span data-stu-id="ce517-196">Update the "Profile editing" policy with custom page information</span></span>

<span data-ttu-id="ce517-197">A „Profilszerkesztés” irányelvnek az egyéni lap információival való frissítéséhez tegye a következőket.</span><span class="sxs-lookup"><span data-stu-id="ce517-197">To update the "Profile editing" policy with custom page information, follow these steps.</span></span>

1. <span data-ttu-id="ce517-198">A korábban konfigurált **Profilszerkesztés** irányelv navigációs ablakában válassza ki a **Lapelrendezések** elemet.</span><span class="sxs-lookup"><span data-stu-id="ce517-198">In the **Profile Editing** policy that you configured earlier, in the navigation pane, select **Page layouts**.</span></span>
1. <span data-ttu-id="ce517-199">Válassza ki **Profilszerkesztés lap** elrendezést.</span><span class="sxs-lookup"><span data-stu-id="ce517-199">Select the **Profile edit page** layout.</span></span>
1. <span data-ttu-id="ce517-200">Az **Egyéni laptartalom használata** lehetőséget állítsa be **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="ce517-200">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="ce517-201">Írja be a teljes profilszerkesztési URL-t az **Egyéni lap URI** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="ce517-201">In the **Custom page URI** field, enter the full profile edit URL.</span></span> <span data-ttu-id="ce517-202">Foglalja bele a **?preloadscripts=true** utótagot.</span><span class="sxs-lookup"><span data-stu-id="ce517-202">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="ce517-203">Például írja be, hogy ``www.<my domain>.com/profile-edit?preloadscripts=true``.</span><span class="sxs-lookup"><span data-stu-id="ce517-203">For example, enter ``www.<my domain>.com/profile-edit?preloadscripts=true``.</span></span>
1. <span data-ttu-id="ce517-204">A **Lapelrendezés verziója (előnézet)** mezőben válassza ki a **1.2.0** értéket.</span><span class="sxs-lookup"><span data-stu-id="ce517-204">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>
1. <span data-ttu-id="ce517-205">A **Felhasználói attribútumok** szakaszban hajtsa végre a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="ce517-205">In the **User attributes** section, follow these steps:</span></span>

    1. <span data-ttu-id="ce517-206">Az **E-mail-cím** és **Utónév** attribútumok esetében válassza a **Nem** értéket az **Ellenőrzés szükséges** mezőben.</span><span class="sxs-lookup"><span data-stu-id="ce517-206">For the **Email Address**, **Given Name** attributes, select **No** in the **Requires Verification** field.</span></span>
    1. <span data-ttu-id="ce517-207">Az **Utónév** és **Vezetéknév** attribútumok esetében válassza a **Nem** értéket az **Opcionális** mezőben.</span><span class="sxs-lookup"><span data-stu-id="ce517-207">For the **Given Name** and **Surname** attributes, select **No** in the **Optional** field.</span></span>

### <a name="update-the-password-reset-policy-with-custom-page-information"></a><span data-ttu-id="ce517-208">Az „Új jelszó létrehozása” irányelv frissítése az egyéni lap információival</span><span class="sxs-lookup"><span data-stu-id="ce517-208">Update the "Password reset" policy with custom page information</span></span>

<span data-ttu-id="ce517-209">Az „Új jelszó létrehozása” irányelvnek az egyéni lap információival való frissítéséhez tegye a következőket.</span><span class="sxs-lookup"><span data-stu-id="ce517-209">To update the "Password reset" policy with custom page information, follow these steps.</span></span>

1. <span data-ttu-id="ce517-210">A korábban konfigurált **Új jelszó létrehozása** irányelv navigációs ablakában válassza ki a **Lapelrendezések** elemet.</span><span class="sxs-lookup"><span data-stu-id="ce517-210">In the **Password Reset** policy that you configured earlier, in the navigation pane, select **Page layouts**.</span></span>
1. <span data-ttu-id="ce517-211">Válassza ki az **Új jelszó létrehozása lap** elrendezést.</span><span class="sxs-lookup"><span data-stu-id="ce517-211">Select the **New password page** layout.</span></span>
1. <span data-ttu-id="ce517-212">Az **Egyéni laptartalom használata** lehetőséget állítsa be **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="ce517-212">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="ce517-213">Írja be a teljes jelszóvisszaállítási URL-t az **Egyéni lap URI** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="ce517-213">In the **Custom page URI** field, enter the full password reset URL.</span></span> <span data-ttu-id="ce517-214">Foglalja bele a **?preloadscripts=true** utótagot.</span><span class="sxs-lookup"><span data-stu-id="ce517-214">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="ce517-215">Például írja be, hogy ``www.<my domain>.com/passwordreset?preloadscripts=true``.</span><span class="sxs-lookup"><span data-stu-id="ce517-215">For example, enter ``www.<my domain>.com/passwordreset?preloadscripts=true``.</span></span>
1. <span data-ttu-id="ce517-216">A **Lapelrendezés verziója (előnézet)** mezőben válassza ki a **1.2.0** értéket.</span><span class="sxs-lookup"><span data-stu-id="ce517-216">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>
1. <span data-ttu-id="ce517-217">Válassza ki a **Fiókellenőrzés lap** elrendezést.</span><span class="sxs-lookup"><span data-stu-id="ce517-217">Select the **Account verification page** layout.</span></span>
1. <span data-ttu-id="ce517-218">Az **Egyéni laptartalom használata** lehetőséget állítsa be **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="ce517-218">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="ce517-219">Írja be a teljes jelszóvisszaállítás-érvényesítési URL-t az **Egyéni lap URI** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="ce517-219">In the **Custom page URI** field, enter the full password reset verification URL.</span></span> <span data-ttu-id="ce517-220">Foglalja bele a **?preloadscripts=true** utótagot.</span><span class="sxs-lookup"><span data-stu-id="ce517-220">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="ce517-221">Például írja be, hogy ``www.<my domain>.com/passwordreset-verification?preloadscripts=true``.</span><span class="sxs-lookup"><span data-stu-id="ce517-221">For example, enter ``www.<my domain>.com/passwordreset-verification?preloadscripts=true``.</span></span>
1. <span data-ttu-id="ce517-222">A **Lapelrendezés verziója (előnézet)** mezőben válassza ki a **1.2.0** értéket.</span><span class="sxs-lookup"><span data-stu-id="ce517-222">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>



## <a name="customize-default-text-strings-for-labels-and-descriptions"></a><span data-ttu-id="ce517-223">Címkék és leírások alapértelmezett szöveges karakterláncainak testreszabása</span><span class="sxs-lookup"><span data-stu-id="ce517-223">Customize default text strings for labels and descriptions</span></span>

<span data-ttu-id="ce517-224">A modulkönyvtárban a bejelentkezési modulok a címkék és leírások alapértelmezett szövegével kerülnek előre kitöltésre.</span><span class="sxs-lookup"><span data-stu-id="ce517-224">In the module library, sign-in modules are prefilled with default text strings for the labels and descriptions.</span></span> <span data-ttu-id="ce517-225">Ezeket a karakterláncokat testreszabhatja a szoftverfejlesztői készletben (SDK) a bejelentkezési modul global.json fájljában található értékek frissítésével.</span><span class="sxs-lookup"><span data-stu-id="ce517-225">You can customize these strings in the software development kit (SDK) by updating the values in the global.json file for the sign in module.</span></span>

<span data-ttu-id="ce517-226">Az elfelejtett jelszó hivatkozásának alapértelmezett szövege például **Elfelejtette a jelszót?**.</span><span class="sxs-lookup"><span data-stu-id="ce517-226">For example, the default text for the forgotten password link is **Forgotten password?**.</span></span> <span data-ttu-id="ce517-227">A következőkben látható ez az alapértelmezett szöveg a bejelentkezési oldalon.</span><span class="sxs-lookup"><span data-stu-id="ce517-227">The following shows this default text on the sign-in page.</span></span>

![Alapértelmezett szöveg a bejelentkezési oldalon található elfelejtett jelszó hivatkozáshoz](./media/B2C_SignUp_ModuleFace.png)

<span data-ttu-id="ce517-229">A modulkönyvtár bejelentkezési moduljának global.json fájljában azonban szerkesztheti a szöveget az **Elfelejtett jelszó?** értékre, ahogy az a következő ábrán látható.</span><span class="sxs-lookup"><span data-stu-id="ce517-229">However, in the global.json file for the module library sign-in module, you can edit the text to **Forgot Password?**, as shown in the following illustration.</span></span>

![Frissített hivatkozásszöveg a bejelentkezési modul global.json fájljában](./media/B2C_CustomizingStringsForModule.png)

<span data-ttu-id="ce517-231">A global.json fájl frissítése és a módosítások közzététele után az új hivatkozásszöveg megjelenik a bejelentkezési modulban, mind a Commerce, mind az éles bejelentkezési lapon.</span><span class="sxs-lookup"><span data-stu-id="ce517-231">After you update the global.json file and publish your changes, the new link text appears in the sign-in module in both Commerce and on the live sign-in page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ce517-232">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="ce517-232">Additional resources</span></span>

[<span data-ttu-id="ce517-233">Tartománynév konfigurálása</span><span class="sxs-lookup"><span data-stu-id="ce517-233">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="ce517-234">Új e-kereskedelmi bérlő telepítése</span><span class="sxs-lookup"><span data-stu-id="ce517-234">Deploy a new e-commerce tenant</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="ce517-235">E-kereskedelmi webhely létrehozása</span><span class="sxs-lookup"><span data-stu-id="ce517-235">Create an e-commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="ce517-236">Dynamics 365 Commerce webhely társítása online csatornával</span><span class="sxs-lookup"><span data-stu-id="ce517-236">Associate a Dynamics 365 Commerce site with an online channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="ce517-237">Robots.txt fájlok kezelése</span><span class="sxs-lookup"><span data-stu-id="ce517-237">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="ce517-238">URL-átirányítások tömeges feltöltése</span><span class="sxs-lookup"><span data-stu-id="ce517-238">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="ce517-239">B2C-bérlő beállítása a Commerce-ben</span><span class="sxs-lookup"><span data-stu-id="ce517-239">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="ce517-240">Több B2C-bérlő konfigurálása egy Commerce környezetben</span><span class="sxs-lookup"><span data-stu-id="ce517-240">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="ce517-241">Tartalomkézbesítési hálózat (CDN) támogatásának hozzáadása</span><span class="sxs-lookup"><span data-stu-id="ce517-241">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="ce517-242">Helyalapú áruházészlelés engedélyezése</span><span class="sxs-lookup"><span data-stu-id="ce517-242">Enable location-based store detection</span></span>](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
