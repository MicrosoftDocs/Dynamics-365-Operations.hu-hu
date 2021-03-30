---
title: Webes tevékenység eseménygyűjteményről való leiratkozás
description: Ez a témakör azt mutatja be, hogyan engedélyezheti a webhely látogatói számára, hogy leiratkozzanak a Microsoft Dynamics 365 Commerce webes tevékenység eseménygyűjteményről.
author: aamiral
manager: AnnBe
ms.date: 05/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 244d612fa01529df4fff250df50a06526632fcf1
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5210923"
---
# <a name="opt-out-of-web-activity-event-collection"></a><span data-ttu-id="fd7b4-103">Webes esemény jellegű tevékenység gyűjtésének kikapcsolása</span><span class="sxs-lookup"><span data-stu-id="fd7b4-103">Opt out of web activity event collection</span></span>
[!include [banner](includes/banner.md)]

<span data-ttu-id="fd7b4-104">Ez a témakör azt mutatja be, hogyan teheti lehetővé az ügyfeleinek a webes tevékenység eseménygyűjteményről való leiratkozást a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="fd7b4-104">This topic explains how you can let customers opt out of web activity event collection in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="fd7b4-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="fd7b4-105">Overview</span></span>

<span data-ttu-id="fd7b4-106">A Dynamics 365 Commerce segítségével a webhely rendszergazdái elemezhetik az e-kereskedelmi webhelyeik felhasználóinak webes tevékenységét.</span><span class="sxs-lookup"><span data-stu-id="fd7b4-106">Dynamics 365 Commerce lets site administrators analyze the web activity of users of their e-commerce sites.</span></span> <span data-ttu-id="fd7b4-107">Ily módon jobban megérthetik a webhelyeik használatát, és optimalizálni tudják a webhelyeket a továbbfejlesztett felhasználói élmény biztosítása és az üzleti célkitűzések kielégítése érdekében.</span><span class="sxs-lookup"><span data-stu-id="fd7b4-107">In that way, they can better understand how their sites are used, and they can optimize the sites to provide an improved user experience and meet business objectives.</span></span>


## <a name="ways-for-administrators-to-implement-an-opt-out-experience"></a><span data-ttu-id="fd7b4-108">A leiratkozási élmény megvalósítási módjai a rendszergazdák számára</span><span class="sxs-lookup"><span data-stu-id="fd7b4-108">Ways for administrators to implement an opt-out experience</span></span>

<span data-ttu-id="fd7b4-109">A leiratkozási élményt a rendszergazdák háromféle módon tudják megvalósítani.</span><span class="sxs-lookup"><span data-stu-id="fd7b4-109">Administrators have three ways to implement an opt-out experience.</span></span>

### <a name="opt-out-on-behalf-of-users"></a><span data-ttu-id="fd7b4-110">Leiratkozás a felhasználók nevében</span><span class="sxs-lookup"><span data-stu-id="fd7b4-110">Opt out on behalf of users</span></span>

<span data-ttu-id="fd7b4-111">A Commerce-központ (HQ) Fiókkezelés részében a rendszergazdák elvégezhetik a leiratkozást a felhasználók nevében.</span><span class="sxs-lookup"><span data-stu-id="fd7b4-111">In Account management in Commerce headquarters (HQ), administrators can opt out on behalf of users.</span></span>

1. <span data-ttu-id="fd7b4-112">A HQ-ügyfél részben, a **Minden ügyfél** oldalon keressen és válasszon ki egy vevőt.</span><span class="sxs-lookup"><span data-stu-id="fd7b4-112">In the HQ client, on the **All customers** page, search for and select a customer.</span></span>
1. <span data-ttu-id="fd7b4-113">A vevői részletek oldalon, a **Kiskereskedelem** gyorslap **Adatvédelem** részében adja meg a **Ne kövesse a webes tevékenységet** beállításnak az **Igen** értéket.</span><span class="sxs-lookup"><span data-stu-id="fd7b4-113">On the customer details page, on the **Retail** FastTab, in the **Privacy** section, set the **Do not track web activity** option to **Yes**.</span></span>

    ![Adatvédelmi beállítások](media/Disablepersonalizationpart2.png)

1. <span data-ttu-id="fd7b4-115">Válassza a **Mentés** gombot, majd zárja be az oldalt.</span><span class="sxs-lookup"><span data-stu-id="fd7b4-115">Select **Save**, and then close the page.</span></span>

### <a name="module-based-opt-out-experience"></a><span data-ttu-id="fd7b4-116">Modulalapú leiratkozási élmény</span><span class="sxs-lookup"><span data-stu-id="fd7b4-116">Module-based opt-out experience</span></span>

<span data-ttu-id="fd7b4-117">A rendszergazdák megengedik a hitelesített felhasználók számára, hogy saját maguk végezzék el a webes tevékenységek eseménygyűjtéséről való leiratkozást.</span><span class="sxs-lookup"><span data-stu-id="fd7b4-117">Administrators can let authenticated users opt out of web activity event collection by themselves.</span></span> <span data-ttu-id="fd7b4-118">Ennek a leiratkozási élménynek a biztosításához adja hozzá a leiratkozási modult a vásárlói fiók profiloldalaihoz.</span><span class="sxs-lookup"><span data-stu-id="fd7b4-118">To provide this opt-out experience, add the user opt-out module to customer account profile pages.</span></span>

### <a name="custom-extensions"></a><span data-ttu-id="fd7b4-119">Egyéni bővítmények</span><span class="sxs-lookup"><span data-stu-id="fd7b4-119">Custom extensions</span></span>

<span data-ttu-id="fd7b4-120">A rendszergazdák saját bővítményeiket hozhatnak létre a felhasználók leiratkozási élményének kezeléséhez.</span><span class="sxs-lookup"><span data-stu-id="fd7b4-120">Administrators can create their own extensions to manage the opt-out experience for users.</span></span> <span data-ttu-id="fd7b4-121">További információk: [Retail Server API-k hívása](e-commerce-extensibility/call-retail-server-apis.md) és [Online csatorna bővíthetősége](e-commerce-extensibility/overview.md).</span><span class="sxs-lookup"><span data-stu-id="fd7b4-121">For more information, see [Call Retail Server APIs](e-commerce-extensibility/call-retail-server-apis.md) and [Online channel extensibility](e-commerce-extensibility/overview.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]