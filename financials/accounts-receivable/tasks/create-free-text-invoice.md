--- 
title: "Szabadszöveges számla létrehozása"
description: "Ez a feladat-útmutató a szabadszöveges számla létrehozását mutatja be."
author: mikefalkner
manager: AnnBe
ms.date: 10/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: a9f9a780868926009f30cee6aa634c53ca870b3f
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-free-text-invoice"></a>Szabadszöveges számla létrehozása

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ez a feladat-útmutató a szabadszöveges számla létrehozását mutatja be. Ez a feladat az USMF bemutatócéget használja.

1. Ugorjon a Kinnlévőségek > Számlák > Kizárólag szabadszöveges számlák pontra.
2. Kattintson az Új lehetőségre.
3. Válasszon egy értéket a Vevői számla mezőnek.
    * A számla alapértelmezett esetben a vevői számlához használt példány.   
    * A könyvelési állapot Folyamatban állapottal kezdődik, ha a számla nincs feladva.   
    * A számlaszám a számla feladásakor kerül hozzárendelésre.  
    * SEPA típusú felhatalmazások használatakor a beszedési megbízási felhatalmazást automatikusan kitölti a program egy felhatalmazással, ha a vevői számla lehetőséget választja.  
4. A Leírás mezőben adjon meg egy értéket.
5. A Fő számla mezőben adja meg a számlaszámot és a dimenziókat.
    * Megadhat továbbá egy vagy több karaktert a fő számlából, és használhatja a keresés funkciót a számlája megtalálásához. Ebben az útmutatóban később kell megadni a dimenziókat.  
6. Bontsa ki a Soradatok gyorslapját, hogy hozzáadhasson dimenziókat a fő számlájához.
7. Kattintson a Pénzügyi dimenziók lapra.
    * A dimenziók kizárólag a kijelölt sorra vonatkoznak.    
    * Az áfacsoportot a vevő tölti ki. Ha a vevő nem rendelkezik áfacsoporttal, akkor a fő számla áfacsoportját kell használni.  
    * A cikkek áfacsoportja a fő számla alapján kerül kitöltésre. Ha a fő számla nem rendelkezik cikkekre vonatkozó áfacsoporttal, akkor a Főkönyv áfa paramétereiben található cikk áfacsoport használatos.    
8. Adjon meg egy számot a Mennyiség mezőben.
    * A mennyiség megadása nem kötelező.  
9. Adjon meg egy számot az Egységár mezőben.
    * Az egységár megadása nem kötelező.  
    * Az összeg a mennyiség és az egységár szorzata alapján kerül kiszámításra. Ugyanakkor felülírhatja a számítást, és bevihet egy összeget.  
10. Kattintson az Áfa lehetőségre a számla számított áfájának megtekintéséhez.
    * Ezen a lapon megtekintheti az áfaösszegeket, vagy felülírhatja ezeket az összegeket a Kiigazítás lapon.  
11. Kattintson az OK gombra.
12. Kattintson a Költségek lehetőségre, ha szeretne költségeket adni a számlához. 
13. Érték beírása a Költségek mezőbe.
14. Adjon meg egy számot az Költségek értéke mezőben.
15. Zárja be a lapot.
16. Kattintson az Összeg lehetőségre az összesítő számla részleteinek és végösszegének áttekintéséhez.
17. Kattintson a Bezárás gombra.
18. Adja fel a számlát a Feladás gombra kattintva. Érvénytelenítheti feladás előtt.
    * A számla nyomtatásának időpontját megváltoztathatja: Válassza ki a Jelenlegi lehetőséget az egyes számlák kinyomtatásához, vagy válassza ki az Után lehetőséget, ekkor az összes számla frissítése után történik a nyomtatás.  
    * Ha szeretné megváltoztatni a vevő hitelkeretének ellenőrzését feladás előtt, akkor változtassa meg a Hitelkeret típusát.  
    * Ha nyomtatni akarja a számlát akkor válassza az Igen lehetőséget.  
    * Ha biztosan feladja a számlát akkor válassza az Igen lehetőséget. Feladás nélkül is kinyomtathatja a számlát.  
19. Kattintson az OK gombra.


