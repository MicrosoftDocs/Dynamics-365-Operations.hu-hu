---
title: Szállítási rendelés közvetlen kiszállításként
description: Ez a témakör bemutatja, hogyan hozhatja létre az értékesítési rendelések közvetlen kiszállításait.
author: omulvad
manager: tfehr
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, PurchCreateFromSalesOrder, VendAccountItemLookup, SalesTableReferences, PurchTable, PurchTablePart, PurchEditLines, PurchTable, PurchTableReferences, MCRDropShipWorkbench, SalesShippingLine
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 31cb26479ccb74dfb58fd5590cd60d7b7c64c292
ms.sourcegitcommit: e3f4dd2257a3255c2982f4fc7b72a1121275b88a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/16/2020
ms.locfileid: "4018514"
---
# <a name="ship-orders-as-direct-deliveries"></a>Szállítási rendelés közvetlen kiszállításként

[!include [banner](../../includes/banner.md)]

Ez a témakör bemutatja, hogyan hozhatja létre az értékesítési rendelések közvetlen kiszállításait. A közvetlen kiszállítás akkor használatos, amikor a szállítótól közvetlenül a vevőhöz kell árut szállítani, ahelyett hogy a saját raktárába szállítaná. Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is futtathatja. A „Közvetlen kiszállítások létrehozása a munkaterületről” második alfeladat sikeres befejezéséhez, ügyeljen rá, hogy az értékesítési rendelésen kiválasztott cikkhez tartozzon alapértelmezett szállító a kiadott alaptermék Beszerzés gyorslapján.

## <a name="set-an-individual-order-for-direct-delivery"></a>Állítson be egyetlen rendelést közvetlen kiszállításhoz.
1. Ugorjon a **Navigációs ablaktábla > Modulok > Kintlévőségek > Megrendelések > Minden értékesítési megrendelés** lehetőségre.
2. Válassza az **Új** lehetőséget.
3. A **Vevőkód** mezőben adjon meg vagy válasszon ki egy értéket, majd nyomja meg az **OK** gombot
4. Írja be vagy válassza ki a **Cikkszámot** és a **Webhely** mező értékét, majd válassza ki a **Mentés** parancsot.
5. A Műveleti ablaktáblán válassza ki az **Értékesítési rendelés** lehetőséget, majd a **Közvetlen kiszállítás** elemet. A Szállítás létrehozás lap felsorolja az összes nyitott értékesítésirendelés-sort az értékesítési rendelésből másolva. Áttekintheti a rendelési részleteket, és ha szükséges módosíthatja az olyan részleteket, mint a beszerzési mennyiség és az árképzési feltételek a közvetlen kiszállítás létrehozása előtt.  
6. Válassza ki az **Igen** lehetőséget az **Összes belefoglalása** mezőben.
    - Ha az értékesítésirendelés-soroknak csupán egy részhalmazához szeretne közvetlen kiszállítást létrehozni, akkor ezeket egyenként válassza ki.  
    - A **Szállítószámla** mező ekkor lehet üres, de szerepelhet is benne egy szállítószám. Ha van alapértelmezett szállítói beállítva a termékhez (a kapcsolódó cikkfedezetnél), akkor az ez a szállító be lesz másolva a sorba. Ellenkező esetben a szállítót manuálisan kell megadni. Ebben a példában egy új szállítót választunk ki a következő lépésben, még akkor is, ha már be van írva egy.   
7. A **Szállítói számla** mezőben adjon meg vagy válasszon ki egy értéket, majd nyomja meg az **OK** gombot. Az üzenet tájékoztat arról, hogy a beszerzési rendelés létrehozása megtörtént.   
8. Bontsa ki a **Sorrészletek** szakaszt.
9. Válassza ki a **Szállítás** lapot, és ellenőrizze, hogy a **Közvetlen kiszállítás** mező értéke **Igen** -e.
10. A Művelet ablaktáblán válassza ki az **Általános** elemet.
11. Válassza ki a **Tervezett rendelések** lehetőséget.
12. Válassza ki a **Beszerzési rendelés** mezőben található hivatkozást.
13. Bontsa ki a **Soradatok** szakaszt, és válassza ki a **Cím** lapot.
    - A beszerzési rendelési sorhoz a szállítási cím a vevő szállítási címe, és nem a vállalat címe.  
    - Ha az eredeti értékesítésirendelés-sor vagy a beszerzésirendelés-sor szállítási címét módosítja, akkor a megfelelő rendelési sor szállítási címe automatikusan frissülni fog.  
