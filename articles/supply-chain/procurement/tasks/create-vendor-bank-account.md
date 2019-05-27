---
title: Szállítói bankszámla létrehozása
description: Ez az eljárás bemutatja a szállítóhoz tartozó bankszámla létrehozásának módját.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, VendBankAccounts, LogisticsPostalAddressSingle
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: deb3587667ac13b95617ec219995bfef931df00c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1546133"
---
# <a name="create-a-vendor-bank-account"></a><span data-ttu-id="0e91f-103">Szállítói bankszámla létrehozása</span><span class="sxs-lookup"><span data-stu-id="0e91f-103">Create a vendor bank account</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0e91f-104">Ez az eljárás bemutatja a szállítóhoz tartozó bankszámla létrehozásának módját.</span><span class="sxs-lookup"><span data-stu-id="0e91f-104">This procedure shows you how to create a bank account for a vendor.</span></span> <span data-ttu-id="0e91f-105">Az USMF bemutatócég adataiban használhatja ezt az eljárást.</span><span class="sxs-lookup"><span data-stu-id="0e91f-105">You can use this procedure in demo data company USMF.</span></span>

1. <span data-ttu-id="0e91f-106">Ugrás a Beszerzés és forrás > Beszállítók > Minden szállító pontra.</span><span class="sxs-lookup"><span data-stu-id="0e91f-106">Go to Procurement and sourcing > Vendors > All vendors.</span></span>
2. <span data-ttu-id="0e91f-107">Válassza ki azt a szállítót, akihez létre szeretne hozni bankszámlát, majd kattintson a Szállítói számla azonosítón található hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="0e91f-107">Select the vendor that you want to create a bank account for, and then click the link on the Vendor account ID.</span></span>
3. <span data-ttu-id="0e91f-108">A Művelet ablaktáblában kattintson a Szállító elemre.</span><span class="sxs-lookup"><span data-stu-id="0e91f-108">On the Action Pane, click Vendor.</span></span>
4. <span data-ttu-id="0e91f-109">Kattintson a Bankszámlák lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0e91f-109">Click Bank accounts.</span></span>
5. <span data-ttu-id="0e91f-110">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0e91f-110">Click New.</span></span>
6. <span data-ttu-id="0e91f-111">A Bankszámla mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="0e91f-111">In the Bank account field, type a value.</span></span>
    * <span data-ttu-id="0e91f-112">Ez az azonosító a szállítói rekordban szereplő bankszámla azonosítására szolgál.</span><span class="sxs-lookup"><span data-stu-id="0e91f-112">This ID will be used to identify the bank account on the vendor record.</span></span>  
7. <span data-ttu-id="0e91f-113">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="0e91f-113">In the Name field, type a value.</span></span>
8. <span data-ttu-id="0e91f-114">A Bankcsoportok mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="0e91f-114">In the Bank groups field, enter or select a value.</span></span>
9. <span data-ttu-id="0e91f-115">Válasszon ki egy beállítást az Útvonalszám típusa mezőben.</span><span class="sxs-lookup"><span data-stu-id="0e91f-115">In the Routing number type field, select an option.</span></span>
    * <span data-ttu-id="0e91f-116">Ez a nemzetközi fizetésekhez használt útvonaltervezés típusa.</span><span class="sxs-lookup"><span data-stu-id="0e91f-116">This is the type of routing number that’s used for international payments.</span></span>  
10. <span data-ttu-id="0e91f-117">A Bankszámlaszám mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="0e91f-117">In the Bank account number field, type a value.</span></span>
11. <span data-ttu-id="0e91f-118">A SWIFT kód mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="0e91f-118">In the SWIFT code field, type a value.</span></span>
12. <span data-ttu-id="0e91f-119">Az IBAN mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="0e91f-119">In the IBAN field, type a value.</span></span>
    * <span data-ttu-id="0e91f-120">Megfelelő formátumban kell megadni az IBAN számot.</span><span class="sxs-lookup"><span data-stu-id="0e91f-120">The IBAN number must be in the correct format.</span></span> <span data-ttu-id="0e91f-121">Például, a következő számot használhatja: DE89370400440532013000.</span><span class="sxs-lookup"><span data-stu-id="0e91f-121">For example, you could use DE89370400440532013000.</span></span>  
    * <span data-ttu-id="0e91f-122">A bankszámla állapota aktív, ha a rendszer elérte az Aktivitás dátumát, és nem lépte túl a Lejárati dátumot.</span><span class="sxs-lookup"><span data-stu-id="0e91f-122">The status of the bank account is Active if the Active date has been reached, and the Expiration date has not been exceeded.</span></span> <span data-ttu-id="0e91f-123">Ez akkor is aktív, ha az Aktiválás dátuma és a Lejárati dátum mező egyaránt üres.</span><span class="sxs-lookup"><span data-stu-id="0e91f-123">It’s also active if both the Active date and Expiration date fields are blank.</span></span> <span data-ttu-id="0e91f-124">Ha az Aktiválás dátuma és a Lejárati dátum mezőben szereplő dátumok egyaránt jövőbeli dátumok, akkor nincs lehetőség elektronikus fizetésre.</span><span class="sxs-lookup"><span data-stu-id="0e91f-124">If the dates in both the Active date and Expiration date fields are in the future electronic payments are not available.</span></span> <span data-ttu-id="0e91f-125">A bankszámla egyébként aktív, és az egyéb fizetési típusok alkalmazhatók.</span><span class="sxs-lookup"><span data-stu-id="0e91f-125">Other payment types are available and the bank account is active.</span></span>  
