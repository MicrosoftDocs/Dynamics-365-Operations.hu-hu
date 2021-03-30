---
title: Rakományok tervezése központösszevonás használatával – áttekintés
description: Ez a leírás ismerteti szállítmányok központi összesítését eltérő raktárakból származó termékek azonos vevőhöz való kiszállítása vagy eltérő szállítóktól származó termékek azonos raktárba való érkezése esetén.
author: MarkusFogelberg
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLoadPlanningWorkbench, WHSHistory, WHSLoadTable, WHSLoadPlanningListPage, TMSParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: 92273
ms.assetid: d27b0926-a534-4caf-a2a3-acbc7c440bca
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 87b599c953244109b56958c0fe02deedfa252973
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5205202"
---
# <a name="plan-loads-using-hub-consolidation-overview"></a>Rakományok tervezése központösszevonás használatával – áttekintés

[!include [banner](../includes/banner.md)]

Ez a leírás ismerteti szállítmányok központi összesítését eltérő raktárakból származó termékek azonos vevőhöz való kiszállítása vagy eltérő szállítóktól származó termékek azonos raktárba való érkezése esetén.

A szállítmányok központi összesítése eltérő raktárakból származó termékek azonos vevőhöz való kiszállítása vagy eltérő szállítóktól származó termékek azonos raktárba való érkezése esetén lehet hasznos.

## <a name="building-loads"></a>Rakományok összeállítása
Központ-összevonás előtt engedélyeznie kell a **Átmozgatás tervezése** beállítást a **Szállításkezelési paraméterek** oldalon. Az összevonás számára létre kell hoznia központokat. Az alábbi diagram központ-összevonást ábrázol. Ebben az esetben különböző raktárakból származó vevői rendelések azonos vevőhöz kerülnek. Az alaprakományok vevői rendelések alapján jönnek létre a **Rakománytervező munkaterület** oldal használatával, a szokásos módon. A két rakomány központi összevonásához a vevőhöz való kiszállítás előtt a **Rakománytervező munkaterület** oldalon a **Szállítás** mezőben válassza ki a **Központ-összevonás** lehetőséget. Ha kijelöli minden rakomány helyes központját, a rakományok központja lesz a „lerakási” cél. Két „szállításigénylési sor” jelenik meg a **Készletek és igények** szakaszon a **Rakománytervező munkaterület** oldalon. Majd hozzáadhatja ezeket a sorokat egy új rakományhoz. Az új rakomány értékesítésirendelés-sorokkal fog rendelkezni, a központ „felvételi” cím lesz, A vevő pedig „lerakási” cél. A három rakomány díja és útvonala beállítható, mint bármely más rakományé. Bármelyik szállítmányozót választhatja rendszer által az egyes rakományokhoz javasoltak közül. [![Központ-összevonás](./media/hubconsol.jpg)](./media/hubconsol.jpg) Többszörös átmozgatási rendelések esetén használhatja ugyanazt a módszert rakományok összesítéséhez. Ebben az esetben, az előző ábrán A vevő egy raktár. Másik lehetőségként több beszerzési rendelés rakományát összesítheti eltérő szállítóktól származó termékek azonos raktárba való érkezése esetén. Több, mint egy összevonás-központtal rendelkezhet és több, eltérő raktárakból származó rakományt összesíthet több központban. Az alaprakományok összeállítása és az központi összevonás használata után az új rakományokat az összevont szállításigénylési sorok használatával állítja össze. Majd állítsa be a rakomány díját és útvonalát.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]