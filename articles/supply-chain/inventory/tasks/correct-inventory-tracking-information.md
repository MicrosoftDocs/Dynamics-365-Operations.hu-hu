---
title: Készletkövetési információk helyesbítése
description: Ez az eljárás végigvezeti a készletátviteli napló feladási létrehozásának folyamatán, hogy képes legyen készletkövetési információk javítására.
author: MarkusFogelberg
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalTransfer, InventJournalCreate, InventItemIdLookupSimple, InventBatchIdLookup, InventLocationIdLookup, InventDimTracking, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d7bbb1f2e6128b1dea2be8dc737d5ae526195f08
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5834073"
---
# <a name="correct-inventory-tracking-information"></a>Készletkövetési információk helyesbítése

[!include [banner](../../includes/banner.md)]

Ez az eljárás végigvezeti a készletátviteli napló feladási létrehozásának folyamatán, hogy képes legyen készletkövetési információk javítására. Ebben a példában egy kötegelt ellenőrzött cikk adatait módosítjuk, azza,l hogy megváltoztatunk egy hibásan regisztrált köteget egy másikra. Ezt a folyamatot az USPI bemutatócégen vagy saját adata használatával is elvégezheti. Saját adatok használatakor rendelkezni kell egy kötegelésre alkalmas cikkel, és nem szabad helyvezéreltnek lennie. Először be kell állítani egy készletnaplónevet a készletmozgatáshoz. Ezeket a feladatokat általában egy raktári alkalmazott végzi el.


## <a name="create-an-inventory-transfer-journal"></a>Készletátviteli napló létrehozása
1. Ugrás az Áthelyezéshez.
2. Kattintson az Új lehetőségre.
3. A Név mezőben adjon meg vagy válasszon ki egy értéket.
4. Kattintson az OK gombra.

## <a name="create-journal-lines"></a>Naplósorok létrehozása
1. Kattintson az Új lehetőségre.
2. Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.
    * Az USPI használata esetén válassza az „M5003” cikket.  
3. Adjon meg egy számot a Mennyiség mezőben.
4. Kattintson a Készlet dimenziók lapra.
5. A Kötegszám mezőben adjon meg vagy válasszon ki egy értéket.
6. A Hely mezőben adjon meg vagy válasszon ki egy értéket.
7. A Raktár mezőben adjon meg vagy válasszon ki egy értéket.
8. A Kötegszám mezőben adjon meg vagy válasszon ki egy értéket.

## <a name="post-the-journal"></a>Napló feladása
1. Kattintson a Feladás lehetőségre.
2. Kattintson az OK gombra.

## <a name="check-tracing-information"></a>Nyomkövetési adatok ellenőrzése
1. Kattintson a Készlet parancsra.
2. Kattintson a Nyomon követés elemre.
3. Kattintson az OK gombra.
    * A nyomkövetési adatokkal visszakövetheti, hogy melyik kötegből korrigálta a készletet.  A Cikk-követés lap használatával is megtekintheti ezt az adatot.  
4. Zárja be a lapot.

## <a name="check-inventory-transactions"></a>Készlettranzakciók ellenőrzése
1. Kattintson a Készlet parancsra.
2. Kattintson a Tranzakciók elemre.
    * Itt láthatók a napló feladásakor létrehozott tranzakciók.   



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]