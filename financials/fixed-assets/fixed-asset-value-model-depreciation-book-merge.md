---
title: "Tárgyi eszközök értékmodellje és az értékcsökkenési könyv egyesítése"
description: "A korábbi kiadásokban a tárgyieszköz - értékmodellek és értékcsökkenés könyvek két értékelési fogalmak voltak. A Microsoft Dynamics 365 műveletek 1611 kiadásban az értékmodell funkcióval és értékcsökkenési könyv beolvadtak néven ismert könyv egy egységes fogalom."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 221564
ms.assetid: 7c68eb7c-8b1a-4dd9-afb8-04b4040e305e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 6c8c005c7f5ede54ce0b6c8114cac69e2551d467
ms.lasthandoff: 03/31/2017


---

# <a name="fixed-asset-value-model-and-depreciation-book-merge"></a>Tárgyi eszközök értékmodellje és az értékcsökkenési könyv egyesítése

A korábbi kiadásokban a tárgyieszköz - értékmodellek és értékcsökkenés könyvek két értékelési fogalmak voltak. A Microsoft Dynamics 365 műveletek 1611 kiadásban az értékmodell funkcióval és értékcsökkenési könyv beolvadtak néven ismert könyv egy egységes fogalom.

Az új könyvfunkciók korábbi értékmodellfunkción alapul, de magában foglal minden olyan funkciót, amelyek korábban csak az értékcsökkenési könyvekben szerepeltek. [![Könyv szerinti érték értékmodell és az értékcsökkenés könyv funkciók egyesítése,](./media/fixed-assets.png)](./media/fixed-assets.png) miatt az egyesítést használható lapok, lekérdezések és jelentések egységes rendszerét az összes tárgyi eszköz folyamat. A jelen témakörben szereplő táblázatok az értékcsökkenési könyvek és értékmodellek korábbi funkcióit ismerteti, a könyvek új funkcióival együtt.

## <a name="setup"></a>Beállítás
Alapértelmezés szerint a könyvek adatokat szolgáltatnak a főkönyvnek (főkönyv) és a tárgyi eszközök analitikus naplójának. A könyveknek van egy új **továbbítás a főkönyvnek** opciójuk, amely lehetővé teszi a főkönyvi feladás tiltását, ahol a feladás csak a tárgyi eszközök analitikus naplójába történik. Ez a funkció az értékcsökkenési könyv korábbi feladási viselkedésére hasonlít. A naplónevek beállításához a "nincs" nevű új feladási réteg tartozik. A feladási réteg kifejezetten a tárgyieszköz-tranzakciókhoz került hozzáadásra. Ahhoz, hogy olyan könyvekhez végezzen feladást, amelyek nem végeznek feladást a főkönyvhöz, egy olyan naplónevet kell használnia, amelynél a feladási réteg beállítása **nincs**.

|                                                  |                                 |                                 |                                                         |
|--------------------------------------------------|---------------------------------|---------------------------------|---------------------------------------------------------|
|                                                  | Értékcsökkenés könyv               | Értékmodell                     | Könyv (új)                                              |
| Feladás a főkönyvnek                                   | Soha                           | Mindig                          | Opcionális feladás a főkönyvnek                                |
| Feladási rétegek                                   | Nem alkalmazható                  | 3. Aktuális, műveletek és adó | 11: Aktuális, műveletek, adó, 7 egyéni réteg és "nincs" |
| Naplónevek                                    | Értékcsökkenés könyv - naplónevek | Főkönyv - Naplónevek              | Főkönyv - Naplónevek                                      |
| Származtatott könyvek                                    | Nem engedélyezett                     | Engedélyezett                         | Engedélyezett                                                 |
| Értékcsökkenési profil felülírása az eszköz szintjén | Engedélyezett                         | Nem engedélyezett                     | Engedélyezett                                                 |

## <a name="processes"></a>Folyamatok
A folyamatok most már egy közös lapot használnak. Egyes folyamatok csak akkor engedélyezettek, ha a **Feladás a főkönyvbe** beállítás **nem** a könyvbeállításokban.

|                                |                           |                     |                                          |
|--------------------------------|---------------------------|---------------------|------------------------------------------|
|                                | Értékcsökkenés könyv         | Értékmodell         | Könyv (új)                               |
| Tranzakció bevitele              | Értékcsökkenési könyv – napló | Tárgyieszköz-napló | Tárgyieszköz-napló                      |
| Rendkívüli értékcsökkenés             | Engedélyezett                   | Nem engedélyezett         | Engedélyezett                                  |
| Tranzakciók előzményeinek törlése | Engedélyezett                   | Nem engedélyezett         | Engedélyezve van, kivéve, ha a főkönyvnek végez feladást |
| Tömeges frissítés                    | Engedélyezett                   | Nem engedélyezett         | Engedélyezve van, kivéve, ha a főkönyvnek végez feladást |

## <a name="inquiries-and-reports"></a>Lekérdezések és jelentések
Minden könyvnél rendelkezésre állnak a lekérdezések és jelentések. Azok a jelentések, amelyek nem szerepelnek az alábbi táblázatban, korábban támogatták az értékcsökkenési könyveket és az értékmodelleket, és jelenleg továbbra is támogatnak minden könyvtípust. A **feladási réteg** mező is hozzá lett adva a jelentésekhez, így könnyebben azonosíthatók a tranzakciófeladások.

|                                       |                                |                          |                          |
|---------------------------------------|--------------------------------|--------------------------|--------------------------|
|                                       | Értékcsökkenés könyv              | Értékmodell              | Könyv (új)               |
| Lekérdezések                             | Értékcsökkenés könyv - tranzakciók | Tárgyieszköz-tranzakciók | Tárgyieszköz-tranzakciók |
| Tárgyi eszközök kimutatása                 | Nem engedélyezett                    | Engedélyezett                  | Engedélyezett                  |
| Tárgyi eszköz alapja                     | Engedélyezett                        | Nem engedélyezett              | Engedélyezett                  |
| Tárgyi eszköz negyedéven belüli felhasználhatósága | Engedélyezett                        | Nem engedélyezett              | Engedélyezett                  |

## <a name="upgrade"></a>Frissítés
A frissítési folyamat áthelyezi a meglévő beállításokat és a meglévő tranzakciókat az új könyv struktúrájának megfelelően. Az értékmodellek megmaradnak a jelenleg állapotukban, olyan könyvként, amely a főkönyvbe ad fel. Az értékcsökkenési könyvek azonban áthelyezésre kerülnek egy olyan könyv, amelynél a **feladása a főkönyvbe** opció beállítása **nem**. Az értékcsökkenési könyvhöz tartozó naplónevek átkerülnek a főkönyvi napló nevéhez, amelynél a feladási réteg beállítása **nincs**.


