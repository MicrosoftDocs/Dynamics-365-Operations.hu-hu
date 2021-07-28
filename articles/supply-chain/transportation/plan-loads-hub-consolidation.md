---
title: Rakományok tervezése központösszevonás használatával – áttekintés
description: Ez a leírás ismerteti szállítmányok központi összesítését eltérő raktárakból származó termékek azonos vevőhöz való kiszállítása vagy eltérő szállítóktól származó termékek azonos raktárba való érkezése esetén.
author: MarkusFogelberg
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLoadPlanningWorkbench, WHSHistory, WHSLoadTable, WHSLoadPlanningListPage, TMSParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "92273"
- intro-internal
ms.assetid: d27b0926-a534-4caf-a2a3-acbc7c440bca
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2c53110f583feeb3ef77226fb57396cfc2988e9f
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2021
ms.locfileid: "6345306"
---
# <a name="plan-loads-using-hub-consolidation-overview"></a>Rakományok tervezése központösszevonás használatával – áttekintés

[!include [banner](../includes/banner.md)]

Ez a leírás ismerteti szállítmányok központi összesítését eltérő raktárakból származó termékek azonos vevőhöz való kiszállítása vagy eltérő szállítóktól származó termékek azonos raktárba való érkezése esetén.

A szállítmányok központi összesítése eltérő raktárakból származó termékek azonos vevőhöz való kiszállítása vagy eltérő szállítóktól származó termékek azonos raktárba való érkezése esetén lehet hasznos.

## <a name="building-loads"></a>Rakományok összeállítása
Központ-összevonás előtt engedélyeznie kell a **Átmozgatás tervezése** beállítást a **Szállításkezelési paraméterek** oldalon. Az összevonás számára létre kell hoznia központokat. Az alábbi diagram központ-összevonást ábrázol. Ebben az esetben különböző raktárakból származó vevői rendelések azonos vevőhöz kerülnek. Az alaprakományok vevői rendelések alapján jönnek létre a **Rakománytervező munkaterület** oldal használatával, a szokásos módon. A két rakomány központi összevonásához a vevőhöz való kiszállítás előtt a **Rakománytervező munkaterület** oldalon a **Szállítás** mezőben válassza ki a **Központ-összevonás** lehetőséget. Ha kijelöli minden rakomány helyes központját, a rakományok központja lesz a „lerakási” cél. Két „szállításigénylési sor” jelenik meg a **Készletek és igények** szakaszon a **Rakománytervező munkaterület** oldalon. Majd hozzáadhatja ezeket a sorokat egy új rakományhoz. Az új rakomány értékesítésirendelés-sorokkal fog rendelkezni, a központ „felvételi” cím lesz, A vevő pedig „lerakási” cél. A három rakomány díja és útvonala beállítható, mint bármely más rakományé. Bármelyik szállítmányozót választhatja rendszer által az egyes rakományokhoz javasoltak közül. [![Központ-összevonás.](./media/hubconsol.jpg)](./media/hubconsol.jpg) Többszörös átmozgatási rendelések esetén használhatja ugyanazt a módszert rakományok összesítéséhez. Ebben az esetben, az előző ábrán A vevő egy raktár. Másik lehetőségként több beszerzési rendelés rakományát összesítheti eltérő szállítóktól származó termékek azonos raktárba való érkezése esetén. Több, mint egy összevonás-központtal rendelkezhet és több, eltérő raktárakból származó rakományt összesíthet több központban. Az alaprakományok összeállítása és az központi összevonás használata után az új rakományokat az összevont szállításigénylési sorok használatával állítja össze. Majd állítsa be a rakomány díját és útvonalát.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]