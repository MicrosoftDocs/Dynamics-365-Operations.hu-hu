---
title: E-mail-értesítési profil beállítása
description: Ez a témakör azt mutatja be, hogyan lehet egy e-mailes értesítést létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.
author: bicyclingfool
manager: annbe
ms.date: 03/01/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: d82a1abe68ff6e162acb75c6fdc1e207af11c279
ms.sourcegitcommit: 88babb2fffe97e93bbde543633fc492120f2a4fc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/06/2021
ms.locfileid: "5555307"
---
# <a name="set-up-an-email-notification-profile"></a><span data-ttu-id="b907b-103">E-mail-értesítési profil beállítása</span><span class="sxs-lookup"><span data-stu-id="b907b-103">Set up an email notification profile</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b907b-104">Ez a témakör azt mutatja be, hogyan lehet egy e-mailes értesítést létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="b907b-104">This topic describes how to create an email notification profile in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="b907b-105">Amikor csatornákat hoz létre, létrehozhat egy e-mail-értesítési profilt.</span><span class="sxs-lookup"><span data-stu-id="b907b-105">When you create channels, you can set up an email notification profile.</span></span> <span data-ttu-id="b907b-106">Ily módon e-maileket küldhet a vevőknek különböző tranzakciós eseményekről, például a rendelés létrehozásáról, a rendelés szállítási állapotáról és a sikertelen kifizetésről.</span><span class="sxs-lookup"><span data-stu-id="b907b-106">In that way, emails can be sent to customers for various transactional events, such as order creation, order shipping status, and payment failure.</span></span>

