---
title: Bejövő raktári műveletek – hibaelhárítás
description: Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben a bejövő raktári műveleteket végzi a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 6f6d689c596b4ec924cb50ec3bea8ce907e6dc6b
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920987"
---
# <a name="troubleshoot-inbound-warehouse-operations"></a><span data-ttu-id="d9b22-103">Bejövő raktári műveletek – hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="d9b22-103">Troubleshoot inbound warehouse operations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d9b22-104">Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben a bejövő raktári műveleteket végzi a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="d9b22-104">This topic describes how to fix common issues that you might encounter while you work with inbound warehouse operations in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-quality-order-1-has-been-generated-cluster-profile-could-not-be-found-please-check-your-configuration"></a><span data-ttu-id="d9b22-105">A következő hibaüzenet jelenik meg: „Minőségi rendelés %1 lett létrehozva.</span><span class="sxs-lookup"><span data-stu-id="d9b22-105">I receive the following error message: "Quality order %1 has been generated.</span></span> <span data-ttu-id="d9b22-106">A fürtprofil nem található, ellenőrizze a konfiguráció.”</span><span class="sxs-lookup"><span data-stu-id="d9b22-106">Cluster profile could not be found please check your configuration."</span></span>

### <a name="issue-description"></a><span data-ttu-id="d9b22-107">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="d9b22-107">Issue description</span></span>

<span data-ttu-id="d9b22-108">Ez a hibaüzenet egy olyan fogadási folyamathoz kapcsolódik, ahol a minőségirányítás (QMS) be van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="d9b22-108">This error message is related to a receiving process where quality management (QMS) is turned on.</span></span> <span data-ttu-id="d9b22-109">A környezet konfigurációjától függően a hibaüzenetet generáló tranzakció további részletei segíthetnek a probléma megoldásában.</span><span class="sxs-lookup"><span data-stu-id="d9b22-109">Depending on the configurations in your environment, additional details about the transaction that is generating the error message might help fix the issue.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="d9b22-110">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="d9b22-110">Issue resolution</span></span>

<span data-ttu-id="d9b22-111">Először tekintse át a [fürtkitárolási](set-up-cluster-picking.md) beállítást, és győződjön meg arról, hogy a fürtprofilok megfelelően vannak beállítva.</span><span class="sxs-lookup"><span data-stu-id="d9b22-111">First, review the [cluster picking](set-up-cluster-picking.md) setup, and make sure that your cluster profiles are set up correctly.</span></span> <span data-ttu-id="d9b22-112">A fürtprofilok beállítása nem használható mobileszköz-menüelem fürtkitároláshoz.</span><span class="sxs-lookup"><span data-stu-id="d9b22-112">You can't use a mobile device menu item for cluster picking unless cluster profiles are set up.</span></span> <span data-ttu-id="d9b22-113">A környezettől függően előfordulhat, hogy más kapcsolódó konfigurációkat is át kell tekintenie.</span><span class="sxs-lookup"><span data-stu-id="d9b22-113">Depending on your environment, you might also have to review other related configurations.</span></span>

## <a name="mixed-license-plate-receiving-doesnt-work-for-any-disposition-code-except-credit"></a><span data-ttu-id="d9b22-114">A vegyes azonosítótábla-fogadás nem működik semmilyen intézkedési kódnál, kivéve a Jóváírást.</span><span class="sxs-lookup"><span data-stu-id="d9b22-114">Mixed license plate receiving doesn't work for any disposition code except Credit.</span></span>

### <a name="issue-description"></a><span data-ttu-id="d9b22-115">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="d9b22-115">Issue description</span></span>

<span data-ttu-id="d9b22-116">Ha egy intézkedési kód **Művelet** mezőjének beállítása *Jóváírás* vagy *Selejt*, akkor csak a [Vegyes azonosítótábla bevételezése](mixed-license-plate-receiving.md) menüpontot használhatja a visszaküldött elemek feldolgozásához.</span><span class="sxs-lookup"><span data-stu-id="d9b22-116">When the **Action** field for a disposition code is set to *Credit* or *Scrap*, you can use only the [Mixed license plate receiving](mixed-license-plate-receiving.md) menu item to process returned items.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="d9b22-117">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="d9b22-117">Issue resolution</span></span>

