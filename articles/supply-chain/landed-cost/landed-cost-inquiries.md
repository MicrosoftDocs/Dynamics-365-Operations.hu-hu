---
title: Partraszállításiköltség-lekérdezések
description: Ez a témakör azt ismerteti, hogyan lehet megtalálni és használni a Partraszállítási költség modulban elérhető különféle típusú lekérdezéseket.
author: sherry-zheng
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMLine, ITMItemTracking, ITMContainerActivityTracking, ITMContainerTracking
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-21
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 0b712e7869c592150a408834855bb1f4fa20277ca26182f0d065b8f3cd77296a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6762938"
---
# <a name="landed-cost-inquiries"></a>Partraszállításiköltség-lekérdezések

[!include [banner](../../includes/banner.md)]

## <a name="voyage-line-inquiries"></a>Hajóútsor-lekérdezések

Az **Hajóútsor** lekérdezés a készlethez tartozó összes hajóútsort megjeleníti. Ez a lekérdezés szűrőként használható egy cikk, beszerzési rendelés vagy más hasznos információ megkeresésében. Arra is használható, hogy azonosítsa egy cikk várható szállítási dátumát, amely egy vagy több hajóúton lehet. Ily módon segíthet a várt készlet bevételezésének kezelésében.

A lekérdezés megnyitásához lépjen a **Partraszállítási költség \> Lekérdezések \> Hajóútsorok** elemre.

### <a name="overview-tab"></a>Áttekintés lap

A **Hajósorok** lekérdezési oldal **Áttekintés** lapja egy rácsot tartalmaz, amely az egyes hajóútsorok alapvető adatait tartalmazza. A következő táblázat a rács különböző oszlopait írja le.

| Oszlop | Leírás |
|---|---|
| **Cikkszám** | A hajóútsorhoz tartozó cikk. |
| **Hivatkozás** | A rendelés típusa (beszerzési rendelés vagy átmozgatási rendelés). |
| **Szám** | A beszerzési rendelés száma vagy az átmozgatási rendelés száma. |
| **Ívlap** | A hajóútsorhoz társított levél. |
| **Szállítási konténer** | A hajóútsorhoz társított szállítókonténer. |
| **Út** | A hajóútsorhoz társított hajóút. |
| **Mennyiség** | A hajóútsor cikkének mennyisége. |
| (Egyéb dimenziók) | Ha szükséges, a további dimenziók oszlopai megjeleníthetők. Ilyen dimenziók például a kötegszám, a készletállapot és a raktár. A Művelet panelen válassza ki a **Készlet \> Dimenziók megjelenítése** lehetőséget egy párbeszédpanel megnyitásához, ahol kiválaszthatja a megjeleníteni kívánt dimenziókat. |

### <a name="general-tab"></a>Általános fül

Az **Általános** lap kiválasztásával megtekintheti az **Áttekintés** lapon aktuálisan kiválasztott sorra vonatkozó további információkat.

### <a name="dimensions-tab"></a>Dimenziók lap

Válassza ki a **Dimenziók** lapot az **Áttekintés** lapon jelenleg kiválasztott sor összes elérhető készletdimenziójához tartozó értékek megjelenítéséhez, függetlenül attól, hogy milyen dimenziók megjelenítését választotta ki azon a lapon.

## <a name="cost-estimate-inquiries"></a>Költségbecslési lekérdezések

Minden alkalommal, amikor költségbecslést generál, a becslés hozzáadódik a **Költségbecslések** lekérdezési oldalhoz. A költségbecslések (beleértve a lekérdezési oldalon található becsléseket is) generálásával, megtekintésével és kezelésével kapcsolatos részletes információkért lásd a [Partraszállítási költségek becslése és kezelése](estimate-manage-landed-costs.md) részt.

## <a name="item-tracking"></a>Cikk nyomon követése

A **Cikk-követés** oldalon megtekintheti a nyitott beszerzésirendelés-sorokat és azok aktuális állapotát. Az itt megjelenő hajóúthoz nem kell sorokat hozzárendelni. Ha viszont egy cikk hajóúthoz van társítva, akkor a cikk-követési rekordsor a hajóút azonosítóját jeleníti meg.

Az oldal megnyitásához nyissa meg a **Partraszállítási költség \> Lekérdezések \> Követés \> Cikk-követés** elemet.

