--- 
title: "Vállalati bankszámlák beállítása ISO20022 típusú átutalásokhoz"
description: "Ez az eljárás bemutatja a cégspecifikus bankszámlaadatok beállítását, amelyek fizetési fájl létrehozásához szükségesek."
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
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 1d0eabdfdeb5ed7d0bdb6df87ebdfa0d41e87492
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-company-bank-accounts-for-iso20022-credit-transfers"></a>Vállalati bankszámlák beállítása ISO20022 típusú átutalásokhoz

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja a cégspecifikus bankszámlaadatok beállítását, amelyek fizetési fájl létrehozásához szükségesek. Az adatok megadása az ISO 20022 átutalási formátum létrehozásának igényei alapján történik, de formátumtól függően lehet, hogy más adatokat, például a vállalat azonosítója vagy a rendezési kódot is meg kell adni. 

Ez az eljárás az DEMF bemutatócéget használja.

Ez a második azon öt eljárás közül, amelyek elektronikus jelentési beállítások használatával mutatják be a szállítói kifizetési folyamatot. Ez az eljárás egy olyan funkcióra vonatkozik, amely a Dynamics 365 for Operations 1611-es verziójába került be.


## <a name="set-up-iban-and-swift-code"></a>IBAN- és SWIFT-kód beállítása
1. Ugorjon a Készpénz- és bankkezelés > Bankszámlák pontra.
2. A gyorsszűrő használatával szűrjön rá a Bankszámla mezőre a „DEMF OPER” értékkel.
3. Kattintson a DEMF OPER lehetőségre a bankszámla adatainak megnyitásához.
4. Kattintson a Szerkesztés lehetőségre.
5. Bontsa ki a További azonosítás szakaszt.
6. Az IBAN mezőbe írja be a „DE89370400440532013000” értéket.
7. A SWIFT kód mezőbe írja be a „DEUTDEFF” értéket.
    * Ne feledje, hogy sok fizetési formátumhoz a SWIFT\BIC nem szükséges, ajánlott viszont rögzíteni a bankszámlához.  
8. Kattintson a Mentés gombra.

## <a name="set-up-bank-account-for-the-legal-entity"></a>Bankszámla beállítása jogi személynek
1. Ugorjon a Szervezeti adminisztráció > Szervezetek > Jogi személyek pontra.
2. Kattintson a Szerkesztés lehetőségre.
3. Bontsa ki a Bankszámlaadatok szakaszt.
4. A Bankszámlák mezőben adjon meg vagy válasszon ki egy értéket.
5. Kattintson a Mentés gombra.


