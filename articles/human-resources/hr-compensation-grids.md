---
title: Kompenzációs rácsok beállítása
description: A kompenzációs rácsok segítségével meghatározható és fenntartható a fix kompenzációs tervek fizetési szerkezete.
author: twheeloc
ms.date: 01/03/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HRCCompGrid, HRCCompGridView, HcmCompensationWorkspace
audience: Application User
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9119c15cf80b9ebb9bed83ac438f24249aa4aa2f
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/04/2022
ms.locfileid: "8691673"
---
# <a name="set-up-compensation-grids"></a>Kompenzációs rácsok beállítása


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

A kompenzációs rácsok segítségével meghatározható és fenntartható a fix kompenzációs tervek fizetési szerkezete. A kompenzációs rácsok megoszthatók több terv között, illetve másolhatók egy új kompenzációs terv létrehozásakor.  Kompenzációs rács létrehozásához a szinteket és a hivatkozási pontokat be kell állítani. Ez a példa egy új Fokozat típusú kompenzációs rácsot hoz létre a szintek és a hivatkozási pontok bemutató adatait használva. Ez az eljárás az USMF bemutatócéget használja.


## <a name="set-up-information-about-the-compensation-grid"></a>A kompenzációs rács adatainak beállítása
1. Ugorjon az **Emberi erőforrások** > **Kompenzáció** > **Fix kompenzáció** > **Kompenzációs rácsok** pontra.
2. Kattintson az **Új** elemre.
3. Érték beírása a **Rács** mezőbe.
4. Írjon egy értéket a **Leírás** mezőbe.
5. A **Típus** mezőben válasszon ki egy lehetőséget.
6. A **Referencia** beállítás mezőben adjon meg vagy válasszon ki egy értéket.
7. A **Pénznem** mezőben adjon meg vagy válasszon ki egy értéket.
8. Adja meg a dátumot az **Érvényesség dátuma** mezőben.

## <a name="add-levels-to-the-compensation-structure"></a>Szintek hozzáadása a kompenzációs struktúrához
1. Kattintson a **Kompenzációs struktúra** elemre.
2. A listában jelölje meg a kiválasztott sort.
3. A **Szint** mezőben adjon meg vagy válasszon ki egy értéket.
4. Kattintson az **Új** elemre.
5. A listában jelölje meg a kiválasztott sort.
6. A **Szint** mezőben adjon meg vagy válasszon ki egy értéket.
7. Kattintson az **Új** elemre.
8. A listában jelölje meg a kiválasztott sort.
9. A **Szint** mezőben adjon meg vagy válasszon ki egy értéket.
10. Kattintson az **Új** elemre.
11. A listában jelölje meg a kiválasztott sort.
12. A **Szint** mezőben adjon meg vagy válasszon ki egy értéket.
13. Kattintson az **Új** elemre.
14. A listában jelölje meg a kiválasztott sort.
15. A **Szint** mezőben adjon meg vagy válasszon ki egy értéket.

## <a name="fill-in-the-compensation-structure-with-values"></a>Töltse ki a kompenzációs struktúrát értékekkel
1. A listában jelölje meg a kiválasztott sort.
    * Ezen a ponton a kompenzációs értékeket meg lehet adni kézzel a tábla minden egyes mezőjében, vagy használható a Tömeges módosítás funkció, amellyel egyszerűen kitölthető több mező is és elvégezhetők egyszerűbb számítások.  
2. Kattintson a **Tömeges módosítás** elemre.
    * Ennél a rácsnál először alkalmazzuk az első szint középpontjának értékét a táblázat minden mezőjére. Ez lesz az alapja a kompenzációs mátrixnak.  
3. A **Módosítás típusa** mezőben válasszon ki egy lehetőséget.
4. A **Kiigazítás összege** mezőben adjon meg egy számot.
5. A listában jelölje meg az összes sort, vagy törölje a jelölésüket.
6. Kattintson az **Alkalmazás a rácsra** elemre.
    * Most a tömeges módosítás funkcióval fogjuk növelni az összegeket minden egymást követő szinten egy bizonyos százalékkal vagy összeggel. Ebben a példában minden fokozat 12,5 % szórással fog rendelkezni a középpontjaik körük.  
7. A **Módosítás típusa** mezőben válasszon ki egy lehetőséget.
8. A **Kiigazítás összege** mezőben adjon meg egy számot.
9. Keresse meg és jelölje ki a kívánt rekordot a listán.
10. Kattintson az **Alkalmazás a rácsra** elemre.
    * Most a Tömeges módosítás funkcióval beállítjuk az egy szintek minimum és maximum referenciapontjait. Ebben a példában 50%-os lesz a szórás így a minimum hivatkozási pont -20%-kal, a maximum pedig +20%-kal módosul.  
11. A **Kiigazítás összege** mezőben adjon meg egy számot.
12. A **Referenciapont** mezőben adjon meg vagy válasszon ki egy értéket.
13. A listában jelölje meg az összes sort, vagy törölje a jelölésüket.
14. Kattintson az **Alkalmazás a rácsra** elemre.
15. A **Kiigazítás összege** mezőben adjon meg egy számot.
16. A **Referenciapont** mezőben adjon meg vagy válasszon ki egy értéket.
17. A listában jelölje meg az összes sort, vagy törölje a jelölésüket.
18. Kattintson az **Alkalmazás a rácsra** elemre.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
