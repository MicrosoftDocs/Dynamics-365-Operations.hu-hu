---
title: Pénzügyi egyeztetés a kiskereskedelmi áruházakban
description: Ez a témakör bemutatja a pénzügyi egyeztetés a kiskereskedelmi áruházakban a Microsoft Dynamics 365 Commerce pénztára esetében.
author: anpurush
ms.date: 06/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-05-21
ms.dyn365.ops.version: ''
ms.openlocfilehash: 2afe967248136e9b658e1ee18053a54ab3f0d325c088a5eb2e522fac335c01f0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6752459"
---
# <a name="financial-reconciliation-in-retail-stores"></a>Pénzügyi egyeztetés a kiskereskedelmi áruházakban

[!include [banner](includes/banner.md)]

A Microsoft Dynamics 365 Commerce 10.0.10-es és korábbi verzióiban a pénztár (POS) ügyfél biztosítja a napivégi folyamatokat a kiskereskedelmi áruházakban, és így az eladók és az üzletvezetők végrehajthatják a napvégi teendőiket. Ilyenek lehetnek például a fizetőeszköz-elszámolások, a számlálás nélkül lezárt műszakok, a műszakbeli tranzakciók egyeztetése és a műszakok lezárása. Azonban a pénztárrendszer nem képes a műszakok pénzügyi adatainak véglegesítésére, hogy az felhasználható legyen a Commerce-központban a pénzügyek feladására. Ennek a feladatnak a végrehajtásáért általában az üzlet vezetői felelősek. A műszakból való kijelentkezés előtt ellenőrizniük kell az adatokat, módosítani kell a szükséges javításokat, és véglegesíteni kell a műszak összegeit. A véglegesített összegeket ezután a Commerce-központ pénzügyi moduljaiban kell feladni.

Ezenkívül a Commerce 10.0.10-es és korábbi verzióiban az üzletek vezetői ellenőrizhetik és módosíthatják a Commerce-központban a kimutatási sorait. A képesség azonban korlátozott, és az áruházi vezetők csak ritkán férhetnek hozzá a Commerce-központ ügyfeléhez. Ezenkívül a pénzforgalmi kimutatások áttekintése és helyesbítése csak akkor hajtható végre, ha a kimutatások a Commerce-központban jönnek létre. Ez a folyamat azonban általában éjszakai folyamat. Ezért az áruházak vezetőinek meg kell várniuk a műszak lezárását, amikor a Commerce-központban létrejönnek a pénzügyi kiskereskedelmi kimutatások.

A Commerce verzió 10.0.11-es és későbbi verzióiban az áruház vezetői megtekinthetik, módosíthatják és véglegesíthetik a műszakjaikat magában a pénztárügyfélben. Ezek az adatok a Commerce-központ pénzügyi kiskereskedelmi kimutatásainak létrehozására és feladására szolgálnak.

> [!NOTE]
> A kiskereskedelmi áruházakban a pénzügyi egyeztetéshez kapcsolódó funkciók csak akkor működnek, ha be van kapcsolva a hírcsatorna-alapú rendeléslétrehozás. További információk: [A rendelések folyamatos, apránkénti létrehozása a kiskereskedelmi áruház tranzakcióihoz](trickle-feed.md).

## <a name="set-up-financial-reconciliation"></a>Pénzügyi egyeztetés beállítása

A pénzügyi egyeztetési funkció használatához kövesse az alábbi lépéseket.

1. A **Funkciókezelés** munkaterületen kapcsolja be a **Kiskereskedelmi kimutatások – Folyamatos, apránkénti létrehozás** funkciót.
1. A megfelelő áruház pénztárfunkció profiljában állítsa be a **Pénzügyi egyeztetés engedélyezése az áruházban** beállítást **Igen** értékre.

## <a name="more-information-about-financial-reconciliation"></a>További információ a pénzügyi egyeztetésről

Amikor a pénzügyi egyeztetés funkció be van kapcsolva, a Commerce-központ **Kiskereskedelmi áruházak** oldalának **Kimutatás/zárás** gyorslapján definiált paraméterek egy része szinkronizálva van a csatorna-adatbázissal. A kiskereskedelmi kimutatásokhoz használt számítási feltételek és küszöbértékek ugyanezen készlete kerül érvényesítésre.

A **Műszakzárás** műveletének meghívásakor a rendszer ellenőrzi, hogy a rendszer által kiszámított összegek és a deklarált összegek egyeznek-e. Ha különböznek egymástól, és a különbség meghaladja a meghatározott küszöbértékeket, a program felkéri a felhasználót, aki elvégezheti a szükséges módosításokat.

Minden fizetőeszköznél korrekciót lehet végezni. Ha egy fizetőeszköz be van jelölve, akkor a felhasználó megtekintheti a különböző tranzakciótípusok összegeit, és szerkesztheti az adott tranzakciótípus összegeit. A szerkesztés során a rendszer megjeleníti az eredeti számított összeget és felülbírált összeget a tranzakciótípushoz. A felhasználó a szerkesztési folyamat részeként is rögzíthet jegyzeteket. A jegyzetek auditálási célokra használhatók.

A felhasználók figyelmen kívül hagyhatják az ellenőrzési figyelmeztetéseket és üzeneteket, és folytathatja a műszak lezárását. Ha azonban egy felhasználó figyelmen kívül hagyja az ellenőrzési figyelmeztetéseket, akkor ugyanezek a problémák lépnek fel, és ezeket javítani kell, amikor a műszak pénzügyi kimutatásokat küld a Commerce-központban.

A pénztár **Műszakzárás** művelete azt is ellenőrzi, hogy az offline adatbázis minden tranzakciója szinkronizálva van-e a csatorna-adatbázissal. Ha egy tranzakciót nem szinkronizálnak, a felhasználó figyelmeztető üzenetet kap, mivel ez a helyzet a rendszerben helytelenül számított összegeket eredményezhet. Ebben a helyzetben a felhasználó befejezheti a **Műszakzárás** műveletet, és megpróbálhatja szinkronizálni az offline tranzakciókat a csatorna-adatbázissal. Alternatív megoldásként a felhasználó manuálisan korrigálhatja a rendszer által kiszámított összegeket a szinkronizálatlan tranzakciók elszámolásához, így a megfelelő pénzügyi számok véglegesítése és feladása történik meg. 

Amikor a folyamatos, apránkénti kimutatásfeladás van használatban, így a tranzakciók feladása el van különítve a pénzügyek feladásától, akkor választhatja azt, hogy a hiányzó offline tranzakciók rendszer által kiszámított összegeit módosítja. Így biztosítható, hogy a pénzügyeket mindig elszámolja és feladja a program, a hiányzó tranzakcióktól függetlenül. Az offline tranzakciók szinkronizálhatók a csatorna-adatbázissal és a Commerce-központtal, majd később feladhatók a pénzügyi feladásoktól külön.

A műszak pénzügyi egyeztetésével kapcsolatos részletek a P-feladat segítségével szinkronizálhatók a Commerce-központtal.

A Commerce-központ pénzügyi kimutatásai nem számítják ki az összegeket a kimutatás soraiban szereplő részletek megjelenítéséhez. Helyette a pénztárügyfél véglegesített összegeit kell használni a pénzügyi kimutatások létrehozásához és feladásához.


[!INCLUDE[footer-include](../includes/footer-banner.md)]