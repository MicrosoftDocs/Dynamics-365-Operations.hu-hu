---
title: Eszköz KPI-k
description: Ez a témakör az Eszközkezelés eszköz KPI-ait ismerteti.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 1aee14c869d84bef38a738bfe78fd09ee7f82d94
ms.sourcegitcommit: fb66731f05207094149a6bc7b8549a4dabbb071a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/22/2019
ms.locfileid: "2652379"
---
# <a name="asset-kpis"></a>Eszköz KPI-k

[!include [banner](../../includes/banner.md)]

 

Az Eszközkezelésben különböző teljesítménymutatókat (KPI-ket) lehet kiszámítani az eszközök és az eszköztípusok esetében. A teljesítménymutatók segítségével áttekintést kaphat az eszközökről, például az üzemidőről, az állásidő, a javítási idő és a meghibásodások közötti átlagos időtartam (MTBF) tekintetében.

1. Kattintson az **Eszközkezelés** > **Lekérdezések** > **Eszközök** > **eszköz KPI-k** elemre.

2. Az **Eszköz KPI-k számítása** párbeszédpanelen kiválaszthatja a számításhoz használandó **Időskálát**, valamint a **Kezdő dátum** és a **Záró dátum** mezőben egy időszakot. 

3. A **Szerepeltetni kívánt rekordok** gyorslapján kiválaszthatja a számításban szerepeltetni kívánt eszközöket és eszköztípusokat.

4. Kattintson az **OK** gombra az számítás indításához.

5. Az **Áttekintés** gyorslapon a számítások eredményei megjelennek a rács nézetben. Minden eszköz külön sorban jelenik meg.

6. A **Kiválasztott sor KPI-ai** gyorslap esetében az **Áttekintés** gyorslapon kiválasztott eszköz számításait tekintheti meg. A KPI-értékek kategorizálására az **Idő**, a **Rendelkezésre állás**, a **Munkarendelések**, a **Karbantartás**, a **Hibák**, a **Karbantartási állásidő** és a **Költség**.

A lenti táblázatban megtalálja a mezők leírását az **Eszköz KPI-k** oldalán.