<span data-ttu-id="b907b-107">Az e-mail konfigurálásával kapcsolatos további tudnivalókat lásd: [E-mail konfigurálása és küldése](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="b907b-107">For additional email configuration information, see [Configure and send email](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span></span>

## <a name="create-an-email-notification-profile"></a><span data-ttu-id="b907b-108">E-mail-értesítési profil létrehozása</span><span class="sxs-lookup"><span data-stu-id="b907b-108">Create an email notification profile</span></span>

<span data-ttu-id="b907b-109">E-mail értesítési profil létrehozásához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="b907b-109">To create an email notification profile, follow these steps.</span></span>

1. <span data-ttu-id="b907b-110">A navigációs ablaktáblán lépjen a **Modulok \> Kiskereskedelem és kereskedelem \> Központ beállítás \> Kereskedelmi e-mail értesítési profil** részhez.</span><span class="sxs-lookup"><span data-stu-id="b907b-110">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce email notification profile**.</span></span>
1. <span data-ttu-id="b907b-111">A műveleti panelen kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="b907b-111">On the action pane, click **New**.</span></span>
1. <span data-ttu-id="b907b-112">Az **E-mail értesítési profilja** mezőbe írjon be egy nevet a profil meghatározásához.</span><span class="sxs-lookup"><span data-stu-id="b907b-112">In the **Email notification profile** field, enter a name to identify the profile.</span></span>
1. <span data-ttu-id="b907b-113">Adjon meg egy releváns leírást a **Leírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="b907b-113">In the **Description** field, enter a relevant description.</span></span>
1. <span data-ttu-id="b907b-114">Az **Aktív** kapcsolót állítsa **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="b907b-114">Set the **Active** switch to **Yes**.</span></span>

### <a name="create-an-email-template"></a><span data-ttu-id="b907b-115">E-mail sablon létrehozása</span><span class="sxs-lookup"><span data-stu-id="b907b-115">Create an email template</span></span>

<span data-ttu-id="b907b-116">Az e-mail-értesítés típusának engedélyezése előtt szervezeti e-mail sablont kell létrehoznia a Commerce központi felületén.</span><span class="sxs-lookup"><span data-stu-id="b907b-116">Before an email notification type can be enabled, you must create an organization email template in Commerce headquarters.</span></span> <span data-ttu-id="b907b-117">Ez a sablon meghatározza az e-mail tárgyát, a feladót, az alapértelmezett nyelvet és az e-mail törzsét minden használni kívánt nyelvhez.</span><span class="sxs-lookup"><span data-stu-id="b907b-117">This template defines the email subject, sender, default language, and email body for each language that you want to support.</span></span>

<span data-ttu-id="b907b-118">E-mail-sablon létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="b907b-118">To create an email template, follow these steps.</span></span>

1. <span data-ttu-id="b907b-119">A navigációs ablaktáblán lépjen a **Modulok \> Kiskereskedelem és kereskedelem \> Központ beállítás \> Paraméterek \> Szervezeti e-mail-sablonok** részhez.</span><span class="sxs-lookup"><span data-stu-id="b907b-119">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Parameters \> Organization email templates**.</span></span>
1. <span data-ttu-id="b907b-120">A műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="b907b-120">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="b907b-121">Az **E-mail azonosító** mezőbe írjon be egy azonosítót, amely segít a sablon azonosításában.</span><span class="sxs-lookup"><span data-stu-id="b907b-121">In the **Email ID** field, enter an ID to help identify this template.</span></span>
1. <span data-ttu-id="b907b-122">A **Küldő név** mezőben adja meg a küldő nevét.</span><span class="sxs-lookup"><span data-stu-id="b907b-122">In the **Sends name** field, enter the senders name.</span></span>
1. <span data-ttu-id="b907b-123">Adjon meg egy releváns leírást az **E-mail leírása** mezőben.</span><span class="sxs-lookup"><span data-stu-id="b907b-123">In the **Email Description**, enter a meaningful description.</span></span>
1. <span data-ttu-id="b907b-124">A **Feladó e-mail címe** mezőbe írja be a feladók e-mail címét.</span><span class="sxs-lookup"><span data-stu-id="b907b-124">In the **Sender email**, enter the senders email address.</span></span>
1. <span data-ttu-id="b907b-125">Az **Általános** szakaszban válassza ki az e-mail-sablon alapértelmezett nyelvét.</span><span class="sxs-lookup"><span data-stu-id="b907b-125">In the **General** section, select a default language for the email template.</span></span> <span data-ttu-id="b907b-126">A rendszer az alapértelmezett nyelvet használja, ha a megadott nyelven nem létezik honosított sablon.</span><span class="sxs-lookup"><span data-stu-id="b907b-126">The default language will be used when no localized template exists for the specified language.</span></span>
1. <span data-ttu-id="b907b-127">Bontsa ki az **E-mail üzenet tartalma** szakaszt, és válassza az **Új** parancsot a sablon tartalmának létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="b907b-127">Expand the **Email message content** section and select **New** to create the template content.</span></span> <span data-ttu-id="b907b-128">Minden tartalmi elemhez válassza ki a nyelvet, és adja meg az e-mail tárgysorát.</span><span class="sxs-lookup"><span data-stu-id="b907b-128">For each content item, select the language and provide the email subject line.</span></span> <span data-ttu-id="b907b-129">Ha az e-mail törzset fog tartalmazni, győződjön meg arról, hogy be van jelölve a **Törzs létezik** jelölőnégyzet.</span><span class="sxs-lookup"><span data-stu-id="b907b-129">If the email will have a body, ensure that the **Has body** box is checked.</span></span>
1. <span data-ttu-id="b907b-130">A műveleti ablaktáblán válassza ki az **E-mail üzenet** elemet az e-mail szövegtörzssablon megadásához.</span><span class="sxs-lookup"><span data-stu-id="b907b-130">On the action pane, select **Email message** to provide an email body template.</span></span>

<span data-ttu-id="b907b-131">A következő képen látható néhány példa az e-mail-sablon beállításaira.</span><span class="sxs-lookup"><span data-stu-id="b907b-131">The following image shows some example email template settings.</span></span>

![E-mail-sablon beállításai](media/email-template.png)

### <a name="create-an-email-event"></a><span data-ttu-id="b907b-133">E-mail esemény létrehozása</span><span class="sxs-lookup"><span data-stu-id="b907b-133">Create an email event</span></span>

<span data-ttu-id="b907b-134">E-mail-esemény létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="b907b-134">To create an email event, follow these steps.</span></span>

1. <span data-ttu-id="b907b-135">A navigációs ablaktáblán lépjen a **Modulok \> Kiskereskedelem és kereskedelem \> Központ beállítás \> Kereskedelmi e-mail értesítési profil** részhez.</span><span class="sxs-lookup"><span data-stu-id="b907b-135">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce email notification profile**.</span></span>
1. <span data-ttu-id="b907b-136">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="b907b-136">In the list, find and select the desired record.</span></span> 
1. <span data-ttu-id="b907b-137">Válassza ki az e-mail sablont az **E-mail azonosítója** legördülő listából.</span><span class="sxs-lookup"><span data-stu-id="b907b-137">Select the email template from the **Email ID** drop-down list.</span></span>
1. <span data-ttu-id="b907b-138">Válassza ki a megfelelő **E-mail-értesítés típusa** kiválasztást a legördülő listából.</span><span class="sxs-lookup"><span data-stu-id="b907b-138">Select the appropriate **Email notification type** from the drop-down list.</span></span>
1. <span data-ttu-id="b907b-139">Jelölje be az **Aktív** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="b907b-139">Select the **Active** check box.</span></span>
1. <span data-ttu-id="b907b-140">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b907b-140">On the action pane, select **Save**.</span></span>

<span data-ttu-id="b907b-141">A következő képen látható néhány példa az eseményértesítés beállításaira.</span><span class="sxs-lookup"><span data-stu-id="b907b-141">The following image shows some example event notification settings.</span></span>

![Esemény értesítési beállításai](media/email-notification-profile.png)

### <a name="next-steps"></a><span data-ttu-id="b907b-143">További lépések</span><span class="sxs-lookup"><span data-stu-id="b907b-143">Next steps</span></span>

<span data-ttu-id="b907b-144">E-mailek küldése előtt konfigurálnia kell a kimenő levelek szolgáltatását, és be kell állítania egy kötegelt feladatot.</span><span class="sxs-lookup"><span data-stu-id="b907b-144">Before you can send mails, you must configure your outgoing mail service and set up a batch job.</span></span> <span data-ttu-id="b907b-145">További információ: [E-mailek konfigurálása és küldése](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="b907b-145">For more information, see [Configure and send email](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span></span>


## <a name="additional-resources"></a><span data-ttu-id="b907b-146">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="b907b-146">Additional resources</span></span>

[<span data-ttu-id="b907b-147">E-mail konfigurálása és küldése</span><span class="sxs-lookup"><span data-stu-id="b907b-147">Configure and send email</span></span>](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="b907b-148">Csatornák áttekintése</span><span class="sxs-lookup"><span data-stu-id="b907b-148">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="b907b-149">Csatornák beállításának előfeltételei</span><span class="sxs-lookup"><span data-stu-id="b907b-149">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="b907b-150">Szervezetek és szervezeti hierarchiák áttekintése</span><span class="sxs-lookup"><span data-stu-id="b907b-150">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
