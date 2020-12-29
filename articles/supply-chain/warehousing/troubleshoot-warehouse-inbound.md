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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 60b6e37ec9d716f635c2d25374ac25a82286660e
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645972"
---
# <a name="troubleshoot-inbound-warehouse-operations"></a>Bejövő raktári műveletek – hibaelhárítás

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben a bejövő raktári műveleteket végzi a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban.

## <a name="i-receive-the-following-error-message-quality-order-1-has-been-generated-cluster-profile-could-not-be-found-please-check-your-configuration"></a>A következő hibaüzenet jelenik meg: „Minőségi rendelés %1 lett létrehozva. A fürtprofil nem található, ellenőrizze a konfiguráció.”

### <a name="issue-description"></a>Probléma leírása

Ez a hibaüzenet egy olyan fogadási folyamathoz kapcsolódik, ahol a minőségirányítás (QMS) be van kapcsolva. A környezet konfigurációjától függően a hibaüzenetet generáló tranzakció további részletei segíthetnek a probléma megoldásában.

### <a name="issue-resolution"></a>Probléma megoldása

Először tekintse át a [fürtkitárolási](set-up-cluster-picking.md) beállítást, és győződjön meg arról, hogy a fürtprofilok megfelelően vannak beállítva. A fürtprofilok beállítása nem használható mobileszköz-menüelem fürtkitároláshoz. A környezettől függően előfordulhat, hogy más kapcsolódó konfigurációkat is át kell tekintenie.

## <a name="mixed-license-plate-receiving-doesnt-work-for-any-disposition-code-except-credit"></a>A vegyes azonosítótábla-fogadás nem működik semmilyen intézkedési kódnál, kivéve a Jóváírást.

### <a name="issue-description"></a>Probléma leírása

Ha egy intézkedési kód **Művelet** mezőjének beállítása *Jóváírás* vagy *Selejt*, akkor csak a [Vegyes azonosítótábla bevételezése](mixed-license-plate-receiving.md) menüpontot használhatja a visszaküldött elemek feldolgozásához.

### <a name="issue-resolution"></a>Probléma megoldása

A Microsoft kiértékelte ezt a hibát, és megállapította, hogy ez egy funkciókorlátozás. Jelenleg csak azok az [intézkedési kódok](../service-management/set-up-disposition-codes.md) támogatottak a vegyes azonosítótábla fogadása esetén, ahol a **Művelet** mező *Jóváírás* vagy *Selejt*.

## <a name="when-i-run-the-update-product-receipts-periodic-task-unconfirmed-purchase-orders-are-confirmed"></a>A Termékbevételezések frissítése időszakos feladat futtatásakor a meg nem erősített beszerzési rendelések megerősítést nyernek.

### <a name="issue-description"></a>Probléma leírása

A *Termékbevételezések frissítése* időszakos feladat futtatása után a rendszer automatikusan megerősíti a *Regisztrált* készlettranzakciós állapotú meg nem erősített beszerzési rendeléseket.

### <a name="issue-resolution"></a>Probléma megoldása

Egy új bejövő rakománykezelési funkció, a *Rakománymennyiségek túlbevételezése* megoldja ezt a problémát. Kapcsolja be ezt a funkciót, menjen a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) lehetőségre, és kapcsolja be a következő funkciókat (ebben a sorrendben):

1. Beszerzési rendelés készlettranzakcióinak társítása rakománnyal
1. Rakománymennyiségek túlbevételezése

További információ: [A regisztrált termékmennyiségek feladása a beszerzési rendelésekkel szemben](inbound-load-handling.md#post-registered-quantities).
