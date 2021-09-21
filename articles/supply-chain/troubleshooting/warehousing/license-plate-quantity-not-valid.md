---
title: A mennyiség nem érvényes bejövő rendelések regisztrálása esetén
description: 'Ha az azonosítótáblához osztott mennyiség meghaladja az aktuális dimenziókhoz még beérkeztetni kívánt mennyiséget, hibaüzenet jelenik meg: „A mennyiség nem érvényes.”'
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 5099b320447bf59c72f5017564ea660f19c690a5
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476592"
---
# <a name="license-plate-quantity-is-not-valid-when-registering-inbound-orders"></a>Az azonosítótábla mennyisége nem érvényes bejövő rendelések regisztrálása esetén

## <a name="symptoms"></a>Tünetek

Amikor bejövő rendeléseket regisztrál, a következő hibaüzenetet kaphatja:

> A mennyiség nem érvényes.

Ha az **Azonosítótábla-csoportosítási házirend** mező beállítása *Felhasználó által meghatározott* egy olyan mobileszköz-menüelem esetén, amellyel bejövő rendeléseket regisztrálnak, ez a hibaüzenet jelenik meg, és a regisztráció nem fejezhető be.

## <a name="cause"></a>Ok

Ha azonosítótábla-csoportosítási házirendként *Felhasználó által meghatározott* van beállítva, a rendszer e bejövő készletet külön azonosítótáblákra bontja az egységszekvencia-csoport alapján. Ha köteg- vagy sorozatszámokat használ a fogadott cikk nyomon követéséhez, az egyes kötegek vagy sorozatok mennyiségét a regisztrált azonosítótáblánként kell megadni. Ha az azonosítótáblához megadott mennyiség meghaladja az aktuális dimenziókhoz még beérkeztetni kívánt mennyiséget, hibaüzenet jelenik meg.

## <a name="resolution"></a>Megoldás

Ha egy elemet olyan mobileszköz-menüelem használatával regisztrál, amelyben az **Azonosítótábla-csoportosítási házirend** mező értéke *felhasználó által meghatározott*, előfordulhat, hogy a rendszer kéri az azonosítótábla-számok, kötegszámok vagy sorozatszámok megerősítését vagy megadását.

Az azonosítótábla-visszaigazoló oldalon a rendszer az aktuális azonosítótáblához lefoglalt mennyiséget mutatja. A köteg vagy sorozat megerősítési oldalain a rendszer megmutatja azt a mennyiséget, amelyet még meg kell kapnia az aktuális azonosítótáblán. Ez magában foglal egy mezőt is, ahol megadhatja az azonosítótábla- és a köteg- vagy sorozatszám kombinációjához regisztrálandó mennyiséget. Ebben az esetben győződjön meg arról, hogy az azonosítótáblához regisztrált mennyiség nem haladja meg a még beérkeztetni kívánt mennyiséget.

Másik lehetőségként, ha túl sok rendszámtábla jön létre a bejövő rendelés regisztrációja során, az **Azonosítótábla-csoportosítási házirend** mező értéke módosítható *Azonosítótábla csoportosítása* értékre, új egységszekvencia-csoport rendelhető a cikkhez, vagy inaktiválni lehet az **Azonosítótábla csoportosítása** beállítást az egységszekvencia-csoportnál.
