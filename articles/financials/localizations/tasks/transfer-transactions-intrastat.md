--- 
title: "Tranzakciók átvitele az Intrastatba"
description: "Ez az eljárás bemutatja, hogy hogyan lehet beállítani az Intrastat paramétereit illetve, hogy hogyan viheti át a tranzakciókat az Intrastatba."
author: Anasyash
manager: AnnBe
ms.date: 06/09/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: anasyash
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: cc21497a6905cdb57bd687b7bff0d9dc810ba9eb
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="transfer-transactions-to-the-intrastat"></a>Tranzakciók átvitele az Intrastatba

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogy hogyan lehet beállítani az Intrastat paramétereit illetve, hogy hogyan viheti át a tranzakciókat az Intrastatba. Ez az eljárás a DEMF bemutatócég segítségével lett létrehozva.


## <a name="create-new-and-update-existing-commodity-code"></a>Hozzon létre egy új árucikk-kódot és módosítsa a meglévő árucikk-kódot
1. Ugorjon a Termékinformációk kezelése > Beállítás > Kategóriák és attribútumok > Kategóriahierarchiák pontra.
2. A listában keresse meg vagy válassza ki a „Intrastat-vámtarifakódok” rekordot.
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
4. Válassza ki az „egy rekord” lehetőséget a fastruktúrában.
    * Például válassza ki a „Intrastat\Beszélő” lehetőséget.  
5. Kattintson a Szerkesztés lehetőségre.
6. Bontsa ki a Külkereskedelem szakaszt.
7. A Kiegészítő egységek mezőben adjon meg vagy válasszon ki egy értéket.
    * Válassza ki például a „darab” lehetőséget.  
8. Válassza az Igen értéket a Súly nem alkalmazható mezőben.
9. Válassza ki az „Intrastat” lehetőséget a fastruktúrában.
10. Kattintson az Új kategória-csomópont gombra.
11. A Név mezőben adja meg az árucikk nevét.
    * Például írja be a „Másik árucikk” szöveget.  
12. A Kód mezpben adja meg az árucikk-kódját.
    * Például írja be a „995 00 00” értéket.  
13. Írjon be egy értéket a Barátságos név mezőbe.
    * Például írja be az „Egyéb” szöveget.  
14. Kattintson a Mentés gombra.
15. Zárja be a lapot.

## <a name="assign-commodity-code-to-product-hierarchy-and-released-product"></a>Rendelje hozzá az árucikk-kódot a termékhierarchiához és a kiadott termékhez.
1. Rekordok kereséséhez használja a gyorsszűrőt. Végezzen szűrést a Név mezőben az „Értékesítés” értékkel.
2. A listában kattintson a kijelölt sorban lévő hivatkozásra.
3. Bontsa ki a fastruktúrában a „a kategória-csomópont” lehetőséget.
    * Például bontsa ki az „Értékesítési hierarchia\Home audio” lehetőséget.  
4. Válassza ki a „A vámtarifakódhoz társítandó kategória” lehetőséget.
    * Például válassza ki az „Értékesítési hierarchia\Home audio\Beszélő” lehetőséget.  
5. Bontsa ki az Árucikk-kódok szakaszt.
6. Kattintson a Hozzáadás gombra.
7. A Hierarchia kiválasztás mezőben válassza ki az „Intrastat” lehetőséget.
8. Keresse meg és válassza ki az árucikk-kódot a listában
    * Például válassza ki a „920 20 34 Beszélő” lehetőséget.  
9. Kattintson a SelectCodes lehetőségre.
10. Kattintson az OK gombra.
11. Kattintson a Termékinformációk kezelése > Termékek > Kiadott termékek lehetőségre.
12. Válassza ki a listában azt a kiadott terméket, amelyet az árucikk-kódhoz rendel.
    * Válassza ki például a „D0001” lehetőséget.  
13. Kattintson a Szerkesztés lehetőségre.
14. Bontsa ki a Külkereskedelem szakaszt.
15. Az Árucikk mezőben adja meg az árucikk-kódját.
    * Válassza ki például a „920 20 34 Beszélő” értéket.    
16. Adjon meg egy számot a Költségszázalék mezőben.
    * Adja meg például a „3” értéket.  
17. Az ország/régió mezőben adjon meg vagy válasszon ki egy származási országot vagy régiót
    * Válassza ki például az „AUT” lehetőséget.  
