---
title: Költségösszesítési irányelv többletköltségek kiszámítása
description: Ez a témakör tájékoztatást nyújt a másodlagos költségelemek helyes szintjének meghatározásáról és az olyan költségszerzési szabályok létrehozásáról, amelyek illeszkednek a szervezet jelentéseibe és a költségek nyomon követhetőségébe.
author: AndersGirke
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMCostRollupRule, CAMDimensionHierarchy, CAMOverheadRatePolicy
audience: Application User
ms.reviewer: roschlom
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: b71dc9b5394ee35b76ead292b72951ece0d1d03d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5226317"
---
# <a name="cost-rollup-policy-and-overhead-calculation"></a>Költségösszesítési irányelv többletköltségek kiszámítása 

[!include [banner](../includes/banner.md)]

A Költségkönyvelés lehetővé teszi, hogy betekintést nyerjen a költségeknek a szervezeten belül szállított termékekhez és szolgáltatásokhoz való kapcsolatáról. A költségek átláthatóságának megítéléséhez kulcsfontosságú a költségfelosztás megvalósítása a megfelelő felosztási alapon a költségobjektumok között. Alapértelmezés szerint a költségfelosztás az elsődleges költségelemre érvényes, ami bizonyos helyzetekben kívánatos, de vannak olyan jellemzői, amelyeket figyelembe kell venni.

-   A kiegészítő költségobjektumok nullás egyenleggel végződnek az elsődleges költségelem után az általános költségek felszámítását követően.

-   Azoknak a költségbejegyzéseknek a mennyisége, amelyeket a járulékosköltség-számítás generál, magas lehet.

-   Nem lehet követni a költségek áramlását a költségobjektumok között.

Ezen következmények elkerülése érdekében a Költségkönyvelés segítségével költségfelosztást állíthat be a szervezet vezetői jelentési követelményeihez. Ez a témakör segítséget nyújt a másodlagos költségelemek helyes szintjének meghatározásáról és az olyan költségszerzési szabályok létrehozásáról, amelyek illeszkednek a szervezet jelentéseibe és a költségek nyomon követhetőségébe.

> [!NOTE]
> Ha a jelentési követelmények megváltoznak, módosíthatja a konfigurációkat.

## <a name="example-of-cost-rollup-policy-setup"></a>Költségösszesítési irányelv beállításának példája

Képzelje el, hogy egy szervezet a következő struktúrával rendelkezik, 4 költségközponttal.

![Példa szervezeti felépítésre](./media/dimension-hierarchy-org.png)

**Költségobjektum dimenziója**

| Költséghelyek | Leírás          |
|--------------|-----------|
| CC001        | HR        |
| CC002        | Pénzügy   |
| CC003        | Szerelvény  |
| CC004        | Csomagolás |

**Költségösszetevő-dimenzió**

| Költségösszetevők | Leírás | Típus    |
|---------------|-------------|---------|
| 1001          | Villamos energia | Elsődleges |
| 1002          | Bérek    | Elsődleges |
| 1003          | Hirdetés | Elsődleges |

A szervezeti jelentési követelményeket teljesítő dimenziók hierarchiája az alábbiak szerint állítható be.

**Dimenzióhierarchia részletei**

| Dimenzióhierarchia neve | Dimenzió    | Dimenzióhierarchia típus neve      | Hozzáférési lista hierarchia |
|--------------------------|--------------|------------------------------------|-----------------------|
| Szervezet             | Költséghelyek | Dimenzió-osztályozáshierarchia | Nincs                    |

**Dimenzióhierarchia**

|    &nbsp;    | Dimenziótag tartományok | &nbsp;              |
|--------------|-------------------------|---------------------|
| **Csomópontok**        | **Forrásdimenzió-tag**   | **Céldimenziótag** |
| Szervezet |                         |                     |
| &nbsp;&nbsp;Rendszergazda             |                         |                     |
| &nbsp;&nbsp;&nbsp;&nbsp;Pénzügy              | CC001                   | CC001               |
| &nbsp;&nbsp;&nbsp;&nbsp;HR               | CC002                   | CC002               |
| &nbsp;&nbsp;Termelés               |                         |                     |
| &nbsp;&nbsp;&nbsp;&nbsp;Csomagolás              | CC003                   | CC003               |
| &nbsp;&nbsp;&nbsp;&nbsp;Szerelvény             | CC004                   | CC004               |

