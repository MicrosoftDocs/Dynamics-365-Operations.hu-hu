---
title: Használatijog-eszközök értékvesztésének könyvelése
description: Ez a témakör az értékvesztést rögzítő funkciókat ismerteti, és a 842-es könyvelési standardok kodifikációs témakörének eszközértékcsökkenési ütemezését módosítja.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 3b648075a681fb01720149aac4f479dccf963489
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5229526"
---
# <a name="impair-right-of-use-assets"></a>Használatijog-eszközök értékvesztésének könyvelése

[!include [banner](../includes/banner.md)]

Ha a használatijog-eszköz (ROU) könyv szerinti értéke nem hasznosítható meg, előfordulhat, hogy meg kell vizsgálnia, hogy az eszköz értékvesztett-e. Ha úgy dönt, hogy az eszköz értékvesztett, az eszközlízing rögzítheti az értékvesztést, és ennek megfelelően módosíthatja az értékcsökkenési ütemezést. Ez a témakör az értékvesztést rögzítő funkciókat ismerteti, és a 842-es könyvelési standardok kodifikációs témakörének értékcsökkenési ütemezését módosítja. Ugyanez a módszer vonatkozik a nemzetközi pénzügyi beszámolási szabvány 16 (IFRS 16) lízingre is.

A ROU-eszköz fennmaradó egyenlegét a fennmaradó időszakok száma alapján pontosan amortizálják, függetlenül attól, hogy a lízinget az IFRS 16 vagy az ASC 842 szerinti operatív lízing alapján pénzügyi lízingnek minősítették-e.

## <a name="impair-an-rou-asset"></a>ROU-eszköz értékvesztésének könyvelése

1. Lépjen a károsult lízingre, és válassza a **Könyvek** lehetőséget.
2. A Műveleti ablaktáblán kattintson a **Értékvesztés** elemre.
3. A megjelenő párbeszédpanel **Értékvesztés összege** mezőjében adja meg az eszközértékvesztés összegét. A ROU-eszköz csökkentéséhez pozitív értéket kell megadnia.
4. A **Tranzakció dátuma** mezőben adja meg azt a dátumot, amikor az értékvesztés tételt könyvelni kell.
5. A **Fennmaradó időszakok** mezőben adja meg az amortizálandó hónapok fennmaradó számát.
6. Ha azt szeretné, hogy a rendszer automatikusan könyvelje az értékvesztési költségnapló-bejegyzést, kapcsolja be a **Közzététel** paramétert. Ha kikapcsolja ezt a paramétert, a rendszer létrehozza a bejegyzést, de nem könyveli azt. Ezután könyvelheti a bejegyzést az **Eszközlízing naplók** oldalon.
7. Állítsa az **Előnézetes verzió közzététel előtt** beállítást **Igen** értékre a javasolt tétel létrehozásának vagy feladási helyének megtekintéséhez.
8. Állítsa a **Könyv bezárása** beállítást **Igen** értékre a lízingkönyv bezárásához. Nem vonható vissza ez a művelet. A tételek nem könyvelhetők lezárt lízingekkel, és a lezárt lízingek nem módosíthatók.
9. Válassza az **OK** lehetőséget az értékvesztési bejegyzés létrehozásához vagy könyveléséhez.
10. Az eszközértékcsökkenési ütemezés megtekintéséhez nyissa meg a lízingkönyv értékcsökkenési ütemezését. Az eszköz mostantól lineárisan leértékelt a **Fennmaradó időszak** mezőben megadott hónapok számának megfelelően.
11. Az értékvesztési költségnapló bejegyzésének megtekintéséhez válassza az **Eszközlízing napló** lehetőséget az értékvesztett lízingkönyv műveletablakában. A rendszer létrehoz egy naplóbejegyzést, amely megterheli az értékvesztési költség könyvelési számlát, és jóváírja a lízingeszköz könyvelési számláját.
12. A ROU-eszköz új könyv szerinti értékének megtekintéséhez válassza az **Eszköztranzakciók** lehetőséget a lízingkönyv műveletablakában.

## <a name="example-of-rou-asset-impairment"></a>Példa a ROU-eszköz értékvesztésére

