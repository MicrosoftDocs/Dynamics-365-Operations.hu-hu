---
title: "Műveletkeresés"
description: "A cikk ismerteti a Microsoft Dynamics 365 műveletek művelet keresési funkciók. A keresési művelet segít keresés és a weblapon futó műveletek."
author: jasongre
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 62303
ms.assetid: 62c70de0-fdde-4417-8e08-0583fb095a40
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4bb647cfd3f012efbffa93a81462c538a24ac850
ms.openlocfilehash: 689d8f9fb0501c5007db21d41f126737af77b89e
ms.lasthandoff: 03/31/2017


---

# <a name="action-search"></a>Műveletkeresés

A cikk ismerteti a Microsoft Dynamics 365 műveletek művelet keresési funkciók. A keresési művelet segít keresés és a weblapon futó műveletek.

<a name="introduction"></a>Bevezetés
------------

Microsoft Dynamics 365 műveletek oldalak elsősorban munkaablakainak szabvány műveleti ablaktábla az oldal tetején megjelenő és a különböző szakaszaiban a lapon megjelenő eszköztárak parancsai teszik ki. A korábbi verziókban a kulcs tippek szolgáltatás lehetővé teszi a gyors eléréséhez nyomja meg az Alt billentyűt, majd a betű sorozata meg egy műveletpanel. 

[![keyTipsAX6](./media/keytipsax6.png)](./media/keytipsax6.png) azonban Dynamics 365 műveletekhez aktuális verziójában kulcs tippek többé nem elérhetők, de a művelet keresés funkció váltotta. Ez az új funkció lehetővé teszi, hogy gyorsan megkeressen és működtessen egy gombot bármelyik látható műveleti ablaktáblán.

## <a name="using-action-search"></a>A műveletkeresés használatával
A műveletkeresési funkció használatához kövesse az alábbi lépéseket.

1.  A műveleti ablaktáblán kattintson a **műveletkeresés** mezőbe. (A **műveletkeresés** mező egy nagyítóüveget ábrázoló ikont tartalmaz.)
2.  Írja be a futtatni kívánt gomb nevét egy részét vagy egészét. A gomb "elérési." szavak használatával is kereshet (További információért lásd a cikk következő része.) Általában egy gomb jelenik meg az eredménylistában felső kettő vagy négy karakter beírása után.
3.  Keresse meg és futtassa a gombot a találati listában (egér vagy billentyűzet segítségével).

A gomb futtatása után a fókusz visszakerül az utolsó pozícióra az oldalon, így tovább dolgozhat. 

[![a mező keresési művelet](./media/action-search-field.png)](./media/action-search-field.png)

A Ctrl+/ vagy az Alt+Q billentyűkombinációkkal is elindíthatja a műveletkeresést. Nyomja le a billentyűparancsot ismét, hogy visszatérjen a fókusz az utolsó pozícióra az oldalon.

## <a name="understanding-the-results-list"></a>Az eredménylista ismertetése
Gyakran műveletek 365 Dynamics, ismernie kell a hely és a keretein belül teljes mértékben tisztában van az a célja, hogy a gomb gomb. Ezért további információ jelenik meg minden egyes cikkhez az eredménylistában, megértéséhez pontosan mely gombok jelennek meg a listában. Főként a gomb „elérési útja” jelenik meg. Az elérési út a felhasználói felület következő elemeihez tartozó címkéket tartalmazhatja lényegesként:

-   Műveleti ablaktábla lap
-   Gombcsoport
-   Menügomb (ha a gomb menügombon belül található)
-   Menüelválasztó (ha a gomb egy névvel ellátott csoporton belül található egy menügombban)
-   Csoport vagy a lap az oldalon (például egy gyorslap neve)

Például beírta, hogy **össz** a **műveletkeresés** mezőbe, és most az eredménylistát nézi. Az első tételt a gomb neve **összesen**, ki van emelve. A gomb elérési útját **eladási rendelés**&gt;**nézet** is megjelennek. A **az eladási rendelés** felel meg az elérési út egy részét a **az eladási rendelés** lapon kattintson a műveletek ablaktábla és a **nézet** megfelel az elérési út egy részét a **nézet** csoport lapon. Hasonlóan, az útvonal a **Összengedmény** gomb (**eladni**&gt;**számítás**) tájékoztat arról, hogy ez a gomb található a **számítás** csoport a **eladni** lapján, a műveletek ablaktábla. Ezért ez az információ segít megérteni, pontosan melyik gomb által kiváltott műveletet keresés (ha az eredménylistában gombot választja). 

[![művelet-keresési mező-a-adatok](./media/action-search-field-with-data.png)](./media/action-search-field-with-data.png) 

Az előző példában a műveletkeresési funkció az oldal tetején található normál Műveleti ablaktáblából mutatott eredményeket. A műveletkeresés azonban az oldal más területein található, látható eszköztárakból is jelenít meg eredményeket. Például keresett a **az aktuális készlet** található gomb a **értékesítési rendelési sorok** gyorslapra. Ebben az esetben az eredménylistában gomb elérési (**értékesítési rendelési sorok**&gt;**készlet**&gt;**nézet**) tájékoztat arról, hogy ez a gomb alatt található a **nézet** a címsor a **készlet** menu gombjának a **értékesítési rendelési sorok** gyorslapon. 

[![az aktuális készlet](./media/on-hand-inventory.png)](./media/on-hand-inventory.png)

## <a name="action-search-vs-navigation-search"></a>Műveletkeresés és navigációs keresés
Keresse meg és futtassa a műveletek lapon keresési művelet célja, mivel van egy külön keresési mechanizmust keresése és műveletek Dynamics 365 oldalra navigál. A szolgáltatásról további információt talál a [navigációs keresés](navigation-search.md) cikk.


