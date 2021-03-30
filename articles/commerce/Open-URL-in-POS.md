---
title: URl megnyitása a pénztárban
description: Ez a témakör áttekintést nyújt a Dynamics 365 Commerce termék- és vevőkeresési funkcióján végrehajtott fejlesztésekről.
author: AamirAllaq
manager: AnnBe
ms.date: 01/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: 141393
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2018-10-30
ms.dyn365.ops.version: 8.1.1
ms.openlocfilehash: 91d10ac383ed860a69d2d62f4a246c5ca8690b3c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5206799"
---
# <a name="open-url-in-pos"></a><span data-ttu-id="78df7-103">URL megnyitása a pénztárban</span><span class="sxs-lookup"><span data-stu-id="78df7-103">Open URL in POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="78df7-104">Ez a témakör leírja, hogyan konfigurálható egy gomb a Retail pénztárban (POS) egy URL megnyitására.</span><span class="sxs-lookup"><span data-stu-id="78df7-104">This topic describes how you can configure a button in Retail point of sale (POS) to open a URL.</span></span> <span data-ttu-id="78df7-105">Ez a funkció nem igényli a kód testreszabását, és nem-fejlesztői szereppel rendelkező személy által konfigurálható.</span><span class="sxs-lookup"><span data-stu-id="78df7-105">This feature does not require a code customization, and can be configured by someone in a non-developer role.</span></span> 

<span data-ttu-id="78df7-106">Ez a funkció lehetővé teszi a pénztárban található gombok konfigurálását a gombrácstervező segítségével egy URL megnyitására.</span><span class="sxs-lookup"><span data-stu-id="78df7-106">This feature allows configuration of a button in POS, using the button grid designer to open a URL.</span></span> <span data-ttu-id="78df7-107">Jelenleg ez az alábbi konfigurációkban támogatott:</span><span class="sxs-lookup"><span data-stu-id="78df7-107">Currently, this is supported in the following configurations:</span></span>

- <span data-ttu-id="78df7-108">Megnyitás új ablakban.</span><span class="sxs-lookup"><span data-stu-id="78df7-108">Open in new window.</span></span>
- <span data-ttu-id="78df7-109">Megnyitás a pénztáron belül.</span><span class="sxs-lookup"><span data-stu-id="78df7-109">Open within POS.</span></span>
- <span data-ttu-id="78df7-110">Natív alkalmazás megnyitása.</span><span class="sxs-lookup"><span data-stu-id="78df7-110">Open a native app.</span></span>

## <a name="open-in-new-window"></a><span data-ttu-id="78df7-111">Megnyitás új ablakban</span><span class="sxs-lookup"><span data-stu-id="78df7-111">Open in new window</span></span>

<span data-ttu-id="78df7-112">Ez a konfiguráció határozza meg, hogy az URL-t új ablakban vagy az alkalmazáson belül nyissa meg.</span><span class="sxs-lookup"><span data-stu-id="78df7-112">This configuration defines whether to open the URL in a new window or within the app.</span></span> <span data-ttu-id="78df7-113">Ha a konfiguráció szerint a rendszer a webes URL-t az alkalmazáson belül nyitja meg, az oldalsó navigációs panel és a pénztár felső sor látható, és végezhetők rajta felhasználói interakciók.</span><span class="sxs-lookup"><span data-stu-id="78df7-113">When configured to open a web URL within the app, the side navigation panel and top bar of POS are visible and available for user interaction.</span></span> <span data-ttu-id="78df7-114">Ha a konfiguráció szerint a rendszer egy új ablakban nyissa meg, az URL egy új alkalmazásablakban nyílik meg a Modern POS for Windows alkalmazásban, és új böngészőlapon minden más pénztárkliens esetén.</span><span class="sxs-lookup"><span data-stu-id="78df7-114">When configured to open in a new window, the URL will open in a new app window on Modern POS for Windows, and in a new browser tab in all other POS clients.</span></span> <span data-ttu-id="78df7-115">A funkció engedélyezéséhez az URL-t konfigurálnia kell úgy, hogy a **Megnyitás új lapon** beállítás ki van választva.</span><span class="sxs-lookup"><span data-stu-id="78df7-115">To enable this, you must configure the URL with the **Open in new window** option selected.</span></span>

## <a name="open-within-pos"></a><span data-ttu-id="78df7-116">Megnyitás a pénztáron belül</span><span class="sxs-lookup"><span data-stu-id="78df7-116">Open within POS</span></span>

