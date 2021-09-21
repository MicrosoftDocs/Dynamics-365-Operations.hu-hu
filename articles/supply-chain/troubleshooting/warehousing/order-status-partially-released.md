---
title: A rendelés állapota Részlegesen kiadott marad a számlázása után is
description: Bizonyos esetekben egy értékesítési rendelés kiadási állapota még az értékesítési rendelés számlázása után is részlegesként jelenik meg. Ez az oldal bemutatja, miért történik ez, valamint a lehetséges megoldást.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 8bfe7ecfd4beb6e77e8dd1e23ccd896d067bdb51
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476562"
---
# <a name="order-status-remains-partially-released-even-after-the-sales-order-is-invoiced"></a>A rendelés állapota Részlegesen kiadott marad az értékesítési rendelés számlázása után is

## <a name="symptoms"></a>Tünetek

Egy értékesítési rendelés szállítási rendelés, de egy vagy több cikknek más a szállítási módja. A rendelés számlázása után a program továbbra is *Részlegesen kiadott* kiadási állapotú.

Például egy értékesítési rendelésnek két eleme van: egy szállításra és egy kitárolásra. A szállítás és a kitárolás is megtörtént. Ennélfogva mindkét sor számlázva van. A kiadási állapot azonban továbbra is *Részleges kiadásként* jelenik meg, ami félrevezető.

## <a name="workaround"></a>Megkerülő megoldás

A kiadás állapota csak azokra a rendelési sorokra vonatkozik, amelyeknél a cikkek engedélyezve vannak a raktárkezelésben. Emiatt a kiadási állapot továbbra is *Részlegesen kiadott* marad ebben a forgatókönyvben. A Microsoft kiértékelte ezt a hibát, és megállapította, hogy ez egy funkciókorlátozás. A kiadási állapot frissítéséhez egy kiterjesztés adható a szállítólevél és a számlázási folyamat részeként.
