--- 
title: "Áfa-hozzárendelés és felülbírálások"
description: "Ez az eljárás bemutatja, hogyan lehet áfacsoportokat társítani kiskereskedelmi csatornákhoz."
author: mkirknel
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 816e00e4238cb0d90a2aea9b2bc070d31504c2ce
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="sales-tax-assignment-and-overrides"></a>Áfa-hozzárendelés és felülbírálások

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogyan lehet áfacsoportokat társítani kiskereskedelmi csatornákhoz. Emellett az új áfafelülírás létrehozásának és annak meglévő áfafelülírás csoporthoz rendelésének folyamatán is végig vezet. Az eljárás

az USRT cég adatait használja, mint bemutatóadatokat.

1. Nyissa meg a következőt: Kiskereskedelem és kereskedelem > Csatornák > Kiskereskedelmi áruházak > Minden kiskereskedelmi üzlet.
2. A listában kattintson a „Houston”-hoz tartozó Kiskereskedelmi csatorna azonosítóra.
3. Kattintson a Szerkesztés lehetőségre.
    * Az „Áfa csoport” mező tartalmazza az aktuális céghez kapcsolódó áfa csoportok listáját. Az aktuálisan hozzárendelt csoport egy általános „Texas” áfacsoport. Vannak áfacsoportok „Washington”-hoz és „Washington, King County”-hoz is. Az áfacsoportok több közigazgatási terület adóit is tartalmazhatják.  
    * Az „Áfa felülírás” mező az, ahol az áfa-felülírási csoport csatornához rendelhető. Az áfa-felülírási csoportok használhatók olyan áfafelülírások csoportosítására, amik több üzletre vonatkoznak. Ahelyett hogy egyesével, manuálisan rendelné össze az áfafelülírásokat, létrehozhat egy csoportot, amit közvetlenül a csatornákhoz rendelhet, így időt takaríthat meg.  
4. Kattintson a Mentés gombra.
5. Zárja be a lapot.
6. Menjen a Kiskereskedelmi és kereskedelem > Csatorna-beállítás > Forgalmi adók > Áfafelülírások lehetőségre.
7. Kattintson az Új lehetőségre.
8. Az Áfafelülírás mezőbe írja be az ön felülírásának nevét.
9. a Leírása mezőbe adja meg a felülírás leírását.
10. Állítsa az állapotot „Engedélyezett”-re.
11. Bontsa ki vagy zárja be Felülírás részt.
12. A Típus mezőben válasszon ki egy lehetőséget.
    * A cikkek áfa csoportjai használhatóak konkrét cikkek áfáinak felülírásához, amennyiben azok a csoportba tartoznak. Például, az élelmiszerek tipikusan eltérő áfával rendelkeznek a fizikai árukhoz képest, így valószínűleg érdemes saját áfacsoportba sorolni őket.     Az áfacsoportok adók csoportjai, amely az adott csatornára használhatóak. Ha például a csatorna értékesít kiskereskedelemben és vállalkozástól-vállalkozásnak is, akkor különböző cikkáfacsoportok használhatóak. Minden alkalmazható adót az áfacsoporthoz kell rendelni.  
    * Most kiválaszthatja a „Kezdő” és „Végző” adókat vagy kiválaszthatja a „Adócsoportból” és „Adócsoportig”, hogy létrehozza az ön adófelülírását.    A "Kezdő" mező mutatja a felülírandó adót vagy adócsoportot. A Cikk áfacsoport szerinti felülírás eltérő lehetőségeket biztosít, az áfacsoporttal történő felülíráshoz képest.    A Áfafelülírások beállíthatók egész tranzakciók áfa felülírására, vagy a tranzakció megadott soraira.  
13. Kattintson a Mentés gombra.
14. Zárja be a lapot.
15. Menjen a Kiskereskedelmi és kereskedelem > Csatorna-beállítás > Forgalmi adók > Áfafelülírás csoportok lehetőségre.
    * Ebben a lépésben az újonnan létrehozott áfafelülírást fogja hozzárendelni a Houston csatornához rendelt áfa-felülírási csoporthoz.  
16. Kattintson a Szerkesztés lehetőségre.
17. Bontsa ki vagy csukja össze a Beállítás szakaszt.
18. Kattintson a Hozzáadás gombra.
19. Az Áfacsoport felülírás mezőben kattintson a legördítő gombra a keresőlista megnyitásához.
20. Válassza ki a korábban létrehozott áfafelülírást a listából.
21. A listában kattintson a kijelölt sorban lévő hivatkozásra.
22. Kattintson a Mentés gombra.


