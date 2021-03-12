---
title: A termékkonfiguráló hibaelhárítása
description: Ez a témakör azt mutatja be, hogyan lehet javítani a termékkonfiguráció használata során felmerülő problémákat.
author: SmithaNataraj
manager: tfehr
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: e6cfeb6a2b4166dfa9a5a5cc1b7d3d913b865ce2
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4999606"
---
# <a name="troubleshoot-the-product-configurator"></a><span data-ttu-id="9700f-103">A termékkonfiguráló hibaelhárítása</span><span class="sxs-lookup"><span data-stu-id="9700f-103">Troubleshoot the product configurator</span></span>

<span data-ttu-id="9700f-104">Ez a témakör azt mutatja be, hogyan lehet javítani a termékkonfiguráció használata során felmerülő problémákat.</span><span class="sxs-lookup"><span data-stu-id="9700f-104">This topic describes how to fix issues that you might encounter while you work with the product configurator.</span></span>

## <a name="item-text-is-overwritten-when-i-configure-a-product-on-a-sales-order-line"></a><span data-ttu-id="9700f-105">A cikk szövege felülíródik, amikor egy terméket konfigurálok egy értékesítési rendeléssorban.</span><span class="sxs-lookup"><span data-stu-id="9700f-105">Item text is overwritten when I configure a product on a sales order line.</span></span>

### <a name="issue-description"></a><span data-ttu-id="9700f-106">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="9700f-106">Issue description</span></span>

<span data-ttu-id="9700f-107">Ez a probléma akkor fordul elő, ha egy konfigurálható cikkhez értékesítési rendeléssort hoz létre, majd módosítja a cikk szövegét.</span><span class="sxs-lookup"><span data-stu-id="9700f-107">This issue occurs when you create a sales order line for a configurable item and then modify the item text.</span></span> <span data-ttu-id="9700f-108">Amikor konfigurálja az elemet, majd az **OK** lehetőséget választja, a program felülírja a szöveget a szabványos szöveggel.</span><span class="sxs-lookup"><span data-stu-id="9700f-108">When you configure the item and then select **OK**, the text is overwritten with the standard text.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="9700f-109">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="9700f-109">Issue resolution</span></span>

<span data-ttu-id="9700f-110">Ez a viselkedés várható.</span><span class="sxs-lookup"><span data-stu-id="9700f-110">This behavior is expected.</span></span> <span data-ttu-id="9700f-111">A szövegmező tartalmazza a változat nevét, amelyet csak a sor konfigurálása után tölt ki a program.</span><span class="sxs-lookup"><span data-stu-id="9700f-111">The text field includes the variant name, which is filled in only after you configure the line.</span></span> <span data-ttu-id="9700f-112">Ezért a szöveget a sor konfigurálása után kell módosítania, nem korábban.</span><span class="sxs-lookup"><span data-stu-id="9700f-112">Therefore, you must change the text after you've configured the line, not before.</span></span>

## <a name="integer-attributes-are-incorrectly-rounded-when-product-configuration-models-are-calculated"></a><span data-ttu-id="9700f-113">Az egész szám attribútumok helytelenül kerekítve jelennek meg a termékkonfigurációs modellek számításakor.</span><span class="sxs-lookup"><span data-stu-id="9700f-113">Integer attributes are incorrectly rounded when product configuration models are calculated.</span></span>

### <a name="issue-description"></a><span data-ttu-id="9700f-114">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="9700f-114">Issue description</span></span>

<span data-ttu-id="9700f-115">Ez a probléma a következő műveletek végrehajtásakor fordulhat elő:</span><span class="sxs-lookup"><span data-stu-id="9700f-115">This issue can occur when you perform the following series of actions:</span></span>

1. <span data-ttu-id="9700f-116">Állítsa be a következő attribútumokat egy termelési konfigurációs modellen:</span><span class="sxs-lookup"><span data-stu-id="9700f-116">Set up the following attributes on a production configuration model:</span></span>

    - <span data-ttu-id="9700f-117">Bemenet (egész szám)</span><span class="sxs-lookup"><span data-stu-id="9700f-117">Input (integer)</span></span>
    - <span data-ttu-id="9700f-118">Százalék (tizedesérték)</span><span class="sxs-lookup"><span data-stu-id="9700f-118">Percent (decimal)</span></span>
    - <span data-ttu-id="9700f-119">Eredmény (egész szám)</span><span class="sxs-lookup"><span data-stu-id="9700f-119">Result (integer)</span></span>

2. <span data-ttu-id="9700f-120">Hozzon létre egy kalkulációt, amelynek kifejezései a következők:</span><span class="sxs-lookup"><span data-stu-id="9700f-120">Create a calculation that has the following expression:</span></span>

    <span data-ttu-id="9700f-121">*Eredmény* = *Bevitel* × *Százalék* ÷ 100</span><span class="sxs-lookup"><span data-stu-id="9700f-121">*Result* = *Input* × *Percent* ÷ 100</span></span>

