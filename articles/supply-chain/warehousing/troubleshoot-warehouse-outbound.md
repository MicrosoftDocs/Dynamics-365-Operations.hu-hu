---
title: Kimenő raktári műveletek – hibaelhárítás
description: Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben a kimenő raktári műveleteket végzi a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 165ac8145ad75c2c6619764b9abe855b9d32eb46
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993978"
---
# <a name="troubleshoot-outbound-warehouse-operations"></a><span data-ttu-id="bdc77-103">Kimenő raktári műveletek – hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="bdc77-103">Troubleshoot outbound warehouse operations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bdc77-104">Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben a kimenő raktári műveleteket végzi a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="bdc77-104">This topic describes how to fix common issues that you might encounter while you work with outbound warehouse operations in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-sales-order-could-not-be-released"></a><span data-ttu-id="bdc77-105">A következő hibaüzenet jelenik meg: „Az értékesítési rendelés nem adható ki.”</span><span class="sxs-lookup"><span data-stu-id="bdc77-105">I receive the following error message: "Sales order could not be released."</span></span>

### <a name="issue-description"></a><span data-ttu-id="bdc77-106">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="bdc77-106">Issue description</span></span>

<span data-ttu-id="bdc77-107">Ez a hiba több okból is előfordulhat.</span><span class="sxs-lookup"><span data-stu-id="bdc77-107">This issue can occur for several reasons.</span></span> <span data-ttu-id="bdc77-108">Például a rendelés hitelkezelés várakozási listán van, és a rendszer nem hozhat létre szállítmányokat mindaddig, amíg az értékesítési rendeléshez társított összes értékesítési sorhoz érvényes postai címet nem ír be.</span><span class="sxs-lookup"><span data-stu-id="bdc77-108">For example, the order is on credit management hold, and no shipments can be created until a valid postal address is entered for all sales lines that are associated with a sales order.</span></span> <span data-ttu-id="bdc77-109">Azt is megteheti, hogy a rendelés várakoztatását a raktárba történő kiadás előtt megoldja.</span><span class="sxs-lookup"><span data-stu-id="bdc77-109">Alternatively, there is an order hold that must be addressed before the order can be released to the warehouse.</span></span> <span data-ttu-id="bdc77-110">Ez a várakoztatás lehet rendeléssel vagy vevői fiókkal kapcsolatos.</span><span class="sxs-lookup"><span data-stu-id="bdc77-110">This hold might be order-specific, or it might be on the customer account.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="bdc77-111">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="bdc77-111">Issue resolution</span></span>

<span data-ttu-id="bdc77-112">Adja hozzá vagy frissítse a címet az értékesítési rendelés és a rendelési sorokban, majd adja ki a rendelést a raktárba.</span><span class="sxs-lookup"><span data-stu-id="bdc77-112">Add or update the address on the sales order and order lines, and then release the order to the warehouse.</span></span> <span data-ttu-id="bdc77-113">A rendelések csak akkor adhatók ki a raktárba, ha rendelkeznek érvényes szállítási címmel (a **Szervezet adminisztrációs** moduljának címformátumának beállításával).</span><span class="sxs-lookup"><span data-stu-id="bdc77-113">Orders can be released to the warehouse only if they have a valid delivery address (per the address format setup in the **Organization administration** module).</span></span>

<span data-ttu-id="bdc77-114">Vizsgálja meg a rendelés visszatartását, és oldja meg a problémákat.</span><span class="sxs-lookup"><span data-stu-id="bdc77-114">Investigate the order hold, and address the issues.</span></span> <span data-ttu-id="bdc77-115">Ezután távolítsa el a rendelésből vagy a vevőtől a várakoztatást, és adja ki a rendelést a raktárba.</span><span class="sxs-lookup"><span data-stu-id="bdc77-115">Then remove the hold from the order or customer, and release the order to the warehouse.</span></span>

