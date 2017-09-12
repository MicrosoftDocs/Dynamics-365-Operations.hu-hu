--- 
title: "Értékesítési szerződések megadása"
description: "Ez az eljárás bemutatja, hogyan hozhat létre értékesítési szerződést, amely kötelezi valamelyik vevőjét egy termék vásárlására egy egyeztetett összegben adott idő alatt, különleges engedményekért cserébe."
author: omulvad
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 943ae430b148670d248716c9ece21850bf7d2dfd
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---
# <a name="enter-sales-agreements"></a><span data-ttu-id="54e5a-103">Értékesítési szerződések megadása</span><span class="sxs-lookup"><span data-stu-id="54e5a-103">Enter sales agreements</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="54e5a-104">Ez az eljárás bemutatja, hogyan hozhat létre olyan értékesítési szerződést, amely kötelezi valamelyik vevőjét egy termék vásárlására</span><span class="sxs-lookup"><span data-stu-id="54e5a-104">This procedure shows you how to create a sales agreement that commits one of your customers to buy a product for an</span></span>

<span data-ttu-id="54e5a-105">egy egyeztetett összegben adott idő alatt, különleges engedményekért cserébe.</span><span class="sxs-lookup"><span data-stu-id="54e5a-105">agreed amount over time in exchange for special discounts.</span></span> <span data-ttu-id="54e5a-106">Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is futtathatja.</span><span class="sxs-lookup"><span data-stu-id="54e5a-106">You can run this procedure in demo data company USMF or on your own data.</span></span>


## <a name="set-up-sales-agreement-header"></a><span data-ttu-id="54e5a-107">Értékesítési szerződés fejléc beállítása</span><span class="sxs-lookup"><span data-stu-id="54e5a-107">Set up sales agreement header</span></span>
1. <span data-ttu-id="54e5a-108">Lépjen az Értékesítés és marketing > Értékesítési szerződések > Értékesítési szerződések menüpontba.</span><span class="sxs-lookup"><span data-stu-id="54e5a-108">Go to Sales and marketing > Sales agreements > Sales agreements.</span></span>
2. <span data-ttu-id="54e5a-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="54e5a-109">Click New.</span></span>
3. <span data-ttu-id="54e5a-110">A Vevői számla mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="54e5a-110">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="54e5a-111">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="54e5a-111">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="54e5a-112">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="54e5a-112">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="54e5a-113">Az Értékesítési szerződés osztályozása mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="54e5a-113">In the Sales agreement classification field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="54e5a-114">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="54e5a-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="54e5a-115">Bontsa ki az Általános szakaszt.</span><span class="sxs-lookup"><span data-stu-id="54e5a-115">Expand the General section.</span></span>
9. <span data-ttu-id="54e5a-116">Az Alapértelmezett kötelezettség mezőben válassza ki a „Termék értékére vonatkozó kötelezettség” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="54e5a-116">In the Default commitment field, select 'Product value commitment'.</span></span>
    * <span data-ttu-id="54e5a-117">A kötelezettségtípus egy kötelező feltétel, amelyet a megállapodáshoz kell hozzárendelnie, hogy meghatározza, miként teljesítendő a megállapodási szerződés.</span><span class="sxs-lookup"><span data-stu-id="54e5a-117">A commitment type is a mandatory criterion that you must assign to the agreement to define how the agreement contract will be fulfilled.</span></span> <span data-ttu-id="54e5a-118">A négy előre meghatározott típus segítségével beállíthatja a vevő kötelezettségének célját, mennyiségben vagy értékben kifejezve.</span><span class="sxs-lookup"><span data-stu-id="54e5a-118">The four predefined types let you set up the customer's commitment target, expressed as a quantity or a value.</span></span> <span data-ttu-id="54e5a-119">A mennyiség kötelezettségtípust kizárólag egy adott termékre lehet alkalmazni, de az értékalapú típusok alkalmazhatóak mind meghatározott és nem meghatározott termékek értékesítésére.</span><span class="sxs-lookup"><span data-stu-id="54e5a-119">The quantity commitment type can only be applied to a specific product, but the value-based types are applicable to sales of both specific and non-specific products.</span></span>  
10. <span data-ttu-id="54e5a-120">A Lejárat dátuma mezőben állítsa be a dátumot egy későbbi dátumra, amikorra szeretné, hogy lejárjon a megállapodás.</span><span class="sxs-lookup"><span data-stu-id="54e5a-120">In the Expiration date field, set the date to a future date when you want the agreement to expire.</span></span>
11. <span data-ttu-id="54e5a-121">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="54e5a-121">Click OK.</span></span>

