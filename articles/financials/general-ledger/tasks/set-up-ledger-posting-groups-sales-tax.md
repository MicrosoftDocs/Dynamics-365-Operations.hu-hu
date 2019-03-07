---
title: Főkönyvi feladási csoportok beállítása az áfához
description: Az áfa számítása és postázása a Főkönyvi feladási csoportok lehetőségben megadott fő számlákra történik.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxAccountGroup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 15421da6f325dfee22a303e9fe83a0e72895fa08
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "308345"
---
# <a name="set-up-ledger-posting-groups-for-sales-tax"></a>Főkönyvi feladási csoportok beállítása az áfához

[!include [task guide banner](../../includes/task-guide-banner.md)]

Az áfa számítása és postázása a Főkönyvi feladási csoportok lehetőségben megadott fő számlákra történik. Az egyes áfakódokhoz Főkönyvi postázási csoportok vannak csatolva. Beállíthat külön főkönyvi feladási csoportot mindegyik áfakódhoz, vagy használhat egyetlen főkönyvi feladási csoportot minden áfakódhoz, továbbá több főkönyvi feladási csoportot is hozzárendelhet az áfakódokhoz. Ez a felvétel az DEMF bemutatócéget használja. 

1. Ugrás az Adó > Beállítás > Áfa > Főkönyvi feladási csoportok elemre.
2. Kattintson az Új lehetőségre.
3. Írjon egy értéket a Főkönyvi feladási mezőbe.
4. A Leírás mezőben adjon meg egy értéket.
5. A Fizetendő áfa mezőben válassza ki a fő számlát kimenő áfához, amelyeket az adóhatóságnak kell kifizetni.
    * Az Áfát az Adóhatóság szedi be, amikor elad adóköteles termékeket és szolgáltatásokat.  
6. A Visszaigényelhető áfa mezőben válassza ki a fő számlát bejövő áfához, amelyeket az adóhatóságtól érkeznek.
    * Az Áfát a szállítók szedik be az adóhatóság nevében, amikor adóköteles termékeket és szolgáltatásokat vesz. Ez a mező nem érhető el, csak ha a Főkönyvi paraméterek oldalon be van jelölve a Áfa adózási szabályok alkalmazása opció. Ehelyett a szállítóknak befizetett adók ugyanarra a beszerzési számlára terhelődnek.   
7. Az Importadó költsége mezőben válassza a fő számlát a leírható Importadók feladásához, amelyek nem visszaigényeltek, vagy jelentettek az adóhatóságnak a szállítók az EU fordított GST/HST részeként.
    * Az Áfa lehetőséget ki kell választani az Áfa kódok közül abból Áfacsoportból amelyet a tranzakcióhoz használnak.  Ez a mező nem érhető el, csak ha a Főkönyvi paraméterek oldalon be van jelölve a Áfa adózási szabályok alkalmazása opció.   
8. A Fizetendő importadó mezőben válassza ki a fő számlát bemenő Importadókhoz, amelyeket az adóhatóságoknak kell kifizetni.
    * Az Áfa lehetőséget ki kell választani az Áfa kódban abból Áfacsoportból amelyet az Importadó feladásához használnak. Ha az Áfa adózási szabályok alkalmazását választja a Főkönyv paramétereiben, akkor az eltérés a tranzakció költségszámlájára kerül feladásra.   
9. A Kiegyenlítési számla mezőben válassza a fő számlát, amelyet a főkönyvi számlák nettó egyenlege megadott az Fizetendő importadó és amire Visszaigényelhető áfa mezők kerülnek feladásra.
    * Az egyenleg az Áfa kiegyenlítése és a feladat lefutása után jön létre.  Ha kiegyenlítés időszak Adóhatósága egy szállítói számlához van rendelve, akkor az egyenleg ehelyett a szállítói számlára kerül feladásra.   
10. A szállítói készpénzfizetési engedmény mezőben válassza ki a fő számlát, a készpénzfizetési engedmény feladásához a főkönyvi feladási csoporthoz társított áfakódhoz.
    * Ez válaszható ha nincs megadva számla, a Készpénzfizetési engedmény kódjain található fő számla kerül felhasználásra. Hasznos lehet ha az egyes Főkönyv postázási csoportokhoz különböző számlákat használ, fordított áfát használatakor a készpénzfizetési engedmény lehetőséghez az Áfacsoportban.  
11. A Vevői eset engedmény mezőben válassza ki a fő számlát, a készpénzfizetési engedmény feladásához a főkönyvi feladási csoporthoz társított áfakódhoz.
    * Ez válaszható ha nincs megadva számla, a Készpénzfizetési engedmény kódjain található fő számla kerül felhasználásra. Hasznos lehet ha az egyes Főkönyv postázási csoportokhoz különböző számlákat használ, fordított áfát használatakor a készpénzfizetési engedmény lehetőséghez az Áfacsoportban.  
12. Kattintson a Mentés gombra.

