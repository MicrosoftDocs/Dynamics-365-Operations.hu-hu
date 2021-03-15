---
title: Szállítmányok automatikus frissítései
description: Ez a témakör áttekintést nyújt azokról a funkciókról, amelyekhez automatikus frissítést biztosítanak a szállítmányok számára.
author: josaw1
manager: tfehr
ms.date: 11/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWaveTemplateTable,SalesTableListPage,SalesTable,WHSWaveTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 1f75e9421ab9cac0b62e1cdee17ecf74796783cc
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001224"
---
# <a name="shipment-auto-updates"></a>Szállítmányok automatikus frissítései

[!include [banner](../includes/banner.md)]

A szállítmány automatikus frissítése funkcióval automatikusan frissítheti a szállítmányhoz kapcsolódó terhelési sor mennyiségeit (a növekményeket és a csökkentéseket is), miután a rakományt a raktárba bocsátották. Ez a funkció mindaddig be van kapcsolva, amíg a szállítmány vagy a rakomány terhelési sora fel nem dolgozza a hullámot. Amikor használatban van, a rendelések frissítései a raktárba történő automatikus átvezetéshez nem szükséges manuális beavatkozás, amíg a raktári munka létre nem jön.

Amikor a szállítmány automatikus frissítése funkció nincs használatban, csak a mennyiség csökken automatikusan, amíg a raktári munka létre nem jön. A felhasználóknak manuálisan kell frissíteniük vagy törölniük a sorokat, majd újra ki kell adniuk a sorokat, ha a rendelési mennyiségek növekednek, vagy új rendelési sorok vannak hozzáadva. A szállítmányok automatikus frissítése funkció használatával a vállalatok zökkenőmentesen biztosíthatják a raktár frissítését anélkül, hogy aggódni kellene azzal kapcsolatosan, hogy a rakományok nem tükrözik a rendelési sorok frissítéseit.

A szállítmányok automatikus frissítése funkció az értékesítésirendelés-sorokra és az átmozgatásirendelés-sorokra egyaránt vonatkozik, és egy adott raktárhoz van bekapcsolva. Ennélfogva a vállalatok igény szerint különböző automatikus szállítmányfrissítési szabályokat alkalmazhatnak a raktárak között. Alapértelmezetten a szállítmányok automatikus frissítésének irányelvei a mennyiségcsökkenésekre automatikusan alkalmazva van minden raktárra, amely raktárkezelési folyamatokat alkalmaz. Ha ez az alapértelmezett irányelv-beállítás van használatban, akkor csak a mennyiségcsökkenés jut el egy szállítmányhoz és rakományhoz, amíg nincs létrehozva a raktári munka. Ez a viselkedés hasonlít a szállítmányok automatikus frissítése funkció bevezetése előtt alkalmazott viselkedésre.

## <a name="main-elements-of-the-functionality"></a>A funkció fő elemei

A szállítmányok automatikus frissítése funkció elsősorban a szállítmány állapotára alapoz annak meghatározására, hogy a rakománysorban szereplő mennyiséget módosítani kell-e egy értékesítésirendelés-sorban vagy az átmozgatási rendelési sorban. Elsősorban a szállítmány állapotán alapul annak meghatározása, hogy mikor kell automatikusan új rakománysort adni egy meglévő rakományhoz. Ha a szállítmány állapota **Hullámba sorolva** vagy magasabb, akkor nem történik automatikus frissítés.

Az automatikus frissítések esetében is figyelembe van véve a hullám állapota. Amikor a rakománysorhoz kapcsolódó hullám állapota **Várakoztatva**, **Végrehajtás folyamatban**, **Kiadva**, **Kitárolva** vagy **Kiszállítva**, ha egy felhasználó megpróbálja csökkenteni a mennyiséget egy terhelési soron (az értékesítési rendelési sor vagy az átviteli rendelési sor mennyiségi csökkentésével), a következő hibaüzenet jelenik meg: „A foglalások nem távolíthatók el, mert létezik a foglalásokon alapuló munka”. Ezenkívül amikor a hullám a korábban említett hullám-állapotok egyikével rendelkezik, ha a felhasználó indirekt módon megpróbálja növelni a rakománysor terhelését azáltal, hogy növeli a mennyiséget az értékesítési rendelés sorában, a rakománysorban található mennyiség nem növekszik automatikusan. Ebben az esetben a rakománysort manuálisan kell frissíteni.

