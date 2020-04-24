---
title: Anyagjegyzékek jelentése befejezettként
description: Ez a cikk az anyagjegyzékek befejezettként való jelentéséről tartalmaz információkat.
author: johanhoffmann
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMReportFinish, BOMReportFinishMax
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 53251
ms.assetid: 510d05a3-0073-438d-b0c4-b6a6df1882ea
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 62514833a80acff27d774f96150aa34b7eb081c7
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3211215"
---
# <a name="report-boms-as-finished"></a>Anyagjegyzékek jelentése befejezettként

[!include [banner](../includes/banner.md)]

Ez a cikk az anyagjegyzékek befejezettként való jelentéséről tartalmaz információkat.

A **jelentés készként** és **Max. készként jelentés** lapok használatosak az anyagjegyzékek (AJ) készként jelentéséhez. Fogalmi szintén az anyagjegyzék készként jelentésének folyamata ugyanaz, mint egy termelési rendelés készként jelentésének folyamata. Ez a folyamat használható például egyszerű összeállítási és kitting folyamatoknál, ahol a termelési rendelések fejlett funkcióira nincs szükség. A **Jelentés készként** lap lehetővé teszi, hogy több anyagjegyzéket kötegben jelentsen késznek. A **Max. készként jelentés** lap segítségével csak egy anyagjegyzék készként jelentése tehető meg egyszerre. A **készként jelentés** lap elérhető egy menüelemből a készletgazdálkodásban és mindkét lap elérhető menüelemekként a **kiadott termékek** lapon.

## <a name="report-as-finished-page"></a>Készként jelentés lap
Ha megnyitja a **készként jelentés**lapot egy kiadott termékből, akkor az oldal azt javasolja, hogy jelentse készként a normál készlet alapértelmezett mennyiségét. Alapértelmezés szerint az aktív anyagjegyzék-verzió megjelenik, de módosíthatja az anyagjegyzék verziót ha vannak egyéb jóváhagyott verziók. A lap azt is lehetővé teszi, hogy rekordokat töröljön, vagy új rekordokat hozzon létre a kiadott termékeknek, amelyeket készként kell jelenteni. Lekérdezés használatához a termékek kiválasztásakor kattintson a **Kiválasztás** menüelemre. Manuálisan megerősítheti a kijelölt termékek készként jelentését az **OK** gombra kattintva. Másik lehetőségként beállíthatja a folyamatot, hogy egy kötegben fusson. Amikor kész folyamatként jelentés megerősítésre került a rendszer létrehoz egy anyagjegyzék naplót, ahol az anyagjegyzékbe feladás feldolgozásra kerül. Ez a napló egy sortételből áll a késztermékhez és egy sortételből minden anyagjegyzéksorhoz. Beállíthatja, hogy a napló automatikusan feladásra kerül-e, vagy nyitva marad további módosításokhoz.

## <a name="max-report-as-finished-page"></a>Max. készként jelentés lap
A **Max. készként jelentés** lapon minden anyagjegyzék sor mutatja azon darabok számát, amelyeket készként lehet jelenteni. Ez a számítás a ténylegesen elérhető aktuális készleten alapul minden anyagsorhoz. A következő példában egy darab FG cikkszámú cikk felhasznál két darab RM10 nyersanyagot és egy darab RM20 nyersanyagot. Mivel csak 10 darab RM10 van készleten az FG maximális készként jelenthető mennyisége öt darab. Ez az érték szerepel a **Max. készként jelentés** mezőben.

| Szint | Cikkszám | Mennyiség | Aktuális készlet | Max. Készként jelentés |
|-------|-------------|----------|---------|-------------------------|
| 0     | FG          |  1       | 0       | 5                       |
| 1     | RM10        | -2       | 10      | 5                       |
| 1     | RM20        | -1       |  8      | 8                       |

## <a name="boms-that-have-multiple-levels"></a>Több szinttel rendelkező anyagjegyzékek
Amikor egy anyagjegyzék több szinttel rendelkezik minden szinten irányíthatja, hogy az anyagok hogyan vannak könyvelve az **Alábontás** mező használatával. Ez a mező elérhető mind a **készként jelentés** lapon és a **Max. készként jelentés** lapon. Az alábbi lehetőségek közül választhat:

-   **Soha** – A mögöttes anyagjegyzékek anyaghiány esetén nem kerülnek alábontásra.
-   **Mindig** – Minden mögöttes anyagjegyzék teljesen alábontásra kerül. Ezért a félkész összetevő cikkek aktuális szabad készlete nem kerül felhasználásra.
-   **Hiány** – A mögöttes anyagjegyzékek csak akkor kerülnek alábontásra, ha a kívánt termék teljes mennyisége nem áll rendelkezésre.

### <a name="example"></a>Példa

Ebben a példában három darab késztermék (FG cikkszám) készen áll, hogy készként jelentsék. Az anyagjegyzék két szintű, az alább látható módon.

| Szint | Cikkszám | Anyagjegyzék-sor mennyiség | Aktuális készlet |
|-------|-------------|-------------------|---------|
| 0     | FG          |                   |         |
| 1     | COMP        | 1                 | 2       |
| 1     | RM          | 1                 |         |

A következő táblázatok mutatják, hogy az **Alábontás** mező beállítása hogyan érinti, a módot, ahogy az anyagjegyzék naplósorai létrejönnek. **Alábontás: soha**

| Szint | Cikkszám | Mennyiség |
|-------|-------------|----------|
| 0     | FG          | 3        |
| 1     | COMP        | -3       |

Ahogy a korábbi táblázat mutatja, az egyetlen levontnak tekintett cikkszám a naplóban a COMP. Az RM cikkszám, ami a COMP része nem kerül alábontásra a naplósorhoz és a COMP két készleten lévő darabja nincs figyelembe véve. **Alábontás: mindig**

| Szint | Cikkszám | Mennyiség |
|-------|-------------|----------|
| 0     | FG          | 3        |
| 1     | RM          | -3       |

Ebben az esetben a COMP cikkszám alábontásra a kerül az RM cikkszámú nyersanyagáig. A két aktuálisan készleten lévő COMP darab nincs figyelembe véve a felhasználásra kerülő RM mennyiségében. **Alábontás: hiány**

| Szint | Cikkszám | Mennyiség |
|-------|-------------|----------|
| 0     | FG          | 3        |
| 1     | COMP        | -2       |
| 1     | RM          | -1       |

Ebben az esetben a két aktuálisan készleten lévő COMP cikkszám figyelembe van véve. Azonban amiért három darab FG cikkszámú cikkre van szükség egy RM cikkszámú cikkre szintén szükség van annak érdekében, hogy létrejöjjön a további egy darab COMP.



