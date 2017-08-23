--- 
title: "Kivételek kivizsgálása/feloldása"
description: "A Szállítói számlára vonatkozó irányelvek akkor futnak, amikor a szállítói számla oldal használatával ad fel egy szállítói számlát, és amikor megnyitja a szállítói számlára vonatkozó irányelv megszegéseinek lapját."
author: abruer
manager: AnnBe
ms.date: 02/16/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: f1c279546dfaa738022369f782df57f02afa883e
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# <a name="research-or-resolve-exceptions"></a>Kivételek kivizsgálása/feloldása

[!include[task guide banner](../../includes/task-guide-banner.md)]

A Szállítói számlára vonatkozó irányelvek akkor futnak, amikor a szállítói számla oldal használatával ad fel egy szállítói számlát, és amikor megnyitja a szállítói számlára vonatkozó irányelv megszegéseinek lapját. A szállítói számla munkafolyamatát is beállíthatja úgy, hogy a valahányszor számlát küld egy munkafolyamathoz, futtatja a szállítói számlára vonatkozó irányelveket. 

A szállítói számla irányelvek nem vonatkoznak azokra a számlákra, amelyek a számlajegyzékben vagy a számlanaplóban jöttek létre. 

A számlaegyeztetés érvényesítése nem használja a szállítói számla irányelveket, ehelyett egy Kötelezettségek paraméterei oldalt hoz létre.

Ez a felvétel az USMF bemutatócéget használja. A kötelezettségeket kezelő vezető vagy a könyvelésért felelős vezető ezeket a lépéseket hajtja végre. Mielőtt elkezdené a beállítást, győződjön meg arról, hogy a Számlaegyeztetés konfigurációs kulcs be van állítva.


## <a name="prepare-to-create-vendor-invoice-policies"></a>Felkészülés a szállítói számlára vonatkozó irányelvek létrehozására
1. Ugorjon a Kötelezettségek > Beállítás > Kötelezettségek paraméterei pontra.
2. Kattintson a Számlaegyeztetés fülre.
3. Válassza ki vagy állítsa alaphelyzetbe a Számlafejléc állapotának automatikus frissítése jelölőnégyzetét.
4. Kattintson az OK gombra.
5. A Számlafeladás eltérésekkel mezőben válasszon a lehetőségek közül.
6. Zárja be a lapot.
7. Ugorjon a Kötelezettségek > Irányelv-beállítás > Szállítói számlára vonatkozó irányelvek pontra.
8. Kattintson a Paraméterek lehetőségre.
9. Majd a btnAdd lehetőségre.
10. Zárja be a lapot.

## <a name="create-policy-rule-types-for-vendor-invoices"></a>Szállítói számla irányelvszabály-típusainak létrehozása szállítói számlákhoz
1. Ugorjon a Kötelezettségek > Irányelv-beállítás > Szállítói számlára vonatkozó irányelvszabály típusok pontra.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Szabály neve mezőbe.
4. A Leírás mezőben adjon meg egy értéket.
5. A Lekérdezés neve mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
6. Keresse meg és jelölje ki a kívánt rekordot a listán.
7. A listában kattintson a kijelölt sorban lévő hivatkozásra.
8. Kattintson a Mentés gombra.
9. Zárja be a lapot.

## <a name="define-a-vendor-invoice-policy"></a>Adjon meg egy Szállítói számlára vonatkozó irányelvet
1. Ugorjon a Kötelezettségek > Irányelv-beállítás > Szállítói számlára vonatkozó irányelvek pontra.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Név mezőbe.
4. A Leírás mezőben adjon meg egy értéket.
5. Csukja be vagy bontsa ki az Irányelv szervezetei szakaszt.
6. A fán válassza ki a „Contoso Szórakozás rendszer USA” lehetőséget.
7. Kattintson a Hozzáadás gombra.
8. Csukja be vagy bontsa ki az Irányelvszabályok szakaszt.
9. Kattintson az Irányelvszabályra.
10. Írjon be egy értéket a Irányelvszabály leírása mezőbe.
11. Kattintson a Szűrő parancsra.
12. Kattintson a Hozzáadás gombra.
13. A listában jelölje meg a kiválasztott sort.
14. A Táblázat mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
15. A listában kattintson a kijelölt sorban lévő hivatkozásra.
16. A Származtatott tábla mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
17. A listában kattintson a kijelölt sorban lévő hivatkozásra.
18. A Mező mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
19. Érték beírása a Mező mezőbe.
20. Zárja be a lapot.
21. Érték beírása a Feltétel mezőbe.
22. Kattintson az OK gombra.
23. Kattintson az OK gombra.
24. Zárja be a lapot.
25. Zárja be a lapot.


