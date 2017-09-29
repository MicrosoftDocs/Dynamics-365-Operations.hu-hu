--- 
title: "Fizetésifelszólítás-sorozat létrehozása"
description: "Használja ezt az útmutatót a fizetésifelszólítás-sorozat létrehozásához."
author: mikefalkner
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 6331c3680169b305c4bfbfada4ba106b619be092
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-collection-letter-sequence"></a><span data-ttu-id="b57e4-103">Fizetésifelszólítás-sorozat létrehozása</span><span class="sxs-lookup"><span data-stu-id="b57e4-103">Create a collection letter sequence</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b57e4-104">Használja ezt az útmutatót a fizetésifelszólítás-sorozat létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="b57e4-104">Use this task guide to create a collection letter sequence.</span></span> <span data-ttu-id="b57e4-105">Ez a feladat az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="b57e4-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="b57e4-106">Ugorjon a Követel és beszedési > Beállítás > Fizetésifelszólítás-sorozat beállítása pontra.</span><span class="sxs-lookup"><span data-stu-id="b57e4-106">Go to Credit and collections > Setup > Set up collection letter sequence.</span></span>
2. <span data-ttu-id="b57e4-107">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b57e4-107">Click New.</span></span>
3. <span data-ttu-id="b57e4-108">A fizetésifelszólítás-sorozat mezőben adjon meg egy sorozatazonosítót, amely a sorozatot jelöli majd.</span><span class="sxs-lookup"><span data-stu-id="b57e4-108">In the Collection letter sequence field, enter a sequence ID that will represent the sequence.</span></span> <span data-ttu-id="b57e4-109">Ezt akkor használja majd, ha feladási profilt állít be.</span><span class="sxs-lookup"><span data-stu-id="b57e4-109">It will be used when you set up a posting profile.</span></span>
4. <span data-ttu-id="b57e4-110">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="b57e4-110">In the Description field, type a value.</span></span>
    * <span data-ttu-id="b57e4-111">A fizetési feltétel opcionális.</span><span class="sxs-lookup"><span data-stu-id="b57e4-111">The terms of payment is optional.</span></span> <span data-ttu-id="b57e4-112">Ha itt megad egy értéket, a fizetési felszólítási díj számlája ezeket a fizetési feltételeket használja a vevőhöz tárolt fizetési feltételek helyett.</span><span class="sxs-lookup"><span data-stu-id="b57e4-112">If you enter a value here, the collection letter fee invoice will use these terms of payment instead of the terms of payment stored with the customer.</span></span>  
5. <span data-ttu-id="b57e4-113">A fizetési felszólítás kódmezőjében válassza ki az első elküldeni kívánt fizetési felszólítás kódját.</span><span class="sxs-lookup"><span data-stu-id="b57e4-113">In the collection letter code field, select the code for the first collection letter that you want to send.</span></span>
    * <span data-ttu-id="b57e4-114">A számlán szereplő határidő, a Napok mezőben megadott türelmi időszak és az ebben a sorban megadott értékek és egyéb információk alapján automatikusan létrehozza az első fizetési felszólítást a rendszer.</span><span class="sxs-lookup"><span data-stu-id="b57e4-114">The first collection letter is created according to the due date on the invoice, the value that you enter for the grace period in the Days field on this line, and other information that you enter on this line.</span></span>  
6. <span data-ttu-id="b57e4-115">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="b57e4-115">In the Description field, type a value.</span></span>
    * <span data-ttu-id="b57e4-116">A díj pénzneme alapértelmezetten a vevő pénzneme.</span><span class="sxs-lookup"><span data-stu-id="b57e4-116">The currency for the fee defaults to the customer currency.</span></span> <span data-ttu-id="b57e4-117">Ez a pénznemkód eltérhet a számla pénznemétől.</span><span class="sxs-lookup"><span data-stu-id="b57e4-117">This currency code can be different than the invoice currency.</span></span>  
7. <span data-ttu-id="b57e4-118">A sorozatban következő fizetési felszólítás hozzáadásához kattintson a Hozzáadás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b57e4-118">Click Add to add the next collection letter that will be sent in the sequence</span></span>
    * <span data-ttu-id="b57e4-119">Az első fizetési felszólítás sok esetben csak figyelmeztetés.</span><span class="sxs-lookup"><span data-stu-id="b57e4-119">In many cases, the first collection letter is just a warning.</span></span> <span data-ttu-id="b57e4-120">Szükség esetén díjakat is hozzáadhat.</span><span class="sxs-lookup"><span data-stu-id="b57e4-120">You can add fees if needed.</span></span>  
8. <span data-ttu-id="b57e4-121">A fizetési felszólítás kódmezőjében válassza ki a soron következő fizetési felszólítást.</span><span class="sxs-lookup"><span data-stu-id="b57e4-121">In the collection letter code field, select the next collection letter that will be sent in the sequence.</span></span>
9. <span data-ttu-id="b57e4-122">Írjon egy értéket a „Leírás” mezőbe.</span><span class="sxs-lookup"><span data-stu-id="b57e4-122">In the Description field, type a value.</span></span>
10. <span data-ttu-id="b57e4-123">A fő számla mezőben válassza ki a díjakhoz használni kívánt bevételi számlát.</span><span class="sxs-lookup"><span data-stu-id="b57e4-123">In the main account field, select the revenue account that will be used for fees.</span></span>
11. <span data-ttu-id="b57e4-124">Adja meg a fizetési felszólítás feladásakor felszámolt díjat.</span><span class="sxs-lookup"><span data-stu-id="b57e4-124">Enter the fee that will be charged when this collection letter is posted.</span></span>
12. <span data-ttu-id="b57e4-125">A Cikkáfacsoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="b57e4-125">In the Item sales tax group field, click the drop down button to open the lookup.</span></span>
    * <span data-ttu-id="b57e4-126">Válasszon a cikkhez áfacsoportot, ha a díj áfaköteles.</span><span class="sxs-lookup"><span data-stu-id="b57e4-126">Select an item sales tax group if sales taxes must be calculated on the fee.</span></span>  
