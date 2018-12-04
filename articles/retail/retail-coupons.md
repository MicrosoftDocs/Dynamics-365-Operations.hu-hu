---
title: "Kiskereskedelmi értékesítési utalványok beállítása"
description: "Ez a témakör a kiskereskedelmi utalványokat tekinti át, és bemutatja, hogyan állíthatja be őket."
author: scott-tucker
manager: AnnBe
ms.date: 05/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailCoupon, RetailParameters, RetailSharedParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 
ms.search.region: Global
ms.search.industry: retail
ms.author: scotttuc
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 5098fb3339403b6f2779dfe3bb7ef5c4ca78051f
ms.openlocfilehash: c718a71ca270c67118a90456bac0cf182032d3db
ms.contentlocale: hu-hu
ms.lasthandoff: 08/09/2018

---

# <a name="set-up-coupons-for-retail-sales"></a>Kiskereskedelmi értékesítési utalványok beállítása

[!include [banner](includes/banner.md)]

## <a name="overview-of-coupons"></a>Utalványok áttekintése

Az utalványok olyan kódok és vonalkódok, amelyek segítségével kiskereskedelmi engedményeket adnak hozzá a tranzakciókhoz. Az egyes utalványok több kóddal rendelkezhetnek, és minden kódnak saját érvényességi dátuma lehet. 

Minden egyes utalványhoz egy kiskereskedelmi engedmény kapcsolódik. Az engedményhez társított árcsoportok meghatározzák, hogy mely vevők használhatnak utalványt, vagy pedig azokat a csatornákat, ahol az utalvány érvényes. 

Az utalványok lényegében a kiskereskedelmi engedményeken túl további ellenőrzést biztosítanak. Az utalvány biztosítja a szükséges utalványkódokat és a vonalkódokat a kódok dátumtartományával együtt. Az utalvány emellett választható felhasználási korlátokat és a vevő által igényelt tulajdonságokat is nyújt. Az engedmény a termékkészletet tartalmazza, amelyre az utalvány érvényes. Az engedmény árcsoportjai megadják azon vevő- csatorna- vagy katalóguskészletet, amely az utalvány érvényes.

Utalvány létrehozásához külön hozza létre az engedményt és az utalványt. Ezután összekapcsolja őket a Microsoft Dynamics for Retail 365 utalványlapján levő engedmény kiválasztásával. 

> [!NOTE]
> Miután az utalvány egy engedmény van kapcsolva, a Microsoft Dynamics for Retail 365 engedménylapján több mező írásvédetté válik, mivel ezek az utalvány beállításaitól függnek. Idetartoznak az állapotjelző és a szokásos dátumtartományok mezői.

### <a name="limited-use-coupons"></a>Korlátozottan használható utalványok

Az utalványok korlátozottan használható utalványokként is konfigurálhatók. A felhasználási korlát ügyfelenként, csatornánként vagy globális korlátozásként adható meg. Ez a határérték a kód vagy a vonalkód pénztárba történő beírásakor vagy beolvasásakor vagy az értékesítési rendelés bevitele során lép érvénybe.

A korlát az utalványon levő utalványkódonként lép érvénybe. Például egy két utalványkódot tartalmazó egyszer felhasználható utalvány kétszer használható: egy-egy alkalommal minden egyes utalványkód esetében. Az utalvány minden kódját függetlenül lehet aktiválni.

> [!NOTE]
> Miután egy utalványkód elérte a felhasználási korlátját, a rendszer *nem* állítja át automatikusan az utalványkód állapotát „Használt”-ra. A rendszer azonban nem engedélyezi a továbbiakban a használati határát elértő utalványkód használatát. Ha az utalványkód állapota manuális beállítás mellett bármi más, mint az „Aktív”, semelyik csatornán sem használható az utalványkód.

## <a name="managing-coupons"></a>Utalványok kezelése

Külön kell létrehoznia az engedményt és az utalványt. Ezután összekapcsolja őket az utalványlapon levő engedmény kiválasztásával. Miután az utalványhoz egy engedményt kapcsolt, az engedményhez kapcsolódó több mező írásvédetté válik, mivel ezek az utalvány beállításaitól függnek. Idetartoznak az állapotjelző és a szokásos dátumtartományok mezői.  

