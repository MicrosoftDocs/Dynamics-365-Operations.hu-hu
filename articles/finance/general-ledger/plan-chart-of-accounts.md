---
title: Számlatükör tervezése
description: A témakör olyan információkat tartalmaz, melyek segítik önt számlatükröt tervezni szervezete számára.
author: aprilolson
manager: AnnBe
ms.date: 04/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionConfigureAccountStructure, LedgerChartOfAccounts
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14051
ms.assetid: 10edb129-33f0-4cf9-b2a7-4b7ffa09b229
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 007b634c18ce897160aea38e05c9a73a64dd3917
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444058"
---
# <a name="plan-your-chart-of-accounts"></a>Számlatükör tervezése

[!include [banner](../includes/banner.md)]

A témakör olyan információkat tartalmaz, melyek segítik önt számlatükröt tervezni szervezete számára.

A szervezet pénzügyi adatainak nyomon követésére és karbantartására számlatükröt állíthat be. A számlatükör a számlák összessége, amelyek meghatározzák a pénzügyi keretet. Ezeken a számlákon szereplő tranzakciók további követésére szegmenseket is hozzáadhat. Ezeket a szegmenseket pénzügyi dimenzióknak nevezik. Például egy költségszámla magába foglalhat olyan pénzügyi dimenziókat, mint a részleg, a költséghely és a cél. Felhasználó által definiált szabályok határozzák meg, hogyan kapcsolódnak ezek a pénzügyi dimenziók a fő számlákhoz és más pénzügyi dimenziókhoz, és hogyan lehet bevinni tranzakciókat. Ezek a felhasználó által megadott szabályokon számlastruktúrák és speciális szabályok néven ismertek.

A számlatükör a jogi személy főkönyvi számláinak rendszerezett felsorolása. A lista alapján lehet előkészíteni a pénzügyi jelentéseket a hatóságok és a tulajdonosok részére. A számlák elsősorban számlatípusok szerint vannak csoportosítva, és további nagyobb kategóriákba vannak gyűjtve. A legáltalánosabb szinten a számlák a bevétel- és költségszámlák (eredményszámlák) csoportjára, illetve az eszközök és források (mérlegszámlák) csoportjára vannak felosztva.

A Számlatükör osztva, és a szervezeten belüli olyan jogi személy által használt is. A jogi személy által használt számlatükör a **Főkönyv** oldalon van definiálva.

A szervezeti számlatükör szerkezetével kapcsolatos döntések meghozatalakor többek között a következő tényezőket kell figyelembe venni:

- Milyen jelentési kötelezettségek vannak érvényben abban az országban vagy régióban, ahol a szervezet működik?
- A jelentési kötelezettségeket a jogi személy
- Milyen szintű részletezést szükséges, mind külső szervezetek, mind a a szervezet számára

A számlatükröket a **Számlatükör** oldalon hozhatja létre. A fő számlákat a **Számlatükör** lapon vagy a **Fő számlák** oldalon hozhatja létre. A fő számlák nevében nem használható olyan speciális karakter, amely a számlatükörben elválasztójelként használ. Ellenkező esetben instabilitást tapasztalhat, vagy előfordulhat, hogy mindig lekérdezéseket vagy párbeszédpanelt kell használnia, amikor számlák és dimenziók kombinációit adja meg. További tudnivalókkal kapcsolatban lásd: [Fő számla létrehozása](tasks/create-main-account.md).

> [!NOTE]
> A Dynamics 365 for Finance and Operations 8.0 verziójában (2018. április) a számlatükör elválasztóját a **Főkönyvi paraméterek** oldalon módosíthatja.

Rendkívül hasznos lehet a fő számlákat összekapcsolni főszámla-kategóriákkal, így kiélvezheti az alapértelmezett pénzügyi jelentések előnyeit anélkül, hogy módosításokat kellene végrehajtania. Így gyorsaban és egyszerűbben tud jelentéseket tervezni és karbantartani.

Számlastruktúrákat a **Számlastruktúrák konfigurálása** oldalon hozhat létre. A számlastruktúrák határozzák meg az érvényes kombinációkat. Ezek a kombinációk, a fő számlákkal együtt, alkotják a számlatükröt. További tudnivalókkal kapcsolatban lásd: [Számlastruktúra létrehozása](tasks/create-account-structures.md).

**Jogi személy felülbírálásai**

Nem minden fő számla érvényes minden jogi személyre, esetenként egyes fő számlák csak egy adott időszakra vonatkoznak. Ebben az esetben a **Jogi személy felülbírálása** szakasz használható annak a megadására, hogy mely vállalatok számára kell felfüggeszteni a fő számlát, ki a tulajdonos, és mely időszakban aktív a dimenzió. A megosztott szinten történő felülbírálások nem lehet szigorúbban korlátozóak, mint a jogi személy szintjén történőek.

További információ a következő témakörökben olvasható:

- [Pénzügyi dimenziók](financial-dimensions.md)
- [Speciális szabálystruktúrák létrehozása és hozzárendelése](tasks/create-assign-advanced-rule-structures.md)
