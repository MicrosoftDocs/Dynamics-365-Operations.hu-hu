---
title: Az értékesítési rendelést nem lehetett kiadni kimenő raktári műveletekkel
description: Több oka is lehet annak, hogy miért kap olyan hibaüzenetet, hogy egy értékesítési rendelést nem lehet kiadni. Ez az oldal bemutatja, hogy miért és hogyan lehet mérsékelni a problémát.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: fca5ee1bc97545ea4de56d940fdedd320a6cfe84
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476567"
---
# <a name="sales-order-could-not-be-released-with-outbound-warehouse-operations"></a>Az értékesítési rendelést nem lehetett kiadni kimenő raktári műveletekkel.

## <a name="symptoms"></a>Tünetek

A kimenő raktári műveletekkel kapcsolatos munka során a következő hibaüzenet jelenik meg:

> Az értékesítési rendelés nem adható ki.

## <a name="cause"></a>Ok

Ez a hiba több okból is előfordulhat. Például a rendelés hitelkezelés várakozási listán van, és a rendszer nem hozhat létre szállítmányokat mindaddig, amíg a rendeléshez társított összes értékesítési sorhoz érvényes postai címet nem ír be. Azt is megteheti, hogy a rendelés várakoztatását a raktárba történő kiadás előtt megoldja. Ez a várakoztatás lehet rendeléssel vagy vevői fiókkal kapcsolatos.

## <a name="resolution"></a>Megoldás

Adja hozzá vagy frissítse a címet az értékesítési rendelés és a rendelési sorokban, majd adja ki a rendelést a raktárba. A rendelések csak akkor adhatók ki a raktárba, ha rendelkeznek érvényes szállítási címmel (a **Szervezet adminisztrációs** moduljának címformátumának beállításával).

Vizsgálja meg a rendelés visszatartását, és oldja meg a problémákat. Ezután távolítsa el a rendelésből vagy a vevőtől a várakoztatást, és adja ki a rendelést a raktárba.
