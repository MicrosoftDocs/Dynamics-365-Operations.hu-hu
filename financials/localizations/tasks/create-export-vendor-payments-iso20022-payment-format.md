--- 
title: "Szállítói kifizetések létrehozása és exportálása ISO20022 fizetési formátumban"
description: "Ez az eljárás bemutatja, hogyan hozhat létre fizetési sorokat a szállítói kifizetési naplóban, és hogyan hozhat létre szállítói fizetési fájlt az ISO2022 átutalást használva példaként."
author: mrolecki
manager: AnnBe
ms.date: 10/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 16c2af862a73047a2e6ebdc056275392fa8a0d93
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# <a name="create-and-export-vendor-payments-using-iso20022-payment-format"></a>Szállítói kifizetések létrehozása és exportálása ISO20022 fizetési formátumban

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogyan hozhat létre fizetési sorokat a szállítói kifizetési naplóban, és hogyan hozhat létre szállítói fizetési fájlt az ISO2022 átutalást használva példaként. 

Ez az eljárás az DEMF bemutatócéget használja.

Ez az ötödik azon öt eljárás közül, amelyek elektronikus jelentési beállítások használatával mutatják be a szállítói kifizetési folyamatot. Ez az eljárás egy olyan funkcióra vonatkozik, amely a Dynamics 365 for Operations 1611-es verziójába került be.


## <a name="create-payment-lines"></a>Fizetési sorok létrehozása
1. Ugorjon a Kötelezettségek > Fizetési beállítás > Fizetési napló pontra.
2. Kattintson az Új lehetőségre.
3. A listában jelölje meg a kiválasztott sort.
4. A Név mezőben adjon meg vagy válasszon ki egy értéket.
5. Kattintson a Sorok pontra.
6. Kattintson a Fizetési javaslat lehetőségre.
7. Kattintson a Fizetési javaslat létrehozása lehetőségre.
8. Bontsa ki a Szerepeltetni kívánt rekordok szakaszt.
9. Kattintson a Szűrő parancsra.
10. A listában jelölje ki a Szállítók táblára és a Szállítói számla mezőre vonatkozó sort.
11. A Feltétel mezőben adjon meg vagy válasszon ki egy értéket.
    * Bármilyen feltétel alkalmazható a szállítói fizetési tranzakció kiválasztásához - ebben a példában a DE-001-et használjuk szállítói számlaként.  
12. Kattintson az OK gombra.
13. Kattintson az OK gombra.
14. Kattintson a Fizetések létrehozása lehetőségre.

## <a name="generate-an-iso20022-payment-file"></a>ISO20022 típusú fizetési fájl létrehozása


