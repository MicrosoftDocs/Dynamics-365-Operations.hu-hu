---
title: Kompenzációs rácsok beállítása
description: A kompenzációs rácsok segítségével meghatározható és fenntartható a fix kompenzációs tervek fizetési szerkezete.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRCCompGrid, HRCCompGridView, HcmCompensationWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5d5ada0817dd73caad38bb2e50302869857c71d8
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4418834"
---
# <a name="set-up-compensation-grids"></a>Kompenzációs rácsok beállítása

A kompenzációs rácsok segítségével meghatározható és fenntartható a fix kompenzációs tervek fizetési szerkezete. A kompenzációs rácsok megoszthatók több terv között, illetve másolhatók egy új kompenzációs terv létrehozásakor.  Kompenzációs rács létrehozásához a szinteket és a hivatkozási pontokat be kell állítani. Ez a példa egy új Fokozat típusú kompenzációs rácsot hoz létre a szintek és a hivatkozási pontok bemutató adatait használva. Ez az eljárás az USMF bemutatócéget használja.


## <a name="set-up-information-about-the-compensation-grid"></a>A kompenzációs rács adatainak beállítása
1. Ugorjon az Emberi erőforrások > Kompenzáció > Fix kompenzációs > Kompenzációs rácsok pontra.
2. Kattintson az Új lehetőségre.
3. Érték beírása a Rács mezőbe
4. A Leírás mezőben adjon meg egy értéket.
5. A Típus mezőben válasszon ki egy lehetőséget.
6. A Referenciabeállítás mezőben adjon meg vagy válasszon ki egy értéket.
7. A Pénznem mezőben adjon meg vagy válasszon ki egy értéket.
8. Érték beírása a Pénznem mezőbe.
9. Adja meg a dátumot az Érvényesség dátuma mezőben.

## <a name="add-levels-to-the-compensation-structure"></a>Szintek hozzáadása a kompenzációs struktúrához
1. Kattintson a Kompenzációs struktúra elemre.
2. A listában jelölje meg a kiválasztott sort.
3. A Szint mezőben adjon meg vagy válasszon ki egy értéket.
4. Kattintson az Új elemre.
5. A listában jelölje meg a kiválasztott sort.
6. A Szint mezőben adjon meg vagy válasszon ki egy értéket.
7. Kattintson az Új elemre.
8. A listában jelölje meg a kiválasztott sort.
9. A Szint mezőben adjon meg vagy válasszon ki egy értéket.
10. Kattintson az Új elemre.
11. A listában jelölje meg a kiválasztott sort.
12. A Szint mezőben adjon meg vagy válasszon ki egy értéket.
13. Kattintson az Új elemre.
14. A listában jelölje meg a kiválasztott sort.
15. A Szint mezőben adjon meg vagy válasszon ki egy értéket.

## <a name="fill-in-the-compensation-structure-with-values"></a>Töltse ki a kompenzációs struktúrát értékekkel
1. A listában jelölje meg a kiválasztott sort.
    * Ezen a ponton a kompenzációs értékeket meg lehet adni kézzel a tábla minden egyes mezőjében, vagy használható a Tömeges módosítás funkció, amellyel egyszerűen kitölthető több mező is és elvégezhetők egyszerűbb számítások.  
2. Kattintson a Tömeges módosítás elemre.
    * Ennél a rácsnál először alkalmazzuk az első szint középpontjának értékét a táblázat minden mezőjére. Ez lesz az alapja a kompenzációs mátrixnak.  
3. A Módosítás típusa mezőben válasszon ki egy lehetőséget.
4. A Kiigazítás összege mezőben adjon meg egy számot.
5. A listában jelölje meg az összes sort, vagy törölje a jelölésüket.
6. Kattintson az Alkalmazás a rácsra elemre.
    * Most a tömeges módosítás funkcióval fogjuk növelni az összegeket minden egymást követő szinten egy bizonyos százalékkal vagy összeggel. Ebben a példában minden fokozat 12,5 % szórással fog rendelkezni a középpontjaik körük.  
7. A Módosítás típusa mezőben válasszon ki egy lehetőséget.
8. A Kiigazítás összege mezőben adjon meg egy számot.
9. A kívánt rekord megkeresése és kijelölése a listán
10. A kívánt rekord megkeresése és kijelölése a listán
11. A kívánt rekord megkeresése és kijelölése a listán
12. A kívánt rekord megkeresése és kijelölése a listán
13. Kattintson az Alkalmazás a rácsra elemre.
14. A kívánt rekord megkeresése és kijelölése a listán
15. A kívánt rekord megkeresése és kijelölése a listán
16. A kívánt rekord megkeresése és kijelölése a listán
17. Kattintson az Alkalmazás a rácsra elemre.
18. A kívánt rekord megkeresése és kijelölése a listán
19. A kívánt rekord megkeresése és kijelölése a listán
20. Kattintson az Alkalmazás a rácsra elemre.
21. Keresse meg és jelölje ki a kívánt rekordot a listán.
22. Kattintson az Alkalmazás a rácsra elemre.
    * Most a Tömeges módosítás funkcióval beállítjuk az egy szintek minimum és maximum referenciapontjait. Ebben a példában 50%-os lesz a szórás így a minimum hivatkozási pont -20%-kal, a maximum pedig +20%-kal módosul.  
23. A Kiigazítás összege mezőben adjon meg egy számot.
24. A Referenciapont mezőben adjon meg vagy válasszon ki egy értéket.
25. A listában jelölje meg az összes sort, vagy törölje a jelölésüket.
26. Kattintson az Alkalmazás a rácsra elemre.
27. A Kiigazítás összege mezőben adjon meg egy számot.
28. A Referenciapont mezőben adjon meg vagy válasszon ki egy értéket.
29. A listában jelölje meg az összes sort, vagy törölje a jelölésüket.
30. Kattintson az Alkalmazás a rácsra elemre.

