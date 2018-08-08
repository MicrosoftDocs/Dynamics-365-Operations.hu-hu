--- 
title: "Kamatfeldolgozás"
description: "Ez az eljárás a kamatlevél létrehozását, nyomtatását és feladását mutatja be."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 543ac29ac1b1cbad52f1c155ac90b04d0c122a1f
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="process-interest"></a>Kamatfeldolgozás

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás a kamatlevél létrehozását, nyomtatását és feladását mutatja be. Ez a feladat az USMF bemutatócéget használja.


## <a name="set-up-interest-on-the-posting-profile"></a>Állítsa be a kamatot a feladási profilon
1. Ugorjon a Követel és beszedések > Beállítás > Vevői feladási profilok pontra.
2. Kattintson a Szerkesztés lehetőségre.
    * Válasszon ki egy kamatkódot a legördülő listáról. Ha nem szeretne kamatot számítani a tranzakciókhoz ehhez a feladói profilhoz, hagyja a mezőt üresen.  
    * A Tábla korlátozási lapján módosíthatja a kamatfeldolgozás módját. Ha ez a mező Igen értékre van állítva, a rendszer számít kamatot a feladási profilhoz.  

## <a name="calculate-interest"></a>Kamatszámítás
1. Ugorjon a Követel és beszedések > Kamat > Kamatlevél létrehozása pontra.
    * Ki kell választania azokat a tranzakciótípusokat, amelyekhez kamatot kíván számítani. Ez ilyen típusokhoz tartozó nyitott tranzakciók szerepelni fognak a számításban.  
    * Ha a Kamat lehetőséget választja, kamatos kamatot számíthat. A kamatos kamat számításához ellenőrizze az adott törvényeket, mielőtt ilyen tranzakciókat végezne.  
    * A kamat számítása ettől a dátumtól a „Záró dátum” dátumig történik. Ha nem ad meg „Kezdő dátum” dátumot, akkor a fel nem adott kamatlevelek törlésre kerülnek, és a kamat újraszámításra kerül a tranzakció dátumától.  
2. Adja meg a kamatlevél dátumát.
    * Háromféle feladási profil lehetőség létezik: Számla – a vevő számlájához rendelt feladási profil minden kamatlevél esetén.   Kiválasztott – a Feladási mezőben megadott feladási profil használata.   Tranzakció – az egyes kamatleveleknél kamat számításához használt tranzakciók egyéni feladási profiljának használata. Az olyan tranzakciók esetében, amelyekhez nincs hozzárendelve feladási profil, a rendszer a Kinnlevőségek paraméterei képernyő Főkönyv és áfa területén megadott feladási profilt fogja használni.  
    * Válasszon ki egy feladási profilt itt, ha módosította a „Feladási profil használata képernyő” lehetőséget „Kiválasztott” lehetőségre.  
3. Bontsa ki vagy csukja össze a Belefoglalandó rekordok részt.
4. Kattintson a Szűrő parancsra.
5. A Feltétel mezőben adjon meg Vevőazonosítót. Adja meg például az „US-001”-et.
6. Kattintson az OK gombra.
7. Kattintson az OK gombra.

## <a name="print-interest-notes"></a>Kamatlevelek nyomtatása
1. Ugorjon a Követel és beszedések > Kamat > Kamatlevél ellenőrzése és feldolgozása pontra.
2. Az Állapot mezőben válassza ki a „Létrehozva” értéket.
3. A Nyomtatott mezőben válassza a „Nem nyomtatva” lehetőséget.
4. Kattintson a Nyomtatás parancsra.
5. Bontsa ki vagy csukja össze a Belefoglalandó rekordok részt.
6. Kattintson az OK gombra.
7. Zárja be a lapot.

## <a name="post-the-interest-note"></a>Kamatlevél feladása
1. Válasszon ki egy olyan kamatlevelet, amely már feladásra kész (az állapota létrehozott).
2. Kattintson a Feladás lehetőségre.
3. A kamatlevél feladási dátumának megadása.
    * Jelölje be az Igent, ha az egyes kamatlevelekhez egyenként szeretné létrehozni a főkönyvi tranzakciókat.     Ha nem jelöli be az Igent, akkor a vevő kamatleveleinek kamatai halmozódnak és egyetlen tranzakcióként kerülnek a főkönyvbe.  
4. Bontsa ki vagy csukja össze a Belefoglalandó rekordok részt.
5. Kattintson az OK gombra.
6. Az Állapot mezőben válassza ki a „Feladott” értéket.


