---
title: Fordított naplófeladás
description: Ez a témakör bemutatja azokat a funkciókat, amelyek lehetővé teszik a bizonylatok sztornírozását a bizonylati tranzakciólistáról vagy a pénzügyi naplókból.
author: MikeFalkner
manager: AnnBe
ms.date: 08/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTransVoucher, LedgerJournalTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5a5456e60f1f3cee5f83ac7f725f7e01ba5bd7a1
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/30/2019
ms.locfileid: "2248585"
---
# <a name="reverse-journal-posting"></a><span data-ttu-id="49c06-103">Naplófeladás sztornírozása</span><span class="sxs-lookup"><span data-stu-id="49c06-103">Reverse journal posting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="49c06-104">Ez a témakör a Microsoft Dynamics 365 Finance egyik funkcióját mutatja be, amelyek lehetővé teszik a teljes napló sztornírozását, illetve egy vagy több bizonylat sztornírozását a bizonylati tranzakciólistáról, az eredettől függetlenül.</span><span class="sxs-lookup"><span data-stu-id="49c06-104">This topic describes capabilities Microsoft Dynamics 365 Finance that allows you to reverse an entire journal or reverse one or more vouchers from the voucher transaction list regardless of their origin.</span></span> 

## <a name="reversing-journals"></a><span data-ttu-id="49c06-105">Naplók sztornózása</span><span class="sxs-lookup"><span data-stu-id="49c06-105">Reversing journals</span></span>

<span data-ttu-id="49c06-106">A naplósorok egyenként is sztornírozhatók.</span><span class="sxs-lookup"><span data-stu-id="49c06-106">You can reverse journal lines individually.</span></span> <span data-ttu-id="49c06-107">A sztornírozási naplófeladással a teljes pénzügyi naplót is sztornírozhatja.</span><span class="sxs-lookup"><span data-stu-id="49c06-107">With reverse journal posting, you can also reverse an entire financial journal.</span></span> <span data-ttu-id="49c06-108">Napló sztornírozása:</span><span class="sxs-lookup"><span data-stu-id="49c06-108">To reverse a journal:</span></span> 
- <span data-ttu-id="49c06-109">A pénzügyi napló megnyitása és a feladott naplók szűrése</span><span class="sxs-lookup"><span data-stu-id="49c06-109">Open the financial journal and filter on posted journals</span></span>
- <span data-ttu-id="49c06-110">Kattintson a képernyő felső részén lévő Sztornírozás menüre</span><span class="sxs-lookup"><span data-stu-id="49c06-110">Click on the Reverse menu at the top of the page</span></span>
- <span data-ttu-id="49c06-111">Megjelenik a bizonylatok és a bizonylatsorok teljes száma, valamint a sztornírozott sorok teljes összege</span><span class="sxs-lookup"><span data-stu-id="49c06-111">You will see the total number of vouchers and voucher lines as well as the total amount of the lines being reversed</span></span>
- <span data-ttu-id="49c06-112">Válassza az Igen lehetőséget, ha a meglévő tranzakciós dátumokat szeretné használni, vagy a Nem lehetőséget új beírásához.</span><span class="sxs-lookup"><span data-stu-id="49c06-112">Select Yes to use the existing transaction dates or No to enter a new one.</span></span> <span data-ttu-id="49c06-113">Bizonyos esetekben előfordulhat, hogy az eredeti tranzakció időszaka le van zárva, és új tranzakció dátumát szeretné megadni a sztornírozáshoz.</span><span class="sxs-lookup"><span data-stu-id="49c06-113">In some cases, the period of the original transaction may be closed and you want to enter a new transaction date for the reversal.</span></span>
- <span data-ttu-id="49c06-114">Ha a Nem beállítást választotta, adjon meg egy tranzakciós dátumot a sztornírozáshoz.</span><span class="sxs-lookup"><span data-stu-id="49c06-114">If you selected No, enter a transaction date for the reversal.</span></span> 
- <span data-ttu-id="49c06-115">Írjon be egy megjegyzést, amelyet a sztornírozási tranzakcióhoz szeretne adni</span><span class="sxs-lookup"><span data-stu-id="49c06-115">Enter a comment that you want added to the reversal transaction</span></span>
- <span data-ttu-id="49c06-116">Kattintson a Sztornírozás gombra.</span><span class="sxs-lookup"><span data-stu-id="49c06-116">Click the Reverse button</span></span>

