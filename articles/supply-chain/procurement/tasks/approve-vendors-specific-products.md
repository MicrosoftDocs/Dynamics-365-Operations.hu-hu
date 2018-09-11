--- 
title: "A meghatározott termékek szállítójának jóváhagyása"
description: "Ez az eljárás bemutatja, hogy hogyan hagyhatja jóvá a szállítókat az adott termékre vonatkozóan."
author: mkirknel
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductDetailsExtended, PdsApprovedVendorList, VendTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: ffc58d2afe73fa2290e4e73a058d47ffd64b8d54
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="approve-vendors-for-specific-products"></a>A meghatározott termékek szállítójának jóváhagyása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogy hogyan hagyhatja jóvá a szállítókat az adott termékre vonatkozóan. Ez lehetővé teszi, hogy ellenőrizze, hogy mely szállítókat lehet használni akkor, amikor a termék hozzá van adva a beszerzési rendeléshez. Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is használhatja. Általában ezt a feladatot egy Beszerzési vezető végzi el.

1. Kattintson a Termékinformációk kezelése > Termékek > Kiadott termékek lehetőségre.
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
4. Bontsa ki a Beszerzés szakaszt.
    * Ha egy elsődleges szállító a szállítói mezőben látható, akkor engedélyezett szállítóként kell hozzáadnia ezt a szállítót az alábbiakban leírt lépésekben. Jegyezze fel a szállító számát, ha legalább egy látható.  
5. A Művelet panelen kattintson a Beszerzés elemre.
6. Kattintson a Beállítások elemre.
7. Kattintson a Hozzáadás gombra.
8. A Szállító mezőben adjon meg vagy válasszon ki egy értéket.
    * Válassza ki a jóváhagyott szállítót. Legalább egy sornak az elsődleges szállítónak kell lennie, amennyiben volt ilyen termékrekordban. Ha korábban már létrehozta a szállító számának megjegyzését, válassza ki itt.  
9. A Lejárat ideje mezőben adjon meg egy dátumot.
    * Válasszon ki egy pár hónappal későbbi dátumot.  
10. Kattintson a Hozzáadás gombra.
11. A Szállító mezőben adjon meg vagy válasszon ki egy értéket.
12. A Lejárat ideje mezőben adjon meg egy dátumot.
    * Válasszon ki egy dátumot, amely nem ugyanaz, mint az előző lejárati dátumot.  
13. Zárja be a lapot.
14. Kattintson az Engedélyezett szállítók lehetőségre.
15. A Lejárat ideje mezőben adjon meg egy dátumot.
    * Ez a dátum szűrőként működik, így láthatja egy bizonyos időpontig azokat a személyeket, akik engedélyezett szállítók.  
16. Zárja be a lapot.
17. Kattintson az Érvényességi időszak lehetőségre.
18. A következő időpontig lejárt szállítók megjelenítése mezőben adjon meg egy dátumot.
    * Az oldal segítségével azonosíthatja a szállítókat, ahol bizonyos idő elteltével lejár a jóváhagyási állapota.  
19. Zárja be a lapot.
20. Kattintson a Szerkesztés lehetőségre.
21. Az Engedélyezett szállítók ellenőrzési módszere mezőben adjon meg egy lehetőséget.
    * Ezen mező segítségével válassza ki a házirendet arra vonatkozóan, hogy mi történjen, ha a termék hozzá van rendelve egy beszerzési rendeléssorhoz, ahol a szállító nem egy engedélyezett szállító.  
22. Kattintson a Mentés gombra.
23. Zárja be a lapot.
24. Zárja be a lapot.
25. Ugorjon a Beszerzés és forrás > Szállítók > Szállító/cikk-kapcsolatok > Jóváhagyott szállítók listája cikk szerint pontra.
    * Ezen lapon áttekintést nyújt az összes termékről és engedélyezett szállítóról.  
26. Zárja be a lapot.
27. Ugrás a Beszerzés és forrás > Beszállítók > Minden szállító pontra.
    * A folyamatot kezdheti a szállítótól, majd ugorjon az engedélyezett termékek listájára a szállítói számlára vonatkozóan.  
28. Keresse meg és jelölje ki a kívánt rekordot a listán.
29. A Művelet panelen kattintson a Beszerzés elemre.
30. Kattintson az Engedélyezett szállítók listája szállító szerint lehetőségre.
31. Zárja be a lapot.
32. Zárja be a lapot.