## <a name="scenarios"></a>Esetek

A szállítmány automatikus frissítése funkció négy esetet támogat: új rendelési sor hozzáadása, egy rendeléssor mennyiségének növelése, egy rendelési sorban szereplő mennyiség csökkentése és egy rendelési sor eltávolítása.

- **Új rendelési sor létrehozása** – Amikor a **Szállítmány automatikus frissítése** mezőben a **Raktárak** gyorslapon a **Raktárak** oldalon (**Raktárkezelés \> Beállítások \> Raktár \> Raktárak**) **Mindig** értékre van állítva, ha van szállítmány a rendeléshez, és egy új rendelési sort ad hozzá egy értékesítési rendeléshez vagy átmozgatási rendeléshez, miután az értékesítési rendeléshez már létrehoztak egy rakományt a meglévő rakomány nem frissül. Létrejön egy új rakománysor, amely nem hivatkozik a meglévő rakományra, és a meglévő szállítmányhoz van társítva. Az új sor hozzáadódik a rakományhoz, és ki van adva.
- **Rendelési sorban szereplő mennyiség növelése** – Amikor a **Szállítmány automatikus frissítése** mező értéke **Mindig**, ha a rendeléshez létezik szállítmány, és egy meglévő értékesítésirendelés-sorban vagy átmozgatási rendelési sorban szereplő mennyiség megnő, miután már létrehoztak egy rakományt az értékesítési rendeléshez, a a rakománysor ugyanazzal a mennyiséggel nő, mint a rendelési sor. Ha a rakomány ki lett adva, de nem jött létre munka, akkor a program a rendelési sor összegével megegyező mennyiséggel növeli a rakománysort.
- **Rendelési sorban szereplő mennyiség csökkentése** – Amikor a **Szállítmány automatikus frissítése** mező értéke **Mindig** vagy a **Mennyiség csökkenése**, ha van szállítmány a rendeléshez, és egy meglévő értékesítésirendelési-sorban vagy átviteli rendelési sorban a mennyiség csökken, miután már lett rakomány létrehozva az értékesítési rendeléshez, a kapcsolódó rakománysor is ennek megfelelően frissül, hacsak a rakománysoron található már nem egyenlő vagy kisebb, mint az új mennyiség a rendelési soron. Ebben az esetben a rakománysor nem érintett. Ha a rakomány ki lett adva, de nem jött létre munka, akkor a kapcsolódó rakománysorban szereplő mennyiség frissítve lesz, hogy ehhez illeszkedjen, kivéve ha a rakomány sorban szereplő mennyiség már kisebb vagy egyenlő mint a rendelési sor új mennyisége. Ebben az esetben a rakománysor érintett.
- **Rendelési sor eltávolítása** – Amikor a **szállítmány automatikus frissítése** mező értéke **Mindig** vagy **Mennyiség csökkenésekor**, ha a felhasználó megpróbálja eltávolítani azt a rendelési sort, amelyhez meg van adva egy rakománysor, akkor egy hibaüzenet jelenik meg.

## <a name="example-scenario"></a>Példaforgatókönyv

Ennél a helyzetnél a demo adatokat kell telepíteni, és az **USMF** demó adatvállalatot kell használnia.

### <a name="turn-on-the-auto-update-shipment-functionality"></a>A szállítmány automatikus frissítése funkció bekapcsolása

A szállítmány automatikus frissítése funkció bekapcsolásához kövesse az alábbi lépéseket.

1. Ugorjon a **Raktárkezelés \> Beállítás \> Raktár \> Raktárak** pontra.
2. Válasszak ki a **24.** raktárt.
3. A **Raktár** gyorslap **Szállítmány automatikus frissítése** mezőjében módosítsa az értéket **Érték csökkenésekor** helyett **Mindig** értékre.

