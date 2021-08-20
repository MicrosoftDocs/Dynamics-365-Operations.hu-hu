---
title: Konszolidáció és megszüntetés áttekintése
description: A cikk a konszolidációs és megszüntetési folyamat általános ismertetését tartalmazza. Magában foglalja a gyakori kérdésekre adott válaszokat is.
author: aprilolson
ms.date: 01/11/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerConsolidate
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "13151"
- intro-internal
ms.assetid: 9d8f55cb-b2cf-4e01-89cf-0e21f5c8ae1f
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b983b8b5f90d00d0c115c57942a2b8be56dce21756cc55fbd405a563348a69d4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6777144"
---
# <a name="consolidation-and-elimination-overview"></a>Konszolidáció és megszüntetés áttekintése

[!include [banner](../includes/banner.md)]

A cikk a konszolidációs és megszüntetési folyamat általános ismertetését tartalmazza. Magában foglalja a gyakori kérdésekre adott válaszokat is.

Ha megszűntet adatokat, akkor több leányvállalat pénzügyi eredményei egyesülnek egy konszolidált vállalatként. A lényvállalatok eltérő verziókon vagy rendszereken lehetnek, résztulajdonoltak lehetnek és eltérő pénznemeket használhatnak. Adategyesítéshez több lehetőséget választhat:

-   **Online konszolidálás** – Ez a lehetőség, összesíti a napi egyenlegeket a kiválasztott számlák és dimenziók szerint, majd eltároljak azokat a konszolidált vállalatban.
-   **Pénzügyi jelentéskészítés** – Ezzel a lehetőséggel bármikor konszolidálhat tranzakciókat és egyenlegeket. Több szinten is létrehozhat hierarchiákat és több jelentés-devizanem is megjeleníthető.
-   **Konszolidálás importálással** – Ez a lehetőség egyenlegeket importál a konszolidációs vállalatba.
-   **Vállalat egyenlegek exportálása** – Ez a lehetőség export fájlt biztosít vállalati egyenlegekhez. A fájl később importálható a többi példányba vagy más rendszerekbe. A pénzügyi jelentések használhatók az egyenlegek Microsoft Excel fájlba történő exportálásához.

Az eltávolításokat többféleképpen lehet jelenteni:

-   Az eltávolítási szabályok a rendszerben adhatók meg, és a konszolidációs folyamat során kerülnek feldolgozásra egy eltávolítási javaslat alapján. A szabályok bármelyik vállalat számára feladhatók, amelyeket kiválasztottak **Pénzügyi eltávolítási folyamatokhoz** a jogi személy beállításoknál.
-   Egy külön vállalat hozható létre és használható, hogy manuálisan meghatározhatók és feladhatók legyenek az eltávolítási tranzakciók. Ez a vállalat használható a konszolidációs folyamatban vagy a pénzügyi jelentésben.
-   A vállaltközi tevékenység meghatározásához használt számlák és pénzügyi dimenziók sor vagy oszlopdefinícióval szűrhetők a Pénzügyi jelentésben, és teljes részletességű képességek használhatók. A számított oszlop vagy sor ezután felhasználható számlák és pénzügyi dimenziók eltávolítására a konszolidált végösszegből.

Sok összevonási eset lehetséges és minden módszer máshogy tudja kezelni ezeket az eseteket.

## <a name="frequently-asked-questions"></a>Gyakori kérdések
1.  Szeretnék eltávolításokat az adatbázisba feladni. Mik a lehetőségeim?

Több lehetőség is létezik. Használhatja az **Online konszolidálás** lehetőséget, majd az eltávolításokat bevonhatja javaslatként a folyamatba. A tranzakciók a konszolidációs vállalatba kerülnek feladásra. Azt is megteheti, hogy elkülönít egy vállalatot, amelyben manuálisan hozza létre az eltávolításokat, majd ezt a vállalatot a Pénzügyi jelentéshez használja az eltávolítási folyamatban.

2.  Az eltávolítási eredmények jelentéseire több pénznemben van szükség.

A **Pénzügyi jelentéskészítés** lehetőségben korlátlan számú pénznemet használhat. Az adatok lefordításra kerülnek a jelentés létrehozásakor a fő számlában megadott árfolyamtípus és pénznem átváltási módszer alapján. Azonban az **Online konszolidálás** lehetőség csak egy jelentési pénznemmel rendelkezik, konszolidált vállalatok szükségesek az egyes jelentési pénznemekhez ha ezt a lehetőséget választja. A **Pénzügyi jelentéskészítés** lehetőség az ajánlott módszer.

