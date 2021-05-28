---
title: Számla felosztása funkció
description: Ez a témakör a számlák szállítási cím és adószámlaszám (TAN) szerint történő felosztásának beállítását és működését ismerteti.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 7dddbb9f69a9735c2a03d2b23928f5cb92d4e0fd
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023303"
---
# <a name="split-invoice-functionality"></a><span data-ttu-id="68948-103">Számla felosztása funkció</span><span class="sxs-lookup"><span data-stu-id="68948-103">Split invoice functionality</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="68948-104">Ez a témakör a számlák szállítási cím és adószámlaszám (TAN) szerint történő felosztásának beállítását és működését ismerteti.</span><span class="sxs-lookup"><span data-stu-id="68948-104">This topic describes the setup and functionality for splitting invoices by delivery address and tax account number (TAN).</span></span>

<span data-ttu-id="68948-105">A **Kötelezettségek paraméterek** oldalon, az **Általános** lapon válassza ki a **Termék nyugta** vagy a **Számla** jelölőnégyzetet a termék nyugtának vagy számlának a **Beszerzési rendelés** oldalán található különböző szállítási címekkel és TAN-ekkel rendelkező feladásához és felosztásához.</span><span class="sxs-lookup"><span data-stu-id="68948-105">On the **Accounts payable parameters** page, on the **General** tab, select the **Product receipt** or **Invoice** checkbox to post and split a product receipt or invoice that has different delivery addresses and TANs on the **Purchase order** page.</span></span> <span data-ttu-id="68948-106">A feladott számlát ezután felosztjuk a szállítási cím és a TAN szerint.</span><span class="sxs-lookup"><span data-stu-id="68948-106">The posted invoice will then be split by delivery address and TAN.</span></span>

<span data-ttu-id="68948-107">Az **Összesített módosítás** lapon, a **Megosztás a következő szerint** gyorslapon, a **Szállítási információk** sorban állítsa be a **Visszaigazolás**, **Átvételi lista**, **Szállítólevél** vagy **Számla** opciót **Igen** értékre a visszaigazolás, a kitárolási lista, a szállítólevél vagy a számla feladásához és felosztásához, ahol az **Értékesítési rendelés** oldalon különböző szállítási címek és TAN-ok vannak meghatározva.</span><span class="sxs-lookup"><span data-stu-id="68948-107">On the **Summary update** tab, on the **Split based on** FastTab, in the **Delivery information** row, set the **Confirmation**, **Picking list**, **Packing slip**, or **Invoice** option to **Yes** to post and split a confirmation, picking list, packing slip, or invoice where different delivery addresses and TANs are defined for different invoice lines on the **Sales order** page.</span></span> <span data-ttu-id="68948-108">A számlát ezután felosztjuk a szállítási cím, majd TAN szerint.</span><span class="sxs-lookup"><span data-stu-id="68948-108">The invoice will be split first by delivery address and then by TAN.</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="68948-109">Ha a **Szállítási adatok** beállításának értéke **Igen**, a számla egyetlen számlaként kerül könyvelésre.</span><span class="sxs-lookup"><span data-stu-id="68948-109">If no options for **Delivery information** are set to **Yes**, the invoice will be posted as a single invoice.</span></span> <span data-ttu-id="68948-110">Nem történik számlamegosztás.</span><span class="sxs-lookup"><span data-stu-id="68948-110">No invoice splitting will occur.</span></span>
> - <span data-ttu-id="68948-111">Ha olyan szállítólevelet szeretne felosztani és könyvelni, ahol a számlasorok eltérő szállítási címmel és TAN-nel rendelkeznek, a **Szállítólevél** opciót be kell állítania a **Szállítási információk** elemhez **Igen** beállításra.</span><span class="sxs-lookup"><span data-stu-id="68948-111">To split and post a packing slip where the invoice lines have different delivery addresses and TANs, you must set the **Packing slip** option for **Delivery information** to **Yes**.</span></span>
> - <span data-ttu-id="68948-112">Ha olyan számlát szeretne felosztani és könyvelni, ahol a számlasorok eltérő szállítási címmel és TAN-nel rendelkeznek, a **Számla** opciót be kell állítania a **Szállítási információk** elemhez **Igen** beállításra.</span><span class="sxs-lookup"><span data-stu-id="68948-112">To split and post an invoice where the invoice lines have different delivery addresses and TANs, you must set the **Invoice** option for **Delivery information** to **Yes**.</span></span>
> - <span data-ttu-id="68948-113">Ha olyan számlát szeretne felosztani és könyvelni, ahol a számlasorok eltérő szállítási címmel, de ugyanazzal TAN-nel rendelkeznek, a **Számla** opciót be kell állítania a **Szállítási információk** elemhez **Nem** beállításra.</span><span class="sxs-lookup"><span data-stu-id="68948-113">To post an invoice where the invoice lines have different delivery addresses but the same TAN, set the **Invoice** option for **Delivery information** to **No**.</span></span> <span data-ttu-id="68948-114">A számlát ezután felosztjuk a szállítási cím szerint.</span><span class="sxs-lookup"><span data-stu-id="68948-114">The invoice will be split by delivery address.</span></span>

