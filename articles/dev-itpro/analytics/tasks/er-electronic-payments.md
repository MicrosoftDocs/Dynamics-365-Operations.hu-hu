--- 
title: "ER – Hozzon létre elektronikus dokumentumokat a kifizetésekre vonatkozóan a formátumkonfiguráció segítségével"
description: "A következő lépések leírják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként használhat egy új Elektronikus jelentés (ER) konfigurációt, az elektronikus fizetési dokumentum létrehozásához a kifizetések feldolgozására vonatkozóan."
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendPaymMode, LedgerJournalTable, LedgerJournalTransVendPaym, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: cf2ae8fb451eba1054bb94edbce009dcfa8c872c
ms.contentlocale: hu-hu
ms.lasthandoff: 09/14/2018

---
# <a name="er-generate-electronic-documents-for-payments-using-a-format-configuration"></a><span data-ttu-id="13478-103">ER – Hozzon létre elektronikus dokumentumokat a kifizetésekre vonatkozóan a formátumkonfiguráció segítségével</span><span class="sxs-lookup"><span data-stu-id="13478-103">ER Generate electronic documents for payments using a format configuration</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="13478-104">A következő lépések leírják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként használhat egy új Elektronikus jelentés (ER) konfigurációt, az elektronikus fizetési dokumentum létrehozásához a kifizetések feldolgozására vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="13478-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can use a new Electronic reporting (ER) format configuration to generate electronic documents for processing payments.</span></span> <span data-ttu-id="13478-105">Ezeket a lépéseket a GBSI minta vállalatban hajthatja végre.</span><span class="sxs-lookup"><span data-stu-id="13478-105">These steps can be performed in the GBSI sample company.</span></span>

<span data-ttu-id="13478-106">Ahhoz, hogy végrehajthassa ezeket a lépéseket hajtsa végre a „Konfiguráció létrehozása a kifizetési dokumentum formátumával” eljárás lépéseit.</span><span class="sxs-lookup"><span data-stu-id="13478-106">To complete these steps, you must first complete the steps in the “Create a configuration with format of payment document” procedure.</span></span>


## <a name="change-the-configuration-of-the-electronic-payment-method"></a><span data-ttu-id="13478-107">Módosítsa az elektronikus fizetési mód konfigurációját</span><span class="sxs-lookup"><span data-stu-id="13478-107">Change the configuration of the electronic payment method</span></span>
1. <span data-ttu-id="13478-108">Ugorjon a Kötelezettségek > Kifizetés beállítása > Fizetési módok pontra.</span><span class="sxs-lookup"><span data-stu-id="13478-108">Go to Accounts payable > Payment setup > Methods of payment.</span></span>
2. <span data-ttu-id="13478-109">Váltsa át a Fájlformátum szakaszt a kibontáshoz, ha szükséges.</span><span class="sxs-lookup"><span data-stu-id="13478-109">Toggle the File format section to expand it, if needed.</span></span>
3. <span data-ttu-id="13478-110">Rekordok kereséséhez használja a gyorsszűrőt.</span><span class="sxs-lookup"><span data-stu-id="13478-110">Use the Quick Filter to find records.</span></span> <span data-ttu-id="13478-111">Például végezzen szűrést az „Elektronikus” érték beírásával a Fizetési mód mezőben.</span><span class="sxs-lookup"><span data-stu-id="13478-111">For example, filter on the Method of payment field with a value of 'Electronic'.</span></span>
4. <span data-ttu-id="13478-112">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="13478-112">Click Edit.</span></span>
5. <span data-ttu-id="13478-113">Állítsa át az Általános elektronikus jelentéskészítés mezőt Igen értékre.</span><span class="sxs-lookup"><span data-stu-id="13478-113">Set the General electronic reporting field to Yes.</span></span>
    * <span data-ttu-id="13478-114">Válassza ki az Igen értéket az általános elektronikus jelentési minta használatba vételéhez a Kifizetési fájlok létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="13478-114">Select Yes to use the General electronic reporting pattern for payment files generation.</span></span>  
6. <span data-ttu-id="13478-115">A Név mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="13478-115">In the Name field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="13478-116">Válassza ki a BACS (UK fiktív) formátumkonfigurációt.</span><span class="sxs-lookup"><span data-stu-id="13478-116">Select BACS (UK fictitious) format configuration.</span></span>
8. <span data-ttu-id="13478-117">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="13478-117">Click Save.</span></span>
9. <span data-ttu-id="13478-118">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="13478-118">Close the page.</span></span>

