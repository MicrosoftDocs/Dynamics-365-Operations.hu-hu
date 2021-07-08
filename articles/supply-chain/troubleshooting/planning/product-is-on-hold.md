---
title: A termék várakoztatva van a tranzakcióknál
description: A tervezési rendelések megerősítése után olyan hibaüzenet jelenik meg, amely szerint egy cikk várakoztatva van a tranzakcióknál.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 6654e6437a088218db116b955631be4c7e62de5f
ms.sourcegitcommit: f9b145ef4a81cec81f420871b4130b05db4f4500
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2021
ms.locfileid: "6301279"
---
# <a name="product-is-on-hold-for-transactions"></a>A termék várakoztatva van a tranzakcióknál

Hibakód: SYS13295

## <a name="symptoms"></a>Tünetek

A tervezett rendelés megerősítése után a következő hibaüzenetet kapja:

> A(z) %1 cikk zárolva van a(z) %2 tranzakcióiban.

## <a name="cause"></a>Ok

A zárolt cikkek leírásában a *zárolt*, a *leállított* és a *várakoztatott* szó ugyanazt jelenti. Ez a hiba azt jelenti, hogy a cikk **Leállítottként** van beállítva az alapértelmezett rendelési beállításaiban.

Ha egy cikk zárolva van, de Ön felveszi egy beszerzési rendelésre vagy egy értékesítési rendelési sorba, figyelmeztető üzenet jelenik meg. Ha egy cikk zárolva van, akkor a beszerzési rendeléshez vagy az értékesítési rendelés sorához kapcsolódó készlettranzakciókat nem lehet módosítani (például szállítólevél vagy számla feladásakor). Lehetőség van arra, hogy egy beszerzett cikket zároljon, ugyanakkor mégis értékesítse. Ebben az esetben a **Leállítva** jelölőnégyzet be van jelölve a beszerzési rendelésen, de a cikk nincs zárolva van a készletben vagy egy értékesítési rendelésen.

Néhány olyan feltétel, amely egy adott számúa cikk eladásának zárolását okozhatja:

- A cikk még fejlesztés vagy gyártás alatt áll. Ezért nem szeretné, hogy eladják vagy lefoglalják.
- Több hibás cikket kapott, és a hibákat ki kell javítani, mielőtt a cikk eladható lenne.

Az ilyen típusú esetekben a cikkeket zárolni lehet a probléma megoldásáig.

Ha egy cikk zárolva van, és visszáru-rendelési sort hoz létre, akkor a rendszer üzenetet küld. A cikkek sorozatai és adagjai nem blokkolhatók. Ha egy cikk egy adott részét kell blokkolni, akkor blokkolhatja őket egy készletbe helyezve, vagy úgy, hogy az adott időszakra a cikk teljes készletét blokkolja.

## <a name="resolution"></a>Megoldás

- Nyissa meg az **Alapértelmezett rendelésbeállítások** oldalt a cikknél, és törölje a jelet a **Leállítva** jelölőnégyzetből.
