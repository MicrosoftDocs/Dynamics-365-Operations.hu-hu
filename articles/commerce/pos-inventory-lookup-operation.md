---
title: Készletkeresés-művelet a pénztárban
description: Ez a témakör azt ismerteti, hogyan lehet a Dynamics 365 Commerce pénztárakban (POS) a készletkeresési művelet segítségével megtekinteni az üzletekben és raktárakban az aktuális készlet rendelkezésre állását.
author: boycezhu
ms.date: 05/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2018-03-30
ms.dyn365.ops.version: Application update 5, AX 8.0
ms.openlocfilehash: c0f753febb0d347015fde1374148835f90df55a3
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2021
ms.locfileid: "6353780"
---
# <a name="inventory-lookup-operation-in-pos"></a>Készletkeresés-művelet a pénztárban

[!include [banner](includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet a Dynamics 365 Commerce pénztárakban (POS) a készletkeresési művelet segítségével megtekinteni az üzletekben és raktárakban az aktuális készlet rendelkezésre állását.

A készletnek a szervezeten belüli pontos nézetének segítségével az üzlet munkatársai gyors és hatékony ügyfélkiszolgálást nyújthatnak. A legfontosabb pillanat az, amikor a vevő készen áll a beszerzési döntés meghozására. Fontos, hogy a pénztárosok a kiskereskedelmi üzletben valós idejű vagy közel valós idejű készletadatokkal rendelkezzenek, és így pontosan ígéreteket tehessenek a termék szállítására és felvételére.

A Commerce POS készletkeresési művelete lehetővé teszi a kiskereskedők számára a kiváló működés elérését, valamint információk lekérését az üzletek összekapcsolásával a Commerce központtal. Ez a funkció az üzletek és raktárak termékeinek készletén elérhetőségét biztosítja. A hatékonyság és a költségmegtakarítás növelését teszi lehetővé a kiskereskedők számára a valós idejű készlettervezés továbbfejlesztésével.

Amikor a készletkeresési művelet a POS alkalmazásból indult el, a pénztáros numerikus billentyűzet használatával adja meg a termékszámot a készletinformációk lekérdezéséhez. Ha a megadott terméknek változatai vannak, a pénztáros tetszőleges módon kiválaszthat dimenziókat vagy más értékeket, hogy egy adott termékváltozat készletinformációit ellenőrizze.

## <a name="inventory-lookup-list-view-for-individual-products"></a>Készletkeresési listanézet az egyes termékekhez

A készletkeresési művelet egy készletkeresési listanézetet biztosít egy adott termékre, amely a következő termékadatokat tartalmazza a helyek listájához:

- **Készlet** – a termék "elérhető fizikai" mennyiségére vonatkozik.
- **Lefoglalva** – a központból lekért "fizikailag lefoglalt" mennyiségre vonatkozik.
- **Megrendelve** – a központból lekért "összesen megrendelt" mennyiségre vonatkozik.
- **Egység** – a központban konfigurált készletegységre vonatkozik.

A helyek listanézete tartalmaz minden üzletet és raktárat, amely az aktuális üzlethez kapcsolt teljesítési csoportokban van konfigurálva, mint azt a következő például szolgáló kép mutatja.

![Készletkeresés-művelet listanézet.](media/inventory-lookup-list-view.png)

> [!NOTE]
> Győződjön meg arról, hogy az aktuális üzlet szerepel a kapcsolódó teljesítési csoportokban.

Az alábbi műveletek érhetők el a pénztár alkalmazássávján:

- **Rendezés** – ez a művelet lehetővé teszi a pénztári felhasználó számára, hogy különböző feltételek alapján rendezzék a listanézetben található adatokat. Az alapértelmezett rendezési beállítás a hely alapú rendezés. 
  - **Földrajzi hely** (a legközelebbi helytől a legtávolabbi helyig az aktuális üzlethez képest)
  - **Név** (növekvő vagy csökkenő sorrendben)
  - **Üzlet száma** (növekvő vagy csökkenő sorrendben)
  - **Készlet** (csökkenő sorrendben)
  - **Lefoglalva** (csökkenő sorrendben)
  - **Megrendelve** (csökkenő sorrendben)
- **Szűrő** – ez a művelet lehetővé teszi a pénztári felhasználó számára egy adott hely szűrt adatainak megtekintését.
- **Az áruház elérhetőségének megjelenítése** – ezzel a művelettel a pénztári felhasználó megtekintheti a kiválasztott üzletben elérhető, ígérethez rendelkezésre álló (ATP) mennyiségeket.
- **Üzlet helyének megjelenítése** – ez a művelet egy külön oldalt nyit meg, amely megjeleníti a kiválasztott üzlet térképnézetét, címét és nyitva tartását.
- **Átvétel üzletben** Ez a művelet létrehoz egy vevői rendelést a termékváltozatra, amely a kijelölt üzletben lesz felvéve, és át irányítja a felhasználót a tranzakció képernyőre.
- **Termék szállítása** Ez a művelet létrehoz egy vevői rendelést a termékváltozatra, amely a kijelölt üzletből lesz szállítva, és átirányítja a felhasználót a tranzakció képernyőre.
- **Összes változat megtekintése** – a változatokkel rendelkező termékeknél ez a művelet egy listanézetről egy mátrixnézetre vált, amely a termék minden változatának készletinformációit jeleníti meg.
- **Hozzáadás a tranzakcióhoz** – ez a művelet hozzáadja a terméket a kosárhoz, és átirányítja a felhasználót a tranzakciós képernyőre.

> [!NOTE]
> A hely alapú rendezéshez hely és az aktuális üzlet közötti távolságot a Commerce központban megadott koordináták (földrajzi szélesség és földrajzi hosszúság) határozzák meg. Üzletnél a helyadatokat az üzlethez társított üzemi egység elsődleges címe alapján van meghatározva. Nem üzlet raktár esetén a helyadatokat a raktár címe határozza meg. Ha az aktuális üzlet koordinátái nincsenek megadva, a hely alapú rendezési beállítás az aktuális üzletet jeleníti meg a lista tetején, majd név szerint rendezi az egyéb helyeket.

> [!NOTE]
> Az **Üzlet elérhetőségének megjelenítése**, az **Üzlet helyének megjelenítése**, az **Átvétel üzletben** és a **Termék szállítása** műveletek nem érhetők el a nem üzleti helyeken.

## <a name="inventory-lookup-matrix-view-for-variants"></a>Készletkeresési mátrix nézet a változatokhoz

A változatokkal rendelkező alaptermék készletkeresési művelete egy dimenzió alapú mátrixnézetet is biztosít, amely megjeleníti a kiválasztott helyen található alaptermék minden változatának rendelkezésre állási adatait. Alapértelmezés szerint a mátrixnézet az aktuális üzletre vonatkozó adatokat jeleníti meg. Az alkalmazássáv **Üzlet** műveletének használatával lehet megtekinteni a készletinformációkat más üzletekhez, amelyek abban a teljesítési csoportban vannak konfigurálva, amelyhez az aktuális üzlet társítva van.

A következő példaként bemutatja a készletkeresési mátrix nézetet a pénztárban.

![Készletkeresés-művelet mátrixnézet.](media/inventory-lookup-matrix-view.png)

A mátrix nézetben minden cella egy egyedi változatot jelenít meg, és megjeleníti a jobb alsó sarokban az aktuális készlet (elérhető fizikai) értékét, valamint a bal felső sarokban a **lefoglalt** (fizikailag lefoglalt) és a **megrendelt** (összes megrendelt) értékeket. Az alábbi táblázat bemutatja a különféle rendelkezésre álló értékek jelentését.

| Aktuális készlet értéke                            | Leírás |
|------------------------------------------|-------------|
| Számszerű érték, amely nagyobb, mint 0 (nulla) | A kiválasztott helyre fel lett adva egy változat, és további műveletek végezhetők el a cellában. |
| **0** (nulla)                             | Egy változat már ki van adva a megadott helyre, de a cikk nem érhető el a kiválasztott helyen. A cellában további műveletek hajthatók végre. |
| **n/a** vagy inaktív cella              | A kiválasztott helyre még nem lett feladva egy változat, és további műveletek nem végezhetők el a cellában. |

A dimenzióértékek mátrixnézetben való megjelenítési sorrendjének alapja a Commerce központ konfigurált dimenziómegjelenítési sorrendje. A dimenzió megjelenítési sorrendjének konfigurációját úgy módosíthatja, hogy kiválaszt egy új dimenziót használatra. 

A mátrixnézet cellában az alábbi műveletek éérhetők el:

- **Eladás most** – ez a művelet hozzáadja a kiválasztott változatot a kosárhoz, és átirányítja a felhasználót a tranzakciós képernyőre.
- **Átvétel üzletben** Ez a művelet létrehoz egy vevői rendelést a kiválasztott változatra, amely a kijelölt üzletben lesz felvéve, és át irányítja a felhasználót a tranzakció képernyőre.
- **Termék szállítása** Ez a művelet létrehoz egy vevői rendelést a kiválasztott változatra, amely a kijelölt üzletből lesz szállítva, és átirányítja a felhasználót a tranzakció képernyőre.
- **Elérhetőség** - Ez a művelet egy külön oldalra viszi a felhasználót, amely a kiválasztott változat ígérethez rendelkezésre áll mennyiségét mutatja a kiválasztott áruházban.
- **Az összes hely megjelenítése** – Ez a művelet a szabványos készlet rendelkezésre állási listanézetre vált, amely a kiválasztott változat készletadatait mutatja.
- **Termékadatok megtekintése** - Ez a művelet átirányítja a felhasználót a kiválasztott változat termékadatok oldalára (PDP).

## <a name="access-inventory-lookup-from-other-pages-in-pos"></a>Készletkeresés elérése a pénztár többi oldaláról

A pénztárfelhasználók a készletkeresés műveletet a POS más oldaláról is elérhetik.

A következő példaként bemutatja a készletkeresési eredményeit a termékrészletek oldalról pénztárban.

![Készletkeresés a termék részletek oldalról.](media/inventory-lookup-from-product-details-page.png)

Az alaptermék termék termékrészletek oldalán az alkalmazássáv **Összes változat megtekintése** műveletével elindíthatja a készletkeresés mátrixnézetét, amely megjeleníti az aktuális áruház készletelérhetőség-adatait a termék minden változatára. Egy adott termék esetében a termékrészletek oldal megjeleníti az adott termék aktuális készletének (rendelkezésre álló fizikai) értékét az aktuális áruházra vonatkozóan. Ezenkívül kiválaszthatja az **Egyéb áruházak készlete** hivatkozást a készletkeresési művelet elindításához, hogy ellenőrizze a termék rendelkezésre állását más üzletekben vagy raktárakban.

> [!NOTE]
> Az **Összes változat megtekintése** művelet a termékrészletek oldalon csak a változatokkal rendelkező alaptermékekhez érhető el. Nem érhető el az adott termékek vagy csomagok esetében.

Beállíthatja, hogy a készletfeltárási művelet hivatkozásként jelenjen meg a pénztár tranzakciós képernyőjén található gombrácsban. A konfiguráció után, amikor a felhasználó kiválaszt egy kosársort, majd kiválasztja a **Készlet kereső** gombot, megjelenik a kijelölt termék készletkeresési lista nézete. A gombrácsok Pénztár képernyőelrendezés-tervező eszközzel történő konfigurálásával kapcsolatos további információkért lásd: [A pénztár felhasználói felületének vizuális konfigurációja](pos-screen-layouts.md).

## <a name="inventory-lookup-with-channel-side-calculation"></a>Készletkeresés csatornaoldali számítással

A Commerce 10.0.9-es és korábbi kiadásában a készletkeresési műveletben az **elérhető fizikai** értéket valós idejű szolgáltatási híváson keresztül lehet lekérni a Commerce központból. A Commerce 10.0.10-es vagy újabb kiadásában konfigurálhatja a pénztár készletkeresési műveletet, hogy a Commerce kiszolgálón csatornaoldali számítást használjon a rendelkezésre álló fizikai érték meghatározásához, ami megbízhatóbb és pontosabb becslést nyújthat az aktuális készletről a még nem szinkronizált tranzakcióadatok figyelembe vételével. A csatornaoldali készletszámítással és a kapcsolódó pénztárkonfigurációval kapcsolatos további információkért lásd: [Kiskereskedelmi csatornák készletelérhetőségének kiszámítása](calculated-inventory-retail-channels.md).

## <a name="additional-resources"></a>További erőforrások

[A pénztár felhasználói felületének vizuális konfigurációja](pos-screen-layouts.md)

[Kiskereskedelmi csatornák készletelérhetőségének kiszámítása](calculated-inventory-retail-channels.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
