---
title: Kifizetések létrehozása beszedési megbízási felhatalmazásokkal rendelkező vevő számára
description: Ez a folyamat bemutatja, hogyan hozhat létre egy ISO20022 állandó átutalásos kifizetési fájlt olyan vevőhöz, akihez beszedési megbízás van beállítva, és van egy kifizetendő számlája.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustFreeInvoice, CustTableLookup, CustPostInvoiceJob, LedgerJournalTable, LedgerJournalTransCustPaym, SysQueryForm, CustPaymProposalEdit, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 65da5f9fe55d11e7ccfb9bd86f9b37181e0adf41
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5260749"
---
# <a name="create-payments-for-a-customer-who-have-direct-debit-mandates"></a><span data-ttu-id="39f78-103">Kifizetések létrehozása beszedési megbízási felhatalmazásokkal rendelkező vevő számára</span><span class="sxs-lookup"><span data-stu-id="39f78-103">Create payments for a customer who have direct debit mandates</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="39f78-104">Ez a folyamat bemutatja, hogyan hozhat létre egy ISO20022 állandó átutalásos kifizetési fájlt olyan vevőhöz, akihez beszedési megbízás van beállítva, és van egy kifizetendő számlája.</span><span class="sxs-lookup"><span data-stu-id="39f78-104">This procedure shows how to generate an ISO20022 direct debit payment file for a customer who has direct debit configured and an invoice to be paid.</span></span> <span data-ttu-id="39f78-105">Számla létrehozása és könyvelése nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="39f78-105">Creating and posting an invoice is optional.</span></span> <span data-ttu-id="39f78-106">A vevői előlegfizetés támogatására kifizetendő számla helyett választhat naplóból beszedési megbízást a kifizetési fájl létrehozása előtt.</span><span class="sxs-lookup"><span data-stu-id="39f78-106">Instead of having an invoice to be paid you can select a mandate in a journal prior to generating a payment file, to support a customer prepayment scenario.</span></span>



<span data-ttu-id="39f78-107">Ez az eljárás az DEMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="39f78-107">The demo data company used to create this procedure is DEMF.</span></span>



<span data-ttu-id="39f78-108">Ez az ötödik a hat olyan feladat közül, amelyek vevői fizetési folyamat elektronikus jelentési konfigurációk segítségével történő végrehajtásának folyamatát mutatják be.</span><span class="sxs-lookup"><span data-stu-id="39f78-108">This is the fifth of five procedures that demonstrate the customer payment process using electronic reporting configurations.</span></span> <span data-ttu-id="39f78-109">A feladat végrehajtása előtt el kell végeznie a korábbi feladatokat.</span><span class="sxs-lookup"><span data-stu-id="39f78-109">Before you can complete this task, you must complete the earlier tasks.</span></span> <span data-ttu-id="39f78-110">Először importálnia kell a vevői kifizetési elektronikus jelentéskészítési konfigurációkat, konfigurálnia kell a fizetési módokat, és be kell állítania a cég- és vevőadatokat.</span><span class="sxs-lookup"><span data-stu-id="39f78-110">You must first import customer payment electronic reporting configurations, configure method of payments, and set up your company and customer information.</span></span> 


## <a name="post-a-free-text-invoice-with-direct-debit-information"></a><span data-ttu-id="39f78-111">Szabadszöveges számla feladása beszedési megbízási információkkal</span><span class="sxs-lookup"><span data-stu-id="39f78-111">Post a free text invoice with direct debit information</span></span>
1. <span data-ttu-id="39f78-112">Ugorjon a Kinnlévőségek > Számlák > Kizárólag szabadszöveges számlák pontra.</span><span class="sxs-lookup"><span data-stu-id="39f78-112">Go to Accounts receivable > Invoices > All free text invoices.</span></span>
2. <span data-ttu-id="39f78-113">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="39f78-113">Click New.</span></span>
3. <span data-ttu-id="39f78-114">A Vevőszámla mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="39f78-114">In the Customer account field, enter or select a value.</span></span>
    * <span data-ttu-id="39f78-115">Válassza ki például a DE-010-et.</span><span class="sxs-lookup"><span data-stu-id="39f78-115">For example, select DE-010.</span></span>  
