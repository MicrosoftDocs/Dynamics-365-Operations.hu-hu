---
title: Számlatükör tervezése
description: A cikk olyan információkat tartalmaz, melyek segítik önt számlatükröt tervezni szervezete számára.
author: aprilolson
ms.date: 04/02/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DimensionConfigureAccountStructure, LedgerChartOfAccounts
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14051
ms.assetid: 10edb129-33f0-4cf9-b2a7-4b7ffa09b229
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 10906d7b30628dfe69907cfa69ae1022fde33243
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/29/2022
ms.locfileid: "9070634"
---
# <a name="plan-your-chart-of-accounts"></a>Számlatükör tervezése

[!include [banner](../includes/banner.md)]

A cikk olyan információkat tartalmaz, melyek segítik önt számlatükröt tervezni szervezete számára.

A szervezet pénzügyi adatainak nyomon követésére és karbantartására számlatükröt állíthat be. A számlatükör a számlák összessége, amelyek meghatározzák a pénzügyi keretet. Ezeken a számlákon szereplő tranzakciók további követésére szegmenseket is hozzáadhat. Ezeket a szegmenseket pénzügyi dimenzióknak nevezik. Például egy költségszámla magába foglalhat olyan pénzügyi dimenziókat, mint a részleg, a költséghely és a cél. Felhasználó által definiált szabályok határozzák meg, hogyan kapcsolódnak ezek a pénzügyi dimenziók a fő számlákhoz és más pénzügyi dimenziókhoz, és hogyan lehet bevinni tranzakciókat. Ezek a felhasználó által megadott szabályokon számlastruktúrák és speciális szabályok néven ismertek.

A számlatükör a jogi személy főkönyvi számláinak rendszerezett felsorolása. A lista alapján lehet előkészíteni a pénzügyi jelentéseket a hatóságok és a tulajdonosok részére. A számlák elsősorban számlatípusok szerint vannak csoportosítva, és további nagyobb kategóriákba vannak gyűjtve. A legáltalánosabb szinten a számlák a bevétel- és költségszámlák (eredményszámlák) csoportjára, illetve az eszközök és források (mérlegszámlák) csoportjára vannak felosztva.

A Számlatükör osztva, és a szervezeten belüli olyan jogi személy által használt is. A jogi személy által használt számlatükör a **Főkönyv** oldalon van definiálva.

A szervezeti számlatükör szerkezetével kapcsolatos döntések meghozatalakor többek között a következő tényezőket kell figyelembe venni:

- Milyen jelentési kötelezettségek vannak érvényben abban az országban vagy régióban, ahol a szervezet működik?
- A jelentési kötelezettségeket a jogi személy
- Milyen szintű részletezést szükséges, mind külső szervezetek, mind a a szervezet számára

A számlatükröket a **Számlatükör** oldalon hozhatja létre. A fő számlákat a **Számlatükör** lapon vagy a **Fő számlák** oldalon hozhatja létre. A fő számlák nevében nem használható olyan speciális karakter, amely a számlatükörben elválasztójelként használ. Ellenkező esetben instabilitást tapasztalhat, vagy előfordulhat, hogy mindig lekérdezéseket vagy párbeszédpanelt kell használnia, amikor számlák és dimenziók kombinációit adja meg. További tudnivalókkal kapcsolatban lásd: [Fő számla létrehozása](tasks/create-main-account.md).

> [!NOTE]
> A Dynamics 365 Pénzügy 8.0-s verziójában (2018. április) **módosíthatja a számlatükr-elválasztót a Főkönyvi paraméterek lapon**.

Rendkívül hasznos lehet a fő számlákat összekapcsolni főszámla-kategóriákkal, így kiélvezheti az alapértelmezett pénzügyi jelentések előnyeit anélkül, hogy módosításokat kellene végrehajtania. Így gyorsaban és egyszerűbben tud jelentéseket tervezni és karbantartani.

Számlastruktúrákat a **Számlastruktúrák konfigurálása** oldalon hozhat létre. A számlastruktúrák határozzák meg az érvényes kombinációkat. Ezek a kombinációk, a fő számlákkal együtt, alkotják a számlatükröt. További tudnivalókkal kapcsolatban lásd: [Számlastruktúra létrehozása](tasks/create-account-structures.md).

**Jogi személy felülbírálásai**

Nem minden fő számla érvényes minden jogi személyre, esetenként egyes fő számlák csak egy adott időszakra vonatkoznak. Ebben az esetben a **Jogi személy felülbírálása** szakasz használható annak a megadására, hogy mely vállalatok számára kell felfüggeszteni a fő számlát, ki a tulajdonos, és mely időszakban aktív a dimenzió. A megosztott szinten történő felülbírálások nem lehet szigorúbban korlátozóak, mint a jogi személy szintjén történőek.

További információ a következő témakörökben olvasható:

- [Pénzügyi dimenziók](financial-dimensions.md)
- [Speciális szabálystruktúrák létrehozása és hozzárendelése](tasks/create-assign-advanced-rule-structures.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