14. Válassza ki a **Szállítás** lapot.
    - Ahogy az értékesítésirendelés-sor esetében, a társított beszerzésirendelés-sor típusa is Közvetlen kiszállítás értékre lesz állítva.  
    - A beszerzésirendelés-sor szállítási dátuma és visszaigazolt szállítási dátuma rendre az eredeti értékesítésirendelés-sor kért bevételezési dátumára és visszaigazolt bevételezési dátumára lesznek állítva.   
    - Ha ezek közül valamelyik dátumot frissíti a beszerzési sornál vagy az értékesítési sornál, akkor a megfelelő rendelésnél automatikusan frissülnek a dátumok.     
    - Egy speciális társítás kapcsolja az eredeti értékesítési rendeléshez azokat a beszerzési rendeléseket, amelyek a beállítás szerint közvetlenül a vevőhöz szállítanak. Ezen társítás azzal a szabállyal jár, hogy az értékesítési rendelés szállítólevél-frissítését nem lehet az értékesítési rendelésből elvégezni, csak a beszerzési rendelés segítségével. A vevői számlázást azonban az értékesítési rendelésből kell elvégezni.  
15. A Műveleti ablaktáblán válassza ki a **Beszerzés** lehetőséget.
16. Válassza ki a **Visszaigazolás** lehetőséget.
17. Válassza ki az **OK** lehetőséget.
18. A Művelet ablaktáblán válassza ki a **Bevételezés** elemet.
19. Válassza ki a **Termékbevételezés** elemet.
20. Írjon be egy értéket a **Termékbevételezés** mezőbe.
21. Válassza ki az **OK** lehetőséget.
22. A Művelet ablaktáblán válassza ki az **Általános** elemet.
23. Válassza ki a **Kapcsolódó rendelések** lehetőséget, és jelölje ki a kívánt rekordot.
    - Miután a beszerzési rendelés bevételezett állapotúre frissült, vagyis amikor a szállító kiszállította az árut a vevő címére, az eredeti értékesítési rendelés állapota automatikusan Leszállítottra frissül  
    - Az értékesítési rendelés most már számlázható.    
24. Válassza ki az **OK** lehetőséget.
25. Zárja be a lapot.
26. Válassza ki az **OK** lehetőséget. Zárja be az oldalakat, és térjen vissza a kezdőlapra.

## <a name="create-direct-deliveries-from-the-workbench"></a>Közvetlen kiszállítások létrehozása a munkaterületről
1. Ugorjon a **Navigáció > Modulok > Kintlévőségek > Megrendelések > Minden értékesítési megrendelés** lehetőségre.
2. Válassza az **Új** lehetőséget.
3. A **Vevőkód** mezőben adjon meg vagy válasszon ki egy értéket, majd nyomja meg az **OK** gombot.
4. Adjon meg vagy válasszon ki egy értéket a **Cikkszám** és a **hely** mezőben.
5. Bontsa ki a **Soradatok** szakaszt, majd válassza ki a **Szállítás** lapot. Ahelyett, hogy létrehozna egy közvetlen kiszállítást az értékesítési rendelés feldolgozásának a részeként, mint az előző eljárásban, most választhatja azt, hogy átadja ezt a feladatot egy beszerzési szakértőnek. Ahhoz, hogy az értékesítésirendelés-sor közvetlen kiszállítás kezelési folyamtának része legyen, be kell jelölni a közvetlen kiszállítást a sornál.  
6. Válassza ki az **Igen** lehetőséget a **Közvetlen kiszállítás** mezőben.
    - Ha a cikkhez már alapértelmezés szerint a közvetlen kiszállítás van beállítva, akkor a mező értéke automatikusan Igen lesz a rendelésisor-bejegyzésnél. A Közvetlen kiszállítás lehetőséget Igen értékre állítva, és egy alapértelmezett közvetlen kiszállítási raktár kiválasztásával beállíthatja egy cikkhez a közvetlen kiszállítást a kiadott termék alaptermékénél.  
    - Mivel a beszerzési rendelést még nem hozták létre, a Közvetlen kiszállítás állapota „közvetlen kiszállítással”.   
7. Válassza a **Mentés** lehetőséget.
8. Zárja be az oldalakat, és térjen vissza a kezdőlapra.
9. Írja be a keresősávba a következőt: `Direct delivery`.
    - A Közvetlen kiszállítás lap munkaterületként funkcionál, és lehetővé teszi a beszerzési ügynökök számára az összes, közvetlen kiszállításra állított értékesítési rendelés áttekintését, így lehetővé teszi számukra, hogy létrehozzák a megfelelő beszerzési rendeléseket. Továbbá a Visszaigazolás és Kiszállítás lapokon megtekinthetik a nyitott közvetlen kiszállítású rendeléseket és a visszaigazolt rendeléseket.  
    - Miután létrehozott egy közvetlen kiszállítású rendelést, automatikusan a Visszaigazolás lapra került. Közvetlenül erről a lapról is megerősítheti a rendelést. Amint megtörténik a beszerzés megerősítése, automatikusan átkerül a Szállítás lapra, ahonnan nyilvántartásba vehető a bevételezése.  

