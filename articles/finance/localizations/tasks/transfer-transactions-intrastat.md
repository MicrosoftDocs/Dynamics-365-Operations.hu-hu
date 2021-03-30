---
title: Tranzakciók átvitele az Intrastatba
description: Ez az eljárás bemutatja, hogy hogyan lehet beállítani az Intrastat paramétereit illetve, hogy hogyan viheti át a tranzakciókat az Intrastatba.
author: Anasyash
manager: AnnBe
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResCategoryHierarchyListPage, EcoResCategory, UnitOfMeasureLookup, ProcCategoryAddCommodityCode, EcoResProductDetailsExtended, IntrastatCommodityLookup, IntrastatTransactionCode, IntrastatParameters, DeliveryMode, MarkupTable, SalesTableListPage, SalesCreateOrder, SalesTable, MarkupTrans, SalesEditLines,  Intrastat, SysQueryForm, DeliveryReason, DeliveryTerms, DestinationCode
audience: Application User
ms.reviewer: kfend
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: anasyash
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8df2f7c9874b2cd78e5539fb9e3781ff9d5f4222
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5208363"
---
# <a name="transfer-transactions-to-the-intrastat"></a>Tranzakciók átvitele az Intrastatba

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja, hogy hogyan lehet beállítani az Intrastat paramétereit illetve, hogy hogyan viheti át a tranzakciókat az Intrastatba. Ez az eljárás a DEMF bemutatócég segítségével lett létrehozva.


## <a name="create-new-and-update-existing-commodity-code"></a>Hozzon létre egy új árucikk-kódot és módosítsa a meglévő árucikk-kódot
1. A Navigációs ablaktáblán ugorjon a **Modulok > Termékinformációk kezelése > Beállítás > Kategóriák és attribútumok > Kategóriahierarchiák** lehetőségre.
2. A listában keresse meg vagy válassza ki a **„Intrastat-vámtarifakódok** rekordot.
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
4. Válasszon ki egy rekordot a fastruktúrában. Például válassza ki az **„Intrastat\Beszélő** lehetőséget.  
5. Kattintson a **Szerkesztés** lehetőségre.
6. Bontsa ki a **Külkereskedelem** gyorslapot.
7. A **Kiegészítő egységek** mezőben adjon meg vagy válasszon ki egy értéket. Válassza ki például a **darab** lehetőséget.  
8. Válassza az **Igen** értéket a **Súly nem alkalmazható** mezőben.
9. Válassza ki az **Intrastat** lehetőséget a fastruktúrában.
10. Kattintson az **Új kategória-csomópont** gombra.
11. A **Név** mezőben adja meg az árucikk nevét. Például írja be a **Másik árucikk** szöveget.  
12. A **Kód** mezőben adja meg az árucikk kódját. Például írja be a **995 00 00** értéket.  
13. Írjon be egy értéket a Barátságos név mezőbe. Például írja be az **Egyéb** szöveget.  
14. Kattintson a **Mentés** gombra.
15. Zárja be a lapot.

## <a name="assign-commodity-code-to-product-hierarchy-and-released-product"></a>Rendelje hozzá az árucikk-kódot a termékhierarchiához és a kiadott termékhez.
1. Rekordok kereséséhez használja a gyorsszűrőt. Például végezzen szűrést a **Név** mezőben az **értékesítés** értékkel.
2. A listában kattintson a kijelölt sorban lévő hivatkozásra.
3. Bontsa ki a fastruktúrában a **kategória-csomópont**” lehetőséget. Például bontsa ki az **Értékesítési hierarchia\Home audio** lehetőséget.  
4. A fastruktúrában válassza ki a **Vámtarifakódhoz társítandó kategória** lehetőséget. Például válassza ki az **Értékesítési hierarchia\Home audio\Hangszóró lehetőséget.  
5. Bontsa ki az **Árucikk-kódok** gyorslapot.
6. Kattintson a **Hozzáadás** parancsra.
7. A **Hierarchia kiválasztása** mezőben válassza ki az **Intrastat** lehetőséget.
8. Keresse meg és válassza ki az árucikk-kódot a listában. Például válassza ki a **920 20 34 Hangszóró** lehetőséget.  
9. Kattintson a jobb nyílra a kód kiválasztásához.
10. Kattintson az **OK** gombra.
11. A Navigációs ablaktáblán ugorjon a **Modulok > Termékinformációk kezelése > Termékek > Kiadott termékek** lehetőségre.
12. Válassza ki a listában azt a kiadott terméket, amelyet az árucikk-kódhoz rendel. Válassza ki például a **D0001** lehetőséget.  
13. Kattintson a **Szerkesztés** lehetőségre.
14. Bontsa ki a **Külkereskedelem** gyorslapot.
15. Az **Árucikk** mezőben adja meg az árucikk-kódot. Válassza ki például a **920 20 34 Hangszóró** értéket.    
16. Adjon meg egy számot a **Költségszázalék** mezőben. Például írja be, hogy **3**.  
17. Az **Ország/régió** mezőben adjon meg vagy válasszon ki egy származási országot vagy régiót. Válassza például az **AUT-t**.  
18. Bontsa ki a **Készletkezelés** gyorslapot.
19. Adja meg a súly értékét kilogrammban a **Nettó tömeg** mezőben. Például írja be, hogy **2,5**.  
20. Kattintson a **Mentés** gombra.