## <a name="set-up-product-value-commitment-lines"></a><span data-ttu-id="54e5a-122">Termék értékére vonatkozó kötelezettség sorainak beállítása.</span><span class="sxs-lookup"><span data-stu-id="54e5a-122">Set up product value commitment lines</span></span>
1. <span data-ttu-id="54e5a-123">Kattintson az Új sor hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="54e5a-123">Click Add line.</span></span>
2. <span data-ttu-id="54e5a-124">A Cikkszám mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="54e5a-124">In the Item number field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="54e5a-125">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="54e5a-125">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="54e5a-126">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="54e5a-126">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="54e5a-127">A megállapodásra kiválasztott kötelezettségvállalás típus hatással van arra, hogy milyen típusú információkat adhat meg a megállapodás soraira.</span><span class="sxs-lookup"><span data-stu-id="54e5a-127">The type of commitment that you have chosen for the agreement affects the kind of information you can enter for the agreement lines.</span></span> <span data-ttu-id="54e5a-128">Például egy értékalapú megállapodásra meg kell adnia a teljes nettó összeget (a megállapodás szerinti pénznemben), amelyért a vevő kötelezően vásárol Öntől árukat.</span><span class="sxs-lookup"><span data-stu-id="54e5a-128">For example, for a value-based agreement you must specify the total net amount (in the agreed currency) for which the customer commits to buys goods from you.</span></span> <span data-ttu-id="54e5a-129">Ebben a példában a soron található Mennyiség és Egységár mezők nem érhetők el, mert a vevő számára egy termékből adott értékben történő vásárlásra vonatkozó megállapodást hoz létre.</span><span class="sxs-lookup"><span data-stu-id="54e5a-129">In this example the Quantity and Unit fields on the line are unavailable because you’re creating an agreement for the customer to buy a specific value of a product.</span></span>   
5. <span data-ttu-id="54e5a-130">A Nettó összeg mezőben adja meg azt a pénzösszeget, amely értékben a vevő kötelezettséget vállalt a vásárlásra.</span><span class="sxs-lookup"><span data-stu-id="54e5a-130">In the Net amount field, enter the monetary amount that the customer has committed to buying.</span></span>
6. <span data-ttu-id="54e5a-131">Az Engedményszázalék mezőbe írjon be egy százalékos értéket, amely az ehhez a szerződéshez kapcsolt vásárlói értékesítésirendelés-sorokra lesznek érvényesek.</span><span class="sxs-lookup"><span data-stu-id="54e5a-131">In the Discount percent field, enter a percentage value that will apply to the customer's sales order lines that are linked to this agreement.</span></span>
7. <span data-ttu-id="54e5a-132">Bontsa ki a Soradatok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="54e5a-132">Expand the Line details section.</span></span>
8. <span data-ttu-id="54e5a-133">A Maximum betartatása mezőben válassza az Igen lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="54e5a-133">Select Yes in the Max is enforced field.</span></span>
    * <span data-ttu-id="54e5a-134">A Maximum betartatása kiválasztása azt jelenti, hogy a kötelezettségvállalás speciális árait, engedményeit és/vagy fizetési feltételeit használó minden értékesítésirendelés-sor teljes összege nem haladhatja meg a kötelezettségvállalásban megadott összeget.</span><span class="sxs-lookup"><span data-stu-id="54e5a-134">Selecting Max is enforced means that the total amount of all the sales order lines that use the commitment's special prices, discounts and/or payment terms must not exceed the amount specified on the commitment.</span></span>  
    * <span data-ttu-id="54e5a-135">A minimális és maximális kiadási összegek olyan értéktartományt adnak meg, amelyet értékesíteni kell minden, a kiválasztott megállapodást használó értékesítési rendelés esetén.</span><span class="sxs-lookup"><span data-stu-id="54e5a-135">The minimum and maximum release amounts specify a range of values that must be sold on each sales order that uses the selected agreement.</span></span>   
9. <span data-ttu-id="54e5a-136">Bontsa ki az Értékesítési szerződés fejléc részét.</span><span class="sxs-lookup"><span data-stu-id="54e5a-136">Expand the Sales agreement header section.</span></span>
    * <span data-ttu-id="54e5a-137">Ha a megállapodás állapotára nem Érvényes van beállítva, az értékesítési rendelések nem társíthatók a megállapodáshoz, és ezért nem járulhatnak hozzá a szerződés teljesítéséhez.</span><span class="sxs-lookup"><span data-stu-id="54e5a-137">Unless the status of the agreement is set to Effective, sales orders cannot be associated with the agreement and can therefore not contribute to the fulfilment of that agreement.</span></span> <span data-ttu-id="54e5a-138">Az állapot manuálisan módosítható ebben a fázisban.</span><span class="sxs-lookup"><span data-stu-id="54e5a-138">You can change the status manually at this stage.</span></span> <span data-ttu-id="54e5a-139">Az állapot azonban normális esetben akkor módosulna, amikor a vevőnek visszaigazolja a megállapodást.</span><span class="sxs-lookup"><span data-stu-id="54e5a-139">However, the status would normally be changed when you confirm the agreement for the customer.</span></span>  
10. <span data-ttu-id="54e5a-140">A Művelet panelen kattintson az Értékesítési szerződés elemre.</span><span class="sxs-lookup"><span data-stu-id="54e5a-140">On the Action Pane, click Sales agreement.</span></span>
11. <span data-ttu-id="54e5a-141">Kattintson a Megerősítés gombra.</span><span class="sxs-lookup"><span data-stu-id="54e5a-141">Click Confirmation.</span></span>
    * <span data-ttu-id="54e5a-142">Győződjön meg arról, hogy a Szerződés megjelölése érvényesként beállítás Igen értékre van állítva.</span><span class="sxs-lookup"><span data-stu-id="54e5a-142">Make sure that the Mark agreement as effective option is set to Yes.</span></span>  
12. <span data-ttu-id="54e5a-143">Válassza az Igen lehetőséget a Jelentés nyomtatása mezőben.</span><span class="sxs-lookup"><span data-stu-id="54e5a-143">Select Yes in the Print report field.</span></span>
13. <span data-ttu-id="54e5a-144">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="54e5a-144">Click OK.</span></span>
14. <span data-ttu-id="54e5a-145">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="54e5a-145">Close the page.</span></span>
    * <span data-ttu-id="54e5a-146">A megállapodás most már érvényes, és elkezdheti a vevői rendelések csatolását a megállapodáshoz, a kötelezettség céljának kiegyenlítéséhez.</span><span class="sxs-lookup"><span data-stu-id="54e5a-146">The agreement is now effective and you can start linking the customer's orders to the agreement, to offset against the committed target.</span></span>  


