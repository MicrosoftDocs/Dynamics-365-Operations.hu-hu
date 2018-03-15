--- 
title: " Hűségpontok definiálása"
description: "Ez az eljárás hűségpontok definiálását mutatja be."
author: scott-tucker
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 26b5615df427fb01cc4a1764507fbaa11bf0d7a0
ms.contentlocale: hu-hu
ms.lasthandoff: 02/07/2018

---
# <a name="define-loyalty-reward-points"></a><span data-ttu-id="383a1-103"> Hűségpontok definiálása</span><span class="sxs-lookup"><span data-stu-id="383a1-103">Define loyalty reward points</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="383a1-104">Ez az eljárás hűségpontok definiálását mutatja be.</span><span class="sxs-lookup"><span data-stu-id="383a1-104">This procedure walks through defining loyalty reward points.</span></span> <span data-ttu-id="383a1-105">Hűségprogram beállítása előtt szükséges a hűségpontok beállítása.</span><span class="sxs-lookup"><span data-stu-id="383a1-105">You should set up loyalty reward points before you set up a loyalty program.</span></span> <span data-ttu-id="383a1-106">Ez az eljárás az USRT bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="383a1-106">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="383a1-107">Nyissa meg a következőt: Kiskereskedelem és kereskedelem > Vevők > Hűség > Hűségpontok.</span><span class="sxs-lookup"><span data-stu-id="383a1-107">Go to Retail and commerce > Customers > Loyalty > Loyalty reward points.</span></span>
2. <span data-ttu-id="383a1-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="383a1-108">Click New.</span></span>
3. <span data-ttu-id="383a1-109">Írjon be egy értéket a Hűségpont azonosítója mezőbe.</span><span class="sxs-lookup"><span data-stu-id="383a1-109">In the Reward point ID field, type a value.</span></span>
4. <span data-ttu-id="383a1-110">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="383a1-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="383a1-111">A Hűségpont típusa mezőben válasszon ki egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="383a1-111">In the Reward point type field, select an option.</span></span>
    * <span data-ttu-id="383a1-112">Válassza ki a Mennyiség lehetőséget, ha a legközelebb egész számra kívánja kerekíteni a hűségpontokat.</span><span class="sxs-lookup"><span data-stu-id="383a1-112">Select Quantity if you want the reward points to be rounded to the nearest integer.</span></span> <span data-ttu-id="383a1-113">Válassza ki az Összeg lehetőséget, ha a pénzkerekítés szabályai szerint kívánja kerekíteni a hűségpontokat.</span><span class="sxs-lookup"><span data-stu-id="383a1-113">Select Amount if you want the reward points to be rounded according to currency rounding rules.</span></span> <span data-ttu-id="383a1-114">Ha a Mennyiség lehetőséget választja, hagyja ki az eljárás következő lépését.</span><span class="sxs-lookup"><span data-stu-id="383a1-114">If you select Quantity, skip the next step of this procedure..</span></span>  
6. <span data-ttu-id="383a1-115">Érték beírása a Pénznem mezőbe.</span><span class="sxs-lookup"><span data-stu-id="383a1-115">In the Currency field, type a value.</span></span>
    * <span data-ttu-id="383a1-116">Az Összeg típusú hűségpontok esetében minden pont a kiválasztott pénznemben kerül elszámolásra.</span><span class="sxs-lookup"><span data-stu-id="383a1-116">For Amount type reward points, all points issued will have the selected currency.</span></span> <span data-ttu-id="383a1-117">A Mennyiség típusú hűségpontok esetében ez a mező nem érvényes, ugorja át ezt a lépést.</span><span class="sxs-lookup"><span data-stu-id="383a1-117">For Quantity type reward points, this field doesn't apply—skip this step.</span></span>  
7. <span data-ttu-id="383a1-118">Jelölje be a Beváltható jelölőnégyzetet, vagy törölje a jelölést.</span><span class="sxs-lookup"><span data-stu-id="383a1-118">Check or uncheck the Redeemable checkbox.</span></span>
8. <span data-ttu-id="383a1-119">Adjon meg egy számot a Beváltási rangsor mezőben.</span><span class="sxs-lookup"><span data-stu-id="383a1-119">In the Redeem ranking field, enter a number.</span></span>
    * <span data-ttu-id="383a1-120">Beváltási rangsort akkor használ a rendszer, ha két vagy több beváltható hűségponttal lehet fizetni a termékekért.</span><span class="sxs-lookup"><span data-stu-id="383a1-120">Redeem ranking is used when two or more redeemable reward points can be used to pay for products.</span></span> <span data-ttu-id="383a1-121">Ha a két hűségpont beváltási rangsorban elfoglalt helye megegyezik, akkor a kevesebb pontszámot igénylő kerül felhasználásra.</span><span class="sxs-lookup"><span data-stu-id="383a1-121">If the two reward points have the same redeem ranking, then the one that needs to lower number of points will be used.</span></span>  
9. <span data-ttu-id="383a1-122">Adjon meg egy számot a Lejárati idő értéke mezőben.</span><span class="sxs-lookup"><span data-stu-id="383a1-122">In the Expiration time value field, enter a number.</span></span>
    * <span data-ttu-id="383a1-123">A hűségpontok a kiadásukkor meghatározott napok, hónapok vagy évek elteltével lejárnak.</span><span class="sxs-lookup"><span data-stu-id="383a1-123">The reward points will expire the specified number of days, months, or years after when the points are issued.</span></span> <span data-ttu-id="383a1-124">A „0” érték azt jelenti, hogy a hűségpontok nem járnak le.</span><span class="sxs-lookup"><span data-stu-id="383a1-124">A value of ‘0’ means the loyalty reward points will never expire.</span></span>  
10. <span data-ttu-id="383a1-125">Válasszon ki egy lehetőséget a Lejárati idő egysége mezőben.</span><span class="sxs-lookup"><span data-stu-id="383a1-125">In the Expiration time unit field, select an option.</span></span>
11. <span data-ttu-id="383a1-126">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="383a1-126">Click Save.</span></span>


