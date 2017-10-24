--- 
title: "Értékesítési szerződések teljesítése"
description: "Ez az eljárás bemutatja, hogyan lehet teljesíteni egy értékesítési szerződés értékesítési rendelések hozzárendelésével."
author: omulvad
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: f0894bf962c139c2e9e4c9f8d1589fd933afcedb
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="fulfill-sales-agreements"></a>Értékesítési szerződések teljesítése

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogyan lehet teljesíteni egy értékesítési szerződés értékesítési rendelések hozzárendelésével. Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is futtathatja. Az útmutató megkezdése előtt ellenőrizze, hogy rendelkezik-e érvényes „Termékértékére vonatkozó kötelezettség” típusú értékesítési szerződéssel. Azt is megteheti, hogy futtathatja az „Értékesítési szerződések létrehozása" nevű feladatútmutatót.  




## <a name="release-a-sales-order-from-the-agreement"></a>Értékesítési rendelés kiadása a szerződésből
1. Lépjen az Értékesítés és marketing > Értékesítési szerződések > Értékesítési szerződések menüpontba.
2. Nyissa meg a listában a szerződést, amelyben ellenében ki szeretné adni a rendelést.
3. A Művelet panelen kattintson az Értékesítési szerződés elemre.
4. Kattintson a Rendelés kiadása lehetőségre.
    * Ahogy a Kiadási rendelés létrehozása lap tetején lévő szöveg is kiemeli, az értékesítési-sorokhoz szükséges részletek eltérők lesznek attól függően, hogy a szerződés mennyiség- vagy értékalapú?  
    * Ez az útmutató a „Termékérték-kötelezettség” típusú szerződést használ. Ez az oka annak, hogy a lap Sorok szakasza üres. Ha kötelezettség mennyiségalapú lenne, a soradatok a megállapodásból lennének átmásolva.  
5. Kattintson a Létrehozás lehetőségre.
    * Az üzenet tájékoztat arról, hogy az értékesítési rendelés létrehozása megtörtént. Mivel a rendelés nem tartalmaz sorokat, rendeléssor-adatokat kell hozzáadni a kiadási folyamat befejezéséhez.   
6. Zárja be a lapot.
7. Zárja be a lapot.
8. Lépjen az Értékesítés és marketing > Értékesítési rendelések > Minden értékesítési rendelés menüpontba.
9. A listában keresse meg és nyissa meg a rendelést, amely az előző feladat rendeléskiadása következtében jött létre.
10. Kattintson az Új sor hozzáadására.
11. A Cikkszám mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
12. A Cikkszám mezőben írja be vagy válassza ki a cikket, amely a társított értékesítési szerződésen meg van adva.
13. Adjon meg egy számot a Mennyiség mezőben.
    * Győződjön meg arról, hogy olyan mennyiséget írjon be, amely a nettó összeget a hozzárendelt értékesítési megállapodás értéke alá viszi.  
    * Figyelje meg, hogy mivel az értékesítési rendelés a szerződéshez kapcsolódik, a letárgyalt kedvezményszázalék módosítja a rendelési sort.  
14. Kattintson a Sor frissítése elemre.
15. Kattintson a Csatolt elemre.
    * A Csatolt szerződés lap mutatja azon szerződés azonosítóját és feltételeit, amelyből a sor ki lett adva.  
16. Zárja be a lapot.
17. A Művelet panelen kattintson az Általános elemre.
18. Kattintson a Csatolt értékesítési szerződés lehetőségre.
19. Bontsa ki a Soradatok szakaszt.
20. Kattintson a Teljesítés fülre.
    * A Teljesítés lap összegzi az összes értékesítésirendelés-sort, amely hozzá van rendelve ehhez a kötelezettséghez, valamint a teljesítési állapotukat és a még ki nem adott összeget vagy mennyiséget.   
21. Zárja be a lapot.
22. Zárja be a lapot.
23. Zárja be a lapot.

## <a name="apply-sales-agreement-in-the-order-process"></a>Értékesítési szerződés használata a rendelési folyamatban
1. Lépjen az Értékesítés és marketing > Értékesítési rendelések > Minden értékesítési rendelés menüpontba.
2. Kattintson az Új lehetőségre.
3. A Vevői számla mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
4. A listában keresse meg és válassza ki az értékesítési szerződésen megadott vevőt.
5. A listában kattintson a kijelölt sorban lévő hivatkozásra.
6. Bontsa ki az Általános szakaszt.
7. Az Értékesítési szerződés azonosítója mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
8. A listában kattintson a kijelölt sorban lévő hivatkozásra.
9. Kattintson az Igen gombra.
10. Kattintson az OK gombra.
11. A listában jelölje meg a kiválasztott sort.
12. A Cikkszám mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
13. A Cikkszám mezőben írja be vagy válassza ki a cikket, amely a társított értékesítési szerződésen meg van adva.
14. A listában kattintson a kijelölt sorban lévő hivatkozásra.
15. Kattintson a Mentés gombra.
16. A Művelet panelen kattintson a Kitárolás és csomagolás elemre.
17. Kattintson A szállítólevél feladása lehetőségre.
18. Bontsa ki a Paraméterek szakaszt.
19. Válassza ki az Igen lehetőséget a Feladás mezőben.
20. Kattintson az OK gombra.
21. Kattintson az OK gombra.
22. A Művelet panelen kattintson az Általános elemre.
23. Kattintson a Csatolt értékesítési szerződés lehetőségre.
24. Kattintson a Teljesítés fülre.


