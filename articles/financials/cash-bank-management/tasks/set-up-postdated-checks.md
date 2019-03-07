---
title: Jövőben esedékes csekkek beállítása
description: Ez a témakör bemutatja, hogyan állíthatja be, miként legyenek feladva a jövőben esedékes csekkek naplóbejegyzési, és melyik feladási naplókat kell használni elszámolási tételekhez és szállítói kifizetésekhez.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankParameters, VendPaymMode, CustPaymMode
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e4b18ebe1388998b45e5ef38318b0ade9153f7c8
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "342615"
---
# <a name="set-up-postdated-checks"></a><span data-ttu-id="5ce86-103">Jövőben esedékes csekkek beállítása</span><span class="sxs-lookup"><span data-stu-id="5ce86-103">Set up postdated checks</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5ce86-104">Ez a témakör bemutatja, hogyan állíthatja be, miként legyenek feladva a jövőben esedékes csekkek naplóbejegyzési, és melyik feladási naplókat kell használni elszámolási tételekhez és szállítói kifizetésekhez.</span><span class="sxs-lookup"><span data-stu-id="5ce86-104">This topic explains how to specify whether to post journal entries for postdated checks and which posting journals to use for clearing entries and vendor payments.</span></span> <span data-ttu-id="5ce86-105">Emellett beállíthat elszámolószámokat a kiállított csekkekhez, a fogadott csekkekhez és az adóelőleghez is.</span><span class="sxs-lookup"><span data-stu-id="5ce86-105">You can also specify clearing accounts for issued checks, received checks, and withholding tax.</span></span> <span data-ttu-id="5ce86-106">Jövőben esedékes csekkek, amelyeket jövőbeli dátumon való fizetés céljából állítottak ki.</span><span class="sxs-lookup"><span data-stu-id="5ce86-106">Postdated checks that are issued to make and receive payments on a future date.</span></span> <span data-ttu-id="5ce86-107">Megadhatja, hogy a csekk szerepeljen-e a számviteli könyvekben az esedékesség dátuma előtt.</span><span class="sxs-lookup"><span data-stu-id="5ce86-107">You can specify whether the check must be reflected in the accounting books before its maturity date.</span></span>



<span data-ttu-id="5ce86-108">Ezen eljárás szerepköre: Pénztáros.</span><span class="sxs-lookup"><span data-stu-id="5ce86-108">The role of this procedure is Treasurer.</span></span> <span data-ttu-id="5ce86-109">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="5ce86-109">This procedure uses the USMF demo company.</span></span>