<span data-ttu-id="9700f-122">Ebben az esetben az egész szám eredmény nem mindig megfelelően van kerekítve.</span><span class="sxs-lookup"><span data-stu-id="9700f-122">In this case, the integer result isn't always correctly rounded.</span></span> <span data-ttu-id="9700f-123">Például a bemenet 1000, és a százalék 2,40.</span><span class="sxs-lookup"><span data-stu-id="9700f-123">For example, the input is 1,000, and the percentage is 2.40.</span></span> <span data-ttu-id="9700f-124">Ezért az egész szám eredmény 24 lesz, mert az 1000 2,40 százaléka 24 (vagy 24,00 tizedesértékben megadva).</span><span class="sxs-lookup"><span data-stu-id="9700f-124">Therefore, you expect the integer result to be 24, because 2.40 percent of 1,000 is 24 (or 24.00 in decimal form).</span></span> <span data-ttu-id="9700f-125">Ehelyett az eredmény 23-ként jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="9700f-125">Instead, the result is shown as 23.</span></span> <span data-ttu-id="9700f-126">Ha azonban a százalék 2,39, akkor a kalkuláció 24-re lesz kerekítve 23 helyett.</span><span class="sxs-lookup"><span data-stu-id="9700f-126">However, when the percentage is 2.39, the calculation is rounded to 24 instead of 23.</span></span> <span data-ttu-id="9700f-127">Ha a százalék 2,50, akkor a kalkuláció a vártnak megfelelően 25 lesz.</span><span class="sxs-lookup"><span data-stu-id="9700f-127">When the percentage is 2.50, the calculation is rounded to 25, as expected.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="9700f-128">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="9700f-128">Issue resolution</span></span>

<span data-ttu-id="9700f-129">Ez a probléma amiatt fordul elő, mert a Microsoft Solver Foundation számokat a törtszámokkal, belső használatra jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="9700f-129">This issue occurs because of the way that Microsoft Solver Foundation internally represents numbers by using fractions.</span></span> <span data-ttu-id="9700f-130">Az előző példában a számítás eredménye, ahol a százalék 2,40 volt, így jelenik meg: 27021597764222975 ÷ 1125899906842624 = 23,99999999999999911182158029987476766109466552734375.</span><span class="sxs-lookup"><span data-stu-id="9700f-130">For the preceding example, the result of the calculation where the percentage is 2.40 is represented as 27021597764222975 ÷ 1125899906842624 = 23.99999999999999911182158029987476766109466552734375.</span></span> <span data-ttu-id="9700f-131">Amikor a .NET egész számként adja meg ezt az értéket, 23-ra fog visszatérni.</span><span class="sxs-lookup"><span data-stu-id="9700f-131">When .NET casts this value as an integer, it will return 23.</span></span>

<span data-ttu-id="9700f-132">Ez a viselkedés nem változik, mert más forgatókönyvek függnek tőle.</span><span class="sxs-lookup"><span data-stu-id="9700f-132">This behavior won't be changed, because other scenarios depend on it.</span></span> <span data-ttu-id="9700f-133">Az előző példában a problémát egy további tizedes attribútum és egy kalkuláció bevezetésével oldhatja meg.</span><span class="sxs-lookup"><span data-stu-id="9700f-133">For the preceding example, you can fix the issue by introducing an additional decimal attribute and a calculation.</span></span>

<span data-ttu-id="9700f-134">Például beállíthatja a következő attribútumokat egy termelési konfigurációs modellen:</span><span class="sxs-lookup"><span data-stu-id="9700f-134">For example, you can set up the following attributes on a production configuration model:</span></span>

- <span data-ttu-id="9700f-135">Bemenet (egész szám)</span><span class="sxs-lookup"><span data-stu-id="9700f-135">Input (integer)</span></span>
- <span data-ttu-id="9700f-136">Százalék (tizedesérték)</span><span class="sxs-lookup"><span data-stu-id="9700f-136">Percent (decimal)</span></span>
- <span data-ttu-id="9700f-137">EredményTizedesérték (tizedesérték)</span><span class="sxs-lookup"><span data-stu-id="9700f-137">ResultDecimal (decimal)</span></span>
- <span data-ttu-id="9700f-138">EredményEgészszám (egész szám)</span><span class="sxs-lookup"><span data-stu-id="9700f-138">ResultInteger (integer)</span></span>

<span data-ttu-id="9700f-139">A következő kalkulációkat adhatja hozzá ezután:</span><span class="sxs-lookup"><span data-stu-id="9700f-139">You can then add the following calculations:</span></span>

- <span data-ttu-id="9700f-140">*EredményTizedesérték* = *Bemeneti* × *Százalék* ÷ 100</span><span class="sxs-lookup"><span data-stu-id="9700f-140">*ResultDecimal* = *Input* × *Percent* ÷ 100</span></span>
- <span data-ttu-id="9700f-141">*EredményEgészszám* = *EredményTizedesérték*</span><span class="sxs-lookup"><span data-stu-id="9700f-141">*ResultInteger* = *ResultDecimal*</span></span>
