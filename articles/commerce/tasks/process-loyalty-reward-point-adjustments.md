---
title: " Hűségpont-helyesbítések feldolgozása"
description: Ez az eljárás bemutatja, hogyan tekintheti meg a hűségkártyával kapcsolatos adatokat és hogyan módosíthatja a hűségpontok számát.
author: scott-tucker
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailLoyaltyCards, RetailLoyaltyCardRewardPointTrans, RetailLoyaltyCardRewardPointAdjustment, RetailAffiliationLookup
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fca59651065d20e79a47b49a4eb3b4def7cac674
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5232810"
---
# <a name="process-loyalty-reward-point-adjustments"></a><span data-ttu-id="deba2-103"> Hűségpont-helyesbítések feldolgozása</span><span class="sxs-lookup"><span data-stu-id="deba2-103">Process loyalty reward point adjustments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="deba2-104">Ez az eljárás bemutatja, hogyan tekintheti meg a hűségkártyával kapcsolatos adatokat és hogyan módosíthatja a hűségpontok számát.</span><span class="sxs-lookup"><span data-stu-id="deba2-104">This procedure demonstrates how to look up loyalty card information and adjust loyalty reward points.</span></span> <span data-ttu-id="deba2-105">A feladat létrehozásához az USRT bemutató vállalatot használtuk példaként.</span><span class="sxs-lookup"><span data-stu-id="deba2-105">The demo data company used to create this task is USRT.</span></span> <span data-ttu-id="deba2-106">Ez a feladat a Commerce műveletek vezetője vagy a Vevőszolgálati vezető szerepkörnek szól.</span><span class="sxs-lookup"><span data-stu-id="deba2-106">This task is intended for the Commerce operations manager role or a Customer service manager role.</span></span>

1. <span data-ttu-id="deba2-107">Ugrás a Hűségkártyák lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="deba2-107">Go to Loyalty cards.</span></span>
2. <span data-ttu-id="deba2-108">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="deba2-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="deba2-109">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="deba2-109">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="deba2-110">Kattintson a Kártyatranzakciók lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="deba2-110">Click Card transactions.</span></span>
    * <span data-ttu-id="deba2-111">Ezen a lapon megtekintheti a kiválasztott hűségkártyához tartozó összes hűség tranzakciót.</span><span class="sxs-lookup"><span data-stu-id="deba2-111">On this page you can view all loyalty transactions for the selected loyalty card.</span></span>  
5. <span data-ttu-id="deba2-112">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="deba2-112">Close the page.</span></span>
6. <span data-ttu-id="deba2-113">Kattintson a Kártyahelyesbítések lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="deba2-113">Click Card adjustments.</span></span>
7. <span data-ttu-id="deba2-114">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="deba2-114">Click New.</span></span>
8. <span data-ttu-id="deba2-115">A Hűségpontok mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="deba2-115">In the Reward point field, enter or select a value.</span></span>
9. <span data-ttu-id="deba2-116">Írjon be egy számot az Összeg vagy mennyiség mezőbe.</span><span class="sxs-lookup"><span data-stu-id="deba2-116">In the Amount or quantity field, enter a number.</span></span>
    * <span data-ttu-id="deba2-117">Pozitív vagy negatív összegek használatával hozzáadhat vagy levonhat pontokat a hűségkártyáról.</span><span class="sxs-lookup"><span data-stu-id="deba2-117">You can add or remove points from the loyalty card by using positive or negative amounts.</span></span>  
10. <span data-ttu-id="deba2-118">A Hűségprogram mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="deba2-118">In the Loyalty program field, enter or select a value.</span></span>
11. <span data-ttu-id="deba2-119">Érték beírása a Megjegyzés mezőbe.</span><span class="sxs-lookup"><span data-stu-id="deba2-119">In the Comment field, type a value.</span></span>
12. <span data-ttu-id="deba2-120">Kattintson a Helyesbítés feladása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="deba2-120">Click Post adjustment.</span></span>
13. <span data-ttu-id="deba2-121">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="deba2-121">Click Yes.</span></span>
14. <span data-ttu-id="deba2-122">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="deba2-122">Close the page.</span></span>
    * <span data-ttu-id="deba2-123">Általában ezen a ponton frissítenie kell a lapot, hogy megtekinthesse a jutalompontokkal kapcsolatos módosítások eredményét a Jutalompont összegző lapon. Azonban ha ezt egy feladati útmutatóként futtatja, ne frissítse, mert akkor a feladati útmutató meg fog állni.</span><span class="sxs-lookup"><span data-stu-id="deba2-123">Normally at this point you'd refresh the page to see the result of the reward points adjustment in the Reward point summary tab. But if you are running this as a task guide, don't refresh now because if you do, the task guide will stop.</span></span>  
15. <span data-ttu-id="deba2-124">Kattintson a Kártyatranzakciók lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="deba2-124">Click Card transactions.</span></span>
16. <span data-ttu-id="deba2-125">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="deba2-125">Close the page.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]