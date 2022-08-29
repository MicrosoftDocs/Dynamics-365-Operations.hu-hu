---
title: Szállító áfatételjegyzékének dátuma
description: Ez a cikk a szállítói áfajegyzék dátumának engedélyezésére vonatkozó funkcióval kapcsolatban tartalmaz tájékoztatást.
author: AdamTrukawka
ms.date: 01/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: global
ms.author: atrukawk
ms.search.validFrom: 2022-01-15
ms.dyn365.ops.version: AX 10.0.24
ms.custom: intro-internal
ms.openlocfilehash: 4af770427f5b19eaf2a129b26d54aeacc6c2f148
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278278"
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
