---
title: E-mail-értesítési profil beállítása
description: Ez a témakör azt mutatja be, hogyan lehet egy e-mailes értesítést létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: feb28b9c801786f63282c4189d3eeb6d53ed07e1
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2020
ms.locfileid: "3003142"
---
# <a name="set-up-an-email-notification-profile"></a><span data-ttu-id="11420-103">E-mail-értesítési profil beállítása</span><span class="sxs-lookup"><span data-stu-id="11420-103">Set up an email notification profile</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="11420-104">Ez a témakör azt mutatja be, hogyan lehet egy e-mailes értesítést létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="11420-104">This topic describes how to create an email notification profile in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="11420-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="11420-105">Overview</span></span>

<span data-ttu-id="11420-106">A csatornák létrehozása előtt be kell állítani egy profilt, amely gondoskodik arról, hogy az e-mailek értesítései különböző eseményekhez, például a rendelések létrehozásához, a rendelés szállítási állapotához és a fizetési hibákhoz lehessenek elküldve.</span><span class="sxs-lookup"><span data-stu-id="11420-106">Before creating channels, you'll want to set up a profile to ensure that email notifications can be sent out for various events, such as order creation, order shipping status, and payment failure.</span></span>

<span data-ttu-id="11420-107">Az e-mail konfigurálásával kapcsolatos további tudnivalókat lásd: [E-mail konfigurálása és küldése](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-email).</span><span class="sxs-lookup"><span data-stu-id="11420-107">For additional email configuration information, see [Configure and send email](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-email).</span></span>

## <a name="create-an-email-notification-profile"></a><span data-ttu-id="11420-108">E-mail-értesítési profil létrehozása</span><span class="sxs-lookup"><span data-stu-id="11420-108">Create an email notification profile</span></span>

<span data-ttu-id="11420-109">E-mail értesítési profil létrehozásához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="11420-109">To create an email notification profile, follow these steps.</span></span>

1. <span data-ttu-id="11420-110">A navigációs ablaktáblán lépjen a **Modulok \> Kiskereskedelem és kereskedelem \> Központ beállítás \> Kiskereskedelmi e-mail értesítési profil** részhez.</span><span class="sxs-lookup"><span data-stu-id="11420-110">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Retail Email notification profile**.</span></span>
1. <span data-ttu-id="11420-111">A műveleti panelen kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="11420-111">On the action pane, click **New**.</span></span>
1. <span data-ttu-id="11420-112">Az **E-mail értesítési profilja** mezőbe írjon be egy nevet a profil meghatározásához.</span><span class="sxs-lookup"><span data-stu-id="11420-112">In the **Email notification profile** field, enter a name to identify the profile.</span></span>
1. <span data-ttu-id="11420-113">Adjon meg egy releváns leírást a **Leírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="11420-113">In the **Description** field, enter a relevant description.</span></span>
1. <span data-ttu-id="11420-114">Az **Aktív** kapcsolót állítsa **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="11420-114">Set the **Active** switch to **Yes**.</span></span>

### <a name="create-an-email-template"></a><span data-ttu-id="11420-115">E-mail sablon létrehozása</span><span class="sxs-lookup"><span data-stu-id="11420-115">Create an email template</span></span>

<span data-ttu-id="11420-116">Mielőtt e-mailes értesítést lehetne létrehozni, létre kell hoznia egy szervezeti e-mail-sablont, amely tartalmazza a feladók e-mailes adatait és az e-mail-sablont.</span><span class="sxs-lookup"><span data-stu-id="11420-116">Before an email notification can be created, you must create an organization email template which contains the senders email information and the email template.</span></span>

<span data-ttu-id="11420-117">E-mail-sablon létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="11420-117">To create an email template, follow these steps.</span></span>

