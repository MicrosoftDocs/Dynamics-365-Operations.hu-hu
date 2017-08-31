--- 
title: "Előleg alkalmazotthoz (Kelet-Európa)"
description: "Ez az eljárás bemutatja, hogyan lehet tranzakciókat beállítani és regisztrálni egy előlegre jogosult számára."
author: v-oloski
manager: AnnBe
ms.date: 10/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 0f0aed4dd530f7ec06d717e51b084d14e0816e43
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# <a name="advance-payment-to-an-employee-eastern-europe"></a>Előleg alkalmazotthoz (Kelet-Európa)

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogyan lehet tranzakciókat beállítani és regisztrálni egy előlegre jogosult számára. Ezt a eljárást a DEMF bemutatócéget használva hozták létre, az elsődleges címéhez tartozó ország pedig Litvánia. Ez a feladat csak az olyan jogi személyek esetében működik, amelyekben Lengyelországban, Litvániában, Lettországban, Észtországban, Csehországban vagy Magyarországon van az elsődleges címe. Ez az eljárás egy olyan funkcióra vonatkozik, amely a Dynamics 365 for Operations 1611-es verziójába került be.


## <a name="create-a-new-cash-account"></a>Új készpénzszámla létrehozása
1. Nyissa meg a következőt: Készpénz- és bankkezelés > Bankszámlák > Készpénzszámlák.
2. Kattintson az Új lehetőségre.
3. A Készpénz mezőben adjon meg egy értéket.
4. Írjon be egy értéket a Név mezőbe.
5. A Számsorozatcsoport mezőben adjon meg, vagy válasszon ki egy értéket.
6. Bontsa ki az Ellenőrzés szakaszt.
7. A Pénznem mezőben adjon meg vagy válasszon ki egy értéket.
8. Válassza az Igen lehetőséget a Negatív készpénz mezőben.
9. Kattintson a Mentés gombra.

## <a name="create-a-new-journal"></a>Új napló létrehozása
1. Ugorjon a Főkönyv > Naplóbeállítások > Naplónevek pontra.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Név mezőbe.
4. A Bizonylatsorozat mezőben adjon meg vagy válasszon ki egy értéket.
5. Kattintson a Mentés gombra.
6. Kattintson az Új elemre.
7. Írjon be egy értéket a Név mezőbe.
8. A Napló típusa mezőben válasszon ki egy lehetőséget.
9. A Bizonylatsorozat mezőben adjon meg vagy válasszon ki egy értéket.
10. Kattintson a Mentés gombra.

## <a name="create-an-advance-holder-group"></a>Előlegre jogosult csoport létrehozása
1. Ugrás a Kötelezettségek > Beállítás > Előlegre jogosultak > Előlegre jogosult csoportok elemre.
2. Kattintson az Új lehetőségre.
3. Érték beírása a Csoport mezőbe.
4. A Leírás mezőben adjon meg egy értéket.
5. Kattintson a Mentés gombra.

## <a name="create-an-employee-posting-profile"></a>Alkalmazott feladási sablonjának létrehozása
1. Ugrás a Kötelezettségek > Beállítás > Előlegre jogosultak > Alkalmazott feladási sablonjai elemre.
2. Kattintson az Új lehetőségre.
3. Írjon egy értéket a Feladási profil mezőbe.
4. A Leírás mezőben adjon meg egy értéket.
5. A listában jelölje meg a kiválasztott sort.
6. Az Érvényes mezőben válasszon ki egy lehetőséget.
7. Az Összegzett számla mezőben adja meg a kívánt értékeket.
8. Kattintson a Mentés gombra.

## <a name="set-up-advance-holder-parameters"></a>Előlegre jogosultak paramétereinek beállítása
1. Ugorjon a Kötelezettségek > Beállítás > Kötelezettségek paraméterei pontra.
2. Kattintson az Előlegre jogosultak fülre.
3. A Feladási profil mezőben adjon meg, vagy válasszon ki egy értéket.
4. A Név mezőben adjon meg vagy válasszon ki egy értéket.
5. A Készpénz mezőben adjon meg vagy válasszon ki egy értéket.
6. A Név mezőben adjon meg vagy válasszon ki egy értéket.
7. Válasszon egy lehetőséget a Számla típusa mezőben.
8. A Fő számla mezőben adja meg a kívánt értékeket.
9. Kattintson a Számsorozatok lapra.
10. Kattintson a Mentés gombra.

## <a name="set-up-a-cash-posting-profile"></a>Állítson be egy készpénzfeladási profilt
1. Nyissa meg a következőt: Készpénz- és bankkezelés > Beállítás > Készpénzfeladási sablonok.
2. Kattintson az Új lehetőségre.
3. A Készpénzfeladás mezőben adjon meg egy értéket.
4. A Leírás mezőben adjon meg egy értéket.
5. A listában jelölje meg a kiválasztott sort.
6. Az Érvényes mezőben válasszon ki egy lehetőséget.
7. A Fő számla mezőben adja meg a kívánt értékeket.
8. Kattintson a Mentés gombra.

