--- 
title: "Kifizetések létrehozása beszedési megbízási felhatalmazásokkal rendelkező vevő számára"
description: "Ez a folyamat bemutatja, hogyan hozhat létre egy ISO20022 állandó átutalásos kifizetési fájlt olyan vevőhöz, akihez beszedési megbízás van beállítva, és van egy kifizetendő számlája."
author: mrolecki
manager: AnnBe
ms.date: 10/14/2016
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
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 8a0e48d4681014899a4cc1a31ba902f244c6644b
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# <a name="create-payments-for-a-customer-who-have-direct-debit-mandates"></a>Kifizetések létrehozása beszedési megbízási felhatalmazásokkal rendelkező vevő számára

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ez a folyamat bemutatja, hogyan hozhat létre egy ISO20022 állandó átutalásos kifizetési fájlt olyan vevőhöz, akihez beszedési megbízás van beállítva, és van egy kifizetendő számlája. Számla létrehozása és könyvelése nem kötelező. A vevői előlegfizetés támogatására kifizetendő számla helyett választhat naplóból beszedési megbízást a kifizetési fájl létrehozása előtt.



Ez az eljárás az DEMF bemutatócéget használja.



Ez az ötödik a hat olyan feladat közül, amelyek vevői fizetési folyamat elektronikus jelentési konfigurációk segítségével történő végrehajtásának folyamatát mutatják be. A feladat végrehajtása előtt el kell végeznie a korábbi feladatokat. Először importálnia kell a vevői kifizetési elektronikus jelentéskészítési konfigurációkat, konfigurálnia kell a fizetési módokat, és be kell állítania a cég- és vevőadatokat. 


## <a name="post-a-free-text-invoice-with-direct-debit-information"></a>Szabadszöveges számla feladása beszedési megbízási információkkal
1. Ugorjon a Kinnlévőségek > Számlák > Kizárólag szabadszöveges számlák pontra.
2. Kattintson az Új lehetőségre.
3. A Vevőszámla mezőben adjon meg vagy válasszon ki egy értéket.
    * Válassza ki például a DE-010-et.  
4. A Fizetési mód mezőben adjon meg vagy válasszon ki egy értéket.
    * Például: válassza az Elektronikus lehetőséget.  
5. A Beszedési megbízási felhatalmazás azonosítója mezőben adjon meg, vagy válasszon ki egy értéket.
6. Kattintson az Új sor hozzáadására.
7. Írjon egy értéket a „Leírás” mezőbe.
8. A Fő számla mezőben adja meg a kívánt értékeket.
9. Adjon meg egy számot az Egységár mezőben.
10. Kattintson a Feladás lehetőségre.
11. Kattintson az OK gombra.

## <a name="create-a-payment"></a>Fizetés létrehozása
1. Ugorjon a Kinnlevőségek > Fizetési beállítás > Fizetési napló pontra.
2. Kattintson az Új lehetőségre.
3. A Név mezőben adjon meg vagy válasszon ki egy értéket.
4. Kattintson a Sorok pontra.
5. Kattintson a Fizetési javaslat lehetőségre.
6. Kattintson a Fizetési javaslat létrehozása lehetőségre.
7. Bontsa ki a Szerepeltetni kívánt rekordok szakaszt.
8. Kattintson a Szűrő parancsra.
9. A listán jelölje ki a Vevői tranzakciók tábla sorát és a Fizetési mód mezőt.
    * A fizetendő vevői tranzakciók kiválasztásához bármilyen szempontot alkalmazhat. Ebben a példában használja az Elektronikus fizetési módot a tranzakciók szűrésére.  
10. A Feltétel mezőben adjon meg vagy válasszon ki egy értéket.
11. Kattintson az OK gombra.
12. Kattintson az OK gombra.
13. Kattintson a Fizetések létrehozása lehetőségre.

## <a name="generate-a-payment-file"></a>Kifizetési fájl előállítása

