---
title: Automatikus megerősítés a tervezési optimalizálással
description: Ez a témakör azt mutatja be, hogyan kell használni az automatikus megerősítést a tervezési optimalizációval.
author: ChristianRytt
manager: tfehr
ms.date: 11/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-11-30
ms.dyn365.ops.version: AX 10.0.7
ms.openlocfilehash: 61e9e6aa660bc0828645c6bf1f2655539804831a
ms.sourcegitcommit: 597476103bb695e3cbe6d9ffcd7a466400346636
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/20/2020
ms.locfileid: "4594526"
---
# <a name="autofirming-with-planning-optimization"></a>Automatikus megerősítés a tervezési optimalizálással

[!include [banner](../../includes/banner.md)]

Az automatikus megerősítéssel az Alaptervezési folyamat részeként megerősítheti (azaz kiadhatja) a tervezett rendeléseket. A tervezett rendelések a megerősítéskor tényleges beszerzési rendelésekké, átmozgatási rendelésekké vagy termelési rendelésekké alakulnak át. A tervezés optimalizálása használata során a program a tervezett rendeléseket az Alaptervezés futtatása során megerősíti, amikor a rendelés dátuma (azaz a kezdő dátum) a megerősítés időkorlátján belül van.

> [!NOTE]
> A tervezett beszerzési rendelés automatikus megerősítése csak akkor lehetséges, ha a cikk társítva van szállítóval.

## <a name="turn-on-autofirming"></a>Automatikus megerősítés bekapcsolása

Ha be szeretné kapcsolni az automatikus megerősítést, hajtsa végre az alábbi lépéseket.

1. A **funkciókezelés** munkaterületen az **új** lapon válassza ki a listában az **Automatikus megerősítés a tervezési optimalizációhoz** elemet. Ha a funkció nem jelenik meg az **új** lapon, akkor keresse a **nem engedélyezett és** az **Összes** lapon.
1. Válassza az **Engedélyezés most** lehetőséget. Azt is megteheti, hogy az **ütemezés** elemet választja, majd azt az időpontot, amikor be kívánja kapcsolni a szolgáltatást.

## <a name="set-up-the-firming-time-fence"></a>Állítsa be a megerősítési időkorlátot

A megerősítési időkorlátot a program az alaptervezés-futtatás dátumától kezdődően számítja ki. A megadott napok száma alapján kerül meghatározásra. A megerősítési időkorlátot a következő módokon lehet szabályozni:

- A fedezeti csoport alapértelmezett megerősítési időkorlátjának megadásához nyissa meg az **Alaptervezés** \> **Beállítás** \> **Fedezet** \> **Fedezeti csoportok**, és válasszon ki egy fedezeti csoportot. Ezután a **Egyéb** gyorslap **automatikus megerősítési időkorlátja (nap)** mezőjébe írja be a napok számát.
- Ha felül szeretné írni egy adott cikk fedezeti csoportjához definiált megerősítési időkorlátot, akkor a **Termékadatok kezelése** \> **Kiadott termékek** pontra lépjen, majd a Művelet panelen válassza ki a **Terv** elemet , majd válassza a **Cikk fedezete** elemet. Ezután az **Általános** lapon jelölje be az **Időkorlát felülbírálása** elemet, és az **automatikus megerősítés időkorlátja (nap)** mezőben adja meg a napok számát.
- Ha felül szeretné írni a fedezeti csoporthoz tartozó megerősítési időkorlátot és az adott alaptervezéshez tartozó cikkfedezetet, lépjen az **Alaptervezés** \> **Beállítás** \> **Alaptervek** pontra, és válasszon alaptervet. Ezután az **Időkorlát napokban** gyorslapon állítsa a **Megerősítés** értékét **Igen** értékre, majd adja meg a napok számát.

Ha az automatikus megerősítés be van kapcsolva egy olyan alaptervezéshez, amely tervezési optimalizációt alkalmaz, az automatikus megerősítési folyamat az automatikus megerősítési beállításnak megfelelően történik. Ha nincs bekapcsolva az automatikus megerősítés, vagy ha a tervezés a **nettó szükségletek** oldalon kezdődik, akkor a rendszer kihagyja az automatikus megerősítési folyamatot.

## <a name="planning-optimization-vs-the-built-in-supply-chain-management-planning-engine"></a>Tervezés optimalizálása és a beépített Supply Chain Management tervezési motorja

Mind a tervezés optimalizálása, mind a Microsoft Dynamics 365 Supply Chain Management szolgáltatásba beépített tervezési motor használható a tervezett rendelések automatikus megerősítésére. Vannak azonban fontos eltérések. Mivel például a tervezés optimalizálása a rendelési dátumot (azaz a kezdő dátumot) használja a megerősítendő tervezett rendelések meghatározásához, a beépített Supply Chain Management tervezési motor a követelmény dátumát (azaz a záró dátumot) használja. Itt van egy összefoglaló a különbségekről.

**Tervezési optimalizálás**

- Az automatikus megerősítés a rendelés dátuma (kezdő dátum) alapján történik.
- Mivel a rendelés dátuma (kezdő dátum) indítja a megerősítést, nem kell figyelembe vennie az átfutási időt a megerősítési időkorlát részeként.
- Ha az összes olyan rendelést meg szeretné erősíteni, amely az aktuális hét során kezdődik, a megerősítési időkorlátnak egy hétnek kell lennie.

**Beépített Supply Chain Management tervezési motor**

- Az automatikus megerősítés a követelmény dátuma (záró dátum) alapján történik.
- Ha biztosítani szeretné, hogy a rendelések megfelelő időben legyenek megerősítve, a megerősítés időtartamának hosszabbnak kell lennie, mint az átfutási idő.
- Ha az összes olyan rendelést meg szeretné erősíteni, amely az aktuális hét során kezdődik, a megerősítési időkorlátnak az átfutási idő plusz egy hétnek kell lennie.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]