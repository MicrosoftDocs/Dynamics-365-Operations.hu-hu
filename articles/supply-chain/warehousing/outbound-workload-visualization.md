---
title: Kimenő munkaterhelések megjelenítése
description: Ez a témakör a kimenő számítási feladat vizualizációjával kapcsolatban tartalmaz információkat. A funkció segítségével a raktárkezelők és a felügyelők egyéni számítási feladatok diagramjait hozhatják létre, amelyek segítségével figyelemmel kísérhető az aktuális munka előrehaladása, és a fennmaradó mennyisége. A raktárkezelők több nézetet is létrehozhatnak, és szükség szerint beállíthatják az automatikus frissítést.
author: Mirzaab
manager: tfehr
ms.date: 08/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-08-28
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: cbfb395c9103ff31979bfd57333f689e38915652
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645432"
---
# <a name="outbound-workload-visualization"></a>Kimenő munkaterhelések megjelenítése

[!include [banner](../includes/banner.md)]

A **Kimenő számítási feladat vizualizációja** lapon elérhető speciális beállítási lehetőségek lehetővé teszik a raktárkezelők és a felügyelők számára, hogy egyéni számításifeladat-diagramokat hozzanak létre, amelyek segítségével figyelhető az aktuális munka előrehaladása és a hátralévő mennyiség. A raktárkezelők több nézetet is létrehozhatnak, és szükség szerint beállíthatják az automatikus frissítést. A kimenő számítási feladat vizualizációi alkalmasak a raktári teljesítményoldalakon való megjelenítésre.

Ezzel a funkcióval nyomon követhető a kitárolási munka előrehaladása. A szolgáltatás integrálva van a munkaerő-gazdálkodással, és ha a munkaerő-gazdálkodás be van állítva, a kimenő munkaterhelés-vizualizációk megjeleníthetik a kitárolási munka hátralévő óráinak számítását, amely megjelenik (szűrve).

## <a name="turn-on-the-outbound-workload-visualization-feature"></a>A Kimenő munkaterhelés vizualizációja funkció bekapcsolása

A funkció használata előtt be kell azt kapcsolnia saját rendszerében. A rendszergazdák használhatják a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításait a funkció állapotának ellenőrzéséhez, és bekapcsolásához. A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:

- **Modul:** *Raktárkezelés*
- **Funkció neve** *A Kimenő munkaterhelés vizualizációja*

## <a name="set-up-outbound-workload-visualizations"></a>Kimenő munkaterhelések vizualizációjának beállítása

A vizualizációk beállításához hozzon létre szűrőket (nézeteket), és tervezze meg az egyes szűrőket úgy, hogy azok különböző típusú elemzéseket jelenítsenek meg. A **Szűrők konfigurálása** lapon tervezheti meg a szűrőket.

Kimenő munkaterhelés-vizualizáció beállításához kövesse az alábbi lépéseket.

1. Nyissa meg a **Raktárkezelés \> Raktárfigyelési jelentések \> Kimenő munkaterhelés vizualizációja** szakaszt.

    Megjelenik a **Kimenő munkaterhelés vizualizációja** lap. Néhány szűrő létrehozása után ezen az oldalon megjelenik a vizualizáció. Tetszőleges számú szűrőt lehet létrehozni. A rendszer az összes létrehozott szűrőt a felhasználói fiókja alá menti, így később is használhatja őket. Más szóval minden felhasználónak saját szűrőkészlete lesz, amelyet ők hoztak létre. Ezek a szűrők nem lesznek megosztva más felhasználókkal.

1. A **Kimenő munkaterhelés vizualizációja** oldalon, a Művelet panel **Szűrők** lapján válassza a **Szűrők konfigurálása** lehetőséget.
1. A **Szűrők konfigurálása** lap Művelet panelén válassza az **Új** lehetőséget szűrő hozzáadásához, majd állítsa be a következő mezőket:

    - **X-tengely csoporttáblája** – Az X-tengely értékeinek csoportosításához használandó mezőt tartalmazó tábla kiválasztása.
    - **X-tengely csoportmezője** – Az **X-tengely csoporttábla** mezőjében kijelölt tábla mezői közül válassza ki az X-tengely értékeinek csoportosításához használni kívánt mezőt.
    - **X-tengely értéktáblája** – A csoportok további elemzéséhez használandó mezőt tartalmazó tábla kiválasztása.
    - **X-tengely értékmezője** – Az **X-tengely értéktábla** mezőjében kijelölt tábla mezői közül válassza ki a mezőt, amely az egyes elemezni kívánt csoportok értékeit biztosítja.
    - **Automatikus frissítés** – Megadhatja, hogy a vizualizáció automatikusan frissüljön-e.
    - **Frissítési időköz (perc)** – Adja meg az automatikus frissítések közötti percek számát.
    - **Megjelenítési szint** – Megadhatja, hogy a diagramon megjelenjen-e a nyitott sorok vagy a nyitott fejlécek száma.
    - **Kitárolási típus** – Ha a **Megjelenítési szint** mezőt _Nyitott sorok_ értékre állítja, válassza ki, hogy a diagram nyitott munkasorainak száma tartalmazza-e a kezdeti kitárolásokat, szakaszos kitárolásokat, illetve mind a kezdeti kitárolásokat, mind a szakaszos kitárolásokat.
    - **Telephely** – Válassza ki azt a telephelyet, amelyhez be szeretné tölteni a diagramot.
    - **Raktár** – Válassza ki azt a raktárt, amelyhez be szeretné tölteni a diagramot.
    - **Tartalmazott napok** – Adja meg a azon múltbéli napok számát, amelyekhez a diagramot létre kell hozni.
    - **Munkarendelés típusa** – Válassza ki a szűrni kívánt kimenő munkarendelés-típusokat.

    ![Szűrők konfigurálása oldal](media/work-viz-filters-1.png "Szűrők konfigurálása oldal")

