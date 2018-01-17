---
title: "Profilelemzés beállítása"
description: "Ez a témakör bemutatja, hogy miként állíthatók be a vevő Recency, gyakorisági és pénzügyi (RFM) elemzésének."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 78943
ms.assetid: 8ff9aac3-5ada-4150-85fd-18901c926d53
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: e66208ccceb4c248c2704bb7358d77447e032205
ms.openlocfilehash: c59d12c54563b883ae6d8ea8594f423f02797f4f
ms.contentlocale: hu-hu
ms.lasthandoff: 12/14/2017

---

# <a name="set-up-rfm-analysis"></a>Profilelemzés beállítása

[!include[banner](includes/banner.md)]


Ez a témakör bemutatja, hogy miként állíthatók be a vevő Recency, gyakorisági és pénzügyi (RFM) elemzésének.

A Recency, gyakorisági és monetáris (RFM) analízis marketing célokat szolgál, amelyek a szervezet a beszerzések a vevő által generált adatok értékelésére használható. RFM analízis beállítása után vevők lesznek hozzájuk rendelve számított RFM-pontszám beszerzések élnek. Az RFM-pontszám háromjegyű minősítést vagy egy összesített szám, attól függően, hogy hogyan konfigurálta a szervezet az RFM analízis is lehet. A következőképpen működik az értékelés, ha szervezete háromjegyű értékelést használ a pontszámoknál:

- Az első számjegy a vevő recency értékelése, amely azt mutatja meg, hogy a vevő milyen régen vásárolt a szervezetétől. 
- A második számjegy a vevő gyakorisági minősítése (milyen gyakran vásárol a vevő a szervezettől). 
- A harmadik számjegy a vevő monetáris minősítése (mennyit költ a vevő, amikor a szervezettől vásárol). 

Például, a szervezet 1-től 5-ig terjedő skálán határozza meg a minősítést, ahol az 5 a legmagasabb minősítés. Ebben az esetben az 535 vevői minősítés a következő információkat szolgáltatja a vevőről:

-   **5-ös recency minősítés** – a vevőnek nemrég vásárolt.
-   **3-as gyakorisági minősítés** – a vevő mérsékelten gyakran vásárol a szervezettől.
-   **5-ös monetáris minősítés** – amikor a vevő vásárol, akkor jelentős mennyiségű pénzt költ.

Ha a szervezet által használt szám egy összesített szám, az egyes minősítések összeadódnak. A példánál maradva a vevő minősítése 13 (5 + 3 + 5).

## <a name="to-set-up-rfm-analysis-for-the-customers-in-your-organization"></a>RFM elemzés beállítása a szervezet vevőinél.

1.  Lépjen a **Hívásközpont** > **Időszakos** > **RFM analízis** ponthoz.

2.  Az **RFM analízis** oldalon válassza az **Új** lehetőséget. Az **RFM-definíció** mezőbe írja be az RFM-definíció nevét. Például a definíció hívhatja RFM-nak.

3.  Adja meg a kezdő és záró dátumot az RFM-definíció számára.

4.  Az **Általános** gyorslapon hajtsa végre a következő műveletet: 
    - Ha az RFM-pontszám minden részén egyenlő számláló vevőt kell tartalmaznia, jelölje be az **Egyenletes eloszlás** négyzetet. 
    - Jelölje be az **Értékelés hozzáadása** jelölőnégyzetet a három pontszám összeadásához. Ezáltal például a vevő 13-as RFM-pontszámot kapna 535 helyett. 
    - Az **Előzmények mentése** jelölőnégyzet bejelölésével kötelezővé teheti a rendszer számára a statisztikai adatok mentését annak érdekében, hogy az adatok az RFM-pontszám számításához használhatók legyenek.
  
