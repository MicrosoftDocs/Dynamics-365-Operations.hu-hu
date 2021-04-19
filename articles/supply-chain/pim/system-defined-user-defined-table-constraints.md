---
title: Rendszer által meghatározott és Felhasználó által meghatározott táblázat megszorítások
description: 'Ez a cikk bemutatja a táblamegszorítások két típusát termékkonfigurációs modell összetevői esetén: felhasználó és rendszer által meghatározott. A táblamegszorítások az engedélyezett attribútumkombinációk mátrixait jelölik, hol minden sor a lehetséges attribútumértékek egy készletét határozza meg.'
author: cvocph
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PCTableConstraintAttachAttributeTree, PCTableConstraintColumnSystem, PCTableConstraintContentUserDef, PCTableConstraintDefinition, PCTableConstraintWizard
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19781
ms.assetid: 0a4ea930-b344-43a8-871e-d5cd077892c4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7ddc7b9f0ccaa787b2297a253a7fdd9de11e9eee
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5812681"
---
# <a name="system-defined-and-user-defined-table-constraints"></a>Rendszer által meghatározott és Felhasználó által meghatározott táblázat megszorítások

[!include [banner](../includes/banner.md)]

Ez a cikk bemutatja a táblamegszorítások két típusát termékkonfigurációs modell összetevői esetén: felhasználó és rendszer által meghatározott. A táblamegszorítások az engedélyezett attribútumkombinációk mátrixait jelölik, hol minden sor a lehetséges attribútumértékek egy készletét határozza meg.

A táblamegszorítások olyan attribútumok kombinációinak a mátrixát képviselik, melyek megengedettek az összetevőknek egy termék konfigurációs modellnél. A táblázat minden sora egy lehetséges attribútum értékhalmazt határoz meg. Két típusú megszorítást nevezhet meg egy termékkonfigurációs modell esetén:

-   **Kifejezés megszorítás** – Hozzon létre egy kifejezést, ami meghatározza az attribútumok közötti kapcsolatot így garantálva, hogy csak az összeegyeztethető értékek váljanak kiválaszthatóvá a termékkonfiguráció során.
-   **Táblamegszorítás** – Hozzon létre egy táblázatot, amely definiálja az összes kombinációt ami megengedett az attribútumok egy bizonyos halmazának. Két típusú táblamegszorítás elérhető: felhasználó által meghatározott táblamegszorítás és rendszer által meghatározott táblamegszorítás.

Ez a cikk bemutatja a felhasználó- és a rendszer által meghatározott táblamegszorításokat termékkonfigurációs modell összetevői esetén.

## <a name="user-defined-table-constraints"></a>Felhasználó által meghatározott táblamegszorítások
A felhasználó által meghatározott táblamegszorítás olyan típusú mátrix, amelyet arra használunk, hogy az attribútum típusok által meghatározott attribútum értékek kombinációit leírjuk. Például, ha hangszórókat gyárt létrehozhat oszlopokat a hangszóró borításának, illetve az elülső rácsnak a felhasználó által meghatározott táblamegszorításokkal. A hangszóró borítás attribútum típusának négy, az elülső rács attribútum típusának három értéke van. Így amennyiben nem használ megszorításokat 4 x 3 azaz 12 lehetséges kombináció létezik. Azonban ebben a példában csak hat kombináció megengedett, ahogy az alábbi táblázat is mutatja. Ez az információ a **Megengedett kombinációk** lapon **Táblamegszorítás szerkesztése** oldalon található.

| Hangszóró borítása | Elülső rács |
|----------------|-------------|
| Fekete          | Fekete       |
| Fekete          | Fém       |
| Tölgyfa            | Fekete       |
| Rózsafa       | Fehér       |
| Fehér          | Fekete       |
| Fehér          | Fehér       |

A felhasználó által meghatározott táblamegszorításokat a statikus beviteli táblázat határozza meg, amely ugyanúgy működik, mint egy vélemény megszorítás. A felhasználó által definiált táblamegszorítás használatának előnye, hogy a táblák könnyebben létrehozhatóak, értelmezhetőek és karbantarthatóak, mint a hosszú kifejezés megszorítások.

## <a name="system-defined-table-constraints"></a>Rendszer által meghatározott táblamegszorítások
A rendszer által definiált táblamegszorítás dinamikus leképezést hoz létre egy attribútum típus és a táblázat egy mezője között. Amikor egy termékkonfigurációs modell rendszer által meghatározott tábla megszorítást tartalmaz, a leképezés garantálja, hogy a táblázatban szereplő adatok jelenjenek meg az attribútum típusok értékei helyett. Ennek eredménye egy dinamikus megszorítás, mivel a táblázat elemei módosíthatóak (például más modulok által).  

Rendszer által definiált táblamegszorítás létrehozásakor válasszon ki egy táblázatot, tetszés szerint megadhatja a használni kívánt lekérdezést, majd társítsa az attribútum típusokat a kiválasztott táblázatban szereplő mezőkhöz. A mezőtípusoknak meg kell egyezniük az attribútum típusokkal.  

Mielőtt egy táblamegszorítás érvénybe lépne a termékkonfigurációs modellen, a táblamegszorítást tartalmaznia kell a modell összetevők egy megszorításának. Az eljárás az, hogy új megszorítást kell létrehozni. Ehhez válassza ki a táblázat megszorítás típusát, majd a táblázat megszorítás használni kívánt definícióját. Végül a táblamegszorítás összes mezőjének kapcsolódnia kell a termékkonfigurációs modell attribútumaihoz.

<a name="additional-resources"></a>További erőforrások
--------

[Termékkonfigurálási modellek áttekintése](product-configuration-models.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]