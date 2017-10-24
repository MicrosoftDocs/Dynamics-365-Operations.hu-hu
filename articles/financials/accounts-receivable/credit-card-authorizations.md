---
title: "Hitelkártya-beállítás, engedélyezés és rögzítés"
description: "Ez a cikk a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition rendszer hitelkártya-engedélyezéséről nyújt tájékoztatást. A fizetési szolgáltatás beállításának módjáról, az értékesítési rendeléshez történő hitelkártya hozzáadásáról és az engedélyezés érvénytelenítéséről nyújt tájékoztatást."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CreditCardProcessors, CustTable, SalesTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 3041
ms.assetid: 678f6899-bfa5-439b-aaca-b4affcc338ba
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: dad3964003d0be0c22b0346aba2b3319278ffaa9
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="credit-card-setup-authorization-and-capture"></a><span data-ttu-id="11b6f-104">Hitelkártya-beállítás, engedélyezés és rögzítés</span><span class="sxs-lookup"><span data-stu-id="11b6f-104">Credit card setup, authorization, and capture</span></span>

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]


<span data-ttu-id="11b6f-105">Ez a cikk a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition rendszer hitelkártya-engedélyezéséről nyújt tájékoztatást.</span><span class="sxs-lookup"><span data-stu-id="11b6f-105">This article provides an overview of credit card authorization in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span></span> <span data-ttu-id="11b6f-106">A fizetési szolgáltatás beállításának módjáról, az értékesítési rendeléshez történő hitelkártya hozzáadásáról és az engedélyezés érvénytelenítéséről nyújt tájékoztatást.</span><span class="sxs-lookup"><span data-stu-id="11b6f-106">It includes information about how to set up a payment service, add a credit card to a sales order, and void an authorization.</span></span>

<a name="setting-up-the-credit-card-payment-service"></a><span data-ttu-id="11b6f-107">A hitelkártyás fizetési szolgáltatás beállítása</span><span class="sxs-lookup"><span data-stu-id="11b6f-107">Setting up the credit card payment service</span></span>
------------------------------------------

<span data-ttu-id="11b6f-108">Hitelkártyák használatához állítson be és aktiváljon egy fizetési szolgáltatást a Fizetési szolgáltatások lapon.</span><span class="sxs-lookup"><span data-stu-id="11b6f-108">To use credit cards, you must set up and activate a payment service on the Payment services page.</span></span> <span data-ttu-id="11b6f-109">A fizetési szolgáltatás a jogi személy és a vevő hitelkártya-terheléseit feldolgozó bank közötti kapcsolatként működik.</span><span class="sxs-lookup"><span data-stu-id="11b6f-109">A payment service acts as a bridge between your legal entity and the bank that processes a customer's credit card charges.</span></span> <span data-ttu-id="11b6f-110">Olyan hitelkártya-szolgáltatóval kell együttműködnie, amely szerepel a Fizetési csatlakoztató mezőben, és ennél a szolgáltatónál kell egy számlát létrehoznia.</span><span class="sxs-lookup"><span data-stu-id="11b6f-110">You must work with a credit card provider that is listed in the Payment connector field and set up an account with that provider.</span></span> <span data-ttu-id="11b6f-111">Ezután további opciókat kell majd beállítania a Fizetési szolgáltatások oldalon, hitelkártyatípusokat kell beállítania az American Express, Discover, MasterCard és Discover számára a hitelkártya-típusok oldalon, és a szolgáltatót alapértelmezett szolgáltatóként kell beállítania.</span><span class="sxs-lookup"><span data-stu-id="11b6f-111">You must then set up the other options on the Payment services page, set up credit card types for American Express, Discover, MasterCard, and Discover on the Credit card types page, and activate the provider as the default provider.</span></span> <span data-ttu-id="11b6f-112">A beállítás befejezéséhez ezeket a lépéseket is be kell tartania:</span><span class="sxs-lookup"><span data-stu-id="11b6f-112">You must also follow these steps to complete your setup:</span></span>
-   <span data-ttu-id="11b6f-113">A Kinnlevőségek paraméteroldalon adja meg a paramétereket a hitelkártya-engedélyezések használatához.</span><span class="sxs-lookup"><span data-stu-id="11b6f-113">On the Accounts receivable parameters page, specify parameters for using credit card authorizations.</span></span>
-   <span data-ttu-id="11b6f-114">A Fizetési feltételek oldalon lehet beállítani a hitelkártyák fizetési feltételeit.</span><span class="sxs-lookup"><span data-stu-id="11b6f-114">On the Terms of payment page, set up payment terms for credit cards.</span></span> <span data-ttu-id="11b6f-115">A Fizetés típusa mezőben válassza ki a Hitelkártyát.</span><span class="sxs-lookup"><span data-stu-id="11b6f-115">In the Payment type field, select Credit card.</span></span>
-   <span data-ttu-id="11b6f-116">A Vásárlói hitelkártyák oldalon adja meg a vevők számára a hitelkártya-adatokat.</span><span class="sxs-lookup"><span data-stu-id="11b6f-116">On the Customer credit cards page, enter credit card information for customers.</span></span>

