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

Egy új bejövő rakománykezelési funkció, a *Rakománymennyiségek túlbevételezése* megoldja ezt a problémát. A funkció bekapcsolásához, menjen a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) munkaterületre, és kapcsolja be a következő funkciókat (ebben a sorrendben):

1. Beszerzési rendelés készlettranzakcióinak társítása rakománnyal
1. Rakománymennyiségek túlbevételezése

További információ: [A regisztrált termékmennyiségek feladása a beszerzési rendelésekkel szemben](inbound-load-handling.md#post-registered-quantities).

## <a name="when-i-register-inbound-orders-i-receive-the-following-error-message-the-quantity-is-not-valid"></a>Bejövő rendelések regisztrálásakor a következő hibaüzenet jelenik meg: "A mennyiség érvénytelen."

### <a name="issue-description"></a>Probléma leírása

Ha az **Azonosítótábla-csoportosítási házirend** mező beállítása *Felhasználó által meghatározott* egy olyan mobileszköz-menüelem esetén, amellyel bejövő rendeléseket regisztrálnak, hibaüzenet jelenik meg („A mennyiség érvénytelen”), és a regisztráció nem fejezhető be.

### <a name="issue-cause"></a>Probléma oka

Ha azonosítótábla-csoportosítási házirendként *Felhasználó által meghatározott* van beállítva, a rendszer e bejövő készletet külön azonosítótáblákra bontja az egységszekvencia-csoport alapján. Ha köteg- vagy sorozatszámokat használ a fogadott cikk nyomon követéséhez, az egyes kötegek vagy sorozatok mennyiségét a regisztrált azonosítótáblánként kell megadni. Ha az azonosítótáblához megadott mennyiség meghaladja az aktuális dimenziókhoz még beérkeztetni kívánt mennyiséget, hibaüzenet jelenik meg.

### <a name="issue-resolution"></a>Probléma megoldása

Ha egy elemet olyan mobileszköz-menüelem használatával regisztrál, amelyben az **Azonosítótábla-csoportosítási házirend** mező értéke *felhasználó által meghatározott*, előfordulhat, hogy a rendszer kéri az azonosítótábla-számok, kötegszámok vagy sorozatszámok megerősítését vagy megadását.

Az azonosítótábla-visszaigazoló oldalon a rendszer az aktuális azonosítótáblához lefoglalt mennyiséget mutatja. A köteg vagy sorozat megerősítési oldalain a rendszer megmutatja azt a mennyiséget, amelyet még meg kell kapnia az aktuális azonosítótáblán. Ez magában foglal egy mezőt is, ahol megadhatja az azonosítótábla- és a köteg- vagy sorozatszám kombinációjához regisztrálandó mennyiséget. Ebben az esetben győződjön meg arról, hogy az azonosítótáblához regisztrált mennyiség nem haladja meg a még beérkeztetni kívánt mennyiséget.

Másik lehetőségként, ha túl sok rendszámtábla jön létre a bejövő rendelés regisztrációja során, az **Azonosítótábla-csoportosítási házirend** mező értéke módosítható *Azonosítótábla csoportosítása* értékre, új egységszekvencia-csoport rendelhető a cikkhez, vagy inaktiválni lehet az **Azonosítótábla csoportosítása** beállítást az egységszekvencia-csoportnál.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