## <a name="set-up-cash-and-bank-parameters"></a>Készpénz- és bankparaméterek beállítása
1. Ugorjon a Készpénz- és bankkezelés > Beállítás > Készpénz- és bankkezelési paraméterek pontra.
2. Kattintson a Készpénz lapra.
3. A Készpénz mezőben adjon meg vagy válasszon ki egy értéket.
4. A Készpénzfeladás mezőben adjon meg vagy válasszon ki egy értéket.
5. Kattintson a Mentés gombra.
6. Kattintson a Számsorozatok lapra.
7. Keresse meg és jelölje ki a kívánt rekordot a listán.
8. A Számsorrend kódja mezőben adjon meg, vagy válasszon ki egy értéket.
9. A kívánt rekord megkeresése és kijelölése a listán
10. A Számsorrend kódja mezőben adjon meg, vagy válasszon ki egy értéket.
11. Kattintson a Mentés gombra.

## <a name="set-up-terms-of-payment"></a>Fizetési feltételek beállítása
1. Ugrás a Kötelezettségek > Kifizetés beállítása > Fizetési feltételek elemre.
2. Kattintson a Szerkesztés lehetőségre.
3. A Kezdő előlegre jogosult mezőben válassza az Igen lehetőséget.
4. Kattintson a Mentés gombra.

## <a name="create-a-new-worker"></a>Új dolgozó létrehozása
1. Ugrás az Emberi erőforrások > Dolgozók > Dolgozók elemre.
2. Kattintson az Új lehetőségre.
3. Az Utónév mezőbe írjon be egy értéket.
4. A Vezetéknéve mezőbe írjon be egy értéket.
5. Adjon meg egy értéket a Dolgozó azonosítója mezőben.
6. Kattintson az Új dolgozó felvételére.
7. Kattintson a Mentés gombra.

## <a name="set-up-a-worker-as-an-advance-holder"></a>Dolgozó beállítása előlegre jogosultként
1. Ugrás a Kötelezettségek > Előlegre jogosultak > Előlegre jogosultak elemre.
2. Kattintson a Szerkesztés lehetőségre.
3. A Csoport mezőben adjon meg vagy válasszon ki egy értéket.
4. Az Előlegre jogosult mezőben válassza az Igen lehetőséget.
5. Kattintson a Mentés gombra.

## <a name="create-and-post-a-purchase-order-invoice"></a>Beszerzési rendelés számlájának létrehozása és feladása
1. Nyissa meg a következőt: Kötelezettségek > Beszerzési rendelések > Minden beszerzési rendelés.
2. Kattintson az Új lehetőségre.
3. A Szállítószámla mezőben adjon meg vagy válasszon ki egy értéket.
4. Kattintson az OK gombra.
5. A Sorok vagy fejléc mezőben válasszon egy lehetőséget.
6. Bontsa ki az Ár és engedmény szakaszt.
7. Adjon meg vagy válasszon ki egy értéket a Fizetési feltételek mezőben.
8. Az Előlegre jogosult mezőben adjon meg vagy válasszon ki egy értéket.
9. A Sorok vagy fejléc mezőben válasszon egy lehetőséget.
10. A listában jelölje meg a kiválasztott sort.
11. Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.
12. Adjon meg egy számot a Mennyiség mezőben.
13. Adjon meg egy számot az Egységár mezőben.
14. Kattintson a Mentés gombra.
15. A Művelet panelen kattintson a Beszerzés elemre.
16. Kattintson a Megerősítés gombra.
17. A Művelet panelen kattintson a Számla lehetőségre.
18. Kattintson a Számla lehetőségre.
19. Kattintson az Alapértelmezett forrás: Termék érkező mennyisége lehetőségre a legördülő párbeszédablak megnyitásához.
20. Egy lehetőség kiválasztása a Sorok alapértelmezett mennyisége mezőben.
21. Kattintson az OK gombra.
22. Érték beírása a Szám mezőbe.
23. A Számla leírása mezőben adjon meg egy értéket.
24. Adjon meg egy dátumot a Számla dátuma mezőben.
25. Az Áfatételjegyzék dátuma mezőbe írjon be egy dátumot.
26. Adjon meg egy dátumot a Beérkezési dokumentum dátuma mezőben.
27. Kattintson a Feladás lehetőségre.

## <a name="balance-and-close-advance-holders-transactions"></a>Előlegre jogosultak tranzakcióinak egyenlegének elkészítése és zárása
1. Ugrás a Kötelezettségek > Előlegre jogosultak > Előlegre jogosultak elemre.
2. Kattintson a Tranzakciók elemre.
3. Zárja be a lapot.
4. Kattintson az Egyenleg lehetőségre.
5. Kattintson a Zárás bankon keresztül lehetőségre.
6. Válassza ki az Igen lehetőséget az Automatikus mezőben.
7. Az Átutalandó összeg mezőben. mezőben adjon meg egy számot.
8. Kattintson az OK gombra.
9. Kattintson a Zárás készpénzen keresztül lehetőségre.
10. Válassza ki az Igen lehetőséget az Automatikus mezőben.
11. Kattintson az OK gombra.
12. Zárja be a lapot.
13. Kattintson a Tranzakciók elemre.


