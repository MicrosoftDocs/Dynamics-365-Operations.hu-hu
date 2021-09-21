---
title: A sorok egyike már rakományban van
description: 'Ez a lap bemutatja, hogy miért kapta ezt a hibát: „A sorok egyike már egy rakományban van. Nem lehet kiadni raktárba.”, és hogyan oldható meg a probléma.'
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 0bdfaed005b9c58f7bd5f87dd6dffe648de47261
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476602"
---
# <a name="one-of-the-lines-is-already-on-a-load"></a>A sorok egyike már rakományban van

## <a name="symptoms"></a>Tünetek

A rakomány-összeállítással és szállítmányokkal kapcsolatos munka során a következő hibaüzenet jelenik meg:

> A sorok egyike már rakományban van. Nem lehet kiadni a raktárba.

Ha manuálisan hoz létre rakományokat, vagy úgy állítja be a folyamatot, hogy a rakományok már az értékesítésrendelési sor bevitele előtt létrejönnek, akkor azt feltételezi a rendszer, hogy a későbbi kiadás manuálisan történik, és a rakományból származó útvonal és minősítés lesz használva.

Egy másik lehetséges forgatókönyv, hogy automatikus kiadást próbál végezni a raktárba, de a hullámfolyamat nem tud munkát létrehozni. Ezért egy nyitott szállítmány vagy rakomány továbbra is létrejön. Ez a nyitott szállítmány vagy betöltés letiltja a rendelés automatikus kiadására irányuló későbbi kísérleteket, amíg nem törli a nyitott szállítmányt vagy betöltést, vagy manuálisan fel nem dolgozza a hullámot.

## <a name="resolution"></a>Megoldás

Az értékesítési rendelés lapról kiadhatja, vagy az automatikus kiadást eszközölhet a kiadás értékesítési rendelés lapról, csakis akkor, ha nincs rakomány a raktárba történő kiadás előtt. A rakomány automatikusan létrejön a hullám feldolgozása után.
