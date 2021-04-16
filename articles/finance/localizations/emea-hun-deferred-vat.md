---
title: Halasztott áfa számítása
description: Ez a témakör azt mutatja be, hogyan lehet beállítani a halasztott áfaszámításokat és a magyarországi áfafeladáshoz.
author: anasyash
ms.date: 09/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetParameters
audience: Application User
ms.reviewer: kfend
ms.custom: 264684
ms.search.region: Hungary
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: 10.0.0
ms.openlocfilehash: 54358a8e94712955c0cb291bfb54940272456bea
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815019"
---
# <a name="deferred-sales-tax-calculations"></a><span data-ttu-id="b9411-103">Halasztott áfa számítása</span><span class="sxs-lookup"><span data-stu-id="b9411-103">Deferred sales tax calculations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b9411-104">Magyarországon az általános forgalmi adót (áfa) folyamatos szolgáltatásteljesítés, például bérlés, lízingelés, konzultáció és fűtés során az esedékesség napján kell rögzíteni és jelenteni.</span><span class="sxs-lookup"><span data-stu-id="b9411-104">In Hungary, value-added tax (VAT) on the continuous delivery of services, such as renting, leasing, consulting, and heating, must be recorded and reported on the due date.</span></span> <span data-ttu-id="b9411-105">Ez a funkció lehetővé teszi az áfa összegének főkönyvi feladásának a halasztott fizetendő áfa és halasztott bejövő áfa számlákra.</span><span class="sxs-lookup"><span data-stu-id="b9411-105">This functionality allows you to process the general ledger postings for VAT amounts to the deferred VAT payable and deferred VAT receivable accounts.</span></span> <span data-ttu-id="b9411-106">A számla esedékességi dátumán is átviheti az összegeket a hagyományos forgalmiadó-számlákra.</span><span class="sxs-lookup"><span data-stu-id="b9411-106">You can also transfer amounts to regular sales tax accounts on the due date of the invoice.</span></span>

<span data-ttu-id="b9411-107">A halasztott adófeladások a következő dokumentumtípusok és naplók esetén működnek:</span><span class="sxs-lookup"><span data-stu-id="b9411-107">Deferred tax postings work for the following document types and journals:</span></span>

- <span data-ttu-id="b9411-108">Értékesítési rendelés</span><span class="sxs-lookup"><span data-stu-id="b9411-108">Sales orders</span></span>
- <span data-ttu-id="b9411-109">Szabadszöveges számlák</span><span class="sxs-lookup"><span data-stu-id="b9411-109">Free text invoices</span></span>
- <span data-ttu-id="b9411-110">Beszerzési rendelések</span><span class="sxs-lookup"><span data-stu-id="b9411-110">Purchase orders</span></span>
- <span data-ttu-id="b9411-111">Számlanaplók</span><span class="sxs-lookup"><span data-stu-id="b9411-111">Invoice journals</span></span>
- <span data-ttu-id="b9411-112">Számlaregiszterek</span><span class="sxs-lookup"><span data-stu-id="b9411-112">Invoice registers</span></span>
- <span data-ttu-id="b9411-113">Számla-jóváhagyási naplók</span><span class="sxs-lookup"><span data-stu-id="b9411-113">Invoice approval journals</span></span>

<span data-ttu-id="b9411-114">Ha ez a funkció be van állítva, akkor a tranzakció feladása alkalmával létrejönnek a következő áfatranzakciók:</span><span class="sxs-lookup"><span data-stu-id="b9411-114">When this feature is configured, the following sales tax transactions are created when the transaction is posted:</span></span>

- <span data-ttu-id="b9411-115">Az áfa összege a feladás napján feladásra kerül a halasztott adó számlára.</span><span class="sxs-lookup"><span data-stu-id="b9411-115">The sales tax amount on the posting date is posted to the deferred tax account.</span></span>
- <span data-ttu-id="b9411-116">Az áfa összege az áfatételjegyzék napján visszaforgatásra kerül a halasztott adó számláról.</span><span class="sxs-lookup"><span data-stu-id="b9411-116">The sales tax amount on the date of the VAT register is reversed from the deferred tax account.</span></span>
- <span data-ttu-id="b9411-117">Az áfa összege az áfatételjegyzék napján feladásra kerül az alapértelmezett fizetendő áfa vagy levonható áfa számlára.</span><span class="sxs-lookup"><span data-stu-id="b9411-117">The sales tax amount on the date of the VAT register is posted to the default sales tax payable or sales tax receivable account.</span></span>