Az irányelvi követelményeket teljesítő dimenziók hierarchiája az alábbiak szerint állítható be.

**Dimenzióhierarchia részletei**

| Dimenzióhierarchia neve | Dimenzió     | Dimenzióhierarchia típus neve      |
|--------------------------|---------------|------------------------------------|
| Eredménykimutatás  | Költségösszetevők | Dimenzió-osztályozáshierarchia |

**Dimenzióhierarchia**

|      &nbsp;             | Dimenziótag tartományok |      &nbsp;         |
|-------------------------|-------------------------|---------------------|
| Csomópontok                   | Forrásdimenzió-tag   | Céldimenziótag |
| Eredménykimutatás |                         |                     |
| &nbsp;&nbsp;&nbsp;&nbsp;Elsődleges költség                    | 10001                   | 10003               |

A főkönyvi bejegyzések feldolgozását követően a költségobjektum szerinti költségbejegyzés-egyenleg a következőképpen néz ki.

|      &nbsp;          | **Költségobjektum** | &nbsp;    |  &nbsp;   |  &nbsp;   | **Összesen**     |
|----------------------|-----------------|-----------|-----------|-----------|---------------|
| **Költségösszetevő**     | **CC001**       | **CC002** | **CC003** | **CC004** |               |
| **1001 Villamos energia** | 100,00          | 200 000    | 6.000,00  | 2.000,00  | **8.300,00**  |
| **1002 Bérek**    | 10.000,00       | 10.000,00 | 8.000,00  | 6.500,00  | **34.500,00** |
| **1003 Hirdetés** | 0,00            | 4.000,00  | 0,00      | 0,00      | **4.000,00**  |
|                      | 10.100,00       | 14.200,00 | 14.000,00 | 8.500,00  | **46.800,00** |

**Statisztikai dimenzió**

| Statisztikai elemek |    Leírás   |
|----------------------|------------------|
| SE-1                 | HR-szolgáltatások      |
| SE-2                 | Pénzügyi szolgáltatások |

A CC001 HR költségobjektum több költségobjektumhoz is HR-szolgáltatásokat rendel.

A HR-szolgáltatásokat a következő mennyiségelosztás jellemzi.

| Költségobjektum | Leírás |   HR-szolgáltatások |
|-------------|-------------|----|
| CC002       | Pénzügy     | 35 |
| CC003       | Szerelvény    | 55 |
| CC004       | Csomagolás   | 10 |

A CC002 Pénzügy költségobjektum több költségobjektumhoz is pénzügyi szolgáltatásokat rendel.

A pénzügyi szolgáltatásokat a következő mennyiségelosztás jellemzi.

| Költségobjektum |   Leírás    |  Pénzügyi szolgáltatások   |
|-------------|------------------|----|
| CC003       | Szerelvény         | 65 |
| CC004       | Csomagolás        | 35 |

A költségfelosztási irányelveket a következőképpen lehet megadni.

| Irányelv neve | Leírás     | Költségobjektum dimenzióhierarchia | Statisztikai dimenzió | Költségösszetevő-dimenzió |
|-------------|-----------------|---------------------------------|-----------------------|------------------------|
| 2017        | Költségfelosztás | Szervezet                    | Statisztikai elemek  | Költségösszetevők          |

A költségfelosztási szabályokat a következőképpen lehet megadni.

| Költségobjektum dimenzióhierarchia-csomópont | Költség működése | Felosztás alapja        |
|--------------------------------------|---------------|------------------------|
| CC001                                | Összesen         | **HR-szolgáltatások**        |
| CC002                                | Összesen         | **Pénzügyi szolgáltatások** |

<a name="brhow-cost-flows-between-cost-centers"></a><br>A költségek áramlása a költségközpontok között 
---------------------------------------------------

