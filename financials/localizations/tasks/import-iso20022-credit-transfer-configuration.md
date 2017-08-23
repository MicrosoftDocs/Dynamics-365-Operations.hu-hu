--- 
title: "ISO20022 jóváírási konfiguráció importálása"
description: "Ez az eljárás bemutatja, hogyan importálható szállítói fizetési elektronikus jelentéskészítési konfiguráció."
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
ms.openlocfilehash: 52d502a53deb6defa619af4ca8cdc3158e086bae
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# <a name="import-iso20022-credit-transfer-configuration"></a>ISO20022 jóváírási konfiguráció importálása

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogyan importálható szállítói fizetési elektronikus jelentéskészítési konfiguráció. A német ISO 20022 átutalási formátum szolgál példaként. Ez az eljárás egyéb rendelkezésre álló elektronikus jelentéskészítési formátumokhoz is használható. 

A feladat DEMF bemutatócég segítségével készült, de a feladat végrehajtásához bármely bemutatócég adatai felhasználhatók.

Ez az első azon öt eljárás közül, amelyek együtt mutatják be elektronikus jelentési beállítások használatával a szállítói kifizetési folyamatot. Ez az eljárás egy olyan funkcióra vonatkozik, amely a Dynamics 365 for Operations 1611-es verziójába került be.

1. Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.
2. Az elérhető konfigurációs szolgáltatók listájáról válassza a Microsoftot.
3. Kattintson erre: Beállítás aktívként.
4. Kattintson a Tárházak gombra.
5. Kattintson a Megnyitás gombra.
6. Kattintson a Szűrők megjelenítése pontra.
7. Alkalmazza a következő szűrőket: adja meg az „ISO20022 átutalás (DE)” szűrőértéket a „Konfiguráció neve” mezőben az „ezzel kezdődik” szűrési operátor használatával
    * Vagy keresse meg a konfigurációt a listán, válassza ki és helyezze át az Importálási feladatba.  
8. Kattintson az Importálás gombra.
    * Ha az Importálás gomb nem elérhető, az azt jelenti, hogy a konfiguráció importálása már megtörtént.  
9. Kattintson az Igen gombra.