Ebben a példában a lízing egy nem specializált eszköz, amely nem adja át a tulajdonjogot, és nem adja meg a lízingbevevőnek a vásárlás lehetőségét.

### <a name="setup"></a>Beállítás

Az alábbi táblázatok a példában használt lízing **Általános** és **Fizetési ütemezési sorai** fülön beállított értékeket mutatják be.

**Általános fül**

| Mező                      | Érték            |
|----------------------------|------------------|
| Az eszköz valós értéke    | 600,000          |
| Járulékos kamatláb | 7%               |
| Összetételi intervallum       | Évente         |
| Eszköz hasznos élettartama (hónap) | 600              |
| Annuitás típusa               | Szokásos annuitás |
| Kezdési dátum          | 2019.01.01.       |

**Kifizetési lista sorai fül**

| Mező             | Érték      |
|-------------------|------------|
| Kezdés dátuma        | 2019.01.01.   |
| Időszak intervalluma   | Havi    |
| Időszakok           | 120        |
| Befejezés          | 2028.12.31. |
| Fizetés gyakorisága | Évente   |
| Fizetés összege    | 10,000     |

### <a name="steps"></a>Lépések

1. Miután létrehozta a lízinget a témakörben korábban leírtak szerint, lépjen a lízingkönyvre, és erősítse meg a fizetési ütemezést. Ezután adja fel a kezdeti megjelenítési naplóbejegyzést. Az eredeti ROU-eszköz és lízingkötelezettségnek 70.235,81 dollárnak kell lennie. Ebben a példában a lízinget az ASC 842 szerinti operatív lízingnek minősítették.
2. Futtassa a kötegnapló-folyamatot háromszor, hogy szimulálja a három év áthaladását a lízingfizetések, a kamatköltségek és az értékcsökkenési költségek esetében.
3. Miután befejezte mindhárom kötegfeladat futtatását, lépjen vissza a lízingkönyvbe, és nyissa meg a forrás- és eszköztranzakciók tábláit a ROU-eszköz és a lízingkötelezettség aktuális könyv szerinti értékének megtekintéséhez. Három év elteltével a kötelezettség értékének körülbelül -53.893,00 dollárnak kell lennie, és az eszköz értékének körülbelül 53.893,00 dollárnak kell lennie. 

    Három év elteltével a vállalkozás értékvesztési vizsgálatokat végez, és megállapítja, hogy a ROU-eszköz értékvesztése 35.000 dollár. Ezt a károsodást most rögzítenie kell.
    
4. Lépjen a lízingkönyvre, majd a Művelet ablaktáblán válassza az **Értékvesztés** lehetőséget.
5. Az **Értékvesztés paraméter** lapon adja meg a következő adatokat.

    | Mező                  | Érték    |
    |------------------------|----------|
    | Értékvesztés összege      | 35,000   |
    | Tranzakció dátuma       | 2022.01.01. |
    | Fennmaradó időszakok      | 84       |
    | Feladás                   | Igen      |
    | Előnézet feladás előtt | Nincs       |
    | Könyv lezárása             | Nincs       |

6. Értékvesztési költség naplóbejegyzés létrehozása és feladása történt. A megtekintéshez nyissa meg az eszköz lízingnaplóját a lízingkönyvben. Figyelje meg, hogy az értékvesztés összegét az Értékvesztés költség feladási számlájára terhelték, és a ROU-eszköz feladási számlát jóváírták.
7. Az értékvesztés nettó hatásának megtekintéséhez lépjen a kötelezettség- és eszköztranzakciók táblához. Figyelje meg, hogy az értékvesztési költség csökkentette a ROU-eszközt, de a lízingkötelezettség könyv szerinti értéke nem változott.

Az értékvesztésnek van még egy hatása, amit figyelembe kell vennie. Mivel a ROU-eszköz összege most már sokkal kisebb, mint a lízingkötelezettség, az összeget másképp kell amortizáltatni, mint korábban. Pontosabban, az eszköz már lineárisan értékcsökkent a lízing teljes, fennmaradó 84 hónapjára, kezdve a tranzakció időpontjától.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]