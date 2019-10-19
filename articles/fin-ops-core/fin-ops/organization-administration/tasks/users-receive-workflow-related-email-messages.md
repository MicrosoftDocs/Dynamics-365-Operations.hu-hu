---
title: Segítségével a felhasználók a munkafolyamattal kapcsolatos e-mail üzeneteket.
description: Beállítható, hogy a rendszer küldjön e-maileket a felhasználók számára, amikor a munkafolyamattal kapcsolatos események zajlanak le.
author: jasongre
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, SysUserSetup
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5e08f95ef6d263ee0f8c0a94b258c8a2795786bc
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2189844"
---
# <a name="enable-users-to-receive-workflow-related-email-messages"></a><span data-ttu-id="e4808-103">Segítségével a felhasználók a munkafolyamattal kapcsolatos e-mail üzeneteket.</span><span class="sxs-lookup"><span data-stu-id="e4808-103">Enable users to receive workflow-related email messages</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e4808-104">Beállítható, hogy a rendszer küldjön e-maileket a felhasználók számára, amikor a munkafolyamattal kapcsolatos események zajlanak le.</span><span class="sxs-lookup"><span data-stu-id="e4808-104">You can configure the system to send email messages to users when workflow-related events occur.</span></span> <span data-ttu-id="e4808-105">Például e-mail üzenetek küldhetők a felhasználók számára, amikor dokumentumok vannak hozzájuk rendelve jóváhagyásra.</span><span class="sxs-lookup"><span data-stu-id="e4808-105">For example, email messages can be sent to users when documents are assigned to them for approval.</span></span> <span data-ttu-id="e4808-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="e4808-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="e4808-107">Ugorjon a **Navigációs ablaktábla > Modulok > Rendszerfelügyelet > Felhasználók > Felhasználók** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e4808-107">Go to **Navigation pane > Modules > System administration > Users > Users**.</span></span>
2. <span data-ttu-id="e4808-108">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="e4808-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="e4808-109">A **Műveleti ablaktáblán** kattintson a **Felhasználói beállítások** elemre.</span><span class="sxs-lookup"><span data-stu-id="e4808-109">On the **Action pane**, click **User options**.</span></span>
4. <span data-ttu-id="e4808-110">Kattintson a **Munkafolyamat** fülre. Győződjön meg róla, hogy az **Értesítések** szakasz ki van bontva.</span><span class="sxs-lookup"><span data-stu-id="e4808-110">Click the **Workflow** tab. Make sure that the **Notifications** section is expanded.</span></span> <span data-ttu-id="e4808-111">Az **Értesítések** szakaszban megadhatja, hogy a felhasználó hogyan kapjon értesítést a munkafolyamattal kapcsolatos eseményekről.</span><span class="sxs-lookup"><span data-stu-id="e4808-111">In the **Notifications** section, you can specify how you want the user to be notified about workflow-related events.</span></span>  
5. <span data-ttu-id="e4808-112">A **Sortétel-munkafolyamat értesítési típusa** mezőben válasszon ki egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e4808-112">In the **Line-item workflow notification type** field, select an option.</span></span>
    - <span data-ttu-id="e4808-113">Csoportosított – A sortételek értesítései egyetlen e-mailbe vannak csoportosítva.</span><span class="sxs-lookup"><span data-stu-id="e4808-113">Grouped – Notifications for line items are grouped into a single email message.</span></span>
    - <span data-ttu-id="e4808-114">Egyedi – Az egyes sortételekhez egy e-mailt küld.</span><span class="sxs-lookup"><span data-stu-id="e4808-114">Individual – An email message is sent for each line item.</span></span>  
    - <span data-ttu-id="e4808-115">Jelölje be az **Értesítések küldése e-mailben** jelölőnégyzetet, ha azt szeretné, hogy a felhasználó értesítések kapjon a kliensben.</span><span class="sxs-lookup"><span data-stu-id="e4808-115">If you want the user to receive notifications in the client, select the **Send notifications in email** check box.</span></span>  
6. <span data-ttu-id="e4808-116">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="e4808-116">Click **Save**.</span></span>
7. <span data-ttu-id="e4808-117">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="e4808-117">Close the page.</span></span>