<span data-ttu-id="d9b22-118">A Microsoft kiértékelte ezt a hibát, és megállapította, hogy ez egy funkciókorlátozás.</span><span class="sxs-lookup"><span data-stu-id="d9b22-118">Microsoft has evaluated this issue and has determined that it's a feature limitation.</span></span> <span data-ttu-id="d9b22-119">Jelenleg csak azok az [intézkedési kódok](../service-management/set-up-disposition-codes.md) támogatottak a vegyes azonosítótábla fogadása esetén, ahol a **Művelet** mező *Jóváírás* vagy *Selejt*.</span><span class="sxs-lookup"><span data-stu-id="d9b22-119">Currently, only [disposition codes](../service-management/set-up-disposition-codes.md) where the **Action** field is set to *Credit* or *Scrap* are supported for mixed license plate receiving.</span></span>

## <a name="when-i-run-the-update-product-receipts-periodic-task-unconfirmed-purchase-orders-are-confirmed"></a><span data-ttu-id="d9b22-120">A Termékbevételezések frissítése időszakos feladat futtatásakor a meg nem erősített beszerzési rendelések megerősítést nyernek.</span><span class="sxs-lookup"><span data-stu-id="d9b22-120">When I run the Update product receipts periodic task, unconfirmed purchase orders are confirmed.</span></span>

### <a name="issue-description"></a><span data-ttu-id="d9b22-121">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="d9b22-121">Issue description</span></span>

<span data-ttu-id="d9b22-122">A *Termékbevételezések frissítése* időszakos feladat futtatása után a rendszer automatikusan megerősíti a *Regisztrált* készlettranzakciós állapotú meg nem erősített beszerzési rendeléseket.</span><span class="sxs-lookup"><span data-stu-id="d9b22-122">After you run the *Update product receipts* periodic task, the system automatically confirms unconfirmed purchase orders that have an inventory transaction status of *Registered*.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="d9b22-123">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="d9b22-123">Issue resolution</span></span>

<span data-ttu-id="d9b22-124">Egy új bejövő rakománykezelési funkció, a *Rakománymennyiségek túlbevételezése* megoldja ezt a problémát.</span><span class="sxs-lookup"><span data-stu-id="d9b22-124">A new inbound load handling feature, *Over receipt of load quantities*, fixes this issue.</span></span> <span data-ttu-id="d9b22-125">A funkció bekapcsolásához, menjen a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) munkaterületre, és kapcsolja be a következő funkciókat (ebben a sorrendben):</span><span class="sxs-lookup"><span data-stu-id="d9b22-125">To turn on this feature, go to the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace and turn on the following features (in the order that they are listed in):</span></span>

1. <span data-ttu-id="d9b22-126">Beszerzési rendelés készlettranzakcióinak társítása rakománnyal</span><span class="sxs-lookup"><span data-stu-id="d9b22-126">Associate purchase order inventory transactions with load</span></span>
1. <span data-ttu-id="d9b22-127">Rakománymennyiségek túlbevételezése</span><span class="sxs-lookup"><span data-stu-id="d9b22-127">Over receipt of load quantities</span></span>