<span data-ttu-id="49c06-117">A tranzakció sztornírozva lesz.</span><span class="sxs-lookup"><span data-stu-id="49c06-117">The transactions will be reversed.</span></span> 

<span data-ttu-id="49c06-118">Ha a bizonylatsorok száma meghaladja a 100 sort, akkor a sztornírozási folyamat kötegelt feldolgozással futtatható.</span><span class="sxs-lookup"><span data-stu-id="49c06-118">If the number of voucher lines exceeds 100 lines, the reversal process will be run using the batch process.</span></span> <span data-ttu-id="49c06-119">Megtekintheti a sztornírozás eredményeit a futtatott kötegelt feladatban szereplő megjegyzések megtekintésével.</span><span class="sxs-lookup"><span data-stu-id="49c06-119">You can review the results of the reversal by viewing the comments in the batch job that was run.</span></span> <span data-ttu-id="49c06-120">A program minden hibát feljegyez a kötegelt feladat előzményeiben.</span><span class="sxs-lookup"><span data-stu-id="49c06-120">All failures will be noted in the batch job history.</span></span>

<span data-ttu-id="49c06-121">Ha a bizonylatsorok száma 100 vagy kisebb, akkor a sztornírozási folyamat azonnal elindul.</span><span class="sxs-lookup"><span data-stu-id="49c06-121">If the number of voucher lines is 100 lines or less, the reversal process will run immediately.</span></span> <span data-ttu-id="49c06-122">Az eredmények egy párbeszédablakban jelennek meg, amely minden olyan bizonylatot megjelenít, amely nem sztornírozható, és megadja a sztornírozás okát is.</span><span class="sxs-lookup"><span data-stu-id="49c06-122">The results will be presented in a dialog that shows any voucher that could not be reversed and the reason why it could not be reversed.</span></span> <span data-ttu-id="49c06-123">Zárja be a párbeszédpanelt az OK gombra kattintva.</span><span class="sxs-lookup"><span data-stu-id="49c06-123">Click on Ok to close the dialog.</span></span>

## <a name="reversing-vouchers-from-the-voucher-transaction-list"></a><span data-ttu-id="49c06-124">Bizonylatok sztornírozása a bizonylati tranzakciók listájából.</span><span class="sxs-lookup"><span data-stu-id="49c06-124">Reversing vouchers from the voucher transaction list.</span></span> 

<span data-ttu-id="49c06-125">A bizonylatokat a **Bizonylat tranzakciólista** modulból sztornírozhatja az összes alfőkönyvet lefedve.</span><span class="sxs-lookup"><span data-stu-id="49c06-125">You can also reverse vouchers from the **Voucher transaction list** across all subledgers.</span></span> <span data-ttu-id="49c06-126">Ezenkívül egyszerre egynél több bizonylatot is sztornírozhat.</span><span class="sxs-lookup"><span data-stu-id="49c06-126">In addition, you can reverse more than one voucher at a time.</span></span> 

