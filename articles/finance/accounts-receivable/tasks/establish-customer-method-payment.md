---
title: Vevői fizetési mód kialakítása
description: Ez a témakör ismerteti a vevők a fizetési mód létrehozását ügyfélkifizetésekhez
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/31/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPaymMode, BankAccountTableLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 22680a3033c1518735eb9edb4c6f22f310509aba
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2188809"
---
# <a name="establish-customer-method-of-payment"></a><span data-ttu-id="90031-103">Vevői fizetési mód kialakítása</span><span class="sxs-lookup"><span data-stu-id="90031-103">Establish customer method of payment</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="90031-104">Ez a témakör ismerteti a vevők a fizetési mód létrehozását ügyfélkifizetésekhez</span><span class="sxs-lookup"><span data-stu-id="90031-104">This topic explains how to create a method of payment for customer payments.</span></span> <span data-ttu-id="90031-105">Ez a feladat az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="90031-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="90031-106">A navigációs ablaktáblán ugorjon a **Modulok > Követelések és beszedések > Fizetés beállítása > Fizetési módok** elemre.</span><span class="sxs-lookup"><span data-stu-id="90031-106">In the navigation pane, go to **Modules > Accounts receivable > Payments setup > Methods of payment**.</span></span>
2. <span data-ttu-id="90031-107">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="90031-107">Select **New**.</span></span>
3. <span data-ttu-id="90031-108">A **Fizetési mód** mezőben adjon meg egy azonosítót a kifizetés módjához.</span><span class="sxs-lookup"><span data-stu-id="90031-108">In the **Method of payment** field, enter an ID for the method of payment.</span></span> <span data-ttu-id="90031-109">A Fizetési mód azonosítója feltüntetésre kerül a számlákon és a kifizetéseken, így gondoskodjon arról, hogy világosan rögzíti a fizetés jellegét, illetve a bankszámlát.</span><span class="sxs-lookup"><span data-stu-id="90031-109">The Method of payment ID is shown on invoices and payments, so make it descriptive enough to understand what type of payment is being recorded, and for what bank account.</span></span>  
4. <span data-ttu-id="90031-110">Adjon meg egy leírást a **Leírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="90031-110">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="90031-111">Válassza ki a kifizetés feladásához szükséges kifizetési állapotot.</span><span class="sxs-lookup"><span data-stu-id="90031-111">Select what payment status is required in order for payments to be posted.</span></span> <span data-ttu-id="90031-112">Vevői kifizetés létrehozásakor az csak akkor adható fel, ha a fizetési állapot megegyezik az Ön által itt megjelölt fizetési állapottal.</span><span class="sxs-lookup"><span data-stu-id="90031-112">When creating a customer payment, it can only be posted when the payment status matches the payment status you define here.</span></span>  
6. <span data-ttu-id="90031-113">Válassza ki az ügyfélkifizetések létrehozásának módját a számlákhoz.</span><span class="sxs-lookup"><span data-stu-id="90031-113">Select how customers payments should be created for invoices.</span></span> <span data-ttu-id="90031-114">Ezt a lehetőség kizárólag fizetési javaslat futtatása esetén kerül alkalmazásra.</span><span class="sxs-lookup"><span data-stu-id="90031-114">This option is only used when running a payment proposal.</span></span> <span data-ttu-id="90031-115">Fizetési javaslat akkor használható fel vevői kifizetésekhez, ha állandó átutalást alkalmaz, és a pénzeszközöket a vevő bankszámláiról emeli le.</span><span class="sxs-lookup"><span data-stu-id="90031-115">A payment proposal could be used for customer payments when doing direct debits, and pulling the funds from the customers' bank accounts.</span></span>  
7. <span data-ttu-id="90031-116">Jelölje ki a kifizetés típusát.</span><span class="sxs-lookup"><span data-stu-id="90031-116">Select the type of payment.</span></span> <span data-ttu-id="90031-117">A fizetéstípus segítségével tudja meghatározni, hogy a fizetés kapcsán sor kerül-e valamilyen ellenőrzésre.</span><span class="sxs-lookup"><span data-stu-id="90031-117">The payment type will help determine whether some validation will occur or not on the payment.</span></span>  
8. <span data-ttu-id="90031-118">Válassza ki, milyen számlatípusokra adhatnak fel kifizetést.</span><span class="sxs-lookup"><span data-stu-id="90031-118">Select what account type payments will post to.</span></span> <span data-ttu-id="90031-119">Általában a bank volna kijelölve ennél a lehetőségnél.</span><span class="sxs-lookup"><span data-stu-id="90031-119">Typically, Bank would be selected for this option.</span></span>  
9. <span data-ttu-id="90031-120">Válassza ki, melyik bankszámlára kerüljön rögzítésre ez a kifizetés.</span><span class="sxs-lookup"><span data-stu-id="90031-120">Select the bank account into which this payment will be recorded.</span></span>
10. <span data-ttu-id="90031-121">Adja meg a banki tranzakció típusát a bankja által használt fizetési típus azonosításához.</span><span class="sxs-lookup"><span data-stu-id="90031-121">Enter the Bank transaction type to identify the type of payment used by your bank.</span></span> <span data-ttu-id="90031-122">A banki tranzakciótípus a banki egyeztetési folyamat során használható fel, az egyeztetés megkönnyítése érdekében.</span><span class="sxs-lookup"><span data-stu-id="90031-122">The bank transaction type is used during the bank reconciliation process, and can make reconciliation easier.</span></span>  
11. <span data-ttu-id="90031-123">Válassza ki, hogy ez a kifizetés ideiglenesen felad-e áthidaló számlára.</span><span class="sxs-lookup"><span data-stu-id="90031-123">Select whether this payment will temporarily post to a bridging account.</span></span> <span data-ttu-id="90031-124">Ha szeretné kipróbálni, hogy mennyi egy kifizetés banki átfutása, használja az Áthidaló funkciót.</span><span class="sxs-lookup"><span data-stu-id="90031-124">If you want to try the float time for a payment to clear the bank, use the Bridging functionality.</span></span> <span data-ttu-id="90031-125">A kifizetés így ideiglenesen, a banki átfutás idejére, a Főkönyvi számlára kerül feladásra, mely időt követően a kifizetés az Ön által itt megjelölt bankszámlára kerül.</span><span class="sxs-lookup"><span data-stu-id="90031-125">The payment will temporarily post to a Ledger account until it clears the bank, at which time the payment will move to the bank account you defined here.</span></span>  
12. <span data-ttu-id="90031-126">Adja meg az áthidaló feladáshoz használt fő számlát.</span><span class="sxs-lookup"><span data-stu-id="90031-126">Enter the main account used for the bridging posting.</span></span> <span data-ttu-id="90031-127">Ez az a fő számla, amelyre - áthidalás esetén - a rendszer ideiglenesen feladja a kifizetést.</span><span class="sxs-lookup"><span data-stu-id="90031-127">This is the main account to which the payment will temporarily post if using bridging.</span></span>  
13. <span data-ttu-id="90031-128">A **Fájlformátum** lap használatával adja meg az elektronikus kifizetésekhez való beállítást.</span><span class="sxs-lookup"><span data-stu-id="90031-128">Use the **File format** tab to define setting for electronic payments.</span></span>
14. <span data-ttu-id="90031-129">A **Fizetés ellenőrzése** lapon határozza meg a kötelező mezőket.</span><span class="sxs-lookup"><span data-stu-id="90031-129">Use the **Payment control** tab to define fields that are mandatory.</span></span> <span data-ttu-id="90031-130">Ha például előírja, hogy az összes ilyen fizetési módú kifizetés letétbe kerüljön, úgy válassza ezt a lehetőséget a lapon.</span><span class="sxs-lookup"><span data-stu-id="90031-130">For example, if you require all payments with this method of payment to be deposited, you can choose that option on this tab.</span></span>  
15. <span data-ttu-id="90031-131">A **Fizetési attribútumok** lapján határozza meg, mely fizetési attribútumokat kívánja használni ehhez a fizetési módhoz.</span><span class="sxs-lookup"><span data-stu-id="90031-131">Use the **Payment atrributes** tab to define which payment attributes you want to use for this method of payment.</span></span>
16. <span data-ttu-id="90031-132">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="90031-132">Select **Save**.</span></span>