Ha meg szeretné tudni, hogyan megy végbe a költségforgalom a szervezet költséghelyei között, akkor költségelemeket hozhat létre **Másodlagos** típussal minden egyes költséghely számára. Ezeket a költségelemeket ezután a költségközpontok közötti egyenlegek átadására használják a járulékos költségek számítása során.

A költségelemek dimenziótagjait a következőképpen lehet megadni.

| Költségösszetevők | Típus          |     &nbsp;    |
|---------------|---------------|---------------|
| 1001          | Villamos energia   | Elsődleges       |
| 1002          | Bérek      | Elsődleges       |
| 1003          | Hirdetés   | Elsődleges       |
| **SC-CC001**  | **HR**        | **Másodlagos** |
| **SC-CC002**  | **Pénzügy**   | **Másodlagos** |
| **SC-CC003**  | **Szerelvény**  | **Másodlagos** |
| **SC-CC004**  | **Csomagolás** | **Másodlagos** |

Az **Eredménykimutatás** dimenzióhierarchiát frissíteni kell az új dimenziótagokkal, hogy a dimenzióhierarchia tartalmazza a megfelelő adatokat, amelyek felhasználhatók a jelentések és irányelvek meghatározásához.

**Dimenzióhierarchia részletei**

| Dimenzióhierarchia neve | Dimenzió     | Dimenzióhierarchia típus neve      |
|--------------------------|---------------|------------------------------------|
| Eredménykimutatás  | Költségösszetevők | Dimenzió-osztályozáshierarchia |

**Dimenzióhierarchia**

|      &nbsp;             | Dimenziótag tartományok |  &nbsp;             |
|-------------------------|-------------------------|---------------------|
| Csomópontok                   | Forrásdimenzió-tag   | Céldimenziótag |
| Eredménykimutatás |                         |                     |
| &nbsp;&nbsp;&nbsp;&nbsp;Elsődleges költség                        | 10001                   | 10003               |
| &nbsp;&nbsp;&nbsp;&nbsp;Másodlagos költség                         | **SC-CC001**            | **SC-CC004**        |

Hozzon létre egy **Költségösszegzési irányelvet**, ahol az egyes költséghelyekhez a kapcsolódó **Másodlagos** típusú költségelemet rendeli a rendszer.

**Költségösszegzési irányelvek**

| Irányelv neve | Leírás | Költségobjektum dimenzióhierarchia | Költségösszetevő dimenzióhierarchia |
|-------------|-------------|---------------------------------|----------------------------------|
| 2017        | Költségforgalom   | Szervezet                    | Eredménykimutatás          |

**Költségösszegzési szabályok**

| Költségobjektum dimenzióhierarchia-csomópont | Költségösszetevő dimenzióhierarchia-csomópont | Másodlagos költségösszetevő |
|--------------------------------------|---------------------------------------|------------------------|
| CC001                                | Eredménykimutatás               | **SC-CC001**           |
| CC002                                | Eredménykimutatás               | **SC-CC002**           |
| CC003                                | Eredménykimutatás               | **SC-CC003**           |
| CC004                                | Eredménykimutatás               | **SC-CC004**           |

## <a name="perform-overhead-calculation"></a>Járulékosköltség-számítás végrehajtása

**Napló**

| Napló | Napló típusa            | Pénzügyi naptári időszak | Év | Időszak | Verzió       |
|---------|-------------------------|------------------------|------|--------|---------------|
| 00002   | Költségfelosztási napló | Pénzügyi                 | 2017    | 1. időszak | Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak |

A rendszer akkor alkalmazza a **Költségösszegzési irányelvet**, amikor létrehozza a **Költségobjektum-egyenlegek naplóbejegyzéseit**.

**Költségobjektum-egyenlegek naplóbejegyzései**