## <a name="set-up-postdated-checks"></a><span data-ttu-id="5ce86-110">Jövőben esedékes csekkek beállítása</span><span class="sxs-lookup"><span data-stu-id="5ce86-110">Set up postdated checks</span></span>
1. <span data-ttu-id="5ce86-111">Ugorjon a Készpénz- és bankkezelés > Beállítás > Készpénz- és bankkezelési paraméterek pontra.</span><span class="sxs-lookup"><span data-stu-id="5ce86-111">Go to Cash and bank management > Setup > Cash and bank management parameters.</span></span>
2. <span data-ttu-id="5ce86-112">Kattintson a Jövőben esedékes csekkek fülre.</span><span class="sxs-lookup"><span data-stu-id="5ce86-112">Click the Postdated checks tab.</span></span>
3. <span data-ttu-id="5ce86-113">Jelölje be a Jövőben esedékes csekkek jelölőnégyzetet, vagy törölje a jelet a jelölőnégyzetből.</span><span class="sxs-lookup"><span data-stu-id="5ce86-113">Select or clear the Enable postdated checks check box.</span></span>
4. <span data-ttu-id="5ce86-114">Jelölje be, vagy törölje a jelet jelölőnégyzetből a Jövőben esedékes csekkekhez naplóbejegyzések feladása mellett.</span><span class="sxs-lookup"><span data-stu-id="5ce86-114">Select or clear the Post journal entries for postdated checks check box.</span></span>
5. <span data-ttu-id="5ce86-115">Az Elszámolási számla a kiállított csekkekhez mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="5ce86-115">In the Clearing account for issued checks field, specify the desired values.</span></span>
6. <span data-ttu-id="5ce86-116">Az Elszámolási számla a kapott csekkekhez mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="5ce86-116">In the Clearing account for received checks field, specify the desired values.</span></span>
7. <span data-ttu-id="5ce86-117">Az Általános napló bejegyzések elszámolásához mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5ce86-117">In the General journal for clearing entries field, type a value.</span></span>
8. <span data-ttu-id="5ce86-118">A Jövőben esedékes csekkek átvezetése ebbe a szállítói kifizetési naplóba mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5ce86-118">In the Transfer postdated checks to this vendor payment journal field, type a value.</span></span>
9. <span data-ttu-id="5ce86-119">Az Adóelőleg-elszámolási számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="5ce86-119">In the Withholding tax clearing account field, specify the desired values.</span></span>
10. <span data-ttu-id="5ce86-120">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="5ce86-120">Click Save.</span></span>
11. <span data-ttu-id="5ce86-121">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5ce86-121">Close the page.</span></span>
12. <span data-ttu-id="5ce86-122">Ugorjon a Kötelezettségek > Kifizetés beállítása > Fizetési módok pontra.</span><span class="sxs-lookup"><span data-stu-id="5ce86-122">Go to Accounts payable > Payment setup > Methods of payment.</span></span>
13. <span data-ttu-id="5ce86-123">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5ce86-123">Click New.</span></span>
14. <span data-ttu-id="5ce86-124">Írjon be egy értéket a Fizetési mód mezőbe.</span><span class="sxs-lookup"><span data-stu-id="5ce86-124">In the Method of payment field, type a value.</span></span>
15. <span data-ttu-id="5ce86-125">A Jövőben esedékes csekk elszámolási feladása lehetőség bejelölésével jelezheti, hogy a csekk összege elszámolószámlára lesz feladva.</span><span class="sxs-lookup"><span data-stu-id="5ce86-125">Select the Postdated check clearing posting option to indicate that the check amount is posted to a clearing account.</span></span>
16. <span data-ttu-id="5ce86-126">A Fiók típusa mezőben válassza ki a „Bank” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5ce86-126">In the Account type field, select 'Bank'.</span></span>
    * <span data-ttu-id="5ce86-127">A fizetési módszer ellenszámlájának ellenőrzési módja egy bank lesz.</span><span class="sxs-lookup"><span data-stu-id="5ce86-127">The offset account of the payment method will be a bank.</span></span>  
17. <span data-ttu-id="5ce86-128">A Fizetési számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="5ce86-128">In the Payment account field, specify the desired values.</span></span>
    * <span data-ttu-id="5ce86-129">Válassza ki a számlaösszeg levonására szolgáló bankszámlát.</span><span class="sxs-lookup"><span data-stu-id="5ce86-129">Select the bank account that is used to deduct the invoice amount.</span></span>  
18. <span data-ttu-id="5ce86-130">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5ce86-130">Close the page.</span></span>
19. <span data-ttu-id="5ce86-131">Ugorjon a Kinnlevőségek > Fizetési beállítás > Fizetési mód pontra</span><span class="sxs-lookup"><span data-stu-id="5ce86-131">Go to Accounts receivable > Payment setup > Methods of payment</span></span>
20. <span data-ttu-id="5ce86-132">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5ce86-132">Click New.</span></span>
21. <span data-ttu-id="5ce86-133">Írjon be egy értéket a Fizetési mód mezőbe.</span><span class="sxs-lookup"><span data-stu-id="5ce86-133">In the Method of payment field, type a value.</span></span>
22. <span data-ttu-id="5ce86-134">A Jövőben esedékes csekk elszámolási feladása lehetőség bejelölésével jelezheti, hogy a csekk összege elszámolószámlára lesz feladva.</span><span class="sxs-lookup"><span data-stu-id="5ce86-134">Select the Postdated check clearing posting option to indicate that the check amount is posted to a clearing account.</span></span>
23. <span data-ttu-id="5ce86-135">A Fiók típusa mezőben válassza ki a „Bank” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5ce86-135">In the Account type field, select 'Bank'.</span></span>
    * <span data-ttu-id="5ce86-136">A fizetési módszer ellenszámlájának ellenőrzési módja egy bank lesz.</span><span class="sxs-lookup"><span data-stu-id="5ce86-136">The offset account of the payment method will be a bank.</span></span>  
24. <span data-ttu-id="5ce86-137">A Fizetési számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="5ce86-137">In the Payment account field, specify the desired values.</span></span>
    * <span data-ttu-id="5ce86-138">Válassza ki a számlaösszeg levonására szolgáló bankszámlát.</span><span class="sxs-lookup"><span data-stu-id="5ce86-138">Select the bank account that is used to deduct the invoice amount.</span></span>  
25. <span data-ttu-id="5ce86-139">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5ce86-139">Close the page.</span></span>

