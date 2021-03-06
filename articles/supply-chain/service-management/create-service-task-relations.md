---
title: Szervizfeladat-kapcsolatok létrehozása
description: A szervizfeladatok társítani lehet a szolgáltatási szerződésekhez vagy szervizrendelésekhez, annak leírásához, hogy milyen szervizfeladatokat kell elvégezni a szerződéhez vagy a rendeléshez.
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f9a7808357916ed80ddfa46e1e4f362e0dde1671
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5819064"
---
# <a name="create-service-task-relations"></a>Szervizfeladat-kapcsolatok létrehozása    

[!include [banner](../includes/banner.md)]

A szervizfeladatok társítani lehet a szolgáltatási szerződésekhez vagy szervizrendelésekhez, annak leírásához, hogy milyen szervizfeladatokat kell elvégezni a szerződéhez vagy a rendeléshez. Ezt az információt a szerviztechnikusok és a vevők látják.

## <a name="create-a-relation-with-a-service-agreement"></a>Kapcsolat létrehozása szolgáltatási szerződéssel

1.  Lépjen a **Szolgáltatáskezelés** \> **Közös** \> **Szolgáltatási szerződések** \> **Szolgáltatási szerződések** lehetőségre.

2.  Válasszon ki egy meglévő szolgáltatási szerződést, vagy hozzon létre egy új szolgáltatási szerződést.

3.  A műveleti panelen válassza a **Szervizfeladatok** gombot.

4.  A **Szervizfeladatok** képernyőn válassza az **Új** lehetőséget egy új sort létrehozásához, majd válassza ki a **Szervizfeladat** listáról azt a szervizfeladatot, amelyet csatolni kíván a szolgáltatási szerződéshez.

5.  Írja be az esetleges belső vagy külső leírásokat a **Leírás** lapon található szabadszöveges mezőkbe.

6.  Mentse a rekordot a képernyő bezárásával.

Ismételje meg ezt az eljárást annyiszor, hogy minden szükséges szervizfeladat-kapcsolatot megadjon szolgáltatási szerződésben. Mostantól megadhatók ezek a szervizfeladatok bármely csatolt szerződéssorban.

A szolgáltatási szerződéshez kapcsolt szervizfeladatok elérhetők minden olyan szervizrendelésen, amely a szolgáltatási szerződéshez van csatolva.

## <a name="create-a-relation-with-a-service-order"></a>Kapcsolat létrehozása szervizrendeléssel

1.  Lépjen ide: **Szolgáltatáskezelés** \> **Közös** \> **Szervizrendelések** \> **Szervizrendelések**.

2.  Válasszon ki egy meglévő szervizrendelést, vagy hozzon létre egy új szervizrendelést.

3.  A műveleti panelen válassza a **Szervizfeladatok** gombot.

4.  A **Szervizfeladatok** űrlapról válassza az **Új** lehetőséget egy új sort létrehozásához, majd válassza ki a **Szervizfeladat** listáról azokat a szervizfeladatokat, amelyet csatolni kíván a szolgáltatási utasításhoz.

5.  Írja be az esetleges belső vagy külső leírásokat a **Leírás** lapon található szabadszöveges mezőkbe.

6.  Mentse a rekordot a képernyő bezárásával.

Ismételje meg ezt az eljárást annyiszor, hogy minden szükséges szervizfeladat-kapcsolatot megadjon szervizrendelésben. Most kiválaszthatja azt a szervizfeladatot, amelyhez létrehozta a kapcsolatot a szervizrendeléssorok létrehozásakor.

A szervizrendelésen létrehozott szervizfeladat-kapcsolatok az adott szervizrendelésen érhetők el.

## <a name="see-also"></a>Lásd még

[Szervizfeladatok áttekintése](service-tasks.md)


  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]