---
title: "Hibrid vevői rendelések"
description: "A hibrid vevői rendelés egy lehet egyetlen rendelés, amely tartalmazza az ügyfél által végezhető ki az üzlet termékek, valamint a felvételre, vagy később szállított termékek."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 261164
ms.assetid: 9d99a5b9-4662-499a-bece-3ea1d6092934
ms.search.region: global
ms.search.industry: Retail
ms.author: anpurush
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 1ddfc050cef94f4a31f5858b84c89eadfa726b95
ms.lasthandoff: 03/31/2017


---

# <a name="hybrid-customer-orders"></a>Hibrid vevői rendelések

A hibrid vevői rendelés egy lehet egyetlen rendelés, amely tartalmazza az ügyfél által végezhető ki az üzlet termékek, valamint a felvételre, vagy később szállított termékek.

A Microsoft Dynamics 365 - műveletekhez kiskereskedelmi, választhat vagy elvégzi az összes termék, vagy végezzük el a kijelölt termékek vevői rendeléshez. Megjelölt sorok szerint végezzük el automatikusan számlázása a rendelés létrehozása után a termék hasonlóképpen ez megegyezik a kell kitárolni felfelé a rendelés létrehozása után a rendelés. Az esedékes összeget a hibrid rendelések hozzáadásával, a letéti százalékos a kivételezési és szállítási termék sorokat a végrehajtandó sorok teljes összegét meghatározni. A hibrid rendelések esetén a rendszer felváltva megjeleníti vevői rendelés és átvétel és fizetés helyben mód az alábbiak szerint:

-   Ha a bevásárlókosárban található összes termék **végez a szállítási**, a rendelés Cash and Carry tranzakcióként fogja kezelni.
-   Ha bármely vagy összes kosár sorai vannak beállítva, vagy **kiválasztása** vagy **hajó szállítási**, a rendelés vevői rendelés tranzakcióként fogja kezelni.

Ha be van jelölve a Bevásárlókocsi sora és a **kijelölt kitárolása**, **a kijelölt hajó**, vagy **végrehajtására kijelölt** van jelölve, csak az adott Bevásárlókocsi sora van beállítva, hogy a szállítási móddal. Ebben az esetben a lefelé irányuló folyamat, a művelet a szokásos módon folytatódik. Azonban ha **kijelölt kitárolása**, **a kijelölt hajó**, vagy **végrehajtására kijelölt** bevásárlókocsi vonallal jelölve, egy új lap megnyitása, amely felsorolja a bevásárlókocsi-sorok nélkül van kijelölve. Ezen a képernyőn több sort egyszerre a kézbesítési mód beállítás közül választhat. Ez a módszer használatakor a sor kijelölése minden korábbi kézbesítési mód a sorhoz rendelt felül lesz írva.

<a name="see-also"></a>Lásd még
--------

[Vevői rendelések áttekintése](customer-orders-overview.md)


