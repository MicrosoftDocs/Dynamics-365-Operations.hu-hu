---
title: Fordított naplófeladás
description: Ez a témakör bemutatja azokat a funkciókat, amelyek lehetővé teszik a bizonylatok sztornírozását a bizonylati tranzakciólistáról vagy a pénzügyi naplókból.
author: MikeFalkner
manager: AnnBe
ms.date: 10/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTransVoucher, LedgerJournalTable
audience: Application User
ms.reviewer: roschloma
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 19f7ea540035a3bc9eba445c508cb6f29e4bd20f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5205002"
---
# <a name="reverse-journal-posting"></a><span data-ttu-id="4e8df-103">Naplófeladás sztornírozása</span><span class="sxs-lookup"><span data-stu-id="4e8df-103">Reverse journal posting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4e8df-104">Ez a témakör a Microsoft Dynamics 365 Finance egyik funkcióját mutatja be, amelyek lehetővé teszik a teljes napló sztornírozását, illetve egy vagy több bizonylat sztornírozását a bizonylati tranzakciólistáról, az eredettől függetlenül.</span><span class="sxs-lookup"><span data-stu-id="4e8df-104">This topic describes capabilities Microsoft Dynamics 365 Finance that allows you to reverse an entire journal, or reverse one or more vouchers from the voucher transaction list, regardless of their origin.</span></span> 

## <a name="reversing-journals"></a><span data-ttu-id="4e8df-105">Naplók sztornózása</span><span class="sxs-lookup"><span data-stu-id="4e8df-105">Reversing journals</span></span>

<span data-ttu-id="4e8df-106">A naplósorok egyenként is sztornírozhatók.</span><span class="sxs-lookup"><span data-stu-id="4e8df-106">You can reverse journal lines individually.</span></span> <span data-ttu-id="4e8df-107">A sztornírozási naplófeladással a teljes pénzügyi naplót is sztornírozhatja.</span><span class="sxs-lookup"><span data-stu-id="4e8df-107">With reverse journal posting, you can also reverse an entire financial journal.</span></span> <span data-ttu-id="4e8df-108">Napló sztornírozása:</span><span class="sxs-lookup"><span data-stu-id="4e8df-108">To reverse a journal:</span></span> 

- <span data-ttu-id="4e8df-109">A pénzügyi napló megnyitása és a feladott naplók szűrése.</span><span class="sxs-lookup"><span data-stu-id="4e8df-109">Open the financial journal and filter on posted journals.</span></span>
- <span data-ttu-id="4e8df-110">Kattintson a képernyő felső részén lévő **Sztornírozás** menüre.</span><span class="sxs-lookup"><span data-stu-id="4e8df-110">Select the **Reverse** menu at the top of the page.</span></span>
- <span data-ttu-id="4e8df-111">Megjelenik a bizonylatok és a bizonylatsorok teljes száma, valamint a sztornírozott sorok teljes összege</span><span class="sxs-lookup"><span data-stu-id="4e8df-111">You will see the total number of vouchers and voucher lines as well as the total amount of the lines being reversed</span></span>
- <span data-ttu-id="4e8df-112">Válassza az **Igen** lehetőséget, ha a meglévő tranzakciós dátumokat szeretné használni, vagy a **Nem** lehetőséget új beírásához.</span><span class="sxs-lookup"><span data-stu-id="4e8df-112">Select **Yes** to use the existing transaction dates or **No** to enter a new one.</span></span> <span data-ttu-id="4e8df-113">Bizonyos esetekben előfordulhat, hogy az eredeti tranzakció időszaka le van zárva, és új tranzakció dátumát kell megadni a sztornírozáshoz.</span><span class="sxs-lookup"><span data-stu-id="4e8df-113">In some cases, the period of the original transaction may be closed and you must enter a new transaction date for the reversal.</span></span>
- <span data-ttu-id="4e8df-114">Ha a **Nem** beállítást választja, adjon meg egy tranzakciós dátumot a sztornírozáshoz.</span><span class="sxs-lookup"><span data-stu-id="4e8df-114">If you select **No**, enter a transaction date for the reversal.</span></span> 
- <span data-ttu-id="4e8df-115">Írjon be egy megjegyzést, amelyet a sztornírozási tranzakcióhoz szeretne adni.</span><span class="sxs-lookup"><span data-stu-id="4e8df-115">Enter a comment that you want added to the reversal transaction.</span></span>
- <span data-ttu-id="4e8df-116">Kattintson a **Sztornírozás** gombra.</span><span class="sxs-lookup"><span data-stu-id="4e8df-116">Select the **Reverse** button.</span></span>