18. Bontsa ki a Készletkezelés szakaszt.
19. Adja meg egy Súly (kg) értéket a Nettó tömeg mezőben.
    * Adja meg például a „2,5” értéket.  
20. Kattintson a Mentés gombra.

## <a name="set-up-intrastat-transaction-codes-and-foreign-trade-parameters"></a>Állítsa be az Intrastat-tranzakciókódokat és a Külkereskedelmi paramétereket
1. Ugorjon az Adó > Beállítás > Külkereskedelem > Tranzakciókódok pontra
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Tranzakciókódok mezőben.
    * Írja be például a „21” értéket a visszatérítésként használt tranzakciókódra vonatkozóan.  
4. A Név mezőbe írja be a Tranzakciókódok nevét.
    * Adja meg például a „Visszatérés” lehetőséget.  
5. Válasszon ki egy lehetőséget a Statisztikai összeg mezőben.
    * Jelölje ki például az „Üres” lehetőséget, amely azt jelzi, hogy a „21”-es tranzakciókódos tranzakcióra vonatkozóan jelentendő Statisztikai értéknek mindig nullának kell lennie.  
6. Ugrás az Adó > Beállítás > Külkereskedelem > Külkereskedelmi paraméterek pontra
7. A Tranzakciókód mezőben adjon meg vagy válasszon ki egy értéket.
    * Válassza ki például a „11”-es lehetőséget.  
8. A Jóváírás mezőben adjon meg vagy válasszon ki egy értéket.
    * Ez az érték a fizikai visszárut azonosítja. A rendszer a tényleges visszaadásra vonatkozó jóváírást az ellenkező irányba helyezi át az Intrastat naplóban. Például a rendszer az érkezés visszáruzásának átvitelét kiszállításként végzi el.   Ellenkező esetben a jóváírást helyesbítésnek minősül, és a rendszer ugyanabba az irányba helyezi át, de ellenkező előjellel. Például a rendszer az érkezés helyesbítésének átvitelét negatív összeges érkezésként végzi el és az aktív jelzőt „Helyesbítés” értékre állítja.  
9. Bontsa ki az Átvitel szakaszt.
10. Válassza az Igen lehetőséget a Cikkek árucikk-kóddal mezőben.
    * Jelölje be ezt a lehetőséget, ha csak az árucikk-kóddal rendelkező tranzakció átvitelét szeretné elvégezni. Az árucikk-kód nélküli tranzakciókat nem lehet áthelyezni az Intrastatba.  
11. Az Átvitel, ha megfelel a következő feltételnek mezőben válasszon ki egy lehetőséget.
    * Válassza ki például az „A kijelöltek egyike” lehetőséget.  
12. Bontsa ki az Árucikk-kódok hierarchiája szakaszt.
13. Kattintson az Ország/régió tulajdonságai lapra.
14. Kattintson az Új lehetőségre.
15. Az Ország/régió mezőben adjon meg vagy válasszon ki egy értéket.
    * Válassza ki például a „FRA” értéket.  
16. Az Intrastat kód mezőben adja meg az ország ISO-kódját.
    * Írja be például a „FR” értéket.  
17. Az Ország/régió típusa mezőben válassza ki az „EU” lehetőséget.
18. Kattintson a Számsorozatok lapra.

## <a name="set-up-modes-of-delivery-and-rules-for-including-charges-in-intrastat"></a>Állítsa be a Szállítási módot és az Intrastat költségek bevételére vonatkozó szabályokat
1. Ugorjon az Értékesítés és marketing > Beállítás > Elosztás > Szállítási módok pontra
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Válassza ki például a „20 Légi” értéket.  
3. Bontsa ki a Külkereskedelem szakaszt.
4. Kattintson a Szerkesztés lehetőségre.
5. A Szállítás mezőben adjon meg vagy válasszon ki egy értéket.
    * Válassza ki például a „02” lehetőséget.  
6. Ugorjon a Kintlévőségek > Költségek beállítása > Költségkód pontra.
7. Rekordok kereséséhez használja a gyorsszűrőt. Például végezzen szűrést a Költségkód mezőben a „ fuvardíj” értékkel.
8. Bontsa ki a Külkereskedelem szakaszt.
9. Kattintson a Szerkesztés lehetőségre.
10. Válassza az Igen lehetőséget az Intrastat számlaérték mezőben.
    * A rendszer átviszi az összeget a Számlaköltségek mezőbe és a Számla összege mezőbe átvitt összeggel végzi el az összegzést.    Jelölje be az Igen értéket az Intrastat statisztikai érték mezőben, ha a módosítások összegét át kell vinni a Statisztikai költségekbe és összegezni kell a Statisztikai összeggel.  

