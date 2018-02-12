---
title: "Munkaidő és jelenlét távollét regisztrálása"
description: "Ez a témakör bemutatja, hogyan kezelje a távollét-regisztrációkat a munkaidő-nyilvántartásban."
author: johanhoffmann
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: JMGParameters
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 477724e6211a084638e8a0b7133f60edef07b3ad
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="absence-registration-in-time-and-attendance"></a>Munkaidő és jelenlét távollét regisztrálása

[!include[banner](../includes/banner.md)]

Ez a témakör bemutatja a távolléti koncepciókat, és azt, hogyan kezelje a távollétet a munkaidő-nyilvántartásban.

## <a name="absence-that-is-based-on-regular-work-hours"></a>Távolléti, amely a normál munkaidőre alapul.

A dolgozók távollevőnek számítanak minden óra esetében, amelyet a normál munkaórákban nem dolgoznak le. A dolgozói időprofilbeállításban határozható meg a munkaidő.

A dolgozó dolgozhat olyan napi profillal, amelyben a kezdés 7:00 óra, a távozás pedig 15:00 óra. Ha a dolgozó érkezéskori blokkolása 9:00 óra, távollevőnek minősül 7:00 óra és 9:00 óra között az adott napon.

Ebben az esetben a dolgozónak meg kell adnia a távollét okát. A távollét kódjának kiválasztásával megadhatja az okot.

## <a name="absence-codes"></a>Távollétkódok

A távolléti kódok meghatározzák a különböző típusú távolléteket. A távolléti kódokat a cég határozza meg.

A távollétkódokra különböző szabályok alkalmazhatók. Például egy távolléti kód levonandó vagy fizetési támogatásként is beállítható.

Például a vállalat meghatározza a **Késés** távolléti kód, amelyet a dolgozók akkor használnak, ha késnek, és a nem rendelkeznek rá megfelelő okkal. A vállalat egy **Belső tanfolyam** távolléti kódot is meghatároz, amelyet a belső tanfolyamokon való részvételhez használnak a dolgozók. A távolléti kódok úgy állíthatók be, hogy a **Késés** levon a dolgozó fizetéséből, de a **Belső tanfolyam** nem.

Automatikus távolléti kódok állíthatók be. A távollétkódok egy dolgozó idejének a kiszámítására használhatók, ha nincs távollét regisztrálva. A dolgozói időprofil határozza meg, hogy a távolléti kód a normál munka időhöz vagy a rugalmas időhöz használatos.

### <a name="set-up-standard-time-and-flex-time"></a>A normál munkaidő és a rugalmas idő beállítása

- A normál munkaidő és a rugalmas idő paramétereinek beállításához használja a **Távollét automatikus beillesztése** és a **Rugalmas idő automatikus beillesztése** lehetőségeket a **Munkaidő és jelenlét paraméterei** lapon.

## <a name="absence-groups"></a>Távollétcsoportok

A távollétcsoportok a távolléti kódok csoportjai. A távollétcsoportokat a közös jellemzőkkel rendelkező távollétkódok csoportosítására használhatja. A példák közé tartozik többek között a szabályos távollét kódjai, vagy a távollét orvos vizsgálat, esküdtszéki kötelezettség vagy beteg gyermek miatt.

## <a name="planned-absence"></a>Tervezett távollét

Ha tudja, hogy a dolgozó távol lesz egy időszakra, például egy közelgő szabadság miatt, a tervezett távollétet használhatja. A tervezett távollét beállításához a távolléti kódot úgy kell beállítani, hogy figyelembe vegye a tervezett távollétet. Tervezett távollét beállításakor a rendszer nem kér távolléti kódot a felhasználói időregisztrációk számításakor a távolléti időszak alatt. Tervezett távollétet meg lehet adni egy dolgozóra, vagy megadhat egy kötegelt feladatot a dolgozók tervezett távollétének tömeges frissítéséhez.

### <a name="set-up-planned-absence"></a>Tervezett távollét beállítása

1. Válassza ki az **Emberi erőforrások** &gt; **Dolgozók** &gt; **Alkalmazottak** elemet, és válasszon ki egy alkalmazottat.
2. Válassza az **Idő** &gt; **Idő-hozzárendelések** &gt; **Távollét regisztrálása** elemet, és végezze el a tervezett távollét beállítását.

## <a name="interrupted-planned-absence"></a>Megszakított tervezett távollét

