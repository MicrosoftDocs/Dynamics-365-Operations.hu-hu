---
title: Tárgyi eszközök értékmodellje és az értékcsökkenési könyv egyesítése
description: 'A korábbi kiadásokban két értékelési fogalom vonatkozott a tárgyi eszközökre - értékmodellek és értékcsökkenési könyvek. A Microsoft Dynamics 365 for Operations 1611-es kiadásában az értékmodell funkcióit és az értékcsökkenési könyv funkcióit egyetlen koncepció alapján egyesítették, ennek neve: könyv.'
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 221564
ms.assetid: 7c68eb7c-8b1a-4dd9-afb8-04b4040e305e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: a8e04f89673b3e0eb07e19aa1e14276f1f22c25b9aaabc91e2919892f74ed985
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6727983"
---
# <a name="fixed-asset-value-model-and-depreciation-book-merge"></a>Tárgyi eszközök értékmodellje és az értékcsökkenési könyv egyesítése

[!include [banner](../includes/banner.md)]

A korábbi kiadásokban két értékelési fogalom vonatkozott a tárgyi eszközökre - értékmodellek és értékcsökkenési könyvek. A Microsoft Dynamics 365 for Operations 1611-es kiadásában az értékmodell funkcióit és az értékcsökkenési könyv funkcióit egyetlen koncepció alapján egyesítették, ennek neve: könyv.

Az új könyvfunkciók korábbi értékmodellfunkción alapul, de magában foglal minden olyan funkciót, amelyek korábban csak az értékcsökkenési könyvekben szerepeltek. [![Tárgyi eszközök értékmodellje és az értékcsökkenési könyv funkciójának egyesítéséből származó könyv.](./media/fixed-assets.png)](./media/fixed-assets.png) Az egyesítésnek köszönhetően most már minden, tárgyi eszközhöz tartozó folyamathoz ugyanazokat az oldalakat, lekérdezéseket és jelentéseket használhatja. A jelen témakörben szereplő táblázatok az értékcsökkenési könyvek és értékmodellek korábbi funkcióit ismerteti, a könyvek új funkcióival együtt.

## <a name="setup"></a>Beállítás
Alapértelmezés szerint a könyvek adatokat szolgáltatnak a főkönyvnek (főkönyv) és a tárgyi eszközök analitikus naplójának. A könyveknek van egy új **továbbítás a főkönyvnek** opciójuk, amely lehetővé teszi a főkönyvi feladás tiltását, ahol a feladás csak a tárgyi eszközök analitikus naplójába történik. Ez a funkció az értékcsökkenési könyv korábbi feladási viselkedésére hasonlít. A naplónevek beállításához a "nincs" nevű új feladási réteg tartozik. A feladási réteg kifejezetten a tárgyieszköz-tranzakciókhoz került hozzáadásra. Ahhoz, hogy olyan könyvekhez végezzen feladást, amelyek nem végeznek feladást a főkönyvhöz, egy olyan naplónevet kell használnia, amelynél a feladási réteg beállítása **nincs**.

| &nbsp;                                           | Értékcsökkenés könyv               | Értékmodell                     | Könyv (új)                                              |
|--------------------------------------------------|---------------------------------|---------------------------------|---------------------------------------------------------|
| Feladás a főkönyvnek                                   | Soha                           | Mindig                          | Opcionális feladás a főkönyvnek                                |
| Feladási rétegek                                   | Nem alkalmazható                  | 3. Aktuális, műveletek és adó | 11: Aktuális, műveletek, adó, 7 egyéni réteg és "nincs" |
| Naplónevek                                    | Értékcsökkenés könyv - naplónevek | Főkönyv - Naplónevek              | Főkönyv - Naplónevek                                      |
| Származtatott könyvek                                    | Nem engedélyezett                     | Engedélyezett                         | Engedélyezett                                                 |
| Értékcsökkenési profil felülírása az eszköz szintjén | Engedélyezett                         | Nem engedélyezett                     | Engedélyezett                                                 |

## <a name="processes"></a>Folyamatok
A folyamatok most már egy közös lapot használnak. Egyes folyamatok csak akkor engedélyezettek, ha a **Feladás a főkönyvbe** beállítás **nem** a könyvbeállításokban.

| &nbsp;                                           | Értékcsökkenés könyv               | Értékmodell                     | Könyv (új)                                              |
|--------------------------------|---------------------------|---------------------|------------------------------------------|
| Tranzakció bevitele              | Értékcsökkenési könyv – napló | Tárgyieszköz-napló | Tárgyieszköz-napló                      |
| Rendkívüli értékcsökkenés             | Engedélyezett                   | Nem engedélyezett         | Engedélyezett                                  |
| Tranzakciók előzményeinek törlése | Engedélyezett                   | Nem engedélyezett         | Engedélyezve van, kivéve, ha a főkönyvnek végez feladást |
| Tömeges frissítés                    | Engedélyezett                   | Nem engedélyezett         | Engedélyezve van, kivéve, ha a főkönyvnek végez feladást |

## <a name="inquiries-and-reports"></a>Lekérdezések és jelentések
Minden könyvnél rendelkezésre állnak a lekérdezések és jelentések. Azok a jelentések, amelyek nem szerepelnek az alábbi táblázatban, korábban támogatták az értékcsökkenési könyveket és az értékmodelleket, és jelenleg továbbra is támogatnak minden könyvtípust. A **feladási réteg** mező is hozzá lett adva a jelentésekhez, így könnyebben azonosíthatók a tranzakciófeladások.

| &nbsp;                                           | Értékcsökkenés könyv               | Értékmodell                     | Könyv (új)                                              |
|---------------------------------------|--------------------------------|--------------------------|--------------------------|
| Lekérdezések                             | Értékcsökkenés könyv - tranzakciók | Tárgyieszköz-tranzakciók | Tárgyieszköz-tranzakciók |
| Tárgyi eszközök kimutatása                 | Nem engedélyezett                    | Engedélyezett                  | Engedélyezett                  |
| Tárgyi eszköz alapja                     | Engedélyezett                        | Nem engedélyezett              | Engedélyezett                  |
| Tárgyi eszköz negyedéven belüli felhasználhatósága | Engedélyezett                        | Nem engedélyezett              | Engedélyezett                  |

## <a name="upgrade"></a>Frissítés
A frissítési folyamat áthelyezi a meglévő beállításokat és a meglévő tranzakciókat az új könyv struktúrájának megfelelően. Az értékmodellek megmaradnak a jelenleg állapotukban, olyan könyvként, amely a főkönyvbe ad fel. Az értékcsökkenési könyvek azonban áthelyezésre kerülnek egy olyan könyv, amelynél a **feladása a főkönyvbe** opció beállítása **nem**. Az értékcsökkenési könyvhöz tartozó naplónevek átkerülnek a főkönyvi napló nevéhez, amelynél a feladási réteg beállítása **nincs**.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]