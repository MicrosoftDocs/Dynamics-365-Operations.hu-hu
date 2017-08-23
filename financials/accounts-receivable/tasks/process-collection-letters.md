--- 
title: "Fizetési felszólítások feldolgozása"
description: "Ez az eljárás a fizetési felszólítások létrehozását, nyomtatását és feladását mutatja be."
author: ShivamPandey-msft
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
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 58dc6176f54a33eda47604b65f5580c21a93fcd7
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# <a name="process-collection-letters"></a>Fizetési felszólítások feldolgozása

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás a fizetési felszólítások létrehozását, nyomtatását és feladását mutatja be. Ez a feladat az USMF bemutatócéget használja.


## <a name="set-up-a-collection-letter-sequence-on-the-posting-profile"></a>Állítson be egy fizetésifelszólítás-sorozatot a feladási profilon.
1. Ugorjon a Követel és beszedések > Beállítás > Vevői feladási profilok pontra.
2. Kattintson a Szerkesztés lehetőségre.
    * Válasszon egy fizetésifelszólítás-sorozatot a legördülő listából. Ha nem szeretne fizetési felszólítást létrehozni a tranzakciókhoz ezzel a feladói profillal, hagyja a mezőt üresen.  
    * A Tábla korlátozási lapján módosíthatja a fizetési felszólítások feldolgozásának módját. Ha ez a mező Igen értékre van állítva, fizetési felszólítások kerülnek létrehozásra a feladási profilhoz.  
3. Zárja be a lapot.

## <a name="create-collection-letters"></a>Fizetési felszólítások létrehozása
1. Ugorjona a Követelések és beszedések > Fizetési felszólítás > Fizetési felszólítások létrehozása pontra.
    * Ki kell választania azokat a tranzakciótípusokat, amelyekre fizetési felszólítást szeretne létrehozni. Ez ilyen típusokhoz tartozó nyitott tranzakciók szerepelni fognak a számításban.  
2. A Fizetési felszólítás mezőben válassza ki a kívánt beállítást.
3. Adja meg a fizetési felszólítás dátumát.
    * Kétféle feladási profil lehetőség létezik: Számla – A vevő számlájához rendelt feladási profil minden egyes kamatlevélre vonatkozóan.   Kiválasztott – a Feladási mezőben megadott feladási profil használata.  
    * Válasszon ki egy feladási profilt, ha módosította a „Feladási profil használata képernyő” lehetőséget „Kiválasztott” lehetőségre.  
4. Bontsa ki a Szerepeltetni kívánt rekordok szakaszt.
5. Kattintson a Szűrő parancsra.
6. A Feltételek mezőben, a Feltételek mezőben, adjon meg egy vevői azonosítót. Adja meg például az „US-001”-et.
7. Kattintson az OK gombra.
8. Kattintson az OK gombra.

## <a name="print-collection-letters"></a>Fizetési felszólítások nyomtatása
1. Ugorjon a Követelések és beszedések > Fizetési felszólítás > Fizetési felszólítások áttekintése és feldolgozása pontra.
2. Az Állapot mezőben válassza ki a „Létrehozva” értéket.
3. A Nyomtatott mezőben válassza a „Nem nyomtatva” lehetőséget.
4. Kattintson a Nyomtatás parancsra.
5. Kattintson a Fizetésre felszólítás gombra.
6. Bontsa ki a Szerepeltetni kívánt rekordok szakaszt.
7. Adja meg a feladások fordulónapjának dátumát.
8. Kattintson az OK gombra a fizetési felszólítás nyomtatásához.

## <a name="post-the-collection-letter"></a>A fizetési felszólítás feladása
1. Kattintson a Feladás lehetőségre.
2. Adja meg a fizetési felszólítás feladási dátumát.
3. Bontsa ki a Szerepeltetni kívánt rekordok szakaszt.
4. Kattintson az OK gombra.
5. Az Állapot mezőben válassza ki a „Feladott” értéket.
6. Válasszon ki egy lehetőséget a Nyomtatott mezőben.


