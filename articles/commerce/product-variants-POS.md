---
title: Készlet ellenőrzése a pénztárnál (POS)
description: Ez a témakör leírja a készletinformációinak megtekintéséhez a pénztárnál (POS) rendelkezésre álló beállításokat.
author: ashishmsft
manager: AnnBe
ms.date: 03/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2018-03-30
ms.dyn365.ops.version: Application update 5, AX 8.0
ms.openlocfilehash: 1d6133d80d7674a1d896bc19a743a6bd4d0fb40f
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2020
ms.locfileid: "3022824"
---
# <a name="inventory-lookup-in-the-point-of-sale-pos"></a>Készlet ellenőrzése a pénztárnál (POS)

[!include [banner](includes/banner.md)]

A keresés a készletben a pénztárnál (POS) segítségével a kiskereskedők valós idejű üzemi kiválóságot érhetnek el, és információkat szerezhetnek az áruházak, a pénztár és a háttériroda összekapcsolásával. Ez a funkció lehetővé teszi az üzletek és elosztóközpontok termékkészletének pontos valós idejű megtekintését. A hatékonyság és a költségmegtakarítás növelését teszi lehetővé a kiskereskedők számára a valós idejű készlettervezés továbbfejlesztésével.

A készletnek a szervezeten belüli pontos valós idejű nézetének segítségével az üzlet munkatársai időbeli, kiváló ügyfélkiszolgálást nyújthatnak. A legfontosabb pillanat az, amikor a vevő készen áll a beszerzési döntés meghozására. Fontos, hogy a pénztárosok az üzletben valós idejű készletadatokkal rendelkezzenek, és így pontosan ígéreteket tehessenek a termék szállítására és felvételére.

Megnyithatja a **Keresés a készletben** lapot a **Retail Modern POS** munkaterületről vagy a **Retail Cloud POS** munkaterületről.

![Készletkeresési csempe a POS-kezdőlapon](media/POSHomepage.png)

A **Keresés a készletben** lapon a numerikus billentyűzet használatával adhatja meg a termékszámot. A készleten lévő cikkmennyiség több áruházra és raktárra tekinthető meg.

![Szabványos készletkeresési lap](media/InventoryLookUp.png)

**Fenntartott** és **Megrendelve** mennyiségek is megjelennek az egyes helyekhez.

- **Fenntartott** – Ez a mennyiség a **Ténylegesen fenntartott** értékre vonatkozik, amely a háttérirodai rendszerből származik, a megadott termékszámra az adott helyen.
- **Megrendelve** – Ez a mennyiség az **Összes rendelés** értékre vonatkozik, amely a háttérirodai rendszerből származik, a megadott termékszámra az adott helyen.

## <a name="locations-that-inventory-availability-information-is-shown-for"></a>Helyek, amelyre a készlet elérhetőségi adatok megjelennek

A helyek listája kétfajta entitást tartalmaz:

- **Áruházak** – A lista azokat az üzleteket tartalmazza, amelyeket az üzletcsoport lokátorcsoport használatával konfiguráltak az aktuális üzletre a központokban.
- **Elosztóközpontok** – Különféle elosztóközpontokat (például raktár) lehet a Commerce alkalmazásban beállítani. A készlet-elérhetőségi adatokat azonban a lista csak a **Szabványos**, alapértelmezett típusú elosztóközpontokra mutatja.

    > [!NOTE]
    > A készlet-elérhetőségi adatok nem jelennek meg a pénztárban a **Tranzit**, **Karantén** és **Úton lévő áruk** típusú raktárak esetében.

A **Keresés a készletben** lapon megtekintheti az ígérethez rendelkezésre álló (ATP) mennyiségeket az egyes üzletekben, az aktuális készleten lévő mennyiségek, a lefoglalt mennyiségek és a megrendelt mennyiségek mellett. Válassza ki az üzletet, amelynek ígérethez rendelkezésre álló információit meg szeretné tekinteni, és válassza ki az **Üzlet elérhetőségének megjelenítése** lehetőséget.

![ATP-mennyiségek](media/ATP.png)

## <a name="opening-the-dimension-based-matrix-view-to-show-all-variants"></a>A dimenzióalapú mátrixnézet megnyitása minden változat megtekintéséhez

A **Termékadatok** lapján az alapterméknek, vagy a **Keresés a készletben** oldalon, válassza **Az összes változat megtekintése** lehetőséget az alkalmazás-eszköztáron az oldal alján. A **Dimenzióalapú mátrix** nézet a kezdeti indításhoz ezeken a lapokon a készletelérhetőségi adatokat jeleníti meg minden termékváltozathoz az aktuális üzlet esetében.

> [!NOTE]
> **Az összes változat megtekintése** gomb csak a termékváltozatokkal rendelkező cikk alaptermékekhez érhető el. Nem érhető el az önálló termékek vagy csomagok esetében.

