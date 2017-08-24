--- 
title: "Szállítási rendelés közvetlen kiszállításként"
description: "Ez az eljárás bemutatja, hogyan hozhatja létre az értékesítési rendelések közvetlen kiszállításait."
author: omulvad
manager: AnnBe
ms.date: 02/12/2016
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
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: d98e288a157183fbf4d7c032d86bb4a65166e297
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# <a name="ship-orders-as-direct-deliveries"></a>Szállítási rendelés közvetlen kiszállításként

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogyan hozhatja létre az értékesítési rendelések közvetlen kiszállításait. A közvetlen kiszállítás akkor használatos, amikor a szállítótól közvetlenül a vevőhöz kell árut szállítani, ahelyett hogy a saját raktárába szállítaná. Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is futtathatja. A „Közvetlen kiszállítások létrehozása a munkaterületről” második alfeladat sikeres befejezéséhez, ügyeljen rá, hogy az értékesítési rendelésen kiválasztott cikkhez tartozzon alapértelmezett szállító a kiadott alaptermék Beszerzés gyorslapján.


## <a name="set-an-individual-order-for-direct-delivery"></a>Állítson be egyetlen rendelést közvetlen kiszállításhoz.
1. Ugrás az összes értékesítési rendelésre.
2. Kattintson az Új lehetőségre.
3. A Vevőszámla mezőben adjon meg vagy válasszon ki egy értéket.
    * Az USMF használata esetén választhatja az „US-001” számlát.  
4. Kattintson az OK gombra.
5. Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.
    * Az USMF használata esetén választhatja a „T0020” cikket.  
6. Kattintson a Mentés gombra.
7. A Művelet panelen kattintson az Értékesítési rendelés elemre.
8. Kattintson a Közvetlen kiszállítás lehetőségre.
    * A Szállítás létrehozás lap felsorolja az összes nyitott értékesítésirendelés-sort az értékesítési rendelésből másolva. Áttekintheti a rendelési részleteket, és ha szükséges módosíthatja az olyan részleteket, mint a beszerzési mennyiség és az árképzési feltételek a közvetlen kiszállítás létrehozása előtt.  
9. Válassza ki az Igen lehetőséget az Összes belefoglalása mezőben.
    * Ha az értékesítésirendelés-soroknak csupán egy részhalmazához szeretne közvetlen kiszállítást létrehozni, akkor ezeket egyenként válassza ki.  
    * A Szállítószámla mező ekkor lehet üres, de akár már szerepelhet is benne egy szállítószám. Ha van alapértelmezett szállítói beállítva a termékhez (a kapcsolódó cikkfedezetnél), akkor az ez a szállító be lesz másolva a sorba. Ellenkező esetben a szállítót manuálisan kell megadni. Ebben a példában egy új szállítót választunk ki a következő lépésben, még akkor is, ha már be van írva egy.   
10. A Szállítószámla mezőben adjon meg vagy válasszon ki egy értéket.
    * Az USMF használata esetén választhatja az 1001 számlát.  
11. Kattintson az OK gombra.
    * Az üzenet tájékoztat arról, hogy a beszerzési rendelés létrehozása megtörtént.   
12. Bontsa ki a Soradatok szakaszt.
13. Kattintson a Kiszállítás lapra.
    * A Közvetlen kiszállítás mező értéke most Igen.  
    * A közvetlen kiszállítás állapota: a beszerzési rendelés létrehozva.   
14. A Művelet panelen kattintson az Általános elemre.
15. Kattintson a Kapcsolódó rendelések lehetőségre.
16. Kattintson a Beszerzési rendelés mezőben található hivatkozásra.
17. Bontsa ki a Soradatok szakaszt.
18. Kattintson a Cím fülre.
    * Ne feledje, hogy a beszerzési rendelési sorhoz a szállítási cím a vevő szállítási címe, és nem a vállalat címe.  
    * Ha az eredeti értékesítésirendelés-sor vagy a beszerzésirendelés-sor szállítási címét módosítja, akkor a megfelelő rendelési sor szállítási címe automatikusan frissülni fog.  
