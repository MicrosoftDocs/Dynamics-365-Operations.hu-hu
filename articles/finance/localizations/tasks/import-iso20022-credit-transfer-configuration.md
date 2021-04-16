---
title: ISO20022 jóváírási konfiguráció importálása
description: Ez az eljárás bemutatja, hogyan importálható szállítói fizetési elektronikus jelentéskészítési konfiguráció.
author: mrolecki
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4a96827bc6e126a7f5de6d67338b5233a65d93c8
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840913"
---
# <a name="import-iso20022-credit-transfer-configuration"></a>ISO20022 jóváírási konfiguráció importálása

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja, hogyan importálható szállítói fizetési elektronikus jelentéskészítési konfiguráció. A német ISO 20022 átutalási formátum szolgál példaként. Ez az eljárás egyéb rendelkezésre álló elektronikus jelentéskészítési formátumokhoz is használható. 

A feladat DEMF bemutatócég segítségével készült, de a feladat végrehajtásához bármely bemutatócég adatai felhasználhatók.

Ez az első azon öt eljárás közül, amelyek együtt mutatják be elektronikus jelentési beállítások használatával a szállítói kifizetési folyamatot. Az eljárás egy olyan szolgáltatáshoz tartozik, amely a Dynamics 365 for Operations 1611-es verziójában jelent meg.

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]