## <a name="adding-a-new-credit-card"></a><span data-ttu-id="11b6f-117">Új hitelkártya hozzáadása</span><span class="sxs-lookup"><span data-stu-id="11b6f-117">Adding a new credit card</span></span>
<span data-ttu-id="11b6f-118">Új hitelkártya-rekordokat a Vevők lapon a Vevő, Beállítás, Hitelkártya használatával hozhat létre.</span><span class="sxs-lookup"><span data-stu-id="11b6f-118">You can create new credit card records on the Customers page by using Customer, Set up, Credit card.</span></span> <span data-ttu-id="11b6f-119">Hitelkártya-rekordokat értékesítési rendelések beírásakor is létrehozhat az Értékesítési rendelés oldalon, a Kezelés, Vevő, Hitelkártya, Jegyzék segítségével.</span><span class="sxs-lookup"><span data-stu-id="11b6f-119">You can also create credit card records when you enter sales orders on the Sales order page, by using Manage, Customer, Credit card, Register.</span></span>
<span data-ttu-id="11b6f-120">Hitelkártya hozzáadása egy értékesítési rendeléshez</span><span class="sxs-lookup"><span data-stu-id="11b6f-120">Adding a credit card to a sales order</span></span>
-------------------------------------

<span data-ttu-id="11b6f-121">Hitelkártyát hozzáadhat egy értékesítési rendeléshez egy hitelkártya kiválasztásával a hitelkártya-keresőben az Ár és engedmények gyorslapon, az Értékesítési rendelés lapon.</span><span class="sxs-lookup"><span data-stu-id="11b6f-121">You can add a credit card to a sales order by selecting a credit card in the credit card lookup on the Price and discounts FastTab on the Sales order page.</span></span> <span data-ttu-id="11b6f-122">Az engedélyezési folyamat elindításához a Műveleti ablakban a Kezelés fülön válassza ki a Hitelkártyát és az Engedélyezést.</span><span class="sxs-lookup"><span data-stu-id="11b6f-122">To start the authorization process, on the Action Pane, on the Manage tab, select Credit card and Authorize.</span></span>
<span data-ttu-id="11b6f-123">Hitelkártya engedélyezése</span><span class="sxs-lookup"><span data-stu-id="11b6f-123">Authorizing a credit card</span></span>
-------------------------

<span data-ttu-id="11b6f-124">Amikor megtörténik a hitelkártya engedélyezése, a kártyaszám és a kártyabirtokos nevének ellenőrzése megy végbe, valamint megerősítést nyer a rendelkezésre álló hitelegyenleg.</span><span class="sxs-lookup"><span data-stu-id="11b6f-124">When a credit card is authorized, the card number and cardholder's name are verified, and the available credit balance is confirmed.</span></span> <span data-ttu-id="11b6f-125">Másik lehetőségként a kártyaellenőrző kód és a kártyatulajdonos címének ellenőrzése megy végbe.</span><span class="sxs-lookup"><span data-stu-id="11b6f-125">Optionally, the card verification value and the cardholder’s address are verified.</span></span> <span data-ttu-id="11b6f-126">Ezt követően a vevő rendelkezésre álló hitelegyenlege a számla összegével csökken.</span><span class="sxs-lookup"><span data-stu-id="11b6f-126">The customer's available credit balance is then reduced by the amount of the invoice.</span></span> <span data-ttu-id="11b6f-127">A fizetési szolgáltatás információt küld arról, hogy a hitelkártyát elfogadja-e, vagy elutasítja.</span><span class="sxs-lookup"><span data-stu-id="11b6f-127">The payment service sends information that the credit card has been approved or declined.</span></span> <span data-ttu-id="11b6f-128">Az értékesítési rendelés számlázásakor a hitelkártyán végbemegy a számlaösszeg terhelése (rögzítése).</span><span class="sxs-lookup"><span data-stu-id="11b6f-128">When the sales order is invoiced, the credit card is charged (captured) for the invoice amount.</span></span>