<span data-ttu-id="d9b22-128">További információ: [A regisztrált termékmennyiségek feladása a beszerzési rendelésekkel szemben](inbound-load-handling.md#post-registered-quantities).</span><span class="sxs-lookup"><span data-stu-id="d9b22-128">For more information, see [Post registered product quantities against purchase orders](inbound-load-handling.md#post-registered-quantities).</span></span>

## <a name="when-i-register-inbound-orders-i-receive-the-following-error-message-the-quantity-is-not-valid"></a><span data-ttu-id="d9b22-129">Bejövő rendelések regisztrálásakor a következő hibaüzenet jelenik meg: "A mennyiség érvénytelen."</span><span class="sxs-lookup"><span data-stu-id="d9b22-129">When I register inbound orders, I receive the following error message: "The quantity is not valid."</span></span>

### <a name="issue-description"></a><span data-ttu-id="d9b22-130">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="d9b22-130">Issue description</span></span>

<span data-ttu-id="d9b22-131">Ha az **Azonosítótábla-csoportosítási házirend** mező beállítása *Felhasználó által meghatározott* egy olyan mobileszköz-menüelem esetén, amellyel bejövő rendeléseket regisztrálnak, hibaüzenet jelenik meg („A mennyiség érvénytelen”), és a regisztráció nem fejezhető be.</span><span class="sxs-lookup"><span data-stu-id="d9b22-131">If the **License plate grouping policy** field is set to *User defined* for a mobile device menu item that is used to register inbound orders, you receive an error message ("The quantity is not valid"), and you can't complete the registration.</span></span>

### <a name="issue-cause"></a><span data-ttu-id="d9b22-132">Probléma oka</span><span class="sxs-lookup"><span data-stu-id="d9b22-132">Issue cause</span></span>

<span data-ttu-id="d9b22-133">Ha azonosítótábla-csoportosítási házirendként *Felhasználó által meghatározott* van beállítva, a rendszer e bejövő készletet külön azonosítótáblákra bontja az egységszekvencia-csoport alapján.</span><span class="sxs-lookup"><span data-stu-id="d9b22-133">When *User defined* is used as a license plate grouping policy, the system splits the incoming inventory into separate license plates, as indicated by the unit sequence group.</span></span> <span data-ttu-id="d9b22-134">Ha köteg- vagy sorozatszámokat használ a fogadott cikk nyomon követéséhez, az egyes kötegek vagy sorozatok mennyiségét a regisztrált azonosítótáblánként kell megadni.</span><span class="sxs-lookup"><span data-stu-id="d9b22-134">If batch or serial numbers are used to track the item that is being received, the quantities of each batch or serial must be specified per license plate that is registered.</span></span> <span data-ttu-id="d9b22-135">Ha az azonosítótáblához megadott mennyiség meghaladja az aktuális dimenziókhoz még beérkeztetni kívánt mennyiséget, hibaüzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="d9b22-135">If the quantity that is specified for a license plate exceeds the quantity that must still be received for the current dimensions, you receive the error message.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="d9b22-136">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="d9b22-136">Issue resolution</span></span>

<span data-ttu-id="d9b22-137">Ha egy elemet olyan mobileszköz-menüelem használatával regisztrál, amelyben az **Azonosítótábla-csoportosítási házirend** mező értéke *felhasználó által meghatározott*, előfordulhat, hogy a rendszer kéri az azonosítótábla-számok, kötegszámok vagy sorozatszámok megerősítését vagy megadását.</span><span class="sxs-lookup"><span data-stu-id="d9b22-137">When you register an item by using a mobile device menu item where the **License plate grouping policy** field is set to *User defined*, the system might require that you confirm or enter license plate numbers, batch numbers, or serial numbers.</span></span>

<span data-ttu-id="d9b22-138">Az azonosítótábla-visszaigazoló oldalon a rendszer az aktuális azonosítótáblához lefoglalt mennyiséget mutatja.</span><span class="sxs-lookup"><span data-stu-id="d9b22-138">On the license plate confirmation page, the system will show the quantity that is allocated for the current license plate.</span></span> <span data-ttu-id="d9b22-139">A köteg vagy sorozat megerősítési oldalain a rendszer megmutatja azt a mennyiséget, amelyet még meg kell kapnia az aktuális azonosítótáblán.</span><span class="sxs-lookup"><span data-stu-id="d9b22-139">On the batch or serial confirmation pages, the system will show the quantity that must still be received on the current license plate.</span></span> <span data-ttu-id="d9b22-140">Ez magában foglal egy mezőt is, ahol megadhatja az azonosítótábla- és a köteg- vagy sorozatszám kombinációjához regisztrálandó mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="d9b22-140">It will also include a field where you can enter the quantity to register for that combination of license plate and batch or serial number.</span></span> <span data-ttu-id="d9b22-141">Ebben az esetben győződjön meg arról, hogy az azonosítótáblához regisztrált mennyiség nem haladja meg a még beérkeztetni kívánt mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="d9b22-141">In this case, make sure that the quantity that is being registered for the license plate doesn't exceed the quantity that must still be received.</span></span>

<span data-ttu-id="d9b22-142">Másik lehetőségként, ha túl sok rendszámtábla jön létre a bejövő rendelés regisztrációja során, az **Azonosítótábla-csoportosítási házirend** mező értéke módosítható *Azonosítótábla csoportosítása* értékre, új egységszekvencia-csoport rendelhető a cikkhez, vagy inaktiválni lehet az **Azonosítótábla csoportosítása** beállítást az egységszekvencia-csoportnál.</span><span class="sxs-lookup"><span data-stu-id="d9b22-142">Alternatively, if too many license plates are being generated on inbound order registration, the value of the **License plate grouping policy** field can be changed to *License plate grouping*, a new unit sequence group can be assigned to the item, or the **License plate grouping** option for the unit sequence group can be inactivated.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
