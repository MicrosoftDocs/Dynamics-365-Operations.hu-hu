--- 
title: "Hűségprogramok meghatározása"
description: "Ez az eljárás bemutatja a hűségprogram meghatározását."
author: jashanno
manager: AnnBe
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 8bbdbf882f6f73d03be0a036cb975109396e4a0d
ms.openlocfilehash: 1fc193e113961705f18488a4341652b3576fb275
ms.contentlocale: hu-hu
ms.lasthandoff: 11/14/2017

---

# <a name="define-loyalty-schemes"></a>Hűségprogramok meghatározása

[!include[task guide banner](../includes/task-guide-banner.md)]

Ez az eljárás bemutatja a hűségprogram meghatározását. Ezek a programok a pontszerzési és beváltási szabályokat tartalmazzák. Ez az eljárás az USRT bemutatócéget használja.

1. Ugorjon a Kiskereskedelem és kereskedelem > Vevők > Hűség > Hűségprogramok lehetőségre.
2. Kattintson az Új lehetőségre.
3. Írjon egy értéket a Programazonosító mezőbe.
4. A Leírás mezőben adjon meg egy értéket.
5. A Név mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
    * Több hűségsémával is rendelkezhet egy hűségprogramon belül. A hűségsémák az összes csatornára, vagy csak a csatornák egy részére is érvényesek lehetnek.  
6. Keresse meg és jelölje ki a kívánt rekordot a listán.
7. A listában kattintson a kijelölt sorban lévő hivatkozásra.
8. Kattintson a Mentés gombra.
9. Kattintson az Új sor hozzáadása lehetőségre.
10. Válasszon ki egy lehetőséget a Tevékenységtípus mezőben.
    * Válassza a Vásárlás termékei összeg szerint lehetőséget, ha az alapján szeretné megjutalmazni a vevőket, hogy mennyit költenek. Válassza a Vásárlás termékei mennyiség szerint lehetőséget, ha az alapján szeretné megjutalmazni a vevőket, hogy hány terméket vásárolnak.  Válassza az Értékesítési tranzakciók száma lehetőséget, ha minden tranzakció esetén szeretné megjutalmazni a vevőt, függetlenül attól, hogy mit és mennyit vásárolt.  
    * Válasszon egy kategóriát. A kategória korlátozza, hogy mely termékekre vonatkozik ez a pontszerzési szabály.  
    * Ha azt szeretné, hogy a pontszerzési szabály minden termékre vonatkozzon, hagyja üresen ezt a mezőt.  
11. Írjon be egy számot a Tevékenységösszeg/mennyiség mezőbe.
    *  Az Értékesítési tranzakciók száma tevékenységtípushoz mindig használjon "1,0" értéket. A Vásárlás összeg szerint vagy Vásárlás mennyiség szerint tevékenységtípus esetén a megadott értéknél kisebb tranzakciók nem aktiválják a pontszerzési szabályt. Például, ha a tevékenységtípus Vásárlás összeg szerint, és „10,00” értéket ad meg, akkor egy „9,00” értékű értékesítési tranzakció nem jár pontszerzéssel ennél a szabálynál.  
12. Írjon be egy értéket a Tevékenység pénzneme mezőbe.
13. A Hűségpont azonosítója mezőben kattintson a legördülő gombra a keresőlista megnyitásához.
14. A listában kattintson a kijelölt sorban lévő hivatkozásra.
15. A Hűségpontok mezőben adjon meg egy számot.
    * Az összeg típusú pontszerzés tizedesjegyekkel rögzíti a megszerzett összeget. Például ha a pontszerzési szabály szerint 1 elköltött kanadai dollár 1 hűségpontot ér, és az ügyfél 1,25 kanadai dollárt költ, akkor 1,25 hűségpontot kap. A mennyiség típusú pontszerzés egész számokkal rögzíti a megszerzett összeget. Például ha a pontszerzési szabály szerint 1 elköltött kanadai dollár 1 hűségpontot ér, és az ügyfél 1,25 kanadai dollárt költ, akkor 1,0 hűségpontot kap.  
16. Kattintson a Mentés gombra.
17. Kattintson az Új sor hozzáadása lehetőségre.
    * A beváltási szabályokat hűségprogramos fizetési mód esetén használják.  
18. A Hűségpont azonosítója mezőben kattintson a legördülő gombra a keresőlista megnyitásához.
    * Csak a beváltható hűségpontok jelennek meg.  
19. A listában kattintson a kijelölt sorban lévő hivatkozásra.
20. A Hűségpontok mezőben adjon meg egy számot.
21. A Beváltás típusa mezőben válasszon ki egy lehetőséget.
    * Ha a Fizetés összeg szerint lehetőséget választja, az Összeg vagy mennyiség mezőt pénznemértékként kezeli a rendszer. Ebben az esetben a fizetés során pénzegységenként felhasznált hűségpontok összege fix arányú. Ha a Fizetés mennyiség szerint lehetőséget választja, az Összeg vagy mennyiség mezőt mennyiségértékként kezeli a rendszer. Ebben az esetben a cikkmennyiségenként felhasznált hűségpontok összege fix arányú, de a pénznemben megadott összeg eltérhet, ha hűségpontokkal kifizetett cikkek összege eltér ugyanakkora mennyiségnél. A beváltás típusú hűségpont-kedvezmény csak akkor érvényes, ha engedélyezve van az „Oroszország” ország/régió specifikus funkciókonfigurációs gomb, és a POS funkcióprofil ISO-kódja „RU”.  
    * Válasszon egy kategóriát. A kategória korlátozza, hogy mely termékekre vonatkozik ez a beváltási szabály.  
    * Ha azt szeretné, hogy a beváltási szabály minden termékre vonatkozzon, hagyja üresen ezt a mezőt.  
22. Írjon be egy számot az Összeg vagy mennyiség mezőbe.
23. Érték beírása a Pénznem mezőbe.
24. Kattintson a Mentés gombra.
25. Kattintson az Új sor hozzáadása lehetőségre.
    * Válasszon ki egy vagy több csomópontot az Elérhető szervezeti csomópontok listájáról, és helyezze át őket a Kiválasztott szervezeti csomópontok listájára úgy, hogy a két lista közötti nyílra kattint.  
26. Kattintson az OK gombra.
27. Kattintson a Mentés gombra.
    * Ha megváltoztatja a hűségprogram csatornáját, le kell futtatnia a Hűségprogramok feldolgozását. Így a csatornákra megérkezik a frissített hűségprogram.  