## <a name="example"></a><span data-ttu-id="68948-115">Példa</span><span class="sxs-lookup"><span data-stu-id="68948-115">Example</span></span>

<span data-ttu-id="68948-116">Ebben a példában a **Szállítási információk** **Számla** opciója a **Kötelezettségek paraméterek** oldal **Összegzés frissítése** lapján **Igen**-re van állítva.</span><span class="sxs-lookup"><span data-stu-id="68948-116">In this example, the **Invoice** option for **Delivery information** is set to **Yes** on the **Summary update** tab of the **Accounts payable parameters** page.</span></span> <span data-ttu-id="68948-117">A beszerzési számla a következő beállítással rendelkezik a szállítási címekre és a TAN-ekre a sorokon:</span><span class="sxs-lookup"><span data-stu-id="68948-117">A purchase invoice is posted that has the following setup for delivery addresses and TANs on the lines:</span></span>

- <span data-ttu-id="68948-118">**1. cikksor:** Szállítási cím 1, TAN-ABCD12345A</span><span class="sxs-lookup"><span data-stu-id="68948-118">**Item line 1:** Delivery address 1, TAN-ABCD12345A</span></span>
- <span data-ttu-id="68948-119">**2. cikksor:** Szállítási cím 1, TAN-ABCD12345A</span><span class="sxs-lookup"><span data-stu-id="68948-119">**Item line 2:** Delivery address 1, TAN-ABCD12345A</span></span>
- <span data-ttu-id="68948-120">**3. cikksor:** Szállítási cím 2, TAN-ABCE12345B</span><span class="sxs-lookup"><span data-stu-id="68948-120">**Item line 3:** Delivery address 2, TAN-ABCE12345B</span></span>
- <span data-ttu-id="68948-121">**4. cikksor:** Szállítási cím 3, TAN-ABCD12345A</span><span class="sxs-lookup"><span data-stu-id="68948-121">**Item line 4:** Delivery address 3, TAN-ABCD12345A</span></span>

<span data-ttu-id="68948-122">Ebben az esetben az eredeti számlát két számlára osztjuk fel, és a következő módon könyveljük:</span><span class="sxs-lookup"><span data-stu-id="68948-122">In this case, the original invoice is split into two invoices and posted in the following way:</span></span>

- <span data-ttu-id="68948-123">Az 1. számla az 1. és a 2. cikksorhoz kerül könyvelésre, mivel mindkét sor szállítási címe és TAN-je azonos.</span><span class="sxs-lookup"><span data-stu-id="68948-123">Invoice 1 is posted for item line 1 and item line 2, because both lines have the same delivery address and TAN.</span></span>
- <span data-ttu-id="68948-124">A 2. számla a 3. cikksorhoz kerül feladásra.</span><span class="sxs-lookup"><span data-stu-id="68948-124">Invoice 2 is posted for item line 3.</span></span>
- <span data-ttu-id="68948-125">A 3. számla a 4. cikksorhoz kerül feladásra.</span><span class="sxs-lookup"><span data-stu-id="68948-125">Invoice 3 is posted for item line 4.</span></span>
