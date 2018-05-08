--- 
title: "Vállalati bankszámlák beállítása ISO20022 beszedési megbízásokhoz"
description: "Ez a feladat végigvezeti a cégspecifikus bankszámla-információk beállításán, amelyek a vevői fizetési fájlok létrehozásához szükségesek."
author: mrolecki
manager: AnnBe
ms.date: 11/14/2016
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
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 6b61495342b18d6dbadb36d8ca146f5a68ba9f6c
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-company-bank-accounts-for-iso20022-direct-debits"></a>Vállalati bankszámlák beállítása ISO20022 beszedési megbízásokhoz

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez a feladat végigvezeti a cégspecifikus bankszámla-információk beállításán, amelyek a vevői fizetési fájlok létrehozásához szükségesek. Ez az eljárás az ISO 20022 beszedési megbízási formátumot használja példaként. Előfordulhat, hogy más formátumoknál további beállítási adatok, mint például a vállalat azonosítója és a rendezési kód szükségesek.



Ez a feladat a DEMF bemutatócég segítségével lett létrehozva.



Ez a második azon öt eljárás közül, amelyek elektronikus jelentési beállítások használatával mutatják be a vevői kifizetési folyamatot.


## <a name="set-up-the-iban-and-swift-codes"></a>Állítson be IBAN és SWIFT kódokat.
1. Ugorjon a Készpénz- és bankkezelés > Bankszámlák pontra.
2. A gyorsszűrő használatával szűrjön rá a Bankszámla mezőre a „DEMF OPER” értékkel.
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * Például: kattintson a „DEMF OPER” lehetőségre a bankszámlaadatok megnyitásához.  
4. Kattintson a Szerkesztés lehetőségre.
5. Bontsa ki vagy csukja össze a További azonosítás szakaszt.
6. Az IBAN mezőben adjon meg egy értéket.
    * Például adja meg a következőt: „DE89370400440532013000”.  
7. A SWIFT kód mezőbe írjon be egy értéket.
    * Például adja meg a következőt: „DEUTDEFF”.    Ne feledje, hogy sok fizetési formátumhoz a SWIFT\BIC nem szükséges, ajánlott viszont rögzíteni a bankszámlához.  
8. Kattintson a Mentés gombra.

## <a name="set-up-a-bank-account-for-the-legal-entity"></a>Bankszámla beállítása jogi személynek
1. Ugorjon a Szervezeti adminisztráció > Szervezetek > Jogi személyek pontra.
2. Kattintson a Szerkesztés lehetőségre.
3. Bontsa ki vagy csukja össze a Bankszámlaadatok szakaszt.
4. A Bankszámla mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
5. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * Például válassza ki a „DEMF OPER” bankszámlát.  
6. Kattintson a Mentés gombra.