## <a name="test-the-format-of-generated-payment-files"></a><span data-ttu-id="13478-119">Tesztelje a létrehozott fizetési fájlok formátumát</span><span class="sxs-lookup"><span data-stu-id="13478-119">Test the format of generated payment files</span></span>
1. <span data-ttu-id="13478-120">Ugorjon a Kötelezettségek > Fizetési beállítás > Fizetési napló pontra.</span><span class="sxs-lookup"><span data-stu-id="13478-120">Go to Accounts payable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="13478-121">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="13478-121">Click New.</span></span>
3. <span data-ttu-id="13478-122">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="13478-122">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="13478-123">A Név mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="13478-123">In the Name field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="13478-124">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="13478-124">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="13478-125">Válassza ki a VendPay lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="13478-125">Select VendPay.</span></span>  
6. <span data-ttu-id="13478-126">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="13478-126">Click Save.</span></span>
7. <span data-ttu-id="13478-127">Kattintson a Sorok pontra.</span><span class="sxs-lookup"><span data-stu-id="13478-127">Click Lines.</span></span>
8. <span data-ttu-id="13478-128">A Vállalat mezőben írja be az „DEMF” értéket.</span><span class="sxs-lookup"><span data-stu-id="13478-128">In the Company field, type 'DEMF'.</span></span>
    * <span data-ttu-id="13478-129">DEMF</span><span class="sxs-lookup"><span data-stu-id="13478-129">DEMF</span></span>  
9. <span data-ttu-id="13478-130">A Számla mezőben állítsa az értékeket „DE-01001”-re.</span><span class="sxs-lookup"><span data-stu-id="13478-130">In the Account field, specify the values 'DE-01001'.</span></span>
    * <span data-ttu-id="13478-131">DE - 01001</span><span class="sxs-lookup"><span data-stu-id="13478-131">DE-01001</span></span>  
10. <span data-ttu-id="13478-132">Írja be a „Fizetés” szöveget a Leírás mezőbe.</span><span class="sxs-lookup"><span data-stu-id="13478-132">In the Description field, type 'Payment'.</span></span>
    * <span data-ttu-id="13478-133">Fizetés</span><span class="sxs-lookup"><span data-stu-id="13478-133">Payment</span></span>  
11. <span data-ttu-id="13478-134">Adjon meg egy számot a Tartozik mezőben.</span><span class="sxs-lookup"><span data-stu-id="13478-134">In the Debit field, enter a number.</span></span>
    * <span data-ttu-id="13478-135">1000</span><span class="sxs-lookup"><span data-stu-id="13478-135">1000</span></span>  
12. <span data-ttu-id="13478-136">Kattintson a Fizetések fülre.</span><span class="sxs-lookup"><span data-stu-id="13478-136">Click the Payment tab.</span></span>
13. <span data-ttu-id="13478-137">A Fizetési mód mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="13478-137">In the Method of payment field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="13478-138">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="13478-138">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="13478-139">Válassza ki az Elektronikus érték lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="13478-139">Select the Electronic value.</span></span>  
15. <span data-ttu-id="13478-140">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="13478-140">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="13478-141">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="13478-141">Click Save.</span></span>
17. <span data-ttu-id="13478-142">Kattintson a Kifizetések létrehozása elemre.</span><span class="sxs-lookup"><span data-stu-id="13478-142">Click Generate payments.</span></span>
18. <span data-ttu-id="13478-143">A Fizetési mód mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="13478-143">In the Method of payment field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="13478-144">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="13478-144">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="13478-145">Válassza ki az Elektronikus érték lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="13478-145">Select the Electronic value.</span></span>  
20. <span data-ttu-id="13478-146">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="13478-146">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="13478-147">Válassza ki az Elektronikus érték lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="13478-147">Select the Electronic value.</span></span>  
21. <span data-ttu-id="13478-148">Írjon be egy értéket a Fájlnév mezőbe.</span><span class="sxs-lookup"><span data-stu-id="13478-148">In the File name field, type a value.</span></span>
    * <span data-ttu-id="13478-149">Például írja be a „Kifizetések” szöveget.</span><span class="sxs-lookup"><span data-stu-id="13478-149">For example, type 'payments'.</span></span>  
22. <span data-ttu-id="13478-150">A Bankszámla mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="13478-150">In the Bank account field, click the drop-down button to open the lookup.</span></span>
23. <span data-ttu-id="13478-151">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="13478-151">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="13478-152">Válassza ki a GBSI MŰV. értéket.</span><span class="sxs-lookup"><span data-stu-id="13478-152">Select the value GBSI OPER.</span></span>  
24. <span data-ttu-id="13478-153">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="13478-153">Click OK.</span></span>
25. <span data-ttu-id="13478-154">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="13478-154">Click OK.</span></span>
    * <span data-ttu-id="13478-155">Elemezze a létrehozott kifizetési fájlt az XML-formátumban.</span><span class="sxs-lookup"><span data-stu-id="13478-155">Analyze the created payment file in XML format.</span></span> <span data-ttu-id="13478-156">Hasonlítsa össze a tervezett dokumentumelrendezéssel és a meghatározott fizetési tranzakció attribútumokkal.</span><span class="sxs-lookup"><span data-stu-id="13478-156">Compare it with the designed document layout and defined payment transaction attributes.</span></span>  


