---
title: Műveletkeresés
description: Ez a cikk a művelet keresési funkciót ismerteti. A műveletkeresés segít megkeresni és adott lapon lefuttatni műveleteket.
author: jasongre
manager: AnnBe
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 62303
ms.assetid: 62c70de0-fdde-4417-8e08-0583fb095a40
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d01247aa356625cb759306e5ead2afd3cdeb840f
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2191316"
---
# <a name="action-search"></a>Műveletkeresés

[!include [banner](../includes/banner.md)]

Ez a cikk a művelet keresési funkciót ismerteti. A műveletkeresés segít megkeresni és adott lapon lefuttatni műveleteket.

## <a name="introduction"></a>Bevezetés

Az oldalakon az utasítások elsősorban a műveletpaneleken láthatók, egyrészt az oldal tetején megjelenő normál műveletpanelen, és az oldal különböző szakaszaiban megjelenő eszköztárakon. A korábbi verziókban a billentyűtippek szolgáltatás lehetővé tette a műveletpanel bármely gombjának gyors elérését az Alt billentyű, majd egy betűsorozat lenyomásával.

[![keyTipsAX6](./media/keytipsax6.png)](./media/keytipsax6.png)

A billentyűparancs-tippek már nem érhetők el, de a műveletkeresés funkció helyettesíti. Ez az új funkció lehetővé teszi, hogy gyorsan megkeressen és működtessen egy gombot bármelyik látható műveleti ablaktáblán.

## <a name="using-action-search"></a>A műveletkeresés használatával

A műveletkeresési funkció használatához kövesse az alábbi lépéseket.

1. A műveleti ablaktáblán kattintson a **műveletkeresés** mezőbe. (A **műveletkeresés** mező egy nagyítóüveget ábrázoló ikont tartalmaz.)
2. Írja be a futtatni kívánt gomb nevének egy részét vagy egészét. Emellett kereshet a gomb „elérési útját” alkotó szavak használatával is. (További információért lásd a cikk következő részét.) Általában kettő vagy négy karakter beírása után megjelenik egy gomb az eredménylista felső részén.
3. Keresse meg és futtassa a gombot a találati listában (egér vagy billentyűzet segítségével).

A gomb futtatása után a fókusz visszakerül az utolsó pozícióra az oldalon, így tovább dolgozhat.

[![műveletkeresési mező](./media/action-search-field.png)](./media/action-search-field.png)

A Ctrl+/ vagy az Alt+Q billentyűkombinációkkal is elindíthatja a műveletkeresést. Nyomja le a billentyűparancsot ismét, hogy visszatérjen a fókusz az utolsó pozícióra az oldalon.

## <a name="understanding-the-results-list"></a>Az eredménylista ismertetése

Gyakran a gomb helyét és környezetét is ismernünk kell ahhoz, hogy teljesen átlássuk a gomb funkcióját. Ezért az eredménylistában minden elemnél további információk is láthatók, amelyek segítenek megérteni, pontosan mely gombok láthatók a listában. Főként a gomb „elérési útja” jelenik meg. Az elérési út a felhasználói felület következő elemeihez tartozó címkéket tartalmazhatja lényegesként:

- Műveleti ablaktábla lap
- Gombcsoport
- Menügomb (ha a gomb menügombon belül található)
- Menüelválasztó (ha a gomb egy névvel ellátott csoporton belül található egy menügombban)
- Csoport vagy a lap az oldalon (például egy gyorslap neve)

Például beírta, hogy **össz** a **műveletkeresés** mezőbe, és most az eredménylistát nézi. Az első tétel az **Összesen** nevű gombnál ki van emelve. A gomb **Értékesítési rendelés** &gt; **Nézet** elérési útja is látható. Az elérési út **Értékesítési rendelés** része felel meg az **Értékesítési rendelés** lapnak a Művelet ablakban, és az elérési út **Megtekintés** része felel meg a **Megtekintés** csoportnak a lapon. Hasonlóan az elérési útja az **Összengedmény** gombnak (**Értékesítés**&gt;**Számítás**) ad tájékoztatást arról, hogy ez a gomb a **Számítás** csoportban az **Értékesítés** lapon található a Művelet ablakban. Tehát ez az információ segít megérteni, pontosan melyik gomb aktiválódik a műveletkeresés hatására (ha az eredménylistában az adott gombot választja).

[![műveletkeresési mező adatokkal](./media/action-search-field-with-data.png)](./media/action-search-field-with-data.png)

Az előző példában a műveletkeresési funkció az oldal tetején található normál Műveleti ablaktáblából mutatott eredményeket. A műveletkeresés azonban az oldal más területein található, látható eszköztárakból is jelenít meg eredményeket. Például az **Aktuális készlet** gombot keresi, amely az **Értékesítési rendelés sorai** gyorslapon található. Ebben az esetben az eredménylistában látható gombelérési út (**Értékesítési rendelés sorai** &gt; **Készlet** &gt; **Nézet**) arról tájékoztat, hogy ez a gomb a **Készlet** menügomb **Nézet** fejlécében található az **Értékesítési rendelés sorai** gyorslapon.

[![aktuális készlet](./media/on-hand-inventory.png)](./media/on-hand-inventory.png)

## <a name="action-search-vs-navigation-search"></a>Műveletkeresés és navigációs keresés

A műveletkereséssel műveletek kereshetők meg és futtathatók egy oldalon. Emellett van egy másik keresési funkció is, amellyel oldalak kereshetők és nyithatók meg. Ezen funkcióval kapcsolatos további információk a [Navigációs keresés](navigation-search.md) cikkben találhatók.