Mivel a rendszer valószínűleg nagyon nagy számú beszerzésirendelés-sort tartalmaz, a **Cikk-követés** oldal kezdetben nem tartalmaz rekordokat. Először az oldal tetején lévő szűrőmezőkkel határozza meg a keresett beszerzésirendelés-sorokat. Ezután a lista létrehozásához válassza a Művelet panel **Frissítés** parancsát. A csillagot (\*) helyettesítő karakterként bármelyik szűrőmezőben lehet használni. Ha például a nevükben a „DVD” szót tartalmazó összes beszerzésirendelés-sort kívánja megkeresni, állítsa a **Típus** mezőt **Terméknév** értékre, majd írja be a *\*DVD\** kifejezést a **Mező értéke** mezőbe.

> [!NOTE]
> Jelenleg a teljesítetlen rendelések csak értékesítési rendeléseket tartalmaznak. Az értékesítési ajánlatok nem jelennek meg, és nem tekinthetők teljesítetlennek.

A következő táblázat a **Cikk-követés** oldal rácsának oszlopait írja le.

| Oszlop | Leírás |
|---|---|
| **Célkikötő** | A végső cél. |
| **Visszaigazolva** | A beszerzésirendelés-sor megerősített dátuma. |
| **Szállítási dátum** | A beszerzésirendelés-sor szállítási dátuma. |
| **Út** | Ha a sor hajóúthoz van társítva, akkor a hajóút azonosítója. |
| **Szállítókonténer** | Ha a sor egy szállítókonténerhez van csatolva, a konténer azonosítója. |
| **Szállítási kikötő** | Az aktuális kikötő a követési képernyő első szakasza alapján, ahol nincs beállítva tényleges dátum a beszerzésirendelés-sorhoz társított szállítókonténerhez. |
| **Tevékenység** | Az aktuális tevékenység a követési képernyő első szakasza alapján, ahol nincs beállítva tényleges dátum a beszerzésirendelés-sorhoz társított szállítókonténerhez. |
| **Becsült záró dátum** | Az a dátum, amikor a hajóút várhatóan bevételezésre kerül a célraktárba. |
| **Név** | A szállító neve. |
| **Hajóót állapota** | A beszerzésirendelés-sorhoz társított szállítmányállapot. |
| **Cikkszám** | A beszerzésirendelés-sor cikkszáma. |
| **Külső** | A szállító cikkjének neve. |
| **Termék neve** | A beszerzésirendelés-sor cikkjének neve. |
| **Mennyiség** | Beszerzésirendelés-sor összege a beszerzésirendelés-sorhoz. |
| **Egység** | A beszerzésirendelés-sor mértékegysége. |
| **Hivatkozás** | A rendelés típusa (beszerzési rendelés vagy átmozgatási rendelés) |
| **Hivatkozási szám** | A beszerzési rendelés száma vagy az átmozgatási rendelés száma. |
| **Teljesítetlen rendelés** | Ez a szimbólum azt jelzi, hogy a cikkhez teljesítetlen értékesítési rendelések vannak. |
| (Egyéb dimenziók) | Ha szükséges, a további dimenziók oszlopai megjeleníthetők. Ilyen dimenziók például a kötegszám, a készletállapot és a raktár. A Művelet panelen válassza ki a **Dimenziók megjelenítése** lehetőséget egy párbeszédpanel megnyitásához, ahol kiválaszthatja a megjeleníteni kívánt dimenziókat. |

### <a name="related-information-about-backorders"></a>A teljesítetlen rendelésekkel kapcsolatos információk

A teljesítetlen rendelésekkel kapcsolatos további információk megtekintéséhez válassza a lap jobb oldalán a **Kapcsolódó információk** lapot, majd válassza a **Teljesítetlen rendelések** lehetőséget. Ha egy bizonyos teljesítetlen rendelésről még több információt szeretne látni, válassza ki annak sorát, majd válassza a **További** hivatkozást.

## <a name="individual-shipping-container-tracking"></a>Egyéni szállítási konténer nyomon követése

Az **Egyéni szállítókonténerek követése** lekérdezése egy szűrőt biztosít, amellyel megkereshető egy szállítókonténer, és azonosítható a konténerben található összes hajóútsor.

A lekérdezés megnyitásához nyissa meg a **Partraszállítási költség \> Lekérdezések \> Követés \> Egyéni szállítókonténerek követése** elemet.

## <a name="multiple-shipping-container-tracking"></a>Több szállítási konténer nyomon követése

A **Több szállítókonténer követése** lekérdezés egy szűrőt biztosít, amellyel megkereshető szállítókonténerek egy gyűjteménye, és azonosítható a konténerekben található összes hajóútsor.

A lekérdezés megnyitásához nyissa meg a **Partraszállítási költség \> Lekérdezések \> Követés \> Több szállítókonténer követése** elemet.
