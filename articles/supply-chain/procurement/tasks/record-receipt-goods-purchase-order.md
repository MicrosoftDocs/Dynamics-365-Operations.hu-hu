--- 
title: "Az áruk bevételezésének rögzítése a beszerzési rendelésen"
description: "Ez az eljárás bemutatja Önnek, hogyan rögzíthet árubeérkezést közvetlenül egy beszerzési rendelésre."
author: FrankDahl
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, PurchEditLines
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 9b2300a593c9e153ee598fa72e29907c82f2b79e
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="record-the-receipt-of-goods-on-the-purchase-order"></a>Az áruk bevételezésének rögzítése a beszerzési rendelésen

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja Önnek, hogyan rögzíthet árubeérkezést közvetlenül egy beszerzési rendelésre. Ezen kívül lehetséges az is, hogy rögzítsen árubeérkezést a raktárban, amit majd később rögzíthet a beszerzési rendelésre. A feladatot általában a beszerzési ügynök, vagy a fizetendő számla koordinátor végzi el. Az útmutatóban mutatott példa használható az USMF demo adatok cégben. A példa tartalmazza az egyszerű beszerzési rendelés létrehozásához szükséges lépéseket, így feladat segédletként használhatja a folyamat során. Ha az eljárás alatt a saját adatait használta, az Árubeérkeztetés részfeladattal kellett volna kezdenie.


## <a name="prepare-a-new-purchase-order-for-receipt-of-goods"></a>Új beszerzési rendelés készítése áru bevételezéshez
1. Ugorjon a Beszerzés és forrás > Beszerzési rendelés > Összes beszerzési rendelés pontra.
2. Kattintson az Új lehetőségre.
3. Írja be az „IS-101” értéket a Szállítói számla mezőbe.
4. Kattintson az OK gombra.
5. Adja meg a „M0001” értéket a Cikkszám mezőben.
6. Adja meg az „5” értéket a Mennyiség mezőbe.
7. A Művelet panelen kattintson a Beszerzés elemre.
8. Kattintson a Megerősítés gombra.

## <a name="record-receipt-of-goods"></a>Áruk bevételezésének rögzítése
1. A Művelet panelen kattintson a Bevételezés elemre.
2. Kattintson a Termékbevételezés elemre.
    * A Mennyiség mező segítségével kiválaszthat különböző lehetőségeket ahhoz a mennyiséghez, amelyet szeretne beérkeztetni. Például, ha a mennyiség korábban már regisztrálva lett a raktárban, akkor kiválaszthatja, hogy ez Regisztrált mennyiség.  Ebben a példában használja a Rendelt mennyiséget.   
3. Írjon be egy értéket a Termék bevételezés mezőbe.
    * Ezzel a mezővel lehet megadni olyan hivatkozást, ami bizonylatként lesz használva a termék bevételezési naplójához.  
4. Bontsa ki a Sorok szakaszt.
5. Állítsa a mennyiséget 4 értékre.
    * Itt is manuálisan adhatja meg a mennyiséget, ami a rendelés minden sorához tartozó bevételezett mennyiség.  
6. Csukja össze Sorok szakaszt.
7. Kattintson az OK gombra.
    * Az áruk most már beérkezettként szerepelnek a beszerzési rendelésen és egy termékbevételezési napló lett létrehozva ennek a dokumentálására. A Termék-bevételezési művelet segítségével áttekintheti a beszerzési rendeléshez létrehozott naplókat, és láthatja, hogy mi érkezett és mikor.  


