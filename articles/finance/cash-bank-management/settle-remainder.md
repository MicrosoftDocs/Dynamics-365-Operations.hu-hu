---
title: Hátralék kiegyenlítése
description: Egy kiegyenlítési tevékenységből maradt összeget úgy egyenlíthet ki, hogy azt a főkönyvi számlához rendeli.
author: angelad116
ms.date: 02/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym, LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2018-12-01
ms.dyn365.ops.version: 8.1.3
ms.openlocfilehash: 1b50098470cfa070a6c430e65f2fa24317c14b97
ms.sourcegitcommit: 0b7a034e644f4d93fe55c7baca5a3f89dbe56898
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/14/2022
ms.locfileid: "9151181"
---
# <a name="settle-remainder"></a>Hátralék kiegyenlítése

[!include [banner](../includes/banner.md)]

Egy kiegyenlítési tevékenységből maradt összeget úgy egyenlíthet ki, hogy azt a főkönyvi számlához vagy egy másik ügyfélhez rendeli. A fennmaradó összegeket kiegyenlítheti amikor egy naplóba vezetett összegeket egyenlít ki, vagy amikor csak nyitott tranzakciókat egyenlít ki.

## <a name="setting-up-defaults"></a>Alapértelmezések beállítása 
A Fennmaradó összeget **csak** **akkor lehet használni, ha engedélyezi a Fennmaradó összeget, és be kell állítania az alapértelmezett beállításokat**.

1)  Kattintson a **Kinnlevőségek > Paraméterek > Kiegyenlítések** vagy **Kötelezettségek > Paraméterek > Kiegyenlítések** lehetőségre
2)  Válassza a Kiegyenlítés **lapot**, és kattintson a Fennmaradó kiegyenlítésének **engedélyezése elemre**.
3)  Az **Alapértelmezett okkód** helyen válassza ki az alapértelmezett okkódot. Az okkódoknak már be kell lennie állítva **Kinnlevőségek > Beállítás > Vevői leírási okkódok** vagy **Kötelezettségek > Beállítás > Vevői leírási okkódok** helyen. A **Hátralékszámlák alapértelmezett kiegyenlítése** alapértelmezetten ahhoz a számlához lesz rendelve, amelyik a leírási okkódhoz van rendelve.
3)  Frissítse a **Hátralékszámlák alapértelmezett kiegyenlítése** elemet szükség szerint.
4)  Az Alapértelmezett **naplónév mezőben** válassza ki azt a kifizetési naplót, amely akkor használatos, ha csak nyitott tranzakciókkal szeretne kifizetési naplót létrehozni. A fennmaradó hátralék kiegyenlítése funkció engedélyezése esetén hozzá kell adnia egy alapértelmezett naplónevet.

## <a name="settle-remainder-from-a-journal"></a>Hátralék kiegyenlítése naplóból
Ha nem engedélyezi a **Hátralék kiegyenlítése** funkciót, akkor is bevihet egy tranzakciót a naplóba, és kiegyenlíthet ezzel szemben tranzakciókat, ahogy korábban is. Amikor rákattint az **OK** gombra, a nyitott egyenleg a számlán a pénzfizetés összegével csökken. Ha pénzösszeg nem egyenlíti ki teljesen a számlát, a számla nyitott a fennmaradó összeg egy későbbi időpontban történő kiegyenlítéséig.

Ha a **Hátralék kiegyenlítése** funkció engedélyezve van, a fennmaradó összeget egy főkönyvi számlára lehet kiegyenlíteni. A hátralékot egy másik vevői számlára (a vevői tranzakciók esetében) is átviheti, vagy egy másik szállítóhoz (szállító tranzakciók esetében), ahelyett, hogy a számlákat nyitva hagyná. 

A hátralék kiegyenlítéséhez a **Kiegyenlítés** oldalról, tegye a következőket:

1)  A **Kiegyenlítés** oldalon jelölje meg a számlákat vagy tranzakciókat, amelyeket ki szeretne egyenlíteni.
2)  Kattintson a **Hátralék kiegyenlítése** gombra.
3)  A párbeszédpanelen jelenik meg, a főkönyvi számla ellenében kiegyenlítendő összeggel, a hátralék kiegyenlítéséhez használt dátummal, az alapértelmezett okkóddal a paraméterekhez és az alapértelmezett számlával a paraméterekből. 
4)  Ha meg szeretné változtatni az alapértelmezett okot válasszon egy új kiegyenlítési okot. A kiegyenlítési számla módosítva lesz az okkódhoz társított számlára.
5)  Ha módosítani szeretné, szerkessze a kiegyenlítési számlát.
6)  Ha vevői tranzakciókat egyenlít ki, és a fennmaradó összeget egy másik vevőhöz szeretné átvinni, válasszon ki egy vevőt a **Vevői számlával szembeni hátralék kiegyenlítése** menüben. Ha beszállítói tranzakciókat egyenlít ki, és a fennmaradó összeget egy másik szállítóhoz szeretné átvinni, válasszon ki egy szállítót a **Szállítói számlával szembeni hátralék kiegyenlítése** menüben.
6)  Kattintson a **Hátralék kiegyenlítése** elemre.
7)  A **Napló** lap jelenik meg. Egy további naplósor hozzáadódik a naplóhoz, a kiegyenlített hátralék összegével összegként, illetve a hátralék kiegyenlítésének számlájával ellenszámlaként. Ha hozzáadott egy vevőt vagy szállítót, hogy a kiegyenlítésiösszeget egy másik vevőhöz vagy szállítóhoz helyezze át, egy további sor lesz hozzáadva a naplóhoz, hogy a kiegyenlítési összeg a vevőhöz vagy beszállítóhoz legyen áthelyezve.

A napló feladásakor a nyitott tranzakció teljesen ki lesz egyenlítve. 

## <a name="settle-remainder-when-you-are-only-settling-open-transactions"></a>Hátralék kiegyenlítése, ha csak nyitott tranzakciókat egyenlít ki
A hátralékot akkor is kiegyenlítheti, amikor nyitott tranzakciókat egyenlít ki napló nélkül.

A hátralék kiegyenlítéséhez tegye a következőket:

1)  A **Kiegyenlítés** oldalon jelölje meg a számlákat vagy tranzakciókat, amelyeket ki szeretne egyenlíteni.
2)  Kattintson a Fennmaradói **egyenlítés gombra**.
3)  A párbeszédpanelen jelenik meg, a főkönyvi számla ellenében kiegyenlítendő összeggel, a hátralék kiegyenlítéséhez használt dátummal, az alapértelmezett okkóddal a paraméterekhez és az alapértelmezett számlával a paraméterekből. 
4)  Ha meg szeretné változtatni az alapértelmezett okot válasszon egy új kiegyenlítési okot. A kiegyenlítési számla módosítva lesz az okkódhoz társított számlára.
5)  Ha módosítani szeretné a **kiegyenlítési számlát**, szerkessze a kiegyenlítési számlát.
6)  Ha vevői tranzakciókat egyenlít ki, és a fennmaradó összeget egy másik vevőhöz szeretné átvinni, válasszon ki egy vevőt a **Vevői számlával szembeni hátralék kiegyenlítése** menüben. Ha beszállítói tranzakciókat egyenlít ki, és a fennmaradó összeget egy másik szállítóhoz szeretné átvinni, válasszon ki egy szállítót a **Szállítói számlával szembeni hátralék kiegyenlítése** menüben
7)  Azt is teheti, hogy kifizetési naplót hoz létre a kiegyenlített hátralékkal, vagy napló nélkül is beküldheti. Válassza ki **Igen** lehetőséget a **Szerkesztés naplóban** menüben kifizetési napló létrehozásához. A létrehozott kifizetési naplót szerkeszteni is lehet.
8)  Kattintson a **Hátralék kiegyenlítése** elemre. Ha azt választotta, hogy hozzon létre egy naplót, a gomb módosul a **Napló létrehozása** értékre. Ehelyett kattintson a **Napló létrehozása** gombra.
9)  Ha egy kifizetési naplót hozott létre, a napló oldal nyílik meg, miután a **Hátralék kiegyenlítése** lehetőségre kattint. Egy naplósor hozzáadódik a naplóhoz, a kiegyenlített hátralék összegével összegként, illetve a hátralék kiegyenlítésének számlájával ellenszámlaként. Ha hozzáadott egy vevőt vagy szállítót, hogy a kiegyenlítésiösszeget egy másik vevőhöz vagy szállítóhoz helyezze át, egy további sor lesz hozzáadva a naplóhoz, hogy a kiegyenlítési összeg a vevőhöz vagy beszállítóhoz legyen áthelyezve.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
