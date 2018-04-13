---
title: "Készletszintek inicializálása a raktárban"
description: "Ez az eljárás bemutatja, hogyan frissítheti kézileg az aktuális készletet a Készletmozgási napló segítségével."
author: perlynne
manager: AnnBe
ms.date: 11/02/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d804480167414cd038f8229db312dc9c52d131f8
ms.openlocfilehash: 3b4685b034f7e6a3af0259fb921230e7b3397754
ms.contentlocale: hu-hu
ms.lasthandoff: 11/02/2017

---
# <a name="initialize-stock-levels-in-the-warehouse"></a>Készletszintek inicializálása a raktárban

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogyan frissítheti kézileg az aktuális készletet a Készletmozgási napló segítségével. (Az aktuális készlet frissítése az adatentitásokban található tranzakciók importálásával is történhet.) Ezt az útmutatót az USMF bemutatócégen is lefuttathatja, ahol minden előfeltétel elérhető, például a naplónevek, cikkbeállítások, feladási profilok és számlák. Az útmutató a használt cikkre és dimenziókra vonatkozóan adott értékeket javasol. Ha egy másik elemet választ, lehetséges, hogy más dimenziók értékeit kell megadnia.

1. Ugrás a Készletgazdálkodás > Naplóbejegyzések > Cikkek > Mozgás menüpontba.
2. Kattintson az Új lehetőségre.
3. A Név mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
4. Válassza ki az IMov. lehetőséget.
    * Tanácsos különböző naplósablonok nevét használni különböző üzleti célokra.  
5. A listában kattintson a kijelölt sorban lévő hivatkozásra.
6. Az Ellenszámla mezőben adja meg a „140200” értékeket.
    * Ez az ellenszámla lesz a naplósorok alapértelmezett számlája. Lehetséges felülírni az alapértelmezettet, ha más ellenszámlát szeretne hozzárendelni egy sorhoz.  
7. Kattintson az OK gombra.
8. Kattintson az Új lehetőségre.
9. A Cikkszám mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
10. Válassza az A0001 elemet.
11. A listában kattintson a kijelölt sorban lévő hivatkozásra.
12. Kattintson a Készlet dimenziók lapra.
13. A Hely mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
14. Válassza ki az 1. helyet.
15. A Raktár mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
16. Válasszak ki a 13. raktárt.
17. A listában kattintson a kijelölt sorban lévő hivatkozásra.
18. A Hely mezőben kattintson a legördülő gombra a keresőlista megnyitásához.
19. Válassza ki a 13. helyet.
20. Adjon meg egy számot a Mennyiség mezőben.
21. Kattintson a Mentés gombra.
22. Kattintson a Feladás lehetőségre.
23. Jelölje be a Minden feladási hiba átvitele egy új naplóba jelölőnégyzetet, vagy törölje a jelölést.
    * Ha engedélyezi ezt a beállítást, a rendszer bemásolja egy új naplóba az olyan sorokat, amelyek nem kerülnek feladásra. A naplóban található információk segítségével korrigálhatja a problémákat, majd újra feladathatja a sorokat.  
24. Kattintson az OK gombra.
25. Zárja be a lapot.
26. Zárja be a lapot.

