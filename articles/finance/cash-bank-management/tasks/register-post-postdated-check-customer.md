---
title: Vevő részére kiállított, jövőben esedékes csekk regisztrálása és feladása
description: A vevőtől érkezett, jövőben esedékes csekkek részletes adatait rögzítheti.
author: kweekley
manager: AnnBe
ms.date: 10/26/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a7b7899e11849175976b4c7ee44be4355e733d1d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5225345"
---
# <a name="register-and-post-a-postdated-check-for-a-customer"></a><span data-ttu-id="6d7c8-103">Vevő részére kiállított, jövőben esedékes csekk regisztrálása és feladása</span><span class="sxs-lookup"><span data-stu-id="6d7c8-103">Register and post a postdated check for a customer</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6d7c8-104">A vevőtől érkezett, jövőben esedékes csekkek részletes adatait rögzítheti.</span><span class="sxs-lookup"><span data-stu-id="6d7c8-104">You can register details of a postdated check received from a customer.</span></span> <span data-ttu-id="6d7c8-105">A jövőben esedékes csekket feladhatja és pénzügyi tranzakciókat hozhat létre.</span><span class="sxs-lookup"><span data-stu-id="6d7c8-105">You can also post the postdated check and generate financial transactions.</span></span>   <span data-ttu-id="6d7c8-106">A vevőtől érkezett, jövőben esedékes csekkek nyilvántartásba vétele és feladása előtt hajtsa végre a következő feladatokat: \* a Készpénz- és bankkezelés lapon állítson be a jövőben esedékes csekkeket \* Állítsa be a fizetési módot a jövőben esedékes csekkekhez Ezen eljárás szerepköre: Pénztáros.</span><span class="sxs-lookup"><span data-stu-id="6d7c8-106">Complete the following tasks before you register and post a postdated check received from a customer:   \* Set up postdated check in the Cash and bank management page \* Set up a method of payment for postdated checks   The role for this procedure is Treasurer.</span></span> <span data-ttu-id="6d7c8-107">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="6d7c8-107">This procedure uses the USMF demo company.</span></span>

1. <span data-ttu-id="6d7c8-108">Ugorjon a Kinnlevőségek > Fizetési beállítás > Fizetési napló pontra.</span><span class="sxs-lookup"><span data-stu-id="6d7c8-108">Go to Accounts receivable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="6d7c8-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6d7c8-109">Click New.</span></span>
3. <span data-ttu-id="6d7c8-110">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="6d7c8-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="6d7c8-111">Kattintson a Sorok pontra.</span><span class="sxs-lookup"><span data-stu-id="6d7c8-111">Click Lines.</span></span>
5. <span data-ttu-id="6d7c8-112">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="6d7c8-112">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="6d7c8-113">A Számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="6d7c8-113">In the Account field, specify the desired values.</span></span>
7. <span data-ttu-id="6d7c8-114">A Hitelkeret mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="6d7c8-114">In the Credit field, enter a number.</span></span>
    * <span data-ttu-id="6d7c8-115">Adja meg a jövőben esedékes csekken látható összeget.</span><span class="sxs-lookup"><span data-stu-id="6d7c8-115">Enter the amount specified in the postdated check.</span></span>  
8. <span data-ttu-id="6d7c8-116">Kattintson a Fizetések fülre.</span><span class="sxs-lookup"><span data-stu-id="6d7c8-116">Click the Payment tab.</span></span>
9. <span data-ttu-id="6d7c8-117">Írjon be egy értéket a Fizetési mód mezőbe.</span><span class="sxs-lookup"><span data-stu-id="6d7c8-117">In the Method of payment field, type a value.</span></span>
    * <span data-ttu-id="6d7c8-118">Válassza ki a jövőben esedékes csekk fizetési módját.</span><span class="sxs-lookup"><span data-stu-id="6d7c8-118">Select the method of payment for the postdated check.</span></span>  
10. <span data-ttu-id="6d7c8-119">Kattintson a Jövőben esedékes csekkek fülre.</span><span class="sxs-lookup"><span data-stu-id="6d7c8-119">Click the Postdated checks tab.</span></span>
11. <span data-ttu-id="6d7c8-120">Az érvényesség mezőben adjon meg egy dátumot.</span><span class="sxs-lookup"><span data-stu-id="6d7c8-120">In the Maturity date field, enter a date.</span></span>
    * <span data-ttu-id="6d7c8-121">Adja meg a dátumot, amikor a jövőben esedékes csekk kifizetése esedékes.</span><span class="sxs-lookup"><span data-stu-id="6d7c8-121">Enter the date when the postdated check is due for payment.</span></span>  
12. <span data-ttu-id="6d7c8-122">A Kiadási bankfiók mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6d7c8-122">In the Issuing bank branch field, type a value.</span></span>
    * <span data-ttu-id="6d7c8-123">Adja meg a jövőben esedékes csekk banki adatait.</span><span class="sxs-lookup"><span data-stu-id="6d7c8-123">Enter the bank details of the postdated check.</span></span>  
13. <span data-ttu-id="6d7c8-124">A csekk száma mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6d7c8-124">In the check number field, type a value.</span></span>
14. <span data-ttu-id="6d7c8-125">A Kiadási bank neve mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6d7c8-125">In the Issuing bank name field, type a value.</span></span>
    * <span data-ttu-id="6d7c8-126">Adja meg a jövőben esedékes csekk banki adatait.</span><span class="sxs-lookup"><span data-stu-id="6d7c8-126">Enter the bank details of the postdated check.</span></span>  
15. <span data-ttu-id="6d7c8-127">Kattintson a Feladás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6d7c8-127">Click Post.</span></span>
16. <span data-ttu-id="6d7c8-128">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="6d7c8-128">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]