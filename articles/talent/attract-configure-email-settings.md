---
title: E-mail beállítások megadása a Microsoft Dynamics 365 Talent - Attract esetében
description: Ez a témakör azt mutatja be, hogyan lehet beállítani az elküldött e-mailek beállításait a Microsoft Dynamcis 365 Talent - Attract esetében.
author: andreabichsel
manager: AnnBe
ms.date: 06/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.search.industry: ''
ms.author: anbichse
ms.search.validFrom: 2019-06-04
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: a457deec757a5d5a3e01c6903b2dd7a9d975ef0b
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/03/2019
ms.locfileid: "2551541"
---
# <a name="configure-email-settings-in-microsoft-dynamics-365-talent---attract"></a><span data-ttu-id="14de9-103">E-mail beállítások megadása a Microsoft Dynamics 365 Talent - Attract esetében</span><span class="sxs-lookup"><span data-stu-id="14de9-103">Configure email settings in Microsoft Dynamics 365 Talent - Attract</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="14de9-104">A márkanév bizalmi kapcsolatot létesít, és segít felépíteni egy kapcsolatot a jelentkezők előtt, még mielőtt jelentkeznének a beosztásokra.</span><span class="sxs-lookup"><span data-stu-id="14de9-104">Your brand establishes trust and helps you build a relationship with candidates before they even apply for your positions.</span></span> <span data-ttu-id="14de9-105">A pozitív márkaértékelés vonzza a legjobb tehetséget, és növeli a meglévő alkalmazottak hűségét.</span><span class="sxs-lookup"><span data-stu-id="14de9-105">Positive brand perception attracts top talent and increases the loyalty of existing employees.</span></span> <span data-ttu-id="14de9-106">Microsoft Dynamics 365 Talent: Attract lehetővé teszi az e-mailek konfigurálását, hogy azok tükrözzék a vállalat márkáját.</span><span class="sxs-lookup"><span data-stu-id="14de9-106">Microsoft Dynamics 365 Talent: Attract lets you configure emails so that they reflect your company's brand.</span></span> <span data-ttu-id="14de9-107">Ennek megfelelően a pályázók számára a jelentkezési folyamat során egységes tapasztalatot lehet biztosítani.</span><span class="sxs-lookup"><span data-stu-id="14de9-107">Therefore, you can provide a consistent experience to job candidates as they progress through the application process.</span></span>

<span data-ttu-id="14de9-108">Az Attract a következő műveletek végrehajtását teszi lehetővé:</span><span class="sxs-lookup"><span data-stu-id="14de9-108">Attract lets you perform these actions:</span></span>

- <span data-ttu-id="14de9-109">E-mailek beállításainak konfigurálása annak érdekében, hogy a vállalat Microsoft Exchange e-mail szolgáltatási fiókját használja a rendszer.</span><span class="sxs-lookup"><span data-stu-id="14de9-109">Configure email settings so that your company's Microsoft Exchange email service account is used.</span></span> <span data-ttu-id="14de9-110">Ily módon a jelentkezők tudják, hogy az e-mailek a vállalatától érkeznek.</span><span class="sxs-lookup"><span data-stu-id="14de9-110">In this way, candidates know that the emails are coming from your company.</span></span> <span data-ttu-id="14de9-111">Beállíthatja például a beállításokat úgy, hogy a jelentkezők a `recruiting@contoso.com` címről kapjanak e-maileket, és ne a `contoso@microsoft.com` címről.</span><span class="sxs-lookup"><span data-stu-id="14de9-111">For example, you can configure your settings so that candidates receive emails from `recruiting@contoso.com` instead of `contoso@microsoft.com`.</span></span>
- <span data-ttu-id="14de9-112">E-mail értesítések konzisztens márkázásának létrehozásához globális fejlécet és láblécet kell megadni az összes e-mail sablonhoz.</span><span class="sxs-lookup"><span data-stu-id="14de9-112">Create consistent branding for all your email communications by setting a global header and footer for email templates.</span></span> 

> [!NOTE]
> <span data-ttu-id="14de9-113">Annak konfigurálásához, hogy az Attract a vállalat e-mail szolgáltatási fiókját használja az e-mail küldéshez, szüksége van az átfogó felvételi bővítményre.</span><span class="sxs-lookup"><span data-stu-id="14de9-113">To configure Attract so that it uses your company's email service account to send email, you need the Comprehensive hiring add-on.</span></span>

## <a name="connect-an-email-service-account"></a><span data-ttu-id="14de9-114">E-mail szolgáltatási fiók csatlakoztatása</span><span class="sxs-lookup"><span data-stu-id="14de9-114">Connect an email service account</span></span>