19. Kattintson a Kiszállítás lapra.
    * Ahogy az értékesítésirendelés-sor esetében, a társított beszerzésirendelés-sor típusa is Közvetlen kiszállítás értékre lesz állítva.  
    * A beszerzésirendelés-sor szállítási dátuma és visszaigazolt szállítási dátuma rendre az eredeti értékesítésirendelés-sor kért bevételezési dátumára és visszaigazolt bevételezési dátumára lesznek állítva.   
    * Ha ezek közül valamelyik dátumot frissíti a beszerzési sornál vagy az értékesítési sornál, akkor a megfelelő rendelésnél automatikusan frissülnek a dátumok.     
    * Egy speciális társítás kapcsolja az eredeti értékesítési rendeléshez azon beszerzési rendeléseket, amelyek a beállítás szerint közvetlenül a vevőhöz szállítanak. Ezen társítás azzal a szabállyal jár, hogy az értékesítési rendelés szállítólevél-frissítését nem lehet az értékesítési rendelésből elvégezni, csak a beszerzési rendelés segítségével. A vevői számlázást azonban az értékesítési rendelésből kell elvégezni.  
20. A Művelet panelen kattintson a Beszerzés elemre.
21. Kattintson a Megerősítés gombra.
22. Kattintson az OK gombra.
23. A Művelet panelen kattintson a Bevételezés elemre.
24. Kattintson a Termékbevételezés elemre.
25. Írjon be egy értéket a Termékbevételezés mezőbe.
26. Kattintson az OK gombra.
27. A Művelet panelen kattintson az Általános elemre.
28. Kattintson a Kapcsolódó rendelések lehetőségre.
29. A listában jelölje meg a kiválasztott sort.
    * Miután a beszerzési rendelés bevételezett állapotúre frissült, vagyis amikor a szállító kiszállította az árut a vevő címére, az eredeti értékesítési rendelés állapota automatikusan Leszállítottra frissül  
    * Az értékesítési rendelés most már számlázható.    
30. Kattintson az OK gombra.
31. Zárja be a lapot.
32. Kattintson az OK gombra.

## <a name="create-direct-deliveries-from-the-workbench"></a>Közvetlen kiszállítások létrehozása a munkaterületről
1. Zárja be a lapot.
2. Zárja be a lapot.
3. Ugrás az összes értékesítési rendelésre.
4. Kattintson az Új lehetőségre.
5. A Vevőszámla mezőben adjon meg vagy válasszon ki egy értéket.
6. Kattintson az OK gombra.
7. Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.
8. Bontsa ki a Soradatok szakaszt.
9. Kattintson a Kiszállítás lapra.
    * Ahelyett, hogy létrehozna egy közvetlen kiszállítást az értékesítési rendelés feldolgozásának a részeként, mint az előző eljárásban, most választhatja azt, hogy átadja ezt a feladatot egy beszerzési szakértőnek. Ahhoz, hogy az értékesítésirendelés-sor közvetlen kiszállítás kezelési folyamtának része legyen, be kell jelölni a közvetlen kiszállítást a sornál.  
10. Válassza az Igen lehetőséget a Közvetlen kiszállítás mezőben.
    *   Ha a cikkhez már alapértelmezés szerint a közvetlen kiszállítás van beállítva, akkor a mező értéke automatikusan Igen lesz a rendelésisor-bejegyzésnél. A Közvetlen kiszállítás lehetőséget Igen értékre állítva, és egy alapértelmezett közvetlen kiszállítási raktár kiválasztásával beállíthatja egy cikkhez a közvetlen kiszállítást a kiadott termék alaptermékénél.  
    * Mivel a beszerzési rendelést még nem hozták létre, a Közvetlen szállítás állapota közvetlen szállítás.   
11. Zárja be a lapot.
12. Zárja be a lapot.
13. Lépjen a Közvetlen kiszállítás részre.
    * A Közvetlen kiszállítás lap munkaterületként funkcionál, és lehetővé teszi a beszerzési ügynökök számára az összes, közvetlen kiszállításra állított értékesítési rendelés áttekintését, így lehetővé teszi számukra, hogy létrehozzák a megfelelő beszerzési rendeléseket. Továbbá a Visszaigazolás és Kiszállítás lapokon megtekinthetik a nyitott közvetlen kiszállítású rendeléseket és a visszaigazolt rendeléseket.   
14. Kattintson a Közvetlen kiszállítású rendelés létrehozása lehetőségre.
15. Kattintson a Visszaigazolás fülre.
    * Miután létrehozott egy közvetlen kiszállítású rendelést, automatikusan a Visszaigazolás lapra került. Közvetlenül erről a lapról is megerősítheti a rendelést. Amint megtörténik a beszerzés megerősítése, automatikusan átkerül a Szállítás lapra, ahonnan nyilvántartásba vehető a bevételezése.  


