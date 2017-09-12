---
title: "A cikk érkezésáttekintési profiljának beállítása"
description: "Ez a feladat érkeztetési áttekintési profil létrehozására szolgál."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: ca70b6afbbadf1122f57285eff58125f8e10346b
ms.contentlocale: hu-hu
ms.lasthandoff: 07/28/2017

---
# <a name="set-up-an-item-arrival-overview-profile"></a>A cikk érkezésáttekintési profiljának beállítása

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ez a feladat érkeztetési áttekintési profil létrehozására szolgál. Az érkeztetési áttekintési profil szabályok gyűjteménye, amelyet egy Érkeztetési áttekintési oldal felhasználó általi megnyitásakor alkalmaz a rendszer. Az USMF bemutatócég adataiban használhatja ezt az eljárást. Általában ezt a feladatot egy befogadó jegyző végzi el.





1. Ugorjon a Készletkezelés > Beállítás > Felosztás > Érkeztetési áttekintési profilok pontra.
2. Kattintson az Új lehetőségre.
    * Mivel szinte mindig ugyanabban a raktárban dolgozik teljes rakományok lerakásával, mindig kell egy érkezési áttekintési profilt létrehozni a beérkezett cikkek regisztrálásának egyszerűsítéséhez.  
3. Az Érkeztetési áttekintési profil mezőbe írjon be egy értéket.
4. Válasszon ki egy lehetőséget a Sorok megjelenítése mezőben.
    * Válassza ki, hogy mely sorok látsszanak a bevételezéseknél: az összes – valamennyi sor megjelenik, állapottól függetlenül.   Folyamatban – Bevételezési sorok megjelenítése, amelyben az előrehaladás Elkészült vagy Részben. Ez azt jelenti, hogy minden sor teljes vagy egy részleges mennyisége regisztrálva van az érkeztetési naplóban.   Nem teljes – Bevételezési sorok megjelenítése, amelyben az előrehaladás Nincs vagy Részben. Ez azt jelenti, hogy az egyes soroknál semmi sem vagy csak a mennyiség egy része van regisztrálva az érkeztetési naplóba.  
5. Bontsa ki vagy csukja össze az Érkezési beállítások szakaszt.
6. A Napok mától mezőbe írjon be egy értéket.
    * Ez beállít egy szűrőt, hogy megmutassa a következő napban fogadni kívánt nyugtasorokat (a beállított számtól függően).  
7. A Napra visszamenőleg mezőbe írjon be egy értéket.
    * Ezzel beállít egy szűrőt, amely megjeleníti az adott nap előtt adott számú nappal fogadott nyugtasorokat.  
8. A Raktárak mezőbe írjon be egy értéket.
    * Szűrjön egy vagy több raktárra.  
9. Válasszon ki egy értéket a Szállítási mód mezőbe.
    * Ez beállít egy szűrőt, hogy csak ezzel a szállítási móddal jelenjenek meg nyugtasorok.  
10. A Név mezőben, válassza a WHS-t.
11. A Raktár mezőben válassza ki a 24-es raktárt.
    * Ez az alapértelmezett raktár, amellyel a profilt használó nyugtasorok be lesznek jegyezve.  
12. A Hely mezőben válassza ki a Baydoor-t.
    * Ez az alapértelmezett hely, amellyel a profilt használó nyugtasorok be lesznek jegyezve.  
13. Bontsa ki vagy csukja össze a Érkezéslekérdezés részletei szakaszt.
14. A Készletező hely mezőben válassza 2. helyet.
    * Ez beállít egy szűrőt, hogy csak ezzel a hellyel jelenjenek meg nyugtasorok.  
15. A Beszerzési rendelések beállítást állítsa Igen értékre.
    * Nyugtasorok kiválasztása beszerzési rendelésekből.  
16. A Szállítási rendelések beállítást állítsa Igen értékre.
    * Nyugtasorok kiválasztása átmozgatási rendelésekből.  
17. Kattintson a Mentés gombra.
18. Zárja be a lapot.