Ha a tervezett távollét beállítása során a **Megszakítás** beállítást alkalmazza, a tervezett távollét megszakad, ha a dolgozó bejelentkezik a tervezett távolléti időszak alatt. A tervezett távollét megjelölése **Megszakítva** lesz, és nem lesz hatással a jövőbeli számításokra.

### <a name="set-up-a-planned-absence-for-interruption"></a>Tervezett távollét megszakításának beállítása

1. Nyissa meg a **Távollét regisztrálása** oldalt a tervezett távollét beállításának folyamatában leírtak szerint.
2. Válassza a **Megszakítás** lehetőséget.

A **Megszakítás** lehetőség akkor érvényes, ha az üzemirányítási terminálon vagy az üzemirányítási eszközön időt regisztrálnak. A beállítás nem érvényes, ha a regisztrációkat beírják a számítási és a jóváhagyási lapon, vagy az **Elektronikus időkártya** oldalon.

## <a name="examples-of-the-use-of-absence-in-a-flex-profile"></a>Példák a távollét rugalmasidő-profilban való használatára

Az alábbi három példa bemutatja a távollét számítási módját egy olyan profilban, amely rendelkezik rugalmasidő-időszakokkal.

A példák a következő profilt használják.

| Érkezéskori blokkolás | Szokásos idő    | Szünet             | Szokásos idő | Rugalmasidő-hiány        | Távozáskori blokkolás | Rugalmasidő-többlet        |
|----------|------------------|-------------------|---------------|--------------|-----------|--------------|
| 08:00     | 09:00–11:30 | 11:30–12:00 | 12:00–15:00 | 15:00–16:00 | 16:00      | 16:00–18:00 |

### <a name="example-1-signing-out-during-a-flex--period"></a>1. példa: Rugalmasidő-hiány időszakban való kiblokkolás

A dolgozó 08:00 órakor blokkol be, és 15:30 órakor blokkol ki. Ebben az esetben, mivel a dolgozó távozáskori blokkolása a rugalmasidő-hiány időszakban történik, nem történik távollét számítása, és a dolgozó rugalmasidő-egyenlegből fél óra lesz levonva.

### <a name="example-2-signing-out-in-during-standard-time-period"></a>2. példa: Kiblokkolás a szokásos munkaidő alatt

A dolgozó 08:00 órakor blokkol be, és 14:30 órakor blokkol ki. Ebben az esetben, mivel a dolgozó távozáskori blokkolása a szokásos időszakon belüli, távollét számítása történik 14:30 és 16:00 között, és 1,5 órás távolléti időszak lesz regisztrálva. Az adott időszakra vonatkozó távollétkód megadása kötelező.

### <a name="example-3-signing-out-during-a-flex-period"></a>3. példa: Rugalmasidő-többlet időszakban való kiblokkolás

A dolgozó 08:00 órakor blokkol be, és 16:30 órakor blokkol ki. Ebben az esetben, mivel a dolgozó távozáskori blokkolása a rugalmasidő-többlet időszakban történik, nem történik távollét számítása, és a dolgozó rugalmasidő-egyenlegéhez fél óra lesz hozzáadva.

## <a name="absence-in-the-calculation-and-approval-process"></a>Távollét a számítási és jóváhagyási folyamatban

A dolgozó időregisztrációt ki kell számítani és jóvá kell hagyni, mielőtt át lehetne vinni a bérrendszerbe fizetési tételekként.

A jóváhagyó módosíthatja a dolgozó időregisztrációit. A jóváhagyó bármilyen, a dolgozó által regisztrált távollétet is módosíthat. Ha a jóváhagyó kézzel beír egy időszakot, amelynek távolléti kódja van, az adott időszakra vonatkozó távolléti kódot nem bírálja felül a munkaidő és jelenlét oldal paramétereinek alapértelmezett távolléti kódja.

Például egy dolgozó 10:00 órakor blokkol be, és kiválaszt egy távolléti kódot, amely azt jelzi, hogy késik. Később a dolgozó tájékoztatja a felettesét, hogy 08:00 és 10:00 között orvosnál volt. Az orvos vizsgálat nem okozhat levonást a dolgozó fizetéséből. Ezért ebben az esetben a felügyelő módosíthatja a két órás távollétet 08:00 és 10:00 között kézzel beírva egy távolléti kódot, amely azt jelzi, hogy a két óra oka betegség volt.

### <a name="calculate-and-approve-absence"></a>Távollét kiszámítására és a jóváhagyása

- Válassza ki a **Munkaidő és jelenlét** &gt; **Ellenőrzés és jóváhagyás** &gt; **Jóváhagyás vagy Számítás** lehetőséget.