<span data-ttu-id="4e8df-117">A tranzakció sztornírozva lesz.</span><span class="sxs-lookup"><span data-stu-id="4e8df-117">The transactions will be reversed.</span></span> 

<span data-ttu-id="4e8df-118">Ha a bizonylat sorainak száma meghaladja a 100 sort, akkor a sztornírozási folyamat kötegelt feldolgozással futtatható.</span><span class="sxs-lookup"><span data-stu-id="4e8df-118">If the voucher contains more than 100 lines, the reversal process will run using the batch process.</span></span> <span data-ttu-id="4e8df-119">Megtekintheti az eredményeket a kötegelt feladat megjegyzésinek megtekintésével.</span><span class="sxs-lookup"><span data-stu-id="4e8df-119">You can review the results by viewing the comments in the batch job.</span></span> <span data-ttu-id="4e8df-120">A nem sztornírozható tranzakciók listázva lesznek a kötegelt feladat előzményeiben.</span><span class="sxs-lookup"><span data-stu-id="4e8df-120">Any transactions that couldn't be reversed will be listed in the batch job history.</span></span>

<span data-ttu-id="4e8df-121">Ha a bizonylat sorainak száma 100 vagy kisebb, akkor a sztornírozási folyamat azonnal elindul.</span><span class="sxs-lookup"><span data-stu-id="4e8df-121">If the voucher contains 100 lines or fewer, the reversal process will run immediately.</span></span> <span data-ttu-id="4e8df-122">Az eredmények egy párbeszédablakban jelennek meg, amely minden olyan bizonylatot megjelenít, amely nem sztornírozható, és megadja a sztornírozás okát.</span><span class="sxs-lookup"><span data-stu-id="4e8df-122">The results will be presented in a dialog box that shows any voucher that could not be reversed, along with the reason why it could not be reversed.</span></span> <span data-ttu-id="4e8df-123">Az **OK** gombbal zárja be a párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="4e8df-123">Select **OK** to close the dialog box.</span></span>

## <a name="reversing-vouchers-from-the-voucher-transaction-list"></a><span data-ttu-id="4e8df-124">Bizonylatok sztornírozása a bizonylati tranzakciók listájából.</span><span class="sxs-lookup"><span data-stu-id="4e8df-124">Reversing vouchers from the voucher transaction list.</span></span> 

<span data-ttu-id="4e8df-125">A bizonylatokat a **Bizonylat tranzakciólista** modulból sztornírozhatja az összes alfőkönyvet lefedve.</span><span class="sxs-lookup"><span data-stu-id="4e8df-125">You can also reverse vouchers from the **Voucher transaction list** across all subledgers.</span></span> <span data-ttu-id="4e8df-126">Ezenkívül egyszerre egynél több bizonylatot is sztornírozhat.</span><span class="sxs-lookup"><span data-stu-id="4e8df-126">In addition, you can reverse more than one voucher at a time.</span></span> 

<span data-ttu-id="4e8df-127">Egy vagy több bizonylat sztornírozása:</span><span class="sxs-lookup"><span data-stu-id="4e8df-127">To reverse one or more vouchers:</span></span> 