Miután az értéket **Mindig** értékre módosította az értékesítésirendelés-sorokban és az átmozgatási rendelés soraiban szereplő mennyiségek növekményei vagy csökkenése, valamint az új sorok hozzáadása a kiválasztott raktárhoz tartozó szállítmányokon és rakományokon tükröződik, a korábban említett kényszerített frissítéseknek megfelelően.

### <a name="change-the-wave-template-so-that-load-lines-arent-automatically-processed"></a>A hullám sablon módosítása annak érdekében, hogy a rakománysorok ne kerüljenek automatikusan feldolgozásra

Ha azt szeretné, hogy a hullámsablon ne dolgozza fel automatikusan a terhelési sorokat, hajtsa végre az alábbi lépéseket.

1. Ugorjon a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámsablonok** pontra.
2. Válassza a **24 Szállítási alapértelmezés** hullámsablont.
3. Válassza ki a **Szerkesztés** opciót.
4. Az **Általános** gyorslapon állítsa be a **Hullám-létrehozás automatizálása** beállítást **Igen** értékre, és győződjön meg róla, hogy minden egyéb beállítás **Nem** értékre van állítva.

Fontos, hogy a hullám-létrehozási folyamat részeként a program nem hozza létre és ad ki automatikusan munkát. Az értékesítési rendelés sorához létrehozott rakománysorral kapcsolatos munka létrehozása után, a program nem frissíti automatikusan a rakománysort, ha módosul az értékesítésirendelés-sorban szereplő mennyiség.

### <a name="create-a-sales-order"></a>Értékesítési rendelés létrehozása

Értékesítési rendelés létrehozásához kövesse az alábbi lépéseket.

1. Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.
2. Válassza ki az **US-003** számú vevőt.
3. Hozzon létre egy sort az **A0001** cikkszámhoz.
4. Adja meg a **10** mennyiséget. (Ügyeljen arra, hogy a **24.** raktárat használja.)
5. Válassza a **Mentés** lehetőséget.
6. Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Műveletek** csoportjának **Kiadás raktárba** parancsát. Létrejön egy szállítmány és egy hullám.

Mivel megváltoztatta a hullám sablonját az előző eljárásban, nem jön létre rakomány vagy munka. A szállítmány állapota **Nyitott**, és a hullám állapota **Létrehozva**.

### <a name="decrease-the-quantity-on-a-sales-order-line"></a>Az értékesítési rendeléssoron szereplő mennyiség csökkentése

Ha csökkenteni szeretné az értékesítésirendelés-sorban szereplő mennyiséget, hajtsa végre az alábbi lépéseket.

1. Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.
2. Válassza ki azt az értékesítési rendelést, amelyet most adott ki a raktárba.
3. Jelölje ki az értékesítésirendelés-sort. A **Mennyiség** mezőben módosítsa az értéket erről: **10**, erre: **8**.
4. Válassza ki az értékesítési rendelés sorában a **Raktár \> Szállítmány adatai** lehetőséget. A **Szállítmány részletei** lap **Rakománysorok** gyorslapján a mennyiség tükrözi az értékesítésirendelés-sor változását.

### <a name="increase-the-quantity-on-a-sales-order-line"></a>Az értékesítési rendeléssoron szereplő mennyiség növelése

Ha növelni szeretné az értékesítésirendelés-sorban szereplő mennyiséget, hajtsa végre az alábbi lépéseket.

1. Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.
2. Válassza ki azt az értékesítési rendelést, amelyet korábban adott ki a raktárba.
3. Módosítsa a sor mennyiségét **8**-ról **12**-re.
4. Válassza a **Mentés** lehetőséget.
5. Térjen vissza az **Összes értékesítési rendelés** lapra, majd válassza ki újra az értékesítési rendelést.
5. A Művelet ablaktábla **Raktár** lapjának **Kapcsolódó információk** csoportjában válassza a **Szállítmány részletei** elemet. A **Szállítmány részletei** lap **Rakománysorok** gyorslapján a mennyiség tükrözi az értékesítésirendelés-sor változását.

