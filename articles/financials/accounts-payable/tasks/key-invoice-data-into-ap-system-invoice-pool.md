--- 
title: "A legfontosabb számlaadatok a kötelezettségkezelési rendszerbe számlagyűjtő használatával"
description: "Ez a feladat-útmutató bemutatja, hogy hogyan tud számlákat hozni létre a számlajegyzék segítségével."
author: abruer
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 96040b1c1ba130f773ba0defbf7bf1dcebedfc13
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="key-invoice-data-into-the-ap-system-using-invoice-pool"></a>A legfontosabb számlaadatok a kötelezettségkezelési rendszerbe számlagyűjtő használatával

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez a feladat-útmutató bemutatja, hogy hogyan tud számlákat hozni létre a számlajegyzék segítségével.  Ezután egyeztesse a számlát egy beszerzési rendeléssel a számlagyűjtő segítségével, majd véglegesítse a költséget a szállítói számla oldalon.


## <a name="create-a-purchase-order"></a>Beszerzési rendelés létrehozása
1. Nyissa meg a következőt: Kötelezettségek > Beszerzési rendelések > Beszerzési rendelések.
2. Új beszerzési rendelés létrehozásához kattintson az Új lehetőségre.
3. A Szállítói számla mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
4. Válasszon ki a listából a szállítót. Például a 1001-es szállítót.
5. Kattintson az OK gombra.
6. A Cikkszám mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
7. A listából keresse ki a szolgáltatási cikkszámot. Válassza, például az S0001-t.
8. Kattintson a cikkszámra, majd válassza ki azt.
    * A nettó összeg 75,00.  Ezt az összeget szeretnénk viszontlátni a számlán is.  
9. A Művelet panelen kattintson a Beszerzés elemre.
10. Kattintson a Megerősítés gombra.

## <a name="create-and-post-and-invoice"></a>Számla létrehozása és feladása
1. Ugorjon a Kötelezettségek > Számlák > Számlajegyzék elemre.
2. Kattintson az Új lehetőségre.
3. Nyissa meg a keresőlistát a használni kívánt számlajegyzék nevének kiválasztásához.
4. Válassza ki a használni kívánt számlajegyzék nevét.
5. Kattintson a Sorokra a jegyzék megnyitásához, adjon meg költségsorokat.
6. A keresőben válasszon egy szállítót. Például, kattintson a 1001 szállító lehetőségre.
7. A Számla mezőben adja meg a számlaszámot.
8. Írjon egy értéket a „Leírás” mezőbe.
9. A Hitelkeret mezőben adjon meg egy számot.
10. A Beszerzési rendelés mezőben kattintson a legördülő gombra a keresőlista megnyitásához.
11. Válassza ki a korábban létrehozott beszerzési rendelést.
12. A Jóváhagyó mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
13. Jelöljön ki egy jóváhagyót és kattintson a Kijelölés gombra a jóváhagyó kiválasztásához.
14. Kattintson a Feladás lehetőségre.
15. Zárja be az űrlapot.
16. Zárja be az űrlapot.

## <a name="open-an-invoice-from-the-pool-and-match-it-to-a-purchase-order-to-complete-the-invoice-process"></a>A számlafolyamat befejezéséhez nyisson meg egy számlát a gyűjtőből, és válassza ki hozzá a megfelelő beszerzési rendelést.
1. Ugorjon a Kötelezettségek > Számlák > Számlajegyzék elemre.
2. Kattintson a Beszerzési rendelés elemre, ha szállítói számlát kíván létrehozni a számlajegyzékből.
3. Válassza ki a megtekinteni kívánt számlát.
4. Az egyeztetés befejezéséhez kattintson az Egyeztetési állapot frissítése elemre.
5. A Művelet ablaktáblában kattintson a Beállítások elemre.
6. Kattintson a Nézetváltás elemre.
7. Kattintson a Rács nézet elemre.
8. Kattintson a Feladás lehetőségre.
9. Zárja be az űrlapot.
10. Nyissa meg a következőt: Kötelezettségek > Szállítók > Szállítók.
11. Válassza ki a beszerzési rendeléshez tartozó szállítót. Válassza ki például az 1001-es szállítót.
12. A listában kattintson a kijelölt sorban lévő hivatkozásra.
13. A Művelet ablaktáblában kattintson a Szállító elemre.
14. Kattintson a Tranzakciók elemre.
15. Válassza ki a létrehozott számlát.
    * A számlajegyzék-elhatárolás sztornírozásra, illetve a megfelelő költségszámlára feladásra került.  