## <a name="i-receive-the-following-message-the-shipment-for-load-1-has-been-confirmed-however-no-lines-are-posted"></a><span data-ttu-id="bdc77-116">A következő üzenet jelenik meg: „A(z) 1% rakomány szállítása visszaigazolva”.</span><span class="sxs-lookup"><span data-stu-id="bdc77-116">I receive the following message: "The shipment for load 1% has been confirmed."</span></span> <span data-ttu-id="bdc77-117">A sorok azonban nem kerülnek feladásra.</span><span class="sxs-lookup"><span data-stu-id="bdc77-117">However, no lines are posted.</span></span>

### <a name="issue-description"></a><span data-ttu-id="bdc77-118">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="bdc77-118">Issue description</span></span>

<span data-ttu-id="bdc77-119">A rakomány szállítása megtörtént, de a feladás nem.</span><span class="sxs-lookup"><span data-stu-id="bdc77-119">A shipment on a load was confirmed, but no further posting occurred.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="bdc77-120">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="bdc77-120">Issue resolution</span></span>

<span data-ttu-id="bdc77-121">A szállítmány visszaigazolása nem befolyásolja a feladást.</span><span class="sxs-lookup"><span data-stu-id="bdc77-121">Shipment confirmation doesn't affect posting.</span></span> <span data-ttu-id="bdc77-122">Csak a szállítás és a rakomány állapotának frissítése.</span><span class="sxs-lookup"><span data-stu-id="bdc77-122">It just updates the shipment and load status.</span></span> <span data-ttu-id="bdc77-123">A feladásnak egy külön folyamatban kell lennie.</span><span class="sxs-lookup"><span data-stu-id="bdc77-123">Posting must occur in a separate process.</span></span>

## <a name="i-receive-the-following-error-message-direct-delivery-is-not-able-to-process-for-warehouse-1-as-it-has-warehouse-management-enabled-please-specify-another-warehouse-that-is-not-enabled-for-warehouse-management"></a><span data-ttu-id="bdc77-124">A következő hibaüzenet jelenik meg: „A közvetlen kiszállítás nem tudja feldolgozni az 1% raktárat, mert engedélyezve van a raktárkezelés.</span><span class="sxs-lookup"><span data-stu-id="bdc77-124">I receive the following error message: "Direct delivery is not able to process for warehouse 1% as it has warehouse management enabled.</span></span> <span data-ttu-id="bdc77-125">Adjon meg egy másik raktárat, amelyben nincs engedélyezve a raktárkezelés.”</span><span class="sxs-lookup"><span data-stu-id="bdc77-125">Please specify another warehouse that is not enabled for warehouse management."</span></span>

### <a name="issue-description"></a><span data-ttu-id="bdc77-126">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="bdc77-126">Issue description</span></span>

<span data-ttu-id="bdc77-127">A cikkek egy értékesítési sorhoz kerülnek a közvetlen kiszállításhoz a raktárkezelés (WMS) számára engedélyezett raktárból.</span><span class="sxs-lookup"><span data-stu-id="bdc77-127">An item is added to a sales line for direct delivery from a warehouse that is enabled for warehouse management (WMS).</span></span> <span data-ttu-id="bdc77-128">Ez a hibaüzenet jelenik meg az értékesítési sor frissítésekor.</span><span class="sxs-lookup"><span data-stu-id="bdc77-128">You receive this error message when the sales line is updated.</span></span> 

### <a name="issue-resolution"></a><span data-ttu-id="bdc77-129">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="bdc77-129">Issue resolution</span></span>

<span data-ttu-id="bdc77-130">A Microsoft kiértékelte ezt a hibát, és megállapította, hogy ez egy funkciókorlátozás.</span><span class="sxs-lookup"><span data-stu-id="bdc77-130">Microsoft has evaluated this issue and has determined that it's a feature limitation.</span></span> <span data-ttu-id="bdc77-131">Jelenleg a WMS nem támogatja a közvetlen kiszállítást.</span><span class="sxs-lookup"><span data-stu-id="bdc77-131">Currently, WMS doesn't support direct delivery.</span></span> <span data-ttu-id="bdc77-132">Ezért a közvetlen kiszállítás használatához ki kell választania egy nem WMS-típusú terméket és raktárat.</span><span class="sxs-lookup"><span data-stu-id="bdc77-132">Therefore, to use direct delivery, you must select a non-WMS item and warehouse.</span></span>