Annak ellenére, hogy a rakománysorban szereplő mennyiség 8-ról 12-re nőtt, csak nyolc cikk marad lefoglalva, kivéve ha az automatikus foglalás be van kapcsolva. Mivel a meglévő szállítmányhoz hozzáadott mennyiséget nem foglalta le a program, ha a hullám feldolgozása ezen a ponton történik, foglalás nélkül, csak a már lefoglalt mennyiséghez jön létre munka.

> [!NOTE]
> Ha egy rendelési sorban szereplő mennyiség csökken, az nem befolyásolja a rakománysorban szereplő mennyiséget, ha az egyenlő vagy kisebb, mint az új mennyiség a rendelési sorban. Amikor egy rendelési sor mennyiségét megnövelik, a program a rendeléssor összegével megegyező mennyiséggel növeli a rakománysor értékét. Ha a rendelési sorban szereplő mennyiség eltér a rakománysorban szereplő mennyiségtől, akkor a különbség továbbra is fennáll.

### <a name="add-a-sales-order-line"></a>Értékesítési rendelési sor hozzáadása

Értékesítési rendelési sor hozzáadásához tegye a következőket.

1. Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.
2. Válassza ki azt az értékesítési rendelést, amelyet korábban adott ki a raktárba.
3. Hozzon létre egy sort az **A0002** cikkszámhoz.
4. Írja be a **10** értéket a **Mennyiség** mezőbe. (Ügyeljen arra, hogy a **24**. raktárat használja.) Az új sor automatikusan hozzáadódik a meglévő szállítmányhoz.
5. Válassza a **Mentés** lehetőséget.
6. Térjen vissza az **Összes értékesítési rendelés** lapra, majd válassza ki újra az értékesítési rendelést.
7. A Művelet ablaktábla **Raktár** lapjának **Kapcsolódó információk** csoportjában válassza a **Szállítmány részletei** elemet. A **Szállítmány részletei** oldalon a **Rakománysorok** gyorslapon figyelje meg a második sort.

Mivel a meglévő szállítmányhoz hozzáadott értékesítésirendelés-sor nem lett lefoglalva, ha a hullám feldolgozása ezen a ponton történik, a munka csak az első értékesítésirendelés-sorban és az első rakománysorban szereplő mennyiséghez jön létre.

### <a name="process-a-wave"></a>Egy hullám feldolgozása

Egy hullám feldolgozásához kövesse az alábbi lépéseket.

1. Ugorjon a **Raktárkezelés \> Kimenő hullámok \> Szállítmányhullámok \> Minden hullám** menübe.
2. Válassza ki a korábban létrehozott hullámot.
3. A Műveleti ablaktáblán a **Hullám** lapon a **Hullám** csoportban válassza a **Folyamat** lehetőséget.

A hullám feldolgozásra kerül, és létrehoz egy munkát a rakománysorokban foglalt mennyiségekhez. A szállítmány állapota a **Nyitott** értékről **Hullámba sorolva** értékre módosul. Mivel a szállítmány állapota **Hullámba sorolva** értékre módosult minden változás, például a sorokban szereplő mennyiségek csökkentése vagy növekedése, illetve az új sorok értékesítési rendeléshez való hozzáadása, nem befolyásolja a hullámba sorolt szállítmányhoz társított meglévő rakománysorokat.

Ha egy szállítmány **Hullámba sorolt** vagy magasabb állapotú, akkor az értékesítésirendelés-sorban szereplő mennyiség frissítése nem tükröződik a szállítmányhoz kapcsolódó rakománysorral szemben. A rakománysorban szereplő mennyiség változását közvetlenül a rakománysorban kell végrehajtani.

Az ellenőrzés a rakománysorhoz létrehozott munka és a foglalás után történik. Az értékesítésirendelés-sorban történő mennyiségcsökkenés ezt követően ellenőrizve lesz a munkasor foglalásához képest.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]