| Könyvelési dátum | Költségobjektum | Leírás  | Költségösszetevő | Leírás |  Összeg |
|-----------------|-------------|--------------|----------|-----------|-----------|
| 2017/01/31      | CC001       | HR           | SC-CC001 | HR        | 10.100,00 |
| 2017/01/31      | CC002       | Pénzügy      | SC-CC002 | Pénzügy   | 17.735,00 |
| 2017/01/31      | CC003       | Szerelvény     | SC-CC003 | Szerelvény  | 31.082,75 |
| 2017/01/31      | CC004       | Csomagolás    | SC-CC004 | Csomagolás | 15.717,25 |

> [!NOTE]
> A naplóbejegyzések a **Költségösszegzési irányelv** szabályai alapján kerülnek létrehozásra, ha létezik irányelv. A megjelenített egyenleg a járulékos költségek számításának egyenlege.

A naplóbejegyzésekből megnyitott **Költségobjektum költségegyenlegnapló-bejegyzéseinek részletei** oldal megjeleníti az egyenleg lekérésének módját.

**Példa: a CC002 Pénzügy költségobjektum naplóbejegyzése**

**Költségobjektum költségegyenlegnapló-bejegyzéseinek részletei**

| Költségösszetevő-dimenziótag | Leírás |  Összeg   |
|-------------------------------|-------------|-----------|
| 1001                          | Villamos energia | 200 000    |
| 1002                          | Bérek    | 10.000,00 |
| 1003                          | Hirdetés | 4.000,00  |
| SC-CC001                      | HR          | 3.535,00  |

**Költségbejegyzések, melyeket a járulékosköltség-számítás generál**

| Költségobjektum | Leírás  | Költségösszetevő   | Leírás  |        Összeg     |       Könyvelési dátum     |
|-------------|--------------|----------|-----------------|-------------|------------|
| CC001       | HR           | SC-CC001 | HR              | \-10.100,00. | 2017/01/31 |
| CC002       | Pénzügy      | SC-CC001 | HR              | 3.535,00    | 2017/01/31 |
| CC003       | Szerelvény     | SC-CC001 | HR              | 5.555,00    | 2017/01/31 |
| CC004       | Csomagolás    | SC-CC001 | HR              | 1.010,00    | 2017/01/31 |
| CC002       | Pénzügy      | SC-CC002 | Pénzügy         | \-17.735,00. | 2017/01/31 |
| CC003       | Szerelvény     | SC-CC002 | Pénzügy         | 11.527,75   | 2017/01/31 |
| CC004       | Csomagolás    | SC-CC002 | Pénzügy         | 6.207,25    | 2017/01/31 |

Miután befejeződik a **járulékos költség** számítása, az eredményekről olyan eszközök segítségével készíthet jelentést, mint a Microsoft SharePoint Workspace, az Excel vagy a Power BI.

## <a name="view-reporting-in-excel"></a>Jelentések megtekintése Excelben 

A dimenzióhierarchiák lehetővé teszik az adatok különböző aggregációs szinteken történő megtekintését.

Íme egy példa a Power Pivot kimutatásokról az Excelben:

| **Eredménykimutatás** | **Költségobjektum** |      &nbsp;    |   &nbsp;      |     &nbsp;    |  **Összesen**    |
|-----------------------------|-----------------|----------------|---------------|---------------|---------------|
|                             | **CC001**       | **CC002**      | **CC003**     | **CC004**     |               |
| **Elsődleges költség**            | **10.100,00**   | **14.200,00**  | **14.000,00** | **8.500,00**  | **46.800,00** |
| &nbsp;&nbsp;&nbsp;&nbsp;1001.                            | 100,00          | 200 000         | 6.000,00      | 2.000,00      | **8.300,00**  |
| &nbsp;&nbsp;&nbsp;&nbsp;1002.                            | 10.000,00       | 10.000,00      | 8.000,00      | 6.500,00      | **34.500,00** |
|&nbsp;&nbsp;&nbsp;&nbsp;1003.                             | 0,00            | 4.000,00       | 0,00          | 0,00          | **4.000,00**  |
|**Másodlagos költség**                            | **-10.100,00**  | **-14.200,00** | **17,082,75** | **7.217,25**  | **0,00**      |
|&nbsp;&nbsp;&nbsp;&nbsp;SC-CC001                            | \-10.100,00.     | 3.535,00       | 5.555,00      | 1.010,00      | **0,00**      |
|&nbsp;&nbsp;&nbsp;&nbsp;SC-CC002                             | 0,00            | \-17.735,00.    | 11.527,75     | 6.207,25      | **0,00**      |
|&nbsp;&nbsp;&nbsp;&nbsp;SC-CC003                            | 0,00            | 0,00           | 0,00          | 0,00          | 0,00          |
|&nbsp;&nbsp;&nbsp;&nbsp;SC-CC004                             | 0,00            | 0,00           | 0,00          | 0,00          | 0,00          |
| **Összesen**                   | **0,00**        | **0,00**       | **31.082,75** | **15.717,25** | **46.800,00** |

