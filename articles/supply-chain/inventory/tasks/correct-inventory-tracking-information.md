---
title: Készletkövetési információk helyesbítése
description: Ez az eljárás végigvezeti a készletátviteli napló feladási létrehozásának folyamatán, hogy képes legyen készletkövetési információk javítására.
author: yufeihuang
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalTransfer, InventJournalCreate, InventItemIdLookupSimple, InventBatchIdLookup, InventLocationIdLookup, InventDimTracking, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 69921651ecd0969e9cdd3cdd3740db212a1953e1
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7573801"
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