<span data-ttu-id="78df7-117">A webes URL pénztáron belül való megnyitása jelenleg csak a Modern POS on Windows szolgáltatásban támogatott.</span><span class="sxs-lookup"><span data-stu-id="78df7-117">Opening a web URL within POS is currently only supported for Modern POS on Windows.</span></span> <span data-ttu-id="78df7-118">A többi kliensen ez a lehetőség még fejlesztés alatt áll, és a jövőbeni frissítésekben tervezzük kiadni.</span><span class="sxs-lookup"><span data-stu-id="78df7-118">On other clients, this capability is under development and planned for release in future updates.</span></span> <span data-ttu-id="78df7-119">A funkció engedélyezéséhez az URL-t konfigurálnia kell úgy, hogy a **Megnyitás új lapon** beállítás nincs kiválasztva.</span><span class="sxs-lookup"><span data-stu-id="78df7-119">To enable this, you must configure the URL with the **Open in new window** option not selected.</span></span>

## <a name="open-a-native-app"></a><span data-ttu-id="78df7-120">Natív alkalmazás megnyitása</span><span class="sxs-lookup"><span data-stu-id="78df7-120">Open a native app</span></span>

<span data-ttu-id="78df7-121">Ez a funkció lehetővé teszi, hogy meghatározzon olyan nem webes URL-ket, amelyek natív alkalmazást nyitnak meg.</span><span class="sxs-lookup"><span data-stu-id="78df7-121">This feature also allows you to specify non-web URLs to open a native app.</span></span> <span data-ttu-id="78df7-122">Például megadhat olyan URL-protokollokat, mint a MailTo, SIP, IM, vagy MSTEAMS, amelyeket a fogadó eszközön a megfelelő natív alkalmazással lehet kezelni.</span><span class="sxs-lookup"><span data-stu-id="78df7-122">For example, you can specify URL protocols such as MailTo, SIP, IM, or MSTEAMS, which can then be handled by respective native apps on the host device.</span></span> <span data-ttu-id="78df7-123">A funkció engedélyezéséhez az URL-t konfigurálnia kell úgy, hogy a **Megnyitás új lapon** beállítás ki van választva.</span><span class="sxs-lookup"><span data-stu-id="78df7-123">To enable this, you must configure the URL with the **Open in new window** option selected.</span></span>

