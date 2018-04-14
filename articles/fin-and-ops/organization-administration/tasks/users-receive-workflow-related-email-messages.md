--- 
title: "Segítségével a felhasználók a munkafolyamattal kapcsolatos e-mail üzeneteket."
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
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 1062bbbfc5563a49cb0ba0b04bf99853f19e58ea
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---
# <a name="enable-users-to-receive-workflow-related-email-messages"></a><span data-ttu-id="9735f-103">Segítségével a felhasználók a munkafolyamattal kapcsolatos e-mail üzeneteket.</span><span class="sxs-lookup"><span data-stu-id="9735f-103">Enable users to receive workflow-related email messages</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9735f-104">Beállítható, hogy a rendszer küldjön e-maileket a felhasználók számára, amikor a munkafolyamattal kapcsolatos események zajlanak le.</span><span class="sxs-lookup"><span data-stu-id="9735f-104">You can configure the system to send email messages to users when workflow-related events occur.</span></span> <span data-ttu-id="9735f-105">Például e-mail üzenetek küldhetők a felhasználók számára, amikor dokumentumok vannak hozzájuk rendelve jóváhagyásra.</span><span class="sxs-lookup"><span data-stu-id="9735f-105">For example, email messages can be sent to users when documents are assigned to them for approval.</span></span> <span data-ttu-id="9735f-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="9735f-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="9735f-107">Ugrás a Rendszerfelügyelet > Felhasználók > Felhasználók elemre.</span><span class="sxs-lookup"><span data-stu-id="9735f-107">Go to System administration > Users > Users.</span></span>
2. <span data-ttu-id="9735f-108">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="9735f-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="9735f-109">Kattintson a Felhasználói beállítások lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9735f-109">Click User options.</span></span>
4. <span data-ttu-id="9735f-110">Kattintson a Munkafolyamat fülre.</span><span class="sxs-lookup"><span data-stu-id="9735f-110">Click the Workflow tab.</span></span>
    * <span data-ttu-id="9735f-111">Győződjön meg arról, hogy az Értesítések adatterület ki legyen bontva.</span><span class="sxs-lookup"><span data-stu-id="9735f-111">Make sure that the Notifications section is expanded.</span></span>     <span data-ttu-id="9735f-112">Az Értesítések szakaszban megadhatja, hogy a felhasználó hogyan kapjon értesítést a munkafolyamattal kapcsolatos eseményekről.</span><span class="sxs-lookup"><span data-stu-id="9735f-112">In the Notifications section, you can specify how you want the user to be notified about workflow-related events.</span></span>  
5. <span data-ttu-id="9735f-113">A Sortétel-munkafolyamat értesítési típusa mezőben válasszon ki egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9735f-113">In the Line-item workflow notification type field, select an option.</span></span>
    * <span data-ttu-id="9735f-114">Csoportosított – A sortételek értesítései egyetlen e-mailbe vannak csoportosítva.</span><span class="sxs-lookup"><span data-stu-id="9735f-114">Grouped – Notifications for line items are grouped into a single email message.</span></span>    <span data-ttu-id="9735f-115">Egyedi – Az egyes sortételekhez egy e-mailt küld.</span><span class="sxs-lookup"><span data-stu-id="9735f-115">Individual – An email message is sent for each line item.</span></span>  
    * <span data-ttu-id="9735f-116">Jelölje be az Értesítések küldése e-mailben jelölőnégyzetet, ha azt szeretné, hogy a felhasználó értesítések kapjon a kliensben.</span><span class="sxs-lookup"><span data-stu-id="9735f-116">If you want the user to receive notifications in the client, select the Send notifications in email check box.</span></span>  
6. <span data-ttu-id="9735f-117">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="9735f-117">Click Save.</span></span>
7. <span data-ttu-id="9735f-118">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="9735f-118">Close the page.</span></span>


