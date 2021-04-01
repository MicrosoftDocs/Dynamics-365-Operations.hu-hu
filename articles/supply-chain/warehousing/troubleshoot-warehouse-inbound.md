---
title: Bejövő raktári műveletek – hibaelhárítás
description: Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben a bejövő raktári műveleteket végzi a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban.
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
ms.openlocfilehash: 6875c3c644b9993a384ba4d8623640536d7307e1
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5250882"
---
# <a name="troubleshoot-inbound-warehouse-operations"></a><span data-ttu-id="34a26-103">Bejövő raktári műveletek – hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="34a26-103">Troubleshoot inbound warehouse operations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="34a26-104">Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben a bejövő raktári műveleteket végzi a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="34a26-104">This topic describes how to fix common issues that you might encounter while you work with inbound warehouse operations in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-quality-order-1-has-been-generated-cluster-profile-could-not-be-found-please-check-your-configuration"></a><span data-ttu-id="34a26-105">A következő hibaüzenet jelenik meg: „Minőségi rendelés %1 lett létrehozva.</span><span class="sxs-lookup"><span data-stu-id="34a26-105">I receive the following error message: "Quality order %1 has been generated.</span></span> <span data-ttu-id="34a26-106">A fürtprofil nem található, ellenőrizze a konfiguráció.”</span><span class="sxs-lookup"><span data-stu-id="34a26-106">Cluster profile could not be found please check your configuration."</span></span>

### <a name="issue-description"></a><span data-ttu-id="34a26-107">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="34a26-107">Issue description</span></span>

<span data-ttu-id="34a26-108">Ez a hibaüzenet egy olyan fogadási folyamathoz kapcsolódik, ahol a minőségirányítás (QMS) be van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="34a26-108">This error message is related to a receiving process where quality management (QMS) is turned on.</span></span> <span data-ttu-id="34a26-109">A környezet konfigurációjától függően a hibaüzenetet generáló tranzakció további részletei segíthetnek a probléma megoldásában.</span><span class="sxs-lookup"><span data-stu-id="34a26-109">Depending on the configurations in your environment, additional details about the transaction that is generating the error message might help fix the issue.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="34a26-110">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="34a26-110">Issue resolution</span></span>

<span data-ttu-id="34a26-111">Először tekintse át a [fürtkitárolási](set-up-cluster-picking.md) beállítást, és győződjön meg arról, hogy a fürtprofilok megfelelően vannak beállítva.</span><span class="sxs-lookup"><span data-stu-id="34a26-111">First, review the [cluster picking](set-up-cluster-picking.md) setup, and make sure that your cluster profiles are set up correctly.</span></span> <span data-ttu-id="34a26-112">A fürtprofilok beállítása nem használható mobileszköz-menüelem fürtkitároláshoz.</span><span class="sxs-lookup"><span data-stu-id="34a26-112">You can't use a mobile device menu item for cluster picking unless cluster profiles are set up.</span></span> <span data-ttu-id="34a26-113">A környezettől függően előfordulhat, hogy más kapcsolódó konfigurációkat is át kell tekintenie.</span><span class="sxs-lookup"><span data-stu-id="34a26-113">Depending on your environment, you might also have to review other related configurations.</span></span>

## <a name="mixed-license-plate-receiving-doesnt-work-for-any-disposition-code-except-credit"></a><span data-ttu-id="34a26-114">A vegyes azonosítótábla-fogadás nem működik semmilyen intézkedési kódnál, kivéve a Jóváírást.</span><span class="sxs-lookup"><span data-stu-id="34a26-114">Mixed license plate receiving doesn't work for any disposition code except Credit.</span></span>

### <a name="issue-description"></a><span data-ttu-id="34a26-115">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="34a26-115">Issue description</span></span>

