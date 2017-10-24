---
title: "Költségszabályok meghatározása"
description: "Be lehet állítani költségszabályokat, amelyeket a munkatársaknak követniük kell költségjelentések, valamint utazásigénylések megadása és benyújtása során a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition rendszerben."
author: saraschi2
manager: AnnBe
ms.date: 09/19/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.search.region: Global
ms.author: saraschi2
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 940d6f8c3d878c2c12806ad04a092856df2acb33
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="expense-policies"></a><span data-ttu-id="66554-103">Költségszabályok</span><span class="sxs-lookup"><span data-stu-id="66554-103">Expense policies</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="66554-104">Fel lehet állítani a dolgozók által követendő irányelveket (szabályokat) a költségjelentések és utazásigénylések benyújtására vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="66554-104">You can define policies that your workers must follow when entering and submitting expense reports and travel requisitions.</span></span> <span data-ttu-id="66554-105">A költségirányelvek bevezetése segítséget nyújthat a hatékony költségkezeléshez.</span><span class="sxs-lookup"><span data-stu-id="66554-105">Implementing expense policies can help you manage expenses effectively.</span></span> 

<span data-ttu-id="66554-106">Például felállíthat egy olyan irányelvet, hogy a New York-i szállodaköltség éjszakánként nem haladhatja meg a 250 dollárt.</span><span class="sxs-lookup"><span data-stu-id="66554-106">For example, you can set a policy for hotel expenses in New York City, which states that the per night expense cannot exceed USD 250.</span></span> <span data-ttu-id="66554-107">Ha egy dolgozó olyan költségjelentést vagy utazásigénylést nyújt be, amelyben a szobaár meghaladja ezt a szintet, a rendszer értesíti a dolgozót, hogy meghaladta az irányelvben meghatározott költségkeretet.</span><span class="sxs-lookup"><span data-stu-id="66554-107">If a worker submits an expense report or a travel requisition in which the room rate exceeds this amount, the system will notify the worker that the policy amount for the expense has been exceeded.</span></span> <span data-ttu-id="66554-108">Az irányelv definiálásakor beállíthatja az üzenetet, amelyet a dolgozó megkap.</span><span class="sxs-lookup"><span data-stu-id="66554-108">You can configure the message that the worker will receive when you define the policy.</span></span> 

<span data-ttu-id="66554-109">Háromféle irányelvet állíthat be:</span><span class="sxs-lookup"><span data-stu-id="66554-109">You can define three types of policies:</span></span> 

 - <span data-ttu-id="66554-110">Figyelmeztetés – lehetővé teszi a dolgozónak, hogy a költségjelentést vagy utazási igénylést nyújtson be, de a program megjelöli a költséget a jóváhagyók számára és</span><span class="sxs-lookup"><span data-stu-id="66554-110">Warning – Allows the worker to submit an expense report or travel requisition but the expense will be marked for all approvers and</span></span>  
 <span data-ttu-id="66554-111">későbbi jelentéstételre.</span><span class="sxs-lookup"><span data-stu-id="66554-111">for later reporting.</span></span> 
 - <span data-ttu-id="66554-112">Hiba – a dolgozó a költségjelentés vagy utazásigénylés benyújtása előtt köteles úgy módosítani a költséget, hogy megfeleljen az irányelvnek.</span><span class="sxs-lookup"><span data-stu-id="66554-112">Error – Requires the worker to revise the expense to comply with the policy before submitting the expense report or travel requisition.</span></span> 
 - <span data-ttu-id="66554-113">Indoklás – a dolgozónak, illetve a vezetőnek a költségjelentés vagy utazásigénylés benyújtása előtt indoklást kell megadnia, hogy miért lépte át az irányelvben megadott összeget.</span><span class="sxs-lookup"><span data-stu-id="66554-113">Justification – Requires the worker or a manager to enter a justification for exceeding the policy amount before submitting the expense report or travel requisition.</span></span> 

<span data-ttu-id="66554-114">Szintén felállítható egy időintervallum, amelyben a költségirányelvek érvényben vannak.</span><span class="sxs-lookup"><span data-stu-id="66554-114">You can also set up a date range for which expense policies are in effect.</span></span> <span data-ttu-id="66554-115">Például a szabadságolások utazási csúcsszezonjában a Magyarország és New York közötti légi közlekedés költsége magasra szökik.</span><span class="sxs-lookup"><span data-stu-id="66554-115">For example, airline fares for flights between Denmark and New York City can be expensive during the peak holiday travel season.</span></span> <span data-ttu-id="66554-116">Meg lehet adni olyan repülési-költség szabályt, amely 5000 dán koronára korlátozza a New York-i repülőutak költségét, és beállítható, hogy ez a szabály március 15-től szeptember 15-ig legyen érvényben.</span><span class="sxs-lookup"><span data-stu-id="66554-116">You can define a flight expense rule that restricts the cost of flights to New York City to a limit of DKK 5000, and you can specify that this rule be in effect between March 15 and September 15.</span></span> 