- <span data-ttu-id="78df7-124">Windows rendszert futtató számítógépekkel kapcsolatban tekintse át az [Exportálás vagy Importálás alapértelmezett alkalmazástársításai](https://docs.microsoft.com/windows-hardware/manufacture/desktop/export-or-import-default-application-associations) lehetőséget az alapértelmezett protokolltársítások kiválasztásához, ha a Telepítési lemezképek karbantartása és kezelése (DISM) rendszer használatával állítja be számítógépét.</span><span class="sxs-lookup"><span data-stu-id="78df7-124">For Windows computers, see [Export or Import Default Application Associations](https://docs.microsoft.com/windows-hardware/manufacture/desktop/export-or-import-default-application-associations) to set the default protocol associations if you are setting up your computer using Deployment Image Servicing and Management (DISM).</span></span>
- <span data-ttu-id="78df7-125">Ha MDM-et használ, mint például Intune-t a Windows számítógépei kezeléséhez, tekintse át az [Irányelv CSP - ApplicationDefaults](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults) részt.</span><span class="sxs-lookup"><span data-stu-id="78df7-125">If you are using MDM, such as Intune to manage your Windows computers, see [Policy CSP - ApplicationDefaults](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults).</span></span>
- <span data-ttu-id="78df7-126">Ha Ön fejlesztő, aki egyedi webhelyet épít, tekintse át az [Alapértelmezett alkalmazás indítása URI-hoz](https://docs.microsoft.com/windows/uwp/launch-resume/launch-default-app) részt.</span><span class="sxs-lookup"><span data-stu-id="78df7-126">If you are a developer building a custom website, see [Launch the default app for a URI](https://docs.microsoft.com/windows/uwp/launch-resume/launch-default-app).</span></span>

## <a name="open-a-native-app-seamlessly"></a><span data-ttu-id="78df7-127">Natív alkalmazás zökkenőmentes megnyitása</span><span class="sxs-lookup"><span data-stu-id="78df7-127">Open a native app seamlessly</span></span>

<span data-ttu-id="78df7-128">A Windows, iOS és Android rendszerek lehetővé teszi az alkalmazások zökkenőmentesebb megnyitását, az alkalmazás-protokoll társítás alapján.</span><span class="sxs-lookup"><span data-stu-id="78df7-128">Windows, iOS, and Android also allow opening of apps more seamlessly, based on app protocol association.</span></span> <span data-ttu-id="78df7-129">Ha az alkalmazás még nincs beállítva, hogy kezelni tudja a webes böngészőből való megnyitást, akkor előfordulhat, hogy szüksége van egy fejlesztőre, aki ezt konfigurálja.</span><span class="sxs-lookup"><span data-stu-id="78df7-129">If your app is not already configured to handle opening from a web browser, you may need a developer to configure this.</span></span>

- <span data-ttu-id="78df7-130">Windows esetén tekintse át az: [Alkalmazások engedélyezése alkalmazás URI-kezelőket használó webhelyeknek](https://docs.microsoft.com/windows/uwp/launch-resume/web-to-app-linking) részt.</span><span class="sxs-lookup"><span data-stu-id="78df7-130">For Windows, see [Enable apps for websites using app URI handlers](https://docs.microsoft.com/windows/uwp/launch-resume/web-to-app-linking).</span></span>
- <span data-ttu-id="78df7-131">iOS esetén tekintse át az: [Univerzális hivatkozások fejlesztőknek](https://developer.apple.com/ios/universal-links/)részt.</span><span class="sxs-lookup"><span data-stu-id="78df7-131">For iOS, see [Universal Links for Developers](https://developer.apple.com/ios/universal-links/).</span></span>
- <span data-ttu-id="78df7-132">Az Android esetén tekintse át [Az Android alkalmazáshivatkozások kezelése](https://developer.android.com/training/app-links/) részt.</span><span class="sxs-lookup"><span data-stu-id="78df7-132">For Android, see [Handling Android App Links](https://developer.android.com/training/app-links/).</span></span>

| <span data-ttu-id="78df7-133">Ügyfél</span><span class="sxs-lookup"><span data-stu-id="78df7-133">Client</span></span>                | <span data-ttu-id="78df7-134">Megnyitás új ablakban</span><span class="sxs-lookup"><span data-stu-id="78df7-134">Open in new window</span></span> | <span data-ttu-id="78df7-135">Natív alkalmazás megnyitása</span><span class="sxs-lookup"><span data-stu-id="78df7-135">Open native app</span></span> | <span data-ttu-id="78df7-136">Megnyitás a pénztáron belül</span><span class="sxs-lookup"><span data-stu-id="78df7-136">Open within POS</span></span> | <span data-ttu-id="78df7-137">Részletek</span><span class="sxs-lookup"><span data-stu-id="78df7-137">Details</span></span>                           |
|-----------------------|--------------------|-----------------|-----------------|-----------------------------------|
| <span data-ttu-id="78df7-138">Modern POS Windows rendszeren</span><span class="sxs-lookup"><span data-stu-id="78df7-138">Modern POS on Windows</span></span> | <span data-ttu-id="78df7-139">✓\*</span><span class="sxs-lookup"><span data-stu-id="78df7-139">✓\*</span></span>                | <span data-ttu-id="78df7-140">✓</span><span class="sxs-lookup"><span data-stu-id="78df7-140">✓</span></span>               | <span data-ttu-id="78df7-141">✓</span><span class="sxs-lookup"><span data-stu-id="78df7-141">✓</span></span>              | <span data-ttu-id="78df7-142">\* Új Modern POS ablakban nyílik meg</span><span class="sxs-lookup"><span data-stu-id="78df7-142">\* Opens in new Modern POS window</span></span> |
| <span data-ttu-id="78df7-143">Felhő pénztár</span><span class="sxs-lookup"><span data-stu-id="78df7-143">Cloud POS</span></span>             | <span data-ttu-id="78df7-144">✓\*</span><span class="sxs-lookup"><span data-stu-id="78df7-144">✓\*</span></span>                | <span data-ttu-id="78df7-145">✓</span><span class="sxs-lookup"><span data-stu-id="78df7-145">✓</span></span>               | <span data-ttu-id="78df7-146">X</span><span class="sxs-lookup"><span data-stu-id="78df7-146">X</span></span>              | <span data-ttu-id="78df7-147">\* Új böngészőlapon nyílik meg</span><span class="sxs-lookup"><span data-stu-id="78df7-147">\* Opens in new browser tab</span></span>        |
| <span data-ttu-id="78df7-148">Modern POS iOS rendszeren</span><span class="sxs-lookup"><span data-stu-id="78df7-148">Modern POS on iOS</span></span>     | <span data-ttu-id="78df7-149">✓\*</span><span class="sxs-lookup"><span data-stu-id="78df7-149">✓\*</span></span>                | <span data-ttu-id="78df7-150">✓</span><span class="sxs-lookup"><span data-stu-id="78df7-150">✓</span></span>               | <span data-ttu-id="78df7-151">X</span><span class="sxs-lookup"><span data-stu-id="78df7-151">X</span></span>              | <span data-ttu-id="78df7-152">\* Új böngészőlapon nyílik meg</span><span class="sxs-lookup"><span data-stu-id="78df7-152">\* Opens in new browser tab</span></span>        |
| <span data-ttu-id="78df7-153">Modern POS Android rendszeren</span><span class="sxs-lookup"><span data-stu-id="78df7-153">Modern POS on Android</span></span> | <span data-ttu-id="78df7-154">✓\*</span><span class="sxs-lookup"><span data-stu-id="78df7-154">✓\*</span></span>                | <span data-ttu-id="78df7-155">✓</span><span class="sxs-lookup"><span data-stu-id="78df7-155">✓</span></span>               | <span data-ttu-id="78df7-156">X</span><span class="sxs-lookup"><span data-stu-id="78df7-156">X</span></span>              | <span data-ttu-id="78df7-157">\* Új böngészőlapon nyílik meg</span><span class="sxs-lookup"><span data-stu-id="78df7-157">\* Opens in new browser tab</span></span>        |

## <a name="before-you-begin"></a><span data-ttu-id="78df7-158">Előzetes feladatok</span><span class="sxs-lookup"><span data-stu-id="78df7-158">Before you begin</span></span>

<span data-ttu-id="78df7-159">Mielőtt hozzálátna, tekintse át, hogy hogyan lehet konfigurálni a következőt: [Képernyő-elrendezések a pénztár (POS) számára](pos-screen-layouts.md).</span><span class="sxs-lookup"><span data-stu-id="78df7-159">Before you begin, review how to configure [Screen layouts for the point of sale (POS)](pos-screen-layouts.md).</span></span>

## <a name="open-url-in-pos"></a><span data-ttu-id="78df7-160">URl megnyitása a pénztárban</span><span class="sxs-lookup"><span data-stu-id="78df7-160">Open URL in POS</span></span>

<span data-ttu-id="78df7-161">Egy URL cím pénztárban való megnyitásának beállításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="78df7-161">To configure a URL to be opened in POS, perform the following steps.</span></span>

1. <span data-ttu-id="78df7-162">A központi irodában lépjen a **Retail és Commerce \> Csatornabeállítás \> Pénztárbeállítás \> Pénztár \> Képernyő-elrendezések** menüpontra.</span><span class="sxs-lookup"><span data-stu-id="78df7-162">In head office, go to **Retail and Commerce \> Channel Setup \> POS Setup \> POS \> Screen Layouts**.</span></span>
2. <span data-ttu-id="78df7-163">Válassza a **Gombrácsok \> Tervező** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="78df7-163">Select **Button Grids \> Designer**.</span></span>
3. <span data-ttu-id="78df7-164">Hozzon létre egy új gombot.</span><span class="sxs-lookup"><span data-stu-id="78df7-164">Create a new button.</span></span>
4. <span data-ttu-id="78df7-165">Válassza ki a **Gomb** tulajdonságait.</span><span class="sxs-lookup"><span data-stu-id="78df7-165">Select **Button** properties.</span></span>
5. <span data-ttu-id="78df7-166">Műveletként válassza az **URL megnyitása** elemet.</span><span class="sxs-lookup"><span data-stu-id="78df7-166">Select **Open URL** as the action.</span></span>
6. <span data-ttu-id="78df7-167">Adja meg az URL-t, amelyet használni szeretne.</span><span class="sxs-lookup"><span data-stu-id="78df7-167">Enter the URL that you want to use.</span></span>
7. <span data-ttu-id="78df7-168">Állítsa be, hogy az URL-cím megnyitása új ablakban szeretné-e.</span><span class="sxs-lookup"><span data-stu-id="78df7-168">Configure whether to open the URL in a new window.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]