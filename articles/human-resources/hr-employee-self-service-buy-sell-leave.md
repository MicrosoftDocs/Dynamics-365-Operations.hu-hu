---
title: Szabadság vásárlása és eladása
description: A Dynamics 365 Human Resources alkalmazásban lehetséges benyújtani szabadáság vásárlására és eladására irányuló kérelmet a vállalatnál beállított szabadság vásárlására és eladására vonatkozó irányelvek alapján.
author: andreabichsel
ms.date: 08/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ESSLeaveBuyRequestEntry, EssWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6d32abacc1539cb930ad6f1ebcfe6fa9af4befcf
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271485"
---
# <a name="buy-and-sell-leave"></a><span data-ttu-id="988ac-103">Szabadság vásárlása és eladása</span><span class="sxs-lookup"><span data-stu-id="988ac-103">Buy and sell leave</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="988ac-104">A Dynamics 365 Human Resources alkalmazásban lehetséges benyújtani szabadáság vásárlására és eladására irányuló kérelmet a vállalatnál beállított szabadság vásárlására és eladására vonatkozó irányelvek alapján.</span><span class="sxs-lookup"><span data-stu-id="988ac-104">In Dynamics 365 Human Resources, you can submit requests to buy and sell leave based on the buy and sell leave policies set up by your company.</span></span>  

## <a name="request-to-buy-leave"></a><span data-ttu-id="988ac-105">Szabadságvásárlási kérelem</span><span class="sxs-lookup"><span data-stu-id="988ac-105">Request to buy leave</span></span>

1. <span data-ttu-id="988ac-106">Az **Alkalmazotti önkiszolgáló rendszer** munkaterületen válassza a **Szabadságvásárlási kérelem** lehetőséget a **Szabadságegyenlegek** csempén.</span><span class="sxs-lookup"><span data-stu-id="988ac-106">In the **Employee self service** workspace, select **Buy leave request** in the **Time Off Balances** tile.</span></span> 

2. <span data-ttu-id="988ac-107">Adjon meg egy **Szabadságtípust**, és adja meg az **Összeg** elemet a megvásárolni kívánt szabadság összegéhez.</span><span class="sxs-lookup"><span data-stu-id="988ac-107">Add a **Leave type** and enter an **Amount** for the amount of leave you'd like to buy.</span></span> 

3. <span data-ttu-id="988ac-108">Ha elkészült, válassza a **Küldés** elemet a kérés elküldéséhez.</span><span class="sxs-lookup"><span data-stu-id="988ac-108">Select **Submit** when you're ready to submit your request.</span></span> 

<span data-ttu-id="988ac-109">Az egyenlegei vagy automatikusan frissülnek, vagy egy jóváhagyási folyamaton mennek keresztül a frissítés előtt.</span><span class="sxs-lookup"><span data-stu-id="988ac-109">Your balances will either automatically update or go through an approval process before updating.</span></span> <span data-ttu-id="988ac-110">Ez attól függ, hogy hogyan lett konfigurálva a vásárlási irányelv.</span><span class="sxs-lookup"><span data-stu-id="988ac-110">This depends on how the buy policy has been configured.</span></span>

## <a name="request-to-sell-leave"></a><span data-ttu-id="988ac-111">Szabadságeladási kérelem</span><span class="sxs-lookup"><span data-stu-id="988ac-111">Request to sell leave</span></span>

1. <span data-ttu-id="988ac-112">Az **Alkalmazotti önkiszolgáló rendszer** munkaterületen válassza a **Szabadságeladási kérelem** lehetőséget a **Szabadságegyenlegek** csempén.</span><span class="sxs-lookup"><span data-stu-id="988ac-112">In the **Employee self service** workspace, select **Sell leave request** in the **Time Off Balances** tile.</span></span> 

2. <span data-ttu-id="988ac-113">Adjon meg egy **Szabadságtípust**, és adja meg az **Összeg** elemet az eladni kívánt szabadság összegéhez.</span><span class="sxs-lookup"><span data-stu-id="988ac-113">Add a **Leave type** and enter an **Amount** for the amount of leave you'd like to sell.</span></span> 

3. <span data-ttu-id="988ac-114">Ha elkészült, válassza a **Küldés** elemet a kérés elküldéséhez.</span><span class="sxs-lookup"><span data-stu-id="988ac-114">Select **Submit** when you're ready to submit your request.</span></span>

<span data-ttu-id="988ac-115">Az egyenlegei vagy automatikusan frissülnek, vagy egy jóváhagyási folyamaton mennek keresztül a frissítés előtt.</span><span class="sxs-lookup"><span data-stu-id="988ac-115">Your balances will either automatically update or go through an approval process before updating.</span></span> <span data-ttu-id="988ac-116">Ez attól függ, hogy hogyan lett konfigurálva a vásárlási irányelv.</span><span class="sxs-lookup"><span data-stu-id="988ac-116">This depends on how the buy policy has been configured.</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="988ac-117">Hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="988ac-117">Troubleshooting</span></span> 

<span data-ttu-id="988ac-118">Ha egy vásárlás vagy eladás szabadságra vonatkozó kérés munkafolyamata sikertelen, az **EssLeaveBuySellRequestApprover** jogosultsággal rendelkező felhasználók minden szabadság vásárlási és eladási kérés üzenetnaplóját áttekinthatják.</span><span class="sxs-lookup"><span data-stu-id="988ac-118">If a buy or sell leave request workflow fails, users with the **EssLeaveBuySellRequestApprover** privilege can review the message log for all leave buy and sell requests.</span></span> <span data-ttu-id="988ac-119">Ehhez lépjen a **Szabadság és távollét > Link > Szabadság vásárlási és eladási kérések > Üzenetnaplóban** (a bal felső oldalon).</span><span class="sxs-lookup"><span data-stu-id="988ac-119">To do this, go to **Leave and absence > Link > Buy and sell leave requests > Message log** (on the upper left).</span></span> <span data-ttu-id="988ac-120">Az **Üzenetnapló** bemutatja a felhasználókat a tranzakciók feldolgozásának és a kapcsolódó munkafolyamat-előzményeknek a megjelenítése.</span><span class="sxs-lookup"><span data-stu-id="988ac-120">The **Message log** shows users how the transactions were processed and the associated workflow history.</span></span>


## <a name="see-also"></a><span data-ttu-id="988ac-121">Lásd még</span><span class="sxs-lookup"><span data-stu-id="988ac-121">See also</span></span>

[<span data-ttu-id="988ac-122">Szabadság és távollét áttekintése</span><span class="sxs-lookup"><span data-stu-id="988ac-122">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)</br>
[<span data-ttu-id="988ac-123">Szabadság vásárlásával és eladásával kapcsolatos irányelv kezelése</span><span class="sxs-lookup"><span data-stu-id="988ac-123">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
