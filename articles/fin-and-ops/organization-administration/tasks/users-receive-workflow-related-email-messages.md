--- 
title: "A rendszer konfigurálása munkafolyamattal kapcsolatos e-mailek küldéséhez a felhasználóknak"
description: "Beállítható, hogy a rendszer küldjön e-maileket a felhasználók számára, amikor a munkafolyamattal kapcsolatos események zajlanak le."
author: jasongre
manager: AnnBe
ms.date: 02/21/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 764d4c9049d94ebcd55c61654aa2f4133b35bae6
ms.openlocfilehash: 04d90c9ded1ba7fb1ceac4ff1d54f54f6c43f9e9
ms.contentlocale: hu-hu
ms.lasthandoff: 08/09/2018

---
# <a name="configure-the-system-to-send-workflow-related-email-to-users"></a><span data-ttu-id="16ef4-103">A rendszer konfigurálása munkafolyamattal kapcsolatos e-mailek küldéséhez a felhasználóknak</span><span class="sxs-lookup"><span data-stu-id="16ef4-103">Configure the system to send workflow-related email to users</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="16ef4-104">Beállítható, hogy a rendszer küldjön e-maileket a felhasználók számára, amikor a munkafolyamattal kapcsolatos események zajlanak le.</span><span class="sxs-lookup"><span data-stu-id="16ef4-104">You can configure the system to send email messages to users when workflow-related events occur.</span></span> <span data-ttu-id="16ef4-105">Például e-mail üzenetek küldhetők a felhasználók számára, amikor dokumentumok vannak hozzájuk rendelve jóváhagyásra.</span><span class="sxs-lookup"><span data-stu-id="16ef4-105">For example, email messages can be sent to users when documents are assigned to them for approval.</span></span> <span data-ttu-id="16ef4-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="16ef4-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="16ef4-107">Ugrás a Rendszerfelügyelet > Felhasználók > Felhasználók elemre.</span><span class="sxs-lookup"><span data-stu-id="16ef4-107">Go to System administration > Users > Users.</span></span>
2. <span data-ttu-id="16ef4-108">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="16ef4-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="16ef4-109">Kattintson a Felhasználói beállítások lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="16ef4-109">Click User options.</span></span>
4. <span data-ttu-id="16ef4-110">Kattintson a Munkafolyamat fülre.</span><span class="sxs-lookup"><span data-stu-id="16ef4-110">Click the Workflow tab.</span></span>
    * <span data-ttu-id="16ef4-111">Győződjön meg arról, hogy az Értesítések adatterület ki legyen bontva.</span><span class="sxs-lookup"><span data-stu-id="16ef4-111">Make sure that the Notifications section is expanded.</span></span>     <span data-ttu-id="16ef4-112">Az Értesítések szakaszban megadhatja, hogy a felhasználó hogyan kapjon értesítést a munkafolyamattal kapcsolatos eseményekről.</span><span class="sxs-lookup"><span data-stu-id="16ef4-112">In the Notifications section, you can specify how you want the user to be notified about workflow-related events.</span></span>  
5. <span data-ttu-id="16ef4-113">A Sortétel-munkafolyamat értesítési típusa mezőben válasszon ki egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="16ef4-113">In the Line-item workflow notification type field, select an option.</span></span>
    * <span data-ttu-id="16ef4-114">Csoportosított – A sortételek értesítései egyetlen e-mailbe vannak csoportosítva.</span><span class="sxs-lookup"><span data-stu-id="16ef4-114">Grouped – Notifications for line items are grouped into a single email message.</span></span>    <span data-ttu-id="16ef4-115">Egyedi – Az egyes sortételekhez egy e-mailt küld.</span><span class="sxs-lookup"><span data-stu-id="16ef4-115">Individual – An email message is sent for each line item.</span></span>  
    * <span data-ttu-id="16ef4-116">Jelölje be az Értesítések küldése e-mailben jelölőnégyzetet, ha azt szeretné, hogy a felhasználó értesítések kapjon a kliensben.</span><span class="sxs-lookup"><span data-stu-id="16ef4-116">If you want the user to receive notifications in the client, select the Send notifications in email check box.</span></span>  
6. <span data-ttu-id="16ef4-117">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="16ef4-117">Click Save.</span></span>
7. <span data-ttu-id="16ef4-118">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="16ef4-118">Close the page.</span></span>


