---
title: A meghatározott termékek szállítójának jóváhagyása
description: Ez az eljárás bemutatja, hogy hogyan hagyhatja jóvá a szállítókat az adott termékre vonatkozóan.
author: RichardLuan
manager: tfehr
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, PdsApprovedVendorList, VendTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d08791caba34908903ce330df0f91e44fbdfcaea
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5237275"
---
# <a name="approve-vendors-for-specific-products"></a>A meghatározott termékek szállítójának jóváhagyása

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja, hogy hogyan hagyhatja jóvá a szállítókat az adott termékre vonatkozóan. Ez lehetővé teszi, hogy ellenőrizze, hogy mely szállítókat lehet használni akkor, amikor a termék hozzá van adva a beszerzési rendeléshez. Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is használhatja. Általában ezt a feladatot egy Beszerzési vezető végzi el.

1. A Navigációs ablaktáblán ugorjon a **Modulok > Termékinformációk kezelése > Termékek > Kiadott termékek** lehetőségre.
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
4. Bontsa ki a **Vásárlás** gyorslapot. Ha egy elsődleges szállító a **Szállító** mezőben látható, akkor engedélyezett szállítóként kell hozzáadnia ezt a szállítót az alábbiakban leírt lépésekben. Jegyezze fel a szállító számát, ha legalább egy látható.  
5. A Művelet panelen kattintson a **Beszerzés** elemre.
6. Kattintson a **Beállítások** elemre.
7. Kattintson a **Hozzáadás** parancsra.
8. A Szállító mezőben adjon meg vagy válasszon ki egy értéket. Válassza ki a jóváhagyott szállítót. Legalább egy sornak az elsődleges szállítónak kell lennie, amennyiben volt ilyen termékrekordban. Ha korábban már létrehozta a szállító számának megjegyzését, válassza ki itt.  
9. A **Lejárat ideje** mezőben adjon meg egy dátumot. Válasszon ki egy pár hónappal későbbi dátumot.  
10. Kattintson a **Hozzáadás** parancsra.
11. A **Szállító** mezőben adjon meg vagy válasszon ki egy értéket.
12. A **Lejárat ideje** mezőben adjon meg egy dátumot. Válasszon ki egy dátumot, amely nem ugyanaz, mint az előző lejárati dátumot.  
13. Zárja be a lapot.
14. A Művelet panelen kattintson a **Jóváhagyott beszállítók** elemre.
15. A **Lejárat ideje** mezőben adjon meg egy dátumot. Ez a dátum szűrőként működik, így láthatja egy bizonyos időpontig azokat a személyeket, akik engedélyezett szállítók.  
16. Zárja be a lapot.
17. A Művelet panelen kattintson **Hatályosság időszaka** elemre.
18. A **Következő időpontig lejárt szállítók megjelenítése** mezőben adjon meg egy dátumot. Az oldal segítségével azonosíthatja a szállítókat, ahol bizonyos idő elteltével lejár a jóváhagyási állapota.  
19. Zárja be a lapot.
20. Kattintson a **Szerkesztés** lehetőségre.
21. Az **Engedélyezett szállítók ellenőrzési módszere** mezőben adjon meg egy lehetőséget. Ezen mező segítségével válassza ki a házirendet arra vonatkozóan, hogy mi történjen, ha a termék hozzá van rendelve egy beszerzési rendeléssorhoz, ahol a szállító nem egy engedélyezett szállító.  
22. Kattintson a **Mentés** gombra.
23. Zárja be a lapot.
24. Zárja be a lapot.
25. A Navigációs panelen Ugorjon a **Modulok > Beszerzés és forrás > Szállítók > Szállító/cikk-kapcsolatok > Jóváhagyott szállítók listája cikk szerint** pontra. Ezen lapon áttekintést nyújt az összes termékről és engedélyezett szállítóról.  
26. Zárja be a lapot.
27. A Navigációs ablaktáblán válasssza a **Modulok > Beszerzés és forrás > Szállítók > Összes beszállító** menübe. A folyamatot kezdheti a szállítótól, majd ugorjon az engedélyezett termékek listájára a szállítói számlára vonatkozóan.  
28. Keresse meg és jelölje ki a kívánt rekordot a listán.
29. A Művelet panelen kattintson a **Beszerzés** elemre.
30. Kattintson az **Engedélyezett szállítók listája szállító szerint** lehetőségre.
31. Zárja be a lapot.
32. Zárja be a lapot.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]