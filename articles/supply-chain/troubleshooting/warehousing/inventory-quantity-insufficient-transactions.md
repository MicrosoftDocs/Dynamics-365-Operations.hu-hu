---
title: A készlet mennyisége nem frissül, mert nincs elég tranzakció
description: A -1%-os készletmennyiséget nem lehet frissíteni, mert a %2 tételhez nincs elég olyan készlettranzakció, amely a megadott dimenziókkal rendelkezik.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 88130a969039dd741c8ea4fbaabe81acf0e6fb6a
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476503"
---
# <a name="system-cant-update-inventory-quantity-because-of-insufficient-transactions"></a>A rendszer nem tudja frissíteni a készletmennyiséget, mert nincs elég tranzakció

## <a name="symptoms"></a>Tünetek

Ez a probléma akkor fordulhat elő, ha a rendszer nem tudja frissíteni a készlet mennyiségét, mivel nincs elég készlettranzakció a megadott dimenziókhoz. A következő hibaüzenetet kapja:

> „Készletmennyiség –%1 nem lehet frissíteni a cikkhez elégtelen készlettranzakciók miatt %2 a következő méretekkel: Méret=%3, Szí=%4, Kiegészítések=%5, Telephely=%6, Raktár=%7, Hely=%8, Készletállapot=Elérhető, Azonosítótábla=%9, Kötegszám=%10 referenciaazonosítónak %11 a tételazonosítóhoz %12.

## <a name="resolution"></a>Megoldás

Győződjön meg arról, hogy a készlettranzakciók ténylegesen nem foglalnak mennyiséget. Előfordulhat például, hogy ezek a tranzakciók nyitott minőségi rendelések, készletzároló rekordok vagy kimenő rendelések.