## <a name="set-up-intrastat-transaction-codes-and-foreign-trade-parameters"></a>Állítsa be az Intrastat-tranzakciókódokat és a Külkereskedelmi paramétereket
1. A Navigációs ablakban ugorjon a **Modulok > Adók > Beállítás > Külkereskedelem > Tranzakciókódok** lehetőségre.
2. Kattintson az **Új** elemre.
3. Írjon be egy értéket a **Tranzakciókódok** mezőbe. Írja be például a **21** értéket a visszatérítésként használt tranzakciókódra vonatkozóan.  
4. A **Név** mezőbe írja be a Tranzakciókód nevét. Adja meg például a **Visszatérés** lehetőséget.  
5. Válasszon ki egy lehetőséget a **Statisztikai összeg** mezőben. Jelölje ki például az **Üres** lehetőséget, amely azt jelzi, hogy a **21-es** tranzakciókódos tranzakcióra vonatkozóan jelentendő Statisztikai értéknek mindig nullának kell lennie.  
6. A Navigációs ablakban ugorjon a **Modulok > Adók > Beállítás > Külkereskedelem > Külkereskedelmi paraméterek** lehetőségre.
7. A **Tranzakciókód** mezőben adjon meg vagy válasszon ki egy értéket. Válassza például a **11-et**.  
8. A **Jóváírás** mezőben adjon meg vagy válasszon ki egy értéket. Ez az érték a fizikai visszárut azonosítja. A rendszer a tényleges visszaadásra vonatkozó jóváírást az ellenkező irányba helyezi át az Intrastat naplóban. Például a rendszer az érkezés visszáruzásának átvitelét kiszállításként végzi el.   Ellenkező esetben a jóváírást helyesbítésnek minősül, és a rendszer ugyanabba az irányba helyezi át, de ellenkező előjellel. Például a rendszer az érkezés helyesbítésének átvitelét negatív összeges érkezésként végzi el és az aktív jelzőt **Helyesbítés** értékre állítja.  
9. Bontsa ki az **Átvitel** gyorslapot.
10. Válassza az **Igen** lehetőséget a **Cikkek árucikk-kóddal** mezőben. Jelölje be ezt a lehetőséget, ha csak az árucikk-kóddal rendelkező tranzakció átvitelét szeretné elvégezni. Az árucikk-kód nélküli tranzakciókat nem lehet áthelyezni az Intrastatba.  
11. Az **Átvitel, ha megfelel a következő feltételnek** mezőben válasszon ki egy lehetőséget. Válassza ki például a **Kijelöltek egyike** lehetőséget.  
12. Bontsa ki az **Árucikk-kódok hierarchiája** szakaszt.
13. Kattintson az **Ország/régió tulajdonságai** lapra.
14. Kattintson az **Új** elemre.
15. Az **Ország/régió** mezőben adjon meg vagy válasszon ki egy értéket. Válassza ki például a **FRA** értéket.  
16. Az **Intrastat kód** mezőben adja meg az ország ISO-kódját.  Írja be például az **FR** értéket.  
17. Az **Ország/régió típusa** mezőben válassza ki az **EU** lehetőséget.
18. Kattintson a Számsorozatok lapra.

## <a name="set-up-modes-of-delivery-and-rules-for-including-charges-in-intrastat"></a>Állítsa be a Szállítási módot és az Intrastat költségek bevételére vonatkozó szabályokat
1. A Navigációs ablaktáblán ugorjon a **Modulok > Értékesítés és marketing > Beállítás > Elosztás > Szállítási módok** lehetőségre.
2. Keresse meg és jelölje ki a kívánt rekordot a listán. Válassza ki például a **20 Légi** értéket.  
3. Bontsa ki a **Külkereskedelem** gyorslapot.
4. Kattintson a **Szerkesztés** lehetőségre.
5. A **Szállítás** mezőben adjon meg vagy válasszon ki egy értéket. Válassza például a **02-t**.  
6. A Navigációs ablaktáblán ugorjon a **Modulok > Kinnlevőségek > Költségek beállítása > Költségkód** lehetőségre.
7. Rekordok kereséséhez használja a gyorsszűrőt. Például végezzen szűrést a Költségkód mezőben a **szállítási költség** értékkel.
8. Bontsa ki a **Külkereskedelem** gyorslapot.
9. Kattintson a **Szerkesztés** lehetőségre.
10. Válassza az **Igen** lehetőséget az **Intrastat számlaérték** mezőben. A rendszer átviszi az összeget a **Számlaköltségek** mezőbe, és a Számla összege mezőbe átvitt összeggel végzi el az összegzést. Jelölje be az **Igen** értéket az **Intrastat statisztikai érték** mezőben, ha a módosítások összegét át kell vinni a **Statisztikai költségek** mezőbe, és összegezni kell a **Statisztikai összeg** mezővel.  