![Az összes változat megtekintése gomb a Keresés a készletben lapon](media/StandardToMatrix.png)

Válassza ki **Az összes változat megtekintése** lehetőséget az alaptermék **Termékadatok** lapján, vagy a **Keresés a készletben** oldalon, a hely kiválasztása nélkül, az ugráshoz a **Dimenzióalapú mátrix** nézetre a készletelérhetőségi adatokat megtekintéséhez minden termékváltozathoz az aktuális üzlet esetében.

![Dimenzióalapú mátrix nézet a Keresés a készletben laphoz](media/Matrix.png)

> [!NOTE]
> Az előző ábrán a dimenziók megjelenítési sorrendje ábécésorrendű,mert a dimenziók megjelenítési sorrendje nem volt konfigurálva a kiválasztott termékhez.

A **Dimenzióalapú mátrix** nézetben a termékváltozatok cellái tartalmaznak egy aktuális készlet értéket a jobb alsó sarokban. Az alábbi táblázat bemutatja a különféle értékek jelentését.

| Aktuális készlet értéke                            | Leírás |
|------------------------------------------|-------------|
| Számszerű érték, amely nagyobb, mint 0 (nulla) | A kiválasztott helyre fel lett adva egy változat, és további műveletek végezhetők el a cellában. (A műveletekről részletesen a jelen témakör későbbi szakaszaiban olvashat.) |
| **0** (nulla)                             | Egy változat már ki van adva a megadott helyre, de a cikk nem érhető el a kiválasztott helyen. Azonban a cellában további műveletek hajthatók végre. (A műveletekről részletesen a jelen témakör későbbi szakaszaiban olvashat.) |
| **n/a** vagy inaktív cella              | A kiválasztott helyre még nem lett feladva egy változat, és további műveletek nem végezhetők el a cellában. |

A kimutatás dimenziók szempontjából is módosítható úgy, hogy kiválasztja a használandó új dimenziót.

![A kimutatás módosítása](media/ChangePivot.png)

![A kimutatás módosult](media/PivotChanged.png)

> [!NOTE]
> Az előző ábrákon a dimenziók megjelenítési sorrendje a kiválasztott termékhez egyéni (nem ábécésorrendet követ). A dimenziók háttérirodában beállított megjelenítési sorrendjén alapul.

Ezenkívül, a **Dimenzióalapú mátrix** nézetben, további műveleteket lehet végrehajtani a kiskereskedelmi munkatársak termelékenységének növelése érdekében. Íme néhány példa:

- Az összes termékváltozat készletének más helyeken levő rendelkezésre állásának megkereséséhez módosítsa a tárolási helyet. Ezek a helyek lehetnek az üzlet lokátorcsoportba tartozó más üzletek, valamint a **Szabványos** alapértelmezett típusú elosztóközpontok.
- Értékesítsen egy konkrét termékváltozatot egy vevőnek cash and carry, üzleten belüli felvétele vagy szállítás címre módon.
- Adja meg a vevőknek az ígérethez rendelkezésre álló információkat egy adott termékváltozatról egy adott helyen.

![A termékváltozatokkal kapcsolatos további műveletek](media/VariantActions.png)

> [!NOTE]
> Az előző ábrán a dimenziók megjelenítési sorrendje ábécésorrendű,mert a dimenziók megjelenítési sorrendje nem volt konfigurálva a kiválasztott termékhez.

A következő táblázatban tájékozódhat a rendelkezésre álló további műveletekről.

| Művelet               | Leírás |
|----------------------|-------------|
| Eladás most             | Adja a kijelölt cikkváltozatot a tranzakcióhoz, és irányítsa át a felhasználót a tranzakció képernyőre. (Ez a művelet nem érhető el, a kiválasztott hely elosztási központ.) |
| Felvétel az üzletben     | Hozzon létre vevői rendelést a termékváltozatra, amely a kijelölt helyen lesz felvéve, és irányítsa át a felhasználót a tranzakció képernyőre. (Ez a művelet nem érhető el, a kiválasztott hely elosztási központ.) |
| Termék szállítása         | Hozzon létre vevői rendelést a termékváltozatra, amely a kijelölt helyre lesz kiszállítva, és irányítsa át a felhasználót a tranzakció képernyőre. |
| Elérhetőség         | Jelenítse meg az ígérethez rendelkezésre álló információkat a kiválasztott változatkombinációra a kiválasztott helyre. |
| Minden hely megjelenítése   | Váltson át a szokásos készletkeresési nézetre, és jelölje ki a készletelérhetőségi információkat a cikkváltozatra az összes üzletben az üzlet-lokátorcsoportban, valamint a **Szabványos/Alapértelmezett** típusú elosztóközpontokban. |
| Termék részleteinek megtekintése | Irányítsa át a felhasználót a társított alaptermék **Termék részletei** oldalára. |