<span data-ttu-id="49c06-127">Egy vagy több bizonylat sztornírozása:</span><span class="sxs-lookup"><span data-stu-id="49c06-127">To reverse one or more vouchers:</span></span> 
- <span data-ttu-id="49c06-128">Kattintson a képernyő felső részén lévő Sztornírozás menüre</span><span class="sxs-lookup"><span data-stu-id="49c06-128">Click on the Reverse menu at the top of the page</span></span>
- <span data-ttu-id="49c06-129">Megjelenik a bizonylatok és a bizonylatsorok teljes száma, valamint a sztornírozott sorok teljes összege</span><span class="sxs-lookup"><span data-stu-id="49c06-129">You will see the total number of vouchers and voucher lines as well as the total amount of the lines being reversed</span></span>
- <span data-ttu-id="49c06-130">Válassza az Igen lehetőséget, ha a meglévő tranzakciós dátumokat szeretné használni, vagy a Nem lehetőséget új beírásához.</span><span class="sxs-lookup"><span data-stu-id="49c06-130">Select Yes to use the existing transaction dates or No to enter a new one.</span></span> <span data-ttu-id="49c06-131">Bizonyos esetekben előfordulhat, hogy az eredeti tranzakció időszaka le van zárva, és új tranzakció dátumát szeretné megadni a sztornírozáshoz.</span><span class="sxs-lookup"><span data-stu-id="49c06-131">In some cases, the period of the original transaction may be closed and you want to enter a new transaction date for the reversal.</span></span>
- <span data-ttu-id="49c06-132">Ha a Nem beállítást választotta, adjon meg egy tranzakciós dátumot a sztornírozáshoz.</span><span class="sxs-lookup"><span data-stu-id="49c06-132">If you selected No, enter a transaction date for the reversal.</span></span> 
- <span data-ttu-id="49c06-133">Írjon be egy megjegyzést, amelyet a sztornírozási tranzakcióhoz szeretne adni</span><span class="sxs-lookup"><span data-stu-id="49c06-133">Enter a comment that you want added to the reversal transaction</span></span>
- <span data-ttu-id="49c06-134">Kattintson a Sztornírozás gombra.</span><span class="sxs-lookup"><span data-stu-id="49c06-134">Click the Reverse button</span></span>

<span data-ttu-id="49c06-135">A tranzakció sztornírozva lesz.</span><span class="sxs-lookup"><span data-stu-id="49c06-135">The transactions will be reversed.</span></span> 

<span data-ttu-id="49c06-136">Ha a bizonylatsorok száma meghaladja a 100 sort, akkor a sztornírozási folyamat kötegelt feldolgozással futtatható.</span><span class="sxs-lookup"><span data-stu-id="49c06-136">If the number of voucher lines exceeds 100 lines, the reversal process will be run using the batch process.</span></span> <span data-ttu-id="49c06-137">Megtekintheti a sztornírozás eredményeit a futtatott kötegelt feladatban szereplő megjegyzések megtekintésével.</span><span class="sxs-lookup"><span data-stu-id="49c06-137">You can review the results of the reversal by viewing the comments in the batch job that was run.</span></span> <span data-ttu-id="49c06-138">A program minden hibát feljegyez a kötegelt feladat előzményeiben.</span><span class="sxs-lookup"><span data-stu-id="49c06-138">All failures will be noted in the batch job history.</span></span>

<span data-ttu-id="49c06-139">Ha a bizonylatsorok száma 100 vagy kisebb, akkor a sztornírozási folyamat azonnal elindul.</span><span class="sxs-lookup"><span data-stu-id="49c06-139">If the number of voucher lines is 100 lines or less, the reversal process will run immediately.</span></span> <span data-ttu-id="49c06-140">Az eredmények egy párbeszédablakban jelennek meg, amely minden olyan bizonylatot megjelenít, amely nem sztornírozható, és megadja a sztornírozás okát is.</span><span class="sxs-lookup"><span data-stu-id="49c06-140">The results will be presented in a dialog that shows any voucher that could not be reversed and the reason why it could not be reversed.</span></span> <span data-ttu-id="49c06-141">Zárja be a párbeszédpanelt az OK gombra kattintva.</span><span class="sxs-lookup"><span data-stu-id="49c06-141">Click on Ok to close the dialog.</span></span>