13. <span data-ttu-id="0e91f-126">Bontsa ki a Beállítások szakaszt.</span><span class="sxs-lookup"><span data-stu-id="0e91f-126">Expand the Setup section.</span></span>
14. <span data-ttu-id="0e91f-127">Adjon meg egy értéket a Szöveges kód mezőben.</span><span class="sxs-lookup"><span data-stu-id="0e91f-127">In the Text code field, type a value.</span></span>
    * <span data-ttu-id="0e91f-128">Ez a mező egy olyan kódot határoz meg, amely az átvevő banki kivonatán fog megjelenni.</span><span class="sxs-lookup"><span data-stu-id="0e91f-128">This field specifies a code that will appear on the bank statement of the recipient.</span></span>  
15. <span data-ttu-id="0e91f-129">Adjon meg egy értéket az Üzenet a banknak mezőben.</span><span class="sxs-lookup"><span data-stu-id="0e91f-129">In the Message to bank field, type a value.</span></span>
16. <span data-ttu-id="0e91f-130">Adjon meg egy értéket az Árfolyam-hivatkozás mezőben.</span><span class="sxs-lookup"><span data-stu-id="0e91f-130">In the Exchange reference field, type a value.</span></span>
    * <span data-ttu-id="0e91f-131">Ez az esetleges előzetes vagy a rögzített átváltási árfolyam hivatkozási száma.</span><span class="sxs-lookup"><span data-stu-id="0e91f-131">This is the reference number for any forward-term or fixed-term rate of exchange.</span></span>  
17. <span data-ttu-id="0e91f-132">A Pénznem mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="0e91f-132">In the Currency field, enter or select a value.</span></span>
    * <span data-ttu-id="0e91f-133">Az ellenőrző tranzakciók elküldésekor, ez a szakasz egy áttekintést nyújt a (folyamatban lévő vagy engedélyezett) állapotukról.</span><span class="sxs-lookup"><span data-stu-id="0e91f-133">When prenotes are issued, this section provides an overview of their status (pending or approved).</span></span>  
18. <span data-ttu-id="0e91f-134">Bontsa ki a Cím szakaszt.</span><span class="sxs-lookup"><span data-stu-id="0e91f-134">Expand the Address section.</span></span>
19. <span data-ttu-id="0e91f-135">Bontsa ki az Ellenőrző tranzakciók szakaszt.</span><span class="sxs-lookup"><span data-stu-id="0e91f-135">Expand the Prenotes section.</span></span>
20. <span data-ttu-id="0e91f-136">Bontsa ki vagy csukja össze a Kapcsolattartási adatok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="0e91f-136">Expand the Contact information section.</span></span>
21. <span data-ttu-id="0e91f-137">Írjon be egy értéket a Telefon mezőbe.</span><span class="sxs-lookup"><span data-stu-id="0e91f-137">In the Telephone field, type a value.</span></span>
22. <span data-ttu-id="0e91f-138">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="0e91f-138">Close the page.</span></span>
23. <span data-ttu-id="0e91f-139">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0e91f-139">Click Edit.</span></span>
24. <span data-ttu-id="0e91f-140">Bontsa ki a Kifizetés szakaszt.</span><span class="sxs-lookup"><span data-stu-id="0e91f-140">Expand the Payment section.</span></span>
25. <span data-ttu-id="0e91f-141">Válassza ki az újonnan létrehozott számlát a Bankszámla mezőben.</span><span class="sxs-lookup"><span data-stu-id="0e91f-141">In the Bank  account field, select the account that you’ve just created.</span></span>
26. <span data-ttu-id="0e91f-142">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="0e91f-142">Click Save.</span></span>
    * <span data-ttu-id="0e91f-143">A cím örökölhető a banki csoporttól, ha meg van határozva egy cím, illetve itt, hozzá is adhatja azt.</span><span class="sxs-lookup"><span data-stu-id="0e91f-143">The address may be inherited from the bank group, if one is specified, or you can add it here.</span></span>  

