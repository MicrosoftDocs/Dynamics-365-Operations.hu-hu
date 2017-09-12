--- 
title: "Vevő által kiállított, jövőben esedékes csekk kiegyenlítése"
description: "A jövőben esedékes csekkeket akkor egyenlítheti ki, miután a bank elszámolta azokat."
author: kweekley
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 9cb6064a83e02ddf1fea2de7928965773d08bbc9
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---
# <a name="settle-a-postdated-check-from-a-customer"></a><span data-ttu-id="e553d-103">Vevő által kiállított, jövőben esedékes csekk kiegyenlítése</span><span class="sxs-lookup"><span data-stu-id="e553d-103">Settle a postdated check from a customer</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e553d-104">A jövőben esedékes csekkeket akkor egyenlítheti ki, miután a bank elszámolta azokat.</span><span class="sxs-lookup"><span data-stu-id="e553d-104">You can settle a postdated check after the check has been cleared by the bank.</span></span> <span data-ttu-id="e553d-105">A pénzügyi tranzakció a jövőben esedékes csekkhez tartozó áthidaló számlát is elszámolja.</span><span class="sxs-lookup"><span data-stu-id="e553d-105">This financial transaction also clears the bridge account transaction for the postdated check.</span></span> 

<span data-ttu-id="e553d-106">Mielőtt hozzálátna, a következő eljárásoknak készen kell lenniük.</span><span class="sxs-lookup"><span data-stu-id="e553d-106">The following tasks must be complete before you start this one.</span></span>

1) <span data-ttu-id="e553d-107">Jövőben esedékes csekkek beállítása</span><span class="sxs-lookup"><span data-stu-id="e553d-107">Set up postdated checks</span></span>

2) <span data-ttu-id="e553d-108">Vevő részére kiállított, jövőben esedékes csekk regisztrálása és feladása</span><span class="sxs-lookup"><span data-stu-id="e553d-108">Register and post a postdated check for a customer</span></span> 



<span data-ttu-id="e553d-109">Ezen feladati útmutatóhoz szükséges szerepkör: Pénztáros.</span><span class="sxs-lookup"><span data-stu-id="e553d-109">The role of this task guides is Treasurer.</span></span>



<span data-ttu-id="e553d-110">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="e553d-110">This procedure uses the USMF demo company.</span></span>

1. <span data-ttu-id="e553d-111">Ugrojon a Hitel és beszedés > Lekérdezések és jelentések > Kifizetések > Vevői jövőben esedékes csekkek pontra.</span><span class="sxs-lookup"><span data-stu-id="e553d-111">Go to Credit and collections > Inquiries and reports > Payments > Customer postdated checks.</span></span>
2. <span data-ttu-id="e553d-112">Kattintson a Kiegyenlítés elemre.</span><span class="sxs-lookup"><span data-stu-id="e553d-112">Click Settle.</span></span>
3. <span data-ttu-id="e553d-113">Kattintson az Elszámolási tételek kiegyenlítése elemre.</span><span class="sxs-lookup"><span data-stu-id="e553d-113">Click Settle clearing entries.</span></span>
    * <span data-ttu-id="e553d-114">Rendezze a csekktranzakció vevői számláját.</span><span class="sxs-lookup"><span data-stu-id="e553d-114">Settle the customer account for the check transaction.</span></span>  
4. <span data-ttu-id="e553d-115">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="e553d-115">Close the page.</span></span>
5. <span data-ttu-id="e553d-116">Ugorjon a Főkönyv > Naplóbejegyzések > Általános naplók pontra.</span><span class="sxs-lookup"><span data-stu-id="e553d-116">Go to General ledger > Journal entries > General journals.</span></span>
6. <span data-ttu-id="e553d-117">Válasszon ki egy lehetőséget a Megjelenítés mezőben.</span><span class="sxs-lookup"><span data-stu-id="e553d-117">In the Show field, select an option.</span></span>
7. <span data-ttu-id="e553d-118">Jelölje be vagy törölje a jelölést a Megjelenítés csak a felhasználó által létrehozott jelölőnégyzetéből.</span><span class="sxs-lookup"><span data-stu-id="e553d-118">Select or clear the Show user-created only check box.</span></span>
8. <span data-ttu-id="e553d-119">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="e553d-119">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="e553d-120">Kattintson a Sorok pontra.</span><span class="sxs-lookup"><span data-stu-id="e553d-120">Click Lines.</span></span>
10. <span data-ttu-id="e553d-121">Kattintson a Bizonylat elemre.</span><span class="sxs-lookup"><span data-stu-id="e553d-121">Click Voucher.</span></span>
11. <span data-ttu-id="e553d-122">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="e553d-122">Close the page.</span></span>


