---
title: Készletszintek inicializálása a raktárban
description: Ez az eljárás bemutatja, hogyan frissítheti kézileg az aktuális készletet a Készletmozgási napló segítségével.
author: perlynne
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalMovement, InventJournalCreate, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2c1e5ca96919acde7e850292a73ebd00185f1f7a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5244474"
---
# <a name="initialize-stock-levels-in-the-warehouse"></a>Készletszintek inicializálása a raktárban

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]