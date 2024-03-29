---
title: A cikk érkezésáttekintési profiljának beállítása
description: Ez a cikk az érkezések áttekintő profiljának beállítását foglalkozik.
author: yufeihuang
ms.date: 07/30/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WMSArrivalOverviewProfile
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8517710f5d0be1859f86449152712d950281769a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8872007"
---
# <a name="set-up-an-item-arrival-overview-profile"></a>A cikk érkezésáttekintési profiljának beállítása

[!include [banner](../../includes/banner.md)]

Ez a cikk az érkezések áttekintő profiljának beállítását foglalkozik. Az érkeztetési áttekintési profil szabályok gyűjteménye, amelyet egy Érkeztetési áttekintési oldal felhasználó általi megnyitásakor alkalmaz a rendszer. Az USMF bemutatócég adataiban használhatja ezt az eljárást. Általában ezt a feladatot egy befogadó jegyző végzi el.

1. A navigációs ablaktáblán lépjen a **Modulok > Készletgazdálkodás > Beállítás > Kiosztás > Érkezésáttekintési profilok** részre.
2. Válassza az **Új** lehetőséget. Mivel szinte mindig ugyanabban a raktárban dolgozik teljes rakományok lerakásával, mindig kell egy érkezési áttekintési profilt létrehozni a beérkezett cikkek regisztrálásának egyszerűsítéséhez.  
3. Adjon meg egy értéket az **Érkezésáttekintési profil** mezőben.
4. Válasszon ki egy lehetőséget a **Sorok megjelenítése** mezőben. Válassza ki, hogy mely soroknak kell látszódniuk a bevételezéseknél:  

    - **Mind** – minden sor megmutatása állapottól függetlenül.   
    - **Folyamatban** – azoknak a bevételezési soroknak a megjelenítése, amelyben az előrehaladás Elkészült vagy Részben. Ez azt jelenti, hogy minden sor teljes vagy egy részleges mennyisége regisztrálva van az érkeztetési naplóban.   
    - **Nem teljes** – azoknak a bevételezési soroknak a megjelenítése, amelyben az előrehaladás Nincs vagy Részben. Ez azt jelenti, hogy az egyes soroknál semmi sem vagy csak a mennyiség egy része van regisztrálva az érkeztetési naplóba.  

5. Bontsa ki vagy csukja össze az **Érkezési beállítások** szakaszt.
6. Adjon meg egy értéket a **Napok mától** mezőben. Ez beállít egy szűrőt, hogy megmutassa a következő napban fogadni kívánt nyugtasorokat (a beállított számtól függően).  
7. Adjon meg egy értéket a **Napra visszamenőleg** mezőben. Ezzel beállít egy szűrőt, amely megjeleníti az adott nap előtt adott számú nappal fogadott nyugtasorokat.  
8. Adjon meg egy értéket a **Raktárak** mezőben. Szűrjön egy vagy több raktárra.  
9. Válasszon ki egy értéket a **Szállítási mód** mezőben. Ez beállít egy szűrőt, hogy csak ezzel a szállítási móddal jelenjenek meg nyugtasorok.  
10. A **Név** mezőben, válassza a WHS-t.
11. A **Raktár** mezőben válassza ki a 24-es raktárt. Ez az alapértelmezett raktár, amellyel a profilt használó nyugtasorok be lesznek jegyezve.  
12. A **Hely** mezőben válassza ki a **Baydoor** elemet. Ez az alapértelmezett hely, amellyel a profilt használó nyugtasorok be lesznek jegyezve.  
13. Bontsa ki vagy csukja össze a **Érkezéslekérdezés részletei** szakaszt.
14. A **Korlátozás a helyre** mezőben válassza 2. helyet. Ez beállít egy szűrőt, hogy csak ezzel a hellyel jelenjenek meg nyugtasorok.  
15. A **Beszerzési rendelések** beállítást állítsa **Igen** értékre. Nyugtasorok kiválasztása beszerzési rendelésekből.  
16. Az **Átvitel** beállítást állítsa **Igen** értékre. Nyugtasorok kiválasztása átmozgatási rendelésekből.  
17. Válassza a **Mentés** lehetőséget.
18. Zárja be a lapot.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
