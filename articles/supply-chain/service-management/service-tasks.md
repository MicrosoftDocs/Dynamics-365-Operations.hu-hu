---
title: Szervizfeladatok áttekintése
description: A szervizfeladatok segítségével lehet leírni azt a feladatot, amelyet a szervizrendelés keretében el kell végezni. Ezt az információt a technikusok és a vevők látják.
author: ShylaThompson
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceTask
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d981972fcdc75de5504ba3341f4ed2cf8f971cb2d13037fd88f01a720cd1cc60
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6782419"
---
# <a name="service-tasks-overview"></a>Szervizfeladatok áttekintése

[!include [banner](../includes/banner.md)]

A szervizfeladatok segítségével lehet leírni azt a feladatot, amelyet a szervizrendelés keretében el kell végezni.
Ezt az információt a technikusok és a vevők látják.

A szervizfeladatok létrehozására a **Szervizfeladatok** lap használható. A szervizfeladat-kapcsolatok létrehozásával a szervizfeladatokat meghatározott szolgáltatási megállapodáshoz vagy szervizrendeléshez lehet társítani. Minden alkalommal, amikor létrehozza a szervizfeladatok egy viszonyát, létrehozhatja a következőket is:

-  Belső megjegyzéseket a feladattal kapcsolatban, mint amilyenek az egy technikus számára lényeges, részletezett műszaki elvárások.

-  Külső megjegyzések, amelyek láthatók a vevő számára. Ezek a vevő és a szolgáltató vállalat megállapodása szerint elvégzendő feladatokról adnak egy kevésbé műszaki jellegű magyarázatot.

Ha beállította a szolgáltatásifeladat‑kapcsolatokat a szervizfeladatok és a szervizrendelés vagy szolgáltatás szerződés között, megadhatja ezt a szolgáltatási feladatot, amikor az aktuális szervizrendelés vagy szolgáltatási szerződés számára szervizrendelési sort vagy szolgáltatási szerződéssort hoz létre.

Amikor szervizrendelési sorokat generál egy szolgáltatási szerződésből, a szolgáltatási szerződés egyes soraihoz rendelt szervizfeladatokat felhasználva csoportosíthatja a szervizrendelési sorokat szervizrendelésekbe.

## <a name="create-a-service-task"></a>Szervizfeladat létrehozása

1. Kattintson a **Szolgáltatáskezelés** \> **Beállítás** \> **Szervizfeladatok** pontra.
2. Hozzon létre egy új sort.
3. Adja meg a szolgáltatás azonosítóját és leírását.

## <a name="example"></a>Példa

Egy technikusnak két feladatot kell elvégeznie egy sebességváltón (GB-1234-as szolgáltatási tárgy) az egyik vevő telephelyén. Egy, a vevőhöz tartozó szolgáltatási szerződés jön létre, és több tranzakció lesz a munkákhoz társítva. A két munkához tartozó szolgáltatási szerződés és a szerződési sorok a következőkben láthatók:

### <a name="service-agreement"></a>Szolgáltatási szerződés

| Project | Szolgáltatási szerződés | Leírás                                  | Csoport   |
|---------|-------------------|----------------------------------------------|---------|
| 9012    | 000008\_001       | Átvizsgálás és rendszeres cserék – GB-1234 | Prémium |

### <a name="service-agreement-lines"></a>Szolgáltatási szerződés sorai

| Leírás             | Tranzakció típusa | A szolgáltatás tárgya | Szervizfeladat |
|-------------------------|------------------|----------------|--------------|
| Átvizsgálás és tisztítás | Óra             | GB-1234        | I/C - GB1234 |
| Utazás                  | Expense          | GB-1234        | I/C - GB1234 |
| Anyagok               | Tétel             | GB-1234        | I/C - GB1234 |
| Rendszeres cserék     | Óra             | GB-1234        | RR - GB1234  |
| GR-1                    | Tétel             | GB-1234        | RR - GB1234  |
| GR-5                    | Tétel             | GB-1234        | RR - GB1234  |

A két munka szolgáltatási szerződéssoraihoz két szervizfeladat van kapcsolva. A szervizfeladat határozza meg az egyes munkákhoz tartozó tranzakciókat. Az első esetben a I/C - GB1234 szervizfeladat azonosítja a GB-1234 tárgy átvizsgálásában és tisztításában résztvevő összes szolgáltatási szerződéssort. A második esetben az RR - GB1234 szervizfeladat azonosít minden szolgáltatási szerződéssort egy rendszeres cserefeladat elvégzésére vonatkozóan.

A szervizfeladat-kapcsolatok, amelyek a szervizfeladatokat a konkrét szolgáltatási szerződéshez kötik, a következők:

### <a name="service-tasks"></a>Szervizfeladatok

| Szervizfeladat | Leírás                             | Belső megjegyzés                                                                                                                 | Külső megjegyzés                 |
|--------------|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------|-------------------------------|
| I/C - GB1234 | GB-1234 – sebességváltó átvizsgálása           | A GB-1234 sebességváltó átnézése, mechanikai vizsgálata és tisztítása.                                                              | Sebességváltó rendszeres felülvizsgálata |
| RR - GB1234  | GB-1234 – alkatrészek rendszeres cseréje | A GR-1 és GR-5 elem rendszeres szervizcseréje (a 2002 előtt gyártott sebességváltóknál a GR-2 elemet is cserélje) | Rendszeres alkatrészcsere  |

## <a name="group-service-orders"></a>Szervizrendelések csoportosítása

Amikor automatikusan állít elő szervizrendeléseket, a szervizfeladatokat fel lehet használni csoportosítási feltételekként. A szervizrendelések szervizfeladatok alapján történő csoportosításához jelezze a szolgáltatási szerződésben, hogy a szolgáltatási szerződésen alapuló szervizrendeléseket szervizfeladat-azonosítók (ID) szerint kell csoportosítani elsődleges csoportosítási szempontként.

**Csoportosítás szervizfeladat alapján**

1. Kattintson a **Szolgáltatáskezelés** \> **Közös** \> **Szolgáltatási szerződések** \> **Szolgáltatási szerződések** lehetőségre.
2. Válassza ki a **Beállítás** lapon a **Szervizfeladat szerint** lehetőséget a **Szervizrendelések kombinálása** mezőben.




[!INCLUDE[footer-include](../../includes/footer-banner.md)]