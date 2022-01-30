---
title: Szállító áfatételjegyzékének dátuma
description: Ez a témakör a szállítói áfajegyzék dátumának engedélyezésével kapcsolatos funkciókkal kapcsolatban tartalmaz tájékoztatást.
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
ms.openlocfilehash: 882d5a8718d819cff80bfa5b86e054a39e9db159
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2022
ms.locfileid: "7991729"
---
# <a name="date-of-vendor-vat-register"></a>Szállító áfatételjegyzékének dátuma

A Microsoft Dynamics 365 Finance 10.0.24-es verziójában a szállítói számlákhoz új Szállítói áfajegyzék dátuma mező **érhető** el. Ez a mező a beszerzés adóköteles készletének dátumát adja meg.

Az új mező engedélyezéséhez menjen a Funkciókezelés munkaterületre, keresse meg és válassza a Szállítói áfajegyzék dátumának engedélyezése lehetőséget a szállítói számlák funkcióban, majd válassza az **Engedélyezés** most **·** **lehetőséget**.

A szállítóktól beérkező számláknak két dátuma lehet: a számla szállítói dátumának és az adóköteles készlet dátumának (ez az a dátum, amikor a szállító az áfa fizetendő áfát felszámítani). Bizonyos helyzetekben ez a két dátum eltérő lehet.

A beszerzési számlák bejövő áfaösszegét levonhatja, és a számlát később, a korábban említett dátumtól eltérő dátumon felveheti a számla áfajelentéseibe. Ezt a dátumot a helyi törvények szabályokkal szabályják, amelyek bizonyos helyzetekben halasztott bejövő áfalevonásra vonatkoznak. Országonként vagy régiónként eltérő.

Egyes áfajelentések, például a Cseh Köztársaság áfaellenőrzési jelentései megkövetelik, hogy a beszerzési dokumentumokban jelenteni kell az adóköteles [készlet](emea-cze-vat-declaration-tax-declaration-model.md#vat-control-statement) dátumát. Ezt a dátumot úgy kell jelenteni, hogy az adóhatóság egyeztetni tudja az áfabevallást az ellen felek között.

A Pénzügy területen a következő mezőkben határozhat meg dátumokat:

- **Számla dátuma** – az a dátum, amikor a szállító kiállította a számlát.
- **Áfajegyzék dátuma – a beszerzési számla** áfaösszeg-levonásának dátuma.
- **Szállítói áfajegyzék dátuma – a szállító** adóköteles készletének dátuma.
- **Dokumentum fogadásának dátuma** – a számla fogadásának dátuma.

Ezek a mezők a következő lapokon szerepelnek:

- Szállítói számla
- Szállítói számlajegyzék
- Szállítói számla jóváhagyása
- Szállítói számla naplója

A szállítói számla feladása után áttekintheti a számlanapló és a szállítói **tranzakciók** **oldalának** dátumát.
