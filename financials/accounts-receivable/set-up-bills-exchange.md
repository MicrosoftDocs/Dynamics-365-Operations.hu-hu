---
title: "Váltók beállítása"
description: "Ez a témakör ismerteti a váltók beállításának lépéseit."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 269964
ms.assetid: f2077165-da90-4359-ab12-e05717728dc7
ms.search.region: global
ms.author: abruer
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: ce2142d946085d8bfc577accf1bb31a89ea29156
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-bills-of-exchange"></a>Váltók beállítása

Ez a témakör ismerteti a váltók beállításának lépéseit.

Váltó egy írásos vagy elektronikus utasítás, amely meghatározza, hogy egy másik fél, általában egy bank egy meghatározott összeget kell fizetnie a vállalat egy vevőtől. Ha a szabad szöveges számla vagy értékesítési rendelési számla kiegyenlítésére váltót használnak, akkor a vevő számláján egy követel tétel jelenik meg. A váltó mindaddig biztosítja ezt a követel tételt, amíg a vevő ki nem fizeti a váltót a banknak. Az esedékességi napon általában fog egyenlítse ki a számlát a váltó. Amint a vállalat megkapja a banktól az értesítés, hogy a váltón megadott összeget kifizették, le lehet zárni a váltót. Váltó rajzolhat, keresztül a bankhoz, vagy a következő alkalmakkor:

-   Az esedékesség napján. Ez a megközelítés a gyűjteményhez átutalt nevezik.
-   A határidő előtt, a megadott vevő beállított fizetési feltételek engedmény dátumának általában a. A tranzakció feladásakor az engedmény összege egy költségszámlára küldhető el. A fennmaradó összeg az Ön kötelezettsége, amíg a bank meg nem kapja a fizetést a vevőtől. Ez a megközelítés az engedményhez átutalt nevezik.

## <a name="set-up-posting-profiles-for-bills-of-exchange"></a>Feladási profilok beállítása váltókhoz
Használja a **vevői feladási profilok** lapon állíthatja be a feladási profilok, váltók, váltók elutasítása, a fizetési átutalások és átutalások engedmény használata. A a **az összegző számla** mezőben, jelölje be az összesítő váltó összegek könyveléséhez. Erre a számlára terhelt vagy követel tételként váltótranzakció típusától függően:
-   A váltók a számlán a váltó feladása, és az átutalás az engedményhez vagy átutalás a gyűjteményhez feladása alkalmával követel.
-   Az óvatolt váltók esetén az óvatolt váltó feladásakor ezen a számlán egy tartozik tétel jelenik meg.
-   A beszedések esetén a beszedés feladásakor ezen a számlán egy tartozik tétel jelenik meg.
-   Az engedményes beszedések esetén az engedményes beszedés feladásakor ezen a számlán egy tartozik tétel jelenik meg.

A a **számla kiegyenlítése** mezőben, jelölje be a készpénzszámla váltó összegek könyveléséhez. A váltók kiegyenlítésekor ezen a számlán egy tartozik tétel jelenik meg. A a **Áfaelőlegek** mezőben, jelölje be az összesítő számla előlegek váltók használatakor az áfaösszegek feladása. A a **kötelezettségek az** mezőben, jelölje be a számla könyvelése az átutalások az engedmény az engedmény összegét. Ezen a számlán az engedményes beszedés feladásakor egy követel tétel jelenik meg.

## <a name="set-up-accounts-receivable-parameters-for-bills-of-exchange"></a>Számla váltókhoz Kinnlevőségek paramétereinek beállítása
A a **Kinnlevőségek paraméterei** oldalon, a feladási profiloknak, a váltók megadott alapértelmezett a **Főkönyv és áfa** fülre. Számsorozatok meg vannak adva a **Number sequences** fülre.
Váltónaplók neveinek beállítása
------------------------------------------

A a **naplónevei** hozza létre a váltók használatához legalább öt naplóneveket. Az alábbiakban a naplótípusok:
-   **Vevői váltókiállítás** – létrehozása a váltó napló napló nevét.
-   **Vevői váltóóvatolás** – hozzon létre egy naplónevet váltó napló elutasítása.
-   **Vevői váltó** – a napló nevét, a újbóli váltókiállítási napló létrehozása.
-   **Vevő-banki utalás** – hozzon létre egy naplónevet az átutalási napló.
-   **Vevői kiegyenlítési váltó** – hozzon létre egy naplónevet a kiegyenlítési váltó napló.

Minden napló napló bizonylat lapon adja meg a váltó információt a **váltó** fülre. A váltó naplósorokat a könyvelés után megtekintheti azokat a **Váltónapló lekérdezésének** lap és a **Váltóstatisztika** oldalon.
Váltók kifizetési módjainak beállítása
-----------------------------------------------

A a **fizetési módok** váltók legalább egy fizetési mód beállítása lapon. Ha több, mint egy bank, egy, amely megfelel az átutalás formátumaként váltók igénylő minden banki fizetési mód beállítása.
Váltók kifizetési díjainak beállítása
-----------------------------------------

A kifizetési díj a kifizetések vevőktől való beszedéséért fizetendő díj. Lehetnek több kifizetési díjak beállításában tartozó minden egyes kifizetés díja. Sorok beállítása segítségével szabályozhatja az alapértelmezett kifizetési díjak összegei kiszámítási módját. Például létrehozhat beállítási sorokat fizetési módokhoz, kifizetési előírásokhoz, pénznemekhez és időszakokhoz. Naponként alapját képező összeg vagy százalékos sorok is létrehozhat. Például akkor állítsa be egy Kamatszázalék fizetés lejárt az idő alapján. Ha a banki díjai eltérő díjakat a különböző átutalási típusokra, például a **gyűjtemény** vagy **engedmény**, hozzon létre egy külön fizetési díj sort az egyes átutalási.
Átutalási díjak beállítása banki átutalási fájlokhoz
------------------------------------------------

A a **bankszámlák** lapon beállíthat átutalási díjak, hogy a bank minden generált átutalási fájl. Az átutalási díjak feladása akkor történik meg, amikor a bank visszaigazolta az átutalást, és a díj realizált összege ismertté válik. Átutalási díjak, vevőktől beszedett és naplósorokhoz kapcsolódó kifizetési díjak különböznek.
Váltódokumentumok elrendezésének beállítása
---------------------------------------------

A a **bankszámlák** lap **meg**, és adja meg a dokumentum elrendezését, amely a dokumentumok minden bankszámla, hogy a nyomtatott anyagjegyzékekkel létrehozza az.
A váltók beállítása a vevőknél
--------------------------------------

A a **vevők** lap, minden egyes vevőhöz, aki vállalta, hogy a váltó használatával állíthat be egy alapértelmezett fizetési módot váltók meg a **Fizetés alapértelmezései** fülre.