4. <span data-ttu-id="39f78-116">A Fizetési mód mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="39f78-116">In the Method of payment field, enter or select a value.</span></span>
    * <span data-ttu-id="39f78-117">Például:</span><span class="sxs-lookup"><span data-stu-id="39f78-117">For example.</span></span> <span data-ttu-id="39f78-118">válassza az Elektronikus lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="39f78-118">select Electronic.</span></span>  
5. <span data-ttu-id="39f78-119">A Beszedési megbízási felhatalmazás azonosítója mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="39f78-119">In the Direct debit mandate ID field, enter or select a value.</span></span>
6. <span data-ttu-id="39f78-120">Kattintson az Új sor hozzáadására.</span><span class="sxs-lookup"><span data-stu-id="39f78-120">Click Add line.</span></span>
7. <span data-ttu-id="39f78-121">Írjon egy értéket a „Leírás” mezőbe.</span><span class="sxs-lookup"><span data-stu-id="39f78-121">In the Description field, type a value.</span></span>
8. <span data-ttu-id="39f78-122">A Fő számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="39f78-122">In the Main account field, specify the desired values.</span></span>
9. <span data-ttu-id="39f78-123">Adjon meg egy számot az Egységár mezőben.</span><span class="sxs-lookup"><span data-stu-id="39f78-123">In the Unit price field, enter a number.</span></span>
10. <span data-ttu-id="39f78-124">Kattintson a Feladás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="39f78-124">Click Post.</span></span>
11. <span data-ttu-id="39f78-125">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="39f78-125">Click OK.</span></span>

## <a name="create-a-payment"></a><span data-ttu-id="39f78-126">Fizetés létrehozása</span><span class="sxs-lookup"><span data-stu-id="39f78-126">Create a payment</span></span>
1. <span data-ttu-id="39f78-127">Ugorjon a Kinnlevőségek > Fizetési beállítás > Fizetési napló pontra.</span><span class="sxs-lookup"><span data-stu-id="39f78-127">Go to Accounts receivable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="39f78-128">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="39f78-128">Click New.</span></span>
3. <span data-ttu-id="39f78-129">A Név mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="39f78-129">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="39f78-130">Kattintson a Sorok pontra.</span><span class="sxs-lookup"><span data-stu-id="39f78-130">Click Lines.</span></span>
5. <span data-ttu-id="39f78-131">Kattintson a Fizetési javaslat lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="39f78-131">Click Payment proposal.</span></span>
6. <span data-ttu-id="39f78-132">Kattintson a Fizetési javaslat létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="39f78-132">Click Create payment proposal.</span></span>
7. <span data-ttu-id="39f78-133">Bontsa ki a Szerepeltetni kívánt rekordok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="39f78-133">Expand the Records to include section.</span></span>
8. <span data-ttu-id="39f78-134">Kattintson a Szűrő parancsra.</span><span class="sxs-lookup"><span data-stu-id="39f78-134">Click Filter.</span></span>
9. <span data-ttu-id="39f78-135">A listán jelölje ki a Vevői tranzakciók tábla sorát és a Fizetési mód mezőt.</span><span class="sxs-lookup"><span data-stu-id="39f78-135">In the list, select the row for the Customer transactions table and the Method of payment field.</span></span>
    * <span data-ttu-id="39f78-136">A fizetendő vevői tranzakciók kiválasztásához bármilyen szempontot alkalmazhat.</span><span class="sxs-lookup"><span data-stu-id="39f78-136">You can apply any criteria for selecting customer transactions to pay.</span></span> <span data-ttu-id="39f78-137">Ebben a példában használja az Elektronikus fizetési módot a tranzakciók szűrésére.</span><span class="sxs-lookup"><span data-stu-id="39f78-137">For this example, use Electronic as a method of payment to filter transactions.</span></span>  
10. <span data-ttu-id="39f78-138">A Feltétel mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="39f78-138">In the Criteria field, enter or select a value.</span></span>
11. <span data-ttu-id="39f78-139">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="39f78-139">Click OK.</span></span>
12. <span data-ttu-id="39f78-140">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="39f78-140">Click OK.</span></span>
13. <span data-ttu-id="39f78-141">Kattintson a Fizetések létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="39f78-141">Click Create payments.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]