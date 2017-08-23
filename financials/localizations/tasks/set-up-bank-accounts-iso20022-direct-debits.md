--- 
title: "Vevők és vevői bankszámlák beállítása ISO20022 beszedési megbízásokhoz"
description: "A feladat végigvezeti a vevői bankszámla és a vevői beszedési megbízási felhatalmazás beállításán, amelyek a vevői fizetési fájl, például az ISO20022 típusú beszedési megbízás létrehozásához szükségesek."
author: mrolecki
manager: AnnBe
ms.date: 10/13/2016
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
ms.openlocfilehash: 7aac1af99f2b5a7b1a123a8e3d3d6ddcaaa39b8d
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-customers-and-customer-bank-accounts-for-iso20022-direct-debits"></a>Vevők és vevői bankszámlák beállítása ISO20022 beszedési megbízásokhoz

[!include[task guide banner](../../includes/task-guide-banner.md)]

A feladat végigvezeti a vevői bankszámla és a vevői beszedési megbízási felhatalmazás beállításán, amelyek a vevői fizetési fájl, például az ISO20022 típusú beszedési megbízás létrehozásához szükségesek. A vevőnél beállított fizetési formátumtól függően ebben az eljárásban nem érintett, további adatok megadására is szükség lehet a vevő vagy a vevői bankszámla számára. 

Ezt a feladatot a jogi személy elsődleges németországi címmel rendelkező DEMF bemutatócég segítségével hozták létre.



Ez a negyedik azon öt eljárás közül, amelyek elektronikus jelentési beállítások használatával mutatják be a vevői kifizetési folyamatot.


## <a name="set-up-a-customer-bank-account"></a>Vevői bankszámla beállítása
1. Ugorjon a Kinnlevőségek > Vevők > Minden vevő pontra.
2. Rekordok kereséséhez használja a gyorsszűrőt. Például szűkítsen a „Számla” mezővel a „DE-010” értéket beírva.
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
4. A Művelet panelen kattintson a Vevő elemre.
5. Kattintson a Bankszámlák lehetőségre.
6. Kattintson az Új lehetőségre.
7. A Bankszámla mezőben adjon meg egy értéket.
8. Írjon be egy értéket a Név mezőbe.
    * Például adja meg a következőt: „EUR bank”.  
9. A Bankcsoportok mezőben adjon meg vagy válasszon ki egy értéket.
10. Az IBAN mezőben adjon meg egy értéket.
    * Például adja meg a következőt: „DE36200400000628808808”.  
11. A SWIFT kód mezőbe írjon be egy értéket.
    * Adja meg például a „COBADEFFXXX” értéket.  Ne feledje, hogy sok fizetési formátumhoz a SWIFT\BIC nem szükséges, ajánlott viszont rögzíteni a bankszámlához.  
12. Kattintson a Mentés gombra.
13. Zárja be a lapot.
14. Kattintson a Szerkesztés lehetőségre.
15. Bontsa ki a Fizetés alapértelmezései szakaszt.
16. A Bankszámlák mezőben adjon meg vagy válasszon ki egy értéket.

## <a name="add-a-direct-debit-mandate"></a>Beszedési megbízási felhatalmazás hozzáadása
1. Bontsa ki a beszedési megbízási felhatalmazások szakaszt.
2. Kattintson a Hozzáadás gombra.
3. A Hitelező bank mezőben adjon meg vagy válasszon ki egy értéket.
    * Válassza például a „DEMF OPER” értéket.  
4. Adja meg a dátumot az Aláírás dátuma mezőben.
5. A dátum frissítéséhez kattintson az Igen lehetőségre.
6. Az Aláírás helye mezőben adjon meg vagy válasszon ki egy értéket.
7. Adjon meg egy számot a Fizetések várt száma mezőben.
8. Kattintson az OK gombra.
9. Kattintson a Mentés gombra.