1. <span data-ttu-id="11420-118">A navigációs ablaktáblán lépjen a **Modulok \> Kiskereskedelem és kereskedelem \> Központ beállítás \> Paraméterek \> Szervezeti e-mail-sablonok** részhez.</span><span class="sxs-lookup"><span data-stu-id="11420-118">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Parameters \> Organization email templates**.</span></span>
1. <span data-ttu-id="11420-119">A műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="11420-119">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="11420-120">Az **E-mail azonosító** mezőbe írjon be egy azonosítót, amely segít a sablon azonosításában.</span><span class="sxs-lookup"><span data-stu-id="11420-120">In the **Email ID** field, enter an ID to help identify this template.</span></span>
1. <span data-ttu-id="11420-121">A **Küldő név** mezőben adja meg a küldő nevét.</span><span class="sxs-lookup"><span data-stu-id="11420-121">In the **Sends name** field, enter the senders name.</span></span>
1. <span data-ttu-id="11420-122">Adjon meg egy releváns leírást az **E-mail leírása** mezőben.</span><span class="sxs-lookup"><span data-stu-id="11420-122">In the **Email Description**, enter a meaningful description.</span></span>
1. <span data-ttu-id="11420-123">A **Feladó e-mail címe** mezőbe írja be a feladók e-mail címét.</span><span class="sxs-lookup"><span data-stu-id="11420-123">In the **Sender email**, enter the senders email address.</span></span>
1. <span data-ttu-id="11420-124">Az **Általános** részben töltse ki az esetleges opcionális adatokat (például az e-mail prioritását).</span><span class="sxs-lookup"><span data-stu-id="11420-124">In the **General** section, fill out any optional information needed (such as the email priority).</span></span>
1. <span data-ttu-id="11420-125">Bontsa ki az **E-mail üzenet tartalma** szakaszt, és válassza az **Új** parancsot a sablon tartalmának létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="11420-125">Expand the **Email message content** section and select **New** to create the template content.</span></span> <span data-ttu-id="11420-126">Minden tartalmi elemhez válassza ki a nyelvet, és adja meg az e-mail tárgysorát.</span><span class="sxs-lookup"><span data-stu-id="11420-126">For each content item, select the language and provide the email subject line.</span></span> <span data-ttu-id="11420-127">Ha az e-mail törzset fog tartalmazni, győződjön meg arról, hogy be van jelölve a **Törzs létezik** jelölőnégyzet.</span><span class="sxs-lookup"><span data-stu-id="11420-127">If the email will have a body, ensure that the **Has body** box is checked.</span></span>
1. <span data-ttu-id="11420-128">A műveleti ablaktáblán válassza ki az **E-mail üzenet** elemet az e-mail szövegtörzssablon megadásához.</span><span class="sxs-lookup"><span data-stu-id="11420-128">On the action pane, select **Email message** to provide an email body template.</span></span>

<span data-ttu-id="11420-129">A következő képen látható néhány példa az e-mail-sablon beállításaira.</span><span class="sxs-lookup"><span data-stu-id="11420-129">The following image shows some example email template settings.</span></span>

![E-mail-sablon beállításai](media/email-template.png)

### <a name="create-an-email-event"></a><span data-ttu-id="11420-131">E-mail esemény létrehozása</span><span class="sxs-lookup"><span data-stu-id="11420-131">Create an email event</span></span>

<span data-ttu-id="11420-132">E-mail-esemény létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="11420-132">To create an email event, follow these steps.</span></span>

1. <span data-ttu-id="11420-133">A navigációs ablaktáblán lépjen a **Modulok \> Kiskereskedelem és kereskedelem \> Központ beállítás \> Kiskereskedelmi e-mail értesítési profil** részhez.</span><span class="sxs-lookup"><span data-stu-id="11420-133">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Retail Email notification profile**.</span></span>
1. <span data-ttu-id="11420-134">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="11420-134">In the list, find and select the desired record.</span></span> 
1. <span data-ttu-id="11420-135">Válassza ki az e-mail sablont az **E-mail azonosítója** legördülő listából.</span><span class="sxs-lookup"><span data-stu-id="11420-135">Select the email template from the **Email ID** drop-down list.</span></span>
1. <span data-ttu-id="11420-136">Válassza ki a megfelelő **E-mail-értesítés típusa** kiválasztást a legördülő listából.</span><span class="sxs-lookup"><span data-stu-id="11420-136">Select the appropriate **Email notification type** from the drop-down list.</span></span>
1. <span data-ttu-id="11420-137">Jelölje be az **Aktív** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="11420-137">Select the **Active** check box.</span></span>
1. <span data-ttu-id="11420-138">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="11420-138">On the action pane, select **Save**.</span></span>

<span data-ttu-id="11420-139">A következő képen látható néhány példa az e-mail-értesítés beállításaira.</span><span class="sxs-lookup"><span data-stu-id="11420-139">The following image shows some example retail event notification settings.</span></span>

![Kiskereskedelmi esemény értesítési beállításai](media/email-notification-profile.png)

## <a name="additional-resources"></a><span data-ttu-id="11420-141">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="11420-141">Additional resources</span></span>

[<span data-ttu-id="11420-142">E-mail konfigurálása és küldése</span><span class="sxs-lookup"><span data-stu-id="11420-142">Configure and send email</span></span>](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-email)

[<span data-ttu-id="11420-143">Csatornák áttekintése</span><span class="sxs-lookup"><span data-stu-id="11420-143">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="11420-144">Csatornák beállításának előfeltételei</span><span class="sxs-lookup"><span data-stu-id="11420-144">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="11420-145">Szervezetek és szervezeti hierarchiák áttekintése</span><span class="sxs-lookup"><span data-stu-id="11420-145">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)
