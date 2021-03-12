---
title: Segítségével a felhasználók a munkafolyamattal kapcsolatos e-mail üzeneteket.
description: Beállítható, hogy a rendszer küldjön e-maileket a felhasználók számára, amikor a munkafolyamattal kapcsolatos események zajlanak le.
author: jasongre
manager: AnnBe
ms.date: 06/01/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, SysUserSetup
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 221e38cbe31e2ad24a56cb2e71206a1ebcdd619e
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/19/2020
ms.locfileid: "4799004"
---
# <a name="enable-users-to-receive-workflow-related-email-messages"></a><span data-ttu-id="ce754-103">Segítségével a felhasználók a munkafolyamattal kapcsolatos e-mail üzeneteket.</span><span class="sxs-lookup"><span data-stu-id="ce754-103">Enable users to receive workflow-related email messages</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ce754-104">Beállítható, hogy a rendszer küldjön e-maileket a felhasználók számára, amikor a munkafolyamattal kapcsolatos események zajlanak le.</span><span class="sxs-lookup"><span data-stu-id="ce754-104">You can configure the system to send email messages to users when workflow-related events occur.</span></span> <span data-ttu-id="ce754-105">Például e-mail üzenetek küldhetők a felhasználók számára, amikor dokumentumok vannak hozzájuk rendelve jóváhagyásra.</span><span class="sxs-lookup"><span data-stu-id="ce754-105">For example, email messages can be sent to users when documents are assigned to them for approval.</span></span> <span data-ttu-id="ce754-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="ce754-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="ce754-107">Ugorjon a **Navigációs ablaktábla > Modulok > Rendszerfelügyelet > Felhasználók > Felhasználók** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ce754-107">Go to **Navigation pane > Modules > System administration > Users > Users**.</span></span>
2. <span data-ttu-id="ce754-108">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="ce754-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="ce754-109">A **Műveleti ablaktáblán** kattintson a **Felhasználói beállítások** elemre.</span><span class="sxs-lookup"><span data-stu-id="ce754-109">On the **Action pane**, click **User options**.</span></span>
4. <span data-ttu-id="ce754-110">Kattintson a **Munkafolyamat** fülre. Győződjön meg róla, hogy az **Értesítések** szakasz ki van bontva.</span><span class="sxs-lookup"><span data-stu-id="ce754-110">Click the **Workflow** tab. Make sure that the **Notifications** section is expanded.</span></span> <span data-ttu-id="ce754-111">Az **Értesítések** szakaszban megadhatja, hogy a felhasználó hogyan kapjon értesítést a munkafolyamattal kapcsolatos eseményekről.</span><span class="sxs-lookup"><span data-stu-id="ce754-111">In the **Notifications** section, you can specify how you want the user to be notified about workflow-related events.</span></span>  
5. <span data-ttu-id="ce754-112">A **Sortétel-munkafolyamat értesítési típusa** mezőben válasszon ki egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ce754-112">In the **Line-item workflow notification type** field, select an option.</span></span>
    - <span data-ttu-id="ce754-113">Csoportosított – A sortételek értesítései egyetlen e-mailbe vannak csoportosítva.</span><span class="sxs-lookup"><span data-stu-id="ce754-113">Grouped – Notifications for line items are grouped into a single email message.</span></span>
    - <span data-ttu-id="ce754-114">Egyedi – Az egyes sortételekhez egy e-mailt küld.</span><span class="sxs-lookup"><span data-stu-id="ce754-114">Individual – An email message is sent for each line item.</span></span>  
    - <span data-ttu-id="ce754-115">Jelölje be az **Értesítések küldése e-mailben** jelölőnégyzetet, ha azt szeretné, hogy a felhasználó értesítések kapjon a kliensben.</span><span class="sxs-lookup"><span data-stu-id="ce754-115">If you want the user to receive notifications in the client, select the **Send notifications in email** check box.</span></span>  
6. <span data-ttu-id="ce754-116">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="ce754-116">Click **Save**.</span></span>
7. <span data-ttu-id="ce754-117">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="ce754-117">Close the page.</span></span>

> [!NOTE]
> <span data-ttu-id="ce754-118">A munkafolyamat e-mail sablonjait a rendszer az e-mailek sablonjaiból vagy a szervezet e-mail sablonjaiból határozza meg attól függően, hogy a munkafolyamat rendszerszintű (nem vállalati specifikus) vagy szervezeti szintű (vállalatra jellemző) munkafolyamat-e.</span><span class="sxs-lookup"><span data-stu-id="ce754-118">The workflow email templates will be sourced from either system email templates or organization email templates depending on whether the workflow is a system-level (not company specific) or organization-level (company specific) workflow.</span></span>