<span data-ttu-id="b9411-118">Szabad szöveges számlák és beszerzési rendelések esetén, ha a dokumentumsorok összegeit elosztják a pénzügyi dimenziók között, az ÁFA összegeket, csakúgy, mint a dokumentumsorok összegeit szintén el kell osztani.</span><span class="sxs-lookup"><span data-stu-id="b9411-118">For free text invoices and purchase orders, if the document line amounts are distributed among financial dimensions, the sale tax amounts are distributed the same as the document line amounts.</span></span>

## <a name="set-up-deferred-vat-posting"></a><span data-ttu-id="b9411-119">Halasztott áfafeladás beállítása</span><span class="sxs-lookup"><span data-stu-id="b9411-119">Set up deferred VAT posting</span></span> 

<span data-ttu-id="b9411-120">Megadhatja, hogy az áfa feladása halasztott áfaszámlára történjen.</span><span class="sxs-lookup"><span data-stu-id="b9411-120">You can specify that VAT is posted to a deferred VAT account.</span></span>

1. <span data-ttu-id="b9411-121">Ugorjon az **Adó** \> **Közvetett adók** \> **Áfa** \> **Áfacsoportok** pontra.</span><span class="sxs-lookup"><span data-stu-id="b9411-121">Go to **Tax** \> **Indirect taxes** \> **Sales tax** \> **Item sales tax groups**.</span></span>
2. <span data-ttu-id="b9411-122">A **Cikkáfacsoportok** oldalon jelölje be a **Halasztott áfa** jelölőnégyzetet, ha meg szeretné adni, hogy az áfa feladása halasztott áfaszámlára történjen.</span><span class="sxs-lookup"><span data-stu-id="b9411-122">On the **Item sales tax groups** page, select the **Deferred VAT** check box to specify that VAT is posted to a deferred VAT account.</span></span>

## <a name="set-up-ledger-accounts-for-deferred-vat-posting"></a><span data-ttu-id="b9411-123">Főkönyvi számlák beállítása áfafeladáshoz</span><span class="sxs-lookup"><span data-stu-id="b9411-123">Set up ledger accounts for deferred VAT posting</span></span>

<span data-ttu-id="b9411-124">A halasztott áfa feladása a főkönyvi számlákra vonatkozóan is megadható.</span><span class="sxs-lookup"><span data-stu-id="b9411-124">You can designate the deferred VAT posting on ledger accounts.</span></span>

1. <span data-ttu-id="b9411-125">Lépjen az **Adó \> Beállítás \> Áfa \> Főkönyvi feladási csoportok** elemre.</span><span class="sxs-lookup"><span data-stu-id="b9411-125">Go to **Tax \> Setup \> Sales tax \> Ledger posting groups**.</span></span>
2. <span data-ttu-id="b9411-126">A **Főkönyvi feladási csoportok** lapon válasszon ki egy főkönyvi feladási csoportot a listáról, és adja hozzá a következő adatokat.</span><span class="sxs-lookup"><span data-stu-id="b9411-126">On the **Ledger posting groups** page, select a ledger posting group from the list and add the following information.</span></span>

- <span data-ttu-id="b9411-127">**Halasztott áfa fizetendő** – Válassza ki a kijelölt főkönyvi feladási csoport halasztott áfaszámláját vagy adószámláját.</span><span class="sxs-lookup"><span data-stu-id="b9411-127">**Deferred VAT payable** - Select the deferred VAT account or tax debit account for the selected ledger posting group.</span></span>
- <span data-ttu-id="b9411-128">**Halasztott áfa visszaigényelhető** – Válassza ki a kijelölt főkönyvi feladási csoport halasztott áfaszámláját vagy adószámláját.</span><span class="sxs-lookup"><span data-stu-id="b9411-128">**Deferred VAT receivable** - Select the deferred VAT account or tax credit account for the selected ledger posting group.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]