### <a name="card-verification-value"></a><span data-ttu-id="11b6f-129">Kártyaellenőrző kód</span><span class="sxs-lookup"><span data-stu-id="11b6f-129">Card verification value</span></span>

<span data-ttu-id="11b6f-130">Igényelheti a kártyaellenőrző kódot, amelyre néha a kártya biztonsági kódjaként utalnak.</span><span class="sxs-lookup"><span data-stu-id="11b6f-130">You can require the card verification value, which is sometimes referred to as the card's security code.</span></span> <span data-ttu-id="11b6f-131">Az American Express esetében ez egy négyjegyű érték.</span><span class="sxs-lookup"><span data-stu-id="11b6f-131">For American Express, this is a four-digit value.</span></span> <span data-ttu-id="11b6f-132">A Discover, MasterCard és Visa esetében ez egy háromjegyű érték.</span><span class="sxs-lookup"><span data-stu-id="11b6f-132">For Discover, MasterCard, and Visa, it is a three-digit value.</span></span>

### <a name="address-verification"></a><span data-ttu-id="11b6f-133">Cím ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="11b6f-133">Address verification</span></span>

<span data-ttu-id="11b6f-134">A kifizetési szolgáltatóhoz mindig beérkezik a címadatok ellenőrzése.</span><span class="sxs-lookup"><span data-stu-id="11b6f-134">Address verification information is always sent to the payment provider.</span></span> <span data-ttu-id="11b6f-135">Megadhatja, hogy mennyi információra szükség egy tranzakció elfogadásához.</span><span class="sxs-lookup"><span data-stu-id="11b6f-135">You can decide how much information is required for a transaction to be accepted.</span></span> <span data-ttu-id="11b6f-136">Ügyeljen arra, hogy egyeztesse a szolgáltatóval, hogy elfogadja-e ezt az információt.</span><span class="sxs-lookup"><span data-stu-id="11b6f-136">Be sure to check with your provider to determine whether it accepts this information.</span></span> <span data-ttu-id="11b6f-137">Az alábbiakban láthatók a címellenőrzés lehetőségei:</span><span class="sxs-lookup"><span data-stu-id="11b6f-137">Here are the options for address verification:</span></span>
-   <span data-ttu-id="11b6f-138">**Tranzakció mindenkori elfogadása** – Elfogadja a tranzakciót, függetlenül a címellenőrzés eredményétől.</span><span class="sxs-lookup"><span data-stu-id="11b6f-138">**Always accept transaction** – Accept the transaction, regardless of address verification results.</span></span>
-   <span data-ttu-id="11b6f-139">**Számlatulajdonos** – A tranzakcióból a kártyatulajdonos nevének összehasonlítása a hitelkártyát feldolgozó vállalat adataival.</span><span class="sxs-lookup"><span data-stu-id="11b6f-139">**Account holder** – Compare the cardholder's name from the transaction with the credit card company’s information.</span></span>
-   <span data-ttu-id="11b6f-140">**Számlázási cím** – A tranzakcióból a kártyatulajdonos nevének és számlázási címének összehasonlítása a hitelkártyát feldolgozó vállalat adataival.</span><span class="sxs-lookup"><span data-stu-id="11b6f-140">**Billing address** – Compare the cardholder's name and billing address from the transaction with the credit card company’s information.</span></span>
-   <span data-ttu-id="11b6f-141">**Számlázási cím irányítószáma** – A tranzakcióból a kártyatulajdonos nevének, számlázási címének és számlázási címe irányítószámának összehasonlítása a hitelkártyát feldolgozó vállalat adataival.</span><span class="sxs-lookup"><span data-stu-id="11b6f-141">**Billing postal code** – Compare the cardholder's name, billing address, and postal code from the transaction with the credit card company’s information.</span></span>