<span data-ttu-id="34a26-116">Ha egy intézkedési kód **Művelet** mezőjének beállítása *Jóváírás* vagy *Selejt*, akkor csak a [Vegyes azonosítótábla bevételezése](mixed-license-plate-receiving.md) menüpontot használhatja a visszaküldött elemek feldolgozásához.</span><span class="sxs-lookup"><span data-stu-id="34a26-116">When the **Action** field for a disposition code is set to *Credit* or *Scrap*, you can use only the [Mixed license plate receiving](mixed-license-plate-receiving.md) menu item to process returned items.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="34a26-117">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="34a26-117">Issue resolution</span></span>

<span data-ttu-id="34a26-118">A Microsoft kiértékelte ezt a hibát, és megállapította, hogy ez egy funkciókorlátozás.</span><span class="sxs-lookup"><span data-stu-id="34a26-118">Microsoft has evaluated this issue and has determined that it's a feature limitation.</span></span> <span data-ttu-id="34a26-119">Jelenleg csak azok az [intézkedési kódok](../service-management/set-up-disposition-codes.md) támogatottak a vegyes azonosítótábla fogadása esetén, ahol a **Művelet** mező *Jóváírás* vagy *Selejt*.</span><span class="sxs-lookup"><span data-stu-id="34a26-119">Currently, only [disposition codes](../service-management/set-up-disposition-codes.md) where the **Action** field is set to *Credit* or *Scrap* are supported for mixed license plate receiving.</span></span>

## <a name="when-i-run-the-update-product-receipts-periodic-task-unconfirmed-purchase-orders-are-confirmed"></a><span data-ttu-id="34a26-120">A Termékbevételezések frissítése időszakos feladat futtatásakor a meg nem erősített beszerzési rendelések megerősítést nyernek.</span><span class="sxs-lookup"><span data-stu-id="34a26-120">When I run the Update product receipts periodic task, unconfirmed purchase orders are confirmed.</span></span>

### <a name="issue-description"></a><span data-ttu-id="34a26-121">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="34a26-121">Issue description</span></span>

<span data-ttu-id="34a26-122">A *Termékbevételezések frissítése* időszakos feladat futtatása után a rendszer automatikusan megerősíti a *Regisztrált* készlettranzakciós állapotú meg nem erősített beszerzési rendeléseket.</span><span class="sxs-lookup"><span data-stu-id="34a26-122">After you run the *Update product receipts* periodic task, the system automatically confirms unconfirmed purchase orders that have an inventory transaction status of *Registered*.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="34a26-123">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="34a26-123">Issue resolution</span></span>

<span data-ttu-id="34a26-124">Egy új bejövő rakománykezelési funkció, a *Rakománymennyiségek túlbevételezése* megoldja ezt a problémát.</span><span class="sxs-lookup"><span data-stu-id="34a26-124">A new inbound load handling feature, *Over receipt of load quantities*, fixes this issue.</span></span> <span data-ttu-id="34a26-125">Kapcsolja be ezt a funkciót, menjen a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) lehetőségre, és kapcsolja be a következő funkciókat (ebben a sorrendben):</span><span class="sxs-lookup"><span data-stu-id="34a26-125">To turn on this feature, go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), and turn on the following features (in the order that they are listed in):</span></span>

1. <span data-ttu-id="34a26-126">Beszerzési rendelés készlettranzakcióinak társítása rakománnyal</span><span class="sxs-lookup"><span data-stu-id="34a26-126">Associate purchase order inventory transactions with load</span></span>
1. <span data-ttu-id="34a26-127">Rakománymennyiségek túlbevételezése</span><span class="sxs-lookup"><span data-stu-id="34a26-127">Over receipt of load quantities</span></span>

<span data-ttu-id="34a26-128">További információ: [A regisztrált termékmennyiségek feladása a beszerzési rendelésekkel szemben](inbound-load-handling.md#post-registered-quantities).</span><span class="sxs-lookup"><span data-stu-id="34a26-128">For more information, see [Post registered product quantities against purchase orders](inbound-load-handling.md#post-registered-quantities).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]