---
title: Termelési rendelés kiadásakor az RM cikk nem foglalható le
description: 'Termelési rendelés kiadása során a következő hiba jelenhet meg: "Az RM cikk nem foglalható le teljesen." Ellenőrizze, hogy a teljes mennyiség elérhető-e, vagy foglalja le a cikkeket manuálisan.'
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 528895252d661bb012f49190c15853989833064d
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476579"
---
# <a name="item-rm-cant-be-fully-reserved-when-a-production-order-is-released"></a>Termelési rendelés kiadásakor az RM cikk nem foglalható le teljesen.

## <a name="symptoms"></a>Tünetek

Ha a termelési rendelés raktárba való kiadásakor fizikailag nem minden anyagjegyzéksor-cikk érhető el, és a **Kiadás raktárba** irányelv *Teljes foglalás szükséges* értékre van állítva, akkor a következő hibaüzenet jelenik meg:

> Az RM cikk nem foglalható le teljesen. Győződjön meg arról, hogy a teljes mennyiség rendelkezésre áll, vagy foglalja le a cikkeket manuálisan, ha az anyagjegyzéksor Foglalás mezőjének beállítása Manuális vagy Elindítva értéken van. Nem sikerült kiadni a rendelést a raktárba, mert bizonyos anyagokat nem lehetett lefoglalni.

## <a name="resolution"></a>Megoldás

Ez a viselkedés szándékos, és a várt módon működik. A probléma megoldásához kövesse a hibaüzenetben megadott útmutatást: „Győződjön meg arról, hogy a teljes mennyiség elérhető, vagy foglalja le manuálisan a cikkeket, ha az anyagjegyzéksor Foglalás mezőjének beállítása Manuális vagy Elindítva.”