## <a name="data-support"></a><span data-ttu-id="11b6f-142">Adattámogatás</span><span class="sxs-lookup"><span data-stu-id="11b6f-142">Data support</span></span>
<span data-ttu-id="11b6f-143">Minden egyes támogatott hitelkártyatípushoz be lehet állítani az adattámogatás szintjét.</span><span class="sxs-lookup"><span data-stu-id="11b6f-143">For each credit card type that is supported, you can specify the level of data support.</span></span> <span data-ttu-id="11b6f-144">A szint szabályozza, hogy mennyi, a tranzakcióval kapcsolatos információ kerül át a fizetési szolgáltatáshoz.</span><span class="sxs-lookup"><span data-stu-id="11b6f-144">The level controls how much information about a transaction is transferred to the payment service.</span></span> <span data-ttu-id="11b6f-145">Ügyeljen arra, hogy egyeztesse a szolgáltatóval, hogy meg tudja-e adni ezt az információt.</span><span class="sxs-lookup"><span data-stu-id="11b6f-145">Be sure to check with your provider to determine whether it can provide this information.</span></span> <span data-ttu-id="11b6f-146">Az adattámogatás szintjének lehetőségei a következők:</span><span class="sxs-lookup"><span data-stu-id="11b6f-146">Here are the options for the level of data support:</span></span>
-   <span data-ttu-id="11b6f-147">**1. szint** – A tranzakció dátumnak, összegének és leírásának átadása.</span><span class="sxs-lookup"><span data-stu-id="11b6f-147">**Level 1** – Transfer the transaction date, transaction amount, and description.</span></span>
-   <span data-ttu-id="11b6f-148">**2. szint** – Az összes 1. szintű információ, valamint a szállítási és kereskedői címek, és az adóval kapcsolatos adatok átadása.</span><span class="sxs-lookup"><span data-stu-id="11b6f-148">**Level 2** – Transfer all Level 1 information, plus the shipping and merchant addresses, and tax information.</span></span>
-   <span data-ttu-id="11b6f-149">**3. szint** – Az összes 2. szintű információ, valamint a rendelési sor információinak átadása.</span><span class="sxs-lookup"><span data-stu-id="11b6f-149">**Level 3** – Transfer all Level 2 information, plus order line information.</span></span>

## <a name="partial-payments"></a><span data-ttu-id="11b6f-150">Részfizetések</span><span class="sxs-lookup"><span data-stu-id="11b6f-150">Partial payments</span></span>
<span data-ttu-id="11b6f-151">Ha egy rendelés egy részét szállítja ki, a rendelés részleges összege kerül rögzítésre, és az engedélyezés, amely a teljes rendelés összegére vonatkozott, lezárul.</span><span class="sxs-lookup"><span data-stu-id="11b6f-151">If you ship part of an order, the amount of the partial order is captured, and the authorization, which was for the amount of the whole order, is closed.</span></span> <span data-ttu-id="11b6f-152">A fennmaradó összeghez a még nem szállított rendelésről egy új engedély lesz leadva.</span><span class="sxs-lookup"><span data-stu-id="11b6f-152">A new authorization is then submitted for the remaining amount of the order that hasn't been shipped.</span></span>

## <a name="voiding-an-authorization"></a><span data-ttu-id="11b6f-153">Engedélyezés érvénytelenítése </span><span class="sxs-lookup"><span data-stu-id="11b6f-153">Voiding an authorization</span></span>
<span data-ttu-id="11b6f-154">A hitelkártya-engedélyezés érvénytelenítéséhez módosíthatja a fizetési módot egy másik módra, amelyhez nem tartozik Hitelkártya-típus.</span><span class="sxs-lookup"><span data-stu-id="11b6f-154">To void a credit card authorization, you can change the method of payment to another method that doesn't have a type of Credit card.</span></span>





