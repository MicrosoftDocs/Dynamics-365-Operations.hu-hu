--- 
title: "Vevő részére kiállított, jövőben esedékes csekk regisztrálása és feladása"
description: "A vevőtől érkezett, jövőben esedékes csekkek részletes adatait rögzítheti."
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
ms.openlocfilehash: 1610036815349f625a67d5dd67260114d42fff97
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---
# <a name="register-and-post-a-postdated-check-for-a-customer"></a><span data-ttu-id="b7990-103">Vevő részére kiállított, jövőben esedékes csekk regisztrálása és feladása</span><span class="sxs-lookup"><span data-stu-id="b7990-103">Register and post a postdated check for a customer</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b7990-104">A vevőtől érkezett, jövőben esedékes csekkek részletes adatait rögzítheti.</span><span class="sxs-lookup"><span data-stu-id="b7990-104">You can register details of a postdated cheque received from a customer.</span></span> <span data-ttu-id="b7990-105">A jövőben esedékes csekket feladhatja és pénzügyi tranzakciókat hozhat létre.</span><span class="sxs-lookup"><span data-stu-id="b7990-105">You can also post the postdated cheque and generate financial transactions.</span></span>   <span data-ttu-id="b7990-106">A vevőtől érkezett, jövőben esedékes csekkek nyilvántartásba vétele és feladása előtt hajtsa végre a következő feladatokat: • a Készpénz- és bankkezelés lapon állítson be a jövőben esedékes csekkeket • Állítsa be a fizetési módot a jövőben esedékes csekkekhez Ezen eljárás szerepköre: Pénztáros.</span><span class="sxs-lookup"><span data-stu-id="b7990-106">Complete the following tasks before you register and post a postdated cheque received from a customer:   • Set up postdated Cheques in the Cash and bank management page • Set up a method of payment for postdated Cheques   The role for this procedure is Treasurer.</span></span> <span data-ttu-id="b7990-107">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="b7990-107">This procedure uses the USMF demo company.</span></span>

1. <span data-ttu-id="b7990-108">Ugorjon a Kinnlevőségek > Fizetési beállítás > Fizetési napló pontra.</span><span class="sxs-lookup"><span data-stu-id="b7990-108">Go to Accounts receivable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="b7990-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b7990-109">Click New.</span></span>
3. <span data-ttu-id="b7990-110">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="b7990-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="b7990-111">Kattintson a Sorok pontra.</span><span class="sxs-lookup"><span data-stu-id="b7990-111">Click Lines.</span></span>
5. <span data-ttu-id="b7990-112">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="b7990-112">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="b7990-113">A Számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="b7990-113">In the Account field, specify the desired values.</span></span>
7. <span data-ttu-id="b7990-114">A Hitelkeret mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="b7990-114">In the Credit field, enter a number.</span></span>
    * <span data-ttu-id="b7990-115">Adja meg a jövőben esedékes csekken látható összeget.</span><span class="sxs-lookup"><span data-stu-id="b7990-115">Enter the amount specified in the postdated cheque.</span></span>  
8. <span data-ttu-id="b7990-116">Kattintson a Fizetések fülre.</span><span class="sxs-lookup"><span data-stu-id="b7990-116">Click the Payment tab.</span></span>
9. <span data-ttu-id="b7990-117">Írjon be egy értéket a Fizetési mód mezőbe.</span><span class="sxs-lookup"><span data-stu-id="b7990-117">In the Method of payment field, type a value.</span></span>
    * <span data-ttu-id="b7990-118">Válassza ki a jövőben esedékes csekk fizetési módját.</span><span class="sxs-lookup"><span data-stu-id="b7990-118">Select the method of payment for the postdated cheque</span></span>  
10. <span data-ttu-id="b7990-119">Kattintson a Jövőben esedékes csekkek fülre.</span><span class="sxs-lookup"><span data-stu-id="b7990-119">Click the Postdated checks tab.</span></span>
11. <span data-ttu-id="b7990-120">Az érvényesség mezőben adjon meg egy dátumot.</span><span class="sxs-lookup"><span data-stu-id="b7990-120">In the Maturity date field, enter a date.</span></span>
    * <span data-ttu-id="b7990-121">Adja meg a dátumot, amikor a jövőben esedékes csekk kifizetése esedékes.</span><span class="sxs-lookup"><span data-stu-id="b7990-121">Enter the date when the postdated cheque is due for payment.</span></span>  
12. <span data-ttu-id="b7990-122">A Kiadási bankfiók mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="b7990-122">In the Issuing bank branch field, type a value.</span></span>
    * <span data-ttu-id="b7990-123">Adja meg a jövőben esedékes csekk banki adatait.</span><span class="sxs-lookup"><span data-stu-id="b7990-123">Enter the bank details of the postdated cheque.</span></span>  
13. <span data-ttu-id="b7990-124">A Csekk száma mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="b7990-124">In the cheque number field, type a value.</span></span>
14. <span data-ttu-id="b7990-125">A Kiadási bank neve mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="b7990-125">In the Issuing bank name field, type a value.</span></span>
    * <span data-ttu-id="b7990-126">Adja meg a jövőben esedékes csekk banki adatait.</span><span class="sxs-lookup"><span data-stu-id="b7990-126">Enter the bank details of the postdated check.</span></span>  
15. <span data-ttu-id="b7990-127">Kattintson a Feladás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b7990-127">Click Post.</span></span>
16. <span data-ttu-id="b7990-128">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b7990-128">Close the page.</span></span>