A **Költségösszegzési irányelv** és a **Másodlagos típusú költségelemek** lehetővé teszik, hogy a költségjelentés költséghelyenkénti elsődleges költségét a belső jelentéskészítés során elsődleges költségként hagyja a **Járulékos költség számítása** után.

Ha ugyanezt a példát a **Költségösszegzési irányelv** létrehozása nélkül hajtanánk végre, akkor a jelentési eredmény az alábbiak szerint alakulna. A költségforgalom helyesen történik, de elveszik a nyomon követhetőség és a költséghelyek közötti költségforgalomra való rálátás.

| **Eredménykimutatás** | **Költségobjektum** |   &nbsp;  |    &nbsp;     |  &nbsp;       |          **Összesen**  |
|-----------------------------|-----------------|-----------|---------------|---------------|---------------|
|                             | **CC001**       | **CC002** | **CC003**     | **CC004**     |               |
| **Elsődleges költség**            | **0,00**        | **0,00**  | **31.082,75** | **15.717,25** | **46.800,00** |
|&nbsp;&nbsp;&nbsp;&nbsp;1001.                              | 0,00            | 0,00      | 6.207,75      | 2.092,25      | **8.300,00**  |
| &nbsp;&nbsp;&nbsp;&nbsp;1002.                             | 0,00            | 0,00      | 22.275,00     | 12.225,00     | **34.500,00** |
|&nbsp;&nbsp;&nbsp;&nbsp;1003.                              | 0,00            | 0,00      | 2600,00       | 1.400,00      | **4.000,00**  |
|**Másodlagos költség**                            | **0,00**        | **0,00**  | **0,00**      | **0,00**      | **0,00**      |
|&nbsp;&nbsp;&nbsp;&nbsp; SC-CC001                             | 0,00            | 0,00      | 0,00          | 0,00          | **0,00**      |
|&nbsp;&nbsp;&nbsp;&nbsp; SC-CC002                             | 0,00            | 0,00      | 0,00          | 0,00          | **0,00**      |
|&nbsp;&nbsp;&nbsp;&nbsp; SC-CC003                             | 0,00            | 0,00      | 0,00          | 0,00          | 0,00          |
|&nbsp;&nbsp;&nbsp;&nbsp; SC-CC004                             | 0,00            | 0,00      | 0,00          | 0,00          | 0,00          |
| **Összesen**                   | **0,00**        | **0,00**  | **31.082,75** | **15.717,25** | **46.800,00** |

Ez a témakör segítséget nyújt a másodlagos költségelemek helyes szintjének meghatározásáról és az olyan költségszerzési szabályok létrehozásáról, amelyek illeszkednek a szervezet jelentéseibe és a költségek nyomon követhetőségébe.

A **Költségfelosztás** és a **Költségösszegzési irányelvek** egyértelmű elkülönítése rugalmasságot biztosít a folyamatos frissítések végrehajtásához anélkül, hogy a frissítések egymásra hatással lennének.



## <a name="additional-resources"></a>További erőforrások
-  [Költségobjektum-dimenziók](cost-objects.md)
-  [Költségösszetevő-dimenziók](cost-elements.md)
-  [Dimenzióhierarchia](dimension-hierarchy.md)
-  [Járulékos költség számítása](overhead-calculation.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]