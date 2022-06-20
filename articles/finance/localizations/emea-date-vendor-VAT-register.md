---
title: Szállító áfatételjegyzékének dátuma
description: Ez a cikk a szállítói áfajegyzék dátumának engedélyezésére vonatkozó funkcióval kapcsolatban tartalmaz tájékoztatást.
author: anasyash
ms.date: 01/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.custom: intro-internal
ms.search.region: global
ms.author: anasyash
ms.search.validFrom: 2022-01-15
ms.dyn365.ops.version: AX 10.0.24
ms.openlocfilehash: b1368e0c7764bed42aa7549f36a6f4bcbb96eff4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8849776"
---
# <a name="date-of-vendor-vat-register"></a>Szállító áfatételjegyzékének dátuma

A Microsoft Dynamics 365 Pénzügy 10.0.24-es verziójában a **szállítói** számlákhoz új szállítói áfajegyzék-dátum mező érhető el. Ez a mező a beszerzés adóköteles készletének dátumát adja meg.

Az új mező engedélyezéséhez menjen a Funkciókezelés **munkaterületre,** **keresse meg és válassza a Szállítói áfajegyzék dátumának engedélyezése lehetőséget a szállítói számlák funkcióban,** majd válassza az Engedélyezés most lehetőséget.**·**

A szállítóktól beérkező számláknak két dátuma lehet: a számla szállítói dátumának és az adóköteles készlet dátumának (ez az a dátum, amikor a szállító az áfa fizetendő áfát felszámítani). Bizonyos helyzetekben ez a két dátum eltérő lehet.

A beszerzési számlák bejövő áfaösszegét levonhatja, és a számlát később, a korábban említett dátumtól eltérő dátumon felveheti a számla áfajelentéseibe. Ezt a dátumot a helyi törvények szabályokkal szabályják, amelyek bizonyos helyzetekben halasztott bejövő áfalevonásra vonatkoznak. Országonként vagy régiónként eltérő.

Egyes áfajelentések, [például](emea-cze-vat-declaration-tax-declaration-model.md#vat-control-statement) a Cseh Köztársaság áfaellenőrzési jelentései megkövetelik, hogy a beszerzési dokumentumokban jelenteni kell az adóköteles készlet dátumát. Ezt a dátumot úgy kell jelenteni, hogy az adóhatóság egyeztetni tudja az áfabevallást az ellen felek között.

A Pénzügy területen a következő mezőkben határozhat meg dátumokat:

- **Számla dátuma** – az a dátum, amikor a szállító kiállította a számlát.
- **Áfajegyzék dátuma** – a beszerzési számla áfaösszeg-levonásának dátuma.
- **Szállítói áfajegyzék dátuma** – a szállító adóköteles készletének dátuma.
- **Dokumentum fogadásának dátuma** – a számla fogadásának dátuma.

Ezek a mezők a következő lapokon szerepelnek:

- Szállítói számla
- Szállítói számlajegyzék
- Szállítói számla jóváhagyása
- Szállítói számla naplója

A szállítói számla feladása után **áttekintheti** **a számlanapló és a szállítói tranzakciók oldalának dátumát.**