13. <span data-ttu-id="b57e4-127">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="b57e4-127">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="b57e4-128">Adja meg fizetési felszólítás elküldéséhez szükséges minimális lejárt egyenleget.</span><span class="sxs-lookup"><span data-stu-id="b57e4-128">Enter the minimum overdue balance required before a collection letter is sent.</span></span>
15. <span data-ttu-id="b57e4-129">Adja meg a türelmi napok számát.</span><span class="sxs-lookup"><span data-stu-id="b57e4-129">Enter the number of grace days that you will allow.</span></span>
    * <span data-ttu-id="b57e4-130">Ez az esedékességi határidő utáni napok száma, amíg fizetési felszólítás hozható létre.</span><span class="sxs-lookup"><span data-stu-id="b57e4-130">This is the number of days after the due date that a collection letter can be generated.</span></span> <span data-ttu-id="b57e4-131">A kiszámítására használt határidő a Fizetésifelszólítás-sorozatban található Fizetésifelszólítás helyén alapul: ⦁ Az első fizetési felszólítás türelmi időszaka a számla esedékességéhez igazodik.</span><span class="sxs-lookup"><span data-stu-id="b57e4-131">The due date that is used for the calculation depends on the position of the collection letter in the collection letter sequence:   ⦁    The grace period for collection letter 1 is relative to the due date on the invoice.</span></span>  <span data-ttu-id="b57e4-132">⦁A 2. és a többi fizetési felszólítás türelmi időszaka az előző feladott vagy kinyomtatott fizetési felszólítástól függ, ami a Frissítés fizetési felszólítás kódjában történő kiválasztáson alapul a Kinnlevőségek paraméterűrlapjában.</span><span class="sxs-lookup"><span data-stu-id="b57e4-132">⦁ The grace period for collection letters 2 and higher is relative to the date that the previous collection letter is posted or printed, depending on the selection in the Update collection letter code field in the Accounts receivable parameters page.</span></span>  
16. <span data-ttu-id="b57e4-133">A sorozatban utolsó fizetési felszólítás hozzáadásához kattintson a Hozzáadás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b57e4-133">Click Add to add the last collection letter in the sequence.</span></span>
    * <span data-ttu-id="b57e4-134">Az egyes fizetésifelszólítás-sorozatokhoz max. öt fizetési felszólítási kódot lehet létrehozni.</span><span class="sxs-lookup"><span data-stu-id="b57e4-134">You can add up to five collection letter codes for a collection letter sequence.</span></span>  
17. <span data-ttu-id="b57e4-135">A fizetési felszólítás kódmezőjében válassza ki a soron következő fizetési felszólítást.</span><span class="sxs-lookup"><span data-stu-id="b57e4-135">In the collection letter code field, select the next collection letter that will be sent in the sequence.</span></span>
18. <span data-ttu-id="b57e4-136">Írjon egy értéket a „Leírás” mezőbe.</span><span class="sxs-lookup"><span data-stu-id="b57e4-136">In the Description field, type a value.</span></span>
19. <span data-ttu-id="b57e4-137">A Fő számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="b57e4-137">In the Main account field, specify the desired values.</span></span>
20. <span data-ttu-id="b57e4-138">A Díj pénzneme mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="b57e4-138">In the Fee in currency field, enter a number.</span></span>
21. <span data-ttu-id="b57e4-139">A Cikkáfacsoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="b57e4-139">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
22. <span data-ttu-id="b57e4-140">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="b57e4-140">In the list, click the link in the selected row.</span></span>
23. <span data-ttu-id="b57e4-141">Az Egyenleg esedékessé válásának minimuma mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="b57e4-141">In the Minimum overdue balance field, enter a number.</span></span>
24. <span data-ttu-id="b57e4-142">A Napok mezőbe írjon be egy számot.</span><span class="sxs-lookup"><span data-stu-id="b57e4-142">In the Days field, enter a number.</span></span>
25. <span data-ttu-id="b57e4-143">A jelölőnégyzetet bejelölve leállíthatja a további szállításokat és további számlák kiállítását a vevőnek.</span><span class="sxs-lookup"><span data-stu-id="b57e4-143">Select this check box to stop the customer from additional deliveries and invoicing.</span></span>
    * <span data-ttu-id="b57e4-144">A számla zárolásának feloldásához válassza a Nem szót a Vevők oldal Számlázás és szállítás felfüggesztve mezőjében.</span><span class="sxs-lookup"><span data-stu-id="b57e4-144">To unblock the account, select No in the Invoicing and delivery on hold field in the Customers page.</span></span>  
26. <span data-ttu-id="b57e4-145">Bontsa ki a Jegyzet gyorslapot.</span><span class="sxs-lookup"><span data-stu-id="b57e4-145">Expand the Note fasttab.</span></span>
27. <span data-ttu-id="b57e4-146">Írja be a fizetési felszólításon megjelentetni kívánt szöveget az adott fizetési felszólítási kód esetén.</span><span class="sxs-lookup"><span data-stu-id="b57e4-146">Enter the text to appear on the collection letter for the selected collection letter code.</span></span>
    * <span data-ttu-id="b57e4-147">Ezt a szöveget több nyelvre lefordíthatja a Fordítás menüben a megjegyzés doboz felett.</span><span class="sxs-lookup"><span data-stu-id="b57e4-147">You can translate this text in to multiple languages using the Translations menu above the note box.</span></span>  