## <a name="sell-products-for-eu-customers"></a>Termékek értékesítése az EU vevőkre vonatkozóan
1. Ugorjon a Kinnlevőségek > Rendelések > Minden értékesítési rendelés elemre.
2. Kattintson az Új lehetőségre.
3. Válasszon ki egy uniós vevőt a Vevői számla mezőben.
    * Jelölje be például a „DE-012 Litware Kiskereskedelem” lehetőséget.  
4. Bontsa ki a Szállítás szakaszt.
5. A Szállítás módja mezőben adjon meg vagy válasszon ki egy értéket.
    * Válassza ki például a „20 Légi” értéket.  
6. Kattintson az OK gombra.
7. Vigye a mutatót az értékesítésirendelés-sorok első sorához.
8. Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.
    * Válassza ki például az „D001” lehetőséget.  
9. Bontsa ki a Soradatok szakaszt.
10. Kattintson a Külkereskedelem fülre.
    * A rendszer automatikusan kitölti az átvitelt a kiválasztott a szállítási mód alapján.  
11. A Port mezőben adjon meg vagy válasszon ki egy értéket.
12. Kattintson a Pénzügyre.
    * A beállítások szerint ez az összeg fog szerepelni az Intrastat számlaértékben.  
13. Kattintson a Költségek karbantartása lehetőségre.
14. A Költségkód mezőben adjon meg vagy válasszon ki egy értéket.
    * Jelölje ki például a „Fuvardíj” lehetőséget.  
15. Jelölje be a Megtartás jelölőnégyzetet.
16. Adjon meg egy számot az Költségek értéke mezőben.
    * Adja meg például a „10” értéket.  
17. Kattintson a Mentés gombra.
18. Zárja be a lapot.
19. A Művelet panelen kattintson a Számla lehetőségre.
20. Kattintson a Számla lehetőségre.
21. Bontsa ki a Paraméterek szakaszt.
22. A Mennyiség mezőben válassza a „Mind” lehetőséget.
23. Bontsa ki a Beállítások szakaszt.
24. A Számla dátuma mezőben adjon meg egy dátumot.
    * Adja meg például a „2015.01.31.” dátumot.  
25. Kattintson az OK gombra.
26. Kattintson az OK gombra.
27. Zárja be a lapot.
28. Kattintson az Új lehetőségre.
29. Válasszon ki egy uniós vevőt a Vevői számla mezőben.
    * Válassza ki például a „DE-013 Trey Wholesales” lehetőséget.  
30. Kattintson az OK gombra.
31. Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.
    * Válassza ki például az „D0001” lehetőséget.  
32. Kattintson a Mentés gombra.
33. Kattintson a Számla lehetőségre.
34. A Számla dátuma mezőben adjon meg egy dátumot.
    * Adja meg például a „2015.01.31.” dátumot.  
35. Kattintson az OK gombra.
36. Kattintson az OK gombra.

## <a name="transfer-transactions-to-the-intrastat"></a>Tranzakciók átvitele az Intrastatba
1. Ugorjon az Adó > Nyilatkozatok > Külkereskedelem > Intrastat pontra.
2. Kattintson az Áthelyezés elemre.
3. Válassza az Igen lehetőséget a Vevői számla mezőben.
4. Kattintson a Szűrő parancsra.
5. Jelölje meg a Dátummal ellátott sort a listában
6. Érték beírása a Feltétel mezőbe.
    * Adja meg például a szűrést a 2015 januári időszakra vonatkozóan (a pontos érték a dátumformátumtól függ): 2015.01.01. .. 2015.01.31.  
7. Kattintson az OK gombra.
8. Kattintson az OK gombra.
9. Keresse meg és válassza ki az átvitt rekordot a listában.
10. Kattintson az Általános fülre.
    * Tekintse át az átvitt adatokat, többek között a cél/feladás országát/régióját, a származási országot, a súlyt, a mennyiséget, a kiegészítő egységek mennyiségét, az árucikket, a tranzakciókódot, a számlaösszeget és a statisztikai összegeket.   Szükség esetén módosíthatja az adatot.  


