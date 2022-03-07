---
title: Hely rakodási korlátai
description: Ez a témakör a hely készletezési korlátainak funkcionalitását írja le.
author: perlynne
ms.date: 11/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocationLimit
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-11-11
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 239b9fa8d8e34a92d453d3387881cff7b0a11f28a3c3b1e19891ea3bd78c3d7c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6714162"
---
# <a name="location-stocking-limits"></a>Hely rakodási korlátai

[!include [banner](../includes/banner.md)]

A **Helyek készletezési korlátai** oldal (**Raktárkezelés \> Beállítás \> Raktár \> Hely készletezési korlátai**) a tényleges termékek térfogatszámításához szükséges fejlettebb folyamatok használata nélkül alkalmas a raktári helyek rakodási kapacitásának szabályozására.

A hely készletezési korlátainak célja, hogy kiértékeljék azt a maximális mennyiséget, amelyet a hely tartalmazhat. A funkciót három szinten lehet beállítani, amelyek mindegyikének saját lapja van a **Hely készletezési korlátai** oldalon:

- Termékek
- Termékváltozatok
- Tárolótípusok

Minden szinthez különböző mezőértékeket lehet definiálni. A rendszer ezután egy adott hely kapacitását az egyes sorok **Mennyiség** és **Egység** értékeinek alapján értékeli. Először a legrészletesebb egyező rekordot fogja kiválasztani. Például egy olyan sort, amelynél szerepel egy érték a raktári **Helyprofil azonosítója** mezőben, a program csak a **Raktár** mezőben értékkel rendelkező sor előtt értékeli ki. A fennmaradó kapacitás is kiértékelésre kerül a használt helykészletezési korlát rekordjának **Mennyiség** értéke alapján.

Az oldal **Termékek** szakaszában a következő mezőértékeket határozhatja meg a hely készletezési korlátainak kereséséhez:

- Raktár
- Hely profilazonosítója
- Helyszín
- Csomagméret-kategóriaazonosító
- Cikkszám
- Egység

> [!NOTE]
> Nem kell **Egység** értéket megadnia az hely készletezési korlátja egyes rekordjaihoz. A hely kapacitásának számításaik a készletegység-mennyiségeken alapulnak. Ha a használt értékhez nincs egységátalakítás megadva, a hely készletezési korlátjának rekordja kimarad, mintha egy másik **Cikkszám** érték lenne megadva számára.

## <a name="example--purchase-order-receiving"></a>Példa – Beszerzésirendelés-sor bevételezése

Ez a példa egy tiszta *USMF* bemutató adatkészleten alapul, ahol a következő értékek vannak beállítva a **Hely készletezési korlátai** oldal **Termékváltozatok** lapján.

| Raktár | Hely profilazonosítója | Cikkszám | Méret | Mennyiség | Egység |
|-----------|---------------------|-------------|------|----------|------|
| 24        | SZINT               | D0013       | H    | 300      | Darab   |
| 24        | SZINT               | D0013       | L    | 240      | Darab   |
| 24        | SZINT               | D0013       | V    | 360      | Darab   |

A termékekhez különböző mértékegységű termékváltozatok vannak beállítva. Ezek a változatok három raklap (PL) helykészletezési korlátjához igazodnak:

- **M méret:** 1 PL = 100 darab (Ea)
- **L méret:** 1 PL = 80 Ea
- **S méret:** 1 PL = 120 Ea

Ezért minden olyan hely, ahol a **Helyprofil-azonosító** értéke *FLOOR*, *3* *PL* mennyiségű, *D0013* számú cikket hordozhat.

### <a name="prepare-for-the-example"></a>Felkészülés a példára

Ebben a példában két sor beszerzési rendelés bevételezési folyamatát futtatja. Azonban először frissítenie kell a bemutató adatokat a következő módon annak érdekében, hogy a helyek lehetővé tegyék a vegyes cikkeket, csak az *FL-002* – *FL-004* üres helyek kerüljenek használatra, és hogy ne legyen nyitott bejövő munka.

1. Az *FL-001* hely esetében módosítsa a **Helyprofil** mezőt *FLOOR* értékről *FLOOR-05* értékre.
1. A *FLOOR* helyprofilnál állítsa a **Vegyes elemek engedélyezése** beállítást *Igen* értékre.
1. Hozzon létre egy beszerzési rendelési sort a következő két sorral.

    | Raktár | Cikkszám | Méret | Mennyiség | Egység |
    |-----------|-------------|------|----------|------|
    | 24        | D0013       | V    | 4        | PL   |
    | 24        | D0013       | L    | 4        | PL   |

### <a name="process-the-example"></a>Példa feldolgozása

Először *4* egység *PL* mennyiséget kap *S* méretben, és áttekinti a létrehozott munka betárolási sorhelyeit. Ezután *4* egység *PL* mennyiséget kap *L* méretben, és áttekinti a létrehozott munka betárolási sorhelyeit.

1. A Raktárkezelés mobilalkalmazásban a *24*-es felhasználói azonosító és az *1* jelszó használatával jelentkezzen be.
1. Válasza a **Bejövő** \> **Beszerzés fogadása** elemet.
1. Vételezzen be *4* *PL* mennyiséget a *D0013* számú cikkből *S* méretben.
1. Tekintse át a létrehozott betárolási munkát. A következő eredményt kell látnia:

    - 3 PL -\> FL-002
    - 1 PL -\> FL-003

1. Vételezzen be *4* *PL* mennyiséget a *D0013* számú cikkből *L* méretben.
1. Tekintse át a létrehozott betárolási munkát. A következő eredményt kell látnia:

    - 1 PL -\> FL-003
    - 3 PL -\> FL-004

Az eredmények alapján arra a következtetésre juthat, hogy a rendszer nem tudta lefoglalni a megfelelő betárolási helyeket. Ellenkező esetben, a rendszer miért ad hozzá csak *1* *PL* mennyiségű *L* méretet az *FL-003* helyre az utolsó lépésben, nem pedig *2* *PL* mennyiséget? Ez azt jelenti, hogy nincs összesen *3* *PL* betároláshoz azon a helyen?

A látszólagos hiba magyarázatához meg kell értenie a helykészletkorlátok kiválasztási kritériumait. A rendszer a legrészletesebb egyező rekordot fogja kiválasztani. Ebben a példában a legrészletesebb egyező rekord az a sor, ahol a **Méret** érték *L*, a **Mennyiség** érték *240*, az **Egység** érték pedig *Ea*. Mivel már van nyitott munkája a *120* *Ea* *S* méretű mennyiségben, a fennmaradó kapacitás *240* – *120* = *120* *Ea*. Ezért a fennmaradó kapacitás csak *1* *PL* *80* *Ea*-t képes hordozni.

> [!NOTE]
> A helykészletezési korlátok nem használhatók például ugyanazon a helyen különböző mennyiségben lévő cikkek feltöltésének szabályozására. Ebben az esetben használjon *feltöltési sablont*.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]