| Mező                   | Leírás                                                                                                                                                                                                                                                                                           |
|-------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Eszköz                   | Eszköz azonosítója.                                                                                                                                                                                                                                                                                             |
| Teljes idő              | A számításban használt, a naptárban beállított összes idő. Ha az eszköz egy erőforráshoz kapcsolódik, a kapcsolódó erőforrásnaptár használatos. Ha az eszköz nem kapcsolódik egy erőforráshoz, akkor a program az **Alapnaptár** mezőben, az **Eszközkezelés paraméterei** alatt kiválasztott naptárat használja. |
| Bekapcsolási idő                  | Teljes idő mínusz a leállás.                                                                                                                                                                                                                                                                            |
| Leállás                | A kiválasztott időszakra vonatkozóan az eszközre vonatkozó karbantartás miatti üzemkimaradás regisztrációk.                                                                                                                                                                                                                              |
| Javítási idő             | A javítási munkarendeléseken felhasznált munkaórák száma összesen.                                                                                                                                                                                                                                            |
| Elérhetőség %          | Üzemidő osztva a teljes idővel és a szorozva százzal.                                                                                                                                                                                                                                                   |
| Hibák száma        | A kiválasztott időszakra vonatkozóan az eszköz hibatüneteihez regisztrált hibaokok száma.                                                                                                                                                                                                             |
| MTBF                    | A hiba közötti átlagos idő, amely a kiválasztott időszakban a teljes idő és az eszközre bejegyzett hibák számának hányadosa. Ha a hibák száma nulla, akkor az MTBF a teljes időre van állítva.                                                                                                                   |
| Sikertelenség mértéke               | 1 elosztva az MTBF-fel.                                                                                                                                                                                                                                                                                    |
| MRT                     | Átlagos javítási idő, amely a kiválasztott időszakban a javítási idő és az eszközre bejegyzett hibák számának hányadosa. Ha a hibák száma nulla, akkor az MRT a javítási időre van állítva.                                                                                                                           |
| Leállások száma         | Az eszközön létrehozott regisztrált karbantartás miatti üzemkimaradások száma.                                                                                                                                                                                                                                     |
| MTBS                    | A megállók közötti átlagos idő, amely a teljes idő osztva a karbantartás miatti üzemkimaradások számával. Ha a karbantartás miatti üzemkimaradás regisztrációk száma nulla a kiválasztott időszakban, akkor a MTB-értéke a teljes idő.                                                                                      |
| Megelőző költség         | A tárgyi eszközhöz a kiválasztott időszakban a „Preventív” költségtípushoz feladott költségek. A költségtípusok a munkarendelés-típusokon állíthatók be.                                                                                                                                                                       |
| Javító költség         | A tárgyi eszközhöz a kiválasztott időszakban a „Helyesbítő” költségtípushoz feladott költségek. A költségtípusok a munkarendelés-típusokon állíthatók be.                                                                                                                                                                       |
| Helyettesítő érték       | Az eszközön a helyettesítési költségként megadott érték.                                                                                                                                                                                                                                                  |
| Eszköztípus             | Az eszközön kiválasztott eszköztípus azonosítása.                                                                                                                                                                                                                                             |
| Gyártó           | Az eszközön kiválasztott gyártó azonosítása.                                                                                                                                                                                                                                                 |
| Típus                   | Az eszközön kiválasztott gyártómodell azonosítása.                                                                                                                                                                                                                                           |
| Kezdő dátum               | A KPI-számítás kezdő dátuma. Ha az eszközt a számításhoz kiválasztott kezdő dátum után hozták létre, ebben a mezőben megjelenik az eszköz kezdő dátuma.                                                                                                                                  |
| Záró dátum                 | A KPI-számítás záró dátuma. Ha az eszközt a számításhoz kiválasztott záró dátum előtt inaktívként regisztrálták, akkor ebben a mezőben látható az a dátum, amelytől kezdve az eszköz már nem aktív.                                                                                               |
| Időskála              | A KPI-k számításakor kiválaszthatja a használandó időskálát: óra, nap vagy hét.                                                                                                                                                                                                            |
| Elérhetőség            | Az üzemidő osztva a teljes idővel.                                                                                                                                                                                                                                                                         |
| Munkarendelések             | A KPI-számításban szereplő munkarendelések teljes száma.                                                                                                                                                                                                                                          |
| Munkarendelés időpontja         | A munkarendeléseken felhasznált munkaórák száma összesen.                                                                                                                                                                                                                                               |
| Elsődleges munkarendelések     | A KPI-számításban szereplő elődleges munkarendelések száma.                                                                                                                                                                                                                                        |
| Másodlagos munkarendelések   | A KPI-számításban szereplő másodlagos munkarendelések száma.                                                                                                                                                                                                                                      |
| Karbantartási munkarendelések | A KPI-számításban szereplő karbantartási munkarendelések száma. A karbantartási munkarendelés olyan munkarendelés, amelyhez nincs megadva a hiba oka.                                                                                                                                                             |
| Karbantartási idő        | A karbantartási munkarendeléseken felhasznált munkaórák száma összesen.                                                                                                                                                                                                                                       |
| Munkarendelések javítása      | A KPI-számításban szereplő javítási munkarendelések száma. A javítási munkarendelés olyan munkarendelés, amelyhez meg van adva a hiba oka.                                                                                                                                                                        |
| Megbízhatóság %           | Számítás az eszközhöz tartozó hibás regisztrációk várható exponenciális fejlődése alapján, ami azt jelenti, hogy az eszköz az amortizáció miatt kevésbé megbízható lesz. A KPI kiszámítása az MTBF és a teljes idő alapján történik.                                                            |
| MTPS                    | A termelési leállások átlagos ideje, amely a karbantartás miatti üzemkimaradás osztva a karbantartás miatti üzemkimaradások számával. Ha a karbantartás miatti üzemkimaradás regisztrációk száma nulla a kiválasztott időszakban, akkor a MTPS-értéke a zéró.                                                                               |
| Teljes költség              | Az eszközre a kiválasztott időszakban feladott összes költség.                                                                                                                                                                                                                                              |
| Beruházási költség         | A tárgyi eszközhöz a kiválasztott időszakban a „Befektetés” költségtípushoz feladott költségek. A költségtípusok a munkarendelés-típusokon állíthatók be.                                                                                                                                                                       |

Az alábbi ábra négy eszköz KPI-számításának képernyőképét jeleníti meg.

![A KPI-számítás négy eszközre vonatkozó képernyőképe](media/11-controlling-and-reporting.png)

- Több eszköz is kiválasztható az **Összes eszköz** lehetőségnél, majd kattintson az **Eszköz KPI** gombra az **Általános** lapon. Ezután kattintson az **OK** gombra az **Eszköz KPI-k kiszámítása** párbeszédpanelen a kiválasztott eszközökhöz tartozó KPI-k számításához.  
- A KPI-számítás eredményei nem kötelező jelleggel tartalmazhatják a [karbantartás miatti üzemkimaradás regisztrációkat](../work-orders/maintenance-downtime.md), a karbantartás miatti üzemkimaradás okkódok beállításának és használatának beállításától függően. 

