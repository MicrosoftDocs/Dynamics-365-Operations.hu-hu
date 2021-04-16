---
title: Banki hitelmegállapodás létrehozása a garancialevélhez
description: A feladat a garancialevél feldolgozásához banki hitelmegállapodást hoz létre.
author: panolte
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e01012df3a5d4b11f332048947ec83962c8b2efd
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5834812"
---
# <a name="create-a-bank-facility-agreement-for-the-letter-of-guarantee"></a><span data-ttu-id="30409-103">Banki hitelmegállapodás létrehozása a garancialevélhez</span><span class="sxs-lookup"><span data-stu-id="30409-103">Create a bank facility agreement for the letter of guarantee</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="30409-104">A feladat a garancialevél feldolgozásához banki hitelmegállapodást hoz létre.</span><span class="sxs-lookup"><span data-stu-id="30409-104">This task creates a bank facility agreement to process a letter of guarantee.</span></span> <span data-ttu-id="30409-105">Ez a feladat az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="30409-105">This task uses the USMF demo company.</span></span> 


## <a name="create-bank-facility-agreement"></a><span data-ttu-id="30409-106">Banki hitelmegállapodás létrehozása</span><span class="sxs-lookup"><span data-stu-id="30409-106">Create Bank facility agreement</span></span>
1. <span data-ttu-id="30409-107">Ugorjon a Készpénz- és bankkezelés > Garancialevelek > Banki hitelmegállapodások pontra.</span><span class="sxs-lookup"><span data-stu-id="30409-107">Go to Cash and bank management > Letters of guarantee > Bank facility agreements.</span></span>
2. <span data-ttu-id="30409-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="30409-108">Click New.</span></span>
3. <span data-ttu-id="30409-109">A Megállapodás száma mezőben adja meg a banki megállapodás számát a tranzakcióhoz.</span><span class="sxs-lookup"><span data-stu-id="30409-109">In the Agreement number field, enter the bank agreement number for the transaction.</span></span>
4. <span data-ttu-id="30409-110">A Bankszámla mezőben válassza ki annak a bankszámlának a számát, amelyhez a garancialevél meg van nyitva.</span><span class="sxs-lookup"><span data-stu-id="30409-110">In the Bank account field, select the bank account number for which the letter of guarantee is open.</span></span> 
5. <span data-ttu-id="30409-111">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="30409-111">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="30409-112">A „Kezdő dátum” mezőben adjon meg egy dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="30409-112">In the Start date field, enter a date and time.</span></span>
7. <span data-ttu-id="30409-113">A Záró dátum mezőben adjon meg egy dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="30409-113">In the End date field, enter a date and time.</span></span>
8. <span data-ttu-id="30409-114">Az Általános szakasz bővítésének átváltása.</span><span class="sxs-lookup"><span data-stu-id="30409-114">Toggle the expansion of the General section.</span></span>
9. <span data-ttu-id="30409-115">Kattintson az Új sor hozzáadására.</span><span class="sxs-lookup"><span data-stu-id="30409-115">Click Add line.</span></span>
10. <span data-ttu-id="30409-116">A Banki hitel típusa mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="30409-116">In the Facility type field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="30409-117">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="30409-117">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="30409-118">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="30409-118">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="30409-119">A Korlát mezőben adja meg a bankkal megtárgyalt összeget.</span><span class="sxs-lookup"><span data-stu-id="30409-119">In the Limit field, enter the amount negotiated with the bank.</span></span>
14. <span data-ttu-id="30409-120">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="30409-120">Click Save.</span></span>
15. <span data-ttu-id="30409-121">Bővítse ki a Garancialevél szakaszt.</span><span class="sxs-lookup"><span data-stu-id="30409-121">Toggle the expansion of the Letter of guarantee section.</span></span>
16. <span data-ttu-id="30409-122">Válassza ki valamelyik lehetőséget a Számítási mód mezőben.</span><span class="sxs-lookup"><span data-stu-id="30409-122">In the Calculation method field, select an option.</span></span>
    * <span data-ttu-id="30409-123">Írja be a számítási módszert és a százalék részleteit a Készpénzkülönbözet, a Bővítési jutalék, a Kiadási jutalék, a Növekményi jutalék vagy az Értékcsökkentési jutalék elemhez, szükség szerint.</span><span class="sxs-lookup"><span data-stu-id="30409-123">Enter the calculation method and percentage details for the Cash margin, Issuance commission, Extension commission, Increase value commission, or Decrease value commission, as appropriate.</span></span>   
17. <span data-ttu-id="30409-124">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="30409-124">Click Save.</span></span>

## <a name="extend-bank-facility-agreement"></a><span data-ttu-id="30409-125">Bővítse ki a banki hitelmegállapodást</span><span class="sxs-lookup"><span data-stu-id="30409-125">Extend bank facility agreement</span></span>
1. <span data-ttu-id="30409-126">A Kibontás gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="30409-126">Click Extend to open the drop dialog.</span></span>
2. <span data-ttu-id="30409-127">Írjon be egy értéket az Új megállapodás mezőbe.</span><span class="sxs-lookup"><span data-stu-id="30409-127">In the New agreement number field, type a value.</span></span>
3. <span data-ttu-id="30409-128">A Záró dátum mezőben adjon meg egy dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="30409-128">In the End date field, enter a date and time.</span></span>
4. <span data-ttu-id="30409-129">Kattintson a Kibontásra.</span><span class="sxs-lookup"><span data-stu-id="30409-129">Click Extend.</span></span>
5. <span data-ttu-id="30409-130">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="30409-130">Click Save.</span></span>
6. <span data-ttu-id="30409-131">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="30409-131">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]