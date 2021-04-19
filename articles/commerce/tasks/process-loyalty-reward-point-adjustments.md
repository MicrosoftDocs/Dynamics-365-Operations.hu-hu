---
title: " Hűségpont-helyesbítések feldolgozása"
description: Ez az eljárás bemutatja, hogyan tekintheti meg a hűségkártyával kapcsolatos adatokat és hogyan módosíthatja a hűségpontok számát.
author: scott-tucker
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailLoyaltyCards, RetailLoyaltyCardRewardPointTrans, RetailLoyaltyCardRewardPointAdjustment, RetailAffiliationLookup
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7eae943985cc2bd706c0c3c4ec7b0470e3a54bff
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5802623"
---
# <a name="process-loyalty-reward-point-adjustments"></a><span data-ttu-id="4707f-103"> Hűségpont-helyesbítések feldolgozása</span><span class="sxs-lookup"><span data-stu-id="4707f-103">Process loyalty reward point adjustments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4707f-104">Ez az eljárás bemutatja, hogyan tekintheti meg a hűségkártyával kapcsolatos adatokat és hogyan módosíthatja a hűségpontok számát.</span><span class="sxs-lookup"><span data-stu-id="4707f-104">This procedure demonstrates how to look up loyalty card information and adjust loyalty reward points.</span></span> <span data-ttu-id="4707f-105">A feladat létrehozásához az USRT bemutató vállalatot használtuk példaként.</span><span class="sxs-lookup"><span data-stu-id="4707f-105">The demo data company used to create this task is USRT.</span></span> <span data-ttu-id="4707f-106">Ez a feladat a Commerce műveletek vezetője vagy a Vevőszolgálati vezető szerepkörnek szól.</span><span class="sxs-lookup"><span data-stu-id="4707f-106">This task is intended for the Commerce operations manager role or a Customer service manager role.</span></span>

1. <span data-ttu-id="4707f-107">Ugrás a Hűségkártyák lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4707f-107">Go to Loyalty cards.</span></span>
2. <span data-ttu-id="4707f-108">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="4707f-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="4707f-109">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="4707f-109">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="4707f-110">Kattintson a Kártyatranzakciók lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4707f-110">Click Card transactions.</span></span>
    * <span data-ttu-id="4707f-111">Ezen a lapon megtekintheti a kiválasztott hűségkártyához tartozó összes hűség tranzakciót.</span><span class="sxs-lookup"><span data-stu-id="4707f-111">On this page you can view all loyalty transactions for the selected loyalty card.</span></span>  
5. <span data-ttu-id="4707f-112">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="4707f-112">Close the page.</span></span>
6. <span data-ttu-id="4707f-113">Kattintson a Kártyahelyesbítések lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4707f-113">Click Card adjustments.</span></span>
7. <span data-ttu-id="4707f-114">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4707f-114">Click New.</span></span>
8. <span data-ttu-id="4707f-115">A Hűségpontok mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="4707f-115">In the Reward point field, enter or select a value.</span></span>
9. <span data-ttu-id="4707f-116">Írjon be egy számot az Összeg vagy mennyiség mezőbe.</span><span class="sxs-lookup"><span data-stu-id="4707f-116">In the Amount or quantity field, enter a number.</span></span>
    * <span data-ttu-id="4707f-117">Pozitív vagy negatív összegek használatával hozzáadhat vagy levonhat pontokat a hűségkártyáról.</span><span class="sxs-lookup"><span data-stu-id="4707f-117">You can add or remove points from the loyalty card by using positive or negative amounts.</span></span>  
10. <span data-ttu-id="4707f-118">A Hűségprogram mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="4707f-118">In the Loyalty program field, enter or select a value.</span></span>
11. <span data-ttu-id="4707f-119">Érték beírása a Megjegyzés mezőbe.</span><span class="sxs-lookup"><span data-stu-id="4707f-119">In the Comment field, type a value.</span></span>
12. <span data-ttu-id="4707f-120">Kattintson a Helyesbítés feladása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4707f-120">Click Post adjustment.</span></span>
13. <span data-ttu-id="4707f-121">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="4707f-121">Click Yes.</span></span>
14. <span data-ttu-id="4707f-122">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="4707f-122">Close the page.</span></span>
    * <span data-ttu-id="4707f-123">Általában ezen a ponton frissítenie kell a lapot, hogy megtekinthesse a jutalompontokkal kapcsolatos módosítások eredményét a Jutalompont összegző lapon. Azonban ha ezt egy feladati útmutatóként futtatja, ne frissítse, mert akkor a feladati útmutató meg fog állni.</span><span class="sxs-lookup"><span data-stu-id="4707f-123">Normally at this point you'd refresh the page to see the result of the reward points adjustment in the Reward point summary tab. But if you are running this as a task guide, don't refresh now because if you do, the task guide will stop.</span></span>  
15. <span data-ttu-id="4707f-124">Kattintson a Kártyatranzakciók lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4707f-124">Click Card transactions.</span></span>
16. <span data-ttu-id="4707f-125">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="4707f-125">Close the page.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]