5.  A **Recency** gyorslapon hajtsa végre a következő műveletet: 
    - A **Részlegek** mezőbe írja be a részlegek vagy a csoportok számát, amely a vevők recency pontszámának kiszámításához használt szám. Ha például 100, vevők, az a része, 5 azt jelenti, hogy az egyes pontszám 20 vevők. A legutóbb vásárlásokat végrehajtó 20 vevő 5-ös recency pontszámot kap. A következő 20 felhasználó recency pontszáma 4, és így tovább. Ha 50 vevők, 10 vevő van-e a recency pontszám 5, 10 van a recency pontszám 4, és így tovább. 
    - A **Prioritás** mezőben válassza ki, hogy milyen súlyú legyen a recency paraméter a többi paraméterhez képest a vevő RFM-pontszámának számításakor. Például előfordulhat, hogy több érték helyezze a recency pontszám, mint a pénzügyi pontszám. 
    - A **Szorzó** mezőbe írja be a recency pontszám szorzószámának értékét. Ha nem ad meg értéket, az eredmény nem kell szorozni. 
    - Az **Időszak** mezőben, válassza ki azt az időtartamot, ameddig a recency pontszám számítása meg kell, hogy történjen. Ha például a hét vagy hónap szerint.
   
6.  A **Gyakoriság** gyorslapon hajtsa végre a következő műveletet: 
    - A **Részlegek** mezőbe írja be a részlegek vagy a csoportok számát, amely a vevők gyakorisági pontszámának kiszámításához használt szám. 
    - A **Prioritás** mezőben válassza ki, hogy milyen súlyú legyen a gyakorisági paraméter a többi paraméterhez képest a vevő RFM-pontszámának számításakor. 
    - A **Szorzó** mezőbe írja be a gyakorisági pontszám szorzószámának értékét. Ha nem ad meg értéket, az eredmény nem kell szorozni.
   
7.  A **Pénzügyi** gyorslapon hajtsa végre a következő műveletet: 
    - A **Részlegek** mezőbe írja be a részlegek vagy a csoportok számát, amely a vevők pénzügyi pontszámának kiszámításához használt szám. 
    - A **Prioritás** mezőben válassza ki, hogy milyen súlyú legyen a pénzügyi paraméter a többi paraméterhez képest a vevő RFM-pontszámának számításakor. 
    - A **Szorzó** mezőbe írja be a pénzügyi pontszám szorzószámának értékét. Ha nem ad meg értéket, az eredmény nem kell szorozni. 
    - A **Bruttó/nettó** mező azt jelzi, hogy a rendszernek a vevő bruttó vagy nettó teljes számlázott összege alapján kell-e számítania a pénzügyi pontszámot. 
    - Ha a vevő által visszaküldött összegeket le kell vonni a vevő teljes számlaösszeg számításában, jelölje be a **Visszáru levonása** négyzetet. 
 
## <a name="view-a-customers-rfm-score"></a>Egy vevő RFM pontszámának megtekintése
Használja az alábbi eljárást egy vevő RFM pontszámának megtekintéséhez. 

1.  Lépjen a **Hívásközpont** > **Naplók** > **Ügyfélszolgálat** ponthoz. 

2.  Az **Ügyfélszolgálat** lap **Ügyfélszolgálat** ablaktáblájában válassza ki a kereséshez használt kulcsszó típusát, és írja be a keresett szöveget a keresőmezőbe.

3.  Válassza a **Keresés** lehetőséget.

4.  Az a **Vevőkeresés** lapon válassza ki a kívánt vevői rekordot, és kattintson a **Vevő kiválasztása** pontra. 

Az RFM-pontszám a **Rendelés előzményei** csoportban jelenik meg, az **Ügyfélszolgálat** lap jobb oldalán. 

## <a name="view-or-clear-the-history-of-an-rfm-analysis-record"></a>RFM-elemzési rekord előzményeinek megtekintése és törlése
Az alábbi eljárással tudja megtekinteni vagy törölni egy RFM-elemzés rekordjának előzményeit. 

1.  Lépjen a **Hívásközpont** > **Időszakos** > **RFM analízis** ponthoz.

2.  Az **RFM-analízis** lapon válassza ki a megtekinteni kívánt rekordot.

3.  A rekordok előzményeinek megtekintéséhez válassza ki az **Előzmények** gyorslapot.

4.  A rekord előzményeinek törléséhez válassza ki az **Előzmények törlése** lehetőséget.