<span data-ttu-id="14de9-115">A vállalat e-mail szolgáltatási fiókjának csatlakoztatásával márkázott e-mail élményt nyújthat a beosztásra jelentkezőknek.</span><span class="sxs-lookup"><span data-stu-id="14de9-115">By connecting your company's email service account, you can create a branded email experience for your job candidates.</span></span> <span data-ttu-id="14de9-116">Ha nem csatlakoztatja a vállalati fiókot, akkor az Attract az alapértelmezett Microsoft védjeggyel ellátott e-mail szolgáltatásfiók használatát.</span><span class="sxs-lookup"><span data-stu-id="14de9-116">If you don't connect your company account, Attract uses the default Microsoft-branded email service account.</span></span>

1. <span data-ttu-id="14de9-117">Válassza ki a **Beállítások** gombot (fogaskerék-szimbólum a jobb felső sarokban), majd válassza a **Felügyeleti központ** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="14de9-117">Select **Settings** (the gear symbol in the upper-right corner), and then select **Admin center**.</span></span>
2. <span data-ttu-id="14de9-118">Válassza ki az **E-mail beállítások** lapon, az **E-mail szolgáltatások fiókja** területén a **Vállalati számla összekapcsolása** beállítást.</span><span class="sxs-lookup"><span data-stu-id="14de9-118">On the **Email settings** tab, under **Email service accounts**, select **Connect a company account**.</span></span>

    ![A vállalat e-mail szolgáltatási fiókjának csatlakoztatása az Attractban](./media/attract-admin-email-service-accounts.png)

    <span data-ttu-id="14de9-120">A megosztott e-mail fiókok létrehozásával kapcsolatos további tudnivalókat lásd: [Megosztott postaládák. Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes)</span><span class="sxs-lookup"><span data-stu-id="14de9-120">For more information about how to create a shared email account, see [Shared mailboxes in Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes).</span></span>

3. <span data-ttu-id="14de9-121">Jelentkezzen be a Microsoft bejelentkezési ablakában a vállalati hitelesítő adatok segítségével.</span><span class="sxs-lookup"><span data-stu-id="14de9-121">In the Microsoft sign-in window, sign in by using your corporate credentials.</span></span>
4. <span data-ttu-id="14de9-122">Ha még nem állított be e-mail szolgáltatásfiókot, vagy ha újat szeretne hozzáadni, jelölje be az **Új szolgáltatásfiók hozzáadása** jelölőnégyzetet, majd adja meg az e-mail adatait.</span><span class="sxs-lookup"><span data-stu-id="14de9-122">If you haven't yet set up an email service account, or if you want to add a new one, select **Add new service account**, and then enter your email information.</span></span> <span data-ttu-id="14de9-123">Ha már beállította a használni kívánt e-mail szolgáltatásfiókot, válassza ki.</span><span class="sxs-lookup"><span data-stu-id="14de9-123">If you've already set up the email service account that you want to use, select it.</span></span>

<span data-ttu-id="14de9-124">Amikor az e-mail szolgáltatás fiókja sikeresen be van állítva, az **E-mail szolgáltatási fiókok** területen jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="14de9-124">When your email service account is successfully configured, you will see it listed under **Email service accounts**.</span></span>

## <a name="disconnect-an-email-service-account"></a><span data-ttu-id="14de9-125">E-mail szolgáltatási fiók lecsatlakoztatása</span><span class="sxs-lookup"><span data-stu-id="14de9-125">Disconnect an email service account</span></span>

<span data-ttu-id="14de9-126">Ha azt szeretné, hogy ne használja a vállalat tartományát az e-mailes kommunikációban az Attract, akkor leválaszthatja az e-mail szolgáltatás fiókját.</span><span class="sxs-lookup"><span data-stu-id="14de9-126">If you want to stop using your company's domain in email communications through Attract, you can disconnect an email service account.</span></span>

1. <span data-ttu-id="14de9-127">Válassza ki a **Beállítások** gombot (fogaskerék-szimbólum a jobb felső sarokban), majd válassza a **Felügyeleti központ** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="14de9-127">Select **Settings** (the gear symbol in the upper-right corner), and then select **Admin center**.</span></span>
2. <span data-ttu-id="14de9-128">Az **E-mail beállításai** lapon, az **E-mail szolgáltatások fiókjai** alatt, jelölje be a leválasztani kívánt e-mail szolgáltatásfiók melletti **További** gombot (három függőleges pont).</span><span class="sxs-lookup"><span data-stu-id="14de9-128">On the **Email settings** tab, under **Email service accounts**, select the **More** button (three vertical dots) next to the email service account that you want to disconnect.</span></span>
3. <span data-ttu-id="14de9-129">Válassza ki az **E-mail fiók lecsatlakoztatása** elemet.</span><span class="sxs-lookup"><span data-stu-id="14de9-129">Select **Disconnect email account**.</span></span>

    ![A vállalat e-mail szolgáltatási fiókjának lecsatlakoztatása](./media/attract-admin-disconnect-email-account.png)

4. <span data-ttu-id="14de9-131">Amikor a program megkérdezi, hogy jóváhagyja a műveletet, válassza a **Kapcsolat bontása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="14de9-131">When you're prompted to confirm the operation, select **Disconnect**.</span></span>

    ![A vállalat e-mail szolgáltatási fiókjának lecsatlakoztatásának megerősítése](./media/attract-admin-email-confirm-disconnect.png)

