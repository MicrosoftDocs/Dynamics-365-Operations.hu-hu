---
title: "Költségszabályok meghatározása"
description: "Be lehet állítani költségszabályokat, amelyeket a munkatársaknak követniük kell költségjelentések, valamint utazásigénylések megadása és benyújtása során a Microsoft Dynamics 365 for Finance and Operations rendszerben."
author: saraschi2
manager: AnnBe
ms.date: 02/23/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysPolicyListPage, TrvPolicyRule
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 3b2a28fe6acf03e52c292048a797ce997f58bcce
ms.contentlocale: hu-hu
ms.lasthandoff: 03/26/2018

---

# <a name="expense-policies"></a><span data-ttu-id="e772d-103">Költségszabályok</span><span class="sxs-lookup"><span data-stu-id="e772d-103">Expense policies</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="e772d-104">Fel lehet állítani a dolgozók által követendő irányelveket (szabályokat) a költségjelentések és utazásigénylések benyújtására vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="e772d-104">You can define policies that your workers must follow when entering and submitting expense reports and travel requisitions.</span></span>         
<span data-ttu-id="e772d-105">A költségirányelvek bevezetése segítséget nyújthat a hatékony költségkezeléshez.</span><span class="sxs-lookup"><span data-stu-id="e772d-105">Implementing expense policies can help you manage expenses effectively.</span></span>         

<span data-ttu-id="e772d-106">Például felállíthat egy olyan irányelvet, hogy a New York-i szállodaköltség éjszakánként nem haladhatja meg a 250 dollárt.</span><span class="sxs-lookup"><span data-stu-id="e772d-106">For example, you can set a policy for hotel expenses in New York City, which states that the per night expense cannot exceed USD 250.</span></span>       
<span data-ttu-id="e772d-107">Ha a dolgozó benyújt egy költségjelentést vagy egy utazási igénylést, amelyben a szobaár meghaladja ezt az összeget, a rendszer értesíti a</span><span class="sxs-lookup"><span data-stu-id="e772d-107">If a worker submits an expense report or a travel requisition in which the room rate exceeds this amount, the system will notify the</span></span>        
<span data-ttu-id="e772d-108">dolgozót, hogy a házirend szerinti költségösszeg túl lett lépve.</span><span class="sxs-lookup"><span data-stu-id="e772d-108">worker that the policy amount for the expense has been exceeded.</span></span> <span data-ttu-id="e772d-109">Az irányelv definiálásakor beállíthatja az üzenetet, amelyet a dolgozó megkap</span><span class="sxs-lookup"><span data-stu-id="e772d-109">You can configure the message that the worker will receive when you</span></span>        
<span data-ttu-id="e772d-110">.</span><span class="sxs-lookup"><span data-stu-id="e772d-110">define the policy.</span></span>      
        
<span data-ttu-id="e772d-111">Háromféle irányelvet állíthat be:</span><span class="sxs-lookup"><span data-stu-id="e772d-111">You can define three types of policies:</span></span>         
        
- <span data-ttu-id="e772d-112">Figyelmeztetés – lehetővé teszi a dolgozónak, hogy a költségjelentést vagy utazási igénylést nyújtson be, de a program megjelöli a költséget a jóváhagyók számára és</span><span class="sxs-lookup"><span data-stu-id="e772d-112">Warning – Allows the worker to submit an expense report or travel requisition but the expense will be marked for all approvers and</span></span>        
<span data-ttu-id="e772d-113">későbbi jelentéstételre.</span><span class="sxs-lookup"><span data-stu-id="e772d-113">for later reporting.</span></span>        

- <span data-ttu-id="e772d-114">Hiba – a dolgozó a költségjelentés vagy utazásigénylés benyújtása előtt köteles úgy módosítani a költséget, hogy megfeleljen az irányelvnek.</span><span class="sxs-lookup"><span data-stu-id="e772d-114">Error – Requires the worker to revise the expense to comply with the policy before submitting the expense report or travel requisition.</span></span>       
 
 - <span data-ttu-id="e772d-115">Indoklás – a dolgozónak, illetve a vezetőnek a költségjelentés vagy utazásigénylés benyújtása előtt indoklást kell megadnia, hogy miért lépte át az irányelvben megadott összeget.</span><span class="sxs-lookup"><span data-stu-id="e772d-115">Justification – Requires the worker or a manager to enter a justification for exceeding the policy amount before submitting the expense report or travel requisition.</span></span>        
 
 <span data-ttu-id="e772d-116">Szintén felállítható egy időintervallum, amelyben a költségirányelvek érvényben vannak.</span><span class="sxs-lookup"><span data-stu-id="e772d-116">You can also set up a date range for which expense policies are in effect.</span></span> <span data-ttu-id="e772d-117">Például a repülőjegyek Dánia</span><span class="sxs-lookup"><span data-stu-id="e772d-117">For example, airline fares for flights between Denmark</span></span>      
 <span data-ttu-id="e772d-118">és New York között magasra szökhetnek a szabadságolások csúcs utazási időszaka alatt.</span><span class="sxs-lookup"><span data-stu-id="e772d-118">and New York City can be expensive during the peak holiday travel season.</span></span> <span data-ttu-id="e772d-119">Definiálni lehet egy repülési költségszabályt, amely</span><span class="sxs-lookup"><span data-stu-id="e772d-119">You can define a flight expense rule that restricts the</span></span>      
 <span data-ttu-id="e772d-120">5000 DKK-ra korlátozza a New York-i repülőutak költségét, és megadhatja, hogy ez a szabály március 15. és</span><span class="sxs-lookup"><span data-stu-id="e772d-120">cost of flights to New York City to a limit of DKK 5000, and you can specify that this rule be in effect between March 15 and</span></span>      
 <span data-ttu-id="e772d-121">szeptember 15. között legyen érvényben.</span><span class="sxs-lookup"><span data-stu-id="e772d-121">September 15.</span></span>

