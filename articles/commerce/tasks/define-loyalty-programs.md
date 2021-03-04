---
title: Hűségprogramok meghatározása
description: Ez az eljárás bemutatja, hogyan hozhat létre egy két hűségszinttel rendelkező hűségprogramot.
author: jashanno
manager: AnnBe
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 91f30d4d1b66e5b4b90f7df67d8f76a95a100338
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412906"
---
# <a name="define-loyalty-programs"></a>Hűségprogramok meghatározása

[!include [banner](../includes/banner.md)]

Ez az eljárás bemutatja, hogyan hozhat létre egy két hűségszinttel rendelkező hűségprogramot. Ez az eljárás az USRT bemutatócéget használja.

1. Lépjen a Kiskereskedelem és kereskedelem > .. > Hűségprogramok lehetőségre.
2. Kattintson az Új elemre.
3. Írjon be egy értéket a Név mezőbe.
4. A Leírás mezőben adjon meg egy értéket.
5. Kattintson az Új sor hozzáadására.
6. Adjon meg egy számot a Szint mezőben.
7. A Szint mezőben adja meg a hűségszint nevét.
8. Írjon egy értéket a „Leírás” mezőbe.
9. A Dátumtartomány mezőben kattintson a legördülő gombra a keresőlista megnyitásához.
    * Ezt az időintervallumot ki kell terjeszteni a jövőre. Ha például egy éves időintervallumot ad meg az arany szinthez, akkor az arany szintet elérő vevők egy éven keresztül kaphatják meg a szintre vonatkozó jutalmakat. Ha egy vevő az arany szintjének érvényességi időszaka alatt újból jogosulttá válik az adott fokozatra, akkor automatikusan egy évvel meghosszabbodik a fokozat érvényességi időtartama a jogosultság újbóli megszerzésétől számítva.  
10. A listában kattintson a kijelölt sorban lévő hivatkozásra.
11. Kattintson az Új sor hozzáadása lehetőségre.
12. Adjon meg egy számot a Szint mezőben.
13. A Szint mezőben adja meg a hűségszint nevét.
14. Írjon egy értéket a „Leírás” mezőbe.
15. A Dátumtartomány mezőben kattintson a legördülő gombra a keresőlista megnyitásához.
16. A listában kattintson a kijelölt sorban lévő hivatkozásra.
17. Kattintson a Mentés gombra.
18. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * A szintszabályok meghatározzák az egy adott időintervallumon belül minimum megszerzendő hűségpontok számát, ami ahhoz szükséges, hogy valaki elérjen egy bizonyos szintet.  
19. Bontsa ki a Szintszabályok részt.
20. Kattintson az Új lehetőségre.
    * Egy fokozatra több szintszabály is vonatkozhat. Például három különböző feltétele is lehet egy szint elérésének: 500 USD elköltése egy hónapban, 1000 USD elköltése egy év alatt, és 20 tranzakció végrehajtása egy év alatt. Ehhez három szintszabályt kell létrehoznia.  
21. A Hűségpont mezőben kattintson a legördülő gombra a keresőlista megnyitásához.
    * Ez egy nem beváltható hűségpont kell, hogy legyen.  
22. A listában kattintson a kijelölt sorban lévő hivatkozásra.
23. A Minimális kiadott pontok mezőben adjon meg egy számot.
    * Ha a legalacsonyabb fokozatú szintre minden vevő jogosult csupán azáltal, hogy részt vesz a programban, írjon be „0” értéket.  
24. A Kiértékelés dátuma mezőben kattintson a legördülő gombra a keresőlista megnyitásához.
    * Ezt az időintervallumot ki kell terjeszteni a múltra. Csak az ebben az időtartományban szerzett pontokat veszik figyelembe a minimum kiadott pontok elérésénél.  
25. A listában kattintson a kijelölt sorban lévő hivatkozásra.
26. Kattintson a Mentés gombra.
27. Keresse meg és jelölje ki a kívánt rekordot a listán.
28. Kattintson az Új elemre.
29. A Hűségpont mezőben kattintson a legördülő gombra a keresőlista megnyitásához.
30. A listában kattintson a kijelölt sorban lévő hivatkozásra.
31. A Minimális kiadott pontok mezőben adjon meg egy számot.
32. A Kiértékelés dátuma mezőben kattintson a legördülő gombra a keresőlista megnyitásához.
    * Ezt az időintervallumot ki kell terjeszteni a múltra.  
33. A listában kattintson a kijelölt sorban lévő hivatkozásra.
34. Kattintson a Mentés gombra.
35. Kattintson az Árcsoportok lehetőségre.
    * Ha szeretne engedményeket adni a hűséges vevőknek. egy vagy több árcsoportot kell hozzárendelnie a hűségprogramhoz és az árcsoportokat hozzá kell rendelnie az engedményekhez. Az a legjobb, ha nem keveri a különböző árcsoportokat a különböző típusú engedmények között.  Például ne használja ugyanazt az árcsoportot egy hűségkedvezmény és egy csatornakedvezmény esetén.  
36. Az Árcsoport mezőben kattintson a legördülő gombra a keresőlista megnyitásához.
    * Az oldal tetején található Árcsoportok hivatkozás a hűségprogramhoz tartozik. A Programszintek gyorslapon található Árcsoportok hivatkozás egy adott hűségszinthez tartozik.  
37. A listában kattintson a kijelölt sorban lévő hivatkozásra.
38. Kattintson a Mentés gombra.
39. Zárja be a lapot.
40. Kattintson a Mentés gombra.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]