<span data-ttu-id="14de9-133">Ha nem csatlakoztat egy másik e-mail szolgáltatási fiókot, akkor az Attract a felhasználó által küldött e-maileket az alapértelmezett Microsoft védjeggyel ellátott e-mail szolgáltatási fiókból küldi.</span><span class="sxs-lookup"><span data-stu-id="14de9-133">If you don't connect a different email service account, emails that are sent from Attract will use the default Microsoft-branded email service account.</span></span>

## <a name="configure-email-template-settings"></a><span data-ttu-id="14de9-134">E-mail sablonbeállítások megadása</span><span class="sxs-lookup"><span data-stu-id="14de9-134">Configure email template settings</span></span>

<span data-ttu-id="14de9-135">A vállalat emblémáját és egyéb adatait a saját e-mail címének márkás fejlécként is feltöltheti.</span><span class="sxs-lookup"><span data-stu-id="14de9-135">You can upload an image of your company's logo and other information as a branded header for your emails.</span></span> <span data-ttu-id="14de9-136">Az adatvédelmi irányelvekre és a felhasználási feltételekre mutató hivatkozásokat is megadhat az e-mailek élőlábában.</span><span class="sxs-lookup"><span data-stu-id="14de9-136">You can also provide links to your privacy policy and terms of use in email footers.</span></span>

> [!NOTE]
> <span data-ttu-id="14de9-137">Meg kell felelnie adott ország vagy régió alkalmazandó jogszabályainak, illetve azon ország vagy régió jogszabályainak, amelyben az e-mail címzettje él.</span><span class="sxs-lookup"><span data-stu-id="14de9-137">You must comply with all applicable laws of your country or region, and also the country or region that governs the email recipient.</span></span> <span data-ttu-id="14de9-138">Ezek a jogszabályok tartalmazzák a levélszemét-ellenes szabályokat is.</span><span class="sxs-lookup"><span data-stu-id="14de9-138">These laws include anti-spam regulations.</span></span>

1. <span data-ttu-id="14de9-139">Válassza ki a **Beállítások** gombot (fogaskerék-szimbólum a jobb felső sarokban), majd válassza a **Felügyeleti központ** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="14de9-139">Select **Settings** (the gear symbol in the upper-right corner), and then select **Admin center**.</span></span>
2. <span data-ttu-id="14de9-140">Az **E-mail beállításai** lap **E-mail sablon beállításai** részén húzza az e-mail fejlécként használni kívánt képet a kép mezőbe, vagy kattintson a kép mezőbe a fájl tallózásához.</span><span class="sxs-lookup"><span data-stu-id="14de9-140">On the **Email settings** tab, under **Email template settings**, drag the image that you want to use as your email header into the image box, or click in the image box to browse for the file.</span></span> <span data-ttu-id="14de9-141">Egy meglévő kép lecseréléséhez először az **Eltávolítást** kell kiválasztania mellette.</span><span class="sxs-lookup"><span data-stu-id="14de9-141">To replace an existing image, you must first select **Remove** next to it.</span></span> <span data-ttu-id="14de9-142">A képnek JPEG, JPG, PNG vagy SVG formátumúnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="14de9-142">The image must be a JPEG, JPG, PNG, or SVG file.</span></span> <span data-ttu-id="14de9-143">A képek ajánlott szélessége 25 és 800 képpont között van, és 25 és 150 képpont között magasnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="14de9-143">The recommended size for images is between 25 and 800 pixels wide, and between 25 and 150 pixels high.</span></span> <span data-ttu-id="14de9-144">A fejléc maximális fájlmérete 1 megabájt (MB).</span><span class="sxs-lookup"><span data-stu-id="14de9-144">The maximum file size for the header is 1 megabyte (MB).</span></span>

    ![Kép hozzáadása a vállalat e-mail fejlécéhez](./media/attract-admin-email-header.png)

3. <span data-ttu-id="14de9-146">**Az ön Adatvédelmi irányelve a kommunikációra vonatkozóan** alatt adjon meg egy linket a vállalat adatvédelmi politikájához.</span><span class="sxs-lookup"><span data-stu-id="14de9-146">Under **Your Privacy policy for communications**, provide a link to your company's privacy policy.</span></span> <span data-ttu-id="14de9-147">**Az ön Felhasználási feltételei a kommunikációra vonatkozóan** alatt adja meg a vállalat felhasználási feltételeire mutató hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="14de9-147">Under **Your Terms and conditions for communication**, provide a link to your company's terms of use.</span></span>

    ![Hivatkozás hozzáadása a vállalat adatvédelmi irányelvéhez és felhasználási feltételeihez az e-mail élőlábjához](./media/attract-admin-email-footer.png)

4. <span data-ttu-id="14de9-149">Az e-mail sablon beállításainak mentéséhez válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="14de9-149">Select **Save** to save your email template settings.</span></span>