1. Zárja be a **Szűrők konfigurálása** oldalt, hogy visszatérjen a **Kimenő munkaterhelés vizualizációi** lapra.

    A **Kimenő munkaterhelés vizualizációi** lap mostantól az új szűrőbeállítások alapján jeleníti meg az adatokat. Az új szűrő már elérhető, és ki van jelölve a **Szűrő** mezőben. A diagram tetején a következő mezők találhatók:

    - **Szűrő** – Ebben a mezőben az eddig létrehozott összes szűrő szerepel. Válasszon egy szűrőt az adatai megjelenítéséhez a diagramban.
    - **Utolsó frissítés** – Ez a mező azt a dátumot és időpontot jeleníti meg, amikor a diagramon szereplő adatokat utoljára frissítették.
    - **Becsült/tényleges idő** – Ha a munkanormák a rendszerben be vannak állítva, akkor a beállítás *Igen* értékre állításával megjelenítheti a diagram egyes oszlopainak felső részén a felhalmozott becsült kitárolási időket. Ha nem használ munkanormákat, akkor ez a beállítás nem érhető el.

    ![Példa vizualizáció](media/work-viz-chart.png "Példa vizualizáció")

1. A kapcsolódó munkasor részletes adatainak megtekintéséhez válassza ki a diagram egyik sorát.

    ![Munkasor adatai](media/work-viz-work-details.png "Munkasor adatai")

## <a name="example-outbound-workload-visualization-for-zones"></a>Példa: A zónákhoz tartozó kimenő munkaterhelés megjelenítése

Ebben a példában egy vizuális megjelenítést szeretne beállítani, amely az egyes zónák munkasorait jeleníti meg, valamint az egyes munkasorok állapotát (_Nyitott_, _Lezárt_ vagy _Érvénytelenített_). Ebben az esetben a következő beállításokat tartalmazó szűrőket lehet beállítani:

- **Szűrő neve** – Adja meg a szűrő nevét (például a _Zóna és a munka állapota_).
- **Leírás** – Adja meg a szűrő rövid leírását (például a _Zóna és a munka állapota_).
- **X-tengely csoporttáblája** – Válassza ki a _Helyek_ elemet.
- **X-tengeéy csoportja** – Válassza ki a _Zónaazonosító_ elemet.
- **X-tengely értéktáblája** – Válassza ki a _Munka_ lehetőséget, mert zónánként szeretné megjeleníteni a munkát.
- **X-tengely értékmezője** – Válassza ki a _Munka állapota_ lehetőséget, mert meg szeretné jeleníteni a munka állapotát.
- **Automatikus frissítés** – Megadhatja, hogy a vizualizáció automatikusan frissüljön-e.
- **Kitárolás típusa** – Válassza ki a _Kezdeti kitárolások és szakaszos kitárolások_ lehetőséget, mert mind a kezdeti kitárolásokat, mind a szakaszos kitárolásokat szerepeltetni kívánja az előkészítési helyekről. Más szóval az összes kitárolási munkasort figyelembe kell venni.
- **Megjelenítés szintje** – Válassza ki _Nyitott sorok_ lehetőséget, mert soronként szeretné megtekinteni az adatokat, nem pedig munkafejlécenként.

A következő ábra az eredményül kapott diagramot szemlélteti.

![Zóna és munkaállapot vizualizációja](media/work-viz-chart.png "Zóna és munkaállapot vizualizációja")

Ez a diagram két olyan zónát mutat be, amelyek a **SZINT** és az **ÖMLESZTETT** elnevezésekkel rendelkeznek, valamint az **Üres** nevű zónát. Az **Üres** zóna minden olyan munkasort jelöl, amely nem tagja egy zónának. A diagram mindig **Üres** állapottal jeleníti meg az összes nem kapcsolódó szűrt adatot, hogy a lehető legnagyobb láthatóságot biztosítsa. A **SZINT** zónában a diagram három lezárt sort és négy nyitott sort mutat be. Az **ÖMLESZTETT** zónában a diagram négy lezárt sort és egy nyitott sort, valamint 24 érvénytelenített sort mutat be. Végezetül a diagram nyolc olyan lezárt sort jelenít meg, amelyek nem részei egy zónának sem, ezért **Üres** állapottal szerepelnek.
