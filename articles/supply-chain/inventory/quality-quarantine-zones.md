---
title: A szabálytalanságok karanténzónái
description: Ez a témakör azt ismerteti, hogyan lehet karanténzónákat létrehozni és használni szabálytalanságok esetén.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventQuarantineZone
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2e556d2aa078a76ff4f81b6763535c38ce1cca0e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8857706"
---
# <a name="quarantine-zones-for-nonconformances"></a>A szabálytalanságok karanténzónái

[!include [banner](../includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet karanténzónákat létrehozni és használni szabálytalanságok esetén.

A **Karanténzónák** képernyőn meghatározhatja azokat a zónákat, amelyek a szabálytalanságokhoz társíthatók. Szabálytalanság létrehozása esetén beállíthatja a **Karanténzóna** és **Karanténtípus** mezőket az **Általános fülön** a **Szabálytalansásgok** lapon. A **Karanténzóna** mező általában azt a területet vagy helyet jelzi, ahol a cikk található. A **Karanténtípus** mező *Korlátozottan használható* vagy *Használhatatlanként* értékkel határozza meg a cikket.

Szabálytalanságra vonatkozó szabálytalansági vagy javítási jelentés nyomtatása esetén megtekintheti, hogy a cikk melyik karanténzónában található.

Szabálytalanságra vonatkozó szabálytalanságcímkét is nyomtathat. Ez a jelentés megmutatja a hozzárendelt karanténzónát, és a használattal kapcsolatos információkat, hogy iránymutatást adjon a hibás anyag kezelésére vonatkozóan. A karanténzónák egyes esetekben megfelelhetnek bizonyos készletezési helyeknek vagy üzemi erőforrásoknak.

## <a name="examples-of-quarantine-zones"></a>Karanténzónák – példák

### <a name="example-1"></a>1. példa

Egy elektronikai gyártóvállalatnál dolgozik, amely televízókat, hangszórókat és médialejátszókat gyárt. Ebben az esetben karanténzónát konfigurálhat, amelyek az egyes terméktípusokat képviselik.

### <a name="example-2"></a>2. példa

A nem megfelelő cikkek tárolására három rekesz és két állvány használható. Ebben az esetben öt karanténzónát konfigurálhat, mindegyik rekeszhez és állványhoz egyet.

## <a name="create-a-quarantine-zone"></a>Hozzon létre egy új karanténzónát

1. Ugorjon a **Készletkezelés \> Beállítás \> Minőségkezelés \> Karanténzónák** pontra.
1. A műveleti ablakpanelen válassza ki az **Új** lehetőséget, ha hozzá szeretne adni egy sort a rácshoz. Ezután új sorhoz állítsa be a következő mezőket:

    - **Karanténzóna** – Adjon meg egy egyedi azonosítót vagy nevet a karanténzóna számára.
    - **Leírás** – Adja meg a karanténzóna részletes leírását.

1. Zárja be a lapot.

## <a name="additional-resources"></a>További erőforrások

- [Minőségkezelés áttekintése](quality-management-processes.md)
- [A minőség- és a szabálytalanságkezelés engedélyezése](enable-quality-management.md)
- [A szabálytalanságok jóváhagyásáért felelős dolgozók](quality-responsible-workers.md)
- [A szabálytalanságok problématípusai](quality-quarantine-zones.md)
- [A szabálytalanságok diagnosztikai típusai](quality-diagnostic-types.md)
- [Szabálytalanságok minőségi költségei](quality-charges.md)
- [Műveletek szabálytalanságokhoz kapcsolódóan](quality-operations.md)
- [Raktári folyamatok minőségkezelése](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