## <a name="sell-products-for-eu-customers"></a>Termékek értékesítése az EU vevőkre vonatkozóan
1. A Navigációs ablaktáblán ugorjon a **Modulok > Kintlévőségek > Megrendelések > Minden értékesítési rendelés** lehetőségre.
2. Kattintson az **Új** elemre.
3. Válasszon ki egy uniós vevőt a **Vevői számla** mezőben. Válassza ki például a **DE-012 Litware Kiskereskedelem** lehetőséget.  
4. Bontsa ki a **Szállítás** gyorslapot.
5. A **Szállítás módja**  mezőben adjon meg vagy válasszon ki egy értéket. Válassza ki például a **20 Légi** értéket.  
6. Kattintson az **OK** gombra.
7. Válassza ki az értékesítésirendelés-sorok első sorát.
8. Az **Cikkszám** mezőben adjon meg vagy válasszon ki egy értéket. Válassza például a **D001-t**.  
9. Bontsa ki a **Soradatok** gyorslapot.
10. Kattintson a **Külkereskedelem** fülre. A rendszer automatikusan kitölti az átvitelt a kiválasztott a szállítási mód alapján.  
11. A **Port** mezőben adjon meg vagy válasszon ki egy értéket.
12. Kattintson a **Pénzügy** lehetőségre. A beállítások szerint ez az összeg fog szerepelni az **Intrastat számlaérték** mezőben.  
13. Kattintson a **Költségek karbantartása** lehetőségre.
14. A **Költségkód** mezőben adjon meg vagy válasszon ki egy értéket. Válassza ki például a **FREIGHT** lehetőséget.  
15. Válassza ki a **Megtartás** jelölőnégyzetet.
16. Adjon meg egy számot az **Költségek értéke** mezőben. Például írja be, hogy **10**.  
17. Kattintson a **Mentés** gombra.
18. Zárja be a lapot.
19. A Műveleti ablaktáblán kattintson a **Számla** elemre.
20. Kattintson a **Számla** pontra.
21. Bontsa ki a **Paraméterek** szakaszt.
22. A **Mennyiség** mezőben válassza a **Mind** lehetőséget.
23. Bontsa ki a **Beállítás** gyorslapot.
24. Adjon meg egy dátumot a **Számla dátuma** mezőben. Például írja be, hogy **2015. 01. 31.**  
25. Kattintson az **OK** gombra.
26. Kattintson az **OK** gombra.
27. Zárja be a lapot.
28. Kattintson az **Új** elemre.
29. Válasszon ki egy uniós vevőt a **Vevői számla** mezőben. Válassza ki például a **DE-013 Trey Nagykereskedelem** lehetőséget.
30. Kattintson az **OK** gombra.
31. Az **Cikkszám** mezőben adjon meg vagy válasszon ki egy értéket. Válassza ki például a **D0001-t**.  
32. Kattintson a **Mentés** gombra.
33. Kattintson a **Számla** pontra.
34. Adjon meg egy dátumot a **Számla dátuma** mezőben. Adja meg például a **2015. 01 31.** dátumot.  
35. Kattintson az **OK** gombra.
36. Kattintson az **OK** gombra.

## <a name="transfer-transactions-to-the-intrastat"></a>Tranzakciók átvitele az Intrastatba
1. A Navigációs ablakban ugorjon a **Modulok > Adók > Nyilatkozatok > Külkereskedelem > Intrastat** lehetőségre.
2. Kattintson az **Áthelyezés** elemre.
3. Válassza ki az **Igen** lehetőséget a **Vevői számla** mezőben.
4. Kattintson a **Szűrő** parancsra.
5. Jelölje meg a **Dátummal** ellátott sort a listában.
6. Adjon meg egy értéket a **Feltétel** mezőben. Adja meg például a szűrést a 2015 januári időszakra vonatkozóan (a pontos érték a dátumformátumtól függ): 2015.01.01. .. 2015.01.31.  
7. Kattintson az **OK** gombra.
8. Kattintson az **OK** gombra.
9. Keresse meg és válassza ki az átvitt rekordot a listában.
10. Kattintson az **Általános** fülre.
    
Tekintse át az átvitt adatokat, többek között a cél/feladás országát/régióját, a származási országot, a súlyt, a mennyiséget, a kiegészítő egységek mennyiségét, az árucikket, a tranzakciókódot, a számlaösszeget és a statisztikai összegeket. Szükség esetén módosíthatja az adatot.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]