Az utalványok most a kiskereskedelmi engedményeken túl további ellenőrzést biztosítanak. Az utalvány biztosítja a szükséges utalványkódokat és a vonalkódokat a kódok dátumtartományával, a felhasználási korláttal és az ügyfelek által igényelt tulajdonsággal együtt. Az engedmény a termékkészletet tartalmazza, amelyre az utalvány érvényes. Az engedmény árcsoportjai megadják azon vevő- csatorna- vagy katalóguskészletet, amely az utalvány érvényes.

## <a name="system-setup-for-coupons"></a>Rendszer beállítása az utalványok létrehozásához 

Utalvány beállítása előtt be kell állítania az utalvány vonalkódját és két utalványszám-sorozatot. 

1.  A **Maszkkarakterek** lapon hozzon létre egy új maszkkaraktert az utalványkódhoz. Itt bármilyen nem használt karaktert kiválaszthat.
2.  A **Vonalkódmaszk beállításai** lapon hozzon létre egy új vonalkódmaszkot. Állítsa a **Típus** mezőt **Utalvány** értékre.
3.  A **Vonalkód beállítása** lapon hozzon létre egy új vonalkódot, amely a most létrehozott vonalkódmaszkot használja.
4.  A **Számsorozatok** lapon hozzon létre két új számsorozatot. Egyik számsorozat az utalványkód azonosítója, a másik az utalványszám sorozata. Az utalványkód azonosítója az utalvány egyes utalványkódjainak egyedi azonosítója. Az utalványszám az utalvány egyedi azonosítója. Minden egyes utalványhoz több kód és vonalkód tartozhat, amelyek aktiválják az utalványt.

    > [!NOTE]
    > Mindkét számsorozat esetén a **Hatókör** mező **Vállalat** értékre kell állítani. A legtöbb esetben generálja automatikusan mindkét számsorozatot.

5.  A **Kiskereskedelmi paraméterek** lapon a **Vonalkódok** fülön válassza ki a korábban létrehozott vonalkódot.
6.  A **Kiskereskedelmi megosztott paraméterek** lapon a **Számsorozatok** fülön válassza ki az utalványszámhoz és az utalványazonosítóhoz létrehozott számsorozatot.
7.  Most megnyithatja az **Utalványok** lapot, és új utalványokat hozhat létre.

## <a name="the-effect-of-partial-updates-on-coupons"></a>Utalványok részleges frissítéseinek hatása

Az Utalvány funkció a Dynamics 365 for Retail alkalmazásban több különálló funkciót tartalmaz. A Microsoft Dynamics 365 Retail Headquarters (HQ) és a csatorna részben frissíthető az összetevők között. Ezért fontos megértenie, hogyan befolyásolják a részleges frissítések az utalvány egészének funkcióit.

- **A HQ részben frissül, de a Retail-kiszolgáló és a pénztár nem.** Egy HQ-frissítés során az utalvány- és engedménycsoportok lapjai frissülnek, és a kiskereskedelmi ármotor is frissül. Ha a kettő közül csak egy összetevő frissül, a Retail alkalmazás egyes lapjai nem egyeznek meg az árszámítási adatokkal. Emiatt nem várt engedmények vagy a hibák fordulhatnk elő az engedményszámítások során.
- **A HQ frissül, de a Retail-kiszolgáló és a pénztár nem (N-1).** Mivel nem minden kiskereskedelmi áruház frissíthető ugyanakkor, javasoljuk, hogy a kiskereskedelmi áruházak frissítése előtt a HQ-t frissítse. Az N-1 forgatókönyvben az utalványokhoz kapcsolódó új funkció nem érhető el a még nem frissített üzletek esetében. Például az utalványfunkció „kizárás” sorokat vezet be. Ha kizárandó sorokat használ egy engedményen, ezeket a rendszer nem alkalmazza őket arra a kiskereskedelmi áruházra, amelyen korábbi verzió fut.
- **A HQ nem frissül, de a Retail-kiszolgáló és a pénztár igen (N+1).** Mivel a Retail-kiszolgáló frissített ármotorja az árkalkulációk során kezelheti az örökölt engedménykódokat, a frissítésnek nem kellene funkcionális hatása legyen ebben a forgatókönyvben.