3.  Az egyes vállalatokkal kapcsolatos részletek megjelenítése tranzakciós szinten.

A **Pénzügyi jelentéskészítés** lehetőség a megfelelő választás, mert a tranzakciós szintű részletek annyi vállalathoz tekinthetők meg, amennyi a jelentési fa definíciójában van megadva.

4.  Költségvetés tervezést vagy költségvetés-ellenőrzést használunk, amit konszolidálni kell.

A **Pénzügyi jelentéskészítés** lehetőség a megoldás minden költségvetés-tervezési vagy költségvetés-ellenőrzési adat konszolidálására.

5.  A leányvállalatok az egész világban vannak szétszórva, és több számlatükörrel rendelkeznek. Mi a legjobb módszer az adatok konszolidálására?

Több lehetőség közül választhat, amikor több számlatükröt kell kezelnie. Használhatja az **Online konszolidálás** lehetőséget, majd válassza ki, hogy a fő számlán megadott konszolidációs számlát vagy a konszolidációs számlacsoportot használja. Emellett használhatja a **Pénzügyi jelentéskészítés** lehetőséget is, megadhat több linket pénzügyi dimenziókhoz a sordefinícióban és leképezheti a számlákat.

6.  Többszintű konszolidáció szükséges. Ez azt jelenti, hogy először az összes európai leányvállalat konszolidációja megy végbe brit fontban (GBP). Ezután létrejönnek az adatok és átváltásra kerül a konszolidált összeg dollárra (USD). Hogy lehet ezt megtenni?

Ha többszintű konszolidáció szükséges, miközben az egyes szintek különböző pénznemeket használnak, akkor az **Online konszolidálás** lehetőséget kell választani. Több konszolidációs vállalat is létrehozható amelyeknek különböző a könyvelési és jelentési pénzneme. A konszolidációt többször kell futtatni. A **Pénzügyi jelentéskészítés** lehetőség mindig átváltja az egyes forrásvállalatok könyvelési pénznemét a választott pénznemre.

7.  A leányvállalatok más rendszerben vannak. Hogyan konszolidálhatók?

Használja a **Konszolidálás importálással** lehetőséget az egyenlegek konszolidációs vállalatba foglalásához.

8.  Néhány leányvállalatot csak részben birtoklunk. Mi a legjobb módszer ezeknek a konszolidálására?

Ezekhez a leányvállalatokhoz több lehetőség van. A **Pénzügyi jelentéskészítés** lehetőséggel megadhatja a jelentési fa definícióját és a tulajdoni viszonyokat. Továbbá használhat számított oszlopot vagy sort, hogy megjelenítse a részlegesen birtokolt összeget. Még a kisebbségi kamatot is megjelenítheti a jelentés külön sorában. Használhatja az **Online konszolidálás** lehetőséget is. A **Jogi személyek** lap tartalmaz egy **Tulajdonos** oszlopot, ahol megadhatja az anyavállalat által birtokolt százalékot.

9.  A szervezetnek meg kell jelenítenie a konszolidációkat üzleti egységenként vagy a szervezeti hierarchiákat kívánja használni.

A **Pénzügyi jelentéskészítés** lehetőség a megoldás. A szervezeti hierarchiák amelyek jogi személyekkel vagy pénzügyi dimenziókkal rendelkeznek jelenthetők a Pénzügyi jelentéskészítéssel. Létrehozhatja a saját, többszintű hierarchiáját a jelentési fa definíciójának segítségével, ami jogi személyek és dimenzióértékek kombinációjából áll.

10. A rendszernek egynél több példánya létezik.

A **Vállalati egyenlegek exportálása** lehetőséggel exportálhat egy példányból, majd használja a **Konszolidálás importálással** lehetőséget a másik példányban, hogy konszolidálja az adatokat.

11. Végezhetek-e Konszolidációt, ha a költségvetésem **TERVEZET** állapotú? 
            
Nem fogja tudni feldolgozni vagy végrehajtani a költségvetéseket a konszolidált vállalatban. A költségvetés-tervezetek konszolidálásához a Financial Reporting használatát javasoltuk.

További információ: [Devizaátértékelés konszolidációs vállalatban](../general-ledger/currency-revaluation-consolidation-company.md).




[!INCLUDE[footer-include](../../includes/footer-banner.md)]