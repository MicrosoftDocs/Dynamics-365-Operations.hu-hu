---
title: Lízing feladási számlák beállítása
description: Ez a témakör a lízingtranzakciókhoz szükséges feladási számlákat sorolja fel, és bemutatja, hogyan határozhatja meg a feladási számlákat a Lízing feladási paraméterek lapon.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePostingAccounts
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: d5b97a999f782bd2ed6de0b692edc2f202860354
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2021
ms.locfileid: "5880862"
---
# <a name="set-up-lease-posting-accounts"></a>Lízing feladási számlák beállítása

[!include [banner](../includes/banner.md)]

Ez a témakör a lízingtranzakciókhoz szükséges feladási számlákat sorolja fel, és bemutatja, hogyan határozhatja meg a feladási számlákat a **Lízing feladási paraméterek** lapon.

A 842 (ASC 842) és a nemzetközi pénzügyi beszámolási szabvány 16. (IFRS 16) szerinti számviteli szabványoknak való megfelelésérdekében előfordulhat, hogy számlákat kell létrehoznia a számlatükörben. Az ASC és IFRS szabványoknak való megfelelés érdekében létrehozott fiókok azonban nem rögzített eszközszámlák. Az ASC 842 keretében a használatijog-eszközt (ROU) mind a pénzügyi, mind az operatív lízingek esetében el kell számolni. Ezek a lízingek elkülönülnek a rögzített eszközöktől. (A tárgyi eszközök használatával továbbra is fenntarthatja a ROU-eszközt.)

A fiókstruktúrák létrehozásáról a [Fiókstruktúrák létrehozása](../general-ledger/tasks/create-account-structures.md) című témakörben talál információt. A fő számla létrehozásáról a [Fő számla létrehozása](../general-ledger/tasks/create-main-account.md) című témakörben talál információt.

Az alábbi tábla példákat mutat be a lízingbe adott eszköztranzakciókhoz létrehozni kívánt számlákra, ha még nem hozták létre őket. Az IFRS 16 szerint az operatív lízingkapcsolatokat még mindig alacsony értékű és rövid távú lízingekre használják.

| Főkönyvi számlaszám | Számla típusa  | Számla neve                                          |
|-----------------------|---------------|-------------------------------------------------------|
| 180150                | Eszközök         | Jármű ROU-eszköz                                     |
| 180160                | Eszközök         | ROU-eszköz építése                                    |
| 180250                | Eszközök         | Halmozott értékcsökkenés – járművek                   |
| 180260                | Eszközök         | Halmozott értékcsökkenés – épületek                  |
| 222300                | Kötelezettség     | Rövid lejáratú kötelezettség – pénzügyi lízingek                |
| 222310                | Mérleg | Rövid lejáratú kötelezettség – Operatív lízingek              |
| 250200                | Kötelezettség     | Kötelezvények                                         |
| 250601                | Mérleg | Hosszú lejáratú kötelezettség – pénzügyi lízingek                 |
| 250602                | Mérleg | Hosszú lejáratú kötelezettség – operatív lízingek               |
| 250606                | Mérleg | Halasztott bérleti díj                                         |
| 300160                | Mérleg | Mérleg szerinti eredmény                                     |
| 604500                | Expense       | Lízingköltség                                         |
| 604501                | Expense       | Jármű operatív lízingköltség – kamatakkreáció  |
| 604502                | Expense       | Jármű operatív lízingköltség – amortizáció        |
| 605200                | Expense       | Épület operatív lízingköltség – kamatakkreáció |
| 605201                | Expense       | Épület operatív lízingköltség – amortizáció       |
| 607101                | Expense       | Jármű lízingamortizációs költség                    |
| 607102                | Expense       | Épület lízingamortizációs költség                   |
| 607103                | Expense       | Értékvesztési költség – pénzügyi lízingek                   |
| 607104                | Expense       | Értékvesztési költség – Operatív lízingek                 |
| 618910                | Expense       | Lízingköltség – pénzügyi lízingek                        |
| 618920                | Expense       | Változó fizetések – pénzügyi lízingek                    |
| 618930                | Expense       | Változó fizetések – operatív lízingek                  |
| 800600                | Expense       | Jármű lízing kamatráfordítás                        |
| 800601                | Expense       | Épület lízing kamatráfordítás                       |
| 801201                | Mérleg | Nyereség és veszteség – lízingmódosítás                      |

## <a name="configure-posting-accounts"></a>Konfigurálja a feladási számlákat

Ha fiókokat szeretne hozzárendelni a létrehozott lízingkönyvekhez és csoportokhoz, konfigurálnia kell az Eszközlízing paramétereit.

1. Nyissa meg az **Eszközlízing \> Beállítás \> Lízing feladás paraméterei** lehetőséget.
2. A **Fiókok** fülön nyissa meg a **Lízingszámlák** gyorslapot. Határozza meg a fő számla pénzügyi és operatív lízingeinek a megfelelő **Feladási típusra**. Az előző tábla azokat a számlákat mutatja, amelyek az operatív és pénzügyi lízingekkel kapcsolatosak.

    > [!NOTE]
    > Ehhez a lépéshez külön számlákat kell beállítania mind az operatív, mind a pénzügyi lízingekhez minden egyes feladási típushoz, kivéve a **Lízingköltség-eltolást** és a **Lízingnövekedést/-csökkenést**. Az IFRS 16 számviteli keretrendszernek megfelelő vállalatoknak hozzá kell adniuk az operatív lízing fő számláját. De a rendszer nem fogja használni ezt a számlát annak ellenére, hogy ez egy kötelező mező, mert az IFRS 16 szerinti összes lízing pénzügyi lízingnek minősül.
    >[!NOTE]
    > **Lízingnövekedés/-csökkenés** további eszközszempontok feladási típusaként lesz használva, beleértve a **Kezdeti közvetlen költséget, a lízingösztönzőket, a lízingelőlegeket és a bontási költségeket**, de a használatijog-eszköz közötti eszköz fő számlájára kerül, amely alapértelmezett a **Lízingeszközre**.        
    
3. A fő számlának megfelelő adott lízingcsoport kiválasztásához a **Számlakód** mezőben válassza a **Csoport** lehetőséget. Ezután a **Számla/Csoport száma** mezőben válassza ki a fő számlához hozzárendelni kívánt lízingcsoportot.
4. Ha számlakódokat szeretne hozzárendelni a rendszerben beállított adminisztratív költségekhez, a **Működési költségek** gyorslapon a **Költség típusa** mezőben válasszon ki egy költséget. Ezután rendelje hozzá az egyes könyvekhez használt pénzügyi és működési számlákat.

    > [!NOTE]
    > A kiválasztott pénzügyi vagy működési számla az ütemezett költség számlájának feladásakor lesz megterhelve.
    > **Lízingköltség-eltolás** a működési költségtranzakciók feladási típusaként lesz használva, de feladja a meghatározott **Ellenszámlára** a **Működési költségek fizetési ütemezési soraiban** a lízing részleteiben vagy a lízingkönyv képernyőn.   


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