- <span data-ttu-id="4e8df-128">Kattintson a képernyő felső részén lévő **Sztornírozás** menüre</span><span class="sxs-lookup"><span data-stu-id="4e8df-128">Select the **Reverse** menu at the top of the page</span></span>
- <span data-ttu-id="4e8df-129">Megjelenik a bizonylatok és a bizonylatsorok teljes száma, valamint a sztornírozott sorok teljes összege.</span><span class="sxs-lookup"><span data-stu-id="4e8df-129">You will see the total number of vouchers and voucher lines as well as the total amount of the lines being reversed.</span></span>
- <span data-ttu-id="4e8df-130">Válassza az **Igen** lehetőséget, ha a meglévő tranzakciós dátumokat szeretné használni, vagy a **Nem** lehetőséget új beírásához.</span><span class="sxs-lookup"><span data-stu-id="4e8df-130">Select **Yes** to use the existing transaction dates or **No** to enter a new one.</span></span> <span data-ttu-id="4e8df-131">Bizonyos esetekben előfordulhat, hogy az eredeti tranzakció időszaka le van zárva, és új tranzakció dátumát kell megadni a sztornírozásához.</span><span class="sxs-lookup"><span data-stu-id="4e8df-131">In some cases, the period of the original transaction may be closed and you must enter a new transaction date to reverse it.</span></span>
- <span data-ttu-id="4e8df-132">Ha a **Nem** beállítást választja, adjon meg egy tranzakciós dátumot a sztornírozáshoz.</span><span class="sxs-lookup"><span data-stu-id="4e8df-132">If you select **No**, enter a transaction date for the reversal.</span></span> 
- <span data-ttu-id="4e8df-133">Megjegyzés megadása a sztornírozási tranzakció leírásához.</span><span class="sxs-lookup"><span data-stu-id="4e8df-133">Enter a comment to describe the reversal transaction.</span></span>
- <span data-ttu-id="4e8df-134">Kattintson a **Sztornírozás** gombra.</span><span class="sxs-lookup"><span data-stu-id="4e8df-134">Select the **Reverse** button.</span></span>

<span data-ttu-id="4e8df-135">A tranzakció sztornírozva lesz.</span><span class="sxs-lookup"><span data-stu-id="4e8df-135">The transactions will be reversed.</span></span> 

<span data-ttu-id="4e8df-136">Ha a bizonylat sorainak száma meghaladja a 100-at, akkor a sztornírozási folyamat kötegelt feldolgozással futtatható.</span><span class="sxs-lookup"><span data-stu-id="4e8df-136">If there are more than 100 voucher lines, the reversal process will run using the batch process.</span></span> <span data-ttu-id="4e8df-137">Megtekintheti az eredményeket a kötegelt feladat megjegyzésinek megtekintésével.</span><span class="sxs-lookup"><span data-stu-id="4e8df-137">You can review the results by viewing the comments in the batch job.</span></span> <span data-ttu-id="4e8df-138">A nem sztornírozható tranzakciók jelezve lesznek a kötegelt feladat előzményeiben.</span><span class="sxs-lookup"><span data-stu-id="4e8df-138">Any transactions that couldn't be reversed will be noted in the batch job history.</span></span>

<span data-ttu-id="4e8df-139">Ha a bizonylatsorok száma 100 vagy kevesebb, akkor a sztornírozási folyamat azonnal elindul.</span><span class="sxs-lookup"><span data-stu-id="4e8df-139">If the number of voucher lines is 100 lines or fewer, the reversal process will run immediately.</span></span> <span data-ttu-id="4e8df-140">Az eredmények egy párbeszédablakban jelennek meg, amely minden olyan bizonylatot megjelenít, amely nem sztornírozható, és megadja a annak okát.</span><span class="sxs-lookup"><span data-stu-id="4e8df-140">The results will display in a dialog box that shows any voucher that couldn't be reversed, along with the reason why.</span></span> <span data-ttu-id="4e8df-141">Az **OK** gombbal zárja be a párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="4e8df-141">Select **OK** to close the dialog box.</span></span>

<span data-ttu-id="4e8df-142">A tranzakciókat csak akkor lehet sztornírozni, ha megfelelnek a sztornírozáshoz szükséges üzleti szabályoknak.</span><span class="sxs-lookup"><span data-stu-id="4e8df-142">Transactions can be reversed only if they meet the business rules for reversing them.</span></span> <span data-ttu-id="4e8df-143">A szállítói kifizetéseket nem lehet sztornírozni az ebben az témakörben leírt képességgel.</span><span class="sxs-lookup"><span data-stu-id="4e8df-143">Vendor payments cannot be reversed using the capability described in this topic.</span></span> <span data-ttu-id="4e8df-144">A szállítói kifizetéseket a [Szállítói kifizetés sztornózása](https://docs.microsoft.com/dynamics365/finance/accounts-payable/reverse-vendor-payment) leírt lépésekkel lehet sztornírozni.</span><span class="sxs-lookup"><span data-stu-id="4e8df-144">Vendor payments must be reversed by following the steps listed in [Reverse a vendor payment](https://docs.microsoft.com/dynamics365/finance/accounts-payable/reverse-vendor-payment).</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]