---
title: Szervizfeladat-kapcsolatok létrehozása
description: A szervizfeladatok társítani lehet a szolgáltatási szerződésekhez vagy szervizrendelésekhez, annak leírásához, hogy milyen szervizfeladatokat kell elvégezni a szerződéhez vagy a rendeléshez.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b167714dc81cf0e4ee70d7092f2ec030043abe71
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3202606"
---
# <a name="create-service-task-relations"></a>Szervizfeladat-kapcsolatok létrehozása    

[!include [banner](../includes/banner.md)]

A szervizfeladatok társítani lehet a szolgáltatási szerződésekhez vagy szervizrendelésekhez, annak leírásához, hogy milyen szervizfeladatokat kell elvégezni a szerződéhez vagy a rendeléshez. Ezt az információt a szerviztechnikusok és a vevők látják.

## <a name="create-a-relation-with-a-service-agreement"></a>Kapcsolat létrehozása szolgáltatási szerződéssel

1.  Kattintson a **Szolgáltatáskezelés** \> **Közös** \> **Szolgáltatási szerződések** \> **Szolgáltatási szerződések** lehetőségre.

2.  Válasszon ki egy meglévő szolgáltatási szerződést, vagy hozzon létre egy új szolgáltatási szerződést.

3.  A műveleti panelen kattintson a **Szervizfeladatok** gombra.

4.  A **Szervizfeladatok** képernyőn nyomja meg a CTRL+N billentyűkombinációt egy új sort létrehozásához, majd válassza ki a **Szervizfeladat** listáról azt a szervizfeladatot, amelyet csatolni kíván a szolgáltatási szerződéshez.

5.  Írja be az esetleges belső vagy külső leírásokat a **Leírás** lapon található szabadszöveges mezőkbe.

6.  Mentse a rekordot a képernyő bezárásával.

Ismételje meg ezt az eljárást annyiszor, hogy minden szükséges szervizfeladat-kapcsolatot megadjon szolgáltatási szerződésben. Mostantól megadhatók ezek a szervizfeladatok bármely csatolt szerződéssorban.

A szolgáltatási szerződéshez kapcsolt szervizfeladatok elérhetők minden olyan szervizrendelésen, amely a szolgáltatási szerződéshez van csatolva.

## <a name="create-a-relation-with-a-service-order"></a>Kapcsolat létrehozása szervizrendeléssel

1.  Kattintson a következőkre: **Szolgáltatáskezelés** \> **Közös** \> **Szervizrendelések** \> **Szervizrendelések**.

2.  Válasszon ki egy meglévő szervizrendelést, vagy hozzon létre egy új szervizrendelést.

3.  A műveleti panelen kattintson a **Szervizfeladatok** gombra.

4.  A **Szervizfeladatok** képernyőn nyomja meg a CTRL+N billentyűkombinációt egy új sort létrehozásához, majd válassza ki a **Szervizfeladat** listáról azokat a szervizfeladatokat, amelyeket csatolni kíván a szervizrendeléshez.

5.  Írja be az esetleges belső vagy külső leírásokat a **Leírás** lapon található szabadszöveges mezőkbe.

6.  Mentse a rekordot a képernyő bezárásával.

Ismételje meg ezt az eljárást annyiszor, hogy minden szükséges szervizfeladat-kapcsolatot megadjon szervizrendelésben. Most kiválaszthatja azt a szervizfeladatot, amelyhez létrehozta a kapcsolatot a szervizrendeléssorok létrehozásakor.

A szervizrendelésen létrehozott szervizfeladat-kapcsolatok az adott szervizrendelésen érhetők el.

## <a name="see-also"></a>Lásd még

[Szervizfeladatok áttekintése](service-tasks.md)


  


